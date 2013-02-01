#Coding Conventions For Vlcchina
##NOTA BENE
The following conventions are the 'classical' VLC code conventions. Those are not enforced anymore.

The important is to keep consistency of codestyle when you modify a file.

If you write a new file, select your style. Common used styles are VLC Style and K&R. 

##Coding conventions
Here you find conventions about how the VLC media player developers write their code. 

###*Function naming*
All functions are named accordingly: module name (in lower case) + _ + function name (in mixed case, without underscores). For instance: intf_FooFunction. Static functions don't need the module name. 

###*variable naming*
We use Hungarian notation. That is, we have the following prefixes:

*    i_ for integers (sometimes l_ for long integers)
*    b_ for booleans
*    d_ for doubles
*    f_ for floats
*    Generally, we add a p when the variable is a pointer to a type
*        pf_ for function pointers
*        psz_ for a pointer to a string terminated by a zero (C-string) 

If a variable has no basic type (for instance a complex structure), don't put any prefix (except p_ if it's a pointer). After one prefix, put an explicit variable name in lower case. If several words are required, join them with an underscore (no mixed case).

Examples:

*    data_packet_t * p_buffer
*    char psz_msg_date[42]
*    int pi_es_refcount[MAX_ES];
*    void (* pf_next_data_packet)( int * ) 

###*A few words about white sapce*
####Indention
*Never* use tabs in the source (nevertheless you're entitled to use them in the Makefile :-).

Use set expandtab under vim or the equivalent under emacs.

Indents are 4 spaces long. 

####Spaces
Put spaces before and after operators, and inside brackets. For instance: 

`for( i = 0; i < 12; i++, j += 42 );`

####Braces
Leave braces alone on their lines (GNU style[1](http://www.gnu.org/prep/standards/standards.html)). For instance: 

>if( i_es == 42 )

>{

>   p_buffer[0] = 0x12;

>}

###*Comments*
ANSI C-style comments /* ... */ are more commonly used for historical reasons, though C++/C99 comments are tolerated, but please don't mix both in the same file. 

##Qt interface added conventions
    See [HACKING](http://git.videolan.org/?p=vlc.git;a=blob;f=modules/gui/qt4/HACKING).


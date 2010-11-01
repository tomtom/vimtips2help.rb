vimtips2help.rb -- Convert vimtips from wikia to vim help files
===============================================================

This ruby script converts wiki dumps that you can download from 
wikia.com to an almost properly formatted and tagged vim help file.

Minimal Makefile:

    vimtips.xml:
        cd ~/.vim/tmp; \
        wget http://wikistats.wikia.com/v/vi/vim/pages_current.xml.gz; \
        gunzip pages_current.xml.gz

    vimtips.txt:
        cd ~/.vim; \
            vimtips2help.rb --xml tmp/pages_current.xml --out doc/vimtips.txt -v -m "*´"; \
            vim -u NONE -U NONE -c "helptags doc" -c q

    vimtips: vimtips.xml vimtips.txt


MAIN := tesi
BUILD_DIR := .\

default: full

start:
	@echo --------------------------------------------------------------
	@echo -                            Init                            -
	@echo --------------------------------------------------------------

full:
	@make start
	@make clean
	mkdir -p $(BUILD_DIR)
	pdflatex -shell-escape tesi.tex
	@make bib
	@make gloss
	pdflatex -shell-escape tesi.tex
	@make bib
	@make gloss
	@make generating
	pdflatex -shell-escape tesi.tex
	pdflatex -shell-escape tesi.tex
	@make end

bib:
	@echo --------------------------------------------------------------
	@echo -                     Update Bibliography                    -
	@echo --------------------------------------------------------------
	biber tesi

gloss:
	@echo --------------------------------------------------------------
	@echo -                   Aggiornamento Glossario                  -
	@echo --------------------------------------------------------------
	makeindex -s $(MAIN).ist -t $(MAIN).glg -o $(MAIN).gls $(MAIN).glo

generating:
	@echo --------------------------------------------------------------
	@echo -                        Generating...                       -
	@echo --------------------------------------------------------------

end:
	@echo ----------------------------END-------------------------------

clean:
	@echo --------------------------------------------------------------
	@echo -                          Clean                             -
	@echo --------------------------------------------------------------
	rm -f *.sc
	rm -f *.acn
	rm -f *.acr
	rm -f *.alg
	rm -f *.aux
	rm -f *.bbl
	rm -f *.bcf
	rm -f *.blg
	rm -f *.glg
	rm -f *.glo
	rm -f *.gls
	rm -f *.ist
	rm -f *.lof
	rm -f *.log
	rm -f *.lot
	rm -f *.pdf
	rm -f *.run
	rm -f *.synctex
	rm -f *.toc
	rm -f *.xml

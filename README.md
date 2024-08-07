# Define the color scheme
set colors(bg) "#ECEFF4"
set colors(bg_secondary) "#E5E9F0"
set colors(bg_highlight) "#D8DEE9"
set colors(fg) "#2E3440"
set colors(fg_secondary) "#3B4252"
set colors(fg_highlight) "#4C566A"
set colors(accent) "#5E81AC"
set colors(accent_hover) "#81A1C1"
set colors(accent_active) "#88C0D0"
set colors(border) "#D8DEE9"
set colors(border_focus) "#5E81AC"
set colors(border_disabled) "#E5E9F0"
set colors(button_bg) "#88C0D0"
set colors(button_fg) "#2E3440"
set colors(button_hover_bg) "#81A1C1"
set colors(button_active_bg) "#5E81AC"
set colors(input_bg) "#E5E9F0"
set colors(input_fg) "#2E3440"
set colors(input_border) "#D8DEE9"
set colors(alert_success_bg) "#A3BE8C"
set colors(alert_success_fg) "#2E3440"
set colors(alert_warning_bg) "#EBCB8B"
set colors(alert_warning_fg) "#2E3440"
set colors(alert_error_bg) "#BF616A"
set colors(alert_error_fg) "#2E3440"

# Create the main window
ttk::style configure TFrame -background $colors(bg)
ttk::style configure TLabel -background $colors(bg) -foreground $colors(fg)
ttk::style configure TButton -background $colors(button_bg) -foreground $colors(button_fg) -padding 6 -relief flat
ttk::style map TButton -background {active $colors(button_active_bg) pressed $colors(button_active_bg) focus $colors(accent_active)}
ttk::style configure TEntry -fieldbackground $colors(input_bg) -foreground $colors(input_fg) -relief solid -padding 6
ttk::style configure TCheckbutton -background $colors(bg) -foreground $colors(fg)
ttk::style configure TRadiobutton -background $colors(bg) -foreground $colors(fg)
ttk::style configure TCombobox -fieldbackground $colors(input_bg) -foreground $colors(input_fg) -relief solid -padding 6
ttk::style configure TSpinbox -fieldbackground $colors(input_bg) -foreground $colors(input_fg) -relief solid -padding 6
ttk::style configure TLabelframe -background $colors(bg) -foreground $colors(fg) -padding 10
ttk::style configure TLabelframe.Label -background $colors(bg) -foreground $colors(fg)
ttk::style configure Treeview -background $colors(bg_secondary) -foreground $colors(fg) -fieldbackground $colors(bg_secondary)
ttk::style configure Treeview.Heading -background $colors(bg_highlight) -foreground $colors(fg_highlight)
ttk::style configure TNotebook -background $colors(bg)
ttk::style configure TNotebook.Tab -background $colors(bg) -foreground $colors(fg)
ttk::style configure Horizontal.TScrollbar -background $colors(border)
ttk::style configure Vertical.TScrollbar -background $colors(border)
ttk::style configure TProgressbar -background $colors(accent)
ttk::style configure TSeparator -background $colors(border)
ttk::style configure TSizegrip -background $colors(bg_secondary)

# Create a sample GUI
ttk::frame .frame -padding "10 10 10 10"
grid .frame -column 0 -row 0 -sticky "nwes"

ttk::label .frame.label -text "Hello, World!"
grid .frame.label -column 0 -row 0 -pady 5

ttk::button .frame.button -text "Click Me"
grid .frame.button -column 0 -row 1 -pady 5

ttk::entry .frame.entry
grid .frame.entry -column 0 -row 2 -pady 5

ttk::checkbutton .frame.check -text "Check Me"
grid .frame.check -column 0 -row 3 -pady 5

ttk::radiobutton .frame.radio -text "Option 1" -value 1 -variable option
grid .frame.radio -column 0 -row 4 -pady 5

ttk::combobox .frame.combo -values {Option1 Option2 Option3}
grid .frame.combo -column 0 -row 5 -pady 5

ttk::spinbox .frame.spin -from 0 -to 10
grid .frame.spin -column 0 -row 6 -pady 5

ttk::labelframe .frame.labelframe -text "Group"
grid .frame.labelframe -column 0 -row 7 -pady 5

ttk::notebook .frame.notebook
grid .frame.notebook -column 0 -row 8 -pady 5

ttk::treeview .frame.tree -columns {Name Age}
grid .frame.tree -column 0 -row 9 -pady 5

ttk::progressbar .frame.progress
grid .frame.progress -column 0 -row 10 -pady 5

# Add contents to the labelframe
ttk::label .frame.labelframe.label -text "Inside Group"
grid .frame.labelframe.label -column 0 -row 0 -pady 5

# Add tabs to the notebook
ttk::frame .frame.notebook.tab1
ttk::frame .frame.notebook.tab2
.frame.notebook add .frame.notebook.tab1 -text "Tab 1"
.frame.notebook add .frame.notebook.tab2 -text "Tab 2"

# Add items to the treeview
.frame.tree heading Name -text "Name"
.frame.tree heading Age -text "Age"
.frame.tree insert {} end -values {"Alice" 30}
.frame.tree insert {} end -values {"Bob" 25}

# Start the main loop
tk::mainloop
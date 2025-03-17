Still attempting to combine a video selection UI, written in LVGL code, with the AviPlayer from moononournation, written using Arduino_GFX.
At present, the program crashes when the selected video file is handed over to the AviPlayer, probably due to memory conflicts.

For example:
14:29:54.846 -> Rebooting...
14:29:54.846 -> ESP-ROM:esp32s3-20210327
14:29:54.846 -> Build:Mar 27 2021
14:29:54.893 -> rst:0xc (RTC_SW_CPU_RST),boot:0x28 (SPI_FAST_FLASH_BOOT)
14:29:54.893 -> Saved PC:0x4037ab32
14:29:54.893 -> SPIWP:0xee
14:29:54.893 -> mode:DIO, clock div:1
14:29:54.893 -> load:0x3fce2820,len:0x1188
14:29:54.893 -> load:0x403c8700,len:0x4
14:29:54.893 -> load:0x403c8704,len:0xbf0
14:29:54.893 -> load:0x403cb700,len:0x30e4
14:29:54.893 -> entry 0x403c88ac
14:29:55.097 -> Bagpuss Episode Player Starting
14:29:55.522 -> 1 selected
14:55:44.921 -> Touchpad pressed: x=269, y=186
14:55:45.007 -> Touchpad pressed: x=269, y=186
14:55:45.054 -> Touchpad pressed: x=269, y=186
14:55:45.090 -> 2 selected
14:55:45.178 -> Touchpad pressed: x=272, y=161
14:55:45.178 -> 2 selected
14:55:45.273 -> Touchpad pressed: x=276, y=113
14:55:45.359 -> Touchpad pressed: x=291, y=67
14:55:45.884 -> 10 selected
14:55:46.117 -> Touchpad pressed: x=251, y=308
14:55:46.196 -> Touchpad pressed: x=251, y=308
14:55:46.243 -> Touchpad pressed: x=251, y=308
14:55:46.324 -> Touchpad pressed: x=251, y=308
14:55:46.324 -> Prepare to play episode 10
14:55:46.414 -> [Warn]	(1551.340, +1551340)	 lv_init: lv_init: already inited 	(in lv_obj.c line #102)
14:55:46.461 -> [Warn]	(1551.375, +35)	 lv_obj_del: the active screen was deleted 	(in lv_obj_tree.c line #72)
14:55:46.461 -> Completed LVGL shutdown routine
14:55:46.920 -> Completed video setup routine
14:55:47.451 -> Preparing to play episode 10
14:55:47.451 -> avi_open(/root/avi320x480/BP10.avi)
14:55:48.000 -> AVI avi_total_frGuru Meditation Error: Core  1 panic'ed (StoreProhibited). Exception was unhandled.
14:55:48.346 -> 
14:55:48.346 -> Core  1 register dump:
14:55:48.346 -> PC      : 0x420319b7  PS      : 0x00060530  A0      : 0x82081ced  A1      : 0x3fca7800  
14:55:48.346 -> A2      : 0x3fc9fbac  A3      : 0x0000002a  A4      : 0x00000010  A5      : 0x0000014f  
14:55:48.346 -> A6      : 0x00000000  A7      : 0x00000000  A8      : 0x851c469a  A9      : 0x0d3650e8  
14:55:48.346 -> A10     : 0x3fca2878  A11     : 0x00000000  A12     : 0x00000000  A13     : 0x00060723  
14:55:48.346 -> A14     : 0x00000001  A15     : 0x3fca2824  SAR     : 0x00000008  EXCCAUSE: 0x0000001d  
14:55:48.346 -> EXCVADDR: 0x851c469a  LBEG    : 0x40056f5c  LEND    : 0x40056f72  LCOUNT  : 0xffffffff  
14:55:48.346 -> 
14:55:48.346 -> 
14:55:48.346 -> Backtrace: 0x420319b4:0x3fca7800 0x42081cea:0x3fca7820 0x4208189b:0x3fca7840 0x420816f7:0x3fca7860 0x420305e3:0x3fca7890 0x42030609:0x3fca78b0 0x42002fc6:0x3fca78d0 0x42003155:0x3fca7990 0x42042d10:0x3fca79b0 0x4037e922:0x3fca79d0
14:55:48.346 -> 
14:55:48.346 -> 


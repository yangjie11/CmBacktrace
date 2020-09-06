from building import *
import rtconfig

cwd     = GetCurrentDir()
src     = Glob('*.c')
path    = [cwd]

LOCAL_CCFLAGS = ''

if rtconfig.CROSS_TOOL == 'gcc':
    LOCAL_CCFLAGS += ' -std=c99'
elif rtconfig.CROSS_TOOL == 'keil':
    # Using ARM Compiler Version 5
    LOCAL_CCFLAGS += ' --c99'
    LOCAL_CCFLAGS += ' --no-multibyte-chars'
    # Using ARM Compiler Version 6
    # pass

group = DefineGroup('cm_backtrace', src, depend = ['PKG_USING_CMBACKTRACE'], CPPPATH = path, LOCAL_CCFLAGS = LOCAL_CCFLAGS)

Return('group')

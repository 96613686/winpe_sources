# NGenTaskLauncher.Logger::Log_0

- ea: `0x7d0`
- end: `0x831`
- name: `NGenTaskLauncher.Logger::Log_0`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1e0`
- `0x6a0`

## callees

- `0x7b0`
- `0x7d0`

## pseudocode

```c

```

## disassembly

```asm
0x7d0  ldarg.2
0x7d1  ldarg.3
0x7d2  call     string [mscorlib]System.String::Format(string, object[])
0x7d7  stloc.0
0x7d8  ldsfld   valuetype LogLevel NGenTaskLauncher.Logger::maxLogLevel
0x7dd  ldc.i4.3
0x7de  bge.s    loc_804
0x7e0  ldarg.0
0x7e1  ldstr    a0Hresult1// "{0} HRESULT({1})"
0x7e6  ldc.i4.2
0x7e7  newarr   [mscorlib]System.Object
0x7ec  dup
0x7ed  ldc.i4.0
0x7ee  ldloc.0
0x7ef  stelem.ref
0x7f0  dup
0x7f1  ldc.i4.1
0x7f2  ldarg.1
0x7f3  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForException(class [mscorlib]System.Exception)
0x7f8  box      [mscorlib]System.Int32
0x7fd  stelem.ref
0x7fe  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x803  ret
0x804  ldarg.0
0x805  ldstr    a0Hresult1Excep// "{0} HRESULT({1}) Exception Message \"{2"...
0x80a  ldc.i4.3
0x80b  newarr   [mscorlib]System.Object
0x810  dup
0x811  ldc.i4.0
0x812  ldloc.0
0x813  stelem.ref
0x814  dup
0x815  ldc.i4.1
0x816  ldarg.1
0x817  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForException(class [mscorlib]System.Exception)
0x81c  box      [mscorlib]System.Int32
0x821  stelem.ref
0x822  dup
0x823  ldc.i4.2
0x824  ldarg.1
0x825  callvirt instance string [mscorlib]System.Exception::get_Message()
0x82a  stelem.ref
0x82b  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x830  ret
```

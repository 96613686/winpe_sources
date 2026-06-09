# NGenTaskLauncher.Logger::.cctor

- ea: `0x760`
- end: `0x7a8`
- name: `NGenTaskLauncher.Logger::.cctor`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x760`
- `0x860`

## pseudocode

```c

```

## disassembly

```asm
0x760  ldc.i4.2
0x761  stsfld   valuetype LogLevel NGenTaskLauncher.Logger::maxLogLevel
0x766  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x76b  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x770  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x775  stloc.0
0x776  ldloc.0
0x777  ldstr    aNgen// "ngen"
0x77c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x781  ldc.i4.0
0x782  ldsflda  valuetype LogLevel NGenTaskLauncher.Logger::maxLogLevel
0x787  call     bool NGenTaskLauncher.Logger::CorInitSvcLogger(string filename, bool userLocal, [out] valuetype LogLevel& logLevel)
0x78c  brtrue.s loc_798
0x78e  ldc.i4   0x80000000
0x793  stsfld   valuetype LogLevel NGenTaskLauncher.Logger::maxLogLevel
0x798  leave.s  loc_7A7
0x79a  pop
0x79b  ldc.i4   0x80000000
0x7a0  stsfld   valuetype LogLevel NGenTaskLauncher.Logger::maxLogLevel
0x7a5  leave.s  loc_7A7
0x7a7  ret
```

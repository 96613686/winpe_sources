# NGenTaskLauncher.Logger::Log

- ea: `0x7b0`
- end: `0x7c6`
- name: `NGenTaskLauncher.Logger::Log`
- size: `22`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x20`
- `0x60`
- `0x120`
- `0x1e0`
- `0x2d0`
- `0x4b0`
- `0x7d0`

## callees

- `0x7b0`
- `0x870`

## pseudocode

```c

```

## disassembly

```asm
0x7b0  ldarg.0
0x7b1  ldsfld   valuetype LogLevel NGenTaskLauncher.Logger::maxLogLevel
0x7b6  ble.s    loc_7B9
0x7b8  ret
0x7b9  ldarg.1
0x7ba  ldarg.2
0x7bb  call     string [mscorlib]System.String::Format(string, object[])
0x7c0  call     void NGenTaskLauncher.Logger::CorSvcLog(string message)
0x7c5  ret
```

# MicrosoftTelemetryAssertTriggeredNoArgsKM

- ea: `0x14000b86c`
- end: `0x14000b897`
- name: `MicrosoftTelemetryAssertTriggeredNoArgsKM`
- size: `43`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400020c4`
- `0x1400059b8`
- `0x14001bd20`
- `0x140020124`

## callees

- `0x14000b8a0`

## pseudocode

```c
void MicrosoftTelemetryAssertTriggeredNoArgsKM()
{
  unsigned __int64 retaddr; // [rsp+38h] [rbp+0h]

  MicrosoftTelemetryAssertTriggeredWorker(retaddr);
}

```

## disassembly

```asm
0x14000b86c  sub     rsp, 38h
0x14000b870  mov     rcx, [rsp+38h]
0x14000b875  or      r9d, 0FFFFFFFFh
0x14000b879  mov     [rsp+38h+var_10], 0
0x14000b882  xor     r8d, r8d
0x14000b885  xor     edx, edx
0x14000b887  mov     [rsp+38h+var_18], r9d
0x14000b88c  call    MicrosoftTelemetryAssertTriggeredWorker
0x14000b891  add     rsp, 38h
0x14000b895  retn
```

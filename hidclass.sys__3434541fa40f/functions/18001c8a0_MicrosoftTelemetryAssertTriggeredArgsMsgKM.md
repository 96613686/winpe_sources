# MicrosoftTelemetryAssertTriggeredArgsMsgKM

- ea: `0x18001c8a0`
- end: `0x18001c8cd`
- name: `MicrosoftTelemetryAssertTriggeredArgsMsgKM`
- size: `45`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800017d0`
- `0x180002a50`
- `0x1800053c0`
- `0x18000621c`
- `0x18001c034`
- `0x180020038`
- `0x180020288`
- `0x180025858`
- `0x180025b70`
- `0x180025f64`
- `0x18003b444`
- `0x18003e5b0`
- `0x18003f634`

## callees

- `0x18001acb8`

## pseudocode

```c
__int64 __fastcall MicrosoftTelemetryAssertTriggeredArgsMsgKM(__int64 a1, int a2, int a3, __int64 a4)
{
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h]

  return MicrosoftTelemetryAssertTriggeredWorker((_DWORD)retaddr, 1, (unsigned int)"HidClass", a2, a3, a4);
}

```

## disassembly

```asm
0x18001c8a0  sub     rsp, 38h
0x18001c8a4  mov     rcx, [rsp+38h]
0x18001c8a9  mov     [rsp+38h+var_10], r9
0x18001c8ae  mov     r9d, edx
0x18001c8b1  mov     [rsp+38h+var_18], r8d
0x18001c8b6  mov     edx, 1
0x18001c8bb  lea     r8, aHidclass_0; "HidClass"
0x18001c8c2  call    MicrosoftTelemetryAssertTriggeredWorker
0x18001c8c7  add     rsp, 38h
0x18001c8cb  retn
```

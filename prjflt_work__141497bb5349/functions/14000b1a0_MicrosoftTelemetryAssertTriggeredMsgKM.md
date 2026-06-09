# MicrosoftTelemetryAssertTriggeredMsgKM

- ea: `0x14000b1a0`
- end: `0x14000b1ca`
- name: `MicrosoftTelemetryAssertTriggeredMsgKM`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `23`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002b50`
- `0x140003e6c`
- `0x1400057b0`
- `0x140005e8c`
- `0x1400211e0`
- `0x140024b24`
- `0x140025944`
- `0x1400260a4`
- `0x1400266ec`
- `0x140026d94`
- `0x140027144`
- `0x1400277f4`
- `0x140027ca0`
- `0x140028464`
- `0x140029650`
- `0x14002b640`
- `0x14002c3f8`
- `0x14002eb70`
- `0x140033de8`
- `0x14003b724`
- `0x140041a3c`
- `0x1400453bc`
- `0x140048078`

## callees

- `0x14000b204`

## pseudocode

```c
__int64 __fastcall MicrosoftTelemetryAssertTriggeredMsgKM(__int64 a1)
{
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h]

  return MicrosoftTelemetryAssertTriggeredWorker((_DWORD)retaddr, 0, 0, -1, -1, a1);
}

```

## disassembly

```asm
0x14000b1a0  sub     rsp, 38h
0x14000b1a4  mov     rax, rcx
0x14000b1a7  or      r9d, 0FFFFFFFFh
0x14000b1ab  mov     rcx, [rsp+38h]
0x14000b1b0  xor     r8d, r8d
0x14000b1b3  mov     [rsp+38h+var_10], rax
0x14000b1b8  xor     edx, edx
0x14000b1ba  mov     [rsp+38h+var_18], r9d
0x14000b1bf  call    MicrosoftTelemetryAssertTriggeredWorker
0x14000b1c4  add     rsp, 38h
0x14000b1c8  retn
```

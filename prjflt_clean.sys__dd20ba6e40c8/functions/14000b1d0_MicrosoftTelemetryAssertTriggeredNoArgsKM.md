# MicrosoftTelemetryAssertTriggeredNoArgsKM

- ea: `0x14000b1d0`
- end: `0x14000b1fb`
- name: `MicrosoftTelemetryAssertTriggeredNoArgsKM`
- size: `43`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `90`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001658`
- `0x140001b3c`
- `0x140002b50`
- `0x140002d9c`
- `0x140002f3c`
- `0x140003480`
- `0x1400035d4`
- `0x1400037e0`
- `0x140003a8c`
- `0x140003e6c`
- `0x14000500c`
- `0x140007694`
- `0x140007cec`
- `0x1400081f0`
- `0x1400083b0`
- `0x1400089d8`
- `0x140009d20`
- `0x1400211e0`
- `0x140021550`
- `0x1400217a4`
- `0x1400220d0`
- `0x140022320`
- `0x140023740`
- `0x140023d68`
- `0x140024184`
- `0x140025734`
- `0x140025a78`
- `0x1400260a4`
- `0x1400266ec`
- `0x140026d94`
- `0x140027144`
- `0x1400277f4`
- `0x140027ca0`
- `0x140027f64`
- `0x140028048`
- `0x1400280f0`
- `0x140028464`
- `0x140028b30`
- `0x140029088`
- `0x140029650`
- `0x140029f60`
- `0x14002aa24`
- `0x14002aecc`
- `0x14002b3c0`
- `0x14002b888`
- `0x14002c090`
- `0x14002c1f4`
- `0x14002c3f8`
- `0x14002c98c`
- `0x14002d988`

## callees

- `0x14000b204`

## pseudocode

```c
__int64 MicrosoftTelemetryAssertTriggeredNoArgsKM()
{
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h]

  return MicrosoftTelemetryAssertTriggeredWorker((_DWORD)retaddr, 0, 0, -1, -1, 0);
}

```

## disassembly

```asm
0x14000b1d0  sub     rsp, 38h
0x14000b1d4  mov     rcx, [rsp+38h]
0x14000b1d9  or      r9d, 0FFFFFFFFh
0x14000b1dd  mov     [rsp+38h+var_10], 0
0x14000b1e6  xor     r8d, r8d
0x14000b1e9  xor     edx, edx
0x14000b1eb  mov     [rsp+38h+var_18], r9d
0x14000b1f0  call    MicrosoftTelemetryAssertTriggeredWorker
0x14000b1f5  add     rsp, 38h
0x14000b1f9  retn
```

# AslLogCallPrintf

- ea: `0x140007074`
- end: `0x1400070a5`
- name: `AslLogCallPrintf`
- size: `49`
- prototype: `__int64 (__fastcall *(__int64, _QWORD, _QWORD, const char *, ...))(_QWORD)`
- caller_count: `62`
- callee_count: `2`
- tags: ``

## callers

- `0x140003610`
- `0x1400039d0`
- `0x140003cd8`
- `0x1400060c0`
- `0x140007268`
- `0x140007350`
- `0x140007448`
- `0x140007614`
- `0x140007838`
- `0x1400078bc`
- `0x1400079ac`
- `0x140007a44`
- `0x140009504`
- `0x1400096a0`
- `0x1400097d4`
- `0x140009a10`
- `0x140009c7c`
- `0x14000b020`
- `0x14000b1f0`
- `0x14000b408`
- `0x14000b6bc`
- `0x14000ba04`
- `0x14000bde8`
- `0x14000bea0`
- `0x14000bf5c`
- `0x14000c110`
- `0x14000c334`
- `0x14000c630`
- `0x14000cb60`
- `0x14000cc48`
- `0x14000cd30`
- `0x14000cdfc`
- `0x14000cfe8`
- `0x14000d190`
- `0x14000d31c`
- `0x14000d420`
- `0x14000d650`
- `0x14000d704`
- `0x14000d7d0`
- `0x14000d858`
- `0x14000d9f8`
- `0x14000dc74`
- `0x14000dd40`
- `0x14000df84`
- `0x14000e0c4`
- `0x14000e18c`
- `0x14000e380`
- `0x14000eab4`
- `0x14000ee0c`
- `0x14000f0e8`

## callees

- `0x140007074`
- `0x140012010`

## pseudocode

```c
__int64 (__fastcall *AslLogCallPrintf(__int64 a1, _QWORD a2, _QWORD a3, const char *a4, ...))(_QWORD)
{
  __int64 (__fastcall *result)(_QWORD); // rax

  result = g_AslLogPfnVPrintf;
  if ( g_AslLogPfnVPrintf )
    return (__int64 (__fastcall *)(_QWORD))g_AslLogPfnVPrintf(a1);
  return result;
}

```

## disassembly

```asm
0x140007074  mov     r11, rsp
0x140007077  mov     [r11+20h], r9
0x14000707b  sub     rsp, 48h
0x14000707f  mov     rax, cs:g_AslLogPfnVPrintf
0x140007086  mov     qword ptr [r11-18h], 0
0x14000708e  test    rax, rax
0x140007091  jz      short loc_1400070A0
0x140007093  lea     r10, [r11+28h]
0x140007097  mov     [r11-28h], r10
0x14000709b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070a0  add     rsp, 48h
0x1400070a4  retn
```

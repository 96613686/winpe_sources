# AslLogCallPrintf

- ea: `0x18000e240`
- end: `0x18000e271`
- name: `AslLogCallPrintf`
- size: `49`
- prototype: `__int64(_QWORD, _QWORD, _QWORD, const char *, ...)`
- caller_count: `84`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039c8`
- `0x180008250`
- `0x1800084d8`
- `0x180008ad0`
- `0x180008bb8`
- `0x180008c38`
- `0x180008f10`
- `0x180009140`
- `0x180009200`
- `0x180009520`
- `0x1800096e0`
- `0x180009a20`
- `0x180009af0`
- `0x180009c00`
- `0x180009cdc`
- `0x180009fe8`
- `0x18000a208`
- `0x18000a60c`
- `0x18000a96c`
- `0x18000aaf4`
- `0x18000ac50`
- `0x18000ad2c`
- `0x18000ae60`
- `0x18000b048`
- `0x18000b1f0`
- `0x18000b710`
- `0x18000b8e8`
- `0x18000cbbc`
- `0x18000cd8c`
- `0x18000cfa4`
- `0x18000d258`
- `0x18000d910`
- `0x18000dcf4`
- `0x18000ddac`
- `0x18000de68`
- `0x18000e01c`
- `0x18000e53c`
- `0x18000e624`
- `0x18000e71c`
- `0x18000e8e8`
- `0x18000eb0c`
- `0x18000eb90`
- `0x18000ec80`
- `0x18000ed18`
- `0x18000edc0`
- `0x18000eef4`
- `0x18000f130`
- `0x18000f39c`
- `0x18000f6e4`
- `0x18000f7cc`

## callees

- `0x18000e240`
- `0x18001a010`

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
0x18000e240  mov     r11, rsp
0x18000e243  mov     [r11+20h], r9
0x18000e247  sub     rsp, 48h
0x18000e24b  mov     rax, cs:g_AslLogPfnVPrintf
0x18000e252  mov     qword ptr [r11-18h], 0
0x18000e25a  test    rax, rax
0x18000e25d  jz      short loc_18000E26C
0x18000e25f  lea     r10, [r11+28h]
0x18000e263  mov     [r11-28h], r10
0x18000e267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e26c  add     rsp, 48h
0x18000e270  retn
```

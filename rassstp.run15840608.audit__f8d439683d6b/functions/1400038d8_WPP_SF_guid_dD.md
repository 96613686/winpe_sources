# WPP_SF__guid_dD

- ea: `0x1400038d8`
- end: `0x140003932`
- name: `WPP_SF__guid_dD`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400018b0`
- `0x140010fd4`

## callees

- `0x140005ef0`

## pseudocode

```c
__int64 WPP_SF__guid_dD(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, ...)
{
  __int64 v5; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v5 = va_arg(va1, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
           a2,
           a4,
           16,
           (__int64 *)va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x1400038d8  mov     r11, rsp
0x1400038db  sub     rsp, 68h
0x1400038df  mov     rax, cs:pfnWppTraceMessage
0x1400038e6  lea     r8, [r11+30h]
0x1400038ea  mov     qword ptr [r11-18h], 0
0x1400038f2  mov     r10d, 4
0x1400038f8  mov     [r11-20h], r10
0x1400038fc  mov     [r11-28h], r8
0x140003900  lea     r8, [r11+28h]
0x140003904  mov     [r11-30h], r10
0x140003908  mov     [r11-38h], r8
0x14000390c  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140003913  mov     qword ptr [r11-40h], 10h
0x14000391b  mov     [r11-48h], r9
0x14000391f  movzx   r9d, dx
0x140003923  lea     edx, [r10+27h]
0x140003927  call    _guard_dispatch_icall
0x14000392c  add     rsp, 68h
0x140003930  retn
```

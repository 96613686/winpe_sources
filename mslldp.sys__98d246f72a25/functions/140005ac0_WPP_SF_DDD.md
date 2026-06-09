# WPP_SF_DDD

- ea: `0x140005ac0`
- end: `0x140005b17`
- name: `WPP_SF_DDD`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001f00`
- `0x140002180`
- `0x140003590`

## callees

- `0x140006670`

## pseudocode

```c
__int64 WPP_SF_DDD(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+88h] [rbp+20h] BYREF
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           (__int64 *)va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x140005ac0  mov     r11, rsp
0x140005ac3  mov     [r11+20h], r9d
0x140005ac7  sub     rsp, 68h
0x140005acb  mov     rax, cs:pfnWppTraceMessage
0x140005ad2  lea     r9, [r11+30h]
0x140005ad6  mov     qword ptr [r11-18h], 0
0x140005ade  mov     r10d, 4
0x140005ae4  mov     [r11-20h], r10
0x140005ae8  mov     [r11-28h], r9
0x140005aec  lea     r9, [r11+28h]
0x140005af0  mov     [r11-30h], r10
0x140005af4  mov     [r11-38h], r9
0x140005af8  lea     r9, [r11+20h]
0x140005afc  mov     [r11-40h], r10
0x140005b00  mov     [r11-48h], r9
0x140005b04  movzx   r9d, dx
0x140005b08  lea     edx, [r10+27h]
0x140005b0c  call    _guard_dispatch_icall
0x140005b11  add     rsp, 68h
0x140005b15  retn
```

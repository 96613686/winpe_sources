# WPP_SF_qddZ

- ea: `0x180001a08`
- end: `0x180001aca`
- name: `WPP_SF_qddZ`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b964`
- `0x18000f4bc`

## callees

- `0x180001a08`
- `0x180001fb0`

## pseudocode

```c
__int64 WPP_SF_qddZ(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  const wchar_t *v3; // r9
  __int64 v4; // r10
  const wchar_t *v5; // r11
  __int64 v7; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  __int64 v9; // [rsp+B0h] [rbp+28h] BYREF
  va_list va1; // [rsp+B0h] [rbp+28h]
  __int64 v11; // [rsp+B8h] [rbp+30h] BYREF
  va_list va2; // [rsp+B8h] [rbp+30h]
  unsigned __int16 *v13; // [rsp+C0h] [rbp+38h]
  va_list va3; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v7 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v9 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v11 = va_arg(va3, _QWORD);
  v13 = va_arg(va3, unsigned __int16 *);
  v3 = v13;
  if ( v13 )
  {
    v4 = *v13;
    if ( *v13 )
    {
      v5 = (const wchar_t *)*((_QWORD *)v13 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 8;
  }
  v5 = L"NULL";
LABEL_6:
  if ( !v13 )
    v3 = L"\b";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           4,
           (__int64 *)va2,
           4,
           v3,
           2,
           v5,
           v4,
           0);
}

```

## disassembly

```asm
0x180001a08  mov     [rsp+arg_18], r9
0x180001a0d  push    rbx
0x180001a0e  sub     rsp, 80h
0x180001a15  mov     r9, [rsp+88h+arg_30]
0x180001a1d  xor     ebx, ebx
0x180001a1f  test    r9, r9
0x180001a22  jz      short loc_180001A34
0x180001a24  movzx   r10d, word ptr [r9]
0x180001a28  cmp     [r9], bx
0x180001a2c  jz      short loc_180001A3A
0x180001a2e  mov     r11, [r9+8]
0x180001a32  jmp     short loc_180001A41
0x180001a34  mov     r10d, 8
0x180001a3a  lea     r11, aNull; "NULL"
0x180001a41  mov     [rsp+88h+var_18], rbx
0x180001a46  lea     rax, asc_18000456C; "\b"
0x180001a4d  mov     [rsp+88h+var_20], r10
0x180001a52  test    r9, r9
0x180001a55  mov     [rsp+88h+var_28], r11
0x180001a5a  mov     r10d, 4
0x180001a60  cmovz   r9, rax
0x180001a64  mov     [rsp+88h+var_30], 2
0x180001a6d  mov     rax, cs:pfnWppTraceMessage
0x180001a74  mov     [rsp+88h+var_38], r9
0x180001a79  lea     r9, [rsp+88h+arg_28]
0x180001a81  mov     [rsp+88h+var_40], r10
0x180001a86  mov     [rsp+88h+var_48], r9
0x180001a8b  lea     r9, [rsp+88h+arg_20]
0x180001a93  mov     [rsp+88h+var_50], r10
0x180001a98  mov     [rsp+88h+var_58], r9
0x180001a9d  lea     r9, [rsp+88h+arg_18]
0x180001aa5  mov     [rsp+88h+var_60], 8
0x180001aae  mov     [rsp+88h+var_68], r9
0x180001ab3  movzx   r9d, dx
0x180001ab7  lea     edx, [r10+27h]
0x180001abb  call    _guard_dispatch_icall
0x180001ac0  add     rsp, 80h
0x180001ac7  pop     rbx
0x180001ac8  retn
```

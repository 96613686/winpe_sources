# WPP_SF_ZZ

- ea: `0x140019d7c`
- end: `0x140019e36`
- name: `WPP_SF_ZZ`
- size: `186`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *, unsigned __int16 *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x14000be20`
- `0x14000c370`
- `0x1400196a8`
- `0x140025040`
- `0x140025484`
- `0x1400273f0`
- `0x1400280c4`
- `0x140028608`

## callees

- `0x140019d7c`
- `0x14003abe0`

## pseudocode

```c
__int64 __fastcall WPP_SF_ZZ(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4, unsigned __int16 *a5)
{
  const wchar_t *v5; // r11
  const wchar_t *v6; // rdi
  __int64 v8; // rbx
  __int64 v9; // r10
  const wchar_t *v10; // r8
  bool v11; // zf

  v5 = a5;
  v6 = L"NULL";
  v8 = 8;
  if ( a5 )
  {
    v9 = *a5;
    if ( *a5 )
    {
      v10 = (const wchar_t *)*((_QWORD *)a5 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v9 = 8;
  }
  v10 = L"NULL";
LABEL_6:
  if ( !a5 )
    v5 = L"\b";
  v11 = a4 == 0;
  if ( a4 )
  {
    v8 = *a4;
    if ( *a4 )
      v6 = (const wchar_t *)*((_QWORD *)a4 + 1);
    v11 = a4 == 0;
  }
  if ( v11 )
    a4 = L"\b";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, const wchar_t *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           2,
           v6,
           v8,
           v5,
           2,
           v10,
           v9,
           0);
}

```

## disassembly

```asm
0x140019d7c  push    rbx
0x140019d7e  push    rbp
0x140019d7f  push    rsi
0x140019d80  push    rdi
0x140019d81  sub     rsp, 78h
0x140019d85  mov     r11, [rsp+98h+arg_20]
0x140019d8d  lea     rdi, aNull_0; "NULL"
0x140019d94  xor     ebp, ebp
0x140019d96  mov     rsi, r8
0x140019d99  mov     ebx, 8
0x140019d9e  test    r11, r11
0x140019da1  jz      short loc_140019DB3
0x140019da3  movzx   r10d, word ptr [r11]
0x140019da7  cmp     [r11], bp
0x140019dab  jz      short loc_140019DB6
0x140019dad  mov     r8, [r11+8]
0x140019db1  jmp     short loc_140019DB9
0x140019db3  mov     r10, rbx
0x140019db6  mov     r8, rdi
0x140019db9  test    r11, r11
0x140019dbc  lea     rax, asc_14003D1F4; "\b"
0x140019dc3  cmovz   r11, rax
0x140019dc7  test    r9, r9
0x140019dca  jz      short loc_140019DDD
0x140019dcc  movzx   ebx, word ptr [r9]
0x140019dd0  cmp     [r9], bp
0x140019dd4  jz      short loc_140019DDA
0x140019dd6  mov     rdi, [r9+8]
0x140019dda  test    r9, r9
0x140019ddd  mov     [rsp+98h+var_38], rbp
0x140019de2  cmovz   r9, rax
0x140019de6  mov     rax, cs:pfnWppTraceMessage
0x140019ded  mov     [rsp+98h+var_40], r10
0x140019df2  mov     [rsp+98h+var_48], r8
0x140019df7  mov     r8d, 2
0x140019dfd  mov     [rsp+98h+var_50], r8
0x140019e02  mov     [rsp+98h+var_58], r11
0x140019e07  mov     [rsp+98h+var_60], rbx
0x140019e0c  mov     [rsp+98h+var_68], rdi
0x140019e11  mov     [rsp+98h+var_70], r8
0x140019e16  mov     r8, rsi
0x140019e19  mov     [rsp+98h+var_78], r9
0x140019e1e  movzx   r9d, dx
0x140019e22  mov     edx, 2Bh ; '+'
0x140019e27  call    _guard_dispatch_icall
0x140019e2c  add     rsp, 78h
0x140019e30  pop     rdi
0x140019e31  pop     rsi
0x140019e32  pop     rbp
0x140019e33  pop     rbx
0x140019e34  retn
```

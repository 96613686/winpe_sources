# WPP_SF_ddZ

- ea: `0x140005f88`
- end: `0x140006035`
- name: `WPP_SF_ddZ`
- size: `173`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int, char, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140005b3c`
- `0x1400253e0`
- `0x140025b9c`

## callees

- `0x140005f88`
- `0x140006880`

## pseudocode

```c
__int64 __fastcall WPP_SF_ddZ(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, char a5, unsigned __int16 *a6)
{
  const wchar_t *v6; // r8
  __int64 v7; // r9
  const wchar_t *v8; // r10
  int v10; // [rsp+98h] [rbp+20h] BYREF

  v10 = a4;
  v6 = a6;
  if ( a6 )
  {
    v7 = *a6;
    if ( *a6 )
    {
      v8 = (const wchar_t *)*((_QWORD *)a6 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v7 = 8;
  }
  v8 = L"NULL";
LABEL_6:
  if ( !a6 )
    v6 = L"\b";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, int *, __int64, char *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids,
           a2,
           &v10,
           4,
           &a5,
           4,
           v6,
           2,
           v8,
           v7,
           0);
}

```

## disassembly

```asm
0x140005f88  mov     [rsp+arg_18], r9d
0x140005f8d  sub     rsp, 78h
0x140005f91  mov     r8, [rsp+78h+arg_28]
0x140005f99  xor     r11d, r11d
0x140005f9c  test    r8, r8
0x140005f9f  jz      short loc_140005FB1
0x140005fa1  movzx   r9d, word ptr [r8]
0x140005fa5  cmp     [r8], r11w
0x140005fa9  jz      short loc_140005FB7
0x140005fab  mov     r10, [r8+8]
0x140005faf  jmp     short loc_140005FBE
0x140005fb1  mov     r9d, 8
0x140005fb7  lea     r10, aNull_0; "NULL"
0x140005fbe  mov     [rsp+78h+var_18], r11
0x140005fc3  lea     rax, asc_140009230; "\b"
0x140005fca  mov     [rsp+78h+var_20], r9
0x140005fcf  test    r8, r8
0x140005fd2  mov     [rsp+78h+var_28], r10
0x140005fd7  mov     r9d, 4
0x140005fdd  cmovz   r8, rax
0x140005fe1  mov     [rsp+78h+var_30], 2
0x140005fea  mov     rax, cs:pfnWppTraceMessage
0x140005ff1  mov     [rsp+78h+var_38], r8
0x140005ff6  lea     r8, [rsp+78h+arg_20]
0x140005ffe  mov     [rsp+78h+var_40], r9
0x140006003  mov     [rsp+78h+var_48], r8
0x140006008  lea     r8, [rsp+78h+arg_18]
0x140006010  mov     [rsp+78h+var_50], r9
0x140006015  mov     [rsp+78h+var_58], r8
0x14000601a  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x140006021  movzx   r9d, dx
0x140006025  mov     edx, 2Bh ; '+'
0x14000602a  call    _guard_dispatch_icall
0x14000602f  add     rsp, 78h
0x140006033  retn
```

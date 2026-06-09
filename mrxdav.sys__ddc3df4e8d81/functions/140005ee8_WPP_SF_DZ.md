# WPP_SF_DZ

- ea: `0x140005ee8`
- end: `0x140005f81`
- name: `WPP_SF_DZ`
- size: `153`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140005b3c`
- `0x1400253e0`
- `0x140025b9c`

## callees

- `0x140005ee8`
- `0x140006880`

## pseudocode

```c
__int64 __fastcall WPP_SF_DZ(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, unsigned __int16 *a5)
{
  const wchar_t *v5; // r8
  __int64 v6; // r9
  const wchar_t *v7; // r10
  int v9; // [rsp+88h] [rbp+20h] BYREF

  v9 = a4;
  v5 = a5;
  if ( a5 )
  {
    v6 = *a5;
    if ( *a5 )
    {
      v7 = (const wchar_t *)*((_QWORD *)a5 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v6 = 8;
  }
  v7 = L"NULL";
LABEL_6:
  if ( !a5 )
    v5 = L"\b";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, int *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids,
           a2,
           &v9,
           4,
           v5,
           2,
           v7,
           v6,
           0);
}

```

## disassembly

```asm
0x140005ee8  mov     [rsp+arg_18], r9d
0x140005eed  sub     rsp, 68h
0x140005ef1  mov     r8, [rsp+68h+arg_20]
0x140005ef9  xor     r11d, r11d
0x140005efc  test    r8, r8
0x140005eff  jz      short loc_140005F11
0x140005f01  movzx   r9d, word ptr [r8]
0x140005f05  cmp     [r8], r11w
0x140005f09  jz      short loc_140005F17
0x140005f0b  mov     r10, [r8+8]
0x140005f0f  jmp     short loc_140005F1E
0x140005f11  mov     r9d, 8
0x140005f17  lea     r10, aNull_0; "NULL"
0x140005f1e  mov     [rsp+68h+var_18], r11
0x140005f23  lea     rax, asc_140009230; "\b"
0x140005f2a  mov     [rsp+68h+var_20], r9
0x140005f2f  test    r8, r8
0x140005f32  mov     [rsp+68h+var_28], r10
0x140005f37  cmovz   r8, rax
0x140005f3b  mov     [rsp+68h+var_30], 2
0x140005f44  mov     rax, cs:pfnWppTraceMessage
0x140005f4b  mov     [rsp+68h+var_38], r8
0x140005f50  lea     r8, [rsp+68h+arg_18]
0x140005f58  movzx   r9d, dx
0x140005f5c  mov     edx, 2Bh ; '+'
0x140005f61  mov     [rsp+68h+var_40], 4
0x140005f6a  mov     [rsp+68h+var_48], r8
0x140005f6f  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x140005f76  call    _guard_dispatch_icall
0x140005f7b  add     rsp, 68h
0x140005f7f  retn
```

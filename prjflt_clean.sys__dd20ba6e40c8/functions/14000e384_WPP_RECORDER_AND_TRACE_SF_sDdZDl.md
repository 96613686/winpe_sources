# WPP_RECORDER_AND_TRACE_SF_sDdZDl

- ea: `0x14000e384`
- end: `0x14000e574`
- name: `WPP_RECORDER_AND_TRACE_SF_sDdZDl`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022320`

## callees

- `0x140005cf4`
- `0x14000e384`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000e553`
- `WppRecorder!WppAutoLogTrace` at `0x14000e553`

## string_xrefs

- `0x14000e3cd`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x14000e48d`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDdZDl(
        __int16 a1,
        char a2,
        char a3,
        __int64 a4,
        unsigned __int8 a5,
        int a6,
        USHORT a7,
        int a8,
        int a9,
        ...)
{
  const wchar_t *v9; // rbx
  const wchar_t *v10; // rsi
  __int64 v11; // rdi
  __int64 v15; // rcx
  const wchar_t *v16; // rdx
  const wchar_t *v17; // rax
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-C8h]
  __int64 v20; // [rsp+A0h] [rbp-48h]
  __int64 v21; // [rsp+A8h] [rbp-40h]
  __int64 v22; // [rsp+138h] [rbp+50h] BYREF
  va_list va; // [rsp+138h] [rbp+50h]
  __int64 v24; // [rsp+140h] [rbp+58h] BYREF
  va_list va1; // [rsp+140h] [rbp+58h]
  unsigned __int16 *v26; // [rsp+148h] [rbp+60h]
  __int64 v27; // [rsp+150h] [rbp+68h] BYREF
  va_list va2; // [rsp+150h] [rbp+68h]
  va_list va3; // [rsp+158h] [rbp+70h] BYREF

  va_start(va3, a9);
  va_start(va2, a9);
  va_start(va1, a9);
  va_start(va, a9);
  v22 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v24 = va_arg(va2, _QWORD);
  v26 = va_arg(va2, unsigned __int16 *);
  va_copy(va3, va2);
  v27 = va_arg(va3, _QWORD);
  v9 = v26;
  v10 = L"NULL";
  v11 = 8;
  if ( !a2 )
    goto LABEL_10;
  if ( !v26 )
  {
    v15 = 8;
    goto LABEL_6;
  }
  v15 = *v26;
  if ( !*v26 )
  {
LABEL_6:
    v16 = L"NULL";
    goto LABEL_7;
  }
  v16 = (const wchar_t *)*((_QWORD *)v26 + 1);
LABEL_7:
  v17 = v26;
  if ( !v26 )
    v17 = L"\b";
  FastWppTraceMessage(
    a1,
    a7,
    (ULONGLONG)&WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
    "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
    42,
    va,
    4,
    va1,
    4,
    v17,
    2,
    v16,
    v15,
    va2,
    4,
    va3,
    4,
    0);
LABEL_10:
  if ( a3 )
  {
    v18 = v9 == 0;
    if ( v9 )
    {
      v11 = *v9;
      if ( *v9 )
        v10 = (const wchar_t *)*((_QWORD *)v9 + 1);
      v18 = v9 == 0;
    }
    if ( v18 )
      v9 = L"\b";
    LOWORD(v19) = a7;
    WppAutoLogTrace(
      a4,
      a5,
      5,
      &WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
      v19,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
      42,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      v9,
      2,
      v10,
      v11,
      (__int64 *)va2,
      4,
      va3,
      4,
      0,
      v20,
      v21);
  }
}

```

## disassembly

```asm
0x14000e384  push    rbx
0x14000e386  push    rbp
0x14000e387  push    rsi
0x14000e388  push    rdi
0x14000e389  push    r12
0x14000e38b  push    r13
0x14000e38d  push    r14
0x14000e38f  push    r15
0x14000e391  sub     rsp, 0A8h
0x14000e398  mov     rbx, [rsp+0E8h+arg_58]
0x14000e3a0  lea     rsi, aNull_0; "NULL"
0x14000e3a7  movzx   r14d, [rsp+0E8h+arg_30]
0x14000e3b0  mov     edi, 8
0x14000e3b5  xor     r12d, r12d
0x14000e3b8  movzx   r10d, cx
0x14000e3bc  mov     r15, r9
0x14000e3bf  mov     bpl, r8b
0x14000e3c2  lea     r8, asc_1400156D4; "\b"
0x14000e3c9  lea     r13d, [rdi-4]
0x14000e3cd  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000e3d4  test    dl, dl
0x14000e3d6  jz      loc_14000E494
0x14000e3dc  test    rbx, rbx
0x14000e3df  jz      short loc_14000E3F0
0x14000e3e1  movzx   ecx, word ptr [rbx]
0x14000e3e4  cmp     [rbx], r12w
0x14000e3e8  jz      short loc_14000E3F3
0x14000e3ea  mov     rdx, [rbx+8]
0x14000e3ee  jmp     short loc_14000E3F6
0x14000e3f0  mov     rcx, rdi
0x14000e3f3  mov     rdx, rsi
0x14000e3f6  mov     [rsp+0E8h+var_60], r12
0x14000e3fe  test    rbx, rbx
0x14000e401  mov     [rsp+0E8h+var_68], r13
0x14000e409  mov     rax, rbx
0x14000e40c  cmovz   rax, r8
0x14000e410  lea     r8, [rsp+0E8h+arg_68]
0x14000e418  mov     [rsp+0E8h+var_70], r8
0x14000e41d  lea     r8, [rsp+0E8h+arg_60]
0x14000e425  mov     [rsp+0E8h+var_78], r13
0x14000e42a  mov     [rsp+0E8h+var_80], r8
0x14000e42f  lea     r8, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000e436  mov     [rsp+0E8h+var_88], rcx
0x14000e43b  mov     ecx, r10d
0x14000e43e  mov     [rsp+0E8h+var_90], rdx
0x14000e443  mov     edx, r14d
0x14000e446  mov     [rsp+0E8h+var_98], 2
0x14000e44f  mov     [rsp+0E8h+var_A0], rax
0x14000e454  lea     rax, [rsp+0E8h+arg_50]
0x14000e45c  mov     [rsp+0E8h+var_A8], r13
0x14000e461  mov     [rsp+0E8h+var_B0], rax
0x14000e466  lea     rax, [rsp+0E8h+arg_48]
0x14000e46e  mov     [rsp+0E8h+var_B8], r13
0x14000e473  mov     [rsp+0E8h+var_C0], rax
0x14000e478  mov     [rsp+0E8h+var_C8], 2Ah ; '*'
0x14000e481  call    FastWppTraceMessage
0x14000e486  lea     r8, asc_1400156D4; "\b"
0x14000e48d  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000e494  test    bpl, bpl
0x14000e497  jz      loc_14000E55F
0x14000e49d  test    rbx, rbx
0x14000e4a0  jz      short loc_14000E4B2
0x14000e4a2  movzx   edi, word ptr [rbx]
0x14000e4a5  cmp     [rbx], r12w
0x14000e4a9  jz      short loc_14000E4AF
0x14000e4ab  mov     rsi, [rbx+8]
0x14000e4af  test    rbx, rbx
0x14000e4b2  movzx   edx, [rsp+0E8h+arg_20]
0x14000e4ba  lea     rax, [rsp+0E8h+arg_68]
0x14000e4c2  mov     [rsp+0E8h+var_50], r12
0x14000e4ca  cmovz   rbx, r8
0x14000e4ce  mov     [rsp+0E8h+var_58], r13
0x14000e4d6  mov     r8d, 5
0x14000e4dc  mov     [rsp+0E8h+var_60], rax
0x14000e4e4  mov     rcx, r15
0x14000e4e7  mov     [rsp+0E8h+var_68], r13
0x14000e4ef  lea     rax, [rsp+0E8h+arg_60]
0x14000e4f7  mov     [rsp+0E8h+var_70], rax
0x14000e4fc  lea     rax, [rsp+0E8h+arg_50]
0x14000e504  mov     [rsp+0E8h+var_78], rdi
0x14000e509  mov     [rsp+0E8h+var_80], rsi
0x14000e50e  mov     [rsp+0E8h+var_88], 2
0x14000e517  mov     [rsp+0E8h+var_90], rbx
0x14000e51c  mov     [rsp+0E8h+var_98], r13
0x14000e521  mov     [rsp+0E8h+var_A0], rax
0x14000e526  lea     rax, [rsp+0E8h+arg_48]
0x14000e52e  mov     [rsp+0E8h+var_A8], r13
0x14000e533  mov     [rsp+0E8h+var_B0], rax
0x14000e538  mov     [rsp+0E8h+var_B8], 2Ah ; '*'
0x14000e541  mov     [rsp+0E8h+var_C0], r9
0x14000e546  lea     r9, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000e54d  mov     word ptr [rsp+0E8h+var_C8], r14w
0x14000e553  call    cs:__imp_WppAutoLogTrace
0x14000e55a  nop     dword ptr [rax+rax+00h]
0x14000e55f  add     rsp, 0A8h
0x14000e566  pop     r15
0x14000e568  pop     r14
0x14000e56a  pop     r13
0x14000e56c  pop     r12
0x14000e56e  pop     rdi
0x14000e56f  pop     rsi
0x14000e570  pop     rbp
0x14000e571  pop     rbx
0x14000e572  retn
```

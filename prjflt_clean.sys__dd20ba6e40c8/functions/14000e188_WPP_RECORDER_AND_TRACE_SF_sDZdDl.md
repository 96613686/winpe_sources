# WPP_RECORDER_AND_TRACE_SF_sDZdDl

- ea: `0x14000e188`
- end: `0x14000e37b`
- name: `WPP_RECORDER_AND_TRACE_SF_sDZdDl`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022320`

## callees

- `0x140005cf4`
- `0x14000e188`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000e35c`
- `WppRecorder!WppAutoLogTrace` at `0x14000e35c`

## string_xrefs

- `0x14000e1bd`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x14000e29b`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDZdDl(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        unsigned __int16 *a11,
        ...)
{
  const wchar_t *v11; // rbx
  const wchar_t *v12; // rsi
  __int64 v13; // rdi
  __int64 v16; // rcx
  const wchar_t *v17; // rdx
  const wchar_t *v18; // rax
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-C8h]
  _QWORD v21[9]; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v22; // [rsp+148h] [rbp+60h] BYREF
  va_list va; // [rsp+148h] [rbp+60h]
  __int64 v24; // [rsp+150h] [rbp+68h] BYREF
  va_list va1; // [rsp+150h] [rbp+68h]
  va_list va2; // [rsp+158h] [rbp+70h] BYREF

  va_start(va2, a11);
  va_start(va1, a11);
  va_start(va, a11);
  v22 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v24 = va_arg(va2, _QWORD);
  v11 = a11;
  v12 = L"NULL";
  v13 = 8;
  LODWORD(v21[0]) = 1447;
  if ( !a2 )
    goto LABEL_10;
  if ( !a11 )
  {
    v16 = 8;
    goto LABEL_6;
  }
  v16 = *a11;
  if ( !*a11 )
  {
LABEL_6:
    v17 = L"NULL";
    goto LABEL_7;
  }
  v17 = (const wchar_t *)*((_QWORD *)a11 + 1);
LABEL_7:
  v18 = a11;
  if ( !a11 )
    v18 = L"\b";
  FastWppTraceMessage(
    773,
    0x21u,
    (ULONGLONG)&WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
    "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
    42,
    v21,
    4,
    v18,
    2,
    v17,
    v16,
    va,
    4,
    va1,
    4,
    va2,
    4,
    0);
LABEL_10:
  if ( a3 )
  {
    v19 = a11 == 0;
    if ( a11 )
    {
      v13 = *a11;
      if ( *a11 )
        v12 = (const wchar_t *)*((_QWORD *)a11 + 1);
      v19 = a11 == 0;
    }
    if ( v19 )
      v11 = L"\b";
    LOWORD(v20) = 33;
    WppAutoLogTrace(
      a4,
      3,
      5,
      &WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
      v20,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
      42,
      v21,
      4,
      v11,
      2,
      v12,
      v13,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      va2,
      4,
      0,
      v21[0],
      v21[1]);
  }
}

```

## disassembly

```asm
0x14000e188  mov     rax, rsp
0x14000e18b  push    rbx
0x14000e18c  push    rbp
0x14000e18d  push    rsi
0x14000e18e  push    rdi
0x14000e18f  push    r12
0x14000e191  push    r14
0x14000e193  push    r15
0x14000e195  sub     rsp, 0B0h
0x14000e19c  mov     rbx, [rsp+0E8h+arg_50]
0x14000e1a4  lea     rsi, aNull_0; "NULL"
0x14000e1ab  mov     edi, 8
0x14000e1b0  mov     dword ptr [rax-48h], 5A7h
0x14000e1b7  xor     r15d, r15d
0x14000e1ba  mov     r14, r9
0x14000e1bd  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000e1c4  mov     bpl, r8b
0x14000e1c7  lea     r8, asc_1400156D4; "\b"
0x14000e1ce  lea     r11d, [rdi+19h]
0x14000e1d2  lea     r12d, [rdi-4]
0x14000e1d6  test    dl, dl
0x14000e1d8  jz      loc_14000E2A2
0x14000e1de  test    rbx, rbx
0x14000e1e1  jz      short loc_14000E1F2
0x14000e1e3  movzx   ecx, word ptr [rbx]
0x14000e1e6  cmp     [rbx], r15w
0x14000e1ea  jz      short loc_14000E1F5
0x14000e1ec  mov     rdx, [rbx+8]
0x14000e1f0  jmp     short loc_14000E1F8
0x14000e1f2  mov     rcx, rdi
0x14000e1f5  mov     rdx, rsi
0x14000e1f8  mov     [rsp+0E8h+var_60], r15
0x14000e200  test    rbx, rbx
0x14000e203  mov     [rsp+0E8h+var_68], r12
0x14000e20b  mov     r10d, 305h
0x14000e211  mov     rax, rbx
0x14000e214  cmovz   rax, r8
0x14000e218  lea     r8, [rsp+0E8h+arg_68]
0x14000e220  mov     [rsp+0E8h+var_70], r8
0x14000e225  lea     r8, [rsp+0E8h+arg_60]
0x14000e22d  mov     [rsp+0E8h+var_78], r12
0x14000e232  mov     [rsp+0E8h+var_80], r8
0x14000e237  lea     r8, [rsp+0E8h+arg_58]
0x14000e23f  mov     [rsp+0E8h+var_88], r12
0x14000e244  mov     [rsp+0E8h+var_90], r8
0x14000e249  lea     r8, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000e250  mov     [rsp+0E8h+var_98], rcx
0x14000e255  mov     ecx, r10d
0x14000e258  mov     [rsp+0E8h+var_A0], rdx
0x14000e25d  mov     edx, r11d
0x14000e260  mov     [rsp+0E8h+var_A8], 2
0x14000e269  mov     [rsp+0E8h+var_B0], rax
0x14000e26e  lea     rax, [rsp+0E8h+var_48]
0x14000e276  mov     [rsp+0E8h+var_B8], r12
0x14000e27b  mov     [rsp+0E8h+var_C0], rax
0x14000e280  mov     [rsp+0E8h+var_C8], 2Ah ; '*'
0x14000e289  call    FastWppTraceMessage
0x14000e28e  lea     r8, asc_1400156D4; "\b"
0x14000e295  mov     r11d, 21h ; '!'
0x14000e29b  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000e2a2  test    bpl, bpl
0x14000e2a5  jz      loc_14000E368
0x14000e2ab  test    rbx, rbx
0x14000e2ae  jz      short loc_14000E2C0
0x14000e2b0  movzx   edi, word ptr [rbx]
0x14000e2b3  cmp     [rbx], r15w
0x14000e2b7  jz      short loc_14000E2BD
0x14000e2b9  mov     rsi, [rbx+8]
0x14000e2bd  test    rbx, rbx
0x14000e2c0  mov     [rsp+0E8h+var_50], r15
0x14000e2c8  lea     rax, [rsp+0E8h+arg_68]
0x14000e2d0  mov     [rsp+0E8h+var_58], r12
0x14000e2d8  cmovz   rbx, r8
0x14000e2dc  mov     [rsp+0E8h+var_60], rax
0x14000e2e4  mov     edx, 3
0x14000e2e9  mov     [rsp+0E8h+var_68], r12
0x14000e2f1  lea     rax, [rsp+0E8h+arg_60]
0x14000e2f9  mov     [rsp+0E8h+var_70], rax
0x14000e2fe  mov     rcx, r14
0x14000e301  mov     [rsp+0E8h+var_78], r12
0x14000e306  lea     rax, [rsp+0E8h+arg_58]
0x14000e30e  mov     [rsp+0E8h+var_80], rax
0x14000e313  lea     r8d, [rdx+2]
0x14000e317  mov     [rsp+0E8h+var_88], rdi
0x14000e31c  lea     rax, [rsp+0E8h+var_48]
0x14000e324  mov     [rsp+0E8h+var_90], rsi
0x14000e329  mov     [rsp+0E8h+var_98], 2
0x14000e332  mov     [rsp+0E8h+var_A0], rbx
0x14000e337  mov     [rsp+0E8h+var_A8], r12
0x14000e33c  mov     [rsp+0E8h+var_B0], rax
0x14000e341  mov     [rsp+0E8h+var_B8], 2Ah ; '*'
0x14000e34a  mov     [rsp+0E8h+var_C0], r9
0x14000e34f  lea     r9, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000e356  mov     word ptr [rsp+0E8h+var_C8], r11w
0x14000e35c  call    cs:__imp_WppAutoLogTrace
0x14000e363  nop     dword ptr [rax+rax+00h]
0x14000e368  add     rsp, 0B0h
0x14000e36f  pop     r15
0x14000e371  pop     r14
0x14000e373  pop     r12
0x14000e375  pop     rdi
0x14000e376  pop     rsi
0x14000e377  pop     rbp
0x14000e378  pop     rbx
0x14000e379  retn
```

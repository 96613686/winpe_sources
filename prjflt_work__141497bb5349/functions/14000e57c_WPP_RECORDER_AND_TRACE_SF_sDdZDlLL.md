# WPP_RECORDER_AND_TRACE_SF_sDdZDlLL

- ea: `0x14000e57c`
- end: `0x14000e7c4`
- name: `WPP_RECORDER_AND_TRACE_SF_sDdZDlLL`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140022320`

## callees

- `0x140005cf4`
- `0x14000e57c`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000e7a3`
- `WppRecorder!WppAutoLogTrace` at `0x14000e7a3`

## string_xrefs

- `0x14000e5ce`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x14000e6be`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDdZDlLL(
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
        int a11,
        unsigned __int16 *a12,
        ...)
{
  const wchar_t *v12; // rbx
  const wchar_t *v13; // rsi
  __int64 v14; // rdi
  __int64 v17; // rcx
  const wchar_t *v18; // rdx
  const wchar_t *v19; // rax
  bool v20; // zf
  int v21; // [rsp+20h] [rbp-B1h]
  int v22; // [rsp+C0h] [rbp-11h] BYREF
  _DWORD v23[18]; // [rsp+C8h] [rbp-9h] BYREF
  __int64 v24; // [rsp+180h] [rbp+AFh] BYREF
  va_list va; // [rsp+180h] [rbp+AFh]
  __int64 v26; // [rsp+188h] [rbp+B7h] BYREF
  va_list va1; // [rsp+188h] [rbp+B7h]
  __int64 v28; // [rsp+190h] [rbp+BFh] BYREF
  va_list va2; // [rsp+190h] [rbp+BFh]
  va_list va3; // [rsp+198h] [rbp+C7h] BYREF

  va_start(va3, a12);
  va_start(va2, a12);
  va_start(va1, a12);
  va_start(va, a12);
  v24 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v26 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v28 = va_arg(va3, _QWORD);
  v12 = a12;
  v13 = L"NULL";
  v14 = 8;
  v22 = -1073689087;
  v23[0] = 1941;
  if ( !a2 )
    goto LABEL_10;
  if ( !a12 )
  {
    v17 = 8;
    goto LABEL_6;
  }
  v17 = *a12;
  if ( !*a12 )
  {
LABEL_6:
    v18 = L"NULL";
    goto LABEL_7;
  }
  v18 = (const wchar_t *)*((_QWORD *)a12 + 1);
LABEL_7:
  v19 = a12;
  if ( !a12 )
    v19 = L"\b";
  FastWppTraceMessage(
    773,
    0x2Cu,
    (ULONGLONG)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
    "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
    42,
    v23,
    4,
    &v22,
    4,
    v19,
    2,
    v18,
    v17,
    va,
    4,
    va1,
    4,
    va2,
    4,
    va3,
    4,
    0);
LABEL_10:
  if ( a3 )
  {
    v20 = a12 == 0;
    if ( a12 )
    {
      v14 = *a12;
      if ( *a12 )
        v13 = (const wchar_t *)*((_QWORD *)a12 + 1);
      v20 = a12 == 0;
    }
    if ( v20 )
      v12 = L"\b";
    LOWORD(v21) = 44;
    ((void (__fastcall *)(__int64, __int64, __int64, __int64 *, int, const char *, __int64, _DWORD *, __int64, int *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))WppAutoLogTrace)(
      a4,
      3,
      5,
      WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
      v21,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
      42,
      v23,
      4,
      &v22,
      4,
      v12,
      2,
      v13,
      v14,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      va3,
      4,
      0);
  }
}

```

## disassembly

```asm
0x14000e57c  push    rbp
0x14000e57e  push    rbx
0x14000e57f  push    rsi
0x14000e580  push    rdi
0x14000e581  push    r12
0x14000e583  push    r13
0x14000e585  push    r14
0x14000e587  push    r15
0x14000e589  lea     rbp, [rsp-7]
0x14000e58e  sub     rsp, 0D8h
0x14000e595  mov     rbx, [rbp+3Fh+arg_58]
0x14000e59c  lea     rsi, aNull_0; "NULL"
0x14000e5a3  mov     edi, 8
0x14000e5a8  mov     [rbp+3Fh+var_50], 0C000CE01h
0x14000e5af  xor     r12d, r12d
0x14000e5b2  mov     [rbp+3Fh+var_48], 795h
0x14000e5b9  mov     r15, r9
0x14000e5bc  mov     r14b, r8b
0x14000e5bf  lea     r8, asc_1400156D4; "\b"
0x14000e5c6  lea     r11d, [rdi+24h]
0x14000e5ca  lea     r13d, [rdi-4]
0x14000e5ce  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000e5d5  test    dl, dl
0x14000e5d7  jz      loc_14000E6C5
0x14000e5dd  test    rbx, rbx
0x14000e5e0  jz      short loc_14000E5F1
0x14000e5e2  movzx   ecx, word ptr [rbx]
0x14000e5e5  cmp     [rbx], r12w
0x14000e5e9  jz      short loc_14000E5F4
0x14000e5eb  mov     rdx, [rbx+8]
0x14000e5ef  jmp     short loc_14000E5F7
0x14000e5f1  mov     rcx, rdi
0x14000e5f4  mov     rdx, rsi
0x14000e5f7  mov     [rsp+110h+var_68], r12
0x14000e5ff  test    rbx, rbx
0x14000e602  mov     [rsp+110h+var_70], r13
0x14000e60a  mov     r10d, 305h
0x14000e610  mov     rax, rbx
0x14000e613  cmovz   rax, r8
0x14000e617  lea     r8, [rbp+3Fh+arg_78]
0x14000e61e  mov     [rsp+110h+var_78], r8
0x14000e626  lea     r8, [rbp+3Fh+arg_70]
0x14000e62d  mov     [rsp+110h+var_80], r13
0x14000e635  mov     [rsp+110h+var_88], r8
0x14000e63d  lea     r8, [rbp+3Fh+arg_68]
0x14000e644  mov     [rsp+110h+var_90], r13
0x14000e64c  mov     [rsp+110h+var_98], r8
0x14000e651  lea     r8, [rbp+3Fh+arg_60]
0x14000e658  mov     [rsp+110h+var_A0], r13
0x14000e65d  mov     [rsp+110h+var_A8], r8
0x14000e662  lea     r8, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000e669  mov     [rsp+110h+var_B0], rcx
0x14000e66e  mov     ecx, r10d
0x14000e671  mov     [rsp+110h+var_B8], rdx
0x14000e676  mov     edx, r11d
0x14000e679  mov     [rsp+110h+var_C0], 2
0x14000e682  mov     [rsp+110h+var_C8], rax
0x14000e687  lea     rax, [rbp+3Fh+var_50]
0x14000e68b  mov     [rsp+110h+var_D0], r13
0x14000e690  mov     [rsp+110h+var_D8], rax
0x14000e695  lea     rax, [rbp+3Fh+var_48]
0x14000e699  mov     [rsp+110h+var_E0], r13
0x14000e69e  mov     [rsp+110h+var_E8], rax
0x14000e6a3  mov     [rsp+110h+var_F0], 2Ah ; '*'
0x14000e6ac  call    FastWppTraceMessage
0x14000e6b1  lea     r8, asc_1400156D4; "\b"
0x14000e6b8  mov     r11d, 2Ch ; ','
0x14000e6be  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000e6c5  test    r14b, r14b
0x14000e6c8  jz      loc_14000E7AF
0x14000e6ce  test    rbx, rbx
0x14000e6d1  jz      short loc_14000E6E3
0x14000e6d3  movzx   edi, word ptr [rbx]
0x14000e6d6  cmp     [rbx], r12w
0x14000e6da  jz      short loc_14000E6E0
0x14000e6dc  mov     rsi, [rbx+8]
0x14000e6e0  test    rbx, rbx
0x14000e6e3  mov     [rsp+110h+var_58], r12
0x14000e6eb  lea     rax, [rbp+3Fh+arg_78]
0x14000e6f2  mov     [rsp+110h+var_60], r13
0x14000e6fa  cmovz   rbx, r8
0x14000e6fe  mov     [rsp+110h+var_68], rax
0x14000e706  mov     edx, 3
0x14000e70b  mov     [rsp+110h+var_70], r13
0x14000e713  lea     rax, [rbp+3Fh+arg_70]
0x14000e71a  mov     [rsp+110h+var_78], rax
0x14000e722  mov     rcx, r15
0x14000e725  mov     [rsp+110h+var_80], r13
0x14000e72d  lea     rax, [rbp+3Fh+arg_68]
0x14000e734  mov     [rsp+110h+var_88], rax
0x14000e73c  lea     r8d, [rdx+2]
0x14000e740  mov     [rsp+110h+var_90], r13
0x14000e748  lea     rax, [rbp+3Fh+arg_60]
0x14000e74f  mov     [rsp+110h+var_98], rax
0x14000e754  lea     rax, [rbp+3Fh+var_50]
0x14000e758  mov     [rsp+110h+var_A0], rdi
0x14000e75d  mov     [rsp+110h+var_A8], rsi
0x14000e762  mov     [rsp+110h+var_B0], 2
0x14000e76b  mov     [rsp+110h+var_B8], rbx
0x14000e770  mov     [rsp+110h+var_C0], r13
0x14000e775  mov     [rsp+110h+var_C8], rax
0x14000e77a  lea     rax, [rbp+3Fh+var_48]
0x14000e77e  mov     [rsp+110h+var_D0], r13
0x14000e783  mov     [rsp+110h+var_D8], rax
0x14000e788  mov     [rsp+110h+var_E0], 2Ah ; '*'
0x14000e791  mov     [rsp+110h+var_E8], r9
0x14000e796  lea     r9, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000e79d  mov     word ptr [rsp+110h+var_F0], r11w
0x14000e7a3  call    cs:__imp_WppAutoLogTrace
0x14000e7aa  nop     dword ptr [rax+rax+00h]
0x14000e7af  add     rsp, 0D8h
0x14000e7b6  pop     r15
0x14000e7b8  pop     r14
0x14000e7ba  pop     r13
0x14000e7bc  pop     r12
0x14000e7be  pop     rdi
0x14000e7bf  pop     rsi
0x14000e7c0  pop     rbx
0x14000e7c1  pop     rbp
0x14000e7c2  retn
```

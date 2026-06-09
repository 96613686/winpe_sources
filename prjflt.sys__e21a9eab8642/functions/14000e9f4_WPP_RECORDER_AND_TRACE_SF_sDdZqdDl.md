# WPP_RECORDER_AND_TRACE_SF_sDdZqdDl

- ea: `0x14000e9f4`
- end: `0x14000ec44`
- name: `WPP_RECORDER_AND_TRACE_SF_sDdZqdDl`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022320`

## callees

- `0x140005cf4`
- `0x14000e9f4`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000ec23`
- `WppRecorder!WppAutoLogTrace` at `0x14000ec23`

## string_xrefs

- `0x14000ea49`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x14000eb39`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDdZqdDl(
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
  const wchar_t *v13; // rdi
  __int64 v16; // rcx
  const wchar_t *v17; // rdx
  const wchar_t *v18; // rax
  __int64 v19; // rax
  int v20; // [rsp+20h] [rbp-B1h]
  int v21; // [rsp+C0h] [rbp-11h] BYREF
  _DWORD v22[18]; // [rsp+C8h] [rbp-9h] BYREF
  __int64 v23; // [rsp+180h] [rbp+AFh] BYREF
  va_list va; // [rsp+180h] [rbp+AFh]
  __int64 v25; // [rsp+188h] [rbp+B7h] BYREF
  va_list va1; // [rsp+188h] [rbp+B7h]
  __int64 v27; // [rsp+190h] [rbp+BFh] BYREF
  va_list va2; // [rsp+190h] [rbp+BFh]
  va_list va3; // [rsp+198h] [rbp+C7h] BYREF

  va_start(va3, a12);
  va_start(va2, a12);
  va_start(va1, a12);
  va_start(va, a12);
  v23 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v25 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v27 = va_arg(va3, _QWORD);
  v12 = a12;
  v13 = L"NULL";
  v21 = -1073741595;
  v22[0] = 1587;
  if ( !a2 )
    goto LABEL_10;
  if ( !a12 )
  {
    v16 = 8;
    goto LABEL_6;
  }
  v16 = *a12;
  if ( !*a12 )
  {
LABEL_6:
    v17 = L"NULL";
    goto LABEL_7;
  }
  v17 = (const wchar_t *)*((_QWORD *)a12 + 1);
LABEL_7:
  v18 = a12;
  if ( !a12 )
    v18 = L"\b";
  FastWppTraceMessage(
    517,
    0x23u,
    (ULONGLONG)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
    "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
    42,
    v22,
    4,
    &v21,
    4,
    v18,
    2,
    v17,
    v16,
    va,
    8,
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
    if ( a12 )
    {
      v19 = *a12;
      if ( *a12 )
        v13 = (const wchar_t *)*((_QWORD *)a12 + 1);
    }
    else
    {
      v19 = 8;
    }
    if ( !a12 )
      v12 = L"\b";
    LOWORD(v20) = 35;
    ((void (__fastcall *)(__int64, __int64, __int64, __int64 *, int, const char *, __int64, _DWORD *, __int64, int *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))WppAutoLogTrace)(
      a4,
      2,
      5,
      WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
      v20,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
      42,
      v22,
      4,
      &v21,
      4,
      v12,
      2,
      v13,
      v19,
      (__int64 *)va,
      8,
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
0x14000e9f4  push    rbp
0x14000e9f6  push    rbx
0x14000e9f7  push    rsi
0x14000e9f8  push    rdi
0x14000e9f9  push    r12
0x14000e9fb  push    r13
0x14000e9fd  push    r14
0x14000e9ff  push    r15
0x14000ea01  lea     rbp, [rsp-7]
0x14000ea06  sub     rsp, 0D8h
0x14000ea0d  mov     rbx, [rbp+3Fh+arg_58]
0x14000ea14  lea     rdi, aNull_0; "NULL"
0x14000ea1b  mov     r12d, 8
0x14000ea21  mov     [rbp+3Fh+var_50], 0C00000E5h
0x14000ea28  xor     r15d, r15d
0x14000ea2b  mov     [rbp+3Fh+var_48], 633h
0x14000ea32  mov     r14, r9
0x14000ea35  mov     sil, r8b
0x14000ea38  lea     r8, asc_1400156D4; "\b"
0x14000ea3f  lea     r11d, [r12+1Bh]
0x14000ea44  lea     r13d, [r12-4]
0x14000ea49  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000ea50  test    dl, dl
0x14000ea52  jz      loc_14000EB40
0x14000ea58  test    rbx, rbx
0x14000ea5b  jz      short loc_14000EA6C
0x14000ea5d  movzx   ecx, word ptr [rbx]
0x14000ea60  cmp     [rbx], r15w
0x14000ea64  jz      short loc_14000EA6F
0x14000ea66  mov     rdx, [rbx+8]
0x14000ea6a  jmp     short loc_14000EA72
0x14000ea6c  mov     rcx, r12
0x14000ea6f  mov     rdx, rdi
0x14000ea72  mov     [rsp+110h+var_68], r15
0x14000ea7a  test    rbx, rbx
0x14000ea7d  mov     [rsp+110h+var_70], r13
0x14000ea85  mov     r10d, 205h
0x14000ea8b  mov     rax, rbx
0x14000ea8e  cmovz   rax, r8
0x14000ea92  lea     r8, [rbp+3Fh+arg_78]
0x14000ea99  mov     [rsp+110h+var_78], r8
0x14000eaa1  lea     r8, [rbp+3Fh+arg_70]
0x14000eaa8  mov     [rsp+110h+var_80], r13
0x14000eab0  mov     [rsp+110h+var_88], r8
0x14000eab8  lea     r8, [rbp+3Fh+arg_68]
0x14000eabf  mov     [rsp+110h+var_90], r13
0x14000eac7  mov     [rsp+110h+var_98], r8
0x14000eacc  lea     r8, [rbp+3Fh+arg_60]
0x14000ead3  mov     [rsp+110h+var_A0], r12
0x14000ead8  mov     [rsp+110h+var_A8], r8
0x14000eadd  lea     r8, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000eae4  mov     [rsp+110h+var_B0], rcx
0x14000eae9  mov     ecx, r10d
0x14000eaec  mov     [rsp+110h+var_B8], rdx
0x14000eaf1  mov     edx, r11d
0x14000eaf4  mov     [rsp+110h+var_C0], 2
0x14000eafd  mov     [rsp+110h+var_C8], rax
0x14000eb02  lea     rax, [rbp+3Fh+var_50]
0x14000eb06  mov     [rsp+110h+var_D0], r13
0x14000eb0b  mov     [rsp+110h+var_D8], rax
0x14000eb10  lea     rax, [rbp+3Fh+var_48]
0x14000eb14  mov     [rsp+110h+var_E0], r13
0x14000eb19  mov     [rsp+110h+var_E8], rax
0x14000eb1e  mov     [rsp+110h+var_F0], 2Ah ; '*'
0x14000eb27  call    FastWppTraceMessage
0x14000eb2c  lea     r8, asc_1400156D4; "\b"
0x14000eb33  mov     r11d, 23h ; '#'
0x14000eb39  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000eb40  test    sil, sil
0x14000eb43  jz      loc_14000EC2F
0x14000eb49  test    rbx, rbx
0x14000eb4c  jz      short loc_14000EB5D
0x14000eb4e  movzx   eax, word ptr [rbx]
0x14000eb51  cmp     [rbx], r15w
0x14000eb55  jz      short loc_14000EB60
0x14000eb57  mov     rdi, [rbx+8]
0x14000eb5b  jmp     short loc_14000EB60
0x14000eb5d  mov     rax, r12
0x14000eb60  mov     [rsp+110h+var_58], r15
0x14000eb68  lea     rcx, [rbp+3Fh+arg_78]
0x14000eb6f  mov     [rsp+110h+var_60], r13
0x14000eb77  test    rbx, rbx
0x14000eb7a  mov     [rsp+110h+var_68], rcx
0x14000eb82  mov     edx, 2
0x14000eb87  mov     [rsp+110h+var_70], r13
0x14000eb8f  lea     rcx, [rbp+3Fh+arg_70]
0x14000eb96  mov     [rsp+110h+var_78], rcx
0x14000eb9e  cmovz   rbx, r8
0x14000eba2  mov     [rsp+110h+var_80], r13
0x14000ebaa  lea     rcx, [rbp+3Fh+arg_68]
0x14000ebb1  mov     [rsp+110h+var_88], rcx
0x14000ebb9  lea     r8d, [rdx+3]
0x14000ebbd  mov     [rsp+110h+var_90], r12
0x14000ebc5  lea     rcx, [rbp+3Fh+arg_60]
0x14000ebcc  mov     [rsp+110h+var_98], rcx
0x14000ebd1  mov     rcx, r14
0x14000ebd4  mov     [rsp+110h+var_A0], rax
0x14000ebd9  lea     rax, [rbp+3Fh+var_50]
0x14000ebdd  mov     [rsp+110h+var_A8], rdi
0x14000ebe2  mov     [rsp+110h+var_B0], 2
0x14000ebeb  mov     [rsp+110h+var_B8], rbx
0x14000ebf0  mov     [rsp+110h+var_C0], r13
0x14000ebf5  mov     [rsp+110h+var_C8], rax
0x14000ebfa  lea     rax, [rbp+3Fh+var_48]
0x14000ebfe  mov     [rsp+110h+var_D0], r13
0x14000ec03  mov     [rsp+110h+var_D8], rax
0x14000ec08  mov     [rsp+110h+var_E0], 2Ah ; '*'
0x14000ec11  mov     [rsp+110h+var_E8], r9
0x14000ec16  lea     r9, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000ec1d  mov     word ptr [rsp+110h+var_F0], r11w
0x14000ec23  call    cs:__imp_WppAutoLogTrace
0x14000ec2a  nop     dword ptr [rax+rax+00h]
0x14000ec2f  add     rsp, 0D8h
0x14000ec36  pop     r15
0x14000ec38  pop     r14
0x14000ec3a  pop     r13
0x14000ec3c  pop     r12
0x14000ec3e  pop     rdi
0x14000ec3f  pop     rsi
0x14000ec40  pop     rbx
0x14000ec41  pop     rbp
0x14000ec42  retn
```

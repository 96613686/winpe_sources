# McTemplateU0szzq_EtwEventWriteTransfer

- ea: `0x1800142ac`
- end: `0x1800143a8`
- name: `McTemplateU0szzq_EtwEventWriteTransfer`
- size: `252`
- prototype: `__int64 __fastcall(__int64, __int64, const char *, const wchar_t *, const wchar_t *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800136b0`

## callees

- `0x180007740`
- `0x18000a07c`
- `0x1800142ac`

## pseudocode

```c
__int64 __fastcall McTemplateU0szzq_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const char *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        char a6)
{
  __int64 v6; // rax
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // edx
  __int64 v11; // rcx
  int v12; // ecx
  const wchar_t *v13; // rcx
  bool v14; // zf
  _BYTE v16[16]; // [rsp+30h] [rbp-19h] BYREF
  const char *v17; // [rsp+40h] [rbp-9h]
  int v18; // [rsp+48h] [rbp-1h]
  int v19; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v20; // [rsp+50h] [rbp+7h]
  int v21; // [rsp+58h] [rbp+Fh]
  int v22; // [rsp+5Ch] [rbp+13h]
  const wchar_t *v23; // [rsp+60h] [rbp+17h]
  int v24; // [rsp+68h] [rbp+1Fh]
  int v25; // [rsp+6Ch] [rbp+23h]
  char *v26; // [rsp+70h] [rbp+27h]
  __int64 v27; // [rsp+78h] [rbp+2Fh]

  v6 = -1;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = v8 + 1;
  }
  else
  {
    v9 = 5;
  }
  v18 = v9;
  v19 = 0;
  if ( !a3 )
    a3 = "NULL";
  v10 = 10;
  v17 = a3;
  if ( a4 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v12 = 10;
  }
  v21 = v12;
  v13 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v22 = 0;
  v20 = a4;
  v14 = a5 == 0;
  if ( a5 )
  {
    do
      ++v6;
    while ( a5[v6] );
    v10 = 2 * v6 + 2;
    v14 = a5 == 0;
  }
  v24 = v10;
  v26 = &a6;
  if ( v14 )
    v13 = L"NULL";
  v23 = v13;
  v25 = 0;
  v27 = 4;
  return McGenEventWrite_EtwEventWriteTransfer((__int64)v13, a2, (__int64)L"NULL", 5, (__int64)v16);
}

```

## disassembly

```asm
0x1800142ac  push    rbp
0x1800142ae  lea     rbp, [rsp-47h]
0x1800142b3  sub     rsp, 90h
0x1800142ba  mov     rax, cs:__security_cookie
0x1800142c1  xor     rax, rsp
0x1800142c4  mov     [rbp+47h+var_10], rax
0x1800142c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800142cc  xor     r11d, r11d
0x1800142cf  mov     r10, rdx
0x1800142d2  test    r8, r8
0x1800142d5  jz      short loc_1800142E7
0x1800142d7  mov     rcx, rax
0x1800142da  inc     rcx
0x1800142dd  cmp     [r8+rcx], r11b
0x1800142e1  jnz     short loc_1800142DA
0x1800142e3  inc     ecx
0x1800142e5  jmp     short loc_1800142EC
0x1800142e7  mov     ecx, 5
0x1800142ec  test    r8, r8
0x1800142ef  mov     [rbp+47h+var_48], ecx
0x1800142f2  lea     rdx, aNull; "NULL"
0x1800142f9  mov     [rbp+47h+var_44], r11d
0x1800142fd  cmovz   r8, rdx
0x180014301  mov     edx, 0Ah
0x180014306  mov     [rbp+47h+var_50], r8
0x18001430a  test    r9, r9
0x18001430d  jz      short loc_180014325
0x18001430f  mov     rcx, rax
0x180014312  inc     rcx
0x180014315  cmp     [r9+rcx*2], r11w
0x18001431a  jnz     short loc_180014312
0x18001431c  lea     ecx, ds:2[rcx*2]
0x180014323  jmp     short loc_180014327
0x180014325  mov     ecx, edx
0x180014327  test    r9, r9
0x18001432a  mov     [rbp+47h+var_38], ecx
0x18001432d  mov     rcx, [rbp+47h+arg_20]
0x180014331  lea     r8, aNull_0; "NULL"
0x180014338  cmovz   r9, r8
0x18001433c  mov     [rbp+47h+var_34], r11d
0x180014340  mov     [rbp+47h+var_40], r9
0x180014344  test    rcx, rcx
0x180014347  jz      short loc_18001435D
0x180014349  inc     rax
0x18001434c  cmp     [rcx+rax*2], r11w
0x180014351  jnz     short loc_180014349
0x180014353  lea     edx, ds:2[rax*2]
0x18001435a  test    rcx, rcx
0x18001435d  lea     rax, [rbp+47h+arg_28]
0x180014361  mov     [rbp+47h+var_28], edx
0x180014364  mov     [rbp+47h+var_20], rax
0x180014368  cmovz   rcx, r8
0x18001436c  lea     rax, [rbp+47h+var_60]
0x180014370  mov     [rbp+47h+var_30], rcx
0x180014374  mov     r9d, 5
0x18001437a  mov     [rsp+90h+var_70], rax
0x18001437f  mov     rdx, r10
0x180014382  mov     [rbp+47h+var_24], r11d
0x180014386  mov     [rbp+47h+var_18], 4
0x18001438e  call    McGenEventWrite_EtwEventWriteTransfer
0x180014393  mov     rcx, [rbp+47h+var_10]
0x180014397  xor     rcx, rsp; StackCookie
0x18001439a  call    __security_check_cookie
0x18001439f  add     rsp, 90h
0x1800143a6  pop     rbp
0x1800143a7  retn
```

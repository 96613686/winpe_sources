# DhcpRegExpandString

- ea: `0x18000f528`
- end: `0x18000f6fe`
- name: `DhcpRegExpandString`
- size: `470`
- prototype: `__int64 __fastcall(const wchar_t *Src, void *, char **)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18000e5f8`
- `0x18000f7d4`
- `0x18000f964`

## callees

- `0x180001f90`
- `0x180002160`
- `0x180003210`
- `0x18000d3cc`
- `0x18000f528`
- `0x180010aac`
- `0x180012a00`
- `0x180012b80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f5a7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f5c0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f5ee`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f64a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f5a7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f5c0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f5ee`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f64a`

## pseudocode

```c
__int64 __fastcall DhcpRegExpandString(const wchar_t *Src, void *a2, char **a3)
{
  char **v3; // r14
  __int64 v5; // rax
  __int64 v6; // rcx
  size_t v7; // r13
  __int64 v8; // r15
  wchar_t *i; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  char *v12; // rdi
  unsigned int v13; // ebx
  wchar_t *v14; // r12
  char *v15; // rsi
  void *v16; // rdi
  __int64 v17; // rbx
  char *v18; // rbx
  size_t v19; // rdx
  unsigned int v20; // eax
  __int64 v22; // [rsp+60h] [rbp+8h] BYREF
  void *Srca; // [rsp+68h] [rbp+10h]
  char **v24; // [rsp+70h] [rbp+18h]

  v24 = a3;
  Srca = a2;
  v3 = a3;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    WPP_SF_(1028, 13, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
    a2 = Srca;
  }
  v5 = -1;
  *v3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)a2 + v6) );
  v7 = 2 * v6;
  do
    ++v5;
  while ( Src[v5] );
  v8 = 2 * v5 + 2;
  for ( i = wcschr(Src, 0x3Fu); i; i = wcschr(i + 1, 0x3Fu) )
    v8 += v7 - 2;
  v22 = DhcpAlloc(v8, v10, v11);
  v12 = (char *)v22;
  if ( v22 )
  {
    v14 = wcschr(Src, 0x3Fu);
    v15 = v12;
    if ( v14 )
    {
      v16 = Srca;
      do
      {
        v17 = v14 - Src;
        memcpy_0(v15, Src, 2LL * (int)v17);
        v18 = &v15[2 * v17];
        memcpy_0(v18, v16, v7);
        Src = v14 + 1;
        v15 = &v18[2 * (v7 >> 1)];
        v14 = wcschr(v14 + 1, 0x3Fu);
      }
      while ( v14 );
      v12 = (char *)v22;
      v3 = v24;
    }
    v19 = (v15 - v12) >> 1;
    if ( !v19 )
      v19 = v8;
    v20 = StringCbCopyW((STRSAFE_LPWSTR)v15, v19, Src);
    v13 = WX_WIN32_FROM_HR(v20);
    if ( !v13 )
    {
      *v3 = v12;
      v12 = 0;
      v22 = 0;
    }
  }
  else
  {
    v13 = 8;
  }
  if ( v12 )
  {
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 14, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v13);
    DhcpFree(&v22);
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 15, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18000f528  mov     [rsp+arg_18], rbx
0x18000f52d  mov     [rsp+arg_10], r8
0x18000f532  mov     [rsp+Src], rdx
0x18000f537  push    rbp
0x18000f538  push    rsi
0x18000f539  push    rdi
0x18000f53a  push    r12
0x18000f53c  push    r13
0x18000f53e  push    r14
0x18000f540  push    r15
0x18000f542  sub     rsp, 20h
0x18000f546  mov     r14, r8
0x18000f549  mov     rbp, rcx
0x18000f54c  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000f553  jz      short loc_18000F570
0x18000f555  mov     edx, 0Dh
0x18000f55a  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000f561  mov     ecx, 404h
0x18000f566  call    WPP_SF_
0x18000f56b  mov     rdx, [rsp+58h+Src]
0x18000f570  xor     esi, esi
0x18000f572  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f576  mov     [r14], rsi
0x18000f579  mov     rcx, rax
0x18000f57c  inc     rcx
0x18000f57f  cmp     [rdx+rcx*2], si
0x18000f583  jnz     short loc_18000F57C
0x18000f585  lea     r13, [rcx+rcx]
0x18000f589  inc     rax
0x18000f58c  cmp     [rbp+rax*2+0], si
0x18000f591  jnz     short loc_18000F589
0x18000f593  mov     r12d, 3Fh ; '?'
0x18000f599  lea     r15, ds:2[rax*2]
0x18000f5a1  mov     edx, r12d; Ch
0x18000f5a4  mov     rcx, rbp; Str
0x18000f5a7  call    cs:__imp_wcschr
0x18000f5ad  test    rax, rax
0x18000f5b0  jz      short loc_18000F5CB
0x18000f5b2  lea     rbx, [r13-2]
0x18000f5b6  mov     edx, r12d; Ch
0x18000f5b9  lea     rcx, [rax+2]; Str
0x18000f5bd  add     r15, rbx
0x18000f5c0  call    cs:__imp_wcschr
0x18000f5c6  test    rax, rax
0x18000f5c9  jnz     short loc_18000F5B6
0x18000f5cb  mov     rcx, r15
0x18000f5ce  call    DhcpAlloc
0x18000f5d3  mov     [rsp+58h+arg_0], rax
0x18000f5d8  mov     rdi, rax
0x18000f5db  test    rax, rax
0x18000f5de  jnz     short loc_18000F5E8
0x18000f5e0  lea     ebx, [rax+8]
0x18000f5e3  jmp     loc_18000F694
0x18000f5e8  mov     edx, r12d; Ch
0x18000f5eb  mov     rcx, rbp; Str
0x18000f5ee  call    cs:__imp_wcschr
0x18000f5f4  mov     r12, rax
0x18000f5f7  mov     rsi, rdi
0x18000f5fa  test    rax, rax
0x18000f5fd  jz      short loc_18000F662
0x18000f5ff  mov     rdi, [rsp+58h+Src]
0x18000f604  mov     r14, r13
0x18000f607  shr     r14, 1
0x18000f60a  add     r14, r14
0x18000f60d  mov     rbx, r12
0x18000f610  mov     rdx, rbp; Src
0x18000f613  sub     rbx, rbp
0x18000f616  mov     rcx, rsi; void *
0x18000f619  sar     rbx, 1
0x18000f61c  movsxd  r8, ebx
0x18000f61f  add     r8, r8; Size
0x18000f622  call    memcpy_0
0x18000f627  lea     rbx, [rsi+rbx*2]
0x18000f62b  mov     r8, r13; Size
0x18000f62e  mov     rcx, rbx; void *
0x18000f631  mov     rdx, rdi; Src
0x18000f634  call    memcpy_0
0x18000f639  lea     rbp, [r12+2]
0x18000f63e  mov     edx, 3Fh ; '?'; Ch
0x18000f643  mov     rcx, rbp; Str
0x18000f646  lea     rsi, [rbx+r14]
0x18000f64a  call    cs:__imp_wcschr
0x18000f650  mov     r12, rax
0x18000f653  test    rax, rax
0x18000f656  jnz     short loc_18000F60D
0x18000f658  mov     rdi, [rsp+58h+arg_0]
0x18000f65d  mov     r14, [rsp+58h+arg_10]
0x18000f662  mov     rdx, rsi
0x18000f665  mov     r8, rbp; pszSrc
0x18000f668  sub     rdx, rdi
0x18000f66b  mov     rcx, rsi; pszDest
0x18000f66e  sar     rdx, 1
0x18000f671  jnz     short loc_18000F676
0x18000f673  mov     rdx, r15; cbDest
0x18000f676  call    StringCbCopyW
0x18000f67b  mov     ecx, eax
0x18000f67d  call    WX_WIN32_FROM_HR
0x18000f682  xor     esi, esi
0x18000f684  mov     ebx, eax
0x18000f686  test    eax, eax
0x18000f688  jnz     short loc_18000F694
0x18000f68a  mov     [r14], rdi
0x18000f68d  mov     edi, esi
0x18000f68f  mov     [rsp+58h+arg_0], rsi
0x18000f694  test    rdi, rdi
0x18000f697  jz      short loc_18000F6C5
0x18000f699  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000f6a0  jz      short loc_18000F6BB
0x18000f6a2  mov     edx, 0Eh
0x18000f6a7  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000f6ae  mov     ecx, 401h
0x18000f6b3  mov     r9d, ebx
0x18000f6b6  call    WPP_SF_d
0x18000f6bb  lea     rcx, [rsp+58h+arg_0]
0x18000f6c0  call    DhcpFree
0x18000f6c5  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000f6cc  jz      short loc_18000F6E7
0x18000f6ce  mov     edx, 0Fh
0x18000f6d3  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000f6da  mov     ecx, 404h
0x18000f6df  mov     r9d, ebx
0x18000f6e2  call    WPP_SF_d
0x18000f6e7  mov     eax, ebx
0x18000f6e9  mov     rbx, [rsp+58h+arg_18]
0x18000f6ee  add     rsp, 20h
0x18000f6f2  pop     r15
0x18000f6f4  pop     r14
0x18000f6f6  pop     r13
0x18000f6f8  pop     r12
0x18000f6fa  pop     rdi
0x18000f6fb  pop     rsi
0x18000f6fc  pop     rbp
0x18000f6fd  retn
```

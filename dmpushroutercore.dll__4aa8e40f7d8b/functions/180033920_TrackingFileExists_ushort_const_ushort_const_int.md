# TrackingFileExists(ushort const *,ushort const *,int *)

- ea: `0x180033920`
- end: `0x180033a53`
- name: `?TrackingFileExists@@YAJPEBG0PEAH@Z`
- size: `307`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002feec`
- `0x180032e3c`
- `0x180032ea8`

## callees

- `0x18000bab4`
- `0x180031bfc`
- `0x180032d0c`
- `0x180033920`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800339bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800339bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033a3b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800339dc`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800339dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TrackingFileExists(const unsigned __int16 *a1, const unsigned __int16 *a2, int *a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int StoragePath; // eax
  HRESULT v9; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HLOCAL hMem; // [rsp+30h] [rbp+8h] BYREF
  PWSTR ppszPathOut; // [rsp+48h] [rbp+20h] BYREF

  if ( !a1 )
  {
    v5 = 397;
LABEL_3:
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)0x80070057LL,
      v10);
    return v6;
  }
  if ( !a2 )
  {
    v5 = 398;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v5 = 399;
    goto LABEL_3;
  }
  *a3 = 0;
  hMem = 0;
  StoragePath = GetStoragePath(a1, (PWSTR *)&hMem);
  v6 = StoragePath;
  if ( StoragePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)StoragePath,
      v10);
LABEL_11:
    if ( hMem )
      LocalFree(hMem);
    return v6;
  }
  ppszPathOut = 0;
  v9 = PathAllocCombine((PCWSTR)hMem, a2, 0, &ppszPathOut);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)v9,
      v10);
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    goto LABEL_11;
  }
  *a3 = FileExists(ppszPathOut);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x180033920  mov     [rsp+arg_8], rbx
0x180033925  mov     [rsp+arg_10], rsi
0x18003392a  push    rdi; int
0x18003392b  sub     rsp, 20h
0x18003392f  mov     rdi, r8
0x180033932  mov     rsi, rdx
0x180033935  test    rcx, rcx
0x180033938  jnz     short loc_18003395F
0x18003393a  mov     edx, 18Dh; void *
0x18003393f  mov     ebx, 80070057h
0x180033944  mov     rcx, [rsp+28h]; this
0x180033949  mov     r9d, ebx; char *
0x18003394c  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033953  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033958  mov     eax, ebx
0x18003395a  jmp     loc_180033A43
0x18003395f  test    rsi, rsi
0x180033962  jnz     short loc_18003396B
0x180033964  mov     edx, 18Eh
0x180033969  jmp     short loc_18003393F
0x18003396b  test    rdi, rdi
0x18003396e  jnz     short loc_180033977
0x180033970  mov     edx, 18Fh
0x180033975  jmp     short loc_18003393F
0x180033977  mov     dword ptr [r8], 0
0x18003397e  mov     [rsp+28h+hMem], 0
0x180033987  lea     rdx, [rsp+28h+hMem]; ppszPathOut
0x18003398c  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x180033991  mov     ebx, eax
0x180033993  test    eax, eax
0x180033995  jns     short loc_1800339C3
0x180033997  mov     rcx, [rsp+28h]; this
0x18003399c  mov     r9d, eax; char *
0x18003399f  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800339a6  mov     edx, 193h; void *
0x1800339ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800339b0  nop
0x1800339b1  mov     rcx, [rsp+28h+hMem]; hMem
0x1800339b6  test    rcx, rcx
0x1800339b9  jz      short loc_180033958
0x1800339bb  call    cs:__imp_LocalFree
0x1800339c1  jmp     short loc_180033958
0x1800339c3  mov     [rsp+28h+ppszPathOut], 0
0x1800339cc  lea     r9, [rsp+28h+ppszPathOut]; ppszPathOut
0x1800339d1  xor     r8d, r8d; dwFlags
0x1800339d4  mov     rdx, rsi; pszMore
0x1800339d7  mov     rcx, [rsp+28h+hMem]; pszPathIn
0x1800339dc  call    cs:__imp_PathAllocCombine
0x1800339e2  mov     ebx, eax
0x1800339e4  test    eax, eax
0x1800339e6  jns     short loc_180033A14
0x1800339e8  mov     rcx, [rsp+28h]; this
0x1800339ed  mov     r9d, eax; char *
0x1800339f0  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800339f7  mov     edx, 195h; void *
0x1800339fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033a01  nop
0x180033a02  mov     rcx, [rsp+28h+ppszPathOut]; hMem
0x180033a07  test    rcx, rcx
0x180033a0a  jz      short loc_1800339B1
0x180033a0c  call    cs:__imp_LocalFree
0x180033a12  jmp     short loc_1800339B1
0x180033a14  mov     rcx, [rsp+28h+ppszPathOut]; unsigned __int16 *
0x180033a19  call    ?FileExists@@YAHPEBG@Z; FileExists(ushort const *)
0x180033a1e  mov     [rdi], eax
0x180033a20  mov     rcx, [rsp+28h+ppszPathOut]; hMem
0x180033a25  test    rcx, rcx
0x180033a28  jz      short loc_180033A31
0x180033a2a  call    cs:__imp_LocalFree
0x180033a30  nop
0x180033a31  mov     rcx, [rsp+28h+hMem]; hMem
0x180033a36  test    rcx, rcx
0x180033a39  jz      short loc_180033A41
0x180033a3b  call    cs:__imp_LocalFree
0x180033a41  xor     eax, eax
0x180033a43  mov     rbx, [rsp+28h+arg_8]
0x180033a48  mov     rsi, [rsp+28h+arg_10]
0x180033a4d  add     rsp, 20h
0x180033a51  pop     rdi
0x180033a52  retn
```

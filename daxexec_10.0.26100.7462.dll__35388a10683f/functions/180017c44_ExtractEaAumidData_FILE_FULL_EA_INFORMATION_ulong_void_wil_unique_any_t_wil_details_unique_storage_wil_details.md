# ExtractEaAumidData(_FILE_FULL_EA_INFORMATION *,ulong,void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,bool,bool &)

- ea: `0x180017c44`
- end: `0x180017fda`
- name: `?ExtractEaAumidData@@YAJPEAU_FILE_FULL_EA_INFORMATION@@KPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@_NAEA_N@Z`
- size: `918`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b8b4`

## callees

- `0x1800053a0`
- `0x180005794`
- `0x180006158`
- `0x1800093a0`
- `0x18000b3c9`
- `0x18000e214`
- `0x18000e234`
- `0x180017c44`
- `0x18001c5ac`
- `0x18001e304`
- `0x18001fae8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017cca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017cca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180017d5b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180017d5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017d7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017d7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017cbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017ddb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017dff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017edb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017cbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017ddb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017dff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017edb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f98`
- `ntdll!strncmp` at `0x180017d07`
- `ntdll!strncmp` at `0x180017d07`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180017eac`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180017eac`

## string_xrefs

- `0x180017e1a`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180017ec0`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180017f74`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180017fbc`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
int __fastcall ExtractEaAumidData(__int64 a1, unsigned int a2, void *a3, const void **a4, char a5, bool *a6)
{
  __int64 v9; // r9
  __int64 v10; // rdx
  void *v11; // r15
  HLOCAL v12; // rdi
  DWORD v13; // r12d
  DWORD LastError; // ebx
  __int64 v15; // r13
  unsigned int v16; // r15d
  HLOCAL v17; // rax
  void *v18; // rbx
  const char *v20; // r9
  int v21; // ebx
  __int64 v22; // rax
  unsigned int v23; // r14d
  unsigned int v24; // r15d
  char *v25; // rax
  char *v26; // rbx
  int v27; // eax
  unsigned __int64 v28; // rdx
  int v29; // esi
  unsigned __int64 v30; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-60h]
  int bIgnoreCasea; // [rsp+20h] [rbp-60h]
  unsigned int v33; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-48h] BYREF
  HLOCAL v35; // [rsp+40h] [rbp-40h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-38h]
  bool *v37; // [rsp+50h] [rbp-30h]
  _BYTE FileInformation[24]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  hFile = a3;
  v37 = a6;
  *a6 = 0;
  if ( !a3 )
  {
    v9 = 3221225485LL;
    v10 = 1235;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v10,
             (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
             (const char *)v9,
             bIgnoreCase);
  }
  v11 = (void *)*a4;
  v12 = 0;
  v33 = 0;
  v13 = 0;
  if ( v11 )
  {
    LastError = GetLastError();
    LocalFree(v11);
    SetLastError(LastError);
  }
  *a4 = 0;
  if ( a2 < 0xC )
  {
    v9 = 3221225507LL;
LABEL_22:
    v10 = 1241;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v10,
             (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
             (const char *)v9,
             bIgnoreCase);
  }
  if ( *(_BYTE *)(a1 + 5) != 40 || strncmp("MICROSOFT.WINDOWS.SPARSEGENERATION.AUMID", (const char *)(a1 + 8), 0x28u) )
  {
LABEL_21:
    v9 = 3221225485LL;
    goto LABEL_22;
  }
  if ( *(_WORD *)(a1 + 6) )
  {
    v15 = *(unsigned __int8 *)(a1 + 5);
    v16 = *(unsigned __int16 *)(a1 + 6) >> 1;
    if ( v16 <= 3 )
    {
      v9 = 3221227787LL;
      goto LABEL_22;
    }
    if ( CompareStringOrdinal((LPCWCH)(v15 + a1 + 9), 3, L"V1 ", 3, 0) == 2 )
    {
      v17 = LocalAlloc(0x40u, 2LL * (v16 + 1));
      v18 = v17;
      if ( !v17 )
      {
        v9 = 3221225495LL;
        goto LABEL_22;
      }
      memcpy_0(v17, (const void *)(v15 + a1 + 9), *(unsigned __int16 *)(a1 + 6));
      hMem = 0;
      v35 = 0;
      if ( !(unsigned int)ParseAutoSparseEAData(
                            (const unsigned __int16 *)v18,
                            v16,
                            (unsigned __int8 **)&v35,
                            &v33,
                            (unsigned __int16 **)&hMem) )
      {
        if ( hMem )
          LocalFree(hMem);
        if ( v35 )
          LocalFree(v35);
        LocalFree(v18);
        goto LABEL_21;
      }
      v12 = v35;
      *a4 = hMem;
      LocalFree(v18);
      v13 = v33;
    }
  }
  if ( !*a4 )
    return 0;
  if ( !a5 )
  {
LABEL_27:
    if ( v12 )
      LocalFree(v12);
    return 0;
  }
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandleEx(hFile, MaximumFileInfoByHandleClass, FileInformation, 0x18u) )
  {
    v21 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x4E8,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            v20);
LABEL_32:
    if ( v12 )
      LocalFree(v12);
    return v21;
  }
  v22 = -1;
  do
    ++v22;
  while ( *((_WORD *)*a4 + v22) );
  v23 = 2 * v22;
  v24 = 2 * v22 + 24;
  v25 = (char *)operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v25;
  if ( !v25 )
  {
    v21 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EF,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    goto LABEL_32;
  }
  memset_0(v25, 0, v24);
  *(_QWORD *)v26 = *(_QWORD *)FileInformation;
  *(_OWORD *)(v26 + 8) = *(_OWORD *)&FileInformation[8];
  memcpy_0(v26 + 24, *a4, v23);
  v27 = VerifyEASignature((const unsigned __int8 *)v26, v24, (BYTE *)v12, v13, v37);
  v29 = v27;
  if ( v27 >= 0 )
  {
    operator delete(v26, v28);
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x502,
    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
    (const char *)(unsigned int)v27,
    bIgnoreCasea);
  operator delete(v26, v30);
  if ( v12 )
    LocalFree(v12);
  return v29;
}

```

## disassembly

```asm
0x180017c44  mov     [rsp-38h+arg_8], rbx
0x180017c49  push    rbp
0x180017c4a  push    rsi
0x180017c4b  push    rdi
0x180017c4c  push    r12
0x180017c4e  push    r13
0x180017c50  push    r14
0x180017c52  push    r15
0x180017c54  mov     rbp, rsp
0x180017c57  sub     rsp, 80h
0x180017c5e  mov     rax, cs:__security_cookie
0x180017c65  xor     rax, rsp
0x180017c68  mov     [rbp+var_10], rax
0x180017c6c  xor     ebx, ebx
0x180017c6e  mov     [rbp+hFile], r8
0x180017c72  mov     r14, rcx
0x180017c75  mov     rcx, [rbp+arg_28]
0x180017c79  mov     [rbp+var_30], rcx
0x180017c7d  mov     rsi, r9
0x180017c80  mov     r13d, edx
0x180017c83  mov     [rcx], bl
0x180017c85  test    r8, r8
0x180017c88  jnz     short loc_180017C9A
0x180017c8a  mov     r9d, 0C000000Dh
0x180017c90  mov     edx, 4D3h
0x180017c95  jmp     loc_180017E16
0x180017c9a  mov     r15, [r9]
0x180017c9d  mov     rdi, rbx
0x180017ca0  mov     [rbp+var_50], ebx
0x180017ca3  mov     r12d, ebx
0x180017ca6  test    r15, r15
0x180017ca9  jz      short loc_180017CD8
0x180017cab  call    cs:__imp_GetLastError
0x180017cb2  nop     dword ptr [rax+rax+00h]
0x180017cb7  mov     rcx, r15; hMem
0x180017cba  mov     ebx, eax
0x180017cbc  call    cs:__imp_LocalFree
0x180017cc3  nop     dword ptr [rax+rax+00h]
0x180017cc8  mov     ecx, ebx; dwErrCode
0x180017cca  call    cs:__imp_SetLastError
0x180017cd1  nop     dword ptr [rax+rax+00h]
0x180017cd6  xor     ebx, ebx
0x180017cd8  mov     [rsi], rbx
0x180017cdb  cmp     r13d, 0Ch
0x180017cdf  jnb     short loc_180017CEC
0x180017ce1  mov     r9d, 0C0000023h
0x180017ce7  jmp     loc_180017E11
0x180017cec  mov     r8d, 28h ; '('; MaxCount
0x180017cf2  cmp     [r14+5], r8b
0x180017cf6  jnz     loc_180017E0B
0x180017cfc  lea     rdx, [r14+8]; Str2
0x180017d00  lea     rcx, Str1; "MICROSOFT.WINDOWS.SPARSEGENERATION.AUMI"...
0x180017d07  call    cs:__imp_strncmp
0x180017d0e  nop     dword ptr [rax+rax+00h]
0x180017d13  test    eax, eax
0x180017d15  jnz     loc_180017E0B
0x180017d1b  cmp     [r14+6], bx
0x180017d20  jbe     loc_180017E6E
0x180017d26  movzx   r15d, word ptr [r14+6]
0x180017d2b  lea     edx, [rax+3]; cchCount1
0x180017d2e  movzx   r13d, byte ptr [r14+5]
0x180017d33  shr     r15d, 1
0x180017d36  cmp     r15d, edx
0x180017d39  ja      short loc_180017D46
0x180017d3b  mov     r9d, 0C000090Bh
0x180017d41  jmp     loc_180017E11
0x180017d46  lea     rcx, [r14+9]
0x180017d4a  mov     [rsp+80h+bIgnoreCase], ebx; bIgnoreCase
0x180017d4e  add     rcx, r13; lpString1
0x180017d51  lea     r8, String2; "V1 "
0x180017d58  mov     r9d, edx; cchCount2
0x180017d5b  call    cs:__imp_CompareStringOrdinal
0x180017d62  nop     dword ptr [rax+rax+00h]
0x180017d67  cmp     eax, 2
0x180017d6a  jnz     loc_180017E6E
0x180017d70  lea     edx, [r15+1]
0x180017d74  add     rdx, rdx; uBytes
0x180017d77  lea     ecx, [rax+3Eh]; uFlags
0x180017d7a  call    cs:__imp_LocalAlloc
0x180017d81  nop     dword ptr [rax+rax+00h]
0x180017d86  mov     rbx, rax
0x180017d89  test    rax, rax
0x180017d8c  jnz     short loc_180017D96
0x180017d8e  mov     r9d, 0C0000017h
0x180017d94  jmp     short loc_180017E11
0x180017d96  movzx   r8d, word ptr [r14+6]; Size
0x180017d9b  lea     rdx, [r14+9]
0x180017d9f  add     rdx, r13; Src
0x180017da2  mov     rcx, rbx; void *
0x180017da5  call    memcpy_0
0x180017daa  lea     rax, [rbp+hMem]
0x180017dae  mov     [rbp+hMem], rdi
0x180017db2  lea     r9, [rbp+var_50]; unsigned int *
0x180017db6  mov     qword ptr [rsp+80h+bIgnoreCase], rax; int
0x180017dbb  lea     r8, [rbp+var_40]; unsigned __int8 **
0x180017dbf  mov     [rbp+var_40], rdi
0x180017dc3  mov     edx, r15d; unsigned int
0x180017dc6  mov     rcx, rbx; unsigned __int16 *
0x180017dc9  call    ?ParseAutoSparseEAData@@YAHPEBGIPEAPEAEPEAIPEAPEAG@Z; ParseAutoSparseEAData(ushort const *,uint,uchar * *,uint *,ushort * *)
0x180017dce  test    eax, eax
0x180017dd0  jnz     short loc_180017E4E
0x180017dd2  mov     rcx, [rbp+hMem]; hMem
0x180017dd6  test    rcx, rcx
0x180017dd9  jz      short loc_180017DE7
0x180017ddb  call    cs:__imp_LocalFree
0x180017de2  nop     dword ptr [rax+rax+00h]
0x180017de7  mov     rcx, [rbp+var_40]; hMem
0x180017deb  test    rcx, rcx
0x180017dee  jz      short loc_180017DFC
0x180017df0  call    cs:__imp_LocalFree
0x180017df7  nop     dword ptr [rax+rax+00h]
0x180017dfc  mov     rcx, rbx; hMem
0x180017dff  call    cs:__imp_LocalFree
0x180017e06  nop     dword ptr [rax+rax+00h]
0x180017e0b  mov     r9d, 0C000000Dh; char *
0x180017e11  mov     edx, 4D9h; void *
0x180017e16  mov     rcx, [rbp+38h]; this
0x180017e1a  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180017e21  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180017e26  mov     rcx, [rbp+var_10]
0x180017e2a  xor     rcx, rsp; StackCookie
0x180017e2d  call    __security_check_cookie
0x180017e32  mov     rbx, [rsp+80h+arg_8]
0x180017e3a  add     rsp, 80h
0x180017e41  pop     r15
0x180017e43  pop     r14
0x180017e45  pop     r13
0x180017e47  pop     r12
0x180017e49  pop     rdi
0x180017e4a  pop     rsi
0x180017e4b  pop     rbp
0x180017e4c  retn
0x180017e4e  mov     rax, [rbp+hMem]
0x180017e52  mov     rcx, rbx; hMem
0x180017e55  mov     rdi, [rbp+var_40]
0x180017e59  mov     [rsi], rax
0x180017e5c  call    cs:__imp_LocalFree
0x180017e63  nop     dword ptr [rax+rax+00h]
0x180017e68  mov     r12d, [rbp+var_50]
0x180017e6c  xor     ebx, ebx
0x180017e6e  cmp     [rsi], rbx
0x180017e71  jz      short loc_180017E8C
0x180017e73  cmp     [rbp+arg_20], bl
0x180017e76  jnz     short loc_180017E90
0x180017e78  test    rdi, rdi
0x180017e7b  jz      short loc_180017E8C
0x180017e7d  mov     rcx, rdi; hMem
0x180017e80  call    cs:__imp_LocalFree
0x180017e87  nop     dword ptr [rax+rax+00h]
0x180017e8c  xor     eax, eax
0x180017e8e  jmp     short loc_180017E26
0x180017e90  mov     rcx, [rbp+hFile]; hFile
0x180017e94  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180017e98  xor     eax, eax
0x180017e9a  xorps   xmm0, xmm0
0x180017e9d  movups  [rbp+FileInformation], xmm0
0x180017ea1  mov     [rbp+var_18], rax
0x180017ea5  lea     r9d, [rax+18h]; dwBufferSize
0x180017ea9  lea     edx, [rax+12h]; FileInformationClass
0x180017eac  call    cs:__imp_GetFileInformationByHandleEx
0x180017eb3  nop     dword ptr [rax+rax+00h]
0x180017eb8  test    eax, eax
0x180017eba  jnz     short loc_180017EEE
0x180017ebc  mov     rcx, [rbp+38h]; this
0x180017ec0  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180017ec7  mov     edx, 4E8h; void *
0x180017ecc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017ed1  mov     ebx, eax
0x180017ed3  test    rdi, rdi
0x180017ed6  jz      short loc_180017EE7
0x180017ed8  mov     rcx, rdi; hMem
0x180017edb  call    cs:__imp_LocalFree
0x180017ee2  nop     dword ptr [rax+rax+00h]
0x180017ee7  mov     eax, ebx
0x180017ee9  jmp     loc_180017E26
0x180017eee  mov     rcx, [rsi]
0x180017ef1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017ef5  inc     rax
0x180017ef8  cmp     [rcx+rax*2], bx
0x180017efc  jnz     short loc_180017EF5
0x180017efe  lea     r14d, [rax+rax]
0x180017f02  lea     r15d, [r14+18h]
0x180017f06  mov     ecx, r15d; unsigned __int64
0x180017f09  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017f10  mov     r13d, r15d
0x180017f13  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017f18  mov     rbx, rax
0x180017f1b  test    rax, rax
0x180017f1e  jz      loc_180017FB8
0x180017f24  mov     r8d, r13d; Size
0x180017f27  xor     edx, edx; Val
0x180017f29  mov     rcx, rax; void *
0x180017f2c  call    memset_0
0x180017f31  mov     rcx, qword ptr [rbp+FileInformation]
0x180017f35  mov     [rbx], rcx
0x180017f38  lea     rcx, [rbx+18h]; void *
0x180017f3c  movups  xmm0, [rbp+FileInformation+8]
0x180017f40  mov     r8d, r14d; Size
0x180017f43  movdqu  xmmword ptr [rbx+8], xmm0
0x180017f48  mov     rdx, [rsi]; Src
0x180017f4b  call    memcpy_0
0x180017f50  mov     rax, [rbp+var_30]
0x180017f54  mov     r9d, r12d; unsigned int
0x180017f57  mov     r8, rdi; unsigned __int8 *
0x180017f5a  mov     qword ptr [rsp+80h+bIgnoreCase], rax; int
0x180017f5f  mov     edx, r15d; unsigned int
0x180017f62  mov     rcx, rbx; unsigned __int8 *
0x180017f65  call    ?VerifyEASignature@@YAJPEBEK0IAEA_N@Z; VerifyEASignature(uchar const *,ulong,uchar const *,uint,bool &)
0x180017f6a  mov     esi, eax
0x180017f6c  test    eax, eax
0x180017f6e  jns     short loc_180017FAB
0x180017f70  mov     rcx, [rbp+38h]; this
0x180017f74  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180017f7b  mov     r9d, eax; char *
0x180017f7e  mov     edx, 502h; void *
0x180017f83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017f88  mov     rcx, rbx; void *
0x180017f8b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017f90  test    rdi, rdi
0x180017f93  jz      short loc_180017FA4
0x180017f95  mov     rcx, rdi; hMem
0x180017f98  call    cs:__imp_LocalFree
0x180017f9f  nop     dword ptr [rax+rax+00h]
0x180017fa4  mov     eax, esi
0x180017fa6  jmp     loc_180017E26
0x180017fab  mov     rcx, rbx; void *
0x180017fae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017fb3  jmp     loc_180017E78
0x180017fb8  mov     rcx, [rbp+38h]; this
0x180017fbc  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180017fc3  mov     ebx, 8007000Eh
0x180017fc8  mov     edx, 4EFh; void *
0x180017fcd  mov     r9d, ebx; char *
0x180017fd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017fd5  jmp     loc_180017ED3
```

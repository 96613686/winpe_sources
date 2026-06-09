# Container::Manager::Image::_anonymous_namespace_::RebuildCatDb

- ea: `0x14001c440`
- end: `0x14001c6de`
- name: `Container::Manager::Image::_anonymous_namespace_::RebuildCatDb`
- size: `670`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x140016da0`

## callees

- `0x140002344`
- `0x140006fc4`
- `0x140006fe4`
- `0x14000a9b8`
- `0x14000cd84`
- `0x14000d7bc`
- `0x14001c440`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c5f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c5f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001c61d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001c68b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001c61d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001c68b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14001c584`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14001c584`

## string_xrefs

- `0x14001c4a2`: `Windows\System32`
- `0x14001c505`: `CryptCatSvc.dll`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::RebuildCatDb(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rdx
  HMODULE LibraryW; // rax
  const char *v5; // r9
  HMODULE v6; // rbx
  unsigned int LastError; // ebx
  FARPROC ProcAddress; // rax
  const char *v9; // r9
  unsigned int v10; // eax
  unsigned int v11; // edi
  unsigned int v12; // eax
  const wchar_t *v13; // [rsp+20h] [rbp-50h] BYREF
  __int64 v14; // [rsp+28h] [rbp-48h]
  void *v15; // [rsp+30h] [rbp-40h] BYREF
  char *v16; // [rsp+38h] [rbp-38h]
  _WORD v17[8]; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+50h] [rbp-20h] BYREF
  _WORD v19[8]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v15 = v17;
  v16 = (char *)v17;
  v17[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)&v15,
          *(const void **)a1,
          (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1) )
  {
    v1 = 1189;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v1,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
LABEL_12:
    if ( v15 != v17 )
      operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v13 = L"Windows\\System32";
  v14 = 16;
  if ( !Csl::Path::Append((Csl::Path *)&v15, &v13) )
  {
    v1 = 1190;
    goto LABEL_3;
  }
  lpLibFileName[0] = v19;
  lpLibFileName[1] = v19;
  v19[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)lpLibFileName,
          v15,
          (v16 - (_BYTE *)v15) >> 1) )
  {
    v2 = 1193;
    goto LABEL_10;
  }
  v13 = L"CryptCatSvc.dll";
  v14 = 15;
  if ( !Csl::Path::Append((Csl::Path *)lpLibFileName, &v13) )
  {
    v2 = 1194;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    if ( lpLibFileName[0] != v19 )
      operator delete((void *)lpLibFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_12;
  }
  LibraryW = LoadLibraryW(lpLibFileName[0]);
  v6 = LibraryW;
  if ( !LibraryW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4AD,
                  (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
                  v5);
    if ( lpLibFileName[0] != v19 )
      operator delete((void *)lpLibFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v15 != v17 )
      operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
    return LastError;
  }
  ProcAddress = GetProcAddress(LibraryW, "CatDbOfflineRebuildDatabasesW");
  if ( !ProcAddress )
  {
    v10 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x4B3,
            (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
            v9);
LABEL_23:
    v11 = v10;
    FreeLibrary(v6);
    if ( lpLibFileName[0] != v19 )
      operator delete((void *)lpLibFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v15 != v17 )
      operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
    return v11;
  }
  v12 = ((__int64 (__fastcall *)(void *, _QWORD))ProcAddress)(v15, 0);
  if ( v12 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4B5,
            (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
            (const char *)v12);
    goto LABEL_23;
  }
  FreeLibrary(v6);
  if ( lpLibFileName[0] != v19 )
    operator delete((void *)lpLibFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v15 != v17 )
    operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x14001c440  mov     [rsp-8+arg_0], rbx
0x14001c445  mov     [rsp-8+arg_8], rdi
0x14001c44a  push    rbp
0x14001c44b  mov     rbp, rsp
0x14001c44e  sub     rsp, 70h
0x14001c452  lea     rax, [rbp+var_30]
0x14001c456  mov     [rbp+var_40], rax
0x14001c45a  lea     rax, [rbp+var_30]
0x14001c45e  mov     [rbp+var_38], rax
0x14001c462  xor     eax, eax
0x14001c464  mov     [rbp+var_30], ax
0x14001c468  mov     r8, [rcx+8]
0x14001c46c  sub     r8, [rcx]
0x14001c46f  sar     r8, 1
0x14001c472  mov     rdx, [rcx]
0x14001c475  lea     rcx, [rbp+var_40]
0x14001c479  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14001c47e  test    al, al
0x14001c480  jnz     short loc_14001C4A2
0x14001c482  mov     edx, 4A5h; void *
0x14001c487  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001c48e  mov     r9d, 8007000Eh; char *
0x14001c494  mov     rcx, [rbp+8]; this
0x14001c498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c49d  jmp     loc_14001C55D
0x14001c4a2  lea     rax, aWindowsSystem3_0; "Windows\\System32"
0x14001c4a9  mov     [rbp+var_50], rax
0x14001c4ad  mov     [rbp+var_48], 10h
0x14001c4b5  lea     rdx, [rbp+var_50]
0x14001c4b9  lea     rcx, [rbp+var_40]; this
0x14001c4bd  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001c4c2  test    al, al
0x14001c4c4  jnz     short loc_14001C4CD
0x14001c4c6  mov     edx, 4A6h
0x14001c4cb  jmp     short loc_14001C487
0x14001c4cd  lea     rax, [rbp+var_10]
0x14001c4d1  mov     [rbp+lpLibFileName], rax
0x14001c4d5  lea     rax, [rbp+var_10]
0x14001c4d9  mov     [rbp+var_18], rax
0x14001c4dd  xor     eax, eax
0x14001c4df  mov     [rbp+var_10], ax
0x14001c4e3  mov     rdx, [rbp+var_40]
0x14001c4e7  mov     r8, [rbp+var_38]
0x14001c4eb  sub     r8, rdx
0x14001c4ee  sar     r8, 1
0x14001c4f1  lea     rcx, [rbp+lpLibFileName]
0x14001c4f5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14001c4fa  test    al, al
0x14001c4fc  jnz     short loc_14001C505
0x14001c4fe  mov     edx, 4A9h
0x14001c503  jmp     short loc_14001C52E
0x14001c505  lea     rax, aCryptcatsvcDll; "CryptCatSvc.dll"
0x14001c50c  mov     [rbp+var_50], rax
0x14001c510  mov     [rbp+var_48], 0Fh
0x14001c518  lea     rdx, [rbp+var_50]
0x14001c51c  lea     rcx, [rbp+lpLibFileName]; this
0x14001c520  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001c525  test    al, al
0x14001c527  jnz     short loc_14001C580
0x14001c529  mov     edx, 4AAh; void *
0x14001c52e  mov     r9d, 8007000Eh; char *
0x14001c534  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001c53b  mov     rcx, [rbp+8]; this
0x14001c53f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c544  lea     rax, [rbp+var_10]
0x14001c548  mov     rcx, [rbp+lpLibFileName]; void *
0x14001c54c  cmp     rcx, rax
0x14001c54f  jz      short loc_14001C55D
0x14001c551  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c558  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001c55d  lea     rax, [rbp+var_30]
0x14001c561  mov     rcx, [rbp+var_40]; void *
0x14001c565  cmp     rcx, rax
0x14001c568  jz      short loc_14001C576
0x14001c56a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c571  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001c576  mov     eax, 8007000Eh
0x14001c57b  jmp     loc_14001C6CB
0x14001c580  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x14001c584  call    cs:__imp_LoadLibraryW
0x14001c58b  nop     dword ptr [rax+rax+00h]
0x14001c590  mov     rbx, rax
0x14001c593  test    rax, rax
0x14001c596  jnz     short loc_14001C5E8
0x14001c598  mov     rcx, [rbp+8]; this
0x14001c59c  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001c5a3  mov     edx, 4ADh; void *
0x14001c5a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001c5ad  mov     ebx, eax
0x14001c5af  mov     rcx, [rbp+lpLibFileName]; void *
0x14001c5b3  lea     rax, [rbp+var_10]
0x14001c5b7  cmp     rcx, rax
0x14001c5ba  jz      short loc_14001C5C8
0x14001c5bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c5c3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001c5c8  mov     rcx, [rbp+var_40]; void *
0x14001c5cc  lea     rax, [rbp+var_30]
0x14001c5d0  cmp     rcx, rax
0x14001c5d3  jz      short loc_14001C5E1
0x14001c5d5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c5dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001c5e1  mov     eax, ebx
0x14001c5e3  jmp     loc_14001C6CB
0x14001c5e8  lea     rdx, aCatdbofflinere; "CatDbOfflineRebuildDatabasesW"
0x14001c5ef  mov     rcx, rbx; hModule
0x14001c5f2  call    cs:__imp_GetProcAddress
0x14001c5f9  nop     dword ptr [rax+rax+00h]
0x14001c5fe  test    rax, rax
0x14001c601  jnz     short loc_14001C65F
0x14001c603  mov     rcx, [rbp+8]; this
0x14001c607  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001c60e  mov     edx, 4B3h; void *
0x14001c613  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001c618  mov     edi, eax
0x14001c61a  mov     rcx, rbx; hLibModule
0x14001c61d  call    cs:__imp_FreeLibrary
0x14001c624  nop     dword ptr [rax+rax+00h]
0x14001c629  lea     rax, [rbp+var_10]
0x14001c62d  mov     rcx, [rbp+lpLibFileName]; void *
0x14001c631  cmp     rcx, rax
0x14001c634  jz      short loc_14001C642
0x14001c636  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c63d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001c642  mov     rcx, [rbp+var_40]; void *
0x14001c646  lea     rax, [rbp+var_30]
0x14001c64a  cmp     rcx, rax
0x14001c64d  jz      short loc_14001C65B
0x14001c64f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c656  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001c65b  mov     eax, edi
0x14001c65d  jmp     short loc_14001C6CB
0x14001c65f  xor     edx, edx
0x14001c661  mov     rcx, [rbp+var_40]
0x14001c665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c66a  test    eax, eax
0x14001c66c  jz      short loc_14001C688
0x14001c66e  mov     rcx, [rbp+8]; this
0x14001c672  mov     r9d, eax; char *
0x14001c675  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001c67c  mov     edx, 4B5h; void *
0x14001c681  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001c686  jmp     short loc_14001C618
0x14001c688  mov     rcx, rbx; hLibModule
0x14001c68b  call    cs:__imp_FreeLibrary
0x14001c692  nop     dword ptr [rax+rax+00h]
0x14001c697  mov     rcx, [rbp+lpLibFileName]; void *
0x14001c69b  lea     rax, [rbp+var_10]
0x14001c69f  cmp     rcx, rax
0x14001c6a2  jz      short loc_14001C6B0
0x14001c6a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c6ab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001c6b0  mov     rcx, [rbp+var_40]; void *
0x14001c6b4  lea     rax, [rbp+var_30]
0x14001c6b8  cmp     rcx, rax
0x14001c6bb  jz      short loc_14001C6C9
0x14001c6bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c6c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001c6c9  xor     eax, eax
0x14001c6cb  lea     r11, [rsp+70h+var_s0]
0x14001c6d0  mov     rbx, [r11+10h]
0x14001c6d4  mov     rdi, [r11+18h]
0x14001c6d8  mov     rsp, r11
0x14001c6db  pop     rbp
0x14001c6dc  retn
```

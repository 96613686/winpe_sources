# Element::OpenElement(ProvisioningPackage *,ushort const *,ushort const *)

- ea: `0x180016c50`
- end: `0x18001708c`
- name: `?OpenElement@Element@@QEAAJPEAVProvisioningPackage@@PEBG1@Z`
- size: `1084`
- prototype: `__int64 __fastcall(Element *this, struct ProvisioningPackage *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d350`
- `0x180014f8c`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180005360`
- `0x180005424`
- `0x180006014`
- `0x18000fc8c`
- `0x180016c50`

## string_xrefs

- `0x180016f3a`: `    Failed to copy element type string`
- `0x180016c8e`: `Element::OpenElement`
- `0x180016d26`: `Element::OpenElement`
- `0x180016d70`: `Element::OpenElement`
- `0x180016e0e`: `Element::OpenElement`
- `0x180016e5c`: `Element::OpenElement`
- `0x180016edd`: `Element::OpenElement`
- `0x180016f27`: `Element::OpenElement`
- `0x180016fbc`: `Element::OpenElement`
- `0x18001700a`: `Element::OpenElement`
- `0x18001705c`: `Element::OpenElement`
- `0x180016d83`: `    Failed to copy element index string`
- `0x180016e21`: `    Failed to allocate _spElementPath.get()`
- `0x180016e6f`: `    Failed to assemble element folder path`
- `0x18001701d`: `    Failed to assemble metadata file path (element type)`
- `0x18001706f`: `    Failed to assemble metadata file path (XML extension)`

## pseudocode

```c
__int64 __fastcall Element::OpenElement(
        Element *this,
        struct ProvisioningPackage *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int v7; // edi
  __int64 v9; // rax
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // kr00_8
  void *v13; // rax
  const struct std::nothrow_t *v14; // rdx
  void *v15; // rcx
  unsigned __int16 *v16; // rcx
  int v17; // eax
  unsigned int v18; // esi
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rax
  void *v23; // rax
  const struct std::nothrow_t *v24; // rdx
  void *v25; // rcx
  WCHAR *v26; // rcx
  HRESULT v27; // eax
  __int64 v28; // rax
  unsigned __int64 v29; // rsi
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // kr10_8
  void *v32; // rax
  const struct std::nothrow_t *v33; // rdx
  void *v34; // rcx
  unsigned __int16 *v35; // rcx
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // r8
  unsigned __int64 v39; // rsi
  unsigned __int64 v40; // rax
  void *v41; // rax
  const struct std::nothrow_t *v42; // rdx
  void *v43; // rcx
  WCHAR *v44; // rcx
  HRESULT v45; // eax
  int v46; // eax
  ULONG v47; // [rsp+20h] [rbp-48h]
  int v48; // [rsp+20h] [rbp-48h]
  int v49; // [rsp+20h] [rbp-48h]
  int v50; // [rsp+20h] [rbp-48h]
  int v51; // [rsp+20h] [rbp-48h]
  __int64 v52; // [rsp+20h] [rbp-48h]
  __int64 v53; // [rsp+20h] [rbp-48h]
  int v54; // [rsp+28h] [rbp-40h]
  int v55; // [rsp+28h] [rbp-40h]
  int v56; // [rsp+28h] [rbp-40h]
  int v57; // [rsp+28h] [rbp-40h]
  HRESULT v58; // [rsp+28h] [rbp-40h]
  int v59; // [rsp+28h] [rbp-40h]
  int v60; // [rsp+28h] [rbp-40h]
  int v61; // [rsp+28h] [rbp-40h]
  HRESULT v62; // [rsp+28h] [rbp-40h]
  int v63; // [rsp+28h] [rbp-40h]

  if ( !a2 )
  {
    v7 = -2147024809;
    v54 = -2147024809;
    v48 = 89;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::OpenElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v48,
      v54);
    ProvPackageLog(3, L"    pkg: Argument cannot be NULL");
    return v7;
  }
  *((_QWORD *)this + 1) = a2;
  v9 = -1;
  do
    ++v9;
  while ( a4[v9] );
  v10 = v9 + 1;
  v12 = v9 + 1;
  v11 = 2 * (v9 + 1);
  if ( !is_mul_ok(v12, 2u) )
    v11 = -1;
  v13 = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  v15 = (void *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = v13;
  if ( v15 )
    operator delete(v15, v14);
  v16 = (unsigned __int16 *)*((_QWORD *)this + 4);
  if ( !v16 )
  {
    v7 = -2147024882;
    v55 = -2147024882;
    v49 = 95;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::OpenElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v49,
      v55);
    ProvPackageLog(3, L"    Failed to allocate _spElementIndex.get()");
    return v7;
  }
  v17 = StringCchCopyW(v16, v10, a4);
  v18 = v17;
  if ( v17 < 0 )
  {
    v56 = v17;
    v50 = 98;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::OpenElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v50,
      v56);
    ProvPackageLog(3, L"    Failed to copy element index string");
    return v18;
  }
  v19 = -1;
  do
    ++v19;
  while ( a3[v19] );
  v20 = -1;
  do
    ++v20;
  while ( *(_WORD *)(*((_QWORD *)this + 4) + 2 * v20) );
  v21 = v20 + v19 + 6;
  v22 = 2 * v21;
  if ( !is_mul_ok(v21, 2u) )
    v22 = -1;
  v23 = operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
  v25 = (void *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v23;
  if ( v25 )
    operator delete(v25, v24);
  v26 = (WCHAR *)*((_QWORD *)this + 2);
  if ( !v26 )
  {
    v7 = -2147024882;
    v57 = -2147024882;
    v51 = 104;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::OpenElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v51,
      v57);
    ProvPackageLog(3, L"    Failed to allocate _spElementPath.get()");
    return v7;
  }
  v27 = PathCchCombineEx(v26, v21, a3, *((PCWSTR *)this + 4), v47);
  v18 = v27;
  if ( v27 < 0 )
  {
    v58 = v27;
    LODWORD(v52) = 108;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::OpenElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v52,
      v58);
    ProvPackageLog(3, L"    Failed to assemble element folder path");
    return v18;
  }
  v28 = -1;
  do
    ++v28;
  while ( a3[v28] );
  v29 = v28 + 1;
  v31 = v28 + 1;
  v30 = 2 * (v28 + 1);
  if ( !is_mul_ok(v31, 2u) )
    v30 = -1;
  v32 = operator new[](v30, (const struct std::nothrow_t *)&std::nothrow);
  v34 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v32;
  if ( v34 )
    operator delete(v34, v33);
  v35 = (unsigned __int16 *)*((_QWORD *)this + 3);
  if ( !v35 )
  {
    v7 = -2147024882;
    v59 = -2147024882;
    LODWORD(v52) = 113;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::OpenElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v52,
      v59);
    ProvPackageLog(3, L"    Failed to allocate _spElementType.get()");
    return v7;
  }
  v36 = StringCchCopyW(v35, v29, a3);
  v18 = v36;
  if ( v36 < 0 )
  {
    v60 = v36;
    LODWORD(v52) = 116;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::OpenElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v52,
      v60);
    ProvPackageLog(3, L"    Failed to copy element type string");
    return v18;
  }
  v37 = -1;
  do
    ++v37;
  while ( a3[v37] );
  v38 = -1;
  do
    ++v38;
  while ( *(_WORD *)(*((_QWORD *)this + 3) + 2 * v38) );
  v39 = v38 + v37 + 10;
  v40 = 2 * v39;
  if ( !is_mul_ok(v39, 2u) )
    v40 = -1;
  v41 = operator new[](v40, (const struct std::nothrow_t *)&std::nothrow);
  v43 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v41;
  if ( v43 )
    operator delete(v43, v42);
  v44 = (WCHAR *)*((_QWORD *)this + 5);
  if ( !v44 )
  {
    v7 = -2147024882;
    v61 = -2147024882;
    LODWORD(v52) = 123;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::OpenElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v52,
      v61);
    ProvPackageLog(3, L"    Failed to allocate _spMetadataFile.get()");
    return v7;
  }
  v45 = PathCchCombineEx(v44, v39, *((PCWSTR *)this + 3), a3, v52);
  v7 = v45;
  if ( v45 < 0 )
  {
    v62 = v45;
    LODWORD(v53) = 127;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::OpenElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v53,
      v62);
    ProvPackageLog(3, L"    Failed to assemble metadata file path (element type)");
    return v7;
  }
  v46 = StringCchCatW(*((unsigned __int16 **)this + 5), v39, L".xml");
  v7 = v46;
  if ( v46 < 0 )
  {
    v63 = v46;
    LODWORD(v53) = 130;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::OpenElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v53,
      v63);
    ProvPackageLog(3, L"    Failed to assemble metadata file path (XML extension)");
    return v7;
  }
  return 0;
}

```

## disassembly

```asm
0x180016c50  push    rbx
0x180016c52  push    rbp
0x180016c53  push    rsi
0x180016c54  push    rdi
0x180016c55  push    r12
0x180016c57  push    r14
0x180016c59  push    r15
0x180016c5b  sub     rsp, 30h
0x180016c5f  xor     r14d, r14d
0x180016c62  mov     rsi, r9
0x180016c65  mov     rdi, r8
0x180016c68  mov     rbx, rcx
0x180016c6b  test    rdx, rdx
0x180016c6e  jnz     short loc_180016CB6
0x180016c70  mov     edi, 80070057h
0x180016c75  lea     ebx, [r14+3]
0x180016c79  mov     [rsp+68h+var_40], edi
0x180016c7d  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016c84  mov     ecx, ebx
0x180016c86  mov     dword ptr [rsp+68h+var_48], 59h ; 'Y'
0x180016c8e  lea     r8, aElementOpenele; "Element::OpenElement"
0x180016c95  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016c9c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016ca1  lea     rdx, aPkgArgumentCan; "    pkg: Argument cannot be NULL"
0x180016ca8  mov     ecx, ebx
0x180016caa  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016caf  mov     eax, edi
0x180016cb1  jmp     loc_18001707D
0x180016cb6  or      r15, 0FFFFFFFFFFFFFFFFh
0x180016cba  mov     [rcx+8], rdx
0x180016cbe  mov     rax, r15
0x180016cc1  inc     rax
0x180016cc4  cmp     [r9+rax*2], r14w
0x180016cc9  jnz     short loc_180016CC1
0x180016ccb  lea     rbp, [rax+1]
0x180016ccf  mov     r12d, 2
0x180016cd5  mov     eax, r12d
0x180016cd8  mul     rbp
0x180016cdb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016ce2  cmovb   rax, r15
0x180016ce6  mov     rcx, rax; unsigned __int64
0x180016ce9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016cee  mov     rcx, [rbx+20h]; void *
0x180016cf2  mov     [rbx+20h], rax
0x180016cf6  test    rcx, rcx
0x180016cf9  jz      short loc_180016D00
0x180016cfb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016d00  mov     rcx, [rbx+20h]; unsigned __int16 *
0x180016d04  test    rcx, rcx
0x180016d07  jnz     short loc_180016D45
0x180016d09  lea     ebx, [rcx+3]
0x180016d0c  mov     edi, 8007000Eh
0x180016d11  mov     [rsp+68h+var_40], edi
0x180016d15  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016d1c  mov     ecx, ebx
0x180016d1e  mov     dword ptr [rsp+68h+var_48], 5Fh ; '_'
0x180016d26  lea     r8, aElementOpenele; "Element::OpenElement"
0x180016d2d  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016d34  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016d39  lea     rdx, aFailedToAlloca_30; "    Failed to allocate _spElementIndex."...
0x180016d40  jmp     loc_180016CA8
0x180016d45  mov     r8, rsi; unsigned __int16 *
0x180016d48  mov     rdx, rbp; unsigned __int64
0x180016d4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016d50  mov     esi, eax
0x180016d52  test    eax, eax
0x180016d54  jns     short loc_180016D98
0x180016d56  mov     [rsp+68h+var_40], eax
0x180016d5a  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016d61  mov     ebx, 3
0x180016d66  mov     dword ptr [rsp+68h+var_48], 62h ; 'b'
0x180016d6e  mov     ecx, ebx
0x180016d70  lea     r8, aElementOpenele; "Element::OpenElement"
0x180016d77  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016d7e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016d83  lea     rdx, aFailedToCopyEl_0; "    Failed to copy element index string"
0x180016d8a  mov     ecx, ebx
0x180016d8c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016d91  mov     eax, esi
0x180016d93  jmp     loc_18001707D
0x180016d98  mov     rax, r15
0x180016d9b  inc     rax
0x180016d9e  cmp     [rdi+rax*2], r14w
0x180016da3  jnz     short loc_180016D9B
0x180016da5  mov     rdx, [rbx+20h]
0x180016da9  mov     rcx, r15
0x180016dac  inc     rcx
0x180016daf  cmp     [rdx+rcx*2], r14w
0x180016db4  jnz     short loc_180016DAC
0x180016db6  lea     rsi, [rax+6]
0x180016dba  mov     rax, r12
0x180016dbd  add     rsi, rcx
0x180016dc0  mul     rsi
0x180016dc3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016dca  cmovb   rax, r15
0x180016dce  mov     rcx, rax; unsigned __int64
0x180016dd1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016dd6  mov     rcx, [rbx+10h]; void *
0x180016dda  mov     [rbx+10h], rax
0x180016dde  test    rcx, rcx
0x180016de1  jz      short loc_180016DE8
0x180016de3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016de8  mov     rcx, [rbx+10h]; pszPathOut
0x180016dec  test    rcx, rcx
0x180016def  jnz     short loc_180016E2D
0x180016df1  lea     ebx, [rcx+3]
0x180016df4  mov     edi, 8007000Eh
0x180016df9  mov     [rsp+68h+var_40], edi
0x180016dfd  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016e04  mov     ecx, ebx
0x180016e06  mov     dword ptr [rsp+68h+var_48], 68h ; 'h'
0x180016e0e  lea     r8, aElementOpenele; "Element::OpenElement"
0x180016e15  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016e1c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016e21  lea     rdx, aFailedToAlloca_37; "    Failed to allocate _spElementPath.g"...
0x180016e28  jmp     loc_180016CA8
0x180016e2d  mov     r9, [rbx+20h]; pszMore
0x180016e31  mov     r8, rdi; pszPathIn
0x180016e34  mov     rdx, rsi; cchPathOut
0x180016e37  call    PathCchCombineEx
0x180016e3c  mov     esi, eax
0x180016e3e  test    eax, eax
0x180016e40  jns     short loc_180016E7B
0x180016e42  mov     [rsp+68h+var_40], eax
0x180016e46  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016e4d  mov     ebx, 3
0x180016e52  mov     dword ptr [rsp+68h+var_48], 6Ch ; 'l'
0x180016e5a  mov     ecx, ebx
0x180016e5c  lea     r8, aElementOpenele; "Element::OpenElement"
0x180016e63  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016e6a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016e6f  lea     rdx, aFailedToAssemb_3; "    Failed to assemble element folder p"...
0x180016e76  jmp     loc_180016D8A
0x180016e7b  mov     rax, r15
0x180016e7e  inc     rax
0x180016e81  cmp     [rdi+rax*2], r14w
0x180016e86  jnz     short loc_180016E7E
0x180016e88  lea     rsi, [rax+1]
0x180016e8c  mov     rax, r12
0x180016e8f  mul     rsi
0x180016e92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016e99  cmovb   rax, r15
0x180016e9d  mov     rcx, rax; unsigned __int64
0x180016ea0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016ea5  mov     rcx, [rbx+18h]; void *
0x180016ea9  mov     [rbx+18h], rax
0x180016ead  test    rcx, rcx
0x180016eb0  jz      short loc_180016EB7
0x180016eb2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016eb7  mov     rcx, [rbx+18h]; unsigned __int16 *
0x180016ebb  test    rcx, rcx
0x180016ebe  jnz     short loc_180016EFC
0x180016ec0  lea     ebx, [rcx+3]
0x180016ec3  mov     edi, 8007000Eh
0x180016ec8  mov     [rsp+68h+var_40], edi
0x180016ecc  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016ed3  mov     ecx, ebx
0x180016ed5  mov     dword ptr [rsp+68h+var_48], 71h ; 'q'
0x180016edd  lea     r8, aElementOpenele; "Element::OpenElement"
0x180016ee4  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016eeb  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016ef0  lea     rdx, aFailedToAlloca_41; "    Failed to allocate _spElementType.g"...
0x180016ef7  jmp     loc_180016CA8
0x180016efc  mov     r8, rdi; unsigned __int16 *
0x180016eff  mov     rdx, rsi; unsigned __int64
0x180016f02  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016f07  mov     esi, eax
0x180016f09  test    eax, eax
0x180016f0b  jns     short loc_180016F46
0x180016f0d  mov     [rsp+68h+var_40], eax
0x180016f11  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016f18  mov     ebx, 3
0x180016f1d  mov     dword ptr [rsp+68h+var_48], 74h ; 't'
0x180016f25  mov     ecx, ebx
0x180016f27  lea     r8, aElementOpenele; "Element::OpenElement"
0x180016f2e  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016f35  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016f3a  lea     rdx, aFailedToCopyEl; "    Failed to copy element type string"
0x180016f41  jmp     loc_180016D8A
0x180016f46  mov     rcx, r15
0x180016f49  inc     rcx
0x180016f4c  cmp     [rdi+rcx*2], r14w
0x180016f51  jnz     short loc_180016F49
0x180016f53  mov     r9, [rbx+18h]
0x180016f57  mov     r8, r15
0x180016f5a  inc     r8
0x180016f5d  cmp     [r9+r8*2], r14w
0x180016f62  jnz     short loc_180016F5A
0x180016f64  lea     rsi, [rcx+0Ah]
0x180016f68  mov     rax, r12
0x180016f6b  add     rsi, r8
0x180016f6e  mul     rsi
0x180016f71  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016f78  cmovb   rax, r15
0x180016f7c  mov     rcx, rax; unsigned __int64
0x180016f7f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016f84  mov     rcx, [rbx+28h]; void *
0x180016f88  mov     [rbx+28h], rax
0x180016f8c  test    rcx, rcx
0x180016f8f  jz      short loc_180016F96
0x180016f91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016f96  mov     rcx, [rbx+28h]; pszPathOut
0x180016f9a  test    rcx, rcx
0x180016f9d  jnz     short loc_180016FDB
0x180016f9f  lea     ebx, [rcx+3]
0x180016fa2  mov     edi, 8007000Eh
0x180016fa7  mov     [rsp+68h+var_40], edi
0x180016fab  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016fb2  mov     ecx, ebx
0x180016fb4  mov     dword ptr [rsp+68h+var_48], 7Bh ; '{'
0x180016fbc  lea     r8, aElementOpenele; "Element::OpenElement"
0x180016fc3  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016fca  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016fcf  lea     rdx, aFailedToAlloca_20; "    Failed to allocate _spMetadataFile."...
0x180016fd6  jmp     loc_180016CA8
0x180016fdb  mov     r8, [rbx+18h]; pszPathIn
0x180016fdf  mov     r9, rdi; pszMore
0x180016fe2  mov     rdx, rsi; cchPathOut
0x180016fe5  call    PathCchCombineEx
0x180016fea  mov     edi, eax
0x180016fec  test    eax, eax
0x180016fee  jns     short loc_180017029
0x180016ff0  mov     [rsp+68h+var_40], eax
0x180016ff4  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016ffb  mov     ebx, 3
0x180017000  mov     dword ptr [rsp+68h+var_48], 7Fh
0x180017008  mov     ecx, ebx
0x18001700a  lea     r8, aElementOpenele; "Element::OpenElement"
0x180017011  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017018  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001701d  lea     rdx, aFailedToAssemb_13; "    Failed to assemble metadata file pa"...
0x180017024  jmp     loc_180016CA8
0x180017029  mov     rcx, [rbx+28h]; unsigned __int16 *
0x18001702d  lea     r8, aXml; ".xml"
0x180017034  mov     rdx, rsi; unsigned __int64
0x180017037  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001703c  mov     edi, eax
0x18001703e  test    eax, eax
0x180017040  jns     short loc_18001707B
0x180017042  mov     [rsp+68h+var_40], eax
0x180017046  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001704d  mov     ebx, 3
0x180017052  mov     dword ptr [rsp+68h+var_48], 82h
0x18001705a  mov     ecx, ebx
0x18001705c  lea     r8, aElementOpenele; "Element::OpenElement"
0x180017063  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001706a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001706f  lea     rdx, aFailedToAssemb_0; "    Failed to assemble metadata file pa"...
0x180017076  jmp     loc_180016CA8
0x18001707b  xor     eax, eax
0x18001707d  add     rsp, 30h
0x180017081  pop     r15
0x180017083  pop     r14
0x180017085  pop     r12
0x180017087  pop     rdi
0x180017088  pop     rsi
0x180017089  pop     rbp
0x18001708a  pop     rbx
0x18001708b  retn
```

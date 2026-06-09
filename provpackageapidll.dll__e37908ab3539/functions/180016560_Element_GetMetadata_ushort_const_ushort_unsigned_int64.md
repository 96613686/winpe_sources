# Element::GetMetadata(ushort const *,ushort *,unsigned __int64)

- ea: `0x180016560`
- end: `0x1800166ef`
- name: `?GetMetadata@Element@@EEAAJPEBGPEAG_K@Z`
- size: `399`
- prototype: `__int64 __fastcall(Element *this, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callees

- `0x1800020a8`
- `0x180006014`
- `0x18000e060`
- `0x18000e4b0`
- `0x180011e38`
- `0x180016560`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016660`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800166c3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016660`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800166c3`

## string_xrefs

- `0x1800165c7`: `    Failed to get metadata temporary file`

## pseudocode

```c
__int64 __fastcall Element::GetMetadata(
        Element *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  int TemporaryFile; // eax
  unsigned int v9; // edi
  const struct std::nothrow_t *v10; // rdx
  WCHAR *v11; // rcx
  int File; // eax
  int ElementMetadata; // eax
  const struct std::nothrow_t *v15; // rdx
  WCHAR *v16; // rcx
  int v17; // [rsp+20h] [rbp-38h]
  int v18; // [rsp+20h] [rbp-38h]
  unsigned __int64 v19; // [rsp+20h] [rbp-38h]
  int v20; // [rsp+28h] [rbp-30h]
  int v21; // [rsp+28h] [rbp-30h]
  int v22; // [rsp+28h] [rbp-30h]
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-28h] BYREF
  char v24; // [rsp+40h] [rbp-18h]

  lpFileName[0] = 0;
  TemporaryFile = GetTemporaryFile((__int64)L"tem", lpFileName);
  v9 = TemporaryFile;
  if ( TemporaryFile < 0 )
  {
    v20 = TemporaryFile;
    v17 = 261;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::GetMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v17,
      v20);
    ProvPackageLog(3, L"    Failed to get metadata temporary file");
LABEL_3:
    v11 = (WCHAR *)lpFileName[0];
    lpFileName[0] = 0;
    if ( v11 )
      operator delete(v11, v10);
    return v9;
  }
  lpFileName[1] = (LPCWSTR)lpFileName;
  v24 = 1;
  File = ExtractFile(*(void **)(*((_QWORD *)this + 1) + 16LL), *((const unsigned __int16 **)this + 5), lpFileName[0], 1);
  v9 = File;
  if ( File < 0 )
  {
    v21 = File;
    v18 = 271;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::GetMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v18,
      v21);
    ProvPackageLog(3, L"    Failed to retrieve metadata file");
LABEL_8:
    DeleteFileW(lpFileName[0]);
    goto LABEL_3;
  }
  ElementMetadata = GetElementMetadata(lpFileName[0], *((const unsigned __int16 **)this + 4), a2, a3, a4);
  v9 = ElementMetadata;
  if ( ElementMetadata < 0 )
  {
    v22 = ElementMetadata;
    LODWORD(v19) = 275;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::GetMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v19,
      v22);
    ProvPackageLog(3, L"    Failed to get element metadata");
    goto LABEL_8;
  }
  DeleteFileW(lpFileName[0]);
  v16 = (WCHAR *)lpFileName[0];
  lpFileName[0] = 0;
  if ( v16 )
    operator delete(v16, v15);
  return 0;
}

```

## disassembly

```asm
0x180016560  push    rbp
0x180016562  push    rbx
0x180016563  push    rsi
0x180016564  push    rdi
0x180016565  push    r14
0x180016567  push    r15
0x180016569  mov     rbp, rsp
0x18001656c  sub     rsp, 58h
0x180016570  mov     rsi, r9
0x180016573  mov     r14, r8
0x180016576  mov     r15, rdx
0x180016579  mov     rbx, rcx
0x18001657c  mov     [rbp+lpFileName], 0
0x180016584  lea     rdx, [rbp+lpFileName]
0x180016588  lea     rcx, aTem; "tem"
0x18001658f  call    ?GetTemporaryFile@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFile(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x180016594  mov     edi, eax
0x180016596  test    eax, eax
0x180016598  jns     short loc_1800165F3
0x18001659a  mov     [rsp+58h+var_30], eax
0x18001659e  mov     dword ptr [rsp+58h+var_38], 105h
0x1800165a6  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800165ad  lea     r8, aElementGetmeta; "Element::GetMetadata"
0x1800165b4  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800165bb  mov     ebx, 3
0x1800165c0  mov     ecx, ebx
0x1800165c2  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800165c7  lea     rdx, aFailedToGetMet_2; "    Failed to get metadata temporary fi"...
0x1800165ce  mov     ecx, ebx
0x1800165d0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800165d5  nop
0x1800165d6  mov     rcx, [rbp+lpFileName]; void *
0x1800165da  mov     [rbp+lpFileName], 0
0x1800165e2  test    rcx, rcx
0x1800165e5  jz      short loc_1800165EC
0x1800165e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800165ec  mov     eax, edi
0x1800165ee  jmp     loc_1800166E2
0x1800165f3  lea     rax, [rbp+lpFileName]
0x1800165f7  mov     [rbp+var_20], rax
0x1800165fb  mov     [rbp+var_18], 1
0x1800165ff  mov     rcx, [rbx+8]
0x180016603  mov     r9d, 1; int
0x180016609  mov     r8, [rbp+lpFileName]; unsigned __int16 *
0x18001660d  mov     rdx, [rbx+28h]; unsigned __int16 *
0x180016611  mov     rcx, [rcx+10h]; void *
0x180016615  call    ?ExtractFile@@YAJPEAXPEBG1H@Z; ExtractFile(void *,ushort const *,ushort const *,int)
0x18001661a  mov     edi, eax
0x18001661c  test    eax, eax
0x18001661e  jns     short loc_18001666B
0x180016620  mov     [rsp+58h+var_30], eax
0x180016624  mov     dword ptr [rsp+58h+var_38], 10Fh
0x18001662c  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016633  lea     r8, aElementGetmeta; "Element::GetMetadata"
0x18001663a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016641  mov     ebx, 3
0x180016646  mov     ecx, ebx
0x180016648  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001664d  lea     rdx, aFailedToRetrie; "    Failed to retrieve metadata file"
0x180016654  mov     ecx, ebx
0x180016656  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001665b  nop
0x18001665c  mov     rcx, [rbp+lpFileName]; lpFileName
0x180016660  call    cs:__imp_DeleteFileW
0x180016666  jmp     loc_1800165D6
0x18001666b  mov     [rsp+58h+var_38], rsi; unsigned __int64
0x180016670  mov     r9, r14; unsigned __int16 *
0x180016673  mov     r8, r15; unsigned __int16 *
0x180016676  mov     rdx, [rbx+20h]; unsigned __int16 *
0x18001667a  mov     rcx, [rbp+lpFileName]; unsigned __int16 *
0x18001667e  call    ?GetElementMetadata@@YAJPEBG00PEAG_K@Z; GetElementMetadata(ushort const *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x180016683  mov     edi, eax
0x180016685  test    eax, eax
0x180016687  jns     short loc_1800166BF
0x180016689  mov     [rsp+58h+var_30], eax
0x18001668d  mov     dword ptr [rsp+58h+var_38], 113h
0x180016695  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001669c  lea     r8, aElementGetmeta; "Element::GetMetadata"
0x1800166a3  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800166aa  mov     ebx, 3
0x1800166af  mov     ecx, ebx
0x1800166b1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800166b6  lea     rdx, aFailedToGetEle_1; "    Failed to get element metadata"
0x1800166bd  jmp     short loc_180016654
0x1800166bf  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800166c3  call    cs:__imp_DeleteFileW
0x1800166c9  nop
0x1800166ca  mov     rcx, [rbp+lpFileName]; void *
0x1800166ce  mov     [rbp+lpFileName], 0
0x1800166d6  test    rcx, rcx
0x1800166d9  jz      short loc_1800166E0
0x1800166db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800166e0  xor     eax, eax
0x1800166e2  add     rsp, 58h
0x1800166e6  pop     r15
0x1800166e8  pop     r14
0x1800166ea  pop     rdi
0x1800166eb  pop     rsi
0x1800166ec  pop     rbx
0x1800166ed  pop     rbp
0x1800166ee  retn
```

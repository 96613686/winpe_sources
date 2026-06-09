# ProvisioningPackage::CreateProvisioningPackage(PackageBuilder const &)

- ea: `0x1800068b8`
- end: `0x180006d43`
- name: `?CreateProvisioningPackage@ProvisioningPackage@@QEAAJAEBVPackageBuilder@@@Z`
- size: `1163`
- prototype: `__int64 __fastcall(ProvisioningPackage *__hidden this, const struct PackageBuilder *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x180009740`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x1800068b8`
- `0x180007f78`
- `0x18000907c`
- `0x18000e4b0`
- `0x18000e7b0`
- `0x18000f040`
- `0x180013c18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b79`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006d08`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006d08`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180006ba1`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180006ba1`
- `WIMGAPI!WIMCaptureImage` at `0x180006af1`
- `WIMGAPI!WIMCaptureImage` at `0x180006af1`
- `WIMGAPI!WIMCloseHandle` at `0x180006b13`
- `WIMGAPI!WIMCloseHandle` at `0x180006b13`

## string_xrefs

- `0x1800068f7`: `ProvisioningPackage::CreateProvisioningPackage`
- `0x180006989`: `ProvisioningPackage::CreateProvisioningPackage`
- `0x1800069da`: `ProvisioningPackage::CreateProvisioningPackage`
- `0x180006a49`: `ProvisioningPackage::CreateProvisioningPackage`
- `0x180006a9e`: `ProvisioningPackage::CreateProvisioningPackage`
- `0x180006b51`: `ProvisioningPackage::CreateProvisioningPackage`
- `0x180006bd6`: `ProvisioningPackage::CreateProvisioningPackage`
- `0x180006c4d`: `ProvisioningPackage::CreateProvisioningPackage`
- `0x180006cbd`: `ProvisioningPackage::CreateProvisioningPackage`
- `0x18000690f`: `    Package path missing`
- `0x1800069a1`: `    Failed to allocate _spPackagePath.get()`
- `0x1800069f4`: `    Failed to copy package path string`
- `0x180006ab8`: `    Failed to get temporary folder`
- `0x180006bf0`: `    Failed to get temporary file`
- `0x180006c67`: `    Failed to write package metadata`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::CreateProvisioningPackage(
        ProvisioningPackage *this,
        const struct PackageBuilder *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // edi
  __int64 v7; // rax
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // kr00_8
  void *v11; // rax
  const struct std::nothrow_t *v12; // rdx
  void *v13; // rcx
  unsigned __int16 *v14; // rcx
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // ecx
  int v18; // ecx
  int WimHandle; // eax
  signed int TemporaryFolder; // eax
  const struct std::nothrow_t *v21; // rdx
  WCHAR *v22; // rdi
  __int64 v23; // rsi
  __int64 v24; // r15
  DWORD LastError; // ebx
  signed int v26; // eax
  signed int v27; // eax
  const struct std::nothrow_t *v28; // rdx
  unsigned int v29; // ebx
  int TemporaryFile; // eax
  unsigned int v31; // esi
  const struct std::nothrow_t *v32; // rdx
  unsigned __int16 *v33; // rsi
  int v34; // eax
  unsigned int v35; // r14d
  const struct std::nothrow_t *v36; // rdx
  int v37; // eax
  unsigned int v38; // ebp
  const struct std::nothrow_t *v39; // rdx
  const struct std::nothrow_t *v40; // rdx
  __int64 v41; // [rsp+20h] [rbp-38h]
  LPCWSTR lpPathName; // [rsp+68h] [rbp+10h] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp+18h] BYREF

  v4 = *((_QWORD *)a2 + 1);
  if ( !v4 )
  {
    v5 = -2147024893;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::CreateProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      20,
      -2147024893);
    ProvPackageLog(3, L"    Package path missing");
    return v5;
  }
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v4 + 2 * v7) );
  v8 = v7 + 1;
  v10 = v7 + 1;
  v9 = 2 * (v7 + 1);
  if ( !is_mul_ok(v10, 2u) )
    v9 = -1;
  v11 = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v13 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v11;
  if ( v13 )
    operator delete(v13, v12);
  v14 = (unsigned __int16 *)*((_QWORD *)this + 3);
  if ( !v14 )
  {
    v5 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::CreateProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      26,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate _spPackagePath.get()");
    return v5;
  }
  v15 = 1;
  v16 = PathCchCanonicalizeEx(v14, v8, *((const unsigned __int16 **)a2 + 1), PATHCCH_ALLOW_LONG_PATHS);
  v5 = v16;
  if ( v16 < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::CreateProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      30,
      v16);
    ProvPackageLog(3, L"    Failed to copy package path string");
    return v5;
  }
  v17 = *((_DWORD *)a2 + 20);
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( v18 )
      v15 = v18 != 1;
    else
      v15 = 2;
  }
  WimHandle = ProvisioningPackage::GetWimHandle(this, *((const unsigned __int16 **)this + 3), 0xC0000000, 2u, v15);
  v5 = WimHandle;
  if ( WimHandle < 0 )
  {
    LODWORD(v41) = 35;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::CreateProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v41,
      WimHandle);
    ProvPackageLog(3, L"    Failed to get wim handle");
    return v5;
  }
  lpPathName = 0;
  TemporaryFolder = GetTemporaryFolder((__int64)L"tem", &lpPathName);
  v5 = TemporaryFolder;
  if ( TemporaryFolder < 0 )
  {
    LODWORD(v41) = 40;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::CreateProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v41,
      TemporaryFolder);
    ProvPackageLog(3, L"    Failed to get temporary folder");
    if ( lpPathName )
      operator delete((void *)lpPathName, v21);
    return v5;
  }
  v22 = (WCHAR *)lpPathName;
  v23 = WIMCaptureImage(*((_QWORD *)this + 1), lpPathName, 131074);
  v24 = *((_QWORD *)this + 2);
  if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    WIMCloseHandle(v24);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = v23;
  if ( v23 )
  {
    RemoveDirectoryW(v22);
    lpFileName = 0;
    TemporaryFile = GetTemporaryFile((__int64)L"tpm", &lpFileName);
    v31 = TemporaryFile;
    if ( TemporaryFile >= 0 )
    {
      v33 = (unsigned __int16 *)lpFileName;
      v34 = WritePackageMetadata(a2, lpFileName);
      v35 = v34;
      if ( v34 >= 0 )
      {
        v37 = ProvisioningPackage::SavePackageMetadata(this, v33);
        v38 = v37;
        if ( v37 >= 0 )
        {
          DeleteFileW(v33);
          if ( v33 )
            operator delete(v33, v40);
          if ( v22 )
            operator delete(v22, v40);
          return 0;
        }
        else
        {
          LODWORD(v41) = 58;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "ProvisioningPackage::CreateProvisioningPackage",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
            v41,
            v37);
          ProvPackageLog(3, L"    Failed to save package metadata");
          if ( v33 )
            operator delete(v33, v39);
          if ( v22 )
            operator delete(v22, v39);
          return v38;
        }
      }
      else
      {
        LODWORD(v41) = 54;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "ProvisioningPackage::CreateProvisioningPackage",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
          v41,
          v34);
        ProvPackageLog(3, L"    Failed to write package metadata");
        if ( v33 )
          operator delete(v33, v36);
        if ( v22 )
          operator delete(v22, v36);
        return v35;
      }
    }
    else
    {
      LODWORD(v41) = 51;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::CreateProvisioningPackage",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        v41,
        TemporaryFile);
      ProvPackageLog(3, L"    Failed to get temporary file");
      if ( lpFileName )
        operator delete((void *)lpFileName, v32);
      if ( v22 )
        operator delete(v22, v32);
      return v31;
    }
  }
  else
  {
    v26 = GetLastError();
    if ( v26 > 0 )
      v26 = (unsigned __int16)v26 | 0x80070000;
    LODWORD(v41) = 43;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::CreateProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v41,
      v26);
    ProvPackageLog(3, L"    Failed to capture image");
    v27 = GetLastError();
    v29 = v27;
    if ( v27 > 0 )
      v29 = (unsigned __int16)v27 | 0x80070000;
    if ( v22 )
      operator delete(v22, v28);
    return v29;
  }
}

```

## disassembly

```asm
0x1800068b8  mov     rax, rsp
0x1800068bb  mov     [rax+8], rbx
0x1800068bf  mov     [rax+20h], rbp
0x1800068c3  push    rsi
0x1800068c4  push    rdi
0x1800068c5  push    r12
0x1800068c7  push    r14
0x1800068c9  push    r15
0x1800068cb  sub     rsp, 30h
0x1800068cf  mov     r14, rdx
0x1800068d2  mov     rbp, rcx
0x1800068d5  mov     rcx, [rdx+8]
0x1800068d9  xor     r12d, r12d
0x1800068dc  test    rcx, rcx
0x1800068df  jnz     short loc_180006924
0x1800068e1  mov     edi, 80070003h
0x1800068e6  mov     [rax-30h], edi
0x1800068e9  mov     dword ptr [rax-38h], 14h
0x1800068f0  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800068f7  lea     r8, aProvisioningpa_2; "ProvisioningPackage::CreateProvisioning"...
0x1800068fe  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006905  lea     ebx, [rcx+3]
0x180006908  mov     ecx, ebx
0x18000690a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000690f  lea     rdx, aPackagePathMis; "    Package path missing"
0x180006916  mov     ecx, ebx
0x180006918  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000691d  mov     eax, edi
0x18000691f  jmp     loc_180006D2C
0x180006924  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006928  mov     rax, r8
0x18000692b  inc     rax
0x18000692e  cmp     [rcx+rax*2], r12w
0x180006933  jnz     short loc_18000692B
0x180006935  lea     rdi, [rax+1]
0x180006939  mov     esi, 2
0x18000693e  mov     eax, esi
0x180006940  mul     rdi
0x180006943  cmovb   rax, r8
0x180006947  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000694e  mov     rcx, rax; unsigned __int64
0x180006951  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006956  mov     rcx, [rbp+18h]; void *
0x18000695a  mov     [rbp+18h], rax
0x18000695e  test    rcx, rcx
0x180006961  jz      short loc_180006968
0x180006963  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006968  mov     rcx, [rbp+18h]; unsigned __int16 *
0x18000696c  test    rcx, rcx
0x18000696f  jnz     short loc_1800069AD
0x180006971  mov     edi, 8007000Eh
0x180006976  mov     [rsp+58h+var_30], edi
0x18000697a  mov     dword ptr [rsp+58h+var_38], 1Ah
0x180006982  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006989  lea     r8, aProvisioningpa_2; "ProvisioningPackage::CreateProvisioning"...
0x180006990  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006997  lea     ebx, [rcx+3]
0x18000699a  mov     ecx, ebx
0x18000699c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800069a1  lea     rdx, aFailedToAlloca_11; "    Failed to allocate _spPackagePath.g"...
0x1800069a8  jmp     loc_180006916
0x1800069ad  mov     ebx, 1
0x1800069b2  mov     r9d, ebx; enum PATHCCH_OPTIONS
0x1800069b5  mov     r8, [r14+8]; unsigned __int16 *
0x1800069b9  mov     rdx, rdi; unsigned __int64
0x1800069bc  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x1800069c1  mov     edi, eax
0x1800069c3  test    eax, eax
0x1800069c5  jns     short loc_180006A00
0x1800069c7  mov     [rsp+58h+var_30], eax
0x1800069cb  mov     dword ptr [rsp+58h+var_38], 1Eh
0x1800069d3  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800069da  lea     r8, aProvisioningpa_2; "ProvisioningPackage::CreateProvisioning"...
0x1800069e1  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800069e8  mov     ebx, 3
0x1800069ed  mov     ecx, ebx
0x1800069ef  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800069f4  lea     rdx, aFailedToCopyPa_0; "    Failed to copy package path string"
0x1800069fb  jmp     loc_180006916
0x180006a00  mov     ecx, [r14+50h]
0x180006a04  test    ecx, ecx
0x180006a06  jz      short loc_180006A17
0x180006a08  sub     ecx, ebx
0x180006a0a  jz      short loc_180006A15
0x180006a0c  cmp     ecx, ebx
0x180006a0e  jnz     short loc_180006A17
0x180006a10  mov     ebx, r12d
0x180006a13  jmp     short loc_180006A17
0x180006a15  mov     ebx, esi
0x180006a17  mov     dword ptr [rsp+58h+var_38], ebx; unsigned int
0x180006a1b  mov     r9d, esi; unsigned int
0x180006a1e  mov     r8d, 0C0000000h; unsigned int
0x180006a24  mov     rdx, [rbp+18h]; unsigned __int16 *
0x180006a28  mov     rcx, rbp; this
0x180006a2b  call    ?GetWimHandle@ProvisioningPackage@@AEAAJPEBGKKI@Z; ProvisioningPackage::GetWimHandle(ushort const *,ulong,ulong,uint)
0x180006a30  mov     edi, eax
0x180006a32  test    eax, eax
0x180006a34  jns     short loc_180006A6F
0x180006a36  mov     [rsp+58h+var_30], eax
0x180006a3a  mov     dword ptr [rsp+58h+var_38], 23h ; '#'
0x180006a42  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006a49  lea     r8, aProvisioningpa_2; "ProvisioningPackage::CreateProvisioning"...
0x180006a50  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006a57  mov     ebx, 3
0x180006a5c  mov     ecx, ebx
0x180006a5e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006a63  lea     rdx, aFailedToGetWim_0; "    Failed to get wim handle"
0x180006a6a  jmp     loc_180006916
0x180006a6f  mov     [rsp+58h+lpPathName], r12
0x180006a74  lea     rdx, [rsp+58h+lpPathName]
0x180006a79  lea     rcx, aTem; "tem"
0x180006a80  call    ?GetTemporaryFolder@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFolder(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x180006a85  mov     edi, eax
0x180006a87  test    eax, eax
0x180006a89  jns     short loc_180006ADF
0x180006a8b  mov     [rsp+58h+var_30], eax
0x180006a8f  mov     dword ptr [rsp+58h+var_38], 28h ; '('
0x180006a97  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006a9e  lea     r8, aProvisioningpa_2; "ProvisioningPackage::CreateProvisioning"...
0x180006aa5  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006aac  mov     ebx, 3
0x180006ab1  mov     ecx, ebx
0x180006ab3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006ab8  lea     rdx, aFailedToGetTem; "    Failed to get temporary folder"
0x180006abf  mov     ecx, ebx
0x180006ac1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006ac6  nop
0x180006ac7  mov     rcx, [rsp+58h+lpPathName]; void *
0x180006acc  test    rcx, rcx
0x180006acf  jz      loc_18000691D
0x180006ad5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006ada  jmp     loc_18000691D
0x180006adf  mov     r8d, 20002h
0x180006ae5  mov     rdi, [rsp+58h+lpPathName]
0x180006aea  mov     rdx, rdi
0x180006aed  mov     rcx, [rbp+8]
0x180006af1  call    cs:__imp_WIMCaptureImage
0x180006af7  mov     rsi, rax
0x180006afa  mov     r15, [rbp+10h]
0x180006afe  lea     rdx, [r15-1]
0x180006b02  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180006b06  ja      short loc_180006B21
0x180006b08  call    cs:__imp_GetLastError
0x180006b0e  mov     ebx, eax
0x180006b10  mov     rcx, r15
0x180006b13  call    cs:__imp_WIMCloseHandle
0x180006b19  mov     ecx, ebx; dwErrCode
0x180006b1b  call    cs:__imp_SetLastError
0x180006b21  mov     [rbp+10h], rsi
0x180006b25  test    rsi, rsi
0x180006b28  jnz     short loc_180006B9E
0x180006b2a  call    cs:__imp_GetLastError
0x180006b30  mov     esi, 80070000h
0x180006b35  test    eax, eax
0x180006b37  jle     short loc_180006B3E
0x180006b39  movzx   eax, ax
0x180006b3c  or      eax, esi
0x180006b3e  mov     [rsp+58h+var_30], eax
0x180006b42  mov     dword ptr [rsp+58h+var_38], 2Bh ; '+'
0x180006b4a  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006b51  lea     r8, aProvisioningpa_2; "ProvisioningPackage::CreateProvisioning"...
0x180006b58  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006b5f  mov     ebx, 3
0x180006b64  mov     ecx, ebx
0x180006b66  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006b6b  lea     rdx, aFailedToCaptur; "    Failed to capture image"
0x180006b72  mov     ecx, ebx
0x180006b74  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006b79  call    cs:__imp_GetLastError
0x180006b7f  mov     ebx, eax
0x180006b81  test    eax, eax
0x180006b83  jle     short loc_180006B8A
0x180006b85  movzx   ebx, ax
0x180006b88  or      ebx, esi
0x180006b8a  test    rdi, rdi
0x180006b8d  jz      short loc_180006B97
0x180006b8f  mov     rcx, rdi; void *
0x180006b92  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006b97  mov     eax, ebx
0x180006b99  jmp     loc_180006D2C
0x180006b9e  mov     rcx, rdi; lpPathName
0x180006ba1  call    cs:__imp_RemoveDirectoryW
0x180006ba7  mov     [rsp+58h+lpFileName], r12
0x180006bac  lea     rdx, [rsp+58h+lpFileName]
0x180006bb1  lea     rcx, aTpm; "tpm"
0x180006bb8  call    ?GetTemporaryFile@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFile(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x180006bbd  mov     esi, eax
0x180006bbf  test    eax, eax
0x180006bc1  jns     short loc_180006C23
0x180006bc3  mov     [rsp+58h+var_30], eax
0x180006bc7  mov     dword ptr [rsp+58h+var_38], 33h ; '3'
0x180006bcf  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006bd6  lea     r8, aProvisioningpa_2; "ProvisioningPackage::CreateProvisioning"...
0x180006bdd  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006be4  mov     ebx, 3
0x180006be9  mov     ecx, ebx
0x180006beb  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006bf0  lea     rdx, aFailedToGetTem_0; "    Failed to get temporary file"
0x180006bf7  mov     ecx, ebx
0x180006bf9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006bfe  nop
0x180006bff  mov     rcx, [rsp+58h+lpFileName]; void *
0x180006c04  test    rcx, rcx
0x180006c07  jz      short loc_180006C0F
0x180006c09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006c0e  nop
0x180006c0f  test    rdi, rdi
0x180006c12  jz      short loc_180006C1C
0x180006c14  mov     rcx, rdi; void *
0x180006c17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006c1c  mov     eax, esi
0x180006c1e  jmp     loc_180006D2C
0x180006c23  mov     rsi, [rsp+58h+lpFileName]
0x180006c28  mov     rdx, rsi; unsigned __int16 *
0x180006c2b  mov     rcx, r14; struct PackageBuilder *
0x180006c2e  call    ?WritePackageMetadata@@YAJAEBVPackageBuilder@@PEBG@Z; WritePackageMetadata(PackageBuilder const &,ushort const *)
0x180006c33  mov     r14d, eax
0x180006c36  test    eax, eax
0x180006c38  jns     short loc_180006C99
0x180006c3a  mov     [rsp+58h+var_30], eax
0x180006c3e  mov     dword ptr [rsp+58h+var_38], 36h ; '6'
0x180006c46  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006c4d  lea     r8, aProvisioningpa_2; "ProvisioningPackage::CreateProvisioning"...
0x180006c54  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006c5b  mov     ebx, 3
0x180006c60  mov     ecx, ebx
0x180006c62  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006c67  lea     rdx, aFailedToWriteP_1; "    Failed to write package metadata"
0x180006c6e  mov     ecx, ebx
0x180006c70  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006c75  nop
0x180006c76  test    rsi, rsi
0x180006c79  jz      short loc_180006C84
0x180006c7b  mov     rcx, rsi; void *
0x180006c7e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006c83  nop
0x180006c84  test    rdi, rdi
0x180006c87  jz      short loc_180006C91
0x180006c89  mov     rcx, rdi; void *
0x180006c8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006c91  mov     eax, r14d
0x180006c94  jmp     loc_180006D2C
0x180006c99  mov     rdx, rsi; unsigned __int16 *
0x180006c9c  mov     rcx, rbp; this
0x180006c9f  call    ?SavePackageMetadata@ProvisioningPackage@@AEAAJPEBG@Z; ProvisioningPackage::SavePackageMetadata(ushort const *)
0x180006ca4  mov     ebp, eax
0x180006ca6  test    eax, eax
0x180006ca8  jns     short loc_180006D05
0x180006caa  mov     [rsp+58h+var_30], eax
0x180006cae  mov     dword ptr [rsp+58h+var_38], 3Ah ; ':'
0x180006cb6  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006cbd  lea     r8, aProvisioningpa_2; "ProvisioningPackage::CreateProvisioning"...
0x180006cc4  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006ccb  mov     ebx, 3
0x180006cd0  mov     ecx, ebx
0x180006cd2  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006cd7  lea     rdx, aFailedToSavePa; "    Failed to save package metadata"
0x180006cde  mov     ecx, ebx
0x180006ce0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006ce5  nop
0x180006ce6  test    rsi, rsi
0x180006ce9  jz      short loc_180006CF4
0x180006ceb  mov     rcx, rsi; void *
0x180006cee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006cf3  nop
0x180006cf4  test    rdi, rdi
0x180006cf7  jz      short loc_180006D01
0x180006cf9  mov     rcx, rdi; void *
0x180006cfc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006d01  mov     eax, ebp
0x180006d03  jmp     short loc_180006D2C
0x180006d05  mov     rcx, rsi; lpFileName
0x180006d08  call    cs:__imp_DeleteFileW
0x180006d0e  nop
0x180006d0f  test    rsi, rsi
0x180006d12  jz      short loc_180006D1D
0x180006d14  mov     rcx, rsi; void *
0x180006d17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006d1c  nop
0x180006d1d  test    rdi, rdi
0x180006d20  jz      short loc_180006D2A
0x180006d22  mov     rcx, rdi; void *
0x180006d25  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006d2a  xor     eax, eax
0x180006d2c  mov     rbx, [rsp+58h+arg_0]
0x180006d31  mov     rbp, [rsp+58h+arg_18]
0x180006d36  add     rsp, 30h
0x180006d3a  pop     r15
0x180006d3c  pop     r14
0x180006d3e  pop     r12
0x180006d40  pop     rdi
0x180006d41  pop     rsi
0x180006d42  retn
```

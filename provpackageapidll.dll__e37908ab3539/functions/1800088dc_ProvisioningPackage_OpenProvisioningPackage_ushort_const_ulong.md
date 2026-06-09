# ProvisioningPackage::OpenProvisioningPackage(ushort const *,ulong)

- ea: `0x1800088dc`
- end: `0x180008b62`
- name: `?OpenProvisioningPackage@ProvisioningPackage@@AEAAJPEBGK@Z`
- size: `646`
- prototype: `__int64 __fastcall(ProvisioningPackage *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x180005cc0`
- `0x180005e10`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x1800078e8`
- `0x1800088dc`
- `0x180008b9c`
- `0x180008d24`
- `0x18000e4b0`
- `0x18000f040`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008af6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008af6`

## string_xrefs

- `0x180008975`: `    Failed to allocate _spPackagePath.get()`
- `0x1800089ce`: `    Failed to copy package path string`
- `0x180008a69`: `    Failed to get temporary file`
- `0x18000895d`: `ProvisioningPackage::OpenProvisioningPackage`
- `0x1800089b4`: `ProvisioningPackage::OpenProvisioningPackage`
- `0x1800089fa`: `ProvisioningPackage::OpenProvisioningPackage`
- `0x180008a4f`: `ProvisioningPackage::OpenProvisioningPackage`
- `0x180008ab9`: `ProvisioningPackage::OpenProvisioningPackage`
- `0x180008b1d`: `ProvisioningPackage::OpenProvisioningPackage`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::OpenProvisioningPackage(
        ProvisioningPackage *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // kr00_8
  void *v10; // rax
  const struct std::nothrow_t *v11; // rdx
  void *v12; // rcx
  unsigned __int16 *v13; // rcx
  unsigned int v14; // edi
  int v16; // eax
  int v17; // eax
  int TemporaryFile; // eax
  const struct std::nothrow_t *v19; // rdx
  WCHAR *v20; // rdi
  int PackageMetadata; // eax
  unsigned int v22; // esi
  const struct std::nothrow_t *v23; // rdx
  int NumElements; // eax
  const struct std::nothrow_t *v25; // rdx
  int v26; // [rsp+20h] [rbp-28h]
  int v27; // [rsp+20h] [rbp-28h]
  int v28; // [rsp+20h] [rbp-28h]
  int v29; // [rsp+20h] [rbp-28h]
  int v30; // [rsp+20h] [rbp-28h]
  int v31; // [rsp+20h] [rbp-28h]
  int v32; // [rsp+28h] [rbp-20h]
  int v33; // [rsp+28h] [rbp-20h]
  int v34; // [rsp+28h] [rbp-20h]
  int v35; // [rsp+28h] [rbp-20h]
  int v36; // [rsp+28h] [rbp-20h]
  int v37; // [rsp+28h] [rbp-20h]
  LPCWSTR lpFileName; // [rsp+50h] [rbp+8h] BYREF

  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = v6 + 1;
  v9 = v6 + 1;
  v8 = 2 * (v6 + 1);
  if ( !is_mul_ok(v9, 2u) )
    v8 = -1;
  v10 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  v12 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v10;
  if ( v12 )
    operator delete(v12, v11);
  v13 = (unsigned __int16 *)*((_QWORD *)this + 3);
  if ( !v13 )
  {
    v14 = -2147024882;
    v32 = -2147024882;
    v26 = 161;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::OpenProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v26,
      v32);
    ProvPackageLog(3, L"    Failed to allocate _spPackagePath.get()");
    return v14;
  }
  v16 = PathCchCanonicalizeEx(v13, v7, a2, PATHCCH_ALLOW_LONG_PATHS);
  v14 = v16;
  if ( v16 < 0 )
  {
    v33 = v16;
    v27 = 164;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::OpenProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v27,
      v33);
    ProvPackageLog(3, L"    Failed to copy package path string");
    return v14;
  }
  v17 = ProvisioningPackage::ResetHandles(this, a3);
  v14 = v17;
  if ( v17 < 0 )
  {
    v34 = v17;
    v28 = 169;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::OpenProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v28,
      v34);
    ProvPackageLog(3, L"    Failed to reset handles");
    return v14;
  }
  lpFileName = 0;
  TemporaryFile = GetTemporaryFile((__int64)L"tpm", &lpFileName);
  v14 = TemporaryFile;
  if ( TemporaryFile < 0 )
  {
    v35 = TemporaryFile;
    v29 = 174;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::OpenProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v29,
      v35);
    ProvPackageLog(3, L"    Failed to get temporary file");
    if ( lpFileName )
      operator delete((void *)lpFileName, v19);
    return v14;
  }
  v20 = (WCHAR *)lpFileName;
  PackageMetadata = ProvisioningPackage::RetrievePackageMetadata(this, lpFileName);
  v22 = PackageMetadata;
  if ( PackageMetadata < 0 )
  {
    v36 = PackageMetadata;
    v30 = 176;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::OpenProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v30,
      v36);
    ProvPackageLog(3, L"    Failed to retrieve package metadata");
LABEL_19:
    if ( v20 )
      operator delete(v20, v23);
    return v22;
  }
  DeleteFileW(v20);
  NumElements = ProvisioningPackage::GetNumElements(this);
  v22 = NumElements;
  if ( NumElements < 0 )
  {
    v37 = NumElements;
    v31 = 180;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::OpenProvisioningPackage",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v31,
      v37);
    ProvPackageLog(3, L"    Failed to get number of elements");
    goto LABEL_19;
  }
  if ( v20 )
    operator delete(v20, v25);
  return 0;
}

```

## disassembly

```asm
0x1800088dc  mov     [rsp+arg_8], rbx
0x1800088e1  mov     [rsp+arg_10], rbp
0x1800088e6  push    rsi
0x1800088e7  push    rdi
0x1800088e8  push    r14
0x1800088ea  sub     rsp, 30h
0x1800088ee  mov     esi, r8d
0x1800088f1  mov     rdi, rdx
0x1800088f4  mov     rbx, rcx
0x1800088f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800088fb  mov     rax, rcx
0x1800088fe  xor     r14d, r14d
0x180008901  inc     rax
0x180008904  cmp     [rdx+rax*2], r14w
0x180008909  jnz     short loc_180008901
0x18000890b  lea     rbp, [rax+1]
0x18000890f  mov     eax, 2
0x180008914  mul     rbp
0x180008917  cmovb   rax, rcx
0x18000891b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008922  mov     rcx, rax; unsigned __int64
0x180008925  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000892a  mov     rcx, [rbx+18h]; void *
0x18000892e  mov     [rbx+18h], rax
0x180008932  test    rcx, rcx
0x180008935  jz      short loc_18000893C
0x180008937  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000893c  mov     rcx, [rbx+18h]; unsigned __int16 *
0x180008940  test    rcx, rcx
0x180008943  jnz     short loc_18000898A
0x180008945  mov     edi, 8007000Eh
0x18000894a  mov     [rsp+48h+var_20], edi
0x18000894e  mov     [rsp+48h+var_28], 0A1h
0x180008956  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000895d  lea     r8, aProvisioningpa_17; "ProvisioningPackage::OpenProvisioningPa"...
0x180008964  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000896b  lea     ebx, [rcx+3]
0x18000896e  mov     ecx, ebx
0x180008970  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008975  lea     rdx, aFailedToAlloca_11; "    Failed to allocate _spPackagePath.g"...
0x18000897c  mov     ecx, ebx
0x18000897e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008983  mov     eax, edi
0x180008985  jmp     loc_180008B4F
0x18000898a  mov     r9d, 1; enum PATHCCH_OPTIONS
0x180008990  mov     r8, rdi; unsigned __int16 *
0x180008993  mov     rdx, rbp; unsigned __int64
0x180008996  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x18000899b  mov     edi, eax
0x18000899d  test    eax, eax
0x18000899f  jns     short loc_1800089D7
0x1800089a1  mov     [rsp+48h+var_20], eax
0x1800089a5  mov     [rsp+48h+var_28], 0A4h
0x1800089ad  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800089b4  lea     r8, aProvisioningpa_17; "ProvisioningPackage::OpenProvisioningPa"...
0x1800089bb  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800089c2  mov     ebx, 3
0x1800089c7  mov     ecx, ebx
0x1800089c9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800089ce  lea     rdx, aFailedToCopyPa_0; "    Failed to copy package path string"
0x1800089d5  jmp     short loc_18000897C
0x1800089d7  mov     edx, esi; unsigned int
0x1800089d9  mov     rcx, rbx; this
0x1800089dc  call    ?ResetHandles@ProvisioningPackage@@AEAAJK@Z; ProvisioningPackage::ResetHandles(ulong)
0x1800089e1  mov     edi, eax
0x1800089e3  test    eax, eax
0x1800089e5  jns     short loc_180008A20
0x1800089e7  mov     [rsp+48h+var_20], eax
0x1800089eb  mov     [rsp+48h+var_28], 0A9h
0x1800089f3  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800089fa  lea     r8, aProvisioningpa_17; "ProvisioningPackage::OpenProvisioningPa"...
0x180008a01  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008a08  mov     ebx, 3
0x180008a0d  mov     ecx, ebx
0x180008a0f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008a14  lea     rdx, aFailedToResetH; "    Failed to reset handles"
0x180008a1b  jmp     loc_18000897C
0x180008a20  mov     [rsp+48h+lpFileName], r14
0x180008a25  lea     rdx, [rsp+48h+lpFileName]
0x180008a2a  lea     rcx, aTpm; "tpm"
0x180008a31  call    ?GetTemporaryFile@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFile(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x180008a36  mov     edi, eax
0x180008a38  test    eax, eax
0x180008a3a  jns     short loc_180008A90
0x180008a3c  mov     [rsp+48h+var_20], eax
0x180008a40  mov     [rsp+48h+var_28], 0AEh
0x180008a48  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008a4f  lea     r8, aProvisioningpa_17; "ProvisioningPackage::OpenProvisioningPa"...
0x180008a56  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008a5d  mov     ebx, 3
0x180008a62  mov     ecx, ebx
0x180008a64  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008a69  lea     rdx, aFailedToGetTem_0; "    Failed to get temporary file"
0x180008a70  mov     ecx, ebx
0x180008a72  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008a77  nop
0x180008a78  mov     rcx, [rsp+48h+lpFileName]; void *
0x180008a7d  test    rcx, rcx
0x180008a80  jz      loc_180008983
0x180008a86  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008a8b  jmp     loc_180008983
0x180008a90  mov     rdi, [rsp+48h+lpFileName]
0x180008a95  mov     rdx, rdi; unsigned __int16 *
0x180008a98  mov     rcx, rbx; this
0x180008a9b  call    ?RetrievePackageMetadata@ProvisioningPackage@@AEAAJPEBG@Z; ProvisioningPackage::RetrievePackageMetadata(ushort const *)
0x180008aa0  mov     esi, eax
0x180008aa2  test    eax, eax
0x180008aa4  jns     short loc_180008AF3
0x180008aa6  mov     [rsp+48h+var_20], eax
0x180008aaa  mov     [rsp+48h+var_28], 0B0h
0x180008ab2  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008ab9  lea     r8, aProvisioningpa_17; "ProvisioningPackage::OpenProvisioningPa"...
0x180008ac0  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008ac7  mov     ebx, 3
0x180008acc  mov     ecx, ebx
0x180008ace  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008ad3  lea     rdx, aFailedToRetrie_0; "    Failed to retrieve package metadata"
0x180008ada  mov     ecx, ebx
0x180008adc  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008ae1  nop
0x180008ae2  test    rdi, rdi
0x180008ae5  jz      short loc_180008AEF
0x180008ae7  mov     rcx, rdi; void *
0x180008aea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008aef  mov     eax, esi
0x180008af1  jmp     short loc_180008B4F
0x180008af3  mov     rcx, rdi; lpFileName
0x180008af6  call    cs:__imp_DeleteFileW
0x180008afc  mov     rcx, rbx; this
0x180008aff  call    ?GetNumElements@ProvisioningPackage@@AEAAJXZ; ProvisioningPackage::GetNumElements(void)
0x180008b04  mov     esi, eax
0x180008b06  test    eax, eax
0x180008b08  jns     short loc_180008B40
0x180008b0a  mov     [rsp+48h+var_20], eax
0x180008b0e  mov     [rsp+48h+var_28], 0B4h
0x180008b16  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008b1d  lea     r8, aProvisioningpa_17; "ProvisioningPackage::OpenProvisioningPa"...
0x180008b24  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008b2b  mov     ebx, 3
0x180008b30  mov     ecx, ebx
0x180008b32  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008b37  lea     rdx, aFailedToGetNum; "    Failed to get number of elements"
0x180008b3e  jmp     short loc_180008ADA
0x180008b40  test    rdi, rdi
0x180008b43  jz      short loc_180008B4D
0x180008b45  mov     rcx, rdi; void *
0x180008b48  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008b4d  xor     eax, eax
0x180008b4f  mov     rbx, [rsp+48h+arg_8]
0x180008b54  mov     rbp, [rsp+48h+arg_10]
0x180008b59  add     rsp, 30h
0x180008b5d  pop     r14
0x180008b5f  pop     rdi
0x180008b60  pop     rsi
0x180008b61  retn
```

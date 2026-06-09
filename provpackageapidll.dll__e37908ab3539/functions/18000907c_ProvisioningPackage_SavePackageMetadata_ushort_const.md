# ProvisioningPackage::SavePackageMetadata(ushort const *)

- ea: `0x18000907c`
- end: `0x1800093ee`
- name: `?SavePackageMetadata@ProvisioningPackage@@AEAAJPEBG@Z`
- size: `882`
- prototype: `int __fastcall(ProvisioningPackage *this, WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x1800068b8`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000907c`
- `0x180012b94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000914d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000926e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009312`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000914d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000926e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009312`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000922d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000922d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093cd`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180009140`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180009140`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800090c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800090c1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000925f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000925f`
- `WIMGAPI!WIMSetImageInformation` at `0x1800092f5`
- `WIMGAPI!WIMSetImageInformation` at `0x1800092f5`

## string_xrefs

- `0x180009118`: `    Failed to create file`
- `0x1800092b9`: `    Failed to read file`

## pseudocode

```c
int __fastcall ProvisioningPackage::SavePackageMetadata(ProvisioningPackage *this, WCHAR *a2)
{
  HANDLE FileW; // rax
  void *v5; // rbx
  signed int LastError; // eax
  int result; // eax
  DWORD FileSize; // eax
  unsigned __int64 v9; // rsi
  signed int v10; // eax
  signed int v11; // eax
  unsigned int v12; // esi
  unsigned __int64 v13; // rax
  void *v14; // rax
  void *v15; // rbp
  int v16; // edi
  signed int v17; // eax
  bool v18; // sf
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  bool v22; // sf
  signed int v23; // eax
  int PackageMetadata; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-58h]
  LPOVERLAPPED lpOverlappeda; // [rsp+20h] [rbp-58h]
  __int64 v27; // [rsp+28h] [rbp-50h]
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+18h] BYREF
  HANDLE v29; // [rsp+98h] [rbp+20h]

  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  v29 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v27) = LastError;
    LODWORD(lpOverlapped) = 392;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::SavePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      lpOverlapped,
      v27);
    ProvPackageLog(3u, L"    Failed to create file");
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  FileSize = GetFileSize(FileW, 0);
  v9 = FileSize;
  if ( FileSize == -1 )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    LODWORD(v27) = v10;
    LODWORD(lpOverlapped) = 397;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::SavePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      lpOverlapped,
      v27);
    ProvPackageLog(3u, L"    Invalid file size");
    v11 = GetLastError();
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
LABEL_12:
    if ( v5 )
      CloseHandle(v5);
    return v12;
  }
  v13 = 2LL * FileSize;
  if ( !is_mul_ok(v9, 2u) )
    v13 = -1;
  v14 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( !v14 )
  {
    v16 = -2147024882;
    LODWORD(v27) = -2147024882;
    LODWORD(lpOverlapped) = 402;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::SavePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      lpOverlapped,
      v27);
    ProvPackageLog(3u, L"    Failed to allocate pBuffer.get()");
LABEL_19:
    if ( v5 )
      CloseHandle(v5);
    return v16;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(v5, v14, v9, &NumberOfBytesRead, 0) )
  {
    v17 = GetLastError();
    v18 = v17 < 0;
    if ( v17 > 0 )
      v18 = 1;
    if ( v18 )
    {
      v19 = GetLastError();
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      LODWORD(v27) = v19;
      LODWORD(lpOverlappeda) = 406;
      ProvPackageLog(
        3u,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::SavePackageMetadata",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        lpOverlappeda,
        v27);
      ProvPackageLog(3u, L"    Failed to read file");
LABEL_29:
      v20 = GetLastError();
      v12 = v20;
      if ( v20 > 0 )
        v12 = (unsigned __int16)v20 | 0x80070000;
      operator delete(v15, (const struct std::nothrow_t *)2);
      goto LABEL_12;
    }
  }
  if ( !(unsigned int)WIMSetImageInformation(*((_QWORD *)this + 2), v15, (unsigned int)v9) )
  {
    v21 = GetLastError();
    v22 = v21 < 0;
    if ( v21 > 0 )
      v22 = 1;
    if ( v22 )
    {
      v23 = GetLastError();
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      LODWORD(v27) = v23;
      LODWORD(lpOverlappeda) = 410;
      ProvPackageLog(
        3u,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::SavePackageMetadata",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        lpOverlappeda,
        v27);
      ProvPackageLog(3u, L"    Failed to set image information");
      goto LABEL_29;
    }
  }
  PackageMetadata = GetPackageMetadata(a2, (__int64)this + 40, (_QWORD *)this + 7);
  v16 = PackageMetadata;
  if ( PackageMetadata < 0 )
  {
    LODWORD(v27) = PackageMetadata;
    LODWORD(lpOverlappeda) = 413;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::SavePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      lpOverlappeda,
      v27);
    ProvPackageLog(3u, L"    Failed to get package metadata");
    operator delete(v15, (const struct std::nothrow_t *)2);
    goto LABEL_19;
  }
  operator delete(v15, (const struct std::nothrow_t *)2);
  if ( v5 )
    CloseHandle(v5);
  return 0;
}

```

## disassembly

```asm
0x18000907c  mov     rax, rsp
0x18000907f  mov     [rax+8], rbx
0x180009083  mov     [rax+10h], rbp
0x180009087  push    rsi
0x180009088  push    rdi
0x180009089  push    r13
0x18000908b  push    r14
0x18000908d  push    r15
0x18000908f  sub     rsp, 50h
0x180009093  mov     r15, rdx
0x180009096  mov     r14, rcx
0x180009099  mov     qword ptr [rax-48h], 0
0x1800090a1  mov     dword ptr [rax-50h], 80h
0x1800090a8  mov     r13d, 3
0x1800090ae  mov     [rax-58h], r13d
0x1800090b2  xor     r9d, r9d; lpSecurityAttributes
0x1800090b5  mov     edx, 80000000h; dwDesiredAccess
0x1800090ba  lea     r8d, [r13-2]; dwShareMode
0x1800090be  mov     rcx, r15; lpFileName
0x1800090c1  call    cs:__imp_CreateFileW
0x1800090c7  mov     rbx, rax
0x1800090ca  mov     [rsp+78h+arg_18], rax
0x1800090d2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800090d6  cmp     rax, rdi
0x1800090d9  jnz     short loc_18000913B
0x1800090db  call    cs:__imp_GetLastError
0x1800090e1  mov     edi, 80070000h
0x1800090e6  test    eax, eax
0x1800090e8  jle     short loc_1800090EF
0x1800090ea  movzx   eax, ax
0x1800090ed  or      eax, edi
0x1800090ef  mov     dword ptr [rsp+78h+var_50], eax
0x1800090f3  mov     dword ptr [rsp+78h+lpOverlapped], 188h
0x1800090fb  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009102  lea     r8, aProvisioningpa_12; "ProvisioningPackage::SavePackageMetadat"...
0x180009109  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009110  mov     ecx, r13d
0x180009113  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009118  lea     rdx, aFailedToCreate_2; "    Failed to create file"
0x18000911f  mov     ecx, r13d
0x180009122  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009127  call    cs:__imp_GetLastError
0x18000912d  test    eax, eax
0x18000912f  jle     short loc_180009136
0x180009131  movzx   eax, ax
0x180009134  or      eax, edi
0x180009136  jmp     loc_1800093D5
0x18000913b  xor     edx, edx; lpFileSizeHigh
0x18000913d  mov     rcx, rbx; hFile
0x180009140  call    cs:__imp_GetFileSize
0x180009146  mov     esi, eax
0x180009148  cmp     eax, 0FFFFFFFFh
0x18000914b  jnz     short loc_1800091BF
0x18000914d  call    cs:__imp_GetLastError
0x180009153  mov     edi, 80070000h
0x180009158  test    eax, eax
0x18000915a  jle     short loc_180009161
0x18000915c  movzx   eax, ax
0x18000915f  or      eax, edi
0x180009161  mov     dword ptr [rsp+78h+var_50], eax
0x180009165  mov     dword ptr [rsp+78h+lpOverlapped], 18Dh
0x18000916d  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009174  lea     r8, aProvisioningpa_12; "ProvisioningPackage::SavePackageMetadat"...
0x18000917b  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009182  mov     ecx, r13d
0x180009185  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000918a  lea     rdx, aInvalidFileSiz; "    Invalid file size"
0x180009191  mov     ecx, r13d
0x180009194  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009199  call    cs:__imp_GetLastError
0x18000919f  mov     esi, eax
0x1800091a1  test    eax, eax
0x1800091a3  jle     short loc_1800091AA
0x1800091a5  movzx   esi, ax
0x1800091a8  or      esi, edi
0x1800091aa  test    rbx, rbx
0x1800091ad  jz      short loc_1800091B8
0x1800091af  mov     rcx, rbx; hObject
0x1800091b2  call    cs:__imp_CloseHandle
0x1800091b8  mov     eax, esi
0x1800091ba  jmp     loc_1800093D5
0x1800091bf  mov     eax, 2
0x1800091c4  mul     rsi
0x1800091c7  cmovb   rax, rdi
0x1800091cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800091d2  mov     rcx, rax; unsigned __int64
0x1800091d5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800091da  mov     rbp, rax
0x1800091dd  mov     [rsp+78h+var_38], rax
0x1800091e2  test    rax, rax
0x1800091e5  jnz     short loc_18000923A
0x1800091e7  mov     edi, 8007000Eh
0x1800091ec  mov     dword ptr [rsp+78h+var_50], edi
0x1800091f0  mov     dword ptr [rsp+78h+lpOverlapped], 192h
0x1800091f8  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800091ff  lea     r8, aProvisioningpa_12; "ProvisioningPackage::SavePackageMetadat"...
0x180009206  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000920d  mov     ecx, r13d
0x180009210  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009215  lea     rdx, aFailedToAlloca_26; "    Failed to allocate pBuffer.get()"
0x18000921c  mov     ecx, r13d
0x18000921f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009224  nop
0x180009225  test    rbx, rbx
0x180009228  jz      short loc_180009233
0x18000922a  mov     rcx, rbx; hObject
0x18000922d  call    cs:__imp_CloseHandle
0x180009233  mov     eax, edi
0x180009235  jmp     loc_1800093D5
0x18000923a  mov     [rsp+78h+NumberOfBytesRead], 0
0x180009245  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18000924e  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180009256  mov     r8d, esi; nNumberOfBytesToRead
0x180009259  mov     rdx, rbp; lpBuffer
0x18000925c  mov     rcx, rbx; hFile
0x18000925f  call    cs:__imp_ReadFile
0x180009265  mov     edi, 80070000h
0x18000926a  test    eax, eax
0x18000926c  jnz     short loc_1800092EB
0x18000926e  call    cs:__imp_GetLastError
0x180009274  test    eax, eax
0x180009276  jle     short loc_18000927F
0x180009278  movzx   eax, ax
0x18000927b  or      eax, edi
0x18000927d  test    eax, eax
0x18000927f  jns     short loc_1800092EB
0x180009281  call    cs:__imp_GetLastError
0x180009287  test    eax, eax
0x180009289  jle     short loc_180009290
0x18000928b  movzx   eax, ax
0x18000928e  or      eax, edi
0x180009290  mov     dword ptr [rsp+78h+var_50], eax
0x180009294  mov     dword ptr [rsp+78h+lpOverlapped], 196h
0x18000929c  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800092a3  lea     r8, aProvisioningpa_12; "ProvisioningPackage::SavePackageMetadat"...
0x1800092aa  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800092b1  mov     ecx, r13d
0x1800092b4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800092b9  lea     rdx, aFailedToReadFi; "    Failed to read file"
0x1800092c0  mov     ecx, r13d
0x1800092c3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800092c8  call    cs:__imp_GetLastError
0x1800092ce  test    eax, eax
0x1800092d0  mov     esi, eax
0x1800092d2  jle     short loc_1800092D9
0x1800092d4  movzx   esi, ax
0x1800092d7  or      esi, edi
0x1800092d9  mov     edx, 2; struct std::nothrow_t *
0x1800092de  mov     rcx, rbp; void *
0x1800092e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800092e6  jmp     loc_1800091AA
0x1800092eb  mov     r8d, esi
0x1800092ee  mov     rdx, rbp
0x1800092f1  mov     rcx, [r14+10h]
0x1800092f5  call    cs:__imp_WIMSetImageInformation
0x1800092fb  test    eax, eax
0x1800092fd  jnz     short loc_180009356
0x1800092ff  call    cs:__imp_GetLastError
0x180009305  test    eax, eax
0x180009307  jle     short loc_180009310
0x180009309  movzx   eax, ax
0x18000930c  or      eax, edi
0x18000930e  test    eax, eax
0x180009310  jns     short loc_180009356
0x180009312  call    cs:__imp_GetLastError
0x180009318  test    eax, eax
0x18000931a  jle     short loc_180009321
0x18000931c  movzx   eax, ax
0x18000931f  or      eax, edi
0x180009321  mov     dword ptr [rsp+78h+var_50], eax
0x180009325  mov     dword ptr [rsp+78h+lpOverlapped], 19Ah
0x18000932d  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009334  lea     r8, aProvisioningpa_12; "ProvisioningPackage::SavePackageMetadat"...
0x18000933b  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009342  mov     ecx, r13d
0x180009345  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000934a  lea     rdx, aFailedToSetIma; "    Failed to set image information"
0x180009351  jmp     loc_1800092C0
0x180009356  lea     r8, [r14+38h]
0x18000935a  lea     rdx, [r14+28h]
0x18000935e  mov     rcx, r15
0x180009361  call    ?GetPackageMetadata@@YAJPEBGAEAV?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@Z; GetPackageMetadata(ushort const *,std::map<ushort const *,std::wstring,stringCompare,std::allocator<std::pair<ushort const * const,std::wstring>>> &,std::list<std::wstring> &)
0x180009366  mov     edi, eax
0x180009368  test    eax, eax
0x18000936a  jns     short loc_1800093B7
0x18000936c  mov     dword ptr [rsp+78h+var_50], eax
0x180009370  mov     dword ptr [rsp+78h+lpOverlapped], 19Dh
0x180009378  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000937f  lea     r8, aProvisioningpa_12; "ProvisioningPackage::SavePackageMetadat"...
0x180009386  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000938d  mov     ecx, r13d
0x180009390  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009395  lea     rdx, aFailedToGetPac; "    Failed to get package metadata"
0x18000939c  mov     ecx, r13d
0x18000939f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800093a4  nop
0x1800093a5  mov     edx, 2; struct std::nothrow_t *
0x1800093aa  mov     rcx, rbp; void *
0x1800093ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800093b2  jmp     loc_180009225
0x1800093b7  mov     edx, 2; struct std::nothrow_t *
0x1800093bc  mov     rcx, rbp; void *
0x1800093bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800093c4  nop
0x1800093c5  test    rbx, rbx
0x1800093c8  jz      short loc_1800093D3
0x1800093ca  mov     rcx, rbx; hObject
0x1800093cd  call    cs:__imp_CloseHandle
0x1800093d3  xor     eax, eax
0x1800093d5  lea     r11, [rsp+78h+var_28]
0x1800093da  mov     rbx, [r11+30h]
0x1800093de  mov     rbp, [r11+38h]
0x1800093e2  mov     rsp, r11
0x1800093e5  pop     r15
0x1800093e7  pop     r14
0x1800093e9  pop     r13
0x1800093eb  pop     rdi
0x1800093ec  pop     rsi
0x1800093ed  retn
```

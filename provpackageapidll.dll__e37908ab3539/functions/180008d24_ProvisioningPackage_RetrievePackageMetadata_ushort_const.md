# ProvisioningPackage::RetrievePackageMetadata(ushort const *)

- ea: `0x180008d24`
- end: `0x180009073`
- name: `?RetrievePackageMetadata@ProvisioningPackage@@AEAAJPEBG@Z`
- size: `847`
- prototype: `__int64 __fastcall(ProvisioningPackage *this, WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1800088dc`

## callees

- `0x180006014`
- `0x180008d24`
- `0x180012b94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000904c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000904c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180008e6d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180008e6d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180008ef5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180008ef5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008de1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008f57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008ff0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000905c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008de1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008f57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008ff0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000905c`
- `WIMGAPI!WIMGetImageInformation` at `0x180008d53`
- `WIMGAPI!WIMGetImageInformation` at `0x180008d53`

## string_xrefs

- `0x180008eb8`: `    Failed to create file`
- `0x180008fb8`: `    Failed to write file`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::RetrievePackageMetadata(ProvisioningPackage *this, WCHAR *a2)
{
  signed int LastError; // eax
  bool v4; // sf
  signed int v5; // eax
  signed int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rcx
  HANDLE FileW; // rax
  void *v11; // rbx
  signed int v12; // eax
  signed int v13; // eax
  BOOL v14; // eax
  unsigned int v15; // esi
  signed int v16; // eax
  bool v17; // sf
  signed int v18; // eax
  signed int v19; // eax
  unsigned int v20; // edi
  int PackageMetadata; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-30h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-30h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-28h]
  DWORD nNumberOfBytesToWrite; // [rsp+90h] [rbp+40h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+A0h] [rbp+50h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp+58h] BYREF

  nNumberOfBytesToWrite = 0;
  hMem = 0;
  if ( !(unsigned int)WIMGetImageInformation(*((_QWORD *)this + 2), &hMem, &nNumberOfBytesToWrite) )
  {
    LastError = GetLastError();
    v4 = LastError < 0;
    if ( LastError > 0 )
      v4 = 1;
    if ( v4 )
    {
      v5 = GetLastError();
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::RetrievePackageMetadata",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        358,
        v5);
      ProvPackageLog(3, L"    Failed to get image information");
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_9;
    }
  }
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)hMem + v9) );
  if ( nNumberOfBytesToWrite > (unsigned __int64)(2 * v9) )
  {
    v7 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::RetrievePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      363,
      -2147024882);
    ProvPackageLog(3, L"    Invalid file size");
LABEL_9:
    if ( hMem )
      LocalFree(hMem);
    return v7;
  }
  FileW = CreateFileW(a2, 0x40000000u, 1u, 0, 3u, 0x80u, 0);
  v11 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    LODWORD(dwFlagsAndAttributes) = v12;
    dwCreationDisposition[0] = 368;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::RetrievePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      *(_QWORD *)dwCreationDisposition,
      dwFlagsAndAttributes);
    ProvPackageLog(3, L"    Failed to create file");
    v13 = GetLastError();
    v7 = v13;
    if ( v13 > 0 )
      v7 = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_9;
  }
  NumberOfBytesWritten = 0;
  v14 = WriteFile(FileW, hMem, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
  if ( nNumberOfBytesToWrite != NumberOfBytesWritten )
  {
    v15 = -2147418113;
    LODWORD(dwFlagsAndAttributes) = -2147418113;
    dwCreationDispositiona[0] = 374;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::RetrievePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      *(_QWORD *)dwCreationDispositiona,
      dwFlagsAndAttributes);
    ProvPackageLog(3, L"    Incorrect number of bytes written");
LABEL_24:
    if ( v11 )
      CloseHandle(v11);
    if ( hMem )
      LocalFree(hMem);
    return v15;
  }
  if ( v14 )
    goto LABEL_42;
  v16 = GetLastError();
  v17 = v16 < 0;
  if ( v16 > 0 )
    v17 = 1;
  if ( !v17 )
  {
LABEL_42:
    PackageMetadata = GetPackageMetadata(a2);
    v15 = PackageMetadata;
    if ( PackageMetadata < 0 )
    {
      LODWORD(dwFlagsAndAttributes) = PackageMetadata;
      dwCreationDispositiona[0] = 379;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ProvisioningPackage::RetrievePackageMetadata",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
        *(_QWORD *)dwCreationDispositiona,
        dwFlagsAndAttributes);
      ProvPackageLog(3, L"    Failed to get package metadata");
      goto LABEL_24;
    }
    if ( v11 )
      CloseHandle(v11);
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
  else
  {
    v18 = GetLastError();
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    LODWORD(dwFlagsAndAttributes) = v18;
    dwCreationDispositiona[0] = 376;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::RetrievePackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      *(_QWORD *)dwCreationDispositiona,
      dwFlagsAndAttributes);
    ProvPackageLog(3, L"    Failed to write file");
    v19 = GetLastError();
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v11 )
      CloseHandle(v11);
    if ( hMem )
      LocalFree(hMem);
    return v20;
  }
}

```

## disassembly

```asm
0x180008d24  push    rbp
0x180008d26  push    rbx
0x180008d27  push    rsi
0x180008d28  push    rdi
0x180008d29  push    r12
0x180008d2b  push    r14
0x180008d2d  push    r15
0x180008d2f  mov     rbp, rsp
0x180008d32  sub     rsp, 50h
0x180008d36  mov     r14, rdx
0x180008d39  mov     rsi, rcx
0x180008d3c  xor     r15d, r15d
0x180008d3f  mov     [rbp+nNumberOfBytesToWrite], r15d
0x180008d43  mov     [rbp+hMem], r15
0x180008d47  lea     r8, [rbp+nNumberOfBytesToWrite]
0x180008d4b  lea     rdx, [rbp+hMem]
0x180008d4f  mov     rcx, [rcx+10h]
0x180008d53  call    cs:__imp_WIMGetImageInformation
0x180008d59  mov     r12d, 80070000h
0x180008d5f  test    eax, eax
0x180008d61  jnz     loc_180008DEE
0x180008d67  call    cs:__imp_GetLastError
0x180008d6d  test    eax, eax
0x180008d6f  jle     short loc_180008D79
0x180008d71  movzx   eax, ax
0x180008d74  or      eax, r12d
0x180008d77  test    eax, eax
0x180008d79  jns     short loc_180008DEE
0x180008d7b  call    cs:__imp_GetLastError
0x180008d81  test    eax, eax
0x180008d83  jle     short loc_180008D8B
0x180008d85  movzx   eax, ax
0x180008d88  or      eax, r12d
0x180008d8b  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], eax
0x180008d8f  mov     [rsp+50h+dwCreationDisposition], 166h
0x180008d97  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008d9e  lea     r8, aProvisioningpa_8; "ProvisioningPackage::RetrievePackageMet"...
0x180008da5  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008dac  mov     edi, 3
0x180008db1  mov     ecx, edi
0x180008db3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008db8  lea     rdx, aFailedToGetIma; "    Failed to get image information"
0x180008dbf  mov     ecx, edi
0x180008dc1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008dc6  call    cs:__imp_GetLastError
0x180008dcc  mov     ebx, eax
0x180008dce  test    eax, eax
0x180008dd0  jle     short loc_180008DD8
0x180008dd2  movzx   ebx, ax
0x180008dd5  or      ebx, r12d
0x180008dd8  mov     rcx, [rbp+hMem]; hMem
0x180008ddc  test    rcx, rcx
0x180008ddf  jz      short loc_180008DE7
0x180008de1  call    cs:__imp_LocalFree
0x180008de7  mov     eax, ebx
0x180008de9  jmp     loc_180009064
0x180008dee  mov     rax, [rbp+hMem]
0x180008df2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008df6  inc     rcx
0x180008df9  cmp     [rax+rcx*2], r15w
0x180008dfe  jnz     short loc_180008DF6
0x180008e00  add     rcx, rcx
0x180008e03  mov     eax, [rbp+nNumberOfBytesToWrite]
0x180008e06  mov     edi, 3
0x180008e0b  cmp     rax, rcx
0x180008e0e  jbe     short loc_180008E4D
0x180008e10  mov     ebx, 8007000Eh
0x180008e15  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], ebx
0x180008e19  mov     [rsp+50h+dwCreationDisposition], 16Bh
0x180008e21  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008e28  lea     r8, aProvisioningpa_8; "ProvisioningPackage::RetrievePackageMet"...
0x180008e2f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008e36  mov     ecx, edi
0x180008e38  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008e3d  lea     rdx, aInvalidFileSiz; "    Invalid file size"
0x180008e44  mov     ecx, edi
0x180008e46  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008e4b  jmp     short loc_180008DD8
0x180008e4d  mov     [rsp+50h+hTemplateFile], r15; hTemplateFile
0x180008e52  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180008e5a  mov     [rsp+50h+dwCreationDisposition], edi; dwCreationDisposition
0x180008e5e  xor     r9d, r9d; lpSecurityAttributes
0x180008e61  mov     edx, 40000000h; dwDesiredAccess
0x180008e66  lea     r8d, [r9+1]; dwShareMode
0x180008e6a  mov     rcx, r14; lpFileName
0x180008e6d  call    cs:__imp_CreateFileW
0x180008e73  mov     rbx, rax
0x180008e76  mov     [rbp+var_10], rax
0x180008e7a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008e7e  jnz     short loc_180008EDD
0x180008e80  call    cs:__imp_GetLastError
0x180008e86  test    eax, eax
0x180008e88  jle     short loc_180008E90
0x180008e8a  movzx   eax, ax
0x180008e8d  or      eax, r12d
0x180008e90  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], eax
0x180008e94  mov     [rsp+50h+dwCreationDisposition], 170h
0x180008e9c  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008ea3  lea     r8, aProvisioningpa_8; "ProvisioningPackage::RetrievePackageMet"...
0x180008eaa  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008eb1  mov     ecx, edi
0x180008eb3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008eb8  lea     rdx, aFailedToCreate_2; "    Failed to create file"
0x180008ebf  mov     ecx, edi
0x180008ec1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008ec6  call    cs:__imp_GetLastError
0x180008ecc  mov     ebx, eax
0x180008ece  test    eax, eax
0x180008ed0  jle     short loc_180008ED8
0x180008ed2  movzx   ebx, ax
0x180008ed5  or      ebx, r12d
0x180008ed8  jmp     loc_180008DD8
0x180008edd  mov     [rbp+NumberOfBytesWritten], r15d
0x180008ee1  mov     qword ptr [rsp+50h+dwCreationDisposition], r15; lpOverlapped
0x180008ee6  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008eea  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180008eee  mov     rdx, [rbp+hMem]; lpBuffer
0x180008ef2  mov     rcx, rbx; hFile
0x180008ef5  call    cs:__imp_WriteFile
0x180008efb  mov     ecx, [rbp+NumberOfBytesWritten]
0x180008efe  cmp     [rbp+nNumberOfBytesToWrite], ecx
0x180008f01  jz      short loc_180008F64
0x180008f03  mov     esi, 8000FFFFh
0x180008f08  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], esi
0x180008f0c  mov     [rsp+50h+dwCreationDisposition], 176h
0x180008f14  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008f1b  lea     r8, aProvisioningpa_8; "ProvisioningPackage::RetrievePackageMet"...
0x180008f22  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008f29  mov     ecx, edi
0x180008f2b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008f30  lea     rdx, aIncorrectNumbe; "    Incorrect number of bytes written"
0x180008f37  mov     ecx, edi
0x180008f39  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008f3e  nop
0x180008f3f  test    rbx, rbx
0x180008f42  jz      short loc_180008F4E
0x180008f44  mov     rcx, rbx; hObject
0x180008f47  call    cs:__imp_CloseHandle
0x180008f4d  nop
0x180008f4e  mov     rcx, [rbp+hMem]; hMem
0x180008f52  test    rcx, rcx
0x180008f55  jz      short loc_180008F5D
0x180008f57  call    cs:__imp_LocalFree
0x180008f5d  mov     eax, esi
0x180008f5f  jmp     loc_180009064
0x180008f64  test    eax, eax
0x180008f66  jnz     loc_180008FFA
0x180008f6c  call    cs:__imp_GetLastError
0x180008f72  test    eax, eax
0x180008f74  jle     short loc_180008F7E
0x180008f76  movzx   eax, ax
0x180008f79  or      eax, r12d
0x180008f7c  test    eax, eax
0x180008f7e  jns     short loc_180008FFA
0x180008f80  call    cs:__imp_GetLastError
0x180008f86  test    eax, eax
0x180008f88  jle     short loc_180008F90
0x180008f8a  movzx   eax, ax
0x180008f8d  or      eax, r12d
0x180008f90  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], eax
0x180008f94  mov     [rsp+50h+dwCreationDisposition], 178h
0x180008f9c  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180008fa3  lea     r8, aProvisioningpa_8; "ProvisioningPackage::RetrievePackageMet"...
0x180008faa  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180008fb1  mov     ecx, edi
0x180008fb3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008fb8  lea     rdx, aFailedToWriteF; "    Failed to write file"
0x180008fbf  mov     ecx, edi
0x180008fc1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180008fc6  call    cs:__imp_GetLastError
0x180008fcc  mov     edi, eax
0x180008fce  test    eax, eax
0x180008fd0  jle     short loc_180008FD8
0x180008fd2  movzx   edi, ax
0x180008fd5  or      edi, r12d
0x180008fd8  test    rbx, rbx
0x180008fdb  jz      short loc_180008FE7
0x180008fdd  mov     rcx, rbx; hObject
0x180008fe0  call    cs:__imp_CloseHandle
0x180008fe6  nop
0x180008fe7  mov     rcx, [rbp+hMem]; hMem
0x180008feb  test    rcx, rcx
0x180008fee  jz      short loc_180008FF6
0x180008ff0  call    cs:__imp_LocalFree
0x180008ff6  mov     eax, edi
0x180008ff8  jmp     short loc_180009064
0x180008ffa  lea     r8, [rsi+38h]
0x180008ffe  lea     rdx, [rsi+28h]
0x180009002  mov     rcx, r14
0x180009005  call    ?GetPackageMetadata@@YAJPEBGAEAV?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@Z; GetPackageMetadata(ushort const *,std::map<ushort const *,std::wstring,stringCompare,std::allocator<std::pair<ushort const * const,std::wstring>>> &,std::list<std::wstring> &)
0x18000900a  mov     esi, eax
0x18000900c  test    eax, eax
0x18000900e  jns     short loc_180009044
0x180009010  mov     dword ptr [rsp+50h+dwFlagsAndAttributes], eax
0x180009014  mov     [rsp+50h+dwCreationDisposition], 17Bh
0x18000901c  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009023  lea     r8, aProvisioningpa_8; "ProvisioningPackage::RetrievePackageMet"...
0x18000902a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009031  mov     ecx, edi
0x180009033  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009038  lea     rdx, aFailedToGetPac; "    Failed to get package metadata"
0x18000903f  jmp     loc_180008F37
0x180009044  test    rbx, rbx
0x180009047  jz      short loc_180009053
0x180009049  mov     rcx, rbx; hObject
0x18000904c  call    cs:__imp_CloseHandle
0x180009052  nop
0x180009053  mov     rcx, [rbp+hMem]; hMem
0x180009057  test    rcx, rcx
0x18000905a  jz      short loc_180009062
0x18000905c  call    cs:__imp_LocalFree
0x180009062  xor     eax, eax
0x180009064  add     rsp, 50h
0x180009068  pop     r15
0x18000906a  pop     r14
0x18000906c  pop     r12
0x18000906e  pop     rdi
0x18000906f  pop     rsi
0x180009070  pop     rbx
0x180009071  pop     rbp
0x180009072  retn
```

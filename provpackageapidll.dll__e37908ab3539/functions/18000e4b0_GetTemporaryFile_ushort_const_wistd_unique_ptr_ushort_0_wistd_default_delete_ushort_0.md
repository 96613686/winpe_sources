# GetTemporaryFile(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)

- ea: `0x18000e4b0`
- end: `0x18000e7a8`
- name: `?GetTemporaryFile@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z`
- size: `760`
- prototype: `__int64 __fastcall(__int64, LPCWSTR *)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800068b8`
- `0x1800088dc`
- `0x18000a5b0`
- `0x18000e7b0`
- `0x180014870`
- `0x180014f8c`
- `0x180015530`
- `0x180016560`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180005498`
- `0x180006014`
- `0x18000e4b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e5e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e5e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e5d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e5d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e5bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e5bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e662`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e64f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e64f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e718`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e65a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e788`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e65a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e788`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e63c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e63c`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000e550`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000e550`

## string_xrefs

- `0x18000e51f`: `GetTemporaryFile`
- `0x18000e56f`: `GetTemporaryFile`
- `0x18000e69e`: `GetTemporaryFile`
- `0x18000e6ed`: `GetTemporaryFile`
- `0x18000e752`: `GetTemporaryFile`
- `0x18000e539`: `    Failed to allocate spPath->get()`
- `0x18000e589`: `    Failed to get AppData temp folder.`
- `0x18000e76c`: `    Failed to compose file name.`
- `0x18000e683`: `Error creating temp file.`
- `0x18000e70a`: `    CreateFile failed for %s`

## pseudocode

```c
__int64 __fastcall GetTemporaryFile(__int64 a1, LPCWSTR *a2)
{
  __int64 v3; // rsi
  __int64 v4; // r15
  __int64 v5; // rbx
  const WCHAR *v6; // rax
  const struct std::nothrow_t *v7; // rdx
  WCHAR *v8; // rcx
  int v9; // r13d
  unsigned int v10; // edi
  int BasicProfileFolderPath; // eax
  DWORD v12; // ebp
  int v13; // eax
  HANDLE FileW; // rsi
  DWORD LastError; // edi
  signed int v16; // eax
  signed int v17; // eax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-58h]
  __int64 dwCreationDispositiona; // [rsp+20h] [rbp-58h]
  __int64 dwCreationDispositionb; // [rsp+20h] [rbp-58h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-50h]
  DWORD dwFlagsAndAttributesa[2]; // [rsp+28h] [rbp-50h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-48h]

  v3 = a1;
  v4 = -1;
  v5 = -1;
  v6 = (const WCHAR *)operator new[](0x20Au, (const struct std::nothrow_t *)&std::nothrow);
  v8 = (WCHAR *)*a2;
  *a2 = v6;
  v9 = 0;
  if ( v8 )
    operator delete(v8, v7);
  if ( *a2 )
  {
    BasicProfileFolderPath = GetBasicProfileFolderPath(6, 0, *a2, 260);
    v10 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath >= 0 )
    {
      v12 = 0;
      do
        ++v4;
      while ( (*a2)[v4] );
      while ( 1 )
      {
        if ( v12 )
        {
          ++v12;
        }
        else
        {
          v12 = dword_1800263D0 + GetTickCount();
          ++dword_1800263D0;
        }
        LODWORD(hTemplateFile) = v12;
        dwFlagsAndAttributes[0] = GetCurrentThreadId();
        LODWORD(dwCreationDisposition) = GetCurrentProcessId();
        v13 = StringCchPrintfW(
                (unsigned __int16 *)&(*a2)[v4],
                260 - v4,
                L"\\%s-%x-%x-%x.tmp",
                v3,
                dwCreationDisposition,
                *(_QWORD *)dwFlagsAndAttributes,
                hTemplateFile);
        v10 = v13;
        if ( v13 < 0 )
        {
          dwFlagsAndAttributesa[0] = v13;
          LODWORD(dwCreationDispositiona) = 230;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "GetTemporaryFile",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
            dwCreationDispositiona,
            *(_QWORD *)dwFlagsAndAttributesa);
          ProvPackageLog(3, L"    Failed to compose file name.");
          if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle((HANDLE)v5);
          return v10;
        }
        FileW = CreateFileW(*a2, 0x80000000, 0, 0, 1u, 0x80u, 0);
        if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          LastError = GetLastError();
          CloseHandle((HANDLE)v5);
          SetLastError(LastError);
        }
        v5 = (__int64)FileW;
        if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          goto LABEL_26;
        LODWORD(dwCreationDispositionb) = 247;
        ProvPackageLog(
          0,
          L"%hs (%hs:%d): %s",
          "GetTemporaryFile",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
          dwCreationDispositionb,
          L"Error creating temp file.");
        if ( (unsigned int)++v9 >= 5 )
          break;
        v3 = a1;
      }
      if ( FileW != (HANDLE)-1LL )
      {
        if ( FileW )
LABEL_26:
          CloseHandle(FileW);
        return 0;
      }
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      dwFlagsAndAttributes[0] = v16;
      LODWORD(dwCreationDisposition) = 250;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "GetTemporaryFile",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
        dwCreationDisposition,
        *(_QWORD *)dwFlagsAndAttributes);
      ProvPackageLog(3, L"    CreateFile failed for %s", *a2);
      v17 = GetLastError();
      v10 = v17;
      if ( v17 > 0 )
        return (unsigned __int16)v17 | 0x80070000;
    }
    else
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "GetTemporaryFile",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
        202,
        BasicProfileFolderPath);
      ProvPackageLog(3, L"    Failed to get AppData temp folder.");
    }
  }
  else
  {
    v10 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "GetTemporaryFile",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      199,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate spPath->get()");
  }
  return v10;
}

```

## disassembly

```asm
0x18000e4b0  mov     rax, rsp
0x18000e4b3  mov     [rax+18h], rbx
0x18000e4b7  mov     [rax+8], rcx
0x18000e4bb  push    rbp
0x18000e4bc  push    rsi
0x18000e4bd  push    rdi
0x18000e4be  push    r12
0x18000e4c0  push    r13
0x18000e4c2  push    r14
0x18000e4c4  push    r15
0x18000e4c6  sub     rsp, 40h
0x18000e4ca  mov     r14, rdx
0x18000e4cd  mov     rsi, rcx
0x18000e4d0  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000e4d4  mov     rbx, r15
0x18000e4d7  mov     [rax+10h], rbx
0x18000e4db  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e4e2  mov     ecx, 20Ah; unsigned __int64
0x18000e4e7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000e4ec  mov     rcx, [r14]; void *
0x18000e4ef  mov     [r14], rax
0x18000e4f2  xor     r13d, r13d
0x18000e4f5  test    rcx, rcx
0x18000e4f8  jz      short loc_18000E4FF
0x18000e4fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e4ff  mov     r8, [r14]
0x18000e502  test    r8, r8
0x18000e505  jnz     short loc_18000E542
0x18000e507  mov     edi, 8007000Eh
0x18000e50c  mov     [rsp+78h+dwFlagsAndAttributes], edi
0x18000e510  mov     dword ptr [rsp+78h+dwCreationDisposition], 0C7h
0x18000e518  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e51f  lea     r8, aGettemporaryfi; "GetTemporaryFile"
0x18000e526  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e52d  mov     esi, 3
0x18000e532  mov     ecx, esi
0x18000e534  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e539  lea     rdx, aFailedToAlloca_10; "    Failed to allocate spPath->get()"
0x18000e540  jmp     short loc_18000E590
0x18000e542  mov     r12d, 104h
0x18000e548  mov     r9d, r12d
0x18000e54b  xor     edx, edx
0x18000e54d  lea     ecx, [rdx+6]
0x18000e550  call    cs:__imp_GetBasicProfileFolderPath
0x18000e556  mov     edi, eax
0x18000e558  test    eax, eax
0x18000e55a  jns     short loc_18000E59C
0x18000e55c  mov     [rsp+78h+dwFlagsAndAttributes], eax
0x18000e560  mov     dword ptr [rsp+78h+dwCreationDisposition], 0CAh
0x18000e568  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e56f  lea     r8, aGettemporaryfi; "GetTemporaryFile"
0x18000e576  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e57d  mov     esi, 3
0x18000e582  mov     ecx, esi
0x18000e584  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e589  lea     rdx, aFailedToGetApp; "    Failed to get AppData temp folder."
0x18000e590  mov     ecx, esi
0x18000e592  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e597  jmp     loc_18000E729
0x18000e59c  mov     ebp, r13d
0x18000e59f  mov     rax, [r14]
0x18000e5a2  inc     r15
0x18000e5a5  cmp     [rax+r15*2], r13w
0x18000e5aa  jnz     short loc_18000E5A2
0x18000e5ac  sub     r12, r15
0x18000e5af  jmp     short loc_18000E5B9
0x18000e5b1  mov     rsi, [rsp+78h+arg_0]
0x18000e5b9  test    ebp, ebp
0x18000e5bb  jnz     short loc_18000E5D6
0x18000e5bd  call    cs:__imp_GetTickCount
0x18000e5c3  mov     ecx, cs:dword_1800263D0
0x18000e5c9  lea     ebp, [rcx+rax]
0x18000e5cc  inc     ecx
0x18000e5ce  mov     cs:dword_1800263D0, ecx
0x18000e5d4  jmp     short loc_18000E5D8
0x18000e5d6  inc     ebp
0x18000e5d8  call    cs:__imp_GetCurrentThreadId
0x18000e5de  mov     edi, eax
0x18000e5e0  call    cs:__imp_GetCurrentProcessId
0x18000e5e6  mov     rcx, [r14]
0x18000e5e9  lea     rcx, [rcx+r15*2]; unsigned __int16 *
0x18000e5ed  mov     dword ptr [rsp+78h+hTemplateFile], ebp
0x18000e5f1  mov     [rsp+78h+dwFlagsAndAttributes], edi
0x18000e5f5  mov     dword ptr [rsp+78h+dwCreationDisposition], eax
0x18000e5f9  mov     r9, rsi
0x18000e5fc  lea     r8, aSXXXTmp; "\\%s-%x-%x-%x.tmp"
0x18000e603  mov     rdx, r12; unsigned __int64
0x18000e606  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e60b  mov     edi, eax
0x18000e60d  test    eax, eax
0x18000e60f  js      loc_18000E73F
0x18000e615  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18000e61e  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000e626  mov     dword ptr [rsp+78h+dwCreationDisposition], 1; dwCreationDisposition
0x18000e62e  xor     r9d, r9d; lpSecurityAttributes
0x18000e631  xor     r8d, r8d; dwShareMode
0x18000e634  mov     edx, 80000000h; dwDesiredAccess
0x18000e639  mov     rcx, [r14]; lpFileName
0x18000e63c  call    cs:__imp_CreateFileW
0x18000e642  mov     rsi, rax
0x18000e645  lea     rcx, [rbx-1]
0x18000e649  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000e64d  ja      short loc_18000E668
0x18000e64f  call    cs:__imp_GetLastError
0x18000e655  mov     edi, eax
0x18000e657  mov     rcx, rbx; hObject
0x18000e65a  call    cs:__imp_CloseHandle
0x18000e660  mov     ecx, edi; dwErrCode
0x18000e662  call    cs:__imp_SetLastError
0x18000e668  mov     rbx, rsi
0x18000e66b  mov     [rsp+78h+arg_8], rbx
0x18000e673  lea     rax, [rsi+1]
0x18000e677  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000e67d  jnz     loc_18000E732
0x18000e683  lea     rax, aErrorCreatingT; "Error creating temp file."
0x18000e68a  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x18000e68f  mov     dword ptr [rsp+78h+dwCreationDisposition], 0F7h
0x18000e697  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e69e  lea     r8, aGettemporaryfi; "GetTemporaryFile"
0x18000e6a5  lea     rdx, aHsHsDS; "%hs (%hs:%d): %s"
0x18000e6ac  xor     ecx, ecx
0x18000e6ae  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e6b3  inc     r13d
0x18000e6b6  cmp     r13d, 5
0x18000e6ba  jb      loc_18000E5B1
0x18000e6c0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000e6c4  jnz     short loc_18000E72B
0x18000e6c6  call    cs:__imp_GetLastError
0x18000e6cc  mov     ebx, 80070000h
0x18000e6d1  test    eax, eax
0x18000e6d3  jle     short loc_18000E6DA
0x18000e6d5  movzx   eax, ax
0x18000e6d8  or      eax, ebx
0x18000e6da  mov     [rsp+78h+dwFlagsAndAttributes], eax
0x18000e6de  mov     dword ptr [rsp+78h+dwCreationDisposition], 0FAh
0x18000e6e6  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e6ed  lea     r8, aGettemporaryfi; "GetTemporaryFile"
0x18000e6f4  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e6fb  mov     esi, 3
0x18000e700  mov     ecx, esi
0x18000e702  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e707  mov     r8, [r14]
0x18000e70a  lea     rdx, aCreatefileFail; "    CreateFile failed for %s"
0x18000e711  mov     ecx, esi
0x18000e713  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e718  call    cs:__imp_GetLastError
0x18000e71e  mov     edi, eax
0x18000e720  test    eax, eax
0x18000e722  jle     short loc_18000E729
0x18000e724  movzx   edi, ax
0x18000e727  or      edi, ebx
0x18000e729  jmp     short loc_18000E78E
0x18000e72b  test    rsi, rsi
0x18000e72e  jz      short loc_18000E73B
0x18000e730  jmp     short $+2
0x18000e732  mov     rcx, rsi; hObject
0x18000e735  call    cs:__imp_CloseHandle
0x18000e73b  xor     eax, eax
0x18000e73d  jmp     short loc_18000E790
0x18000e73f  mov     [rsp+78h+dwFlagsAndAttributes], edi
0x18000e743  mov     dword ptr [rsp+78h+dwCreationDisposition], 0E6h
0x18000e74b  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e752  lea     r8, aGettemporaryfi; "GetTemporaryFile"
0x18000e759  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e760  mov     esi, 3
0x18000e765  mov     ecx, esi
0x18000e767  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e76c  lea     rdx, aFailedToCompos; "    Failed to compose file name."
0x18000e773  mov     ecx, esi
0x18000e775  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e77a  nop
0x18000e77b  lea     rax, [rbx-1]
0x18000e77f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e783  ja      short loc_18000E78E
0x18000e785  mov     rcx, rbx; hObject
0x18000e788  call    cs:__imp_CloseHandle
0x18000e78e  mov     eax, edi
0x18000e790  mov     rbx, [rsp+78h+arg_10]
0x18000e798  add     rsp, 40h
0x18000e79c  pop     r15
0x18000e79e  pop     r14
0x18000e7a0  pop     r13
0x18000e7a2  pop     r12
0x18000e7a4  pop     rdi
0x18000e7a5  pop     rsi
0x18000e7a6  pop     rbp
0x18000e7a7  retn
```

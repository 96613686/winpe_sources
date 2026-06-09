# FindClosestFileInStorageArea

- ea: `0x18005ca6c`
- end: `0x18005cd2b`
- name: `FindClosestFileInStorageArea`
- size: `703`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, STRSAFE_LPCSTR pszSrc@<rdx>, STRSAFE_LPWSTR pszDest@<r8>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005ab4`

## callees

- `0x180004c04`
- `0x180007530`
- `0x18000af80`
- `0x18000d3d0`
- `0x180017a50`
- `0x180038970`
- `0x18005ca6c`
- `0x18005d34c`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cca7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18005cb7f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18005cb7f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005cce5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005cce5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005cc6c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005cc6c`

## string_xrefs

- `0x18005cb0a`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18005cb45`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18005cbf2`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18005cc28`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18005ccb9`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`

## pseudocode

```c
__int64 __fastcall FindClosestFileInStorageArea(
        _WORD *Src,
        STRSAFE_LPCSTR pszSrc,
        STRSAFE_LPWSTR pszDest,
        __int64 a4,
        _QWORD *a5)
{
  LPCWSTR v8; // rsi
  __int64 FirstFile; // r14
  DWORD HashOfContainerA; // eax
  DWORD LastError; // edi
  __int64 v12; // r9
  __int64 v13; // rcx
  DWORD KeyFileFullPath; // eax
  DWORD v15; // eax
  HANDLE FileW; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  DWORD v19; // ebx
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE FindFileData[44]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszSrca[274]; // [rsp+7Ch] [rbp-84h] BYREF
  wchar_t pszDesta[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v25; // [rsp+2E0h] [rbp+1E0h]

  v8 = 0;
  lpFileName[0] = 0;
  FirstFile = -1;
  memset_0(FindFileData, 0, 0x250u);
  memset_0(pszDesta, 0, 0x46u);
  *a5 = -1;
  HashOfContainerA = GetHashOfContainerA(pszSrc, pszDesta, 0x23u);
  LastError = HashOfContainerA;
  if ( HashOfContainerA )
  {
    v12 = 2067;
    v13 = HashOfContainerA;
LABEL_3:
    DebugTraceError(v13, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", v12);
LABEL_22:
    FindClose((HANDLE)FirstFile);
    goto LABEL_23;
  }
  v25 = 2752607;
  KeyFileFullPath = GetKeyFileFullPath(Src, pszDesta, lpFileName);
  LastError = KeyFileFullPath;
  if ( KeyFileFullPath )
  {
    DebugTraceError(KeyFileFullPath, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", 2079);
    v8 = lpFileName[0];
    goto LABEL_22;
  }
  v8 = lpFileName[0];
  FirstFile = (__int64)FindFirstFileExW(lpFileName[0], FindExInfoStandard, FindFileData, FindExSearchNameMatch, 0, 0);
  if ( FirstFile == -1 )
  {
    LastError = GetLastError();
    if ( LastError - 2 > 1 )
      goto LABEL_22;
    LastError = -2146893802;
    v12 = 2096;
    v13 = 2148073494LL;
    goto LABEL_3;
  }
  MSCryptFree(v8);
  lpFileName[0] = 0;
  LastError = -2146893802;
  if ( StringCchCopyW(pszDest, 0x6Fu, pszSrca) < 0 )
    DebugTraceError(2148073494LL, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", 2114);
  v15 = GetKeyFileFullPath(Src, pszSrca, lpFileName);
  v8 = lpFileName[0];
  if ( v15 )
  {
    LastError = v15;
    DebugTraceError(v15, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", 2122);
  }
  else
  {
    FileW = CreateFileW(lpFileName[0], 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
    *a5 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, v8);
      v19 = GetLastError();
      DebugTraceError(v19, "dwSts", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", 2138);
      if ( v19 - 2 > 1 )
        LastError = v19;
    }
    else
    {
      LastError = 0;
    }
  }
  if ( FirstFile )
    goto LABEL_22;
LABEL_23:
  if ( v8 )
    MSCryptFree(v8);
  return LastError;
}

```

## disassembly

```asm
0x18005ca6c  mov     [rsp-8+arg_18], rbx
0x18005ca71  push    rbp
0x18005ca72  push    rsi
0x18005ca73  push    rdi
0x18005ca74  push    r12
0x18005ca76  push    r13
0x18005ca78  push    r14
0x18005ca7a  push    r15
0x18005ca7c  lea     rbp, [rsp-200h]
0x18005ca84  sub     rsp, 300h
0x18005ca8b  mov     rax, cs:__security_cookie
0x18005ca92  xor     rax, rsp
0x18005ca95  mov     [rbp+230h+var_40], rax
0x18005ca9c  mov     r12, [rbp+230h+arg_20]
0x18005caa3  mov     r13, r8
0x18005caa6  mov     rbx, rdx
0x18005caa9  mov     r15, rcx
0x18005caac  xor     esi, esi
0x18005caae  lea     rcx, [rsp+330h+FindFileData]; void *
0x18005cab3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005cab7  mov     [rsp+330h+lpFileName], rsi
0x18005cabc  xor     edx, edx; Val
0x18005cabe  mov     r8d, 250h; Size
0x18005cac4  mov     r14, rdi
0x18005cac7  call    memset_0
0x18005cacc  xor     edx, edx; Val
0x18005cace  lea     r8d, [rsi+46h]; Size
0x18005cad2  lea     rcx, [rbp+230h+pszDest]; void *
0x18005cad9  call    memset_0
0x18005cade  lea     r8d, [rsi+23h]; cchDest
0x18005cae2  mov     [r12], rdi
0x18005cae6  lea     rdx, [rbp+230h+pszDest]; pszDest
0x18005caed  mov     rcx, rbx; pszSrc
0x18005caf0  call    GetHashOfContainerA
0x18005caf5  mov     edi, eax
0x18005caf7  test    eax, eax
0x18005caf9  jz      short loc_18005CB1B
0x18005cafb  mov     r9d, 813h
0x18005cb01  mov     ecx, eax
0x18005cb03  lea     rdx, aDwreturn; "dwReturn"
0x18005cb0a  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cb11  call    DebugTraceError
0x18005cb16  jmp     loc_18005CCE2
0x18005cb1b  lea     r8, [rsp+330h+lpFileName]
0x18005cb20  mov     [rbp+230h+var_50], 2A005Fh
0x18005cb2a  lea     rdx, [rbp+230h+pszDest]; void *
0x18005cb31  mov     rcx, r15; Src
0x18005cb34  call    GetKeyFileFullPath
0x18005cb39  mov     edi, eax
0x18005cb3b  test    eax, eax
0x18005cb3d  jz      short loc_18005CB64
0x18005cb3f  mov     r9d, 81Fh
0x18005cb45  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cb4c  lea     rdx, aDwreturn; "dwReturn"
0x18005cb53  mov     ecx, eax
0x18005cb55  call    DebugTraceError
0x18005cb5a  mov     rsi, [rsp+330h+lpFileName]
0x18005cb5f  jmp     loc_18005CCE2
0x18005cb64  mov     [rsp+330h+dwAdditionalFlags], esi; dwAdditionalFlags
0x18005cb68  lea     r8, [rsp+330h+FindFileData]; lpFindFileData
0x18005cb6d  mov     [rsp+330h+lpSearchFilter], rsi; lpSearchFilter
0x18005cb72  xor     r9d, r9d; fSearchOp
0x18005cb75  mov     rsi, [rsp+330h+lpFileName]
0x18005cb7a  xor     edx, edx; fInfoLevelId
0x18005cb7c  mov     rcx, rsi; lpFileName
0x18005cb7f  call    cs:__imp_FindFirstFileExW
0x18005cb86  nop     dword ptr [rax+rax+00h]
0x18005cb8b  mov     r14, rax
0x18005cb8e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005cb92  jnz     short loc_18005CBC0
0x18005cb94  call    cs:__imp_GetLastError
0x18005cb9b  nop     dword ptr [rax+rax+00h]
0x18005cba0  mov     edi, eax
0x18005cba2  lea     ecx, [rax-2]
0x18005cba5  cmp     ecx, 1
0x18005cba8  ja      loc_18005CCE2
0x18005cbae  mov     edi, 80090016h
0x18005cbb3  mov     r9d, 830h
0x18005cbb9  mov     ecx, edi
0x18005cbbb  jmp     loc_18005CB03
0x18005cbc0  mov     rcx, rsi
0x18005cbc3  call    MSCryptFree
0x18005cbc8  lea     r8, [rsp+330h+pszSrc]; pszSrc
0x18005cbcd  mov     [rsp+330h+lpFileName], 0
0x18005cbd6  mov     edx, 6Fh ; 'o'; cchDest
0x18005cbdb  mov     rcx, r13; pszDest
0x18005cbde  call    StringCchCopyW
0x18005cbe3  mov     edi, 80090016h
0x18005cbe8  test    eax, eax
0x18005cbea  jns     short loc_18005CC07
0x18005cbec  mov     r9d, 842h
0x18005cbf2  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cbf9  lea     rdx, aDwreturn; "dwReturn"
0x18005cc00  mov     ecx, edi
0x18005cc02  call    DebugTraceError
0x18005cc07  lea     r8, [rsp+330h+lpFileName]
0x18005cc0c  mov     rcx, r15; Src
0x18005cc0f  lea     rdx, [rsp+330h+pszSrc]; void *
0x18005cc14  call    GetKeyFileFullPath
0x18005cc19  mov     rsi, [rsp+330h+lpFileName]
0x18005cc1e  test    eax, eax
0x18005cc20  jz      short loc_18005CC44
0x18005cc22  mov     r9d, 84Ah
0x18005cc28  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cc2f  lea     rdx, aDwreturn; "dwReturn"
0x18005cc36  mov     ecx, eax
0x18005cc38  mov     edi, eax
0x18005cc3a  call    DebugTraceError
0x18005cc3f  jmp     loc_18005CCDD
0x18005cc44  xor     r9d, r9d; lpSecurityAttributes
0x18005cc47  mov     [rsp+330h+hTemplateFile], 0; hTemplateFile
0x18005cc50  mov     [rsp+330h+dwAdditionalFlags], 8000000h; dwFlagsAndAttributes
0x18005cc58  mov     edx, 80000000h; dwDesiredAccess
0x18005cc5d  mov     rcx, rsi; lpFileName
0x18005cc60  mov     dword ptr [rsp+330h+lpSearchFilter], 3; dwCreationDisposition
0x18005cc68  lea     r8d, [r9+1]; dwShareMode
0x18005cc6c  call    cs:__imp_CreateFileW
0x18005cc73  nop     dword ptr [rax+rax+00h]
0x18005cc78  mov     [r12], rax
0x18005cc7c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005cc80  jnz     short loc_18005CCDB
0x18005cc82  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cc89  lea     rax, WPP_GLOBAL_Control
0x18005cc90  cmp     rcx, rax
0x18005cc93  jz      short loc_18005CCA7
0x18005cc95  test    byte ptr [rcx+1Ch], 1
0x18005cc99  jz      short loc_18005CCA7
0x18005cc9b  mov     rcx, [rcx+10h]
0x18005cc9f  mov     r9, rsi
0x18005cca2  call    WPP_SF_SDD
0x18005cca7  call    cs:__imp_GetLastError
0x18005ccae  nop     dword ptr [rax+rax+00h]
0x18005ccb3  mov     r9d, 85Ah
0x18005ccb9  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005ccc0  mov     ecx, eax
0x18005ccc2  lea     rdx, aDwsts; "dwSts"
0x18005ccc9  mov     ebx, eax
0x18005cccb  call    DebugTraceError
0x18005ccd0  lea     ecx, [rbx-2]
0x18005ccd3  cmp     ecx, 1
0x18005ccd6  cmova   edi, ebx
0x18005ccd9  jmp     short loc_18005CCDD
0x18005ccdb  xor     edi, edi
0x18005ccdd  test    r14, r14
0x18005cce0  jz      short loc_18005CCF1
0x18005cce2  mov     rcx, r14; hFindFile
0x18005cce5  call    cs:__imp_FindClose
0x18005ccec  nop     dword ptr [rax+rax+00h]
0x18005ccf1  test    rsi, rsi
0x18005ccf4  jz      short loc_18005CCFE
0x18005ccf6  mov     rcx, rsi
0x18005ccf9  call    MSCryptFree
0x18005ccfe  mov     eax, edi
0x18005cd00  mov     rcx, [rbp+230h+var_40]
0x18005cd07  xor     rcx, rsp; StackCookie
0x18005cd0a  call    __security_check_cookie
0x18005cd0f  mov     rbx, [rsp+330h+arg_18]
0x18005cd17  add     rsp, 300h
0x18005cd1e  pop     r15
0x18005cd20  pop     r14
0x18005cd22  pop     r13
0x18005cd24  pop     r12
0x18005cd26  pop     rdi
0x18005cd27  pop     rsi
0x18005cd28  pop     rbp
0x18005cd29  retn
```

# KspFindFirstFullTrustKeyFile

- ea: `0x1800528f4`
- end: `0x180052b6b`
- name: `KspFindFirstFullTrustKeyFile`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053500`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x180011548`
- `0x180038970`
- `0x180046dc0`
- `0x180051e8c`
- `0x18005283c`
- `0x1800528f4`
- `0x1800532a4`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052ac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052adb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052ac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052adb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800529cd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800529cd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180052afd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180052afd`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180052a6f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180052a6f`

## string_xrefs

- `0x18005297c`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x1800529f4`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180052a52`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180052aa0`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`

## pseudocode

```c
__int64 __fastcall KspFindFirstFullTrustKeyFile(__int64 a1, __int64 *a2, _QWORD *a3)
{
  __int64 v6; // rsi
  __int64 FirstFile; // rdi
  __int64 v8; // r14
  DWORD KeySearchPath; // eax
  DWORD LastError; // ebx
  __int64 v11; // r9
  unsigned int v12; // eax
  DWORD v13; // eax
  DWORD v14; // r14d
  __int64 v16; // rax
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v18; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  v17 = 0;
  v6 = 0;
  FirstFile = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v18 = 0;
  hObject = 0;
  v8 = *a2;
  KeySearchPath = GetKeySearchPath(*(STRSAFE_LPCWSTR *)(*a2 + 40));
  LastError = KeySearchPath;
  if ( KeySearchPath )
  {
    v11 = 1588;
LABEL_3:
    DebugTraceError(KeySearchPath, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", v11);
    goto LABEL_15;
  }
  KeySearchPath = ChangeThreadILToMedium(&v18, &hObject);
  LastError = KeySearchPath;
  if ( KeySearchPath )
  {
    v11 = 1602;
    goto LABEL_3;
  }
  LastError = 0;
  FirstFile = (__int64)FindFirstFileExW(0, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
  if ( FirstFile != -1 )
  {
    while ( 1 )
    {
      if ( (unsigned int)IsValidKeyFileName(&FindFileData, *(unsigned int *)(a1 + 48), 1) )
      {
        v12 = ReadKeyNameFromFile(*(_WORD **)(v8 + 40), FindFileData.cFileName, *(_DWORD *)(v8 + 48), &v17);
        if ( !v12 )
        {
          v16 = v17;
          *(_QWORD *)(v8 + 32) = FirstFile;
          FirstFile = -1;
          *(_DWORD *)(v8 + 24) = 0;
          *(_DWORD *)(v8 + 52) = 1;
          *a3 = v16;
          goto LABEL_15;
        }
        DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1653);
      }
      if ( !FindNextFileW((HANDLE)FirstFile, &FindFileData) )
      {
        v6 = v17;
        goto LABEL_14;
      }
    }
  }
  LastError = GetLastError();
  DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1622);
  if ( LastError - 2 <= 1 )
LABEL_14:
    LastError = -2146893782;
LABEL_15:
  v13 = RevertBackToCallerToken((__int64)v18);
  v14 = v13;
  if ( v13 )
  {
    DebugTraceError(v13, "RevertStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1692);
    if ( !LastError )
      LastError = v14;
  }
  if ( hObject )
    CloseHandle(hObject);
  if ( v18 )
    CloseHandle(v18);
  if ( v6 )
    MSCryptFree(v6);
  if ( FirstFile != -1 )
    FindClose((HANDLE)FirstFile);
  return LastError;
}

```

## disassembly

```asm
0x1800528f4  mov     [rsp-8+arg_0], rbx
0x1800528f9  mov     [rsp-8+arg_18], rsi
0x1800528fe  push    rbp
0x1800528ff  push    rdi
0x180052900  push    r12
0x180052902  push    r13
0x180052904  push    r14
0x180052906  lea     rbp, [rsp-1B0h]
0x18005290e  sub     rsp, 2B0h
0x180052915  mov     rax, cs:__security_cookie
0x18005291c  xor     rax, rsp
0x18005291f  mov     [rbp+1D0h+var_30], rax
0x180052926  xor     r14d, r14d
0x180052929  mov     r12, r8
0x18005292c  mov     rbx, rdx
0x18005292f  mov     [rsp+2D0h+var_298], r14
0x180052934  mov     r13, rcx
0x180052937  mov     [rsp+2D0h+lpFileName], r14
0x18005293c  xor     edx, edx; Val
0x18005293e  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x180052943  mov     r8d, 250h; Size
0x180052949  mov     esi, r14d
0x18005294c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180052950  call    memset_0
0x180052955  mov     [rsp+2D0h+var_290], r14
0x18005295a  lea     rdx, [rsp+2D0h+lpFileName]
0x18005295f  mov     [rsp+2D0h+hObject], r14
0x180052964  mov     r14, [rbx]
0x180052967  mov     rcx, [r14+28h]; pszSrc
0x18005296b  call    GetKeySearchPath
0x180052970  mov     ebx, eax
0x180052972  test    eax, eax
0x180052974  jz      short loc_180052996
0x180052976  mov     r9d, 634h
0x18005297c  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052983  mov     ecx, eax
0x180052985  lea     rdx, aStatus; "Status"
0x18005298c  call    DebugTraceError
0x180052991  jmp     loc_180052A89
0x180052996  lea     rdx, [rsp+2D0h+hObject]
0x18005299b  lea     rcx, [rsp+2D0h+var_290]
0x1800529a0  call    ChangeThreadILToMedium
0x1800529a5  mov     ebx, eax
0x1800529a7  test    eax, eax
0x1800529a9  jz      short loc_1800529B3
0x1800529ab  mov     r9d, 642h
0x1800529b1  jmp     short loc_18005297C
0x1800529b3  mov     rcx, [rsp+2D0h+lpFileName]; lpFileName
0x1800529b8  lea     r8, [rsp+2D0h+FindFileData]; lpFindFileData
0x1800529bd  xor     ebx, ebx
0x1800529bf  xor     r9d, r9d; fSearchOp
0x1800529c2  mov     [rsp+2D0h+dwAdditionalFlags], ebx; dwAdditionalFlags
0x1800529c6  xor     edx, edx; fInfoLevelId
0x1800529c8  mov     [rsp+2D0h+lpSearchFilter], rbx; lpSearchFilter
0x1800529cd  call    cs:__imp_FindFirstFileExW
0x1800529d4  nop     dword ptr [rax+rax+00h]
0x1800529d9  mov     rdi, rax
0x1800529dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800529e0  jnz     short loc_180052A15
0x1800529e2  call    cs:__imp_GetLastError
0x1800529e9  nop     dword ptr [rax+rax+00h]
0x1800529ee  mov     r9d, 656h
0x1800529f4  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800529fb  mov     ecx, eax
0x1800529fd  lea     rdx, aStatus; "Status"
0x180052a04  mov     ebx, eax
0x180052a06  call    DebugTraceError
0x180052a0b  lea     ecx, [rbx-2]
0x180052a0e  cmp     ecx, 1
0x180052a11  ja      short loc_180052A89
0x180052a13  jmp     short loc_180052A84
0x180052a15  mov     edx, [r13+30h]
0x180052a19  lea     rcx, [rsp+2D0h+FindFileData]
0x180052a1e  mov     r8d, 1
0x180052a24  call    IsValidKeyFileName
0x180052a29  test    eax, eax
0x180052a2b  jz      short loc_180052A67
0x180052a2d  mov     r8d, [r14+30h]
0x180052a31  lea     r9, [rsp+2D0h+var_298]
0x180052a36  mov     rcx, [r14+28h]
0x180052a3a  lea     rdx, [rsp+2D0h+var_254]
0x180052a3f  call    ReadKeyNameFromFile
0x180052a44  test    eax, eax
0x180052a46  jz      loc_180052B49
0x180052a4c  mov     r9d, 675h
0x180052a52  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052a59  lea     rdx, aStatus; "Status"
0x180052a60  mov     ecx, eax
0x180052a62  call    DebugTraceError
0x180052a67  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180052a6c  mov     rcx, rdi; hFindFile
0x180052a6f  call    cs:__imp_FindNextFileW
0x180052a76  nop     dword ptr [rax+rax+00h]
0x180052a7b  test    eax, eax
0x180052a7d  jnz     short loc_180052A15
0x180052a7f  mov     rsi, [rsp+2D0h+var_298]
0x180052a84  mov     ebx, 8009002Ah
0x180052a89  mov     rcx, [rsp+2D0h+var_290]
0x180052a8e  call    RevertBackToCallerToken
0x180052a93  mov     r14d, eax
0x180052a96  test    eax, eax
0x180052a98  jz      short loc_180052ABB
0x180052a9a  mov     r9d, 69Ch
0x180052aa0  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052aa7  lea     rdx, aRevertstatus; "RevertStatus"
0x180052aae  mov     ecx, eax
0x180052ab0  call    DebugTraceError
0x180052ab5  test    ebx, ebx
0x180052ab7  cmovz   ebx, r14d
0x180052abb  mov     rcx, [rsp+2D0h+hObject]; hObject
0x180052ac0  test    rcx, rcx
0x180052ac3  jz      short loc_180052AD1
0x180052ac5  call    cs:__imp_CloseHandle
0x180052acc  nop     dword ptr [rax+rax+00h]
0x180052ad1  mov     rcx, [rsp+2D0h+var_290]; hObject
0x180052ad6  test    rcx, rcx
0x180052ad9  jz      short loc_180052AE7
0x180052adb  call    cs:__imp_CloseHandle
0x180052ae2  nop     dword ptr [rax+rax+00h]
0x180052ae7  test    rsi, rsi
0x180052aea  jz      short loc_180052AF4
0x180052aec  mov     rcx, rsi
0x180052aef  call    MSCryptFree
0x180052af4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180052af8  jz      short loc_180052B09
0x180052afa  mov     rcx, rdi; hFindFile
0x180052afd  call    cs:__imp_FindClose
0x180052b04  nop     dword ptr [rax+rax+00h]
0x180052b09  cmp     [rsp+2D0h+lpFileName], 0
0x180052b0f  jz      short loc_180052B1B
0x180052b11  mov     rcx, [rsp+2D0h+lpFileName]
0x180052b16  call    MSCryptFree
0x180052b1b  mov     eax, ebx
0x180052b1d  mov     rcx, [rbp+1D0h+var_30]
0x180052b24  xor     rcx, rsp; StackCookie
0x180052b27  call    __security_check_cookie
0x180052b2c  lea     r11, [rsp+2D0h+var_20]
0x180052b34  mov     rbx, [r11+30h]
0x180052b38  mov     rsi, [r11+48h]
0x180052b3c  mov     rsp, r11
0x180052b3f  pop     r14
0x180052b41  pop     r13
0x180052b43  pop     r12
0x180052b45  pop     rdi
0x180052b46  pop     rbp
0x180052b47  retn
0x180052b49  mov     rax, [rsp+2D0h+var_298]
0x180052b4e  mov     [r14+20h], rdi
0x180052b52  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180052b56  mov     [r14+18h], ebx
0x180052b5a  mov     dword ptr [r14+34h], 1
0x180052b62  mov     [r12], rax
0x180052b66  jmp     loc_180052A89
```

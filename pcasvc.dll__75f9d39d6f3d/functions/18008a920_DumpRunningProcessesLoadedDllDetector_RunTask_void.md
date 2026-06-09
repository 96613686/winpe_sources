# DumpRunningProcessesLoadedDllDetector_RunTask(void)

- ea: `0x18008a920`
- end: `0x18008ad6d`
- name: `?DumpRunningProcessesLoadedDllDetector_RunTask@@YAXXZ`
- size: `1101`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007fee0`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x18007a9cf`
- `0x18008a920`
- `0x18008b8a4`
- `0x18008ba9c`
- `0x18008bad8`
- `0x18008c120`
- `0x18008c4fc`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18008abb6`
- `msvcrt!_wcsicmp` at `0x18008abb6`
- `ntdll!RtlFreeHeap` at `0x18008ad3a`
- `ntdll!RtlFreeHeap` at `0x18008ad3a`
- `ntdll!RtlAllocateHeap` at `0x18008aa42`
- `ntdll!RtlAllocateHeap` at `0x18008aa42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a9c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aabe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a9c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aabe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab39`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008a9b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008a9b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008a9a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008a9a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ad1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ad1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008ac37`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008ac37`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18008ab2f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18008ab2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008aa03`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008aa8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008aa03`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008aa8a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008ac7a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008ac7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ad4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ad4a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008aab4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008aab4`

## string_xrefs

- `0x18008ac6c`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18008aa9a`: `GetTokenInformation failed [%d]`
- `0x18008a983`: `Starting DumpRunningProcessesLoadedDllDetector task...`
- `0x18008a9c7`: `OpenProcessToken failed [%d]`
- `0x18008a990`: `DumpRunningProcessesLoadedDllDetector_RunTask`
- `0x18008acc5`: `DumpRunningProcessesLoadedDllDetector_RunTask`
- `0x18008acee`: `DumpRunningProcessesLoadedDllDetector_RunTask`
- `0x18008aa55`: `Failed to allocate memory for token user`
- `0x18008aa1a`: `GetTokenInformation failed to get buffer size [%d]`
- `0x18008aac4`: `ConvertSidToStringSidW failed [%d]`
- `0x18008aaf8`: `StringCchPrintfW failed to build user file path`
- `0x18008aadb`: `%%windir%%\appcompat\pca\ProcessLoadedDllList.%ws.txt`
- `0x18008ab64`: `Failed to read existing DLL list`
- `0x18008ace1`: `Exception occurred while reading existing DLL list. Exception code: 0x%x`
- `0x18008abec`: `Successfully merged exe launch history from AppCompatCache.`
- `0x18008abc0`: `Merging exe launch history from AppCompatCache...`
- `0x18008ac20`: `Failed to write DLL list to file`
- `0x18008abfb`: `Failed to merge exe launch history from AppCompatCache or no data available.`
- `0x18008ac88`: `RegSetKeyValueW failed to set last run Timestamp [%d]`
- `0x18008ac65`: `ProcessLoadedDllDetectorLastRun`
- `0x18008ac9f`: `DumpRunningProcessesLoadedDllDetector task completed successfully.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void DumpRunningProcessesLoadedDllDetector_RunTask(void)
{
  PSID *Heap; // rdi
  HANDLE CurrentProcess; // rax
  const char *v2; // r9
  int v3; // r8d
  const char *v4; // r9
  int v5; // r8d
  int v6; // ecx
  const char *v7; // r9
  int v8; // r8d
  DWORD TokenInformationLength; // [rsp+30h] [rbp-498h] BYREF
  PVOID P; // [rsp+38h] [rbp-490h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-488h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-480h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-478h] BYREF
  _QWORD Data[3]; // [rsp+58h] [rbp-470h] BYREF
  WCHAR Dst[264]; // [rsp+70h] [rbp-458h] BYREF
  WCHAR Src[264]; // [rsp+280h] [rbp-248h] BYREF

  SystemTimeAsFileTime = 0;
  Data[0] = 0;
  P = 0;
  memset_0(Src, 0, 0x208u);
  TokenHandle = 0;
  Heap = 0;
  TokenInformationLength = 0;
  StringSid = 0;
  AslLogCallPrintf(
    3,
    (unsigned int)"DumpRunningProcessesLoadedDllDetector_RunTask",
    1386,
    (unsigned int)"Starting DumpRunningProcessesLoadedDllDetector task...");
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    GetLastError();
    v2 = "OpenProcessToken failed [%d]";
    v3 = 1391;
LABEL_3:
    AslLogCallPrintf(1, (unsigned int)"DumpRunningProcessesLoadedDllDetector_RunTask", v3, (_DWORD)v2);
    goto LABEL_32;
  }
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() != 122 )
  {
    GetLastError();
    v2 = "GetTokenInformation failed to get buffer size [%d]";
    v3 = 1399;
    goto LABEL_3;
  }
  Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TokenInformationLength);
  Data[1] = Heap;
  if ( !Heap )
  {
    v4 = "Failed to allocate memory for token user";
    v5 = 1406;
    goto LABEL_8;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, Heap, TokenInformationLength, &TokenInformationLength) )
  {
    GetLastError();
    v2 = "GetTokenInformation failed [%d]";
    v3 = 1412;
    goto LABEL_3;
  }
  if ( !ConvertSidToStringSidW(*Heap, &StringSid) )
  {
    GetLastError();
    v2 = "ConvertSidToStringSidW failed [%d]";
    v3 = 1419;
    goto LABEL_3;
  }
  if ( StringCchPrintfW(Src, 0x104u, L"%%windir%%\\appcompat\\pca\\ProcessLoadedDllList.%ws.txt", StringSid) < 0 )
  {
    v4 = "StringCchPrintfW failed to build user file path";
    v5 = 1426;
    goto LABEL_8;
  }
  memset_0(Dst, 0, 0x208u);
  if ( !ExpandEnvironmentStringsW(Src, Dst, 0x104u) )
  {
    GetLastError();
    v2 = "ExpandEnvironmentStringsW failed [%d]";
    v3 = 1434;
    goto LABEL_3;
  }
  if ( (unsigned int)ReadExistingDllList(Dst, (struct _DLL_LIST_ENTRY **)&P) )
  {
    if ( (unsigned int)EnumerateRunningProcesses((struct _DLL_LIST_ENTRY **)&P) )
    {
      if ( !_wcsicmp(StringSid, L"S-1-5-18") )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_RunTask",
          1474,
          (unsigned int)"Merging exe launch history from AppCompatCache...");
        if ( (unsigned int)GetExeLaunchedHistory((struct _DLL_LIST_ENTRY **)&P) )
        {
          v7 = "Successfully merged exe launch history from AppCompatCache.";
          v8 = 1477;
        }
        else
        {
          v7 = "Failed to merge exe launch history from AppCompatCache or no data available.";
          v8 = 1481;
        }
        AslLogCallPrintf(3, (unsigned int)"DumpRunningProcessesLoadedDllDetector_RunTask", v8, (_DWORD)v7);
      }
      if ( (unsigned int)WriteDllListToFile(Dst, (struct _DLL_LIST_ENTRY *)P) )
      {
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        Data[0] = SystemTimeAsFileTime;
        if ( RegSetKeyValueW(
               HKEY_CURRENT_USER,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
               L"ProcessLoadedDllDetectorLastRun",
               0xBu,
               Data,
               8u) )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"DumpRunningProcessesLoadedDllDetector_RunTask",
            1506,
            (unsigned int)"RegSetKeyValueW failed to set last run Timestamp [%d]");
        }
        v4 = "DumpRunningProcessesLoadedDllDetector task completed successfully.";
        v5 = 1509;
        v6 = 3;
        goto LABEL_9;
      }
      v4 = "Failed to write DLL list to file";
      v5 = 1488;
LABEL_8:
      v6 = 1;
LABEL_9:
      AslLogCallPrintf(v6, (unsigned int)"DumpRunningProcessesLoadedDllDetector_RunTask", v5, (_DWORD)v4);
      goto LABEL_32;
    }
    AslLogCallPrintf(
      1,
      (unsigned int)"DumpRunningProcessesLoadedDllDetector_RunTask",
      1458,
      (unsigned int)"Failed to enumerate running processes");
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"DumpRunningProcessesLoadedDllDetector_RunTask",
      1443,
      (unsigned int)"Failed to read existing DLL list");
  }
LABEL_32:
  if ( P )
    FreeDllList(P);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( StringSid )
    LocalFree(StringSid);
}

```

## disassembly

```asm
0x18008a920  push    rbx
0x18008a922  push    rsi
0x18008a923  push    rdi
0x18008a924  push    r14
0x18008a926  sub     rsp, 4A8h
0x18008a92d  mov     rax, cs:__security_cookie
0x18008a934  xor     rax, rsp
0x18008a937  mov     [rsp+4C8h+var_38], rax
0x18008a93f  mov     qword ptr [rsp+4C8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18008a948  mov     [rsp+4C8h+Data], 0
0x18008a951  mov     [rsp+4C8h+P], 0
0x18008a95a  xor     edx, edx; Val
0x18008a95c  mov     r8d, 208h; Size
0x18008a962  lea     rcx, [rsp+4C8h+Src]; void *
0x18008a96a  call    memset_0
0x18008a96f  mov     [rsp+4C8h+TokenHandle], 0
0x18008a978  xor     edi, edi
0x18008a97a  mov     [rsp+4C8h+TokenInformationLength], edi
0x18008a97e  mov     [rsp+4C8h+StringSid], rdi
0x18008a983  lea     r9, aStartingDumpru_0; "Starting DumpRunningProcessesLoadedDllD"...
0x18008a98a  mov     r8d, 56Ah
0x18008a990  lea     rsi, aDumprunningpro_3; "DumpRunningProcessesLoadedDllDetector_R"...
0x18008a997  mov     rdx, rsi
0x18008a99a  lea     r14d, [rdi+3]
0x18008a99e  mov     ecx, r14d
0x18008a9a1  call    AslLogCallPrintf
0x18008a9a6  call    cs:__imp_GetCurrentProcess
0x18008a9ac  mov     rcx, rax; ProcessHandle
0x18008a9af  lea     r8, [rsp+4C8h+TokenHandle]; TokenHandle
0x18008a9b4  lea     edx, [rdi+8]; DesiredAccess
0x18008a9b7  call    cs:__imp_OpenProcessToken
0x18008a9bd  test    eax, eax
0x18008a9bf  jnz     short loc_18008A9E8
0x18008a9c1  call    cs:__imp_GetLastError
0x18008a9c7  lea     r9, aOpenprocesstok; "OpenProcessToken failed [%d]"
0x18008a9ce  mov     r8d, 56Fh
0x18008a9d4  lea     ecx, [rdi+1]
0x18008a9d7  mov     dword ptr [rsp+4C8h+ReturnLength], eax
0x18008a9db  mov     rdx, rsi
0x18008a9de  call    AslLogCallPrintf
0x18008a9e3  jmp     loc_18008AD04
0x18008a9e8  lea     rax, [rsp+4C8h+TokenInformationLength]
0x18008a9ed  mov     [rsp+4C8h+ReturnLength], rax; ReturnLength
0x18008a9f2  xor     r9d, r9d; TokenInformationLength
0x18008a9f5  xor     r8d, r8d; TokenInformation
0x18008a9f8  lea     ebx, [r9+1]
0x18008a9fc  mov     edx, ebx; TokenInformationClass
0x18008a9fe  mov     rcx, [rsp+4C8h+TokenHandle]; TokenHandle
0x18008aa03  call    cs:__imp_GetTokenInformation
0x18008aa09  call    cs:__imp_GetLastError
0x18008aa0f  cmp     eax, 7Ah ; 'z'
0x18008aa12  jz      short loc_18008AA2B
0x18008aa14  call    cs:__imp_GetLastError
0x18008aa1a  lea     r9, aGettokeninform; "GetTokenInformation failed to get buffe"...
0x18008aa21  mov     r8d, 577h
0x18008aa27  mov     ecx, ebx
0x18008aa29  jmp     short loc_18008A9D7
0x18008aa2b  mov     r8d, [rsp+4C8h+TokenInformationLength]; Size
0x18008aa30  mov     rcx, gs:60h
0x18008aa39  mov     edx, 8; Flags
0x18008aa3e  mov     rcx, [rcx+30h]; HeapHandle
0x18008aa42  call    cs:__imp_RtlAllocateHeap
0x18008aa48  mov     rdi, rax
0x18008aa4b  mov     [rsp+4C8h+var_468], rax
0x18008aa50  test    rax, rax
0x18008aa53  jnz     short loc_18008AA71
0x18008aa55  lea     r9, aFailedToAlloca_32; "Failed to allocate memory for token use"...
0x18008aa5c  mov     r8d, 57Eh
0x18008aa62  mov     ecx, ebx
0x18008aa64  mov     rdx, rsi
0x18008aa67  call    AslLogCallPrintf
0x18008aa6c  jmp     loc_18008AD04
0x18008aa71  lea     rax, [rsp+4C8h+TokenInformationLength]
0x18008aa76  mov     [rsp+4C8h+ReturnLength], rax; ReturnLength
0x18008aa7b  mov     r9d, [rsp+4C8h+TokenInformationLength]; TokenInformationLength
0x18008aa80  mov     r8, rdi; TokenInformation
0x18008aa83  mov     edx, ebx; TokenInformationClass
0x18008aa85  mov     rcx, [rsp+4C8h+TokenHandle]; TokenHandle
0x18008aa8a  call    cs:__imp_GetTokenInformation
0x18008aa90  test    eax, eax
0x18008aa92  jnz     short loc_18008AAAC
0x18008aa94  call    cs:__imp_GetLastError
0x18008aa9a  lea     r9, aGettokeninform_2; "GetTokenInformation failed [%d]"
0x18008aaa1  mov     r8d, 584h
0x18008aaa7  jmp     loc_18008AA27
0x18008aaac  lea     rdx, [rsp+4C8h+StringSid]; StringSid
0x18008aab1  mov     rcx, [rdi]; Sid
0x18008aab4  call    cs:__imp_ConvertSidToStringSidW
0x18008aaba  test    eax, eax
0x18008aabc  jnz     short loc_18008AAD6
0x18008aabe  call    cs:__imp_GetLastError
0x18008aac4  lea     r9, aConvertsidtost_1; "ConvertSidToStringSidW failed [%d]"
0x18008aacb  mov     r8d, 58Bh
0x18008aad1  jmp     loc_18008AA27
0x18008aad6  mov     r9, [rsp+4C8h+StringSid]
0x18008aadb  lea     r8, aWindirAppcompa; "%%windir%%\\appcompat\\pca\\ProcessLoad"...
0x18008aae2  mov     edx, 104h; unsigned __int64
0x18008aae7  lea     rcx, [rsp+4C8h+Src]; unsigned __int16 *
0x18008aaef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008aaf4  test    eax, eax
0x18008aaf6  jns     short loc_18008AB0A
0x18008aaf8  lea     r9, aStringcchprint_0; "StringCchPrintfW failed to build user f"...
0x18008aaff  mov     r8d, 592h
0x18008ab05  jmp     loc_18008AA62
0x18008ab0a  xor     edx, edx; Val
0x18008ab0c  mov     r8d, 208h; Size
0x18008ab12  lea     rcx, [rsp+4C8h+Dst]; void *
0x18008ab17  call    memset_0
0x18008ab1c  mov     r8d, 104h; nSize
0x18008ab22  lea     rdx, [rsp+4C8h+Dst]; lpDst
0x18008ab27  lea     rcx, [rsp+4C8h+Src]; lpSrc
0x18008ab2f  call    cs:__imp_ExpandEnvironmentStringsW
0x18008ab35  test    eax, eax
0x18008ab37  jnz     short loc_18008AB51
0x18008ab39  call    cs:__imp_GetLastError
0x18008ab3f  lea     r9, aExpandenvironm_0; "ExpandEnvironmentStringsW failed [%d]"
0x18008ab46  mov     r8d, 59Ah
0x18008ab4c  jmp     loc_18008AA27
0x18008ab51  lea     rdx, [rsp+4C8h+P]; struct _DLL_LIST_ENTRY **
0x18008ab56  lea     rcx, [rsp+4C8h+Dst]; unsigned __int16 *
0x18008ab5b  call    ?ReadExistingDllList@@YAHPEBGPEAPEAU_DLL_LIST_ENTRY@@@Z; ReadExistingDllList(ushort const *,_DLL_LIST_ENTRY * *)
0x18008ab60  test    eax, eax
0x18008ab62  jnz     short loc_18008AB80
0x18008ab64  lea     r9, aFailedToReadEx; "Failed to read existing DLL list"
0x18008ab6b  mov     r8d, 5A3h
0x18008ab71  mov     rdx, rsi
0x18008ab74  mov     ecx, ebx
0x18008ab76  call    AslLogCallPrintf
0x18008ab7b  jmp     loc_18008AD04
0x18008ab80  lea     rcx, [rsp+4C8h+P]; struct _DLL_LIST_ENTRY **
0x18008ab85  call    ?EnumerateRunningProcesses@@YAHPEAPEAU_DLL_LIST_ENTRY@@@Z; EnumerateRunningProcesses(_DLL_LIST_ENTRY * *)
0x18008ab8a  test    eax, eax
0x18008ab8c  jnz     short loc_18008ABAA
0x18008ab8e  lea     r9, aFailedToEnumer; "Failed to enumerate running processes"
0x18008ab95  mov     r8d, 5B2h
0x18008ab9b  mov     rdx, rsi
0x18008ab9e  mov     ecx, ebx
0x18008aba0  call    AslLogCallPrintf
0x18008aba5  jmp     loc_18008AD04
0x18008abaa  lea     rdx, aS1518_0; "S-1-5-18"
0x18008abb1  mov     rcx, [rsp+4C8h+StringSid]; String1
0x18008abb6  call    cs:__imp__wcsicmp
0x18008abbc  test    eax, eax
0x18008abbe  jnz     short loc_18008AC0D
0x18008abc0  lea     r9, aMergingExeLaun; "Merging exe launch history from AppComp"...
0x18008abc7  mov     r8d, 5C2h
0x18008abcd  mov     rdx, rsi
0x18008abd0  mov     ecx, r14d
0x18008abd3  call    AslLogCallPrintf
0x18008abd8  lea     rcx, [rsp+4C8h+P]; struct _DLL_LIST_ENTRY **
0x18008abdd  call    ?GetExeLaunchedHistory@@YAHPEAPEAU_DLL_LIST_ENTRY@@@Z; GetExeLaunchedHistory(_DLL_LIST_ENTRY * *)
0x18008abe2  mov     rdx, rsi
0x18008abe5  mov     ecx, r14d
0x18008abe8  test    eax, eax
0x18008abea  jz      short loc_18008ABFB
0x18008abec  lea     r9, aSuccessfullyMe; "Successfully merged exe launch history "...
0x18008abf3  mov     r8d, 5C5h
0x18008abf9  jmp     short loc_18008AC08
0x18008abfb  lea     r9, aFailedToMergeE; "Failed to merge exe launch history from"...
0x18008ac02  mov     r8d, 5C9h
0x18008ac08  call    AslLogCallPrintf
0x18008ac0d  mov     rdx, [rsp+4C8h+P]; struct _DLL_LIST_ENTRY *
0x18008ac12  lea     rcx, [rsp+4C8h+Dst]; unsigned __int16 *
0x18008ac17  call    ?WriteDllListToFile@@YAHPEBGPEAU_DLL_LIST_ENTRY@@@Z; WriteDllListToFile(ushort const *,_DLL_LIST_ENTRY *)
0x18008ac1c  test    eax, eax
0x18008ac1e  jnz     short loc_18008AC32
0x18008ac20  lea     r9, aFailedToWriteD; "Failed to write DLL list to file"
0x18008ac27  mov     r8d, 5D0h
0x18008ac2d  jmp     loc_18008AA62
0x18008ac32  lea     rcx, [rsp+4C8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18008ac37  call    cs:__imp_GetSystemTimeAsFileTime
0x18008ac3d  mov     eax, [rsp+4C8h+SystemTimeAsFileTime.dwHighDateTime]
0x18008ac41  mov     dword ptr [rsp+4C8h+Data+4], eax
0x18008ac45  mov     eax, [rsp+4C8h+SystemTimeAsFileTime.dwLowDateTime]
0x18008ac49  mov     dword ptr [rsp+4C8h+Data], eax
0x18008ac4d  mov     [rsp+4C8h+cbData], 8; cbData
0x18008ac55  lea     rax, [rsp+4C8h+Data]
0x18008ac5a  mov     [rsp+4C8h+ReturnLength], rax; lpData
0x18008ac5f  mov     r9d, 0Bh; dwType
0x18008ac65  lea     r8, aProcessloadedd_1; "ProcessLoadedDllDetectorLastRun"
0x18008ac6c  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18008ac73  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18008ac7a  call    cs:__imp_RegSetKeyValueW
0x18008ac80  test    eax, eax
0x18008ac82  jz      short loc_18008AC9F
0x18008ac84  mov     dword ptr [rsp+4C8h+ReturnLength], eax
0x18008ac88  lea     r9, aRegsetkeyvalue; "RegSetKeyValueW failed to set last run "...
0x18008ac8f  mov     r8d, 5E2h
0x18008ac95  mov     rdx, rsi
0x18008ac98  mov     ecx, ebx
0x18008ac9a  call    AslLogCallPrintf
0x18008ac9f  lea     r9, aDumprunningpro_6; "DumpRunningProcessesLoadedDllDetector t"...
0x18008aca6  mov     r8d, 5E5h
0x18008acac  mov     ecx, r14d
0x18008acaf  jmp     loc_18008AA64
0x18008acb4  mov     dword ptr [rsp+4C8h+ReturnLength], eax
0x18008acb8  lea     r9, aExceptionOccur_1; "Exception occurred while enumerating ru"...
0x18008acbf  mov     r8d, 5B8h
0x18008acc5  lea     rdx, aDumprunningpro_3; "DumpRunningProcessesLoadedDllDetector_R"...
0x18008accc  mov     ecx, 1
0x18008acd1  call    AslLogCallPrintf
0x18008acd6  mov     rdi, [rsp+4C8h+var_468]
0x18008acdb  jmp     short loc_18008AD04
0x18008acdd  mov     dword ptr [rsp+4C8h+ReturnLength], eax
0x18008ace1  lea     r9, aExceptionOccur_0; "Exception occurred while reading existi"...
0x18008ace8  mov     r8d, 5A9h
0x18008acee  lea     rdx, aDumprunningpro_3; "DumpRunningProcessesLoadedDllDetector_R"...
0x18008acf5  mov     ecx, 1
0x18008acfa  call    AslLogCallPrintf
0x18008acff  mov     rdi, [rsp+4C8h+var_468]
0x18008ad04  mov     rcx, [rsp+4C8h+P]; P
0x18008ad09  test    rcx, rcx
0x18008ad0c  jz      short loc_18008AD13
0x18008ad0e  call    ?FreeDllList@@YAXPEAU_DLL_LIST_ENTRY@@@Z; FreeDllList(_DLL_LIST_ENTRY *)
0x18008ad13  mov     rcx, [rsp+4C8h+TokenHandle]; hObject
0x18008ad18  test    rcx, rcx
0x18008ad1b  jz      short loc_18008AD23
0x18008ad1d  call    cs:__imp_CloseHandle
0x18008ad23  test    rdi, rdi
0x18008ad26  jz      short loc_18008AD40
0x18008ad28  mov     rcx, gs:60h
0x18008ad31  mov     r8, rdi; P
0x18008ad34  xor     edx, edx; Flags
0x18008ad36  mov     rcx, [rcx+30h]; HeapHandle
0x18008ad3a  call    cs:__imp_RtlFreeHeap
0x18008ad40  mov     rcx, [rsp+4C8h+StringSid]; hMem
0x18008ad45  test    rcx, rcx
0x18008ad48  jz      short loc_18008AD50
0x18008ad4a  call    cs:__imp_LocalFree
0x18008ad50  mov     rcx, [rsp+4C8h+var_38]
0x18008ad58  xor     rcx, rsp; StackCookie
0x18008ad5b  call    __security_check_cookie
0x18008ad60  add     rsp, 4A8h
0x18008ad67  pop     r14
0x18008ad69  pop     rdi
0x18008ad6a  pop     rsi
0x18008ad6b  pop     rbx
0x18008ad6c  retn
```

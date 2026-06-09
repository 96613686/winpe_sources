# StartCrashVertical

- ea: `0x18005216c`
- end: `0x1800525c0`
- name: `StartCrashVertical`
- size: `1108`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ac44`

## callees

- `0x18003f154`
- `0x180052140`
- `0x18005216c`
- `0x1800525c8`
- `0x1800529d0`
- `0x180052a6c`
- `0x180052b0c`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18005225e`
- `ntdll!DbgPrintEx` at `0x180052436`
- `ntdll!DbgPrintEx` at `0x180052492`
- `ntdll!DbgPrintEx` at `0x1800524df`
- `ntdll!DbgPrintEx` at `0x1800525a5`
- `ntdll!DbgPrintEx` at `0x18005225e`
- `ntdll!DbgPrintEx` at `0x180052436`
- `ntdll!DbgPrintEx` at `0x180052492`
- `ntdll!DbgPrintEx` at `0x1800524df`
- `ntdll!DbgPrintEx` at `0x1800525a5`
- `ntdll!NtClose` at `0x18005251a`
- `ntdll!NtClose` at `0x18005251a`
- `ntdll!RtlGetCurrentTransaction` at `0x1800522a8`
- `ntdll!RtlGetCurrentTransaction` at `0x1800522a8`
- `ntdll!RtlSetCurrentTransaction` at `0x1800522b9`
- `ntdll!RtlSetCurrentTransaction` at `0x180052553`
- `ntdll!RtlSetCurrentTransaction` at `0x1800522b9`
- `ntdll!RtlSetCurrentTransaction` at `0x180052553`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800523e4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800523e4`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180052452`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180052452`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18005229c`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18005253f`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18005229c`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18005253f`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180052285`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18005252d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180052285`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18005252d`

## string_xrefs

- `0x1800524c4`: `WER/ReportFault/%u:%u: ERROR CreateProcess/mode%u failed with Win32 error %u.\n`
- `0x180052419`: `WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n`
- `0x180052477`: `WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n`
- `0x18005258e`: `WER/ReportFault/%u:%u: ERROR WerpBuildCreateProcessAttributeList failed, HRESULT %08X.\n`
- `0x180052244`: `WER/ReportFault/%u:%u: ERROR Failed to get the paths for the crash vertical: HRESULT %08X.\n`

## pseudocode

```c
__int64 __fastcall StartCrashVertical(void *a1, void *a2, unsigned int a3, HANDLE *a4)
{
  void *v4; // r12
  void *v7; // rdx
  int CrashVerticalPaths; // eax
  unsigned int LastError; // ebx
  int v10; // r15d
  __int64 CurrentTransaction; // r13
  unsigned int i; // edi
  int v13; // r14d
  __int64 v14; // rdx
  int v15; // eax
  void *v16; // r12
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  BOOL bInheritHandles; // [rsp+20h] [rbp-E0h]
  unsigned int lpEnvironment; // [rsp+30h] [rbp-D0h]
  unsigned int lpStartupInfo; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v25[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v26; // [rsp+54h] [rbp-ACh] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID lpAddress; // [rsp+60h] [rbp-A0h] BYREF
  DWORD OldMode; // [rsp+68h] [rbp-98h] BYREF
  int v30; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v31; // [rsp+70h] [rbp-90h]
  UINT uMode; // [rsp+74h] [rbp-8Ch]
  void *v33; // [rsp+78h] [rbp-88h]
  HANDLE *v34; // [rsp+80h] [rbp-80h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+88h] [rbp-78h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v37; // [rsp+108h] [rbp+8h]
  WCHAR CurrentDirectory[32]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR ApplicationName[64]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR CommandLine[128]; // [rsp+1D0h] [rbp+D0h] BYREF

  v31 = a3;
  v4 = a2;
  v33 = a2;
  v34 = a4;
  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  v30 = 2;
  *a4 = 0;
  OldMode = 0;
  v27 = 0;
  CurrentDirectory[0] = 0;
  ApplicationName[0] = 0;
  CommandLine[0] = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  StartupInfo.cb = 112;
  StartupInfo.dwFlags = 1;
  StartupInfo.wShowWindow = 0;
  CrashVerticalPaths = GetCrashVerticalPaths(
                         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                         v7,
                         a1,
                         ApplicationName,
                         bInheritHandles,
                         CommandLine,
                         lpEnvironment,
                         CurrentDirectory,
                         lpStartupInfo);
  LastError = CrashVerticalPaths;
  if ( CrashVerticalPaths < 0 )
  {
    DbgPrintEx(
      0x96u,
      0,
      "WER/ReportFault/%u:%u: ERROR Failed to get the paths for the crash vertical: HRESULT %08X.\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      621,
      CrashVerticalPaths);
    return LastError;
  }
  v10 = (unsigned int)WerpIsProtectedProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL) != 0 ? 0x40000 : 0;
  uMode = SetErrorMode(1u);
  SetThreadErrorMode(1u, &OldMode);
  CurrentTransaction = RtlGetCurrentTransaction();
  RtlSetCurrentTransaction(0);
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
      goto LABEL_27;
    if ( !i )
    {
      v27 = 4;
      goto LABEL_10;
    }
    if ( i != 1 )
    {
      v27 = 0;
LABEL_10:
      v13 = v10;
      goto LABEL_11;
    }
    v27 = 0;
    v13 = v10 | 0x1000000;
LABEL_11:
    v25[0] = 0;
    v26 = 0;
    WerpGetProcessArchitecture((void *)0xFFFFFFFFFFFFFFFFLL, v25, &v26);
    if ( v26 != 0xAA64 || v25[0] != 0x8664 )
      v25[0] = 0;
    lpAddress = 0;
    v15 = WerpBuildCreateProcessAttributeList(&lpAddress, v14, &v27, v4, v31, &v30, v25);
    LastError = v15;
    if ( v15 < 0 )
    {
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR WerpBuildCreateProcessAttributeList failed, HRESULT %08X.\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        703,
        v15);
      goto LABEL_32;
    }
    v16 = lpAddress;
    v37 = lpAddress;
    if ( CreateProcessW(
           ApplicationName,
           CommandLine,
           0,
           0,
           1,
           v13 | (lpAddress != 0 ? 0x80000 : 0),
           0,
           CurrentDirectory,
           &StartupInfo,
           &ProcessInformation) )
    {
      utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(&lpAddress);
LABEL_27:
      *v34 = ProcessInformation.hProcess;
      NtClose(ProcessInformation.hThread);
      LastError = 0;
      goto LABEL_28;
    }
    LastError = WerpGetLastError(v18, v17, v19, v20);
    if ( i )
      break;
    if ( LastError != 1314 )
      goto LABEL_24;
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      732,
      0,
      1314);
    if ( v16 )
      VirtualFree(v16, 0, 0x8000u);
LABEL_23:
    v4 = v33;
  }
  if ( i == 1 && LastError == 5 )
  {
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      738,
      1,
      5);
    utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(&lpAddress);
    goto LABEL_23;
  }
LABEL_24:
  DbgPrintEx(
    0x96u,
    0,
    "WER/ReportFault/%u:%u: ERROR CreateProcess/mode%u failed with Win32 error %u.\n",
    NtCurrentTeb()->ClientId.UniqueProcess,
    743,
    i,
    LastError);
  if ( (int)LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_32:
  utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(&lpAddress);
LABEL_28:
  SetErrorMode(uMode);
  SetThreadErrorMode(OldMode, 0);
  if ( CurrentTransaction )
    RtlSetCurrentTransaction(CurrentTransaction);
  return LastError;
}

```

## disassembly

```asm
0x18005216c  push    rbp
0x18005216e  push    rbx
0x18005216f  push    rsi
0x180052170  push    rdi
0x180052171  push    r12
0x180052173  push    r13
0x180052175  push    r14
0x180052177  push    r15
0x180052179  lea     rbp, [rsp-1E8h]
0x180052181  sub     rsp, 2E8h
0x180052188  mov     rax, cs:__security_cookie
0x18005218f  xor     rax, rsp
0x180052192  mov     [rbp+220h+var_50], rax
0x180052199  xor     eax, eax
0x18005219b  mov     [rsp+320h+var_2B0], r8d
0x1800521a0  mov     r12, rdx
0x1800521a3  mov     [rsp+320h+var_2A8], rdx
0x1800521a8  mov     rbx, rcx
0x1800521ab  mov     [rbp+220h+var_2A0], r9
0x1800521af  xor     edx, edx; Val
0x1800521b1  mov     dword ptr [rbp+220h+StartupInfo+4], eax
0x1800521b4  lea     r8d, [rax+68h]; Size
0x1800521b8  mov     rdi, r9
0x1800521bb  lea     rcx, [rbp+220h+StartupInfo.lpReserved]; void *
0x1800521bf  call    memset_0
0x1800521c4  xor     r14d, r14d
0x1800521c7  mov     [rsp+320h+var_2B4], 2
0x1800521cf  xor     eax, eax
0x1800521d1  mov     [rdi], r14
0x1800521d4  mov     qword ptr [rbp+220h+ProcessInformation.dwProcessId], rax
0x1800521d8  lea     r9, [rbp+220h+ApplicationName]; wchar_t *
0x1800521dc  xorps   xmm0, xmm0
0x1800521df  mov     [rsp+320h+OldMode], r14d
0x1800521e4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800521e8  mov     [rsp+320h+var_2C8], r14d
0x1800521ed  lea     edi, [rax+1]
0x1800521f0  mov     [rbp+220h+CurrentDirectory], r14w
0x1800521f5  lea     rax, [rbp+220h+CurrentDirectory]
0x1800521f9  mov     [rbp+220h+ApplicationName], r14w
0x1800521fe  mov     [rsp+320h+lpCurrentDirectory], rax; wchar_t *
0x180052203  mov     r8, rbx; void *
0x180052206  lea     rax, [rbp+220h+CommandLine]
0x18005220d  mov     [rbp+220h+CommandLine], r14w
0x180052215  mov     rcx, rsi; Process
0x180052218  mov     qword ptr [rsp+320h+dwCreationFlags], rax; wchar_t *
0x18005221d  movups  xmmword ptr [rbp+220h+ProcessInformation.hProcess], xmm0
0x180052221  mov     [rbp+220h+StartupInfo.cb], 70h ; 'p'
0x180052228  mov     [rbp+220h+StartupInfo.dwFlags], edi
0x18005222b  mov     [rbp+220h+StartupInfo.wShowWindow], r14w
0x180052230  call    ?GetCrashVerticalPaths@@YAJPEAX00PEA_WK1K1K@Z; GetCrashVerticalPaths(void *,void *,void *,wchar_t *,ulong,wchar_t *,ulong,wchar_t *,ulong)
0x180052235  mov     ebx, eax
0x180052237  test    eax, eax
0x180052239  jns     short loc_18005226F
0x18005223b  mov     r9, gs:40h
0x180052244  lea     r8, aWerReportfault_20; "WER/ReportFault/%u:%u: ERROR Failed to "...
0x18005224b  mov     [rsp+320h+dwCreationFlags], eax
0x18005224f  xor     edx, edx; Level
0x180052251  mov     ecx, 96h; ComponentId
0x180052256  mov     [rsp+320h+bInheritHandles], 26Dh
0x18005225e  call    cs:__imp_DbgPrintEx
0x180052265  nop     dword ptr [rax+rax+00h]
0x18005226a  jmp     loc_18005255F
0x18005226f  mov     rcx, rsi; ProcessHandle
0x180052272  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x180052277  neg     eax
0x180052279  mov     ecx, edi; uMode
0x18005227b  sbb     r15d, r15d
0x18005227e  and     r15d, 40000h
0x180052285  call    cs:__imp_SetErrorMode
0x18005228c  nop     dword ptr [rax+rax+00h]
0x180052291  lea     rdx, [rsp+320h+OldMode]; lpOldMode
0x180052296  mov     ecx, edi; dwNewMode
0x180052298  mov     [rsp+320h+uMode], eax
0x18005229c  call    cs:__imp_SetThreadErrorMode
0x1800522a3  nop     dword ptr [rax+rax+00h]
0x1800522a8  call    cs:__imp_RtlGetCurrentTransaction
0x1800522af  nop     dword ptr [rax+rax+00h]
0x1800522b4  xor     ecx, ecx
0x1800522b6  mov     r13, rax
0x1800522b9  call    cs:__imp_RtlSetCurrentTransaction
0x1800522c0  nop     dword ptr [rax+rax+00h]
0x1800522c5  mov     edi, r14d
0x1800522c8  mov     esi, 96h
0x1800522cd  cmp     edi, 3
0x1800522d0  jnb     loc_18005250B
0x1800522d6  mov     ecx, edi
0x1800522d8  test    edi, edi
0x1800522da  jz      short loc_180052300
0x1800522dc  sub     ecx, 1
0x1800522df  jz      short loc_1800522F1
0x1800522e1  cmp     ecx, 1
0x1800522e4  jnz     loc_1800524B4
0x1800522ea  mov     [rsp+320h+var_2C8], r14d
0x1800522ef  jmp     short loc_180052308
0x1800522f1  mov     [rsp+320h+var_2C8], r14d
0x1800522f6  mov     r14d, r15d
0x1800522f9  bts     r14d, 18h
0x1800522fe  jmp     short loc_18005230B
0x180052300  mov     [rsp+320h+var_2C8], 4
0x180052308  mov     r14d, r15d
0x18005230b  xor     eax, eax
0x18005230d  lea     r8, [rsp+320h+var_2CC]; unsigned __int16 *
0x180052312  lea     rdx, [rsp+320h+var_2D0]; unsigned __int16 *
0x180052317  mov     [rsp+320h+var_2D0], ax
0x18005231c  or      rcx, 0FFFFFFFFFFFFFFFFh; void *
0x180052320  mov     [rsp+320h+var_2CC], ax
0x180052325  call    ?WerpGetProcessArchitecture@@YAJPEAXPEAG1@Z; WerpGetProcessArchitecture(void *,ushort *,ushort *)
0x18005232a  mov     eax, 0AA64h
0x18005232f  cmp     [rsp+320h+var_2CC], ax
0x180052334  jnz     short loc_180052342
0x180052336  mov     eax, 8664h
0x18005233b  cmp     [rsp+320h+var_2D0], ax
0x180052340  jz      short loc_180052349
0x180052342  xor     eax, eax
0x180052344  mov     [rsp+320h+var_2D0], ax
0x180052349  lea     rax, [rsp+320h+var_2D0]
0x18005234e  mov     [rsp+320h+lpAddress], 0
0x180052357  mov     [rsp+320h+lpEnvironment], rax
0x18005235c  lea     r8, [rsp+320h+var_2C8]
0x180052361  lea     rax, [rsp+320h+var_2B4]
0x180052366  mov     r9, r12
0x180052369  mov     qword ptr [rsp+320h+dwCreationFlags], rax
0x18005236e  lea     rcx, [rsp+320h+lpAddress]
0x180052373  mov     eax, [rsp+320h+var_2B0]
0x180052377  mov     [rsp+320h+bInheritHandles], eax
0x18005237b  call    ?WerpBuildCreateProcessAttributeList@@YAJPEAV?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@PEAPEAXPEAK1K2PEAG@Z; WerpBuildCreateProcessAttributeList(utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>> *,void * *,ulong *,void * *,ulong,ulong *,ushort *)
0x180052380  mov     ebx, eax
0x180052382  test    eax, eax
0x180052384  js      loc_180052585
0x18005238a  mov     r12, [rsp+320h+lpAddress]
0x18005238f  lea     rdx, [rbp+220h+CommandLine]; lpCommandLine
0x180052396  mov     rax, r12
0x180052399  mov     [rbp+220h+var_218], r12
0x18005239d  neg     rax
0x1800523a0  lea     rax, [rbp+220h+ProcessInformation]
0x1800523a4  mov     [rsp+320h+lpProcessInformation], rax; lpProcessInformation
0x1800523a9  sbb     ecx, ecx
0x1800523ab  and     ecx, 80000h
0x1800523b1  lea     rax, [rbp+220h+StartupInfo]
0x1800523b5  mov     [rsp+320h+lpStartupInfo], rax; lpStartupInfo
0x1800523ba  or      ecx, r14d
0x1800523bd  lea     rax, [rbp+220h+CurrentDirectory]
0x1800523c1  xor     r14d, r14d
0x1800523c4  mov     [rsp+320h+lpCurrentDirectory], rax; lpCurrentDirectory
0x1800523c9  xor     r9d, r9d; lpThreadAttributes
0x1800523cc  mov     [rsp+320h+lpEnvironment], r14; lpEnvironment
0x1800523d1  xor     r8d, r8d; lpProcessAttributes
0x1800523d4  mov     [rsp+320h+dwCreationFlags], ecx; dwCreationFlags
0x1800523d8  lea     rcx, [rbp+220h+ApplicationName]; lpApplicationName
0x1800523dc  mov     [rsp+320h+bInheritHandles], 1; bInheritHandles
0x1800523e4  call    cs:__imp_CreateProcessW
0x1800523eb  nop     dword ptr [rax+rax+00h]
0x1800523f0  test    eax, eax
0x1800523f2  jnz     loc_180052501
0x1800523f8  call    WerpGetLastError
0x1800523fd  mov     ebx, eax
0x1800523ff  test    edi, edi
0x180052401  jnz     short loc_180052460
0x180052403  mov     eax, 522h
0x180052408  cmp     ebx, eax
0x18005240a  jnz     loc_1800524BB
0x180052410  mov     r9, gs:40h
0x180052419  lea     r8, aWerReportfault_21; "WER/ReportFault/%u:%u: WARNING CreatePr"...
0x180052420  mov     dword ptr [rsp+320h+lpEnvironment], eax
0x180052424  lea     edx, [rdi+1]; Level
0x180052427  mov     [rsp+320h+dwCreationFlags], r14d
0x18005242c  mov     ecx, esi; ComponentId
0x18005242e  mov     [rsp+320h+bInheritHandles], 2DCh
0x180052436  call    cs:__imp_DbgPrintEx
0x18005243d  nop     dword ptr [rax+rax+00h]
0x180052442  test    r12, r12
0x180052445  jz      short loc_1800524A8
0x180052447  xor     edx, edx; dwSize
0x180052449  mov     r8d, 8000h; dwFreeType
0x18005244f  mov     rcx, r12; lpAddress
0x180052452  call    cs:__imp_VirtualFree
0x180052459  nop     dword ptr [rax+rax+00h]
0x18005245e  jmp     short loc_1800524A8
0x180052460  mov     eax, 1
0x180052465  cmp     edi, eax
0x180052467  jnz     short loc_1800524BB
0x180052469  cmp     ebx, 5
0x18005246c  jnz     short loc_1800524BB
0x18005246e  mov     r9, gs:40h
0x180052477  lea     r8, aWerReportfault_21; "WER/ReportFault/%u:%u: WARNING CreatePr"...
0x18005247e  mov     dword ptr [rsp+320h+lpEnvironment], ebx
0x180052482  mov     edx, eax; Level
0x180052484  mov     [rsp+320h+dwCreationFlags], eax
0x180052488  mov     ecx, esi; ComponentId
0x18005248a  mov     [rsp+320h+bInheritHandles], 2E2h
0x180052492  call    cs:__imp_DbgPrintEx
0x180052499  nop     dword ptr [rax+rax+00h]
0x18005249e  lea     rcx, [rsp+320h+lpAddress]
0x1800524a3  call    ??1?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(void)
0x1800524a8  mov     r12, [rsp+320h+var_2A8]
0x1800524ad  inc     edi
0x1800524af  jmp     loc_1800522CD
0x1800524b4  mov     ebx, 80004005h
0x1800524b9  jmp     short loc_180052529
0x1800524bb  mov     r9, gs:40h
0x1800524c4  lea     r8, aWerReportfault_5; "WER/ReportFault/%u:%u: ERROR CreateProc"...
0x1800524cb  mov     dword ptr [rsp+320h+lpEnvironment], ebx
0x1800524cf  xor     edx, edx; Level
0x1800524d1  mov     [rsp+320h+dwCreationFlags], edi
0x1800524d5  mov     ecx, esi; ComponentId
0x1800524d7  mov     [rsp+320h+bInheritHandles], 2E7h
0x1800524df  call    cs:__imp_DbgPrintEx
0x1800524e6  nop     dword ptr [rax+rax+00h]
0x1800524eb  test    ebx, ebx
0x1800524ed  jle     loc_1800525B1
0x1800524f3  movzx   ebx, bx
0x1800524f6  or      ebx, 80070000h
0x1800524fc  jmp     loc_1800525B1
0x180052501  lea     rcx, [rsp+320h+lpAddress]
0x180052506  call    ??1?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(void)
0x18005250b  mov     rcx, [rbp+220h+var_2A0]
0x18005250f  mov     rax, [rbp+220h+ProcessInformation.hProcess]
0x180052513  mov     [rcx], rax
0x180052516  mov     rcx, [rbp+220h+ProcessInformation.hThread]; Handle
0x18005251a  call    cs:__imp_NtClose
0x180052521  nop     dword ptr [rax+rax+00h]
0x180052526  mov     ebx, r14d
0x180052529  mov     ecx, [rsp+320h+uMode]; uMode
0x18005252d  call    cs:__imp_SetErrorMode
0x180052534  nop     dword ptr [rax+rax+00h]
0x180052539  mov     ecx, [rsp+320h+OldMode]; dwNewMode
0x18005253d  xor     edx, edx; lpOldMode
0x18005253f  call    cs:__imp_SetThreadErrorMode
0x180052546  nop     dword ptr [rax+rax+00h]
0x18005254b  test    r13, r13
0x18005254e  jz      short loc_18005255F
0x180052550  mov     rcx, r13
0x180052553  call    cs:__imp_RtlSetCurrentTransaction
0x18005255a  nop     dword ptr [rax+rax+00h]
0x18005255f  mov     eax, ebx
0x180052561  mov     rcx, [rbp+220h+var_50]
0x180052568  xor     rcx, rsp; StackCookie
0x18005256b  call    __security_check_cookie
0x180052570  add     rsp, 2E8h
0x180052577  pop     r15
0x180052579  pop     r14
0x18005257b  pop     r13
0x18005257d  pop     r12
0x18005257f  pop     rdi
0x180052580  pop     rsi
0x180052581  pop     rbx
0x180052582  pop     rbp
0x180052583  retn
0x180052585  mov     r9, gs:40h
0x18005258e  lea     r8, aWerReportfault_10; "WER/ReportFault/%u:%u: ERROR WerpBuildC"...
0x180052595  mov     [rsp+320h+dwCreationFlags], eax
0x180052599  xor     edx, edx; Level
0x18005259b  mov     ecx, esi; ComponentId
0x18005259d  mov     [rsp+320h+bInheritHandles], 2BFh
0x1800525a5  call    cs:__imp_DbgPrintEx
0x1800525ac  nop     dword ptr [rax+rax+00h]
0x1800525b1  lea     rcx, [rsp+320h+lpAddress]
0x1800525b6  call    ??1?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(void)
0x1800525bb  jmp     loc_180052529
```

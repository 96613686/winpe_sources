# StartCrashVertical

- ea: `0x180041bdc`
- end: `0x180041ff8`
- name: `StartCrashVertical`
- size: `1052`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, HANDLE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180042690`

## callees

- `0x180002890`
- `0x180003474`
- `0x180003617`
- `0x180004e5d`
- `0x180004e69`
- `0x18001bfb0`
- `0x1800419b8`
- `0x180041bdc`
- `0x180042000`
- `0x1800424dc`
- `0x180042504`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180041c7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180041cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180041d66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180041c7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180041cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180041d66`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180041e3a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180041e3a`
- `ntdll!RtlSetCurrentTransaction` at `0x180041d1c`
- `ntdll!RtlSetCurrentTransaction` at `0x180041fcf`
- `ntdll!RtlSetCurrentTransaction` at `0x180041d1c`
- `ntdll!RtlSetCurrentTransaction` at `0x180041fcf`
- `ntdll!RtlGetCurrentTransaction` at `0x180041d11`
- `ntdll!RtlGetCurrentTransaction` at `0x180041d11`
- `ntdll!DbgPrintEx` at `0x180041cd0`
- `ntdll!DbgPrintEx` at `0x180041e88`
- `ntdll!DbgPrintEx` at `0x180041ee2`
- `ntdll!DbgPrintEx` at `0x180041f26`
- `ntdll!DbgPrintEx` at `0x180041f95`
- `ntdll!DbgPrintEx` at `0x180041cd0`
- `ntdll!DbgPrintEx` at `0x180041e88`
- `ntdll!DbgPrintEx` at `0x180041ee2`
- `ntdll!DbgPrintEx` at `0x180041f26`
- `ntdll!DbgPrintEx` at `0x180041f95`
- `ntdll!NtClose` at `0x180041f68`
- `ntdll!NtClose` at `0x180041f68`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180041e9e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180041f53`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180041fad`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180041e9e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180041f53`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180041fad`

## string_xrefs

- `0x180041cba`: `WER/ReportFault/%u:%u: ERROR Failed to get the paths for the crash vertical: HRESULT %08X.\n`
- `0x180041f7f`: `WER/ReportFault/%u:%u: ERROR WerpBuildCreateProcessAttributeList failed, HRESULT %08X.\n`
- `0x180041e67`: `WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n`
- `0x180041ec3`: `WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n`
- `0x180041f09`: `WER/ReportFault/%u:%u: ERROR CreateProcess/mode%u failed with Win32 error %u.\n`

## pseudocode

```c
__int64 __fastcall StartCrashVertical(void *a1, void *a2, unsigned int a3, HANDLE *a4)
{
  void *v4; // rsi
  HANDLE CurrentProcess; // rax
  int CrashVerticalPaths; // ebx
  DWORD CurrentProcessId_0; // eax
  HANDLE v10; // rax
  int v11; // r12d
  __int64 CurrentTransaction; // r13
  int v13; // edi
  int v14; // r15d
  HANDLE v15; // rax
  void *v16; // rsi
  int LastError; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  void *v21; // rcx
  DWORD v22; // eax
  __int16 bInheritHandles; // [rsp+20h] [rbp-E0h]
  unsigned int lpEnvironment; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v26[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v27; // [rsp+54h] [rbp-ACh] BYREF
  int v28; // [rsp+58h] [rbp-A8h] BYREF
  DWORD OldMode; // [rsp+5Ch] [rbp-A4h] BYREF
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-9Ch]
  UINT uMode; // [rsp+68h] [rbp-98h]
  void *v33; // [rsp+70h] [rbp-90h]
  LPVOID lpAddress; // [rsp+78h] [rbp-88h] BYREF
  HANDLE *v35; // [rsp+80h] [rbp-80h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+88h] [rbp-78h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v38; // [rsp+108h] [rbp+8h]
  WCHAR CurrentDirectory[32]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR ApplicationName[64]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR CommandLine[128]; // [rsp+1D0h] [rbp+D0h] BYREF

  v31 = a3;
  v4 = a2;
  v33 = a2;
  v35 = a4;
  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  v30 = 2;
  OldMode = 0;
  v28 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  *a4 = 0;
  CurrentDirectory[0] = 0;
  ApplicationName[0] = 0;
  CommandLine[0] = 0;
  StartupInfo.cb = 112;
  StartupInfo.dwFlags = 1;
  StartupInfo.wShowWindow = 0;
  CurrentProcess = GetCurrentProcess();
  CrashVerticalPaths = GetCrashVerticalPaths(
                         CurrentProcess,
                         0,
                         a1,
                         ApplicationName,
                         bInheritHandles,
                         CommandLine,
                         lpEnvironment,
                         CurrentDirectory);
  if ( CrashVerticalPaths < 0 )
  {
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      0,
      "WER/ReportFault/%u:%u: ERROR Failed to get the paths for the crash vertical: HRESULT %08X.\n",
      CurrentProcessId_0,
      621,
      CrashVerticalPaths);
    return (unsigned int)CrashVerticalPaths;
  }
  v10 = GetCurrentProcess();
  v11 = (unsigned int)WerpIsProtectedProcess(v10) != 0 ? 0x40000 : 0;
  uMode = SetErrorMode_0(1u);
  SetThreadErrorMode_0(1u, &OldMode);
  CurrentTransaction = RtlGetCurrentTransaction();
  RtlSetCurrentTransaction(0);
  v13 = 0;
  while ( 1 )
  {
    if ( !v13 )
    {
      v28 = 4;
LABEL_10:
      v14 = v11;
      goto LABEL_11;
    }
    if ( v13 != 1 )
    {
      if ( v13 != 2 )
      {
        CrashVerticalPaths = -2147467259;
        goto LABEL_37;
      }
      v28 = 0;
      goto LABEL_10;
    }
    v28 = 0;
    v14 = v11 | 0x1000000;
LABEL_11:
    v26[0] = 0;
    v27 = 0;
    v15 = GetCurrentProcess();
    WerpGetProcessArchitecture(v15, v26, &v27);
    if ( v27 != 0xAA64 || v26[0] != 0x8664 )
      v26[0] = 0;
    lpAddress = 0;
    CrashVerticalPaths = WerpBuildCreateProcessAttributeList(&lpAddress, 0, &v28, v4, v31, &v30, v26);
    if ( CrashVerticalPaths < 0 )
    {
      v22 = GetCurrentProcessId_0();
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR WerpBuildCreateProcessAttributeList failed, HRESULT %08X.\n",
        v22,
        703,
        CrashVerticalPaths);
      v21 = lpAddress;
      if ( !lpAddress )
        goto LABEL_37;
      goto LABEL_36;
    }
    v16 = lpAddress;
    v38 = lpAddress;
    if ( CreateProcessW(
           ApplicationName,
           CommandLine,
           0,
           0,
           1,
           v14 | (lpAddress != 0 ? 0x80000 : 0),
           0,
           CurrentDirectory,
           &StartupInfo,
           &ProcessInformation) )
    {
      if ( v16 )
        VirtualFree(v16, 0, 0x8000u);
      *v35 = ProcessInformation.hProcess;
      NtClose(ProcessInformation.hThread);
      CrashVerticalPaths = 0;
      goto LABEL_37;
    }
    LastError = WerpGetLastError();
    CrashVerticalPaths = LastError;
    if ( !v13 )
    {
      if ( LastError != 1314 )
        break;
      v18 = GetCurrentProcessId_0();
      DbgPrintEx(
        0x96u,
        1u,
        "WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n",
        v18,
        732,
        0,
        CrashVerticalPaths);
      if ( v16 )
LABEL_19:
        VirtualFree(v16, 0, 0x8000u);
      ++v13;
      goto LABEL_21;
    }
    if ( v13 != 1 || LastError != 5 )
      break;
    v19 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n",
      v19,
      738,
      1,
      5);
    if ( v16 )
      goto LABEL_19;
    v13 = 2;
LABEL_21:
    v4 = v33;
  }
  v20 = GetCurrentProcessId_0();
  DbgPrintEx(
    0x96u,
    0,
    "WER/ReportFault/%u:%u: ERROR CreateProcess/mode%u failed with Win32 error %u.\n",
    v20,
    743,
    v13,
    CrashVerticalPaths);
  if ( CrashVerticalPaths > 0 )
    CrashVerticalPaths = (unsigned __int16)CrashVerticalPaths | 0x80070000;
  if ( v16 )
  {
    v21 = v16;
LABEL_36:
    VirtualFree(v21, 0, 0x8000u);
  }
LABEL_37:
  SetErrorMode_0(uMode);
  SetThreadErrorMode_0(OldMode, 0);
  if ( CurrentTransaction )
    RtlSetCurrentTransaction(CurrentTransaction);
  return (unsigned int)CrashVerticalPaths;
}

```

## disassembly

```asm
0x180041bdc  push    rbp
0x180041bde  push    rbx
0x180041bdf  push    rsi
0x180041be0  push    rdi
0x180041be1  push    r12
0x180041be3  push    r13
0x180041be5  push    r15
0x180041be7  lea     rbp, [rsp-1E0h]
0x180041bef  sub     rsp, 2E0h
0x180041bf6  mov     rax, cs:__security_cookie
0x180041bfd  xor     rax, rsp
0x180041c00  mov     [rbp+210h+var_40], rax
0x180041c07  xor     eax, eax
0x180041c09  mov     [rsp+310h+var_2AC], r8d
0x180041c0e  mov     rsi, rdx
0x180041c11  mov     [rsp+310h+var_2A0], rdx
0x180041c16  mov     rbx, rcx
0x180041c19  mov     [rbp+210h+var_290], r9
0x180041c1d  xor     edx, edx; Val
0x180041c1f  mov     dword ptr [rbp+210h+StartupInfo+4], eax
0x180041c22  lea     r8d, [rax+68h]; Size
0x180041c26  mov     rdi, r9
0x180041c29  lea     rcx, [rbp+210h+StartupInfo.lpReserved]; void *
0x180041c2d  call    memset_0
0x180041c32  xor     r15d, r15d
0x180041c35  mov     [rsp+310h+var_2B0], 2
0x180041c3d  xorps   xmm0, xmm0
0x180041c40  mov     [rsp+310h+OldMode], r15d
0x180041c45  xor     eax, eax
0x180041c47  mov     [rsp+310h+var_2B8], r15d
0x180041c4c  movups  xmmword ptr [rbp+210h+ProcessInformation.hProcess], xmm0
0x180041c50  mov     qword ptr [rbp+210h+ProcessInformation.dwProcessId], rax
0x180041c54  mov     [rdi], r15
0x180041c57  mov     [rbp+210h+CurrentDirectory], r15w
0x180041c5c  mov     [rbp+210h+ApplicationName], r15w
0x180041c61  mov     [rbp+210h+CommandLine], r15w
0x180041c69  mov     [rbp+210h+StartupInfo.cb], 70h ; 'p'
0x180041c70  mov     [rbp+210h+StartupInfo.dwFlags], 1
0x180041c77  mov     [rbp+210h+StartupInfo.wShowWindow], r15w
0x180041c7c  call    cs:__imp_GetCurrentProcess
0x180041c82  lea     r9, [rbp+210h+ApplicationName]; wchar_t *
0x180041c86  mov     r8, rbx; void *
0x180041c89  mov     rcx, rax; Process
0x180041c8c  xor     edx, edx; HANDLE
0x180041c8e  lea     rax, [rbp+210h+CurrentDirectory]
0x180041c92  mov     [rsp+310h+lpCurrentDirectory], rax; wchar_t *
0x180041c97  lea     rax, [rbp+210h+CommandLine]
0x180041c9e  mov     qword ptr [rsp+310h+dwCreationFlags], rax; wchar_t *
0x180041ca3  call    ?GetCrashVerticalPaths@@YAJPEAX00PEA_WK1K1K@Z; GetCrashVerticalPaths(void *,void *,void *,wchar_t *,ulong,wchar_t *,ulong,wchar_t *,ulong)
0x180041ca8  mov     ebx, eax
0x180041caa  test    eax, eax
0x180041cac  jns     short loc_180041CDB
0x180041cae  call    GetCurrentProcessId_0
0x180041cb3  mov     r9d, eax
0x180041cb6  mov     [rsp+310h+dwCreationFlags], ebx
0x180041cba  lea     r8, aWerReportfault_20; "WER/ReportFault/%u:%u: ERROR Failed to "...
0x180041cc1  mov     dword ptr [rsp+310h+bInheritHandles], 26Dh
0x180041cc9  xor     edx, edx; Level
0x180041ccb  mov     ecx, 96h; ComponentId
0x180041cd0  call    cs:__imp_DbgPrintEx
0x180041cd6  jmp     loc_180041FD5
0x180041cdb  call    cs:__imp_GetCurrentProcess
0x180041ce1  mov     rcx, rax; ProcessHandle
0x180041ce4  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x180041ce9  neg     eax
0x180041ceb  mov     ebx, 1
0x180041cf0  mov     ecx, ebx; uMode
0x180041cf2  sbb     r12d, r12d
0x180041cf5  and     r12d, 40000h
0x180041cfc  call    SetErrorMode_0
0x180041d01  lea     rdx, [rsp+310h+OldMode]; lpOldMode
0x180041d06  mov     [rsp+310h+uMode], eax
0x180041d0a  mov     ecx, ebx; dwNewMode
0x180041d0c  call    SetThreadErrorMode_0
0x180041d11  call    cs:__imp_RtlGetCurrentTransaction
0x180041d17  xor     ecx, ecx
0x180041d19  mov     r13, rax
0x180041d1c  call    cs:__imp_RtlSetCurrentTransaction
0x180041d22  mov     edi, r15d
0x180041d25  mov     ecx, edi
0x180041d27  test    edi, edi
0x180041d29  jz      short loc_180041D4F
0x180041d2b  sub     ecx, 1
0x180041d2e  jz      short loc_180041D40
0x180041d30  cmp     ecx, 1
0x180041d33  jnz     loc_180041EF6
0x180041d39  mov     [rsp+310h+var_2B8], r15d
0x180041d3e  jmp     short loc_180041D57
0x180041d40  mov     [rsp+310h+var_2B8], r15d
0x180041d45  mov     r15d, r12d
0x180041d48  bts     r15d, 18h
0x180041d4d  jmp     short loc_180041D5A
0x180041d4f  mov     [rsp+310h+var_2B8], 4
0x180041d57  mov     r15d, r12d
0x180041d5a  xor     eax, eax
0x180041d5c  mov     [rsp+310h+var_2C0], ax
0x180041d61  mov     [rsp+310h+var_2BC], ax
0x180041d66  call    cs:__imp_GetCurrentProcess
0x180041d6c  mov     rcx, rax; void *
0x180041d6f  lea     r8, [rsp+310h+var_2BC]; unsigned __int16 *
0x180041d74  lea     rdx, [rsp+310h+var_2C0]; unsigned __int16 *
0x180041d79  call    ?WerpGetProcessArchitecture@@YAJPEAXPEAG1@Z; WerpGetProcessArchitecture(void *,ushort *,ushort *)
0x180041d7e  mov     eax, 0AA64h
0x180041d83  cmp     [rsp+310h+var_2BC], ax
0x180041d88  jnz     short loc_180041D96
0x180041d8a  mov     eax, 8664h
0x180041d8f  cmp     [rsp+310h+var_2C0], ax
0x180041d94  jz      short loc_180041D9D
0x180041d96  xor     eax, eax
0x180041d98  mov     [rsp+310h+var_2C0], ax
0x180041d9d  lea     rax, [rsp+310h+var_2C0]
0x180041da2  mov     [rsp+310h+lpAddress], 0
0x180041dab  mov     [rsp+310h+lpEnvironment], rax
0x180041db0  lea     r8, [rsp+310h+var_2B8]
0x180041db5  lea     rax, [rsp+310h+var_2B0]
0x180041dba  mov     r9, rsi
0x180041dbd  mov     qword ptr [rsp+310h+dwCreationFlags], rax
0x180041dc2  lea     rcx, [rsp+310h+lpAddress]
0x180041dc7  mov     eax, [rsp+310h+var_2AC]
0x180041dcb  xor     edx, edx
0x180041dcd  mov     dword ptr [rsp+310h+bInheritHandles], eax
0x180041dd1  call    ?WerpBuildCreateProcessAttributeList@@YAJPEAV?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@PEAPEAXPEAK1K2PEAG@Z; WerpBuildCreateProcessAttributeList(utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>> *,void * *,ulong *,void * *,ulong,ulong *,ushort *)
0x180041dd6  mov     ebx, eax
0x180041dd8  test    eax, eax
0x180041dda  js      loc_180041F73
0x180041de0  mov     rsi, [rsp+310h+lpAddress]
0x180041de5  lea     rdx, [rbp+210h+CommandLine]; lpCommandLine
0x180041dec  mov     rax, rsi
0x180041def  mov     [rbp+210h+var_208], rsi
0x180041df3  neg     rax
0x180041df6  lea     rax, [rbp+210h+ProcessInformation]
0x180041dfa  mov     [rsp+310h+lpProcessInformation], rax; lpProcessInformation
0x180041dff  sbb     ecx, ecx
0x180041e01  and     ecx, 80000h
0x180041e07  lea     rax, [rbp+210h+StartupInfo]
0x180041e0b  mov     [rsp+310h+lpStartupInfo], rax; lpStartupInfo
0x180041e10  or      ecx, r15d
0x180041e13  lea     rax, [rbp+210h+CurrentDirectory]
0x180041e17  xor     r15d, r15d
0x180041e1a  mov     [rsp+310h+lpCurrentDirectory], rax; lpCurrentDirectory
0x180041e1f  xor     r9d, r9d; lpThreadAttributes
0x180041e22  mov     [rsp+310h+lpEnvironment], r15; lpEnvironment
0x180041e27  xor     r8d, r8d; lpProcessAttributes
0x180041e2a  mov     [rsp+310h+dwCreationFlags], ecx; dwCreationFlags
0x180041e2e  lea     rcx, [rbp+210h+ApplicationName]; lpApplicationName
0x180041e32  mov     dword ptr [rsp+310h+bInheritHandles], 1; bInheritHandles
0x180041e3a  call    cs:__imp_CreateProcessW
0x180041e40  test    eax, eax
0x180041e42  jnz     loc_180041F43
0x180041e48  call    WerpGetLastError
0x180041e4d  mov     ebx, eax
0x180041e4f  test    edi, edi
0x180041e51  jnz     short loc_180041EB0
0x180041e53  cmp     eax, 522h
0x180041e58  jnz     loc_180041F00
0x180041e5e  call    GetCurrentProcessId_0
0x180041e63  mov     dword ptr [rsp+310h+lpEnvironment], ebx
0x180041e67  lea     r8, aWerReportfault_21; "WER/ReportFault/%u:%u: WARNING CreatePr"...
0x180041e6e  lea     ebx, [rdi+1]
0x180041e71  mov     [rsp+310h+dwCreationFlags], r15d
0x180041e76  mov     edx, ebx; Level
0x180041e78  mov     dword ptr [rsp+310h+bInheritHandles], 2DCh
0x180041e80  mov     r9d, eax
0x180041e83  mov     ecx, 96h; ComponentId
0x180041e88  call    cs:__imp_DbgPrintEx
0x180041e8e  test    rsi, rsi
0x180041e91  jz      short loc_180041EA4
0x180041e93  xor     edx, edx; dwSize
0x180041e95  mov     r8d, 8000h; dwFreeType
0x180041e9b  mov     rcx, rsi; lpAddress
0x180041e9e  call    cs:__imp_VirtualFree
0x180041ea4  add     edi, ebx
0x180041ea6  mov     rsi, [rsp+310h+var_2A0]
0x180041eab  jmp     loc_180041D25
0x180041eb0  cmp     edi, 1
0x180041eb3  jnz     short loc_180041F00
0x180041eb5  cmp     ebx, 5
0x180041eb8  jnz     short loc_180041F00
0x180041eba  call    GetCurrentProcessId_0
0x180041ebf  mov     dword ptr [rsp+310h+lpEnvironment], ebx
0x180041ec3  lea     r8, aWerReportfault_21; "WER/ReportFault/%u:%u: WARNING CreatePr"...
0x180041eca  mov     ebx, edi
0x180041ecc  mov     r9d, eax
0x180041ecf  mov     [rsp+310h+dwCreationFlags], ebx
0x180041ed3  mov     edx, ebx; Level
0x180041ed5  mov     ecx, 96h; ComponentId
0x180041eda  mov     dword ptr [rsp+310h+bInheritHandles], 2E2h
0x180041ee2  call    cs:__imp_DbgPrintEx
0x180041ee8  test    rsi, rsi
0x180041eeb  jnz     short loc_180041E93
0x180041eed  add     edi, ebx
0x180041eef  cmp     edi, 3
0x180041ef2  jnb     short loc_180041F59
0x180041ef4  jmp     short loc_180041EA6
0x180041ef6  mov     ebx, 80004005h
0x180041efb  jmp     loc_180041FB3
0x180041f00  call    GetCurrentProcessId_0
0x180041f05  mov     dword ptr [rsp+310h+lpEnvironment], ebx
0x180041f09  lea     r8, aWerReportfault_5; "WER/ReportFault/%u:%u: ERROR CreateProc"...
0x180041f10  mov     r9d, eax
0x180041f13  mov     [rsp+310h+dwCreationFlags], edi
0x180041f17  xor     edx, edx; Level
0x180041f19  mov     dword ptr [rsp+310h+bInheritHandles], 2E7h
0x180041f21  mov     ecx, 96h; ComponentId
0x180041f26  call    cs:__imp_DbgPrintEx
0x180041f2c  test    ebx, ebx
0x180041f2e  jle     short loc_180041F39
0x180041f30  movzx   ebx, bx
0x180041f33  or      ebx, 80070000h
0x180041f39  test    rsi, rsi
0x180041f3c  jz      short loc_180041FB3
0x180041f3e  mov     rcx, rsi
0x180041f41  jmp     short loc_180041FA5
0x180041f43  test    rsi, rsi
0x180041f46  jz      short loc_180041F59
0x180041f48  xor     edx, edx; dwSize
0x180041f4a  mov     r8d, 8000h; dwFreeType
0x180041f50  mov     rcx, rsi; lpAddress
0x180041f53  call    cs:__imp_VirtualFree
0x180041f59  mov     rcx, [rbp+210h+var_290]
0x180041f5d  mov     rax, [rbp+210h+ProcessInformation.hProcess]
0x180041f61  mov     [rcx], rax
0x180041f64  mov     rcx, [rbp+210h+ProcessInformation.hThread]; Handle
0x180041f68  call    cs:__imp_NtClose
0x180041f6e  mov     ebx, r15d
0x180041f71  jmp     short loc_180041FB3
0x180041f73  call    GetCurrentProcessId_0
0x180041f78  mov     r9d, eax
0x180041f7b  mov     [rsp+310h+dwCreationFlags], ebx
0x180041f7f  lea     r8, aWerReportfault_10; "WER/ReportFault/%u:%u: ERROR WerpBuildC"...
0x180041f86  mov     dword ptr [rsp+310h+bInheritHandles], 2BFh
0x180041f8e  xor     edx, edx; Level
0x180041f90  mov     ecx, 96h; ComponentId
0x180041f95  call    cs:__imp_DbgPrintEx
0x180041f9b  mov     rcx, [rsp+310h+lpAddress]; lpAddress
0x180041fa0  test    rcx, rcx
0x180041fa3  jz      short loc_180041FB3
0x180041fa5  mov     r8d, 8000h; dwFreeType
0x180041fab  xor     edx, edx; dwSize
0x180041fad  call    cs:__imp_VirtualFree
0x180041fb3  mov     ecx, [rsp+310h+uMode]; uMode
0x180041fb7  call    SetErrorMode_0
0x180041fbc  mov     ecx, [rsp+310h+OldMode]; dwNewMode
0x180041fc0  xor     edx, edx; lpOldMode
0x180041fc2  call    SetThreadErrorMode_0
0x180041fc7  test    r13, r13
0x180041fca  jz      short loc_180041FD5
0x180041fcc  mov     rcx, r13
0x180041fcf  call    cs:__imp_RtlSetCurrentTransaction
0x180041fd5  mov     eax, ebx
0x180041fd7  mov     rcx, [rbp+210h+var_40]
0x180041fde  xor     rcx, rsp; StackCookie
0x180041fe1  call    __security_check_cookie
0x180041fe6  add     rsp, 2E0h
0x180041fed  pop     r15
0x180041fef  pop     r13
0x180041ff1  pop     r12
0x180041ff3  pop     rdi
0x180041ff4  pop     rsi
0x180041ff5  pop     rbx
0x180041ff6  pop     rbp
0x180041ff7  retn
```

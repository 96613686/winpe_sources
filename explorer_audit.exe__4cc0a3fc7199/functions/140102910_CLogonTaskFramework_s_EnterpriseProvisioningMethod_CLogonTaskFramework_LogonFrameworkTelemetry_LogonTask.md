# CLogonTaskFramework::s_EnterpriseProvisioningMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x140102910`
- end: `0x140102c75`
- name: `?s_EnterpriseProvisioningMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `869`
- prototype: `static int(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140012074`
- `0x14001eba8`
- `0x14003588c`
- `0x140075164`
- `0x1400954e0`
- `0x14009943c`
- `0x140102910`
- `0x140102c7c`
- `0x140102d58`
- `0x1401040e0`
- `0x140104ce0`
- `0x140139bb0`
- `0x14015e358`
- `0x140185e18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x140102a33`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x140102a33`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140102b65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140102b65`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1401029d7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1401029d7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140102b9e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140102b9e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140102b1c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140102b1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140102993`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140102993`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x1401029cd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x1401029cd`

## string_xrefs

- `0x140102a72`: `shell\lib\logontasks\logontasks.cpp`
- `0x140102aa6`: `shell\lib\logontasks\logontasks.cpp`
- `0x140102b2f`: `shell\lib\logontasks\logontasks.cpp`
- `0x140102bba`: `shell\lib\logontasks\logontasks.cpp`
- `0x140102c2d`: `shell\lib\logontasks\logontasks.cpp`
- `0x140102a83`: ` /source LogonTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLogonTaskFramework::s_EnterpriseProvisioningMethod(
        struct CLogonTaskFramework *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2)
{
  int PathInSystemDirectory; // eax
  wil::details::in1diag3 *v5; // rcx
  __int64 v6; // rdx
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  int v10; // eax
  unsigned int v11; // ebx
  BOOL v13; // ebx
  const char *v14; // r9
  HANDLE hProcess; // rbx
  DWORD v16; // esi
  __int64 v17; // rdx
  int v18; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v25[2]; // [rsp+5Ch] [rbp-A4h] BYREF
  HANDLE hThread; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v27; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR sz[264]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v31[264]; // [rsp+310h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+468h]

  if ( (*((_BYTE *)a1 + 216) & 1) == 0 )
    return 0;
  pvData = 0;
  pcbData = 4;
  RegGetValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Provisioning\\", L"UserPackages", 0x10u, 0, &pvData, &pcbData);
  if ( !pvData )
    return 0;
  PathInSystemDirectory = GetPathInSystemDirectory(L"provtool.exe", sz);
  v5 = retaddr;
  if ( PathInSystemDirectory < 0 )
  {
    v6 = 8018;
LABEL_14:
    wil::details::in1diag3::_Log_Hr(
      v5,
      (void *)v6,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)PathInSystemDirectory,
      pdwType);
    return 0;
  }
  PathQuoteSpacesW(sz);
  if ( GetFileAttributesW(sz) != -1 )
  {
    if ( *((_BYTE *)a1 + 237) )
      LogonFrameworkTelemetry::LogonTask::EnterpriseProvisioning(a2);
    PathInSystemDirectory = StringCchCatW(sz, 0x104u, L" /turn ");
    v5 = retaddr;
    if ( PathInSystemDirectory < 0 )
    {
      v6 = 8030;
      goto LABEL_14;
    }
    if ( (unsigned int)_o__itow_s(4, v25, 2) )
    {
      wil::details::in1diag3::Log_Win32(retaddr, v7, v8, v9, pdwType);
    }
    else
    {
      PathInSystemDirectory = StringCchCatW(sz, 0x104u, v25);
      v5 = retaddr;
      if ( PathInSystemDirectory < 0 )
      {
        v6 = 8040;
        goto LABEL_14;
      }
      v10 = StringCchCatW(sz, 0x104u, L" /source LogonTask");
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F6B,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v10,
          pdwType);
        return v11;
      }
      memset_0(&StartupInfo, 0, sizeof(StartupInfo));
      memset(&ProcessInformation, 0, sizeof(ProcessInformation));
      v13 = CreateProcessW(0, sz, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation);
      if ( !v13 )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x1F71,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          v14);
      if ( v13 )
      {
        hProcess = ProcessInformation.hProcess;
        v27 = ProcessInformation.hProcess;
        hThread = ProcessInformation.hThread;
        v16 = WaitForSingleObject(ProcessInformation.hProcess, 0x2BF20u);
        ExitCode = v16;
        if ( *((_BYTE *)a1 + 237) )
          LogonFrameworkTelemetry::LogonTask::WaitResult<unsigned short const (&)[23],unsigned long &>(
            a2,
            L"enterpriseProvisioning",
            &ExitCode);
        if ( !v16 )
        {
          ExitCode = 0;
          if ( GetExitCodeProcess(hProcess, &ExitCode) && (ExitCode & 0x80000000) != 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1F86,
              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
              (const char *)ExitCode,
              pdwTypea);
        }
        if ( (int)SHRegGetStringEx(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Provisioning\\AppLaunchId",
                    0,
                    2,
                    v31,
                    0x104u) >= 0 )
        {
          v18 = ActivateApplicationForLaunch(v31, v17, v31, 2);
          if ( v18 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1F8F,
              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
              (const char *)(unsigned int)v18,
              pdwTypeb);
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v27);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140102910  push    rbp
0x140102912  push    rbx
0x140102913  push    rsi
0x140102914  push    rdi
0x140102915  push    r12
0x140102917  push    r14
0x140102919  lea     rbp, [rsp-438h]
0x140102921  sub     rsp, 538h
0x140102928  mov     rax, cs:__security_cookie
0x14010292f  xor     rax, rsp
0x140102932  mov     [rbp+460h+var_40], rax
0x140102939  mov     r14, rdx
0x14010293c  mov     rdi, rcx
0x14010293f  test    byte ptr [rcx+0D8h], 1
0x140102946  jz      loc_140102C54
0x14010294c  mov     [rsp+560h+var_50C], 0
0x140102954  mov     ebx, 4
0x140102959  mov     [rsp+560h+var_508], ebx
0x14010295d  lea     rax, [rsp+560h+var_508]
0x140102962  mov     [rsp+560h+pcbData], rax; pcbData
0x140102967  lea     rax, [rsp+560h+var_50C]
0x14010296c  mov     [rsp+560h+pvData], rax; pvData
0x140102971  mov     [rsp+560h+pdwType], 0; int
0x14010297a  lea     r9d, [rbx+0Ch]; dwFlags
0x14010297e  lea     r8, aUserpackages; "UserPackages"
0x140102985  lea     rdx, aSoftwareMicros_81; "SOFTWARE\\Microsoft\\Provisioning\\"
0x14010298c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140102993  call    cs:__imp_RegGetValueW
0x140102999  cmp     [rsp+560h+var_50C], 0
0x14010299e  jz      loc_140102C54
0x1401029a4  lea     rdx, [rbp+460h+sz]; pszPath
0x1401029a8  lea     rcx, aProvtoolExe; "provtool.exe"
0x1401029af  call    GetPathInSystemDirectory
0x1401029b4  mov     rcx, [rbp+468h]
0x1401029bb  test    eax, eax
0x1401029bd  jns     short loc_1401029C9
0x1401029bf  mov     edx, 1F52h
0x1401029c4  jmp     loc_140102A6F
0x1401029c9  lea     rcx, [rbp+460h+sz]; lpsz
0x1401029cd  call    cs:__imp_PathQuoteSpacesW
0x1401029d3  lea     rcx, [rbp+460h+sz]; lpFileName
0x1401029d7  call    cs:__imp_GetFileAttributesW
0x1401029dd  cmp     eax, 0FFFFFFFFh
0x1401029e0  jz      loc_140102C54
0x1401029e6  cmp     byte ptr [rdi+0EDh], 0
0x1401029ed  jz      short loc_1401029F7
0x1401029ef  mov     rcx, r14; this
0x1401029f2  call    ?EnterpriseProvisioning@LogonTask@LogonFrameworkTelemetry@@QEAAXXZ; LogonFrameworkTelemetry::LogonTask::EnterpriseProvisioning(void)
0x1401029f7  lea     r8, aTurn; " /turn "
0x1401029fe  mov     r12d, 104h
0x140102a04  mov     edx, r12d; unsigned __int64
0x140102a07  lea     rcx, [rbp+460h+sz]; unsigned __int16 *
0x140102a0b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140102a10  mov     rcx, [rbp+468h]
0x140102a17  test    eax, eax
0x140102a19  jns     short loc_140102A22
0x140102a1b  mov     edx, 1F5Eh
0x140102a20  jmp     short loc_140102A6F
0x140102a22  mov     r9d, 0Ah
0x140102a28  lea     r8d, [r9-8]
0x140102a2c  lea     rdx, [rsp+560h+var_504]
0x140102a31  mov     ecx, ebx
0x140102a33  call    cs:__imp__o__itow_s
0x140102a39  test    eax, eax
0x140102a3b  jz      short loc_140102A4E
0x140102a3d  mov     rcx, [rbp+468h]; this
0x140102a44  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x140102a49  jmp     loc_140102C54
0x140102a4e  lea     r8, [rsp+560h+var_504]; unsigned __int16 *
0x140102a53  mov     rdx, r12; unsigned __int64
0x140102a56  lea     rcx, [rbp+460h+sz]; unsigned __int16 *
0x140102a5a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140102a5f  mov     rcx, [rbp+468h]; this
0x140102a66  test    eax, eax
0x140102a68  jns     short loc_140102A83
0x140102a6a  mov     edx, 1F68h; void *
0x140102a6f  mov     r9d, eax; char *
0x140102a72  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140102a79  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140102a7e  jmp     loc_140102C54
0x140102a83  lea     r8, aSourceLogontas; " /source LogonTask"
0x140102a8a  mov     rdx, r12; unsigned __int64
0x140102a8d  lea     rcx, [rbp+460h+sz]; unsigned __int16 *
0x140102a91  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140102a96  mov     ebx, eax
0x140102a98  test    eax, eax
0x140102a9a  jns     short loc_140102ABE
0x140102a9c  mov     rcx, [rbp+468h]; this
0x140102aa3  mov     r9d, eax; char *
0x140102aa6  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140102aad  mov     edx, 1F6Bh; void *
0x140102ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140102ab7  mov     eax, ebx
0x140102ab9  jmp     loc_140102C56
0x140102abe  xor     edx, edx; Val
0x140102ac0  lea     r8d, [rdx+68h]; Size
0x140102ac4  lea     rcx, [rbp+460h+StartupInfo]; void *
0x140102ac8  call    memset_0
0x140102acd  xorps   xmm0, xmm0
0x140102ad0  xor     eax, eax
0x140102ad2  movups  xmmword ptr [rsp+560h+ProcessInformation.hProcess], xmm0
0x140102ad7  mov     qword ptr [rbp+460h+ProcessInformation.dwProcessId], rax
0x140102adb  lea     rax, [rsp+560h+ProcessInformation]
0x140102ae0  mov     [rsp+560h+lpProcessInformation], rax; lpProcessInformation
0x140102ae5  lea     rax, [rbp+460h+StartupInfo]
0x140102ae9  mov     [rsp+560h+lpStartupInfo], rax; lpStartupInfo
0x140102aee  mov     [rsp+560h+lpCurrentDirectory], 0; lpCurrentDirectory
0x140102af7  mov     [rsp+560h+pcbData], 0; lpEnvironment
0x140102b00  mov     dword ptr [rsp+560h+pvData], 0; dwCreationFlags
0x140102b08  mov     dword ptr [rsp+560h+pdwType], 0; int
0x140102b10  xor     r9d, r9d; lpThreadAttributes
0x140102b13  xor     r8d, r8d; lpProcessAttributes
0x140102b16  lea     rdx, [rbp+460h+sz]; lpCommandLine
0x140102b1a  xor     ecx, ecx; lpApplicationName
0x140102b1c  call    cs:__imp_CreateProcessW
0x140102b22  mov     ebx, eax
0x140102b24  mov     rcx, [rbp+468h]; this
0x140102b2b  test    eax, eax
0x140102b2d  jnz     short loc_140102B40
0x140102b2f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140102b36  mov     edx, 1F71h; void *
0x140102b3b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140102b40  cmp     ebx, 1
0x140102b43  jnz     loc_140102C54
0x140102b49  mov     rbx, [rsp+560h+ProcessInformation.hProcess]
0x140102b4e  mov     [rsp+560h+var_4F8], rbx
0x140102b53  mov     rax, [rsp+560h+ProcessInformation.hThread]
0x140102b58  mov     [rsp+560h+var_500], rax
0x140102b5d  mov     edx, 2BF20h; dwMilliseconds
0x140102b62  mov     rcx, rbx; hHandle
0x140102b65  call    cs:__imp_WaitForSingleObject
0x140102b6b  mov     esi, eax
0x140102b6d  mov     [rsp+560h+ExitCode], eax
0x140102b71  cmp     byte ptr [rdi+0EDh], 0
0x140102b78  jz      short loc_140102B8E
0x140102b7a  lea     r8, [rsp+560h+ExitCode]
0x140102b7f  lea     rdx, aEnterpriseprov; "enterpriseProvisioning"
0x140102b86  mov     rcx, r14
0x140102b89  call    ??$WaitResult@AEAY0BH@$$CBGAEAK@LogonTask@LogonFrameworkTelemetry@@QEAAXAEAY0BH@$$CBGAEAK@Z; LogonFrameworkTelemetry::LogonTask::WaitResult<ushort const (&)[23],ulong &>(ushort const (&)[23],ulong &)
0x140102b8e  test    esi, esi
0x140102b90  jnz     short loc_140102BCB
0x140102b92  mov     [rsp+560h+ExitCode], esi
0x140102b96  lea     rdx, [rsp+560h+ExitCode]; lpExitCode
0x140102b9b  mov     rcx, rbx; hProcess
0x140102b9e  call    cs:__imp_GetExitCodeProcess
0x140102ba4  cmp     eax, 1
0x140102ba7  jnz     short loc_140102BCB
0x140102ba9  mov     r9d, [rsp+560h+ExitCode]; char *
0x140102bae  mov     rcx, [rbp+468h]; this
0x140102bb5  test    r9d, r9d
0x140102bb8  jns     short loc_140102BCB
0x140102bba  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140102bc1  mov     edx, 1F86h; void *
0x140102bc6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140102bcb  mov     dword ptr [rsp+560h+pvData], r12d; unsigned int
0x140102bd0  lea     rax, [rbp+460h+var_250]
0x140102bd7  mov     [rsp+560h+pdwType], rax; int
0x140102bdc  mov     r9d, 2; int
0x140102be2  xor     r8d, r8d; unsigned __int16 *
0x140102be5  lea     rdx, aSoftwareMicros_104; "SOFTWARE\\Microsoft\\Provisioning\\AppL"...
0x140102bec  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140102bf3  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x140102bf8  test    eax, eax
0x140102bfa  js      short loc_140102C3F
0x140102bfc  lea     rax, [rsp+560h+ExitCode]
0x140102c01  mov     [rsp+560h+pvData], rax
0x140102c06  mov     r9d, 2
0x140102c0c  lea     r8, [rbp+460h+var_250]
0x140102c13  lea     rcx, [rbp+460h+var_250]
0x140102c1a  call    ?ActivateApplicationForLaunch@@YAJPEBG00W4ACTIVATEOPTIONSINTERNAL@@PEAUHMONITOR__@@PEAK@Z; ActivateApplicationForLaunch(ushort const *,ushort const *,ushort const *,ACTIVATEOPTIONSINTERNAL,HMONITOR__ *,ulong *)
0x140102c1f  mov     rcx, [rbp+468h]; this
0x140102c26  test    eax, eax
0x140102c28  jns     short loc_140102C3F
0x140102c2a  mov     r9d, eax; char *
0x140102c2d  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140102c34  mov     edx, 1F8Fh; void *
0x140102c39  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140102c3e  nop
0x140102c3f  lea     rcx, [rsp+560h+var_500]
0x140102c44  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140102c49  nop
0x140102c4a  lea     rcx, [rsp+560h+var_4F8]
0x140102c4f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140102c54  xor     eax, eax
0x140102c56  mov     rcx, [rbp+460h+var_40]
0x140102c5d  xor     rcx, rsp; StackCookie
0x140102c60  call    __security_check_cookie
0x140102c65  add     rsp, 538h
0x140102c6c  pop     r14
0x140102c6e  pop     r12
0x140102c70  pop     rdi
0x140102c71  pop     rsi
0x140102c72  pop     rbx
0x140102c73  pop     rbp
0x140102c74  retn
```

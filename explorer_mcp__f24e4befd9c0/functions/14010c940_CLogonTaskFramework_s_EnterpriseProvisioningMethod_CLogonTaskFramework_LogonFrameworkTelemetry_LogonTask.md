# CLogonTaskFramework::s_EnterpriseProvisioningMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x14010c940`
- end: `0x14010ccd0`
- name: `?s_EnterpriseProvisioningMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `912`
- prototype: `static int(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x14001b2c8`
- `0x140021aac`
- `0x1400283bc`
- `0x140079cc8`
- `0x14009ac68`
- `0x14009ea84`
- `0x14010c940`
- `0x14010ccd8`
- `0x14010cdbc`
- `0x14010e160`
- `0x14010ed90`
- `0x140145dfc`
- `0x140168bfc`
- `0x140191f58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x14010ca75`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x14010ca75`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14010cbb3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14010cbb3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14010ca13`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14010ca13`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14010cb64`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14010cb64`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14010cbf2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14010cbf2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14010c9c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14010c9c3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x14010ca03`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x14010ca03`

## string_xrefs

- `0x14010caba`: `shell\lib\logontasks\logontasks.cpp`
- `0x14010caee`: `shell\lib\logontasks\logontasks.cpp`
- `0x14010cb7d`: `shell\lib\logontasks\logontasks.cpp`
- `0x14010cc14`: `shell\lib\logontasks\logontasks.cpp`
- `0x14010cc87`: `shell\lib\logontasks\logontasks.cpp`
- `0x14010cacb`: ` /source LogonTask`

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
    v6 = 8044;
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
      v6 = 8056;
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
        v6 = 8066;
        goto LABEL_14;
      }
      v10 = StringCchCatW(sz, 0x104u, L" /source LogonTask");
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F85,
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
          (void *)0x1F8B,
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
              (void *)0x1FA0,
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
              (void *)0x1FA9,
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
0x14010c940  push    rbp
0x14010c942  push    rbx
0x14010c943  push    rsi
0x14010c944  push    rdi
0x14010c945  push    r12
0x14010c947  push    r14
0x14010c949  lea     rbp, [rsp-438h]
0x14010c951  sub     rsp, 538h
0x14010c958  mov     rax, cs:__security_cookie
0x14010c95f  xor     rax, rsp
0x14010c962  mov     [rbp+460h+var_40], rax
0x14010c969  mov     r14, rdx
0x14010c96c  mov     rdi, rcx
0x14010c96f  test    byte ptr [rcx+0D8h], 1
0x14010c976  jz      loc_14010CCAE
0x14010c97c  mov     [rsp+560h+var_50C], 0
0x14010c984  mov     ebx, 4
0x14010c989  mov     [rsp+560h+var_508], ebx
0x14010c98d  lea     rax, [rsp+560h+var_508]
0x14010c992  mov     [rsp+560h+pcbData], rax; pcbData
0x14010c997  lea     rax, [rsp+560h+var_50C]
0x14010c99c  mov     [rsp+560h+pvData], rax; pvData
0x14010c9a1  mov     [rsp+560h+pdwType], 0; int
0x14010c9aa  lea     r9d, [rbx+0Ch]; dwFlags
0x14010c9ae  lea     r8, aUserpackages; "UserPackages"
0x14010c9b5  lea     rdx, aSoftwareMicros_81; "SOFTWARE\\Microsoft\\Provisioning\\"
0x14010c9bc  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14010c9c3  call    cs:__imp_RegGetValueW
0x14010c9ca  nop     dword ptr [rax+rax+00h]
0x14010c9cf  cmp     [rsp+560h+var_50C], 0
0x14010c9d4  jz      loc_14010CCAE
0x14010c9da  lea     rdx, [rbp+460h+sz]; pszPath
0x14010c9de  lea     rcx, aProvtoolExe; "provtool.exe"
0x14010c9e5  call    GetPathInSystemDirectory
0x14010c9ea  mov     rcx, [rbp+468h]
0x14010c9f1  test    eax, eax
0x14010c9f3  jns     short loc_14010C9FF
0x14010c9f5  mov     edx, 1F6Ch
0x14010c9fa  jmp     loc_14010CAB7
0x14010c9ff  lea     rcx, [rbp+460h+sz]; lpsz
0x14010ca03  call    cs:__imp_PathQuoteSpacesW
0x14010ca0a  nop     dword ptr [rax+rax+00h]
0x14010ca0f  lea     rcx, [rbp+460h+sz]; lpFileName
0x14010ca13  call    cs:__imp_GetFileAttributesW
0x14010ca1a  nop     dword ptr [rax+rax+00h]
0x14010ca1f  cmp     eax, 0FFFFFFFFh
0x14010ca22  jz      loc_14010CCAE
0x14010ca28  cmp     byte ptr [rdi+0EDh], 0
0x14010ca2f  jz      short loc_14010CA39
0x14010ca31  mov     rcx, r14; this
0x14010ca34  call    ?EnterpriseProvisioning@LogonTask@LogonFrameworkTelemetry@@QEAAXXZ; LogonFrameworkTelemetry::LogonTask::EnterpriseProvisioning(void)
0x14010ca39  lea     r8, aTurn; " /turn "
0x14010ca40  mov     r12d, 104h
0x14010ca46  mov     edx, r12d; unsigned __int64
0x14010ca49  lea     rcx, [rbp+460h+sz]; unsigned __int16 *
0x14010ca4d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14010ca52  mov     rcx, [rbp+468h]
0x14010ca59  test    eax, eax
0x14010ca5b  jns     short loc_14010CA64
0x14010ca5d  mov     edx, 1F78h
0x14010ca62  jmp     short loc_14010CAB7
0x14010ca64  mov     r9d, 0Ah
0x14010ca6a  lea     r8d, [r9-8]
0x14010ca6e  lea     rdx, [rsp+560h+var_504]
0x14010ca73  mov     ecx, ebx
0x14010ca75  call    cs:__imp__o__itow_s
0x14010ca7c  nop     dword ptr [rax+rax+00h]
0x14010ca81  test    eax, eax
0x14010ca83  jz      short loc_14010CA96
0x14010ca85  mov     rcx, [rbp+468h]; this
0x14010ca8c  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x14010ca91  jmp     loc_14010CCAE
0x14010ca96  lea     r8, [rsp+560h+var_504]; unsigned __int16 *
0x14010ca9b  mov     rdx, r12; unsigned __int64
0x14010ca9e  lea     rcx, [rbp+460h+sz]; unsigned __int16 *
0x14010caa2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14010caa7  mov     rcx, [rbp+468h]; this
0x14010caae  test    eax, eax
0x14010cab0  jns     short loc_14010CACB
0x14010cab2  mov     edx, 1F82h; void *
0x14010cab7  mov     r9d, eax; char *
0x14010caba  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14010cac1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14010cac6  jmp     loc_14010CCAE
0x14010cacb  lea     r8, aSourceLogontas; " /source LogonTask"
0x14010cad2  mov     rdx, r12; unsigned __int64
0x14010cad5  lea     rcx, [rbp+460h+sz]; unsigned __int16 *
0x14010cad9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14010cade  mov     ebx, eax
0x14010cae0  test    eax, eax
0x14010cae2  jns     short loc_14010CB06
0x14010cae4  mov     rcx, [rbp+468h]; this
0x14010caeb  mov     r9d, eax; char *
0x14010caee  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14010caf5  mov     edx, 1F85h; void *
0x14010cafa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14010caff  mov     eax, ebx
0x14010cb01  jmp     loc_14010CCB0
0x14010cb06  xor     edx, edx; Val
0x14010cb08  lea     r8d, [rdx+68h]; Size
0x14010cb0c  lea     rcx, [rbp+460h+StartupInfo]; void *
0x14010cb10  call    memset_0
0x14010cb15  xorps   xmm0, xmm0
0x14010cb18  xor     eax, eax
0x14010cb1a  movups  xmmword ptr [rsp+560h+ProcessInformation.hProcess], xmm0
0x14010cb1f  mov     qword ptr [rbp+460h+ProcessInformation.dwProcessId], rax
0x14010cb23  lea     rax, [rsp+560h+ProcessInformation]
0x14010cb28  mov     [rsp+560h+lpProcessInformation], rax; lpProcessInformation
0x14010cb2d  lea     rax, [rbp+460h+StartupInfo]
0x14010cb31  mov     [rsp+560h+lpStartupInfo], rax; lpStartupInfo
0x14010cb36  mov     [rsp+560h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14010cb3f  mov     [rsp+560h+pcbData], 0; lpEnvironment
0x14010cb48  mov     dword ptr [rsp+560h+pvData], 0; dwCreationFlags
0x14010cb50  mov     dword ptr [rsp+560h+pdwType], 0; int
0x14010cb58  xor     r9d, r9d; lpThreadAttributes
0x14010cb5b  xor     r8d, r8d; lpProcessAttributes
0x14010cb5e  lea     rdx, [rbp+460h+sz]; lpCommandLine
0x14010cb62  xor     ecx, ecx; lpApplicationName
0x14010cb64  call    cs:__imp_CreateProcessW
0x14010cb6b  nop     dword ptr [rax+rax+00h]
0x14010cb70  mov     ebx, eax
0x14010cb72  mov     rcx, [rbp+468h]; this
0x14010cb79  test    eax, eax
0x14010cb7b  jnz     short loc_14010CB8E
0x14010cb7d  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14010cb84  mov     edx, 1F8Bh; void *
0x14010cb89  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14010cb8e  cmp     ebx, 1
0x14010cb91  jnz     loc_14010CCAE
0x14010cb97  mov     rbx, [rsp+560h+ProcessInformation.hProcess]
0x14010cb9c  mov     [rsp+560h+var_4F8], rbx
0x14010cba1  mov     rax, [rsp+560h+ProcessInformation.hThread]
0x14010cba6  mov     [rsp+560h+var_500], rax
0x14010cbab  mov     edx, 2BF20h; dwMilliseconds
0x14010cbb0  mov     rcx, rbx; hHandle
0x14010cbb3  call    cs:__imp_WaitForSingleObject
0x14010cbba  nop     dword ptr [rax+rax+00h]
0x14010cbbf  mov     esi, eax
0x14010cbc1  mov     [rsp+560h+ExitCode], eax
0x14010cbc5  cmp     byte ptr [rdi+0EDh], 0
0x14010cbcc  jz      short loc_14010CBE2
0x14010cbce  lea     r8, [rsp+560h+ExitCode]
0x14010cbd3  lea     rdx, aEnterpriseprov; "enterpriseProvisioning"
0x14010cbda  mov     rcx, r14
0x14010cbdd  call    ??$WaitResult@AEAY0BH@$$CBGAEAK@LogonTask@LogonFrameworkTelemetry@@QEAAXAEAY0BH@$$CBGAEAK@Z; LogonFrameworkTelemetry::LogonTask::WaitResult<ushort const (&)[23],ulong &>(ushort const (&)[23],ulong &)
0x14010cbe2  test    esi, esi
0x14010cbe4  jnz     short loc_14010CC25
0x14010cbe6  mov     [rsp+560h+ExitCode], esi
0x14010cbea  lea     rdx, [rsp+560h+ExitCode]; lpExitCode
0x14010cbef  mov     rcx, rbx; hProcess
0x14010cbf2  call    cs:__imp_GetExitCodeProcess
0x14010cbf9  nop     dword ptr [rax+rax+00h]
0x14010cbfe  cmp     eax, 1
0x14010cc01  jnz     short loc_14010CC25
0x14010cc03  mov     r9d, [rsp+560h+ExitCode]; char *
0x14010cc08  mov     rcx, [rbp+468h]; this
0x14010cc0f  test    r9d, r9d
0x14010cc12  jns     short loc_14010CC25
0x14010cc14  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14010cc1b  mov     edx, 1FA0h; void *
0x14010cc20  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14010cc25  mov     dword ptr [rsp+560h+pvData], r12d; unsigned int
0x14010cc2a  lea     rax, [rbp+460h+var_250]
0x14010cc31  mov     [rsp+560h+pdwType], rax; int
0x14010cc36  mov     r9d, 2; int
0x14010cc3c  xor     r8d, r8d; unsigned __int16 *
0x14010cc3f  lea     rdx, aSoftwareMicros_104; "SOFTWARE\\Microsoft\\Provisioning\\AppL"...
0x14010cc46  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x14010cc4d  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x14010cc52  test    eax, eax
0x14010cc54  js      short loc_14010CC99
0x14010cc56  lea     rax, [rsp+560h+ExitCode]
0x14010cc5b  mov     [rsp+560h+pvData], rax
0x14010cc60  mov     r9d, 2
0x14010cc66  lea     r8, [rbp+460h+var_250]
0x14010cc6d  lea     rcx, [rbp+460h+var_250]
0x14010cc74  call    ?ActivateApplicationForLaunch@@YAJPEBG00W4ACTIVATEOPTIONSINTERNAL@@PEAUHMONITOR__@@PEAK@Z; ActivateApplicationForLaunch(ushort const *,ushort const *,ushort const *,ACTIVATEOPTIONSINTERNAL,HMONITOR__ *,ulong *)
0x14010cc79  mov     rcx, [rbp+468h]; this
0x14010cc80  test    eax, eax
0x14010cc82  jns     short loc_14010CC99
0x14010cc84  mov     r9d, eax; char *
0x14010cc87  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14010cc8e  mov     edx, 1FA9h; void *
0x14010cc93  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14010cc98  nop
0x14010cc99  lea     rcx, [rsp+560h+var_500]
0x14010cc9e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14010cca3  nop
0x14010cca4  lea     rcx, [rsp+560h+var_4F8]
0x14010cca9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14010ccae  xor     eax, eax
0x14010ccb0  mov     rcx, [rbp+460h+var_40]
0x14010ccb7  xor     rcx, rsp; StackCookie
0x14010ccba  call    __security_check_cookie
0x14010ccbf  add     rsp, 538h
0x14010ccc6  pop     r14
0x14010ccc8  pop     r12
0x14010ccca  pop     rdi
0x14010cccb  pop     rsi
0x14010cccc  pop     rbx
0x14010cccd  pop     rbp
0x14010ccce  retn
```

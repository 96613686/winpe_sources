# CLogonTaskFramework::s_RunPostAppInstallTasks(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *,bool)

- ea: `0x140025e1c`
- end: `0x14002631a`
- name: `?s_RunPostAppInstallTasks@CLogonTaskFramework@@CAXPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@_N@Z`
- size: `1278`
- prototype: `void __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14007a1d0`
- `0x1401a7bf0`

## callees

- `0x14001b2c8`
- `0x14001c330`
- `0x1400203a4`
- `0x140023118`
- `0x1400231f8`
- `0x140025e1c`
- `0x1400272e0`
- `0x140027ec0`
- `0x140066528`
- `0x140066ba0`
- `0x14008f52c`
- `0x1400baba8`
- `0x1400e1654`
- `0x14010e160`
- `0x140145cdc`
- `0x1401a0848`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140025fb3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140025fb3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002612a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002612a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002602e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400262bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002602e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400262bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026153`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026153`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14002629a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14002629a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140025f51`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140025f93`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140025f51`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140025f93`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140025f34`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140025f34`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140025f0c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140025f0c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140025f77`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140025f77`

## string_xrefs

- `0x140025ff6`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400261c5`: `shell\lib\logontasks\logontasks.cpp`
- `0x14002621f`: `shell\lib\logontasks\logontasks.cpp`
- `0x14002627c`: `shell\lib\logontasks\logontasks.cpp`
- `0x140025f03`: `ServicesActive`
- `0x140025f2a`: `AppReadiness`
- `0x1400260b8`: `OSData\Software\Microsoft\Windows\CurrentVersion\AppReadiness`
- `0x1400260bf`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness`
- `0x140025e7b`: `PostAppInstallTasksCompleted`
- `0x14002606c`: `PostAppInstallTasksCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CLogonTaskFramework::s_RunPostAppInstallTasks(
        struct CLogonTaskFramework *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2,
        char a3,
        unsigned int a4)
{
  struct LogonFrameworkTelemetry::LogonTask *v5; // rsi
  char v7; // r13
  int v8; // eax
  bool v9; // di
  int CurrentUserSid; // r12d
  DWORD dwCurrentState; // esi
  unsigned int v12; // r14d
  int Error; // edi
  SC_HANDLE v14; // rax
  SC_HANDLE v15; // rsi
  SC_HANDLE v16; // rbx
  int v17; // eax
  HLOCAL v18; // rbx
  const wchar_t *v19; // r8
  void *v20; // r13
  LSTATUS ValueW; // eax
  signed int v22; // ebx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  int pdwType; // [rsp+20h] [rbp-69h]
  bool v30; // [rsp+40h] [rbp-49h] BYREF
  bool v31; // [rsp+41h] [rbp-48h]
  int pvData; // [rsp+44h] [rbp-45h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-41h] BYREF
  struct LogonFrameworkTelemetry::LogonTask *v34; // [rsp+50h] [rbp-39h]
  HLOCAL hMem[3]; // [rsp+58h] [rbp-31h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v5 = a2;
  v34 = a2;
  v7 = 0;
  pvData = 0;
  v8 = *((_DWORD *)a1 + 54);
  if ( (v8 & 0x200) == 0
    && (v8 & 0x4402) != 0
    && ((int)SHRegGetBOOLWithREGSAM(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
               L"PostAppInstallTasksCompleted",
               a4,
               &pvData) < 0
     || !pvData) )
  {
    v9 = (*((_DWORD *)a1 + 54) & 0x4002) != 0;
    v31 = v9;
    if ( a3 )
    {
      hMem[1] = (HLOCAL)-1LL;
      hMem[2] = (HLOCAL)-1LL;
      hMem[0] = 0;
      *(_QWORD *)pcbData = 0;
      CurrentUserSid = GetCurrentUserSid((void **)pcbData);
      if ( CurrentUserSid >= 0 )
      {
        if ( ConvertSidToStringSidW(*(PSID *)pcbData, (LPWSTR *)hMem) )
          CurrentUserSid = 0;
        else
          CurrentUserSid = ResultFromKnownLastError();
        LocalFree(*(HLOCAL *)pcbData);
      }
      dwCurrentState = 4;
      v12 = 1800000;
      Error = 0;
      while ( 1 )
      {
        if ( CurrentUserSid < 0 )
          goto LABEL_9;
        v18 = hMem[0];
        v30 = 0;
        Common::StateSeparation::GetIsStateSeparationEnabled(&v30);
        v19 = L"OSData\\Software\\Microsoft\\Windows\\CurrentVersion\\AppReadiness";
        if ( !v30 )
          v19 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AppReadiness";
        memset(&ServiceStatus, 0, 24);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          &ServiceStatus,
          L"%s\\%s",
          v19,
          v18);
        pvData = 0;
        pcbData[0] = 4;
        v20 = *(void **)&ServiceStatus.dwServiceType;
        ValueW = RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   *(LPCWSTR *)&ServiceStatus.dwServiceType,
                   L"UserState",
                   0x10u,
                   0,
                   &pvData,
                   pcbData);
        v22 = ValueW;
        if ( ValueW > 0 )
          v22 = (unsigned __int16)ValueW | 0x80070000;
        v23 = pvData;
        pcbData[0] = pvData;
        if ( v20 )
        {
          CoTaskMemFree(v20);
          v23 = pcbData[0];
        }
        v7 = 0;
        if ( v22 >= 0 && v23 == 3 )
        {
          v7 = 1;
        }
        else
        {
LABEL_9:
          v14 = OpenSCManagerW(0, L"ServicesActive", 1u);
          v15 = v14;
          if ( v14 )
          {
            v16 = OpenServiceW(v14, L"AppReadiness", 4u);
            Error = v16 ? 0 : ResultFromLastError();
            CloseServiceHandle(v15);
          }
          else
          {
            v16 = 0;
            Error = ResultFromLastError();
          }
          if ( Error < 0
            || ((memset(&ServiceStatus, 0, sizeof(ServiceStatus)), !QueryServiceStatus(v16, &ServiceStatus))
              ? (dwCurrentState = 1, Error = ResultFromLastError())
              : (dwCurrentState = ServiceStatus.dwCurrentState, Error = 0),
                CloseServiceHandle(v16),
                Error < 0) )
          {
            dwCurrentState = 4;
          }
          else if ( dwCurrentState != 1 )
          {
            Sleep(0x7D0u);
            v17 = 2000;
            if ( v12 < 0x7D0 )
              v17 = v12;
            v12 -= v17;
          }
        }
        if ( !v12 || v7 )
          break;
        v7 = 0;
        if ( Error < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1DCF,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)Error,
            pdwType);
          break;
        }
        if ( dwCurrentState == 1 )
          goto LABEL_28;
      }
      if ( dwCurrentState == 1 )
      {
LABEL_28:
        pvData = 0;
        goto LABEL_29;
      }
      pvData = v12 != 0 ? -1 : 258;
LABEL_29:
      v5 = v34;
      if ( *((_BYTE *)a1 + 237) )
        LogonFrameworkTelemetry::LogonTask::WaitResult<unsigned short const (&)[22],unsigned long &>(
          v34,
          L"arsWaitForSteadyState",
          &pvData);
      if ( hMem[0] )
        LocalFree(hMem[0]);
      v9 = v31;
    }
    if ( v9 && (*((_BYTE *)a1 + 216) & 0x10) != 0 )
    {
      v24 = UnregisterInvalidLockScreenApplications();
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1DDE,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v24,
          pdwType);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids, v25);
      }
    }
    CLogonTaskFramework::s_WriteOutOOBEDataForOEMApp(v5, *((_BYTE *)a1 + 237));
    if ( v9 )
    {
      v26 = RegisterDefaultLockScreenApplications();
      v27 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1DF2,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v26,
          pdwType);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids, v27);
      }
      if ( (*((_BYTE *)a1 + 220) & 1) != 0 )
      {
        v28 = CLogonTaskFramework::s_RemoveTempOOBEUserWork();
        if ( v28 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1DFE,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v28,
            pdwType);
      }
    }
    SHRegSetBOOL(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
      L"PostAppInstallTasksCompleted",
      1);
  }
}

```

## disassembly

```asm
0x140025e1c  push    rbp
0x140025e1e  push    rbx
0x140025e1f  push    rsi
0x140025e20  push    rdi
0x140025e21  push    r12
0x140025e23  push    r13
0x140025e25  push    r14
0x140025e27  push    r15
0x140025e29  lea     rbp, [rsp-1Fh]
0x140025e2e  sub     rsp, 0A8h
0x140025e35  mov     rax, cs:__security_cookie
0x140025e3c  xor     rax, rsp
0x140025e3f  mov     [rbp+57h+var_50], rax
0x140025e43  mov     bl, r8b
0x140025e46  mov     rsi, rdx
0x140025e49  mov     [rbp+57h+var_90], rdx
0x140025e4d  mov     r15, rcx
0x140025e50  xor     r13d, r13d
0x140025e53  mov     [rbp+57h+var_9C], r13d
0x140025e57  mov     eax, [rcx+0D8h]
0x140025e5d  bt      eax, 9
0x140025e61  jb      loc_140026086
0x140025e67  test    eax, 4402h
0x140025e6c  jz      loc_140026086
0x140025e72  lea     rax, [rbp+57h+var_9C]
0x140025e76  mov     [rsp+0E0h+pdwType], rax; int
0x140025e7b  lea     r8, aPostappinstall; "PostAppInstallTasksCompleted"
0x140025e82  lea     rdx, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140025e89  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x140025e90  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x140025e95  test    eax, eax
0x140025e97  js      short loc_140025EA3
0x140025e99  cmp     [rbp+57h+var_9C], r13d
0x140025e9d  jnz     loc_140026086
0x140025ea3  test    dword ptr [r15+0D8h], 4002h
0x140025eae  setnz   dil
0x140025eb2  mov     [rbp+57h+var_9F], dil
0x140025eb6  test    bl, bl
0x140025eb8  jz      loc_14002603E
0x140025ebe  or      rax, 0FFFFFFFFFFFFFFFFh
0x140025ec2  mov     [rbp+57h+var_80], rax
0x140025ec6  mov     [rbp+57h+var_78], rax
0x140025eca  mov     [rbp+57h+hMem], r13
0x140025ece  mov     qword ptr [rbp+57h+var_98], r13
0x140025ed2  lea     rcx, [rbp+57h+var_98]; void **
0x140025ed6  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x140025edb  mov     r12d, eax
0x140025ede  test    eax, eax
0x140025ee0  jns     loc_140026292
0x140025ee6  mov     esi, 4
0x140025eeb  mov     r14d, 1B7740h
0x140025ef1  mov     edi, r13d
0x140025ef4  test    r12d, r12d
0x140025ef7  jns     loc_1400260A7
0x140025efd  mov     r8d, 1; dwDesiredAccess
0x140025f03  lea     rdx, DatabaseName; "ServicesActive"
0x140025f0a  xor     ecx, ecx; lpMachineName
0x140025f0c  call    cs:__imp_OpenSCManagerW
0x140025f13  nop     dword ptr [rax+rax+00h]
0x140025f18  mov     rsi, rax
0x140025f1b  test    rax, rax
0x140025f1e  jz      loc_14002618F
0x140025f24  mov     r8d, 4; dwDesiredAccess
0x140025f2a  lea     rdx, aAppreadiness; "AppReadiness"
0x140025f31  mov     rcx, rax; hSCManager
0x140025f34  call    cs:__imp_OpenServiceW
0x140025f3b  nop     dword ptr [rax+rax+00h]
0x140025f40  mov     rbx, rax
0x140025f43  test    rax, rax
0x140025f46  jz      loc_1400262CC
0x140025f4c  xor     edi, edi
0x140025f4e  mov     rcx, rsi; hSCObject
0x140025f51  call    cs:__imp_CloseServiceHandle
0x140025f58  nop     dword ptr [rax+rax+00h]
0x140025f5d  test    edi, edi
0x140025f5f  js      loc_14002619D
0x140025f65  xorps   xmm0, xmm0
0x140025f68  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x140025f6c  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x140025f70  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x140025f74  mov     rcx, rbx; hService
0x140025f77  call    cs:__imp_QueryServiceStatus
0x140025f7e  nop     dword ptr [rax+rax+00h]
0x140025f83  test    eax, eax
0x140025f85  jz      loc_14002617E
0x140025f8b  mov     esi, [rbp+57h+ServiceStatus.dwCurrentState]
0x140025f8e  xor     edi, edi
0x140025f90  mov     rcx, rbx; hSCObject
0x140025f93  call    cs:__imp_CloseServiceHandle
0x140025f9a  nop     dword ptr [rax+rax+00h]
0x140025f9f  test    edi, edi
0x140025fa1  js      loc_14002619D
0x140025fa7  cmp     esi, 1
0x140025faa  jz      short loc_140025FCB
0x140025fac  mov     ebx, 7D0h
0x140025fb1  mov     ecx, ebx; dwMilliseconds
0x140025fb3  call    cs:__imp_Sleep
0x140025fba  nop     dword ptr [rax+rax+00h]
0x140025fbf  mov     eax, ebx
0x140025fc1  cmp     r14d, ebx
0x140025fc4  cmovb   eax, r14d
0x140025fc8  sub     r14d, eax
0x140025fcb  test    r14d, r14d
0x140025fce  jz      loc_1400261A7
0x140025fd4  test    r13b, r13b
0x140025fd7  jnz     loc_1400261A7
0x140025fdd  mov     rcx, [rbp+5Fh]; this
0x140025fe1  xor     r13d, r13d
0x140025fe4  test    edi, edi
0x140025fe6  js      short loc_140025FF3
0x140025fe8  cmp     esi, 1
0x140025feb  jnz     loc_140025EF4
0x140025ff1  jmp     short loc_140026010
0x140025ff3  mov     r9d, edi; char *
0x140025ff6  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140025ffd  mov     edx, 1DCFh; void *
0x140026002  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140026007  cmp     esi, 1
0x14002600a  jnz     loc_1400262D8
0x140026010  mov     [rbp+57h+var_9C], r13d
0x140026014  mov     rsi, [rbp+57h+var_90]
0x140026018  cmp     [r15+0EDh], r13b
0x14002601f  jnz     loc_1400262EF
0x140026025  mov     rcx, [rbp+57h+hMem]; hMem
0x140026029  test    rcx, rcx
0x14002602c  jz      short loc_14002603A
0x14002602e  call    cs:__imp_LocalFree
0x140026035  nop     dword ptr [rax+rax+00h]
0x14002603a  mov     dil, [rbp+57h+var_9F]
0x14002603e  lea     r14, WPP_GLOBAL_Control
0x140026045  test    dil, dil
0x140026048  jnz     loc_140026307
0x14002604e  mov     dl, [r15+0EDh]; bool
0x140026055  mov     rcx, rsi; struct LogonFrameworkTelemetry::LogonTask *
0x140026058  call    ?s_WriteOutOOBEDataForOEMApp@CLogonTaskFramework@@CAXPEAVLogonTask@LogonFrameworkTelemetry@@_N@Z; CLogonTaskFramework::s_WriteOutOOBEDataForOEMApp(LogonFrameworkTelemetry::LogonTask *,bool)
0x14002605d  test    dil, dil
0x140026060  jnz     loc_14002620D
0x140026066  mov     r9d, 1; int
0x14002606c  lea     r8, aPostappinstall; "PostAppInstallTasksCompleted"
0x140026073  lea     rdx, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14002607a  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x140026081  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x140026086  mov     rcx, [rbp+57h+var_50]
0x14002608a  xor     rcx, rsp; StackCookie
0x14002608d  call    __security_check_cookie
0x140026092  add     rsp, 0A8h
0x140026099  pop     r15
0x14002609b  pop     r14
0x14002609d  pop     r13
0x14002609f  pop     r12
0x1400260a1  pop     rdi
0x1400260a2  pop     rsi
0x1400260a3  pop     rbx
0x1400260a4  pop     rbp
0x1400260a5  retn
0x1400260a7  mov     rbx, [rbp+57h+hMem]
0x1400260ab  mov     [rbp+57h+var_A0], r13b
0x1400260af  lea     rcx, [rbp+57h+var_A0]; bool *
0x1400260b3  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1400260b8  lea     r8, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Windows\\C"...
0x1400260bf  lea     rax, aSoftwareMicros_49; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400260c6  cmp     [rbp+57h+var_A0], r13b
0x1400260ca  cmovz   r8, rax
0x1400260ce  mov     qword ptr [rbp+57h+ServiceStatus.dwServiceType], r13
0x1400260d2  mov     qword ptr [rbp+57h+ServiceStatus.dwControlsAccepted], r13
0x1400260d6  mov     qword ptr [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], r13
0x1400260da  mov     r9, rbx
0x1400260dd  lea     rdx, aSS; "%s\\%s"
0x1400260e4  lea     rcx, [rbp+57h+ServiceStatus]
0x1400260e8  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1400260ed  mov     [rbp+57h+var_9C], r13d
0x1400260f1  mov     [rbp+57h+var_98], 4
0x1400260f8  lea     rax, [rbp+57h+var_98]
0x1400260fc  mov     [rsp+0E0h+pcbData], rax; pcbData
0x140026101  lea     rax, [rbp+57h+var_9C]
0x140026105  mov     [rsp+0E0h+pvData], rax; pvData
0x14002610a  mov     [rsp+0E0h+pdwType], r13; pdwType
0x14002610f  mov     r9d, 10h; dwFlags
0x140026115  lea     r8, aUserstate; "UserState"
0x14002611c  mov     r13, qword ptr [rbp+57h+ServiceStatus.dwServiceType]
0x140026120  mov     rdx, r13; lpSubKey
0x140026123  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14002612a  call    cs:__imp_RegGetValueW
0x140026131  nop     dword ptr [rax+rax+00h]
0x140026136  mov     ebx, eax
0x140026138  test    eax, eax
0x14002613a  jle     short loc_140026145
0x14002613c  movzx   ebx, ax
0x14002613f  or      ebx, 80070000h
0x140026145  mov     eax, [rbp+57h+var_9C]
0x140026148  mov     [rbp+57h+var_98], eax
0x14002614b  test    r13, r13
0x14002614e  jz      short loc_140026162
0x140026150  mov     rcx, r13; pv
0x140026153  call    cs:__imp_CoTaskMemFree
0x14002615a  nop     dword ptr [rax+rax+00h]
0x14002615f  mov     eax, [rbp+57h+var_98]
0x140026162  xor     r13d, r13d
0x140026165  test    ebx, ebx
0x140026167  js      loc_140025EFD
0x14002616d  cmp     eax, 3
0x140026170  jnz     loc_140025EFD
0x140026176  mov     r13b, 1
0x140026179  jmp     loc_140025FCB
0x14002617e  mov     esi, 1
0x140026183  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140026188  mov     edi, eax
0x14002618a  jmp     loc_140025F90
0x14002618f  xor     ebx, ebx
0x140026191  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140026196  mov     edi, eax
0x140026198  jmp     loc_140025F5D
0x14002619d  mov     esi, 4
0x1400261a2  jmp     loc_140025FCB
0x1400261a7  xor     r13d, r13d
0x1400261aa  jmp     loc_140026007
0x1400261af  call    ?UnregisterInvalidLockScreenApplications@@YAJXZ; UnregisterInvalidLockScreenApplications(void)
0x1400261b4  mov     ebx, eax
0x1400261b6  test    eax, eax
0x1400261b8  jns     loc_14002604E
0x1400261be  mov     rcx, [rbp+5Fh]; this
0x1400261c2  mov     r9d, eax; char *
0x1400261c5  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400261cc  mov     edx, 1DDEh; void *
0x1400261d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400261d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400261dd  cmp     rcx, r14
0x1400261e0  jz      loc_14002604E
0x1400261e6  test    byte ptr [rcx+1Ch], 2
0x1400261ea  jz      loc_14002604E
0x1400261f0  mov     edx, 2Ah ; '*'
0x1400261f5  mov     r9d, ebx
0x1400261f8  lea     r8, WPP_c7f01c30bfbc324b604380eed958234f_Traceguids
0x1400261ff  mov     rcx, [rcx+10h]
0x140026203  call    WPP_SF_d
0x140026208  jmp     loc_14002604E
0x14002620d  call    ?RegisterDefaultLockScreenApplications@@YAJXZ; RegisterDefaultLockScreenApplications(void)
0x140026212  mov     ebx, eax
0x140026214  test    eax, eax
0x140026216  jns     short loc_14002625A
0x140026218  mov     rcx, [rbp+5Fh]; this
0x14002621c  mov     r9d, eax; char *
0x14002621f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140026226  mov     edx, 1DF2h; void *
0x14002622b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140026230  mov     rcx, cs:WPP_GLOBAL_Control
0x140026237  cmp     rcx, r14
0x14002623a  jz      short loc_14002625A
0x14002623c  test    byte ptr [rcx+1Ch], 2
0x140026240  jz      short loc_14002625A
0x140026242  mov     edx, 2Bh ; '+'
0x140026247  mov     r9d, ebx
0x14002624a  lea     r8, WPP_c7f01c30bfbc324b604380eed958234f_Traceguids
0x140026251  mov     rcx, [rcx+10h]
0x140026255  call    WPP_SF_d
0x14002625a  test    byte ptr [r15+0DCh], 1
0x140026262  jz      loc_140026066
0x140026268  call    ?s_RemoveTempOOBEUserWork@CLogonTaskFramework@@CAJXZ; CLogonTaskFramework::s_RemoveTempOOBEUserWork(void)
0x14002626d  test    eax, eax
0x14002626f  jns     loc_140026066
0x140026275  mov     rcx, [rbp+5Fh]; this
0x140026279  mov     r9d, eax; char *
0x14002627c  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140026283  mov     edx, 1DFEh; void *
0x140026288  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14002628d  jmp     loc_140026066
0x140026292  lea     rdx, [rbp+57h+hMem]; StringSid
0x140026296  mov     rcx, qword ptr [rbp+57h+var_98]; Sid
0x14002629a  call    cs:__imp_ConvertSidToStringSidW
0x1400262a1  nop     dword ptr [rax+rax+00h]
0x1400262a6  test    eax, eax
0x1400262a8  jz      short loc_1400262AF
0x1400262aa  mov     r12d, r13d
0x1400262ad  jmp     short loc_1400262B7
0x1400262af  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400262b4  mov     r12d, eax
0x1400262b7  mov     rcx, qword ptr [rbp+57h+var_98]; hMem
0x1400262bb  call    cs:__imp_LocalFree
0x1400262c2  nop     dword ptr [rax+rax+00h]
0x1400262c7  jmp     loc_140025EE6
0x1400262cc  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400262d1  mov     edi, eax
0x1400262d3  jmp     loc_140025F4E
0x1400262d8  neg     r14d
0x1400262db  sbb     eax, eax
0x1400262dd  and     eax, 0FFFFFEFDh
0x1400262e2  add     eax, 102h
0x1400262e7  mov     [rbp+57h+var_9C], eax
0x1400262ea  jmp     loc_140026014
0x1400262ef  lea     r8, [rbp+57h+var_9C]
0x1400262f3  lea     rdx, aArswaitforstea; "arsWaitForSteadyState"
0x1400262fa  mov     rcx, rsi
0x1400262fd  call    ??$WaitResult@AEAY0BG@$$CBGAEAK@LogonTask@LogonFrameworkTelemetry@@QEAAXAEAY0BG@$$CBGAEAK@Z; LogonFrameworkTelemetry::LogonTask::WaitResult<ushort const (&)[22],ulong &>(ushort const (&)[22],ulong &)
0x140026302  jmp     loc_140026025
0x140026307  test    byte ptr [r15+0D8h], 10h
0x14002630f  jz      loc_14002604E
0x140026315  jmp     loc_1400261AF
```

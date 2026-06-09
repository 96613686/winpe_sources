# CLogonTaskFramework::s_RunPostAppInstallTasks(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *,bool)

- ea: `0x1400334f4`
- end: `0x140033a33`
- name: `?s_RunPostAppInstallTasks@CLogonTaskFramework@@CAXPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@_N@Z`
- size: `1343`
- prototype: `void __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *, bool)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400753a0`
- `0x1401a7410`

## callees

- `0x140015710`
- `0x140016b10`
- `0x14001eba8`
- `0x140030a10`
- `0x1400334f4`
- `0x140034b10`
- `0x1400356a8`
- `0x140062ca4`
- `0x1400632b0`
- `0x140089c7c`
- `0x1400b4b84`
- `0x1400d9ebc`
- `0x1401040e0`
- `0x140139a90`
- `0x140193ee0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140033651`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140033651`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140033832`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140033832`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003387c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003387c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140033865`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140033865`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140033715`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140033715`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400337c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400339da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400337c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400339da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033738`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400339bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400339bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140033601`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140033637`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140033601`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140033637`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400335ea`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400335ea`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400335c8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400335c8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140033621`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140033621`

## string_xrefs

- `0x140033789`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400338a5`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400338ff`: `shell\lib\logontasks\logontasks.cpp`
- `0x14003395c`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400335bf`: `ServicesActive`
- `0x1400335e0`: `AppReadiness`
- `0x1400336a3`: `OSData\Software\Microsoft\Windows\CurrentVersion\AppReadiness`
- `0x1400336aa`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness`
- `0x14003385a`: `PostAppInstallTasksCompleted`
- `0x140033986`: `PostAppInstallTasksCompleted`

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
  char v7; // r12
  int v8; // eax
  bool v9; // di
  int CurrentUserSid; // r13d
  DWORD dwCurrentState; // esi
  unsigned int v12; // r14d
  int Error; // edi
  SC_HANDLE v14; // rax
  SC_HANDLE v15; // rsi
  SC_HANDLE v16; // rbx
  int v17; // eax
  HLOCAL v18; // rbx
  const wchar_t *v19; // r8
  void *v20; // r12
  LSTATUS ValueW; // eax
  signed int v22; // ebx
  DWORD v23; // eax
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  int pdwType; // [rsp+20h] [rbp-79h]
  bool v30; // [rsp+50h] [rbp-49h] BYREF
  bool v31; // [rsp+51h] [rbp-48h]
  HKEY hKey; // [rsp+58h] [rbp-41h] BYREF
  DWORD pcbData[2]; // [rsp+60h] [rbp-39h] BYREF
  struct LogonFrameworkTelemetry::LogonTask *v34; // [rsp+68h] [rbp-31h]
  HLOCAL hMem[3]; // [rsp+70h] [rbp-29h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+88h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v5 = a2;
  v34 = a2;
  v7 = 0;
  LODWORD(hKey) = 0;
  v8 = *((_DWORD *)a1 + 54);
  if ( (v8 & 0x200) == 0
    && (v8 & 0x4402) != 0
    && ((int)SHRegGetBOOLWithREGSAM(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
               L"PostAppInstallTasksCompleted",
               a4,
               (int *)&hKey) < 0
     || !(_DWORD)hKey) )
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
          goto LABEL_7;
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
        LODWORD(hKey) = 0;
        pcbData[0] = 4;
        v20 = *(void **)&ServiceStatus.dwServiceType;
        ValueW = RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   *(LPCWSTR *)&ServiceStatus.dwServiceType,
                   L"UserState",
                   0x10u,
                   0,
                   &hKey,
                   pcbData);
        v22 = ValueW;
        if ( ValueW > 0 )
          v22 = (unsigned __int16)ValueW | 0x80070000;
        v23 = (unsigned int)hKey;
        pcbData[0] = (unsigned int)hKey;
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
LABEL_7:
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
            (void *)0x1DB5,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)Error,
            pdwType);
          break;
        }
        if ( dwCurrentState == 1 )
          goto LABEL_38;
      }
      if ( dwCurrentState == 1 )
      {
LABEL_38:
        LODWORD(hKey) = 0;
        goto LABEL_39;
      }
      LODWORD(hKey) = v12 != 0 ? -1 : 258;
LABEL_39:
      v5 = v34;
      if ( *((_BYTE *)a1 + 237) )
        LogonFrameworkTelemetry::LogonTask::WaitResult<unsigned short const (&)[22],unsigned long &>(
          v34,
          L"arsWaitForSteadyState",
          &hKey);
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
          (void *)0x1DC4,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v24,
          pdwType);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids, v25);
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
          (void *)0x1DD8,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v26,
          pdwType);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids, v27);
      }
      if ( (*((_BYTE *)a1 + 220) & 1) != 0 )
      {
        v28 = CLogonTaskFramework::s_RemoveTempOOBEUserWork();
        if ( v28 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1DE4,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v28,
            pdwType);
      }
    }
    pcbData[0] = 1;
    hKey = 0;
    if ( !RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
            0,
            0,
            0,
            2u,
            0,
            &hKey,
            0) )
    {
      RegSetValueExW(hKey, L"PostAppInstallTasksCompleted", 0, 4u, (const BYTE *)pcbData, 4u);
      if ( hKey != HKEY_CURRENT_USER )
        RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x1400334f4  push    rbp
0x1400334f6  push    rbx
0x1400334f7  push    rsi
0x1400334f8  push    rdi
0x1400334f9  push    r12
0x1400334fb  push    r13
0x1400334fd  push    r14
0x1400334ff  push    r15
0x140033501  lea     rbp, [rsp-1Fh]
0x140033506  sub     rsp, 0B8h
0x14003350d  mov     rax, cs:__security_cookie
0x140033514  xor     rax, rsp
0x140033517  mov     [rbp+57h+var_48], rax
0x14003351b  mov     bl, r8b
0x14003351e  mov     rsi, rdx
0x140033521  mov     [rbp+57h+var_88], rdx
0x140033525  mov     r15, rcx
0x140033528  xor     r12d, r12d
0x14003352b  mov     dword ptr [rbp+57h+hKey], r12d
0x14003352f  mov     eax, [rcx+0D8h]
0x140033535  bt      eax, 9
0x140033539  jnb     loc_140033972
0x14003353f  mov     rcx, [rbp+57h+var_48]
0x140033543  xor     rcx, rsp; StackCookie
0x140033546  call    __security_check_cookie
0x14003354b  add     rsp, 0B8h
0x140033552  pop     r15
0x140033554  pop     r14
0x140033556  pop     r13
0x140033558  pop     r12
0x14003355a  pop     rdi
0x14003355b  pop     rsi
0x14003355c  pop     rbx
0x14003355d  pop     rbp
0x14003355e  retn
0x14003355f  test    dword ptr [r15+0D8h], 4002h
0x14003356a  setnz   dil
0x14003356e  mov     [rbp+57h+var_9F], dil
0x140033572  test    bl, bl
0x140033574  jz      loc_1400337CB
0x14003357a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003357e  mov     [rbp+57h+var_78], rax
0x140033582  mov     [rbp+57h+var_70], rax
0x140033586  mov     [rbp+57h+hMem], r12
0x14003358a  mov     qword ptr [rbp+57h+var_90], r12
0x14003358e  lea     rcx, [rbp+57h+var_90]; void **
0x140033592  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x140033597  mov     r13d, eax
0x14003359a  test    eax, eax
0x14003359c  jns     loc_1400339B7
0x1400335a2  mov     esi, 4
0x1400335a7  mov     r14d, 1B7740h
0x1400335ad  mov     edi, r12d
0x1400335b0  test    r13d, r13d
0x1400335b3  jns     loc_140033692
0x1400335b9  mov     r8d, 1; dwDesiredAccess
0x1400335bf  lea     rdx, DatabaseName; "ServicesActive"
0x1400335c6  xor     ecx, ecx; lpMachineName
0x1400335c8  call    cs:__imp_OpenSCManagerW
0x1400335ce  mov     rsi, rax
0x1400335d1  test    rax, rax
0x1400335d4  jz      loc_14003376E
0x1400335da  mov     r8d, 4; dwDesiredAccess
0x1400335e0  lea     rdx, aAppreadiness; "AppReadiness"
0x1400335e7  mov     rcx, rax; hSCManager
0x1400335ea  call    cs:__imp_OpenServiceW
0x1400335f0  mov     rbx, rax
0x1400335f3  test    rax, rax
0x1400335f6  jz      loc_1400339E5
0x1400335fc  xor     edi, edi
0x1400335fe  mov     rcx, rsi; hSCObject
0x140033601  call    cs:__imp_CloseServiceHandle
0x140033607  test    edi, edi
0x140033609  js      loc_14003377C
0x14003360f  xorps   xmm0, xmm0
0x140033612  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x140033616  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x14003361a  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x14003361e  mov     rcx, rbx; hService
0x140033621  call    cs:__imp_QueryServiceStatus
0x140033627  test    eax, eax
0x140033629  jz      loc_14003375D
0x14003362f  mov     esi, [rbp+57h+ServiceStatus.dwCurrentState]
0x140033632  xor     edi, edi
0x140033634  mov     rcx, rbx; hSCObject
0x140033637  call    cs:__imp_CloseServiceHandle
0x14003363d  test    edi, edi
0x14003363f  js      loc_14003377C
0x140033645  cmp     esi, 1
0x140033648  jz      short loc_140033663
0x14003364a  mov     ebx, 7D0h
0x14003364f  mov     ecx, ebx; dwMilliseconds
0x140033651  call    cs:__imp_Sleep
0x140033657  mov     eax, ebx
0x140033659  cmp     r14d, ebx
0x14003365c  cmovb   eax, r14d
0x140033660  sub     r14d, eax
0x140033663  test    r14d, r14d
0x140033666  jz      loc_140033887
0x14003366c  test    r12b, r12b
0x14003366f  jnz     loc_140033887
0x140033675  mov     rcx, [rbp+5Fh]; this
0x140033679  xor     r12d, r12d
0x14003367c  test    edi, edi
0x14003367e  js      loc_140033786
0x140033684  cmp     esi, 1
0x140033687  jnz     loc_1400335B0
0x14003368d  jmp     loc_1400337A3
0x140033692  mov     rbx, [rbp+57h+hMem]
0x140033696  mov     [rbp+57h+var_A0], r12b
0x14003369a  lea     rcx, [rbp+57h+var_A0]; bool *
0x14003369e  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1400336a3  lea     r8, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Windows\\C"...
0x1400336aa  lea     rax, aSoftwareMicros_49; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400336b1  cmp     [rbp+57h+var_A0], r12b
0x1400336b5  cmovz   r8, rax
0x1400336b9  mov     qword ptr [rbp+57h+ServiceStatus.dwServiceType], r12
0x1400336bd  mov     qword ptr [rbp+57h+ServiceStatus.dwControlsAccepted], r12
0x1400336c1  mov     qword ptr [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], r12
0x1400336c5  mov     r9, rbx
0x1400336c8  lea     rdx, aSS; "%s\\%s"
0x1400336cf  lea     rcx, [rbp+57h+ServiceStatus]
0x1400336d3  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1400336d8  mov     dword ptr [rbp+57h+hKey], r12d
0x1400336dc  mov     [rbp+57h+var_90], 4
0x1400336e3  lea     rax, [rbp+57h+var_90]
0x1400336e7  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1400336ec  lea     rax, [rbp+57h+hKey]
0x1400336f0  mov     [rsp+0F0h+pvData], rax; pvData
0x1400336f5  mov     [rsp+0F0h+pdwType], r12; pdwType
0x1400336fa  mov     r9d, 10h; dwFlags
0x140033700  lea     r8, aUserstate; "UserState"
0x140033707  mov     r12, qword ptr [rbp+57h+ServiceStatus.dwServiceType]
0x14003370b  mov     rdx, r12; lpSubKey
0x14003370e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140033715  call    cs:__imp_RegGetValueW
0x14003371b  mov     ebx, eax
0x14003371d  test    eax, eax
0x14003371f  jle     short loc_14003372A
0x140033721  movzx   ebx, ax
0x140033724  or      ebx, 80070000h
0x14003372a  mov     eax, dword ptr [rbp+57h+hKey]
0x14003372d  mov     [rbp+57h+var_90], eax
0x140033730  test    r12, r12
0x140033733  jz      short loc_140033741
0x140033735  mov     rcx, r12; pv
0x140033738  call    cs:__imp_CoTaskMemFree
0x14003373e  mov     eax, [rbp+57h+var_90]
0x140033741  xor     r12d, r12d
0x140033744  test    ebx, ebx
0x140033746  js      loc_1400335B9
0x14003374c  cmp     eax, 3
0x14003374f  jnz     loc_1400335B9
0x140033755  mov     r12b, 1
0x140033758  jmp     loc_140033663
0x14003375d  mov     esi, 1
0x140033762  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140033767  mov     edi, eax
0x140033769  jmp     loc_140033634
0x14003376e  xor     ebx, ebx
0x140033770  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140033775  mov     edi, eax
0x140033777  jmp     loc_140033607
0x14003377c  mov     esi, 4
0x140033781  jmp     loc_140033663
0x140033786  mov     r9d, edi; char *
0x140033789  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140033790  mov     edx, 1DB5h; void *
0x140033795  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003379a  cmp     esi, 1
0x14003379d  jnz     loc_1400339F1
0x1400337a3  mov     dword ptr [rbp+57h+hKey], r12d
0x1400337a7  mov     rsi, [rbp+57h+var_88]
0x1400337ab  cmp     [r15+0EDh], r12b
0x1400337b2  jnz     loc_140033A08
0x1400337b8  mov     rcx, [rbp+57h+hMem]; hMem
0x1400337bc  test    rcx, rcx
0x1400337bf  jz      short loc_1400337C7
0x1400337c1  call    cs:__imp_LocalFree
0x1400337c7  mov     dil, [rbp+57h+var_9F]
0x1400337cb  lea     r14, WPP_GLOBAL_Control
0x1400337d2  test    dil, dil
0x1400337d5  jnz     loc_140033A20
0x1400337db  mov     dl, [r15+0EDh]; bool
0x1400337e2  mov     rcx, rsi; struct LogonFrameworkTelemetry::LogonTask *
0x1400337e5  call    ?s_WriteOutOOBEDataForOEMApp@CLogonTaskFramework@@CAXPEAVLogonTask@LogonFrameworkTelemetry@@_N@Z; CLogonTaskFramework::s_WriteOutOOBEDataForOEMApp(LogonFrameworkTelemetry::LogonTask *,bool)
0x1400337ea  test    dil, dil
0x1400337ed  jnz     loc_1400338ED
0x1400337f3  mov     [rbp+57h+var_90], 1
0x1400337fa  mov     [rbp+57h+hKey], r12
0x1400337fe  mov     [rsp+0F0h+lpdwDisposition], r12; lpdwDisposition
0x140033803  lea     rax, [rbp+57h+hKey]
0x140033807  mov     [rsp+0F0h+phkResult], rax; phkResult
0x14003380c  mov     [rsp+0F0h+pcbData], r12; lpSecurityAttributes
0x140033811  mov     dword ptr [rsp+0F0h+pvData], 2; samDesired
0x140033819  mov     dword ptr [rsp+0F0h+pdwType], r12d; dwOptions
0x14003381e  xor     r9d, r9d; lpClass
0x140033821  xor     r8d, r8d; Reserved
0x140033824  lea     rdx, aSoftwareMicros_119; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14003382b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140033832  call    cs:__imp_RegCreateKeyExW
0x140033838  test    eax, eax
0x14003383a  jnz     loc_14003353F
0x140033840  mov     dword ptr [rsp+0F0h+pvData], 4; cbData
0x140033848  lea     rax, [rbp+57h+var_90]
0x14003384c  mov     [rsp+0F0h+pdwType], rax; lpData
0x140033851  mov     r9d, 4; dwType
0x140033857  xor     r8d, r8d; Reserved
0x14003385a  lea     rdx, aPostappinstall; "PostAppInstallTasksCompleted"
0x140033861  mov     rcx, [rbp+57h+hKey]; hKey
0x140033865  call    cs:__imp_RegSetValueExW
0x14003386b  mov     rcx, [rbp+57h+hKey]; hKey
0x14003386f  cmp     rcx, 0FFFFFFFF80000001h
0x140033876  jz      loc_14003353F
0x14003387c  call    cs:__imp_RegCloseKey
0x140033882  jmp     loc_14003353F
0x140033887  xor     r12d, r12d
0x14003388a  jmp     loc_14003379A
0x14003388f  call    ?UnregisterInvalidLockScreenApplications@@YAJXZ; UnregisterInvalidLockScreenApplications(void)
0x140033894  mov     ebx, eax
0x140033896  test    eax, eax
0x140033898  jns     loc_1400337DB
0x14003389e  mov     rcx, [rbp+5Fh]; this
0x1400338a2  mov     r9d, eax; char *
0x1400338a5  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400338ac  mov     edx, 1DC4h; void *
0x1400338b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400338b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400338bd  cmp     rcx, r14
0x1400338c0  jz      loc_1400337DB
0x1400338c6  test    byte ptr [rcx+1Ch], 2
0x1400338ca  jz      loc_1400337DB
0x1400338d0  mov     edx, 2Ah ; '*'
0x1400338d5  mov     r9d, ebx
0x1400338d8  lea     r8, WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids
0x1400338df  mov     rcx, [rcx+10h]
0x1400338e3  call    WPP_SF_d
0x1400338e8  jmp     loc_1400337DB
0x1400338ed  call    ?RegisterDefaultLockScreenApplications@@YAJXZ; RegisterDefaultLockScreenApplications(void)
0x1400338f2  mov     ebx, eax
0x1400338f4  test    eax, eax
0x1400338f6  jns     short loc_14003393A
0x1400338f8  mov     rcx, [rbp+5Fh]; this
0x1400338fc  mov     r9d, eax; char *
0x1400338ff  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140033906  mov     edx, 1DD8h; void *
0x14003390b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140033910  mov     rcx, cs:WPP_GLOBAL_Control
0x140033917  cmp     rcx, r14
0x14003391a  jz      short loc_14003393A
0x14003391c  test    byte ptr [rcx+1Ch], 2
0x140033920  jz      short loc_14003393A
0x140033922  mov     edx, 2Bh ; '+'
0x140033927  mov     r9d, ebx
0x14003392a  lea     r8, WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids
0x140033931  mov     rcx, [rcx+10h]
0x140033935  call    WPP_SF_d
0x14003393a  test    byte ptr [r15+0DCh], 1
0x140033942  jz      loc_1400337F3
0x140033948  call    ?s_RemoveTempOOBEUserWork@CLogonTaskFramework@@CAJXZ; CLogonTaskFramework::s_RemoveTempOOBEUserWork(void)
0x14003394d  test    eax, eax
0x14003394f  jns     loc_1400337F3
0x140033955  mov     rcx, [rbp+5Fh]; this
0x140033959  mov     r9d, eax; char *
0x14003395c  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140033963  mov     edx, 1DE4h; void *
0x140033968  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003396d  jmp     loc_1400337F3
0x140033972  test    eax, 4402h
0x140033977  jz      loc_14003353F
0x14003397d  lea     rax, [rbp+57h+hKey]
0x140033981  mov     [rsp+0F0h+pdwType], rax; int *
0x140033986  lea     r8, aPostappinstall; "PostAppInstallTasksCompleted"
0x14003398d  lea     rdx, aSoftwareMicros_119; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140033994  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x14003399b  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1400339a0  test    eax, eax
0x1400339a2  js      loc_14003355F
0x1400339a8  cmp     dword ptr [rbp+57h+hKey], r12d
0x1400339ac  jnz     loc_14003353F
0x1400339b2  jmp     loc_14003355F
0x1400339b7  lea     rdx, [rbp+57h+hMem]; StringSid
0x1400339bb  mov     rcx, qword ptr [rbp+57h+var_90]; Sid
0x1400339bf  call    cs:__imp_ConvertSidToStringSidW
0x1400339c5  test    eax, eax
0x1400339c7  jz      short loc_1400339CE
0x1400339c9  mov     r13d, r12d
0x1400339cc  jmp     short loc_1400339D6
0x1400339ce  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400339d3  mov     r13d, eax
0x1400339d6  mov     rcx, qword ptr [rbp+57h+var_90]; hMem
0x1400339da  call    cs:__imp_LocalFree
0x1400339e0  jmp     loc_1400335A2
0x1400339e5  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400339ea  mov     edi, eax
0x1400339ec  jmp     loc_1400335FE
0x1400339f1  neg     r14d
0x1400339f4  sbb     eax, eax
0x1400339f6  and     eax, 0FFFFFEFDh
0x1400339fb  add     eax, 102h
  ... truncated ...
```

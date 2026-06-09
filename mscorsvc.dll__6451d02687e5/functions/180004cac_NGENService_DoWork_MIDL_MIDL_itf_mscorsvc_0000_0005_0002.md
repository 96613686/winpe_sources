# NGENService::DoWork(__MIDL___MIDL_itf_mscorsvc_0000_0005_0002)

- ea: `0x180004cac`
- end: `0x1800050b1`
- name: `?DoWork@NGENService@@YAJW4__MIDL___MIDL_itf_mscorsvc_0000_0005_0002@@@Z`
- size: `1029`
- prototype: `__int64 __fastcall(int, struct ICorSvcManager **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800053a0`

## callees

- `0x180002eb4`
- `0x180002f44`
- `0x1800036b0`
- `0x180003f08`
- `0x180004078`
- `0x180004c5c`
- `0x180004cac`
- `0x18002e1d0`
- `0x18002e308`
- `0x18002e418`
- `0x1800364c0`
- `0x1800366a8`
- `0x180037340`
- `0x1800373e0`
- `0x18003f280`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004f59`
- `KERNEL32!EnterCriticalSection` at `0x180004fbc`
- `KERNEL32!EnterCriticalSection` at `0x180004f59`
- `KERNEL32!EnterCriticalSection` at `0x180004fbc`
- `KERNEL32!LeaveCriticalSection` at `0x180004f6c`
- `KERNEL32!LeaveCriticalSection` at `0x180004fd4`
- `KERNEL32!LeaveCriticalSection` at `0x180004f6c`
- `KERNEL32!LeaveCriticalSection` at `0x180004fd4`
- `KERNEL32!WaitForSingleObject` at `0x180004ec2`
- `KERNEL32!WaitForSingleObject` at `0x180004ec2`
- `KERNEL32!CloseHandle` at `0x180004ff6`
- `KERNEL32!CloseHandle` at `0x18000506d`
- `KERNEL32!CloseHandle` at `0x180004ff6`
- `KERNEL32!CloseHandle` at `0x18000506d`
- `ole32!CoDisconnectObject` at `0x180004da5`
- `ole32!CoDisconnectObject` at `0x180005020`
- `ole32!CoDisconnectObject` at `0x180004da5`
- `ole32!CoDisconnectObject` at `0x180005020`

## string_xrefs

- `0x180004f12`: `ngenservice_pri0_lock.dat`
- `0x180004f09`: `ngenservice_pri1_lock.dat`
- `0x180004f00`: `ngenservice_pri2_lock.dat`
- `0x180004ef7`: `ngenservice_pri3_lock.dat`
- `0x180004cf8`: `PendingUpdate`
- `0x180004d7d`: `PendingUpdate`
- `0x180004cdc`: `DoWork(): Failed to retrieve service manager\n`
- `0x180004d16`: `DoWork(): There is a pending update...\n`
- `0x180004d4a`: `Deferred Update() failed(). Returned HR=0x%08x\n`
- `0x180004d60`: `Service successfully completed pending update\n`
- `0x180004e1a`: `DoWork(): Attempting to acquire priority lock\n`
- `0x180004e78`: `DoWork(): Waiting for other service to complete higher priority work\n`
- `0x18000504c`: `DoWork(): We were interrupted while wait for other service to complete higher pri work`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
__int64 __fastcall NGENService::DoWork(int a1, struct ICorSvcManager **a2)
{
  unsigned int ServiceManager; // eax
  int v4; // edx
  const unsigned __int16 *v5; // rdx
  int v6; // ebx
  const unsigned __int16 *v7; // r8
  IUnknown *v8; // rdi
  int Long; // eax
  NGENService *v10; // rcx
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // eax
  int v13; // edx
  int v14; // eax
  const unsigned __int16 *v15; // r8
  unsigned int v16; // r15d
  unsigned int v17; // esi
  struct ICorSvcManager **v18; // rdx
  unsigned int v19; // eax
  int v20; // edx
  unsigned int v21; // eax
  int v22; // edx
  int v23; // eax
  const unsigned __int16 *v24; // rdx
  NGENService *v25; // rcx
  bool v26; // dl
  unsigned int ConfigValue; // eax
  unsigned int v28; // edx
  unsigned int v29; // eax
  const unsigned __int16 *v30; // rdx
  const unsigned __int16 *v31; // rdx
  const unsigned __int16 *v32; // rdx
  const unsigned __int16 *v33; // rdx
  unsigned int v34; // eax
  int v35; // edx
  const unsigned __int16 *v37; // [rsp+20h] [rbp-50h]
  int v38; // [rsp+30h] [rbp-40h] BYREF
  LPUNKNOWN pUnk; // [rsp+38h] [rbp-38h] BYREF
  void **v40; // [rsp+40h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-28h]
  struct _RTL_CRITICAL_SECTION *v42; // [rsp+50h] [rbp-20h]
  char v43; // [rsp+58h] [rbp-18h]
  struct _RTL_CRITICAL_SECTION *v44; // [rsp+60h] [rbp-10h]
  char v45; // [rsp+68h] [rbp-8h]
  bool v46; // [rsp+B8h] [rbp+48h] BYREF
  bool v47; // [rsp+C0h] [rbp+50h] BYREF
  int v48; // [rsp+C8h] [rbp+58h] BYREF

  pUnk = 0;
  ServiceManager = NGENService::GetServiceManager((NGENService *)&pUnk, a2);
  v6 = NGENService::HandleServiceManagerHR((NGENService *)ServiceManager, v4);
  if ( v6 < 0 )
  {
LABEL_2:
    NGENService::DebugLog((NGENService *)L"DoWork(): Failed to retrieve service manager\n", v5);
    v8 = pUnk;
    goto LABEL_40;
  }
  Long = REGUTIL::GetLong(L"PendingUpdate", (int)v5, v7, NGENService::g_hkNGENServicePersistentState);
  v8 = pUnk;
  if ( Long == 1 && !NGENService::IsWorkForbiddenUntilReboot(v10) )
  {
    NGENService::DebugLog((NGENService *)L"DoWork(): There is a pending update...\n", v11);
    v12 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, LPCWSTR))v8->lpVtbl[2].AddRef)(
            v8,
            0,
            NGENService::g_bstrInterruptEventName);
    v14 = NGENService::HandleServiceManagerHR((NGENService *)v12, v13);
    v6 = v14;
    if ( v14 < 0 )
    {
      NGENService::Log(
        (NGENService *)L"Deferred Update() failed(). Returned HR=0x%08x\n",
        (const unsigned __int16 *)(unsigned int)v14);
      goto LABEL_40;
    }
    NGENService::EventLog(
      0,
      (const unsigned __int16 *)4,
      0x459u,
      (unsigned int)L"Service successfully completed pending update\n",
      v37);
    REGUTIL::SetOrCreateLong(L"PendingUpdate", 0, v15, NGENService::g_hkNGENServicePersistentState);
  }
  v16 = NGENService::ConfigWorkerPriority(v10);
  v17 = 0;
  if ( a1 >= 0 )
  {
    while ( 1 )
    {
      CoDisconnectObject(v8, 0);
      ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
      pUnk = 0;
      v19 = NGENService::GetServiceManager((NGENService *)&pUnk, v18);
      v6 = NGENService::HandleServiceManagerHR((NGENService *)v19, v20);
      if ( v6 < 0 )
        goto LABEL_2;
      v48 = 0;
      v8 = pUnk;
      v21 = ((__int64 (__fastcall *)(LPUNKNOWN, _QWORD, LPCWSTR, int *))pUnk->lpVtbl[1].QueryInterface)(
              pUnk,
              v17,
              NGENService::g_bstrInterruptEventName,
              &v48);
      v23 = NGENService::HandleServiceManagerHR((NGENService *)v21, v22);
      v6 = v23;
      if ( v23 < 0 )
      {
        NGENService::DebugLog(
          (NGENService *)L"ControllerIsWorkAvailable(): ICorSvcManager::IsWorkAvailable() failed(). Returned HR=0x%08x\n",
          (const unsigned __int16 *)(unsigned int)v23);
        goto LABEL_40;
      }
      if ( v48 )
      {
        NGENService::DebugLog((NGENService *)L"DoWork(): Attempting to acquire priority lock\n", v24);
        hObject = (HANDLE)-1LL;
        v40 = &MachineWideMutexHolder::`vftable';
        if ( byte_18007082C )
        {
          ConfigValue = dword_180070828;
        }
        else
        {
          ConfigValue = CLRConfig::GetConfigValue(
                          (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServiceSynchronization,
                          v26,
                          &v46);
          dword_180070828 = ConfigValue;
          byte_18007082C = 1;
        }
        if ( ConfigValue )
        {
          while ( (unsigned int)NGENService::IsOtherServiceDoingHigherPriorityWork(v17) )
          {
            NGENService::DebugLog(
              (NGENService *)L"DoWork(): Waiting for other service to complete higher priority work\n",
              v31);
            if ( byte_1800707E4 )
            {
              v29 = dword_1800707E0;
            }
            else
            {
              v29 = CLRConfig::GetConfigValue(
                      (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServiceWaitWorking,
                      v28,
                      &v47);
              dword_1800707E0 = v29;
              byte_1800707E4 = 1;
            }
            NGENService::WaitForNextStateMachineCheck((NGENService *)v29, v28);
            if ( !WaitForSingleObject(NGENService::g_hInterruptEvent, 0) )
            {
              v6 = -2147467259;
              NGENService::DebugLog(
                (NGENService *)L"DoWork(): We were interrupted while wait for other service to complete higher pri work",
                v30);
              goto LABEL_44;
            }
          }
          v38 = 0;
          if ( v17 )
          {
            switch ( v17 )
            {
              case 1u:
                v32 = L"ngenservice_pri1_lock.dat";
                break;
              case 2u:
                v32 = L"ngenservice_pri2_lock.dat";
                break;
              case 3u:
                v32 = L"ngenservice_pri3_lock.dat";
                break;
              default:
                v32 = 0;
                break;
            }
          }
          else
          {
            v32 = L"ngenservice_pri0_lock.dat";
          }
          if ( (int)FileLockHolder::AcquireNoThrow((FileLockHolder *)&v40, v32, NGENService::g_hInterruptEvent, &v38) < 0 )
            NGENService::DebugLog((NGENService *)L"DoWork(): Failed to acquire priority lock\n", v33);
          if ( v38 )
          {
            v6 = -2147467259;
            NGENService::DebugLog((NGENService *)L"DoWork(): We were interrupted while acquiring priority lock", v33);
            goto LABEL_44;
          }
        }
        v42 = &NGENService::ControllerState::m_csControllerState;
        v43 = 0;
        EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
        v43 = 1;
        NGENService::ControllerState::g_currentPriorityLevel = v17;
        LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
        NGENService::Log((NGENService *)L"Processing work for priority %i\n", (const unsigned __int16 *)v17);
        v34 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, void ***, LPCWSTR))v8->lpVtbl[1].AddRef)(
                v8,
                v16,
                NGENService::g_ProgressNotification,
                NGENService::g_bstrInterruptEventName);
        v6 = NGENService::HandleServiceManagerHR((NGENService *)v34, v35);
        v44 = &NGENService::ControllerState::m_csControllerState;
        v45 = 0;
        EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
        v45 = 1;
        NGENService::ControllerState::g_currentPriorityLevel = -1;
        LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
        if ( v6 < 0 )
        {
          NGENService::DebugLog(
            (NGENService *)L"DoWork(): ICorSvcManager::Work() failed(). Returned HR=0x%08x\n",
            (const unsigned __int16 *)(unsigned int)v6);
LABEL_44:
          v40 = &FileLockHolder::`vftable';
          if ( hObject != (HANDLE)-1LL )
          {
            CloseHandle(hObject);
            hObject = (HANDLE)-1LL;
          }
          goto LABEL_40;
        }
        v40 = &FileLockHolder::`vftable';
        v25 = (NGENService *)hObject;
        if ( hObject != (HANDLE)-1LL )
        {
          CloseHandle(hObject);
          hObject = (HANDLE)-1LL;
        }
      }
      if ( !NGENService::IsWorkForbiddenUntilReboot(v25) && (int)++v17 <= a1 )
        continue;
      break;
    }
  }
  v6 = 0;
LABEL_40:
  if ( v8 )
  {
    CoDisconnectObject(v8, 0);
    ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004cac  push    rbp
0x180004cae  push    rbx
0x180004caf  push    rsi
0x180004cb0  push    rdi
0x180004cb1  push    r13
0x180004cb3  push    r14
0x180004cb5  push    r15
0x180004cb7  mov     rbp, rsp
0x180004cba  sub     rsp, 70h
0x180004cbe  mov     r14d, ecx
0x180004cc1  and     [rbp+pUnk], 0
0x180004cc6  lea     rcx, [rbp+pUnk]; this
0x180004cca  call    ?GetServiceManager@NGENService@@YAJPEAPEAUICorSvcManager@@@Z; NGENService::GetServiceManager(ICorSvcManager * *)
0x180004ccf  mov     ecx, eax; this
0x180004cd1  call    ?HandleServiceManagerHR@NGENService@@YAJJ@Z; NGENService::HandleServiceManagerHR(long)
0x180004cd6  mov     ebx, eax
0x180004cd8  test    eax, eax
0x180004cda  jns     short loc_180004CF1
0x180004cdc  lea     rcx, aDoworkFailedTo; "DoWork(): Failed to retrieve service ma"...
0x180004ce3  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004ce8  mov     rdi, [rbp+pUnk]
0x180004cec  jmp     loc_180005016
0x180004cf1  mov     r9, cs:?g_hkNGENServicePersistentState@NGENService@@3PEAUHKEY__@@EA; HKEY
0x180004cf8  lea     rcx, aPendingupdate; "PendingUpdate"
0x180004cff  call    ?GetLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::GetLong(ushort const *,long,ushort const *,HKEY__ *)
0x180004d04  mov     rdi, [rbp+pUnk]
0x180004d08  cmp     eax, 1
0x180004d0b  jnz     short loc_180004D89
0x180004d0d  call    ?IsWorkForbiddenUntilReboot@NGENService@@YA_NXZ; NGENService::IsWorkForbiddenUntilReboot(void)
0x180004d12  test    al, al
0x180004d14  jnz     short loc_180004D89
0x180004d16  lea     rcx, aDoworkThereIsA; "DoWork(): There is a pending update..."...
0x180004d1d  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004d22  mov     rax, [rdi]
0x180004d25  mov     r8, cs:?g_bstrInterruptEventName@NGENService@@3PEAGEA; ushort * NGENService::g_bstrInterruptEventName
0x180004d2c  xor     edx, edx
0x180004d2e  mov     rcx, rdi
0x180004d31  mov     rax, [rax+38h]
0x180004d35  call    cs:__guard_dispatch_icall_fptr
0x180004d3b  mov     ecx, eax; this
0x180004d3d  call    ?HandleServiceManagerHR@NGENService@@YAJJ@Z; NGENService::HandleServiceManagerHR(long)
0x180004d42  mov     ebx, eax
0x180004d44  test    eax, eax
0x180004d46  jns     short loc_180004D5B
0x180004d48  mov     edx, eax; unsigned __int16 *
0x180004d4a  lea     rcx, aDeferredUpdate; "Deferred Update() failed(). Returned HR"...
0x180004d51  call    ?Log@NGENService@@YAXPEBGZZ; NGENService::Log(ushort const *,...)
0x180004d56  jmp     loc_180005016
0x180004d5b  mov     edx, 4; unsigned __int16 *
0x180004d60  lea     r9, aServiceSuccess; "Service successfully completed pending "...
0x180004d67  xor     ecx, ecx; this
0x180004d69  mov     r8d, 459h; unsigned __int16
0x180004d6f  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x180004d74  mov     r9, cs:?g_hkNGENServicePersistentState@NGENService@@3PEAUHKEY__@@EA; HKEY
0x180004d7b  xor     edx, edx; int
0x180004d7d  lea     rcx, aPendingupdate; "PendingUpdate"
0x180004d84  call    ?SetOrCreateLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::SetOrCreateLong(ushort const *,long,ushort const *,HKEY__ *)
0x180004d89  call    ?ConfigWorkerPriority@NGENService@@YAKXZ; NGENService::ConfigWorkerPriority(void)
0x180004d8e  mov     r15d, eax
0x180004d91  xor     esi, esi
0x180004d93  test    r14d, r14d
0x180004d96  js      loc_180005014
0x180004d9c  or      r13, 0FFFFFFFFFFFFFFFFh
0x180004da0  xor     edx, edx; dwReserved
0x180004da2  mov     rcx, rdi; pUnk
0x180004da5  call    cs:__imp_CoDisconnectObject
0x180004dab  mov     rax, [rdi]
0x180004dae  mov     rcx, rdi
0x180004db1  mov     rax, [rax+10h]
0x180004db5  call    cs:__guard_dispatch_icall_fptr
0x180004dbb  and     [rbp+pUnk], 0
0x180004dc0  lea     rcx, [rbp+pUnk]; this
0x180004dc4  call    ?GetServiceManager@NGENService@@YAJPEAPEAUICorSvcManager@@@Z; NGENService::GetServiceManager(ICorSvcManager * *)
0x180004dc9  mov     ecx, eax; this
0x180004dcb  call    ?HandleServiceManagerHR@NGENService@@YAJJ@Z; NGENService::HandleServiceManagerHR(long)
0x180004dd0  mov     ebx, eax
0x180004dd2  test    eax, eax
0x180004dd4  js      loc_180004CDC
0x180004dda  and     [rbp+arg_18], 0
0x180004dde  mov     rdi, [rbp+pUnk]
0x180004de2  mov     rax, [rdi]
0x180004de5  lea     r9, [rbp+arg_18]
0x180004de9  mov     r8, cs:?g_bstrInterruptEventName@NGENService@@3PEAGEA; ushort * NGENService::g_bstrInterruptEventName
0x180004df0  mov     edx, esi
0x180004df2  mov     rcx, rdi
0x180004df5  mov     rax, [rax+18h]
0x180004df9  call    cs:__guard_dispatch_icall_fptr
0x180004dff  mov     ecx, eax; this
0x180004e01  call    ?HandleServiceManagerHR@NGENService@@YAJJ@Z; NGENService::HandleServiceManagerHR(long)
0x180004e06  mov     ebx, eax
0x180004e08  test    eax, eax
0x180004e0a  js      loc_18000509E
0x180004e10  cmp     [rbp+arg_18], 0
0x180004e14  jz      loc_180005000
0x180004e1a  lea     rcx, aDoworkAttempti; "DoWork(): Attempting to acquire priorit"...
0x180004e21  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004e26  lea     rax, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x180004e2d  mov     [rbp+var_30], rax
0x180004e31  mov     [rbp+hObject], r13
0x180004e35  lea     rax, ??_7MachineWideMutexHolder@@6B@; const MachineWideMutexHolder::`vftable'
0x180004e3c  mov     [rbp+var_30], rax
0x180004e40  cmp     cs:byte_18007082C, 0
0x180004e47  jnz     short loc_180004E68
0x180004e49  lea     r8, [rbp+arg_8]; bool *
0x180004e4d  lea     rcx, ?UNSUPPORTED_NGENServiceSynchronization@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180004e54  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180004e59  mov     cs:dword_180070828, eax
0x180004e5f  mov     cs:byte_18007082C, 1
0x180004e66  jmp     short loc_180004E6E
0x180004e68  mov     eax, cs:dword_180070828
0x180004e6e  test    eax, eax
0x180004e70  jz      loc_180004F47
0x180004e76  jmp     short loc_180004ED0
0x180004e78  lea     rcx, aDoworkWaitingF; "DoWork(): Waiting for other service to "...
0x180004e7f  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004e84  cmp     cs:byte_1800707E4, 0
0x180004e8b  jnz     short loc_180004EAC
0x180004e8d  lea     r8, [rbp+arg_10]; bool *
0x180004e91  lea     rcx, ?UNSUPPORTED_NGENServiceWaitWorking@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180004e98  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180004e9d  mov     cs:dword_1800707E0, eax
0x180004ea3  mov     cs:byte_1800707E4, 1
0x180004eaa  jmp     short loc_180004EB2
0x180004eac  mov     eax, cs:dword_1800707E0
0x180004eb2  mov     ecx, eax; this
0x180004eb4  call    ?WaitForNextStateMachineCheck@NGENService@@YAXK@Z; NGENService::WaitForNextStateMachineCheck(ulong)
0x180004eb9  xor     edx, edx; dwMilliseconds
0x180004ebb  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; hHandle
0x180004ec2  call    cs:__imp_WaitForSingleObject
0x180004ec8  test    eax, eax
0x180004eca  jz      loc_180005047
0x180004ed0  mov     ecx, esi
0x180004ed2  call    ?IsOtherServiceDoingHigherPriorityWork@NGENService@@YAHW4__MIDL___MIDL_itf_mscorsvc_0000_0005_0002@@@Z; NGENService::IsOtherServiceDoingHigherPriorityWork(__MIDL___MIDL_itf_mscorsvc_0000_0005_0002)
0x180004ed7  test    eax, eax
0x180004ed9  jnz     short loc_180004E78
0x180004edb  and     [rbp+var_40], eax
0x180004ede  mov     ecx, esi
0x180004ee0  test    esi, esi
0x180004ee2  jz      short loc_180004F12
0x180004ee4  sub     ecx, 1
0x180004ee7  jz      short loc_180004F09
0x180004ee9  sub     ecx, 1
0x180004eec  jz      short loc_180004F00
0x180004eee  cmp     ecx, 1
0x180004ef1  jz      short loc_180004EF7
0x180004ef3  xor     edx, edx
0x180004ef5  jmp     short loc_180004F19
0x180004ef7  lea     rdx, aNgenservicePri_2; "ngenservice_pri3_lock.dat"
0x180004efe  jmp     short loc_180004F19
0x180004f00  lea     rdx, aNgenservicePri_1; "ngenservice_pri2_lock.dat"
0x180004f07  jmp     short loc_180004F19
0x180004f09  lea     rdx, aNgenservicePri; "ngenservice_pri1_lock.dat"
0x180004f10  jmp     short loc_180004F19
0x180004f12  lea     rdx, aNgenservicePri_0; "ngenservice_pri0_lock.dat"
0x180004f19  lea     r9, [rbp+var_40]; int *
0x180004f1d  mov     r8, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; void *
0x180004f24  lea     rcx, [rbp+var_30]; this
0x180004f28  call    ?AcquireNoThrow@FileLockHolder@@QEAAJPEBGPEAXPEAH@Z; FileLockHolder::AcquireNoThrow(ushort const *,void *,int *)
0x180004f2d  test    eax, eax
0x180004f2f  jns     short loc_180004F3D
0x180004f31  lea     rcx, aDoworkFailedTo_0; "DoWork(): Failed to acquire priority lo"...
0x180004f38  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004f3d  cmp     [rbp+var_40], 0
0x180004f41  jnz     loc_180005079
0x180004f47  lea     rbx, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; CriticalSection NGENService::ControllerState::m_csControllerState
0x180004f4e  mov     [rbp+var_20], rbx
0x180004f52  mov     [rbp+var_18], 0
0x180004f56  mov     rcx, rbx; lpCriticalSection
0x180004f59  call    cs:__imp_EnterCriticalSection
0x180004f5f  mov     [rbp+var_18], 1
0x180004f63  mov     cs:?g_currentPriorityLevel@ControllerState@NGENService@@1V?$Volatile@W4__MIDL___MIDL_itf_mscorsvc_0000_0005_0002@@@@A, esi; Volatile<__MIDL___MIDL_itf_mscorsvc_0000_0005_0002> NGENService::ControllerState::g_currentPriorityLevel
0x180004f69  mov     rcx, rbx; lpCriticalSection
0x180004f6c  call    cs:__imp_LeaveCriticalSection
0x180004f72  mov     edx, esi; unsigned __int16 *
0x180004f74  lea     rcx, aProcessingWork; "Processing work for priority %i\n"
0x180004f7b  call    ?Log@NGENService@@YAXPEBGZZ; NGENService::Log(ushort const *,...)
0x180004f80  mov     rax, [rdi]
0x180004f83  mov     r9, cs:?g_bstrInterruptEventName@NGENService@@3PEAGEA; ushort * NGENService::g_bstrInterruptEventName
0x180004f8a  lea     r8, ?g_ProgressNotification@NGENService@@3VControllerCompileProgressNotification@1@A; NGENService::ControllerCompileProgressNotification NGENService::g_ProgressNotification
0x180004f91  mov     edx, r15d
0x180004f94  mov     rcx, rdi
0x180004f97  mov     rax, [rax+20h]
0x180004f9b  call    cs:__guard_dispatch_icall_fptr
0x180004fa1  mov     ecx, eax; this
0x180004fa3  call    ?HandleServiceManagerHR@NGENService@@YAJJ@Z; NGENService::HandleServiceManagerHR(long)
0x180004fa8  mov     ebx, eax
0x180004faa  lea     rax, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; CriticalSection NGENService::ControllerState::m_csControllerState
0x180004fb1  mov     [rbp+var_10], rax
0x180004fb5  mov     [rbp+var_8], 0
0x180004fb9  mov     rcx, rax; lpCriticalSection
0x180004fbc  call    cs:__imp_EnterCriticalSection
0x180004fc2  mov     [rbp+var_8], 1
0x180004fc6  mov     cs:?g_currentPriorityLevel@ControllerState@NGENService@@1V?$Volatile@W4__MIDL___MIDL_itf_mscorsvc_0000_0005_0002@@@@A, r13d; Volatile<__MIDL___MIDL_itf_mscorsvc_0000_0005_0002> NGENService::ControllerState::g_currentPriorityLevel
0x180004fcd  lea     rcx, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; lpCriticalSection
0x180004fd4  call    cs:__imp_LeaveCriticalSection
0x180004fda  test    ebx, ebx
0x180004fdc  js      loc_18000508D
0x180004fe2  lea     rax, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x180004fe9  mov     [rbp+var_30], rax
0x180004fed  mov     rcx, [rbp+hObject]; hObject
0x180004ff1  cmp     rcx, r13
0x180004ff4  jz      short loc_180005000
0x180004ff6  call    cs:__imp_CloseHandle
0x180004ffc  mov     [rbp+hObject], r13
0x180005000  call    ?IsWorkForbiddenUntilReboot@NGENService@@YA_NXZ; NGENService::IsWorkForbiddenUntilReboot(void)
0x180005005  test    al, al
0x180005007  jnz     short loc_180005014
0x180005009  inc     esi
0x18000500b  cmp     esi, r14d
0x18000500e  jle     loc_180004DA0
0x180005014  xor     ebx, ebx
0x180005016  test    rdi, rdi
0x180005019  jz      short loc_180005036
0x18000501b  xor     edx, edx; dwReserved
0x18000501d  mov     rcx, rdi; pUnk
0x180005020  call    cs:__imp_CoDisconnectObject
0x180005026  mov     rcx, [rdi]
0x180005029  mov     rax, [rcx+10h]
0x18000502d  mov     rcx, rdi
0x180005030  call    cs:__guard_dispatch_icall_fptr
0x180005036  mov     eax, ebx
0x180005038  add     rsp, 70h
0x18000503c  pop     r15
0x18000503e  pop     r14
0x180005040  pop     r13
0x180005042  pop     rdi
0x180005043  pop     rsi
0x180005044  pop     rbx
0x180005045  pop     rbp
0x180005046  retn
0x180005047  mov     ebx, 80004005h
0x18000504c  lea     rcx, aDoworkWeWereIn_0; "DoWork(): We were interrupted while wai"...
0x180005053  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180005058  nop
0x180005059  lea     rax, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x180005060  mov     [rbp+var_30], rax
0x180005064  mov     rcx, [rbp+hObject]; hObject
0x180005068  cmp     rcx, r13
0x18000506b  jz      short loc_180005016
0x18000506d  call    cs:__imp_CloseHandle
0x180005073  mov     [rbp+hObject], r13
0x180005077  jmp     short loc_180005016
0x180005079  mov     ebx, 80004005h
0x18000507e  lea     rcx, aDoworkWeWereIn; "DoWork(): We were interrupted while acq"...
0x180005085  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18000508a  nop
0x18000508b  jmp     short loc_180005059
0x18000508d  mov     edx, ebx; unsigned __int16 *
0x18000508f  lea     rcx, aDoworkIcorsvcm; "DoWork(): ICorSvcManager::Work() failed"...
0x180005096  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18000509b  nop
0x18000509c  jmp     short loc_180005059
0x18000509e  mov     edx, eax; unsigned __int16 *
0x1800050a0  lea     rcx, aControlleriswo_0; "ControllerIsWorkAvailable(): ICorSvcMan"...
0x1800050a7  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800050ac  jmp     loc_180005016
```

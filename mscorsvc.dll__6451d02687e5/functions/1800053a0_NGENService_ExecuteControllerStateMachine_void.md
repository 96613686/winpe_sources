# NGENService::ExecuteControllerStateMachine(void)

- ea: `0x1800053a0`
- end: `0x180005688`
- name: `?ExecuteControllerStateMachine@NGENService@@YA_NXZ`
- size: `744`
- prototype: `bool __fastcall(NGENService *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x180005688`

## callees

- `0x180002f44`
- `0x18000352c`
- `0x1800035bc`
- `0x1800036b0`
- `0x180003f08`
- `0x180004cac`
- `0x1800050b4`
- `0x1800053a0`
- `0x18002e1d0`
- `0x18002e418`
- `0x1800366a8`
- `0x180036dfc`
- `0x18003f280`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800053f0`
- `KERNEL32!EnterCriticalSection` at `0x1800053f0`
- `KERNEL32!LeaveCriticalSection` at `0x180005403`
- `KERNEL32!LeaveCriticalSection` at `0x180005403`
- `KERNEL32!WaitForSingleObject` at `0x18000544d`
- `KERNEL32!WaitForSingleObject` at `0x180005565`
- `KERNEL32!WaitForSingleObject` at `0x18000544d`
- `KERNEL32!WaitForSingleObject` at `0x180005565`
- `ole32!CoDisconnectObject` at `0x1800055e4`
- `ole32!CoDisconnectObject` at `0x1800055e4`

## string_xrefs

- `0x18000559a`: `ControllerIsWorkAvailable(): Failed to retrieve service manager\n`
- `0x1800053be`: `Service will shutdown due to a pending reboot\n`
- `0x18000563e`: `NGENServiceWaitAggressiveWork`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall NGENService::ExecuteControllerStateMachine(NGENService *this)
{
  char v2; // di
  int v3; // ebx
  struct ICorSvcManager **v4; // rdx
  __int64 v5; // r9
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  unsigned int ConfigValue; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // ebx
  struct ICorSvcManager **v15; // rdx
  unsigned int ServiceManager; // eax
  const unsigned __int16 *v17; // rdx
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  IUnknown *v20; // rbx
  unsigned int v21; // eax
  const unsigned __int16 *v22; // rdx
  int v23; // eax
  unsigned int v24; // ecx
  unsigned __int64 v25; // rcx
  const unsigned __int16 *v26; // [rsp+20h] [rbp-40h]
  unsigned int v27[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v28; // [rsp+48h] [rbp-18h]
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+50h] [rbp-10h]
  char v30; // [rsp+58h] [rbp-8h]
  __int64 v31; // [rsp+90h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+98h] [rbp+38h] BYREF
  bool v33; // [rsp+A0h] [rbp+40h] BYREF
  bool v34; // [rsp+A8h] [rbp+48h] BYREF

  if ( NGENService::IsWorkForbiddenUntilReboot(this) )
  {
    NGENService::EventLog(
      0,
      (const unsigned __int16 *)4,
      0x458u,
      (unsigned int)L"Service will shutdown due to a pending reboot\n",
      v26);
    return 0;
  }
  v2 = 1;
  v29 = &NGENService::ControllerState::m_csControllerState;
  EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
  v30 = 1;
  v3 = NGENService::ControllerState::m_dwControllerState;
  LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
  if ( !v3 )
  {
    *(_QWORD *)v27 = 0;
    v28 = 0;
    if ( byte_1800707DC )
    {
      v25 = (unsigned int)dword_1800707D8;
    }
    else
    {
      REGUTIL::GetConfigInteger(L"NGENServiceWaitAggressiveWork", 5000, &v31, v5, 7, 1, 0);
      v25 = (unsigned int)v31;
      LODWORD(dword_1800707D8) = v31;
      byte_1800707DC = 1;
    }
    NGENService::ControlStateMachineWaitHelper((NGENService *)v25, (int)v4, (unsigned int)v25 >> 2, 1u, v27);
    return v2;
  }
  v6 = v3 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( !v7 )
    {
      v27[0] = 7;
      if ( byte_1800707EC )
      {
        ConfigValue = dword_1800707E8;
      }
      else
      {
        ConfigValue = CLRConfig::GetConfigValue(
                        (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServicePassiveWorkWaitTimeout,
                        (bool)v4,
                        (bool *)&v31);
        dword_1800707E8 = ConfigValue;
        byte_1800707EC = 1;
      }
      v27[1] = ConfigValue;
      if ( byte_1800707F4 )
      {
        v11 = dword_1800707F0;
      }
      else
      {
        v11 = CLRConfig::GetConfigValue(
                (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServicePassiveHardDiskIdleTimeout,
                (bool)v4,
                (bool *)&pUnk);
        dword_1800707F0 = v11;
        byte_1800707F4 = 1;
      }
      HIDWORD(v28) = v11;
      if ( byte_1800707FC )
      {
        v12 = dword_1800707F8;
      }
      else
      {
        v12 = CLRConfig::GetConfigValue(
                (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServicePassiveExceptInputTimeout,
                (bool)v4,
                &v33);
        dword_1800707F8 = v12;
        byte_1800707FC = 1;
      }
      LODWORD(v28) = v12;
      if ( byte_1800707D4 )
      {
        v13 = dword_1800707D0;
      }
      else
      {
        v13 = CLRConfig::GetConfigValue(
                (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServiceWaitPassiveWork,
                (bool)v4,
                &v34);
        dword_1800707D0 = v13;
        byte_1800707D4 = 1;
      }
      NGENService::ControlStateMachineWaitHelper((NGENService *)v13, (int)v4, v13 >> 2, 3u, v27);
      return v2;
    }
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 == 1 )
      {
        NGENService::ControllerState::SetAccumulatedWaitIdleTime(0);
        return 0;
      }
      return v2;
    }
    v9 = NGENService::DoWork(3, v4);
    if ( !WaitForSingleObject(NGENService::g_hInterruptEvent, 0) || v9 < 0 )
      return v2;
  }
  else
  {
    v14 = NGENService::DoWork(2, v4);
    if ( !WaitForSingleObject(NGENService::g_hInterruptEvent, 0) || v14 < 0 )
      return v2;
    LODWORD(v31) = 1;
    pUnk = 0;
    ServiceManager = NGENService::GetServiceManager((NGENService *)&pUnk, v15);
    v18 = NGENService::HandleServiceManagerHR((NGENService *)ServiceManager, v17);
    v20 = pUnk;
    if ( v18 >= 0 )
    {
      v21 = ((__int64 (__fastcall *)(LPUNKNOWN, __int64, __int64 *))pUnk->lpVtbl[2].QueryInterface)(pUnk, 3, &v31);
      v23 = NGENService::HandleServiceManagerHR((NGENService *)v21, v22);
      if ( v23 < 0 )
        NGENService::DebugLog(
          (NGENService *)L"ControllerIsWorkAvailable(): ICorSvcManager::IsWorkAvailable() failed(). Returned HR=0x%08x\n",
          (const unsigned __int16 *)(unsigned int)v23);
    }
    else
    {
      NGENService::DebugLog((NGENService *)L"ControllerIsWorkAvailable(): Failed to retrieve service manager\n", v19);
    }
    if ( v20 )
    {
      CoDisconnectObject(v20, 0);
      ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
    }
    v24 = 2;
    if ( (_DWORD)v31 )
      goto LABEL_35;
  }
  v24 = 4;
LABEL_35:
  NGENService::ControllerState::Set(v24, 7u);
  return v2;
}

```

## disassembly

```asm
0x1800053a0  push    rbp
0x1800053a2  push    rbx
0x1800053a3  push    rsi
0x1800053a4  push    rdi
0x1800053a5  push    r14
0x1800053a7  mov     rbp, rsp
0x1800053aa  sub     rsp, 60h
0x1800053ae  call    ?IsWorkForbiddenUntilReboot@NGENService@@YA_NXZ; NGENService::IsWorkForbiddenUntilReboot(void)
0x1800053b3  xor     r14d, r14d
0x1800053b6  test    al, al
0x1800053b8  jz      short loc_1800053D9
0x1800053ba  lea     edx, [r14+4]; unsigned __int16 *
0x1800053be  lea     r9, aServiceWillShu; "Service will shutdown due to a pending "...
0x1800053c5  xor     ecx, ecx; this
0x1800053c7  mov     r8d, 458h; unsigned __int16
0x1800053cd  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x1800053d2  xor     al, al
0x1800053d4  jmp     loc_18000567D
0x1800053d9  mov     edi, 1
0x1800053de  lea     rsi, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; CriticalSection NGENService::ControllerState::m_csControllerState
0x1800053e5  mov     [rbp+var_10], rsi
0x1800053e9  mov     [rbp+var_8], r14b
0x1800053ed  mov     rcx, rsi; lpCriticalSection
0x1800053f0  call    cs:__imp_EnterCriticalSection
0x1800053f6  mov     [rbp+var_8], dil
0x1800053fa  mov     ebx, cs:?m_dwControllerState@ControllerState@NGENService@@1V?$Volatile@K@@A; Volatile<ulong> NGENService::ControllerState::m_dwControllerState
0x180005400  mov     rcx, rsi; lpCriticalSection
0x180005403  call    cs:__imp_LeaveCriticalSection
0x180005409  test    ebx, ebx
0x18000540b  jz      loc_180005613
0x180005411  sub     ebx, edi
0x180005413  jz      loc_18000554E
0x180005419  sub     ebx, edi
0x18000541b  jz      short loc_18000546D
0x18000541d  sub     ebx, edi
0x18000541f  jz      short loc_180005438
0x180005421  cmp     ebx, edi
0x180005423  jnz     loc_18000567A
0x180005429  xor     ecx, ecx; unsigned int
0x18000542b  call    ?SetAccumulatedWaitIdleTime@ControllerState@NGENService@@SAJK@Z; NGENService::ControllerState::SetAccumulatedWaitIdleTime(ulong)
0x180005430  mov     dil, r14b
0x180005433  jmp     loc_18000567A
0x180005438  mov     ecx, 3
0x18000543d  call    ?DoWork@NGENService@@YAJW4__MIDL___MIDL_itf_mscorsvc_0000_0005_0002@@@Z; NGENService::DoWork(__MIDL___MIDL_itf_mscorsvc_0000_0005_0002)
0x180005442  mov     ebx, eax
0x180005444  xor     edx, edx; dwMilliseconds
0x180005446  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; hHandle
0x18000544d  call    cs:__imp_WaitForSingleObject
0x180005453  test    eax, eax
0x180005455  jz      loc_18000567A
0x18000545b  test    ebx, ebx
0x18000545d  js      loc_18000567A
0x180005463  mov     edx, 7
0x180005468  jmp     loc_180005607
0x18000546d  mov     [rbp+var_20], 7
0x180005474  cmp     cs:byte_1800707EC, r14b
0x18000547b  jnz     short loc_18000549C
0x18000547d  lea     r8, [rbp+arg_0]; bool *
0x180005481  lea     rcx, ?UNSUPPORTED_NGENServicePassiveWorkWaitTimeout@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180005488  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18000548d  mov     cs:dword_1800707E8, eax
0x180005493  mov     cs:byte_1800707EC, dil
0x18000549a  jmp     short loc_1800054A2
0x18000549c  mov     eax, cs:dword_1800707E8
0x1800054a2  mov     [rbp+var_20+4], eax
0x1800054a5  cmp     cs:byte_1800707F4, r14b
0x1800054ac  jnz     short loc_1800054CD
0x1800054ae  lea     r8, [rbp+pUnk]; bool *
0x1800054b2  lea     rcx, ?UNSUPPORTED_NGENServicePassiveHardDiskIdleTimeout@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x1800054b9  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x1800054be  mov     cs:dword_1800707F0, eax
0x1800054c4  mov     cs:byte_1800707F4, dil
0x1800054cb  jmp     short loc_1800054D3
0x1800054cd  mov     eax, cs:dword_1800707F0
0x1800054d3  mov     dword ptr [rbp+var_18+4], eax
0x1800054d6  cmp     cs:byte_1800707FC, r14b
0x1800054dd  jnz     short loc_1800054FE
0x1800054df  lea     r8, [rbp+arg_10]; bool *
0x1800054e3  lea     rcx, ?UNSUPPORTED_NGENServicePassiveExceptInputTimeout@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x1800054ea  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x1800054ef  mov     cs:dword_1800707F8, eax
0x1800054f5  mov     cs:byte_1800707FC, dil
0x1800054fc  jmp     short loc_180005504
0x1800054fe  mov     eax, cs:dword_1800707F8
0x180005504  mov     dword ptr [rbp+var_18], eax
0x180005507  cmp     cs:byte_1800707D4, r14b
0x18000550e  jnz     short loc_18000552F
0x180005510  lea     r8, [rbp+arg_18]; bool *
0x180005514  lea     rcx, ?UNSUPPORTED_NGENServiceWaitPassiveWork@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18000551b  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180005520  mov     cs:dword_1800707D0, eax
0x180005526  mov     cs:byte_1800707D4, dil
0x18000552d  jmp     short loc_180005535
0x18000552f  mov     eax, cs:dword_1800707D0
0x180005535  mov     r8d, eax
0x180005538  lea     rcx, [rbp+var_20]
0x18000553c  mov     qword ptr [rsp+60h+var_40], rcx
0x180005541  mov     r9d, 3
0x180005547  mov     ecx, eax
0x180005549  jmp     loc_180005671
0x18000554e  mov     esi, 2
0x180005553  mov     ecx, esi
0x180005555  call    ?DoWork@NGENService@@YAJW4__MIDL___MIDL_itf_mscorsvc_0000_0005_0002@@@Z; NGENService::DoWork(__MIDL___MIDL_itf_mscorsvc_0000_0005_0002)
0x18000555a  mov     ebx, eax
0x18000555c  xor     edx, edx; dwMilliseconds
0x18000555e  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; hHandle
0x180005565  call    cs:__imp_WaitForSingleObject
0x18000556b  test    eax, eax
0x18000556d  jz      loc_18000567A
0x180005573  test    ebx, ebx
0x180005575  js      loc_18000567A
0x18000557b  mov     dword ptr [rbp+arg_0], edi
0x18000557e  mov     [rbp+pUnk], r14
0x180005582  lea     rcx, [rbp+pUnk]; this
0x180005586  call    ?GetServiceManager@NGENService@@YAJPEAPEAUICorSvcManager@@@Z; NGENService::GetServiceManager(ICorSvcManager * *)
0x18000558b  mov     ecx, eax; this
0x18000558d  call    ?HandleServiceManagerHR@NGENService@@YAJJ@Z; NGENService::HandleServiceManagerHR(long)
0x180005592  mov     rbx, [rbp+pUnk]
0x180005596  test    eax, eax
0x180005598  jns     short loc_1800055A8
0x18000559a  lea     rcx, aControlleriswo; "ControllerIsWorkAvailable(): Failed to "...
0x1800055a1  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800055a6  jmp     short loc_1800055DA
0x1800055a8  mov     rax, [rbx]
0x1800055ab  lea     r8, [rbp+arg_0]
0x1800055af  mov     edx, 3
0x1800055b4  mov     rcx, rbx
0x1800055b7  mov     rax, [rax+30h]
0x1800055bb  call    cs:__guard_dispatch_icall_fptr
0x1800055c1  mov     ecx, eax; this
0x1800055c3  call    ?HandleServiceManagerHR@NGENService@@YAJJ@Z; NGENService::HandleServiceManagerHR(long)
0x1800055c8  test    eax, eax
0x1800055ca  jns     short loc_1800055DA
0x1800055cc  mov     edx, eax; unsigned __int16 *
0x1800055ce  lea     rcx, aControlleriswo_0; "ControllerIsWorkAvailable(): ICorSvcMan"...
0x1800055d5  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800055da  test    rbx, rbx
0x1800055dd  jz      short loc_1800055FA
0x1800055df  xor     edx, edx; dwReserved
0x1800055e1  mov     rcx, rbx; pUnk
0x1800055e4  call    cs:__imp_CoDisconnectObject
0x1800055ea  mov     rax, [rbx]
0x1800055ed  mov     rcx, rbx
0x1800055f0  mov     rax, [rax+10h]
0x1800055f4  call    cs:__guard_dispatch_icall_fptr
0x1800055fa  mov     edx, 7; unsigned int
0x1800055ff  cmp     dword ptr [rbp+arg_0], r14d
0x180005603  mov     ecx, esi
0x180005605  jnz     short loc_18000560C
0x180005607  mov     ecx, 4; unsigned int
0x18000560c  call    ?Set@ControllerState@NGENService@@SAXKK@Z; NGENService::ControllerState::Set(ulong,ulong)
0x180005611  jmp     short loc_18000567A
0x180005613  mov     qword ptr [rbp+var_20], r14
0x180005617  mov     [rbp+var_18], r14
0x18000561b  cmp     cs:byte_1800707DC, r14b
0x180005622  jnz     short loc_18000565C
0x180005624  mov     [rsp+60h+var_30], r14d
0x180005629  mov     [rsp+60h+var_38], edi
0x18000562d  mov     [rsp+60h+var_40], 7
0x180005635  lea     r8, [rbp+arg_0]
0x180005639  mov     edx, 1388h
0x18000563e  lea     rcx, aNgenservicewai_1; "NGENServiceWaitAggressiveWork"
0x180005645  call    ?GetConfigInteger@REGUTIL@@CAJPEBG_KPEA_KHW4CORConfigLevel@1@HH@Z; REGUTIL::GetConfigInteger(ushort const *,unsigned __int64,unsigned __int64 *,int,REGUTIL::CORConfigLevel,int,int)
0x18000564a  mov     ecx, dword ptr [rbp+arg_0]
0x18000564d  mov     cs:dword_1800707D8, ecx
0x180005653  mov     cs:byte_1800707DC, dil
0x18000565a  jmp     short loc_180005662
0x18000565c  mov     ecx, cs:dword_1800707D8; this
0x180005662  mov     r8d, ecx
0x180005665  lea     rax, [rbp+var_20]
0x180005669  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x18000566e  mov     r9d, edi; unsigned int
0x180005671  shr     r8d, 2; int
0x180005675  call    ?ControlStateMachineWaitHelper@NGENService@@YAXKHKKPEAUIdleConsiderations@1@@Z; NGENService::ControlStateMachineWaitHelper(ulong,int,ulong,ulong,NGENService::IdleConsiderations *)
0x18000567a  mov     al, dil
0x18000567d  add     rsp, 60h
0x180005681  pop     r14
0x180005683  pop     rdi
0x180005684  pop     rsi
0x180005685  pop     rbx
0x180005686  pop     rbp
0x180005687  retn
```

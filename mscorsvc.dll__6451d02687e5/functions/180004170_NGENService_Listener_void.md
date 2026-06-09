# NGENService::Listener(void *)

- ea: `0x180004170`
- end: `0x18000457e`
- name: `?Listener@NGENService@@YAKPEAX@Z`
- size: `1038`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callees

- `0x180004078`
- `0x1800040e8`
- `0x180004170`
- `0x180006238`
- `0x180007130`
- `0x180007518`
- `0x18002e1d0`
- `0x1800366a8`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800041c4`
- `KERNEL32!EnterCriticalSection` at `0x1800041e6`
- `KERNEL32!EnterCriticalSection` at `0x18000424f`
- `KERNEL32!EnterCriticalSection` at `0x1800042ae`
- `KERNEL32!EnterCriticalSection` at `0x1800043c3`
- `KERNEL32!EnterCriticalSection` at `0x1800041c4`
- `KERNEL32!EnterCriticalSection` at `0x1800041e6`
- `KERNEL32!EnterCriticalSection` at `0x18000424f`
- `KERNEL32!EnterCriticalSection` at `0x1800042ae`
- `KERNEL32!EnterCriticalSection` at `0x1800043c3`
- `KERNEL32!LeaveCriticalSection` at `0x1800041f9`
- `KERNEL32!LeaveCriticalSection` at `0x180004262`
- `KERNEL32!LeaveCriticalSection` at `0x180004304`
- `KERNEL32!LeaveCriticalSection` at `0x1800043d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800043fa`
- `KERNEL32!LeaveCriticalSection` at `0x1800041f9`
- `KERNEL32!LeaveCriticalSection` at `0x180004262`
- `KERNEL32!LeaveCriticalSection` at `0x180004304`
- `KERNEL32!LeaveCriticalSection` at `0x1800043d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800043fa`
- `KERNEL32!ResetEvent` at `0x1800041d5`
- `KERNEL32!ResetEvent` at `0x180004234`
- `KERNEL32!ResetEvent` at `0x1800041d5`
- `KERNEL32!ResetEvent` at `0x180004234`
- `KERNEL32!WaitForSingleObject` at `0x180004208`
- `KERNEL32!WaitForSingleObject` at `0x180004223`
- `KERNEL32!WaitForSingleObject` at `0x1800044e6`
- `KERNEL32!WaitForSingleObject` at `0x180004208`
- `KERNEL32!WaitForSingleObject` at `0x180004223`
- `KERNEL32!WaitForSingleObject` at `0x1800044e6`
- `KERNEL32!WaitForMultipleObjects` at `0x18000447f`
- `KERNEL32!WaitForMultipleObjects` at `0x180004521`
- `KERNEL32!WaitForMultipleObjects` at `0x18000447f`
- `KERNEL32!WaitForMultipleObjects` at `0x180004521`
- `KERNEL32!IsDebuggerPresent` at `0x18000431e`
- `KERNEL32!IsDebuggerPresent` at `0x18000431e`

## string_xrefs

- `0x1800044ad`: `	: Listener thread shutting down\n`
- `0x180004530`: `	: Listener thread shutting down\n`
- `0x18000427a`: `ngenserviceclientlock.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NGENService::Listener(LPVOID lpThreadParameter)
{
  int v1; // edi
  int v2; // ebx
  char v3; // si
  unsigned int v4; // ebx
  struct SYSTEM_SNAPSHOT *v5; // rdx
  unsigned int *v6; // r9
  const unsigned __int16 *v7; // rdx
  char v8; // bl
  const unsigned __int16 *v9; // rdx
  bool v10; // dl
  unsigned int v11; // eax
  unsigned int v12; // eax
  int v13; // ebx
  bool v14; // dl
  DWORD ConfigValue; // edi
  DWORD v16; // ebx
  const unsigned __int16 *v17; // rdx
  DWORD v18; // ebx
  DWORD v19; // ebx
  DWORD v20; // ebx
  wchar_t *v21; // rcx
  const unsigned __int16 *v22; // rdx
  DWORD v23; // eax
  const unsigned __int16 *v24; // rdx
  wchar_t *v25; // rcx
  bool v27; // [rsp+28h] [rbp-59h] BYREF
  bool v28; // [rsp+29h] [rbp-58h] BYREF
  bool v29; // [rsp+2Ah] [rbp-57h] BYREF
  int v30; // [rsp+2Ch] [rbp-55h] BYREF
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+30h] [rbp-51h]
  char v32; // [rsp+38h] [rbp-49h]
  struct _RTL_CRITICAL_SECTION *v33; // [rsp+40h] [rbp-41h]
  char v34; // [rsp+48h] [rbp-39h]
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+50h] [rbp-31h]
  char v36; // [rsp+58h] [rbp-29h]
  struct _RTL_CRITICAL_SECTION *v37; // [rsp+60h] [rbp-21h]
  char v38; // [rsp+68h] [rbp-19h]
  struct _RTL_CRITICAL_SECTION *v39; // [rsp+70h] [rbp-11h]
  char v40; // [rsp+78h] [rbp-9h]
  HANDLE v41[2]; // [rsp+80h] [rbp-1h] BYREF
  HANDLE Handles; // [rsp+90h] [rbp+Fh] BYREF
  HANDLE v43; // [rsp+98h] [rbp+17h]
  HANDLE v44; // [rsp+A0h] [rbp+1Fh]
  HANDLE v45; // [rsp+A8h] [rbp+27h]
  HANDLE v46; // [rsp+B0h] [rbp+2Fh]

  if ( !NGENService::g_bStopEventListener )
  {
    while ( 1 )
    {
      v31 = &NGENService::ControllerState::m_csControllerState;
      v32 = 0;
      EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
      v32 = 1;
      ResetEvent(NGENService::g_hControllerStateChange);
      v33 = &NGENService::ControllerState::m_csControllerState;
      v34 = 0;
      EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
      v34 = 1;
      v1 = NGENService::ControllerState::m_dwControllerState;
      LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
      if ( !WaitForSingleObject(NGENService::g_hRootStoreDirtyEvent, 0) )
        NGENService::ControllerInterrupt(8);
      if ( !WaitForSingleObject(NGENService::g_hSCMRequestEvent, 0) )
      {
        ResetEvent(NGENService::g_hSCMRequestEvent);
        NGENService::ControllerInterrupt(1);
      }
      v35 = &NGENService::ControllerState::m_csControllerState;
      v36 = 0;
      EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
      v36 = 1;
      v2 = NGENService::ControllerState::m_dwControllerState;
      LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
      if ( ((v2 - 1) & 0xFFFFFFFD) != 0 )
      {
        v3 = 0;
      }
      else
      {
        v3 = 1;
        if ( (unsigned int)MachineWideMutexHolder::IsTaken(L"ngenserviceclientlock.dat") )
          NGENService::ControllerInterrupt(2);
      }
      if ( v1 == 3 )
        break;
LABEL_33:
      v39 = &NGENService::ControllerState::m_csControllerState;
      v40 = 0;
      EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
      v40 = 1;
      v13 = NGENService::ControllerState::g_currentPriorityLevel;
      LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
      if ( v13 != -1 && (unsigned int)NGENService::IsOtherServiceDoingHigherPriorityWork(v13) )
        NGENService::ControllerInterrupt(16);
      LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
      if ( v3 )
      {
        if ( byte_1800707E4 )
        {
          ConfigValue = dword_1800707E0;
        }
        else
        {
          ConfigValue = CLRConfig::GetConfigValue(
                          (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServiceWaitWorking,
                          v14,
                          &v29);
          dword_1800707E0 = ConfigValue;
          byte_1800707E4 = 1;
        }
      }
      else
      {
        ConfigValue = -1;
      }
      Handles = NGENService::g_hInterruptEvent;
      v43 = NGENService::g_hRootStoreDirtyEvent;
      v44 = NGENService::g_hSCMRequestEvent;
      v45 = NGENService::g_hControllerStateChange;
      v46 = NGENService::g_hListenerShutdownEvent;
      v16 = WaitForMultipleObjects(5u, &Handles, 0, ConfigValue);
      NGENService::DebugLog(
        (NGENService *)L"WaitForNextListenerCheck(): Waiting for %i ms\n",
        (const unsigned __int16 *)ConfigValue);
      if ( v16 )
      {
        v18 = v16 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              if ( v20 != 1 )
                goto LABEL_52;
              v21 = L"\t: Listener thread shutting down\n";
            }
            else
            {
              v21 = L"\t: Exiting due to controller state change\n";
            }
          }
          else
          {
            v21 = L"\t: Exiting due to SCM request event\n";
          }
        }
        else
        {
          v21 = L"\t: Exiting due to dirty root store event\n";
        }
      }
      else
      {
        v21 = L"\t: Interrupts dispatched. Listener will wait until they're processed\n";
      }
      NGENService::DebugLog((NGENService *)v21, v17);
LABEL_52:
      if ( !WaitForSingleObject(NGENService::g_hInterruptEvent, 0) )
      {
        v41[0] = NGENService::g_hInterruptProcessedEvent;
        v41[1] = NGENService::g_hListenerShutdownEvent;
        NGENService::DebugLog((NGENService *)L"WaitForInterruptProcessedEvent()\n", v22);
        v23 = WaitForMultipleObjects(2u, v41, 0, 0xFFFFFFFF);
        if ( !v23 )
        {
          v25 = L"\t: Interrupts were processed, continuing\n";
          goto LABEL_57;
        }
        if ( v23 == 1 )
        {
          v25 = L"\t: Listener thread shutting down\n";
LABEL_57:
          NGENService::DebugLog((NGENService *)v25, v24);
        }
      }
      if ( NGENService::g_bStopEventListener )
        return 0;
    }
    v4 = (unsigned int)NGENService::ControllerState::m_dwIdleConsiderations;
    v37 = &NGENService::g_IdleCS;
    v38 = 0;
    EnterCriticalSection(&NGENService::g_IdleCS);
    v38 = 1;
    NGENService::GetSystemSnapshot((struct _SYSTEM_POWER_STATUS *)&Handles, v5);
    v30 = 0;
    if ( NGENService::IdleWorkIsForbidden((NGENService *)v4, (unsigned int)&Handles, (struct SYSTEM_SNAPSHOT *)&v30, v6) )
      goto LABEL_12;
    if ( (BYTE4(Handles) & 0x40) != 0 && SBYTE4(Handles) < 0 && !(_DWORD)v46 && HIDWORD(v45) )
    {
      NGENService::DebugLog((NGENService *)L"IdleWorkAlways returns true: System is running screensaver.\n", v7);
    }
    else if ( (v4 & 2) != 0 )
    {
      if ( (BYTE4(Handles) & 1) == 0
        || (byte_180070804
          ? (v12 = dword_180070800)
          : (v12 = CLRConfig::GetConfigValue(
                     (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServiceIdleNoInputPeriod,
                     (bool)v7,
                     &v27),
             dword_180070800 = v12,
             byte_180070804 = 1),
            (unsigned int)v43 < v12) )
      {
        NGENService::DebugLog(
          (NGENService *)L"ContinueIdleWork() returns false: Input has happened or LastInput not available.\n",
          v7);
LABEL_12:
        v8 = 0;
LABEL_19:
        LeaveCriticalSection(&NGENService::g_IdleCS);
        if ( !v8 )
        {
          NGENService::DebugLog((NGENService *)L"Listener(): ShouldContinueIdleWork() returned false\n", v9);
          if ( !IsDebuggerPresent()
            || (byte_180070834
              ? (v11 = dword_180070830)
              : (v11 = CLRConfig::GetConfigValue(
                         (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::INTERNAL_NGENServiceAbortIdleWorkUnderDebugger,
                         v10,
                         &v28),
                 dword_180070830 = v11,
                 byte_180070834 = 1),
                v11) )
          {
            NGENService::ControllerInterrupt(4);
          }
        }
        goto LABEL_33;
      }
    }
    v8 = 1;
    goto LABEL_19;
  }
  return 0;
}

```

## disassembly

```asm
0x180004170  mov     rax, rsp
0x180004173  mov     [rax+8], rbx
0x180004177  mov     [rax+10h], rsi
0x18000417b  mov     [rax+18h], rdi
0x18000417f  push    rbp
0x180004180  push    r13
0x180004182  push    r15
0x180004184  lea     rbp, [rax-5Fh]
0x180004188  sub     rsp, 0C0h
0x18000418f  mov     rax, cs:__security_cookie
0x180004196  xor     rax, rsp
0x180004199  mov     [rbp+57h+var_20], rax
0x18000419d  mov     al, cs:?g_bStopEventListener@NGENService@@3V?$Volatile@_N@@A; Volatile<bool> NGENService::g_bStopEventListener
0x1800041a3  test    al, al
0x1800041a5  jnz     loc_180004553
0x1800041ab  lea     r15, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; CriticalSection NGENService::ControllerState::m_csControllerState
0x1800041b2  lea     r13, ?g_IdleCS@NGENService@@3VCriticalSection@@A; CriticalSection NGENService::g_IdleCS
0x1800041b9  mov     [rbp+57h+var_A8], r15
0x1800041bd  mov     [rbp+57h+var_A0], 0
0x1800041c1  mov     rcx, r15; lpCriticalSection
0x1800041c4  call    cs:__imp_EnterCriticalSection
0x1800041ca  mov     [rbp+57h+var_A0], 1
0x1800041ce  mov     rcx, cs:?g_hControllerStateChange@NGENService@@3PEAXEA; hEvent
0x1800041d5  call    cs:__imp_ResetEvent
0x1800041db  mov     [rbp+57h+var_98], r15
0x1800041df  mov     [rbp+57h+var_90], 0
0x1800041e3  mov     rcx, r15; lpCriticalSection
0x1800041e6  call    cs:__imp_EnterCriticalSection
0x1800041ec  mov     [rbp+57h+var_90], 1
0x1800041f0  mov     edi, cs:?m_dwControllerState@ControllerState@NGENService@@1V?$Volatile@K@@A; Volatile<ulong> NGENService::ControllerState::m_dwControllerState
0x1800041f6  mov     rcx, r15; lpCriticalSection
0x1800041f9  call    cs:__imp_LeaveCriticalSection
0x1800041ff  xor     edx, edx; dwMilliseconds
0x180004201  mov     rcx, cs:?g_hRootStoreDirtyEvent@NGENService@@3PEAXEA; hHandle
0x180004208  call    cs:__imp_WaitForSingleObject
0x18000420e  test    eax, eax
0x180004210  jnz     short loc_18000421A
0x180004212  lea     ecx, [rax+8]
0x180004215  call    ?ControllerInterrupt@NGENService@@YAXW4InterruptReason@1@@Z; NGENService::ControllerInterrupt(NGENService::InterruptReason)
0x18000421a  xor     edx, edx; dwMilliseconds
0x18000421c  mov     rcx, cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA; hHandle
0x180004223  call    cs:__imp_WaitForSingleObject
0x180004229  test    eax, eax
0x18000422b  jnz     short loc_180004244
0x18000422d  mov     rcx, cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA; hEvent
0x180004234  call    cs:__imp_ResetEvent
0x18000423a  mov     ecx, 1
0x18000423f  call    ?ControllerInterrupt@NGENService@@YAXW4InterruptReason@1@@Z; NGENService::ControllerInterrupt(NGENService::InterruptReason)
0x180004244  mov     [rbp+57h+var_88], r15
0x180004248  mov     [rbp+57h+var_80], 0
0x18000424c  mov     rcx, r15; lpCriticalSection
0x18000424f  call    cs:__imp_EnterCriticalSection
0x180004255  mov     [rbp+57h+var_80], 1
0x180004259  mov     ebx, cs:?m_dwControllerState@ControllerState@NGENService@@1V?$Volatile@K@@A; Volatile<ulong> NGENService::ControllerState::m_dwControllerState
0x18000425f  mov     rcx, r15; lpCriticalSection
0x180004262  call    cs:__imp_LeaveCriticalSection
0x180004268  lea     eax, [rbx-1]
0x18000426b  test    eax, 0FFFFFFFDh
0x180004270  jz      short loc_180004277
0x180004272  xor     sil, sil
0x180004275  jmp     short loc_180004294
0x180004277  mov     sil, 1
0x18000427a  lea     rcx, aNgenservicecli; "ngenserviceclientlock.dat"
0x180004281  call    ?IsTaken@MachineWideMutexHolder@@SAHPEBG@Z; MachineWideMutexHolder::IsTaken(ushort const *)
0x180004286  test    eax, eax
0x180004288  jz      short loc_180004294
0x18000428a  mov     ecx, 2
0x18000428f  call    ?ControllerInterrupt@NGENService@@YAXW4InterruptReason@1@@Z; NGENService::ControllerInterrupt(NGENService::InterruptReason)
0x180004294  cmp     edi, 3
0x180004297  jnz     loc_1800043B8
0x18000429d  mov     ebx, cs:?m_dwIdleConsiderations@ControllerState@NGENService@@1V?$Volatile@K@@A; Volatile<ulong> NGENService::ControllerState::m_dwIdleConsiderations
0x1800042a3  mov     [rbp+57h+var_78], r13
0x1800042a7  mov     [rbp+57h+var_70], 0
0x1800042ab  mov     rcx, r13; lpCriticalSection
0x1800042ae  call    cs:__imp_EnterCriticalSection
0x1800042b4  mov     [rbp+57h+var_70], 1
0x1800042b8  lea     rcx, [rbp+57h+Handles]; this
0x1800042bc  call    ?GetSystemSnapshot@NGENService@@YAXPEAUSYSTEM_SNAPSHOT@@K@Z; NGENService::GetSystemSnapshot(SYSTEM_SNAPSHOT *,ulong)
0x1800042c1  and     [rbp+57h+var_AC], 0
0x1800042c5  lea     r8, [rbp+57h+var_AC]; struct SYSTEM_SNAPSHOT *
0x1800042c9  lea     rdx, [rbp+57h+Handles]; unsigned int
0x1800042cd  mov     ecx, ebx; this
0x1800042cf  call    ?IdleWorkIsForbidden@NGENService@@YA_NKPEAUSYSTEM_SNAPSHOT@@PEAK@Z; NGENService::IdleWorkIsForbidden(ulong,SYSTEM_SNAPSHOT *,ulong *)
0x1800042d4  test    al, al
0x1800042d6  jz      short loc_1800042DC
0x1800042d8  xor     bl, bl
0x1800042da  jmp     short loc_180004301
0x1800042dc  mov     eax, dword ptr [rbp+57h+Handles+4]
0x1800042df  test    al, 40h
0x1800042e1  jz      short loc_180004353
0x1800042e3  test    al, al
0x1800042e5  jns     short loc_180004353
0x1800042e7  cmp     dword ptr [rbp+57h+var_28], 0
0x1800042eb  jnz     short loc_180004353
0x1800042ed  cmp     [rbp+57h+var_2C], 0
0x1800042f1  jz      short loc_180004353
0x1800042f3  lea     rcx, aIdleworkalways; "IdleWorkAlways returns true: System is "...
0x1800042fa  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800042ff  mov     bl, 1
0x180004301  mov     rcx, r13; lpCriticalSection
0x180004304  call    cs:__imp_LeaveCriticalSection
0x18000430a  test    bl, bl
0x18000430c  jnz     loc_1800043B8
0x180004312  lea     rcx, aListenerShould; "Listener(): ShouldContinueIdleWork() re"...
0x180004319  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18000431e  call    cs:__imp_IsDebuggerPresent
0x180004324  test    eax, eax
0x180004326  jz      loc_1800043AE
0x18000432c  cmp     cs:byte_180070834, bl
0x180004332  jnz     short loc_1800043A4
0x180004334  lea     r8, [rbp+57h+var_AF]; bool *
0x180004338  lea     rcx, ?INTERNAL_NGENServiceAbortIdleWorkUnderDebugger@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18000433f  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180004344  mov     cs:dword_180070830, eax
0x18000434a  mov     cs:byte_180070834, 1
0x180004351  jmp     short loc_1800043AA
0x180004353  test    bl, 2
0x180004356  jz      short loc_1800042FF
0x180004358  test    al, 1
0x18000435a  jz      short loc_180004393
0x18000435c  cmp     cs:byte_180070804, 0
0x180004363  jnz     short loc_180004384
0x180004365  lea     r8, [rbp+57h+var_B0]; bool *
0x180004369  lea     rcx, ?UNSUPPORTED_NGENServiceIdleNoInputPeriod@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180004370  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180004375  mov     cs:dword_180070800, eax
0x18000437b  mov     cs:byte_180070804, 1
0x180004382  jmp     short loc_18000438A
0x180004384  mov     eax, cs:dword_180070800
0x18000438a  cmp     dword ptr [rbp+57h+var_40], eax
0x18000438d  jnb     loc_1800042FF
0x180004393  lea     rcx, aContinueidlewo; "ContinueIdleWork() returns false: Input"...
0x18000439a  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18000439f  jmp     loc_1800042D8
0x1800043a4  mov     eax, cs:dword_180070830
0x1800043aa  test    eax, eax
0x1800043ac  jz      short loc_1800043B8
0x1800043ae  mov     ecx, 4
0x1800043b3  call    ?ControllerInterrupt@NGENService@@YAXW4InterruptReason@1@@Z; NGENService::ControllerInterrupt(NGENService::InterruptReason)
0x1800043b8  mov     [rbp+57h+var_68], r15
0x1800043bc  mov     [rbp+57h+var_60], 0
0x1800043c0  mov     rcx, r15; lpCriticalSection
0x1800043c3  call    cs:__imp_EnterCriticalSection
0x1800043c9  mov     [rbp+57h+var_60], 1
0x1800043cd  mov     ebx, cs:?g_currentPriorityLevel@ControllerState@NGENService@@1V?$Volatile@W4__MIDL___MIDL_itf_mscorsvc_0000_0005_0002@@@@A; Volatile<__MIDL___MIDL_itf_mscorsvc_0000_0005_0002> NGENService::ControllerState::g_currentPriorityLevel
0x1800043d3  mov     rcx, r15; lpCriticalSection
0x1800043d6  call    cs:__imp_LeaveCriticalSection
0x1800043dc  cmp     ebx, 0FFFFFFFFh
0x1800043df  jz      short loc_1800043F7
0x1800043e1  mov     ecx, ebx
0x1800043e3  call    ?IsOtherServiceDoingHigherPriorityWork@NGENService@@YAHW4__MIDL___MIDL_itf_mscorsvc_0000_0005_0002@@@Z; NGENService::IsOtherServiceDoingHigherPriorityWork(__MIDL___MIDL_itf_mscorsvc_0000_0005_0002)
0x1800043e8  test    eax, eax
0x1800043ea  jz      short loc_1800043F7
0x1800043ec  mov     ecx, 10h
0x1800043f1  call    ?ControllerInterrupt@NGENService@@YAXW4InterruptReason@1@@Z; NGENService::ControllerInterrupt(NGENService::InterruptReason)
0x1800043f6  nop
0x1800043f7  mov     rcx, r15; lpCriticalSection
0x1800043fa  call    cs:__imp_LeaveCriticalSection
0x180004400  test    sil, sil
0x180004403  jz      short loc_180004437
0x180004405  cmp     cs:byte_1800707E4, 0
0x18000440c  jnz     short loc_18000442F
0x18000440e  lea     r8, [rbp+57h+var_AE]; bool *
0x180004412  lea     rcx, ?UNSUPPORTED_NGENServiceWaitWorking@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180004419  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18000441e  mov     edi, eax
0x180004420  mov     cs:dword_1800707E0, eax
0x180004426  mov     cs:byte_1800707E4, 1
0x18000442d  jmp     short loc_18000443A
0x18000442f  mov     edi, cs:dword_1800707E0
0x180004435  jmp     short loc_18000443A
0x180004437  or      edi, 0FFFFFFFFh
0x18000443a  mov     rax, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; void * NGENService::g_hInterruptEvent
0x180004441  mov     [rbp+57h+Handles], rax
0x180004445  mov     rax, cs:?g_hRootStoreDirtyEvent@NGENService@@3PEAXEA; void * NGENService::g_hRootStoreDirtyEvent
0x18000444c  mov     [rbp+57h+var_40], rax
0x180004450  mov     rax, cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA; void * NGENService::g_hSCMRequestEvent
0x180004457  mov     [rbp+57h+var_38], rax
0x18000445b  mov     rax, cs:?g_hControllerStateChange@NGENService@@3PEAXEA; void * NGENService::g_hControllerStateChange
0x180004462  mov     [rbp+27h], rax
0x180004466  mov     rax, cs:?g_hListenerShutdownEvent@NGENService@@3PEAXEA; void * NGENService::g_hListenerShutdownEvent
0x18000446d  mov     [rbp+57h+var_28], rax
0x180004471  mov     r9d, edi; dwMilliseconds
0x180004474  xor     r8d, r8d; bWaitAll
0x180004477  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000447b  lea     ecx, [r8+5]; nCount
0x18000447f  call    cs:__imp_WaitForMultipleObjects
0x180004485  mov     ebx, eax
0x180004487  mov     edx, edi; unsigned __int16 *
0x180004489  lea     rcx, aWaitfornextlis; "WaitForNextListenerCheck(): Waiting for"...
0x180004490  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004495  test    ebx, ebx
0x180004497  jz      short loc_1800044D1
0x180004499  sub     ebx, 1
0x18000449c  jz      short loc_1800044C8
0x18000449e  sub     ebx, 1
0x1800044a1  jz      short loc_1800044BF
0x1800044a3  sub     ebx, 1
0x1800044a6  jz      short loc_1800044B6
0x1800044a8  cmp     ebx, 1
0x1800044ab  jnz     short loc_1800044DD
0x1800044ad  lea     rcx, aListenerThread; "\t: Listener thread shutting down\n"
0x1800044b4  jmp     short loc_1800044D8
0x1800044b6  lea     rcx, aExitingDueToCo; "\t: Exiting due to controller state cha"...
0x1800044bd  jmp     short loc_1800044D8
0x1800044bf  lea     rcx, aExitingDueToSc; "\t: Exiting due to SCM request event\n"
0x1800044c6  jmp     short loc_1800044D8
0x1800044c8  lea     rcx, aExitingDueToDi; "\t: Exiting due to dirty root store eve"...
0x1800044cf  jmp     short loc_1800044D8
0x1800044d1  lea     rcx, aInterruptsDisp; "\t: Interrupts dispatched. Listener wil"...
0x1800044d8  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800044dd  xor     edx, edx; dwMilliseconds
0x1800044df  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; hHandle
0x1800044e6  call    cs:__imp_WaitForSingleObject
0x1800044ec  test    eax, eax
0x1800044ee  jnz     short loc_180004545
0x1800044f0  mov     rax, cs:?g_hInterruptProcessedEvent@NGENService@@3PEAXEA; void * NGENService::g_hInterruptProcessedEvent
0x1800044f7  mov     [rbp+57h+var_58], rax
0x1800044fb  mov     rax, cs:?g_hListenerShutdownEvent@NGENService@@3PEAXEA; void * NGENService::g_hListenerShutdownEvent
0x180004502  mov     [rbp+57h+var_50], rax
0x180004506  lea     rcx, aWaitforinterru; "WaitForInterruptProcessedEvent()\n"
0x18000450d  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004512  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180004516  xor     r8d, r8d; bWaitAll
0x180004519  lea     rdx, [rbp+57h+var_58]; lpHandles
0x18000451d  lea     ecx, [r8+2]; nCount
0x180004521  call    cs:__imp_WaitForMultipleObjects
0x180004527  test    eax, eax
0x180004529  jz      short loc_180004539
0x18000452b  cmp     eax, 1
0x18000452e  jnz     short loc_180004545
0x180004530  lea     rcx, aListenerThread; "\t: Listener thread shutting down\n"
0x180004537  jmp     short loc_180004540
0x180004539  lea     rcx, aInterruptsWere; "\t: Interrupts were processed, continui"...
0x180004540  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004545  mov     al, cs:?g_bStopEventListener@NGENService@@3V?$Volatile@_N@@A; Volatile<bool> NGENService::g_bStopEventListener
0x18000454b  test    al, al
0x18000454d  jz      loc_1800041B9
0x180004553  xor     eax, eax
0x180004555  mov     rcx, [rbp+57h+var_20]
0x180004559  xor     rcx, rsp; StackCookie
0x18000455c  call    __security_check_cookie
0x180004561  lea     r11, [rsp+0D0h+var_10]
0x180004569  mov     rbx, [r11+20h]
0x18000456d  mov     rsi, [r11+28h]
0x180004571  mov     rdi, [r11+30h]
0x180004575  mov     rsp, r11
0x180004578  pop     r15
0x18000457a  pop     r13
0x18000457c  pop     rbp
0x18000457d  retn
```

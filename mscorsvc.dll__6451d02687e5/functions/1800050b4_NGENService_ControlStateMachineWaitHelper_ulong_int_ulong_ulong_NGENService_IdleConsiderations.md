# NGENService::ControlStateMachineWaitHelper(ulong,int,ulong,ulong,NGENService::IdleConsiderations *)

- ea: `0x1800050b4`
- end: `0x18000539d`
- name: `?ControlStateMachineWaitHelper@NGENService@@YAXKHKKPEAUIdleConsiderations@1@@Z`
- size: `745`
- prototype: `void __fastcall(NGENService *this, int, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800053a0`

## callees

- `0x18000352c`
- `0x1800035bc`
- `0x180004c5c`
- `0x1800050b4`
- `0x180006238`
- `0x180007130`
- `0x18000765c`
- `0x180007774`
- `0x18002e1d0`
- `0x1800366a8`
- `0x180037340`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800050f8`
- `KERNEL32!EnterCriticalSection` at `0x1800051e2`
- `KERNEL32!EnterCriticalSection` at `0x180005332`
- `KERNEL32!EnterCriticalSection` at `0x1800050f8`
- `KERNEL32!EnterCriticalSection` at `0x1800051e2`
- `KERNEL32!EnterCriticalSection` at `0x180005332`
- `KERNEL32!LeaveCriticalSection` at `0x180005114`
- `KERNEL32!LeaveCriticalSection` at `0x18000528e`
- `KERNEL32!LeaveCriticalSection` at `0x180005372`
- `KERNEL32!LeaveCriticalSection` at `0x180005114`
- `KERNEL32!LeaveCriticalSection` at `0x18000528e`
- `KERNEL32!LeaveCriticalSection` at `0x180005372`
- `KERNEL32!GetTickCount` at `0x18000511a`
- `KERNEL32!GetTickCount` at `0x1800051d1`
- `KERNEL32!GetTickCount` at `0x18000520e`
- `KERNEL32!GetTickCount` at `0x180005228`
- `KERNEL32!GetTickCount` at `0x18000511a`
- `KERNEL32!GetTickCount` at `0x1800051d1`
- `KERNEL32!GetTickCount` at `0x18000520e`
- `KERNEL32!GetTickCount` at `0x180005228`
- `KERNEL32!WaitForSingleObject` at `0x18000514b`
- `KERNEL32!WaitForSingleObject` at `0x180005189`
- `KERNEL32!WaitForSingleObject` at `0x18000514b`
- `KERNEL32!WaitForSingleObject` at `0x180005189`

## string_xrefs

- `0x1800051b8`: `ControlStateMachineWaitHelper():Can't proceed: Waiting for client to complete work...\n`
- `0x1800051a8`: `ngenserviceclientlock.dat`

## pseudocode

```c
void __fastcall NGENService::ControlStateMachineWaitHelper(
        NGENService *this,
        int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned int v5; // esi
  unsigned int v6; // r13d
  unsigned int *v7; // r12
  unsigned int v8; // ebx
  char v9; // di
  unsigned int *v10; // r8
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // r15d
  int v13; // r14d
  int v14; // ebx
  unsigned int *v15; // r8
  unsigned int *v16; // r8
  int v17; // edx
  const unsigned __int16 *v18; // r8
  bool v19; // dl
  DWORD TickCount; // ebx
  unsigned int ConfigValue; // eax
  unsigned int v22; // esi
  int v23; // ebx
  struct SYSTEM_SNAPSHOT *v24; // rdx
  unsigned int v25; // r8d
  const unsigned __int16 *v26; // rdx
  int v27; // [rsp+78h] [rbp+48h] BYREF
  unsigned int v28; // [rsp+80h] [rbp+50h]
  unsigned int v29; // [rsp+88h] [rbp+58h]

  v29 = a4;
  v28 = a3;
  v27 = a2;
  v5 = a3;
  v6 = (unsigned int)this;
  v7 = a5;
  v8 = *a5;
  EnterCriticalSection(&NGENService::g_IdleCS);
  v9 = 1;
  NGENService::IdleIsMachineIdleWorker((NGENService *)v8, 0, v10);
  LeaveCriticalSection(&NGENService::g_IdleCS);
  GetTickCount();
  v12 = 6;
LABEL_2:
  v13 = 0;
  while ( !v13 )
  {
    NGENService::WaitForNextStateMachineCheck((NGENService *)v6, (unsigned int)v11);
    if ( !WaitForSingleObject(NGENService::g_hInterruptEvent, 0) )
      return;
    if ( NGENService::IdleIsMachineIdle((NGENService *)*v7, (unsigned int)&a5, v16) )
    {
      if ( (unsigned int)MachineWideMutexHolder::IsTaken(L"ngenserviceclientlock.dat") )
        NGENService::DebugLog(
          (NGENService *)L"ControlStateMachineWaitHelper():Can't proceed: Waiting for client to complete work...\n",
          v11);
      else
        v13 = 1;
    }
    else
    {
      GetTickCount();
      EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
      if ( `NGENService::ControllerState::AddAccumulatedWaitIdleTime'::`2'::bFirst )
      {
        NGENService::ControllerState::m_dwAccumulatedTime = REGUTIL::GetLong(
                                                              L"AccumulatedWaitIdleTime",
                                                              v17,
                                                              v18,
                                                              NGENService::g_hkNGENServicePersistentState);
        NGENService::ControllerState::m_dwAccumulatedTimeLastUpdate = GetTickCount();
        `NGENService::ControllerState::AddAccumulatedWaitIdleTime'::`2'::bFirst = 0;
      }
      NGENService::ControllerState::m_dwAccumulatedTime += v6;
      TickCount = GetTickCount();
      if ( byte_1800707D4 )
      {
        ConfigValue = dword_1800707D0;
      }
      else
      {
        ConfigValue = CLRConfig::GetConfigValue(
                        (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServiceWaitPassiveWork,
                        v19,
                        (bool *)&v27);
        dword_1800707D0 = ConfigValue;
        byte_1800707D4 = 1;
      }
      if ( TickCount - NGENService::ControllerState::m_dwAccumulatedTimeLastUpdate > 20 * ConfigValue )
      {
        NGENService::ControllerState::SetAccumulatedWaitIdleTime(NGENService::ControllerState::m_dwAccumulatedTime);
        NGENService::ControllerState::m_dwAccumulatedTimeLastUpdate = TickCount;
      }
      v22 = NGENService::ControllerState::m_dwAccumulatedTime;
      LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
      v23 = (int)a5;
      if ( v7[3] && ((unsigned __int8)a5 & 1) != 0 && v22 >= v7[3] )
      {
        NGENService::DebugLog(
          (NGENService *)L"ControlStateMachineWaitHelper():Timeout for idle hard disk detection expired\n",
          v11);
        v23 &= ~1u;
        LODWORD(a5) = v23;
        v12 &= ~1u;
      }
      if ( v7[2] && v22 >= v7[2] )
      {
        NGENService::DebugLog(
          (NGENService *)L"ControlStateMachineWaitHelper():Running in input backstop mode: will ignore anything other than input\n",
          v11);
        v23 &= 2u;
        LODWORD(a5) = v23;
        v12 = 2;
      }
      if ( v7[1] && v22 >= v7[1] )
      {
        NGENService::DebugLog(
          (NGENService *)L"ControlStateMachineWaitHelper():Running in absolute backstop mode: declaring the machine as idle\n",
          v11);
        v23 = 0;
        LODWORD(a5) = 0;
        v12 = 0;
      }
      v5 = v28;
      if ( !v23 )
      {
LABEL_33:
        EnterCriticalSection(&NGENService::g_IdleCS);
        NGENService::GetSystemSnapshot((NGENService *)&NGENService::g_IdleWorkInitialSnapshot, v24, v25);
        if ( (byte_18006FBB4 & 1) != 0 )
        {
          NGENService::DebugLog((NGENService *)L"IdleCanBeginWork() returns true.\n", v26);
        }
        else
        {
          NGENService::DebugLog(
            (NGENService *)L"IdleCanBeginWork() returns false: Failed to get current input time.\n",
            v26);
          v9 = 0;
        }
        LeaveCriticalSection(&NGENService::g_IdleCS);
        if ( v9 )
          NGENService::ControllerState::Set(v29, v12);
        return;
      }
    }
  }
  v14 = 0;
  while ( 1 )
  {
    NGENService::WaitForNextStateMachineCheck((NGENService *)v5, (unsigned int)v11);
    if ( !WaitForSingleObject(NGENService::g_hInterruptEvent, 0) )
      break;
    if ( NGENService::IdleIsMachineIdle((NGENService *)*v7, 0, v15) && ++v14 < 1 )
      continue;
    if ( v14 == 1 )
      goto LABEL_33;
    goto LABEL_2;
  }
}

```

## disassembly

```asm
0x1800050b4  mov     rax, rsp
0x1800050b7  mov     [rax+8], rbx
0x1800050bb  mov     [rax+20h], r9d
0x1800050bf  mov     [rax+18h], r8d
0x1800050c3  mov     [rax+10h], edx
0x1800050c6  push    rbp
0x1800050c7  push    rsi
0x1800050c8  push    rdi
0x1800050c9  push    r12
0x1800050cb  push    r13
0x1800050cd  push    r14
0x1800050cf  push    r15
0x1800050d1  mov     rbp, rsp
0x1800050d4  sub     rsp, 30h
0x1800050d8  mov     esi, r8d
0x1800050db  mov     r13d, ecx
0x1800050de  mov     r12, [rbp+arg_20]
0x1800050e2  mov     ebx, [r12]
0x1800050e6  lea     r14, ?g_IdleCS@NGENService@@3VCriticalSection@@A; CriticalSection NGENService::g_IdleCS
0x1800050ed  mov     [rbp+var_10], r14
0x1800050f1  mov     [rbp+var_8], 0
0x1800050f5  mov     rcx, r14; lpCriticalSection
0x1800050f8  call    cs:__imp_EnterCriticalSection
0x1800050fe  mov     edi, 1
0x180005103  mov     [rbp+var_8], dil
0x180005107  xor     edx, edx; unsigned int
0x180005109  mov     ecx, ebx; this
0x18000510b  call    ?IdleIsMachineIdleWorker@NGENService@@YA_NKPEAK@Z; NGENService::IdleIsMachineIdleWorker(ulong,ulong *)
0x180005110  nop
0x180005111  mov     rcx, r14; lpCriticalSection
0x180005114  call    cs:__imp_LeaveCriticalSection
0x18000511a  call    cs:__imp_GetTickCount
0x180005120  lea     r15d, [rdi+5]
0x180005124  lea     rbx, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; CriticalSection NGENService::ControllerState::m_csControllerState
0x18000512b  xor     r14d, r14d
0x18000512e  test    r14d, r14d
0x180005131  jz      short loc_180005178
0x180005133  cmp     r14d, 1
0x180005137  jnz     short loc_18000512E
0x180005139  xor     ebx, ebx
0x18000513b  mov     ecx, esi; this
0x18000513d  call    ?WaitForNextStateMachineCheck@NGENService@@YAXK@Z; NGENService::WaitForNextStateMachineCheck(ulong)
0x180005142  xor     edx, edx; dwMilliseconds
0x180005144  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; hHandle
0x18000514b  call    cs:__imp_WaitForSingleObject
0x180005151  test    eax, eax
0x180005153  jz      loc_180005388
0x180005159  xor     edx, edx; unsigned int
0x18000515b  mov     ecx, [r12]; this
0x18000515f  call    ?IdleIsMachineIdle@NGENService@@YA_NKPEAK@Z; NGENService::IdleIsMachineIdle(ulong,ulong *)
0x180005164  test    al, al
0x180005166  jz      short loc_18000516E
0x180005168  add     ebx, edi
0x18000516a  cmp     ebx, edi
0x18000516c  jl      short loc_18000513B
0x18000516e  cmp     ebx, edi
0x180005170  jz      loc_180005320
0x180005176  jmp     short loc_180005124
0x180005178  mov     ecx, r13d; this
0x18000517b  call    ?WaitForNextStateMachineCheck@NGENService@@YAXK@Z; NGENService::WaitForNextStateMachineCheck(ulong)
0x180005180  xor     edx, edx; dwMilliseconds
0x180005182  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; hHandle
0x180005189  call    cs:__imp_WaitForSingleObject
0x18000518f  test    eax, eax
0x180005191  jz      loc_180005388
0x180005197  lea     rdx, [rbp+arg_20]; unsigned int
0x18000519b  mov     ecx, [r12]; this
0x18000519f  call    ?IdleIsMachineIdle@NGENService@@YA_NKPEAK@Z; NGENService::IdleIsMachineIdle(ulong,ulong *)
0x1800051a4  test    al, al
0x1800051a6  jz      short loc_1800051D1
0x1800051a8  lea     rcx, aNgenservicecli; "ngenserviceclientlock.dat"
0x1800051af  call    ?IsTaken@MachineWideMutexHolder@@SAHPEBG@Z; MachineWideMutexHolder::IsTaken(ushort const *)
0x1800051b4  test    eax, eax
0x1800051b6  jz      short loc_1800051C9
0x1800051b8  lea     rcx, aControlstatema_1; "ControlStateMachineWaitHelper():Can't p"...
0x1800051bf  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800051c4  jmp     loc_18000512E
0x1800051c9  mov     r14d, edi
0x1800051cc  jmp     loc_18000512E
0x1800051d1  call    cs:__imp_GetTickCount
0x1800051d7  mov     [rbp+var_10], rbx
0x1800051db  mov     [rbp+var_8], 0
0x1800051df  mov     rcx, rbx; lpCriticalSection
0x1800051e2  call    cs:__imp_EnterCriticalSection
0x1800051e8  mov     [rbp+var_8], dil
0x1800051ec  cmp     cs:?bFirst@?1??AddAccumulatedWaitIdleTime@ControllerState@NGENService@@SAKK@Z@4_NA, 0; bool `NGENService::ControllerState::AddAccumulatedWaitIdleTime(ulong)'::`2'::bFirst
0x1800051f3  jz      short loc_180005221
0x1800051f5  mov     r9, cs:?g_hkNGENServicePersistentState@NGENService@@3PEAUHKEY__@@EA; HKEY
0x1800051fc  lea     rcx, aAccumulatedwai; "AccumulatedWaitIdleTime"
0x180005203  call    ?GetLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::GetLong(ushort const *,long,ushort const *,HKEY__ *)
0x180005208  mov     cs:?m_dwAccumulatedTime@ControllerState@NGENService@@1KA, eax; ulong NGENService::ControllerState::m_dwAccumulatedTime
0x18000520e  call    cs:__imp_GetTickCount
0x180005214  mov     cs:?m_dwAccumulatedTimeLastUpdate@ControllerState@NGENService@@1KA, eax; ulong NGENService::ControllerState::m_dwAccumulatedTimeLastUpdate
0x18000521a  mov     cs:?bFirst@?1??AddAccumulatedWaitIdleTime@ControllerState@NGENService@@SAKK@Z@4_NA, 0; bool `NGENService::ControllerState::AddAccumulatedWaitIdleTime(ulong)'::`2'::bFirst
0x180005221  add     cs:?m_dwAccumulatedTime@ControllerState@NGENService@@1KA, r13d; ulong NGENService::ControllerState::m_dwAccumulatedTime
0x180005228  call    cs:__imp_GetTickCount
0x18000522e  mov     ebx, eax
0x180005230  cmp     cs:byte_1800707D4, 0
0x180005237  jnz     short loc_180005258
0x180005239  lea     r8, [rbp+arg_8]; bool *
0x18000523d  lea     rcx, ?UNSUPPORTED_NGENServiceWaitPassiveWork@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180005244  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180005249  mov     cs:dword_1800707D0, eax
0x18000524f  mov     cs:byte_1800707D4, dil
0x180005256  jmp     short loc_18000525E
0x180005258  mov     eax, cs:dword_1800707D0
0x18000525e  mov     ecx, ebx
0x180005260  sub     ecx, cs:?m_dwAccumulatedTimeLastUpdate@ControllerState@NGENService@@1KA; ulong NGENService::ControllerState::m_dwAccumulatedTimeLastUpdate
0x180005266  lea     eax, [rax+rax*4]
0x180005269  shl     eax, 2
0x18000526c  cmp     ecx, eax
0x18000526e  jbe     short loc_180005281
0x180005270  mov     ecx, cs:?m_dwAccumulatedTime@ControllerState@NGENService@@1KA; unsigned int
0x180005276  call    ?SetAccumulatedWaitIdleTime@ControllerState@NGENService@@SAJK@Z; NGENService::ControllerState::SetAccumulatedWaitIdleTime(ulong)
0x18000527b  mov     cs:?m_dwAccumulatedTimeLastUpdate@ControllerState@NGENService@@1KA, ebx; ulong NGENService::ControllerState::m_dwAccumulatedTimeLastUpdate
0x180005281  mov     esi, cs:?m_dwAccumulatedTime@ControllerState@NGENService@@1KA; ulong NGENService::ControllerState::m_dwAccumulatedTime
0x180005287  lea     rcx, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; lpCriticalSection
0x18000528e  call    cs:__imp_LeaveCriticalSection
0x180005294  mov     ebx, dword ptr [rbp+arg_20]
0x180005297  cmp     dword ptr [r12+0Ch], 0
0x18000529d  jz      short loc_1800052C4
0x18000529f  test    dil, bl
0x1800052a2  jz      short loc_1800052C4
0x1800052a4  cmp     esi, [r12+0Ch]
0x1800052a9  jb      short loc_1800052C4
0x1800052ab  lea     rcx, aControlstatema; "ControlStateMachineWaitHelper():Timeout"...
0x1800052b2  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800052b7  mov     eax, 0FFFFFFFEh
0x1800052bc  and     ebx, eax
0x1800052be  mov     dword ptr [rbp+arg_20], ebx
0x1800052c1  and     r15d, eax
0x1800052c4  cmp     dword ptr [r12+8], 0
0x1800052ca  jz      short loc_1800052EB
0x1800052cc  cmp     esi, [r12+8]
0x1800052d1  jb      short loc_1800052EB
0x1800052d3  lea     rcx, aControlstatema_0; "ControlStateMachineWaitHelper():Running"...
0x1800052da  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800052df  and     ebx, 2
0x1800052e2  mov     dword ptr [rbp+arg_20], ebx
0x1800052e5  mov     r15d, 2
0x1800052eb  cmp     dword ptr [r12+4], 0
0x1800052f1  jz      short loc_18000530E
0x1800052f3  cmp     esi, [r12+4]
0x1800052f8  jb      short loc_18000530E
0x1800052fa  lea     rcx, aControlstatema_2; "ControlStateMachineWaitHelper():Running"...
0x180005301  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180005306  xor     ebx, ebx
0x180005308  mov     dword ptr [rbp+arg_20], ebx
0x18000530b  xor     r15d, r15d
0x18000530e  test    ebx, ebx
0x180005310  mov     esi, [rbp+arg_10]
0x180005313  lea     rbx, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; CriticalSection NGENService::ControllerState::m_csControllerState
0x18000531a  jnz     loc_18000512E
0x180005320  lea     rbx, ?g_IdleCS@NGENService@@3VCriticalSection@@A; CriticalSection NGENService::g_IdleCS
0x180005327  mov     [rbp+var_10], rbx
0x18000532b  mov     [rbp+var_8], 0
0x18000532f  mov     rcx, rbx; lpCriticalSection
0x180005332  call    cs:__imp_EnterCriticalSection
0x180005338  mov     [rbp+var_8], dil
0x18000533c  lea     rcx, ?g_IdleWorkInitialSnapshot@NGENService@@3USYSTEM_SNAPSHOT@@A; this
0x180005343  call    ?GetSystemSnapshot@NGENService@@YAXPEAUSYSTEM_SNAPSHOT@@K@Z; NGENService::GetSystemSnapshot(SYSTEM_SNAPSHOT *,ulong)
0x180005348  test    cs:byte_18006FBB4, dil
0x18000534f  jnz     short loc_180005362
0x180005351  lea     rcx, aIdlecanbeginwo; "IdleCanBeginWork() returns false: Faile"...
0x180005358  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18000535d  xor     dil, dil
0x180005360  jmp     short loc_18000536F
0x180005362  lea     rcx, aIdlecanbeginwo_0; "IdleCanBeginWork() returns true.\n"
0x180005369  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18000536e  nop
0x18000536f  mov     rcx, rbx; lpCriticalSection
0x180005372  call    cs:__imp_LeaveCriticalSection
0x180005378  test    dil, dil
0x18000537b  jz      short loc_180005388
0x18000537d  mov     edx, r15d; unsigned int
0x180005380  mov     ecx, [rbp+arg_18]; unsigned int
0x180005383  call    ?Set@ControllerState@NGENService@@SAXKK@Z; NGENService::ControllerState::Set(ulong,ulong)
0x180005388  mov     rbx, [rsp+30h+arg_0]
0x18000538d  add     rsp, 30h
0x180005391  pop     r15
0x180005393  pop     r14
0x180005395  pop     r13
0x180005397  pop     r12
0x180005399  pop     rdi
0x18000539a  pop     rsi
0x18000539b  pop     rbp
0x18000539c  retn
```

# Container::Manager::Core::Details::Globals::CreateHeartbeatMonitor(void)

- ea: `0x1800743d8`
- end: `0x180074632`
- name: `?CreateHeartbeatMonitor@Globals@Details@Core@Manager@Container@@QEAAJXZ`
- size: `602`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::Globals *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180073dd8`
- `0x1800748e0`

## callees

- `0x18000da68`
- `0x18000da88`
- `0x1800471dc`
- `0x180072964`
- `0x180073848`
- `0x1800743d8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800744a9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800744a9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180074470`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180074470`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800744d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180074542`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800745f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800744d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180074542`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800745f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180074588`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800745dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180074588`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800745dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074577`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180074550`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180074596`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180074550`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180074596`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::Globals::CreateHeartbeatMonitor(
        Container::Manager::Core::Details::Globals *this)
{
  int started; // eax
  unsigned int v2; // ebx
  char *v4; // rbp
  struct _TP_TIMER *ThreadpoolTimer; // rbx
  const char *v6; // r9
  int v7; // edi
  struct _TP_WORK *ThreadpoolWork; // rdi
  const char *v9; // r9
  struct _TP_TIMER **v10; // r14
  struct _TP_TIMER *v11; // r15
  DWORD LastError; // esi
  struct _TP_WORK **v13; // r14
  struct _TP_WORK *v14; // r15
  DWORD v15; // esi
  Container::Manager::Core::Details::PolicyManager *v16; // rcx
  utl::_RefCountBase *v17; // rax
  utl::_RefCountBase *v18; // rcx
  utl::_RefCountBase *v19; // rcx
  int v20; // [rsp+20h] [rbp-58h] BYREF
  char v21; // [rsp+28h] [rbp-50h] BYREF
  PVOID pv; // [rsp+30h] [rbp-48h] BYREF
  utl::_RefCountBase *v23; // [rsp+38h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( Container::Manager::Core::g_heartbeatMonitor )
    return 0;
  started = Container::Manager::Core::Details::Globals::CreateAndStartPolicyManager(this);
  v2 = started;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\globals.cpp",
      (const char *)(unsigned int)started,
      v20);
    return v2;
  }
  utl::make_shared<Container::Manager::Core::Details::HeartbeatMonitor,>(&pv);
  v4 = (char *)pv;
  if ( !pv )
  {
    v2 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x411,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\globals.cpp",
      (const char *)0x8007000ELL,
      v20);
    if ( v23 )
      utl::_RefCountBase::_DecStrong(v23);
    return v2;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(
                      Container::Manager::Core::Details::HeartbeatMonitor::HeartbeatTimerCallback,
                      pv,
                      0);
  if ( ThreadpoolTimer )
  {
    ThreadpoolWork = CreateThreadpoolWork(
                       Container::Manager::Core::Details::HeartbeatMonitor::DumpCollectionThread,
                       v4,
                       0);
    if ( ThreadpoolWork )
    {
      v10 = (struct _TP_TIMER **)(v4 + 48);
      if ( v4 + 48 != (char *)&v20 )
      {
        v11 = *v10;
        if ( *v10 )
        {
          LastError = GetLastError();
          CloseThreadpoolTimer(v11);
          SetLastError(LastError);
        }
        *v10 = ThreadpoolTimer;
        ThreadpoolTimer = 0;
      }
      v13 = (struct _TP_WORK **)(v4 + 72);
      if ( v4 + 72 != &v21 )
      {
        v14 = *v13;
        if ( *v13 )
        {
          v15 = GetLastError();
          CloseThreadpoolWork(v14);
          SetLastError(v15);
        }
        *v13 = ThreadpoolWork;
        ThreadpoolWork = 0;
      }
      v16 = Container::Manager::Core::g_policyManager;
      v17 = qword_18021F478;
      if ( qword_18021F478 )
        _InterlockedIncrement((volatile signed __int32 *)qword_18021F478 + 2);
      *((_QWORD *)v4 + 10) = v16;
      v18 = (utl::_RefCountBase *)*((_QWORD *)v4 + 11);
      *((_QWORD *)v4 + 11) = v17;
      if ( v18 )
        utl::_RefCountBase::_DecStrong(v18);
      if ( ThreadpoolWork )
        CloseThreadpoolWork(ThreadpoolWork);
      if ( ThreadpoolTimer )
        CloseThreadpoolTimer(ThreadpoolTimer);
      goto LABEL_33;
    }
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x5F,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\heartbeatmonitor.cpp",
           v9);
    CloseThreadpoolTimer(ThreadpoolTimer);
  }
  else
  {
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x58,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\heartbeatmonitor.cpp",
           v6);
  }
  if ( v7 >= 0 )
  {
LABEL_33:
    Container::Manager::Core::g_heartbeatMonitor = (PSRWLOCK)v4;
    v19 = qword_18021F4A8;
    qword_18021F4A8 = v23;
    if ( v19 )
      utl::_RefCountBase::_DecStrong(v19);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x413,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\globals.cpp",
    (const char *)(unsigned int)v7,
    v20);
  if ( v23 )
    utl::_RefCountBase::_DecStrong(v23);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800743d8  push    rbx
0x1800743da  push    rbp
0x1800743db  push    rsi
0x1800743dc  push    rdi
0x1800743dd  push    r14
0x1800743df  push    r15
0x1800743e1  sub     rsp, 48h
0x1800743e5  cmp     cs:?g_heartbeatMonitor@Core@Manager@Container@@3V?$shared_ptr@VHeartbeatMonitor@Details@Core@Manager@Container@@@utl@@A, 0; utl::shared_ptr<Container::Manager::Core::Details::HeartbeatMonitor> Container::Manager::Core::g_heartbeatMonitor
0x1800743ed  jnz     loc_180074622
0x1800743f3  call    ?CreateAndStartPolicyManager@Globals@Details@Core@Manager@Container@@QEAAJXZ; Container::Manager::Core::Details::Globals::CreateAndStartPolicyManager(void)
0x1800743f8  mov     ebx, eax
0x1800743fa  test    eax, eax
0x1800743fc  jns     short loc_18007441E
0x1800743fe  mov     rcx, [rsp+78h]; this
0x180074403  mov     r9d, eax; char *
0x180074406  lea     r8, aOnecoreBaseGen_29; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18007440d  mov     edx, 40Eh; void *
0x180074412  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074417  mov     eax, ebx
0x180074419  jmp     loc_180074624
0x18007441e  lea     rcx, [rsp+78h+pv]
0x180074423  call    ??$make_shared@VHeartbeatMonitor@Details@Core@Manager@Container@@$$V@utl@@YA?AV?$shared_ptr@VHeartbeatMonitor@Details@Core@Manager@Container@@@0@XZ; utl::make_shared<Container::Manager::Core::Details::HeartbeatMonitor,>(void)
0x180074428  mov     rbp, [rsp+78h+pv]
0x18007442d  test    rbp, rbp
0x180074430  jnz     short loc_180074463
0x180074432  mov     rcx, [rsp+78h]; this
0x180074437  mov     ebx, 8007000Eh
0x18007443c  mov     r9d, ebx; char *
0x18007443f  lea     r8, aOnecoreBaseGen_29; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180074446  mov     edx, 411h; void *
0x18007444b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074450  nop
0x180074451  mov     rcx, [rsp+78h+var_40]; this
0x180074456  test    rcx, rcx
0x180074459  jz      short loc_180074461
0x18007445b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180074460  nop
0x180074461  jmp     short loc_180074417
0x180074463  xor     r8d, r8d; pcbe
0x180074466  mov     rdx, rbp; pv
0x180074469  lea     rcx, ?HeartbeatTimerCallback@HeartbeatMonitor@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180074470  call    cs:__imp_CreateThreadpoolTimer
0x180074477  nop     dword ptr [rax+rax+00h]
0x18007447c  mov     rbx, rax
0x18007447f  test    rax, rax
0x180074482  jnz     short loc_18007449C
0x180074484  mov     rcx, [rsp+78h]; this
0x180074489  lea     r8, aOnecoreBaseGen_30; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180074490  lea     edx, [rax+58h]; void *
0x180074493  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180074498  mov     edi, eax
0x18007449a  jmp     short loc_1800744E2
0x18007449c  xor     r8d, r8d; pcbe
0x18007449f  mov     rdx, rbp; pv
0x1800744a2  lea     rcx, ?DumpCollectionThread@HeartbeatMonitor@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800744a9  call    cs:__imp_CreateThreadpoolWork
0x1800744b0  nop     dword ptr [rax+rax+00h]
0x1800744b5  mov     rdi, rax
0x1800744b8  test    rax, rax
0x1800744bb  jnz     short loc_18007451B
0x1800744bd  mov     rcx, [rsp+78h]; this
0x1800744c2  lea     r8, aOnecoreBaseGen_30; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800744c9  lea     edx, [rax+5Fh]; void *
0x1800744cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800744d1  mov     edi, eax
0x1800744d3  mov     rcx, rbx; pti
0x1800744d6  call    cs:__imp_CloseThreadpoolTimer
0x1800744dd  nop     dword ptr [rax+rax+00h]
0x1800744e2  test    edi, edi
0x1800744e4  jns     loc_1800745FD
0x1800744ea  mov     rcx, [rsp+78h]; this
0x1800744ef  mov     r9d, edi; char *
0x1800744f2  lea     r8, aOnecoreBaseGen_29; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800744f9  mov     edx, 413h; void *
0x1800744fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074503  nop
0x180074504  mov     rcx, [rsp+78h+var_40]; this
0x180074509  test    rcx, rcx
0x18007450c  jz      short loc_180074514
0x18007450e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180074513  nop
0x180074514  mov     eax, edi
0x180074516  jmp     loc_180074624
0x18007451b  lea     r14, [rbp+30h]
0x18007451f  lea     rax, [rsp+78h+var_58]
0x180074524  cmp     r14, rax
0x180074527  jz      short loc_180074561
0x180074529  mov     r15, [r14]
0x18007452c  test    r15, r15
0x18007452f  jz      short loc_18007455C
0x180074531  call    cs:__imp_GetLastError
0x180074538  nop     dword ptr [rax+rax+00h]
0x18007453d  mov     esi, eax
0x18007453f  mov     rcx, r15; pti
0x180074542  call    cs:__imp_CloseThreadpoolTimer
0x180074549  nop     dword ptr [rax+rax+00h]
0x18007454e  mov     ecx, esi; dwErrCode
0x180074550  call    cs:__imp_SetLastError
0x180074557  nop     dword ptr [rax+rax+00h]
0x18007455c  mov     [r14], rbx
0x18007455f  xor     ebx, ebx
0x180074561  lea     r14, [rbp+48h]
0x180074565  lea     rax, [rsp+78h+var_50]
0x18007456a  cmp     r14, rax
0x18007456d  jz      short loc_1800745A7
0x18007456f  mov     r15, [r14]
0x180074572  test    r15, r15
0x180074575  jz      short loc_1800745A2
0x180074577  call    cs:__imp_GetLastError
0x18007457e  nop     dword ptr [rax+rax+00h]
0x180074583  mov     esi, eax
0x180074585  mov     rcx, r15; pwk
0x180074588  call    cs:__imp_CloseThreadpoolWork
0x18007458f  nop     dword ptr [rax+rax+00h]
0x180074594  mov     ecx, esi; dwErrCode
0x180074596  call    cs:__imp_SetLastError
0x18007459d  nop     dword ptr [rax+rax+00h]
0x1800745a2  mov     [r14], rdi
0x1800745a5  xor     edi, edi
0x1800745a7  mov     rcx, cs:?g_policyManager@Core@Manager@Container@@3V?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@A; utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> Container::Manager::Core::g_policyManager
0x1800745ae  mov     rax, cs:qword_18021F478
0x1800745b5  test    rax, rax
0x1800745b8  jz      short loc_1800745BE
0x1800745ba  lock inc dword ptr [rax+8]
0x1800745be  mov     [rbp+50h], rcx
0x1800745c2  mov     rcx, [rbp+58h]; this
0x1800745c6  mov     [rbp+58h], rax
0x1800745ca  test    rcx, rcx
0x1800745cd  jz      short loc_1800745D5
0x1800745cf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800745d4  nop
0x1800745d5  test    rdi, rdi
0x1800745d8  jz      short loc_1800745E9
0x1800745da  mov     rcx, rdi; pwk
0x1800745dd  call    cs:__imp_CloseThreadpoolWork
0x1800745e4  nop     dword ptr [rax+rax+00h]
0x1800745e9  test    rbx, rbx
0x1800745ec  jz      short loc_1800745FD
0x1800745ee  mov     rcx, rbx; pti
0x1800745f1  call    cs:__imp_CloseThreadpoolTimer
0x1800745f8  nop     dword ptr [rax+rax+00h]
0x1800745fd  mov     cs:?g_heartbeatMonitor@Core@Manager@Container@@3V?$shared_ptr@VHeartbeatMonitor@Details@Core@Manager@Container@@@utl@@A, rbp; utl::shared_ptr<Container::Manager::Core::Details::HeartbeatMonitor> Container::Manager::Core::g_heartbeatMonitor
0x180074604  mov     rcx, cs:qword_18021F4A8; this
0x18007460b  mov     rax, [rsp+78h+var_40]
0x180074610  mov     cs:qword_18021F4A8, rax
0x180074617  test    rcx, rcx
0x18007461a  jz      short loc_180074622
0x18007461c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180074621  nop
0x180074622  xor     eax, eax
0x180074624  add     rsp, 48h
0x180074628  pop     r15
0x18007462a  pop     r14
0x18007462c  pop     rdi
0x18007462d  pop     rsi
0x18007462e  pop     rbp
0x18007462f  pop     rbx
0x180074630  retn
```

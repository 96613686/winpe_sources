# CJobManager::RevokeAndDisconnectJobNotificationInterfaces(void)

- ea: `0x1800094cc`
- end: `0x180009810`
- name: `?RevokeAndDisconnectJobNotificationInterfaces@CJobManager@@QEAAXXZ`
- size: `836`
- prototype: `void __fastcall(CJobManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180086324`

## callees

- `0x1800094cc`
- `0x180009818`
- `0x180009ac0`
- `0x18000b4d0`
- `0x18000c520`
- `0x180029304`
- `0x1800327f0`
- `0x180034760`
- `0x180068424`
- `0x180099740`
- `0x18009d024`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000972d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000972d`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18000974c`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18000974c`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800097af`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800097af`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800097c5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800097c5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180009785`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180009785`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CJobManager::RevokeAndDisconnectJobNotificationInterfaces(struct IBackgroundCopyCallback *this)
{
  CJobManager *v1; // r14
  void (*v2)(void); // r9
  _QWORD *v3; // rbx
  _QWORD *i; // rbx
  struct IBackgroundCopyCallback *v5; // rax
  struct IBackgroundCopyCallback *v6; // rsi
  struct IBackgroundCopyCallback *v7; // rax
  struct IBackgroundCopyCallback *v8; // rsi
  __int64 *v9; // rbx
  __int64 *v10; // rsi
  __int64 v11; // rdi
  ComError *v12; // rax
  __int64 v13; // rax
  __int64 *v14; // [rsp+40h] [rbp-B8h] BYREF
  __int64 *v15; // [rsp+48h] [rbp-B0h]
  __int64 *v16; // [rsp+50h] [rbp-A8h]
  DWORD Parameter; // [rsp+58h] [rbp-A0h] BYREF
  char v18; // [rsp+5Ch] [rbp-9Ch]
  HRESULT v19; // [rsp+60h] [rbp-98h]
  void *phNewTimer; // [rsp+68h] [rbp-90h] BYREF
  const ComError *v21; // [rsp+70h] [rbp-88h] BYREF
  const std::exception *v22; // [rsp+78h] [rbp-80h] BYREF
  CJobManager *v23; // [rsp+80h] [rbp-78h] BYREF
  _QWORD Context[11]; // [rsp+88h] [rbp-70h] BYREF
  struct IBackgroundCopyCallback *v25; // [rsp+100h] [rbp+8h] BYREF
  struct IBackgroundCopyCallback *v26; // [rsp+108h] [rbp+10h] BYREF

  v25 = this;
  v1 = g_Manager;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
  std::vector<_GUID>::vector<_GUID>(&v14);
  v23 = v1;
  ScopedWatchdogTimer::ScopedWatchdogTimer(Context, 0x7530u, -2145386391, v2);
  TaskScheduler::LockWriter((CJobManager *)((char *)v23 + 520), 0);
  v3 = (_QWORD *)*((_QWORD *)v1 + 87);
  try
  {
    while ( v3 != (_QWORD *)((char *)v1 + 688) )
    {
      v25 = 0;
      if ( (int)CJob::GetNotifyInterface((CJob *)((unsigned __int64)(v3 - 78) & -(__int64)(v3 != 0)), &v25) < 0 )
      {
        v8 = v25;
      }
      else
      {
        v7 = v25;
        v8 = 0;
        v25 = 0;
        v26 = v7;
        if ( v15 == v16 )
          std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(
            (__int64)&v14,
            v15,
            &v26);
        else
          *v15++ = (__int64)v7;
      }
      CJob::SetNotifyInterface((CJob *)((unsigned __int64)(v3 - 78) & -(__int64)(v3 != 0)), 0, &GUID_NULL, 0);
      if ( v8 )
        ((void (__fastcall *)(struct IBackgroundCopyCallback *))v8->lpVtbl->Release)(v8);
      v3 = (_QWORD *)v3[1];
    }
    for ( i = (_QWORD *)*((_QWORD *)v1 + 92); i != (_QWORD *)((char *)v1 + 728); i = (_QWORD *)i[1] )
    {
      v25 = 0;
      if ( (int)CJob::GetNotifyInterface((CJob *)((unsigned __int64)(i - 78) & -(__int64)(i != 0)), &v25) < 0 )
      {
        v6 = v25;
      }
      else
      {
        v5 = v25;
        v6 = 0;
        v25 = 0;
        v26 = v5;
        if ( v15 == v16 )
          std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(
            (__int64)&v14,
            v15,
            &v26);
        else
          *v15++ = (__int64)v5;
      }
      CJob::SetNotifyInterface((CJob *)((unsigned __int64)(i - 78) & -(__int64)(i != 0)), 0, &GUID_NULL, 0);
      if ( v6 )
        ((void (__fastcall *)(struct IBackgroundCopyCallback *))v6->lpVtbl->Release)(v6);
    }
    TaskScheduler::UnlockWriter((CJobManager *)((char *)v23 + 520));
    ScopedWatchdogTimer::~ScopedWatchdogTimer((ScopedWatchdogTimer *)Context);
  }
  catch ( const ComError *v21 )
  {
    v12 = ComError::ComError((ComError *)&v23, v21);
    LogException(v12);
  }
  catch ( const std::exception *v22 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v22 + 8LL))(v22);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, v13);
    }
  }
  v9 = v14;
  v10 = v15;
  if ( v14 != v15 )
  {
    do
    {
      v11 = *v9;
      Parameter = GetCurrentThreadId();
      v18 = 0;
      v19 = -2147467259;
      phNewTimer = 0;
      v19 = CoEnableCallCancellation(0);
      if ( v19 >= 0 )
        CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x7D0u, 0x3E8u, 0);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v19 >= 0 )
      {
        v19 = -2147467259;
        CoDisableCallCancellation(0);
        if ( phNewTimer )
          DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      }
      ++v9;
    }
    while ( v9 != v10 );
    v9 = v14;
  }
  if ( v9 )
    std::_Deallocate<16>(v9, ((char *)v16 - (char *)v9) & 0xFFFFFFFFFFFFFFF8uLL);
}

```

## disassembly

```asm
0x1800094cc  mov     [rsp+arg_10], rbx
0x1800094d1  mov     [rsp+arg_18], rsi
0x1800094d6  mov     [rsp+arg_0], rcx
0x1800094db  push    rdi
0x1800094dc  push    r14
0x1800094de  push    r15
0x1800094e0  sub     rsp, 0E0h
0x1800094e7  mov     r14, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x1800094ee  lea     rax, WPP_GLOBAL_Control
0x1800094f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094fc  cmp     rcx, rax
0x1800094ff  jz      short loc_18000951C
0x180009501  test    byte ptr [rcx+1Ch], 1
0x180009505  jz      short loc_18000951C
0x180009507  mov     edx, 2Eh ; '.'
0x18000950c  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x180009513  mov     rcx, [rcx+10h]
0x180009517  call    WPP_SF_
0x18000951c  lea     rcx, [rsp+0F8h+var_B8]
0x180009521  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180009526  nop
0x180009527  mov     [rsp+0F8h+var_78], r14
0x18000952f  mov     edx, 7530h; dwMilliseconds
0x180009534  mov     r8d, 80200069h; int
0x18000953a  lea     rcx, [rsp+0F8h+Context]; Context
0x180009542  call    ??0ScopedWatchdogTimer@@QEAA@KJP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,long,void (*)(void))
0x180009547  mov     rcx, [rsp+0F8h+var_78]
0x18000954f  add     rcx, 208h; this
0x180009556  xor     edx, edx; void *
0x180009558  call    ?LockWriter@TaskScheduler@@QEAA_NPEAX@Z; TaskScheduler::LockWriter(void *)
0x18000955d  nop
0x18000955e  lea     rdi, [r14+2B0h]
0x180009565  mov     rbx, [rdi+8]
0x180009569  cmp     rbx, rdi
0x18000956c  jnz     loc_18000965C
0x180009572  lea     rdi, [r14+2D8h]
0x180009579  mov     rbx, [rdi+8]
0x18000957d  cmp     rbx, rdi
0x180009580  jnz     short loc_1800095A9
0x180009582  mov     rcx, [rsp+0F8h+var_78]
0x18000958a  add     rcx, 208h; this
0x180009591  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x180009596  lea     rcx, [rsp+0F8h+Context]; this
0x18000959e  call    ??1ScopedWatchdogTimer@@QEAA@XZ; ScopedWatchdogTimer::~ScopedWatchdogTimer(void)
0x1800095a3  nop
0x1800095a4  jmp     loc_180009711
0x1800095a9  mov     rax, rbx
0x1800095ac  lea     rcx, [rbx-270h]
0x1800095b3  neg     rax
0x1800095b6  sbb     r14, r14
0x1800095b9  and     r14, rcx
0x1800095bc  mov     [rsp+0F8h+arg_0], 0
0x1800095c8  lea     rdx, [rsp+0F8h+arg_0]; struct IBackgroundCopyCallback **
0x1800095d0  mov     rcx, r14; this
0x1800095d3  call    ?GetNotifyInterface@CJob@@QEBAJPEAPEAUIBackgroundCopyCallback@@@Z; CJob::GetNotifyInterface(IBackgroundCopyCallback * *)
0x1800095d8  test    eax, eax
0x1800095da  js      short loc_180009621
0x1800095dc  mov     rax, [rsp+0F8h+arg_0]
0x1800095e4  xor     esi, esi
0x1800095e6  mov     [rsp+0F8h+arg_0], rsi
0x1800095ee  mov     [rsp+0F8h+arg_8], rax
0x1800095f6  mov     rdx, [rsp+0F8h+var_B0]
0x1800095fb  cmp     rdx, [rsp+0F8h+var_A8]
0x180009600  jz      short loc_18000960D
0x180009602  mov     [rdx], rax
0x180009605  add     [rsp+0F8h+var_B0], 8
0x18000960b  jmp     short loc_180009629
0x18000960d  lea     r8, [rsp+0F8h+arg_8]
0x180009615  lea     rcx, [rsp+0F8h+var_B8]
0x18000961a  call    ??$_Emplace_reallocate@AEBQEAVServiceAccountUserSession@@@?$vector@PEAVServiceAccountUserSession@@V?$allocator@PEAVServiceAccountUserSession@@@std@@@std@@AEAAPEAPEAVServiceAccountUserSession@@QEAPEAV2@AEBQEAV2@@Z; std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(ServiceAccountUserSession * * const,ServiceAccountUserSession * const &)
0x18000961f  jmp     short loc_180009629
0x180009621  mov     rsi, [rsp+0F8h+arg_0]
0x180009629  xor     r9d, r9d; int
0x18000962c  lea     r8, GUID_NULL; struct _GUID *
0x180009633  xor     edx, edx; struct IBackgroundCopyCallback *
0x180009635  mov     rcx, r14; this
0x180009638  call    ?SetNotifyInterface@CJob@@QEAAXPEAUIBackgroundCopyCallback@@AEBU_GUID@@H@Z; CJob::SetNotifyInterface(IBackgroundCopyCallback *,_GUID const &,int)
0x18000963d  nop
0x18000963e  test    rsi, rsi
0x180009641  jz      short loc_180009653
0x180009643  mov     rax, [rsi]
0x180009646  mov     rcx, rsi
0x180009649  mov     rax, [rax+10h]
0x18000964d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009652  nop
0x180009653  mov     rbx, [rbx+8]
0x180009657  jmp     loc_18000957D
0x18000965c  mov     rax, rbx
0x18000965f  lea     rcx, [rbx-270h]
0x180009666  neg     rax
0x180009669  sbb     r15, r15
0x18000966c  and     r15, rcx
0x18000966f  mov     [rsp+0F8h+arg_0], 0
0x18000967b  lea     rdx, [rsp+0F8h+arg_0]; struct IBackgroundCopyCallback **
0x180009683  mov     rcx, r15; this
0x180009686  call    ?GetNotifyInterface@CJob@@QEBAJPEAPEAUIBackgroundCopyCallback@@@Z; CJob::GetNotifyInterface(IBackgroundCopyCallback * *)
0x18000968b  test    eax, eax
0x18000968d  js      short loc_1800096D4
0x18000968f  mov     rax, [rsp+0F8h+arg_0]
0x180009697  xor     esi, esi
0x180009699  mov     [rsp+0F8h+arg_0], rsi
0x1800096a1  mov     [rsp+0F8h+arg_8], rax
0x1800096a9  mov     rdx, [rsp+0F8h+var_B0]
0x1800096ae  cmp     rdx, [rsp+0F8h+var_A8]
0x1800096b3  jz      short loc_1800096C0
0x1800096b5  mov     [rdx], rax
0x1800096b8  add     [rsp+0F8h+var_B0], 8
0x1800096be  jmp     short loc_1800096DC
0x1800096c0  lea     r8, [rsp+0F8h+arg_8]
0x1800096c8  lea     rcx, [rsp+0F8h+var_B8]
0x1800096cd  call    ??$_Emplace_reallocate@AEBQEAVServiceAccountUserSession@@@?$vector@PEAVServiceAccountUserSession@@V?$allocator@PEAVServiceAccountUserSession@@@std@@@std@@AEAAPEAPEAVServiceAccountUserSession@@QEAPEAV2@AEBQEAV2@@Z; std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(ServiceAccountUserSession * * const,ServiceAccountUserSession * const &)
0x1800096d2  jmp     short loc_1800096DC
0x1800096d4  mov     rsi, [rsp+0F8h+arg_0]
0x1800096dc  xor     r9d, r9d; int
0x1800096df  lea     r8, GUID_NULL; struct _GUID *
0x1800096e6  xor     edx, edx; struct IBackgroundCopyCallback *
0x1800096e8  mov     rcx, r15; this
0x1800096eb  call    ?SetNotifyInterface@CJob@@QEAAXPEAUIBackgroundCopyCallback@@AEBU_GUID@@H@Z; CJob::SetNotifyInterface(IBackgroundCopyCallback *,_GUID const &,int)
0x1800096f0  nop
0x1800096f1  test    rsi, rsi
0x1800096f4  jz      short loc_180009706
0x1800096f6  mov     rax, [rsi]
0x1800096f9  mov     rcx, rsi
0x1800096fc  mov     rax, [rax+10h]
0x180009700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009705  nop
0x180009706  mov     rbx, [rbx+8]
0x18000970a  jmp     loc_180009569
0x18000970f  jmp     short $+2
0x180009711  mov     rbx, [rsp+0F8h+var_B8]
0x180009716  mov     rsi, [rsp+0F8h+var_B0]
0x18000971b  cmp     rbx, rsi
0x18000971e  jz      loc_1800097DD
0x180009724  mov     r14d, 80004005h
0x18000972a  mov     rdi, [rbx]
0x18000972d  call    cs:__imp_GetCurrentThreadId
0x180009733  mov     [rsp+0F8h+Parameter], eax
0x180009737  mov     [rsp+0F8h+var_9C], 0
0x18000973c  mov     [rsp+0F8h+var_98], r14d
0x180009741  mov     [rsp+0F8h+phNewTimer], 0
0x18000974a  xor     ecx, ecx; pReserved
0x18000974c  call    cs:__imp_CoEnableCallCancellation
0x180009752  mov     [rsp+0F8h+var_98], eax
0x180009756  test    eax, eax
0x180009758  js      short loc_18000978C
0x18000975a  mov     [rsp+0F8h+Flags], 0; Flags
0x180009762  mov     [rsp+0F8h+Period], 3E8h; Period
0x18000976a  mov     [rsp+0F8h+DueTime], 7D0h; DueTime
0x180009772  lea     r9, [rsp+0F8h+Parameter]; Parameter
0x180009777  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18000977e  xor     edx, edx; TimerQueue
0x180009780  lea     rcx, [rsp+0F8h+phNewTimer]; phNewTimer
0x180009785  call    cs:__imp_CreateTimerQueueTimer
0x18000978b  nop
0x18000978c  test    rdi, rdi
0x18000978f  jz      short loc_1800097A1
0x180009791  mov     rax, [rdi]
0x180009794  mov     rcx, rdi
0x180009797  mov     rax, [rax+10h]
0x18000979b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097a0  nop
0x1800097a1  cmp     [rsp+0F8h+var_98], 0
0x1800097a6  jl      short loc_1800097CB
0x1800097a8  mov     [rsp+0F8h+var_98], r14d
0x1800097ad  xor     ecx, ecx; pReserved
0x1800097af  call    cs:__imp_CoDisableCallCancellation
0x1800097b5  mov     rdx, [rsp+0F8h+phNewTimer]; Timer
0x1800097ba  test    rdx, rdx
0x1800097bd  jz      short loc_1800097CB
0x1800097bf  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800097c3  xor     ecx, ecx; TimerQueue
0x1800097c5  call    cs:__imp_DeleteTimerQueueTimer
0x1800097cb  add     rbx, 8
0x1800097cf  cmp     rbx, rsi
0x1800097d2  jnz     loc_18000972A
0x1800097d8  mov     rbx, [rsp+0F8h+var_B8]
0x1800097dd  test    rbx, rbx
0x1800097e0  jz      short loc_1800097F7
0x1800097e2  mov     rdx, [rsp+0F8h+var_A8]
0x1800097e7  sub     rdx, rbx
0x1800097ea  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800097ee  mov     rcx, rbx
0x1800097f1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800097f6  nop
0x1800097f7  lea     r11, [rsp+0F8h+var_18]
0x1800097ff  mov     rbx, [r11+30h]
0x180009803  mov     rsi, [r11+38h]
0x180009807  mov     rsp, r11
0x18000980a  pop     r15
0x18000980c  pop     r14
0x18000980e  pop     rdi
0x18000980f  retn
```

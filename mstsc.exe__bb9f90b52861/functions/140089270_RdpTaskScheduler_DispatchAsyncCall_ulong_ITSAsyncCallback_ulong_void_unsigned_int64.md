# RdpTaskScheduler::DispatchAsyncCall(ulong,ITSAsyncCallback *,ulong,void *,unsigned __int64)

- ea: `0x140089270`
- end: `0x1400895b0`
- name: `?DispatchAsyncCall@RdpTaskScheduler@@UEAAJKPEAVITSAsyncCallback@@KPEAX_K@Z`
- size: `832`
- prototype: `__int64 __fastcall(RdpTaskScheduler *__hidden this, unsigned int, struct ITSAsyncCallback *, unsigned int, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update`

## callees

- `0x140001940`
- `0x1400019e8`
- `0x140088628`
- `0x14008891c`
- `0x140088aa8`
- `0x140089270`
- `0x14008a4dc`
- `0x14008aba0`
- `0x140114010`

## import_xrefs

- `KERNEL32!IsThreadpoolTimerSet` at `0x140089419`
- `KERNEL32!IsThreadpoolTimerSet` at `0x140089419`
- `KERNEL32!SubmitThreadpoolWork` at `0x14008950c`
- `KERNEL32!SubmitThreadpoolWork` at `0x14008950c`
- `KERNEL32!GetTickCount64` at `0x140089294`
- `KERNEL32!GetTickCount64` at `0x140089294`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400892ab`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400892ab`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400894e8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089590`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400894e8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089590`

## string_xrefs

- `0x14008934c`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140089402`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008948d`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140089535`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008940d`: `DispatchAsyncCall - m_timerThreadPool is null`
- `0x140089498`: `DispatchAsyncCall - m_workThreadPool is null`
- `0x1400892cc`: `Task scheduler queue`
- `0x140089357`: `asyncTask.SetBuffer failed`
- `0x140089547`: `Adding task to task list failed`

## pseudocode

```c
__int64 __fastcall RdpTaskScheduler::DispatchAsyncCall(
        RdpTaskScheduler *this,
        unsigned int a2,
        struct ITSAsyncCallback *a3,
        unsigned int a4,
        void *a5,
        unsigned __int64 a6)
{
  RTL_SRWLOCK *v10; // rdi
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  const char **v14; // rcx
  int v15; // r8d
  int v16; // r9d
  __int64 *v17; // rdx
  struct _TP_TIMER *v18; // rcx
  __int64 *v19; // rdx
  const char *v20; // rax
  const char **v22; // [rsp+20h] [rbp-49h]
  const char **v23; // [rsp+30h] [rbp-39h]
  const char *v24; // [rsp+50h] [rbp-19h] BYREF
  const char *v25; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v26[80]; // [rsp+60h] [rbp-9h] BYREF
  const char *v27; // [rsp+C0h] [rbp+57h] BYREF
  int v28; // [rsp+C8h] [rbp+5Fh] BYREF
  int v29; // [rsp+D8h] [rbp+6Fh] BYREF

  v10 = (RTL_SRWLOCK *)((char *)this + 232);
  v27 = (const char *)(a2 + GetTickCount64());
  AcquireSRWLockExclusive(v10);
  if ( (unsigned int)dword_140152118 > 5 )
  {
    v28 = *((_DWORD *)this + 50);
    v24 = "Task scheduler queue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)qword_1401437A8,
      v12,
      v13,
      (__int64)&v24,
      (__int64)&v28);
  }
  RdpTaskScheduler::AsyncTask::AsyncTask((RdpTaskScheduler::AsyncTask *)v26, a3, a6);
  if ( a4 && a5 && RdpTaskScheduler::AsyncTask::SetBuffer((RdpTaskScheduler::AsyncTask *)v26, a4, a5) < 0 )
  {
    if ( (unsigned int)dword_140152118 > 2 )
    {
      v28 = 641;
      v27 = "DispatchAsyncCall";
      v17 = qword_140143760;
      v24 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v25 = "asyncTask.SetBuffer failed";
      v23 = &v24;
      v22 = &v25;
LABEL_25:
      v29 = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v14,
        (_DWORD)v17,
        v15,
        v16,
        (__int64)v22,
        (__int64)&v29,
        (__int64)v23,
        (__int64)&v28,
        (__int64)&v27);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  utl::_Tree<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>>,utl::pair<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> const,RdpTaskScheduler::AsyncTask>,utl::less<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>>>,utl::allocator<utl::pair<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> const,RdpTaskScheduler::AsyncTask>>,1>::emplace<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> &,RdpTaskScheduler::AsyncTask,0>(
    (char *)this + 176,
    &v25,
    &v27,
    v26);
  if ( v25 && v25 != (char *)this + 176 )
  {
    if ( a2 )
    {
      v18 = (struct _TP_TIMER *)*((_QWORD *)this + 19);
      if ( v18 )
      {
        if ( !IsThreadpoolTimerSet(v18) || (__int64)v27 < *((_QWORD *)this + 21) )
        {
          *((_QWORD *)this + 21) = v27;
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
          RdpTaskScheduler::ResetTimer(this, a2);
        }
        goto LABEL_21;
      }
      if ( (unsigned int)dword_140152118 > 2 )
      {
        v28 = 659;
        v27 = "DispatchAsyncCall";
        v19 = qword_140143490;
        v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
        v20 = "DispatchAsyncCall - m_timerThreadPool is null";
LABEL_20:
        v24 = v20;
        v29 = -2147467261;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)v18,
          (_DWORD)v19,
          v15,
          v16,
          (__int64)&v24,
          (__int64)&v29,
          (__int64)&v25,
          (__int64)&v28,
          (__int64)&v27);
      }
    }
    else
    {
      if ( *((_QWORD *)this + 18) )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
        SubmitThreadpoolWork(*((PTP_WORK *)this + 18));
        goto LABEL_21;
      }
      if ( (unsigned int)dword_140152118 > 2 )
      {
        v28 = 682;
        v27 = "DispatchAsyncCall";
        v19 = qword_140143448;
        v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
        v20 = "DispatchAsyncCall - m_workThreadPool is null";
        goto LABEL_20;
      }
    }
LABEL_21:
    RdpTaskScheduler::AsyncTask::~AsyncTask((RdpTaskScheduler::AsyncTask *)v26);
    ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
    return 0;
  }
  if ( (unsigned int)dword_140152118 > 2 )
  {
    v28 = 650;
    v27 = "DispatchAsyncCall";
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v17 = qword_1401434D8;
    v24 = "Adding task to task list failed";
    v23 = &v25;
    v14 = &v24;
    v22 = &v24;
    goto LABEL_25;
  }
LABEL_26:
  RdpTaskScheduler::AsyncTask::~AsyncTask((RdpTaskScheduler::AsyncTask *)v26);
  ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140089270  mov     [rsp-8+arg_10], rbx
0x140089275  push    rbp
0x140089276  push    rsi
0x140089277  push    rdi
0x140089278  push    r14
0x14008927a  push    r15
0x14008927c  lea     rbp, [rsp-27h]
0x140089281  sub     rsp, 90h
0x140089288  mov     esi, r9d
0x14008928b  mov     r14d, edx
0x14008928e  mov     r15, r8
0x140089291  mov     rbx, rcx
0x140089294  call    cs:__imp_GetTickCount64
0x14008929a  add     rax, r14
0x14008929d  lea     rdi, [rbx+0E8h]
0x1400892a4  mov     rcx, rdi; SRWLock
0x1400892a7  mov     [rbp+47h+arg_0], rax
0x1400892ab  call    cs:__imp_AcquireSRWLockExclusive
0x1400892b1  mov     eax, cs:dword_140152118
0x1400892b7  cmp     eax, 5
0x1400892ba  jbe     short loc_1400892EE
0x1400892bc  mov     eax, [rbx+0C8h]
0x1400892c2  lea     rdx, qword_1401437A8
0x1400892c9  mov     [rbp+47h+arg_8], eax
0x1400892cc  lea     rax, aTaskSchedulerQ; "Task scheduler queue"
0x1400892d3  mov     [rbp+47h+var_60], rax
0x1400892d7  lea     rax, [rbp+47h+arg_8]
0x1400892db  mov     [rsp+0B0h+var_88], rax
0x1400892e0  lea     rax, [rbp+47h+var_60]
0x1400892e4  mov     [rsp+0B0h+var_90], rax
0x1400892e9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400892ee  mov     r8, [rbp+47h+arg_28]; unsigned __int64
0x1400892f2  lea     rcx, [rbp+47h+var_50]; this
0x1400892f6  mov     rdx, r15; struct ITSAsyncCallback *
0x1400892f9  call    ??0AsyncTask@RdpTaskScheduler@@QEAA@PEAVITSAsyncCallback@@_K@Z; RdpTaskScheduler::AsyncTask::AsyncTask(ITSAsyncCallback *,unsigned __int64)
0x1400892fe  mov     r15d, 8007000Eh
0x140089304  test    esi, esi
0x140089306  jz      loc_140089394
0x14008930c  mov     r8, [rbp+47h+arg_20]; void *
0x140089310  test    r8, r8
0x140089313  jz      short loc_140089394
0x140089315  mov     edx, esi; unsigned int
0x140089317  lea     rcx, [rbp+47h+var_50]; this
0x14008931b  call    ?SetBuffer@AsyncTask@RdpTaskScheduler@@QEAAJKPEAX@Z; RdpTaskScheduler::AsyncTask::SetBuffer(ulong,void *)
0x140089320  test    eax, eax
0x140089322  jns     short loc_140089394
0x140089324  mov     eax, cs:dword_140152118
0x14008932a  cmp     eax, 2
0x14008932d  jbe     loc_140089584
0x140089333  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x14008933a  mov     [rbp+47h+arg_8], 281h
0x140089341  mov     [rbp+47h+arg_0], rax
0x140089345  lea     rdx, qword_140143760
0x14008934c  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140089353  mov     [rbp+47h+var_60], rax
0x140089357  lea     rax, aAsynctaskSetbu; "asyncTask.SetBuffer failed"
0x14008935e  mov     [rbp+47h+var_58], rax
0x140089362  lea     rax, [rbp+47h+arg_0]
0x140089366  mov     [rsp+0B0h+var_70], rax
0x14008936b  lea     rax, [rbp+47h+arg_8]
0x14008936f  mov     [rsp+0B0h+var_78], rax
0x140089374  lea     rax, [rbp+47h+var_60]
0x140089378  mov     [rsp+0B0h+var_80], rax
0x14008937d  lea     rax, [rbp+47h+arg_18]
0x140089381  mov     [rsp+0B0h+var_88], rax
0x140089386  lea     rax, [rbp+47h+var_58]
0x14008938a  mov     [rsp+0B0h+var_90], rax
0x14008938f  jmp     loc_14008957B
0x140089394  lea     rsi, [rbx+0B0h]
0x14008939b  mov     rcx, rsi
0x14008939e  lea     r9, [rbp+47h+var_50]
0x1400893a2  lea     r8, [rbp+47h+arg_0]
0x1400893a6  lea     rdx, [rbp+47h+var_58]
0x1400893aa  call    ??$emplace@AEAV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@$0A@@?$_Tree@V?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@U?$pair@$$CBV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@@3@U?$less@V?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@@3@V?$allocator@U?$pair@$$CBV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@@utl@@@3@$00@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@@utl@@@1@AEAV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@1@$$QEAUAsyncTask@RdpTaskScheduler@@@Z; utl::_Tree<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>>,utl::pair<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> const,RdpTaskScheduler::AsyncTask>,utl::less<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>>>,utl::allocator<utl::pair<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> const,RdpTaskScheduler::AsyncTask>>,1>::emplace<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> &,RdpTaskScheduler::AsyncTask,0>(utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> &,RdpTaskScheduler::AsyncTask &&)
0x1400893af  mov     rax, [rbp+47h+var_58]
0x1400893b3  test    rax, rax
0x1400893b6  jz      loc_140089514
0x1400893bc  cmp     rax, rsi
0x1400893bf  jz      loc_140089514
0x1400893c5  test    r14d, r14d
0x1400893c8  jz      loc_14008945B
0x1400893ce  mov     rcx, [rbx+98h]; pti
0x1400893d5  test    rcx, rcx
0x1400893d8  jnz     short loc_140089419
0x1400893da  mov     eax, cs:dword_140152118
0x1400893e0  cmp     eax, 2
0x1400893e3  jbe     loc_1400894DC
0x1400893e9  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x1400893f0  mov     [rbp+47h+arg_8], 293h
0x1400893f7  mov     [rbp+47h+arg_0], rax
0x1400893fb  lea     rdx, qword_140143490
0x140089402  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140089409  mov     [rbp+47h+var_58], rax
0x14008940d  lea     rax, aDispatchasyncc_2; "DispatchAsyncCall - m_timerThreadPool i"...
0x140089414  jmp     loc_14008949F
0x140089419  call    cs:__imp_IsThreadpoolTimerSet
0x14008941f  mov     rcx, [rbp+47h+arg_0]
0x140089423  test    eax, eax
0x140089425  jz      short loc_140089434
0x140089427  cmp     rcx, [rbx+0A8h]
0x14008942e  jge     loc_1400894DC
0x140089434  mov     [rbx+0A8h], rcx
0x14008943b  mov     rcx, [rbx+30h]
0x14008943f  mov     rax, [rcx]
0x140089442  mov     rax, [rax+8]
0x140089446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008944b  mov     edx, r14d; unsigned int
0x14008944e  mov     rcx, rbx; this
0x140089451  call    ?ResetTimer@RdpTaskScheduler@@IEAAXK@Z; RdpTaskScheduler::ResetTimer(ulong)
0x140089456  jmp     loc_1400894DC
0x14008945b  cmp     qword ptr [rbx+90h], 0
0x140089463  jnz     loc_1400894F5
0x140089469  mov     eax, cs:dword_140152118
0x14008946f  cmp     eax, 2
0x140089472  jbe     short loc_1400894DC
0x140089474  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x14008947b  mov     [rbp+47h+arg_8], 2AAh
0x140089482  mov     [rbp+47h+arg_0], rax
0x140089486  lea     rdx, qword_140143448
0x14008948d  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140089494  mov     [rbp+47h+var_58], rax
0x140089498  lea     rax, aDispatchasyncc_0; "DispatchAsyncCall - m_workThreadPool is"...
0x14008949f  mov     [rbp+47h+var_60], rax
0x1400894a3  lea     rax, [rbp+47h+arg_0]
0x1400894a7  mov     [rsp+0B0h+var_70], rax
0x1400894ac  lea     rax, [rbp+47h+arg_8]
0x1400894b0  mov     [rsp+0B0h+var_78], rax
0x1400894b5  lea     rax, [rbp+47h+var_58]
0x1400894b9  mov     [rsp+0B0h+var_80], rax
0x1400894be  lea     rax, [rbp+47h+arg_18]
0x1400894c2  mov     [rsp+0B0h+var_88], rax
0x1400894c7  lea     rax, [rbp+47h+var_60]
0x1400894cb  mov     [rsp+0B0h+var_90], rax
0x1400894d0  mov     [rbp+47h+arg_18], 80004003h
0x1400894d7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400894dc  lea     rcx, [rbp+47h+var_50]; this
0x1400894e0  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x1400894e5  mov     rcx, rdi; SRWLock
0x1400894e8  call    cs:__imp_ReleaseSRWLockExclusive
0x1400894ee  xor     eax, eax
0x1400894f0  jmp     loc_140089599
0x1400894f5  mov     rcx, [rbx+30h]
0x1400894f9  mov     rax, [rcx]
0x1400894fc  mov     rax, [rax+8]
0x140089500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089505  mov     rcx, [rbx+90h]; pwk
0x14008950c  call    cs:__imp_SubmitThreadpoolWork
0x140089512  jmp     short loc_1400894DC
0x140089514  mov     eax, cs:dword_140152118
0x14008951a  cmp     eax, 2
0x14008951d  jbe     short loc_140089584
0x14008951f  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x140089526  mov     [rbp+47h+arg_8], 28Ah
0x14008952d  mov     [rbp+47h+arg_0], rax
0x140089531  lea     rcx, [rbp+47h+var_58]
0x140089535  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008953c  mov     [rbp+47h+var_58], rax
0x140089540  lea     rdx, qword_1401434D8
0x140089547  lea     rax, aAddingTaskToTa; "Adding task to task list failed"
0x14008954e  mov     [rbp+47h+var_60], rax
0x140089552  lea     rax, [rbp+47h+arg_0]
0x140089556  mov     [rsp+0B0h+var_70], rax
0x14008955b  lea     rax, [rbp+47h+arg_8]
0x14008955f  mov     [rsp+0B0h+var_78], rax
0x140089564  mov     [rsp+0B0h+var_80], rcx
0x140089569  lea     rcx, [rbp+47h+arg_18]
0x14008956d  mov     [rsp+0B0h+var_88], rcx
0x140089572  lea     rcx, [rbp+47h+var_60]
0x140089576  mov     [rsp+0B0h+var_90], rcx
0x14008957b  mov     [rbp+47h+arg_18], r15d
0x14008957f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140089584  lea     rcx, [rbp+47h+var_50]; this
0x140089588  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x14008958d  mov     rcx, rdi; SRWLock
0x140089590  call    cs:__imp_ReleaseSRWLockExclusive
0x140089596  mov     eax, r15d
0x140089599  mov     rbx, [rsp+0B0h+arg_10]
0x1400895a1  add     rsp, 90h
0x1400895a8  pop     r15
0x1400895aa  pop     r14
0x1400895ac  pop     rdi
0x1400895ad  pop     rsi
0x1400895ae  pop     rbp
0x1400895af  retn
```

# RdpTaskScheduler::DispatchAsyncCall(ulong,ITSAsyncCallback *,ulong,void *,unsigned __int64)

- ea: `0x140087100`
- end: `0x140087440`
- name: `?DispatchAsyncCall@RdpTaskScheduler@@UEAAJKPEAVITSAsyncCallback@@KPEAX_K@Z`
- size: `832`
- prototype: `__int64 __fastcall(RdpTaskScheduler *__hidden this, unsigned int, struct ITSAsyncCallback *, unsigned int, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update`

## callees

- `0x140001940`
- `0x1400019e8`
- `0x1400864b8`
- `0x1400867ac`
- `0x140086938`
- `0x140087100`
- `0x14008836c`
- `0x140088a30`
- `0x140112010`

## import_xrefs

- `KERNEL32!IsThreadpoolTimerSet` at `0x1400872a9`
- `KERNEL32!IsThreadpoolTimerSet` at `0x1400872a9`
- `KERNEL32!SubmitThreadpoolWork` at `0x14008739c`
- `KERNEL32!SubmitThreadpoolWork` at `0x14008739c`
- `KERNEL32!GetTickCount64` at `0x140087124`
- `KERNEL32!GetTickCount64` at `0x140087124`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14008713b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14008713b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087378`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087420`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087378`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087420`

## string_xrefs

- `0x1400871dc`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140087292`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008731d`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1400873c5`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008729d`: `DispatchAsyncCall - m_timerThreadPool is null`
- `0x140087328`: `DispatchAsyncCall - m_workThreadPool is null`
- `0x14008715c`: `Task scheduler queue`
- `0x1400871e7`: `asyncTask.SetBuffer failed`
- `0x1400873d7`: `Adding task to task list failed`

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
  if ( (unsigned int)dword_140150118 > 5 )
  {
    v28 = *((_DWORD *)this + 50);
    v24 = "Task scheduler queue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)qword_140141670,
      v12,
      v13,
      (__int64)&v24,
      (__int64)&v28);
  }
  RdpTaskScheduler::AsyncTask::AsyncTask((RdpTaskScheduler::AsyncTask *)v26, a3, a6);
  if ( a4 && a5 && RdpTaskScheduler::AsyncTask::SetBuffer((RdpTaskScheduler::AsyncTask *)v26, a4, a5) < 0 )
  {
    if ( (unsigned int)dword_140150118 > 2 )
    {
      v28 = 641;
      v27 = "DispatchAsyncCall";
      v17 = qword_140141628;
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
      if ( (unsigned int)dword_140150118 > 2 )
      {
        v28 = 659;
        v27 = "DispatchAsyncCall";
        v19 = qword_140141350;
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
      if ( (unsigned int)dword_140150118 > 2 )
      {
        v28 = 682;
        v27 = "DispatchAsyncCall";
        v19 = qword_140141308;
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
  if ( (unsigned int)dword_140150118 > 2 )
  {
    v28 = 650;
    v27 = "DispatchAsyncCall";
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v17 = qword_1401415E0;
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
0x140087100  mov     [rsp-8+arg_10], rbx
0x140087105  push    rbp
0x140087106  push    rsi
0x140087107  push    rdi
0x140087108  push    r14
0x14008710a  push    r15
0x14008710c  lea     rbp, [rsp-27h]
0x140087111  sub     rsp, 90h
0x140087118  mov     esi, r9d
0x14008711b  mov     r14d, edx
0x14008711e  mov     r15, r8
0x140087121  mov     rbx, rcx
0x140087124  call    cs:__imp_GetTickCount64
0x14008712a  add     rax, r14
0x14008712d  lea     rdi, [rbx+0E8h]
0x140087134  mov     rcx, rdi; SRWLock
0x140087137  mov     [rbp+47h+arg_0], rax
0x14008713b  call    cs:__imp_AcquireSRWLockExclusive
0x140087141  mov     eax, cs:dword_140150118
0x140087147  cmp     eax, 5
0x14008714a  jbe     short loc_14008717E
0x14008714c  mov     eax, [rbx+0C8h]
0x140087152  lea     rdx, qword_140141670
0x140087159  mov     [rbp+47h+arg_8], eax
0x14008715c  lea     rax, aTaskSchedulerQ; "Task scheduler queue"
0x140087163  mov     [rbp+47h+var_60], rax
0x140087167  lea     rax, [rbp+47h+arg_8]
0x14008716b  mov     [rsp+0B0h+var_88], rax
0x140087170  lea     rax, [rbp+47h+var_60]
0x140087174  mov     [rsp+0B0h+var_90], rax
0x140087179  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14008717e  mov     r8, [rbp+47h+arg_28]; unsigned __int64
0x140087182  lea     rcx, [rbp+47h+var_50]; this
0x140087186  mov     rdx, r15; struct ITSAsyncCallback *
0x140087189  call    ??0AsyncTask@RdpTaskScheduler@@QEAA@PEAVITSAsyncCallback@@_K@Z; RdpTaskScheduler::AsyncTask::AsyncTask(ITSAsyncCallback *,unsigned __int64)
0x14008718e  mov     r15d, 8007000Eh
0x140087194  test    esi, esi
0x140087196  jz      loc_140087224
0x14008719c  mov     r8, [rbp+47h+arg_20]; void *
0x1400871a0  test    r8, r8
0x1400871a3  jz      short loc_140087224
0x1400871a5  mov     edx, esi; unsigned int
0x1400871a7  lea     rcx, [rbp+47h+var_50]; this
0x1400871ab  call    ?SetBuffer@AsyncTask@RdpTaskScheduler@@QEAAJKPEAX@Z; RdpTaskScheduler::AsyncTask::SetBuffer(ulong,void *)
0x1400871b0  test    eax, eax
0x1400871b2  jns     short loc_140087224
0x1400871b4  mov     eax, cs:dword_140150118
0x1400871ba  cmp     eax, 2
0x1400871bd  jbe     loc_140087414
0x1400871c3  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x1400871ca  mov     [rbp+47h+arg_8], 281h
0x1400871d1  mov     [rbp+47h+arg_0], rax
0x1400871d5  lea     rdx, qword_140141628
0x1400871dc  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400871e3  mov     [rbp+47h+var_60], rax
0x1400871e7  lea     rax, aAsynctaskSetbu; "asyncTask.SetBuffer failed"
0x1400871ee  mov     [rbp+47h+var_58], rax
0x1400871f2  lea     rax, [rbp+47h+arg_0]
0x1400871f6  mov     [rsp+0B0h+var_70], rax
0x1400871fb  lea     rax, [rbp+47h+arg_8]
0x1400871ff  mov     [rsp+0B0h+var_78], rax
0x140087204  lea     rax, [rbp+47h+var_60]
0x140087208  mov     [rsp+0B0h+var_80], rax
0x14008720d  lea     rax, [rbp+47h+arg_18]
0x140087211  mov     [rsp+0B0h+var_88], rax
0x140087216  lea     rax, [rbp+47h+var_58]
0x14008721a  mov     [rsp+0B0h+var_90], rax
0x14008721f  jmp     loc_14008740B
0x140087224  lea     rsi, [rbx+0B0h]
0x14008722b  mov     rcx, rsi
0x14008722e  lea     r9, [rbp+47h+var_50]
0x140087232  lea     r8, [rbp+47h+arg_0]
0x140087236  lea     rdx, [rbp+47h+var_58]
0x14008723a  call    ??$emplace@AEAV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@$0A@@?$_Tree@V?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@U?$pair@$$CBV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@@3@U?$less@V?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@@3@V?$allocator@U?$pair@$$CBV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@@utl@@@3@$00@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@@utl@@@1@AEAV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@1@$$QEAUAsyncTask@RdpTaskScheduler@@@Z; utl::_Tree<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>>,utl::pair<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> const,RdpTaskScheduler::AsyncTask>,utl::less<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>>>,utl::allocator<utl::pair<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> const,RdpTaskScheduler::AsyncTask>>,1>::emplace<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> &,RdpTaskScheduler::AsyncTask,0>(utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> &,RdpTaskScheduler::AsyncTask &&)
0x14008723f  mov     rax, [rbp+47h+var_58]
0x140087243  test    rax, rax
0x140087246  jz      loc_1400873A4
0x14008724c  cmp     rax, rsi
0x14008724f  jz      loc_1400873A4
0x140087255  test    r14d, r14d
0x140087258  jz      loc_1400872EB
0x14008725e  mov     rcx, [rbx+98h]; pti
0x140087265  test    rcx, rcx
0x140087268  jnz     short loc_1400872A9
0x14008726a  mov     eax, cs:dword_140150118
0x140087270  cmp     eax, 2
0x140087273  jbe     loc_14008736C
0x140087279  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x140087280  mov     [rbp+47h+arg_8], 293h
0x140087287  mov     [rbp+47h+arg_0], rax
0x14008728b  lea     rdx, qword_140141350
0x140087292  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140087299  mov     [rbp+47h+var_58], rax
0x14008729d  lea     rax, aDispatchasyncc_2; "DispatchAsyncCall - m_timerThreadPool i"...
0x1400872a4  jmp     loc_14008732F
0x1400872a9  call    cs:__imp_IsThreadpoolTimerSet
0x1400872af  mov     rcx, [rbp+47h+arg_0]
0x1400872b3  test    eax, eax
0x1400872b5  jz      short loc_1400872C4
0x1400872b7  cmp     rcx, [rbx+0A8h]
0x1400872be  jge     loc_14008736C
0x1400872c4  mov     [rbx+0A8h], rcx
0x1400872cb  mov     rcx, [rbx+30h]
0x1400872cf  mov     rax, [rcx]
0x1400872d2  mov     rax, [rax+8]
0x1400872d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400872db  mov     edx, r14d; unsigned int
0x1400872de  mov     rcx, rbx; this
0x1400872e1  call    ?ResetTimer@RdpTaskScheduler@@IEAAXK@Z; RdpTaskScheduler::ResetTimer(ulong)
0x1400872e6  jmp     loc_14008736C
0x1400872eb  cmp     qword ptr [rbx+90h], 0
0x1400872f3  jnz     loc_140087385
0x1400872f9  mov     eax, cs:dword_140150118
0x1400872ff  cmp     eax, 2
0x140087302  jbe     short loc_14008736C
0x140087304  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x14008730b  mov     [rbp+47h+arg_8], 2AAh
0x140087312  mov     [rbp+47h+arg_0], rax
0x140087316  lea     rdx, qword_140141308
0x14008731d  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140087324  mov     [rbp+47h+var_58], rax
0x140087328  lea     rax, aDispatchasyncc_0; "DispatchAsyncCall - m_workThreadPool is"...
0x14008732f  mov     [rbp+47h+var_60], rax
0x140087333  lea     rax, [rbp+47h+arg_0]
0x140087337  mov     [rsp+0B0h+var_70], rax
0x14008733c  lea     rax, [rbp+47h+arg_8]
0x140087340  mov     [rsp+0B0h+var_78], rax
0x140087345  lea     rax, [rbp+47h+var_58]
0x140087349  mov     [rsp+0B0h+var_80], rax
0x14008734e  lea     rax, [rbp+47h+arg_18]
0x140087352  mov     [rsp+0B0h+var_88], rax
0x140087357  lea     rax, [rbp+47h+var_60]
0x14008735b  mov     [rsp+0B0h+var_90], rax
0x140087360  mov     [rbp+47h+arg_18], 80004003h
0x140087367  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14008736c  lea     rcx, [rbp+47h+var_50]; this
0x140087370  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x140087375  mov     rcx, rdi; SRWLock
0x140087378  call    cs:__imp_ReleaseSRWLockExclusive
0x14008737e  xor     eax, eax
0x140087380  jmp     loc_140087429
0x140087385  mov     rcx, [rbx+30h]
0x140087389  mov     rax, [rcx]
0x14008738c  mov     rax, [rax+8]
0x140087390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087395  mov     rcx, [rbx+90h]; pwk
0x14008739c  call    cs:__imp_SubmitThreadpoolWork
0x1400873a2  jmp     short loc_14008736C
0x1400873a4  mov     eax, cs:dword_140150118
0x1400873aa  cmp     eax, 2
0x1400873ad  jbe     short loc_140087414
0x1400873af  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x1400873b6  mov     [rbp+47h+arg_8], 28Ah
0x1400873bd  mov     [rbp+47h+arg_0], rax
0x1400873c1  lea     rcx, [rbp+47h+var_58]
0x1400873c5  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400873cc  mov     [rbp+47h+var_58], rax
0x1400873d0  lea     rdx, qword_1401415E0
0x1400873d7  lea     rax, aAddingTaskToTa; "Adding task to task list failed"
0x1400873de  mov     [rbp+47h+var_60], rax
0x1400873e2  lea     rax, [rbp+47h+arg_0]
0x1400873e6  mov     [rsp+0B0h+var_70], rax
0x1400873eb  lea     rax, [rbp+47h+arg_8]
0x1400873ef  mov     [rsp+0B0h+var_78], rax
0x1400873f4  mov     [rsp+0B0h+var_80], rcx
0x1400873f9  lea     rcx, [rbp+47h+arg_18]
0x1400873fd  mov     [rsp+0B0h+var_88], rcx
0x140087402  lea     rcx, [rbp+47h+var_60]
0x140087406  mov     [rsp+0B0h+var_90], rcx
0x14008740b  mov     [rbp+47h+arg_18], r15d
0x14008740f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140087414  lea     rcx, [rbp+47h+var_50]; this
0x140087418  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x14008741d  mov     rcx, rdi; SRWLock
0x140087420  call    cs:__imp_ReleaseSRWLockExclusive
0x140087426  mov     eax, r15d
0x140087429  mov     rbx, [rsp+0B0h+arg_10]
0x140087431  add     rsp, 90h
0x140087438  pop     r15
0x14008743a  pop     r14
0x14008743c  pop     rdi
0x14008743d  pop     rsi
0x14008743e  pop     rbp
0x14008743f  retn
```

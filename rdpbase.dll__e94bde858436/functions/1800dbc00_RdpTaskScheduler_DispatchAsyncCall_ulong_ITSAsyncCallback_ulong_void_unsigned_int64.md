# RdpTaskScheduler::DispatchAsyncCall(ulong,ITSAsyncCallback *,ulong,void *,unsigned __int64)

- ea: `0x1800dbc00`
- end: `0x1800dbf40`
- name: `?DispatchAsyncCall@RdpTaskScheduler@@UEAAJKPEAVITSAsyncCallback@@KPEAX_K@Z`
- size: `832`
- prototype: `__int64 __fastcall(RdpTaskScheduler *__hidden this, unsigned int, struct ITSAsyncCallback *, unsigned int, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update`

## callees

- `0x1800018a4`
- `0x180004a94`
- `0x1800db164`
- `0x1800db47c`
- `0x1800db608`
- `0x1800dbc00`
- `0x1800dcd24`
- `0x1800dd3e0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800dbc24`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800dbc24`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dbc3b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dbc3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dbe78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dbf20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dbe78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dbf20`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800dbda9`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800dbda9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dbe9c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dbe9c`

## string_xrefs

- `0x1800dbcdc`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dbd92`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dbe1d`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dbec5`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dbc5c`: `Task scheduler queue`
- `0x1800dbed7`: `Adding task to task list failed`
- `0x1800dbce7`: `asyncTask.SetBuffer failed`
- `0x1800dbe28`: `DispatchAsyncCall - m_workThreadPool is null`
- `0x1800dbd9d`: `DispatchAsyncCall - m_timerThreadPool is null`

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
  char *v17; // rdx
  struct _TP_TIMER *v18; // rcx
  char *v19; // rdx
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
  if ( (unsigned int)CallbackContext > 5 )
  {
    v28 = *((_DWORD *)this + 50);
    v24 = "Task scheduler queue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)byte_1801BBF95,
      v12,
      v13,
      (__int64)&v24,
      (__int64)&v28);
  }
  RdpTaskScheduler::AsyncTask::AsyncTask((RdpTaskScheduler::AsyncTask *)v26, a3, a6);
  if ( a4 && a5 && RdpTaskScheduler::AsyncTask::SetBuffer((RdpTaskScheduler::AsyncTask *)v26, a4, a5) < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v28 = 641;
      v27 = "DispatchAsyncCall";
      v17 = byte_1801BBEBD;
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
      if ( (unsigned int)CallbackContext > 2 )
      {
        v28 = 659;
        v27 = "DispatchAsyncCall";
        v19 = byte_1801BBE75;
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
      if ( (unsigned int)CallbackContext > 2 )
      {
        v28 = 682;
        v27 = "DispatchAsyncCall";
        v19 = byte_1801BBDE5;
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
  if ( (unsigned int)CallbackContext > 2 )
  {
    v28 = 650;
    v27 = "DispatchAsyncCall";
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v17 = byte_1801BBF05;
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
0x1800dbc00  mov     [rsp-8+arg_10], rbx
0x1800dbc05  push    rbp
0x1800dbc06  push    rsi
0x1800dbc07  push    rdi
0x1800dbc08  push    r14
0x1800dbc0a  push    r15
0x1800dbc0c  lea     rbp, [rsp-27h]
0x1800dbc11  sub     rsp, 90h
0x1800dbc18  mov     esi, r9d
0x1800dbc1b  mov     r14d, edx
0x1800dbc1e  mov     r15, r8
0x1800dbc21  mov     rbx, rcx
0x1800dbc24  call    cs:__imp_GetTickCount64
0x1800dbc2a  add     rax, r14
0x1800dbc2d  lea     rdi, [rbx+0E8h]
0x1800dbc34  mov     rcx, rdi; SRWLock
0x1800dbc37  mov     [rbp+47h+arg_0], rax
0x1800dbc3b  call    cs:__imp_AcquireSRWLockExclusive
0x1800dbc41  mov     eax, cs:CallbackContext
0x1800dbc47  cmp     eax, 5
0x1800dbc4a  jbe     short loc_1800DBC7E
0x1800dbc4c  mov     eax, [rbx+0C8h]
0x1800dbc52  lea     rdx, byte_1801BBF95
0x1800dbc59  mov     [rbp+47h+arg_8], eax
0x1800dbc5c  lea     rax, aTaskSchedulerQ; "Task scheduler queue"
0x1800dbc63  mov     [rbp+47h+var_60], rax
0x1800dbc67  lea     rax, [rbp+47h+arg_8]
0x1800dbc6b  mov     [rsp+0B0h+var_88], rax
0x1800dbc70  lea     rax, [rbp+47h+var_60]
0x1800dbc74  mov     [rsp+0B0h+var_90], rax
0x1800dbc79  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800dbc7e  mov     r8, [rbp+47h+arg_28]; unsigned __int64
0x1800dbc82  lea     rcx, [rbp+47h+var_50]; this
0x1800dbc86  mov     rdx, r15; struct ITSAsyncCallback *
0x1800dbc89  call    ??0AsyncTask@RdpTaskScheduler@@QEAA@PEAVITSAsyncCallback@@_K@Z; RdpTaskScheduler::AsyncTask::AsyncTask(ITSAsyncCallback *,unsigned __int64)
0x1800dbc8e  mov     r15d, 8007000Eh
0x1800dbc94  test    esi, esi
0x1800dbc96  jz      loc_1800DBD24
0x1800dbc9c  mov     r8, [rbp+47h+arg_20]; void *
0x1800dbca0  test    r8, r8
0x1800dbca3  jz      short loc_1800DBD24
0x1800dbca5  mov     edx, esi; unsigned int
0x1800dbca7  lea     rcx, [rbp+47h+var_50]; this
0x1800dbcab  call    ?SetBuffer@AsyncTask@RdpTaskScheduler@@QEAAJKPEAX@Z; RdpTaskScheduler::AsyncTask::SetBuffer(ulong,void *)
0x1800dbcb0  test    eax, eax
0x1800dbcb2  jns     short loc_1800DBD24
0x1800dbcb4  mov     eax, cs:CallbackContext
0x1800dbcba  cmp     eax, 2
0x1800dbcbd  jbe     loc_1800DBF14
0x1800dbcc3  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x1800dbcca  mov     [rbp+47h+arg_8], 281h
0x1800dbcd1  mov     [rbp+47h+arg_0], rax
0x1800dbcd5  lea     rdx, byte_1801BBEBD
0x1800dbcdc  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dbce3  mov     [rbp+47h+var_60], rax
0x1800dbce7  lea     rax, aAsynctaskSetbu; "asyncTask.SetBuffer failed"
0x1800dbcee  mov     [rbp+47h+var_58], rax
0x1800dbcf2  lea     rax, [rbp+47h+arg_0]
0x1800dbcf6  mov     [rsp+0B0h+var_70], rax
0x1800dbcfb  lea     rax, [rbp+47h+arg_8]
0x1800dbcff  mov     [rsp+0B0h+var_78], rax
0x1800dbd04  lea     rax, [rbp+47h+var_60]
0x1800dbd08  mov     [rsp+0B0h+var_80], rax
0x1800dbd0d  lea     rax, [rbp+47h+arg_18]
0x1800dbd11  mov     [rsp+0B0h+var_88], rax
0x1800dbd16  lea     rax, [rbp+47h+var_58]
0x1800dbd1a  mov     [rsp+0B0h+var_90], rax
0x1800dbd1f  jmp     loc_1800DBF0B
0x1800dbd24  lea     rsi, [rbx+0B0h]
0x1800dbd2b  mov     rcx, rsi
0x1800dbd2e  lea     r9, [rbp+47h+var_50]
0x1800dbd32  lea     r8, [rbp+47h+arg_0]
0x1800dbd36  lea     rdx, [rbp+47h+var_58]
0x1800dbd3a  call    ??$emplace@AEAV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@$0A@@?$_Tree@V?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@U?$pair@$$CBV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@@3@U?$less@V?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@@3@V?$allocator@U?$pair@$$CBV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@@utl@@@3@$00@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@utl@@UAsyncTask@RdpTaskScheduler@@@utl@@@1@AEAV?$time_point@Vsteady_clock@chrono@utl@@V?$duration@_JV?$ratio@$00$0DOI@@utl@@@23@@chrono@1@$$QEAUAsyncTask@RdpTaskScheduler@@@Z; utl::_Tree<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>>,utl::pair<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> const,RdpTaskScheduler::AsyncTask>,utl::less<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>>>,utl::allocator<utl::pair<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> const,RdpTaskScheduler::AsyncTask>>,1>::emplace<utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> &,RdpTaskScheduler::AsyncTask,0>(utl::chrono::time_point<utl::chrono::steady_clock,utl::chrono::duration<__int64,utl::ratio<1,1000>>> &,RdpTaskScheduler::AsyncTask &&)
0x1800dbd3f  mov     rax, [rbp+47h+var_58]
0x1800dbd43  test    rax, rax
0x1800dbd46  jz      loc_1800DBEA4
0x1800dbd4c  cmp     rax, rsi
0x1800dbd4f  jz      loc_1800DBEA4
0x1800dbd55  test    r14d, r14d
0x1800dbd58  jz      loc_1800DBDEB
0x1800dbd5e  mov     rcx, [rbx+98h]; pti
0x1800dbd65  test    rcx, rcx
0x1800dbd68  jnz     short loc_1800DBDA9
0x1800dbd6a  mov     eax, cs:CallbackContext
0x1800dbd70  cmp     eax, 2
0x1800dbd73  jbe     loc_1800DBE6C
0x1800dbd79  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x1800dbd80  mov     [rbp+47h+arg_8], 293h
0x1800dbd87  mov     [rbp+47h+arg_0], rax
0x1800dbd8b  lea     rdx, byte_1801BBE75
0x1800dbd92  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dbd99  mov     [rbp+47h+var_58], rax
0x1800dbd9d  lea     rax, aDispatchasyncc_2; "DispatchAsyncCall - m_timerThreadPool i"...
0x1800dbda4  jmp     loc_1800DBE2F
0x1800dbda9  call    cs:__imp_IsThreadpoolTimerSet
0x1800dbdaf  mov     rcx, [rbp+47h+arg_0]
0x1800dbdb3  test    eax, eax
0x1800dbdb5  jz      short loc_1800DBDC4
0x1800dbdb7  cmp     rcx, [rbx+0A8h]
0x1800dbdbe  jge     loc_1800DBE6C
0x1800dbdc4  mov     [rbx+0A8h], rcx
0x1800dbdcb  mov     rcx, [rbx+30h]
0x1800dbdcf  mov     rax, [rcx]
0x1800dbdd2  mov     rax, [rax+8]
0x1800dbdd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbddb  mov     edx, r14d; unsigned int
0x1800dbdde  mov     rcx, rbx; this
0x1800dbde1  call    ?ResetTimer@RdpTaskScheduler@@IEAAXK@Z; RdpTaskScheduler::ResetTimer(ulong)
0x1800dbde6  jmp     loc_1800DBE6C
0x1800dbdeb  cmp     qword ptr [rbx+90h], 0
0x1800dbdf3  jnz     loc_1800DBE85
0x1800dbdf9  mov     eax, cs:CallbackContext
0x1800dbdff  cmp     eax, 2
0x1800dbe02  jbe     short loc_1800DBE6C
0x1800dbe04  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x1800dbe0b  mov     [rbp+47h+arg_8], 2AAh
0x1800dbe12  mov     [rbp+47h+arg_0], rax
0x1800dbe16  lea     rdx, byte_1801BBDE5
0x1800dbe1d  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dbe24  mov     [rbp+47h+var_58], rax
0x1800dbe28  lea     rax, aDispatchasyncc_0; "DispatchAsyncCall - m_workThreadPool is"...
0x1800dbe2f  mov     [rbp+47h+var_60], rax
0x1800dbe33  lea     rax, [rbp+47h+arg_0]
0x1800dbe37  mov     [rsp+0B0h+var_70], rax
0x1800dbe3c  lea     rax, [rbp+47h+arg_8]
0x1800dbe40  mov     [rsp+0B0h+var_78], rax
0x1800dbe45  lea     rax, [rbp+47h+var_58]
0x1800dbe49  mov     [rsp+0B0h+var_80], rax
0x1800dbe4e  lea     rax, [rbp+47h+arg_18]
0x1800dbe52  mov     [rsp+0B0h+var_88], rax
0x1800dbe57  lea     rax, [rbp+47h+var_60]
0x1800dbe5b  mov     [rsp+0B0h+var_90], rax
0x1800dbe60  mov     [rbp+47h+arg_18], 80004003h
0x1800dbe67  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dbe6c  lea     rcx, [rbp+47h+var_50]; this
0x1800dbe70  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x1800dbe75  mov     rcx, rdi; SRWLock
0x1800dbe78  call    cs:__imp_ReleaseSRWLockExclusive
0x1800dbe7e  xor     eax, eax
0x1800dbe80  jmp     loc_1800DBF29
0x1800dbe85  mov     rcx, [rbx+30h]
0x1800dbe89  mov     rax, [rcx]
0x1800dbe8c  mov     rax, [rax+8]
0x1800dbe90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbe95  mov     rcx, [rbx+90h]; pwk
0x1800dbe9c  call    cs:__imp_SubmitThreadpoolWork
0x1800dbea2  jmp     short loc_1800DBE6C
0x1800dbea4  mov     eax, cs:CallbackContext
0x1800dbeaa  cmp     eax, 2
0x1800dbead  jbe     short loc_1800DBF14
0x1800dbeaf  lea     rax, aDispatchasyncc_3; "DispatchAsyncCall"
0x1800dbeb6  mov     [rbp+47h+arg_8], 28Ah
0x1800dbebd  mov     [rbp+47h+arg_0], rax
0x1800dbec1  lea     rcx, [rbp+47h+var_58]
0x1800dbec5  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dbecc  mov     [rbp+47h+var_58], rax
0x1800dbed0  lea     rdx, byte_1801BBF05
0x1800dbed7  lea     rax, aAddingTaskToTa; "Adding task to task list failed"
0x1800dbede  mov     [rbp+47h+var_60], rax
0x1800dbee2  lea     rax, [rbp+47h+arg_0]
0x1800dbee6  mov     [rsp+0B0h+var_70], rax
0x1800dbeeb  lea     rax, [rbp+47h+arg_8]
0x1800dbeef  mov     [rsp+0B0h+var_78], rax
0x1800dbef4  mov     [rsp+0B0h+var_80], rcx
0x1800dbef9  lea     rcx, [rbp+47h+arg_18]
0x1800dbefd  mov     [rsp+0B0h+var_88], rcx
0x1800dbf02  lea     rcx, [rbp+47h+var_60]
0x1800dbf06  mov     [rsp+0B0h+var_90], rcx
0x1800dbf0b  mov     [rbp+47h+arg_18], r15d
0x1800dbf0f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dbf14  lea     rcx, [rbp+47h+var_50]; this
0x1800dbf18  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x1800dbf1d  mov     rcx, rdi; SRWLock
0x1800dbf20  call    cs:__imp_ReleaseSRWLockExclusive
0x1800dbf26  mov     eax, r15d
0x1800dbf29  mov     rbx, [rsp+0B0h+arg_10]
0x1800dbf31  add     rsp, 90h
0x1800dbf38  pop     r15
0x1800dbf3a  pop     r14
0x1800dbf3c  pop     rdi
0x1800dbf3d  pop     rsi
0x1800dbf3e  pop     rbp
0x1800dbf3f  retn
```

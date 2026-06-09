# RdpTaskScheduler::DispatchAsyncCallOnSignaledEvent(void *,int,ITSAsyncCallback *,ulong,void *,unsigned __int64)

- ea: `0x1400895c0`
- end: `0x1400897ef`
- name: `?DispatchAsyncCallOnSignaledEvent@RdpTaskScheduler@@UEAAJPEAXHPEAVITSAsyncCallback@@K0_K@Z`
- size: `559`
- prototype: `int(RdpTaskScheduler *__hidden this, void *, int, struct ITSAsyncCallback *, unsigned int, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x1400019e8`
- `0x140088708`
- `0x14008891c`
- `0x140088aa8`
- `0x1400895c0`
- `0x14008aba0`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x14008975a`
- `KERNEL32!SetThreadpoolWait` at `0x14008975a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400895ed`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400895ed`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089729`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089742`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089729`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089742`

## string_xrefs

- `0x140089651`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1400896cf`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140089786`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140089798`: `DispatchAsyncCallOnSignaledEvent - m_waitThreadPool is null`
- `0x14008965c`: `asyncTask.SetBuffer failed`
- `0x1400896e1`: `Adding task to task list failed`

## pseudocode

```c
__int64 __fastcall RdpTaskScheduler::DispatchAsyncCallOnSignaledEvent(
        RTL_SRWLOCK *this,
        void *a2,
        __int64 a3,
        struct ITSAsyncCallback *a4,
        unsigned int a5,
        void *a6,
        unsigned __int64 a7)
{
  RTL_SRWLOCK *v7; // rdi
  const char **v11; // rcx
  int v12; // r8d
  int v13; // r9d
  __int64 *v14; // rdx
  int v16; // r8d
  int v17; // r9d
  struct _TP_WAIT *Ptr; // rcx
  const char **v19; // [rsp+20h] [rbp-41h]
  const char **v20; // [rsp+40h] [rbp-21h]
  const char *v21; // [rsp+50h] [rbp-11h] BYREF
  const char *v22; // [rsp+58h] [rbp-9h] BYREF
  const char *v23; // [rsp+60h] [rbp-1h] BYREF
  _BYTE v24[40]; // [rsp+68h] [rbp+7h] BYREF
  int v25; // [rsp+B0h] [rbp+4Fh] BYREF

  v7 = this + 29;
  AcquireSRWLockExclusive(this + 29);
  RdpTaskScheduler::AsyncTask::AsyncTask((RdpTaskScheduler::AsyncTask *)v24, a4, a7);
  if ( a5 && a6 && RdpTaskScheduler::AsyncTask::SetBuffer((RdpTaskScheduler::AsyncTask *)v24, a5, a6) < 0 )
  {
    if ( (unsigned int)dword_140152118 > 2 )
    {
      a5 = 715;
      v21 = "DispatchAsyncCallOnSignaledEvent";
      v14 = qword_1401435F8;
      v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v23 = "asyncTask.SetBuffer failed";
      v20 = &v21;
      v19 = &v23;
LABEL_9:
      v25 = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v11,
        (_DWORD)v14,
        v12,
        v13,
        (__int64)v19,
        (__int64)&v25,
        (__int64)&v22,
        (__int64)&a5,
        (__int64)v20);
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  if ( !(unsigned __int8)utl::vector<RdpTaskScheduler::AsyncTask,utl::allocator<RdpTaskScheduler::AsyncTask>>::emplace_back<RdpTaskScheduler::AsyncTask,0>(
                           &this[26],
                           v24) )
  {
    if ( (unsigned int)dword_140152118 > 2 )
    {
      a5 = 722;
      v23 = "DispatchAsyncCallOnSignaledEvent";
      v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v14 = qword_1401435B0;
      v21 = "Adding task to task list failed";
      v20 = &v23;
      v11 = &v21;
      v19 = &v21;
      goto LABEL_9;
    }
LABEL_10:
    RdpTaskScheduler::AsyncTask::~AsyncTask((RdpTaskScheduler::AsyncTask *)v24);
    ReleaseSRWLockExclusive(v7);
    return 2147942414LL;
  }
  RdpTaskScheduler::AsyncTask::~AsyncTask((RdpTaskScheduler::AsyncTask *)v24);
  ReleaseSRWLockExclusive(v7);
  Ptr = (struct _TP_WAIT *)this[20].Ptr;
  if ( Ptr )
  {
    SetThreadpoolWait(Ptr, a2, 0);
  }
  else if ( (unsigned int)dword_140152118 > 2 )
  {
    a5 = 734;
    v23 = "DispatchAsyncCallOnSignaledEvent";
    v25 = -2147467261;
    v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v21 = "DispatchAsyncCallOnSignaledEvent - m_waitThreadPool is null";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0,
      (unsigned int)qword_140143568,
      v16,
      v17,
      (__int64)&v21,
      (__int64)&v25,
      (__int64)&v22,
      (__int64)&a5,
      (__int64)&v23);
  }
  return 0;
}

```

## disassembly

```asm
0x1400895c0  mov     [rsp-8+arg_8], rbx
0x1400895c5  mov     [rsp-8+arg_10], rsi
0x1400895ca  push    rbp
0x1400895cb  push    rdi
0x1400895cc  push    r14
0x1400895ce  lea     rbp, [rsp-2Fh]
0x1400895d3  sub     rsp, 90h
0x1400895da  lea     rdi, [rcx+0E8h]
0x1400895e1  mov     rsi, rcx
0x1400895e4  mov     rcx, rdi; SRWLock
0x1400895e7  mov     rbx, r9
0x1400895ea  mov     r14, rdx
0x1400895ed  call    cs:__imp_AcquireSRWLockExclusive
0x1400895f3  mov     r8, [rbp+3Fh+arg_30]; unsigned __int64
0x1400895f7  lea     rcx, [rbp+3Fh+var_38]; this
0x1400895fb  mov     rdx, rbx; struct ITSAsyncCallback *
0x1400895fe  call    ??0AsyncTask@RdpTaskScheduler@@QEAA@PEAVITSAsyncCallback@@_K@Z; RdpTaskScheduler::AsyncTask::AsyncTask(ITSAsyncCallback *,unsigned __int64)
0x140089603  mov     edx, [rbp+3Fh+arg_20]; unsigned int
0x140089606  mov     ebx, 8007000Eh
0x14008960b  test    edx, edx
0x14008960d  jz      loc_140089696
0x140089613  mov     r8, [rbp+3Fh+arg_28]; void *
0x140089617  test    r8, r8
0x14008961a  jz      short loc_140089696
0x14008961c  lea     rcx, [rbp+3Fh+var_38]; this
0x140089620  call    ?SetBuffer@AsyncTask@RdpTaskScheduler@@QEAAJKPEAX@Z; RdpTaskScheduler::AsyncTask::SetBuffer(ulong,void *)
0x140089625  test    eax, eax
0x140089627  jns     short loc_140089696
0x140089629  mov     eax, cs:dword_140152118
0x14008962f  cmp     eax, 2
0x140089632  jbe     loc_14008971D
0x140089638  lea     rax, aDispatchasyncc; "DispatchAsyncCallOnSignaledEvent"
0x14008963f  mov     [rbp+3Fh+arg_20], 2CBh
0x140089646  mov     [rbp+3Fh+var_50], rax
0x14008964a  lea     rdx, qword_1401435F8
0x140089651  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140089658  mov     [rbp+3Fh+var_48], rax
0x14008965c  lea     rax, aAsynctaskSetbu; "asyncTask.SetBuffer failed"
0x140089663  mov     [rbp+3Fh+var_40], rax
0x140089667  lea     rax, [rbp+3Fh+var_50]
0x14008966b  mov     [rsp+0A0h+var_60], rax
0x140089670  lea     rax, [rbp+3Fh+arg_20]
0x140089674  mov     [rsp+0A0h+var_68], rax
0x140089679  lea     rax, [rbp+3Fh+var_48]
0x14008967d  mov     [rsp+0A0h+var_70], rax
0x140089682  lea     rax, [rbp+3Fh+arg_0]
0x140089686  mov     [rsp+0A0h+var_78], rax
0x14008968b  lea     rax, [rbp+3Fh+var_40]
0x14008968f  mov     [rsp+0A0h+var_80], rax
0x140089694  jmp     short loc_140089715
0x140089696  lea     rcx, [rsi+0D0h]
0x14008969d  lea     rdx, [rbp+3Fh+var_38]
0x1400896a1  call    ??$emplace_back@UAsyncTask@RdpTaskScheduler@@$0A@@?$vector@UAsyncTask@RdpTaskScheduler@@V?$allocator@UAsyncTask@RdpTaskScheduler@@@utl@@@utl@@QEAA_N$$QEAUAsyncTask@RdpTaskScheduler@@@Z; utl::vector<RdpTaskScheduler::AsyncTask,utl::allocator<RdpTaskScheduler::AsyncTask>>::emplace_back<RdpTaskScheduler::AsyncTask,0>(RdpTaskScheduler::AsyncTask &&)
0x1400896a6  test    al, al
0x1400896a8  jnz     loc_140089736
0x1400896ae  mov     eax, cs:dword_140152118
0x1400896b4  cmp     eax, 2
0x1400896b7  jbe     short loc_14008971D
0x1400896b9  lea     rax, aDispatchasyncc; "DispatchAsyncCallOnSignaledEvent"
0x1400896c0  mov     [rbp+3Fh+arg_20], 2D2h
0x1400896c7  mov     [rbp+3Fh+var_40], rax
0x1400896cb  lea     rcx, [rbp+3Fh+var_48]
0x1400896cf  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400896d6  mov     [rbp+3Fh+var_48], rax
0x1400896da  lea     rdx, qword_1401435B0
0x1400896e1  lea     rax, aAddingTaskToTa; "Adding task to task list failed"
0x1400896e8  mov     [rbp+3Fh+var_50], rax
0x1400896ec  lea     rax, [rbp+3Fh+var_40]
0x1400896f0  mov     [rsp+0A0h+var_60], rax
0x1400896f5  lea     rax, [rbp+3Fh+arg_20]
0x1400896f9  mov     [rsp+0A0h+var_68], rax
0x1400896fe  mov     [rsp+0A0h+var_70], rcx
0x140089703  lea     rcx, [rbp+3Fh+arg_0]
0x140089707  mov     [rsp+0A0h+var_78], rcx
0x14008970c  lea     rcx, [rbp+3Fh+var_50]
0x140089710  mov     [rsp+0A0h+var_80], rcx
0x140089715  mov     [rbp+3Fh+arg_0], ebx
0x140089718  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14008971d  lea     rcx, [rbp+3Fh+var_38]; this
0x140089721  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x140089726  mov     rcx, rdi; SRWLock
0x140089729  call    cs:__imp_ReleaseSRWLockExclusive
0x14008972f  mov     eax, ebx
0x140089731  jmp     loc_1400897D7
0x140089736  lea     rcx, [rbp+3Fh+var_38]; this
0x14008973a  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x14008973f  mov     rcx, rdi; SRWLock
0x140089742  call    cs:__imp_ReleaseSRWLockExclusive
0x140089748  mov     rcx, [rsi+0A0h]; pwa
0x14008974f  test    rcx, rcx
0x140089752  jz      short loc_140089762
0x140089754  xor     r8d, r8d; pftTimeout
0x140089757  mov     rdx, r14; h
0x14008975a  call    cs:__imp_SetThreadpoolWait
0x140089760  jmp     short loc_1400897D5
0x140089762  mov     eax, cs:dword_140152118
0x140089768  cmp     eax, 2
0x14008976b  jbe     short loc_1400897D5
0x14008976d  lea     rax, aDispatchasyncc; "DispatchAsyncCallOnSignaledEvent"
0x140089774  mov     [rbp+3Fh+arg_20], 2DEh
0x14008977b  mov     [rbp+3Fh+var_40], rax
0x14008977f  lea     rdx, qword_140143568
0x140089786  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008978d  mov     [rbp+3Fh+arg_0], 80004003h
0x140089794  mov     [rbp+3Fh+var_48], rax
0x140089798  lea     rax, aDispatchasyncc_1; "DispatchAsyncCallOnSignaledEvent - m_wa"...
0x14008979f  mov     [rbp+3Fh+var_50], rax
0x1400897a3  lea     rax, [rbp+3Fh+var_40]
0x1400897a7  mov     [rsp+0A0h+var_60], rax
0x1400897ac  lea     rax, [rbp+3Fh+arg_20]
0x1400897b0  mov     [rsp+0A0h+var_68], rax
0x1400897b5  lea     rax, [rbp+3Fh+var_48]
0x1400897b9  mov     [rsp+0A0h+var_70], rax
0x1400897be  lea     rax, [rbp+3Fh+arg_0]
0x1400897c2  mov     [rsp+0A0h+var_78], rax
0x1400897c7  lea     rax, [rbp+3Fh+var_50]
0x1400897cb  mov     [rsp+0A0h+var_80], rax
0x1400897d0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400897d5  xor     eax, eax
0x1400897d7  lea     r11, [rsp+0A0h+var_10]
0x1400897df  mov     rbx, [r11+28h]
0x1400897e3  mov     rsi, [r11+30h]
0x1400897e7  mov     rsp, r11
0x1400897ea  pop     r14
0x1400897ec  pop     rdi
0x1400897ed  pop     rbp
0x1400897ee  retn
```

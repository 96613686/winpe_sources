# RdpTaskScheduler::DispatchAsyncCallOnSignaledEvent(void *,int,ITSAsyncCallback *,ulong,void *,unsigned __int64)

- ea: `0x140087450`
- end: `0x14008767f`
- name: `?DispatchAsyncCallOnSignaledEvent@RdpTaskScheduler@@UEAAJPEAXHPEAVITSAsyncCallback@@K0_K@Z`
- size: `559`
- prototype: `int(RdpTaskScheduler *__hidden this, void *, int, struct ITSAsyncCallback *, unsigned int, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x1400019e8`
- `0x140086598`
- `0x1400867ac`
- `0x140086938`
- `0x140087450`
- `0x140088a30`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x1400875ea`
- `KERNEL32!SetThreadpoolWait` at `0x1400875ea`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14008747d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14008747d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400875b9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400875d2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400875b9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400875d2`

## string_xrefs

- `0x1400874e1`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008755f`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140087616`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140087628`: `DispatchAsyncCallOnSignaledEvent - m_waitThreadPool is null`
- `0x1400874ec`: `asyncTask.SetBuffer failed`
- `0x140087571`: `Adding task to task list failed`

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
    if ( (unsigned int)dword_140150118 > 2 )
    {
      a5 = 715;
      v21 = "DispatchAsyncCallOnSignaledEvent";
      v14 = qword_1401412C0;
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
    if ( (unsigned int)dword_140150118 > 2 )
    {
      a5 = 722;
      v23 = "DispatchAsyncCallOnSignaledEvent";
      v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v14 = qword_140141478;
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
  else if ( (unsigned int)dword_140150118 > 2 )
  {
    a5 = 734;
    v23 = "DispatchAsyncCallOnSignaledEvent";
    v25 = -2147467261;
    v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v21 = "DispatchAsyncCallOnSignaledEvent - m_waitThreadPool is null";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0,
      (unsigned int)qword_140141430,
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
0x140087450  mov     [rsp-8+arg_8], rbx
0x140087455  mov     [rsp-8+arg_10], rsi
0x14008745a  push    rbp
0x14008745b  push    rdi
0x14008745c  push    r14
0x14008745e  lea     rbp, [rsp-2Fh]
0x140087463  sub     rsp, 90h
0x14008746a  lea     rdi, [rcx+0E8h]
0x140087471  mov     rsi, rcx
0x140087474  mov     rcx, rdi; SRWLock
0x140087477  mov     rbx, r9
0x14008747a  mov     r14, rdx
0x14008747d  call    cs:__imp_AcquireSRWLockExclusive
0x140087483  mov     r8, [rbp+3Fh+arg_30]; unsigned __int64
0x140087487  lea     rcx, [rbp+3Fh+var_38]; this
0x14008748b  mov     rdx, rbx; struct ITSAsyncCallback *
0x14008748e  call    ??0AsyncTask@RdpTaskScheduler@@QEAA@PEAVITSAsyncCallback@@_K@Z; RdpTaskScheduler::AsyncTask::AsyncTask(ITSAsyncCallback *,unsigned __int64)
0x140087493  mov     edx, [rbp+3Fh+arg_20]; unsigned int
0x140087496  mov     ebx, 8007000Eh
0x14008749b  test    edx, edx
0x14008749d  jz      loc_140087526
0x1400874a3  mov     r8, [rbp+3Fh+arg_28]; void *
0x1400874a7  test    r8, r8
0x1400874aa  jz      short loc_140087526
0x1400874ac  lea     rcx, [rbp+3Fh+var_38]; this
0x1400874b0  call    ?SetBuffer@AsyncTask@RdpTaskScheduler@@QEAAJKPEAX@Z; RdpTaskScheduler::AsyncTask::SetBuffer(ulong,void *)
0x1400874b5  test    eax, eax
0x1400874b7  jns     short loc_140087526
0x1400874b9  mov     eax, cs:dword_140150118
0x1400874bf  cmp     eax, 2
0x1400874c2  jbe     loc_1400875AD
0x1400874c8  lea     rax, aDispatchasyncc; "DispatchAsyncCallOnSignaledEvent"
0x1400874cf  mov     [rbp+3Fh+arg_20], 2CBh
0x1400874d6  mov     [rbp+3Fh+var_50], rax
0x1400874da  lea     rdx, qword_1401412C0
0x1400874e1  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400874e8  mov     [rbp+3Fh+var_48], rax
0x1400874ec  lea     rax, aAsynctaskSetbu; "asyncTask.SetBuffer failed"
0x1400874f3  mov     [rbp+3Fh+var_40], rax
0x1400874f7  lea     rax, [rbp+3Fh+var_50]
0x1400874fb  mov     [rsp+0A0h+var_60], rax
0x140087500  lea     rax, [rbp+3Fh+arg_20]
0x140087504  mov     [rsp+0A0h+var_68], rax
0x140087509  lea     rax, [rbp+3Fh+var_48]
0x14008750d  mov     [rsp+0A0h+var_70], rax
0x140087512  lea     rax, [rbp+3Fh+arg_0]
0x140087516  mov     [rsp+0A0h+var_78], rax
0x14008751b  lea     rax, [rbp+3Fh+var_40]
0x14008751f  mov     [rsp+0A0h+var_80], rax
0x140087524  jmp     short loc_1400875A5
0x140087526  lea     rcx, [rsi+0D0h]
0x14008752d  lea     rdx, [rbp+3Fh+var_38]
0x140087531  call    ??$emplace_back@UAsyncTask@RdpTaskScheduler@@$0A@@?$vector@UAsyncTask@RdpTaskScheduler@@V?$allocator@UAsyncTask@RdpTaskScheduler@@@utl@@@utl@@QEAA_N$$QEAUAsyncTask@RdpTaskScheduler@@@Z; utl::vector<RdpTaskScheduler::AsyncTask,utl::allocator<RdpTaskScheduler::AsyncTask>>::emplace_back<RdpTaskScheduler::AsyncTask,0>(RdpTaskScheduler::AsyncTask &&)
0x140087536  test    al, al
0x140087538  jnz     loc_1400875C6
0x14008753e  mov     eax, cs:dword_140150118
0x140087544  cmp     eax, 2
0x140087547  jbe     short loc_1400875AD
0x140087549  lea     rax, aDispatchasyncc; "DispatchAsyncCallOnSignaledEvent"
0x140087550  mov     [rbp+3Fh+arg_20], 2D2h
0x140087557  mov     [rbp+3Fh+var_40], rax
0x14008755b  lea     rcx, [rbp+3Fh+var_48]
0x14008755f  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140087566  mov     [rbp+3Fh+var_48], rax
0x14008756a  lea     rdx, qword_140141478
0x140087571  lea     rax, aAddingTaskToTa; "Adding task to task list failed"
0x140087578  mov     [rbp+3Fh+var_50], rax
0x14008757c  lea     rax, [rbp+3Fh+var_40]
0x140087580  mov     [rsp+0A0h+var_60], rax
0x140087585  lea     rax, [rbp+3Fh+arg_20]
0x140087589  mov     [rsp+0A0h+var_68], rax
0x14008758e  mov     [rsp+0A0h+var_70], rcx
0x140087593  lea     rcx, [rbp+3Fh+arg_0]
0x140087597  mov     [rsp+0A0h+var_78], rcx
0x14008759c  lea     rcx, [rbp+3Fh+var_50]
0x1400875a0  mov     [rsp+0A0h+var_80], rcx
0x1400875a5  mov     [rbp+3Fh+arg_0], ebx
0x1400875a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400875ad  lea     rcx, [rbp+3Fh+var_38]; this
0x1400875b1  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x1400875b6  mov     rcx, rdi; SRWLock
0x1400875b9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400875bf  mov     eax, ebx
0x1400875c1  jmp     loc_140087667
0x1400875c6  lea     rcx, [rbp+3Fh+var_38]; this
0x1400875ca  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x1400875cf  mov     rcx, rdi; SRWLock
0x1400875d2  call    cs:__imp_ReleaseSRWLockExclusive
0x1400875d8  mov     rcx, [rsi+0A0h]; pwa
0x1400875df  test    rcx, rcx
0x1400875e2  jz      short loc_1400875F2
0x1400875e4  xor     r8d, r8d; pftTimeout
0x1400875e7  mov     rdx, r14; h
0x1400875ea  call    cs:__imp_SetThreadpoolWait
0x1400875f0  jmp     short loc_140087665
0x1400875f2  mov     eax, cs:dword_140150118
0x1400875f8  cmp     eax, 2
0x1400875fb  jbe     short loc_140087665
0x1400875fd  lea     rax, aDispatchasyncc; "DispatchAsyncCallOnSignaledEvent"
0x140087604  mov     [rbp+3Fh+arg_20], 2DEh
0x14008760b  mov     [rbp+3Fh+var_40], rax
0x14008760f  lea     rdx, qword_140141430
0x140087616  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008761d  mov     [rbp+3Fh+arg_0], 80004003h
0x140087624  mov     [rbp+3Fh+var_48], rax
0x140087628  lea     rax, aDispatchasyncc_1; "DispatchAsyncCallOnSignaledEvent - m_wa"...
0x14008762f  mov     [rbp+3Fh+var_50], rax
0x140087633  lea     rax, [rbp+3Fh+var_40]
0x140087637  mov     [rsp+0A0h+var_60], rax
0x14008763c  lea     rax, [rbp+3Fh+arg_20]
0x140087640  mov     [rsp+0A0h+var_68], rax
0x140087645  lea     rax, [rbp+3Fh+var_48]
0x140087649  mov     [rsp+0A0h+var_70], rax
0x14008764e  lea     rax, [rbp+3Fh+arg_0]
0x140087652  mov     [rsp+0A0h+var_78], rax
0x140087657  lea     rax, [rbp+3Fh+var_50]
0x14008765b  mov     [rsp+0A0h+var_80], rax
0x140087660  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140087665  xor     eax, eax
0x140087667  lea     r11, [rsp+0A0h+var_10]
0x14008766f  mov     rbx, [r11+28h]
0x140087673  mov     rsi, [r11+30h]
0x140087677  mov     rsp, r11
0x14008767a  pop     r14
0x14008767c  pop     rdi
0x14008767d  pop     rbp
0x14008767e  retn
```

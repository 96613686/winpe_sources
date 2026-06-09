# RdpTaskScheduler::DispatchAsyncCallOnSignaledEvent(void *,int,ITSAsyncCallback *,ulong,void *,unsigned __int64)

- ea: `0x1800dbf50`
- end: `0x1800dc17f`
- name: `?DispatchAsyncCallOnSignaledEvent@RdpTaskScheduler@@UEAAJPEAXHPEAVITSAsyncCallback@@K0_K@Z`
- size: `559`
- prototype: `int(RdpTaskScheduler *__hidden this, void *, int, struct ITSAsyncCallback *, unsigned int, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x1800018a4`
- `0x1800db244`
- `0x1800db47c`
- `0x1800db608`
- `0x1800dbf50`
- `0x1800dd3e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dbf7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dbf7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc0b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc0d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc0b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc0d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800dc0ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800dc0ea`

## string_xrefs

- `0x1800dbfe1`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dc05f`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dc116`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dc071`: `Adding task to task list failed`
- `0x1800dbfec`: `asyncTask.SetBuffer failed`
- `0x1800dc128`: `DispatchAsyncCallOnSignaledEvent - m_waitThreadPool is null`

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
  char *v14; // rdx
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
    if ( (unsigned int)CallbackContext > 2 )
    {
      a5 = 715;
      v21 = "DispatchAsyncCallOnSignaledEvent";
      v14 = byte_1801BBE2D;
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
    if ( (unsigned int)CallbackContext > 2 )
    {
      a5 = 722;
      v23 = "DispatchAsyncCallOnSignaledEvent";
      v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v14 = byte_1801BBD55;
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
  else if ( (unsigned int)CallbackContext > 2 )
  {
    a5 = 734;
    v23 = "DispatchAsyncCallOnSignaledEvent";
    v25 = -2147467261;
    v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v21 = "DispatchAsyncCallOnSignaledEvent - m_waitThreadPool is null";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0,
      (unsigned int)byte_1801BBD9D,
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
0x1800dbf50  mov     [rsp-8+arg_8], rbx
0x1800dbf55  mov     [rsp-8+arg_10], rsi
0x1800dbf5a  push    rbp
0x1800dbf5b  push    rdi
0x1800dbf5c  push    r14
0x1800dbf5e  lea     rbp, [rsp-2Fh]
0x1800dbf63  sub     rsp, 90h
0x1800dbf6a  lea     rdi, [rcx+0E8h]
0x1800dbf71  mov     rsi, rcx
0x1800dbf74  mov     rcx, rdi; SRWLock
0x1800dbf77  mov     rbx, r9
0x1800dbf7a  mov     r14, rdx
0x1800dbf7d  call    cs:__imp_AcquireSRWLockExclusive
0x1800dbf83  mov     r8, [rbp+3Fh+arg_30]; unsigned __int64
0x1800dbf87  lea     rcx, [rbp+3Fh+var_38]; this
0x1800dbf8b  mov     rdx, rbx; struct ITSAsyncCallback *
0x1800dbf8e  call    ??0AsyncTask@RdpTaskScheduler@@QEAA@PEAVITSAsyncCallback@@_K@Z; RdpTaskScheduler::AsyncTask::AsyncTask(ITSAsyncCallback *,unsigned __int64)
0x1800dbf93  mov     edx, [rbp+3Fh+arg_20]; unsigned int
0x1800dbf96  mov     ebx, 8007000Eh
0x1800dbf9b  test    edx, edx
0x1800dbf9d  jz      loc_1800DC026
0x1800dbfa3  mov     r8, [rbp+3Fh+arg_28]; void *
0x1800dbfa7  test    r8, r8
0x1800dbfaa  jz      short loc_1800DC026
0x1800dbfac  lea     rcx, [rbp+3Fh+var_38]; this
0x1800dbfb0  call    ?SetBuffer@AsyncTask@RdpTaskScheduler@@QEAAJKPEAX@Z; RdpTaskScheduler::AsyncTask::SetBuffer(ulong,void *)
0x1800dbfb5  test    eax, eax
0x1800dbfb7  jns     short loc_1800DC026
0x1800dbfb9  mov     eax, cs:CallbackContext
0x1800dbfbf  cmp     eax, 2
0x1800dbfc2  jbe     loc_1800DC0AD
0x1800dbfc8  lea     rax, aDispatchasyncc; "DispatchAsyncCallOnSignaledEvent"
0x1800dbfcf  mov     [rbp+3Fh+arg_20], 2CBh
0x1800dbfd6  mov     [rbp+3Fh+var_50], rax
0x1800dbfda  lea     rdx, byte_1801BBE2D
0x1800dbfe1  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dbfe8  mov     [rbp+3Fh+var_48], rax
0x1800dbfec  lea     rax, aAsynctaskSetbu; "asyncTask.SetBuffer failed"
0x1800dbff3  mov     [rbp+3Fh+var_40], rax
0x1800dbff7  lea     rax, [rbp+3Fh+var_50]
0x1800dbffb  mov     [rsp+0A0h+var_60], rax
0x1800dc000  lea     rax, [rbp+3Fh+arg_20]
0x1800dc004  mov     [rsp+0A0h+var_68], rax
0x1800dc009  lea     rax, [rbp+3Fh+var_48]
0x1800dc00d  mov     [rsp+0A0h+var_70], rax
0x1800dc012  lea     rax, [rbp+3Fh+arg_0]
0x1800dc016  mov     [rsp+0A0h+var_78], rax
0x1800dc01b  lea     rax, [rbp+3Fh+var_40]
0x1800dc01f  mov     [rsp+0A0h+var_80], rax
0x1800dc024  jmp     short loc_1800DC0A5
0x1800dc026  lea     rcx, [rsi+0D0h]
0x1800dc02d  lea     rdx, [rbp+3Fh+var_38]
0x1800dc031  call    ??$emplace_back@UAsyncTask@RdpTaskScheduler@@$0A@@?$vector@UAsyncTask@RdpTaskScheduler@@V?$allocator@UAsyncTask@RdpTaskScheduler@@@utl@@@utl@@QEAA_N$$QEAUAsyncTask@RdpTaskScheduler@@@Z; utl::vector<RdpTaskScheduler::AsyncTask,utl::allocator<RdpTaskScheduler::AsyncTask>>::emplace_back<RdpTaskScheduler::AsyncTask,0>(RdpTaskScheduler::AsyncTask &&)
0x1800dc036  test    al, al
0x1800dc038  jnz     loc_1800DC0C6
0x1800dc03e  mov     eax, cs:CallbackContext
0x1800dc044  cmp     eax, 2
0x1800dc047  jbe     short loc_1800DC0AD
0x1800dc049  lea     rax, aDispatchasyncc; "DispatchAsyncCallOnSignaledEvent"
0x1800dc050  mov     [rbp+3Fh+arg_20], 2D2h
0x1800dc057  mov     [rbp+3Fh+var_40], rax
0x1800dc05b  lea     rcx, [rbp+3Fh+var_48]
0x1800dc05f  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dc066  mov     [rbp+3Fh+var_48], rax
0x1800dc06a  lea     rdx, byte_1801BBD55
0x1800dc071  lea     rax, aAddingTaskToTa; "Adding task to task list failed"
0x1800dc078  mov     [rbp+3Fh+var_50], rax
0x1800dc07c  lea     rax, [rbp+3Fh+var_40]
0x1800dc080  mov     [rsp+0A0h+var_60], rax
0x1800dc085  lea     rax, [rbp+3Fh+arg_20]
0x1800dc089  mov     [rsp+0A0h+var_68], rax
0x1800dc08e  mov     [rsp+0A0h+var_70], rcx
0x1800dc093  lea     rcx, [rbp+3Fh+arg_0]
0x1800dc097  mov     [rsp+0A0h+var_78], rcx
0x1800dc09c  lea     rcx, [rbp+3Fh+var_50]
0x1800dc0a0  mov     [rsp+0A0h+var_80], rcx
0x1800dc0a5  mov     [rbp+3Fh+arg_0], ebx
0x1800dc0a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dc0ad  lea     rcx, [rbp+3Fh+var_38]; this
0x1800dc0b1  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x1800dc0b6  mov     rcx, rdi; SRWLock
0x1800dc0b9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800dc0bf  mov     eax, ebx
0x1800dc0c1  jmp     loc_1800DC167
0x1800dc0c6  lea     rcx, [rbp+3Fh+var_38]; this
0x1800dc0ca  call    ??1AsyncTask@RdpTaskScheduler@@QEAA@XZ; RdpTaskScheduler::AsyncTask::~AsyncTask(void)
0x1800dc0cf  mov     rcx, rdi; SRWLock
0x1800dc0d2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800dc0d8  mov     rcx, [rsi+0A0h]; pwa
0x1800dc0df  test    rcx, rcx
0x1800dc0e2  jz      short loc_1800DC0F2
0x1800dc0e4  xor     r8d, r8d; pftTimeout
0x1800dc0e7  mov     rdx, r14; h
0x1800dc0ea  call    cs:__imp_SetThreadpoolWait
0x1800dc0f0  jmp     short loc_1800DC165
0x1800dc0f2  mov     eax, cs:CallbackContext
0x1800dc0f8  cmp     eax, 2
0x1800dc0fb  jbe     short loc_1800DC165
0x1800dc0fd  lea     rax, aDispatchasyncc; "DispatchAsyncCallOnSignaledEvent"
0x1800dc104  mov     [rbp+3Fh+arg_20], 2DEh
0x1800dc10b  mov     [rbp+3Fh+var_40], rax
0x1800dc10f  lea     rdx, byte_1801BBD9D
0x1800dc116  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dc11d  mov     [rbp+3Fh+arg_0], 80004003h
0x1800dc124  mov     [rbp+3Fh+var_48], rax
0x1800dc128  lea     rax, aDispatchasyncc_1; "DispatchAsyncCallOnSignaledEvent - m_wa"...
0x1800dc12f  mov     [rbp+3Fh+var_50], rax
0x1800dc133  lea     rax, [rbp+3Fh+var_40]
0x1800dc137  mov     [rsp+0A0h+var_60], rax
0x1800dc13c  lea     rax, [rbp+3Fh+arg_20]
0x1800dc140  mov     [rsp+0A0h+var_68], rax
0x1800dc145  lea     rax, [rbp+3Fh+var_48]
0x1800dc149  mov     [rsp+0A0h+var_70], rax
0x1800dc14e  lea     rax, [rbp+3Fh+arg_0]
0x1800dc152  mov     [rsp+0A0h+var_78], rax
0x1800dc157  lea     rax, [rbp+3Fh+var_50]
0x1800dc15b  mov     [rsp+0A0h+var_80], rax
0x1800dc160  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dc165  xor     eax, eax
0x1800dc167  lea     r11, [rsp+0A0h+var_10]
0x1800dc16f  mov     rbx, [r11+28h]
0x1800dc173  mov     rsi, [r11+30h]
0x1800dc177  mov     rsp, r11
0x1800dc17a  pop     r14
0x1800dc17c  pop     rdi
0x1800dc17d  pop     rbp
0x1800dc17e  retn
```

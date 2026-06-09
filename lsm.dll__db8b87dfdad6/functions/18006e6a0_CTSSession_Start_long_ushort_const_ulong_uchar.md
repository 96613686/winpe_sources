# CTSSession::Start(long,ushort const *,ulong,uchar *)

- ea: `0x18006e6a0`
- end: `0x18006ebe5`
- name: `?Start@CTSSession@@UEAAJJPEBGKPEAE@Z`
- size: `1349`
- prototype: `__int64 __fastcall(CTSSession *this, int, const unsigned __int16 *, __int64, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800016b4`
- `0x180001b80`
- `0x1800074c0`
- `0x180008f64`
- `0x1800092a4`
- `0x1800093d0`
- `0x1800093f8`
- `0x180009420`
- `0x180009a68`
- `0x18000aad4`
- `0x180010fb0`
- `0x180018c90`
- `0x18001ce00`
- `0x1800245e4`
- `0x180024b9c`
- `0x180026a10`
- `0x180028784`
- `0x180028bbc`
- `0x18002bf6c`
- `0x180032028`
- `0x18004b460`
- `0x18006caec`
- `0x18006e514`
- `0x18006e6a0`
- `0x180097010`

## import_xrefs

- `KERNELBASE!WTSGetServiceSessionId` at `0x18006e761`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18006e761`

## string_xrefs

- `0x18006ebd1`: `Task completed successfully`
- `0x18006e708`: `Session Create`
- `0x18006e7a4`: `Session Create`
- `0x18006e8e1`: `invalid state for EvCreated, state is: "%s"`
- `0x18006e96a`: `ReadSecurityDescriptor`
- `0x18006e9f0`: `CommonData.Start`

## pseudocode

```c
__int64 __fastcall CTSSession::Start(
        CTSSession *this,
        int a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int8 *a5)
{
  const char *v8; // r13
  int v9; // r8d
  int v10; // r9d
  int SecurityDescriptor; // ebx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  const char *v15; // rax
  char *v16; // rdx
  int v18; // eax
  int v19; // r8d
  int v20; // r9d
  int *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  const char *StateName; // rax
  const unsigned __int16 *LsmEventName; // rax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  const char *v29; // rax
  char *v30; // rdx
  __int64 v31; // [rsp+20h] [rbp-B1h]
  const char *v32; // [rsp+50h] [rbp-81h] BYREF
  const char *v33; // [rsp+58h] [rbp-79h] BYREF
  const char *v34; // [rsp+60h] [rbp-71h] BYREF
  const char *v35; // [rsp+68h] [rbp-69h] BYREF
  const char *v36; // [rsp+70h] [rbp-61h] BYREF
  __int64 v37; // [rsp+78h] [rbp-59h] BYREF
  __int64 v38; // [rsp+80h] [rbp-51h] BYREF
  _BYTE v39[16]; // [rsp+88h] [rbp-49h] BYREF
  __int128 v40; // [rsp+98h] [rbp-39h] BYREF
  unsigned int v41[4]; // [rsp+A8h] [rbp-29h]
  __int128 v42; // [rsp+B8h] [rbp-19h] BYREF
  __int64 v43; // [rsp+C8h] [rbp-9h] BYREF
  _BYTE v44[24]; // [rsp+D0h] [rbp-1h] BYREF

  v38 = 0;
  v37 = 0;
  v8 = (char *)this + 3208;
  CAutoSetActivityId::CAutoSetActivityId((CAutoSetActivityId *)v44, (struct _GUID *)((char *)this + 3208));
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v32 = "Start csrss for a new session";
    v34 = "CTSSession::Start";
    v35 = "Session Create";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"CTSSession::Start",
      (unsigned int)word_1800C4A8A,
      v9,
      v10,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v32);
  }
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v39, (CTSSession *)((char *)this + 1856));
  if ( (unsigned int)WTSGetServiceSessionId() == a2 )
  {
    SecurityDescriptor = -2147024809;
LABEL_5:
    CAutoLock::Unlock((CAutoLock *)v39);
    CTSSession::LogFailedTransition(this, 1, (unsigned int)SecurityDescriptor);
    goto LABEL_6;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 199) + 24LL))(
          *((_QWORD *)this + 199),
          &IID_ITSSession,
          &v37);
  SecurityDescriptor = v18;
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v35 = "Start";
      LODWORD(v32) = v18;
      v34 = "QI( ITSSession )";
      v33 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1800DA020,
        (unsigned int)byte_1800C4A4D,
        v19,
        v20,
        (__int64)&v33,
        (__int64)&v34,
        (__int64)&v32,
        (__int64)&v35);
    }
    v21 = (int *)((char *)this + 3256);
    goto LABEL_34;
  }
  v21 = (int *)((char *)this + 3256);
  v22 = CTSSession::CState::CheckState((char *)this + 3256, 1);
  SecurityDescriptor = v22;
  if ( v22 < 0 )
  {
    StateName = (const char *)CUtils::GetStateName((unsigned int)*v21);
    _DbgPrintMessage(8, "invalid state for EvCreated, state is: \"%s\"", StateName);
    goto LABEL_34;
  }
  if ( v22 == 1 )
  {
    GetLsmStateName(*v21);
    LsmEventName = GetLsmEventName(1);
    if ( (g_DebugTraceComponent & 4) != 0 )
    {
      HIDWORD(v31) = HIDWORD(LsmEventName);
      _DbgPrintMessage(2, "No change to session %d state %ws with event %ws", *((unsigned int *)this + 436));
    }
    goto LABEL_35;
  }
  SecurityDescriptor = CTSSession::ReadSecurityDescriptor(this, a5, v23);
  if ( SecurityDescriptor < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_34;
    v33 = "Start";
    v29 = "ReadSecurityDescriptor";
    v30 = (char *)qword_1800C4A10;
    goto LABEL_22;
  }
  SecurityDescriptor = CTSSession::CCommonSessionData::Start(
                         (CTSSession *)((char *)this + 1728),
                         (CTSSession *)((char *)this + 1792),
                         a3);
  if ( SecurityDescriptor < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_34;
    v33 = "Start";
    v29 = "CommonData.Start";
    v30 = byte_1800C49D3;
    goto LABEL_22;
  }
  SecurityDescriptor = CTSSession::GetCsrPipe(this, (struct ICsrPipe **)this + 214);
  if ( SecurityDescriptor < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_34;
    v33 = "Start";
    v29 = "GetCsrPipe";
    v30 = (char *)&word_1800C4996;
    goto LABEL_22;
  }
  SecurityDescriptor = CSessionList::Add(*((CSessionList **)this + 230), this);
  if ( SecurityDescriptor < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_34;
    v33 = "Start";
    v29 = "SessionList::Add";
    v30 = byte_1800C4959;
LABEL_22:
    v35 = v29;
    v34 = "Warning HResult failed";
    LODWORD(v32) = SecurityDescriptor;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v26,
      (_DWORD)v30,
      v27,
      v28,
      (__int64)&v34,
      (__int64)&v35,
      (__int64)&v32,
      (__int64)&v33);
    goto LABEL_34;
  }
  *((_DWORD *)this + 516) = a2;
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v33 = (const char *)a3;
    v35 = (const char *)*((int *)this + 516);
    v34 = v8;
    v32 = (const char *)*((int *)this + 436);
    v36 = "Associating session with activity id";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      v26,
      (unsigned int)byte_1800C48FB,
      v27,
      v28,
      (__int64)&v36,
      (__int64)&v32,
      (__int64)&v34,
      (__int64)&v35,
      (__int64)&v33);
  }
LABEL_34:
  if ( SecurityDescriptor < 0 )
    goto LABEL_5;
LABEL_35:
  v40 = 0;
  *(_OWORD *)v41 = 0;
  v42 = 0;
  v43 = 0;
  SecurityDescriptor = CTSSession::InitializeNotifyInfo(this, (struct __PTSSessInfo *)&v40);
  if ( SecurityDescriptor < 0 )
  {
LABEL_6:
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v36 = "CTSSession::Start";
      v15 = "Session Create";
      v16 = byte_1800C48BD;
LABEL_8:
      v33 = v15;
      LODWORD(v32) = SecurityDescriptor;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v12,
        (_DWORD)v16,
        v13,
        v14,
        (__int64)&v33,
        (__int64)&v36,
        (__int64)&v32);
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  LODWORD(v31) = 3277;
  CTSSession::CState::ChangeState(v21, 1, (char *)&v42 + 8, &v43, v31);
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)(*((_QWORD *)this + 228) + 1832LL) + 24LL))(
    *((_QWORD *)this + 228) + 1832LL,
    &v40);
  CTSSession::PublishWNFNotification(this, 0xAu, v41[2]);
  CAutoLock::Unlock((CAutoLock *)v39);
  if ( (_QWORD)v40 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40 + 16LL))(v40);
    *(_QWORD *)&v40 = 0;
  }
  v12 = v42;
  if ( (_QWORD)v42 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v42 + 16LL))(v42);
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    v36 = "CTSSession::Start";
    v15 = "Task completed successfully";
    v16 = &byte_1800C4887;
    goto LABEL_8;
  }
LABEL_9:
  CAutoLock::Unlock((CAutoLock *)v39);
  CAutoSetActivityId::~CAutoSetActivityId((CAutoSetActivityId *)v44);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v37);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v38);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x18006e6a0  mov     [rsp-8+arg_8], rbx
0x18006e6a5  push    rbp
0x18006e6a6  push    rsi
0x18006e6a7  push    rdi
0x18006e6a8  push    r12
0x18006e6aa  push    r13
0x18006e6ac  push    r14
0x18006e6ae  push    r15
0x18006e6b0  lea     rbp, [rsp-1Fh]
0x18006e6b5  sub     rsp, 0F0h
0x18006e6bc  mov     rax, cs:__security_cookie
0x18006e6c3  xor     rax, rsp
0x18006e6c6  mov     [rbp+4Fh+var_38], rax
0x18006e6ca  mov     r15, r8
0x18006e6cd  mov     r14d, edx
0x18006e6d0  mov     rsi, rcx
0x18006e6d3  mov     r12, [rbp+4Fh+arg_20]
0x18006e6d7  mov     [rbp+4Fh+var_A0], 0
0x18006e6df  mov     [rbp+4Fh+var_A8], 0
0x18006e6e7  lea     r13, [rcx+0C88h]
0x18006e6ee  mov     rdx, r13; struct _GUID *
0x18006e6f1  lea     rcx, [rbp+4Fh+var_50]; this
0x18006e6f5  call    ??0CAutoSetActivityId@@QEAA@PEAU_GUID@@@Z; CAutoSetActivityId::CAutoSetActivityId(_GUID *)
0x18006e6fa  nop
0x18006e6fb  mov     eax, cs:dword_1800DA020
0x18006e701  lea     rcx, aCtssessionStar; "CTSSession::Start"
0x18006e708  lea     rdx, aSessionCreate; "Session Create"
0x18006e70f  cmp     eax, 4
0x18006e712  jbe     short loc_18006E750
0x18006e714  lea     rax, aStartCsrssForA; "Start csrss for a new session"
0x18006e71b  mov     [rsp+120h+var_D0], rax
0x18006e720  mov     [rbp+4Fh+var_C0], rcx
0x18006e724  mov     [rbp+4Fh+var_B8], rdx
0x18006e728  lea     rax, [rsp+120h+var_D0]
0x18006e72d  mov     [rsp+120h+var_F0], rax
0x18006e732  lea     rax, [rbp+4Fh+var_C0]
0x18006e736  mov     [rsp+120h+var_F8], rax
0x18006e73b  lea     rax, [rbp+4Fh+var_B8]
0x18006e73f  mov     [rsp+120h+var_100], rax
0x18006e744  lea     rdx, word_1800C4A8A
0x18006e74b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18006e750  lea     rdx, [rsi+740h]; struct CResource *
0x18006e757  lea     rcx, [rbp+4Fh+var_98]; this
0x18006e75b  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18006e760  nop
0x18006e761  call    cs:__imp_WTSGetServiceSessionId
0x18006e767  cmp     eax, r14d
0x18006e76a  jnz     loc_18006E82C
0x18006e770  mov     ebx, 80070057h
0x18006e775  lea     rcx, [rbp+4Fh+var_98]; this
0x18006e779  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18006e77e  mov     r8d, ebx
0x18006e781  mov     edx, 1
0x18006e786  mov     rcx, rsi
0x18006e789  call    ?LogFailedTransition@CTSSession@@AEAAXW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@J@Z; CTSSession::LogFailedTransition(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,long)
0x18006e78e  mov     eax, cs:dword_1800DA020
0x18006e794  cmp     eax, 3
0x18006e797  jbe     short loc_18006E7DC
0x18006e799  lea     rax, aCtssessionStar; "CTSSession::Start"
0x18006e7a0  mov     [rbp+4Fh+var_B0], rax
0x18006e7a4  lea     rax, aSessionCreate; "Session Create"
0x18006e7ab  lea     rdx, byte_1800C48BD
0x18006e7b2  mov     [rbp+4Fh+var_C8], rax
0x18006e7b6  lea     rax, [rsp+120h+var_D0]
0x18006e7bb  mov     [rsp+120h+var_F0], rax
0x18006e7c0  lea     rax, [rbp+4Fh+var_B0]
0x18006e7c4  mov     [rsp+120h+var_F8], rax
0x18006e7c9  lea     rax, [rbp+4Fh+var_C8]
0x18006e7cd  mov     [rsp+120h+var_100], rax
0x18006e7d2  mov     dword ptr [rsp+120h+var_D0], ebx
0x18006e7d6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006e7db  nop
0x18006e7dc  lea     rcx, [rbp+4Fh+var_98]; this
0x18006e7e0  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18006e7e5  nop
0x18006e7e6  lea     rcx, [rbp+4Fh+var_50]; this
0x18006e7ea  call    ??1CAutoSetActivityId@@QEAA@XZ; CAutoSetActivityId::~CAutoSetActivityId(void)
0x18006e7ef  nop
0x18006e7f0  lea     rcx, [rbp+4Fh+var_A8]
0x18006e7f4  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006e7f9  nop
0x18006e7fa  lea     rcx, [rbp+4Fh+var_A0]
0x18006e7fe  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006e803  mov     eax, ebx
0x18006e805  mov     rcx, [rbp+4Fh+var_38]
0x18006e809  xor     rcx, rsp; StackCookie
0x18006e80c  call    __security_check_cookie
0x18006e811  mov     rbx, [rsp+120h+arg_8]
0x18006e819  add     rsp, 0F0h
0x18006e820  pop     r15
0x18006e822  pop     r14
0x18006e824  pop     r13
0x18006e826  pop     r12
0x18006e828  pop     rdi
0x18006e829  pop     rsi
0x18006e82a  pop     rbp
0x18006e82b  retn
0x18006e82c  mov     rcx, [rsi+638h]
0x18006e833  mov     rax, [rcx]
0x18006e836  lea     r8, [rbp+4Fh+var_A8]
0x18006e83a  lea     rdx, IID_ITSSession
0x18006e841  mov     rax, [rax+18h]
0x18006e845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e84a  mov     ebx, eax
0x18006e84c  test    eax, eax
0x18006e84e  jns     short loc_18006E8BD
0x18006e850  mov     ecx, cs:dword_1800DA020
0x18006e856  cmp     ecx, 3
0x18006e859  jbe     short loc_18006E8B1
0x18006e85b  lea     rax, aStart; "Start"
0x18006e862  mov     [rbp+4Fh+var_B8], rax
0x18006e866  mov     dword ptr [rsp+120h+var_D0], ebx
0x18006e86a  lea     rax, aQiItssession; "QI( ITSSession )"
0x18006e871  mov     [rbp+4Fh+var_C0], rax
0x18006e875  lea     rax, aWarningHresult; "Warning HResult failed"
0x18006e87c  mov     [rbp+4Fh+var_C8], rax
0x18006e880  lea     rax, [rbp+4Fh+var_B8]
0x18006e884  mov     [rsp+120h+var_E8], rax
0x18006e889  lea     rax, [rsp+120h+var_D0]
0x18006e88e  mov     [rsp+120h+var_F0], rax
0x18006e893  lea     rax, [rbp+4Fh+var_C0]
0x18006e897  mov     [rsp+120h+var_F8], rax
0x18006e89c  lea     rax, [rbp+4Fh+var_C8]
0x18006e8a0  mov     [rsp+120h+var_100], rax
0x18006e8a5  lea     rdx, byte_1800C4A4D
0x18006e8ac  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006e8b1  lea     rdi, [rsi+0CB8h]
0x18006e8b8  jmp     loc_18006EAFD
0x18006e8bd  lea     rdi, [rsi+0CB8h]
0x18006e8c4  mov     edx, 1
0x18006e8c9  mov     rcx, rdi
0x18006e8cc  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x18006e8d1  mov     ebx, eax
0x18006e8d3  test    eax, eax
0x18006e8d5  jns     short loc_18006E8F7
0x18006e8d7  mov     ecx, [rdi]
0x18006e8d9  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x18006e8de  mov     r8, rax
0x18006e8e1  lea     rdx, aInvalidStateFo_3; "invalid state for EvCreated, state is: "...
0x18006e8e8  mov     ecx, 8; int
0x18006e8ed  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e8f2  jmp     loc_18006EAFD
0x18006e8f7  cmp     eax, 1
0x18006e8fa  jnz     short loc_18006E93F
0x18006e8fc  mov     ecx, [rdi]; int
0x18006e8fe  call    ?GetLsmStateName@@YAPEBGH@Z; GetLsmStateName(int)
0x18006e903  mov     r9, rax
0x18006e906  mov     ecx, 1; int
0x18006e90b  call    ?GetLsmEventName@@YAPEBGH@Z; GetLsmEventName(int)
0x18006e910  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006e917  jz      loc_18006EB05
0x18006e91d  mov     [rsp+120h+var_100], rax
0x18006e922  mov     r8d, [rsi+6D0h]
0x18006e929  lea     rdx, aNoChangeToSess; "No change to session %d state %ws with "...
0x18006e930  mov     ecx, 2; int
0x18006e935  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e93a  jmp     loc_18006EB05
0x18006e93f  mov     rdx, r12; unsigned __int8 *
0x18006e942  mov     rcx, rsi; this
0x18006e945  call    ?ReadSecurityDescriptor@CTSSession@@AEAAJPEAEK@Z; CTSSession::ReadSecurityDescriptor(uchar *,ulong)
0x18006e94a  mov     ebx, eax
0x18006e94c  test    eax, eax
0x18006e94e  jns     short loc_18006E9BA
0x18006e950  mov     eax, cs:dword_1800DA020
0x18006e956  cmp     eax, 3
0x18006e959  jbe     loc_18006EAFD
0x18006e95f  lea     rax, aStart; "Start"
0x18006e966  mov     [rbp+4Fh+var_C8], rax
0x18006e96a  lea     rax, aReadsecurityde; "ReadSecurityDescriptor"
0x18006e971  lea     rdx, qword_1800C4A10
0x18006e978  mov     [rbp+4Fh+var_B8], rax
0x18006e97c  lea     rax, aWarningHresult; "Warning HResult failed"
0x18006e983  mov     [rbp+4Fh+var_C0], rax
0x18006e987  lea     rax, [rbp+4Fh+var_C8]
0x18006e98b  mov     [rsp+120h+var_E8], rax
0x18006e990  lea     rax, [rsp+120h+var_D0]
0x18006e995  mov     [rsp+120h+var_F0], rax
0x18006e99a  lea     rax, [rbp+4Fh+var_B8]
0x18006e99e  mov     [rsp+120h+var_F8], rax
0x18006e9a3  lea     rax, [rbp+4Fh+var_C0]
0x18006e9a7  mov     [rsp+120h+var_100], rax
0x18006e9ac  mov     dword ptr [rsp+120h+var_D0], ebx
0x18006e9b0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006e9b5  jmp     loc_18006EAFD
0x18006e9ba  lea     rdx, [rsi+700h]; struct ICsrEventSink *
0x18006e9c1  lea     rcx, [rsi+6C0h]; this
0x18006e9c8  mov     r8, r15; unsigned __int16 *
0x18006e9cb  call    ?Start@CCommonSessionData@CTSSession@@QEAAJPEAVICsrEventSink@@PEBG@Z; CTSSession::CCommonSessionData::Start(ICsrEventSink *,ushort const *)
0x18006e9d0  mov     ebx, eax
0x18006e9d2  test    eax, eax
0x18006e9d4  jns     short loc_18006EA03
0x18006e9d6  mov     eax, cs:dword_1800DA020
0x18006e9dc  cmp     eax, 3
0x18006e9df  jbe     loc_18006EAFD
0x18006e9e5  lea     rax, aStart; "Start"
0x18006e9ec  mov     [rbp+4Fh+var_C8], rax
0x18006e9f0  lea     rax, aCommondataStar; "CommonData.Start"
0x18006e9f7  lea     rdx, byte_1800C49D3
0x18006e9fe  jmp     loc_18006E978
0x18006ea03  lea     rdx, [rsi+6B0h]; struct ICsrPipe **
0x18006ea0a  mov     rcx, rsi; this
0x18006ea0d  call    ?GetCsrPipe@CTSSession@@UEAAJPEAPEAVICsrPipe@@@Z; CTSSession::GetCsrPipe(ICsrPipe * *)
0x18006ea12  mov     ebx, eax
0x18006ea14  test    eax, eax
0x18006ea16  jns     short loc_18006EA45
0x18006ea18  mov     eax, cs:dword_1800DA020
0x18006ea1e  cmp     eax, 3
0x18006ea21  jbe     loc_18006EAFD
0x18006ea27  lea     rax, aStart; "Start"
0x18006ea2e  mov     [rbp+4Fh+var_C8], rax
0x18006ea32  lea     rax, aGetcsrpipe; "GetCsrPipe"
0x18006ea39  lea     rdx, word_1800C4996
0x18006ea40  jmp     loc_18006E978
0x18006ea45  mov     rdx, rsi; struct ITSUnknown *
0x18006ea48  mov     rcx, [rsi+730h]; this
0x18006ea4f  call    ?Add@CSessionList@@QEAAJPEAUITSUnknown@@@Z; CSessionList::Add(ITSUnknown *)
0x18006ea54  mov     ebx, eax
0x18006ea56  test    eax, eax
0x18006ea58  jns     short loc_18006EA87
0x18006ea5a  mov     eax, cs:dword_1800DA020
0x18006ea60  cmp     eax, 3
0x18006ea63  jbe     loc_18006EAFD
0x18006ea69  lea     rax, aStart; "Start"
0x18006ea70  mov     [rbp+4Fh+var_C8], rax
0x18006ea74  lea     rax, aSessionlistAdd; "SessionList::Add"
0x18006ea7b  lea     rdx, byte_1800C4959
0x18006ea82  jmp     loc_18006E978
0x18006ea87  mov     [rsi+810h], r14d
0x18006ea8e  mov     eax, cs:dword_1800DA020
0x18006ea94  cmp     eax, 4
0x18006ea97  jbe     short loc_18006EAFD
0x18006ea99  mov     [rbp+4Fh+var_C8], r15
0x18006ea9d  movsxd  rax, dword ptr [rsi+810h]
0x18006eaa4  mov     [rbp+4Fh+var_B8], rax
0x18006eaa8  mov     [rbp+4Fh+var_C0], r13
0x18006eaac  movsxd  rax, dword ptr [rsi+6D0h]
0x18006eab3  mov     [rsp+120h+var_D0], rax
0x18006eab8  lea     rax, aAssociatingSes; "Associating session with activity id"
0x18006eabf  mov     [rbp+4Fh+var_B0], rax
0x18006eac3  lea     rax, [rbp+4Fh+var_C8]
0x18006eac7  mov     [rsp+120h+var_E0], rax
0x18006eacc  lea     rax, [rbp+4Fh+var_B8]
0x18006ead0  mov     [rsp+120h+var_E8], rax
0x18006ead5  lea     rax, [rbp+4Fh+var_C0]
0x18006ead9  mov     [rsp+120h+var_F0], rax
0x18006eade  lea     rax, [rsp+120h+var_D0]
0x18006eae3  mov     [rsp+120h+var_F8], rax
0x18006eae8  lea     rax, [rbp+4Fh+var_B0]
0x18006eaec  mov     [rsp+120h+var_100], rax
0x18006eaf1  lea     rdx, byte_1800C48FB
0x18006eaf8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18006eafd  test    ebx, ebx
0x18006eaff  js      loc_18006E775
0x18006eb05  xorps   xmm0, xmm0
0x18006eb08  xor     eax, eax
0x18006eb0a  movups  [rbp+4Fh+var_88], xmm0
0x18006eb0e  movups  xmmword ptr [rbp+4Fh+var_78], xmm0
0x18006eb12  movups  [rbp+4Fh+var_68], xmm0
0x18006eb16  mov     [rbp+4Fh+var_58], rax
0x18006eb1a  lea     rdx, [rbp+4Fh+var_88]; struct __PTSSessInfo *
0x18006eb1e  mov     rcx, rsi; this
0x18006eb21  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x18006eb26  mov     ebx, eax
0x18006eb28  test    eax, eax
0x18006eb2a  js      loc_18006E78E
0x18006eb30  mov     dword ptr [rsp+120h+var_100], 0CCDh
0x18006eb38  lea     r9, [rbp+4Fh+var_58]
0x18006eb3c  lea     r8, [rbp+4Fh+var_68+8]
0x18006eb40  mov     edx, 1
0x18006eb45  mov     rcx, rdi
0x18006eb48  call    ?ChangeState@CState@CTSSession@@QEAA?AW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@PEAKPEAT_LARGE_INTEGER@@K@Z; CTSSession::CState::ChangeState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,ulong *,_LARGE_INTEGER *,ulong)
0x18006eb4d  mov     rcx, [rsi+720h]
0x18006eb54  add     rcx, 728h
0x18006eb5b  mov     rax, [rcx]
0x18006eb5e  lea     rdx, [rbp+4Fh+var_88]
0x18006eb62  mov     rax, [rax+18h]
0x18006eb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb6b  mov     r8d, [rbp+4Fh+var_78+8]; unsigned int
0x18006eb6f  mov     edx, 0Ah; unsigned int
0x18006eb74  mov     rcx, rsi; this
0x18006eb77  call    ?PublishWNFNotification@CTSSession@@AEAAXKK@Z; CTSSession::PublishWNFNotification(ulong,ulong)
0x18006eb7c  lea     rcx, [rbp+4Fh+var_98]; this
0x18006eb80  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18006eb85  mov     rcx, qword ptr [rbp+4Fh+var_88]
0x18006eb89  test    rcx, rcx
0x18006eb8c  jz      short loc_18006EBA2
0x18006eb8e  mov     rax, [rcx]
0x18006eb91  mov     rax, [rax+10h]
0x18006eb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb9a  mov     qword ptr [rbp+4Fh+var_88], 0
0x18006eba2  mov     rcx, qword ptr [rbp+4Fh+var_68]
0x18006eba6  test    rcx, rcx
0x18006eba9  jz      short loc_18006EBB7
0x18006ebab  mov     rax, [rcx]
0x18006ebae  mov     rax, [rax+10h]
0x18006ebb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ebb7  mov     eax, cs:dword_1800DA020
0x18006ebbd  cmp     eax, 5
0x18006ebc0  jbe     loc_18006E7DC
0x18006ebc6  lea     rax, aCtssessionStar; "CTSSession::Start"
  ... truncated ...
```

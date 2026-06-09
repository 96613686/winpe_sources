# CTSSession::Start(long,ushort const *,ulong,uchar *)

- ea: `0x180072640`
- end: `0x180072b8c`
- name: `?Start@CTSSession@@UEAAJJPEBGKPEAE@Z`
- size: `1356`
- prototype: `__int64 __usercall@<rax>(CTSSession *__hidden this@<rcx>, int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800016b8`
- `0x180001b90`
- `0x1800077a0`
- `0x1800098e8`
- `0x18000c684`
- `0x1800118f4`
- `0x180011a28`
- `0x180011a50`
- `0x180011a78`
- `0x1800120d0`
- `0x18001266c`
- `0x1800129d0`
- `0x180014b20`
- `0x180026548`
- `0x180026b1c`
- `0x180028b30`
- `0x180029f3c`
- `0x18002ae18`
- `0x18002dfb0`
- `0x1800340f8`
- `0x18004e850`
- `0x1800709ac`
- `0x18007249c`
- `0x180072640`
- `0x18009c010`

## import_xrefs

- `KERNELBASE!WTSGetServiceSessionId` at `0x180072701`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180072701`

## string_xrefs

- `0x180072b78`: `Task completed successfully`
- `0x1800726a8`: `Session Create`
- `0x18007274a`: `Session Create`
- `0x180072888`: `invalid state for EvCreated, state is: "%s"`
- `0x180072911`: `ReadSecurityDescriptor`
- `0x180072997`: `CommonData.Start`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  const char *v28; // rax
  char *v29; // rdx
  const char *v30; // [rsp+50h] [rbp-81h] BYREF
  const char *v31; // [rsp+58h] [rbp-79h] BYREF
  const char *v32; // [rsp+60h] [rbp-71h] BYREF
  const char *v33; // [rsp+68h] [rbp-69h] BYREF
  const char *v34; // [rsp+70h] [rbp-61h] BYREF
  __int64 v35; // [rsp+78h] [rbp-59h] BYREF
  __int64 v36; // [rsp+80h] [rbp-51h] BYREF
  _BYTE v37[16]; // [rsp+88h] [rbp-49h] BYREF
  __int128 v38; // [rsp+98h] [rbp-39h] BYREF
  unsigned int v39[4]; // [rsp+A8h] [rbp-29h]
  __int128 v40; // [rsp+B8h] [rbp-19h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-9h] BYREF
  _BYTE v42[24]; // [rsp+D0h] [rbp-1h] BYREF

  v36 = 0;
  v35 = 0;
  v8 = (char *)this + 3208;
  CAutoSetActivityId::CAutoSetActivityId((CAutoSetActivityId *)v42, (struct _GUID *)((char *)this + 3208));
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v30 = "Start csrss for a new session";
    v32 = "CTSSession::Start";
    v33 = "Session Create";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"CTSSession::Start",
      (unsigned int)word_1800C9C12,
      v9,
      v10,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&v30);
  }
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v37, (CTSSession *)((char *)this + 1856));
  if ( (unsigned int)WTSGetServiceSessionId() == a2 )
  {
    SecurityDescriptor = -2147024809;
LABEL_5:
    CAutoLock::Unlock((CAutoLock *)v37);
    CTSSession::LogFailedTransition(this, 1, (unsigned int)SecurityDescriptor);
    goto LABEL_6;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 199) + 24LL))(
          *((_QWORD *)this + 199),
          &IID_ITSSession,
          &v35);
  SecurityDescriptor = v18;
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v33 = "Start";
      LODWORD(v30) = v18;
      v32 = "QI( ITSSession )";
      v31 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1800DF020,
        (unsigned int)byte_1800C9BD5,
        v19,
        v20,
        (__int64)&v31,
        (__int64)&v32,
        (__int64)&v30,
        (__int64)&v33);
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
    GetLsmEventName(1);
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "No change to session %d state %ws with event %ws", *((unsigned int *)this + 436));
    goto LABEL_35;
  }
  SecurityDescriptor = CTSSession::ReadSecurityDescriptor(this, a5, v23);
  if ( SecurityDescriptor < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_34;
    v31 = "Start";
    v28 = "ReadSecurityDescriptor";
    v29 = (char *)qword_1800C9B98;
    goto LABEL_22;
  }
  SecurityDescriptor = CTSSession::CCommonSessionData::Start(
                         (CTSSession *)((char *)this + 1728),
                         (CTSSession *)((char *)this + 1792),
                         a3);
  if ( SecurityDescriptor < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_34;
    v31 = "Start";
    v28 = "CommonData.Start";
    v29 = byte_1800C9B5B;
    goto LABEL_22;
  }
  SecurityDescriptor = CTSSession::GetCsrPipe(this, (struct ICsrPipe **)this + 214);
  if ( SecurityDescriptor < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_34;
    v31 = "Start";
    v28 = "GetCsrPipe";
    v29 = (char *)&word_1800C9B1E;
    goto LABEL_22;
  }
  SecurityDescriptor = CSessionList::Add(*((CSessionList **)this + 230), this);
  if ( SecurityDescriptor < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_34;
    v31 = "Start";
    v28 = "SessionList::Add";
    v29 = byte_1800C9AE1;
LABEL_22:
    v33 = v28;
    v32 = "Warning HResult failed";
    LODWORD(v30) = SecurityDescriptor;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v25,
      (_DWORD)v29,
      v26,
      v27,
      (__int64)&v32,
      (__int64)&v33,
      (__int64)&v30,
      (__int64)&v31);
    goto LABEL_34;
  }
  *((_DWORD *)this + 516) = a2;
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v31 = (const char *)a3;
    v33 = (const char *)*((int *)this + 516);
    v32 = v8;
    v30 = (const char *)*((int *)this + 436);
    v34 = "Associating session with activity id";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      v25,
      (unsigned int)byte_1800C9A83,
      v26,
      v27,
      (__int64)&v34,
      (__int64)&v30,
      (__int64)&v32,
      (__int64)&v33,
      (__int64)&v31);
  }
LABEL_34:
  if ( SecurityDescriptor < 0 )
    goto LABEL_5;
LABEL_35:
  v38 = 0;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v41 = 0;
  SecurityDescriptor = CTSSession::InitializeNotifyInfo(this, (struct __PTSSessInfo *)&v38);
  if ( SecurityDescriptor < 0 )
  {
LABEL_6:
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v34 = "CTSSession::Start";
      v15 = "Session Create";
      v16 = byte_1800C9A45;
LABEL_8:
      v31 = v15;
      LODWORD(v30) = SecurityDescriptor;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v12,
        (_DWORD)v16,
        v13,
        v14,
        (__int64)&v31,
        (__int64)&v34,
        (__int64)&v30);
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  CTSSession::CState::ChangeState(v21, 1, (char *)&v40 + 8, &v41, 3277);
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)(*((_QWORD *)this + 228) + 1832LL) + 24LL))(
    *((_QWORD *)this + 228) + 1832LL,
    &v38);
  CTSSession::PublishWNFNotification(this, 0xAu, v39[2]);
  CAutoLock::Unlock((CAutoLock *)v37);
  if ( (_QWORD)v38 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v38 + 16LL))(v38);
    *(_QWORD *)&v38 = 0;
  }
  v12 = v40;
  if ( (_QWORD)v40 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40 + 16LL))(v40);
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    v34 = "CTSSession::Start";
    v15 = "Task completed successfully";
    v16 = &byte_1800C9A0F;
    goto LABEL_8;
  }
LABEL_9:
  CAutoLock::Unlock((CAutoLock *)v37);
  CAutoSetActivityId::~CAutoSetActivityId((CAutoSetActivityId *)v42);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v35);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v36);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x180072640  mov     [rsp-8+arg_8], rbx
0x180072645  push    rbp
0x180072646  push    rsi
0x180072647  push    rdi
0x180072648  push    r12
0x18007264a  push    r13
0x18007264c  push    r14
0x18007264e  push    r15
0x180072650  lea     rbp, [rsp-1Fh]
0x180072655  sub     rsp, 0F0h
0x18007265c  mov     rax, cs:__security_cookie
0x180072663  xor     rax, rsp
0x180072666  mov     [rbp+4Fh+var_38], rax
0x18007266a  mov     r15, r8
0x18007266d  mov     r14d, edx
0x180072670  mov     rsi, rcx
0x180072673  mov     r12, [rbp+4Fh+arg_20]
0x180072677  mov     [rbp+4Fh+var_A0], 0
0x18007267f  mov     [rbp+4Fh+var_A8], 0
0x180072687  lea     r13, [rcx+0C88h]
0x18007268e  mov     rdx, r13; struct _GUID *
0x180072691  lea     rcx, [rbp+4Fh+var_50]; this
0x180072695  call    ??0CAutoSetActivityId@@QEAA@PEAU_GUID@@@Z; CAutoSetActivityId::CAutoSetActivityId(_GUID *)
0x18007269a  nop
0x18007269b  mov     eax, cs:dword_1800DF020
0x1800726a1  lea     rcx, aCtssessionStar; "CTSSession::Start"
0x1800726a8  lea     rdx, aSessionCreate; "Session Create"
0x1800726af  cmp     eax, 4
0x1800726b2  jbe     short loc_1800726F0
0x1800726b4  lea     rax, aStartCsrssForA; "Start csrss for a new session"
0x1800726bb  mov     [rsp+120h+var_D0], rax
0x1800726c0  mov     [rbp+4Fh+var_C0], rcx
0x1800726c4  mov     [rbp+4Fh+var_B8], rdx
0x1800726c8  lea     rax, [rsp+120h+var_D0]
0x1800726cd  mov     [rsp+120h+var_F0], rax
0x1800726d2  lea     rax, [rbp+4Fh+var_C0]
0x1800726d6  mov     [rsp+120h+var_F8], rax
0x1800726db  lea     rax, [rbp+4Fh+var_B8]
0x1800726df  mov     [rsp+120h+var_100], rax
0x1800726e4  lea     rdx, word_1800C9C12
0x1800726eb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800726f0  lea     rdx, [rsi+740h]; struct CResource *
0x1800726f7  lea     rcx, [rbp+4Fh+var_98]; this
0x1800726fb  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180072700  nop
0x180072701  call    cs:__imp_WTSGetServiceSessionId
0x180072708  nop     dword ptr [rax+rax+00h]
0x18007270d  cmp     eax, r14d
0x180072710  jnz     loc_1800727D3
0x180072716  mov     ebx, 80070057h
0x18007271b  lea     rcx, [rbp+4Fh+var_98]; this
0x18007271f  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180072724  mov     r8d, ebx
0x180072727  mov     edx, 1
0x18007272c  mov     rcx, rsi
0x18007272f  call    ?LogFailedTransition@CTSSession@@AEAAXW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@J@Z; CTSSession::LogFailedTransition(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,long)
0x180072734  mov     eax, cs:dword_1800DF020
0x18007273a  cmp     eax, 3
0x18007273d  jbe     short loc_180072782
0x18007273f  lea     rax, aCtssessionStar; "CTSSession::Start"
0x180072746  mov     [rbp+4Fh+var_B0], rax
0x18007274a  lea     rax, aSessionCreate; "Session Create"
0x180072751  lea     rdx, byte_1800C9A45
0x180072758  mov     [rbp+4Fh+var_C8], rax
0x18007275c  lea     rax, [rsp+120h+var_D0]
0x180072761  mov     [rsp+120h+var_F0], rax
0x180072766  lea     rax, [rbp+4Fh+var_B0]
0x18007276a  mov     [rsp+120h+var_F8], rax
0x18007276f  lea     rax, [rbp+4Fh+var_C8]
0x180072773  mov     [rsp+120h+var_100], rax
0x180072778  mov     dword ptr [rsp+120h+var_D0], ebx
0x18007277c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180072781  nop
0x180072782  lea     rcx, [rbp+4Fh+var_98]; this
0x180072786  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18007278b  nop
0x18007278c  lea     rcx, [rbp+4Fh+var_50]; this
0x180072790  call    ??1CAutoSetActivityId@@QEAA@XZ; CAutoSetActivityId::~CAutoSetActivityId(void)
0x180072795  nop
0x180072796  lea     rcx, [rbp+4Fh+var_A8]
0x18007279a  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18007279f  nop
0x1800727a0  lea     rcx, [rbp+4Fh+var_A0]
0x1800727a4  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800727a9  mov     eax, ebx
0x1800727ab  mov     rcx, [rbp+4Fh+var_38]
0x1800727af  xor     rcx, rsp; StackCookie
0x1800727b2  call    __security_check_cookie
0x1800727b7  mov     rbx, [rsp+120h+arg_8]
0x1800727bf  add     rsp, 0F0h
0x1800727c6  pop     r15
0x1800727c8  pop     r14
0x1800727ca  pop     r13
0x1800727cc  pop     r12
0x1800727ce  pop     rdi
0x1800727cf  pop     rsi
0x1800727d0  pop     rbp
0x1800727d1  retn
0x1800727d3  mov     rcx, [rsi+638h]
0x1800727da  mov     rax, [rcx]
0x1800727dd  lea     r8, [rbp+4Fh+var_A8]
0x1800727e1  lea     rdx, IID_ITSSession
0x1800727e8  mov     rax, [rax+18h]
0x1800727ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800727f1  mov     ebx, eax
0x1800727f3  test    eax, eax
0x1800727f5  jns     short loc_180072864
0x1800727f7  mov     ecx, cs:dword_1800DF020
0x1800727fd  cmp     ecx, 3
0x180072800  jbe     short loc_180072858
0x180072802  lea     rax, aStart; "Start"
0x180072809  mov     [rbp+4Fh+var_B8], rax
0x18007280d  mov     dword ptr [rsp+120h+var_D0], ebx
0x180072811  lea     rax, aQiItssession; "QI( ITSSession )"
0x180072818  mov     [rbp+4Fh+var_C0], rax
0x18007281c  lea     rax, aWarningHresult; "Warning HResult failed"
0x180072823  mov     [rbp+4Fh+var_C8], rax
0x180072827  lea     rax, [rbp+4Fh+var_B8]
0x18007282b  mov     [rsp+120h+var_E8], rax
0x180072830  lea     rax, [rsp+120h+var_D0]
0x180072835  mov     [rsp+120h+var_F0], rax
0x18007283a  lea     rax, [rbp+4Fh+var_C0]
0x18007283e  mov     [rsp+120h+var_F8], rax
0x180072843  lea     rax, [rbp+4Fh+var_C8]
0x180072847  mov     [rsp+120h+var_100], rax
0x18007284c  lea     rdx, byte_1800C9BD5
0x180072853  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180072858  lea     rdi, [rsi+0CB8h]
0x18007285f  jmp     loc_180072AA4
0x180072864  lea     rdi, [rsi+0CB8h]
0x18007286b  mov     edx, 1
0x180072870  mov     rcx, rdi
0x180072873  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x180072878  mov     ebx, eax
0x18007287a  test    eax, eax
0x18007287c  jns     short loc_18007289E
0x18007287e  mov     ecx, [rdi]
0x180072880  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x180072885  mov     r8, rax
0x180072888  lea     rdx, aInvalidStateFo_3; "invalid state for EvCreated, state is: "...
0x18007288f  mov     ecx, 8; int
0x180072894  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180072899  jmp     loc_180072AA4
0x18007289e  cmp     eax, 1
0x1800728a1  jnz     short loc_1800728E6
0x1800728a3  mov     ecx, [rdi]; int
0x1800728a5  call    ?GetLsmStateName@@YAPEBGH@Z; GetLsmStateName(int)
0x1800728aa  mov     r9, rax
0x1800728ad  mov     ecx, 1; int
0x1800728b2  call    ?GetLsmEventName@@YAPEBGH@Z; GetLsmEventName(int)
0x1800728b7  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x1800728be  jz      loc_180072AAC
0x1800728c4  mov     [rsp+120h+var_100], rax
0x1800728c9  mov     r8d, [rsi+6D0h]
0x1800728d0  lea     rdx, aNoChangeToSess; "No change to session %d state %ws with "...
0x1800728d7  mov     ecx, 2; int
0x1800728dc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800728e1  jmp     loc_180072AAC
0x1800728e6  mov     rdx, r12; unsigned __int8 *
0x1800728e9  mov     rcx, rsi; this
0x1800728ec  call    ?ReadSecurityDescriptor@CTSSession@@AEAAJPEAEK@Z; CTSSession::ReadSecurityDescriptor(uchar *,ulong)
0x1800728f1  mov     ebx, eax
0x1800728f3  test    eax, eax
0x1800728f5  jns     short loc_180072961
0x1800728f7  mov     eax, cs:dword_1800DF020
0x1800728fd  cmp     eax, 3
0x180072900  jbe     loc_180072AA4
0x180072906  lea     rax, aStart; "Start"
0x18007290d  mov     [rbp+4Fh+var_C8], rax
0x180072911  lea     rax, aReadsecurityde; "ReadSecurityDescriptor"
0x180072918  lea     rdx, qword_1800C9B98
0x18007291f  mov     [rbp+4Fh+var_B8], rax
0x180072923  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007292a  mov     [rbp+4Fh+var_C0], rax
0x18007292e  lea     rax, [rbp+4Fh+var_C8]
0x180072932  mov     [rsp+120h+var_E8], rax
0x180072937  lea     rax, [rsp+120h+var_D0]
0x18007293c  mov     [rsp+120h+var_F0], rax
0x180072941  lea     rax, [rbp+4Fh+var_B8]
0x180072945  mov     [rsp+120h+var_F8], rax
0x18007294a  lea     rax, [rbp+4Fh+var_C0]
0x18007294e  mov     [rsp+120h+var_100], rax
0x180072953  mov     dword ptr [rsp+120h+var_D0], ebx
0x180072957  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007295c  jmp     loc_180072AA4
0x180072961  lea     rdx, [rsi+700h]; struct ICsrEventSink *
0x180072968  lea     rcx, [rsi+6C0h]; this
0x18007296f  mov     r8, r15; unsigned __int16 *
0x180072972  call    ?Start@CCommonSessionData@CTSSession@@QEAAJPEAVICsrEventSink@@PEBG@Z; CTSSession::CCommonSessionData::Start(ICsrEventSink *,ushort const *)
0x180072977  mov     ebx, eax
0x180072979  test    eax, eax
0x18007297b  jns     short loc_1800729AA
0x18007297d  mov     eax, cs:dword_1800DF020
0x180072983  cmp     eax, 3
0x180072986  jbe     loc_180072AA4
0x18007298c  lea     rax, aStart; "Start"
0x180072993  mov     [rbp+4Fh+var_C8], rax
0x180072997  lea     rax, aCommondataStar; "CommonData.Start"
0x18007299e  lea     rdx, byte_1800C9B5B
0x1800729a5  jmp     loc_18007291F
0x1800729aa  lea     rdx, [rsi+6B0h]; struct ICsrPipe **
0x1800729b1  mov     rcx, rsi; this
0x1800729b4  call    ?GetCsrPipe@CTSSession@@UEAAJPEAPEAVICsrPipe@@@Z; CTSSession::GetCsrPipe(ICsrPipe * *)
0x1800729b9  mov     ebx, eax
0x1800729bb  test    eax, eax
0x1800729bd  jns     short loc_1800729EC
0x1800729bf  mov     eax, cs:dword_1800DF020
0x1800729c5  cmp     eax, 3
0x1800729c8  jbe     loc_180072AA4
0x1800729ce  lea     rax, aStart; "Start"
0x1800729d5  mov     [rbp+4Fh+var_C8], rax
0x1800729d9  lea     rax, aGetcsrpipe; "GetCsrPipe"
0x1800729e0  lea     rdx, word_1800C9B1E
0x1800729e7  jmp     loc_18007291F
0x1800729ec  mov     rdx, rsi; struct ITSUnknown *
0x1800729ef  mov     rcx, [rsi+730h]; this
0x1800729f6  call    ?Add@CSessionList@@QEAAJPEAUITSUnknown@@@Z; CSessionList::Add(ITSUnknown *)
0x1800729fb  mov     ebx, eax
0x1800729fd  test    eax, eax
0x1800729ff  jns     short loc_180072A2E
0x180072a01  mov     eax, cs:dword_1800DF020
0x180072a07  cmp     eax, 3
0x180072a0a  jbe     loc_180072AA4
0x180072a10  lea     rax, aStart; "Start"
0x180072a17  mov     [rbp+4Fh+var_C8], rax
0x180072a1b  lea     rax, aSessionlistAdd; "SessionList::Add"
0x180072a22  lea     rdx, byte_1800C9AE1
0x180072a29  jmp     loc_18007291F
0x180072a2e  mov     [rsi+810h], r14d
0x180072a35  mov     eax, cs:dword_1800DF020
0x180072a3b  cmp     eax, 4
0x180072a3e  jbe     short loc_180072AA4
0x180072a40  mov     [rbp+4Fh+var_C8], r15
0x180072a44  movsxd  rax, dword ptr [rsi+810h]
0x180072a4b  mov     [rbp+4Fh+var_B8], rax
0x180072a4f  mov     [rbp+4Fh+var_C0], r13
0x180072a53  movsxd  rax, dword ptr [rsi+6D0h]
0x180072a5a  mov     [rsp+120h+var_D0], rax
0x180072a5f  lea     rax, aAssociatingSes; "Associating session with activity id"
0x180072a66  mov     [rbp+4Fh+var_B0], rax
0x180072a6a  lea     rax, [rbp+4Fh+var_C8]
0x180072a6e  mov     [rsp+120h+var_E0], rax
0x180072a73  lea     rax, [rbp+4Fh+var_B8]
0x180072a77  mov     [rsp+120h+var_E8], rax
0x180072a7c  lea     rax, [rbp+4Fh+var_C0]
0x180072a80  mov     [rsp+120h+var_F0], rax
0x180072a85  lea     rax, [rsp+120h+var_D0]
0x180072a8a  mov     [rsp+120h+var_F8], rax
0x180072a8f  lea     rax, [rbp+4Fh+var_B0]
0x180072a93  mov     [rsp+120h+var_100], rax
0x180072a98  lea     rdx, byte_1800C9A83
0x180072a9f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180072aa4  test    ebx, ebx
0x180072aa6  js      loc_18007271B
0x180072aac  xorps   xmm0, xmm0
0x180072aaf  xor     eax, eax
0x180072ab1  movups  [rbp+4Fh+var_88], xmm0
0x180072ab5  movups  xmmword ptr [rbp+4Fh+var_78], xmm0
0x180072ab9  movups  [rbp+4Fh+var_68], xmm0
0x180072abd  mov     [rbp+4Fh+var_58], rax
0x180072ac1  lea     rdx, [rbp+4Fh+var_88]; struct __PTSSessInfo *
0x180072ac5  mov     rcx, rsi; this
0x180072ac8  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x180072acd  mov     ebx, eax
0x180072acf  test    eax, eax
0x180072ad1  js      loc_180072734
0x180072ad7  mov     dword ptr [rsp+120h+var_100], 0CCDh
0x180072adf  lea     r9, [rbp+4Fh+var_58]
0x180072ae3  lea     r8, [rbp+4Fh+var_68+8]
0x180072ae7  mov     edx, 1
0x180072aec  mov     rcx, rdi
0x180072aef  call    ?ChangeState@CState@CTSSession@@QEAA?AW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@PEAKPEAT_LARGE_INTEGER@@K@Z; CTSSession::CState::ChangeState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,ulong *,_LARGE_INTEGER *,ulong)
0x180072af4  mov     rcx, [rsi+720h]
0x180072afb  add     rcx, 728h
0x180072b02  mov     rax, [rcx]
0x180072b05  lea     rdx, [rbp+4Fh+var_88]
0x180072b09  mov     rax, [rax+18h]
0x180072b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b12  mov     r8d, [rbp+4Fh+var_78+8]; unsigned int
0x180072b16  mov     edx, 0Ah; unsigned int
0x180072b1b  mov     rcx, rsi; this
0x180072b1e  call    ?PublishWNFNotification@CTSSession@@AEAAXKK@Z; CTSSession::PublishWNFNotification(ulong,ulong)
0x180072b23  lea     rcx, [rbp+4Fh+var_98]; this
0x180072b27  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180072b2c  mov     rcx, qword ptr [rbp+4Fh+var_88]
0x180072b30  test    rcx, rcx
0x180072b33  jz      short loc_180072B49
0x180072b35  mov     rax, [rcx]
0x180072b38  mov     rax, [rax+10h]
0x180072b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b41  mov     qword ptr [rbp+4Fh+var_88], 0
0x180072b49  mov     rcx, qword ptr [rbp+4Fh+var_68]
0x180072b4d  test    rcx, rcx
0x180072b50  jz      short loc_180072B5E
0x180072b52  mov     rax, [rcx]
0x180072b55  mov     rax, [rax+10h]
0x180072b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b5e  mov     eax, cs:dword_1800DF020
0x180072b64  cmp     eax, 5
0x180072b67  jbe     loc_180072782
  ... truncated ...
```

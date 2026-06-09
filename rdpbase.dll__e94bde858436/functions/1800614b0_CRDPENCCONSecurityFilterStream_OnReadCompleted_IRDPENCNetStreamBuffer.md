# CRDPENCCONSecurityFilterStream::OnReadCompleted(IRDPENCNetStreamBuffer *)

- ea: `0x1800614b0`
- end: `0x180061c12`
- name: `?OnReadCompleted@CRDPENCCONSecurityFilterStream@@UEAAXPEAUIRDPENCNetStreamBuffer@@@Z`
- size: `1890`
- prototype: `void __fastcall(CRDPENCCONSecurityFilterStream *__hidden this, struct IRDPENCNetStreamBuffer *)`
- caller_count: `1`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005e950`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x180003158`
- `0x180005090`
- `0x18001b8b4`
- `0x180038d30`
- `0x180038dc0`
- `0x18003c4b4`
- `0x18003c6ac`
- `0x18003cbb8`
- `0x180044ee0`
- `0x18004bcc0`
- `0x18004e90c`
- `0x18005efd0`
- `0x18005f64c`
- `0x1800614b0`
- `0x180061fe0`
- `0x180062448`
- `0x1800ed3cc`
- `0x1800efeac`
- `0x1800f13cc`
- `0x1800f1cb4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180061589`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180061589`

## string_xrefs

- `0x180061af4`: `Not posting a receive on the transport, one already exists.`
- `0x1800614f7`: `OnReadCompleted`
- `0x180061681`: `OnReadCompleted`
- `0x180061759`: `OnReadCompleted`
- `0x18006181c`: `OnReadCompleted`
- `0x1800618e2`: `OnReadCompleted`
- `0x1800619ab`: `OnReadCompleted`
- `0x180061a4d`: `OnReadCompleted`
- `0x180061b89`: `OnReadCompleted`
- `0x1800615de`: `Read operation failed: freeing the read buffer.`
- `0x180061a34`: `Failed to dispatch reads`

## pseudocode

```c
void __fastcall CRDPENCCONSecurityFilterStream::OnReadCompleted(
        CRDPENCCONSecurityFilterStream *this,
        struct IRDPENCNetStreamBuffer *a2,
        int a3,
        int a4)
{
  CRDPENCCONSecurityFilterStream *v4; // rsi
  int v5; // r15d
  char *v8; // rdx
  int v9; // r9d
  int v10; // eax
  int v11; // ebx
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  char *v15; // rdx
  const char **v16; // rax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // eax
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  const char **v30; // [rsp+30h] [rbp-50h]
  const char **v31; // [rsp+40h] [rbp-40h]
  const char **v32; // [rsp+48h] [rbp-38h]
  const char *v33; // [rsp+50h] [rbp-30h] BYREF
  const char *v34; // [rsp+58h] [rbp-28h] BYREF
  const char *v35; // [rsp+60h] [rbp-20h] BYREF
  const char *v36; // [rsp+68h] [rbp-18h] BYREF
  int v37; // [rsp+70h] [rbp-10h] BYREF
  PSRWLOCK SRWLock; // [rsp+78h] [rbp-8h]
  int v39; // [rsp+B0h] [rbp+30h] BYREF
  const char *v40; // [rsp+C0h] [rbp+40h] BYREF
  const char *v41; // [rsp+C8h] [rbp+48h] BYREF

  v4 = (CRDPENCCONSecurityFilterStream *)((char *)this - 72);
  v39 = 0;
  v5 = 1;
  if ( *((_DWORD *)this + 65) != 1 )
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v40) = -2147019873;
      v41 = "OnReadCompleted";
      v33 = "state check failed.";
      v34 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)&word_1801C2E5E,
        a3,
        a4,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v40,
        (__int64)&v41);
    }
    return;
  }
  v8 = (char *)this + 56;
  if ( !*((_DWORD *)this + 66) )
  {
    v40 = 0;
    CAutoReadLock<CTSThreadPoolSafeReaderWriterLock>::CAutoReadLock<CTSThreadPoolSafeReaderWriterLock>(&v37, v8);
    ComCrossModuleSmartPtr<IRDPENCNetStreamEvents>::operator=(&v40, *((_QWORD *)this + 45));
    if ( v37 )
      ReleaseSRWLockShared(SRWLock);
    if ( v40 )
      (*(void (__fastcall **)(const char *, struct IRDPENCNetStreamBuffer *))(*(_QWORD *)v40 + 32LL))(v40, a2);
    ComCrossModuleSmartPtr<IRDPENCNetStreamEvents>::~ComCrossModuleSmartPtr<IRDPENCNetStreamEvents>(&v40);
    return;
  }
  CAutoWriteLock<CTSThreadPoolSafeReaderWriterLock>::CAutoWriteLock<CTSThreadPoolSafeReaderWriterLock>(&v37, v8);
  (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, int *))(*(_QWORD *)a2 + 72LL))(a2, &v39);
  if ( (v39 & 8) != 0 )
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      v40 = "Read operation failed: freeing the read buffer.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)byte_1801C2EA1,
        0,
        v9,
        (__int64)&v40);
    }
    CRDPENCCONSecurityFilterStream::FreeBuffer((CRDPENCCONSecurityFilterStream *)((char *)this - 24), a2);
    CAutoWriteLock<CTSThreadPoolSafeReaderWriterLock>::Unlock(&v37);
    return;
  }
  if ( (unsigned int)(*((_DWORD *)this + 66) - 1) <= 1 )
  {
    v10 = CRDPENCCONSecurityFilterStream::DoHandshake(v4, a2);
    v11 = v10;
    if ( v10 < 0 )
    {
      CRDPENCCONSecurityFilterStream::SetAndLogErrorState(v4, 9, 10, (unsigned int)v10);
      v14 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext <= 2 )
      {
LABEL_19:
        CAutoWriteLock<CTSThreadPoolSafeReaderWriterLock>::Unlock(&v37);
LABEL_51:
        CRDPENCCONSecurityFilterStream::OnStreamClosed(this, v11);
        CRDPENCCONSecurityFilterStream::Close((CRDPENCCONSecurityFilterStream *)((char *)this - 24));
        return;
      }
      LODWORD(v40) = 1017;
      v34 = "DoHandshake failed";
      v15 = (char *)&dword_1801C2DB4;
      v33 = "OnReadCompleted";
      v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v36 = "Error HResult failed";
      v32 = &v34;
      v31 = &v33;
      v30 = &v35;
      v16 = &v36;
LABEL_18:
      LODWORD(v41) = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v14,
        (_DWORD)v15,
        v12,
        v13,
        (__int64)v16,
        (__int64)&v41,
        (__int64)v30,
        (__int64)&v40,
        (__int64)v31,
        (__int64)v32);
      goto LABEL_19;
    }
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, 0);
  }
  if ( *((_DWORD *)this + 66) == 4 )
  {
    v17 = CRDPENCCONSecurityFilterStream::ProcessRDSTLSCreds(v4, a2);
    v11 = v17;
    if ( v17 < 0 )
    {
      CRDPENCCONSecurityFilterStream::SetAndLogErrorState(v4, 9, 14, (unsigned int)v17);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_19;
      LODWORD(v40) = 1029;
      v36 = "Failed to process redirected credentials";
      v15 = byte_1801C2E09;
      v35 = "OnReadCompleted";
      v34 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v33 = "Error HResult failed";
      v32 = &v36;
      v31 = &v35;
      v30 = &v34;
      v16 = &v33;
      goto LABEL_18;
    }
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, 0);
  }
  if ( *((_DWORD *)this + 66) == 3 )
  {
    v18 = CRDPENCCONSecurityFilterStream::SendRDSTLSCapabilities(v4);
    v11 = v18;
    if ( v18 < 0 )
    {
      CRDPENCCONSecurityFilterStream::SetAndLogErrorState(v4, 9, 15, (unsigned int)v18);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_19;
      LODWORD(v40) = 1041;
      v36 = "Failed to send RDSTLS capabilities packet to the client";
      v15 = (char *)word_1801C2D0A;
      v35 = "OnReadCompleted";
      v34 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v33 = "Error HResult failed";
      v32 = &v36;
      v31 = &v35;
      v30 = &v34;
      v16 = &v33;
      goto LABEL_18;
    }
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, 0);
  }
  if ( *((_DWORD *)this + 66) == 10 )
  {
    v19 = CRDPENCCONSecurityFilterStream::DoRdsAadHandshake(v4, a2);
    v11 = v19;
    if ( v19 < 0 )
    {
      CRDPENCCONSecurityFilterStream::SetAndLogErrorState(v4, 9, 20, (unsigned int)v19);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_19;
      LODWORD(v40) = 1053;
      v36 = "RDS AAD Auth handshake failed";
      v15 = &byte_1801C2D5F;
      v35 = "OnReadCompleted";
      v34 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v33 = "Error HResult failed";
      v32 = &v36;
      v31 = &v35;
      v30 = &v34;
      v16 = &v33;
      goto LABEL_18;
    }
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, 0);
  }
  if ( *((_DWORD *)this + 66) == 8 )
  {
    v20 = CRDPENCCONSecurityFilterStream::ProcessRecvdData(v4, a2, 1);
    v11 = v20;
    if ( v20 < 0 )
    {
      CRDPENCCONSecurityFilterStream::SetAndLogErrorState(v4, 9, 16, (unsigned int)v20);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_19;
      LODWORD(v40) = 1069;
      v36 = "Failed to process recvd data";
      v15 = (char *)&unk_1801C2C60;
      v35 = "OnReadCompleted";
      v34 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v33 = "Error HResult failed";
      v32 = &v36;
      v31 = &v35;
      v30 = &v34;
      v16 = &v33;
      goto LABEL_18;
    }
    v21 = CRDPENCCONSecurityFilterStream::CheckAndCompleteReads(v4);
    v11 = v21;
    if ( v21 < 0 )
    {
      CRDPENCCONSecurityFilterStream::SetAndLogErrorState(v4, 9, 17, (unsigned int)v21);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_19;
      LODWORD(v40) = 1080;
      v36 = "Failed to dispatch reads";
      v15 = byte_1801C2CB5;
      v35 = "OnReadCompleted";
      v34 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v33 = "Error HResult failed";
      v32 = &v36;
      v31 = &v35;
      v30 = &v34;
      v16 = &v33;
      goto LABEL_18;
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 28);
  if ( (unsigned int)CRDPENCCONSecurityFilterStream::NeedToPostReceive(v4) )
  {
    _InterlockedAdd((volatile signed __int32 *)this + 28, 1u);
    v22 = *((_DWORD *)this + 98);
  }
  else
  {
    v5 = 0;
    v22 = 0;
    if ( (unsigned int)CallbackContext > 5 )
    {
      LODWORD(v40) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 46) + 96LL))(*((_QWORD *)this + 46));
      LODWORD(v41) = *((_DWORD *)this + 28);
      v36 = "Not posting a receive on the transport, one already exists.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)word_1801C2BD2,
        v24,
        v25,
        (__int64)&v36,
        (__int64)&v41,
        (__int64)&v40);
    }
  }
  CRDPENCCONSecurityFilterStream::FreeBuffer((CRDPENCCONSecurityFilterStream *)((char *)this - 24), a2);
  CAutoWriteLock<CTSThreadPoolSafeReaderWriterLock>::Unlock(&v37);
  if ( v5 )
  {
    v26 = CRDPENCCONSecurityFilterStream::PostReceive(v4, v22);
    v11 = v26;
    if ( v26 < 0 )
    {
      CRDPENCCONSecurityFilterStream::SetAndLogErrorState(v4, 9, 18, (unsigned int)v26);
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v40) = 1121;
        v36 = "Failed to post receive";
        LODWORD(v41) = v11;
        v35 = "OnReadCompleted";
        v34 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
        v33 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v27,
          (unsigned int)byte_1801C2C0B,
          v28,
          v29,
          (__int64)&v33,
          (__int64)&v41,
          (__int64)&v34,
          (__int64)&v40,
          (__int64)&v35,
          (__int64)&v36);
      }
      goto LABEL_51;
    }
  }
}

```

## disassembly

```asm
0x1800614b0  mov     r11, rsp
0x1800614b3  mov     [r11+10h], rbx
0x1800614b7  push    rbp
0x1800614b8  push    rsi
0x1800614b9  push    rdi
0x1800614ba  push    r14
0x1800614bc  push    r15
0x1800614be  mov     rbp, rsp
0x1800614c1  sub     rsp, 80h
0x1800614c8  lea     rsi, [rcx-48h]
0x1800614cc  mov     [rbp+arg_0], 0
0x1800614d3  mov     r15d, 1
0x1800614d9  mov     r14, rdx
0x1800614dc  mov     rdi, rcx
0x1800614df  cmp     [rsi+14Ch], r15d
0x1800614e6  jz      short loc_180061551
0x1800614e8  mov     eax, cs:CallbackContext
0x1800614ee  cmp     eax, 3
0x1800614f1  jbe     loc_180061BFB
0x1800614f7  lea     rax, aOnreadcomplete; "OnReadCompleted"
0x1800614fe  mov     dword ptr [rbp+arg_10], 8007139Fh
0x180061505  mov     [rbp+arg_18], rax
0x180061509  lea     rdx, word_1801C2E5E
0x180061510  lea     rax, aStateCheckFail; "state check failed."
0x180061517  mov     [rbp+var_30], rax
0x18006151b  lea     rax, aWarningHresult; "Warning HResult failed"
0x180061522  mov     [rbp+var_28], rax
0x180061526  lea     rax, [rbp+arg_18]
0x18006152a  mov     [r11-70h], rax
0x18006152e  lea     rax, [rbp+arg_10]
0x180061532  mov     [r11-78h], rax
0x180061536  lea     rax, [rbp+var_30]
0x18006153a  mov     [r11-80h], rax
0x18006153e  lea     rax, [rbp+var_28]
0x180061542  mov     [rsp+80h+var_60], rax
0x180061547  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006154c  jmp     loc_180061BFB
0x180061551  cmp     dword ptr [rcx+108h], 0
0x180061558  lea     rdx, [rcx+38h]
0x18006155c  lea     rcx, [rbp+var_10]
0x180061560  jnz     short loc_1800615B5
0x180061562  mov     [rbp+arg_10], 0
0x18006156a  call    ??0?$CAutoReadLock@VCTSThreadPoolSafeReaderWriterLock@@@@QEAA@AEAVCTSThreadPoolSafeReaderWriterLock@@H@Z; CAutoReadLock<CTSThreadPoolSafeReaderWriterLock>::CAutoReadLock<CTSThreadPoolSafeReaderWriterLock>(CTSThreadPoolSafeReaderWriterLock &,int)
0x18006156f  mov     rdx, [rdi+168h]
0x180061576  lea     rcx, [rbp+arg_10]
0x18006157a  call    ??4?$ComCrossModuleSmartPtr@UIRDPENCNetStreamEvents@@@@QEAAPEAUIRDPENCNetStreamEvents@@PEAU1@@Z; ComCrossModuleSmartPtr<IRDPENCNetStreamEvents>::operator=(IRDPENCNetStreamEvents *)
0x18006157f  cmp     [rbp+var_10], 0
0x180061583  jz      short loc_18006158F
0x180061585  mov     rcx, [rbp+SRWLock]; SRWLock
0x180061589  call    cs:__imp_ReleaseSRWLockShared
0x18006158f  mov     rcx, [rbp+arg_10]
0x180061593  test    rcx, rcx
0x180061596  jz      short loc_1800615A7
0x180061598  mov     rax, [rcx]
0x18006159b  mov     rdx, r14
0x18006159e  mov     rax, [rax+20h]
0x1800615a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615a7  lea     rcx, [rbp+arg_10]; void *
0x1800615ab  call    ??1?$ComCrossModuleSmartPtr@UIRDPENCNetStreamEvents@@@@QEAA@XZ; ComCrossModuleSmartPtr<IRDPENCNetStreamEvents>::~ComCrossModuleSmartPtr<IRDPENCNetStreamEvents>(void)
0x1800615b0  jmp     loc_180061BFB
0x1800615b5  call    ??0?$CAutoWriteLock@VCTSThreadPoolSafeReaderWriterLock@@@@QEAA@AEAVCTSThreadPoolSafeReaderWriterLock@@H@Z; CAutoWriteLock<CTSThreadPoolSafeReaderWriterLock>::CAutoWriteLock<CTSThreadPoolSafeReaderWriterLock>(CTSThreadPoolSafeReaderWriterLock &,int)
0x1800615ba  mov     rax, [r14]
0x1800615bd  lea     rdx, [rbp+arg_0]
0x1800615c1  mov     rcx, r14
0x1800615c4  mov     rax, [rax+48h]
0x1800615c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615cd  test    byte ptr [rbp+arg_0], 8
0x1800615d1  jz      short loc_180061622
0x1800615d3  mov     eax, cs:CallbackContext
0x1800615d9  cmp     eax, 3
0x1800615dc  jbe     short loc_180061608
0x1800615de  lea     rax, aReadOperationF; "Read operation failed: freeing the read"...
0x1800615e5  xor     r8d, r8d
0x1800615e8  mov     [rbp+arg_10], rax
0x1800615ec  lea     rdx, byte_1801C2EA1
0x1800615f3  lea     rax, [rbp+arg_10]
0x1800615f7  lea     rcx, CallbackContext
0x1800615fe  mov     [rsp+80h+var_60], rax
0x180061603  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180061608  lea     rcx, [rdi-18h]; this
0x18006160c  mov     rdx, r14; struct IRDPENCNetStreamBuffer *
0x18006160f  call    ?FreeBuffer@CRDPENCCONSecurityFilterStream@@UEAAJPEAUIRDPENCNetStreamBuffer@@@Z; CRDPENCCONSecurityFilterStream::FreeBuffer(IRDPENCNetStreamBuffer *)
0x180061614  lea     rcx, [rbp+var_10]
0x180061618  call    ?Unlock@?$CAutoWriteLock@VCTSThreadPoolSafeReaderWriterLock@@@@QEAAXXZ; CAutoWriteLock<CTSThreadPoolSafeReaderWriterLock>::Unlock(void)
0x18006161d  jmp     loc_180061BFB
0x180061622  mov     eax, [rdi+108h]
0x180061628  sub     eax, r15d
0x18006162b  cmp     eax, r15d
0x18006162e  ja      loc_1800616FF
0x180061634  mov     rdx, r14; struct IRDPENCNetStreamBuffer *
0x180061637  mov     rcx, rsi; this
0x18006163a  call    ?DoHandshake@CRDPENCCONSecurityFilterStream@@AEAAJPEAUIRDPENCNetStreamBuffer@@@Z; CRDPENCCONSecurityFilterStream::DoHandshake(IRDPENCNetStreamBuffer *)
0x18006163f  mov     ebx, eax
0x180061641  test    eax, eax
0x180061643  jns     loc_1800616EE
0x180061649  mov     edx, 9
0x18006164e  mov     r9d, eax
0x180061651  mov     rcx, rsi
0x180061654  lea     r8d, [rdx+1]
0x180061658  call    ?SetAndLogErrorState@CRDPENCCONSecurityFilterStream@@AEAAXW4SecFilterState@1@W4SecFilterEvent@1@J@Z; CRDPENCCONSecurityFilterStream::SetAndLogErrorState(CRDPENCCONSecurityFilterStream::SecFilterState,CRDPENCCONSecurityFilterStream::SecFilterEvent,long)
0x18006165d  mov     ecx, cs:CallbackContext
0x180061663  cmp     ecx, 2
0x180061666  jbe     short loc_1800616E0
0x180061668  lea     rax, aDohandshakeFai; "DoHandshake failed"
0x18006166f  mov     dword ptr [rbp+arg_10], 3F9h
0x180061676  mov     [rbp+var_28], rax
0x18006167a  lea     rdx, dword_1801C2DB4
0x180061681  lea     rax, aOnreadcomplete; "OnReadCompleted"
0x180061688  mov     [rbp+var_30], rax
0x18006168c  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180061693  mov     [rbp+var_20], rax
0x180061697  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18006169e  mov     [rbp+var_18], rax
0x1800616a2  lea     rax, [rbp+var_28]
0x1800616a6  mov     [rsp+80h+var_38], rax
0x1800616ab  lea     rax, [rbp+var_30]
0x1800616af  mov     [rsp+80h+var_40], rax
0x1800616b4  lea     rax, [rbp+arg_10]
0x1800616b8  mov     [rsp+80h+var_48], rax
0x1800616bd  lea     rax, [rbp+var_20]
0x1800616c1  mov     [rsp+80h+var_50], rax
0x1800616c6  lea     rax, [rbp+arg_18]
0x1800616ca  mov     [rsp+80h+var_58], rax
0x1800616cf  lea     rax, [rbp+var_18]
0x1800616d3  mov     [rsp+80h+var_60], rax
0x1800616d8  mov     dword ptr [rbp+arg_18], ebx
0x1800616db  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800616e0  lea     rcx, [rbp+var_10]
0x1800616e4  call    ?Unlock@?$CAutoWriteLock@VCTSThreadPoolSafeReaderWriterLock@@@@QEAAXXZ; CAutoWriteLock<CTSThreadPoolSafeReaderWriterLock>::Unlock(void)
0x1800616e9  jmp     loc_180061BE8
0x1800616ee  mov     rax, [r14]
0x1800616f1  xor     edx, edx
0x1800616f3  mov     rcx, r14
0x1800616f6  mov     rax, [rax+30h]
0x1800616fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800616ff  cmp     dword ptr [rdi+108h], 4
0x180061706  jnz     loc_1800617C1
0x18006170c  mov     rdx, r14; struct IRDPENCNetStreamBuffer *
0x18006170f  mov     rcx, rsi; this
0x180061712  call    ?ProcessRDSTLSCreds@CRDPENCCONSecurityFilterStream@@AEAAJPEAUIRDPENCNetStreamBuffer@@@Z; CRDPENCCONSecurityFilterStream::ProcessRDSTLSCreds(IRDPENCNetStreamBuffer *)
0x180061717  mov     ebx, eax
0x180061719  test    eax, eax
0x18006171b  jns     loc_1800617B0
0x180061721  mov     edx, 9
0x180061726  mov     r9d, eax
0x180061729  mov     rcx, rsi
0x18006172c  lea     r8d, [rdx+5]
0x180061730  call    ?SetAndLogErrorState@CRDPENCCONSecurityFilterStream@@AEAAXW4SecFilterState@1@W4SecFilterEvent@1@J@Z; CRDPENCCONSecurityFilterStream::SetAndLogErrorState(CRDPENCCONSecurityFilterStream::SecFilterState,CRDPENCCONSecurityFilterStream::SecFilterEvent,long)
0x180061735  mov     eax, cs:CallbackContext
0x18006173b  cmp     eax, 2
0x18006173e  jbe     short loc_1800616E0
0x180061740  lea     rax, aFailedToProces_1; "Failed to process redirected credential"...
0x180061747  mov     dword ptr [rbp+arg_10], 405h
0x18006174e  mov     [rbp+var_18], rax
0x180061752  lea     rdx, byte_1801C2E09
0x180061759  lea     rax, aOnreadcomplete; "OnReadCompleted"
0x180061760  mov     [rbp+var_20], rax
0x180061764  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006176b  mov     [rbp+var_28], rax
0x18006176f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180061776  mov     [rbp+var_30], rax
0x18006177a  lea     rax, [rbp+var_18]
0x18006177e  mov     [rsp+80h+var_38], rax
0x180061783  lea     rax, [rbp+var_20]
0x180061787  mov     [rsp+80h+var_40], rax
0x18006178c  lea     rax, [rbp+arg_10]
0x180061790  mov     [rsp+80h+var_48], rax
0x180061795  lea     rax, [rbp+var_28]
0x180061799  mov     [rsp+80h+var_50], rax
0x18006179e  lea     rax, [rbp+arg_18]
0x1800617a2  mov     [rsp+80h+var_58], rax
0x1800617a7  lea     rax, [rbp+var_30]
0x1800617ab  jmp     loc_1800616D3
0x1800617b0  mov     rax, [r14]
0x1800617b3  xor     edx, edx
0x1800617b5  mov     rcx, r14
0x1800617b8  mov     rax, [rax+30h]
0x1800617bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617c1  cmp     dword ptr [rdi+108h], 3
0x1800617c8  jnz     loc_180061884
0x1800617ce  mov     rcx, rsi; this
0x1800617d1  call    ?SendRDSTLSCapabilities@CRDPENCCONSecurityFilterStream@@AEAAJXZ; CRDPENCCONSecurityFilterStream::SendRDSTLSCapabilities(void)
0x1800617d6  mov     ebx, eax
0x1800617d8  test    eax, eax
0x1800617da  jns     loc_180061873
0x1800617e0  mov     edx, 9
0x1800617e5  mov     r9d, eax
0x1800617e8  mov     rcx, rsi
0x1800617eb  lea     r8d, [rdx+6]
0x1800617ef  call    ?SetAndLogErrorState@CRDPENCCONSecurityFilterStream@@AEAAXW4SecFilterState@1@W4SecFilterEvent@1@J@Z; CRDPENCCONSecurityFilterStream::SetAndLogErrorState(CRDPENCCONSecurityFilterStream::SecFilterState,CRDPENCCONSecurityFilterStream::SecFilterEvent,long)
0x1800617f4  mov     eax, cs:CallbackContext
0x1800617fa  cmp     eax, 2
0x1800617fd  jbe     loc_1800616E0
0x180061803  lea     rax, aFailedToSendRd; "Failed to send RDSTLS capabilities pack"...
0x18006180a  mov     dword ptr [rbp+arg_10], 411h
0x180061811  mov     [rbp+var_18], rax
0x180061815  lea     rdx, word_1801C2D0A
0x18006181c  lea     rax, aOnreadcomplete; "OnReadCompleted"
0x180061823  mov     [rbp+var_20], rax
0x180061827  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006182e  mov     [rbp+var_28], rax
0x180061832  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180061839  mov     [rbp+var_30], rax
0x18006183d  lea     rax, [rbp+var_18]
0x180061841  mov     [rsp+80h+var_38], rax
0x180061846  lea     rax, [rbp+var_20]
0x18006184a  mov     [rsp+80h+var_40], rax
0x18006184f  lea     rax, [rbp+arg_10]
0x180061853  mov     [rsp+80h+var_48], rax
0x180061858  lea     rax, [rbp+var_28]
0x18006185c  mov     [rsp+80h+var_50], rax
0x180061861  lea     rax, [rbp+arg_18]
0x180061865  mov     [rsp+80h+var_58], rax
0x18006186a  lea     rax, [rbp+var_30]
0x18006186e  jmp     loc_1800616D3
0x180061873  mov     rax, [r14]
0x180061876  xor     edx, edx
0x180061878  mov     rcx, r14
0x18006187b  mov     rax, [rax+30h]
0x18006187f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061884  cmp     dword ptr [rdi+108h], 0Ah
0x18006188b  jnz     loc_18006194A
0x180061891  mov     rdx, r14; struct IRDPENCNetStreamBuffer *
0x180061894  mov     rcx, rsi; this
0x180061897  call    ?DoRdsAadHandshake@CRDPENCCONSecurityFilterStream@@AEAAJPEAUIRDPENCNetStreamBuffer@@@Z; CRDPENCCONSecurityFilterStream::DoRdsAadHandshake(IRDPENCNetStreamBuffer *)
0x18006189c  mov     ebx, eax
0x18006189e  test    eax, eax
0x1800618a0  jns     loc_180061939
0x1800618a6  mov     edx, 9
0x1800618ab  mov     r9d, eax
0x1800618ae  mov     rcx, rsi
0x1800618b1  lea     r8d, [rdx+0Bh]
0x1800618b5  call    ?SetAndLogErrorState@CRDPENCCONSecurityFilterStream@@AEAAXW4SecFilterState@1@W4SecFilterEvent@1@J@Z; CRDPENCCONSecurityFilterStream::SetAndLogErrorState(CRDPENCCONSecurityFilterStream::SecFilterState,CRDPENCCONSecurityFilterStream::SecFilterEvent,long)
0x1800618ba  mov     eax, cs:CallbackContext
0x1800618c0  cmp     eax, 2
0x1800618c3  jbe     loc_1800616E0
0x1800618c9  lea     rax, aRdsAadAuthHand; "RDS AAD Auth handshake failed"
0x1800618d0  mov     dword ptr [rbp+arg_10], 41Dh
0x1800618d7  mov     [rbp+var_18], rax
0x1800618db  lea     rdx, byte_1801C2D5F
0x1800618e2  lea     rax, aOnreadcomplete; "OnReadCompleted"
0x1800618e9  mov     [rbp+var_20], rax
0x1800618ed  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800618f4  mov     [rbp+var_28], rax
0x1800618f8  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800618ff  mov     [rbp+var_30], rax
0x180061903  lea     rax, [rbp+var_18]
0x180061907  mov     [rsp+80h+var_38], rax
0x18006190c  lea     rax, [rbp+var_20]
0x180061910  mov     [rsp+80h+var_40], rax
0x180061915  lea     rax, [rbp+arg_10]
0x180061919  mov     [rsp+80h+var_48], rax
0x18006191e  lea     rax, [rbp+var_28]
0x180061922  mov     [rsp+80h+var_50], rax
0x180061927  lea     rax, [rbp+arg_18]
0x18006192b  mov     [rsp+80h+var_58], rax
0x180061930  lea     rax, [rbp+var_30]
0x180061934  jmp     loc_1800616D3
0x180061939  mov     rax, [r14]
0x18006193c  xor     edx, edx
0x18006193e  mov     rcx, r14
0x180061941  mov     rax, [rax+30h]
0x180061945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006194a  cmp     dword ptr [rdi+108h], 8
0x180061951  jnz     loc_180061AA4
0x180061957  mov     r8d, r15d; int
0x18006195a  mov     rdx, r14; struct IRDPENCNetStreamBuffer *
0x18006195d  mov     rcx, rsi; this
0x180061960  call    ?ProcessRecvdData@CRDPENCCONSecurityFilterStream@@AEAAJPEAUIRDPENCNetStreamBuffer@@H@Z; CRDPENCCONSecurityFilterStream::ProcessRecvdData(IRDPENCNetStreamBuffer *,int)
0x180061965  mov     ebx, eax
0x180061967  mov     rcx, rsi; this
0x18006196a  test    eax, eax
0x18006196c  jns     loc_180061A02
0x180061972  mov     edx, 9
0x180061977  mov     r9d, eax
0x18006197a  lea     r8d, [rdx+7]
0x18006197e  call    ?SetAndLogErrorState@CRDPENCCONSecurityFilterStream@@AEAAXW4SecFilterState@1@W4SecFilterEvent@1@J@Z; CRDPENCCONSecurityFilterStream::SetAndLogErrorState(CRDPENCCONSecurityFilterStream::SecFilterState,CRDPENCCONSecurityFilterStream::SecFilterEvent,long)
0x180061983  mov     eax, cs:CallbackContext
0x180061989  cmp     eax, 2
0x18006198c  jbe     loc_1800616E0
0x180061992  lea     rax, aFailedToProces_0; "Failed to process recvd data"
0x180061999  mov     dword ptr [rbp+arg_10], 42Dh
0x1800619a0  mov     [rbp+var_18], rax
0x1800619a4  lea     rdx, unk_1801C2C60
0x1800619ab  lea     rax, aOnreadcomplete; "OnReadCompleted"
0x1800619b2  mov     [rbp+var_20], rax
0x1800619b6  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800619bd  mov     [rbp+var_28], rax
0x1800619c1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800619c8  mov     [rbp+var_30], rax
0x1800619cc  lea     rax, [rbp+var_18]
0x1800619d0  mov     [rsp+80h+var_38], rax
0x1800619d5  lea     rax, [rbp+var_20]
0x1800619d9  mov     [rsp+80h+var_40], rax
0x1800619de  lea     rax, [rbp+arg_10]
0x1800619e2  mov     [rsp+80h+var_48], rax
0x1800619e7  lea     rax, [rbp+var_28]
0x1800619eb  mov     [rsp+80h+var_50], rax
0x1800619f0  lea     rax, [rbp+arg_18]
0x1800619f4  mov     [rsp+80h+var_58], rax
  ... truncated ...
```

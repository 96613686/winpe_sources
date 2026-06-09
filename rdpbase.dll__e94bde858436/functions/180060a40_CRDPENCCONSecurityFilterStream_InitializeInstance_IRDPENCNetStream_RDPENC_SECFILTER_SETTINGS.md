# CRDPENCCONSecurityFilterStream::InitializeInstance(IRDPENCNetStream *,RDPENC_SECFILTER_SETTINGS *)

- ea: `0x180060a40`
- end: `0x1800612cb`
- name: `?InitializeInstance@CRDPENCCONSecurityFilterStream@@UEAAJPEAUIRDPENCNetStream@@PEAURDPENC_SECFILTER_SETTINGS@@@Z`
- size: `2187`
- prototype: `__int64 __fastcall(CRDPENCCONSecurityFilterStream *__hidden this, struct IRDPENCNetStream *, struct RDPENC_SECFILTER_SETTINGS *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001aa0`
- `0x180005090`
- `0x180019a80`
- `0x180019ab0`
- `0x1800205c0`
- `0x180038984`
- `0x180040f6c`
- `0x180046690`
- `0x180047710`
- `0x1800480a0`
- `0x18004a888`
- `0x18005ec08`
- `0x18005fdfc`
- `0x180060a40`
- `0x1800787d4`
- `0x180078c20`
- `0x18007969c`
- `0x1800888d8`
- `0x1800ec1c0`
- `0x18015e498`
- `0x1801614c4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060f1a`
- `ntdll!RtlIpv6StringToAddressW` at `0x180060ff8`
- `ntdll!RtlIpv6StringToAddressW` at `0x180060ff8`
- `ntdll!RtlIpv4StringToAddressW` at `0x180060fcd`
- `ntdll!RtlIpv4StringToAddressW` at `0x180060fcd`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180060db5`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180060db5`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180060f10`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180060f10`

## string_xrefs

- `0x180060d00`: `StringCchCopy failed`
- `0x180060eb9`: `StringCchCopy failed`
- `0x180060b98`: `Failed to create Context Pool`
- `0x180060af4`: `Failed to create LastSendCompletedEvent`
- `0x180060be9`: `StringCbCopy failed`
- `0x180060c30`: `StringCbCopy failed`
- `0x1800611de`: `Failed to create the read completion sync thread`
- `0x18006113e`: `Failed to initialize TLSLogger in CRDPENCCONSecurityFilterStream!`
- `0x180061185`: `Failed to initialize TLSLogger in CRDPENCCONSecurityFilterStream!`
- `0x18006121c`: `Failed to start the read completion sync thread`

## pseudocode

```c
__int64 __fastcall CRDPENCCONSecurityFilterStream::InitializeInstance(
        CRDPENCCONSecurityFilterStream *this,
        struct IRDPENCNetStream *a2,
        struct RDPENC_SECFILTER_SETTINGS *a3)
{
  _QWORD *v6; // r12
  __int64 v7; // rdx
  __int64 v8; // rcx
  signed int InstanceOfRDPSecFilterEvent; // ebx
  int v10; // r8d
  int v11; // r9d
  unsigned __int16 *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  const char *v15; // rax
  char *v16; // rdx
  unsigned __int16 *v17; // rcx
  size_t v18; // r11
  unsigned __int64 v19; // rbx
  size_t v20; // rax
  unsigned __int16 *v21; // rax
  __int64 v22; // rbx
  const CERT_CONTEXT *v23; // rcx
  unsigned int v24; // eax
  void *v25; // rax
  const unsigned __int16 *v26; // rcx
  unsigned __int64 v27; // rbx
  unsigned __int16 *v28; // rax
  void *v29; // rax
  signed int LastError; // eax
  const WCHAR *v31; // rcx
  _DWORD *v32; // rbx
  int v33; // eax
  int v34; // r8d
  int v35; // r9d
  unsigned int TLSLoggerInstance; // eax
  unsigned int v37; // eax
  __int64 v38; // rcx
  unsigned __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  const char *v42; // [rsp+60h] [rbp-A0h] BYREF
  const char *v43; // [rsp+68h] [rbp-98h] BYREF
  const char *v44; // [rsp+70h] [rbp-90h] BYREF
  const char *v45; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR Terminator[2]; // [rsp+80h] [rbp-80h] BYREF
  in_addr Addr[4]; // [rsp+90h] [rbp-70h] BYREF

  v40 = 0;
  v41 = 0;
  Terminator[0] = 0;
  memset_0(Addr, 0, 0x80u);
  v6 = (_QWORD *)((char *)this + 256);
  if ( a2 != *((struct IRDPENCNetStream **)this + 32) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 256);
    *v6 = a2;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 256);
  }
  *((_DWORD *)this + 61) = 0;
  CRDPENCCONSecurityFilterStream::SetAndLogState((char *)this - 88, 0, 0);
  InstanceOfRDPSecFilterEvent = CRDPSecFilterEvent::GetInstanceOfRDPSecFilterEvent((struct CRDPSecFilterEvent **)this + 54);
  if ( InstanceOfRDPSecFilterEvent < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v41) = 182;
      v45 = "Failed to create LastSendCompletedEvent";
      v42 = "InitializeInstance";
      v43 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      LODWORD(v40) = InstanceOfRDPSecFilterEvent;
      v44 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_1801C395B,
        v10,
        v11,
        (__int64)&v44,
        (__int64)&v40,
        (__int64)&v43,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v45);
    }
    goto LABEL_86;
  }
  InstanceOfRDPSecFilterEvent = CTSObjectPool<CRDPSecFilterContext>::CreateInstance(v8, v7, (char *)this + 384);
  if ( InstanceOfRDPSecFilterEvent < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v15 = "Failed to create Context Pool";
      LODWORD(v40) = 185;
      v16 = byte_1801C38B1;
LABEL_85:
      v44 = v15;
      v42 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v45 = "Error HResult failed";
      v43 = "InitializeInstance";
      LODWORD(v41) = InstanceOfRDPSecFilterEvent;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v12,
        (_DWORD)v16,
        v13,
        v14,
        (__int64)&v45,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v40,
        (__int64)&v43,
        (__int64)&v44);
      goto LABEL_86;
    }
    goto LABEL_86;
  }
  v17 = (unsigned __int16 *)((char *)this + 120);
  if ( *(_QWORD *)a3 )
  {
    InstanceOfRDPSecFilterEvent = StringCbCopyW(v17, 0x42u, *(const unsigned __int16 **)a3);
    if ( InstanceOfRDPSecFilterEvent < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v15 = "StringCbCopy failed";
        LODWORD(v40) = 189;
        v16 = (char *)&word_1801C3906;
        goto LABEL_85;
      }
LABEL_86:
      CRDPENCCONSecurityFilterStream::Terminate((CRDPENCCONSecurityFilterStream *)((char *)this - 80));
      return (unsigned int)InstanceOfRDPSecFilterEvent;
    }
  }
  else
  {
    InstanceOfRDPSecFilterEvent = StringCbCopyW(v17, 0x42u, L"DefaultListener");
    if ( InstanceOfRDPSecFilterEvent < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v15 = "StringCbCopy failed";
        LODWORD(v40) = 193;
        v16 = &byte_1801C3807;
        goto LABEL_85;
      }
      goto LABEL_86;
    }
  }
  v12 = (unsigned __int16 *)*((_QWORD *)a3 + 2);
  if ( v12 )
  {
    InstanceOfRDPSecFilterEvent = StringCchLengthW(v12, 0x104u, &v40);
    if ( InstanceOfRDPSecFilterEvent < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v15 = "StringCchLength failed";
        LODWORD(v40) = 199;
        v16 = (char *)&dword_1801C385C;
        goto LABEL_85;
      }
      goto LABEL_86;
    }
    v19 = v40 + 1;
    v20 = 2 * (v40 + 1);
    if ( !is_mul_ok(v40 + 1, 2u) )
      v20 = v18;
    v21 = (unsigned __int16 *)operator new(v20);
    *((_QWORD *)this + 24) = v21;
    if ( !v21 )
    {
LABEL_23:
      InstanceOfRDPSecFilterEvent = -2147024882;
      goto LABEL_86;
    }
    InstanceOfRDPSecFilterEvent = StringCchCopyW(v21, v19, *((const unsigned __int16 **)a3 + 2));
    if ( InstanceOfRDPSecFilterEvent < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v15 = "StringCchCopy failed";
        LODWORD(v40) = 210;
        v16 = byte_1801C375D;
        goto LABEL_85;
      }
      goto LABEL_86;
    }
  }
  v22 = *((_QWORD *)a3 + 3);
  if ( v22 != *((_QWORD *)this + 37) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 296);
    *((_QWORD *)this + 37) = v22;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
  }
  *((_DWORD *)this + 50) = *((_DWORD *)a3 + 8);
  *((_BYTE *)this + 204) = *((_BYTE *)a3 + 36);
  *((_BYTE *)this + 205) = *((_BYTE *)a3 + 37);
  InstanceOfRDPSecFilterEvent = CRDPENCCONSecurityFilterStream::AdjustEncryptionLevel(
                                  (CRDPENCCONSecurityFilterStream *)v12,
                                  (unsigned __int8 *)this + 205);
  if ( InstanceOfRDPSecFilterEvent < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v15 = "AdjustEncryptionLevel failed";
      LODWORD(v40) = 220;
      v16 = (char *)word_1801C37B2;
      goto LABEL_85;
    }
    goto LABEL_86;
  }
  v23 = (const CERT_CONTEXT *)*((_QWORD *)a3 + 6);
  if ( v23 )
    *((_QWORD *)this + 26) = CertDuplicateCertificateContext(v23);
  if ( *((_QWORD *)this + 26) )
  {
    *((_DWORD *)this + 56) = 20;
    v29 = operator new(0x14u);
    *((_QWORD *)this + 27) = v29;
    if ( !v29 )
      goto LABEL_23;
    if ( !CertGetCertificateContextProperty(*((PCCERT_CONTEXT *)this + 26), 3u, v29, (DWORD *)this + 56) )
    {
      LastError = GetLastError();
      InstanceOfRDPSecFilterEvent = LastError;
      if ( LastError > 0 )
        InstanceOfRDPSecFilterEvent = (unsigned __int16)LastError | 0x80070000;
      if ( InstanceOfRDPSecFilterEvent < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v15 = "CertGetCertificateContextProperty failed";
          LODWORD(v40) = 280;
          v16 = byte_1801C3609;
          goto LABEL_85;
        }
        goto LABEL_86;
      }
    }
  }
  else
  {
    if ( *((_QWORD *)a3 + 7) )
    {
      v24 = *((_DWORD *)a3 + 16);
      if ( v24 )
      {
        *((_DWORD *)this + 56) = v24;
        v25 = operator new(v24);
        *((_QWORD *)this + 27) = v25;
        if ( !v25 )
          goto LABEL_23;
        memcpy_0(v25, *((const void **)a3 + 7), *((unsigned int *)this + 56));
      }
    }
    v26 = (const unsigned __int16 *)*((_QWORD *)a3 + 9);
    if ( v26 )
    {
      InstanceOfRDPSecFilterEvent = StringCchLengthW(v26, 0x104u, &v41);
      if ( InstanceOfRDPSecFilterEvent < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v15 = "StringCchLength failed";
          LODWORD(v40) = 247;
          v16 = byte_1801C36B3;
          goto LABEL_85;
        }
        goto LABEL_86;
      }
      v27 = v41 + 1;
      v28 = (unsigned __int16 *)operator new(saturated_mul(v41 + 1, 2u));
      *((_QWORD *)this + 29) = v28;
      if ( !v28 )
        goto LABEL_23;
      InstanceOfRDPSecFilterEvent = StringCchCopyW(v28, v27, *((const unsigned __int16 **)a3 + 9));
      if ( InstanceOfRDPSecFilterEvent < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v15 = "StringCchCopy failed";
          LODWORD(v40) = 258;
          v16 = (char *)&unk_1801C3708;
          goto LABEL_85;
        }
        goto LABEL_86;
      }
    }
  }
  if ( *((_DWORD *)a3 + 3) )
  {
    *((_DWORD *)this + 60) = 1;
    InstanceOfRDPSecFilterEvent = CRDPENCCONSecurityFilterStream::ActivateInternal((CRDPENCCONSecurityFilterStream *)((char *)this - 88));
    if ( InstanceOfRDPSecFilterEvent < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v15 = "ActivateInternal failed";
        LODWORD(v40) = 289;
        v16 = (char *)&word_1801C365E;
        goto LABEL_85;
      }
      goto LABEL_86;
    }
  }
  v31 = (const WCHAR *)*((_QWORD *)a3 + 11);
  if ( v31 )
  {
    v32 = (_DWORD *)((char *)this + 472);
    if ( RtlIpv4StringToAddressW(v31, 1u, Terminator, Addr) )
    {
      if ( RtlIpv6StringToAddressW(*((PCWSTR *)a3 + 11), Terminator, (struct in6_addr *)Addr) )
      {
        memset_0((char *)this + 472, 0, 0x80u);
      }
      else
      {
        *((_OWORD *)this + 30) = *(_OWORD *)&Addr[0].S_un.S_un_b.s_b1;
        *v32 = 23;
        *((_DWORD *)this + 116) = 28;
      }
    }
    else
    {
      *((in_addr *)this + 119) = Addr[0];
      *v32 = 2;
      *((_DWORD *)this + 116) = 16;
    }
  }
  v33 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v6)(*v6, &IID_IRDPENCTcpEndpointInfo, (char *)this + 272);
  if ( v33 < 0 && (unsigned int)CallbackContext > 3 )
  {
    LODWORD(v40) = v33;
    v44 = "InitializeInstance";
    v43 = "TcpEndpointInfo interface not present on the underlying stream. Continuing without it.";
    v42 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)CallbackContext,
      (unsigned int)byte_1801C3571,
      v34,
      v35,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v40,
      (__int64)&v44);
  }
  InstanceOfRDPSecFilterEvent = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v6)(
                                  *v6,
                                  &IID_IRDPENCNetStreamEx,
                                  (char *)this + 264);
  if ( InstanceOfRDPSecFilterEvent < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v15 = "Failed to query for NetStreamEx interface!";
      LODWORD(v40) = 323;
      v16 = (char *)&dword_1801C35B4;
      goto LABEL_85;
    }
    goto LABEL_86;
  }
  if ( (unsigned int)IsTLSLoggerEnabled(1) == 1 )
  {
    TLSLoggerInstance = CreateTLSLoggerInstance(1, (char *)this + 600);
    InstanceOfRDPSecFilterEvent = MapXResultToHR(TLSLoggerInstance);
    if ( InstanceOfRDPSecFilterEvent < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v15 = "Failed to initialize TLSLogger in CRDPENCCONSecurityFilterStream!";
        LODWORD(v40) = 328;
        v16 = (char *)&dword_1801C351C;
        goto LABEL_85;
      }
      goto LABEL_86;
    }
    v37 = CreateTLSLoggerInstance(1, (char *)this + 608);
    InstanceOfRDPSecFilterEvent = MapXResultToHR(v37);
    if ( InstanceOfRDPSecFilterEvent < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v15 = "Failed to initialize TLSLogger in CRDPENCCONSecurityFilterStream!";
        LODWORD(v40) = 331;
        v16 = &byte_1801C34C7;
        goto LABEL_85;
      }
      goto LABEL_86;
    }
  }
  v38 = *((_QWORD *)this + 35);
  if ( v38 )
  {
    InstanceOfRDPSecFilterEvent = (*(__int64 (__fastcall **)(__int64, void (__fastcall *)(void *), _QWORD, char *))(*(_QWORD *)v38 + 56LL))(
                                    v38,
                                    CRDPENCCONSecurityFilterStream::STATIC_OnReadCompletedCallbackThreadProc,
                                    *((_QWORD *)this + 35),
                                    (char *)this + 72);
    if ( InstanceOfRDPSecFilterEvent < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v15 = "Failed to create the read completion sync thread";
        LODWORD(v40) = 341;
        v16 = byte_1801C3431;
        goto LABEL_85;
      }
      goto LABEL_86;
    }
    InstanceOfRDPSecFilterEvent = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 9) + 32LL))(
                                    *((_QWORD *)this + 9),
                                    0);
    if ( InstanceOfRDPSecFilterEvent < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v15 = "Failed to start the read completion sync thread";
        LODWORD(v40) = 344;
        v16 = (char *)&dword_1801C347C;
        goto LABEL_85;
      }
      goto LABEL_86;
    }
  }
  return (unsigned int)InstanceOfRDPSecFilterEvent;
}

```

## disassembly

```asm
0x180060a40  mov     [rsp-8+arg_8], rbx
0x180060a45  push    rbp
0x180060a46  push    rsi
0x180060a47  push    rdi
0x180060a48  push    r12
0x180060a4a  push    r13
0x180060a4c  push    r14
0x180060a4e  push    r15
0x180060a50  lea     rbp, [rsp-20h]
0x180060a55  sub     rsp, 120h
0x180060a5c  mov     rax, cs:__security_cookie
0x180060a63  xor     rax, rsp
0x180060a66  mov     [rbp+50h+var_40], rax
0x180060a6a  xor     r15d, r15d
0x180060a6d  mov     rsi, r8
0x180060a70  mov     rbx, rdx
0x180060a73  mov     [rsp+150h+var_100], r15
0x180060a78  mov     r14, rcx
0x180060a7b  mov     [rsp+150h+var_F8], r15
0x180060a80  xor     edx, edx; Val
0x180060a82  mov     [rbp+50h+Terminator], r15
0x180060a86  mov     r8d, 80h; Size
0x180060a8c  lea     rcx, [rbp+50h+Addr]; void *
0x180060a90  call    memset_0
0x180060a95  lea     r12, [r14+100h]
0x180060a9c  cmp     rbx, [r12]
0x180060aa0  jz      short loc_180060AB6
0x180060aa2  mov     rcx, r12; void *
0x180060aa5  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180060aaa  mov     rcx, r12
0x180060aad  mov     [r12], rbx
0x180060ab1  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180060ab6  xor     r8d, r8d
0x180060ab9  mov     [r14+0F4h], r15d
0x180060ac0  xor     edx, edx
0x180060ac2  lea     rcx, [r14-58h]
0x180060ac6  call    ?SetAndLogState@CRDPENCCONSecurityFilterStream@@AEAAXW4SecFilterState@1@W4SecFilterEvent@1@@Z; CRDPENCCONSecurityFilterStream::SetAndLogState(CRDPENCCONSecurityFilterStream::SecFilterState,CRDPENCCONSecurityFilterStream::SecFilterEvent)
0x180060acb  lea     rcx, [r14+1B0h]; struct CRDPSecFilterEvent **
0x180060ad2  call    ?GetInstanceOfRDPSecFilterEvent@CRDPSecFilterEvent@@SAJPEAPEAV1@@Z; CRDPSecFilterEvent::GetInstanceOfRDPSecFilterEvent(CRDPSecFilterEvent * *)
0x180060ad7  mov     ebx, eax
0x180060ad9  test    eax, eax
0x180060adb  jns     loc_180060B73
0x180060ae1  mov     ecx, cs:CallbackContext
0x180060ae7  mov     edi, 2
0x180060aec  cmp     ecx, edi
0x180060aee  jbe     loc_180061299
0x180060af4  lea     rax, aFailedToCreate_19; "Failed to create LastSendCompletedEvent"
0x180060afb  mov     dword ptr [rsp+150h+var_F8], 0B6h
0x180060b03  mov     [rsp+150h+var_D8], rax
0x180060b08  lea     rsi, aInitializeinst_1; "InitializeInstance"
0x180060b0f  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180060b16  mov     [rsp+150h+var_F0], rsi
0x180060b1b  mov     [rsp+150h+var_E8], rax
0x180060b20  lea     rdx, byte_1801C395B
0x180060b27  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180060b2e  mov     dword ptr [rsp+150h+var_100], ebx
0x180060b32  mov     [rsp+150h+var_E0], rax
0x180060b37  lea     rax, [rsp+150h+var_D8]
0x180060b3c  mov     [rsp+150h+var_108], rax
0x180060b41  lea     rax, [rsp+150h+var_F0]
0x180060b46  mov     [rsp+150h+var_110], rax
0x180060b4b  lea     rax, [rsp+150h+var_F8]
0x180060b50  mov     [rsp+150h+var_118], rax
0x180060b55  lea     rax, [rsp+150h+var_E8]
0x180060b5a  mov     [rsp+150h+var_120], rax
0x180060b5f  lea     rax, [rsp+150h+var_100]
0x180060b64  mov     [rsp+150h+var_128], rax
0x180060b69  lea     rax, [rsp+150h+var_E0]
0x180060b6e  jmp     loc_18006128F
0x180060b73  lea     r8, [r14+180h]
0x180060b7a  call    ?CreateInstance@?$CTSObjectPool@VCRDPSecFilterContext@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRDPSecFilterContext>::CreateInstance(uint,uint,CTSObjectPool<CRDPSecFilterContext> * *,int)
0x180060b7f  mov     ebx, eax
0x180060b81  test    eax, eax
0x180060b83  jns     short loc_180060BBA
0x180060b85  mov     eax, cs:CallbackContext
0x180060b8b  mov     edi, 2
0x180060b90  cmp     eax, edi
0x180060b92  jbe     loc_180061299
0x180060b98  lea     rax, aFailedToCreate_85; "Failed to create Context Pool"
0x180060b9f  mov     dword ptr [rsp+150h+var_100], 0B9h
0x180060ba7  lea     rsi, aInitializeinst_1; "InitializeInstance"
0x180060bae  lea     rdx, byte_1801C38B1
0x180060bb5  jmp     loc_180061232
0x180060bba  mov     r8, [rsi]; unsigned __int16 *
0x180060bbd  lea     rcx, [r14+78h]; unsigned __int16 *
0x180060bc1  mov     edx, 42h ; 'B'; unsigned __int64
0x180060bc6  test    r8, r8
0x180060bc9  jz      short loc_180060C0B
0x180060bcb  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180060bd0  mov     ebx, eax
0x180060bd2  test    eax, eax
0x180060bd4  jns     short loc_180060C52
0x180060bd6  mov     eax, cs:CallbackContext
0x180060bdc  mov     edi, 2
0x180060be1  cmp     eax, edi
0x180060be3  jbe     loc_180061299
0x180060be9  lea     rax, aStringcbcopyFa; "StringCbCopy failed"
0x180060bf0  mov     dword ptr [rsp+150h+var_100], 0BDh
0x180060bf8  lea     rsi, aInitializeinst_1; "InitializeInstance"
0x180060bff  lea     rdx, word_1801C3906
0x180060c06  jmp     loc_180061232
0x180060c0b  lea     r8, aDefaultlistene; "DefaultListener"
0x180060c12  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180060c17  mov     ebx, eax
0x180060c19  test    eax, eax
0x180060c1b  jns     short loc_180060C52
0x180060c1d  mov     eax, cs:CallbackContext
0x180060c23  mov     edi, 2
0x180060c28  cmp     eax, edi
0x180060c2a  jbe     loc_180061299
0x180060c30  lea     rax, aStringcbcopyFa; "StringCbCopy failed"
0x180060c37  mov     dword ptr [rsp+150h+var_100], 0C1h
0x180060c3f  lea     rsi, aInitializeinst_1; "InitializeInstance"
0x180060c46  lea     rdx, byte_1801C3807
0x180060c4d  jmp     loc_180061232
0x180060c52  mov     rcx, [rsi+10h]; unsigned __int16 *
0x180060c56  or      r11, 0FFFFFFFFFFFFFFFFh
0x180060c5a  mov     edi, 2
0x180060c5f  test    rcx, rcx
0x180060c62  jz      loc_180060D22
0x180060c68  lea     r8, [rsp+150h+var_100]; unsigned __int64 *
0x180060c6d  mov     edx, 104h; unsigned __int64
0x180060c72  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180060c77  mov     ebx, eax
0x180060c79  test    eax, eax
0x180060c7b  jns     short loc_180060CAD
0x180060c7d  mov     eax, cs:CallbackContext
0x180060c83  cmp     eax, edi
0x180060c85  jbe     loc_180061299
0x180060c8b  lea     rax, aStringcchlengt_3; "StringCchLength failed"
0x180060c92  mov     dword ptr [rsp+150h+var_100], 0C7h
0x180060c9a  lea     rsi, aInitializeinst_1; "InitializeInstance"
0x180060ca1  lea     rdx, dword_1801C385C
0x180060ca8  jmp     loc_180061232
0x180060cad  mov     rbx, [rsp+150h+var_100]
0x180060cb2  mov     rax, rdi
0x180060cb5  inc     rbx
0x180060cb8  mul     rbx
0x180060cbb  cmovb   rax, r11
0x180060cbf  mov     rcx, rax; Size
0x180060cc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060cc7  mov     [r14+0C0h], rax
0x180060cce  test    rax, rax
0x180060cd1  jnz     short loc_180060CDD
0x180060cd3  mov     ebx, 8007000Eh
0x180060cd8  jmp     loc_180061299
0x180060cdd  mov     r8, [rsi+10h]; unsigned __int16 *
0x180060ce1  mov     rdx, rbx; unsigned __int64
0x180060ce4  mov     rcx, rax; unsigned __int16 *
0x180060ce7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180060cec  mov     ebx, eax
0x180060cee  test    eax, eax
0x180060cf0  jns     short loc_180060D22
0x180060cf2  mov     eax, cs:CallbackContext
0x180060cf8  cmp     eax, edi
0x180060cfa  jbe     loc_180061299
0x180060d00  lea     rax, aStringcchcopyF_0; "StringCchCopy failed"
0x180060d07  mov     dword ptr [rsp+150h+var_100], 0D2h
0x180060d0f  lea     rsi, aInitializeinst_1; "InitializeInstance"
0x180060d16  lea     rdx, byte_1801C375D
0x180060d1d  jmp     loc_180061232
0x180060d22  mov     rbx, [rsi+18h]
0x180060d26  lea     r15, [r14+128h]
0x180060d2d  cmp     rbx, [r15]
0x180060d30  jz      short loc_180060D51
0x180060d32  mov     rcx, r15; void *
0x180060d35  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180060d3a  mov     [r15], rbx
0x180060d3d  test    rbx, rbx
0x180060d40  jz      short loc_180060D51
0x180060d42  mov     rax, [rbx]
0x180060d45  mov     rcx, rbx
0x180060d48  mov     rax, [rax+8]
0x180060d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060d51  mov     eax, [rsi+20h]
0x180060d54  lea     rdx, [r14+0CDh]; unsigned __int8 *
0x180060d5b  mov     [r14+0C8h], eax
0x180060d62  mov     al, [rsi+24h]
0x180060d65  mov     [r14+0CCh], al
0x180060d6c  mov     al, [rsi+25h]
0x180060d6f  mov     [rdx], al
0x180060d71  call    ?AdjustEncryptionLevel@CRDPENCCONSecurityFilterStream@@AEAAJPEAE@Z; CRDPENCCONSecurityFilterStream::AdjustEncryptionLevel(uchar *)
0x180060d76  mov     ebx, eax
0x180060d78  test    eax, eax
0x180060d7a  jns     short loc_180060DAC
0x180060d7c  mov     eax, cs:CallbackContext
0x180060d82  cmp     eax, edi
0x180060d84  jbe     loc_180061299
0x180060d8a  lea     rax, aAdjustencrypti; "AdjustEncryptionLevel failed"
0x180060d91  mov     dword ptr [rsp+150h+var_100], 0DCh
0x180060d99  lea     rsi, aInitializeinst_1; "InitializeInstance"
0x180060da0  lea     rdx, word_1801C37B2
0x180060da7  jmp     loc_180061232
0x180060dac  mov     rcx, [rsi+30h]; pCertContext
0x180060db0  test    rcx, rcx
0x180060db3  jz      short loc_180060DC2
0x180060db5  call    cs:__imp_CertDuplicateCertificateContext
0x180060dbb  mov     [r14+0D0h], rax
0x180060dc2  cmp     qword ptr [r14+0D0h], 0
0x180060dca  jnz     loc_180060EDB
0x180060dd0  cmp     qword ptr [rsi+38h], 0
0x180060dd5  jz      short loc_180060E0F
0x180060dd7  mov     eax, [rsi+40h]
0x180060dda  test    eax, eax
0x180060ddc  jz      short loc_180060E0F
0x180060dde  mov     ecx, eax; Size
0x180060de0  mov     [r14+0E0h], eax
0x180060de7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060dec  mov     [r14+0D8h], rax
0x180060df3  test    rax, rax
0x180060df6  jz      loc_180060CD3
0x180060dfc  mov     r8d, [r14+0E0h]; Size
0x180060e03  mov     rcx, rax; void *
0x180060e06  mov     rdx, [rsi+38h]; Src
0x180060e0a  call    memcpy_0
0x180060e0f  mov     rcx, [rsi+48h]; unsigned __int16 *
0x180060e13  test    rcx, rcx
0x180060e16  jz      loc_180060F63
0x180060e1c  lea     r8, [rsp+150h+var_F8]; unsigned __int64 *
0x180060e21  mov     edx, 104h; unsigned __int64
0x180060e26  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180060e2b  mov     ebx, eax
0x180060e2d  test    eax, eax
0x180060e2f  jns     short loc_180060E61
0x180060e31  mov     eax, cs:CallbackContext
0x180060e37  cmp     eax, edi
0x180060e39  jbe     loc_180061299
0x180060e3f  lea     rax, aStringcchlengt_3; "StringCchLength failed"
0x180060e46  mov     dword ptr [rsp+150h+var_100], 0F7h
0x180060e4e  lea     rsi, aInitializeinst_1; "InitializeInstance"
0x180060e55  lea     rdx, byte_1801C36B3
0x180060e5c  jmp     loc_180061232
0x180060e61  mov     rbx, [rsp+150h+var_F8]
0x180060e66  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180060e6d  inc     rbx
0x180060e70  mov     rax, rdi
0x180060e73  mul     rbx
0x180060e76  cmovb   rax, rcx
0x180060e7a  mov     rcx, rax; Size
0x180060e7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060e82  mov     [r14+0E8h], rax
0x180060e89  test    rax, rax
0x180060e8c  jz      loc_180060CD3
0x180060e92  mov     r8, [rsi+48h]; unsigned __int16 *
0x180060e96  mov     rdx, rbx; unsigned __int64
0x180060e99  mov     rcx, rax; unsigned __int16 *
0x180060e9c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180060ea1  mov     ebx, eax
0x180060ea3  test    eax, eax
0x180060ea5  jns     loc_180060F63
0x180060eab  mov     eax, cs:CallbackContext
0x180060eb1  cmp     eax, edi
0x180060eb3  jbe     loc_180061299
0x180060eb9  lea     rax, aStringcchcopyF_0; "StringCchCopy failed"
0x180060ec0  mov     dword ptr [rsp+150h+var_100], 102h
0x180060ec8  lea     rsi, aInitializeinst_1; "InitializeInstance"
0x180060ecf  lea     rdx, unk_1801C3708
0x180060ed6  jmp     loc_180061232
0x180060edb  mov     ecx, 14h; Size
0x180060ee0  lea     rbx, [r14+0E0h]
0x180060ee7  mov     [rbx], ecx
0x180060ee9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060eee  mov     [r14+0D8h], rax
0x180060ef5  test    rax, rax
0x180060ef8  jz      loc_180060CD3
0x180060efe  mov     rcx, [r14+0D0h]; pCertContext
0x180060f05  mov     r9, rbx; pcbData
0x180060f08  mov     r8, rax; pvData
0x180060f0b  mov     edx, 3; dwPropId
0x180060f10  call    cs:__imp_CertGetCertificateContextProperty
0x180060f16  test    eax, eax
0x180060f18  jnz     short loc_180060F63
0x180060f1a  call    cs:__imp_GetLastError
0x180060f20  mov     ebx, eax
0x180060f22  test    eax, eax
0x180060f24  jle     short loc_180060F2F
0x180060f26  movzx   ebx, ax
0x180060f29  or      ebx, 80070000h
0x180060f2f  test    ebx, ebx
0x180060f31  jns     short loc_180060F63
0x180060f33  mov     eax, cs:CallbackContext
0x180060f39  cmp     eax, edi
0x180060f3b  jbe     loc_180061299
0x180060f41  lea     rax, aCertgetcertifi_0; "CertGetCertificateContextProperty faile"...
0x180060f48  mov     dword ptr [rsp+150h+var_100], 118h
0x180060f50  lea     rsi, aInitializeinst_1; "InitializeInstance"
0x180060f57  lea     rdx, byte_1801C3609
0x180060f5e  jmp     loc_180061232
0x180060f63  cmp     dword ptr [rsi+0Ch], 0
0x180060f67  jz      short loc_180060FB3
0x180060f69  lea     rcx, [r14-58h]; this
0x180060f6d  mov     dword ptr [r14+0F0h], 1
0x180060f78  call    ?ActivateInternal@CRDPENCCONSecurityFilterStream@@AEAAJXZ; CRDPENCCONSecurityFilterStream::ActivateInternal(void)
0x180060f7d  mov     ebx, eax
0x180060f7f  test    eax, eax
0x180060f81  jns     short loc_180060FB3
0x180060f83  mov     eax, cs:CallbackContext
0x180060f89  cmp     eax, edi
0x180060f8b  jbe     loc_180061299
0x180060f91  lea     rax, aActivateintern_0; "ActivateInternal failed"
  ... truncated ...
```

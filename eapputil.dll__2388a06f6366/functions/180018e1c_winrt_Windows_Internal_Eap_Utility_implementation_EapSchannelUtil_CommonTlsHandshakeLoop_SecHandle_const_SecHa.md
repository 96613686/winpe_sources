# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::CommonTlsHandshakeLoop(_SecHandle * const,_SecHandle * const,_SecBufferDesc * const)

- ea: `0x180018e1c`
- end: `0x18001963e`
- name: `?CommonTlsHandshakeLoop@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXQEAU_SecHandle@@0QEAU_SecBufferDesc@@@Z`
- size: `2082`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *__hidden this, struct _SecHandle *const, struct _SecHandle *const, struct _SecBufferDesc *const)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001866c`
- `0x1800196c0`

## callees

- `0x18000163c`
- `0x1800021d0`
- `0x180005efc`
- `0x1800083ec`
- `0x1800101c4`
- `0x180010df0`
- `0x180010e04`
- `0x18001392c`
- `0x180013bd8`
- `0x18001636c`
- `0x180016458`
- `0x1800164e8`
- `0x180018e1c`
- `0x180019dc4`
- `0x18001b578`
- `0x18001ccc4`
- `0x18001cd3c`
- `0x18001d6d0`
- `0x18001e4c8`
- `0x180023af4`
- `0x180024f14`
- `0x18002e2c8`
- `0x18002e5f4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190da`
- `SspiCli!FreeContextBuffer` at `0x180019564`
- `SspiCli!FreeContextBuffer` at `0x180019564`
- `SspiCli!InitializeSecurityContextW` at `0x180019052`
- `SspiCli!InitializeSecurityContextW` at `0x180019052`
- `SspiCli!QueryContextAttributesW` at `0x180019097`
- `SspiCli!QueryContextAttributesW` at `0x1800190b9`
- `SspiCli!QueryContextAttributesW` at `0x180019105`
- `SspiCli!QueryContextAttributesW` at `0x180019097`
- `SspiCli!QueryContextAttributesW` at `0x1800190b9`
- `SspiCli!QueryContextAttributesW` at `0x180019105`
- `CRYPT32!CertFreeCertificateContext` at `0x1800190e5`
- `CRYPT32!CertFreeCertificateContext` at `0x1800190e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::CommonTlsHandshakeLoop(
        winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *this,
        struct _SecHandle *const a2,
        struct _SecHandle *const phNewContext,
        struct _SecBufferDesc *const a4)
{
  char v6; // al
  PSecBuffer pBuffers; // rax
  struct _SecBuffer *pvBuffer; // rdx
  __int64 *v9; // rax
  int v10; // ebx
  int v11; // edi
  int v12; // esi
  const unsigned __int16 *AlgString; // rax
  char *v14; // r12
  int v15; // edx
  unsigned int v16; // edi
  bool v17; // r8
  SECURITY_STATUS ContextAttributesW; // eax
  SECURITY_STATUS v19; // eax
  const CERT_CONTEXT *v20; // r15
  DWORD LastError; // ebx
  SECURITY_STATUS v22; // eax
  const void *const *v23; // rdx
  char v24; // r8
  PSecBuffer v25; // rdx
  char v26; // al
  int v27; // eax
  char IsEnabled; // al
  int *v29; // rbx
  int v30; // ecx
  PSecBuffer v31; // rax
  unsigned int cbBuffer; // r15d
  gsl::details *v33; // rcx
  char *v34; // r8
  int v35; // eax
  __int64 v36; // rbx
  __int64 *v37; // rax
  int v38; // ebx
  int v39; // edi
  int v40; // esi
  const unsigned __int16 *v41; // rax
  _DWORD *v42; // rcx
  unsigned int Reserved1; // [rsp+20h] [rbp-E0h]
  unsigned int Reserved1a; // [rsp+20h] [rbp-E0h]
  unsigned int Reserved2; // [rsp+38h] [rbp-C8h]
  char v46; // [rsp+60h] [rbp-A0h]
  unsigned int v47; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+78h] [rbp-88h] BYREF
  unsigned int pfContextAttr[2]; // [rsp+80h] [rbp-80h] BYREF
  int v52[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v54[2]; // [rsp+98h] [rbp-68h] BYREF
  PVOID pvContextBuffer; // [rsp+A0h] [rbp-60h]
  struct _SecBufferDesc pOutput; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v58; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v59; // [rsp+D0h] [rbp-30h] BYREF
  struct _SecHandle *v60; // [rsp+D8h] [rbp-28h]
  struct _SecHandle *v61; // [rsp+E0h] [rbp-20h]
  _QWORD v62[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v63[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v64[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v65[3]; // [rsp+120h] [rbp+20h] BYREF
  char v66; // [rsp+138h] [rbp+38h]
  int v67; // [rsp+140h] [rbp+40h] BYREF
  __int128 v68; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v61 = phNewContext;
  v60 = a2;
  if ( !a4 || (v6 = 1, a4->cBuffers == 2) )
    v6 = 0;
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2DC,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)0x80070057LL,
      Reserved1);
  if ( *((_DWORD *)this + 19) == 2 )
  {
    pBuffers = a4->pBuffers;
    pvBuffer = (struct _SecBuffer *)pBuffers->pvBuffer;
    if ( !pvBuffer && pBuffers->cbBuffer )
      gsl::details::terminate((gsl::details *)pBuffers->cbBuffer);
    *(_QWORD *)&pOutput.ulVersion = pBuffers->cbBuffer;
    pOutput.pBuffers = pvBuffer;
    winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(&v50, &pOutput);
    winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::DecryptData(
      (__int64)this,
      (__int64)pfContextAttr,
      (__int64)&v50);
    *((_DWORD *)this + 19) = 3;
    v47 = ((unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(pfContextAttr) == 0)
        + 1;
    *(_QWORD *)&pOutput.ulVersion = 0;
    pOutput.pBuffers = 0;
    winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(&v49, &pOutput);
    v9 = winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation,winrt::Windows::Storage::Streams::IBuffer &,_SecPkgContext_StreamSizes &,unsigned long &>(
           &v53,
           &v49,
           (_DWORD *)this + 34,
           (int *)this + 39);
    winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs,enum winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus &,winrt::Windows::Internal::Eap::Utility::EapTlsConnectedPeerInformation>(
      &v48,
      (int *)&v47,
      v9);
    if ( v53 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v53);
    winrt::Windows::Internal::Eap::Utility::implementation::inproc_error_propagating_event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>>::operator()<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>(
      (char *)this + 48,
      this,
      &v48);
    v10 = *((_DWORD *)this + 36);
    v11 = *((_DWORD *)this + 35);
    v12 = *((_DWORD *)this + 34);
    AlgString = winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::GetAlgString(this);
    winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::TlsHandshakeFinished(
      *((unsigned int *)this + 18),
      v47,
      *((unsigned int *)this + 39),
      AlgString,
      v12,
      v11,
      v10,
      0);
    if ( v48 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v48);
    if ( v49 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v49);
    if ( *(_QWORD *)pfContextAttr )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(pfContextAttr);
    if ( v50 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v50);
    return;
  }
  *(_QWORD *)v52 = 0;
  v46 = 0;
  if ( a4 )
    v14 = (char *)a4->pBuffers->pvBuffer;
  else
    v14 = 0;
  while ( 1 )
  {
    v54[0] = 0;
    v54[1] = 2;
    pvContextBuffer = 0;
    pOutput.ulVersion = 0;
    pOutput.cBuffers = 1;
    pOutput.pBuffers = (PSecBuffer)v54;
    pfContextAttr[0] = 0;
    v16 = InitializeSecurityContextW(
            (PCredHandle)((char *)this + 104),
            a2,
            0,
            0x819Cu,
            0,
            0,
            a4,
            0,
            phNewContext,
            &pOutput,
            pfContextAttr,
            0);
    v65[2] = v54;
    v66 = 1;
    if ( !v16 || (LOBYTE(v15) = 1, v16 == 590610) )
      LOBYTE(v15) = 0;
    winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(
      (winrt::Windows::Internal::Eap::Utility::implementation *)v16,
      v15,
      v17);
    if ( !v16 )
    {
      ContextAttributesW = QueryContextAttributesW((PCtxtHandle)((char *)this + 120), 0x5Au, (char *)this + 156);
      if ( ContextAttributesW < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x322,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
          (const char *)(unsigned int)ContextAttributesW,
          Reserved1a);
      v19 = QueryContextAttributesW((PCtxtHandle)((char *)this + 120), 4u, (char *)this + 136);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x323,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
          (const char *)(unsigned int)v19,
          Reserved1a);
      v20 = (const CERT_CONTEXT *)*((_QWORD *)this + 12);
      if ( v20 )
      {
        LastError = GetLastError();
        CertFreeCertificateContext(v20);
        SetLastError(LastError);
      }
      *((_QWORD *)this + 12) = 0;
      v22 = QueryContextAttributesW((PCtxtHandle)((char *)this + 120), 0x53u, (char *)this + 96);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x324,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
          (const char *)(unsigned int)v22,
          Reserved1a);
      v14 = 0;
    }
    if ( pvContextBuffer && v54[0] )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl) )
      {
        if ( v16 != 590610 && v16 )
          goto LABEL_55;
        if ( !pvContextBuffer && v54[0] )
          goto LABEL_114;
        v62[0] = v54[0];
        v62[1] = pvContextBuffer;
        v23 = (const void *const *)v62;
      }
      else
      {
        if ( v16 != 590610 && (*((_DWORD *)this + 39) & 0x3000) == 0 )
          goto LABEL_55;
        if ( !pvContextBuffer && v54[0] )
LABEL_114:
          gsl::details::terminate(0);
        v63[0] = v54[0];
        v63[1] = pvContextBuffer;
        v23 = (const void *const *)v63;
      }
      winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReallocateComPtrAndAppendData(
        (char *)v52,
        v23);
      v24 = 1;
      v46 = 1;
    }
    else
    {
      v24 = v46;
    }
    if ( v16 == 590610 )
    {
      if ( v14 && (v25 = a4->pBuffers, v25[1].BufferType == 5) )
      {
        v14 += v25->cbBuffer - (unsigned __int64)v25[1].cbBuffer;
        v25->pvBuffer = v14;
        a4->pBuffers->cbBuffer = a4->pBuffers[1].cbBuffer;
        a4->pBuffers->BufferType = 2;
        a4->pBuffers[1].pvBuffer = 0;
        a4->pBuffers[1].cbBuffer = 0;
        a4->pBuffers[1].BufferType = 0;
      }
      else
      {
        v14 = 0;
      }
      if ( v24 || (v26 = 1, v14) )
        v26 = 0;
      if ( v26 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x377,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
          (const char *)0x90090304LL,
          Reserved1a);
    }
LABEL_55:
    if ( !v14 && v46 )
    {
      v48 = 0;
      if ( *(_QWORD *)v52 )
      {
        v67 = 0;
        v68 = 0;
        v27 = (***(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))v52)(
                *(_QWORD *)v52,
                winrt::impl::guid_v<winrt::Windows::Storage::Streams::IBuffer>,
                &v48);
        if ( v27 < 0 )
          winrt::throw_hresult((unsigned int)v27, &v67);
      }
      winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsDataGeneratedEventArgs,winrt::Windows::Storage::Streams::IBuffer &>(
        &v50,
        &v48);
      v47 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(&v48);
      winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::TlsHandshakeDataGenerated<unsigned int>(&v47);
      winrt::Windows::Internal::Eap::Utility::implementation::inproc_error_propagating_event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>>::operator()<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>(
        (char *)this + 24,
        this,
        &v50);
      if ( v50 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v50);
      if ( v48 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v48);
    }
    if ( !v16 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl);
      v29 = (int *)((char *)this + 156);
      v30 = *((_DWORD *)this + 39) & 0x3000;
      if ( IsEnabled )
      {
        *((_DWORD *)this + 19) = 3;
        if ( v30
          && (*((_DWORD *)this + 18) == 2
           || winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::IsTlsSessionReconnect(this)) )
        {
          *((_DWORD *)this + 19) = 2;
        }
      }
      else
      {
        *((_DWORD *)this + 19) = 2;
        if ( !v30 || *((_DWORD *)this + 18) != 2 )
          *((_DWORD *)this + 19) = 3;
      }
      v47 = 1;
      v31 = a4->pBuffers;
      if ( v31[1].BufferType == 5 )
        cbBuffer = v31[1].cbBuffer;
      else
        cbBuffer = 0;
      v64[0] = 0;
      v64[1] = 0;
      winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(&v49, v64);
      if ( cbBuffer )
      {
        v34 = (char *)a4->pBuffers->pvBuffer + a4->pBuffers->cbBuffer - cbBuffer;
        if ( !v34 )
          gsl::details::terminate(v33);
        v65[0] = cbBuffer;
        v65[1] = v34;
        winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(&v58, v65);
        winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::DecryptData(
          (__int64)this,
          (__int64)&v57,
          (__int64)&v58);
        v35 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(&v57);
        v36 = v57;
        if ( *((_DWORD *)this + 19) == 2 )
        {
          if ( v35 )
            *((_DWORD *)this + 19) = 3;
        }
        else
        {
          if ( v49 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v49);
          v49 = v36;
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
        }
        if ( v36 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v57);
        if ( v58 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v58);
        v29 = (int *)((char *)this + 156);
      }
      if ( *((_DWORD *)this + 19) == 2 )
      {
        if ( !*(_QWORD *)v52 )
        {
          *((_DWORD *)this + 19) = 3;
          v47 = 2;
          goto LABEL_93;
        }
LABEL_97:
        v42 = (_DWORD *)*((_QWORD *)winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::Instance()
                        + 1);
        if ( *v42 > 4u )
          tlgWriteTransfer_EventWriteTransfer(v42, byte_18003AA61, 0, 0);
      }
      else
      {
        if ( *((_DWORD *)this + 19) != 3 )
          goto LABEL_97;
LABEL_93:
        v37 = winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation,winrt::Windows::Storage::Streams::IBuffer &,_SecPkgContext_StreamSizes &,unsigned long &>(
                &v59,
                &v49,
                (_DWORD *)this + 34,
                v29);
        winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs,enum winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus &,winrt::Windows::Internal::Eap::Utility::EapTlsConnectedPeerInformation>(
          &v53,
          (int *)&v47,
          v37);
        if ( v59 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v59);
        winrt::Windows::Internal::Eap::Utility::implementation::inproc_error_propagating_event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>>::operator()<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>(
          (char *)this + 48,
          this,
          &v53);
        v38 = *((_DWORD *)this + 36);
        v39 = *((_DWORD *)this + 35);
        v40 = *((_DWORD *)this + 34);
        v41 = winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::GetAlgString(this);
        LOBYTE(Reserved2) = cbBuffer != 0;
        winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::TlsHandshakeFinished(
          *((unsigned int *)this + 18),
          v47,
          *((unsigned int *)this + 39),
          v41,
          v40,
          v39,
          v38,
          Reserved2);
        if ( v53 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v53);
      }
      if ( v49 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v49);
    }
    v66 = 0;
    if ( pvContextBuffer )
      FreeContextBuffer(pvContextBuffer);
    if ( !v14 )
      break;
    a2 = v60;
    phNewContext = v61;
  }
  if ( *(_QWORD *)v52 )
    winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(v52);
}

```

## disassembly

```asm
0x180018e1c  push    rbp
0x180018e1e  push    rbx
0x180018e1f  push    rsi
0x180018e20  push    rdi
0x180018e21  push    r12
0x180018e23  push    r13
0x180018e25  push    r14
0x180018e27  push    r15
0x180018e29  lea     rbp, [rsp-78h]
0x180018e2e  sub     rsp, 178h
0x180018e35  mov     rax, cs:__security_cookie
0x180018e3c  xor     rax, rsp
0x180018e3f  mov     [rbp+0B0h+var_50], rax
0x180018e43  mov     r13, r9
0x180018e46  mov     [rbp+0B0h+var_D0], r8
0x180018e4a  mov     [rbp+0B0h+var_D8], rdx
0x180018e4e  mov     r14, rcx
0x180018e51  xor     esi, esi
0x180018e53  lea     r15d, [rsi+2]
0x180018e57  test    r9, r9
0x180018e5a  jz      short loc_180018E64
0x180018e5c  cmp     [r9+4], r15d
0x180018e60  mov     al, 1
0x180018e62  jnz     short loc_180018E67
0x180018e64  mov     al, sil
0x180018e67  mov     rcx, [rbp+0B8h]; this
0x180018e6e  test    al, al
0x180018e70  jnz     loc_1800195B7
0x180018e76  cmp     [r14+4Ch], r15d
0x180018e7a  jnz     loc_180018FDA
0x180018e80  mov     rax, [r9+8]
0x180018e84  mov     ecx, [rax]; this
0x180018e86  mov     rdx, [rax+8]
0x180018e8a  test    rdx, rdx
0x180018e8d  jnz     short loc_180018E98
0x180018e8f  test    rcx, rcx
0x180018e92  jnz     loc_1800195CF
0x180018e98  mov     qword ptr [rbp+0B0h+var_100.ulVersion], rcx
0x180018e9c  mov     [rbp+0B0h+var_100.pBuffers], rdx
0x180018ea0  lea     rdx, [rbp+0B0h+var_100]
0x180018ea4  lea     rcx, [rsp+1B0h+var_138]
0x180018ea9  call    ?CreateIBufferOverCallerManagedBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(gsl::span<uchar,-1>)
0x180018eae  nop
0x180018eaf  lea     r8, [rsp+1B0h+var_138]
0x180018eb4  lea     rdx, [rbp+0B0h+var_130]
0x180018eb8  mov     rcx, r14
0x180018ebb  call    ?DecryptData@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@QEAA?AUIBuffer@Streams@Storage@67@AEBU89Storage@67@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::DecryptData(winrt::Windows::Storage::Streams::IBuffer const &)
0x180018ec0  nop
0x180018ec1  mov     dword ptr [r14+4Ch], 3
0x180018ec9  lea     rcx, [rbp+0B0h+var_130]
0x180018ecd  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(void)
0x180018ed2  mov     ecx, esi
0x180018ed4  test    eax, eax
0x180018ed6  setz    cl
0x180018ed9  inc     ecx
0x180018edb  mov     [rsp+1B0h+var_14C], ecx
0x180018edf  mov     qword ptr [rbp+0B0h+var_100.ulVersion], rsi
0x180018ee3  mov     [rbp+0B0h+var_100.pBuffers], rsi
0x180018ee7  lea     rdx, [rbp+0B0h+var_100]
0x180018eeb  lea     rcx, [rsp+1B0h+var_140]
0x180018ef0  call    ?CreateIBufferOverCallerManagedBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(gsl::span<uchar,-1>)
0x180018ef5  nop
0x180018ef6  lea     r15, [r14+9Ch]
0x180018efd  lea     rsi, [r14+88h]
0x180018f04  mov     r9, r15
0x180018f07  mov     r8, rsi
0x180018f0a  lea     rdx, [rsp+1B0h+var_140]
0x180018f0f  lea     rcx, [rbp+0B0h+var_120]
0x180018f13  call    ??$make@UEapTlsConnectedPeerInformation@implementation@Utility@Eap@Internal@Windows@winrt@@AEAUIBuffer@Streams@Storage@67@AEAU_SecPkgContext_StreamSizes@@AEAK@winrt@@YA?A_PAEAUIBuffer@Streams@Storage@Windows@0@AEAU_SecPkgContext_StreamSizes@@AEAK@Z
0x180018f18  nop
0x180018f19  mov     r8, rax
0x180018f1c  lea     rdx, [rsp+1B0h+var_14C]
0x180018f21  lea     rcx, [rsp+1B0h+var_148]
0x180018f26  call    ??$make@UEapTlsHandshakeCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAW4EapTlsHandshakeStatus@34567@UEapTlsConnectedPeerInformation@34567@@winrt@@YA?A_PAEAW4EapTlsHandshakeStatus@Utility@Eap@Internal@Windows@0@$$QEAUEapTlsConnectedPeerInformation@23450@@Z
0x180018f2b  nop
0x180018f2c  xor     r12d, r12d
0x180018f2f  cmp     [rbp+0B0h+var_120], r12
0x180018f33  jz      short loc_180018F3E
0x180018f35  lea     rcx, [rbp+0B0h+var_120]
0x180018f39  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180018f3e  lea     rcx, [r14+30h]
0x180018f42  lea     r8, [rsp+1B0h+var_148]
0x180018f47  mov     rdx, r14
0x180018f4a  call    ??$?RUEapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UEapTlsDataGeneratedEventArgs@23456@@?$inproc_error_propagating_event@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsDataGeneratedEventArgs@23456@@Foundation@Windows@winrt@@@implementation@Utility@Eap@Internal@Windows@winrt@@QEAAXAEBUEapSchannelUtil@123456@AEBUEapTlsDataGeneratedEventArgs@23456@@Z; winrt::Windows::Internal::Eap::Utility::implementation::inproc_error_propagating_event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>>::operator()<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil const &,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs const &)
0x180018f4f  mov     ebx, [r14+90h]
0x180018f56  mov     edi, [r14+8Ch]
0x180018f5d  mov     esi, [rsi]
0x180018f5f  mov     rcx, r14; this
0x180018f62  call    ?GetAlgString@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEBAPEBGXZ; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::GetAlgString(void)
0x180018f67  mov     byte ptr [rsp+1B0h+Reserved2], r12b
0x180018f6c  mov     dword ptr [rsp+1B0h+pInput], ebx
0x180018f70  mov     [rsp+1B0h+TargetDataRep], edi
0x180018f74  mov     [rsp+1B0h+Reserved1], esi
0x180018f78  mov     r9, rax
0x180018f7b  mov     r8d, [r15]
0x180018f7e  mov     edx, [rsp+1B0h+var_14C]
0x180018f82  mov     ecx, [r14+48h]
0x180018f86  call    ?TlsHandshakeFinished@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAXW4EapMethodType@34567@W4EapTlsHandshakeStatus@34567@KQEBGKKK_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::TlsHandshakeFinished(winrt::Windows::Internal::Eap::Utility::EapMethodType,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus,ulong,ushort const * const,ulong,ulong,ulong,bool)
0x180018f8b  nop
0x180018f8c  cmp     [rsp+1B0h+var_148], r12
0x180018f91  jz      short loc_180018F9E
0x180018f93  lea     rcx, [rsp+1B0h+var_148]
0x180018f98  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180018f9d  nop
0x180018f9e  cmp     [rsp+1B0h+var_140], r12
0x180018fa3  jz      short loc_180018FB0
0x180018fa5  lea     rcx, [rsp+1B0h+var_140]
0x180018faa  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180018faf  nop
0x180018fb0  cmp     qword ptr [rbp+0B0h+var_130], r12
0x180018fb4  jz      short loc_180018FC0
0x180018fb6  lea     rcx, [rbp+0B0h+var_130]
0x180018fba  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180018fbf  nop
0x180018fc0  cmp     [rsp+1B0h+var_138], r12
0x180018fc5  jz      loc_180019591
0x180018fcb  lea     rcx, [rsp+1B0h+var_138]
0x180018fd0  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180018fd5  jmp     loc_180019591
0x180018fda  mov     qword ptr [rbp+0B0h+var_128], rsi
0x180018fde  mov     [rsp+1B0h+var_150], sil
0x180018fe3  test    r13, r13
0x180018fe6  jnz     short loc_180018FED
0x180018fe8  mov     r12, rsi
0x180018feb  jmp     short loc_180018FF5
0x180018fed  mov     rax, [r9+8]
0x180018ff1  mov     r12, [rax+8]
0x180018ff5  lea     rax, [r14+68h]
0x180018ff9  mov     [rbp+0B0h+var_118], esi
0x180018ffc  mov     [rbp+0B0h+var_114], r15d
0x180019000  mov     [rbp+0B0h+pvContextBuffer], rsi
0x180019004  mov     [rbp+0B0h+var_100.ulVersion], esi
0x180019007  mov     [rbp+0B0h+var_100.cBuffers], 1
0x18001900e  lea     rcx, [rbp+0B0h+var_118]
0x180019012  mov     [rbp+0B0h+var_100.pBuffers], rcx
0x180019016  mov     [rbp+0B0h+var_130], esi
0x180019019  mov     [rsp+1B0h+ptsExpiry], rsi; ptsExpiry
0x18001901e  lea     rcx, [rbp+0B0h+var_130]
0x180019022  mov     [rsp+1B0h+pfContextAttr], rcx; pfContextAttr
0x180019027  lea     rcx, [rbp+0B0h+var_100]
0x18001902b  mov     [rsp+1B0h+pOutput], rcx; pOutput
0x180019030  mov     [rsp+1B0h+phNewContext], r8; phNewContext
0x180019035  mov     [rsp+1B0h+Reserved2], esi; Reserved2
0x180019039  mov     [rsp+1B0h+pInput], r13; pInput
0x18001903e  mov     [rsp+1B0h+TargetDataRep], esi; TargetDataRep
0x180019042  mov     [rsp+1B0h+Reserved1], esi; int
0x180019046  mov     r9d, 819Ch; fContextReq
0x18001904c  xor     r8d, r8d; pszTargetName
0x18001904f  mov     rcx, rax; phCredential
0x180019052  call    cs:__imp_InitializeSecurityContextW
0x180019058  mov     edi, eax
0x18001905a  lea     rax, [rbp+0B0h+var_118]
0x18001905e  mov     [rbp+0B0h+var_80], rax
0x180019062  mov     [rbp+0B0h+var_78], 1
0x180019066  test    edi, edi
0x180019068  jz      short loc_180019074
0x18001906a  cmp     edi, 90312h
0x180019070  mov     dl, 1
0x180019072  jnz     short loc_180019077
0x180019074  mov     dl, sil; int
0x180019077  mov     ecx, edi; this
0x180019079  call    ?ThrowSecurityStatusIf@implementation@Utility@Eap@Internal@Windows@winrt@@YAXJ_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(long,bool)
0x18001907e  test    edi, edi
0x180019080  jnz     loc_180019123
0x180019086  lea     r12, [r14+78h]
0x18001908a  lea     r8, [r14+9Ch]; pBuffer
0x180019091  lea     edx, [rdi+5Ah]; ulAttribute
0x180019094  mov     rcx, r12; phContext
0x180019097  call    cs:__imp_QueryContextAttributesW
0x18001909d  mov     rcx, [rbp+0B8h]; this
0x1800190a4  test    eax, eax
0x1800190a6  js      loc_1800195FF
0x1800190ac  lea     r8, [r14+88h]; pBuffer
0x1800190b3  lea     edx, [rdi+4]; ulAttribute
0x1800190b6  mov     rcx, r12; phContext
0x1800190b9  call    cs:__imp_QueryContextAttributesW
0x1800190bf  mov     rcx, [rbp+0B8h]; this
0x1800190c6  test    eax, eax
0x1800190c8  js      loc_1800195EA
0x1800190ce  lea     rsi, [r14+60h]
0x1800190d2  mov     r15, [rsi]
0x1800190d5  test    r15, r15
0x1800190d8  jz      short loc_1800190F3
0x1800190da  call    cs:__imp_GetLastError
0x1800190e0  mov     ebx, eax
0x1800190e2  mov     rcx, r15; pCertContext
0x1800190e5  call    cs:__imp_CertFreeCertificateContext
0x1800190eb  mov     ecx, ebx; dwErrCode
0x1800190ed  call    cs:__imp_SetLastError
0x1800190f3  mov     qword ptr [rsi], 0
0x1800190fa  mov     r8, rsi; pBuffer
0x1800190fd  mov     edx, 53h ; 'S'; ulAttribute
0x180019102  mov     rcx, r12; phContext
0x180019105  call    cs:__imp_QueryContextAttributesW
0x18001910b  mov     rcx, [rbp+0B8h]; this
0x180019112  xor     esi, esi
0x180019114  test    eax, eax
0x180019116  js      loc_1800195D5
0x18001911c  mov     r12d, esi
0x18001911f  lea     r15d, [rsi+2]
0x180019123  cmp     [rbp+0B0h+pvContextBuffer], rsi
0x180019127  jz      loc_1800191C6
0x18001912d  cmp     [rbp+0B0h+var_118], esi
0x180019130  jz      loc_1800191C6
0x180019136  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x18001913d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x180019142  test    al, al
0x180019144  jz      short loc_18001918A
0x180019146  cmp     edi, 90312h
0x18001914c  jz      short loc_180019156
0x18001914e  test    edi, edi
0x180019150  jnz     loc_18001923B
0x180019156  mov     eax, [rbp+0B0h+var_118]
0x180019159  mov     rcx, [rbp+0B0h+pvContextBuffer]; this
0x18001915d  test    rcx, rcx
0x180019160  jnz     short loc_18001916B
0x180019162  test    rax, rax
0x180019165  jnz     loc_180019614
0x18001916b  mov     [rbp+0B0h+var_C0], rax
0x18001916f  mov     [rbp+0B0h+var_B8], rcx
0x180019173  lea     rdx, [rbp+0B0h+var_C0]
0x180019177  lea     rcx, [rbp+0B0h+var_128]; int
0x18001917b  call    ?ReallocateComPtrAndAppendData@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@CAXAEAU?$com_ptr@UIBuffer@Streams@Storage@Windows@@@7@V?$span@$$CBE$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReallocateComPtrAndAppendData(winrt::com_ptr<Windows::Storage::Streams::IBuffer> &,gsl::span<uchar const,-1>)
0x180019180  mov     r8b, 1
0x180019183  mov     [rsp+1B0h+var_150], r8b
0x180019188  jmp     short loc_1800191CB
0x18001918a  cmp     edi, 90312h
0x180019190  jz      short loc_1800191A3
0x180019192  test    dword ptr [r14+9Ch], 3000h
0x18001919d  jz      loc_18001923B
0x1800191a3  mov     eax, [rbp+0B0h+var_118]
0x1800191a6  mov     rcx, [rbp+0B0h+pvContextBuffer]
0x1800191aa  test    rcx, rcx
0x1800191ad  jnz     short loc_1800191B8
0x1800191af  test    rax, rax
0x1800191b2  jnz     loc_180019614
0x1800191b8  mov     [rbp+0B0h+var_B0], rax
0x1800191bc  mov     [rbp+0B0h+var_A8], rcx
0x1800191c0  lea     rdx, [rbp+0B0h+var_B0]
0x1800191c4  jmp     short loc_180019177
0x1800191c6  mov     r8b, [rsp+1B0h+var_150]
0x1800191cb  cmp     edi, 90312h
0x1800191d1  jnz     short loc_18001923B
0x1800191d3  test    r12, r12
0x1800191d6  jz      short loc_18001921A
0x1800191d8  mov     rdx, [r13+8]
0x1800191dc  cmp     dword ptr [rdx+14h], 5
0x1800191e0  jnz     short loc_18001921A
0x1800191e2  mov     eax, [rdx+10h]
0x1800191e5  mov     ecx, [rdx]
0x1800191e7  sub     rcx, rax
0x1800191ea  add     r12, rcx
0x1800191ed  mov     [rdx+8], r12
0x1800191f1  mov     rcx, [r13+8]
0x1800191f5  mov     eax, [rcx+10h]
0x1800191f8  mov     [rcx], eax
0x1800191fa  mov     rax, [r13+8]
0x1800191fe  mov     [rax+4], r15d
0x180019202  mov     rax, [r13+8]
0x180019206  mov     [rax+18h], rsi
0x18001920a  mov     rax, [r13+8]
0x18001920e  mov     [rax+10h], esi
0x180019211  mov     rax, [r13+8]
0x180019215  mov     [rax+14h], esi
0x180019218  jmp     short loc_18001921D
0x18001921a  mov     r12, rsi
0x18001921d  test    r8b, r8b
0x180019220  jnz     short loc_180019229
0x180019222  test    r12, r12
0x180019225  mov     al, 1
0x180019227  jz      short loc_18001922C
0x180019229  mov     al, sil
0x18001922c  mov     rcx, [rbp+0B8h]; this
0x180019233  test    al, al
0x180019235  jnz     loc_18001961A
0x18001923b  test    r12, r12
0x18001923e  jnz     loc_1800192EE
0x180019244  cmp     [rsp+1B0h+var_150], sil
0x180019249  jz      loc_1800192EE
0x18001924f  mov     rcx, qword ptr [rbp+0B0h+var_128]
0x180019253  mov     [rsp+1B0h+var_148], rsi
0x180019258  test    rcx, rcx
0x18001925b  jz      short loc_180019291
0x18001925d  mov     [rbp+0B0h+var_70], esi
0x180019260  xorps   xmm0, xmm0
0x180019263  movdqu  [rbp+0B0h+var_68], xmm0
0x180019268  mov     rax, [rcx]
0x18001926b  lea     r8, [rsp+1B0h+var_148]
0x180019270  lea     rdx, ??$guid_v@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IBuffer>
0x180019277  mov     rax, [rax]
0x18001927a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001927f  test    eax, eax
0x180019281  js      loc_180019632
0x180019287  mov     rax, [rsp+1B0h+var_148]
0x18001928c  mov     [rsp+1B0h+var_148], rax
0x180019291  lea     rdx, [rsp+1B0h+var_148]
0x180019296  lea     rcx, [rsp+1B0h+var_138]
0x18001929b  call    ??$make@UEapTlsDataGeneratedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAUIBuffer@Streams@Storage@67@@winrt@@YA?A_PAEAUIBuffer@Streams@Storage@Windows@0@@Z
0x1800192a0  nop
0x1800192a1  lea     rcx, [rsp+1B0h+var_148]
  ... truncated ...
```

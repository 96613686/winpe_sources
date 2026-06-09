# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ContinueTlsHandshakeNew(winrt::Windows::Storage::Streams::IBuffer const &)

- ea: `0x180019794`
- end: `0x180019bfc`
- name: `?ContinueTlsHandshakeNew@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBUIBuffer@Streams@Storage@67@@Z`
- size: `1128`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *__hidden this, const struct winrt::Windows::Storage::Streams::IBuffer *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180019650`

## callees

- `0x18000163c`
- `0x1800021d0`
- `0x180005efc`
- `0x1800083ec`
- `0x180008d90`
- `0x1800101c4`
- `0x180010df0`
- `0x180013ae0`
- `0x1800144b4`
- `0x18001767c`
- `0x180018d5c`
- `0x180019794`
- `0x18001ccc4`
- `0x18001cd3c`
- `0x18001e330`
- `0x18001e42c`
- `0x18002de70`
- `0x18002e598`
- `0x18002e5f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001998d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001998d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001997a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001997a`
- `SspiCli!FreeContextBuffer` at `0x180019ad2`
- `SspiCli!FreeContextBuffer` at `0x180019ad2`
- `SspiCli!InitializeSecurityContextW` at `0x1800198eb`
- `SspiCli!InitializeSecurityContextW` at `0x1800198eb`
- `SspiCli!QueryContextAttributesW` at `0x18001993a`
- `SspiCli!QueryContextAttributesW` at `0x18001995c`
- `SspiCli!QueryContextAttributesW` at `0x1800199ac`
- `SspiCli!QueryContextAttributesW` at `0x18001993a`
- `SspiCli!QueryContextAttributesW` at `0x18001995c`
- `SspiCli!QueryContextAttributesW` at `0x1800199ac`
- `CRYPT32!CertFreeCertificateContext` at `0x180019985`
- `CRYPT32!CertFreeCertificateContext` at `0x180019985`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ContinueTlsHandshakeNew(
        winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *this,
        const struct winrt::Windows::Storage::Streams::IBuffer *a2)
{
  char v4; // r15
  bool v5; // bl
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r13
  int v8; // edx
  bool v9; // r8
  unsigned int v10; // r12d
  _DWORD *v11; // rbx
  SECURITY_STATUS ContextAttributesW; // eax
  SECURITY_STATUS v13; // eax
  const CERT_CONTEXT *v14; // r12
  DWORD LastError; // ebx
  SECURITY_STATUS v16; // eax
  wil::details::in1diag3 *v17; // rcx
  PVOID v18; // rcx
  int Reserved1; // [rsp+20h] [rbp-E0h]
  unsigned int pfContextAttr; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v22[2]; // [rsp+70h] [rbp-90h] BYREF
  PVOID pvContextBuffer; // [rsp+78h] [rbp-88h]
  __int128 v24; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h]
  _DWORD v26[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  struct _SecBufferDesc pOutput; // [rsp+B8h] [rbp-48h] BYREF
  struct _SecBufferDesc pInput; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v32[3]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v33[3]; // [rsp+F0h] [rbp-10h] BYREF
  char v34; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( !*((_DWORD *)this + 19) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)0x139F,
      Reserved1);
  if ( !(unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(a2) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24A,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)0x80070057LL,
      Reserved1);
  pfContextAttr = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(a2);
  winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::ReceivedHandshakeMessageFromServer<unsigned int>(&pfContextAttr);
  v24 = 0;
  v25 = 0;
  v4 = 1;
  if ( *((_DWORD *)this + 19) != 1 )
  {
    winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::CheckEncryptedApplicationData(this, a2);
    if ( *((_DWORD *)this + 19) == 3 )
      goto LABEL_44;
    *((_DWORD *)this + 19) = 3;
    goto LABEL_43;
  }
  v5 = 0;
  winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(v32, a2);
  v6 = 0;
  v7 = v32[0];
  if ( v32[0] )
  {
    do
    {
      v26[0] = v7 - v6;
      v26[1] = 2;
      v27 = v6 + v32[1];
      v28 = 0;
      v29 = 0;
      pInput.ulVersion = 0;
      pInput.cBuffers = 2;
      pInput.pBuffers = (PSecBuffer)v26;
      v22[0] = 0;
      v22[1] = 2;
      pvContextBuffer = 0;
      pOutput.ulVersion = 0;
      pOutput.cBuffers = 1;
      pOutput.pBuffers = (PSecBuffer)v22;
      pfContextAttr = 0;
      v10 = InitializeSecurityContextW(
              (PCredHandle)((char *)this + 104),
              (PCtxtHandle)((char *)this + 120),
              0,
              0x819Cu,
              0,
              0,
              &pInput,
              0,
              (PCtxtHandle)((char *)this + 120),
              &pOutput,
              &pfContextAttr,
              0);
      v33[2] = v22;
      v34 = 1;
      if ( !v10 || v10 == 590610 )
        v8 = 0;
      else
        LOBYTE(v8) = 1;
      winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(
        (winrt::Windows::Internal::Eap::Utility::implementation *)v10,
        v8,
        v9);
      if ( v10 )
      {
        if ( v10 == 590610 )
        {
          v6 = v7;
          if ( HIDWORD(v28) == 5 )
            v6 = v7 - (unsigned int)v28;
        }
      }
      else
      {
        v11 = (_DWORD *)((char *)this + 156);
        ContextAttributesW = QueryContextAttributesW((PCtxtHandle)((char *)this + 120), 0x5Au, (char *)this + 156);
        if ( ContextAttributesW < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x22F,
            (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
            (const char *)(unsigned int)ContextAttributesW,
            Reserved1);
        v13 = QueryContextAttributesW((PCtxtHandle)((char *)this + 120), 4u, (char *)this + 136);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x230,
            (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
            (const char *)(unsigned int)v13,
            Reserved1);
        v14 = (const CERT_CONTEXT *)*((_QWORD *)this + 12);
        if ( v14 )
        {
          LastError = GetLastError();
          CertFreeCertificateContext(v14);
          SetLastError(LastError);
          v11 = (_DWORD *)((char *)this + 156);
        }
        *((_QWORD *)this + 12) = 0;
        v16 = QueryContextAttributesW((PCtxtHandle)((char *)this + 120), 0x53u, (char *)this + 96);
        v17 = retaddr;
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x231,
            (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
            (const char *)(unsigned int)v16,
            Reserved1);
        *((_DWORD *)this + 19) = 3;
        *((_DWORD *)this + 22) = 1;
        if ( (*v11 & 0x3000) != 0
          && (winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::IsTlsSessionReconnect(this)
           || *((_DWORD *)this + 18) == 2) )
        {
          *((_DWORD *)this + 19) = 2;
          *((_DWORD *)this + 22) = 2;
          v17 = (wil::details::in1diag3 *)*((_QWORD *)winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::Instance()
                                          + 1);
          if ( *(_DWORD *)v17 > 4u )
          {
            Reserved1 = 2;
            tlgWriteTransfer_EventWriteTransfer(v17, byte_18003AA61, 0, 0);
          }
        }
        if ( HIDWORD(v28) == 5 && (_DWORD)v28 )
        {
          if ( !(v27 + v26[0] - (unsigned __int64)(unsigned int)v28) )
            gsl::details::terminate(v17);
          v33[0] = (unsigned int)v28;
          v33[1] = v27 + v26[0] - (unsigned __int64)(unsigned int)v28;
          winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(&v21, (unsigned int *)v33);
          winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::CheckEncryptedApplicationData(
            this,
            (const struct winrt::Windows::Storage::Streams::IBuffer *)&v21);
          *((_DWORD *)this + 19) = 3;
          if ( v21 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v21);
        }
        v6 = v7;
        v5 = *((_DWORD *)this + 19) == 3;
      }
      v18 = pvContextBuffer;
      if ( pvContextBuffer && v22[0] )
      {
        std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
          &v24,
          *((_QWORD *)&v24 + 1),
          pvContextBuffer,
          v22[0]);
        v18 = pvContextBuffer;
      }
      v34 = 0;
      if ( v18 )
        FreeContextBuffer(v18);
    }
    while ( v6 < v7 );
    if ( v5 )
      goto LABEL_37;
  }
  if ( *((_QWORD *)&v24 + 1) != (_QWORD)v24 )
LABEL_37:
    v4 = 0;
  if ( v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)0x83760002LL,
      Reserved1);
  if ( v5 )
LABEL_43:
    winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TlsHandshakeCompleted(this);
LABEL_44:
  if ( *((_QWORD *)&v24 + 1) != (_QWORD)v24 )
    winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TlsHandshakeDataGenerated(this, &v24);
  std::vector<unsigned char>::~vector<unsigned char>(&v24);
}

```

## disassembly

```asm
0x180019794  mov     [rsp-8+arg_10], rbx
0x180019799  push    rbp
0x18001979a  push    rsi
0x18001979b  push    rdi
0x18001979c  push    r12
0x18001979e  push    r13
0x1800197a0  push    r14
0x1800197a2  push    r15
0x1800197a4  lea     rbp, [rsp-40h]
0x1800197a9  sub     rsp, 140h
0x1800197b0  mov     rax, cs:__security_cookie
0x1800197b7  xor     rax, rsp
0x1800197ba  mov     [rbp+70h+var_40], rax
0x1800197be  mov     rsi, rdx
0x1800197c1  mov     rdi, rcx
0x1800197c4  mov     rcx, [rbp+78h]; this
0x1800197c8  xor     r12d, r12d
0x1800197cb  cmp     [rdi+4Ch], r12d
0x1800197cf  jz      loc_180019B81
0x1800197d5  mov     rbx, [rbp+78h]
0x1800197d9  mov     rcx, rdx
0x1800197dc  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(void)
0x1800197e1  test    eax, eax
0x1800197e3  jz      loc_180019B99
0x1800197e9  mov     rcx, rsi
0x1800197ec  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(void)
0x1800197f1  mov     [rsp+170h+var_110], eax
0x1800197f5  lea     rcx, [rsp+170h+var_110]
0x1800197fa  call    ??$ReceivedHandshakeMessageFromServer@I@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAX$$QEAI@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::ReceivedHandshakeMessageFromServer<uint>(uint &&)
0x1800197ff  xorps   xmm0, xmm0
0x180019802  movdqu  [rbp+70h+var_F0], xmm0
0x180019807  mov     [rbp+70h+var_E0], r12
0x18001980b  lea     r15d, [r12+1]
0x180019810  mov     rdx, rsi; struct winrt::Windows::Storage::Streams::IBuffer *
0x180019813  cmp     [rdi+4Ch], r15d
0x180019817  jnz     loc_180019B05
0x18001981d  mov     bl, r12b
0x180019820  lea     rcx, [rbp+70h+var_98]
0x180019824  call    ?GetBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AV?$span@$$CBE$0?0@gsl@@AEBUIBuffer@Streams@Storage@56@@Z; winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(winrt::Windows::Storage::Streams::IBuffer const &)
0x180019829  mov     esi, r12d
0x18001982c  mov     r13, [rbp+70h+var_98]
0x180019830  test    r13, r13
0x180019833  jz      loc_180019AE5
0x180019839  lea     r14d, [r12+3]
0x18001983e  lea     r10, [rdi+68h]
0x180019842  lea     rcx, [rdi+78h]
0x180019846  mov     eax, r13d
0x180019849  sub     eax, esi
0x18001984b  mov     [rbp+70h+var_D8], eax
0x18001984e  mov     [rbp+70h+var_D4], 2
0x180019855  mov     rax, [rbp+70h+var_90]
0x180019859  add     rax, rsi
0x18001985c  mov     [rbp+70h+var_D0], rax
0x180019860  mov     [rbp+70h+var_C8], 0
0x180019868  mov     [rbp+70h+var_C0], r12
0x18001986c  mov     [rbp+70h+var_A8.ulVersion], r12d
0x180019870  mov     [rbp+70h+var_A8.cBuffers], 2
0x180019877  lea     rax, [rbp+70h+var_D8]
0x18001987b  mov     [rbp+70h+var_A8.pBuffers], rax
0x18001987f  mov     [rsp+170h+var_100], r12d
0x180019884  mov     [rsp+170h+var_FC], 2
0x18001988c  mov     [rsp+170h+pvContextBuffer], r12
0x180019891  mov     [rbp+70h+var_B8.ulVersion], r12d
0x180019895  mov     [rbp+70h+var_B8.cBuffers], r15d
0x180019899  lea     rax, [rsp+170h+var_100]
0x18001989e  mov     [rbp+70h+var_B8.pBuffers], rax
0x1800198a2  mov     [rsp+170h+var_110], r12d
0x1800198a7  mov     [rsp+170h+ptsExpiry], r12; ptsExpiry
0x1800198ac  lea     rax, [rsp+170h+var_110]
0x1800198b1  mov     [rsp+170h+pfContextAttr], rax; pfContextAttr
0x1800198b6  lea     rax, [rbp+70h+var_B8]
0x1800198ba  mov     [rsp+170h+pOutput], rax; pOutput
0x1800198bf  mov     [rsp+170h+phNewContext], rcx; phNewContext
0x1800198c4  mov     [rsp+170h+Reserved2], r12d; Reserved2
0x1800198c9  lea     rax, [rbp+70h+var_A8]
0x1800198cd  mov     [rsp+170h+pInput], rax; pInput
0x1800198d2  mov     [rsp+170h+TargetDataRep], r12d; TargetDataRep
0x1800198d7  mov     [rsp+170h+Reserved1], r12d; int
0x1800198dc  mov     r9d, 819Ch; fContextReq
0x1800198e2  xor     r8d, r8d; pszTargetName
0x1800198e5  mov     rdx, rcx; phContext
0x1800198e8  mov     rcx, r10; phCredential
0x1800198eb  call    cs:__imp_InitializeSecurityContextW
0x1800198f1  mov     r12d, eax
0x1800198f4  lea     rax, [rsp+170h+var_100]
0x1800198f9  mov     [rbp+70h+var_70], rax
0x1800198fd  mov     [rbp+70h+var_68], r15b
0x180019901  test    r12d, r12d
0x180019904  jz      short loc_180019914
0x180019906  cmp     r12d, 90312h
0x18001990d  jz      short loc_180019914
0x18001990f  mov     dl, r15b
0x180019912  jmp     short loc_180019916
0x180019914  xor     edx, edx; int
0x180019916  mov     ecx, r12d; this
0x180019919  call    ?ThrowSecurityStatusIf@implementation@Utility@Eap@Internal@Windows@winrt@@YAXJ_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(long,bool)
0x18001991e  test    r12d, r12d
0x180019921  jnz     loc_180019A84
0x180019927  lea     rbx, [rdi+9Ch]
0x18001992e  mov     r8, rbx; pBuffer
0x180019931  lea     edx, [r12+5Ah]; ulAttribute
0x180019936  lea     rcx, [rdi+78h]; phContext
0x18001993a  call    cs:__imp_QueryContextAttributesW
0x180019940  mov     rcx, [rbp+78h]; this
0x180019944  test    eax, eax
0x180019946  js      loc_180019B6C
0x18001994c  lea     r8, [rdi+88h]; pBuffer
0x180019953  lea     edx, [r12+4]; ulAttribute
0x180019958  lea     rcx, [rdi+78h]; phContext
0x18001995c  call    cs:__imp_QueryContextAttributesW
0x180019962  mov     rcx, [rbp+78h]; this
0x180019966  test    eax, eax
0x180019968  js      loc_180019BE7
0x18001996e  lea     rsi, [rdi+60h]
0x180019972  mov     r12, [rsi]
0x180019975  test    r12, r12
0x180019978  jz      short loc_18001999A
0x18001997a  call    cs:__imp_GetLastError
0x180019980  mov     ebx, eax
0x180019982  mov     rcx, r12; pCertContext
0x180019985  call    cs:__imp_CertFreeCertificateContext
0x18001998b  mov     ecx, ebx; dwErrCode
0x18001998d  call    cs:__imp_SetLastError
0x180019993  lea     rbx, [rdi+9Ch]
0x18001999a  xor     r12d, r12d
0x18001999d  mov     [rsi], r12
0x1800199a0  mov     r8, rsi; pBuffer
0x1800199a3  lea     edx, [r12+53h]; ulAttribute
0x1800199a8  lea     rcx, [rdi+78h]; phContext
0x1800199ac  call    cs:__imp_QueryContextAttributesW
0x1800199b2  mov     rcx, [rbp+78h]; this
0x1800199b6  test    eax, eax
0x1800199b8  js      loc_180019BD2
0x1800199be  mov     [rdi+4Ch], r14d
0x1800199c2  mov     [rdi+58h], r15d
0x1800199c6  test    dword ptr [rbx], 3000h
0x1800199cc  jz      short loc_180019A21
0x1800199ce  mov     rcx, rdi; this
0x1800199d1  call    ?IsTlsSessionReconnect@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@QEAA_NXZ; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::IsTlsSessionReconnect(void)
0x1800199d6  test    al, al
0x1800199d8  jnz     short loc_1800199E0
0x1800199da  cmp     dword ptr [rdi+48h], 2
0x1800199de  jnz     short loc_180019A21
0x1800199e0  mov     dword ptr [rdi+4Ch], 2
0x1800199e7  mov     dword ptr [rdi+58h], 2
0x1800199ee  call    ?Instance@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@KAPEAV1234567@XZ; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::Instance(void)
0x1800199f3  mov     rcx, [rax+8]
0x1800199f7  mov     eax, [rcx]
0x1800199f9  cmp     eax, 4
0x1800199fc  jbe     short loc_180019A21
0x1800199fe  lea     rax, [rbp+70h+var_60]
0x180019a02  mov     qword ptr [rsp+170h+TargetDataRep], rax
0x180019a07  mov     [rsp+170h+Reserved1], 2
0x180019a0f  xor     r9d, r9d
0x180019a12  xor     r8d, r8d
0x180019a15  lea     rdx, byte_18003AA61
0x180019a1c  call    _tlgWriteTransfer_EventWriteTransfer
0x180019a21  cmp     dword ptr [rbp+70h+var_C8+4], 5
0x180019a25  jnz     short loc_180019A78
0x180019a27  mov     eax, dword ptr [rbp+70h+var_C8]
0x180019a2a  test    eax, eax
0x180019a2c  jz      short loc_180019A78
0x180019a2e  mov     r8d, [rbp+70h+var_D8]
0x180019a32  sub     r8, rax
0x180019a35  add     r8, [rbp+70h+var_D0]
0x180019a39  jz      loc_180019BCC
0x180019a3f  mov     [rbp+70h+var_80], rax
0x180019a43  mov     [rbp+70h+var_78], r8
0x180019a47  lea     rdx, [rbp+70h+var_80]
0x180019a4b  lea     rcx, [rsp+170h+var_108]
0x180019a50  call    ?AllocateIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(gsl::span<uchar,-1>)
0x180019a55  nop
0x180019a56  lea     rdx, [rsp+170h+var_108]; struct winrt::Windows::Storage::Streams::IBuffer *
0x180019a5b  mov     rcx, rdi; this
0x180019a5e  call    ?CheckEncryptedApplicationData@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBUIBuffer@Streams@Storage@67@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::CheckEncryptedApplicationData(winrt::Windows::Storage::Streams::IBuffer const &)
0x180019a63  mov     [rdi+4Ch], r14d
0x180019a67  cmp     [rsp+170h+var_108], r12
0x180019a6c  jz      short loc_180019A78
0x180019a6e  lea     rcx, [rsp+170h+var_108]
0x180019a73  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180019a78  mov     rsi, r13
0x180019a7b  cmp     [rdi+4Ch], r14d
0x180019a7f  setz    bl
0x180019a82  jmp     short loc_180019A9F
0x180019a84  cmp     r12d, 90312h
0x180019a8b  jnz     short loc_180019A9C
0x180019a8d  mov     rsi, r13
0x180019a90  cmp     dword ptr [rbp+70h+var_C8+4], 5
0x180019a94  jnz     short loc_180019A9C
0x180019a96  mov     eax, dword ptr [rbp+70h+var_C8]
0x180019a99  sub     rsi, rax
0x180019a9c  xor     r12d, r12d
0x180019a9f  mov     rcx, [rsp+170h+pvContextBuffer]
0x180019aa4  test    rcx, rcx
0x180019aa7  jz      short loc_180019AC9
0x180019aa9  mov     eax, [rsp+170h+var_100]
0x180019aad  test    eax, eax
0x180019aaf  jz      short loc_180019AC9
0x180019ab1  mov     r9d, eax
0x180019ab4  mov     r8, rcx
0x180019ab7  mov     rdx, qword ptr [rbp+70h+var_F0+8]
0x180019abb  lea     rcx, [rbp+70h+var_F0]
0x180019abf  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x180019ac4  mov     rcx, [rsp+170h+pvContextBuffer]; pvContextBuffer
0x180019ac9  mov     [rbp+70h+var_68], r12b
0x180019acd  test    rcx, rcx
0x180019ad0  jz      short loc_180019AD8
0x180019ad2  call    cs:__imp_FreeContextBuffer
0x180019ad8  cmp     rsi, r13
0x180019adb  jb      loc_18001983E
0x180019ae1  test    bl, bl
0x180019ae3  jnz     short loc_180019AEF
0x180019ae5  mov     rax, qword ptr [rbp+70h+var_F0+8]
0x180019ae9  cmp     rax, qword ptr [rbp+70h+var_F0]
0x180019aed  jz      short loc_180019AF2
0x180019aef  mov     r15b, r12b
0x180019af2  mov     rcx, [rbp+78h]; this
0x180019af6  test    r15b, r15b
0x180019af9  jnz     loc_180019BB4
0x180019aff  test    bl, bl
0x180019b01  jz      short loc_180019B25
0x180019b03  jmp     short loc_180019B1D
0x180019b05  mov     rcx, rdi; this
0x180019b08  call    ?CheckEncryptedApplicationData@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBUIBuffer@Streams@Storage@67@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::CheckEncryptedApplicationData(winrt::Windows::Storage::Streams::IBuffer const &)
0x180019b0d  mov     r14d, 3
0x180019b13  cmp     [rdi+4Ch], r14d
0x180019b17  jz      short loc_180019B25
0x180019b19  mov     [rdi+4Ch], r14d
0x180019b1d  mov     rcx, rdi; this
0x180019b20  call    ?TlsHandshakeCompleted@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TlsHandshakeCompleted(void)
0x180019b25  mov     rax, qword ptr [rbp+70h+var_F0+8]
0x180019b29  cmp     rax, qword ptr [rbp+70h+var_F0]
0x180019b2d  jz      short loc_180019B3C
0x180019b2f  lea     rdx, [rbp+70h+var_F0]
0x180019b33  mov     rcx, rdi
0x180019b36  call    ?TlsHandshakeDataGenerated@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TlsHandshakeDataGenerated(std::vector<uchar> const &)
0x180019b3b  nop
0x180019b3c  lea     rcx, [rbp+70h+var_F0]
0x180019b40  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180019b45  mov     rcx, [rbp+70h+var_40]
0x180019b49  xor     rcx, rsp; StackCookie
0x180019b4c  call    __security_check_cookie
0x180019b51  mov     rbx, [rsp+170h+arg_10]
0x180019b59  add     rsp, 140h
0x180019b60  pop     r15
0x180019b62  pop     r14
0x180019b64  pop     r13
0x180019b66  pop     r12
0x180019b68  pop     rdi
0x180019b69  pop     rsi
0x180019b6a  pop     rbp
0x180019b6b  retn
0x180019b6c  mov     r9d, eax; char *
0x180019b6f  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180019b76  mov     edx, 22Fh; void *
0x180019b7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019b81  mov     r9d, 139Fh; char *
0x180019b87  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180019b8e  mov     edx, 249h; void *
0x180019b93  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180019b99  mov     r9d, 80070057h; char *
0x180019b9f  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180019ba6  mov     edx, 24Ah; void *
0x180019bab  mov     rcx, rbx; this
0x180019bae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019bb4  mov     r9d, 83760002h; char *
0x180019bba  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180019bc1  mov     edx, 2A3h; void *
0x180019bc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019bcc  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x180019bd2  mov     r9d, eax; char *
0x180019bd5  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180019bdc  mov     edx, 231h; void *
0x180019be1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019be7  mov     r9d, eax; char *
0x180019bea  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180019bf1  mov     edx, 230h; void *
0x180019bf6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

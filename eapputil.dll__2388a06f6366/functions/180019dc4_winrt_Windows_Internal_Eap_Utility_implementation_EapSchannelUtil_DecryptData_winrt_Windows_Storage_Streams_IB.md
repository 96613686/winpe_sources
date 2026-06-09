# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::DecryptData(winrt::Windows::Storage::Streams::IBuffer const &)

- ea: `0x180019dc4`
- end: `0x18001a179`
- name: `?DecryptData@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@QEAA?AUIBuffer@Streams@Storage@67@AEBU89Storage@67@@Z`
- size: `949`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180018d5c`
- `0x180018e1c`
- `0x180019d60`

## callees

- `0x18000163c`
- `0x1800021d0`
- `0x180005efc`
- `0x1800101c4`
- `0x180010df0`
- `0x180019dc4`
- `0x18001d6d0`
- `0x18001e190`
- `0x180024f14`
- `0x18002e598`
- `0x18002e5f4`

## import_xrefs

- `SspiCli!FreeContextBuffer` at `0x180019fe8`
- `SspiCli!FreeContextBuffer` at `0x18001a120`
- `SspiCli!FreeContextBuffer` at `0x180019fe8`
- `SspiCli!FreeContextBuffer` at `0x18001a120`
- `SspiCli!InitializeSecurityContextW` at `0x180019f47`
- `SspiCli!InitializeSecurityContextW` at `0x180019f47`
- `SspiCli!DecryptMessage` at `0x180019e65`
- `SspiCli!DecryptMessage` at `0x180019e65`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::DecryptData(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  PSecBuffer pBuffers; // rdi
  __int64 cbBuffer; // rbx
  unsigned int v7; // eax
  struct _SecBuffer *v8; // rcx
  int v9; // ecx
  struct _SecBuffer *v10; // rdx
  unsigned int v11; // eax
  int v12; // edx
  bool v13; // r8
  char v14; // al
  gsl::details *v15; // rcx
  const char *v16; // r9
  int v17; // edx
  unsigned int Reserved1; // [rsp+20h] [rbp-E0h]
  int v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _SecBufferDesc pMessage; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v22[2]; // [rsp+78h] [rbp-88h] BYREF
  PVOID pvContextBuffer; // [rsp+80h] [rbp-80h]
  unsigned int pfContextAttr; // [rsp+88h] [rbp-78h] BYREF
  struct _SecBufferDesc pInput; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v26[2]; // [rsp+A0h] [rbp-60h] BYREF
  char *pvBuffer; // [rsp+A8h] [rbp-58h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  struct _SecBufferDesc pOutput; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD *v31; // [rsp+D8h] [rbp-28h]
  char v32; // [rsp+E0h] [rbp-20h]
  const void *v33[2]; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v34[2]; // [rsp+100h] [rbp+0h] BYREF
  PSecBuffer v35; // [rsp+108h] [rbp+8h]
  unsigned int v36; // [rsp+110h] [rbp+10h]
  int v37; // [rsp+114h] [rbp+14h]
  gsl::details *v38; // [rsp+118h] [rbp+18h]
  int v39; // [rsp+124h] [rbp+24h]
  int v40; // [rsp+134h] [rbp+34h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  pMessage.ulVersion = 0;
  pMessage.cBuffers = 4;
  pMessage.pBuffers = (PSecBuffer)v34;
  *(_QWORD *)v20 = 0;
  winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(&pInput, a3);
  pBuffers = pInput.pBuffers;
  LODWORD(cbBuffer) = pInput.ulVersion;
  while ( 1 )
  {
    pMessage.ulVersion = 0;
    pMessage.cBuffers = 4;
    pMessage.pBuffers = (PSecBuffer)v34;
    v34[0] = cbBuffer;
    v34[1] = 1;
    v35 = pBuffers;
    v37 = 0;
    v39 = 0;
    v40 = 0;
    v7 = DecryptMessage((PCtxtHandle)(a1 + 120), &pMessage, 0, 0);
    if ( v7 == 590625 )
      break;
    if ( !v7 || (LOBYTE(v8) = 1, v7 == 590615) )
      LOBYTE(v8) = 0;
    v16 = (const char *)v7;
    if ( (_BYTE)v8 )
    {
      LODWORD(v16) = v7 | 0x10000000;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F1,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        v16,
        Reserved1);
    }
    if ( v7 == 590615 )
    {
      v8 = (struct _SecBuffer *)*((_QWORD *)winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::Instance()
                                + 1);
      if ( v8->cbBuffer > 4 )
      {
        Reserved1 = 2;
        tlgWriteTransfer_EventWriteTransfer(v8, word_18003AA32, 0, 0);
      }
    }
    if ( v36 )
    {
      v8 = (struct _SecBuffer *)v38;
      if ( !v38 )
        goto LABEL_43;
      v33[0] = (const void *)v36;
      v33[1] = v38;
      winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReallocateComPtrAndAppendData(
        (char *)v20,
        v33);
    }
    v17 = 0;
    if ( !pMessage.cBuffers )
      goto LABEL_32;
    while ( 1 )
    {
      v8 = &pMessage.pBuffers[v17];
      if ( v8->BufferType == 5 )
        break;
      if ( ++v17 >= pMessage.cBuffers )
        goto LABEL_32;
    }
    if ( !v8 )
    {
LABEL_32:
      winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReturnAsIBufferIfExistsOrEmptyBufferIfNot(
        v8,
        a2,
        v20);
      goto LABEL_33;
    }
    cbBuffer = v8->cbBuffer;
    pBuffers = (PSecBuffer)v8->pvBuffer;
    if ( !pBuffers && v8->cbBuffer )
LABEL_43:
      gsl::details::terminate((gsl::details *)v8);
LABEL_39:
    if ( !cbBuffer )
      goto LABEL_32;
  }
  v9 = 0;
  if ( pMessage.cBuffers )
  {
    while ( 1 )
    {
      v10 = &pMessage.pBuffers[v9];
      if ( v10->BufferType == 5 )
        break;
      if ( ++v9 >= pMessage.cBuffers )
        goto LABEL_6;
    }
  }
  else
  {
LABEL_6:
    v10 = 0;
  }
  if ( !v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4B8,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)0x90090304LL,
      Reserved1);
  v26[0] = v10->cbBuffer;
  v26[1] = 2;
  pvBuffer = (char *)v10->pvBuffer;
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
  v11 = InitializeSecurityContextW(
          (PCredHandle)(a1 + 104),
          (PCtxtHandle)(a1 + 120),
          0,
          0x819Cu,
          0,
          0,
          &pInput,
          0,
          0,
          &pOutput,
          &pfContextAttr,
          0);
  LOBYTE(v12) = v11 != 0;
  winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(
    (winrt::Windows::Internal::Eap::Utility::implementation *)v11,
    v12,
    v13);
  v31 = v22;
  v32 = 1;
  if ( pvContextBuffer || (v14 = 0, v22[0]) )
    v14 = 1;
  if ( v14 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4E1,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)0x90090304LL,
      Reserved1);
  v15 = (gsl::details *)*((_QWORD *)winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::Instance()
                        + 1);
  if ( *(_DWORD *)v15 > 4u )
  {
    Reserved1 = 2;
    tlgWriteTransfer_EventWriteTransfer(v15, byte_18003AA03, 0, 0);
  }
  if ( HIDWORD(v28) == 5 )
  {
    cbBuffer = (unsigned int)v28;
    pBuffers = (PSecBuffer)&pvBuffer[v26[0] - (unsigned __int64)(unsigned int)v28];
    if ( !pBuffers && (_DWORD)v28 )
      gsl::details::terminate(v15);
    v32 = 0;
    v8 = (struct _SecBuffer *)pvContextBuffer;
    if ( pvContextBuffer )
      FreeContextBuffer(pvContextBuffer);
    goto LABEL_39;
  }
  winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReturnAsIBufferIfExistsOrEmptyBufferIfNot(
    v15,
    a2,
    v20);
  if ( pvContextBuffer )
    FreeContextBuffer(pvContextBuffer);
LABEL_33:
  if ( *(_QWORD *)v20 )
    winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(v20);
  return a2;
}

```

## disassembly

```asm
0x180019dc4  push    rbp
0x180019dc6  push    rbx
0x180019dc7  push    rsi
0x180019dc8  push    rdi
0x180019dc9  push    r12
0x180019dcb  push    r14
0x180019dcd  push    r15
0x180019dcf  lea     rbp, [rsp-70h]
0x180019dd4  sub     rsp, 170h
0x180019ddb  mov     rax, cs:__security_cookie
0x180019de2  xor     rax, rsp
0x180019de5  mov     [rbp+0A0h+var_40], rax
0x180019de9  mov     rsi, rdx
0x180019dec  mov     r15, rcx
0x180019def  mov     qword ptr [rsp+1A0h+var_140], rdx
0x180019df4  xor     r12d, r12d
0x180019df7  mov     [rsp+1A0h+pMessage.ulVersion], r12d
0x180019dfc  mov     [rsp+1A0h+pMessage.cBuffers], 4
0x180019e04  lea     rax, [rbp+0A0h+var_A0]
0x180019e08  mov     [rsp+1A0h+pMessage.pBuffers], rax
0x180019e0d  mov     qword ptr [rsp+1A0h+var_140], r12
0x180019e12  mov     rdx, r8
0x180019e15  lea     rcx, [rbp+0A0h+var_110]
0x180019e19  call    ?GetBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AV?$span@$$CBE$0?0@gsl@@AEBUIBuffer@Streams@Storage@56@@Z; winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(winrt::Windows::Storage::Streams::IBuffer const &)
0x180019e1e  mov     rdi, [rbp+0A0h+var_110.pBuffers]
0x180019e22  mov     rbx, qword ptr [rbp+0A0h+var_110.ulVersion]
0x180019e26  mov     [rsp+1A0h+pMessage.ulVersion], r12d
0x180019e2b  mov     [rsp+1A0h+pMessage.cBuffers], 4
0x180019e33  lea     rax, [rbp+0A0h+var_A0]
0x180019e37  mov     [rsp+1A0h+pMessage.pBuffers], rax
0x180019e3c  mov     [rbp+0A0h+var_A0], ebx
0x180019e3f  mov     [rbp+0A0h+var_9C], 1
0x180019e46  mov     [rbp+0A0h+var_98], rdi
0x180019e4a  mov     [rbp+0A0h+var_8C], r12d
0x180019e4e  mov     [rbp+0A0h+var_7C], r12d
0x180019e52  mov     [rbp+0A0h+var_6C], r12d
0x180019e56  xor     r9d, r9d; pfQOP
0x180019e59  xor     r8d, r8d; MessageSeqNo
0x180019e5c  lea     rdx, [rsp+1A0h+pMessage]; pMessage
0x180019e61  lea     rcx, [r15+78h]; phContext
0x180019e65  call    cs:__imp_DecryptMessage
0x180019e6b  cmp     eax, 90321h
0x180019e70  jnz     loc_180019FF3
0x180019e76  mov     ecx, r12d
0x180019e79  mov     r8d, [rsp+1A0h+pMessage.cBuffers]
0x180019e7e  test    r8d, r8d
0x180019e81  jz      short loc_180019E9E
0x180019e83  mov     r9, [rsp+1A0h+pMessage.pBuffers]
0x180019e88  mov     edx, ecx
0x180019e8a  shl     rdx, 4
0x180019e8e  add     rdx, r9
0x180019e91  cmp     dword ptr [rdx+4], 5
0x180019e95  jz      short loc_180019EA1
0x180019e97  inc     ecx
0x180019e99  cmp     ecx, r8d
0x180019e9c  jb      short loc_180019E88
0x180019e9e  mov     rdx, r12
0x180019ea1  mov     rcx, [rbp+0A8h]; this
0x180019ea8  test    rdx, rdx
0x180019eab  jz      loc_18001A161
0x180019eb1  mov     eax, [rdx]
0x180019eb3  mov     [rbp+0A0h+var_100], eax
0x180019eb6  mov     ebx, 2
0x180019ebb  mov     [rbp+0A0h+var_FC], ebx
0x180019ebe  mov     rax, [rdx+8]
0x180019ec2  mov     [rbp+0A0h+var_F8], rax
0x180019ec6  mov     [rbp+0A0h+var_F0], r12
0x180019eca  mov     [rbp+0A0h+var_E8], r12
0x180019ece  mov     [rbp+0A0h+var_110.ulVersion], r12d
0x180019ed2  mov     [rbp+0A0h+var_110.cBuffers], ebx
0x180019ed5  lea     rax, [rbp+0A0h+var_100]
0x180019ed9  mov     [rbp+0A0h+var_110.pBuffers], rax
0x180019edd  mov     [rsp+1A0h+var_128], r12d
0x180019ee2  mov     [rsp+1A0h+var_124], ebx
0x180019ee6  mov     [rbp+0A0h+pvContextBuffer], r12
0x180019eea  mov     [rbp+0A0h+var_D8.ulVersion], r12d
0x180019eee  mov     [rbp+0A0h+var_D8.cBuffers], 1
0x180019ef5  lea     rax, [rsp+1A0h+var_128]
0x180019efa  mov     [rbp+0A0h+var_D8.pBuffers], rax
0x180019efe  mov     [rbp+0A0h+var_118], r12d
0x180019f02  lea     rcx, [r15+68h]; phCredential
0x180019f06  mov     [rsp+1A0h+ptsExpiry], r12; ptsExpiry
0x180019f0b  lea     rax, [rbp+0A0h+var_118]
0x180019f0f  mov     [rsp+1A0h+pfContextAttr], rax; pfContextAttr
0x180019f14  lea     rax, [rbp+0A0h+var_D8]
0x180019f18  mov     [rsp+1A0h+pOutput], rax; pOutput
0x180019f1d  mov     [rsp+1A0h+phNewContext], r12; phNewContext
0x180019f22  mov     [rsp+1A0h+Reserved2], r12d; Reserved2
0x180019f27  lea     rax, [rbp+0A0h+var_110]
0x180019f2b  mov     [rsp+1A0h+pInput], rax; pInput
0x180019f30  mov     [rsp+1A0h+TargetDataRep], r12d; TargetDataRep
0x180019f35  mov     [rsp+1A0h+Reserved1], r12d; int
0x180019f3a  mov     r9d, 819Ch; fContextReq
0x180019f40  xor     r8d, r8d; pszTargetName
0x180019f43  lea     rdx, [r15+78h]; phContext
0x180019f47  call    cs:__imp_InitializeSecurityContextW
0x180019f4d  test    eax, eax
0x180019f4f  setnz   dl; int
0x180019f52  mov     ecx, eax; this
0x180019f54  call    ?ThrowSecurityStatusIf@implementation@Utility@Eap@Internal@Windows@winrt@@YAXJ_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(long,bool)
0x180019f59  lea     rax, [rsp+1A0h+var_128]
0x180019f5e  mov     [rbp+0A0h+var_C8], rax
0x180019f62  mov     [rbp+0A0h+var_C0], 1
0x180019f66  cmp     [rbp+0A0h+pvContextBuffer], r12
0x180019f6a  jnz     short loc_180019F76
0x180019f6c  cmp     [rsp+1A0h+var_128], r12d
0x180019f71  mov     al, r12b
0x180019f74  jz      short loc_180019F78
0x180019f76  mov     al, 1
0x180019f78  mov     rcx, [rbp+0A8h]; this
0x180019f7f  test    al, al
0x180019f81  jnz     loc_18001A149
0x180019f87  call    ?Instance@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@KAPEAV1234567@XZ; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::Instance(void)
0x180019f8c  mov     rcx, [rax+8]
0x180019f90  mov     eax, [rcx]
0x180019f92  cmp     eax, 4
0x180019f95  jbe     short loc_180019FB6
0x180019f97  lea     rax, [rbp+0A0h+var_60]
0x180019f9b  mov     qword ptr [rsp+1A0h+TargetDataRep], rax
0x180019fa0  mov     [rsp+1A0h+Reserved1], ebx
0x180019fa4  xor     r9d, r9d
0x180019fa7  xor     r8d, r8d
0x180019faa  lea     rdx, byte_18003AA03
0x180019fb1  call    _tlgWriteTransfer_EventWriteTransfer
0x180019fb6  cmp     dword ptr [rbp+0A0h+var_F0+4], 5
0x180019fba  jnz     loc_18001A109
0x180019fc0  mov     ebx, dword ptr [rbp+0A0h+var_F0]
0x180019fc3  mov     edi, [rbp+0A0h+var_100]
0x180019fc6  sub     rdi, rbx
0x180019fc9  add     rdi, [rbp+0A0h+var_F8]
0x180019fcd  jnz     short loc_180019FD7
0x180019fcf  test    ebx, ebx
0x180019fd1  jnz     loc_18001A143
0x180019fd7  mov     [rbp+0A0h+var_C0], r12b
0x180019fdb  mov     rcx, [rbp+0A0h+pvContextBuffer]; pvContextBuffer
0x180019fdf  test    rcx, rcx
0x180019fe2  jz      loc_18001A0FB
0x180019fe8  call    cs:__imp_FreeContextBuffer
0x180019fee  jmp     loc_18001A0FB
0x180019ff3  test    eax, eax
0x180019ff5  jz      short loc_18001A000
0x180019ff7  cmp     eax, 90317h
0x180019ffc  mov     cl, 1
0x180019ffe  jnz     short loc_18001A003
0x18001a000  mov     cl, r12b
0x18001a003  mov     r9d, eax
0x18001a006  bts     r9d, 1Ch; char *
0x18001a00b  mov     r10, [rbp+0A8h]
0x18001a012  test    cl, cl
0x18001a014  jnz     loc_18001A12E
0x18001a01a  cmp     eax, 90317h
0x18001a01f  jnz     short loc_18001A054
0x18001a021  call    ?Instance@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@KAPEAV1234567@XZ; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::Instance(void)
0x18001a026  mov     rcx, [rax+8]
0x18001a02a  mov     eax, [rcx]
0x18001a02c  cmp     eax, 4
0x18001a02f  jbe     short loc_18001A054
0x18001a031  lea     rax, [rbp+0A0h+var_60]
0x18001a035  mov     qword ptr [rsp+1A0h+TargetDataRep], rax
0x18001a03a  mov     [rsp+1A0h+Reserved1], 2
0x18001a042  xor     r9d, r9d
0x18001a045  xor     r8d, r8d
0x18001a048  lea     rdx, word_18003AA32
0x18001a04f  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a054  mov     eax, [rbp+0A0h+var_90]
0x18001a057  test    eax, eax
0x18001a059  jz      short loc_18001A07E
0x18001a05b  mov     rcx, [rbp+0A0h+var_88]; this
0x18001a05f  test    rcx, rcx
0x18001a062  jz      loc_18001A128
0x18001a068  mov     [rbp+0A0h+var_B0], rax
0x18001a06c  mov     [rbp+0A0h+var_A8], rcx
0x18001a070  lea     rdx, [rbp+0A0h+var_B0]
0x18001a074  lea     rcx, [rsp+1A0h+var_140]; int
0x18001a079  call    ?ReallocateComPtrAndAppendData@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@CAXAEAU?$com_ptr@UIBuffer@Streams@Storage@Windows@@@7@V?$span@$$CBE$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReallocateComPtrAndAppendData(winrt::com_ptr<Windows::Storage::Streams::IBuffer> &,gsl::span<uchar const,-1>)
0x18001a07e  mov     edx, r12d
0x18001a081  mov     r8d, [rsp+1A0h+pMessage.cBuffers]
0x18001a086  test    r8d, r8d
0x18001a089  jz      short loc_18001A0A6
0x18001a08b  mov     r9, [rsp+1A0h+pMessage.pBuffers]
0x18001a090  mov     ecx, edx
0x18001a092  shl     rcx, 4
0x18001a096  add     rcx, r9
0x18001a099  cmp     dword ptr [rcx+4], 5
0x18001a09d  jz      short loc_18001A0E6
0x18001a09f  inc     edx
0x18001a0a1  cmp     edx, r8d
0x18001a0a4  jb      short loc_18001A090
0x18001a0a6  lea     r8, [rsp+1A0h+var_140]
0x18001a0ab  mov     rdx, rsi
0x18001a0ae  call    ?ReturnAsIBufferIfExistsOrEmptyBufferIfNot@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAA?AUIBuffer@Streams@Storage@67@AEAU?$com_ptr@UIBuffer@Streams@Storage@Windows@@@7@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReturnAsIBufferIfExistsOrEmptyBufferIfNot(winrt::com_ptr<Windows::Storage::Streams::IBuffer> &)
0x18001a0b3  nop
0x18001a0b4  cmp     qword ptr [rsp+1A0h+var_140], r12
0x18001a0b9  jz      short loc_18001A0C5
0x18001a0bb  lea     rcx, [rsp+1A0h+var_140]
0x18001a0c0  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18001a0c5  mov     rax, rsi
0x18001a0c8  mov     rcx, [rbp+0A0h+var_40]
0x18001a0cc  xor     rcx, rsp; StackCookie
0x18001a0cf  call    __security_check_cookie
0x18001a0d4  add     rsp, 170h
0x18001a0db  pop     r15
0x18001a0dd  pop     r14
0x18001a0df  pop     r12
0x18001a0e1  pop     rdi
0x18001a0e2  pop     rsi
0x18001a0e3  pop     rbx
0x18001a0e4  pop     rbp
0x18001a0e5  retn
0x18001a0e6  test    rcx, rcx
0x18001a0e9  jz      short loc_18001A0A6
0x18001a0eb  mov     ebx, [rcx]
0x18001a0ed  mov     rdi, [rcx+8]
0x18001a0f1  test    rdi, rdi
0x18001a0f4  jnz     short loc_18001A0FB
0x18001a0f6  test    rbx, rbx
0x18001a0f9  jnz     short loc_18001A128
0x18001a0fb  mov     rax, rbx
0x18001a0fe  test    rax, rax
0x18001a101  jnz     loc_180019E26
0x18001a107  jmp     short loc_18001A0A6
0x18001a109  lea     r8, [rsp+1A0h+var_140]
0x18001a10e  mov     rdx, rsi
0x18001a111  call    ?ReturnAsIBufferIfExistsOrEmptyBufferIfNot@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAA?AUIBuffer@Streams@Storage@67@AEAU?$com_ptr@UIBuffer@Streams@Storage@Windows@@@7@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReturnAsIBufferIfExistsOrEmptyBufferIfNot(winrt::com_ptr<Windows::Storage::Streams::IBuffer> &)
0x18001a116  nop
0x18001a117  mov     rcx, [rbp+0A0h+pvContextBuffer]; pvContextBuffer
0x18001a11b  test    rcx, rcx
0x18001a11e  jz      short loc_18001A0B4
0x18001a120  call    cs:__imp_FreeContextBuffer
0x18001a126  jmp     short loc_18001A0B4
0x18001a128  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x18001a12e  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001a135  mov     edx, 4F1h; void *
0x18001a13a  mov     rcx, r10; this
0x18001a13d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a143  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x18001a149  mov     r9d, 90090304h; char *
0x18001a14f  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001a156  mov     edx, 4E1h; void *
0x18001a15b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a161  mov     r9d, 90090304h; char *
0x18001a167  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001a16e  mov     edx, 4B8h; void *
0x18001a173  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

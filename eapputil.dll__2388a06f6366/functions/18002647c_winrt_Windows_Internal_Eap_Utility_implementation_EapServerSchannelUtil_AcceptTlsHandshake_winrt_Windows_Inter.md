# winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::AcceptTlsHandshake(winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions const &,winrt::Windows::Storage::Streams::IBuffer const &)

- ea: `0x18002647c`
- end: `0x180026688`
- name: `?AcceptTlsHandshake@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@QEAAXAEBUEapTlsHandshakeOptions@34567@AEBUIBuffer@Streams@Storage@67@@Z`
- size: `524`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil *__hidden this, const struct winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions *, const struct winrt::Windows::Storage::Streams::IBuffer *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800263d0`
- `0x180026690`

## callees

- `0x1800101c4`
- `0x1800137f0`
- `0x18001767c`
- `0x18001e218`
- `0x180025350`
- `0x18002647c`
- `0x180028528`
- `0x1800296e4`
- `0x18002e598`
- `0x18002e5f4`

## import_xrefs

- `SspiCli!FreeContextBuffer` at `0x180026652`
- `SspiCli!FreeContextBuffer` at `0x180026652`
- `SspiCli!AcceptSecurityContext` at `0x1800265bb`
- `SspiCli!AcceptSecurityContext` at `0x1800265bb`
- `SspiCli!DeleteSecurityContext` at `0x18002651b`
- `SspiCli!DeleteSecurityContext` at `0x18002651b`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::AcceptTlsHandshake(
        winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil *this,
        const struct winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions *a2,
        const struct winrt::Windows::Storage::Streams::IBuffer *a3)
{
  int v5; // esi
  unsigned int v6; // eax
  int v7; // edx
  bool v8; // r8
  unsigned int TargetDataRep; // [rsp+20h] [rbp-79h]
  _DWORD v10[2]; // [rsp+50h] [rbp-49h] BYREF
  PVOID pvContextBuffer; // [rsp+58h] [rbp-41h]
  __int128 v12; // [rsp+60h] [rbp-39h] BYREF
  __int64 v13; // [rsp+70h] [rbp-29h]
  _DWORD *v14; // [rsp+78h] [rbp-21h] BYREF
  __int64 v15; // [rsp+80h] [rbp-19h]
  __int128 v16; // [rsp+88h] [rbp-11h] BYREF
  __int64 v17; // [rsp+98h] [rbp-1h]
  struct _SecBufferDesc pOutput; // [rsp+A0h] [rbp+7h] BYREF
  struct _SecBufferDesc pInput; // [rsp+B0h] [rbp+17h] BYREF
  _DWORD v20[2]; // [rsp+C0h] [rbp+27h] BYREF
  __int64 v21; // [rsp+C8h] [rbp+2Fh]
  __int64 v22; // [rsp+D0h] [rbp+37h]
  __int64 v23; // [rsp+D8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  int v25; // [rsp+100h] [rbp+67h] BYREF
  unsigned int pfContextAttr; // [rsp+118h] [rbp+7Fh] BYREF

  ++*((_DWORD *)this + 38);
  winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(&v14, a3);
  v5 = (int)v14;
  if ( !v14 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)0x80070057LL,
      TargetDataRep);
  v25 = (int)v14;
  winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::ReceivedHandshakeMessageFromClient<unsigned int>(&v25);
  if ( !*((_DWORD *)this + 58)
    || !(unsigned int)winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::SessionResumptionState(a2)
    || *((_DWORD *)this + 7) != 2 )
  {
    winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::InitializeCredentialsHandle(this, a2);
  }
  *((_DWORD *)this + 58) = winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::SessionResumptionState(a2);
  if ( *((_QWORD *)this + 4) != -1 && *((_QWORD *)this + 5) != -1 )
  {
    DeleteSecurityContext((PCtxtHandle)this + 2);
    *((_QWORD *)this + 5) = -1;
    *((_QWORD *)this + 4) = -1;
  }
  *((_DWORD *)this + 7) = 1;
  v20[0] = v5;
  v20[1] = 2;
  v21 = v15;
  v22 = 0;
  v23 = 0;
  pInput.ulVersion = 0;
  pInput.cBuffers = 2;
  pInput.pBuffers = (PSecBuffer)v20;
  v10[0] = 0;
  v10[1] = 2;
  pvContextBuffer = 0;
  pOutput.ulVersion = 0;
  pOutput.cBuffers = 1;
  pOutput.pBuffers = (PSecBuffer)v10;
  pfContextAttr = 0;
  v6 = AcceptSecurityContext(
         (PCredHandle)this + 3,
         0,
         &pInput,
         0x1811Eu,
         0,
         (PCtxtHandle)this + 2,
         &pOutput,
         &pfContextAttr,
         0);
  v14 = v10;
  LOBYTE(v15) = 1;
  LOBYTE(v7) = v6 != 590610;
  winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(
    (winrt::Windows::Internal::Eap::Utility::implementation *)v6,
    v7,
    v8);
  v16 = 0;
  v17 = 0;
  if ( pvContextBuffer && v10[0] )
  {
    std::vector<unsigned char>::vector<unsigned char>(&v12, pvContextBuffer, (char *)pvContextBuffer + v10[0]);
    v16 = v12;
    v12 = 0u;
    v17 = v13;
    v13 = 0;
    std::vector<unsigned char>::~vector<unsigned char>((char **)&v12);
  }
  winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::TlsHandshakeDataGenerated(this, &v16);
  std::vector<unsigned char>::~vector<unsigned char>((char **)&v16);
  if ( pvContextBuffer )
    FreeContextBuffer(pvContextBuffer);
}

```

## disassembly

```asm
0x18002647c  mov     [rsp-8+arg_8], rbx
0x180026481  mov     [rsp-8+arg_10], rsi
0x180026486  push    rbp
0x180026487  push    rdi
0x180026488  push    r14
0x18002648a  lea     rbp, [rsp-47h]
0x18002648f  sub     rsp, 0E0h
0x180026496  mov     rdi, rdx
0x180026499  mov     rbx, rcx
0x18002649c  inc     dword ptr [rcx+98h]
0x1800264a2  mov     rdx, r8
0x1800264a5  lea     rcx, [rbp+57h+var_78]
0x1800264a9  call    ?GetBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AV?$span@$$CBE$0?0@gsl@@AEBUIBuffer@Streams@Storage@56@@Z; winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(winrt::Windows::Storage::Streams::IBuffer const &)
0x1800264ae  mov     rsi, [rbp+57h+var_78]
0x1800264b2  xor     r14d, r14d
0x1800264b5  test    rsi, rsi
0x1800264b8  setz    al
0x1800264bb  mov     rcx, [rbp+5Fh]; this
0x1800264bf  test    al, al
0x1800264c1  jnz     loc_180026670
0x1800264c7  mov     [rbp+57h+arg_0], esi
0x1800264ca  lea     rcx, [rbp+57h+arg_0]
0x1800264ce  call    ??$ReceivedHandshakeMessageFromClient@I@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAX$$QEAI@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::ReceivedHandshakeMessageFromClient<uint>(uint &&)
0x1800264d3  cmp     [rbx+0E8h], r14d
0x1800264da  jz      short loc_1800264EE
0x1800264dc  mov     rcx, rdi
0x1800264df  call    ?SessionResumptionState@?$consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions@UIEapTlsHandshakeOptions@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::SessionResumptionState(void)
0x1800264e4  test    eax, eax
0x1800264e6  jz      short loc_1800264EE
0x1800264e8  cmp     dword ptr [rbx+1Ch], 2
0x1800264ec  jz      short loc_1800264F9
0x1800264ee  mov     rdx, rdi; struct winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions *
0x1800264f1  mov     rcx, rbx; this
0x1800264f4  call    ?InitializeCredentialsHandle@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBUEapTlsHandshakeOptions@34567@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::InitializeCredentialsHandle(winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions const &)
0x1800264f9  mov     rcx, rdi
0x1800264fc  call    ?SessionResumptionState@?$consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions@UIEapTlsHandshakeOptions@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::SessionResumptionState(void)
0x180026501  mov     [rbx+0E8h], eax
0x180026507  lea     rdi, [rbx+20h]
0x18002650b  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18002650f  jz      short loc_180026530
0x180026511  cmp     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180026516  jz      short loc_180026530
0x180026518  mov     rcx, rdi; phContext
0x18002651b  call    cs:__imp_DeleteSecurityContext
0x180026521  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180026529  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180026530  mov     dword ptr [rbx+1Ch], 1
0x180026537  mov     [rbp+57h+var_30], esi
0x18002653a  mov     [rbp+57h+var_2C], 2
0x180026541  mov     rax, [rbp+57h+var_70]
0x180026545  mov     [rbp+57h+var_28], rax
0x180026549  mov     [rbp+57h+var_20], r14
0x18002654d  mov     [rbp+57h+var_18], r14
0x180026551  mov     [rbp+57h+pInput.ulVersion], r14d
0x180026555  mov     [rbp+57h+pInput.cBuffers], 2
0x18002655c  lea     rax, [rbp+57h+var_30]
0x180026560  mov     [rbp+57h+pInput.pBuffers], rax
0x180026564  mov     [rbp+57h+var_A0], r14d
0x180026568  mov     [rbp+57h+var_9C], 2
0x18002656f  mov     [rbp+57h+pvContextBuffer], r14
0x180026573  mov     [rbp+57h+var_50.ulVersion], r14d
0x180026577  mov     [rbp+57h+var_50.cBuffers], 1
0x18002657e  lea     rax, [rbp+57h+var_A0]
0x180026582  mov     [rbp+57h+var_50.pBuffers], rax
0x180026586  mov     [rbp+57h+arg_18], r14d
0x18002658a  lea     rcx, [rbx+30h]; phCredential
0x18002658e  mov     [rsp+0F0h+ptsExpiry], r14; ptsExpiry
0x180026593  lea     rax, [rbp+57h+arg_18]
0x180026597  mov     [rsp+0F0h+pfContextAttr], rax; pfContextAttr
0x18002659c  lea     rax, [rbp+57h+var_50]
0x1800265a0  mov     [rsp+0F0h+pOutput], rax; pOutput
0x1800265a5  mov     [rsp+0F0h+phNewContext], rdi; phNewContext
0x1800265aa  mov     [rsp+0F0h+TargetDataRep], r14d; TargetDataRep
0x1800265af  mov     r9d, 1811Eh; fContextReq
0x1800265b5  lea     r8, [rbp+57h+pInput]; pInput
0x1800265b9  xor     edx, edx; phContext
0x1800265bb  call    cs:__imp_AcceptSecurityContext
0x1800265c1  lea     rcx, [rbp+57h+var_A0]
0x1800265c5  mov     [rbp+57h+var_78], rcx
0x1800265c9  mov     byte ptr [rbp+57h+var_70], 1
0x1800265cd  cmp     eax, 90312h
0x1800265d2  setnz   dl; int
0x1800265d5  mov     ecx, eax; this
0x1800265d7  call    ?ThrowSecurityStatusIf@implementation@Utility@Eap@Internal@Windows@winrt@@YAXJ_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(long,bool)
0x1800265dc  xorps   xmm0, xmm0
0x1800265df  movdqu  [rbp+57h+var_68], xmm0
0x1800265e4  mov     [rbp+57h+var_58], r14
0x1800265e8  mov     rdx, [rbp+57h+pvContextBuffer]
0x1800265ec  test    rdx, rdx
0x1800265ef  jz      short loc_180026632
0x1800265f1  mov     eax, [rbp+57h+var_A0]
0x1800265f4  test    eax, eax
0x1800265f6  jz      short loc_180026632
0x1800265f8  lea     r8, [rdx+rax]
0x1800265fc  lea     rcx, [rbp+57h+var_90]
0x180026600  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x180026605  mov     rax, qword ptr [rbp+57h+var_90]
0x180026609  mov     qword ptr [rbp+57h+var_68], rax
0x18002660d  mov     qword ptr [rbp+57h+var_90], r14
0x180026611  mov     rax, qword ptr [rbp+57h+var_90+8]
0x180026615  mov     qword ptr [rbp+57h+var_68+8], rax
0x180026619  mov     qword ptr [rbp+57h+var_90+8], r14
0x18002661d  mov     rax, [rbp+57h+var_80]
0x180026621  mov     [rbp+57h+var_58], rax
0x180026625  mov     [rbp+57h+var_80], r14
0x180026629  lea     rcx, [rbp+57h+var_90]
0x18002662d  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180026632  lea     rdx, [rbp+57h+var_68]
0x180026636  mov     rcx, rbx
0x180026639  call    ?TlsHandshakeDataGenerated@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::TlsHandshakeDataGenerated(std::vector<uchar> const &)
0x18002663e  nop
0x18002663f  lea     rcx, [rbp+57h+var_68]
0x180026643  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180026648  nop
0x180026649  mov     rcx, [rbp+57h+pvContextBuffer]; pvContextBuffer
0x18002664d  test    rcx, rcx
0x180026650  jz      short loc_180026658
0x180026652  call    cs:__imp_FreeContextBuffer
0x180026658  lea     r11, [rsp+0F0h+var_10]
0x180026660  mov     rbx, [r11+28h]
0x180026664  mov     rsi, [r11+30h]
0x180026668  mov     rsp, r11
0x18002666b  pop     r14
0x18002666d  pop     rdi
0x18002666e  pop     rbp
0x18002666f  retn
0x180026670  mov     r9d, 80070057h; char *
0x180026676  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002667d  mov     edx, 54h ; 'T'; void *
0x180026682  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

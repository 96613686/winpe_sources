# winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::ContinueTlsHandshake(winrt::Windows::Storage::Streams::IBuffer const &)

- ea: `0x180026844`
- end: `0x180026bab`
- name: `?ContinueTlsHandshake@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@QEAAXAEBUIBuffer@Streams@Storage@67@@Z`
- size: `871`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil *__hidden this, const struct winrt::Windows::Storage::Streams::IBuffer *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180026810`

## callees

- `0x1800101c4`
- `0x1800144b4`
- `0x18001767c`
- `0x180026844`
- `0x1800272dc`
- `0x1800294d0`
- `0x1800296e4`
- `0x18002b7a0`
- `0x18002e598`
- `0x18002e5f4`

## import_xrefs

- `SspiCli!FreeContextBuffer` at `0x180026ac0`
- `SspiCli!FreeContextBuffer` at `0x180026ac0`
- `SspiCli!AcceptSecurityContext` at `0x180026961`
- `SspiCli!AcceptSecurityContext` at `0x180026961`
- `SspiCli!QueryContextAttributesW` at `0x1800269a4`
- `SspiCli!QueryContextAttributesW` at `0x1800269c1`
- `SspiCli!QueryContextAttributesW` at `0x1800269de`
- `SspiCli!QueryContextAttributesW` at `0x1800269a4`
- `SspiCli!QueryContextAttributesW` at `0x1800269c1`
- `SspiCli!QueryContextAttributesW` at `0x1800269de`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::ContinueTlsHandshake(
        winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil *this,
        const struct winrt::Windows::Storage::Streams::IBuffer *a2)
{
  unsigned __int64 v3; // rdi
  char v4; // r13
  unsigned __int64 v5; // r14
  char v6; // si
  int v7; // edx
  bool v8; // r8
  unsigned int v9; // r15d
  SECURITY_STATUS ContextAttributesW; // eax
  SECURITY_STATUS v11; // eax
  SECURITY_STATUS v12; // eax
  PVOID v13; // rcx
  unsigned int TargetDataRep; // [rsp+20h] [rbp-E0h]
  unsigned int TargetDataRepa; // [rsp+20h] [rbp-E0h]
  _DWORD v16[2]; // [rsp+50h] [rbp-B0h] BYREF
  PVOID pvContextBuffer; // [rsp+58h] [rbp-A8h]
  __int128 v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h]
  _DWORD v20[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v21; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  __int64 v23; // [rsp+90h] [rbp-70h]
  struct _SecBufferDesc pOutput; // [rsp+98h] [rbp-68h] BYREF
  struct _SecBufferDesc pInput; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v26[3]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v27[3]; // [rsp+D0h] [rbp-30h] BYREF
  char v28; // [rsp+E8h] [rbp-18h]
  char *v29[10]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  int v31; // [rsp+150h] [rbp+50h] BYREF
  unsigned int pfContextAttr; // [rsp+160h] [rbp+60h] BYREF

  if ( (*((_DWORD *)this + 7) & 0xFFFFFFFD) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)0x8007139FLL,
      TargetDataRep);
  winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(v26, a2);
  v3 = v26[0];
  if ( !v26[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)0x80070057LL,
      TargetDataRep);
  v4 = 0;
  v18 = 0;
  v19 = 0;
  std::vector<unsigned char>::reserve(&v18, v26[0]);
  v5 = 0;
  v6 = 1;
  do
  {
    v20[0] = v3 - v5;
    v20[1] = 2;
    v21 = v5 + v26[1];
    v22 = 0;
    v23 = 0;
    pInput.ulVersion = 0;
    pInput.cBuffers = 2;
    pInput.pBuffers = (PSecBuffer)v20;
    v16[0] = 0;
    v16[1] = 2;
    pvContextBuffer = 0;
    pOutput.ulVersion = 0;
    pOutput.cBuffers = 1;
    pOutput.pBuffers = (PSecBuffer)v16;
    pfContextAttr = 0;
    v9 = AcceptSecurityContext(
           (PCredHandle)this + 3,
           (PCtxtHandle)this + 2,
           &pInput,
           0x1811Eu,
           0,
           (PCtxtHandle)this + 2,
           &pOutput,
           &pfContextAttr,
           0);
    v27[2] = v16;
    v28 = 1;
    if ( !v9 || v9 == 590610 )
      v7 = 0;
    else
      LOBYTE(v7) = 1;
    winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(
      (winrt::Windows::Internal::Eap::Utility::implementation *)v9,
      v7,
      v8);
    if ( v9 )
    {
      if ( v9 == 590610 )
      {
        v5 = v3;
        if ( HIDWORD(v22) == 5 )
          v5 = v3 - (unsigned int)v22;
      }
    }
    else
    {
      ContextAttributesW = QueryContextAttributesW((PCtxtHandle)this + 2, 0x5Au, (char *)this + 64);
      if ( ContextAttributesW < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x197,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
          (const char *)(unsigned int)ContextAttributesW,
          TargetDataRepa);
      v11 = QueryContextAttributesW((PCtxtHandle)this + 2, 4u, (char *)this + 92);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x198,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
          (const char *)(unsigned int)v11,
          TargetDataRepa);
      v12 = QueryContextAttributesW((PCtxtHandle)this + 2, 0x5Du, (char *)this + 112);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x199,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
          (const char *)(unsigned int)v12,
          TargetDataRepa);
      v5 = v3;
      v31 = 1;
      winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::TlsHandshakeCompleted(
        this,
        (const enum winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus *)&v31);
      v4 = 1;
    }
    v13 = pvContextBuffer;
    if ( pvContextBuffer && v16[0] )
    {
      std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
        &v18,
        *((_QWORD *)&v18 + 1),
        pvContextBuffer,
        v16[0]);
      v13 = pvContextBuffer;
    }
    if ( !v9
      && (*((_DWORD *)this + 16) & 0x3000) != 0
      && (*((_DWORD *)this + 6) == 2 || (*((_BYTE *)this + 112) & 1) != 0) )
    {
      LOBYTE(v31) = 0;
      v27[0] = 1;
      v27[1] = &v31;
      winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::EncryptData(
        (__int64)this,
        (__int64 *)v29,
        (unsigned int *)v27);
      std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
        &v18,
        *((_QWORD *)&v18 + 1),
        v29[0],
        v29[1] - v29[0]);
      std::vector<unsigned char>::~vector<unsigned char>(v29);
      v13 = pvContextBuffer;
    }
    v28 = 0;
    if ( v13 )
      FreeContextBuffer(v13);
  }
  while ( v5 < v3 );
  if ( *((_QWORD *)&v18 + 1) != (_QWORD)v18 || v4 )
    v6 = 0;
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)0x83760002LL,
      TargetDataRepa);
  if ( *((_QWORD *)&v18 + 1) != (_QWORD)v18 )
    winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::TlsHandshakeDataGenerated(this, &v18);
  std::vector<unsigned char>::~vector<unsigned char>((char **)&v18);
}

```

## disassembly

```asm
0x180026844  mov     [rsp-8+arg_8], rbx
0x180026849  push    rbp
0x18002684a  push    rsi
0x18002684b  push    rdi
0x18002684c  push    r12
0x18002684e  push    r13
0x180026850  push    r14
0x180026852  push    r15
0x180026854  lea     rbp, [rsp-10h]
0x180026859  sub     rsp, 110h
0x180026860  mov     rbx, rcx
0x180026863  test    dword ptr [rcx+1Ch], 0FFFFFFFDh
0x18002686a  setz    al
0x18002686d  mov     rcx, [rbp+48h]; this
0x180026871  xor     r15d, r15d
0x180026874  test    al, al
0x180026876  jnz     loc_180026B39
0x18002687c  lea     rcx, [rbp+40h+var_88]
0x180026880  call    ?GetBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AV?$span@$$CBE$0?0@gsl@@AEBUIBuffer@Streams@Storage@56@@Z; winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(winrt::Windows::Storage::Streams::IBuffer const &)
0x180026885  mov     rdi, [rbp+40h+var_88]
0x180026889  test    rdi, rdi
0x18002688c  setz    al
0x18002688f  mov     rcx, [rbp+48h]; this
0x180026893  test    al, al
0x180026895  jnz     loc_180026B51
0x18002689b  mov     r13b, r15b
0x18002689e  xorps   xmm0, xmm0
0x1800268a1  movdqu  [rsp+140h+var_E0], xmm0
0x1800268a7  mov     [rsp+140h+var_D0], r15
0x1800268ac  mov     rdx, rdi
0x1800268af  lea     rcx, [rsp+140h+var_E0]
0x1800268b4  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x1800268b9  mov     r14d, r15d
0x1800268bc  lea     esi, [r15+1]
0x1800268c0  test    rdi, rdi
0x1800268c3  jz      loc_180026ACF
0x1800268c9  lea     r12, [rbx+20h]
0x1800268cd  lea     rcx, [rbx+30h]; phCredential
0x1800268d1  mov     eax, edi
0x1800268d3  sub     eax, r14d
0x1800268d6  mov     [rsp+140h+var_C8], eax
0x1800268da  mov     [rsp+140h+var_C4], 2
0x1800268e2  mov     rax, [rbp+40h+var_80]
0x1800268e6  add     rax, r14
0x1800268e9  mov     [rbp+40h+var_C0], rax
0x1800268ed  mov     [rbp+40h+var_B8], 0
0x1800268f5  mov     [rbp+40h+var_B0], r15
0x1800268f9  mov     [rbp+40h+pInput.ulVersion], r15d
0x1800268fd  mov     [rbp+40h+pInput.cBuffers], 2
0x180026904  lea     rax, [rsp+140h+var_C8]
0x180026909  mov     [rbp+40h+pInput.pBuffers], rax
0x18002690d  mov     [rsp+140h+var_F0], r15d
0x180026912  mov     [rsp+140h+var_EC], 2
0x18002691a  mov     [rsp+140h+pvContextBuffer], r15
0x18002691f  mov     [rbp+40h+var_A8.ulVersion], r15d
0x180026923  mov     [rbp+40h+var_A8.cBuffers], esi
0x180026926  lea     rax, [rsp+140h+var_F0]
0x18002692b  mov     [rbp+40h+var_A8.pBuffers], rax
0x18002692f  mov     [rbp+40h+arg_10], r15d
0x180026933  mov     [rsp+140h+ptsExpiry], r15; ptsExpiry
0x180026938  lea     rax, [rbp+40h+arg_10]
0x18002693c  mov     [rsp+140h+pfContextAttr], rax; pfContextAttr
0x180026941  lea     rax, [rbp+40h+var_A8]
0x180026945  mov     [rsp+140h+pOutput], rax; pOutput
0x18002694a  mov     [rsp+140h+phNewContext], r12; phNewContext
0x18002694f  mov     [rsp+140h+TargetDataRep], r15d; int
0x180026954  mov     r9d, 1811Eh; fContextReq
0x18002695a  lea     r8, [rbp+40h+pInput]; pInput
0x18002695e  mov     rdx, r12; phContext
0x180026961  call    cs:__imp_AcceptSecurityContext
0x180026967  mov     r15d, eax
0x18002696a  lea     rax, [rsp+140h+var_F0]
0x18002696f  mov     [rbp+40h+var_60], rax
0x180026973  mov     [rbp+40h+var_58], sil
0x180026977  test    r15d, r15d
0x18002697a  jz      short loc_18002698A
0x18002697c  cmp     r15d, 90312h
0x180026983  jz      short loc_18002698A
0x180026985  mov     dl, sil
0x180026988  jmp     short loc_18002698C
0x18002698a  xor     edx, edx; int
0x18002698c  mov     ecx, r15d; this
0x18002698f  call    ?ThrowSecurityStatusIf@implementation@Utility@Eap@Internal@Windows@winrt@@YAXJ_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(long,bool)
0x180026994  test    r15d, r15d
0x180026997  jnz     short loc_180026A07
0x180026999  lea     r8, [rbx+40h]; pBuffer
0x18002699d  lea     edx, [r15+5Ah]; ulAttribute
0x1800269a1  mov     rcx, r12; phContext
0x1800269a4  call    cs:__imp_QueryContextAttributesW
0x1800269aa  mov     rcx, [rbp+48h]; this
0x1800269ae  test    eax, eax
0x1800269b0  js      loc_180026B24
0x1800269b6  lea     r8, [rbx+5Ch]; pBuffer
0x1800269ba  lea     edx, [r15+4]; ulAttribute
0x1800269be  mov     rcx, r12; phContext
0x1800269c1  call    cs:__imp_QueryContextAttributesW
0x1800269c7  mov     rcx, [rbp+48h]; this
0x1800269cb  test    eax, eax
0x1800269cd  js      loc_180026B96
0x1800269d3  lea     r8, [rbx+70h]; pBuffer
0x1800269d7  lea     edx, [r15+5Dh]; ulAttribute
0x1800269db  mov     rcx, r12; phContext
0x1800269de  call    cs:__imp_QueryContextAttributesW
0x1800269e4  mov     rcx, [rbp+48h]; this
0x1800269e8  test    eax, eax
0x1800269ea  js      loc_180026B81
0x1800269f0  mov     r14, rdi
0x1800269f3  mov     [rbp+40h+arg_0], esi
0x1800269f6  lea     rdx, [rbp+40h+arg_0]; enum winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus *
0x1800269fa  mov     rcx, rbx; this
0x1800269fd  call    ?TlsHandshakeCompleted@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBW4EapTlsHandshakeStatus@34567@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::TlsHandshakeCompleted(winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus const &)
0x180026a02  mov     r13b, sil
0x180026a05  jmp     short loc_180026A1F
0x180026a07  cmp     r15d, 90312h
0x180026a0e  jnz     short loc_180026A1F
0x180026a10  mov     r14, rdi
0x180026a13  cmp     dword ptr [rbp+40h+var_B8+4], 5
0x180026a17  jnz     short loc_180026A1F
0x180026a19  mov     eax, dword ptr [rbp+40h+var_B8]
0x180026a1c  sub     r14, rax
0x180026a1f  mov     rcx, [rsp+140h+pvContextBuffer]
0x180026a24  test    rcx, rcx
0x180026a27  jz      short loc_180026A4B
0x180026a29  mov     eax, [rsp+140h+var_F0]
0x180026a2d  test    eax, eax
0x180026a2f  jz      short loc_180026A4B
0x180026a31  mov     r9d, eax
0x180026a34  mov     r8, rcx
0x180026a37  mov     rdx, qword ptr [rsp+140h+var_E0+8]
0x180026a3c  lea     rcx, [rsp+140h+var_E0]
0x180026a41  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x180026a46  mov     rcx, [rsp+140h+pvContextBuffer]; pvContextBuffer
0x180026a4b  test    r15d, r15d
0x180026a4e  jnz     short loc_180026AB4
0x180026a50  test    dword ptr [rbx+40h], 3000h
0x180026a57  jz      short loc_180026AB4
0x180026a59  cmp     dword ptr [rbx+18h], 2
0x180026a5d  jz      short loc_180026A65
0x180026a5f  test    [rbx+70h], sil
0x180026a63  jz      short loc_180026AB4
0x180026a65  xor     r15d, r15d
0x180026a68  mov     byte ptr [rbp+40h+arg_0], r15b
0x180026a6c  mov     [rbp+40h+var_70], rsi
0x180026a70  lea     rax, [rbp+40h+arg_0]
0x180026a74  mov     [rbp+40h+var_68], rax
0x180026a78  lea     r8, [rbp+40h+var_70]
0x180026a7c  lea     rdx, [rbp+40h+var_50]
0x180026a80  mov     rcx, rbx
0x180026a83  call    ?EncryptData@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@V?$span@$$CBE$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::EncryptData(gsl::span<uchar const,-1>)
0x180026a88  nop
0x180026a89  mov     r8, [rbp+40h+var_50]
0x180026a8d  mov     r9, [rbp+40h+var_48]
0x180026a91  sub     r9, r8
0x180026a94  mov     rdx, qword ptr [rsp+140h+var_E0+8]
0x180026a99  lea     rcx, [rsp+140h+var_E0]
0x180026a9e  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x180026aa3  nop
0x180026aa4  lea     rcx, [rbp+40h+var_50]
0x180026aa8  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180026aad  mov     rcx, [rsp+140h+pvContextBuffer]
0x180026ab2  jmp     short loc_180026AB7
0x180026ab4  xor     r15d, r15d
0x180026ab7  mov     [rbp+40h+var_58], r15b
0x180026abb  test    rcx, rcx
0x180026abe  jz      short loc_180026AC6
0x180026ac0  call    cs:__imp_FreeContextBuffer
0x180026ac6  cmp     r14, rdi
0x180026ac9  jb      loc_1800268CD
0x180026acf  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x180026ad4  sub     rax, qword ptr [rsp+140h+var_E0]
0x180026ad9  jnz     short loc_180026AE0
0x180026adb  test    r13b, r13b
0x180026ade  jz      short loc_180026AE3
0x180026ae0  mov     sil, r15b
0x180026ae3  mov     rcx, [rbp+48h]; this
0x180026ae7  test    sil, sil
0x180026aea  jnz     short loc_180026B69
0x180026aec  test    rax, rax
0x180026aef  jz      short loc_180026AFF
0x180026af1  lea     rdx, [rsp+140h+var_E0]
0x180026af6  mov     rcx, rbx
0x180026af9  call    ?TlsHandshakeDataGenerated@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::TlsHandshakeDataGenerated(std::vector<uchar> const &)
0x180026afe  nop
0x180026aff  lea     rcx, [rsp+140h+var_E0]
0x180026b04  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180026b09  mov     rbx, [rsp+140h+arg_8]
0x180026b11  add     rsp, 110h
0x180026b18  pop     r15
0x180026b1a  pop     r14
0x180026b1c  pop     r13
0x180026b1e  pop     r12
0x180026b20  pop     rdi
0x180026b21  pop     rsi
0x180026b22  pop     rbp
0x180026b23  retn
0x180026b24  mov     r9d, eax; char *
0x180026b27  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180026b2e  mov     edx, 197h; void *
0x180026b33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026b39  mov     r9d, 8007139Fh; char *
0x180026b3f  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180026b46  mov     edx, 138h; void *
0x180026b4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026b51  mov     r9d, 80070057h; char *
0x180026b57  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180026b5e  mov     edx, 13Bh; void *
0x180026b63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026b69  mov     r9d, 83760002h; char *
0x180026b6f  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180026b76  mov     edx, 18Dh; void *
0x180026b7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026b81  mov     r9d, eax; char *
0x180026b84  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180026b8b  mov     edx, 199h; void *
0x180026b90  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026b96  mov     r9d, eax; char *
0x180026b99  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180026ba0  mov     edx, 198h; void *
0x180026ba5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::MakeTlsAlertWithAlertNumber(uint)

- ea: `0x18001d040`
- end: `0x18001d242`
- name: `?MakeTlsAlertWithAlertNumber@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@QEAA?AUIBuffer@Streams@Storage@67@I@Z`
- size: `514`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001cf40`
- `0x18001cfe0`

## callees

- `0x1800021d0`
- `0x1800101c4`
- `0x180010df0`
- `0x18001d040`
- `0x18002de70`
- `0x18002e5f4`

## import_xrefs

- `SspiCli!FreeContextBuffer` at `0x18001d1ca`
- `SspiCli!FreeContextBuffer` at `0x18001d1ca`
- `SspiCli!InitializeSecurityContextW` at `0x18001d154`
- `SspiCli!InitializeSecurityContextW` at `0x18001d154`
- `SspiCli!ApplyControlToken` at `0x18001d0b1`
- `SspiCli!ApplyControlToken` at `0x18001d0b1`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::MakeTlsAlertWithAlertNumber(
        __int64 a1,
        _QWORD *a2,
        int a3)
{
  bool v5; // bl
  int v6; // eax
  unsigned int v7; // eax
  bool v8; // r8
  unsigned int Reserved1; // [rsp+20h] [rbp-E0h]
  unsigned int Reserved1a; // [rsp+20h] [rbp-E0h]
  _DWORD v12[2]; // [rsp+60h] [rbp-A0h] BYREF
  PVOID pvContextBuffer; // [rsp+68h] [rbp-98h]
  unsigned int pfContextAttr[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v15[2]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v16; // [rsp+88h] [rbp-78h]
  struct _SecBufferDesc pInput; // [rsp+90h] [rbp-70h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+A0h] [rbp-60h] BYREF
  struct _SecBufferDesc v19; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v20[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v21; // [rsp+C8h] [rbp-38h]
  __int64 v22; // [rsp+D0h] [rbp-30h]
  __int64 v23; // [rsp+D8h] [rbp-28h]
  _QWORD v24[3]; // [rsp+E0h] [rbp-20h] BYREF
  char v25; // [rsp+F8h] [rbp-8h]
  _DWORD v26[4]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *(_QWORD *)pfContextAttr = a2;
  v26[0] = 2;
  v26[1] = 2;
  v26[2] = a3;
  v15[0] = 12;
  v15[1] = 2;
  v16 = v26;
  pInput.ulVersion = 0;
  v5 = 1;
  pInput.cBuffers = 1;
  pInput.pBuffers = (PSecBuffer)v15;
  v6 = ApplyControlToken((PCtxtHandle)(a1 + 120), &pInput) | 0x10000000;
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44B,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)(unsigned int)v6,
      Reserved1);
  v20[0] = 0;
  v20[1] = 2;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v19.ulVersion = 0;
  v19.cBuffers = 2;
  v19.pBuffers = (PSecBuffer)v20;
  v12[0] = 0;
  v12[1] = 2;
  pvContextBuffer = 0;
  pOutput.ulVersion = 0;
  pOutput.cBuffers = 1;
  pOutput.pBuffers = (PSecBuffer)v12;
  pfContextAttr[0] = 0;
  v7 = InitializeSecurityContextW(
         (PCredHandle)(a1 + 104),
         (PCtxtHandle)(a1 + 120),
         0,
         0x819Cu,
         0,
         0,
         &v19,
         0,
         0,
         &pOutput,
         pfContextAttr,
         0);
  winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(
    (winrt::Windows::Internal::Eap::Utility::implementation *)v7,
    v7 >> 31,
    v8);
  v24[2] = v12;
  v25 = 1;
  if ( pvContextBuffer )
    v5 = v12[0] == 0;
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x471,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)0x90090304LL,
      Reserved1a);
  if ( HIDWORD(v22) == 5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)0x90090304LL,
      Reserved1a);
  if ( !pvContextBuffer && v12[0] )
    gsl::details::terminate(0);
  v24[0] = v12[0];
  v24[1] = pvContextBuffer;
  winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(a2, (unsigned int *)v24);
  if ( pvContextBuffer )
    FreeContextBuffer(pvContextBuffer);
  return a2;
}

```

## disassembly

```asm
0x18001d040  push    rbp
0x18001d042  push    rbx
0x18001d043  push    rsi
0x18001d044  push    rdi
0x18001d045  push    r12
0x18001d047  push    r14
0x18001d049  push    r15
0x18001d04b  lea     rbp, [rsp-20h]
0x18001d050  sub     rsp, 120h
0x18001d057  mov     rax, cs:__security_cookie
0x18001d05e  xor     rax, rsp
0x18001d061  mov     [rbp+50h+var_40], rax
0x18001d065  mov     rdi, rdx
0x18001d068  mov     rsi, rcx
0x18001d06b  mov     qword ptr [rsp+150h+var_E0], rdx
0x18001d070  xor     r15d, r15d
0x18001d073  lea     r12d, [r15+2]
0x18001d077  mov     [rbp+50h+var_50], r12d
0x18001d07b  mov     [rbp+50h+var_4C], r12d
0x18001d07f  mov     [rbp+50h+var_48], r8d
0x18001d083  mov     [rbp+50h+var_D0], 0Ch
0x18001d08a  mov     [rbp+50h+var_CC], r12d
0x18001d08e  lea     rax, [rbp+50h+var_50]
0x18001d092  mov     [rbp+50h+var_C8], rax
0x18001d096  mov     [rbp+50h+pInput.ulVersion], r15d
0x18001d09a  lea     ebx, [r15+1]
0x18001d09e  mov     [rbp+50h+pInput.cBuffers], ebx
0x18001d0a1  lea     rax, [rbp+50h+var_D0]
0x18001d0a5  mov     [rbp+50h+pInput.pBuffers], rax
0x18001d0a9  lea     rdx, [rbp+50h+pInput]; pInput
0x18001d0ad  add     rcx, 78h ; 'x'; phContext
0x18001d0b1  call    cs:__imp_ApplyControlToken
0x18001d0b7  or      eax, 10000000h
0x18001d0bc  mov     rcx, [rbp+58h]; this
0x18001d0c0  jl      loc_18001D1F7
0x18001d0c6  mov     [rbp+50h+var_90], r15d
0x18001d0ca  mov     [rbp+50h+var_8C], r12d
0x18001d0ce  mov     [rbp+50h+var_88], r15
0x18001d0d2  mov     [rbp+50h+var_80], r15
0x18001d0d6  mov     [rbp+50h+var_78], r15
0x18001d0da  mov     [rbp+50h+var_A0.ulVersion], r15d
0x18001d0de  mov     [rbp+50h+var_A0.cBuffers], r12d
0x18001d0e2  lea     rax, [rbp+50h+var_90]
0x18001d0e6  mov     [rbp+50h+var_A0.pBuffers], rax
0x18001d0ea  mov     [rsp+150h+var_F0], r15d
0x18001d0ef  mov     [rsp+150h+var_EC], r12d
0x18001d0f4  mov     [rsp+150h+pvContextBuffer], r15
0x18001d0f9  mov     [rbp+50h+var_B0.ulVersion], r15d
0x18001d0fd  mov     [rbp+50h+var_B0.cBuffers], ebx
0x18001d100  lea     rax, [rsp+150h+var_F0]
0x18001d105  mov     [rbp+50h+var_B0.pBuffers], rax
0x18001d109  mov     [rsp+150h+var_E0], r15d
0x18001d10e  lea     rcx, [rsi+68h]; phCredential
0x18001d112  mov     [rsp+150h+ptsExpiry], r15; ptsExpiry
0x18001d117  lea     rax, [rsp+150h+var_E0]
0x18001d11c  mov     [rsp+150h+pfContextAttr], rax; pfContextAttr
0x18001d121  lea     rax, [rbp+50h+var_B0]
0x18001d125  mov     [rsp+150h+pOutput], rax; pOutput
0x18001d12a  mov     [rsp+150h+phNewContext], r15; phNewContext
0x18001d12f  mov     [rsp+150h+Reserved2], r15d; Reserved2
0x18001d134  lea     rax, [rbp+50h+var_A0]
0x18001d138  mov     [rsp+150h+var_120], rax; pInput
0x18001d13d  mov     [rsp+150h+TargetDataRep], r15d; TargetDataRep
0x18001d142  mov     [rsp+150h+Reserved1], r15d; int
0x18001d147  mov     r9d, 819Ch; fContextReq
0x18001d14d  xor     r8d, r8d; pszTargetName
0x18001d150  lea     rdx, [rsi+78h]; phContext
0x18001d154  call    cs:__imp_InitializeSecurityContextW
0x18001d15a  mov     edx, eax
0x18001d15c  shr     edx, 1Fh; int
0x18001d15f  mov     ecx, eax; this
0x18001d161  call    ?ThrowSecurityStatusIf@implementation@Utility@Eap@Internal@Windows@winrt@@YAXJ_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(long,bool)
0x18001d166  lea     rax, [rsp+150h+var_F0]
0x18001d16b  mov     [rbp+50h+var_60], rax
0x18001d16f  mov     [rbp+50h+var_58], bl
0x18001d172  mov     edx, [rsp+150h+var_F0]
0x18001d176  mov     rcx, [rsp+150h+pvContextBuffer]; this
0x18001d17b  test    rcx, rcx
0x18001d17e  jz      short loc_18001D187
0x18001d180  test    edx, edx
0x18001d182  jz      short loc_18001D187
0x18001d184  mov     bl, r15b
0x18001d187  mov     rax, [rbp+58h]
0x18001d18b  test    bl, bl
0x18001d18d  jnz     short loc_18001D20C
0x18001d18f  cmp     dword ptr [rbp+50h+var_80+4], 5
0x18001d193  setz    al
0x18001d196  mov     r10, [rbp+58h]
0x18001d19a  test    al, al
0x18001d19c  jnz     loc_18001D227
0x18001d1a2  test    rcx, rcx
0x18001d1a5  jnz     short loc_18001D1AB
0x18001d1a7  test    edx, edx
0x18001d1a9  jnz     short loc_18001D1F1
0x18001d1ab  mov     [rbp+50h+var_70], rdx
0x18001d1af  mov     [rbp+50h+var_68], rcx
0x18001d1b3  lea     rdx, [rbp+50h+var_70]
0x18001d1b7  mov     rcx, rdi
0x18001d1ba  call    ?AllocateIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(gsl::span<uchar,-1>)
0x18001d1bf  nop
0x18001d1c0  mov     rcx, [rsp+150h+pvContextBuffer]; pvContextBuffer
0x18001d1c5  test    rcx, rcx
0x18001d1c8  jz      short loc_18001D1D0
0x18001d1ca  call    cs:__imp_FreeContextBuffer
0x18001d1d0  mov     rax, rdi
0x18001d1d3  mov     rcx, [rbp+50h+var_40]
0x18001d1d7  xor     rcx, rsp; StackCookie
0x18001d1da  call    __security_check_cookie
0x18001d1df  add     rsp, 120h
0x18001d1e6  pop     r15
0x18001d1e8  pop     r14
0x18001d1ea  pop     r12
0x18001d1ec  pop     rdi
0x18001d1ed  pop     rsi
0x18001d1ee  pop     rbx
0x18001d1ef  pop     rbp
0x18001d1f0  retn
0x18001d1f1  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x18001d1f7  mov     r9d, eax; char *
0x18001d1fa  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001d201  mov     edx, 44Bh; void *
0x18001d206  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d20c  mov     r9d, 90090304h; char *
0x18001d212  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001d219  mov     edx, 471h; void *
0x18001d21e  mov     rcx, rax; this
0x18001d221  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d227  mov     r9d, 90090304h; char *
0x18001d22d  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001d234  mov     edx, 472h; void *
0x18001d239  mov     rcx, r10; this
0x18001d23c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

# winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::MakeTlsAlertWithAlertNumber(uint)

- ea: `0x180028ad0`
- end: `0x180028cda`
- name: `?MakeTlsAlertWithAlertNumber@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@QEAA?AUIBuffer@Streams@Storage@67@I@Z`
- size: `522`
- prototype: `_QWORD *__fastcall(struct _SecHandle *, _QWORD *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180028a70`

## callees

- `0x1800021d0`
- `0x1800101c4`
- `0x180010df0`
- `0x180028ad0`
- `0x18002de70`

## import_xrefs

- `SspiCli!FreeContextBuffer` at `0x180028c4d`
- `SspiCli!FreeContextBuffer` at `0x180028c4d`
- `SspiCli!AcceptSecurityContext` at `0x180028bd3`
- `SspiCli!AcceptSecurityContext` at `0x180028bd3`
- `SspiCli!ApplyControlToken` at `0x180028b45`
- `SspiCli!ApplyControlToken` at `0x180028b45`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::MakeTlsAlertWithAlertNumber(
        struct _SecHandle *a1,
        _QWORD *a2,
        int a3)
{
  bool v5; // bl
  SECURITY_STATUS v6; // eax
  SECURITY_STATUS v7; // eax
  unsigned int TargetDataRep; // [rsp+20h] [rbp-E0h]
  unsigned int TargetDataRepa; // [rsp+20h] [rbp-E0h]
  _DWORD v11[2]; // [rsp+50h] [rbp-B0h] BYREF
  PVOID pvContextBuffer; // [rsp+58h] [rbp-A8h]
  unsigned int pfContextAttr[4]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v14[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v15; // [rsp+78h] [rbp-88h]
  struct _SecBufferDesc pInput; // [rsp+80h] [rbp-80h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+90h] [rbp-70h] BYREF
  struct _SecBufferDesc v18; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v19[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v20; // [rsp+B8h] [rbp-48h]
  __int64 v21; // [rsp+C0h] [rbp-40h]
  __int64 v22; // [rsp+C8h] [rbp-38h]
  _QWORD v23[3]; // [rsp+D0h] [rbp-30h] BYREF
  char v24; // [rsp+E8h] [rbp-18h]
  _DWORD v25[4]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *(_QWORD *)pfContextAttr = a2;
  v25[0] = 2;
  v25[1] = 2;
  v25[2] = a3;
  v14[0] = 12;
  v14[1] = 2;
  v15 = v25;
  pInput.ulVersion = 0;
  v5 = 1;
  pInput.cBuffers = 1;
  pInput.pBuffers = (PSecBuffer)v14;
  v6 = ApplyControlToken(a1 + 2, &pInput);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)(unsigned int)v6,
      TargetDataRep);
  v19[0] = 0;
  v19[1] = 2;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v18.ulVersion = 0;
  v18.cBuffers = 2;
  v18.pBuffers = (PSecBuffer)v19;
  v11[0] = 0;
  v11[1] = 2;
  pvContextBuffer = 0;
  pOutput.ulVersion = 0;
  pOutput.cBuffers = 1;
  pOutput.pBuffers = (PSecBuffer)v11;
  pfContextAttr[0] = 0;
  v7 = AcceptSecurityContext(a1 + 3, a1 + 2, &v18, 0x1811Eu, 0, 0, &pOutput, pfContextAttr, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C1,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)(unsigned int)v7,
      TargetDataRepa);
  v23[2] = v11;
  v24 = 1;
  if ( pvContextBuffer )
    v5 = v11[0] == 0;
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)0x80090304LL,
      TargetDataRepa);
  if ( HIDWORD(v21) == 5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D2,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)0x80090304LL,
      TargetDataRepa);
  if ( !pvContextBuffer && v11[0] )
    gsl::details::terminate(0);
  v23[0] = v11[0];
  v23[1] = pvContextBuffer;
  winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(a2, (unsigned int *)v23);
  if ( pvContextBuffer )
    FreeContextBuffer(pvContextBuffer);
  return a2;
}

```

## disassembly

```asm
0x180028ad0  push    rbp
0x180028ad2  push    rbx
0x180028ad3  push    rsi
0x180028ad4  push    rdi
0x180028ad5  push    r12
0x180028ad7  push    r14
0x180028ad9  push    r15
0x180028adb  lea     rbp, [rsp-10h]
0x180028ae0  sub     rsp, 110h
0x180028ae7  mov     rax, cs:__security_cookie
0x180028aee  xor     rax, rsp
0x180028af1  mov     [rbp+40h+var_40], rax
0x180028af5  mov     rdi, rdx
0x180028af8  mov     rsi, rcx
0x180028afb  mov     qword ptr [rsp+140h+var_E0], rdx
0x180028b00  xor     r15d, r15d
0x180028b03  lea     r12d, [r15+2]
0x180028b07  mov     [rbp+40h+var_50], r12d
0x180028b0b  mov     [rbp+40h+var_4C], r12d
0x180028b0f  mov     [rbp+40h+var_48], r8d
0x180028b13  mov     [rsp+140h+var_D0], 0Ch
0x180028b1b  mov     [rsp+140h+var_CC], r12d
0x180028b20  lea     rax, [rbp+40h+var_50]
0x180028b24  mov     [rsp+140h+var_C8], rax
0x180028b29  mov     [rbp+40h+pInput.ulVersion], r15d
0x180028b2d  lea     ebx, [r15+1]
0x180028b31  mov     [rbp+40h+pInput.cBuffers], ebx
0x180028b34  lea     rax, [rsp+140h+var_D0]
0x180028b39  mov     [rbp+40h+pInput.pBuffers], rax
0x180028b3d  lea     rdx, [rbp+40h+pInput]; pInput
0x180028b41  add     rcx, 20h ; ' '; phContext
0x180028b45  call    cs:__imp_ApplyControlToken
0x180028b4b  mov     rcx, [rbp+48h]; this
0x180028b4f  test    eax, eax
0x180028b51  js      loc_180028C7A
0x180028b57  mov     [rbp+40h+var_90], r15d
0x180028b5b  mov     [rbp+40h+var_8C], r12d
0x180028b5f  mov     [rbp+40h+var_88], r15
0x180028b63  mov     [rbp+40h+var_80], r15
0x180028b67  mov     [rbp+40h+var_78], r15
0x180028b6b  mov     [rbp+40h+var_A0.ulVersion], r15d
0x180028b6f  mov     [rbp+40h+var_A0.cBuffers], r12d
0x180028b73  lea     rax, [rbp+40h+var_90]
0x180028b77  mov     [rbp+40h+var_A0.pBuffers], rax
0x180028b7b  mov     [rsp+140h+var_F0], r15d
0x180028b80  mov     [rsp+140h+var_EC], r12d
0x180028b85  mov     [rsp+140h+pvContextBuffer], r15
0x180028b8a  mov     [rbp+40h+var_B0.ulVersion], r15d
0x180028b8e  mov     [rbp+40h+var_B0.cBuffers], ebx
0x180028b91  lea     rax, [rsp+140h+var_F0]
0x180028b96  mov     [rbp+40h+var_B0.pBuffers], rax
0x180028b9a  mov     [rsp+140h+var_E0], r15d
0x180028b9f  lea     rcx, [rsi+30h]; phCredential
0x180028ba3  mov     [rsp+140h+ptsExpiry], r15; ptsExpiry
0x180028ba8  lea     rax, [rsp+140h+var_E0]
0x180028bad  mov     [rsp+140h+pfContextAttr], rax; pfContextAttr
0x180028bb2  lea     rax, [rbp+40h+var_B0]
0x180028bb6  mov     [rsp+140h+pOutput], rax; pOutput
0x180028bbb  mov     [rsp+140h+phNewContext], r15; phNewContext
0x180028bc0  mov     [rsp+140h+TargetDataRep], r15d; int
0x180028bc5  mov     r9d, 1811Eh; fContextReq
0x180028bcb  lea     r8, [rbp+40h+var_A0]; pInput
0x180028bcf  lea     rdx, [rsi+20h]; phContext
0x180028bd3  call    cs:__imp_AcceptSecurityContext
0x180028bd9  mov     rcx, [rbp+48h]; this
0x180028bdd  test    eax, eax
0x180028bdf  js      loc_180028C8F
0x180028be5  lea     rax, [rsp+140h+var_F0]
0x180028bea  mov     [rbp+40h+var_60], rax
0x180028bee  mov     [rbp+40h+var_58], bl
0x180028bf1  mov     edx, [rsp+140h+var_F0]
0x180028bf5  mov     rcx, [rsp+140h+pvContextBuffer]; this
0x180028bfa  test    rcx, rcx
0x180028bfd  jz      short loc_180028C06
0x180028bff  test    edx, edx
0x180028c01  jz      short loc_180028C06
0x180028c03  mov     bl, r15b
0x180028c06  mov     rax, [rbp+48h]
0x180028c0a  test    bl, bl
0x180028c0c  jnz     loc_180028CA4
0x180028c12  cmp     dword ptr [rbp+40h+var_80+4], 5
0x180028c16  setz    al
0x180028c19  mov     r10, [rbp+48h]
0x180028c1d  test    al, al
0x180028c1f  jnz     loc_180028CBF
0x180028c25  test    rcx, rcx
0x180028c28  jnz     short loc_180028C2E
0x180028c2a  test    edx, edx
0x180028c2c  jnz     short loc_180028C74
0x180028c2e  mov     [rbp+40h+var_70], rdx
0x180028c32  mov     [rbp+40h+var_68], rcx
0x180028c36  lea     rdx, [rbp+40h+var_70]
0x180028c3a  mov     rcx, rdi
0x180028c3d  call    ?AllocateIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(gsl::span<uchar,-1>)
0x180028c42  nop
0x180028c43  mov     rcx, [rsp+140h+pvContextBuffer]; pvContextBuffer
0x180028c48  test    rcx, rcx
0x180028c4b  jz      short loc_180028C53
0x180028c4d  call    cs:__imp_FreeContextBuffer
0x180028c53  mov     rax, rdi
0x180028c56  mov     rcx, [rbp+40h+var_40]
0x180028c5a  xor     rcx, rsp; StackCookie
0x180028c5d  call    __security_check_cookie
0x180028c62  add     rsp, 110h
0x180028c69  pop     r15
0x180028c6b  pop     r14
0x180028c6d  pop     r12
0x180028c6f  pop     rdi
0x180028c70  pop     rsi
0x180028c71  pop     rbx
0x180028c72  pop     rbp
0x180028c73  retn
0x180028c74  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x180028c7a  mov     r9d, eax; char *
0x180028c7d  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180028c84  mov     edx, 1B7h; void *
0x180028c89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028c8f  mov     r9d, eax; char *
0x180028c92  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180028c99  mov     edx, 1C1h; void *
0x180028c9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028ca4  mov     r9d, 80090304h; char *
0x180028caa  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180028cb1  mov     edx, 1D1h; void *
0x180028cb6  mov     rcx, rax; this
0x180028cb9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028cbf  mov     r9d, 80090304h; char *
0x180028cc5  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180028ccc  mov     edx, 1D2h; void *
0x180028cd1  mov     rcx, r10; this
0x180028cd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

# SAMLAssertionTokenRequest::AcquireToken(CSecureString const &,SamlAssertionType)

- ea: `0x140018000`
- end: `0x1400180b0`
- name: `?AcquireToken@SAMLAssertionTokenRequest@@UEAA_NAEBVCSecureString@@W4SamlAssertionType@@@Z`
- size: `176`
- prototype: `char __fastcall(struct OAuthTokenRequestBase *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140016a04`

## callees

- `0x14000579c`
- `0x140008ba8`
- `0x140014ea4`
- `0x140018000`
- `0x1400180b8`
- `0x14001e1a8`
- `0x140030010`

## pseudocode

```c
char __fastcall SAMLAssertionTokenRequest::AcquireToken(struct OAuthTokenRequestBase *a1, __int64 a2, unsigned int a3)
{
  char v4; // bl
  _QWORD *v5; // rdx
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64); // [rsp+40h] [rbp+8h] BYREF
  char v9; // [rsp+58h] [rbp+20h] BYREF

  SAMLAssertionTokenRequest::BuildTokenRequestMessageForAssertions(a1, &v9, a2, a3);
  AuthenticationContext::GetTokenEndpoint(*((_QWORD *)a1 + 1), v7);
  WebRequestFactory::CreateBasicConnection(&v8, *((_QWORD *)a1 + 1), 0);
  v4 = OAuthTokenRequestBase::ProcessTokenRequest(a1);
  if ( v8 )
    (**v8)(v8, 1);
  v5 = (_QWORD *)(v7[0] - 24LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7[0] - 24LL + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  CSecureString::~CSecureString((CSecureString *)&v9);
  return v4;
}

```

## disassembly

```asm
0x140018000  mov     [rsp+arg_8], rbx
0x140018005  push    rdi
0x140018006  sub     rsp, 30h
0x14001800a  mov     rdi, rcx
0x14001800d  mov     r9d, r8d
0x140018010  mov     r8, rdx
0x140018013  lea     rdx, [rsp+38h+arg_18]
0x140018018  call    ?BuildTokenRequestMessageForAssertions@SAMLAssertionTokenRequest@@AEAA?AVCSecureString@@AEBV2@W4SamlAssertionType@@@Z; SAMLAssertionTokenRequest::BuildTokenRequestMessageForAssertions(CSecureString const &,SamlAssertionType)
0x14001801d  nop
0x14001801e  lea     rdx, [rsp+38h+var_18]
0x140018023  mov     rcx, [rdi+8]
0x140018027  call    ?GetTokenEndpoint@AuthenticationContext@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; AuthenticationContext::GetTokenEndpoint(void)
0x14001802c  mov     rbx, rax
0x14001802f  xor     r8d, r8d
0x140018032  mov     rdx, [rdi+8]
0x140018036  lea     rcx, [rsp+38h+arg_0]
0x14001803b  call    ?CreateBasicConnection@WebRequestFactory@@CA?AV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVAuthenticationContext@@_N@Z; WebRequestFactory::CreateBasicConnection(AuthenticationContext const &,bool)
0x140018040  nop
0x140018041  mov     r9, rbx
0x140018044  lea     r8, [rsp+38h+arg_18]
0x140018049  lea     rdx, [rsp+38h+arg_0]
0x14001804e  mov     rcx, rdi; struct OAuthTokenRequestBase *
0x140018051  call    ?ProcessTokenRequest@OAuthTokenRequestBase@@IEAA_NAEBV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; OAuthTokenRequestBase::ProcessTokenRequest(std::unique_ptr<WebRequest> const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140018056  mov     bl, al
0x140018058  mov     rcx, [rsp+38h+arg_0]
0x14001805d  test    rcx, rcx
0x140018060  jz      short loc_140018073
0x140018062  mov     rdx, [rcx]
0x140018065  mov     rax, [rdx]
0x140018068  mov     edx, 1
0x14001806d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018072  nop
0x140018073  mov     rdx, [rsp+38h+var_18]
0x140018078  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001807c  or      eax, 0FFFFFFFFh
0x14001807f  lock xadd [rdx+10h], eax
0x140018084  sub     eax, 1
0x140018087  jg      short loc_140018099
0x140018089  mov     rcx, [rdx]
0x14001808c  mov     rax, [rcx]
0x14001808f  mov     rax, [rax+8]
0x140018093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018098  nop
0x140018099  lea     rcx, [rsp+38h+arg_18]; this
0x14001809e  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400180a3  mov     al, bl
0x1400180a5  mov     rbx, [rsp+38h+arg_8]
0x1400180aa  add     rsp, 30h
0x1400180ae  pop     rdi
0x1400180af  retn
```

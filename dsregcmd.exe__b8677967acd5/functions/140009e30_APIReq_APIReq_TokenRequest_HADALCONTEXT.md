# APIReq::APIReq(TokenRequest *,HADALCONTEXT__ *)

- ea: `0x140009e30`
- end: `0x140009f21`
- name: `??0APIReq@@AEAA@PEAVTokenRequest@@PEAUHADALCONTEXT__@@@Z`
- size: `241`
- prototype: `APIReq *__fastcall(APIReq *__hidden this, struct TokenRequest *, struct HADALCONTEXT__ *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000651c`

## callees

- `0x140001814`
- `0x140006484`
- `0x140009e30`
- `0x140009f58`
- `0x14000e020`
- `0x14002c3e8`

## string_xrefs

- `0x140009e66`: `onecore\ds\security\dsreg\win32\adal.native\APIHandle.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
APIReq *__fastcall APIReq::APIReq(APIReq *this, struct TokenRequest *a2, struct HADALCONTEXT__ *a3)
{
  _QWORD *v5; // rbx
  __int64 v6; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-18h] BYREF
  _QWORD *v9; // [rsp+40h] [rbp+8h] BYREF

  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = a2;
  v5 = operator new(0x20u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\APIHandle.h", 68);
  v9 = v5;
  if ( v5 )
  {
    if ( !a3 || !(unsigned __int8)APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254>::Validate(a3) )
    {
      InvalidHandleException::InvalidHandleException((InvalidHandleException *)pExceptionObject, 0xCAA1000E);
      throw (InvalidHandleException *)pExceptionObject;
    }
    v5[1] = 0;
    v5[2] = 0;
    v6 = *((_QWORD *)a3 + 2);
    if ( v6 )
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
    v5[1] = *((_QWORD *)a3 + 1);
    v5[2] = *((_QWORD *)a3 + 2);
    *(_DWORD *)v5 = -1441095254;
    *((_BYTE *)v5 + 24) = 0;
  }
  else
  {
    v5 = 0;
  }
  *((_BYTE *)v5 + 24) = 1;
  v9 = 0;
  std::unique_ptr<APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254>>::~unique_ptr<APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254>>(&v9);
  *((_QWORD *)this + 3) = v5;
  return this;
}

```

## disassembly

```asm
0x140009e30  mov     [rsp+arg_8], rbx
0x140009e35  mov     [rsp+arg_10], rsi
0x140009e3a  push    rdi
0x140009e3b  sub     rsp, 30h
0x140009e3f  mov     rdi, r8
0x140009e42  mov     rsi, rcx
0x140009e45  mov     qword ptr [rcx+20h], 0
0x140009e4d  mov     qword ptr [rcx], 0
0x140009e54  mov     qword ptr [rcx+8], 0
0x140009e5c  mov     [rcx+10h], rdx
0x140009e60  mov     r9d, 44h ; 'D'; int
0x140009e66  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140009e6d  lea     edx, [r9-43h]; int
0x140009e71  lea     ecx, [rdx+1Fh]; unsigned __int64
0x140009e74  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140009e79  mov     rbx, rax
0x140009e7c  mov     [rsp+38h+arg_0], rax
0x140009e81  test    rax, rax
0x140009e84  jz      short loc_140009ED0
0x140009e86  test    rdi, rdi
0x140009e89  jz      short loc_140009F00
0x140009e8b  mov     rcx, rdi
0x140009e8e  call    ?Validate@?$APIHandle@VAuthenticationContext@@PEAUHADALCONTEXT__@@$0?FFOFFOFG@@@CA_NPEBV1@@Z; APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254>::Validate(APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254> const *)
0x140009e93  test    al, al
0x140009e95  jz      short loc_140009F00
0x140009e97  mov     qword ptr [rbx+8], 0
0x140009e9f  mov     qword ptr [rbx+10h], 0
0x140009ea7  mov     rax, [rdi+10h]
0x140009eab  test    rax, rax
0x140009eae  jz      short loc_140009EB4
0x140009eb0  lock inc dword ptr [rax+8]
0x140009eb4  mov     rax, [rdi+8]
0x140009eb8  mov     [rbx+8], rax
0x140009ebc  mov     rax, [rdi+10h]
0x140009ec0  mov     [rbx+10h], rax
0x140009ec4  mov     dword ptr [rbx], 0AA1AA1AAh
0x140009eca  mov     byte ptr [rbx+18h], 0
0x140009ece  jmp     short loc_140009ED2
0x140009ed0  xor     ebx, ebx
0x140009ed2  mov     byte ptr [rbx+18h], 1
0x140009ed6  mov     [rsp+38h+arg_0], 0
0x140009edf  lea     rcx, [rsp+38h+arg_0]
0x140009ee4  call    ??1?$unique_ptr@V?$APIHandle@VAuthenticationContext@@PEAUHADALCONTEXT__@@$0?FFOFFOFG@@@U?$default_delete@V?$APIHandle@VAuthenticationContext@@PEAUHADALCONTEXT__@@$0?FFOFFOFG@@@@std@@@std@@QEAA@XZ; std::unique_ptr<APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254>>::~unique_ptr<APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254>>(void)
0x140009ee9  mov     [rsi+18h], rbx
0x140009eed  mov     rax, rsi
0x140009ef0  mov     rbx, [rsp+38h+arg_8]
0x140009ef5  mov     rsi, [rsp+38h+arg_10]
0x140009efa  add     rsp, 30h
0x140009efe  pop     rdi
0x140009eff  retn
0x140009f00  mov     edx, 0CAA1000Eh; unsigned int
0x140009f05  lea     rcx, [rsp+38h+pExceptionObject]; this
0x140009f0a  call    ??0InvalidHandleException@@QEAA@K@Z; InvalidHandleException::InvalidHandleException(ulong)
0x140009f0f  lea     rdx, _TI4?AVInvalidHandleException@@; pThrowInfo
0x140009f16  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x140009f1b  call    _CxxThrowException_0
```

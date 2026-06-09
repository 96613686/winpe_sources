# GetServerVariableClientCertIssuer(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x180029c70`
- end: `0x180029d6f`
- name: `?GetServerVariableClientCertIssuer@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `255`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180029c70`
- `0x18002ca5c`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180029cb1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180029cb1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029d04`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029d36`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029d04`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029d36`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029ccf`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029d29`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029ccf`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029d29`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180029d1b`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180029d1b`

## pseudocode

```c
__int64 __fastcall GetServerVariableClientCertIssuer(
        struct W3_CONTEXT *a1,
        const unsigned __int16 **a2,
        unsigned int *a3)
{
  CERTIFICATE_CONTEXT *v6; // rbx
  int Issuer; // ebx
  unsigned int v8; // edx
  __int64 v9; // rax
  unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // rbx
  unsigned int v13; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v14[56]; // [rsp+28h] [rbp-60h] BYREF

  v6 = *(CERTIFICATE_CONTEXT **)(*((_QWORD *)a1 + 49) + 9480LL);
  if ( v6 )
  {
    STRU::STRU((STRU *)v14);
    Issuer = CERTIFICATE_CONTEXT::GetIssuer(v6, (struct STRU *)v14);
    if ( Issuer < 0 )
    {
LABEL_5:
      STRU::~STRU((STRU *)v14);
      return (unsigned int)Issuer;
    }
    v8 = 2 * STRU::QueryCCH((STRU *)v14) + 2;
    v9 = *(_QWORD *)a1;
    v13 = v8;
    v10 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *))(v9 + 144))(a1);
    v11 = v10;
    if ( !v10 )
    {
      Issuer = -2147024888;
      goto LABEL_5;
    }
    STRU::CopyToBuffer((STRU *)v14, v10, &v13);
    *a2 = v11;
    *a3 = STRU::QueryCCH((STRU *)v14);
    STRU::~STRU((STRU *)v14);
  }
  else
  {
    *a2 = &dword_180039134;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180029c70  mov     [rsp+arg_18], rbx
0x180029c75  push    rsi
0x180029c76  push    rdi
0x180029c77  push    r14
0x180029c79  sub     rsp, 70h
0x180029c7d  mov     rax, cs:__security_cookie
0x180029c84  xor     rax, rsp
0x180029c87  mov     [rsp+88h+var_28], rax
0x180029c8c  mov     rax, [rcx+188h]
0x180029c93  mov     rsi, r8
0x180029c96  mov     rdi, rdx
0x180029c99  mov     r14, rcx
0x180029c9c  mov     rbx, [rax+2508h]
0x180029ca3  test    rbx, rbx
0x180029ca6  jz      loc_180029D3E
0x180029cac  lea     rcx, [rsp+88h+var_60]
0x180029cb1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180029cb7  lea     rdx, [rsp+88h+var_60]; struct STRU *
0x180029cbc  mov     rcx, rbx; this
0x180029cbf  call    ?GetIssuer@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z; CERTIFICATE_CONTEXT::GetIssuer(STRU *)
0x180029cc4  mov     ebx, eax
0x180029cc6  test    eax, eax
0x180029cc8  js      short loc_180029CFF
0x180029cca  lea     rcx, [rsp+88h+var_60]
0x180029ccf  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180029cd5  mov     rcx, r14
0x180029cd8  lea     edx, ds:2[rax*2]
0x180029cdf  mov     rax, [r14]
0x180029ce2  mov     [rsp+88h+var_68], edx
0x180029ce6  mov     rax, [rax+90h]
0x180029ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cf2  mov     rbx, rax
0x180029cf5  test    rax, rax
0x180029cf8  jnz     short loc_180029D0E
0x180029cfa  mov     ebx, 80070008h
0x180029cff  lea     rcx, [rsp+88h+var_60]
0x180029d04  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180029d0a  mov     eax, ebx
0x180029d0c  jmp     short loc_180029D51
0x180029d0e  lea     r8, [rsp+88h+var_68]
0x180029d13  mov     rdx, rbx
0x180029d16  lea     rcx, [rsp+88h+var_60]
0x180029d1b  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x180029d21  lea     rcx, [rsp+88h+var_60]
0x180029d26  mov     [rdi], rbx
0x180029d29  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180029d2f  lea     rcx, [rsp+88h+var_60]
0x180029d34  mov     [rsi], eax
0x180029d36  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180029d3c  jmp     short loc_180029D4F
0x180029d3e  lea     rax, dword_180039134
0x180029d45  mov     [rdx], rax
0x180029d48  mov     dword ptr [r8], 0
0x180029d4f  xor     eax, eax
0x180029d51  mov     rcx, [rsp+88h+var_28]
0x180029d56  xor     rcx, rsp; StackCookie
0x180029d59  call    __security_check_cookie
0x180029d5e  mov     rbx, [rsp+88h+arg_18]
0x180029d66  add     rsp, 70h
0x180029d6a  pop     r14
0x180029d6c  pop     rdi
0x180029d6d  pop     rsi
0x180029d6e  retn
```

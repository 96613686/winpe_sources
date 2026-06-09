# GetServerVariableClientCertIssuer(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x18002c180`
- end: `0x18002c2a4`
- name: `?GetServerVariableClientCertIssuer@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002c180`
- `0x18002f340`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18002c1c1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002c1c1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c220`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c264`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c220`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c264`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c1e5`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c251`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c1e5`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c251`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002c23d`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002c23d`

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
    *a2 = &dword_18003C134;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002c180  mov     [rsp+arg_18], rbx
0x18002c185  push    rsi
0x18002c186  push    rdi
0x18002c187  push    r14
0x18002c189  sub     rsp, 70h
0x18002c18d  mov     rax, cs:__security_cookie
0x18002c194  xor     rax, rsp
0x18002c197  mov     [rsp+88h+var_28], rax
0x18002c19c  mov     rax, [rcx+188h]
0x18002c1a3  mov     rsi, r8
0x18002c1a6  mov     rdi, rdx
0x18002c1a9  mov     r14, rcx
0x18002c1ac  mov     rbx, [rax+2508h]
0x18002c1b3  test    rbx, rbx
0x18002c1b6  jz      loc_18002C272
0x18002c1bc  lea     rcx, [rsp+88h+var_60]
0x18002c1c1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002c1c8  nop     dword ptr [rax+rax+00h]
0x18002c1cd  lea     rdx, [rsp+88h+var_60]; struct STRU *
0x18002c1d2  mov     rcx, rbx; this
0x18002c1d5  call    ?GetIssuer@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z; CERTIFICATE_CONTEXT::GetIssuer(STRU *)
0x18002c1da  mov     ebx, eax
0x18002c1dc  test    eax, eax
0x18002c1de  js      short loc_18002C21B
0x18002c1e0  lea     rcx, [rsp+88h+var_60]
0x18002c1e5  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002c1ec  nop     dword ptr [rax+rax+00h]
0x18002c1f1  mov     rcx, r14
0x18002c1f4  lea     edx, ds:2[rax*2]
0x18002c1fb  mov     rax, [r14]
0x18002c1fe  mov     [rsp+88h+var_68], edx
0x18002c202  mov     rax, [rax+90h]
0x18002c209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c20e  mov     rbx, rax
0x18002c211  test    rax, rax
0x18002c214  jnz     short loc_18002C230
0x18002c216  mov     ebx, 80070008h
0x18002c21b  lea     rcx, [rsp+88h+var_60]
0x18002c220  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002c227  nop     dword ptr [rax+rax+00h]
0x18002c22c  mov     eax, ebx
0x18002c22e  jmp     short loc_18002C285
0x18002c230  lea     r8, [rsp+88h+var_68]
0x18002c235  mov     rdx, rbx
0x18002c238  lea     rcx, [rsp+88h+var_60]
0x18002c23d  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18002c244  nop     dword ptr [rax+rax+00h]
0x18002c249  lea     rcx, [rsp+88h+var_60]
0x18002c24e  mov     [rdi], rbx
0x18002c251  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002c258  nop     dword ptr [rax+rax+00h]
0x18002c25d  lea     rcx, [rsp+88h+var_60]
0x18002c262  mov     [rsi], eax
0x18002c264  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002c26b  nop     dword ptr [rax+rax+00h]
0x18002c270  jmp     short loc_18002C283
0x18002c272  lea     rax, dword_18003C134
0x18002c279  mov     [rdx], rax
0x18002c27c  mov     dword ptr [r8], 0
0x18002c283  xor     eax, eax
0x18002c285  mov     rcx, [rsp+88h+var_28]
0x18002c28a  xor     rcx, rsp; StackCookie
0x18002c28d  call    __security_check_cookie
0x18002c292  mov     rbx, [rsp+88h+arg_18]
0x18002c29a  add     rsp, 70h
0x18002c29e  pop     r14
0x18002c2a0  pop     rdi
0x18002c2a1  pop     rsi
0x18002c2a2  retn
```

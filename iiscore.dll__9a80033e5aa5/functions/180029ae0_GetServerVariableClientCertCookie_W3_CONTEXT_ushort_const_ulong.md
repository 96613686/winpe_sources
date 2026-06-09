# GetServerVariableClientCertCookie(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x180029ae0`
- end: `0x180029bdf`
- name: `?GetServerVariableClientCertCookie@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `255`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180029ae0`
- `0x18002c768`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180029b21`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180029b21`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029b74`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029ba6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029b74`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029ba6`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029b3f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029b99`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029b3f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029b99`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180029b8b`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180029b8b`

## pseudocode

```c
__int64 __fastcall GetServerVariableClientCertCookie(
        struct W3_CONTEXT *a1,
        const unsigned __int16 **a2,
        unsigned int *a3)
{
  CERTIFICATE_CONTEXT *v6; // rbx
  int Cookie; // ebx
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
    Cookie = CERTIFICATE_CONTEXT::GetCookie(v6, (struct STRU *)v14);
    if ( Cookie < 0 )
    {
LABEL_5:
      STRU::~STRU((STRU *)v14);
      return (unsigned int)Cookie;
    }
    v8 = 2 * STRU::QueryCCH((STRU *)v14) + 2;
    v9 = *(_QWORD *)a1;
    v13 = v8;
    v10 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *))(v9 + 144))(a1);
    v11 = v10;
    if ( !v10 )
    {
      Cookie = -2147024888;
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
0x180029ae0  mov     [rsp+arg_18], rbx
0x180029ae5  push    rsi
0x180029ae6  push    rdi
0x180029ae7  push    r14
0x180029ae9  sub     rsp, 70h
0x180029aed  mov     rax, cs:__security_cookie
0x180029af4  xor     rax, rsp
0x180029af7  mov     [rsp+88h+var_28], rax
0x180029afc  mov     rax, [rcx+188h]
0x180029b03  mov     rsi, r8
0x180029b06  mov     rdi, rdx
0x180029b09  mov     r14, rcx
0x180029b0c  mov     rbx, [rax+2508h]
0x180029b13  test    rbx, rbx
0x180029b16  jz      loc_180029BAE
0x180029b1c  lea     rcx, [rsp+88h+var_60]
0x180029b21  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180029b27  lea     rdx, [rsp+88h+var_60]; struct STRU *
0x180029b2c  mov     rcx, rbx; this
0x180029b2f  call    ?GetCookie@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z; CERTIFICATE_CONTEXT::GetCookie(STRU *)
0x180029b34  mov     ebx, eax
0x180029b36  test    eax, eax
0x180029b38  js      short loc_180029B6F
0x180029b3a  lea     rcx, [rsp+88h+var_60]
0x180029b3f  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180029b45  mov     rcx, r14
0x180029b48  lea     edx, ds:2[rax*2]
0x180029b4f  mov     rax, [r14]
0x180029b52  mov     [rsp+88h+var_68], edx
0x180029b56  mov     rax, [rax+90h]
0x180029b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b62  mov     rbx, rax
0x180029b65  test    rax, rax
0x180029b68  jnz     short loc_180029B7E
0x180029b6a  mov     ebx, 80070008h
0x180029b6f  lea     rcx, [rsp+88h+var_60]
0x180029b74  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180029b7a  mov     eax, ebx
0x180029b7c  jmp     short loc_180029BC1
0x180029b7e  lea     r8, [rsp+88h+var_68]
0x180029b83  mov     rdx, rbx
0x180029b86  lea     rcx, [rsp+88h+var_60]
0x180029b8b  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x180029b91  lea     rcx, [rsp+88h+var_60]
0x180029b96  mov     [rdi], rbx
0x180029b99  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180029b9f  lea     rcx, [rsp+88h+var_60]
0x180029ba4  mov     [rsi], eax
0x180029ba6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180029bac  jmp     short loc_180029BBF
0x180029bae  lea     rax, dword_180039134
0x180029bb5  mov     [rdx], rax
0x180029bb8  mov     dword ptr [r8], 0
0x180029bbf  xor     eax, eax
0x180029bc1  mov     rcx, [rsp+88h+var_28]
0x180029bc6  xor     rcx, rsp; StackCookie
0x180029bc9  call    __security_check_cookie
0x180029bce  mov     rbx, [rsp+88h+arg_18]
0x180029bd6  add     rsp, 70h
0x180029bda  pop     r14
0x180029bdc  pop     rdi
0x180029bdd  pop     rsi
0x180029bde  retn
```

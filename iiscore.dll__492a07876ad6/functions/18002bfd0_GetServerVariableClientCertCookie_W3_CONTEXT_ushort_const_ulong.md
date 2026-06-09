# GetServerVariableClientCertCookie(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x18002bfd0`
- end: `0x18002c0f4`
- name: `?GetServerVariableClientCertCookie@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002bfd0`
- `0x18002efb0`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18002c011`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002c011`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c070`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c0b4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c070`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c0b4`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c035`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c0a1`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c035`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c0a1`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002c08d`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002c08d`

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
    *a2 = &dword_18003C134;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002bfd0  mov     [rsp+arg_18], rbx
0x18002bfd5  push    rsi
0x18002bfd6  push    rdi
0x18002bfd7  push    r14
0x18002bfd9  sub     rsp, 70h
0x18002bfdd  mov     rax, cs:__security_cookie
0x18002bfe4  xor     rax, rsp
0x18002bfe7  mov     [rsp+88h+var_28], rax
0x18002bfec  mov     rax, [rcx+188h]
0x18002bff3  mov     rsi, r8
0x18002bff6  mov     rdi, rdx
0x18002bff9  mov     r14, rcx
0x18002bffc  mov     rbx, [rax+2508h]
0x18002c003  test    rbx, rbx
0x18002c006  jz      loc_18002C0C2
0x18002c00c  lea     rcx, [rsp+88h+var_60]
0x18002c011  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002c018  nop     dword ptr [rax+rax+00h]
0x18002c01d  lea     rdx, [rsp+88h+var_60]; struct STRU *
0x18002c022  mov     rcx, rbx; this
0x18002c025  call    ?GetCookie@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z; CERTIFICATE_CONTEXT::GetCookie(STRU *)
0x18002c02a  mov     ebx, eax
0x18002c02c  test    eax, eax
0x18002c02e  js      short loc_18002C06B
0x18002c030  lea     rcx, [rsp+88h+var_60]
0x18002c035  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002c03c  nop     dword ptr [rax+rax+00h]
0x18002c041  mov     rcx, r14
0x18002c044  lea     edx, ds:2[rax*2]
0x18002c04b  mov     rax, [r14]
0x18002c04e  mov     [rsp+88h+var_68], edx
0x18002c052  mov     rax, [rax+90h]
0x18002c059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c05e  mov     rbx, rax
0x18002c061  test    rax, rax
0x18002c064  jnz     short loc_18002C080
0x18002c066  mov     ebx, 80070008h
0x18002c06b  lea     rcx, [rsp+88h+var_60]
0x18002c070  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002c077  nop     dword ptr [rax+rax+00h]
0x18002c07c  mov     eax, ebx
0x18002c07e  jmp     short loc_18002C0D5
0x18002c080  lea     r8, [rsp+88h+var_68]
0x18002c085  mov     rdx, rbx
0x18002c088  lea     rcx, [rsp+88h+var_60]
0x18002c08d  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18002c094  nop     dword ptr [rax+rax+00h]
0x18002c099  lea     rcx, [rsp+88h+var_60]
0x18002c09e  mov     [rdi], rbx
0x18002c0a1  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002c0a8  nop     dword ptr [rax+rax+00h]
0x18002c0ad  lea     rcx, [rsp+88h+var_60]
0x18002c0b2  mov     [rsi], eax
0x18002c0b4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002c0bb  nop     dword ptr [rax+rax+00h]
0x18002c0c0  jmp     short loc_18002C0D3
0x18002c0c2  lea     rax, dword_18003C134
0x18002c0c9  mov     [rdx], rax
0x18002c0cc  mov     dword ptr [r8], 0
0x18002c0d3  xor     eax, eax
0x18002c0d5  mov     rcx, [rsp+88h+var_28]
0x18002c0da  xor     rcx, rsp; StackCookie
0x18002c0dd  call    __security_check_cookie
0x18002c0e2  mov     rbx, [rsp+88h+arg_18]
0x18002c0ea  add     rsp, 70h
0x18002c0ee  pop     r14
0x18002c0f0  pop     rdi
0x18002c0f1  pop     rsi
0x18002c0f2  retn
```

# GetServerVariableClientCertSubject(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x18002c3e0`
- end: `0x18002c504`
- name: `?GetServerVariableClientCertSubject@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002c3e0`
- `0x18002f604`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18002c421`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002c421`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c480`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c4c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c480`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c4c4`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c445`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c4b1`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c445`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c4b1`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002c49d`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002c49d`

## pseudocode

```c
__int64 __fastcall GetServerVariableClientCertSubject(
        struct W3_CONTEXT *a1,
        const unsigned __int16 **a2,
        unsigned int *a3)
{
  CERTIFICATE_CONTEXT *v6; // rbx
  int Subject; // ebx
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
    Subject = CERTIFICATE_CONTEXT::GetSubject(v6, (struct STRU *)v14);
    if ( Subject < 0 )
    {
LABEL_5:
      STRU::~STRU((STRU *)v14);
      return (unsigned int)Subject;
    }
    v8 = 2 * STRU::QueryCCH((STRU *)v14) + 2;
    v9 = *(_QWORD *)a1;
    v13 = v8;
    v10 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *))(v9 + 144))(a1);
    v11 = v10;
    if ( !v10 )
    {
      Subject = -2147024888;
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
0x18002c3e0  mov     [rsp+arg_18], rbx
0x18002c3e5  push    rsi
0x18002c3e6  push    rdi
0x18002c3e7  push    r14
0x18002c3e9  sub     rsp, 70h
0x18002c3ed  mov     rax, cs:__security_cookie
0x18002c3f4  xor     rax, rsp
0x18002c3f7  mov     [rsp+88h+var_28], rax
0x18002c3fc  mov     rax, [rcx+188h]
0x18002c403  mov     rsi, r8
0x18002c406  mov     rdi, rdx
0x18002c409  mov     r14, rcx
0x18002c40c  mov     rbx, [rax+2508h]
0x18002c413  test    rbx, rbx
0x18002c416  jz      loc_18002C4D2
0x18002c41c  lea     rcx, [rsp+88h+var_60]
0x18002c421  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002c428  nop     dword ptr [rax+rax+00h]
0x18002c42d  lea     rdx, [rsp+88h+var_60]; struct STRU *
0x18002c432  mov     rcx, rbx; this
0x18002c435  call    ?GetSubject@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z; CERTIFICATE_CONTEXT::GetSubject(STRU *)
0x18002c43a  mov     ebx, eax
0x18002c43c  test    eax, eax
0x18002c43e  js      short loc_18002C47B
0x18002c440  lea     rcx, [rsp+88h+var_60]
0x18002c445  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002c44c  nop     dword ptr [rax+rax+00h]
0x18002c451  mov     rcx, r14
0x18002c454  lea     edx, ds:2[rax*2]
0x18002c45b  mov     rax, [r14]
0x18002c45e  mov     [rsp+88h+var_68], edx
0x18002c462  mov     rax, [rax+90h]
0x18002c469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c46e  mov     rbx, rax
0x18002c471  test    rax, rax
0x18002c474  jnz     short loc_18002C490
0x18002c476  mov     ebx, 80070008h
0x18002c47b  lea     rcx, [rsp+88h+var_60]
0x18002c480  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002c487  nop     dword ptr [rax+rax+00h]
0x18002c48c  mov     eax, ebx
0x18002c48e  jmp     short loc_18002C4E5
0x18002c490  lea     r8, [rsp+88h+var_68]
0x18002c495  mov     rdx, rbx
0x18002c498  lea     rcx, [rsp+88h+var_60]
0x18002c49d  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18002c4a4  nop     dword ptr [rax+rax+00h]
0x18002c4a9  lea     rcx, [rsp+88h+var_60]
0x18002c4ae  mov     [rdi], rbx
0x18002c4b1  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002c4b8  nop     dword ptr [rax+rax+00h]
0x18002c4bd  lea     rcx, [rsp+88h+var_60]
0x18002c4c2  mov     [rsi], eax
0x18002c4c4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002c4cb  nop     dword ptr [rax+rax+00h]
0x18002c4d0  jmp     short loc_18002C4E3
0x18002c4d2  lea     rax, dword_18003C134
0x18002c4d9  mov     [rdx], rax
0x18002c4dc  mov     dword ptr [r8], 0
0x18002c4e3  xor     eax, eax
0x18002c4e5  mov     rcx, [rsp+88h+var_28]
0x18002c4ea  xor     rcx, rsp; StackCookie
0x18002c4ed  call    __security_check_cookie
0x18002c4f2  mov     rbx, [rsp+88h+arg_18]
0x18002c4fa  add     rsp, 70h
0x18002c4fe  pop     r14
0x18002c500  pop     rdi
0x18002c501  pop     rsi
0x18002c502  retn
```

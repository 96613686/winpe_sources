# GetServerVariableClientCertSubject(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x180029e90`
- end: `0x180029f8f`
- name: `?GetServerVariableClientCertSubject@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `255`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180029e90`
- `0x18002ccc0`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180029ed1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180029ed1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029f24`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029f56`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029f24`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029f56`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029eef`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029f49`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029eef`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029f49`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180029f3b`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180029f3b`

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
    *a2 = &dword_180039134;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180029e90  mov     [rsp+arg_18], rbx
0x180029e95  push    rsi
0x180029e96  push    rdi
0x180029e97  push    r14
0x180029e99  sub     rsp, 70h
0x180029e9d  mov     rax, cs:__security_cookie
0x180029ea4  xor     rax, rsp
0x180029ea7  mov     [rsp+88h+var_28], rax
0x180029eac  mov     rax, [rcx+188h]
0x180029eb3  mov     rsi, r8
0x180029eb6  mov     rdi, rdx
0x180029eb9  mov     r14, rcx
0x180029ebc  mov     rbx, [rax+2508h]
0x180029ec3  test    rbx, rbx
0x180029ec6  jz      loc_180029F5E
0x180029ecc  lea     rcx, [rsp+88h+var_60]
0x180029ed1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180029ed7  lea     rdx, [rsp+88h+var_60]; struct STRU *
0x180029edc  mov     rcx, rbx; this
0x180029edf  call    ?GetSubject@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z; CERTIFICATE_CONTEXT::GetSubject(STRU *)
0x180029ee4  mov     ebx, eax
0x180029ee6  test    eax, eax
0x180029ee8  js      short loc_180029F1F
0x180029eea  lea     rcx, [rsp+88h+var_60]
0x180029eef  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180029ef5  mov     rcx, r14
0x180029ef8  lea     edx, ds:2[rax*2]
0x180029eff  mov     rax, [r14]
0x180029f02  mov     [rsp+88h+var_68], edx
0x180029f06  mov     rax, [rax+90h]
0x180029f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f12  mov     rbx, rax
0x180029f15  test    rax, rax
0x180029f18  jnz     short loc_180029F2E
0x180029f1a  mov     ebx, 80070008h
0x180029f1f  lea     rcx, [rsp+88h+var_60]
0x180029f24  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180029f2a  mov     eax, ebx
0x180029f2c  jmp     short loc_180029F71
0x180029f2e  lea     r8, [rsp+88h+var_68]
0x180029f33  mov     rdx, rbx
0x180029f36  lea     rcx, [rsp+88h+var_60]
0x180029f3b  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x180029f41  lea     rcx, [rsp+88h+var_60]
0x180029f46  mov     [rdi], rbx
0x180029f49  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180029f4f  lea     rcx, [rsp+88h+var_60]
0x180029f54  mov     [rsi], eax
0x180029f56  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180029f5c  jmp     short loc_180029F6F
0x180029f5e  lea     rax, dword_180039134
0x180029f65  mov     [rdx], rax
0x180029f68  mov     dword ptr [r8], 0
0x180029f6f  xor     eax, eax
0x180029f71  mov     rcx, [rsp+88h+var_28]
0x180029f76  xor     rcx, rsp; StackCookie
0x180029f79  call    __security_check_cookie
0x180029f7e  mov     rbx, [rsp+88h+arg_18]
0x180029f86  add     rsp, 70h
0x180029f8a  pop     r14
0x180029f8c  pop     rdi
0x180029f8d  pop     rsi
0x180029f8e  retn
```

# GetServerVariableClientCertSerialNumber(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x180029d80`
- end: `0x180029e7f`
- name: `?GetServerVariableClientCertSerialNumber@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `255`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180029d80`
- `0x18002cba8`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180029dc1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180029dc1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029e14`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029e46`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029e14`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029e46`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029ddf`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029e39`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029ddf`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180029e39`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180029e2b`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180029e2b`

## pseudocode

```c
__int64 __fastcall GetServerVariableClientCertSerialNumber(
        struct W3_CONTEXT *a1,
        const unsigned __int16 **a2,
        unsigned int *a3)
{
  CERTIFICATE_CONTEXT *v6; // rbx
  int SerialNumber; // ebx
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
    SerialNumber = CERTIFICATE_CONTEXT::GetSerialNumber(v6, (struct STRU *)v14);
    if ( SerialNumber < 0 )
    {
LABEL_5:
      STRU::~STRU((STRU *)v14);
      return (unsigned int)SerialNumber;
    }
    v8 = 2 * STRU::QueryCCH((STRU *)v14) + 2;
    v9 = *(_QWORD *)a1;
    v13 = v8;
    v10 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *))(v9 + 144))(a1);
    v11 = v10;
    if ( !v10 )
    {
      SerialNumber = -2147024888;
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
0x180029d80  mov     [rsp+arg_18], rbx
0x180029d85  push    rsi
0x180029d86  push    rdi
0x180029d87  push    r14
0x180029d89  sub     rsp, 70h
0x180029d8d  mov     rax, cs:__security_cookie
0x180029d94  xor     rax, rsp
0x180029d97  mov     [rsp+88h+var_28], rax
0x180029d9c  mov     rax, [rcx+188h]
0x180029da3  mov     rsi, r8
0x180029da6  mov     rdi, rdx
0x180029da9  mov     r14, rcx
0x180029dac  mov     rbx, [rax+2508h]
0x180029db3  test    rbx, rbx
0x180029db6  jz      loc_180029E4E
0x180029dbc  lea     rcx, [rsp+88h+var_60]
0x180029dc1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180029dc7  lea     rdx, [rsp+88h+var_60]; struct STRU *
0x180029dcc  mov     rcx, rbx; this
0x180029dcf  call    ?GetSerialNumber@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z; CERTIFICATE_CONTEXT::GetSerialNumber(STRU *)
0x180029dd4  mov     ebx, eax
0x180029dd6  test    eax, eax
0x180029dd8  js      short loc_180029E0F
0x180029dda  lea     rcx, [rsp+88h+var_60]
0x180029ddf  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180029de5  mov     rcx, r14
0x180029de8  lea     edx, ds:2[rax*2]
0x180029def  mov     rax, [r14]
0x180029df2  mov     [rsp+88h+var_68], edx
0x180029df6  mov     rax, [rax+90h]
0x180029dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e02  mov     rbx, rax
0x180029e05  test    rax, rax
0x180029e08  jnz     short loc_180029E1E
0x180029e0a  mov     ebx, 80070008h
0x180029e0f  lea     rcx, [rsp+88h+var_60]
0x180029e14  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180029e1a  mov     eax, ebx
0x180029e1c  jmp     short loc_180029E61
0x180029e1e  lea     r8, [rsp+88h+var_68]
0x180029e23  mov     rdx, rbx
0x180029e26  lea     rcx, [rsp+88h+var_60]
0x180029e2b  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x180029e31  lea     rcx, [rsp+88h+var_60]
0x180029e36  mov     [rdi], rbx
0x180029e39  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180029e3f  lea     rcx, [rsp+88h+var_60]
0x180029e44  mov     [rsi], eax
0x180029e46  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180029e4c  jmp     short loc_180029E5F
0x180029e4e  lea     rax, dword_180039134
0x180029e55  mov     [rdx], rax
0x180029e58  mov     dword ptr [r8], 0
0x180029e5f  xor     eax, eax
0x180029e61  mov     rcx, [rsp+88h+var_28]
0x180029e66  xor     rcx, rsp; StackCookie
0x180029e69  call    __security_check_cookie
0x180029e6e  mov     rbx, [rsp+88h+arg_18]
0x180029e76  add     rsp, 70h
0x180029e7a  pop     r14
0x180029e7c  pop     rdi
0x180029e7d  pop     rsi
0x180029e7e  retn
```

# GetServerVariableClientCertSerialNumber(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x18002c2b0`
- end: `0x18002c3d4`
- name: `?GetServerVariableClientCertSerialNumber@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002c2b0`
- `0x18002f4d0`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18002c2f1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002c2f1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c350`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c394`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c350`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c394`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c315`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c381`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c315`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002c381`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002c36d`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002c36d`

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
    *a2 = &dword_18003C134;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002c2b0  mov     [rsp+arg_18], rbx
0x18002c2b5  push    rsi
0x18002c2b6  push    rdi
0x18002c2b7  push    r14
0x18002c2b9  sub     rsp, 70h
0x18002c2bd  mov     rax, cs:__security_cookie
0x18002c2c4  xor     rax, rsp
0x18002c2c7  mov     [rsp+88h+var_28], rax
0x18002c2cc  mov     rax, [rcx+188h]
0x18002c2d3  mov     rsi, r8
0x18002c2d6  mov     rdi, rdx
0x18002c2d9  mov     r14, rcx
0x18002c2dc  mov     rbx, [rax+2508h]
0x18002c2e3  test    rbx, rbx
0x18002c2e6  jz      loc_18002C3A2
0x18002c2ec  lea     rcx, [rsp+88h+var_60]
0x18002c2f1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002c2f8  nop     dword ptr [rax+rax+00h]
0x18002c2fd  lea     rdx, [rsp+88h+var_60]; struct STRU *
0x18002c302  mov     rcx, rbx; this
0x18002c305  call    ?GetSerialNumber@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z; CERTIFICATE_CONTEXT::GetSerialNumber(STRU *)
0x18002c30a  mov     ebx, eax
0x18002c30c  test    eax, eax
0x18002c30e  js      short loc_18002C34B
0x18002c310  lea     rcx, [rsp+88h+var_60]
0x18002c315  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002c31c  nop     dword ptr [rax+rax+00h]
0x18002c321  mov     rcx, r14
0x18002c324  lea     edx, ds:2[rax*2]
0x18002c32b  mov     rax, [r14]
0x18002c32e  mov     [rsp+88h+var_68], edx
0x18002c332  mov     rax, [rax+90h]
0x18002c339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c33e  mov     rbx, rax
0x18002c341  test    rax, rax
0x18002c344  jnz     short loc_18002C360
0x18002c346  mov     ebx, 80070008h
0x18002c34b  lea     rcx, [rsp+88h+var_60]
0x18002c350  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002c357  nop     dword ptr [rax+rax+00h]
0x18002c35c  mov     eax, ebx
0x18002c35e  jmp     short loc_18002C3B5
0x18002c360  lea     r8, [rsp+88h+var_68]
0x18002c365  mov     rdx, rbx
0x18002c368  lea     rcx, [rsp+88h+var_60]
0x18002c36d  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18002c374  nop     dword ptr [rax+rax+00h]
0x18002c379  lea     rcx, [rsp+88h+var_60]
0x18002c37e  mov     [rdi], rbx
0x18002c381  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002c388  nop     dword ptr [rax+rax+00h]
0x18002c38d  lea     rcx, [rsp+88h+var_60]
0x18002c392  mov     [rsi], eax
0x18002c394  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002c39b  nop     dword ptr [rax+rax+00h]
0x18002c3a0  jmp     short loc_18002C3B3
0x18002c3a2  lea     rax, dword_18003C134
0x18002c3a9  mov     [rdx], rax
0x18002c3ac  mov     dword ptr [r8], 0
0x18002c3b3  xor     eax, eax
0x18002c3b5  mov     rcx, [rsp+88h+var_28]
0x18002c3ba  xor     rcx, rsp; StackCookie
0x18002c3bd  call    __security_check_cookie
0x18002c3c2  mov     rbx, [rsp+88h+arg_18]
0x18002c3ca  add     rsp, 70h
0x18002c3ce  pop     r14
0x18002c3d0  pop     rdi
0x18002c3d1  pop     rsi
0x18002c3d2  retn
```

# GetServerVariablePathTranslated(W3_CONTEXT *,ushort const * *,ulong *)

- ea: `0x18002d280`
- end: `0x18002d507`
- name: `?GetServerVariablePathTranslated@@YAJPEAVW3_CONTEXT@@PEAPEBGPEAK@Z`
- size: `647`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *this, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180002db0`
- `0x18002d280`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18002d30d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002d30d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d3b2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d3c3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d44a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d45b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d4a0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d4b1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d3b2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d3c3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d44a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d45b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d4a0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002d4b1`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002d40f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002d48c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002d40f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002d48c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002d3db`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002d3db`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002d339`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002d339`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002d39b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002d39b`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002d478`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18002d478`

## pseudocode

```c
__int64 __fastcall GetServerVariablePathTranslated(
        struct W3_CONTEXT *this,
        const unsigned __int16 **a2,
        unsigned int *a3)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rax
  unsigned int v9; // edi
  unsigned __int16 *Str; // rdx
  unsigned int v11; // edi
  int v12; // esi
  int v14; // edi
  unsigned int v15; // edx
  __int64 v16; // rax
  unsigned __int16 *v17; // rax
  const unsigned __int16 *v18; // rbx
  const unsigned __int16 *v19; // rax
  bool v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v22; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v23[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[56]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v25[256]; // [rsp+B0h] [rbp-50h] BYREF

  if ( (*(__int64 (__fastcall **)(struct W3_CONTEXT *))(*(_QWORD *)this + 192LL))(this)
    && (v6 = (*(__int64 (__fastcall **)(struct W3_CONTEXT *))(*(_QWORD *)this + 192LL))(this),
        (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6)) )
  {
    v7 = *(_QWORD *)(*((_QWORD *)this + 6) + 40LL);
    v21 = 0;
    STRU::STRU((STRU *)v24);
    memset_0(v25, 0, sizeof(v25));
    STRU::STRU((STRU *)v23, v25, 0x100u);
    v8 = *(_QWORD *)this;
    v20 = 0;
    (*(void (__fastcall **)(struct W3_CONTEXT *, unsigned int *))(v8 + 176))(this, &v21);
    v9 = *(unsigned __int16 *)(v7 + 68) >> 1;
    if ( v21 <= v9 )
    {
      v11 = v9 - v21;
      Str = (unsigned __int16 *)(*(_QWORD *)(v7 + 88) + 2LL * v21);
    }
    else
    {
      Str = (unsigned __int16 *)byte_18003F3C0;
      v11 = 0;
    }
    if ( Str[v11] )
    {
      v12 = STRU::Copy((STRU *)v24, Str, v11);
      if ( v12 < 0 )
      {
        STRU::~STRU((STRU *)v23);
        STRU::~STRU((STRU *)v24);
        return (unsigned int)v12;
      }
      Str = STRU::QueryStr((STRU *)v24);
    }
    v14 = W3_CONTEXT::MapPath(this, Str, v11, (struct STRU *)v23, &v20);
    if ( v14 < 0 )
      goto LABEL_13;
    v15 = 2 * STRU::QueryCCH((STRU *)v23) + 2;
    v16 = *(_QWORD *)this;
    v22 = v15;
    v17 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *))(v16 + 144))(this);
    v18 = v17;
    if ( !v17 )
    {
      v14 = -2147024888;
LABEL_13:
      STRU::~STRU((STRU *)v23);
      STRU::~STRU((STRU *)v24);
      return (unsigned int)v14;
    }
    STRU::CopyToBuffer((STRU *)v23, v17, &v22);
    *a2 = v18;
    *a3 = STRU::QueryCCH((STRU *)v23);
    STRU::~STRU((STRU *)v23);
    STRU::~STRU((STRU *)v24);
    return 0;
  }
  else
  {
    v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *, unsigned int *))(*(_QWORD *)this + 168LL))(
                                      this,
                                      a3);
    *a2 = v19;
    return v19 == 0 ? 0x80070008 : 0;
  }
}

```

## disassembly

```asm
0x18002d280  push    rbp
0x18002d282  push    rbx
0x18002d283  push    rsi
0x18002d284  push    rdi
0x18002d285  push    r12
0x18002d287  push    r14
0x18002d289  push    r15
0x18002d28b  lea     rbp, [rsp-1C0h]
0x18002d293  sub     rsp, 2C0h
0x18002d29a  mov     rax, cs:__security_cookie
0x18002d2a1  xor     rax, rsp
0x18002d2a4  mov     [rbp+1F0h+var_40], rax
0x18002d2ab  mov     rax, [rcx]
0x18002d2ae  mov     r15, r8
0x18002d2b1  mov     r14, rdx
0x18002d2b4  mov     rbx, rcx
0x18002d2b7  mov     rax, [rax+0C0h]
0x18002d2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2c3  xor     r12d, r12d
0x18002d2c6  test    rax, rax
0x18002d2c9  jz      loc_18002D4C1
0x18002d2cf  mov     rax, [rbx]
0x18002d2d2  mov     rcx, rbx
0x18002d2d5  mov     rax, [rax+0C0h]
0x18002d2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2e1  mov     rdx, rax
0x18002d2e4  mov     rcx, [rax]
0x18002d2e7  mov     rax, [rcx+28h]
0x18002d2eb  mov     rcx, rdx
0x18002d2ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2f3  test    eax, eax
0x18002d2f5  jz      loc_18002D4C1
0x18002d2fb  mov     rax, [rbx+30h]
0x18002d2ff  lea     rcx, [rsp+2F0h+var_278]
0x18002d304  mov     rsi, [rax+28h]
0x18002d308  mov     [rsp+2F0h+var_2BC], r12d
0x18002d30d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002d314  nop     dword ptr [rax+rax+00h]
0x18002d319  xor     edx, edx; Val
0x18002d31b  lea     rcx, [rbp+1F0h+var_240]; void *
0x18002d31f  mov     r8d, 200h; Size
0x18002d325  call    memset_0
0x18002d32a  mov     r8d, 100h
0x18002d330  lea     rdx, [rbp+1F0h+var_240]
0x18002d334  lea     rcx, [rsp+2F0h+var_2B0]
0x18002d339  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002d340  nop     dword ptr [rax+rax+00h]
0x18002d345  mov     rax, [rbx]
0x18002d348  lea     rdx, [rsp+2F0h+var_2BC]
0x18002d34d  mov     rcx, rbx
0x18002d350  mov     [rsp+2F0h+var_2C0], r12b
0x18002d355  mov     rax, [rax+0B0h]
0x18002d35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d361  movzx   eax, word ptr [rsi+44h]
0x18002d365  mov     r8d, [rsp+2F0h+var_2BC]
0x18002d36a  shr     eax, 1
0x18002d36c  mov     edi, eax
0x18002d36e  cmp     r8d, eax
0x18002d371  jbe     short loc_18002D37F
0x18002d373  lea     rdx, byte_18003F3C0
0x18002d37a  mov     edi, r12d
0x18002d37d  jmp     short loc_18002D38A
0x18002d37f  mov     rax, [rsi+58h]
0x18002d383  sub     edi, r8d
0x18002d386  lea     rdx, [rax+r8*2]
0x18002d38a  mov     eax, edi
0x18002d38c  cmp     [rdx+rax*2], r12w
0x18002d391  jz      short loc_18002D3EA
0x18002d393  mov     r8d, edi
0x18002d396  lea     rcx, [rsp+2F0h+var_278]
0x18002d39b  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002d3a2  nop     dword ptr [rax+rax+00h]
0x18002d3a7  mov     esi, eax
0x18002d3a9  test    eax, eax
0x18002d3ab  jns     short loc_18002D3D6
0x18002d3ad  lea     rcx, [rsp+2F0h+var_2B0]
0x18002d3b2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002d3b9  nop     dword ptr [rax+rax+00h]
0x18002d3be  lea     rcx, [rsp+2F0h+var_278]
0x18002d3c3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002d3ca  nop     dword ptr [rax+rax+00h]
0x18002d3cf  mov     eax, esi
0x18002d3d1  jmp     loc_18002D4E5
0x18002d3d6  lea     rcx, [rsp+2F0h+var_278]
0x18002d3db  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002d3e2  nop     dword ptr [rax+rax+00h]
0x18002d3e7  mov     rdx, rax; unsigned __int16 *
0x18002d3ea  lea     rax, [rsp+2F0h+var_2C0]
0x18002d3ef  mov     r8d, edi; unsigned int
0x18002d3f2  lea     r9, [rsp+2F0h+var_2B0]; struct STRU *
0x18002d3f7  mov     [rsp+2F0h+var_2D0], rax; bool *
0x18002d3fc  mov     rcx, rbx; this
0x18002d3ff  call    ?MapPath@W3_CONTEXT@@QEAAJPEBGKPEAVSTRU@@PEA_N@Z; W3_CONTEXT::MapPath(ushort const *,ulong,STRU *,bool *)
0x18002d404  mov     edi, eax
0x18002d406  test    eax, eax
0x18002d408  js      short loc_18002D445
0x18002d40a  lea     rcx, [rsp+2F0h+var_2B0]
0x18002d40f  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002d416  nop     dword ptr [rax+rax+00h]
0x18002d41b  mov     rcx, rbx
0x18002d41e  lea     edx, ds:2[rax*2]
0x18002d425  mov     rax, [rbx]
0x18002d428  mov     [rsp+2F0h+var_2B8], edx
0x18002d42c  mov     rax, [rax+90h]
0x18002d433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d438  mov     rbx, rax
0x18002d43b  test    rax, rax
0x18002d43e  jnz     short loc_18002D46B
0x18002d440  mov     edi, 80070008h
0x18002d445  lea     rcx, [rsp+2F0h+var_2B0]
0x18002d44a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002d451  nop     dword ptr [rax+rax+00h]
0x18002d456  lea     rcx, [rsp+2F0h+var_278]
0x18002d45b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002d462  nop     dword ptr [rax+rax+00h]
0x18002d467  mov     eax, edi
0x18002d469  jmp     short loc_18002D4E5
0x18002d46b  lea     r8, [rsp+2F0h+var_2B8]
0x18002d470  mov     rdx, rbx
0x18002d473  lea     rcx, [rsp+2F0h+var_2B0]
0x18002d478  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18002d47f  nop     dword ptr [rax+rax+00h]
0x18002d484  lea     rcx, [rsp+2F0h+var_2B0]
0x18002d489  mov     [r14], rbx
0x18002d48c  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18002d493  nop     dword ptr [rax+rax+00h]
0x18002d498  lea     rcx, [rsp+2F0h+var_2B0]
0x18002d49d  mov     [r15], eax
0x18002d4a0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002d4a7  nop     dword ptr [rax+rax+00h]
0x18002d4ac  lea     rcx, [rsp+2F0h+var_278]
0x18002d4b1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002d4b8  nop     dword ptr [rax+rax+00h]
0x18002d4bd  xor     eax, eax
0x18002d4bf  jmp     short loc_18002D4E5
0x18002d4c1  mov     rax, [rbx]
0x18002d4c4  mov     rdx, r15
0x18002d4c7  mov     rcx, rbx
0x18002d4ca  mov     rax, [rax+0A8h]
0x18002d4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4d6  mov     [r14], rax
0x18002d4d9  neg     rax
0x18002d4dc  sbb     eax, eax
0x18002d4de  not     eax
0x18002d4e0  and     eax, 80070008h
0x18002d4e5  mov     rcx, [rbp+1F0h+var_40]
0x18002d4ec  xor     rcx, rsp; StackCookie
0x18002d4ef  call    __security_check_cookie
0x18002d4f4  add     rsp, 2C0h
0x18002d4fb  pop     r15
0x18002d4fd  pop     r14
0x18002d4ff  pop     r12
0x18002d501  pop     rdi
0x18002d502  pop     rsi
0x18002d503  pop     rbx
0x18002d504  pop     rbp
0x18002d505  retn
```

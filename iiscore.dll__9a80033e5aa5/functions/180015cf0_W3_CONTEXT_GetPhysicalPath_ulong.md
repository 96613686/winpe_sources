# W3_CONTEXT::GetPhysicalPath(ulong *)

- ea: `0x180015cf0`
- end: `0x180015e55`
- name: `?GetPhysicalPath@W3_CONTEXT@@UEAAPEBGPEAK@Z`
- size: `357`
- prototype: `const unsigned __int16 *__fastcall(W3_CONTEXT *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180002bf0`
- `0x180015cf0`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180015e15`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180015e22`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180015e15`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180015e22`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180015d2e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180015dce`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180015e3e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180015d2e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180015dce`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180015e3e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180015ddb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180015e4a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180015ddb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180015e4a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180015da0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180015da0`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180015dbf`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180015dbf`

## pseudocode

```c
unsigned __int16 *__fastcall W3_CONTEXT::GetPhysicalPath(W3_CONTEXT *this, unsigned int *a2)
{
  int v4; // ebx
  unsigned int CCH; // ebx
  unsigned __int16 *Str; // rax
  STRU *v8; // rsi
  _BYTE v9[64]; // [rsp+30h] [rbp-868h] BYREF
  unsigned __int16 v10[1024]; // [rsp+70h] [rbp-828h] BYREF

  v4 = *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 68LL) >> 1;
  if ( STRU::QueryCCH((W3_CONTEXT *)((char *)this + 8728)) == v4 )
    return (unsigned __int16 *)(*(__int64 (__fastcall **)(W3_CONTEXT *, unsigned int *))(*(_QWORD *)this + 184LL))(
                                 this,
                                 a2);
  if ( *((_BYTE *)this + 8099) )
  {
    v8 = (W3_CONTEXT *)((char *)this + 8104);
  }
  else
  {
    memset_0(v10, 0, sizeof(v10));
    STRU::STRU((STRU *)v9, v10, 0x400u);
    if ( (int)STRU::Copy(
                (STRU *)v9,
                *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 88LL),
                *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 68LL) >> 1) < 0
      || (CCH = STRU::QueryCCH((STRU *)v9),
          Str = STRU::QueryStr((STRU *)v9),
          v8 = (W3_CONTEXT *)((char *)this + 8104),
          (int)W3_CONTEXT::MapPath(this, Str, CCH, (W3_CONTEXT *)((char *)this + 8104), (bool *)this + 8100) < 0) )
    {
      STRU::~STRU((STRU *)v9);
      return 0;
    }
    *((_BYTE *)this + 8099) = 1;
    STRU::~STRU((STRU *)v9);
  }
  if ( a2 )
    *a2 = STRU::QueryCCH(v8);
  return STRU::QueryStr(v8);
}

```

## disassembly

```asm
0x180015cf0  mov     [rsp+arg_10], rbx
0x180015cf5  push    rsi
0x180015cf6  push    rdi
0x180015cf7  push    r14
0x180015cf9  sub     rsp, 880h
0x180015d00  mov     rax, cs:__security_cookie
0x180015d07  xor     rax, rsp
0x180015d0a  mov     [rsp+898h+var_28], rax
0x180015d12  mov     rax, [rcx+30h]
0x180015d16  mov     rdi, rcx
0x180015d19  add     rcx, 2218h
0x180015d20  mov     r14, rdx
0x180015d23  mov     r8, [rax+28h]
0x180015d27  movzx   ebx, word ptr [r8+44h]
0x180015d2c  shr     ebx, 1
0x180015d2e  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180015d34  cmp     eax, ebx
0x180015d36  jnz     short loc_180015D71
0x180015d38  mov     rax, [rdi]
0x180015d3b  mov     rdx, r14
0x180015d3e  mov     rcx, rdi
0x180015d41  mov     rax, [rax+0B8h]
0x180015d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d4d  mov     rcx, [rsp+898h+var_28]
0x180015d55  xor     rcx, rsp; StackCookie
0x180015d58  call    __security_check_cookie
0x180015d5d  mov     rbx, [rsp+898h+arg_10]
0x180015d65  add     rsp, 880h
0x180015d6c  pop     r14
0x180015d6e  pop     rdi
0x180015d6f  pop     rsi
0x180015d70  retn
0x180015d71  cmp     byte ptr [rdi+1FA3h], 0
0x180015d78  jnz     loc_180015E2F
0x180015d7e  xor     edx, edx; Val
0x180015d80  lea     rcx, [rsp+898h+var_828]; void *
0x180015d85  mov     r8d, 800h; Size
0x180015d8b  call    memset_0
0x180015d90  mov     r8d, 400h
0x180015d96  lea     rdx, [rsp+898h+var_828]
0x180015d9b  lea     rcx, [rsp+898h+var_868]
0x180015da0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180015da6  mov     rax, [rdi+30h]
0x180015daa  lea     rcx, [rsp+898h+var_868]
0x180015daf  mov     rdx, [rax+28h]
0x180015db3  movzx   r8d, word ptr [rdx+44h]
0x180015db8  mov     rdx, [rdx+58h]
0x180015dbc  shr     r8d, 1
0x180015dbf  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180015dc5  test    eax, eax
0x180015dc7  js      short loc_180015E1D
0x180015dc9  lea     rcx, [rsp+898h+var_868]
0x180015dce  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180015dd4  lea     rcx, [rsp+898h+var_868]
0x180015dd9  mov     ebx, eax
0x180015ddb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180015de1  lea     rcx, [rdi+1FA4h]
0x180015de8  mov     r8d, ebx; unsigned int
0x180015deb  mov     [rsp+898h+var_878], rcx; bool *
0x180015df0  lea     rsi, [rdi+1FA8h]
0x180015df7  mov     rcx, rdi; this
0x180015dfa  mov     r9, rsi; struct STRU *
0x180015dfd  mov     rdx, rax; unsigned __int16 *
0x180015e00  call    ?MapPath@W3_CONTEXT@@QEAAJPEBGKPEAVSTRU@@PEA_N@Z; W3_CONTEXT::MapPath(ushort const *,ulong,STRU *,bool *)
0x180015e05  test    eax, eax
0x180015e07  js      short loc_180015E1D
0x180015e09  lea     rcx, [rsp+898h+var_868]
0x180015e0e  mov     byte ptr [rdi+1FA3h], 1
0x180015e15  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180015e1b  jmp     short loc_180015E36
0x180015e1d  lea     rcx, [rsp+898h+var_868]
0x180015e22  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180015e28  xor     eax, eax
0x180015e2a  jmp     loc_180015D4D
0x180015e2f  lea     rsi, [rdi+1FA8h]
0x180015e36  test    r14, r14
0x180015e39  jz      short loc_180015E47
0x180015e3b  mov     rcx, rsi
0x180015e3e  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180015e44  mov     [r14], eax
0x180015e47  mov     rcx, rsi
0x180015e4a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180015e50  jmp     loc_180015D4D
```

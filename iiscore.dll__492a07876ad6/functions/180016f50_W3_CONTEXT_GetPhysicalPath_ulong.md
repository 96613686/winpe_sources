# W3_CONTEXT::GetPhysicalPath(ulong *)

- ea: `0x180016f50`
- end: `0x1800170ec`
- name: `?GetPhysicalPath@W3_CONTEXT@@UEAAPEBGPEAK@Z`
- size: `412`
- prototype: `const unsigned __int16 *__fastcall(W3_CONTEXT *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180002db0`
- `0x180016f50`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180017094`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800170a7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017094`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800170a7`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180016f8e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180017041`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800170c9`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180016f8e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180017041`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800170c9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180017054`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800170db`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180017054`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800170db`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017007`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017007`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001702c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001702c`

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
0x180016f50  mov     [rsp+arg_10], rbx
0x180016f55  push    rsi
0x180016f56  push    rdi
0x180016f57  push    r14
0x180016f59  sub     rsp, 880h
0x180016f60  mov     rax, cs:__security_cookie
0x180016f67  xor     rax, rsp
0x180016f6a  mov     [rsp+898h+var_28], rax
0x180016f72  mov     rax, [rcx+30h]
0x180016f76  mov     rdi, rcx
0x180016f79  add     rcx, 2218h
0x180016f80  mov     r14, rdx
0x180016f83  mov     r8, [rax+28h]
0x180016f87  movzx   ebx, word ptr [r8+44h]
0x180016f8c  shr     ebx, 1
0x180016f8e  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180016f95  nop     dword ptr [rax+rax+00h]
0x180016f9a  cmp     eax, ebx
0x180016f9c  jnz     short loc_180016FD8
0x180016f9e  mov     rax, [rdi]
0x180016fa1  mov     rdx, r14
0x180016fa4  mov     rcx, rdi
0x180016fa7  mov     rax, [rax+0B8h]
0x180016fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fb3  mov     rcx, [rsp+898h+var_28]
0x180016fbb  xor     rcx, rsp; StackCookie
0x180016fbe  call    __security_check_cookie
0x180016fc3  mov     rbx, [rsp+898h+arg_10]
0x180016fcb  add     rsp, 880h
0x180016fd2  pop     r14
0x180016fd4  pop     rdi
0x180016fd5  pop     rsi
0x180016fd6  retn
0x180016fd8  cmp     byte ptr [rdi+1FA3h], 0
0x180016fdf  jnz     loc_1800170BA
0x180016fe5  xor     edx, edx; Val
0x180016fe7  lea     rcx, [rsp+898h+var_828]; void *
0x180016fec  mov     r8d, 800h; Size
0x180016ff2  call    memset_0
0x180016ff7  mov     r8d, 400h
0x180016ffd  lea     rdx, [rsp+898h+var_828]
0x180017002  lea     rcx, [rsp+898h+var_868]
0x180017007  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001700e  nop     dword ptr [rax+rax+00h]
0x180017013  mov     rax, [rdi+30h]
0x180017017  lea     rcx, [rsp+898h+var_868]
0x18001701c  mov     rdx, [rax+28h]
0x180017020  movzx   r8d, word ptr [rdx+44h]
0x180017025  mov     rdx, [rdx+58h]
0x180017029  shr     r8d, 1
0x18001702c  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180017033  nop     dword ptr [rax+rax+00h]
0x180017038  test    eax, eax
0x18001703a  js      short loc_1800170A2
0x18001703c  lea     rcx, [rsp+898h+var_868]
0x180017041  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180017048  nop     dword ptr [rax+rax+00h]
0x18001704d  lea     rcx, [rsp+898h+var_868]
0x180017052  mov     ebx, eax
0x180017054  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001705b  nop     dword ptr [rax+rax+00h]
0x180017060  lea     rcx, [rdi+1FA4h]
0x180017067  mov     r8d, ebx; unsigned int
0x18001706a  mov     [rsp+898h+var_878], rcx; bool *
0x18001706f  lea     rsi, [rdi+1FA8h]
0x180017076  mov     rcx, rdi; this
0x180017079  mov     r9, rsi; struct STRU *
0x18001707c  mov     rdx, rax; unsigned __int16 *
0x18001707f  call    ?MapPath@W3_CONTEXT@@QEAAJPEBGKPEAVSTRU@@PEA_N@Z; W3_CONTEXT::MapPath(ushort const *,ulong,STRU *,bool *)
0x180017084  test    eax, eax
0x180017086  js      short loc_1800170A2
0x180017088  lea     rcx, [rsp+898h+var_868]
0x18001708d  mov     byte ptr [rdi+1FA3h], 1
0x180017094  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001709b  nop     dword ptr [rax+rax+00h]
0x1800170a0  jmp     short loc_1800170C1
0x1800170a2  lea     rcx, [rsp+898h+var_868]
0x1800170a7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800170ae  nop     dword ptr [rax+rax+00h]
0x1800170b3  xor     eax, eax
0x1800170b5  jmp     loc_180016FB3
0x1800170ba  lea     rsi, [rdi+1FA8h]
0x1800170c1  test    r14, r14
0x1800170c4  jz      short loc_1800170D8
0x1800170c6  mov     rcx, rsi
0x1800170c9  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800170d0  nop     dword ptr [rax+rax+00h]
0x1800170d5  mov     [r14], eax
0x1800170d8  mov     rcx, rsi
0x1800170db  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800170e2  nop     dword ptr [rax+rax+00h]
0x1800170e7  jmp     loc_180016FB3
```

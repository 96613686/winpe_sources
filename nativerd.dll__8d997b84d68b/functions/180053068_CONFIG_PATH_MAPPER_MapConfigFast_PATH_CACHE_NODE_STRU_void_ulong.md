# CONFIG_PATH_MAPPER::MapConfigFast(_PATH_CACHE_NODE *,STRU *,void * *,ulong *)

- ea: `0x180053068`
- end: `0x1800531c4`
- name: `?MapConfigFast@CONFIG_PATH_MAPPER@@QEAAJPEAU_PATH_CACHE_NODE@@PEAVSTRU@@PEAPEAXPEAK@Z`
- size: `348`
- prototype: `__int64 __usercall@<rax>(CONFIG_PATH_MAPPER *__hidden this@<rcx>, struct _PATH_CACHE_NODE *@<rdx>, struct STRU *@<r8>, void **@<r9>, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18004e9fc`
- `0x18004f92c`
- `0x180050238`

## callees

- `0x180005a30`
- `0x180016ba0`
- `0x180017380`
- `0x1800526b4`
- `0x180053068`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180053199`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180053199`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180053180`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180053180`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800530d3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800530d3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800530f2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800530f2`
- `iisutil!MakePathCanonicalizationProof` at `0x18005318c`
- `iisutil!MakePathCanonicalizationProof` at `0x18005318c`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::MapConfigFast(
        CONFIG_PATH_MAPPER *this,
        struct _PATH_CACHE_NODE *a2,
        struct STRU *a3,
        void **a4,
        unsigned int *a5)
{
  __int64 v9; // rdx
  signed int ParentVdirNode; // ebx
  struct _PATH_CACHE_NODE *v11; // rdi
  const unsigned __int16 *Str; // rax
  struct _PATH_CACHE_NODE *v14; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v15[56]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 v16[264]; // [rsp+60h] [rbp-A0h] BYREF

  v14 = 0;
  memset_0(v16, 0, 0x208u);
  STRU::STRU((STRU *)v15, v16, 0x104u);
  v9 = *((_QWORD *)a2 + 5);
  if ( v9 )
  {
    ParentVdirNode = 0;
    if ( a3 )
    {
      ParentVdirNode = STRU::Copy((STRU *)v15, *(const unsigned __int16 **)(v9 + 8));
      if ( ParentVdirNode < 0 )
        goto LABEL_15;
    }
    v11 = a2;
  }
  else
  {
    ParentVdirNode = CONFIG_PATH_MAPPER::GetParentVdirNode(a2, &v14);
    if ( ParentVdirNode < 0 )
      goto LABEL_15;
    v11 = v14;
    if ( a3 )
    {
      ParentVdirNode = CONFIG_VDIR::GetDirectory(*((CONFIG_VDIR **)v14 + 6), (struct STRU *)v15);
      if ( ParentVdirNode < 0 )
        goto LABEL_15;
      ParentVdirNode = CONFIG_PATH_MAPPER::AppendRelativePath(a2, v11, (struct STRU *)v15);
      if ( ParentVdirNode < 0 )
        goto LABEL_15;
    }
  }
  if ( !a4 || (ParentVdirNode = CONFIG_PATH_MAPPER::GetUserToken(this, v11, a4, 0), ParentVdirNode >= 0) )
  {
    if ( a5 )
      *a5 = *((_DWORD *)a2 + 19);
    if ( a3 )
    {
      Str = STRU::QueryStr((STRU *)v15);
      ParentVdirNode = MakePathCanonicalizationProof(Str, a3);
    }
  }
LABEL_15:
  STRU::~STRU((STRU *)v15);
  return (unsigned int)ParentVdirNode;
}

```

## disassembly

```asm
0x180053068  push    rbp
0x18005306a  push    rbx
0x18005306b  push    rsi
0x18005306c  push    rdi
0x18005306d  push    r12
0x18005306f  push    r13
0x180053071  push    r14
0x180053073  push    r15
0x180053075  lea     rbp, [rsp-188h]
0x18005307d  sub     rsp, 288h
0x180053084  mov     rax, cs:__security_cookie
0x18005308b  xor     rax, rsp
0x18005308e  mov     [rbp+1C0h+var_50], rax
0x180053095  mov     r15, [rbp+1C0h+arg_20]
0x18005309c  mov     rsi, r8
0x18005309f  mov     r14, rdx
0x1800530a2  mov     [rsp+2C0h+var_2A0], 0
0x1800530ab  mov     r13, rcx
0x1800530ae  xor     edx, edx; Val
0x1800530b0  mov     r8d, 208h; Size
0x1800530b6  lea     rcx, [rsp+2C0h+var_260]; void *
0x1800530bb  mov     r12, r9
0x1800530be  call    memset_0
0x1800530c3  mov     r8d, 104h
0x1800530c9  lea     rdx, [rsp+2C0h+var_260]
0x1800530ce  lea     rcx, [rsp+2C0h+var_298]
0x1800530d3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800530d9  mov     rdx, [r14+28h]
0x1800530dd  test    rdx, rdx
0x1800530e0  jz      short loc_180053107
0x1800530e2  xor     ebx, ebx
0x1800530e4  test    rsi, rsi
0x1800530e7  jz      short loc_180053102
0x1800530e9  mov     rdx, [rdx+8]
0x1800530ed  lea     rcx, [rsp+2C0h+var_298]
0x1800530f2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800530f8  mov     ebx, eax
0x1800530fa  test    eax, eax
0x1800530fc  js      loc_180053194
0x180053102  mov     rdi, r14
0x180053105  jmp     short loc_18005314E
0x180053107  lea     rdx, [rsp+2C0h+var_2A0]; struct _PATH_CACHE_NODE **
0x18005310c  mov     rcx, r14; struct _PATH_CACHE_NODE *
0x18005310f  call    ?GetParentVdirNode@CONFIG_PATH_MAPPER@@CAJPEAU_PATH_CACHE_NODE@@PEAPEAU2@@Z; CONFIG_PATH_MAPPER::GetParentVdirNode(_PATH_CACHE_NODE *,_PATH_CACHE_NODE * *)
0x180053114  mov     ebx, eax
0x180053116  test    eax, eax
0x180053118  js      short loc_180053194
0x18005311a  mov     rdi, [rsp+2C0h+var_2A0]
0x18005311f  test    rsi, rsi
0x180053122  jz      short loc_18005314E
0x180053124  mov     rcx, [rdi+30h]; this
0x180053128  lea     rdx, [rsp+2C0h+var_298]; struct STRU *
0x18005312d  call    ?GetDirectory@CONFIG_VDIR@@QEAAJPEAVSTRU@@@Z; CONFIG_VDIR::GetDirectory(STRU *)
0x180053132  mov     ebx, eax
0x180053134  test    eax, eax
0x180053136  js      short loc_180053194
0x180053138  lea     r8, [rsp+2C0h+var_298]; struct STRU *
0x18005313d  mov     rdx, rdi; struct _PATH_CACHE_NODE *
0x180053140  mov     rcx, r14; struct _PATH_CACHE_NODE *
0x180053143  call    ?AppendRelativePath@CONFIG_PATH_MAPPER@@CAJPEAU_PATH_CACHE_NODE@@0PEAVSTRU@@@Z; CONFIG_PATH_MAPPER::AppendRelativePath(_PATH_CACHE_NODE *,_PATH_CACHE_NODE *,STRU *)
0x180053148  mov     ebx, eax
0x18005314a  test    eax, eax
0x18005314c  js      short loc_180053194
0x18005314e  test    r12, r12
0x180053151  jz      short loc_18005316A
0x180053153  xor     r9d, r9d; struct PARSE_ERROR_INFO *
0x180053156  mov     r8, r12; void **
0x180053159  mov     rdx, rdi; struct _PATH_CACHE_NODE *
0x18005315c  mov     rcx, r13; this
0x18005315f  call    ?GetUserToken@CONFIG_PATH_MAPPER@@AEAAJPEAU_PATH_CACHE_NODE@@PEAPEAXPEAVPARSE_ERROR_INFO@@@Z; CONFIG_PATH_MAPPER::GetUserToken(_PATH_CACHE_NODE *,void * *,PARSE_ERROR_INFO *)
0x180053164  mov     ebx, eax
0x180053166  test    eax, eax
0x180053168  js      short loc_180053194
0x18005316a  test    r15, r15
0x18005316d  jz      short loc_180053176
0x18005316f  mov     eax, [r14+4Ch]
0x180053173  mov     [r15], eax
0x180053176  test    rsi, rsi
0x180053179  jz      short loc_180053194
0x18005317b  lea     rcx, [rsp+2C0h+var_298]
0x180053180  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180053186  mov     rcx, rax
0x180053189  mov     rdx, rsi
0x18005318c  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180053192  mov     ebx, eax
0x180053194  lea     rcx, [rsp+2C0h+var_298]
0x180053199  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005319f  mov     eax, ebx
0x1800531a1  mov     rcx, [rbp+1C0h+var_50]
0x1800531a8  xor     rcx, rsp; StackCookie
0x1800531ab  call    __security_check_cookie
0x1800531b0  add     rsp, 288h
0x1800531b7  pop     r15
0x1800531b9  pop     r14
0x1800531bb  pop     r13
0x1800531bd  pop     r12
0x1800531bf  pop     rdi
0x1800531c0  pop     rsi
0x1800531c1  pop     rbx
0x1800531c2  pop     rbp
0x1800531c3  retn
```

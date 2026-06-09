# DeleteOrphanedKeysFromPool(void)

- ea: `0x18001b7fc`
- end: `0x18001b949`
- name: `?DeleteOrphanedKeysFromPool@@YAJXZ`
- size: `333`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019964`

## callees

- `0x18000b0fc`
- `0x18001069c`
- `0x1800198b8`
- `0x18001b6a0`
- `0x18001b7fc`
- `0x18001c09c`
- `0x18001c1e4`

## string_xrefs

- `0x18001b84f`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b8b5`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b8fa`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 DeleteOrphanedKeysFromPool(void)
{
  int v0; // eax
  int v1; // ebx
  __int64 v2; // rdx
  unsigned __int64 v3; // r9
  __int64 v4; // rsi
  __int64 v5; // r12
  __int64 v6; // rax
  const unsigned __int16 *v7; // r15
  __int64 v8; // r14
  int v9; // eax
  int v10; // edi
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rcx
  int v14[2]; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v15; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)v14 = 0;
  v15 = 0;
  v0 = PoolKeyList::Populate((PoolKeyList *)v14);
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = 1926;
LABEL_5:
    v3 = (unsigned int)v0;
    goto LABEL_6;
  }
  v0 = MarkExistingKeys((struct PoolKeyList *)v14);
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = 1929;
    goto LABEL_5;
  }
  v1 = 0;
  v4 = 0;
  if ( !v15 )
  {
LABEL_25:
    v1 = 0;
    goto LABEL_26;
  }
  v5 = *(_QWORD *)v14;
  do
  {
    v6 = v5 + 24 * v4;
    if ( !v6 || *(_BYTE *)(v6 + 16) )
      goto LABEL_22;
    v7 = *(const unsigned __int16 **)v6;
    v8 = *(_QWORD *)(v6 + 8);
    v9 = DeleteFromRegistry(*(const unsigned __int16 **)(v8 + 24), *(const unsigned __int16 **)v6, 1);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v12 = *(const unsigned __int16 **)(v8 + 40);
      if ( !v12 || (v9 = DeleteFromRegistry(v12, v7, 0), v10 = v9, v9 >= 0) )
      {
        v10 = 0;
        goto LABEL_18;
      }
      v11 = 1914;
    }
    else
    {
      v11 = 1907;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v9,
      v14[0]);
LABEL_18:
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x795,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v10,
        v14[0]);
    if ( !v1 )
      v1 = v10;
LABEL_22:
    v4 = (unsigned int)(v4 + 1);
  }
  while ( (unsigned int)v4 < v15 );
  if ( v1 >= 0 )
    goto LABEL_25;
  v3 = (unsigned int)v1;
  v2 = 1949;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
    (const char *)v3,
    v14[0]);
LABEL_26:
  PoolKeyList::~PoolKeyList((PoolKeyList *)v14);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001b7fc  push    rbx
0x18001b7fe  push    rsi
0x18001b7ff  push    rdi
0x18001b800  push    r12
0x18001b802  push    r14
0x18001b804  push    r15
0x18001b806  sub     rsp, 38h
0x18001b80a  mov     qword ptr [rsp+68h+var_48], 0; int
0x18001b813  mov     [rsp+68h+var_40], 0
0x18001b81b  lea     rcx, [rsp+68h+var_48]; this
0x18001b820  call    ?Populate@PoolKeyList@@QEAAJXZ; PoolKeyList::Populate(void)
0x18001b825  mov     ebx, eax
0x18001b827  test    eax, eax
0x18001b829  jns     short loc_18001B832
0x18001b82b  mov     edx, 786h
0x18001b830  jmp     short loc_18001B847
0x18001b832  lea     rcx, [rsp+68h+var_48]; this
0x18001b837  call    ?MarkExistingKeys@@YAJAEAVPoolKeyList@@@Z; MarkExistingKeys(PoolKeyList &)
0x18001b83c  mov     ebx, eax
0x18001b83e  test    eax, eax
0x18001b840  jns     short loc_18001B860
0x18001b842  mov     edx, 789h; void *
0x18001b847  mov     r9d, eax; char *
0x18001b84a  mov     rcx, [rsp+68h]; this
0x18001b84f  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b856  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b85b  jmp     loc_18001B92F
0x18001b860  xor     ebx, ebx
0x18001b862  xor     esi, esi
0x18001b864  cmp     [rsp+68h+var_40], ebx
0x18001b868  jbe     loc_18001B92D
0x18001b86e  mov     r12, qword ptr [rsp+68h+var_48]
0x18001b873  cmp     esi, [rsp+68h+var_40]
0x18001b877  jnb     loc_18001B910
0x18001b87d  lea     rcx, [rsi+rsi*2]
0x18001b881  lea     rax, [r12+rcx*8]
0x18001b885  test    rax, rax
0x18001b888  jz      loc_18001B910
0x18001b88e  cmp     byte ptr [rax+10h], 0
0x18001b892  jnz     short loc_18001B910
0x18001b894  mov     r15, [rax]
0x18001b897  mov     r14, [rax+8]
0x18001b89b  mov     r8b, 1; bool
0x18001b89e  mov     rdx, r15; unsigned __int16 *
0x18001b8a1  mov     rcx, [r14+18h]; unsigned __int16 *
0x18001b8a5  call    ?DeleteFromRegistry@@YAJPEBG0_N@Z; DeleteFromRegistry(ushort const *,ushort const *,bool)
0x18001b8aa  mov     edi, eax
0x18001b8ac  test    eax, eax
0x18001b8ae  jns     short loc_18001B8CB
0x18001b8b0  mov     edx, 773h; void *
0x18001b8b5  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b8bc  mov     r9d, eax; char *
0x18001b8bf  mov     rcx, [rsp+68h]; this
0x18001b8c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b8c9  jmp     short loc_18001B8EE
0x18001b8cb  mov     rcx, [r14+28h]; unsigned __int16 *
0x18001b8cf  test    rcx, rcx
0x18001b8d2  jz      short loc_18001B8EC
0x18001b8d4  xor     r8d, r8d; bool
0x18001b8d7  mov     rdx, r15; unsigned __int16 *
0x18001b8da  call    ?DeleteFromRegistry@@YAJPEBG0_N@Z; DeleteFromRegistry(ushort const *,ushort const *,bool)
0x18001b8df  mov     edi, eax
0x18001b8e1  test    eax, eax
0x18001b8e3  jns     short loc_18001B8EC
0x18001b8e5  mov     edx, 77Ah
0x18001b8ea  jmp     short loc_18001B8B5
0x18001b8ec  xor     edi, edi
0x18001b8ee  mov     rcx, [rsp+68h]; this
0x18001b8f3  test    edi, edi
0x18001b8f5  jns     short loc_18001B90B
0x18001b8f7  mov     r9d, edi; char *
0x18001b8fa  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b901  mov     edx, 795h; void *
0x18001b906  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b90b  test    ebx, ebx
0x18001b90d  cmovz   ebx, edi
0x18001b910  inc     esi
0x18001b912  cmp     esi, [rsp+68h+var_40]
0x18001b916  jb      loc_18001B87D
0x18001b91c  test    ebx, ebx
0x18001b91e  jns     short loc_18001B92D
0x18001b920  mov     r9d, ebx
0x18001b923  mov     edx, 79Dh
0x18001b928  jmp     loc_18001B84A
0x18001b92d  xor     ebx, ebx
0x18001b92f  lea     rcx, [rsp+68h+var_48]; this
0x18001b934  call    ??1PoolKeyList@@QEAA@XZ; PoolKeyList::~PoolKeyList(void)
0x18001b939  mov     eax, ebx
0x18001b93b  add     rsp, 38h
0x18001b93f  pop     r15
0x18001b941  pop     r14
0x18001b943  pop     r12
0x18001b945  pop     rdi
0x18001b946  pop     rsi
0x18001b947  pop     rbx
0x18001b948  retn
```

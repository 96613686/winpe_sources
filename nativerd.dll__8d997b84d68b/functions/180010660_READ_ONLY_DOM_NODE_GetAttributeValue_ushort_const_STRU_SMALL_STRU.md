# READ_ONLY_DOM_NODE::GetAttributeValue(ushort const *,STRU *,SMALL_STRU *)

- ea: `0x180010660`
- end: `0x180010803`
- name: `?GetAttributeValue@READ_ONLY_DOM_NODE@@UEAAJPEBGPEAVSTRU@@PEAVSMALL_STRU@@@Z`
- size: `419`
- prototype: `int(READ_ONLY_DOM_NODE *__hidden this, const unsigned __int16 *, struct STRU *, struct SMALL_STRU *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180010660`
- `0x180010810`
- `0x180010a80`
- `0x180059bd2`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001076a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001076a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001077b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001077b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800107a5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800107a5`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800107ee`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800107ee`

## pseudocode

```c
__int64 __fastcall READ_ONLY_DOM_NODE::GetAttributeValue(
        READ_ONLY_DOM_NODE *this,
        const unsigned __int16 *a2,
        struct STRU *a3,
        struct SMALL_STRU *a4)
{
  unsigned int v7; // ebx
  __int64 v9; // rcx
  unsigned int i; // edi
  __int64 v11; // rcx
  unsigned int (__fastcall ***v12)(_QWORD, _QWORD *); // rax
  const WCHAR *v13; // rbp
  int v14; // r15d
  const unsigned __int16 *v15; // rdi
  __int64 v16; // rax
  SIZE_T v17; // rbx
  HANDLE ProcessHeap; // rax
  void *v19; // rax
  __int64 v20; // rcx
  _QWORD v21[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v22; // [rsp+78h] [rbp+10h] BYREF

  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( a3 )
  {
    if ( a4 )
      return (unsigned int)-2147024809;
  }
  else if ( !a4 )
  {
    return (unsigned int)-2147024809;
  }
  v9 = *((_QWORD *)this + 9);
  v21[0] = &NAMED_ENTRY_KEY::`vftable';
  v7 = -2147023483;
  v21[2] = 0;
  v21[1] = a2;
  if ( !v9 )
  {
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      v11 = *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * i);
      v12 = (unsigned int (__fastcall ***)(_QWORD, _QWORD *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      if ( (**v12)(v12, v21) )
      {
        _mm_lfence();
        v20 = *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * i);
        goto LABEL_26;
      }
    }
    goto LABEL_12;
  }
  v22 = 0;
  if ( (unsigned int)CLKRHashTable::FindKey(v9, v21, &v22) )
  {
LABEL_12:
    v13 = 0;
    v14 = -2147023483;
    goto LABEL_13;
  }
  v20 = v22;
LABEL_26:
  v13 = &szDomain;
  v14 = 0;
  if ( *(_QWORD *)(v20 + 40) )
    v13 = *(const WCHAR **)(v20 + 40);
LABEL_13:
  NAMED_ENTRY_KEY::~NAMED_ENTRY_KEY((NAMED_ENTRY_KEY *)v21);
  v15 = 0;
  if ( v14 >= 0 )
    v15 = v13;
  if ( v15 )
  {
    if ( a3 )
    {
      return (unsigned int)STRU::Copy(a3, v15);
    }
    else
    {
      if ( v15 != *(const unsigned __int16 **)a4 )
      {
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
        v17 = 2 * v16 + 2;
        SMALL_STRU::Reset(a4);
        ProcessHeap = GetProcessHeap();
        v19 = HeapAlloc(ProcessHeap, 8u, v17);
        *(_QWORD *)a4 = v19;
        if ( !v19 )
          return (unsigned int)-2147024888;
        memcpy_0(v19, v15, v17);
      }
      return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180010660  mov     [rsp+arg_0], rbx
0x180010665  mov     [rsp+arg_10], rbp
0x18001066a  push    rsi
0x18001066b  push    rdi
0x18001066c  push    r12
0x18001066e  push    r14
0x180010670  push    r15
0x180010672  sub     rsp, 40h
0x180010676  xor     r12d, r12d
0x180010679  mov     rsi, r9
0x18001067c  mov     r14, r8
0x18001067f  mov     rbp, rcx
0x180010682  test    rdx, rdx
0x180010685  jz      short loc_180010691
0x180010687  test    r8, r8
0x18001068a  jz      short loc_1800106B1
0x18001068c  test    r9, r9
0x18001068f  jz      short loc_1800106B6
0x180010691  mov     ebx, 80070057h
0x180010696  lea     r11, [rsp+68h+var_28]
0x18001069b  mov     eax, ebx
0x18001069d  mov     rbx, [r11+30h]
0x1800106a1  mov     rbp, [r11+40h]
0x1800106a5  mov     rsp, r11
0x1800106a8  pop     r15
0x1800106aa  pop     r14
0x1800106ac  pop     r12
0x1800106ae  pop     rdi
0x1800106af  pop     rsi
0x1800106b0  retn
0x1800106b1  test    rsi, rsi
0x1800106b4  jz      short loc_180010691
0x1800106b6  mov     rcx, [rcx+48h]
0x1800106ba  lea     rax, ??_7NAMED_ENTRY_KEY@@6B@; const NAMED_ENTRY_KEY::`vftable'
0x1800106c1  mov     [rsp+68h+var_48], rax
0x1800106c6  mov     ebx, 80070585h
0x1800106cb  mov     [rsp+68h+var_38], r12
0x1800106d0  mov     [rsp+68h+var_40], rdx
0x1800106d5  test    rcx, rcx
0x1800106d8  jnz     loc_1800107DF
0x1800106de  mov     edi, r12d
0x1800106e1  cmp     edi, [rbp+40h]
0x1800106e4  jnb     short loc_18001071F
0x1800106e6  mov     rax, [rbp+38h]
0x1800106ea  mov     r15d, edi
0x1800106ed  mov     rcx, [rax+r15*8]
0x1800106f1  mov     rax, [rcx]
0x1800106f4  mov     rax, [rax+8]
0x1800106f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106fd  mov     r8, rax
0x180010700  lea     rdx, [rsp+68h+var_48]
0x180010705  mov     rcx, [rax]
0x180010708  mov     rax, [rcx]
0x18001070b  mov     rcx, r8
0x18001070e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010713  test    eax, eax
0x180010715  jnz     loc_1800107BC
0x18001071b  inc     edi
0x18001071d  jmp     short loc_1800106E1
0x18001071f  mov     rbp, r12
0x180010722  mov     r15d, ebx
0x180010725  lea     rcx, [rsp+68h+var_48]; this
0x18001072a  call    ??1NAMED_ENTRY_KEY@@UEAA@XZ; NAMED_ENTRY_KEY::~NAMED_ENTRY_KEY(void)
0x18001072f  test    r15d, r15d
0x180010732  mov     rdi, r12
0x180010735  cmovns  rdi, rbp
0x180010739  test    rdi, rdi
0x18001073c  jz      loc_180010696
0x180010742  test    r14, r14
0x180010745  jnz     short loc_18001079F
0x180010747  cmp     rdi, [rsi]
0x18001074a  jz      short loc_180010797
0x18001074c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010750  inc     rax
0x180010753  cmp     [rdi+rax*2], r12w
0x180010758  jnz     short loc_180010750
0x18001075a  mov     rcx, rsi; this
0x18001075d  lea     rbx, ds:2[rax*2]
0x180010765  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x18001076a  call    cs:__imp_GetProcessHeap
0x180010770  mov     r8, rbx; dwBytes
0x180010773  mov     edx, 8; dwFlags
0x180010778  mov     rcx, rax; hHeap
0x18001077b  call    cs:__imp_HeapAlloc
0x180010781  mov     [rsi], rax
0x180010784  test    rax, rax
0x180010787  jz      short loc_1800107B2
0x180010789  mov     r8, rbx; Size
0x18001078c  mov     rdx, rdi; Src
0x18001078f  mov     rcx, rax; void *
0x180010792  call    memcpy_0
0x180010797  mov     ebx, r12d
0x18001079a  jmp     loc_180010696
0x18001079f  mov     rdx, rdi
0x1800107a2  mov     rcx, r14
0x1800107a5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800107ab  mov     ebx, eax
0x1800107ad  jmp     loc_180010696
0x1800107b2  mov     ebx, 80070008h
0x1800107b7  jmp     loc_180010696
0x1800107bc  lfence
0x1800107bf  mov     rax, [rbp+38h]
0x1800107c3  mov     rcx, [rax+r15*8]
0x1800107c7  cmp     [rcx+28h], r12
0x1800107cb  lea     rbp, szDomain
0x1800107d2  mov     r15d, r12d
0x1800107d5  cmovnz  rbp, [rcx+28h]
0x1800107da  jmp     loc_180010725
0x1800107df  lea     r8, [rsp+68h+arg_8]
0x1800107e4  mov     [rsp+68h+arg_8], r12
0x1800107e9  lea     rdx, [rsp+68h+var_48]
0x1800107ee  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800107f4  test    eax, eax
0x1800107f6  jnz     loc_18001071F
0x1800107fc  mov     rcx, [rsp+68h+arg_8]
0x180010801  jmp     short loc_1800107C7
```

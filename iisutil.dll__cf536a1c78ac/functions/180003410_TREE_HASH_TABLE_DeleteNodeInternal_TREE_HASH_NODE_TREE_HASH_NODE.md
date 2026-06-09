# TREE_HASH_TABLE::DeleteNodeInternal(TREE_HASH_NODE * *,TREE_HASH_NODE *)

- ea: `0x180003410`
- end: `0x1800034e5`
- name: `?DeleteNodeInternal@TREE_HASH_TABLE@@AEAAXPEAPEAUTREE_HASH_NODE@@PEAU2@@Z`
- size: `213`
- prototype: `void __fastcall(TREE_HASH_TABLE *__hidden this, struct TREE_HASH_NODE **, struct TREE_HASH_NODE *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ec0`
- `0x180002fd0`
- `0x180003410`

## callees

- `0x180003410`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034b1`

## pseudocode

```c
void __fastcall TREE_HASH_TABLE::DeleteNodeInternal(
        TREE_HASH_TABLE *this,
        struct TREE_HASH_NODE **a2,
        struct TREE_HASH_NODE *a3)
{
  __int64 v5; // rdx
  _QWORD *i; // rdx
  __int64 v7; // r8
  __int64 v8; // rsi
  struct TREE_HASH_NODE **v9; // rdx
  struct TREE_HASH_NODE *j; // rcx
  __int64 v11; // rdx
  HANDLE ProcessHeap; // rax

  *a2 = *(struct TREE_HASH_NODE **)a3;
  v5 = *((_QWORD *)a3 + 1);
  if ( v5 )
  {
    for ( i = (_QWORD *)(v5 + 16); (struct TREE_HASH_NODE *)*i != a3; i = (_QWORD *)(*i + 24LL) )
      ;
    *i = *((_QWORD *)a3 + 3);
  }
  v7 = *((_QWORD *)a3 + 2);
  if ( v7 )
  {
    do
    {
      v8 = *(_QWORD *)(v7 + 24);
      v9 = (struct TREE_HASH_NODE **)(*((_QWORD *)this + 1)
                                    + 8LL * (unsigned int)(*(_DWORD *)(v7 + 48) % *((_DWORD *)this + 4)));
      for ( j = *v9; j != (struct TREE_HASH_NODE *)v7; j = *(struct TREE_HASH_NODE **)j )
        v9 = (struct TREE_HASH_NODE **)j;
      *(_QWORD *)(v7 + 8) = 0;
      TREE_HASH_TABLE::DeleteNodeInternal(this, v9, (struct TREE_HASH_NODE *)v7);
      v7 = v8;
    }
    while ( v8 );
  }
  v11 = *((_QWORD *)a3 + 4);
  if ( v11 )
    (*(void (__fastcall **)(TREE_HASH_TABLE *, __int64, __int64))(*(_QWORD *)this + 8LL))(this, v11, v7);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a3);
  --*((_DWORD *)this + 5);
}

```

## disassembly

```asm
0x180003410  mov     [rsp+arg_0], rbx
0x180003415  mov     [rsp+arg_8], rsi
0x18000341a  push    rdi
0x18000341b  sub     rsp, 20h
0x18000341f  mov     rax, [r8]
0x180003422  mov     rbx, r8
0x180003425  mov     [rdx], rax
0x180003428  mov     rdi, rcx
0x18000342b  mov     rdx, [r8+8]
0x18000342f  test    rdx, rdx
0x180003432  jz      short loc_18000344D
0x180003434  add     rdx, 10h
0x180003438  jmp     short loc_18000343E
0x18000343a  lea     rdx, [rax+18h]
0x18000343e  mov     rax, [rdx]
0x180003441  cmp     rax, rbx
0x180003444  jnz     short loc_18000343A
0x180003446  mov     rax, [r8+18h]
0x18000344a  mov     [rdx], rax
0x18000344d  mov     r8, [r8+10h]; struct TREE_HASH_NODE *
0x180003451  test    r8, r8
0x180003454  jz      short loc_180003499
0x180003456  mov     eax, [r8+30h]
0x18000345a  xor     edx, edx
0x18000345c  div     dword ptr [rdi+10h]
0x18000345f  mov     rax, [rdi+8]
0x180003463  mov     rsi, [r8+18h]
0x180003467  lea     rdx, [rax+rdx*8]
0x18000346b  mov     rcx, [rdx]
0x18000346e  cmp     rcx, r8
0x180003471  jz      short loc_180003481
0x180003473  mov     rax, [rcx]
0x180003476  mov     rdx, rcx; struct TREE_HASH_NODE **
0x180003479  mov     rcx, rax
0x18000347c  cmp     rax, r8
0x18000347f  jnz     short loc_180003473
0x180003481  mov     rcx, rdi; this
0x180003484  mov     qword ptr [r8+8], 0
0x18000348c  call    ?DeleteNodeInternal@TREE_HASH_TABLE@@AEAAXPEAPEAUTREE_HASH_NODE@@PEAU2@@Z; TREE_HASH_TABLE::DeleteNodeInternal(TREE_HASH_NODE * *,TREE_HASH_NODE *)
0x180003491  mov     r8, rsi
0x180003494  test    rsi, rsi
0x180003497  jnz     short loc_180003456
0x180003499  mov     rdx, [rbx+20h]
0x18000349d  test    rdx, rdx
0x1800034a0  jz      short loc_1800034B1
0x1800034a2  mov     rax, [rdi]
0x1800034a5  mov     rcx, rdi
0x1800034a8  mov     rax, [rax+8]
0x1800034ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b1  call    cs:__imp_GetProcessHeap
0x1800034b8  nop     dword ptr [rax+rax+00h]
0x1800034bd  mov     r8, rbx; lpMem
0x1800034c0  xor     edx, edx; dwFlags
0x1800034c2  mov     rcx, rax; hHeap
0x1800034c5  call    cs:__imp_HeapFree
0x1800034cc  nop     dword ptr [rax+rax+00h]
0x1800034d1  dec     dword ptr [rdi+14h]
0x1800034d4  mov     rbx, [rsp+28h+arg_0]
0x1800034d9  mov     rsi, [rsp+28h+arg_8]
0x1800034de  add     rsp, 20h
0x1800034e2  pop     rdi
0x1800034e3  retn
```

# TREE_HASH_TABLE::DeleteNodeInternal(TREE_HASH_NODE * *,TREE_HASH_NODE *)

- ea: `0x180002a90`
- end: `0x180002b58`
- name: `?DeleteNodeInternal@TREE_HASH_TABLE@@AEAAXPEAPEAUTREE_HASH_NODE@@PEAU2@@Z`
- size: `200`
- prototype: `void __fastcall(TREE_HASH_TABLE *__hidden this, struct TREE_HASH_NODE **, struct TREE_HASH_NODE *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002570`
- `0x180002680`
- `0x180002a90`

## callees

- `0x180002a90`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002b3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002b3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b31`

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
0x180002a90  mov     [rsp+arg_0], rbx
0x180002a95  mov     [rsp+arg_8], rsi
0x180002a9a  push    rdi
0x180002a9b  sub     rsp, 20h
0x180002a9f  mov     rax, [r8]
0x180002aa2  mov     rbx, r8
0x180002aa5  mov     [rdx], rax
0x180002aa8  mov     rdi, rcx
0x180002aab  mov     rdx, [r8+8]
0x180002aaf  test    rdx, rdx
0x180002ab2  jz      short loc_180002ACD
0x180002ab4  add     rdx, 10h
0x180002ab8  jmp     short loc_180002ABE
0x180002aba  lea     rdx, [rax+18h]
0x180002abe  mov     rax, [rdx]
0x180002ac1  cmp     rax, rbx
0x180002ac4  jnz     short loc_180002ABA
0x180002ac6  mov     rax, [r8+18h]
0x180002aca  mov     [rdx], rax
0x180002acd  mov     r8, [r8+10h]; struct TREE_HASH_NODE *
0x180002ad1  test    r8, r8
0x180002ad4  jz      short loc_180002B19
0x180002ad6  mov     eax, [r8+30h]
0x180002ada  xor     edx, edx
0x180002adc  div     dword ptr [rdi+10h]
0x180002adf  mov     rax, [rdi+8]
0x180002ae3  mov     rsi, [r8+18h]
0x180002ae7  lea     rdx, [rax+rdx*8]
0x180002aeb  mov     rcx, [rdx]
0x180002aee  cmp     rcx, r8
0x180002af1  jz      short loc_180002B01
0x180002af3  mov     rax, [rcx]
0x180002af6  mov     rdx, rcx; struct TREE_HASH_NODE **
0x180002af9  mov     rcx, rax
0x180002afc  cmp     rax, r8
0x180002aff  jnz     short loc_180002AF3
0x180002b01  mov     rcx, rdi; this
0x180002b04  mov     qword ptr [r8+8], 0
0x180002b0c  call    ?DeleteNodeInternal@TREE_HASH_TABLE@@AEAAXPEAPEAUTREE_HASH_NODE@@PEAU2@@Z; TREE_HASH_TABLE::DeleteNodeInternal(TREE_HASH_NODE * *,TREE_HASH_NODE *)
0x180002b11  mov     r8, rsi
0x180002b14  test    rsi, rsi
0x180002b17  jnz     short loc_180002AD6
0x180002b19  mov     rdx, [rbx+20h]
0x180002b1d  test    rdx, rdx
0x180002b20  jz      short loc_180002B31
0x180002b22  mov     rax, [rdi]
0x180002b25  mov     rcx, rdi
0x180002b28  mov     rax, [rax+8]
0x180002b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b31  call    cs:__imp_GetProcessHeap
0x180002b37  mov     r8, rbx; lpMem
0x180002b3a  xor     edx, edx; dwFlags
0x180002b3c  mov     rcx, rax; hHeap
0x180002b3f  call    cs:__imp_HeapFree
0x180002b45  dec     dword ptr [rdi+14h]
0x180002b48  mov     rbx, [rsp+28h+arg_0]
0x180002b4d  mov     rsi, [rsp+28h+arg_8]
0x180002b52  add     rsp, 20h
0x180002b56  pop     rdi
0x180002b57  retn
```

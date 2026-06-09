# std::vector<NDFExecutedRepair,std::allocator<NDFExecutedRepair>>::_Reallocate(unsigned __int64)

- ea: `0x18000fca8`
- end: `0x18000fd3b`
- name: `?_Reallocate@?$vector@UNDFExecutedRepair@@V?$allocator@UNDFExecutedRepair@@@std@@@std@@IEAAX_K@Z`
- size: `147`
- prototype: `_OWORD *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18000f590`

## callees

- `0x1800018c0`
- `0x180001ac8`
- `0x18000b930`
- `0x18000fca8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fd0f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fd0f`

## pseudocode

```c
_OWORD *__fastcall std::vector<NDFExecutedRepair>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  __int64 v3; // rbx
  _OWORD *v4; // rax
  _OWORD *v5; // rdi
  void *v6; // rcx
  __int64 v7; // rsi
  _OWORD *result; // rax
  _OWORD *v9; // [rsp+68h] [rbp+10h]

  if ( a2 )
  {
    if ( a2 > 0xFFFFFFFFFFFFFFFLL || (v3 = a2, v4 = operator new(16 * a2), v5 = v4, (v9 = v4) == 0) )
      std::_Xbad_alloc();
  }
  else
  {
    v5 = 0;
    v9 = 0;
    v3 = 0;
  }
  try
  {
    std::_Uninit_move<NDFExecutedRepair *,NDFExecutedRepair *,std::allocator<NDFExecutedRepair>,NDFExecutedRepair>(
      *(_OWORD **)a1,
      *(_OWORD **)(a1 + 8),
      v5);
    v6 = *(void **)a1;
    v7 = *(_QWORD *)(a1 + 8) - *(_QWORD *)a1;
    if ( *(_QWORD *)a1 )
      operator delete(v6);
    result = &v5[v3];
    *(_QWORD *)(a1 + 16) = &v5[v3];
    *(_QWORD *)(a1 + 8) = (char *)v5 + (v7 & 0xFFFFFFFFFFFFFFF0uLL);
    *(_QWORD *)a1 = v5;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<std::_Tree_node<std::pair<std::wstring const,_GUID>,void *>>>::deallocate(v6, v9);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000fca8  push    rbx
0x18000fcaa  push    rsi
0x18000fcab  push    rdi
0x18000fcac  push    r14
0x18000fcae  sub     rsp, 38h
0x18000fcb2  mov     rbx, rdx
0x18000fcb5  mov     r14, rcx
0x18000fcb8  test    rdx, rdx
0x18000fcbb  jz      short loc_18000FCE7
0x18000fcbd  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000fcc7  cmp     rdx, rax
0x18000fcca  ja      short loc_18000FD35
0x18000fccc  shl     rbx, 4
0x18000fcd0  mov     rcx, rbx; Size
0x18000fcd3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fcd8  mov     rdi, rax
0x18000fcdb  mov     [rsp+58h+arg_8], rax
0x18000fce0  test    rax, rax
0x18000fce3  jz      short loc_18000FD35
0x18000fce5  jmp     short loc_18000FCF0
0x18000fce7  xor     edi, edi
0x18000fce9  mov     [rsp+58h+arg_8], rdi
0x18000fcee  xor     ebx, ebx
0x18000fcf0  mov     r8, rdi
0x18000fcf3  mov     rdx, [r14+8]
0x18000fcf7  mov     rcx, [r14]
0x18000fcfa  call    ??$_Uninit_move@PEAUNDFExecutedRepair@@PEAU1@V?$allocator@UNDFExecutedRepair@@@std@@U1@@std@@YAPEAUNDFExecutedRepair@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@UNDFExecutedRepair@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<NDFExecutedRepair *,NDFExecutedRepair *,std::allocator<NDFExecutedRepair>,NDFExecutedRepair>(NDFExecutedRepair *,NDFExecutedRepair *,NDFExecutedRepair *,std::_Wrap_alloc<std::allocator<NDFExecutedRepair>> &,NDFExecutedRepair *,std::_Nonscalar_ptr_iterator_tag)
0x18000fcff  nop
0x18000fd00  mov     rcx, [r14]
0x18000fd03  mov     rsi, [r14+8]
0x18000fd07  sub     rsi, rcx
0x18000fd0a  test    rcx, rcx
0x18000fd0d  jz      short loc_18000FD15
0x18000fd0f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fd15  lea     rax, [rbx+rdi]
0x18000fd19  mov     [r14+10h], rax
0x18000fd1d  and     rsi, 0FFFFFFFFFFFFFFF0h
0x18000fd21  add     rsi, rdi
0x18000fd24  mov     [r14+8], rsi
0x18000fd28  mov     [r14], rdi
0x18000fd2b  add     rsp, 38h
0x18000fd2f  pop     r14
0x18000fd31  pop     rdi
0x18000fd32  pop     rsi
0x18000fd33  pop     rbx
0x18000fd34  retn
0x18000fd35  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```

# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::_Reallocate(unsigned __int64)

- ea: `0x18003a82c`
- end: `0x18003a90b`
- name: `?_Reallocate@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `223`
- prototype: `__int64 *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003a914`

## callees

- `0x1800021b4`
- `0x1800396ac`
- `0x18003a82c`
- `0x180047010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18003a87e`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18003a87e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a8db`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a8db`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall std::vector<std::unique_ptr<ProvPackage>>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 *v6; // r14
  __int64 *v7; // r13
  __int64 v8; // r12
  __int64 **v9; // rsi
  __int64 *result; // rax
  void *v11; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v11 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = operator new(8 * a2), (v11 = v4) == 0) )
      std::_Xbad_alloc();
  }
  try
  {
    v9 = (__int64 **)(a1 + 8);
    std::_Uninit_move<std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::allocator<std::unique_ptr<ProvPackage>>,std::unique_ptr<ProvPackage>>(
      *(__int64 **)a1,
      *(__int64 **)(a1 + 8),
      v4);
  }
  catch ( ... )
  {
    std::_Tree_buy<unsigned short const *>::_Freenode0(v5, v11);
    throw;
  }
  v6 = *(__int64 **)a1;
  v7 = *v9;
  v8 = ((__int64)*v9 - *(_QWORD *)a1) >> 3;
  if ( *(_QWORD *)a1 )
  {
    if ( v6 != v7 )
    {
      do
      {
        if ( *v6 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*v6 + 64LL))(*v6, 1);
        ++v6;
      }
      while ( v6 != v7 );
      v9 = (__int64 **)(a1 + 8);
    }
    operator delete(*(void **)a1);
  }
  *(_QWORD *)(a1 + 16) = &v4[a2];
  result = &v4[v8];
  *v9 = result;
  *(_QWORD *)a1 = v4;
  return result;
}

```

## disassembly

```asm
0x18003a82c  mov     [rsp+arg_0], rbx
0x18003a831  mov     [rsp+arg_10], rsi
0x18003a836  push    rdi
0x18003a837  push    r12
0x18003a839  push    r13
0x18003a83b  push    r14
0x18003a83d  push    r15
0x18003a83f  sub     rsp, 30h
0x18003a843  mov     r15, rdx
0x18003a846  mov     rdi, rcx
0x18003a849  xor     ebx, ebx
0x18003a84b  mov     [rsp+58h+arg_8], rbx
0x18003a850  test    rdx, rdx
0x18003a853  jz      short loc_18003A885
0x18003a855  mov     rax, 1FFFFFFFFFFFFFFFh
0x18003a85f  cmp     rdx, rax
0x18003a862  ja      short loc_18003A87E
0x18003a864  lea     rcx, ds:0[rdx*8]; Size
0x18003a86c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a871  mov     rbx, rax
0x18003a874  mov     [rsp+58h+arg_8], rax
0x18003a879  test    rax, rax
0x18003a87c  jnz     short loc_18003A885
0x18003a87e  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18003a884  nop
0x18003a885  lea     rsi, [rdi+8]
0x18003a889  mov     r8, rbx
0x18003a88c  mov     rdx, [rsi]
0x18003a88f  mov     rcx, [rdi]
0x18003a892  call    ??$_Uninit_move@PEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::allocator<std::unique_ptr<ProvPackage>>,std::unique_ptr<ProvPackage>>(std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::unique_ptr<ProvPackage> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<ProvPackage>>> &,std::unique_ptr<ProvPackage> *,std::_Nonscalar_ptr_iterator_tag)
0x18003a897  nop
0x18003a898  mov     r14, [rdi]
0x18003a89b  mov     r13, [rsi]
0x18003a89e  mov     r12, r13
0x18003a8a1  sub     r12, r14
0x18003a8a4  sar     r12, 3
0x18003a8a8  test    r14, r14
0x18003a8ab  jz      short loc_18003A8E1
0x18003a8ad  cmp     r14, r13
0x18003a8b0  jz      short loc_18003A8D8
0x18003a8b2  mov     rcx, [r14]
0x18003a8b5  test    rcx, rcx
0x18003a8b8  jz      short loc_18003A8CB
0x18003a8ba  mov     rax, [rcx]
0x18003a8bd  mov     edx, 1
0x18003a8c2  mov     rax, [rax+40h]
0x18003a8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8cb  add     r14, 8
0x18003a8cf  cmp     r14, r13
0x18003a8d2  jnz     short loc_18003A8B2
0x18003a8d4  lea     rsi, [rdi+8]
0x18003a8d8  mov     rcx, [rdi]
0x18003a8db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a8e1  lea     rax, [rbx+r15*8]
0x18003a8e5  mov     [rdi+10h], rax
0x18003a8e9  lea     rax, [rbx+r12*8]
0x18003a8ed  mov     [rsi], rax
0x18003a8f0  mov     [rdi], rbx
0x18003a8f3  mov     rbx, [rsp+58h+arg_0]
0x18003a8f8  mov     rsi, [rsp+58h+arg_10]
0x18003a8fd  add     rsp, 30h
0x18003a901  pop     r15
0x18003a903  pop     r14
0x18003a905  pop     r13
0x18003a907  pop     r12
0x18003a909  pop     rdi
0x18003a90a  retn
```

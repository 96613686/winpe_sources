# std::vector<PropertyBagEntryItem,std::allocator<PropertyBagEntryItem>>::_Reallocate(unsigned __int64)

- ea: `0x180011980`
- end: `0x180011a13`
- name: `?_Reallocate@?$vector@UPropertyBagEntryItem@@V?$allocator@UPropertyBagEntryItem@@@std@@@std@@IEAAX_K@Z`
- size: `147`
- prototype: `_OWORD *__fastcall(void **, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x180011a1c`

## callees

- `0x1800017f4`
- `0x1800018d8`
- `0x180011668`
- `0x180011980`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800119ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800119ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall std::vector<PropertyBagEntryItem>::_Reallocate(void **a1, unsigned __int64 a2)
{
  _OWORD *v3; // rsi
  __int64 v4; // rbx
  signed __int64 v5; // rdi
  _OWORD *result; // rax
  void *v7; // [rsp+68h] [rbp+10h]

  v3 = 0;
  v7 = 0;
  if ( a2 )
  {
    if ( a2 > 0xFFFFFFFFFFFFFFFLL || (v4 = a2, v3 = operator new(16 * a2), (v7 = v3) == 0) )
      std::_Xbad_alloc();
  }
  else
  {
    v4 = 0;
  }
  try
  {
    std::_Uninit_move<PropertyBagEntry *,PropertyBagEntry *,std::allocator<PropertyBagEntry>,PropertyBagEntry>(
      *a1,
      a1[1],
      v3);
  }
  catch ( ... )
  {
    operator delete(v7);
    throw;
  }
  v5 = (_BYTE *)a1[1] - (_BYTE *)*a1;
  if ( *a1 )
    operator delete(*a1);
  result = &v3[v4];
  a1[2] = &v3[v4];
  a1[1] = (char *)v3 + (v5 & 0xFFFFFFFFFFFFFFF0uLL);
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180011980  push    rbx
0x180011982  push    rsi
0x180011983  push    rdi
0x180011984  push    r14
0x180011986  sub     rsp, 38h
0x18001198a  mov     rbx, rdx
0x18001198d  mov     r14, rcx
0x180011990  xor     esi, esi
0x180011992  mov     [rsp+58h+arg_8], rsi
0x180011997  test    rdx, rdx
0x18001199a  jz      short loc_1800119CA
0x18001199c  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800119a6  cmp     rdx, rax
0x1800119a9  ja      short loc_1800119C4
0x1800119ab  shl     rbx, 4
0x1800119af  mov     rcx, rbx; Size
0x1800119b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800119b7  mov     rsi, rax
0x1800119ba  mov     [rsp+58h+arg_8], rax
0x1800119bf  test    rax, rax
0x1800119c2  jnz     short loc_1800119CE
0x1800119c4  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800119ca  shl     rbx, 4
0x1800119ce  mov     r8, rsi
0x1800119d1  mov     rdx, [r14+8]
0x1800119d5  mov     rcx, [r14]
0x1800119d8  call    ??$_Uninit_move@PEAUPropertyBagEntry@@PEAU1@V?$allocator@UPropertyBagEntry@@@std@@U1@@std@@YAPEAUPropertyBagEntry@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@UPropertyBagEntry@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<PropertyBagEntry *,PropertyBagEntry *,std::allocator<PropertyBagEntry>,PropertyBagEntry>(PropertyBagEntry *,PropertyBagEntry *,PropertyBagEntry *,std::_Wrap_alloc<std::allocator<PropertyBagEntry>> &,PropertyBagEntry *,std::_Nonscalar_ptr_iterator_tag)
0x1800119dd  nop
0x1800119de  mov     rcx, [r14]
0x1800119e1  mov     rdi, [r14+8]
0x1800119e5  sub     rdi, rcx
0x1800119e8  test    rcx, rcx
0x1800119eb  jz      short loc_1800119F3
0x1800119ed  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800119f3  lea     rax, [rbx+rsi]
0x1800119f7  mov     [r14+10h], rax
0x1800119fb  and     rdi, 0FFFFFFFFFFFFFFF0h
0x1800119ff  add     rdi, rsi
0x180011a02  mov     [r14+8], rdi
0x180011a06  mov     [r14], rsi
0x180011a09  add     rsp, 38h
0x180011a0d  pop     r14
0x180011a0f  pop     rdi
0x180011a10  pop     rsi
0x180011a11  pop     rbx
0x180011a12  retn
```

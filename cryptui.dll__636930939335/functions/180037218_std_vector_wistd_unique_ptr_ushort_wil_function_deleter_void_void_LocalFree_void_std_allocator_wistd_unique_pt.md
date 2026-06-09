# std::vector<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>,std::allocator<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>>::_Reallocate(unsigned __int64)

- ea: `0x180037218`
- end: `0x1800372b4`
- name: `?_Reallocate@?$vector@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@std@@@std@@IEAAX_K@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800372bc`

## callees

- `0x180001354`
- `0x180001508`
- `0x180034904`
- `0x1800371d4`
- `0x180037218`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180037291`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037291`

## pseudocode

```c
char *__fastcall std::vector<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::_Reallocate(
        _QWORD *a1,
        unsigned __int64 a2)
{
  char *v4; // rbx
  __int64 v5; // r14
  char *result; // rax
  void *v7; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v7 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = (char *)operator new(8 * a2), (v7 = v4) == 0) )
      std::_Xbad_alloc();
  }
  try
  {
    std::_Uninit_move<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>> *,wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>> *,std::allocator<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>,wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(
      *a1,
      a1[1],
      v4);
  }
  catch ( ... )
  {
    operator delete(v7);
    throw;
  }
  v5 = (__int64)(a1[1] - *a1) >> 3;
  if ( *a1 )
  {
    std::vector<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::_Destroy();
    operator delete((void *)*a1);
  }
  a1[2] = &v4[8 * a2];
  result = &v4[8 * v5];
  a1[1] = result;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180037218  push    rbx
0x18003721a  push    rsi
0x18003721b  push    rdi
0x18003721c  push    r14
0x18003721e  sub     rsp, 38h
0x180037222  mov     rsi, rdx
0x180037225  mov     rdi, rcx
0x180037228  xor     ebx, ebx
0x18003722a  mov     [rsp+58h+arg_8], rbx
0x18003722f  test    rdx, rdx
0x180037232  jz      short loc_180037263
0x180037234  mov     rax, 1FFFFFFFFFFFFFFFh
0x18003723e  cmp     rdx, rax
0x180037241  ja      short loc_18003725D
0x180037243  lea     rcx, ds:0[rdx*8]; Size
0x18003724b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037250  mov     rbx, rax
0x180037253  mov     [rsp+58h+arg_8], rax
0x180037258  test    rax, rax
0x18003725b  jnz     short loc_180037263
0x18003725d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180037263  mov     r8, rbx
0x180037266  mov     rdx, [rdi+8]
0x18003726a  mov     rcx, [rdi]
0x18003726d  call    ??$_Uninit_move@PEAV?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@PEAV12@V?$allocator@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@std@@V12@@std@@YAPEAV?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> *,wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> *,std::allocator<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>,wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> *,wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> *,wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> *,std::_Wrap_alloc<std::allocator<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>> &,wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> *,std::_Nonscalar_ptr_iterator_tag)
0x180037272  nop
0x180037273  mov     rdx, [rdi]
0x180037276  mov     r8, [rdi+8]
0x18003727a  mov     r14, r8
0x18003727d  sub     r14, rdx
0x180037280  sar     r14, 3
0x180037284  test    rdx, rdx
0x180037287  jz      short loc_180037297
0x180037289  call    ?_Destroy@?$vector@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@std@@@std@@IEAAXPEAV?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@0@Z; std::vector<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::_Destroy(wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> *,wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> *)
0x18003728e  mov     rcx, [rdi]
0x180037291  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180037297  lea     rax, [rbx+rsi*8]
0x18003729b  mov     [rdi+10h], rax
0x18003729f  lea     rax, [rbx+r14*8]
0x1800372a3  mov     [rdi+8], rax
0x1800372a7  mov     [rdi], rbx
0x1800372aa  add     rsp, 38h
0x1800372ae  pop     r14
0x1800372b0  pop     rdi
0x1800372b1  pop     rsi
0x1800372b2  pop     rbx
0x1800372b3  retn
```

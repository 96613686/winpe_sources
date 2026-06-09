# std::vector<wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>,std::allocator<wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>>>::_Reallocate(unsigned __int64)

- ea: `0x18001e650`
- end: `0x18001e6f5`
- name: `?_Reallocate@?$vector@V?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@@std@@@std@@IEAAX_K@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18001e778`

## callees

- `0x180010e8c`
- `0x180011038`
- `0x18001e280`
- `0x18001e3dc`
- `0x18001e650`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001e6c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e6c2`

## pseudocode

```c
char *__fastcall std::vector<wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>>::_Reallocate(
        __int64 a1,
        unsigned __int64 a2)
{
  __int64 v3; // rdi
  char *v4; // rax
  char *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rsi
  char *result; // rax
  char *v9; // [rsp+68h] [rbp+10h]

  if ( a2 )
  {
    if ( a2 > 0xFFFFFFFFFFFFFFFLL || (v3 = 16 * a2, v4 = (char *)operator new(16 * a2), v5 = v4, (v9 = v4) == 0) )
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
    std::_Uninit_move<wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64> *,wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64> *,std::allocator<wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>>,wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>>();
    v7 = *(_QWORD *)(a1 + 8) - *(_QWORD *)a1;
    if ( *(_QWORD *)a1 )
    {
      std::vector<wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>>::_Destroy();
      operator delete(*(void **)a1);
    }
    result = &v5[v3];
    *(_QWORD *)(a1 + 16) = &v5[v3];
    *(_QWORD *)(a1 + 8) = &v5[v7 & 0xFFFFFFFFFFFFFFF0uLL];
    *(_QWORD *)a1 = v5;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::deallocate(
      v6,
      v9);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001e650  push    rbx
0x18001e652  push    rsi
0x18001e653  push    rdi
0x18001e654  push    r14
0x18001e656  sub     rsp, 38h
0x18001e65a  mov     rdi, rdx
0x18001e65d  mov     r14, rcx
0x18001e660  test    rdx, rdx
0x18001e663  jz      short loc_18001E68F
0x18001e665  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001e66f  cmp     rdx, rax
0x18001e672  ja      short loc_18001E6EF
0x18001e674  shl     rdi, 4
0x18001e678  mov     rcx, rdi; Size
0x18001e67b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e680  mov     rbx, rax
0x18001e683  mov     [rsp+58h+arg_8], rax
0x18001e688  test    rax, rax
0x18001e68b  jz      short loc_18001E6EF
0x18001e68d  jmp     short loc_18001E698
0x18001e68f  xor     ebx, ebx
0x18001e691  mov     [rsp+58h+arg_8], rbx
0x18001e696  xor     edi, edi
0x18001e698  mov     r8, rbx
0x18001e69b  mov     rdx, [r14+8]
0x18001e69f  mov     rcx, [r14]
0x18001e6a2  call    ??$_Uninit_move@PEAV?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@PEAV12@V?$allocator@V?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@@std@@V12@@std@@YAPEAV?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z
0x18001e6a7  nop
0x18001e6a8  mov     rdx, [r14]
0x18001e6ab  mov     r8, [r14+8]
0x18001e6af  mov     rsi, r8
0x18001e6b2  sub     rsi, rdx
0x18001e6b5  test    rdx, rdx
0x18001e6b8  jz      short loc_18001E6CE
0x18001e6ba  call    ?_Destroy@?$vector@V?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@@std@@@std@@IEAAXPEAV?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@0@Z; std::vector<wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>>::_Destroy(wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64> *,wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64> *)
0x18001e6bf  mov     rcx, [r14]
0x18001e6c2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e6c9  nop     dword ptr [rax+rax+00h]
0x18001e6ce  lea     rax, [rdi+rbx]
0x18001e6d2  mov     [r14+10h], rax
0x18001e6d6  and     rsi, 0FFFFFFFFFFFFFFF0h
0x18001e6da  add     rsi, rbx
0x18001e6dd  mov     [r14+8], rsi
0x18001e6e1  mov     [r14], rbx
0x18001e6e4  add     rsp, 38h
0x18001e6e8  pop     r14
0x18001e6ea  pop     rdi
0x18001e6eb  pop     rsi
0x18001e6ec  pop     rbx
0x18001e6ed  retn
0x18001e6ef  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```

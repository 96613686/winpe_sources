# Details::ClientStringAllocator::make_string_nothrow(ushort const *)

- ea: `0x18002b26c`
- end: `0x18002b3ca`
- name: `?make_string_nothrow@ClientStringAllocator@Details@@QEAAXPEBG@Z`
- size: `350`
- prototype: `void(Details::ClientStringAllocator *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a744`
- `0x18002ab0c`

## callees

- `0x1800073aa`
- `0x180007438`
- `0x180007fd5`
- `0x18000b948`
- `0x180029f2c`
- `0x18002b26c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002b34e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002b34e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b2c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b38d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b2c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b38d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b37a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b2bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b2df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b2bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b2df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b31c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b31c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b3a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b3a0`

## string_xrefs

- `0x18002b3b8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall Details::ClientStringAllocator::make_string_nothrow(
        Details::ClientStringAllocator *this,
        const unsigned __int16 *a2,
        __int64 a3,
        const char *a4)
{
  void **v6; // rdi
  void *v7; // rsi
  HLOCAL v8; // rbp
  DWORD v9; // ebx
  HLOCAL v10; // rcx
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rax
  size_t v13; // rbx
  size_t v14; // r14
  char *v15; // rax
  char *v16; // rdi
  void **v17; // rsi
  void *v18; // rbp
  DWORD LastError; // ebx
  HLOCAL hMem; // [rsp+20h] [rbp-48h] BYREF
  char v21; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( *(_DWORD *)this )
  {
    if ( !a2 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v11 = 0x7FFFFFFF;
    v12 = a2;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    v13 = 2 * (v12 - a2);
    v14 = v13 + 2;
    v15 = (char *)CoTaskMemAlloc(v13 + 2);
    v16 = v15;
    if ( v15 )
    {
      if ( v13 )
      {
        if ( v14 < v13 )
        {
          memset_0(v15, 0, v14);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v15, a2, v13);
        }
      }
      *(_WORD *)&v16[v13] = 0;
    }
    v17 = (void **)((char *)this + 16);
    if ( (char *)this + 16 == &v21 )
    {
      if ( v16 )
        CoTaskMemFree(v16);
    }
    else
    {
      v18 = *v17;
      if ( *v17 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v18);
        SetLastError(LastError);
      }
      *v17 = v16;
    }
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &hMem,
      a2,
      -1);
    v6 = (void **)((char *)this + 8);
    if ( (HLOCAL *)((char *)this + 8) == &hMem )
    {
      v10 = hMem;
    }
    else
    {
      v7 = *v6;
      v8 = hMem;
      if ( *v6 )
      {
        v9 = GetLastError();
        LocalFree(v7);
        SetLastError(v9);
      }
      *v6 = v8;
      v10 = 0;
    }
    if ( v10 )
      LocalFree(v10);
  }
}

```

## disassembly

```asm
0x18002b26c  push    rbx
0x18002b26e  push    rbp
0x18002b26f  push    rsi
0x18002b270  push    rdi
0x18002b271  push    r14
0x18002b273  push    r15
0x18002b275  sub     rsp, 38h
0x18002b279  xor     r15d, r15d
0x18002b27c  mov     rsi, rdx
0x18002b27f  mov     rbp, rcx
0x18002b282  cmp     [rcx], r15d
0x18002b285  jnz     short loc_18002B2EA
0x18002b287  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b28b  lea     rcx, [rsp+68h+hMem]
0x18002b290  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002b295  lea     rax, [rsp+68h+hMem]
0x18002b29a  lea     rdi, [rbp+8]
0x18002b29e  cmp     rdi, rax
0x18002b2a1  jz      short loc_18002B2D1
0x18002b2a3  mov     rsi, [rdi]
0x18002b2a6  mov     rbp, [rsp+68h+hMem]
0x18002b2ab  test    rsi, rsi
0x18002b2ae  jz      short loc_18002B2C9
0x18002b2b0  call    cs:__imp_GetLastError
0x18002b2b6  mov     rcx, rsi; hMem
0x18002b2b9  mov     ebx, eax
0x18002b2bb  call    cs:__imp_LocalFree
0x18002b2c1  mov     ecx, ebx; dwErrCode
0x18002b2c3  call    cs:__imp_SetLastError
0x18002b2c9  mov     [rdi], rbp
0x18002b2cc  mov     rcx, r15
0x18002b2cf  jmp     short loc_18002B2D6
0x18002b2d1  mov     rcx, [rsp+68h+hMem]; hMem
0x18002b2d6  test    rcx, rcx
0x18002b2d9  jz      loc_18002B3A6
0x18002b2df  call    cs:__imp_LocalFree
0x18002b2e5  jmp     loc_18002B3A6
0x18002b2ea  test    rsi, rsi
0x18002b2ed  jz      loc_18002B3B3
0x18002b2f3  mov     ecx, 7FFFFFFFh
0x18002b2f8  mov     rax, rsi
0x18002b2fb  cmp     [rax], r15w
0x18002b2ff  jz      short loc_18002B30B
0x18002b301  add     rax, 2
0x18002b305  sub     rcx, 1
0x18002b309  jnz     short loc_18002B2FB
0x18002b30b  sub     rax, rsi
0x18002b30e  sar     rax, 1
0x18002b311  lea     rbx, [rax+rax]
0x18002b315  lea     r14, [rbx+2]
0x18002b319  mov     rcx, r14; cb
0x18002b31c  call    cs:__imp_CoTaskMemAlloc
0x18002b322  mov     rdi, rax
0x18002b325  test    rax, rax
0x18002b328  jz      short loc_18002B364
0x18002b32a  test    rbx, rbx
0x18002b32d  jz      short loc_18002B35F
0x18002b32f  mov     rcx, rax; void *
0x18002b332  cmp     r14, rbx
0x18002b335  jb      short loc_18002B344
0x18002b337  mov     r8, rbx; Size
0x18002b33a  mov     rdx, rsi; Src
0x18002b33d  call    memcpy_0
0x18002b342  jmp     short loc_18002B35F
0x18002b344  mov     r8, r14; Size
0x18002b347  xor     edx, edx; Val
0x18002b349  call    memset_0
0x18002b34e  call    cs:__imp__o__errno
0x18002b354  mov     dword ptr [rax], 22h ; '"'
0x18002b35a  call    _invalid_parameter_noinfo
0x18002b35f  mov     [rbx+rdi], r15w
0x18002b364  lea     rsi, [rbp+10h]
0x18002b368  lea     rax, [rsp+68h+var_40]
0x18002b36d  cmp     rsi, rax
0x18002b370  jz      short loc_18002B398
0x18002b372  mov     rbp, [rsi]
0x18002b375  test    rbp, rbp
0x18002b378  jz      short loc_18002B393
0x18002b37a  call    cs:__imp_GetLastError
0x18002b380  mov     rcx, rbp; pv
0x18002b383  mov     ebx, eax
0x18002b385  call    cs:__imp_CoTaskMemFree
0x18002b38b  mov     ecx, ebx; dwErrCode
0x18002b38d  call    cs:__imp_SetLastError
0x18002b393  mov     [rsi], rdi
0x18002b396  jmp     short loc_18002B3A6
0x18002b398  test    rdi, rdi
0x18002b39b  jz      short loc_18002B3A6
0x18002b39d  mov     rcx, rdi; pv
0x18002b3a0  call    cs:__imp_CoTaskMemFree
0x18002b3a6  add     rsp, 38h
0x18002b3aa  pop     r15
0x18002b3ac  pop     r14
0x18002b3ae  pop     rdi
0x18002b3af  pop     rsi
0x18002b3b0  pop     rbp
0x18002b3b1  pop     rbx
0x18002b3b2  retn
0x18002b3b3  mov     rcx, [rsp+68h]; this
0x18002b3b8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b3bf  mov     edx, 0F89h; void *
0x18002b3c4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

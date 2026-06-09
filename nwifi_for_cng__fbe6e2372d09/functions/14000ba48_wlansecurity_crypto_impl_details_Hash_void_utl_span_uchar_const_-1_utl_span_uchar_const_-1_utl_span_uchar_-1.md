# wlansecurity::crypto::impl::details::Hash(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)

- ea: `0x14000ba48`
- end: `0x14000bb41`
- name: `?Hash@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@1V?$span@E$0?0@6@@Z`
- size: `249`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b120`
- `0x14000b430`
- `0x14001f4d4`
- `0x140023e44`
- `0x140024e84`
- `0x14008fda0`
- `0x1400900e4`
- `0x1400901b8`

## callees

- `0x14000ba48`
- `0x14000bb48`
- `0x14000cbe8`
- `0x14009bbf0`

## import_xrefs

- `ksecdd!BCryptHashData` at `0x14000bac1`
- `ksecdd!BCryptHashData` at `0x14000bac1`
- `ksecdd!BCryptCreateHash` at `0x14000ba98`
- `ksecdd!BCryptCreateHash` at `0x14000ba98`
- `ksecdd!BCryptFinishHash` at `0x14000bae1`
- `ksecdd!BCryptFinishHash` at `0x14000bae1`
- `ksecdd!BCryptDestroyHash` at `0x14000bafc`
- `ksecdd!BCryptDestroyHash` at `0x14000bb19`

## pseudocode

```c
__int64 __fastcall wlansecurity::crypto::impl::details::Hash(void *a1, __int64 a2, __int64 a3, __int64 a4)
{
  UCHAR *pbSecret; // rax
  NTSTATUS v7; // esi
  NTSTATUS v8; // ebx
  ULONG cbSecret; // [rsp+28h] [rbp-40h]
  BCRYPT_HASH_HANDLE *p_hHash; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  char v13; // [rsp+50h] [rbp-18h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+A0h] [rbp+38h] BYREF

  p_hHash = &hHash;
  cbSecret = *(_DWORD *)(a3 + 8);
  pbSecret = *(UCHAR **)a3;
  hHash = 0;
  phHash = 0;
  v13 = 1;
  v7 = BCryptCreateHash(a1, &phHash, 0, 0, pbSecret, cbSecret, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_hHash);
  if ( v7 < 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    return (unsigned int)v7;
  }
  else
  {
    v8 = BCryptHashData(hHash, *(PUCHAR *)a2, *(_DWORD *)(a2 + 8), 0);
    if ( v8 < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
      return (unsigned int)v8;
    }
    v8 = BCryptFinishHash(hHash, *(PUCHAR *)a4, *(_DWORD *)(a4 + 8), 0);
    if ( v8 < 0 )
    {
      if ( hHash )
        ((void (__fastcall *)(BCRYPT_HASH_HANDLE))BCryptDestroyHash)(hHash);
      return (unsigned int)v8;
    }
    if ( hHash )
      ((void (__fastcall *)(BCRYPT_HASH_HANDLE))BCryptDestroyHash)(hHash);
    return 0;
  }
}

```

## disassembly

```asm
0x14000ba48  push    rbp
0x14000ba4a  push    rbx
0x14000ba4b  push    rsi
0x14000ba4c  push    rdi
0x14000ba4d  mov     rbp, rsp
0x14000ba50  sub     rsp, 68h
0x14000ba54  lea     rax, [rbp+hHash]
0x14000ba58  mov     [rsp+68h+dwFlags], 0; dwFlags
0x14000ba60  mov     [rbp+var_28], rax
0x14000ba64  mov     rdi, r9
0x14000ba67  mov     eax, [r8+8]
0x14000ba6b  mov     rbx, rdx
0x14000ba6e  mov     [rsp+68h+cbSecret], eax; cbSecret
0x14000ba72  lea     rdx, [rbp+phHash]; phHash
0x14000ba76  mov     rax, [r8]
0x14000ba79  xor     r9d, r9d; cbHashObject
0x14000ba7c  xor     r8d, r8d; pbHashObject
0x14000ba7f  mov     [rsp+68h+pbSecret], rax; pbSecret
0x14000ba84  mov     [rbp+hHash], 0
0x14000ba8c  mov     [rbp+phHash], 0
0x14000ba94  mov     [rbp+var_18], 1
0x14000ba98  call    cs:__imp_BCryptCreateHash
0x14000ba9f  nop     dword ptr [rax+rax+00h]
0x14000baa4  lea     rcx, [rbp+var_28]
0x14000baa8  mov     esi, eax
0x14000baaa  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x14000baaf  test    esi, esi
0x14000bab1  js      short loc_14000BB29
0x14000bab3  mov     r8d, [rbx+8]; cbInput
0x14000bab7  xor     r9d, r9d; dwFlags
0x14000baba  mov     rdx, [rbx]; pbInput
0x14000babd  mov     rcx, [rbp+hHash]; hHash
0x14000bac1  call    cs:__imp_BCryptHashData
0x14000bac8  nop     dword ptr [rax+rax+00h]
0x14000bacd  mov     ebx, eax
0x14000bacf  test    eax, eax
0x14000bad1  js      short loc_14000BB36
0x14000bad3  mov     r8d, [rdi+8]; cbOutput
0x14000bad7  xor     r9d, r9d; dwFlags
0x14000bada  mov     rdx, [rdi]; pbOutput
0x14000badd  mov     rcx, [rbp+hHash]; hHash
0x14000bae1  call    cs:__imp_BCryptFinishHash
0x14000bae8  nop     dword ptr [rax+rax+00h]
0x14000baed  mov     rcx, [rbp+hHash]
0x14000baf1  mov     ebx, eax
0x14000baf3  test    eax, eax
0x14000baf5  jns     short loc_14000BB14
0x14000baf7  test    rcx, rcx
0x14000bafa  jz      short loc_14000BB08
0x14000bafc  mov     rax, cs:__imp_BCryptDestroyHash
0x14000bb03  call    _guard_dispatch_icall
0x14000bb08  mov     eax, ebx
0x14000bb0a  add     rsp, 68h
0x14000bb0e  pop     rdi
0x14000bb0f  pop     rsi
0x14000bb10  pop     rbx
0x14000bb11  pop     rbp
0x14000bb12  retn
0x14000bb14  test    rcx, rcx
0x14000bb17  jz      short loc_14000BB25
0x14000bb19  mov     rax, cs:__imp_BCryptDestroyHash
0x14000bb20  call    _guard_dispatch_icall
0x14000bb25  xor     eax, eax
0x14000bb27  jmp     short loc_14000BB0A
0x14000bb29  lea     rcx, [rbp+hHash]
0x14000bb2d  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000bb32  mov     eax, esi
0x14000bb34  jmp     short loc_14000BB0A
0x14000bb36  lea     rcx, [rbp+hHash]
0x14000bb3a  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000bb3f  jmp     short loc_14000BB08
```

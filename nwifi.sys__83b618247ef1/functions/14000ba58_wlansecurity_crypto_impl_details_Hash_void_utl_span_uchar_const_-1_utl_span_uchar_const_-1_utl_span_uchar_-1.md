# wlansecurity::crypto::impl::details::Hash(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)

- ea: `0x14000ba58`
- end: `0x14000bb51`
- name: `?Hash@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@1V?$span@E$0?0@6@@Z`
- size: `249`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b130`
- `0x14000b440`
- `0x14001f4d4`
- `0x140023e44`
- `0x140024e84`
- `0x14008e5c0`
- `0x14008e904`
- `0x14008e9d8`

## callees

- `0x14000ba58`
- `0x14000bb58`
- `0x14000cbf8`
- `0x14009a410`

## import_xrefs

- `ksecdd!BCryptHashData` at `0x14000bad1`
- `ksecdd!BCryptHashData` at `0x14000bad1`
- `ksecdd!BCryptCreateHash` at `0x14000baa8`
- `ksecdd!BCryptCreateHash` at `0x14000baa8`
- `ksecdd!BCryptFinishHash` at `0x14000baf1`
- `ksecdd!BCryptFinishHash` at `0x14000baf1`
- `ksecdd!BCryptDestroyHash` at `0x14000bb0c`
- `ksecdd!BCryptDestroyHash` at `0x14000bb29`

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
0x14000ba58  push    rbp
0x14000ba5a  push    rbx
0x14000ba5b  push    rsi
0x14000ba5c  push    rdi
0x14000ba5d  mov     rbp, rsp
0x14000ba60  sub     rsp, 68h
0x14000ba64  lea     rax, [rbp+hHash]
0x14000ba68  mov     [rsp+68h+dwFlags], 0; dwFlags
0x14000ba70  mov     [rbp+var_28], rax
0x14000ba74  mov     rdi, r9
0x14000ba77  mov     eax, [r8+8]
0x14000ba7b  mov     rbx, rdx
0x14000ba7e  mov     [rsp+68h+cbSecret], eax; cbSecret
0x14000ba82  lea     rdx, [rbp+phHash]; phHash
0x14000ba86  mov     rax, [r8]
0x14000ba89  xor     r9d, r9d; cbHashObject
0x14000ba8c  xor     r8d, r8d; pbHashObject
0x14000ba8f  mov     [rsp+68h+pbSecret], rax; pbSecret
0x14000ba94  mov     [rbp+hHash], 0
0x14000ba9c  mov     [rbp+phHash], 0
0x14000baa4  mov     [rbp+var_18], 1
0x14000baa8  call    cs:__imp_BCryptCreateHash
0x14000baaf  nop     dword ptr [rax+rax+00h]
0x14000bab4  lea     rcx, [rbp+var_28]
0x14000bab8  mov     esi, eax
0x14000baba  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x14000babf  test    esi, esi
0x14000bac1  js      short loc_14000BB39
0x14000bac3  mov     r8d, [rbx+8]; cbInput
0x14000bac7  xor     r9d, r9d; dwFlags
0x14000baca  mov     rdx, [rbx]; pbInput
0x14000bacd  mov     rcx, [rbp+hHash]; hHash
0x14000bad1  call    cs:__imp_BCryptHashData
0x14000bad8  nop     dword ptr [rax+rax+00h]
0x14000badd  mov     ebx, eax
0x14000badf  test    eax, eax
0x14000bae1  js      short loc_14000BB46
0x14000bae3  mov     r8d, [rdi+8]; cbOutput
0x14000bae7  xor     r9d, r9d; dwFlags
0x14000baea  mov     rdx, [rdi]; pbOutput
0x14000baed  mov     rcx, [rbp+hHash]; hHash
0x14000baf1  call    cs:__imp_BCryptFinishHash
0x14000baf8  nop     dword ptr [rax+rax+00h]
0x14000bafd  mov     rcx, [rbp+hHash]
0x14000bb01  mov     ebx, eax
0x14000bb03  test    eax, eax
0x14000bb05  jns     short loc_14000BB24
0x14000bb07  test    rcx, rcx
0x14000bb0a  jz      short loc_14000BB18
0x14000bb0c  mov     rax, cs:__imp_BCryptDestroyHash
0x14000bb13  call    _guard_dispatch_icall
0x14000bb18  mov     eax, ebx
0x14000bb1a  add     rsp, 68h
0x14000bb1e  pop     rdi
0x14000bb1f  pop     rsi
0x14000bb20  pop     rbx
0x14000bb21  pop     rbp
0x14000bb22  retn
0x14000bb24  test    rcx, rcx
0x14000bb27  jz      short loc_14000BB35
0x14000bb29  mov     rax, cs:__imp_BCryptDestroyHash
0x14000bb30  call    _guard_dispatch_icall
0x14000bb35  xor     eax, eax
0x14000bb37  jmp     short loc_14000BB1A
0x14000bb39  lea     rcx, [rbp+hHash]
0x14000bb3d  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000bb42  mov     eax, esi
0x14000bb44  jmp     short loc_14000BB1A
0x14000bb46  lea     rcx, [rbp+hHash]
0x14000bb4a  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000bb4f  jmp     short loc_14000BB18
```

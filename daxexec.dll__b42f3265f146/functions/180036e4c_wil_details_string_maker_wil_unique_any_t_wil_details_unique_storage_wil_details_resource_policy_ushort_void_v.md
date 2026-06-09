# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x180036e4c`
- end: `0x180036eec`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025afc`

## callees

- `0x18002b6a8`
- `0x180036e4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036e9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036e8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ebd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036e8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ebd`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        void **a1,
        __int64 a2,
        __int64 a3)
{
  void **v4; // rax
  void **v5; // rsi
  void *v6; // rbp
  void *v7; // r14
  DWORD LastError; // ebx
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v4 = (void **)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &pv,
                  a2,
                  a3);
  v5 = v4;
  if ( a1 != v4 )
  {
    v6 = *a1;
    v7 = *v4;
    if ( *a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v6);
      SetLastError(LastError);
    }
    *a1 = v7;
    *v5 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return *a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180036e4c  mov     [rsp+arg_8], rbx
0x180036e51  mov     [rsp+arg_10], rbp
0x180036e56  push    rsi
0x180036e57  push    rdi
0x180036e58  push    r14
0x180036e5a  sub     rsp, 20h
0x180036e5e  mov     rdi, rcx
0x180036e61  lea     rcx, [rsp+38h+pv]
0x180036e66  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180036e6b  mov     rsi, rax
0x180036e6e  cmp     rdi, rax
0x180036e71  jz      short loc_180036EB3
0x180036e73  mov     rbp, [rdi]
0x180036e76  mov     r14, [rax]
0x180036e79  test    rbp, rbp
0x180036e7c  jz      short loc_180036EA9
0x180036e7e  call    cs:__imp_GetLastError
0x180036e85  nop     dword ptr [rax+rax+00h]
0x180036e8a  mov     rcx, rbp; pv
0x180036e8d  mov     ebx, eax
0x180036e8f  call    cs:__imp_CoTaskMemFree
0x180036e96  nop     dword ptr [rax+rax+00h]
0x180036e9b  mov     ecx, ebx; dwErrCode
0x180036e9d  call    cs:__imp_SetLastError
0x180036ea4  nop     dword ptr [rax+rax+00h]
0x180036ea9  mov     [rdi], r14
0x180036eac  mov     qword ptr [rsi], 0
0x180036eb3  mov     rcx, [rsp+38h+pv]; pv
0x180036eb8  test    rcx, rcx
0x180036ebb  jz      short loc_180036EC9
0x180036ebd  call    cs:__imp_CoTaskMemFree
0x180036ec4  nop     dword ptr [rax+rax+00h]
0x180036ec9  mov     rax, [rdi]
0x180036ecc  mov     rbx, [rsp+38h+arg_8]
0x180036ed1  neg     rax
0x180036ed4  mov     rbp, [rsp+38h+arg_10]
0x180036ed9  sbb     eax, eax
0x180036edb  not     eax
0x180036edd  and     eax, 8007000Eh
0x180036ee2  add     rsp, 20h
0x180036ee6  pop     r14
0x180036ee8  pop     rdi
0x180036ee9  pop     rsi
0x180036eea  retn
```

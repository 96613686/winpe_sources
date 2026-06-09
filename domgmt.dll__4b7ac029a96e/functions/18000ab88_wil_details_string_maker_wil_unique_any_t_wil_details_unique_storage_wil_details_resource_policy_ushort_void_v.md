# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x18000ab88`
- end: `0x18000ac0f`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `135`
- prototype: `__int64 __fastcall(void **, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006af8`

## callees

- `0x1800080fc`
- `0x18000ab88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000abcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000abcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abe7`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        void **a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  void **v5; // rax
  void **v6; // rsi
  void *v7; // rbp
  void *v8; // r14
  DWORD LastError; // ebx
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v5 = (void **)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &pv,
                  a2,
                  a3,
                  a4);
  v6 = v5;
  if ( a1 != v5 )
  {
    v7 = *a1;
    v8 = *v5;
    if ( *a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v7);
      SetLastError(LastError);
    }
    *a1 = v8;
    *v6 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return *a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18000ab88  mov     [rsp+arg_8], rbx
0x18000ab8d  mov     [rsp+arg_10], rbp
0x18000ab92  push    rsi
0x18000ab93  push    rdi
0x18000ab94  push    r14
0x18000ab96  sub     rsp, 20h
0x18000ab9a  mov     rdi, rcx
0x18000ab9d  lea     rcx, [rsp+38h+pv]
0x18000aba2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000aba7  mov     rsi, rax
0x18000abaa  cmp     rdi, rax
0x18000abad  jz      short loc_18000ABDD
0x18000abaf  mov     rbp, [rdi]
0x18000abb2  mov     r14, [rax]
0x18000abb5  test    rbp, rbp
0x18000abb8  jz      short loc_18000ABD3
0x18000abba  call    cs:__imp_GetLastError
0x18000abc0  mov     rcx, rbp; pv
0x18000abc3  mov     ebx, eax
0x18000abc5  call    cs:__imp_CoTaskMemFree
0x18000abcb  mov     ecx, ebx; dwErrCode
0x18000abcd  call    cs:__imp_SetLastError
0x18000abd3  mov     [rdi], r14
0x18000abd6  mov     qword ptr [rsi], 0
0x18000abdd  mov     rcx, [rsp+38h+pv]; pv
0x18000abe2  test    rcx, rcx
0x18000abe5  jz      short loc_18000ABED
0x18000abe7  call    cs:__imp_CoTaskMemFree
0x18000abed  mov     rax, [rdi]
0x18000abf0  mov     rbx, [rsp+38h+arg_8]
0x18000abf5  neg     rax
0x18000abf8  mov     rbp, [rsp+38h+arg_10]
0x18000abfd  sbb     eax, eax
0x18000abff  not     eax
0x18000ac01  and     eax, 8007000Eh
0x18000ac06  add     rsp, 20h
0x18000ac0a  pop     r14
0x18000ac0c  pop     rdi
0x18000ac0d  pop     rsi
0x18000ac0e  retn
```

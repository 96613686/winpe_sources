# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)

- ea: `0x18000ac5c`
- end: `0x18000ac73`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000cc45`
- `0x18000cc57`

## callees

- `0x18000ac5c`

## import_xrefs

- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000ac68`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000ac68`

## pseudocode

```c
__int64 __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return FreeTransientObjectSecurityDescriptor(v1);
  return result;
}

```

## disassembly

```asm
0x18000ac5c  sub     rsp, 28h
0x18000ac60  mov     rcx, [rcx]
0x18000ac63  test    rcx, rcx
0x18000ac66  jz      short loc_18000AC6E
0x18000ac68  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000ac6e  add     rsp, 28h
0x18000ac72  retn
```

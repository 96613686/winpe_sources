# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NsiDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NsiDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180032404`
- end: `0x18003241b`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?NsiDisconnectFromServer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800323d8`
- `0x180035ff0`
- `0x180036674`

## callees

- `0x180032404`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x180032410`
- `WINNSI!NsiDisconnectFromServer` at `0x180032410`

## pseudocode

```c
__int64 __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NsiDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NsiDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return NsiDisconnectFromServer();
  return result;
}

```

## disassembly

```asm
0x180032404  sub     rsp, 28h
0x180032408  mov     rcx, [rcx]
0x18003240b  test    rcx, rcx
0x18003240e  jz      short loc_180032416
0x180032410  call    cs:__imp_NsiDisconnectFromServer
0x180032416  add     rsp, 28h
0x18003241a  retn
```

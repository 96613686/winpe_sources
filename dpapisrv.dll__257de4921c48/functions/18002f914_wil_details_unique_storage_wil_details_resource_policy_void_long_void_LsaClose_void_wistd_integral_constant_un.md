# wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18002f914`
- end: `0x18002f932`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: `NTSTATUS __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002f908`
- `0x180030f00`
- `0x180032e84`

## callees

- `0x18002f914`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002f920`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002f920`

## pseudocode

```c
NTSTATUS __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx
  NTSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return LsaClose(v1);
  return result;
}

```

## disassembly

```asm
0x18002f914  sub     rsp, 28h
0x18002f918  mov     rcx, [rcx]; ObjectHandle
0x18002f91b  test    rcx, rcx
0x18002f91e  jz      short loc_18002F92C
0x18002f920  call    cs:__imp_LsaClose
0x18002f927  nop     dword ptr [rax+rax+00h]
0x18002f92c  add     rsp, 28h
0x18002f930  retn
```

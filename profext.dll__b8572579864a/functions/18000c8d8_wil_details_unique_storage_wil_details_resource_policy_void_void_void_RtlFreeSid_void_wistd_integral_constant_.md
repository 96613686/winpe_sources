# wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000c8d8`
- end: `0x18000c8e9`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `17`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000c8cc`
- `0x18000ca58`
- `0x180016740`
- `0x18001f390`
- `0x18001fc88`
- `0x18001fed0`
- `0x180020664`

## callees

- `0x18000c8d8`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18000c8e2`

## pseudocode

```c
PVOID __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx
  PVOID result; // rax

  v1 = *a1;
  if ( v1 )
    return RtlFreeSid(v1);
  return result;
}

```

## disassembly

```asm
0x18000c8d8  mov     rcx, [rcx]
0x18000c8db  test    rcx, rcx
0x18000c8de  jnz     short loc_18000C8E2
0x18000c8e0  retn
0x18000c8e2  jmp     cs:__imp_RtlFreeSid
```

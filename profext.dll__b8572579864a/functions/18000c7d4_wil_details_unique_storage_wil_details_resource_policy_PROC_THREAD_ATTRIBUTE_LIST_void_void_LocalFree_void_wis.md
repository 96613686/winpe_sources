# wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)

- ea: `0x18000c7d4`
- end: `0x18000c7f2`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `27`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800045bc`
- `0x18000ad78`
- `0x18000b7e0`
- `0x18000c7c8`
- `0x18000ca58`
- `0x180013ab4`
- `0x180013de4`
- `0x180016740`
- `0x18001a380`
- `0x18001cc00`
- `0x18001d7dc`
- `0x18001d970`
- `0x18001de80`
- `0x18001e2b8`
- `0x18001ef94`
- `0x18001f2b0`
- `0x18001f390`
- `0x18001f5e4`
- `0x18001f7b0`
- `0x18001fa9c`
- `0x18001fc88`
- `0x18001fed0`
- `0x180020488`
- `0x180020558`
- `0x180020664`
- `0x180020898`
- `0x180020ab0`

## callees

- `0x18000c7d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7e0`

## pseudocode

```c
HLOCAL __fastcall wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx
  HLOCAL result; // rax

  v1 = *a1;
  if ( v1 )
    return LocalFree(v1);
  return result;
}

```

## disassembly

```asm
0x18000c7d4  sub     rsp, 28h
0x18000c7d8  mov     rcx, [rcx]; hMem
0x18000c7db  test    rcx, rcx
0x18000c7de  jz      short loc_18000C7EC
0x18000c7e0  call    cs:__imp_LocalFree
0x18000c7e7  nop     dword ptr [rax+rax+00h]
0x18000c7ec  add     rsp, 28h
0x18000c7f0  retn
```

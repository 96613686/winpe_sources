# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)

- ea: `0x14000f088`
- end: `0x14000f0a7`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ReleaseConfigRefreshMutex@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140015ec7`

## callees

- `0x14000f088`

## import_xrefs

- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14000f094`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14000f094`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    ReleaseConfigRefreshMutex(v1);
}

```

## disassembly

```asm
0x14000f088  sub     rsp, 28h
0x14000f08c  mov     rcx, [rcx]
0x14000f08f  test    rcx, rcx
0x14000f092  jz      short loc_14000F0A1
0x14000f094  call    cs:__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z; ReleaseConfigRefreshMutex(void *)
0x14000f09b  nop     dword ptr [rax+rax+00h]
0x14000f0a0  nop
0x14000f0a1  add     rsp, 28h
0x14000f0a5  retn
```

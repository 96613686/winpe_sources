# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)

- ea: `0x180011024`
- end: `0x18001103c`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ReleaseConfigRefreshMutex@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180038ede`

## callees

- `0x180011024`

## import_xrefs

- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x180011030`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x180011030`

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
0x180011024  sub     rsp, 28h
0x180011028  mov     rcx, [rcx]
0x18001102b  test    rcx, rcx
0x18001102e  jz      short loc_180011037
0x180011030  call    cs:__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z; ReleaseConfigRefreshMutex(void *)
0x180011036  nop
0x180011037  add     rsp, 28h
0x18001103b  retn
```

# tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)

- ea: `0x14001f978`
- end: `0x14001f9dc`
- name: `??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140023bac`
- `0x140048ad0`

## callees

- `0x14000d7ec`
- `0x14001f978`
- `0x14001fa58`
- `0x14001faf0`
- `0x14001fb84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001f988`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001f988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f9c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f9c9`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(__int64 a1)
{
  void *v2; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  if ( *(_QWORD *)(a1 + 240) )
    TestClose();
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(a1 + 120);
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(a1 + 96);
  tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(a1 + 72);
  v2 = *(void **)(a1 + 8);
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x14001f978  push    rbx
0x14001f97a  sub     rsp, 20h
0x14001f97e  mov     rbx, rcx
0x14001f981  add     rcx, 0C0h; lpCriticalSection
0x14001f988  call    cs:__imp_DeleteCriticalSection
0x14001f98f  nop     dword ptr [rax+rax+00h]
0x14001f994  mov     rcx, [rbx+0F0h]
0x14001f99b  test    rcx, rcx
0x14001f99e  jz      short loc_14001F9A5
0x14001f9a0  call    TestClose
0x14001f9a5  lea     rcx, [rbx+78h]
0x14001f9a9  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x14001f9ae  lea     rcx, [rbx+60h]
0x14001f9b2  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x14001f9b7  lea     rcx, [rbx+48h]
0x14001f9bb  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x14001f9c0  mov     rcx, [rbx+8]; pv
0x14001f9c4  test    rcx, rcx
0x14001f9c7  jz      short loc_14001F9D5
0x14001f9c9  call    cs:__imp_CoTaskMemFree
0x14001f9d0  nop     dword ptr [rax+rax+00h]
0x14001f9d5  add     rsp, 20h
0x14001f9d9  pop     rbx
0x14001f9da  retn
```

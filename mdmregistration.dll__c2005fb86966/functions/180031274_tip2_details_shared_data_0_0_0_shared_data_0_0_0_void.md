# tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)

- ea: `0x180031274`
- end: `0x1800312d8`
- name: `??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003894c`

## callees

- `0x180031274`
- `0x18003136c`
- `0x180031404`
- `0x180031498`
- `0x18003b6dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031284`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800312c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800312c5`

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
0x180031274  push    rbx
0x180031276  sub     rsp, 20h
0x18003127a  mov     rbx, rcx
0x18003127d  add     rcx, 0C0h; lpCriticalSection
0x180031284  call    cs:__imp_DeleteCriticalSection
0x18003128b  nop     dword ptr [rax+rax+00h]
0x180031290  mov     rcx, [rbx+0F0h]
0x180031297  test    rcx, rcx
0x18003129a  jz      short loc_1800312A1
0x18003129c  call    TestClose
0x1800312a1  lea     rcx, [rbx+78h]
0x1800312a5  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800312aa  lea     rcx, [rbx+60h]
0x1800312ae  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x1800312b3  lea     rcx, [rbx+48h]
0x1800312b7  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x1800312bc  mov     rcx, [rbx+8]; pv
0x1800312c0  test    rcx, rcx
0x1800312c3  jz      short loc_1800312D1
0x1800312c5  call    cs:__imp_CoTaskMemFree
0x1800312cc  nop     dword ptr [rax+rax+00h]
0x1800312d1  add     rsp, 20h
0x1800312d5  pop     rbx
0x1800312d6  retn
```

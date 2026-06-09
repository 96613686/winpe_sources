# tip2::details::shared_data<0,0,1>::~shared_data<0,0,1>(void)

- ea: `0x180007c64`
- end: `0x180007cc8`
- name: `??1?$shared_data@$0A@$0A@$00@details@tip2@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180007bf0`
- `0x180010ba8`

## callees

- `0x180007c64`
- `0x180007e3c`
- `0x180007ec8`
- `0x180016544`
- `0x18001a4cc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007c74`
- `KERNEL32!DeleteCriticalSection` at `0x180007c74`
- `ole32!CoTaskMemFree` at `0x180007cb5`
- `ole32!CoTaskMemFree` at `0x180007cb5`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::~shared_data<0,0,1>(__int64 a1)
{
  __int64 v2; // rcx
  void *v3; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  v2 = *(_QWORD *)(a1 + 240);
  if ( v2 )
    TestClose(v2);
  tip2::vector_nothrow<tip2::test_flag>::clear(a1 + 120);
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(a1 + 96);
  tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(a1 + 72);
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    CoTaskMemFree(v3);
}

```

## disassembly

```asm
0x180007c64  push    rbx
0x180007c66  sub     rsp, 20h
0x180007c6a  mov     rbx, rcx
0x180007c6d  add     rcx, 0C0h; lpCriticalSection
0x180007c74  call    cs:__imp_DeleteCriticalSection
0x180007c7b  nop     dword ptr [rax+rax+00h]
0x180007c80  mov     rcx, [rbx+0F0h]
0x180007c87  test    rcx, rcx
0x180007c8a  jz      short loc_180007C91
0x180007c8c  call    TestClose
0x180007c91  lea     rcx, [rbx+78h]
0x180007c95  call    ?clear@?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAAXXZ; tip2::vector_nothrow<tip2::test_flag>::clear(void)
0x180007c9a  lea     rcx, [rbx+60h]
0x180007c9e  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180007ca3  lea     rcx, [rbx+48h]
0x180007ca7  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180007cac  mov     rcx, [rbx+8]; pv
0x180007cb0  test    rcx, rcx
0x180007cb3  jz      short loc_180007CC1
0x180007cb5  call    cs:__imp_CoTaskMemFree
0x180007cbc  nop     dword ptr [rax+rax+00h]
0x180007cc1  add     rsp, 20h
0x180007cc5  pop     rbx
0x180007cc6  retn
```

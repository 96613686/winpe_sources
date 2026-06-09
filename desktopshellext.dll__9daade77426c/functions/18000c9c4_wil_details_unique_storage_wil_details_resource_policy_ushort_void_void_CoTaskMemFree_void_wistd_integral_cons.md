# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18000c9c4`
- end: `0x18000ca11`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c250`
- `0x18000c470`
- `0x18000c6d0`
- `0x180016a54`
- `0x180019ec8`
- `0x18001c498`
- `0x18001c550`
- `0x18002fef8`

## callees

- `0x1800055d8`
- `0x18000c9c4`
- `0x180015eb8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c9ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c9ee`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CoTaskMemFree(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000c9c4  mov     [rsp+arg_8], rbx
0x18000c9c9  mov     [rsp+arg_10], rsi
0x18000c9ce  push    rdi
0x18000c9cf  sub     rsp, 20h
0x18000c9d3  mov     rdi, [rcx]
0x18000c9d6  mov     rsi, rdx
0x18000c9d9  mov     rbx, rcx
0x18000c9dc  test    rdi, rdi
0x18000c9df  jz      short loc_18000C9FE
0x18000c9e1  lea     rcx, [rsp+28h+arg_0]; this
0x18000c9e6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000c9eb  mov     rcx, rdi; pv
0x18000c9ee  call    cs:__imp_CoTaskMemFree
0x18000c9f4  lea     rcx, [rsp+28h+arg_0]; this
0x18000c9f9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000c9fe  mov     [rbx], rsi
0x18000ca01  mov     rbx, [rsp+28h+arg_8]
0x18000ca06  mov     rsi, [rsp+28h+arg_10]
0x18000ca0b  add     rsp, 20h
0x18000ca0f  pop     rdi
0x18000ca10  retn
```

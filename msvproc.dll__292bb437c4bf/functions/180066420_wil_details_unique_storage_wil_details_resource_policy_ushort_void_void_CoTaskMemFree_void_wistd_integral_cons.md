# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180066420`
- end: `0x18006646d`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b3270`

## callees

- `0x1800432a0`
- `0x18005671c`
- `0x180066420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006644a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006644a`

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
0x180066420  mov     [rsp+arg_8], rbx
0x180066425  mov     [rsp+arg_10], rsi
0x18006642a  push    rdi
0x18006642b  sub     rsp, 20h
0x18006642f  mov     rdi, [rcx]
0x180066432  mov     rsi, rdx
0x180066435  mov     rbx, rcx
0x180066438  test    rdi, rdi
0x18006643b  jz      short loc_18006645A
0x18006643d  lea     rcx, [rsp+28h+arg_0]; this
0x180066442  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180066447  mov     rcx, rdi; pv
0x18006644a  call    cs:__imp_CoTaskMemFree
0x180066450  lea     rcx, [rsp+28h+arg_0]; this
0x180066455  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006645a  mov     [rbx], rsi
0x18006645d  mov     rbx, [rsp+28h+arg_8]
0x180066462  mov     rsi, [rsp+28h+arg_10]
0x180066467  add     rsp, 20h
0x18006646b  pop     rdi
0x18006646c  retn
```

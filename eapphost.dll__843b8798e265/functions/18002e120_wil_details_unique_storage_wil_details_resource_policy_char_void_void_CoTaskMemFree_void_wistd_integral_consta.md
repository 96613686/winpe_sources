# wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)

- ea: `0x18002e120`
- end: `0x18002e174`
- name: `?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002259c`
- `0x180022644`

## callees

- `0x180004cc8`
- `0x1800050ec`
- `0x18002e120`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e14a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e14a`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
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
0x18002e120  mov     [rsp+arg_8], rbx
0x18002e125  mov     [rsp+arg_10], rsi
0x18002e12a  push    rdi
0x18002e12b  sub     rsp, 20h
0x18002e12f  mov     rdi, [rcx]
0x18002e132  mov     rsi, rdx
0x18002e135  mov     rbx, rcx
0x18002e138  test    rdi, rdi
0x18002e13b  jz      short loc_18002E160
0x18002e13d  lea     rcx, [rsp+28h+arg_0]; this
0x18002e142  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002e147  mov     rcx, rdi; pv
0x18002e14a  call    cs:__imp_CoTaskMemFree
0x18002e151  nop     dword ptr [rax+rax+00h]
0x18002e156  lea     rcx, [rsp+28h+arg_0]; this
0x18002e15b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002e160  mov     [rbx], rsi
0x18002e163  mov     rbx, [rsp+28h+arg_8]
0x18002e168  mov     rsi, [rsp+28h+arg_10]
0x18002e16d  add     rsp, 20h
0x18002e171  pop     rdi
0x18002e172  retn
```

# wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)

- ea: `0x18002d0b4`
- end: `0x18002d101`
- name: `?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021990`
- `0x180021a30`

## callees

- `0x180004b50`
- `0x180004fa4`
- `0x18002d0b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d0de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d0de`

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
0x18002d0b4  mov     [rsp+arg_8], rbx
0x18002d0b9  mov     [rsp+arg_10], rsi
0x18002d0be  push    rdi
0x18002d0bf  sub     rsp, 20h
0x18002d0c3  mov     rdi, [rcx]
0x18002d0c6  mov     rsi, rdx
0x18002d0c9  mov     rbx, rcx
0x18002d0cc  test    rdi, rdi
0x18002d0cf  jz      short loc_18002D0EE
0x18002d0d1  lea     rcx, [rsp+28h+arg_0]; this
0x18002d0d6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002d0db  mov     rcx, rdi; pv
0x18002d0de  call    cs:__imp_CoTaskMemFree
0x18002d0e4  lea     rcx, [rsp+28h+arg_0]; this
0x18002d0e9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002d0ee  mov     [rbx], rsi
0x18002d0f1  mov     rbx, [rsp+28h+arg_8]
0x18002d0f6  mov     rsi, [rsp+28h+arg_10]
0x18002d0fb  add     rsp, 20h
0x18002d0ff  pop     rdi
0x18002d100  retn
```

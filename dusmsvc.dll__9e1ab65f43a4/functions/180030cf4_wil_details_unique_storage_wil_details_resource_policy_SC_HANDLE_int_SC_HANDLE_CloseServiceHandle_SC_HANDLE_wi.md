# wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)

- ea: `0x180030cf4`
- end: `0x180030d41`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18003092c`
- `0x18003840c`
- `0x18003b0fc`

## callees

- `0x18000a810`
- `0x18000aaf4`
- `0x180030cf4`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180030d1e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180030d1e`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
        SC_HANDLE *a1,
        SC_HANDLE a2)
{
  SC_HANDLE v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CloseServiceHandle(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180030cf4  mov     [rsp+arg_8], rbx
0x180030cf9  mov     [rsp+arg_10], rsi
0x180030cfe  push    rdi
0x180030cff  sub     rsp, 20h
0x180030d03  mov     rdi, [rcx]
0x180030d06  mov     rsi, rdx
0x180030d09  mov     rbx, rcx
0x180030d0c  test    rdi, rdi
0x180030d0f  jz      short loc_180030D2E
0x180030d11  lea     rcx, [rsp+28h+arg_0]; this
0x180030d16  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180030d1b  mov     rcx, rdi; hSCObject
0x180030d1e  call    cs:__imp_CloseServiceHandle
0x180030d24  lea     rcx, [rsp+28h+arg_0]; this
0x180030d29  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180030d2e  mov     [rbx], rsi
0x180030d31  mov     rbx, [rsp+28h+arg_8]
0x180030d36  mov     rsi, [rsp+28h+arg_10]
0x180030d3b  add     rsp, 20h
0x180030d3f  pop     rdi
0x180030d40  retn
```

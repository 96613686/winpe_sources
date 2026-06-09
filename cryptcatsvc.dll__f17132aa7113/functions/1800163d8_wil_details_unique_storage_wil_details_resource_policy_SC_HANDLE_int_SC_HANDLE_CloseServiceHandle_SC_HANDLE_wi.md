# wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)

- ea: `0x1800163d8`
- end: `0x180016425`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180015688`

## callees

- `0x18000dbf4`
- `0x18000df68`
- `0x1800163d8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016402`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016402`

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
0x1800163d8  mov     [rsp+arg_8], rbx
0x1800163dd  mov     [rsp+arg_10], rsi
0x1800163e2  push    rdi
0x1800163e3  sub     rsp, 20h
0x1800163e7  mov     rdi, [rcx]
0x1800163ea  mov     rsi, rdx
0x1800163ed  mov     rbx, rcx
0x1800163f0  test    rdi, rdi
0x1800163f3  jz      short loc_180016412
0x1800163f5  lea     rcx, [rsp+28h+arg_0]; this
0x1800163fa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800163ff  mov     rcx, rdi; hSCObject
0x180016402  call    cs:__imp_CloseServiceHandle
0x180016408  lea     rcx, [rsp+28h+arg_0]; this
0x18001640d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180016412  mov     [rbx], rsi
0x180016415  mov     rbx, [rsp+28h+arg_8]
0x18001641a  mov     rsi, [rsp+28h+arg_10]
0x18001641f  add     rsp, 20h
0x180016423  pop     rdi
0x180016424  retn
```

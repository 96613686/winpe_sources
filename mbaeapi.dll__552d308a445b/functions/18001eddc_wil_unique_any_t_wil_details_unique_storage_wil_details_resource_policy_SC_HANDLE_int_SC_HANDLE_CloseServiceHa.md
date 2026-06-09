# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>>(void)

- ea: `0x18001eddc`
- end: `0x18001edf3`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `BOOL __fastcall(SC_HANDLE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180059715`
- `0x180059727`

## callees

- `0x18001eddc`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ede8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ede8`

## pseudocode

```c
BOOL __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>>(
        SC_HANDLE *a1)
{
  SC_HANDLE v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return CloseServiceHandle(v1);
  return result;
}

```

## disassembly

```asm
0x18001eddc  sub     rsp, 28h
0x18001ede0  mov     rcx, [rcx]; hSCObject
0x18001ede3  test    rcx, rcx
0x18001ede6  jz      short loc_18001EDEE
0x18001ede8  call    cs:__imp_CloseServiceHandle
0x18001edee  add     rsp, 28h
0x18001edf2  retn
```

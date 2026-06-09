# DusmNla::RegisterServiceNotification(void)

- ea: `0x18003092c`
- end: `0x1800309b7`
- name: `?RegisterServiceNotification@DusmNla@@AEAAKXZ`
- size: `139`
- prototype: `unsigned int __fastcall(DusmNla *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800303f0`

## callees

- `0x18003092c`
- `0x180030cf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003095e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003095e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180030973`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180030973`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180030945`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180030945`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800309a6`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800309a6`

## pseudocode

```c
DWORD __fastcall DusmNla::RegisterServiceNotification(DusmNla *this)
{
  DusmNla *v1; // rdi
  SC_HANDLE v2; // rax
  SC_HANDLE v4; // rax
  __int64 v5; // rcx

  v1 = DusmNla::s_pInstance;
  v2 = OpenSCManagerW(0, 0, 5u);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    v1,
    v2);
  if ( *(_QWORD *)v1
    && (v4 = OpenServiceW(*(SC_HANDLE *)v1, L"netprofm", 4u),
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
          (char *)v1 + 8,
          v4),
        (v5 = *((_QWORD *)v1 + 1)) != 0) )
  {
    return SubscribeServiceChangeNotifications(v5, 2, DusmNla::NotificationCallback, v1, (char *)v1 + 16);
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x18003092c  mov     [rsp+arg_0], rbx
0x180030931  push    rdi
0x180030932  sub     rsp, 30h
0x180030936  mov     rdi, cs:?s_pInstance@DusmNla@@0PEAV1@EA; DusmNla * DusmNla::s_pInstance
0x18003093d  xor     edx, edx; lpDatabaseName
0x18003093f  xor     ecx, ecx; lpMachineName
0x180030941  lea     r8d, [rdx+5]; dwDesiredAccess
0x180030945  call    cs:__imp_OpenSCManagerW
0x18003094b  mov     rdx, rax
0x18003094e  mov     rcx, rdi
0x180030951  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x180030956  mov     rcx, [rdi]; hSCManager
0x180030959  test    rcx, rcx
0x18003095c  jnz     short loc_180030966
0x18003095e  call    cs:__imp_GetLastError
0x180030964  jmp     short loc_1800309AC
0x180030966  mov     r8d, 4; dwDesiredAccess
0x18003096c  lea     rdx, aNetprofm; "netprofm"
0x180030973  call    cs:__imp_OpenServiceW
0x180030979  mov     rdx, rax
0x18003097c  lea     rcx, [rdi+8]
0x180030980  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x180030985  mov     rcx, [rdi+8]
0x180030989  test    rcx, rcx
0x18003098c  jz      short loc_18003095E
0x18003098e  lea     rax, [rdi+10h]
0x180030992  mov     r9, rdi
0x180030995  lea     r8, ?NotificationCallback@DusmNla@@CAXKPEAX@Z; DusmNla::NotificationCallback(ulong,void *)
0x18003099c  mov     [rsp+38h+var_18], rax
0x1800309a1  mov     edx, 2
0x1800309a6  call    cs:__imp_SubscribeServiceChangeNotifications
0x1800309ac  mov     rbx, [rsp+38h+arg_0]
0x1800309b1  add     rsp, 30h
0x1800309b5  pop     rdi
0x1800309b6  retn
```

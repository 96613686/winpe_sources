# DasOpenService(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &,ulong)

- ea: `0x18002a96c`
- end: `0x18002aa2e`
- name: `?DasOpenService@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `194`
- prototype: `__int64 __fastcall(SC_HANDLE *, DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180024a64`
- `0x180042dcc`

## callees

- `0x180024bec`
- `0x1800263f4`
- `0x18002a96c`
- `0x18002aa34`
- `0x18002e0bc`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a9c2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a9c2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a98f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a98f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a9e0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a9e0`

## string_xrefs

- `0x18002a980`: `ServicesActive`
- `0x18002a9b8`: `DeviceAssociationService`
- `0x18002a9a4`: `onecore\base\devices\association\service\lib\srventry.cpp`
- `0x18002a9fd`: `onecore\base\devices\association\service\lib\srventry.cpp`

## pseudocode

```c
__int64 __fastcall DasOpenService(SC_HANDLE *a1, DWORD a2)
{
  SC_HANDLE v4; // rax
  const char *v5; // r9
  SC_HANDLE v7; // rax
  const char *v8; // r9
  SC_HANDLE v9; // rsi
  SC_HANDLE v10; // rbx
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v13; // [rsp+40h] [rbp+18h] BYREF
  SC_HANDLE v14; // [rsp+48h] [rbp+20h] BYREF

  v4 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v14 = v4;
  if ( !v4 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4D,
             (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\srventry.cpp",
             v5);
  v7 = OpenServiceW(v4, L"DeviceAssociationService", a2);
  v9 = *a1;
  v10 = v7;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
    CloseServiceHandle(v9);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
  }
  *a1 = v10;
  if ( v10 )
    LastError = 0;
  else
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4F,
                  (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\srventry.cpp",
                  v8);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
  return LastError;
}

```

## disassembly

```asm
0x18002a96c  mov     [rsp+arg_0], rbx
0x18002a971  mov     [rsp+arg_8], rsi
0x18002a976  push    rdi
0x18002a977  sub     rsp, 20h
0x18002a97b  mov     ebx, edx
0x18002a97d  mov     rdi, rcx
0x18002a980  lea     rdx, DatabaseName; "ServicesActive"
0x18002a987  xor     ecx, ecx; lpMachineName
0x18002a989  mov     r8d, 1; dwDesiredAccess
0x18002a98f  call    cs:__imp_OpenSCManagerW
0x18002a995  mov     [rsp+28h+arg_18], rax
0x18002a99a  test    rax, rax
0x18002a99d  jnz     short loc_18002A9B5
0x18002a99f  mov     rcx, [rsp+28h]; this
0x18002a9a4  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\association\\se"...
0x18002a9ab  lea     edx, [rax+4Dh]; void *
0x18002a9ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a9b3  jmp     short loc_18002AA1E
0x18002a9b5  mov     r8d, ebx; dwDesiredAccess
0x18002a9b8  lea     rdx, ServiceName; "DeviceAssociationService"
0x18002a9bf  mov     rcx, rax; hSCManager
0x18002a9c2  call    cs:__imp_OpenServiceW
0x18002a9c8  mov     rsi, [rdi]
0x18002a9cb  mov     rbx, rax
0x18002a9ce  test    rsi, rsi
0x18002a9d1  jz      short loc_18002A9F0
0x18002a9d3  lea     rcx, [rsp+28h+arg_10]; this
0x18002a9d8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002a9dd  mov     rcx, rsi; hSCObject
0x18002a9e0  call    cs:__imp_CloseServiceHandle
0x18002a9e6  lea     rcx, [rsp+28h+arg_10]; this
0x18002a9eb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002a9f0  mov     [rdi], rbx
0x18002a9f3  test    rbx, rbx
0x18002a9f6  jnz     short loc_18002AA10
0x18002a9f8  mov     rcx, [rsp+28h]; this
0x18002a9fd  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\association\\se"...
0x18002aa04  lea     edx, [rbx+4Fh]; void *
0x18002aa07  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002aa0c  mov     ebx, eax
0x18002aa0e  jmp     short loc_18002AA12
0x18002aa10  xor     ebx, ebx
0x18002aa12  lea     rcx, [rsp+28h+arg_18]
0x18002aa17  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18002aa1c  mov     eax, ebx
0x18002aa1e  mov     rbx, [rsp+28h+arg_0]
0x18002aa23  mov     rsi, [rsp+28h+arg_8]
0x18002aa28  add     rsp, 20h
0x18002aa2c  pop     rdi
0x18002aa2d  retn
```

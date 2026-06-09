# TeredoUPnP::Initialize(void)

- ea: `0x180028de4`
- end: `0x180028faa`
- name: `?Initialize@TeredoUPnP@@QEAAJXZ`
- size: `454`
- prototype: `__int64 __fastcall(TeredoUPnP *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028950`
- `0x1800289ec`

## callees

- `0x18000d7b0`
- `0x1800190e0`
- `0x180028de4`
- `0x1800406ec`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180028f1e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180028f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f4c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028e59`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028e59`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180028e06`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180028e06`

## string_xrefs

- `0x180028ec8`: `DisableServiceEventing returned 0x%x`
- `0x180028edb`: `UPnP Service eventing disabled successfully!`
- `0x180028e6b`: `CoCreateInstance returned 0x%x`

## pseudocode

```c
__int64 __fastcall TeredoUPnP::Initialize(TeredoUPnP *this)
{
  unsigned int Instance; // ebx
  _QWORD *v3; // r14
  __int64 (__fastcall ***v4)(_QWORD, GUID *, HANDLE *); // rcx
  int v5; // eax
  int v6; // eax
  signed int LastError; // eax
  HANDLE hObject; // [rsp+40h] [rbp+8h] BYREF

  Instance = 0;
  if ( (*((_BYTE *)this + 168) & 1) == 0 )
  {
    Instance = CoInitializeEx(0, 0);
    if ( (Instance & 0x80000000) != 0 )
    {
      EventWriteError0(0x100000, L"CoInitializeEx returned 0x%x", Instance);
      return Instance;
    }
    *((_DWORD *)this + 42) |= 1u;
  }
  v3 = (_QWORD *)((char *)this + 16);
  if ( !*((_QWORD *)this + 2) )
  {
    *v3 = 0;
    Instance = CoCreateInstance(&CLSID_UPnPDeviceFinder, 0, 1u, &IID_IUPnPDeviceFinder, (LPVOID *)this + 2);
    if ( (Instance & 0x80000000) != 0 )
    {
      EventWriteError0(0x100000, L"CoCreateInstance returned 0x%x", Instance);
      return Instance;
    }
    v4 = (__int64 (__fastcall ***)(_QWORD, GUID *, HANDLE *))*v3;
    hObject = 0;
    v5 = (**v4)(v4, &GUID_29b4fdfe_201b_4581_baa5_88a2cc12668e, &hObject);
    if ( v5 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)hObject + 24LL))(hObject);
      Instance = v6;
      if ( v6 >= 0 )
      {
        EventWrite0(0x100000, L"UPnP Service eventing disabled successfully!");
LABEL_14:
        if ( hObject )
          (*(void (__fastcall **)(HANDLE))(*(_QWORD *)hObject + 16LL))(hObject);
        goto LABEL_16;
      }
      EventWriteError0(0x100000, L"DisableServiceEventing returned 0x%x", (unsigned int)v6);
    }
    else
    {
      EventWriteError0(0x100000, L"Failed to QueryInterface to IUPnPEventingControl 0x%x", (unsigned int)v5);
    }
    Instance = 0;
    goto LABEL_14;
  }
LABEL_16:
  if ( ((*((_QWORD *)this + 6) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    hObject = CreateEventExW(0, 0, 1u, 0x1F0003u);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      (char *)this + 48,
      &hObject);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( ((*((_QWORD *)this + 6) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
      EventWriteError0(0x100000, L"CreaveEventEx returned 0x%x", Instance);
    }
  }
  return Instance;
}

```

## disassembly

```asm
0x180028de4  mov     [rsp+arg_8], rbx
0x180028de9  mov     [rsp+arg_10], rsi
0x180028dee  push    r14
0x180028df0  sub     rsp, 30h
0x180028df4  xor     ebx, ebx
0x180028df6  mov     rsi, rcx
0x180028df9  test    byte ptr [rcx+0A8h], 1
0x180028e00  jnz     short loc_180028E2B
0x180028e02  xor     edx, edx; dwCoInit
0x180028e04  xor     ecx, ecx; pvReserved
0x180028e06  call    cs:__imp_CoInitializeEx
0x180028e0d  nop     dword ptr [rax+rax+00h]
0x180028e12  mov     ebx, eax
0x180028e14  test    eax, eax
0x180028e16  jns     short loc_180028E24
0x180028e18  lea     rdx, aCoinitializeex_1; "CoInitializeEx returned 0x%x"
0x180028e1f  jmp     loc_180028F89
0x180028e24  or      dword ptr [rsi+0A8h], 1
0x180028e2b  lea     r14, [rsi+10h]
0x180028e2f  cmp     qword ptr [r14], 0
0x180028e33  jnz     loc_180028EFD
0x180028e39  xor     edx, edx; pUnkOuter
0x180028e3b  mov     qword ptr [r14], 0
0x180028e42  lea     r9, IID_IUPnPDeviceFinder; riid
0x180028e49  mov     [rsp+38h+ppv], r14; ppv
0x180028e4e  lea     rcx, CLSID_UPnPDeviceFinder; rclsid
0x180028e55  lea     r8d, [rdx+1]; dwClsContext
0x180028e59  call    cs:__imp_CoCreateInstance
0x180028e60  nop     dword ptr [rax+rax+00h]
0x180028e65  mov     ebx, eax
0x180028e67  test    eax, eax
0x180028e69  jns     short loc_180028E77
0x180028e6b  lea     rdx, aCocreateinstan_0; "CoCreateInstance returned 0x%x"
0x180028e72  jmp     loc_180028F89
0x180028e77  mov     rcx, [r14]
0x180028e7a  lea     r8, [rsp+38h+hObject]
0x180028e7f  mov     [rsp+38h+hObject], 0
0x180028e88  lea     rdx, _GUID_29b4fdfe_201b_4581_baa5_88a2cc12668e
0x180028e8f  mov     rax, [rcx]
0x180028e92  mov     rax, [rax]
0x180028e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e9a  test    eax, eax
0x180028e9c  jns     short loc_180028EAC
0x180028e9e  lea     rdx, aFailedToQueryi; "Failed to QueryInterface to IUPnPEventi"...
0x180028ea5  mov     ecx, 100000h
0x180028eaa  jmp     short loc_180028ECF
0x180028eac  mov     rcx, [rsp+38h+hObject]
0x180028eb1  mov     rax, [rcx]
0x180028eb4  mov     rax, [rax+18h]
0x180028eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ebd  mov     ebx, eax
0x180028ebf  mov     ecx, 100000h
0x180028ec4  test    eax, eax
0x180028ec6  jns     short loc_180028EDB
0x180028ec8  lea     rdx, aDisableservice; "DisableServiceEventing returned 0x%x"
0x180028ecf  mov     r8d, eax
0x180028ed2  call    EventWriteError0
0x180028ed7  xor     ebx, ebx
0x180028ed9  jmp     short loc_180028EE7
0x180028edb  lea     rdx, aUpnpServiceEve; "UPnP Service eventing disabled successf"...
0x180028ee2  call    EventWrite0
0x180028ee7  mov     rcx, [rsp+38h+hObject]
0x180028eec  test    rcx, rcx
0x180028eef  jz      short loc_180028EFD
0x180028ef1  mov     rax, [rcx]
0x180028ef4  mov     rax, [rax+10h]
0x180028ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028efd  mov     rax, [rsi+30h]
0x180028f01  inc     rax
0x180028f04  test    rax, 0FFFFFFFFFFFFFFFEh
0x180028f0a  jnz     loc_180028F96
0x180028f10  xor     edx, edx; lpName
0x180028f12  xor     ecx, ecx; lpEventAttributes
0x180028f14  mov     r9d, 1F0003h; dwDesiredAccess
0x180028f1a  lea     r8d, [rdx+1]; dwFlags
0x180028f1e  call    cs:__imp_CreateEventExW
0x180028f25  nop     dword ptr [rax+rax+00h]
0x180028f2a  lea     rdx, [rsp+38h+hObject]
0x180028f2f  mov     [rsp+38h+hObject], rax
0x180028f34  lea     rcx, [rsi+30h]
0x180028f38  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180028f3d  mov     rcx, [rsp+38h+hObject]; hObject
0x180028f42  lea     rax, [rcx-1]
0x180028f46  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028f4a  ja      short loc_180028F58
0x180028f4c  call    cs:__imp_CloseHandle
0x180028f53  nop     dword ptr [rax+rax+00h]
0x180028f58  mov     rax, [rsi+30h]
0x180028f5c  inc     rax
0x180028f5f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180028f65  jnz     short loc_180028F96
0x180028f67  call    cs:__imp_GetLastError
0x180028f6e  nop     dword ptr [rax+rax+00h]
0x180028f73  mov     ebx, eax
0x180028f75  test    eax, eax
0x180028f77  jle     short loc_180028F82
0x180028f79  movzx   ebx, ax
0x180028f7c  or      ebx, 80070000h
0x180028f82  lea     rdx, aCreaveeventexR; "CreaveEventEx returned 0x%x"
0x180028f89  mov     r8d, ebx
0x180028f8c  mov     ecx, 100000h
0x180028f91  call    EventWriteError0
0x180028f96  mov     rsi, [rsp+38h+arg_10]
0x180028f9b  mov     eax, ebx
0x180028f9d  mov     rbx, [rsp+38h+arg_8]
0x180028fa2  add     rsp, 30h
0x180028fa6  pop     r14
0x180028fa8  retn
```

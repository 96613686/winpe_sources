# TeredoUPnP::Initialize(void)

- ea: `0x180028df4`
- end: `0x180028fba`
- name: `?Initialize@TeredoUPnP@@QEAAJXZ`
- size: `454`
- prototype: `__int64 __fastcall(TeredoUPnP *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028960`
- `0x1800289fc`

## callees

- `0x18000d7c0`
- `0x1800190f0`
- `0x180028df4`
- `0x1800406ac`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180028f2e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180028f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f5c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028e69`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028e69`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180028e16`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180028e16`

## string_xrefs

- `0x180028ed8`: `DisableServiceEventing returned 0x%x`
- `0x180028eeb`: `UPnP Service eventing disabled successfully!`
- `0x180028e7b`: `CoCreateInstance returned 0x%x`

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
0x180028df4  mov     [rsp+arg_8], rbx
0x180028df9  mov     [rsp+arg_10], rsi
0x180028dfe  push    r14
0x180028e00  sub     rsp, 30h
0x180028e04  xor     ebx, ebx
0x180028e06  mov     rsi, rcx
0x180028e09  test    byte ptr [rcx+0A8h], 1
0x180028e10  jnz     short loc_180028E3B
0x180028e12  xor     edx, edx; dwCoInit
0x180028e14  xor     ecx, ecx; pvReserved
0x180028e16  call    cs:__imp_CoInitializeEx
0x180028e1d  nop     dword ptr [rax+rax+00h]
0x180028e22  mov     ebx, eax
0x180028e24  test    eax, eax
0x180028e26  jns     short loc_180028E34
0x180028e28  lea     rdx, aCoinitializeex_1; "CoInitializeEx returned 0x%x"
0x180028e2f  jmp     loc_180028F99
0x180028e34  or      dword ptr [rsi+0A8h], 1
0x180028e3b  lea     r14, [rsi+10h]
0x180028e3f  cmp     qword ptr [r14], 0
0x180028e43  jnz     loc_180028F0D
0x180028e49  xor     edx, edx; pUnkOuter
0x180028e4b  mov     qword ptr [r14], 0
0x180028e52  lea     r9, IID_IUPnPDeviceFinder; riid
0x180028e59  mov     [rsp+38h+ppv], r14; ppv
0x180028e5e  lea     rcx, CLSID_UPnPDeviceFinder; rclsid
0x180028e65  lea     r8d, [rdx+1]; dwClsContext
0x180028e69  call    cs:__imp_CoCreateInstance
0x180028e70  nop     dword ptr [rax+rax+00h]
0x180028e75  mov     ebx, eax
0x180028e77  test    eax, eax
0x180028e79  jns     short loc_180028E87
0x180028e7b  lea     rdx, aCocreateinstan_0; "CoCreateInstance returned 0x%x"
0x180028e82  jmp     loc_180028F99
0x180028e87  mov     rcx, [r14]
0x180028e8a  lea     r8, [rsp+38h+hObject]
0x180028e8f  mov     [rsp+38h+hObject], 0
0x180028e98  lea     rdx, _GUID_29b4fdfe_201b_4581_baa5_88a2cc12668e
0x180028e9f  mov     rax, [rcx]
0x180028ea2  mov     rax, [rax]
0x180028ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eaa  test    eax, eax
0x180028eac  jns     short loc_180028EBC
0x180028eae  lea     rdx, aFailedToQueryi; "Failed to QueryInterface to IUPnPEventi"...
0x180028eb5  mov     ecx, 100000h
0x180028eba  jmp     short loc_180028EDF
0x180028ebc  mov     rcx, [rsp+38h+hObject]
0x180028ec1  mov     rax, [rcx]
0x180028ec4  mov     rax, [rax+18h]
0x180028ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ecd  mov     ebx, eax
0x180028ecf  mov     ecx, 100000h
0x180028ed4  test    eax, eax
0x180028ed6  jns     short loc_180028EEB
0x180028ed8  lea     rdx, aDisableservice; "DisableServiceEventing returned 0x%x"
0x180028edf  mov     r8d, eax
0x180028ee2  call    EventWriteError0
0x180028ee7  xor     ebx, ebx
0x180028ee9  jmp     short loc_180028EF7
0x180028eeb  lea     rdx, aUpnpServiceEve; "UPnP Service eventing disabled successf"...
0x180028ef2  call    EventWrite0
0x180028ef7  mov     rcx, [rsp+38h+hObject]
0x180028efc  test    rcx, rcx
0x180028eff  jz      short loc_180028F0D
0x180028f01  mov     rax, [rcx]
0x180028f04  mov     rax, [rax+10h]
0x180028f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f0d  mov     rax, [rsi+30h]
0x180028f11  inc     rax
0x180028f14  test    rax, 0FFFFFFFFFFFFFFFEh
0x180028f1a  jnz     loc_180028FA6
0x180028f20  xor     edx, edx; lpName
0x180028f22  xor     ecx, ecx; lpEventAttributes
0x180028f24  mov     r9d, 1F0003h; dwDesiredAccess
0x180028f2a  lea     r8d, [rdx+1]; dwFlags
0x180028f2e  call    cs:__imp_CreateEventExW
0x180028f35  nop     dword ptr [rax+rax+00h]
0x180028f3a  lea     rdx, [rsp+38h+hObject]
0x180028f3f  mov     [rsp+38h+hObject], rax
0x180028f44  lea     rcx, [rsi+30h]
0x180028f48  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180028f4d  mov     rcx, [rsp+38h+hObject]; hObject
0x180028f52  lea     rax, [rcx-1]
0x180028f56  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028f5a  ja      short loc_180028F68
0x180028f5c  call    cs:__imp_CloseHandle
0x180028f63  nop     dword ptr [rax+rax+00h]
0x180028f68  mov     rax, [rsi+30h]
0x180028f6c  inc     rax
0x180028f6f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180028f75  jnz     short loc_180028FA6
0x180028f77  call    cs:__imp_GetLastError
0x180028f7e  nop     dword ptr [rax+rax+00h]
0x180028f83  mov     ebx, eax
0x180028f85  test    eax, eax
0x180028f87  jle     short loc_180028F92
0x180028f89  movzx   ebx, ax
0x180028f8c  or      ebx, 80070000h
0x180028f92  lea     rdx, aCreaveeventexR; "CreaveEventEx returned 0x%x"
0x180028f99  mov     r8d, ebx
0x180028f9c  mov     ecx, 100000h
0x180028fa1  call    EventWriteError0
0x180028fa6  mov     rsi, [rsp+38h+arg_10]
0x180028fab  mov     eax, ebx
0x180028fad  mov     rbx, [rsp+38h+arg_8]
0x180028fb2  add     rsp, 30h
0x180028fb6  pop     r14
0x180028fb8  retn
```

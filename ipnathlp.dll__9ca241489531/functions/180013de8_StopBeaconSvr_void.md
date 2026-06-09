# StopBeaconSvr(void)

- ea: `0x180013de8`
- end: `0x180013eef`
- name: `?StopBeaconSvr@@YAJXZ`
- size: `263`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013ef8`
- `0x180047690`

## callees

- `0x180013de8`
- `0x180013f34`
- `0x180037c3c`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013e0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013e0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ee1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ee1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ec9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ec9`
- `OLEAUT32!__imp_SysFreeString` at `0x180013ea1`
- `OLEAUT32!__imp_SysFreeString` at `0x180013ea1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013eb2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013eb2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180013e25`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180013e25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013e53`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013e53`

## pseudocode

```c
__int64 StopBeaconSvr(void)
{
  __int64 result; // rax
  HRESULT Instance; // ebx
  struct IUnknown *ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = 0;
  result = IsHomenetModuleOSType();
  if ( (_DWORD)result )
  {
    Instance = 0;
    EnterCriticalSection(&g_RegistrationProtection);
    if ( bstrString )
    {
      Instance = CoInitializeEx(0, 4u);
      if ( Instance >= 0 )
      {
        Instance = CoCreateInstance(&CLSID_UPnPRegistrar, 0, 0x15u, &IID_IUPnPRegistrar, (LPVOID *)&ppv);
        if ( Instance >= 0 )
        {
          SetProxyBlanket(ppv);
          Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, __int64))ppv->lpVtbl[2].AddRef)(
                       ppv,
                       bstrString,
                       1);
          ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
        }
        SysFreeString(bstrString);
        bstrString = 0;
        CoUninitialize();
      }
    }
    dword_1800A8A34 = 0;
    CloseHandle(CSwitchSecurityContext::m_hImpersonationToken);
    CSwitchSecurityContext::m_hImpersonationToken = 0;
    LeaveCriticalSection(&g_RegistrationProtection);
    return (unsigned int)Instance;
  }
  return result;
}

```

## disassembly

```asm
0x180013de8  push    rbx
0x180013dea  sub     rsp, 30h
0x180013dee  mov     [rsp+38h+arg_0], 0
0x180013df7  call    ?IsHomenetModuleOSType@@YAHW4_ENUM_HNET_MODULE@@@Z; IsHomenetModuleOSType(_ENUM_HNET_MODULE)
0x180013dfc  test    eax, eax
0x180013dfe  jz      loc_180013EE9
0x180013e04  lea     rcx, ?g_RegistrationProtection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180013e0b  xor     ebx, ebx
0x180013e0d  call    cs:__imp_EnterCriticalSection
0x180013e13  cmp     cs:bstrString, rbx
0x180013e1a  jz      loc_180013EB8
0x180013e20  lea     edx, [rbx+4]; dwCoInit
0x180013e23  xor     ecx, ecx; pvReserved
0x180013e25  call    cs:__imp_CoInitializeEx
0x180013e2b  mov     ebx, eax
0x180013e2d  test    eax, eax
0x180013e2f  js      loc_180013EB8
0x180013e35  xor     edx, edx; pUnkOuter
0x180013e37  lea     rax, [rsp+38h+arg_0]
0x180013e3c  lea     r9, IID_IUPnPRegistrar; riid
0x180013e43  mov     [rsp+38h+ppv], rax; ppv
0x180013e48  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x180013e4f  lea     r8d, [rdx+15h]; dwClsContext
0x180013e53  call    cs:__imp_CoCreateInstance
0x180013e59  mov     ebx, eax
0x180013e5b  test    eax, eax
0x180013e5d  js      short loc_180013E9A
0x180013e5f  mov     rcx, [rsp+38h+arg_0]; struct IUnknown *
0x180013e64  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x180013e69  mov     rcx, [rsp+38h+arg_0]
0x180013e6e  mov     r8d, 1
0x180013e74  mov     rdx, cs:bstrString
0x180013e7b  mov     rax, [rcx]
0x180013e7e  mov     rax, [rax+38h]
0x180013e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e87  mov     rcx, [rsp+38h+arg_0]
0x180013e8c  mov     ebx, eax
0x180013e8e  mov     rax, [rcx]
0x180013e91  mov     rax, [rax+10h]
0x180013e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e9a  mov     rcx, cs:bstrString; bstrString
0x180013ea1  call    cs:__imp_SysFreeString
0x180013ea7  mov     cs:bstrString, 0
0x180013eb2  call    cs:__imp_CoUninitialize
0x180013eb8  mov     rcx, cs:?m_hImpersonationToken@CSwitchSecurityContext@@0PEAXEA; hObject
0x180013ebf  mov     cs:dword_1800A8A34, 0
0x180013ec9  call    cs:__imp_CloseHandle
0x180013ecf  lea     rcx, ?g_RegistrationProtection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180013ed6  mov     cs:?m_hImpersonationToken@CSwitchSecurityContext@@0PEAXEA, 0; void * CSwitchSecurityContext::m_hImpersonationToken
0x180013ee1  call    cs:__imp_LeaveCriticalSection
0x180013ee7  mov     eax, ebx
0x180013ee9  add     rsp, 30h
0x180013eed  pop     rbx
0x180013eee  retn
```

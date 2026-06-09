# StopBeaconSvr(void)

- ea: `0x180014e34`
- end: `0x180014f66`
- name: `?StopBeaconSvr@@YAJXZ`
- size: `306`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014f6c`
- `0x18004b1b0`

## callees

- `0x180014e34`
- `0x180014fa8`
- `0x18003a9c0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014e59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014e59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014f51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014f51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f33`
- `OLEAUT32!__imp_SysFreeString` at `0x180014eff`
- `OLEAUT32!__imp_SysFreeString` at `0x180014eff`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014f16`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014f16`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014e77`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014e77`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014eab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014eab`

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
    dword_1800AFAF4 = 0;
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
0x180014e34  push    rbx
0x180014e36  sub     rsp, 30h
0x180014e3a  mov     [rsp+38h+arg_0], 0
0x180014e43  call    ?IsHomenetModuleOSType@@YAHW4_ENUM_HNET_MODULE@@@Z; IsHomenetModuleOSType(_ENUM_HNET_MODULE)
0x180014e48  test    eax, eax
0x180014e4a  jz      loc_180014F5F
0x180014e50  lea     rcx, ?g_RegistrationProtection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014e57  xor     ebx, ebx
0x180014e59  call    cs:__imp_EnterCriticalSection
0x180014e60  nop     dword ptr [rax+rax+00h]
0x180014e65  cmp     cs:bstrString, rbx
0x180014e6c  jz      loc_180014F22
0x180014e72  lea     edx, [rbx+4]; dwCoInit
0x180014e75  xor     ecx, ecx; pvReserved
0x180014e77  call    cs:__imp_CoInitializeEx
0x180014e7e  nop     dword ptr [rax+rax+00h]
0x180014e83  mov     ebx, eax
0x180014e85  test    eax, eax
0x180014e87  js      loc_180014F22
0x180014e8d  xor     edx, edx; pUnkOuter
0x180014e8f  lea     rax, [rsp+38h+arg_0]
0x180014e94  lea     r9, IID_IUPnPRegistrar; riid
0x180014e9b  mov     [rsp+38h+ppv], rax; ppv
0x180014ea0  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x180014ea7  lea     r8d, [rdx+15h]; dwClsContext
0x180014eab  call    cs:__imp_CoCreateInstance
0x180014eb2  nop     dword ptr [rax+rax+00h]
0x180014eb7  mov     ebx, eax
0x180014eb9  test    eax, eax
0x180014ebb  js      short loc_180014EF8
0x180014ebd  mov     rcx, [rsp+38h+arg_0]; struct IUnknown *
0x180014ec2  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x180014ec7  mov     rcx, [rsp+38h+arg_0]
0x180014ecc  mov     r8d, 1
0x180014ed2  mov     rdx, cs:bstrString
0x180014ed9  mov     rax, [rcx]
0x180014edc  mov     rax, [rax+38h]
0x180014ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ee5  mov     rcx, [rsp+38h+arg_0]
0x180014eea  mov     ebx, eax
0x180014eec  mov     rax, [rcx]
0x180014eef  mov     rax, [rax+10h]
0x180014ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ef8  mov     rcx, cs:bstrString; bstrString
0x180014eff  call    cs:__imp_SysFreeString
0x180014f06  nop     dword ptr [rax+rax+00h]
0x180014f0b  mov     cs:bstrString, 0
0x180014f16  call    cs:__imp_CoUninitialize
0x180014f1d  nop     dword ptr [rax+rax+00h]
0x180014f22  mov     rcx, cs:?m_hImpersonationToken@CSwitchSecurityContext@@0PEAXEA; hObject
0x180014f29  mov     cs:dword_1800AFAF4, 0
0x180014f33  call    cs:__imp_CloseHandle
0x180014f3a  nop     dword ptr [rax+rax+00h]
0x180014f3f  lea     rcx, ?g_RegistrationProtection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014f46  mov     cs:?m_hImpersonationToken@CSwitchSecurityContext@@0PEAXEA, 0; void * CSwitchSecurityContext::m_hImpersonationToken
0x180014f51  call    cs:__imp_LeaveCriticalSection
0x180014f58  nop     dword ptr [rax+rax+00h]
0x180014f5d  mov     eax, ebx
0x180014f5f  add     rsp, 30h
0x180014f63  pop     rbx
0x180014f64  retn
```

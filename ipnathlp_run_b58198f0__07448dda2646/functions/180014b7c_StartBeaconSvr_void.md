# StartBeaconSvr(void)

- ea: `0x180014b7c`
- end: `0x180014e2d`
- name: `?StartBeaconSvr@@YAJXZ`
- size: `689`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014f6c`
- `0x180075f14`

## callees

- `0x180014b7c`
- `0x180014fa8`
- `0x18003a9c0`
- `0x18003caec`
- `0x180042fc4`
- `0x18004e0b8`
- `0x18008f270`
- `0x18008f3a8`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ba5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ba5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014d42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014d42`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014d90`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014d90`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180014d24`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180014d24`
- `OLEAUT32!__imp_SysAllocString` at `0x180014ca9`
- `OLEAUT32!__imp_SysAllocString` at `0x180014ca9`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180014db5`
- `OLEAUT32!__imp_SysFreeString` at `0x180014dcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180014db5`
- `OLEAUT32!__imp_SysFreeString` at `0x180014dcc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014df7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014df7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014bcd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014bcd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014c17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014c17`

## string_xrefs

- `0x180014d38`: `DllRegisterServer`
- `0x180014d1d`: `UPNPHOST.DLL`

## pseudocode

```c
__int64 StartBeaconSvr(void)
{
  __int64 result; // rax
  HRESULT Instance; // ebx
  BSTR v2; // rdi
  __int64 v3; // rax
  OLECHAR *v4; // rsi
  OLECHAR *v5; // r12
  HMODULE LibraryW; // rax
  HMODULE v7; // r14
  void (*ProcAddress)(void); // rax
  struct IUnknown *ppv; // [rsp+70h] [rbp+30h] BYREF
  BSTR v10; // [rsp+78h] [rbp+38h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+40h] BYREF

  result = IsHomenetModuleOSType();
  if ( (_DWORD)result )
  {
    Instance = 0;
    EnterCriticalSection(&g_RegistrationProtection);
    dword_1800AFAF4 = 1;
    if ( !::bstrString )
    {
      Instance = CoInitializeEx(0, 4u);
      if ( Instance >= 0 )
      {
        Instance = BeaconEnabled();
        if ( Instance >= 0 )
        {
          ppv = 0;
          Instance = CoCreateInstance(&CLSID_UPnPRegistrar, 0, 0x15u, &IID_IUPnPRegistrar, (LPVOID *)&ppv);
          if ( Instance >= 0 )
          {
            SetProxyBlanket(ppv);
            CSwitchSecurityContext::ObtainImpersonationToken();
            v10 = 0;
            Instance = ATL::CComObject<CInternetGatewayDevice>::CreateInstance(&v10);
            if ( Instance >= 0 )
            {
              v2 = v10;
              if ( v10 )
              {
                (*(void (__fastcall **)(BSTR))(*(_QWORD *)v10 + 8LL))(v10);
                v3 = *((_QWORD *)v2 + 9);
                v10 = 0;
                Instance = GetDescriptionDocument((unsigned int)(*(_DWORD *)(v3 + 104) != 3) + 1, &v10);
                if ( Instance >= 0 )
                {
                  v4 = SysAllocString(L"Init");
                  if ( v4 )
                  {
                    bstrString = 0;
                    if ( (int)GetXMLPath(&bstrString) < 0 )
                    {
                      Instance = -2147024882;
                    }
                    else
                    {
                      v5 = bstrString;
                      Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, BSTR, OLECHAR *, BSTR, int, BSTR *))ppv->lpVtbl[1].AddRef)(
                                   ppv,
                                   v10,
                                   v2,
                                   v4,
                                   bstrString,
                                   1800,
                                   &::bstrString);
                      if ( Instance == -2147024891 )
                      {
                        LibraryW = LoadLibraryW(L"UPNPHOST.DLL");
                        v7 = LibraryW;
                        if ( LibraryW )
                        {
                          ProcAddress = (void (*)(void))GetProcAddress(LibraryW, "DllRegisterServer");
                          if ( ProcAddress )
                          {
                            ProcAddress();
                            Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, BSTR, OLECHAR *, OLECHAR *, int, BSTR *))ppv->lpVtbl[1].AddRef)(
                                         ppv,
                                         v10,
                                         v2,
                                         v4,
                                         v5,
                                         1800,
                                         &::bstrString);
                          }
                          FreeLibrary(v7);
                        }
                      }
                      SysFreeString(v5);
                    }
                    SysFreeString(v4);
                  }
                  else
                  {
                    Instance = -2147024882;
                  }
                  SysFreeString(v10);
                }
                (*(void (__fastcall **)(BSTR))(*(_QWORD *)v2 + 16LL))(v2);
              }
              else
              {
                Instance = -2147467259;
              }
            }
            ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
          }
        }
        CoUninitialize();
      }
    }
    LeaveCriticalSection(&g_RegistrationProtection);
    return (unsigned int)Instance;
  }
  return result;
}

```

## disassembly

```asm
0x180014b7c  mov     [rsp-28h+arg_18], rbx
0x180014b81  push    rbp
0x180014b82  push    rsi
0x180014b83  push    rdi
0x180014b84  push    r12
0x180014b86  push    r14
0x180014b88  mov     rbp, rsp
0x180014b8b  sub     rsp, 40h
0x180014b8f  call    ?IsHomenetModuleOSType@@YAHW4_ENUM_HNET_MODULE@@@Z; IsHomenetModuleOSType(_ENUM_HNET_MODULE)
0x180014b94  test    eax, eax
0x180014b96  jz      loc_180014E18
0x180014b9c  lea     rcx, ?g_RegistrationProtection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014ba3  xor     ebx, ebx
0x180014ba5  call    cs:__imp_EnterCriticalSection
0x180014bac  nop     dword ptr [rax+rax+00h]
0x180014bb1  cmp     cs:bstrString, rbx
0x180014bb8  mov     cs:dword_1800AFAF4, 1
0x180014bc2  jnz     loc_180014E03
0x180014bc8  lea     edx, [rbx+4]; dwCoInit
0x180014bcb  xor     ecx, ecx; pvReserved
0x180014bcd  call    cs:__imp_CoInitializeEx
0x180014bd4  nop     dword ptr [rax+rax+00h]
0x180014bd9  mov     ebx, eax
0x180014bdb  test    eax, eax
0x180014bdd  js      loc_180014E03
0x180014be3  call    ?BeaconEnabled@@YAJXZ; BeaconEnabled(void)
0x180014be8  mov     ebx, eax
0x180014bea  test    eax, eax
0x180014bec  js      loc_180014DF7
0x180014bf2  xor     edx, edx; pUnkOuter
0x180014bf4  mov     [rbp+arg_0], 0
0x180014bfc  lea     rax, [rbp+arg_0]
0x180014c00  lea     r9, IID_IUPnPRegistrar; riid
0x180014c07  mov     [rsp+40h+ppv], rax; ppv
0x180014c0c  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x180014c13  lea     r8d, [rdx+15h]; dwClsContext
0x180014c17  call    cs:__imp_CoCreateInstance
0x180014c1e  nop     dword ptr [rax+rax+00h]
0x180014c23  mov     ebx, eax
0x180014c25  test    eax, eax
0x180014c27  js      loc_180014DF7
0x180014c2d  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180014c31  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x180014c36  call    ?ObtainImpersonationToken@CSwitchSecurityContext@@SAJXZ; CSwitchSecurityContext::ObtainImpersonationToken(void)
0x180014c3b  lea     rcx, [rbp+arg_8]
0x180014c3f  mov     [rbp+arg_8], 0
0x180014c47  call    ?CreateInstance@?$CComObject@VCInternetGatewayDevice@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInternetGatewayDevice>::CreateInstance(ATL::CComObject<CInternetGatewayDevice> * *)
0x180014c4c  mov     ebx, eax
0x180014c4e  test    eax, eax
0x180014c50  js      loc_180014DE7
0x180014c56  mov     rdi, [rbp+arg_8]
0x180014c5a  test    rdi, rdi
0x180014c5d  jnz     short loc_180014C69
0x180014c5f  mov     ebx, 80004005h
0x180014c64  jmp     loc_180014DE7
0x180014c69  mov     rax, [rdi]
0x180014c6c  mov     rcx, rdi
0x180014c6f  mov     rax, [rax+8]
0x180014c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c78  mov     rax, [rdi+48h]
0x180014c7c  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180014c80  xor     ecx, ecx
0x180014c82  mov     [rbp+arg_8], 0
0x180014c8a  cmp     dword ptr [rax+68h], 3
0x180014c8e  setnz   cl
0x180014c91  inc     ecx; int
0x180014c93  call    ?GetDescriptionDocument@@YAJHPEAPEAG@Z; GetDescriptionDocument(int,ushort * *)
0x180014c98  mov     ebx, eax
0x180014c9a  test    eax, eax
0x180014c9c  js      loc_180014DD8
0x180014ca2  lea     rcx, psz; "Init"
0x180014ca9  call    cs:__imp_SysAllocString
0x180014cb0  nop     dword ptr [rax+rax+00h]
0x180014cb5  mov     rsi, rax
0x180014cb8  test    rax, rax
0x180014cbb  jz      loc_180014DC3
0x180014cc1  lea     rcx, [rbp+bstrString]; unsigned __int16 **
0x180014cc5  mov     [rbp+bstrString], 0
0x180014ccd  call    ?GetXMLPath@@YAJPEAPEAG@Z; GetXMLPath(ushort * *)
0x180014cd2  test    eax, eax
0x180014cd4  js      loc_180014DAD
0x180014cda  mov     r10, [rbp+arg_0]
0x180014cde  mov     r9, rsi
0x180014ce1  mov     r12, [rbp+bstrString]
0x180014ce5  mov     r8, rdi
0x180014ce8  mov     rdx, [rbp+arg_8]
0x180014cec  mov     rcx, [r10]
0x180014cef  mov     rax, [rcx+20h]
0x180014cf3  lea     rcx, bstrString
0x180014cfa  mov     [rsp+40h+var_10], rcx
0x180014cff  mov     rcx, r10
0x180014d02  mov     [rsp+40h+var_18], 708h
0x180014d0a  mov     [rsp+40h+ppv], r12
0x180014d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d14  mov     ebx, eax
0x180014d16  cmp     eax, 80070005h
0x180014d1b  jnz     short loc_180014D9C
0x180014d1d  lea     rcx, LibFileName; "UPNPHOST.DLL"
0x180014d24  call    cs:__imp_LoadLibraryW
0x180014d2b  nop     dword ptr [rax+rax+00h]
0x180014d30  mov     r14, rax
0x180014d33  test    rax, rax
0x180014d36  jz      short loc_180014D9C
0x180014d38  lea     rdx, ProcName; "DllRegisterServer"
0x180014d3f  mov     rcx, rax; hModule
0x180014d42  call    cs:__imp_GetProcAddress
0x180014d49  nop     dword ptr [rax+rax+00h]
0x180014d4e  test    rax, rax
0x180014d51  jz      short loc_180014D8D
0x180014d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d58  mov     rcx, [rbp+arg_0]
0x180014d5c  lea     rdx, bstrString
0x180014d63  mov     [rsp+40h+var_10], rdx
0x180014d68  mov     r9, rsi
0x180014d6b  mov     rdx, [rbp+arg_8]
0x180014d6f  mov     r8, rdi
0x180014d72  mov     [rsp+40h+var_18], 708h
0x180014d7a  mov     rax, [rcx]
0x180014d7d  mov     [rsp+40h+ppv], r12
0x180014d82  mov     rax, [rax+20h]
0x180014d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d8b  mov     ebx, eax
0x180014d8d  mov     rcx, r14; hLibModule
0x180014d90  call    cs:__imp_FreeLibrary
0x180014d97  nop     dword ptr [rax+rax+00h]
0x180014d9c  mov     rcx, r12; bstrString
0x180014d9f  call    cs:__imp_SysFreeString
0x180014da6  nop     dword ptr [rax+rax+00h]
0x180014dab  jmp     short loc_180014DB2
0x180014dad  mov     ebx, 8007000Eh
0x180014db2  mov     rcx, rsi; bstrString
0x180014db5  call    cs:__imp_SysFreeString
0x180014dbc  nop     dword ptr [rax+rax+00h]
0x180014dc1  jmp     short loc_180014DC8
0x180014dc3  mov     ebx, 8007000Eh
0x180014dc8  mov     rcx, [rbp+arg_8]; bstrString
0x180014dcc  call    cs:__imp_SysFreeString
0x180014dd3  nop     dword ptr [rax+rax+00h]
0x180014dd8  mov     rax, [rdi]
0x180014ddb  mov     rcx, rdi
0x180014dde  mov     rax, [rax+10h]
0x180014de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014de7  mov     rcx, [rbp+arg_0]
0x180014deb  mov     rax, [rcx]
0x180014dee  mov     rax, [rax+10h]
0x180014df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014df7  call    cs:__imp_CoUninitialize
0x180014dfe  nop     dword ptr [rax+rax+00h]
0x180014e03  lea     rcx, ?g_RegistrationProtection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014e0a  call    cs:__imp_LeaveCriticalSection
0x180014e11  nop     dword ptr [rax+rax+00h]
0x180014e16  mov     eax, ebx
0x180014e18  mov     rbx, [rsp+40h+arg_18]
0x180014e20  add     rsp, 40h
0x180014e24  pop     r14
0x180014e26  pop     r12
0x180014e28  pop     rdi
0x180014e29  pop     rsi
0x180014e2a  pop     rbp
0x180014e2b  retn
```

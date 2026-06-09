# StartBeaconSvr(void)

- ea: `0x180013b78`
- end: `0x180013de0`
- name: `?StartBeaconSvr@@YAJXZ`
- size: `616`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013ef8`
- `0x180070598`

## callees

- `0x180013b78`
- `0x180013f34`
- `0x180037c3c`
- `0x180039bbc`
- `0x18003fb24`
- `0x18004a434`
- `0x1800885ec`
- `0x1800886f4`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ba1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ba1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013dc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013dc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013d20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013d20`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013d68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013d68`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180013d08`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180013d08`
- `OLEAUT32!__imp_SysAllocString` at `0x180013c93`
- `OLEAUT32!__imp_SysAllocString` at `0x180013c93`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d71`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d81`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d92`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d71`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d81`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d92`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013db7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013db7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180013bc3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180013bc3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013c07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013c07`

## string_xrefs

- `0x180013d16`: `DllRegisterServer`
- `0x180013d01`: `UPNPHOST.DLL`

## pseudocode

```c
__int64 StartBeaconSvr(void)
{
  __int64 result; // rax
  int Instance; // ebx
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
    dword_1800A8A34 = 1;
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
            Instance = ATL::CComObject<CInternetGatewayDevice>::CreateInstance((char **)&v10);
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
0x180013b78  mov     [rsp-28h+arg_18], rbx
0x180013b7d  push    rbp
0x180013b7e  push    rsi
0x180013b7f  push    rdi
0x180013b80  push    r12
0x180013b82  push    r14
0x180013b84  mov     rbp, rsp
0x180013b87  sub     rsp, 40h
0x180013b8b  call    ?IsHomenetModuleOSType@@YAHW4_ENUM_HNET_MODULE@@@Z; IsHomenetModuleOSType(_ENUM_HNET_MODULE)
0x180013b90  test    eax, eax
0x180013b92  jz      loc_180013DCC
0x180013b98  lea     rcx, ?g_RegistrationProtection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180013b9f  xor     ebx, ebx
0x180013ba1  call    cs:__imp_EnterCriticalSection
0x180013ba7  cmp     cs:bstrString, rbx
0x180013bae  mov     cs:dword_1800A8A34, 1
0x180013bb8  jnz     loc_180013DBD
0x180013bbe  lea     edx, [rbx+4]; dwCoInit
0x180013bc1  xor     ecx, ecx; pvReserved
0x180013bc3  call    cs:__imp_CoInitializeEx
0x180013bc9  mov     ebx, eax
0x180013bcb  test    eax, eax
0x180013bcd  js      loc_180013DBD
0x180013bd3  call    ?BeaconEnabled@@YAJXZ; BeaconEnabled(void)
0x180013bd8  mov     ebx, eax
0x180013bda  test    eax, eax
0x180013bdc  js      loc_180013DB7
0x180013be2  xor     edx, edx; pUnkOuter
0x180013be4  mov     [rbp+arg_0], 0
0x180013bec  lea     rax, [rbp+arg_0]
0x180013bf0  lea     r9, IID_IUPnPRegistrar; riid
0x180013bf7  mov     [rsp+40h+ppv], rax; ppv
0x180013bfc  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x180013c03  lea     r8d, [rdx+15h]; dwClsContext
0x180013c07  call    cs:__imp_CoCreateInstance
0x180013c0d  mov     ebx, eax
0x180013c0f  test    eax, eax
0x180013c11  js      loc_180013DB7
0x180013c17  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180013c1b  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x180013c20  call    ?ObtainImpersonationToken@CSwitchSecurityContext@@SAJXZ; CSwitchSecurityContext::ObtainImpersonationToken(void)
0x180013c25  lea     rcx, [rbp+arg_8]
0x180013c29  mov     [rbp+arg_8], 0
0x180013c31  call    ?CreateInstance@?$CComObject@VCInternetGatewayDevice@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInternetGatewayDevice>::CreateInstance(ATL::CComObject<CInternetGatewayDevice> * *)
0x180013c36  mov     ebx, eax
0x180013c38  test    eax, eax
0x180013c3a  js      loc_180013DA7
0x180013c40  mov     rdi, [rbp+arg_8]
0x180013c44  test    rdi, rdi
0x180013c47  jnz     short loc_180013C53
0x180013c49  mov     ebx, 80004005h
0x180013c4e  jmp     loc_180013DA7
0x180013c53  mov     rax, [rdi]
0x180013c56  mov     rcx, rdi
0x180013c59  mov     rax, [rax+8]
0x180013c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c62  mov     rax, [rdi+48h]
0x180013c66  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180013c6a  xor     ecx, ecx
0x180013c6c  mov     [rbp+arg_8], 0
0x180013c74  cmp     dword ptr [rax+68h], 3
0x180013c78  setnz   cl
0x180013c7b  inc     ecx; int
0x180013c7d  call    ?GetDescriptionDocument@@YAJHPEAPEAG@Z; GetDescriptionDocument(int,ushort * *)
0x180013c82  mov     ebx, eax
0x180013c84  test    eax, eax
0x180013c86  js      loc_180013D98
0x180013c8c  lea     rcx, psz; "Init"
0x180013c93  call    cs:__imp_SysAllocString
0x180013c99  mov     rsi, rax
0x180013c9c  test    rax, rax
0x180013c9f  jz      loc_180013D89
0x180013ca5  lea     rcx, [rbp+bstrString]; unsigned __int16 **
0x180013ca9  mov     [rbp+bstrString], 0
0x180013cb1  call    ?GetXMLPath@@YAJPEAPEAG@Z; GetXMLPath(ushort * *)
0x180013cb6  test    eax, eax
0x180013cb8  js      loc_180013D79
0x180013cbe  mov     r10, [rbp+arg_0]
0x180013cc2  mov     r9, rsi
0x180013cc5  mov     r12, [rbp+bstrString]
0x180013cc9  mov     r8, rdi
0x180013ccc  mov     rdx, [rbp+arg_8]
0x180013cd0  mov     rcx, [r10]
0x180013cd3  mov     rax, [rcx+20h]
0x180013cd7  lea     rcx, bstrString
0x180013cde  mov     [rsp+40h+var_10], rcx
0x180013ce3  mov     rcx, r10
0x180013ce6  mov     [rsp+40h+var_18], 708h
0x180013cee  mov     [rsp+40h+ppv], r12
0x180013cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cf8  mov     ebx, eax
0x180013cfa  cmp     eax, 80070005h
0x180013cff  jnz     short loc_180013D6E
0x180013d01  lea     rcx, LibFileName; "UPNPHOST.DLL"
0x180013d08  call    cs:__imp_LoadLibraryW
0x180013d0e  mov     r14, rax
0x180013d11  test    rax, rax
0x180013d14  jz      short loc_180013D6E
0x180013d16  lea     rdx, ProcName; "DllRegisterServer"
0x180013d1d  mov     rcx, rax; hModule
0x180013d20  call    cs:__imp_GetProcAddress
0x180013d26  test    rax, rax
0x180013d29  jz      short loc_180013D65
0x180013d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d30  mov     rcx, [rbp+arg_0]
0x180013d34  lea     rdx, bstrString
0x180013d3b  mov     [rsp+40h+var_10], rdx
0x180013d40  mov     r9, rsi
0x180013d43  mov     rdx, [rbp+arg_8]
0x180013d47  mov     r8, rdi
0x180013d4a  mov     [rsp+40h+var_18], 708h
0x180013d52  mov     rax, [rcx]
0x180013d55  mov     [rsp+40h+ppv], r12
0x180013d5a  mov     rax, [rax+20h]
0x180013d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d63  mov     ebx, eax
0x180013d65  mov     rcx, r14; hLibModule
0x180013d68  call    cs:__imp_FreeLibrary
0x180013d6e  mov     rcx, r12; bstrString
0x180013d71  call    cs:__imp_SysFreeString
0x180013d77  jmp     short loc_180013D7E
0x180013d79  mov     ebx, 8007000Eh
0x180013d7e  mov     rcx, rsi; bstrString
0x180013d81  call    cs:__imp_SysFreeString
0x180013d87  jmp     short loc_180013D8E
0x180013d89  mov     ebx, 8007000Eh
0x180013d8e  mov     rcx, [rbp+arg_8]; bstrString
0x180013d92  call    cs:__imp_SysFreeString
0x180013d98  mov     rax, [rdi]
0x180013d9b  mov     rcx, rdi
0x180013d9e  mov     rax, [rax+10h]
0x180013da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da7  mov     rcx, [rbp+arg_0]
0x180013dab  mov     rax, [rcx]
0x180013dae  mov     rax, [rax+10h]
0x180013db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013db7  call    cs:__imp_CoUninitialize
0x180013dbd  lea     rcx, ?g_RegistrationProtection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180013dc4  call    cs:__imp_LeaveCriticalSection
0x180013dca  mov     eax, ebx
0x180013dcc  mov     rbx, [rsp+40h+arg_18]
0x180013dd4  add     rsp, 40h
0x180013dd8  pop     r14
0x180013dda  pop     r12
0x180013ddc  pop     rdi
0x180013ddd  pop     rsi
0x180013dde  pop     rbp
0x180013ddf  retn
```

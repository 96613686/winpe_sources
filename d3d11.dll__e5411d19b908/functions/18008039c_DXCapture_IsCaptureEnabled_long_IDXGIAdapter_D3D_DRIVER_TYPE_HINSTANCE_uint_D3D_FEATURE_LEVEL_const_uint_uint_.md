# DXCapture::IsCaptureEnabled<long (IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)>(long (*)(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *),char const *,char const *)

- ea: `0x18008039c`
- end: `0x18008056b`
- name: `??$IsCaptureEnabled@$$A6AJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@Z@DXCapture@@YAP6AJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@ZP6AJ012I3II456@ZPEBD8@Z`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180080310`

## callees

- `0x18008039c`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800803e5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800803e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008047e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180080560`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008047e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180080560`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080420`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080447`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008045b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080420`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080447`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008045b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008054d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008054d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800803cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800803cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080538`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080538`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180080517`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180080517`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800804d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800804d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800804a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800804a1`

## string_xrefs

- `0x1800803c2`: `DXCaptureReplay.dll`
- `0x180080541`: `DXCaptureReplay.dll`
- `0x180080440`: `GetRealPtrPtrD3D11CreateDevice`
- `0x180080451`: `D3D11CreateDeviceGenerated`

## pseudocode

```c
__int64 (__fastcall *__fastcall DXCapture::IsCaptureEnabled<long (IDXGIAdapter *,enum D3D_DRIVER_TYPE,HINSTANCE__ *,unsigned int,enum D3D_FEATURE_LEVEL const *,unsigned int,unsigned int,ID3D11Device * *,enum D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)>(
        __int64 a1,
        __int64 a2,
        __int64 a3))(struct IDXGIAdapter *, enum D3D_DRIVER_TYPE, HINSTANCE, unsigned int, const enum D3D_FEATURE_LEVEL *, UINT, UINT, struct ID3D11Device **, enum D3D_FEATURE_LEVEL *, struct ID3D11DeviceContext **)
{
  BOOL ModuleHandle; // esi
  HANDLE v4; // rax
  HMODULE Library; // rax
  int (*ProcAddress)(void); // rax
  __int64 (*v8)(void); // rdi
  FARPROC v9; // rax
  FARPROC v10; // rbx
  int v11; // ebx
  HKEY hkey; // [rsp+40h] [rbp-18h] BYREF
  __int64 pvData; // [rsp+80h] [rbp+28h] BYREF
  __int64 pcbData; // [rsp+88h] [rbp+30h] BYREF
  __int64 pdwType; // [rsp+90h] [rbp+38h] BYREF
  HMODULE phModule; // [rsp+98h] [rbp+40h] BYREF

  pdwType = a3;
  pcbData = a2;
  pvData = a1;
  phModule = 0;
  ModuleHandle = GetModuleHandleExW(0, L"DXCaptureReplay.dll", &phModule);
  if ( !ModuleHandle || (Library = phModule) == 0 )
  {
    v4 = OpenSemaphoreW(0x100000u, 0, L"DXEnableCapture");
    if ( v4 )
    {
      CloseHandle(v4);
      hkey = 0;
      v11 = 1;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DXTools", 0, 0x20019u, &hkey) )
      {
        LODWORD(pdwType) = 0;
        LODWORD(pvData) = 0;
        LODWORD(pcbData) = 4;
        if ( !RegGetValueW(hkey, 0, L"LoadFromAnywhere", 0x10u, (LPDWORD)&pdwType, &pvData, (LPDWORD)&pcbData)
          && (_DWORD)pdwType == 4
          && (_DWORD)pcbData == 4 )
        {
          v11 = pvData == 0;
        }
        RegCloseKey(hkey);
      }
      Library = LoadLibraryExW(L"DXCaptureReplay.dll", 0, v11 << 11);
      phModule = Library;
    }
    else
    {
      Library = phModule;
    }
    if ( !Library )
      return D3D11CreateDeviceImpl;
  }
  ProcAddress = (int (*)(void))GetProcAddress(Library, "LazyAttachToMonitor");
  if ( !ProcAddress
    || ProcAddress() < 0
    || (v8 = GetProcAddress(phModule, "GetRealPtrPtrD3D11CreateDevice"),
        v9 = GetProcAddress(phModule, "D3D11CreateDeviceGenerated"),
        v10 = v9,
        !v8)
    || !v9 )
  {
    FreeLibrary(phModule);
    return D3D11CreateDeviceImpl;
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v8() = D3D11CreateDeviceImpl;
  return (__int64 (__fastcall *)(struct IDXGIAdapter *, enum D3D_DRIVER_TYPE, HINSTANCE, unsigned int, const enum D3D_FEATURE_LEVEL *, UINT, UINT, struct ID3D11Device **, enum D3D_FEATURE_LEVEL *, struct ID3D11DeviceContext **))v10;
}

```

## disassembly

```asm
0x18008039c  mov     [rsp-20h+pdwType], r8
0x1800803a1  mov     [rsp-20h+arg_8], rdx
0x1800803a6  mov     [rsp-20h+arg_0], rcx
0x1800803ab  push    rbp
0x1800803ac  push    rbx
0x1800803ad  push    rsi
0x1800803ae  push    rdi
0x1800803af  mov     rbp, rsp
0x1800803b2  sub     rsp, 58h
0x1800803b6  lea     r8, [rbp+phModule]; phModule
0x1800803ba  mov     [rbp+phModule], 0
0x1800803c2  lea     rdx, aDxcapturerepla; "DXCaptureReplay.dll"
0x1800803c9  xor     ecx, ecx; dwFlags
0x1800803cb  call    cs:__imp_GetModuleHandleExW
0x1800803d1  mov     esi, eax
0x1800803d3  test    eax, eax
0x1800803d5  jnz     short loc_18008040D
0x1800803d7  lea     r8, aDxenablecaptur; "DXEnableCapture"
0x1800803de  xor     edx, edx; bInheritHandle
0x1800803e0  mov     ecx, 100000h; dwDesiredAccess
0x1800803e5  call    cs:__imp_OpenSemaphoreW
0x1800803eb  test    rax, rax
0x1800803ee  jnz     loc_18008049E
0x1800803f4  mov     rax, [rbp+phModule]
0x1800803f8  test    rax, rax
0x1800803fb  jnz     short loc_180080416
0x1800803fd  lea     rax, ?D3D11CreateDeviceImpl@@YAJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@Z; D3D11CreateDeviceImpl(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)
0x180080404  add     rsp, 58h
0x180080408  pop     rdi
0x180080409  pop     rsi
0x18008040a  pop     rbx
0x18008040b  pop     rbp
0x18008040c  retn
0x18008040d  mov     rax, [rbp+phModule]
0x180080411  test    rax, rax
0x180080414  jz      short loc_1800803D7
0x180080416  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x18008041d  mov     rcx, rax; hModule
0x180080420  call    cs:__imp_GetProcAddress
0x180080426  test    rax, rax
0x180080429  jz      loc_18008055C
0x18008042f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080434  test    eax, eax
0x180080436  js      loc_18008055C
0x18008043c  mov     rcx, [rbp+phModule]; hModule
0x180080440  lea     rdx, aGetrealptrptrd; "GetRealPtrPtrD3D11CreateDevice"
0x180080447  call    cs:__imp_GetProcAddress
0x18008044d  mov     rcx, [rbp+phModule]; hModule
0x180080451  lea     rdx, aD3d11createdev_7; "D3D11CreateDeviceGenerated"
0x180080458  mov     rdi, rax
0x18008045b  call    cs:__imp_GetProcAddress
0x180080461  mov     rbx, rax
0x180080464  test    rdi, rdi
0x180080467  jz      loc_18008055C
0x18008046d  test    rax, rax
0x180080470  jz      loc_18008055C
0x180080476  test    esi, esi
0x180080478  jz      short loc_180080484
0x18008047a  mov     rcx, [rbp+phModule]; hLibModule
0x18008047e  call    cs:__imp_FreeLibrary
0x180080484  mov     rax, rdi
0x180080487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008048c  lea     rcx, ?D3D11CreateDeviceImpl@@YAJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@Z; D3D11CreateDeviceImpl(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)
0x180080493  mov     [rax], rcx
0x180080496  mov     rax, rbx
0x180080499  jmp     loc_180080404
0x18008049e  mov     rcx, rax; hObject
0x1800804a1  call    cs:__imp_CloseHandle
0x1800804a7  lea     rax, [rbp+hkey]
0x1800804ab  mov     [rbp+hkey], 0
0x1800804b3  mov     r9d, 20019h; samDesired
0x1800804b9  mov     [rsp+58h+phkResult], rax; phkResult
0x1800804be  xor     r8d, r8d; ulOptions
0x1800804c1  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\DXTools"
0x1800804c8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800804cf  mov     ebx, 1
0x1800804d4  call    cs:__imp_RegOpenKeyExW
0x1800804da  test    eax, eax
0x1800804dc  jnz     short loc_18008053E
0x1800804de  mov     rcx, [rbp+hkey]; hkey
0x1800804e2  lea     r9d, [rbx+0Fh]; dwFlags
0x1800804e6  mov     dword ptr [rbp+pdwType], eax
0x1800804e9  lea     r8, Value; "LoadFromAnywhere"
0x1800804f0  mov     dword ptr [rbp+arg_0], eax
0x1800804f3  xor     edx, edx; lpSubKey
0x1800804f5  lea     rax, [rbp+arg_8]
0x1800804f9  mov     dword ptr [rbp+arg_8], 4
0x180080500  mov     [rsp+58h+pcbData], rax; pcbData
0x180080505  lea     rax, [rbp+arg_0]
0x180080509  mov     [rsp+58h+pvData], rax; pvData
0x18008050e  lea     rax, [rbp+pdwType]
0x180080512  mov     [rsp+58h+phkResult], rax; pdwType
0x180080517  call    cs:__imp_RegGetValueW
0x18008051d  test    eax, eax
0x18008051f  jnz     short loc_180080534
0x180080521  cmp     dword ptr [rbp+pdwType], 4
0x180080525  jnz     short loc_180080534
0x180080527  cmp     dword ptr [rbp+arg_8], 4
0x18008052b  jnz     short loc_180080534
0x18008052d  cmp     dword ptr [rbp+arg_0], eax
0x180080530  jz      short loc_180080534
0x180080532  xor     ebx, ebx
0x180080534  mov     rcx, [rbp+hkey]; hKey
0x180080538  call    cs:__imp_RegCloseKey
0x18008053e  shl     ebx, 0Bh
0x180080541  lea     rcx, aDxcapturerepla; "DXCaptureReplay.dll"
0x180080548  mov     r8d, ebx; dwFlags
0x18008054b  xor     edx, edx; hFile
0x18008054d  call    cs:__imp_LoadLibraryExW
0x180080553  mov     [rbp+phModule], rax
0x180080557  jmp     loc_1800803F8
0x18008055c  mov     rcx, [rbp+phModule]; hLibModule
0x180080560  call    cs:__imp_FreeLibrary
0x180080566  jmp     loc_1800803FD
```

# DXCapture::IsCaptureEnabled<long (IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,DXGI_SWAP_CHAIN_DESC const *,IDXGISwapChain * *,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)>(long (*)(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,DXGI_SWAP_CHAIN_DESC const *,IDXGISwapChain * *,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *),char const *,char const *)

- ea: `0x18007f184`
- end: `0x18007f353`
- name: `??$IsCaptureEnabled@$$A6AJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEBUDXGI_SWAP_CHAIN_DESC@@PEAPEAUIDXGISwapChain@@PEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@Z@DXCapture@@YAP6AJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEBUDXGI_SWAP_CHAIN_DESC@@PEAPEAUIDXGISwapChain@@PEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@ZP6AJ012I3II45678@ZPEBDPEBD@Z`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007f0e0`

## callees

- `0x18007f184`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18007f1cd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18007f1cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007f266`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007f348`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007f266`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007f348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f208`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f22f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f243`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f208`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f22f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f243`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007f335`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007f335`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007f1b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007f1b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f320`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f320`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007f2ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007f2ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f2bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f2bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f289`

## string_xrefs

- `0x18007f228`: `GetRealPtrPtrD3D11CreateDeviceAndSwapChain`
- `0x18007f239`: `D3D11CreateDeviceAndSwapChainGenerated`
- `0x18007f1aa`: `DXCaptureReplay.dll`
- `0x18007f329`: `DXCaptureReplay.dll`

## pseudocode

```c
int (*__fastcall DXCapture::IsCaptureEnabled<long (IDXGIAdapter *,enum D3D_DRIVER_TYPE,HINSTANCE__ *,unsigned int,enum D3D_FEATURE_LEVEL const *,unsigned int,unsigned int,DXGI_SWAP_CHAIN_DESC const *,IDXGISwapChain * *,ID3D11Device * *,enum D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)>(
        __int64 a1,
        __int64 a2,
        __int64 a3))(struct IDXGIAdapter *, enum D3D_DRIVER_TYPE, HINSTANCE, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, unsigned int, const struct DXGI_SWAP_CHAIN_DESC *, struct IDXGISwapChain **, struct ID3D11Device **, enum D3D_FEATURE_LEVEL *, struct ID3D11DeviceContext **)
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
      return D3D11CreateDeviceAndSwapChainImpl;
  }
  ProcAddress = (int (*)(void))GetProcAddress(Library, "LazyAttachToMonitor");
  if ( !ProcAddress
    || ProcAddress() < 0
    || (v8 = GetProcAddress(phModule, "GetRealPtrPtrD3D11CreateDeviceAndSwapChain"),
        v9 = GetProcAddress(phModule, "D3D11CreateDeviceAndSwapChainGenerated"),
        v10 = v9,
        !v8)
    || !v9 )
  {
    FreeLibrary(phModule);
    return D3D11CreateDeviceAndSwapChainImpl;
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v8() = D3D11CreateDeviceAndSwapChainImpl;
  return (int (*)(struct IDXGIAdapter *, enum D3D_DRIVER_TYPE, HINSTANCE, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, unsigned int, const struct DXGI_SWAP_CHAIN_DESC *, struct IDXGISwapChain **, struct ID3D11Device **, enum D3D_FEATURE_LEVEL *, struct ID3D11DeviceContext **))v10;
}

```

## disassembly

```asm
0x18007f184  mov     [rsp-20h+pdwType], r8
0x18007f189  mov     [rsp-20h+arg_8], rdx
0x18007f18e  mov     [rsp-20h+arg_0], rcx
0x18007f193  push    rbp
0x18007f194  push    rbx
0x18007f195  push    rsi
0x18007f196  push    rdi
0x18007f197  mov     rbp, rsp
0x18007f19a  sub     rsp, 58h
0x18007f19e  lea     r8, [rbp+phModule]; phModule
0x18007f1a2  mov     [rbp+phModule], 0
0x18007f1aa  lea     rdx, aDxcapturerepla; "DXCaptureReplay.dll"
0x18007f1b1  xor     ecx, ecx; dwFlags
0x18007f1b3  call    cs:__imp_GetModuleHandleExW
0x18007f1b9  mov     esi, eax
0x18007f1bb  test    eax, eax
0x18007f1bd  jnz     short loc_18007F1F5
0x18007f1bf  lea     r8, aDxenablecaptur; "DXEnableCapture"
0x18007f1c6  xor     edx, edx; bInheritHandle
0x18007f1c8  mov     ecx, 100000h; dwDesiredAccess
0x18007f1cd  call    cs:__imp_OpenSemaphoreW
0x18007f1d3  test    rax, rax
0x18007f1d6  jnz     loc_18007F286
0x18007f1dc  mov     rax, [rbp+phModule]
0x18007f1e0  test    rax, rax
0x18007f1e3  jnz     short loc_18007F1FE
0x18007f1e5  lea     rax, ?D3D11CreateDeviceAndSwapChainImpl@@YAJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEBUDXGI_SWAP_CHAIN_DESC@@PEAPEAUIDXGISwapChain@@PEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@Z; D3D11CreateDeviceAndSwapChainImpl(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,DXGI_SWAP_CHAIN_DESC const *,IDXGISwapChain * *,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)
0x18007f1ec  add     rsp, 58h
0x18007f1f0  pop     rdi
0x18007f1f1  pop     rsi
0x18007f1f2  pop     rbx
0x18007f1f3  pop     rbp
0x18007f1f4  retn
0x18007f1f5  mov     rax, [rbp+phModule]
0x18007f1f9  test    rax, rax
0x18007f1fc  jz      short loc_18007F1BF
0x18007f1fe  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x18007f205  mov     rcx, rax; hModule
0x18007f208  call    cs:__imp_GetProcAddress
0x18007f20e  test    rax, rax
0x18007f211  jz      loc_18007F344
0x18007f217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f21c  test    eax, eax
0x18007f21e  js      loc_18007F344
0x18007f224  mov     rcx, [rbp+phModule]; hModule
0x18007f228  lea     rdx, aGetrealptrptrd_0; "GetRealPtrPtrD3D11CreateDeviceAndSwapCh"...
0x18007f22f  call    cs:__imp_GetProcAddress
0x18007f235  mov     rcx, [rbp+phModule]; hModule
0x18007f239  lea     rdx, aD3d11createdev_9; "D3D11CreateDeviceAndSwapChainGenerated"
0x18007f240  mov     rdi, rax
0x18007f243  call    cs:__imp_GetProcAddress
0x18007f249  mov     rbx, rax
0x18007f24c  test    rdi, rdi
0x18007f24f  jz      loc_18007F344
0x18007f255  test    rax, rax
0x18007f258  jz      loc_18007F344
0x18007f25e  test    esi, esi
0x18007f260  jz      short loc_18007F26C
0x18007f262  mov     rcx, [rbp+phModule]; hLibModule
0x18007f266  call    cs:__imp_FreeLibrary
0x18007f26c  mov     rax, rdi
0x18007f26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f274  lea     rcx, ?D3D11CreateDeviceAndSwapChainImpl@@YAJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEBUDXGI_SWAP_CHAIN_DESC@@PEAPEAUIDXGISwapChain@@PEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@Z; D3D11CreateDeviceAndSwapChainImpl(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,DXGI_SWAP_CHAIN_DESC const *,IDXGISwapChain * *,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)
0x18007f27b  mov     [rax], rcx
0x18007f27e  mov     rax, rbx
0x18007f281  jmp     loc_18007F1EC
0x18007f286  mov     rcx, rax; hObject
0x18007f289  call    cs:__imp_CloseHandle
0x18007f28f  lea     rax, [rbp+hkey]
0x18007f293  mov     [rbp+hkey], 0
0x18007f29b  mov     r9d, 20019h; samDesired
0x18007f2a1  mov     [rsp+58h+phkResult], rax; phkResult
0x18007f2a6  xor     r8d, r8d; ulOptions
0x18007f2a9  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\DXTools"
0x18007f2b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007f2b7  mov     ebx, 1
0x18007f2bc  call    cs:__imp_RegOpenKeyExW
0x18007f2c2  test    eax, eax
0x18007f2c4  jnz     short loc_18007F326
0x18007f2c6  mov     rcx, [rbp+hkey]; hkey
0x18007f2ca  lea     r9d, [rbx+0Fh]; dwFlags
0x18007f2ce  mov     dword ptr [rbp+pdwType], eax
0x18007f2d1  lea     r8, Value; "LoadFromAnywhere"
0x18007f2d8  mov     dword ptr [rbp+arg_0], eax
0x18007f2db  xor     edx, edx; lpSubKey
0x18007f2dd  lea     rax, [rbp+arg_8]
0x18007f2e1  mov     dword ptr [rbp+arg_8], 4
0x18007f2e8  mov     [rsp+58h+pcbData], rax; pcbData
0x18007f2ed  lea     rax, [rbp+arg_0]
0x18007f2f1  mov     [rsp+58h+pvData], rax; pvData
0x18007f2f6  lea     rax, [rbp+pdwType]
0x18007f2fa  mov     [rsp+58h+phkResult], rax; pdwType
0x18007f2ff  call    cs:__imp_RegGetValueW
0x18007f305  test    eax, eax
0x18007f307  jnz     short loc_18007F31C
0x18007f309  cmp     dword ptr [rbp+pdwType], 4
0x18007f30d  jnz     short loc_18007F31C
0x18007f30f  cmp     dword ptr [rbp+arg_8], 4
0x18007f313  jnz     short loc_18007F31C
0x18007f315  cmp     dword ptr [rbp+arg_0], eax
0x18007f318  jz      short loc_18007F31C
0x18007f31a  xor     ebx, ebx
0x18007f31c  mov     rcx, [rbp+hkey]; hKey
0x18007f320  call    cs:__imp_RegCloseKey
0x18007f326  shl     ebx, 0Bh
0x18007f329  lea     rcx, aDxcapturerepla; "DXCaptureReplay.dll"
0x18007f330  mov     r8d, ebx; dwFlags
0x18007f333  xor     edx, edx; hFile
0x18007f335  call    cs:__imp_LoadLibraryExW
0x18007f33b  mov     [rbp+phModule], rax
0x18007f33f  jmp     loc_18007F1E0
0x18007f344  mov     rcx, [rbp+phModule]; hLibModule
0x18007f348  call    cs:__imp_FreeLibrary
0x18007f34e  jmp     loc_18007F1E5
```

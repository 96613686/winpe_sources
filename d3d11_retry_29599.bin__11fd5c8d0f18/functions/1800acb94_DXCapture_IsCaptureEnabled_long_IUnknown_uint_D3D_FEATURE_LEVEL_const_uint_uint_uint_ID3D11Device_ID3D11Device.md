# DXCapture::IsCaptureEnabled<long (IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *)>(long (*)(IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *),char const *,char const *)

- ea: `0x1800acb94`
- end: `0x1800acd4c`
- name: `??$IsCaptureEnabled@$$A6AJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IIIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@Z@DXCapture@@YAP6AJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IIIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@ZP6AJ0I1III234@ZPEBD6@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800aebd0`

## callees

- `0x1800acb94`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800acbea`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800acbea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acd15`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acd36`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acd15`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acd36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800accc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800acce6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800accfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800accc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800acce6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800accfa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800acca8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800acca8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800acbc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800acbc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800acc93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800acc93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acc72`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acc72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800acc2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800acc2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acbfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acbfc`

## string_xrefs

- `0x1800acbba`: `DXCaptureReplay.dll`
- `0x1800acc9c`: `DXCaptureReplay.dll`
- `0x1800accf0`: `D3D11On12CreateDeviceGenerated`
- `0x1800accdf`: `GetRealPtrPtrD3D11On12CreateDevice`

## pseudocode

```c
__int64 (__fastcall *__fastcall DXCapture::IsCaptureEnabled<long (IUnknown *,unsigned int,enum D3D_FEATURE_LEVEL const *,unsigned int,unsigned int,unsigned int,ID3D11Device * *,ID3D11DeviceContext * *,enum D3D_FEATURE_LEVEL *)>(
        __int64 a1,
        __int64 a2,
        __int64 a3))(struct IUnknown *, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, unsigned int, ULONGLONG, struct ID3D11Device **, struct ID3D11DeviceContext **, enum D3D_FEATURE_LEVEL *)
{
  BOOL ModuleHandle; // esi
  HMODULE Library; // rax
  HANDLE v5; // rax
  int v6; // ebx
  int (*ProcAddress)(void); // rax
  __int64 (*v8)(void); // rdi
  FARPROC v9; // rax
  FARPROC v10; // rbx
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
    v5 = OpenSemaphoreW(0x100000u, 0, L"DXEnableCapture");
    if ( v5 )
    {
      CloseHandle(v5);
      hkey = 0;
      v6 = 1;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DXTools", 0, 0x20019u, &hkey) )
      {
        LODWORD(pdwType) = 0;
        LODWORD(pvData) = 0;
        LODWORD(pcbData) = 4;
        if ( !RegGetValueW(hkey, 0, L"LoadFromAnywhere", 0x10u, (LPDWORD)&pdwType, &pvData, (LPDWORD)&pcbData)
          && (_DWORD)pdwType == 4
          && (_DWORD)pcbData == 4 )
        {
          v6 = pvData == 0;
        }
        RegCloseKey(hkey);
      }
      Library = LoadLibraryExW(L"DXCaptureReplay.dll", 0, v6 << 11);
      phModule = Library;
    }
    else
    {
      Library = phModule;
    }
    if ( !Library )
      return D3D11CreateDeviceForD3D12Impl;
  }
  ProcAddress = (int (*)(void))GetProcAddress(Library, "LazyAttachToMonitor");
  if ( !ProcAddress
    || ProcAddress() < 0
    || (v8 = GetProcAddress(phModule, "GetRealPtrPtrD3D11On12CreateDevice"),
        v9 = GetProcAddress(phModule, "D3D11On12CreateDeviceGenerated"),
        v10 = v9,
        !v8)
    || !v9 )
  {
    FreeLibrary(phModule);
    return D3D11CreateDeviceForD3D12Impl;
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v8() = D3D11CreateDeviceForD3D12Impl;
  return (__int64 (__fastcall *)(struct IUnknown *, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, unsigned int, ULONGLONG, struct ID3D11Device **, struct ID3D11DeviceContext **, enum D3D_FEATURE_LEVEL *))v10;
}

```

## disassembly

```asm
0x1800acb94  mov     [rsp-20h+pdwType], r8
0x1800acb99  mov     [rsp-20h+arg_8], rdx
0x1800acb9e  mov     [rsp-20h+arg_0], rcx
0x1800acba3  push    rbp
0x1800acba4  push    rbx
0x1800acba5  push    rsi
0x1800acba6  push    rdi
0x1800acba7  mov     rbp, rsp
0x1800acbaa  sub     rsp, 58h
0x1800acbae  lea     r8, [rbp+phModule]; phModule
0x1800acbb2  mov     [rbp+phModule], 0
0x1800acbba  lea     rdx, aDxcapturerepla; "DXCaptureReplay.dll"
0x1800acbc1  xor     ecx, ecx; dwFlags
0x1800acbc3  call    cs:__imp_GetModuleHandleExW
0x1800acbc9  mov     esi, eax
0x1800acbcb  test    eax, eax
0x1800acbcd  jz      short loc_1800ACBDC
0x1800acbcf  mov     rax, [rbp+phModule]
0x1800acbd3  test    rax, rax
0x1800acbd6  jnz     loc_1800ACCBD
0x1800acbdc  lea     r8, aDxenablecaptur; "DXEnableCapture"
0x1800acbe3  xor     edx, edx; bInheritHandle
0x1800acbe5  mov     ecx, 100000h; dwDesiredAccess
0x1800acbea  call    cs:__imp_OpenSemaphoreW
0x1800acbf0  test    rax, rax
0x1800acbf3  jz      loc_1800ACCB4
0x1800acbf9  mov     rcx, rax; hObject
0x1800acbfc  call    cs:__imp_CloseHandle
0x1800acc02  lea     rax, [rbp+hkey]
0x1800acc06  mov     [rbp+hkey], 0
0x1800acc0e  mov     r9d, 20019h; samDesired
0x1800acc14  mov     [rsp+58h+phkResult], rax; phkResult
0x1800acc19  xor     r8d, r8d; ulOptions
0x1800acc1c  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\DXTools"
0x1800acc23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800acc2a  mov     ebx, 1
0x1800acc2f  call    cs:__imp_RegOpenKeyExW
0x1800acc35  test    eax, eax
0x1800acc37  jnz     short loc_1800ACC99
0x1800acc39  mov     rcx, [rbp+hkey]; hkey
0x1800acc3d  lea     r9d, [rbx+0Fh]; dwFlags
0x1800acc41  mov     dword ptr [rbp+pdwType], eax
0x1800acc44  lea     r8, Value; "LoadFromAnywhere"
0x1800acc4b  mov     dword ptr [rbp+arg_0], eax
0x1800acc4e  xor     edx, edx; lpSubKey
0x1800acc50  lea     rax, [rbp+arg_8]
0x1800acc54  mov     dword ptr [rbp+arg_8], 4
0x1800acc5b  mov     [rsp+58h+pcbData], rax; pcbData
0x1800acc60  lea     rax, [rbp+arg_0]
0x1800acc64  mov     [rsp+58h+pvData], rax; pvData
0x1800acc69  lea     rax, [rbp+pdwType]
0x1800acc6d  mov     [rsp+58h+phkResult], rax; pdwType
0x1800acc72  call    cs:__imp_RegGetValueW
0x1800acc78  test    eax, eax
0x1800acc7a  jnz     short loc_1800ACC8F
0x1800acc7c  cmp     dword ptr [rbp+pdwType], 4
0x1800acc80  jnz     short loc_1800ACC8F
0x1800acc82  cmp     dword ptr [rbp+arg_8], 4
0x1800acc86  jnz     short loc_1800ACC8F
0x1800acc88  cmp     dword ptr [rbp+arg_0], eax
0x1800acc8b  jz      short loc_1800ACC8F
0x1800acc8d  xor     ebx, ebx
0x1800acc8f  mov     rcx, [rbp+hkey]; hKey
0x1800acc93  call    cs:__imp_RegCloseKey
0x1800acc99  shl     ebx, 0Bh
0x1800acc9c  lea     rcx, aDxcapturerepla; "DXCaptureReplay.dll"
0x1800acca3  mov     r8d, ebx; dwFlags
0x1800acca6  xor     edx, edx; hFile
0x1800acca8  call    cs:__imp_LoadLibraryExW
0x1800accae  mov     [rbp+phModule], rax
0x1800accb2  jmp     short loc_1800ACCB8
0x1800accb4  mov     rax, [rbp+phModule]
0x1800accb8  test    rax, rax
0x1800accbb  jz      short loc_1800ACD3C
0x1800accbd  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x1800accc4  mov     rcx, rax; hModule
0x1800accc7  call    cs:__imp_GetProcAddress
0x1800acccd  test    rax, rax
0x1800accd0  jz      short loc_1800ACD32
0x1800accd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800accd7  test    eax, eax
0x1800accd9  js      short loc_1800ACD32
0x1800accdb  mov     rcx, [rbp+phModule]; hModule
0x1800accdf  lea     rdx, aGetrealptrptrd_1; "GetRealPtrPtrD3D11On12CreateDevice"
0x1800acce6  call    cs:__imp_GetProcAddress
0x1800accec  mov     rcx, [rbp+phModule]; hModule
0x1800accf0  lea     rdx, aD3d11on12creat_2; "D3D11On12CreateDeviceGenerated"
0x1800accf7  mov     rdi, rax
0x1800accfa  call    cs:__imp_GetProcAddress
0x1800acd00  mov     rbx, rax
0x1800acd03  test    rdi, rdi
0x1800acd06  jz      short loc_1800ACD32
0x1800acd08  test    rax, rax
0x1800acd0b  jz      short loc_1800ACD32
0x1800acd0d  test    esi, esi
0x1800acd0f  jz      short loc_1800ACD1B
0x1800acd11  mov     rcx, [rbp+phModule]; hLibModule
0x1800acd15  call    cs:__imp_FreeLibrary
0x1800acd1b  mov     rax, rdi
0x1800acd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acd23  lea     rcx, ?D3D11CreateDeviceForD3D12Impl@@YAJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IIIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@Z; D3D11CreateDeviceForD3D12Impl(IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *)
0x1800acd2a  mov     [rax], rcx
0x1800acd2d  mov     rax, rbx
0x1800acd30  jmp     short loc_1800ACD43
0x1800acd32  mov     rcx, [rbp+phModule]; hLibModule
0x1800acd36  call    cs:__imp_FreeLibrary
0x1800acd3c  lea     rax, ?D3D11CreateDeviceForD3D12Impl@@YAJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IIIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@Z; D3D11CreateDeviceForD3D12Impl(IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *)
0x1800acd43  add     rsp, 58h
0x1800acd47  pop     rdi
0x1800acd48  pop     rsi
0x1800acd49  pop     rbx
0x1800acd4a  pop     rbp
0x1800acd4b  retn
```

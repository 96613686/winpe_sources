# DXCapture::IsCaptureEnabled<long (IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,IUnknown * const *,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *)>(long (*)(IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,IUnknown * const *,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *),char const *,char const *)

- ea: `0x1800acd54`
- end: `0x1800acf0c`
- name: `??$IsCaptureEnabled@$$A6AJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IPEBQEAU1@IIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@Z@DXCapture@@YAP6AJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IPEBQEAU1@IIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@ZP6AJ0I1I2II345@ZPEBD7@Z`
- size: `440`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, __int64))(struct IUnknown *, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, struct IUnknown *const *, unsigned int, ULONGLONG Value, struct ID3D11Device **, struct ID3D11DeviceContext **, enum D3D_FEATURE_LEVEL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b0f80`

## callees

- `0x1800acd54`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800acdaa`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800acdaa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800aced5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acef6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800aced5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acef6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ace87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800acea6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aceba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ace87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800acea6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aceba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ace68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ace68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800acd83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800acd83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ace53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ace53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ace32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ace32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800acdef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800acdef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acdbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acdbc`

## string_xrefs

- `0x1800acd7a`: `DXCaptureReplay.dll`
- `0x1800ace5c`: `DXCaptureReplay.dll`
- `0x1800aceb0`: `D3D11On12CreateDeviceGenerated`
- `0x1800ace9f`: `GetRealPtrPtrD3D11On12CreateDevice`

## pseudocode

```c
__int64 (__fastcall *__fastcall DXCapture::IsCaptureEnabled<long (IUnknown *,unsigned int,enum D3D_FEATURE_LEVEL const *,unsigned int,IUnknown * const *,unsigned int,unsigned int,ID3D11Device * *,ID3D11DeviceContext * *,enum D3D_FEATURE_LEVEL *)>(
        __int64 a1,
        __int64 a2,
        __int64 a3))(struct IUnknown *, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, struct IUnknown *const *, unsigned int, ULONGLONG Value, struct ID3D11Device **, struct ID3D11DeviceContext **, enum D3D_FEATURE_LEVEL *)
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
      return D3D11On12CreateDeviceImpl;
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
    return D3D11On12CreateDeviceImpl;
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v8() = D3D11On12CreateDeviceImpl;
  return (__int64 (__fastcall *)(struct IUnknown *, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, struct IUnknown *const *, unsigned int, ULONGLONG, struct ID3D11Device **, struct ID3D11DeviceContext **, enum D3D_FEATURE_LEVEL *))v10;
}

```

## disassembly

```asm
0x1800acd54  mov     [rsp-20h+pdwType], r8
0x1800acd59  mov     [rsp-20h+arg_8], rdx
0x1800acd5e  mov     [rsp-20h+arg_0], rcx
0x1800acd63  push    rbp
0x1800acd64  push    rbx
0x1800acd65  push    rsi
0x1800acd66  push    rdi
0x1800acd67  mov     rbp, rsp
0x1800acd6a  sub     rsp, 58h
0x1800acd6e  lea     r8, [rbp+phModule]; phModule
0x1800acd72  mov     [rbp+phModule], 0
0x1800acd7a  lea     rdx, aDxcapturerepla; "DXCaptureReplay.dll"
0x1800acd81  xor     ecx, ecx; dwFlags
0x1800acd83  call    cs:__imp_GetModuleHandleExW
0x1800acd89  mov     esi, eax
0x1800acd8b  test    eax, eax
0x1800acd8d  jz      short loc_1800ACD9C
0x1800acd8f  mov     rax, [rbp+phModule]
0x1800acd93  test    rax, rax
0x1800acd96  jnz     loc_1800ACE7D
0x1800acd9c  lea     r8, aDxenablecaptur; "DXEnableCapture"
0x1800acda3  xor     edx, edx; bInheritHandle
0x1800acda5  mov     ecx, 100000h; dwDesiredAccess
0x1800acdaa  call    cs:__imp_OpenSemaphoreW
0x1800acdb0  test    rax, rax
0x1800acdb3  jz      loc_1800ACE74
0x1800acdb9  mov     rcx, rax; hObject
0x1800acdbc  call    cs:__imp_CloseHandle
0x1800acdc2  lea     rax, [rbp+hkey]
0x1800acdc6  mov     [rbp+hkey], 0
0x1800acdce  mov     r9d, 20019h; samDesired
0x1800acdd4  mov     [rsp+58h+phkResult], rax; phkResult
0x1800acdd9  xor     r8d, r8d; ulOptions
0x1800acddc  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\DXTools"
0x1800acde3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800acdea  mov     ebx, 1
0x1800acdef  call    cs:__imp_RegOpenKeyExW
0x1800acdf5  test    eax, eax
0x1800acdf7  jnz     short loc_1800ACE59
0x1800acdf9  mov     rcx, [rbp+hkey]; hkey
0x1800acdfd  lea     r9d, [rbx+0Fh]; dwFlags
0x1800ace01  mov     dword ptr [rbp+pdwType], eax
0x1800ace04  lea     r8, Value; "LoadFromAnywhere"
0x1800ace0b  mov     dword ptr [rbp+arg_0], eax
0x1800ace0e  xor     edx, edx; lpSubKey
0x1800ace10  lea     rax, [rbp+arg_8]
0x1800ace14  mov     dword ptr [rbp+arg_8], 4
0x1800ace1b  mov     [rsp+58h+pcbData], rax; pcbData
0x1800ace20  lea     rax, [rbp+arg_0]
0x1800ace24  mov     [rsp+58h+pvData], rax; pvData
0x1800ace29  lea     rax, [rbp+pdwType]
0x1800ace2d  mov     [rsp+58h+phkResult], rax; pdwType
0x1800ace32  call    cs:__imp_RegGetValueW
0x1800ace38  test    eax, eax
0x1800ace3a  jnz     short loc_1800ACE4F
0x1800ace3c  cmp     dword ptr [rbp+pdwType], 4
0x1800ace40  jnz     short loc_1800ACE4F
0x1800ace42  cmp     dword ptr [rbp+arg_8], 4
0x1800ace46  jnz     short loc_1800ACE4F
0x1800ace48  cmp     dword ptr [rbp+arg_0], eax
0x1800ace4b  jz      short loc_1800ACE4F
0x1800ace4d  xor     ebx, ebx
0x1800ace4f  mov     rcx, [rbp+hkey]; hKey
0x1800ace53  call    cs:__imp_RegCloseKey
0x1800ace59  shl     ebx, 0Bh
0x1800ace5c  lea     rcx, aDxcapturerepla; "DXCaptureReplay.dll"
0x1800ace63  mov     r8d, ebx; dwFlags
0x1800ace66  xor     edx, edx; hFile
0x1800ace68  call    cs:__imp_LoadLibraryExW
0x1800ace6e  mov     [rbp+phModule], rax
0x1800ace72  jmp     short loc_1800ACE78
0x1800ace74  mov     rax, [rbp+phModule]
0x1800ace78  test    rax, rax
0x1800ace7b  jz      short loc_1800ACEFC
0x1800ace7d  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x1800ace84  mov     rcx, rax; hModule
0x1800ace87  call    cs:__imp_GetProcAddress
0x1800ace8d  test    rax, rax
0x1800ace90  jz      short loc_1800ACEF2
0x1800ace92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace97  test    eax, eax
0x1800ace99  js      short loc_1800ACEF2
0x1800ace9b  mov     rcx, [rbp+phModule]; hModule
0x1800ace9f  lea     rdx, aGetrealptrptrd_1; "GetRealPtrPtrD3D11On12CreateDevice"
0x1800acea6  call    cs:__imp_GetProcAddress
0x1800aceac  mov     rcx, [rbp+phModule]; hModule
0x1800aceb0  lea     rdx, aD3d11on12creat_2; "D3D11On12CreateDeviceGenerated"
0x1800aceb7  mov     rdi, rax
0x1800aceba  call    cs:__imp_GetProcAddress
0x1800acec0  mov     rbx, rax
0x1800acec3  test    rdi, rdi
0x1800acec6  jz      short loc_1800ACEF2
0x1800acec8  test    rax, rax
0x1800acecb  jz      short loc_1800ACEF2
0x1800acecd  test    esi, esi
0x1800acecf  jz      short loc_1800ACEDB
0x1800aced1  mov     rcx, [rbp+phModule]; hLibModule
0x1800aced5  call    cs:__imp_FreeLibrary
0x1800acedb  mov     rax, rdi
0x1800acede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acee3  lea     rcx, ?D3D11On12CreateDeviceImpl@@YAJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IPEBQEAU1@IIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@Z; D3D11On12CreateDeviceImpl(IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,IUnknown * const *,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *)
0x1800aceea  mov     [rax], rcx
0x1800aceed  mov     rax, rbx
0x1800acef0  jmp     short loc_1800ACF03
0x1800acef2  mov     rcx, [rbp+phModule]; hLibModule
0x1800acef6  call    cs:__imp_FreeLibrary
0x1800acefc  lea     rax, ?D3D11On12CreateDeviceImpl@@YAJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IPEBQEAU1@IIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@Z; D3D11On12CreateDeviceImpl(IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,IUnknown * const *,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *)
0x1800acf03  add     rsp, 58h
0x1800acf07  pop     rdi
0x1800acf08  pop     rsi
0x1800acf09  pop     rbx
0x1800acf0a  pop     rbp
0x1800acf0b  retn
```

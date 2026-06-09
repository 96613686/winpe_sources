# DXCapture::IsCaptureEnabled<long (IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *)>(long (*)(IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *),char const *,char const *)

- ea: `0x180008070`
- end: `0x180008238`
- name: `??$IsCaptureEnabled@$$A6AJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@Z@DXCapture@@YAP6AJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@ZP6AJ0123@ZPEBD5@Z`
- size: `456`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008030`
- `0x18000e940`

## callees

- `0x180008070`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000811a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000812e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000811a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000812e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008152`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000822d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008152`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000822d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000821a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000821a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000809f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000809f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800080ba`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800080ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000816e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000816e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008205`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008205`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800081a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800081a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800081e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800081e4`

## string_xrefs

- `0x180008098`: `DXCaptureReplay.dll`
- `0x18000820e`: `DXCaptureReplay.dll`
- `0x180008124`: `D3D12CreateDeviceGenerated`
- `0x180008113`: `GetRealPtrPtrD3D12CreateDevice`

## pseudocode

```c
FARPROC __fastcall DXCapture::IsCaptureEnabled<long (IUnknown *,enum D3D_FEATURE_LEVEL,_GUID const &,void * *)>(__int64 a1, __int64 a2, __int64 a3)
{
  BOOL ModuleHandle; // r14d
  HANDLE v5; // rax
  HMODULE Library; // rax
  int (*ProcAddress)(void); // rax
  __int64 (*v9)(void); // rdi
  FARPROC v10; // rax
  FARPROC v11; // rbx
  int v12; // ebx
  HMODULE phModule; // [rsp+40h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-8h] BYREF
  __int64 pcbData; // [rsp+88h] [rbp+38h] BYREF
  __int64 pdwType; // [rsp+90h] [rbp+40h] BYREF
  int pvData; // [rsp+98h] [rbp+48h] BYREF

  pdwType = a3;
  pcbData = a2;
  phModule = 0;
  ModuleHandle = GetModuleHandleExW(0, L"DXCaptureReplay.dll", &phModule);
  if ( !ModuleHandle || (Library = phModule) == 0 )
  {
    v5 = OpenSemaphoreW(0x100000u, 0, L"DXEnableCapture");
    if ( v5 )
    {
      CloseHandle(v5);
      hkey = 0;
      v12 = 1;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DXTools", 0, 0x20019u, &hkey) )
      {
        LODWORD(pdwType) = 0;
        pvData = 0;
        LODWORD(pcbData) = 4;
        if ( !RegGetValueW(hkey, 0, L"LoadFromAnywhere", 0x10u, (LPDWORD)&pdwType, &pvData, (LPDWORD)&pcbData)
          && (_DWORD)pdwType == 4
          && (_DWORD)pcbData == 4 )
        {
          v12 = pvData == 0;
        }
        RegCloseKey(hkey);
      }
      Library = LoadLibraryExW(L"DXCaptureReplay.dll", 0, v12 << 11);
      phModule = Library;
    }
    else
    {
      Library = phModule;
    }
    if ( !Library )
      return (FARPROC)a1;
  }
  ProcAddress = (int (*)(void))GetProcAddress(Library, "LazyAttachToMonitor");
  if ( !ProcAddress
    || ProcAddress() < 0
    || (v9 = GetProcAddress(phModule, "GetRealPtrPtrD3D12CreateDevice"),
        v10 = GetProcAddress(phModule, "D3D12CreateDeviceGenerated"),
        v11 = v10,
        !v9)
    || !v10 )
  {
    FreeLibrary(phModule);
    return (FARPROC)a1;
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v9() = a1;
  return v11;
}

```

## disassembly

```asm
0x180008070  mov     [rsp-28h+pdwType], r8
0x180008075  mov     [rsp-28h+arg_8], rdx
0x18000807a  push    rbp
0x18000807b  push    rbx
0x18000807c  push    rsi
0x18000807d  push    rdi
0x18000807e  push    r14
0x180008080  mov     rbp, rsp
0x180008083  sub     rsp, 50h
0x180008087  mov     rsi, rcx
0x18000808a  mov     [rbp+phModule], 0
0x180008092  xor     ecx, ecx; dwFlags
0x180008094  lea     r8, [rbp+phModule]; phModule
0x180008098  lea     rdx, LibFileName; "DXCaptureReplay.dll"
0x18000809f  call    cs:__imp_GetModuleHandleExW
0x1800080a5  mov     r14d, eax
0x1800080a8  test    eax, eax
0x1800080aa  jnz     short loc_1800080E0
0x1800080ac  lea     r8, Name; "DXEnableCapture"
0x1800080b3  xor     edx, edx; bInheritHandle
0x1800080b5  mov     ecx, 100000h; dwDesiredAccess
0x1800080ba  call    cs:__imp_OpenSemaphoreW
0x1800080c0  test    rax, rax
0x1800080c3  jnz     loc_18000816B
0x1800080c9  mov     rax, [rbp+phModule]
0x1800080cd  test    rax, rax
0x1800080d0  jnz     short loc_1800080E9
0x1800080d2  mov     rax, rsi
0x1800080d5  add     rsp, 50h
0x1800080d9  pop     r14
0x1800080db  pop     rdi
0x1800080dc  pop     rsi
0x1800080dd  pop     rbx
0x1800080de  pop     rbp
0x1800080df  retn
0x1800080e0  mov     rax, [rbp+phModule]
0x1800080e4  test    rax, rax
0x1800080e7  jz      short loc_1800080AC
0x1800080e9  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x1800080f0  mov     rcx, rax; hModule
0x1800080f3  call    cs:__imp_GetProcAddress
0x1800080f9  test    rax, rax
0x1800080fc  jz      loc_180008229
0x180008102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008107  test    eax, eax
0x180008109  js      loc_180008229
0x18000810f  mov     rcx, [rbp+phModule]; hModule
0x180008113  lea     rdx, aGetrealptrptrd_0; "GetRealPtrPtrD3D12CreateDevice"
0x18000811a  call    cs:__imp_GetProcAddress
0x180008120  mov     rcx, [rbp+phModule]; hModule
0x180008124  lea     rdx, aD3d12createdev_0; "D3D12CreateDeviceGenerated"
0x18000812b  mov     rdi, rax
0x18000812e  call    cs:__imp_GetProcAddress
0x180008134  mov     rbx, rax
0x180008137  test    rdi, rdi
0x18000813a  jz      loc_180008229
0x180008140  test    rax, rax
0x180008143  jz      loc_180008229
0x180008149  test    r14d, r14d
0x18000814c  jz      short loc_180008158
0x18000814e  mov     rcx, [rbp+phModule]; hLibModule
0x180008152  call    cs:__imp_FreeLibrary
0x180008158  mov     rax, rdi
0x18000815b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008160  mov     [rax], rsi
0x180008163  mov     rax, rbx
0x180008166  jmp     loc_1800080D5
0x18000816b  mov     rcx, rax; hObject
0x18000816e  call    cs:__imp_CloseHandle
0x180008174  lea     rax, [rbp+hkey]
0x180008178  mov     [rbp+hkey], 0
0x180008180  mov     r9d, 20019h; samDesired
0x180008186  mov     [rsp+50h+phkResult], rax; phkResult
0x18000818b  xor     r8d, r8d; ulOptions
0x18000818e  lea     rdx, SubKey; "Software\\Microsoft\\DXTools"
0x180008195  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000819c  mov     ebx, 1
0x1800081a1  call    cs:__imp_RegOpenKeyExW
0x1800081a7  test    eax, eax
0x1800081a9  jnz     short loc_18000820B
0x1800081ab  mov     rcx, [rbp+hkey]; hkey
0x1800081af  lea     r9d, [rbx+0Fh]; dwFlags
0x1800081b3  mov     dword ptr [rbp+pdwType], eax
0x1800081b6  lea     r8, Value; "LoadFromAnywhere"
0x1800081bd  mov     [rbp+arg_18], eax
0x1800081c0  xor     edx, edx; lpSubKey
0x1800081c2  lea     rax, [rbp+arg_8]
0x1800081c6  mov     dword ptr [rbp+arg_8], 4
0x1800081cd  mov     [rsp+50h+pcbData], rax; pcbData
0x1800081d2  lea     rax, [rbp+arg_18]
0x1800081d6  mov     [rsp+50h+pvData], rax; pvData
0x1800081db  lea     rax, [rbp+pdwType]
0x1800081df  mov     [rsp+50h+phkResult], rax; pdwType
0x1800081e4  call    cs:__imp_RegGetValueW
0x1800081ea  test    eax, eax
0x1800081ec  jnz     short loc_180008201
0x1800081ee  cmp     dword ptr [rbp+pdwType], 4
0x1800081f2  jnz     short loc_180008201
0x1800081f4  cmp     dword ptr [rbp+arg_8], 4
0x1800081f8  jnz     short loc_180008201
0x1800081fa  cmp     [rbp+arg_18], eax
0x1800081fd  jz      short loc_180008201
0x1800081ff  xor     ebx, ebx
0x180008201  mov     rcx, [rbp+hkey]; hKey
0x180008205  call    cs:__imp_RegCloseKey
0x18000820b  shl     ebx, 0Bh
0x18000820e  lea     rcx, LibFileName; "DXCaptureReplay.dll"
0x180008215  mov     r8d, ebx; dwFlags
0x180008218  xor     edx, edx; hFile
0x18000821a  call    cs:__imp_LoadLibraryExW
0x180008220  mov     [rbp+phModule], rax
0x180008224  jmp     loc_1800080CD
0x180008229  mov     rcx, [rbp+phModule]; hLibModule
0x18000822d  call    cs:__imp_FreeLibrary
0x180008233  jmp     loc_1800080D2
```

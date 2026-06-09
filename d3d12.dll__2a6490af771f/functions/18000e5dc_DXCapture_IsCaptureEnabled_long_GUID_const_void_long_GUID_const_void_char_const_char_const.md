# DXCapture::IsCaptureEnabled<long (_GUID const &,void * *)>(long (*)(_GUID const &,void * *),char const *,char const *)

- ea: `0x18000e5dc`
- end: `0x18000e794`
- name: `??$IsCaptureEnabled@$$A6AJAEBU_GUID@@PEAPEAX@Z@DXCapture@@YAP6AJAEBU_GUID@@PEAPEAX@ZP6AJ01@ZPEBD3@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f2f0`

## callees

- `0x18000e5dc`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e70f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e72e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e742`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e70f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e72e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e742`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e75d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e77e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e75d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e77e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e6f0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e6f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000e60b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000e60b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e632`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e632`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e644`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e644`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e677`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e677`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e6ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e6ba`

## string_xrefs

- `0x18000e602`: `DXCaptureReplay.dll`
- `0x18000e6e4`: `DXCaptureReplay.dll`

## pseudocode

```c
__int64 (__fastcall *__fastcall DXCapture::IsCaptureEnabled<long (_GUID const &,void * *)>(
        __int64 a1,
        __int64 a2,
        __int64 a3))(const struct _GUID *, void **)
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
      return D3D12GetDebugInterfaceImpl;
  }
  ProcAddress = (int (*)(void))GetProcAddress(Library, "LazyAttachToMonitor");
  if ( !ProcAddress
    || ProcAddress() < 0
    || (v8 = GetProcAddress(phModule, "GetRealPtrPtrD3D12GetDebugInterface"),
        v9 = GetProcAddress(phModule, "D3D12GetDebugInterfaceGenerated"),
        v10 = v9,
        !v8)
    || !v9 )
  {
    FreeLibrary(phModule);
    return D3D12GetDebugInterfaceImpl;
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v8() = D3D12GetDebugInterfaceImpl;
  return (__int64 (__fastcall *)(const struct _GUID *, void **))v10;
}

```

## disassembly

```asm
0x18000e5dc  mov     [rsp-20h+pdwType], r8
0x18000e5e1  mov     [rsp-20h+arg_8], rdx
0x18000e5e6  mov     [rsp-20h+arg_0], rcx
0x18000e5eb  push    rbp
0x18000e5ec  push    rbx
0x18000e5ed  push    rsi
0x18000e5ee  push    rdi
0x18000e5ef  mov     rbp, rsp
0x18000e5f2  sub     rsp, 58h
0x18000e5f6  lea     r8, [rbp+phModule]; phModule
0x18000e5fa  mov     [rbp+phModule], 0
0x18000e602  lea     rdx, LibFileName; "DXCaptureReplay.dll"
0x18000e609  xor     ecx, ecx; dwFlags
0x18000e60b  call    cs:__imp_GetModuleHandleExW
0x18000e611  mov     esi, eax
0x18000e613  test    eax, eax
0x18000e615  jz      short loc_18000E624
0x18000e617  mov     rax, [rbp+phModule]
0x18000e61b  test    rax, rax
0x18000e61e  jnz     loc_18000E705
0x18000e624  lea     r8, Name; "DXEnableCapture"
0x18000e62b  xor     edx, edx; bInheritHandle
0x18000e62d  mov     ecx, 100000h; dwDesiredAccess
0x18000e632  call    cs:__imp_OpenSemaphoreW
0x18000e638  test    rax, rax
0x18000e63b  jz      loc_18000E6FC
0x18000e641  mov     rcx, rax; hObject
0x18000e644  call    cs:__imp_CloseHandle
0x18000e64a  lea     rax, [rbp+hkey]
0x18000e64e  mov     [rbp+hkey], 0
0x18000e656  mov     r9d, 20019h; samDesired
0x18000e65c  mov     [rsp+58h+phkResult], rax; phkResult
0x18000e661  xor     r8d, r8d; ulOptions
0x18000e664  lea     rdx, SubKey; "Software\\Microsoft\\DXTools"
0x18000e66b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e672  mov     ebx, 1
0x18000e677  call    cs:__imp_RegOpenKeyExW
0x18000e67d  test    eax, eax
0x18000e67f  jnz     short loc_18000E6E1
0x18000e681  mov     rcx, [rbp+hkey]; hkey
0x18000e685  lea     r9d, [rbx+0Fh]; dwFlags
0x18000e689  mov     dword ptr [rbp+pdwType], eax
0x18000e68c  lea     r8, Value; "LoadFromAnywhere"
0x18000e693  mov     dword ptr [rbp+arg_0], eax
0x18000e696  xor     edx, edx; lpSubKey
0x18000e698  lea     rax, [rbp+arg_8]
0x18000e69c  mov     dword ptr [rbp+arg_8], 4
0x18000e6a3  mov     [rsp+58h+pcbData], rax; pcbData
0x18000e6a8  lea     rax, [rbp+arg_0]
0x18000e6ac  mov     [rsp+58h+pvData], rax; pvData
0x18000e6b1  lea     rax, [rbp+pdwType]
0x18000e6b5  mov     [rsp+58h+phkResult], rax; pdwType
0x18000e6ba  call    cs:__imp_RegGetValueW
0x18000e6c0  test    eax, eax
0x18000e6c2  jnz     short loc_18000E6D7
0x18000e6c4  cmp     dword ptr [rbp+pdwType], 4
0x18000e6c8  jnz     short loc_18000E6D7
0x18000e6ca  cmp     dword ptr [rbp+arg_8], 4
0x18000e6ce  jnz     short loc_18000E6D7
0x18000e6d0  cmp     dword ptr [rbp+arg_0], eax
0x18000e6d3  jz      short loc_18000E6D7
0x18000e6d5  xor     ebx, ebx
0x18000e6d7  mov     rcx, [rbp+hkey]; hKey
0x18000e6db  call    cs:__imp_RegCloseKey
0x18000e6e1  shl     ebx, 0Bh
0x18000e6e4  lea     rcx, LibFileName; "DXCaptureReplay.dll"
0x18000e6eb  mov     r8d, ebx; dwFlags
0x18000e6ee  xor     edx, edx; hFile
0x18000e6f0  call    cs:__imp_LoadLibraryExW
0x18000e6f6  mov     [rbp+phModule], rax
0x18000e6fa  jmp     short loc_18000E700
0x18000e6fc  mov     rax, [rbp+phModule]
0x18000e700  test    rax, rax
0x18000e703  jz      short loc_18000E784
0x18000e705  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x18000e70c  mov     rcx, rax; hModule
0x18000e70f  call    cs:__imp_GetProcAddress
0x18000e715  test    rax, rax
0x18000e718  jz      short loc_18000E77A
0x18000e71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e71f  test    eax, eax
0x18000e721  js      short loc_18000E77A
0x18000e723  mov     rcx, [rbp+phModule]; hModule
0x18000e727  lea     rdx, aGetrealptrptrd; "GetRealPtrPtrD3D12GetDebugInterface"
0x18000e72e  call    cs:__imp_GetProcAddress
0x18000e734  mov     rcx, [rbp+phModule]; hModule
0x18000e738  lea     rdx, aD3d12getdebugi_0; "D3D12GetDebugInterfaceGenerated"
0x18000e73f  mov     rdi, rax
0x18000e742  call    cs:__imp_GetProcAddress
0x18000e748  mov     rbx, rax
0x18000e74b  test    rdi, rdi
0x18000e74e  jz      short loc_18000E77A
0x18000e750  test    rax, rax
0x18000e753  jz      short loc_18000E77A
0x18000e755  test    esi, esi
0x18000e757  jz      short loc_18000E763
0x18000e759  mov     rcx, [rbp+phModule]; hLibModule
0x18000e75d  call    cs:__imp_FreeLibrary
0x18000e763  mov     rax, rdi
0x18000e766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e76b  lea     rcx, ?D3D12GetDebugInterfaceImpl@@YAJAEBU_GUID@@PEAPEAX@Z; D3D12GetDebugInterfaceImpl(_GUID const &,void * *)
0x18000e772  mov     [rax], rcx
0x18000e775  mov     rax, rbx
0x18000e778  jmp     short loc_18000E78B
0x18000e77a  mov     rcx, [rbp+phModule]; hLibModule
0x18000e77e  call    cs:__imp_FreeLibrary
0x18000e784  lea     rax, ?D3D12GetDebugInterfaceImpl@@YAJAEBU_GUID@@PEAPEAX@Z; D3D12GetDebugInterfaceImpl(_GUID const &,void * *)
0x18000e78b  add     rsp, 58h
0x18000e78f  pop     rdi
0x18000e790  pop     rsi
0x18000e791  pop     rbx
0x18000e792  pop     rbp
0x18000e793  retn
```

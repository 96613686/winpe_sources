# DXCapture::IsCaptureEnabled<long (D2D1_FACTORY_TYPE,_GUID const &,D2D1_FACTORY_OPTIONS const *,void * *)>(long (*)(D2D1_FACTORY_TYPE,_GUID const &,D2D1_FACTORY_OPTIONS const *,void * *),char const *,char const *)

- ea: `0x1801aa268`
- end: `0x1801aa2eb`
- name: `??$IsCaptureEnabled@$$A6AJW4D2D1_FACTORY_TYPE@@AEBU_GUID@@PEBUD2D1_FACTORY_OPTIONS@@PEAPEAX@Z@DXCapture@@YAP6AJW4D2D1_FACTORY_TYPE@@AEBU_GUID@@PEBUD2D1_FACTORY_OPTIONS@@PEAPEAX@ZP6AJ0123@ZPEBD5@Z`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801aa230`

## callees

- `0x1801aa268`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180305b46`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180305b6a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180305b46`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180305b6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180305af8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180305b17`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180305b2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180305af8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180305b17`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180305b2b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180305adf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180305adf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1801aa297`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1801aa297`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1801aa2b1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1801aa2b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180305a33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180305a33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180305a66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180305a66`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180305aa9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180305aa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180305aca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180305aca`

## string_xrefs

- `0x1801aa28e`: `DXCaptureReplay.dll`
- `0x180305ad3`: `DXCaptureReplay.dll`
- `0x180305b21`: `D2D1CreateFactoryGenerated`
- `0x180305b10`: `GetRealPtrPtrD2D1CreateFactory`

## pseudocode

```c
__int64 (__fastcall *__fastcall DXCapture::IsCaptureEnabled<long (enum D2D1_FACTORY_TYPE,_GUID const &,D2D1_FACTORY_OPTIONS const *,void * *)>(
        __int64 a1,
        __int64 a2,
        __int64 a3))(enum D2D1_FACTORY_TYPE, const struct _GUID *, const struct D2D1_FACTORY_OPTIONS *, void **)
{
  BOOL ModuleHandle; // esi
  HANDLE v4; // rax
  HMODULE Library; // rax
  int v7; // ebx
  int (*ProcAddress)(void); // rax
  __int64 (*v9)(void); // rdi
  FARPROC v10; // rax
  FARPROC v11; // rbx
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
      v7 = 1;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DXTools", 0, 0x20019u, &hkey) )
      {
        LODWORD(pdwType) = 0;
        LODWORD(pvData) = 0;
        LODWORD(pcbData) = 4;
        if ( !RegGetValueW(hkey, 0, L"LoadFromAnywhere", 0x10u, (LPDWORD)&pdwType, &pvData, (LPDWORD)&pcbData)
          && (_DWORD)pdwType == 4
          && (_DWORD)pcbData == 4 )
        {
          v7 = pvData == 0;
        }
        RegCloseKey(hkey);
      }
      Library = LoadLibraryExW(L"DXCaptureReplay.dll", 0, v7 << 11);
      phModule = Library;
    }
    else
    {
      Library = phModule;
    }
    if ( !Library )
      return D2D1CreateFactoryImpl;
  }
  ProcAddress = (int (*)(void))GetProcAddress(Library, "LazyAttachToMonitor");
  if ( !ProcAddress
    || ProcAddress() < 0
    || (v9 = GetProcAddress(phModule, "GetRealPtrPtrD2D1CreateFactory"),
        v10 = GetProcAddress(phModule, "D2D1CreateFactoryGenerated"),
        v11 = v10,
        !v9)
    || !v10 )
  {
    FreeLibrary(phModule);
    return D2D1CreateFactoryImpl;
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v9() = D2D1CreateFactoryImpl;
  return (__int64 (__fastcall *)(enum D2D1_FACTORY_TYPE, const struct _GUID *, const struct D2D1_FACTORY_OPTIONS *, void **))v11;
}

```

## disassembly

```asm
0x1801aa268  mov     [rsp-20h+pdwType], r8
0x1801aa26d  mov     [rsp-20h+arg_8], rdx
0x1801aa272  mov     [rsp-20h+arg_0], rcx
0x1801aa277  push    rbp
0x1801aa278  push    rbx
0x1801aa279  push    rsi
0x1801aa27a  push    rdi
0x1801aa27b  mov     rbp, rsp
0x1801aa27e  sub     rsp, 58h
0x1801aa282  lea     r8, [rbp+phModule]; phModule
0x1801aa286  mov     [rbp+phModule], 0
0x1801aa28e  lea     rdx, ModuleName; "DXCaptureReplay.dll"
0x1801aa295  xor     ecx, ecx; dwFlags
0x1801aa297  call    cs:__imp_GetModuleHandleExW
0x1801aa29d  mov     esi, eax
0x1801aa29f  test    eax, eax
0x1801aa2a1  jnz     short loc_1801AA2DD
0x1801aa2a3  lea     r8, aDxenablecaptur; "DXEnableCapture"
0x1801aa2aa  xor     edx, edx; bInheritHandle
0x1801aa2ac  mov     ecx, 100000h; dwDesiredAccess
0x1801aa2b1  call    cs:__imp_OpenSemaphoreW
0x1801aa2b7  test    rax, rax
0x1801aa2ba  jnz     loc_180305A30
0x1801aa2c0  mov     rax, [rbp+phModule]
0x1801aa2c4  test    rax, rax
0x1801aa2c7  jnz     loc_180305AEE
0x1801aa2cd  lea     rax, ?D2D1CreateFactoryImpl@@YAJW4D2D1_FACTORY_TYPE@@AEBU_GUID@@PEBUD2D1_FACTORY_OPTIONS@@PEAPEAX@Z; D2D1CreateFactoryImpl(D2D1_FACTORY_TYPE,_GUID const &,D2D1_FACTORY_OPTIONS const *,void * *)
0x1801aa2d4  add     rsp, 58h
0x1801aa2d8  pop     rdi
0x1801aa2d9  pop     rsi
0x1801aa2da  pop     rbx
0x1801aa2db  pop     rbp
0x1801aa2dc  retn
0x1801aa2dd  mov     rax, [rbp+phModule]
0x1801aa2e1  test    rax, rax
0x1801aa2e4  jz      short loc_1801AA2A3
0x1801aa2e6  jmp     loc_180305AEE
0x180305a30  mov     rcx, rax; hObject
0x180305a33  call    cs:__imp_CloseHandle
0x180305a39  lea     rax, [rbp+hkey]
0x180305a3d  mov     [rbp+hkey], 0
0x180305a45  mov     r9d, 20019h; samDesired
0x180305a4b  mov     [rsp+58h+phkResult], rax; phkResult
0x180305a50  xor     r8d, r8d; ulOptions
0x180305a53  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\DXTools"
0x180305a5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180305a61  mov     ebx, 1
0x180305a66  call    cs:__imp_RegOpenKeyExW
0x180305a6c  test    eax, eax
0x180305a6e  jnz     short loc_180305AD0
0x180305a70  mov     rcx, [rbp+hkey]; hkey
0x180305a74  lea     r9d, [rbx+0Fh]; dwFlags
0x180305a78  mov     dword ptr [rbp+pdwType], eax
0x180305a7b  lea     r8, Value; "LoadFromAnywhere"
0x180305a82  mov     dword ptr [rbp+arg_0], eax
0x180305a85  xor     edx, edx; lpSubKey
0x180305a87  lea     rax, [rbp+arg_8]
0x180305a8b  mov     dword ptr [rbp+arg_8], 4
0x180305a92  mov     [rsp+58h+pcbData], rax; pcbData
0x180305a97  lea     rax, [rbp+arg_0]
0x180305a9b  mov     [rsp+58h+pvData], rax; pvData
0x180305aa0  lea     rax, [rbp+pdwType]
0x180305aa4  mov     [rsp+58h+phkResult], rax; pdwType
0x180305aa9  call    cs:__imp_RegGetValueW
0x180305aaf  test    eax, eax
0x180305ab1  jnz     short loc_180305AC6
0x180305ab3  cmp     dword ptr [rbp+pdwType], 4
0x180305ab7  jnz     short loc_180305AC6
0x180305ab9  cmp     dword ptr [rbp+arg_8], 4
0x180305abd  jnz     short loc_180305AC6
0x180305abf  cmp     dword ptr [rbp+arg_0], eax
0x180305ac2  jz      short loc_180305AC6
0x180305ac4  xor     ebx, ebx
0x180305ac6  mov     rcx, [rbp+hkey]; hKey
0x180305aca  call    cs:__imp_RegCloseKey
0x180305ad0  shl     ebx, 0Bh
0x180305ad3  lea     rcx, ModuleName; "DXCaptureReplay.dll"
0x180305ada  mov     r8d, ebx; dwFlags
0x180305add  xor     edx, edx; hFile
0x180305adf  call    cs:__imp_LoadLibraryExW
0x180305ae5  mov     [rbp+phModule], rax
0x180305ae9  jmp     loc_1801AA2C4
0x180305aee  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x180305af5  mov     rcx, rax; hModule
0x180305af8  call    cs:__imp_GetProcAddress
0x180305afe  test    rax, rax
0x180305b01  jz      short loc_180305B66
0x180305b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305b08  test    eax, eax
0x180305b0a  js      short loc_180305B66
0x180305b0c  mov     rcx, [rbp+phModule]; hModule
0x180305b10  lea     rdx, aGetrealptrptrd_1; "GetRealPtrPtrD2D1CreateFactory"
0x180305b17  call    cs:__imp_GetProcAddress
0x180305b1d  mov     rcx, [rbp+phModule]; hModule
0x180305b21  lea     rdx, aD2d1createfact_0; "D2D1CreateFactoryGenerated"
0x180305b28  mov     rdi, rax
0x180305b2b  call    cs:__imp_GetProcAddress
0x180305b31  mov     rbx, rax
0x180305b34  test    rdi, rdi
0x180305b37  jz      short loc_180305B66
0x180305b39  test    rax, rax
0x180305b3c  jz      short loc_180305B66
0x180305b3e  test    esi, esi
0x180305b40  jz      short loc_180305B4C
0x180305b42  mov     rcx, [rbp+phModule]; hLibModule
0x180305b46  call    cs:__imp_FreeLibrary
0x180305b4c  mov     rax, rdi
0x180305b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305b54  lea     rcx, ?D2D1CreateFactoryImpl@@YAJW4D2D1_FACTORY_TYPE@@AEBU_GUID@@PEBUD2D1_FACTORY_OPTIONS@@PEAPEAX@Z; D2D1CreateFactoryImpl(D2D1_FACTORY_TYPE,_GUID const &,D2D1_FACTORY_OPTIONS const *,void * *)
0x180305b5b  mov     [rax], rcx
0x180305b5e  mov     rax, rbx
0x180305b61  jmp     loc_1801AA2D4
0x180305b66  mov     rcx, [rbp+phModule]; hLibModule
0x180305b6a  call    cs:__imp_FreeLibrary
0x180305b70  nop
0x180305b71  jmp     loc_1801AA2CD
```

# DXCapture::IsCaptureEnabled<long (IDXGISurface *,D2D1_CREATION_PROPERTIES const *,ID2D1DeviceContext * *)>(long (*)(IDXGISurface *,D2D1_CREATION_PROPERTIES const *,ID2D1DeviceContext * *),char const *,char const *)

- ea: `0x180260228`
- end: `0x1802603e0`
- name: `??$IsCaptureEnabled@$$A6AJPEAUIDXGISurface@@PEBUD2D1_CREATION_PROPERTIES@@PEAPEAUID2D1DeviceContext@@@Z@DXCapture@@YAP6AJPEAUIDXGISurface@@PEBUD2D1_CREATION_PROPERTIES@@PEAPEAUID2D1DeviceContext@@@ZP6AJ012@ZPEBD4@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802604e0`

## callees

- `0x180260228`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802603a9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802603ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802603a9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802603ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18026035b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18026037a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18026038e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18026035b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18026037a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18026038e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18026033c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18026033c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180260257`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180260257`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18026027e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18026027e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180260290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180260290`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802602c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802602c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180260306`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180260306`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180260327`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180260327`

## string_xrefs

- `0x18026024e`: `DXCaptureReplay.dll`
- `0x180260330`: `DXCaptureReplay.dll`
- `0x180260384`: `D2D1CreateDeviceContextGenerated`
- `0x180260373`: `GetRealPtrPtrD2D1CreateDeviceContext`

## pseudocode

```c
int (*__fastcall DXCapture::IsCaptureEnabled<long (IDXGISurface *,D2D1_CREATION_PROPERTIES const *,ID2D1DeviceContext * *)>(
        __int64 a1,
        __int64 a2,
        __int64 a3))(struct IDXGISurface *, const struct D2D1_CREATION_PROPERTIES *, struct ID2D1DeviceContext **)
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
      return D2D1CreateDeviceContextImpl;
  }
  ProcAddress = (int (*)(void))GetProcAddress(Library, "LazyAttachToMonitor");
  if ( !ProcAddress
    || ProcAddress() < 0
    || (v8 = GetProcAddress(phModule, "GetRealPtrPtrD2D1CreateDeviceContext"),
        v9 = GetProcAddress(phModule, "D2D1CreateDeviceContextGenerated"),
        v10 = v9,
        !v8)
    || !v9 )
  {
    FreeLibrary(phModule);
    return D2D1CreateDeviceContextImpl;
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v8() = D2D1CreateDeviceContextImpl;
  return (int (*)(struct IDXGISurface *, const struct D2D1_CREATION_PROPERTIES *, struct ID2D1DeviceContext **))v10;
}

```

## disassembly

```asm
0x180260228  mov     [rsp-20h+pdwType], r8
0x18026022d  mov     [rsp-20h+arg_8], rdx
0x180260232  mov     [rsp-20h+arg_0], rcx
0x180260237  push    rbp
0x180260238  push    rbx
0x180260239  push    rsi
0x18026023a  push    rdi
0x18026023b  mov     rbp, rsp
0x18026023e  sub     rsp, 58h
0x180260242  lea     r8, [rbp+phModule]; phModule
0x180260246  mov     [rbp+phModule], 0
0x18026024e  lea     rdx, ModuleName; "DXCaptureReplay.dll"
0x180260255  xor     ecx, ecx; dwFlags
0x180260257  call    cs:__imp_GetModuleHandleExW
0x18026025d  mov     esi, eax
0x18026025f  test    eax, eax
0x180260261  jz      short loc_180260270
0x180260263  mov     rax, [rbp+phModule]
0x180260267  test    rax, rax
0x18026026a  jnz     loc_180260351
0x180260270  lea     r8, aDxenablecaptur; "DXEnableCapture"
0x180260277  xor     edx, edx; bInheritHandle
0x180260279  mov     ecx, 100000h; dwDesiredAccess
0x18026027e  call    cs:__imp_OpenSemaphoreW
0x180260284  test    rax, rax
0x180260287  jz      loc_180260348
0x18026028d  mov     rcx, rax; hObject
0x180260290  call    cs:__imp_CloseHandle
0x180260296  lea     rax, [rbp+hkey]
0x18026029a  mov     [rbp+hkey], 0
0x1802602a2  mov     r9d, 20019h; samDesired
0x1802602a8  mov     [rsp+58h+phkResult], rax; phkResult
0x1802602ad  xor     r8d, r8d; ulOptions
0x1802602b0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\DXTools"
0x1802602b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802602be  mov     ebx, 1
0x1802602c3  call    cs:__imp_RegOpenKeyExW
0x1802602c9  test    eax, eax
0x1802602cb  jnz     short loc_18026032D
0x1802602cd  mov     rcx, [rbp+hkey]; hkey
0x1802602d1  lea     r9d, [rbx+0Fh]; dwFlags
0x1802602d5  mov     dword ptr [rbp+pdwType], eax
0x1802602d8  lea     r8, Value; "LoadFromAnywhere"
0x1802602df  mov     dword ptr [rbp+arg_0], eax
0x1802602e2  xor     edx, edx; lpSubKey
0x1802602e4  lea     rax, [rbp+arg_8]
0x1802602e8  mov     dword ptr [rbp+arg_8], 4
0x1802602ef  mov     [rsp+58h+pcbData], rax; pcbData
0x1802602f4  lea     rax, [rbp+arg_0]
0x1802602f8  mov     [rsp+58h+pvData], rax; pvData
0x1802602fd  lea     rax, [rbp+pdwType]
0x180260301  mov     [rsp+58h+phkResult], rax; pdwType
0x180260306  call    cs:__imp_RegGetValueW
0x18026030c  test    eax, eax
0x18026030e  jnz     short loc_180260323
0x180260310  cmp     dword ptr [rbp+pdwType], 4
0x180260314  jnz     short loc_180260323
0x180260316  cmp     dword ptr [rbp+arg_8], 4
0x18026031a  jnz     short loc_180260323
0x18026031c  cmp     dword ptr [rbp+arg_0], eax
0x18026031f  jz      short loc_180260323
0x180260321  xor     ebx, ebx
0x180260323  mov     rcx, [rbp+hkey]; hKey
0x180260327  call    cs:__imp_RegCloseKey
0x18026032d  shl     ebx, 0Bh
0x180260330  lea     rcx, ModuleName; "DXCaptureReplay.dll"
0x180260337  mov     r8d, ebx; dwFlags
0x18026033a  xor     edx, edx; hFile
0x18026033c  call    cs:__imp_LoadLibraryExW
0x180260342  mov     [rbp+phModule], rax
0x180260346  jmp     short loc_18026034C
0x180260348  mov     rax, [rbp+phModule]
0x18026034c  test    rax, rax
0x18026034f  jz      short loc_1802603D0
0x180260351  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x180260358  mov     rcx, rax; hModule
0x18026035b  call    cs:__imp_GetProcAddress
0x180260361  test    rax, rax
0x180260364  jz      short loc_1802603C6
0x180260366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026036b  test    eax, eax
0x18026036d  js      short loc_1802603C6
0x18026036f  mov     rcx, [rbp+phModule]; hModule
0x180260373  lea     rdx, aGetrealptrptrd; "GetRealPtrPtrD2D1CreateDeviceContext"
0x18026037a  call    cs:__imp_GetProcAddress
0x180260380  mov     rcx, [rbp+phModule]; hModule
0x180260384  lea     rdx, aD2d1createdevi_1; "D2D1CreateDeviceContextGenerated"
0x18026038b  mov     rdi, rax
0x18026038e  call    cs:__imp_GetProcAddress
0x180260394  mov     rbx, rax
0x180260397  test    rdi, rdi
0x18026039a  jz      short loc_1802603C6
0x18026039c  test    rax, rax
0x18026039f  jz      short loc_1802603C6
0x1802603a1  test    esi, esi
0x1802603a3  jz      short loc_1802603AF
0x1802603a5  mov     rcx, [rbp+phModule]; hLibModule
0x1802603a9  call    cs:__imp_FreeLibrary
0x1802603af  mov     rax, rdi
0x1802603b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802603b7  lea     rcx, ?D2D1CreateDeviceContextImpl@@YAJPEAUIDXGISurface@@PEBUD2D1_CREATION_PROPERTIES@@PEAPEAUID2D1DeviceContext@@@Z; D2D1CreateDeviceContextImpl(IDXGISurface *,D2D1_CREATION_PROPERTIES const *,ID2D1DeviceContext * *)
0x1802603be  mov     [rax], rcx
0x1802603c1  mov     rax, rbx
0x1802603c4  jmp     short loc_1802603D7
0x1802603c6  mov     rcx, [rbp+phModule]; hLibModule
0x1802603ca  call    cs:__imp_FreeLibrary
0x1802603d0  lea     rax, ?D2D1CreateDeviceContextImpl@@YAJPEAUIDXGISurface@@PEBUD2D1_CREATION_PROPERTIES@@PEAPEAUID2D1DeviceContext@@@Z; D2D1CreateDeviceContextImpl(IDXGISurface *,D2D1_CREATION_PROPERTIES const *,ID2D1DeviceContext * *)
0x1802603d7  add     rsp, 58h
0x1802603db  pop     rdi
0x1802603dc  pop     rsi
0x1802603dd  pop     rbx
0x1802603de  pop     rbp
0x1802603df  retn
```

# DXCapture::IsCaptureEnabled<long (IDXGIDevice *,D2D1_CREATION_PROPERTIES const *,ID2D1Device * *)>(long (*)(IDXGIDevice *,D2D1_CREATION_PROPERTIES const *,ID2D1Device * *),char const *,char const *)

- ea: `0x180260068`
- end: `0x180260220`
- name: `??$IsCaptureEnabled@$$A6AJPEAUIDXGIDevice@@PEBUD2D1_CREATION_PROPERTIES@@PEAPEAUID2D1Device@@@Z@DXCapture@@YAP6AJPEAUIDXGIDevice@@PEBUD2D1_CREATION_PROPERTIES@@PEAPEAUID2D1Device@@@ZP6AJ012@ZPEBD4@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802594f0`

## callees

- `0x180260068`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802601e9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18026020a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802601e9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18026020a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18026019b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802601ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802601ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18026019b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802601ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802601ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18026017c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18026017c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180260097`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180260097`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1802600be`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1802600be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802600d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802600d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180260103`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180260103`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180260146`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180260146`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180260167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180260167`

## string_xrefs

- `0x18026008e`: `DXCaptureReplay.dll`
- `0x180260170`: `DXCaptureReplay.dll`
- `0x1802601c4`: `D2D1CreateDeviceGenerated`
- `0x1802601b3`: `GetRealPtrPtrD2D1CreateDevice`

## pseudocode

```c
__int64 (__fastcall *__fastcall DXCapture::IsCaptureEnabled<long (IDXGIDevice *,D2D1_CREATION_PROPERTIES const *,ID2D1Device * *)>(
        __int64 a1,
        __int64 a2,
        __int64 a3))(struct IDXGIDevice *, const struct D2D1_CREATION_PROPERTIES *, struct ID2D1Device **)
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
      return D2D1CreateDeviceImpl;
  }
  ProcAddress = (int (*)(void))GetProcAddress(Library, "LazyAttachToMonitor");
  if ( !ProcAddress
    || ProcAddress() < 0
    || (v8 = GetProcAddress(phModule, "GetRealPtrPtrD2D1CreateDevice"),
        v9 = GetProcAddress(phModule, "D2D1CreateDeviceGenerated"),
        v10 = v9,
        !v8)
    || !v9 )
  {
    FreeLibrary(phModule);
    return D2D1CreateDeviceImpl;
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v8() = D2D1CreateDeviceImpl;
  return (__int64 (__fastcall *)(struct IDXGIDevice *, const struct D2D1_CREATION_PROPERTIES *, struct ID2D1Device **))v10;
}

```

## disassembly

```asm
0x180260068  mov     [rsp-20h+pdwType], r8
0x18026006d  mov     [rsp-20h+arg_8], rdx
0x180260072  mov     [rsp-20h+arg_0], rcx
0x180260077  push    rbp
0x180260078  push    rbx
0x180260079  push    rsi
0x18026007a  push    rdi
0x18026007b  mov     rbp, rsp
0x18026007e  sub     rsp, 58h
0x180260082  lea     r8, [rbp+phModule]; phModule
0x180260086  mov     [rbp+phModule], 0
0x18026008e  lea     rdx, ModuleName; "DXCaptureReplay.dll"
0x180260095  xor     ecx, ecx; dwFlags
0x180260097  call    cs:__imp_GetModuleHandleExW
0x18026009d  mov     esi, eax
0x18026009f  test    eax, eax
0x1802600a1  jz      short loc_1802600B0
0x1802600a3  mov     rax, [rbp+phModule]
0x1802600a7  test    rax, rax
0x1802600aa  jnz     loc_180260191
0x1802600b0  lea     r8, aDxenablecaptur; "DXEnableCapture"
0x1802600b7  xor     edx, edx; bInheritHandle
0x1802600b9  mov     ecx, 100000h; dwDesiredAccess
0x1802600be  call    cs:__imp_OpenSemaphoreW
0x1802600c4  test    rax, rax
0x1802600c7  jz      loc_180260188
0x1802600cd  mov     rcx, rax; hObject
0x1802600d0  call    cs:__imp_CloseHandle
0x1802600d6  lea     rax, [rbp+hkey]
0x1802600da  mov     [rbp+hkey], 0
0x1802600e2  mov     r9d, 20019h; samDesired
0x1802600e8  mov     [rsp+58h+phkResult], rax; phkResult
0x1802600ed  xor     r8d, r8d; ulOptions
0x1802600f0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\DXTools"
0x1802600f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802600fe  mov     ebx, 1
0x180260103  call    cs:__imp_RegOpenKeyExW
0x180260109  test    eax, eax
0x18026010b  jnz     short loc_18026016D
0x18026010d  mov     rcx, [rbp+hkey]; hkey
0x180260111  lea     r9d, [rbx+0Fh]; dwFlags
0x180260115  mov     dword ptr [rbp+pdwType], eax
0x180260118  lea     r8, Value; "LoadFromAnywhere"
0x18026011f  mov     dword ptr [rbp+arg_0], eax
0x180260122  xor     edx, edx; lpSubKey
0x180260124  lea     rax, [rbp+arg_8]
0x180260128  mov     dword ptr [rbp+arg_8], 4
0x18026012f  mov     [rsp+58h+pcbData], rax; pcbData
0x180260134  lea     rax, [rbp+arg_0]
0x180260138  mov     [rsp+58h+pvData], rax; pvData
0x18026013d  lea     rax, [rbp+pdwType]
0x180260141  mov     [rsp+58h+phkResult], rax; pdwType
0x180260146  call    cs:__imp_RegGetValueW
0x18026014c  test    eax, eax
0x18026014e  jnz     short loc_180260163
0x180260150  cmp     dword ptr [rbp+pdwType], 4
0x180260154  jnz     short loc_180260163
0x180260156  cmp     dword ptr [rbp+arg_8], 4
0x18026015a  jnz     short loc_180260163
0x18026015c  cmp     dword ptr [rbp+arg_0], eax
0x18026015f  jz      short loc_180260163
0x180260161  xor     ebx, ebx
0x180260163  mov     rcx, [rbp+hkey]; hKey
0x180260167  call    cs:__imp_RegCloseKey
0x18026016d  shl     ebx, 0Bh
0x180260170  lea     rcx, ModuleName; "DXCaptureReplay.dll"
0x180260177  mov     r8d, ebx; dwFlags
0x18026017a  xor     edx, edx; hFile
0x18026017c  call    cs:__imp_LoadLibraryExW
0x180260182  mov     [rbp+phModule], rax
0x180260186  jmp     short loc_18026018C
0x180260188  mov     rax, [rbp+phModule]
0x18026018c  test    rax, rax
0x18026018f  jz      short loc_180260210
0x180260191  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x180260198  mov     rcx, rax; hModule
0x18026019b  call    cs:__imp_GetProcAddress
0x1802601a1  test    rax, rax
0x1802601a4  jz      short loc_180260206
0x1802601a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802601ab  test    eax, eax
0x1802601ad  js      short loc_180260206
0x1802601af  mov     rcx, [rbp+phModule]; hModule
0x1802601b3  lea     rdx, aGetrealptrptrd_0; "GetRealPtrPtrD2D1CreateDevice"
0x1802601ba  call    cs:__imp_GetProcAddress
0x1802601c0  mov     rcx, [rbp+phModule]; hModule
0x1802601c4  lea     rdx, aD2d1createdevi_2; "D2D1CreateDeviceGenerated"
0x1802601cb  mov     rdi, rax
0x1802601ce  call    cs:__imp_GetProcAddress
0x1802601d4  mov     rbx, rax
0x1802601d7  test    rdi, rdi
0x1802601da  jz      short loc_180260206
0x1802601dc  test    rax, rax
0x1802601df  jz      short loc_180260206
0x1802601e1  test    esi, esi
0x1802601e3  jz      short loc_1802601EF
0x1802601e5  mov     rcx, [rbp+phModule]; hLibModule
0x1802601e9  call    cs:__imp_FreeLibrary
0x1802601ef  mov     rax, rdi
0x1802601f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802601f7  lea     rcx, ?D2D1CreateDeviceImpl@@YAJPEAUIDXGIDevice@@PEBUD2D1_CREATION_PROPERTIES@@PEAPEAUID2D1Device@@@Z; D2D1CreateDeviceImpl(IDXGIDevice *,D2D1_CREATION_PROPERTIES const *,ID2D1Device * *)
0x1802601fe  mov     [rax], rcx
0x180260201  mov     rax, rbx
0x180260204  jmp     short loc_180260217
0x180260206  mov     rcx, [rbp+phModule]; hLibModule
0x18026020a  call    cs:__imp_FreeLibrary
0x180260210  lea     rax, ?D2D1CreateDeviceImpl@@YAJPEAUIDXGIDevice@@PEBUD2D1_CREATION_PROPERTIES@@PEAPEAUID2D1Device@@@Z; D2D1CreateDeviceImpl(IDXGIDevice *,D2D1_CREATION_PROPERTIES const *,ID2D1Device * *)
0x180260217  add     rsp, 58h
0x18026021b  pop     rdi
0x18026021c  pop     rsi
0x18026021d  pop     rbx
0x18026021e  pop     rbp
0x18026021f  retn
```

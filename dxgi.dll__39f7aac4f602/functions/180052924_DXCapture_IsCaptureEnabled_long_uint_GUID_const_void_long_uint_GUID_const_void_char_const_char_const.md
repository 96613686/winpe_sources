# DXCapture::IsCaptureEnabled<long (uint,_GUID const &,void * *)>(long (*)(uint,_GUID const &,void * *),char const *,char const *)

- ea: `0x180052924`
- end: `0x180052ae5`
- name: `??$IsCaptureEnabled@$$A6AJIAEBU_GUID@@PEAPEAX@Z@DXCapture@@YAP6AJIAEBU_GUID@@PEAPEAX@ZP6AJI01@ZPEBD3@Z`
- size: `449`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800528d0`
- `0x1800938c0`

## callees

- `0x180052924`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180052952`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180052952`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800529a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800529cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800529db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800529a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800529cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800529db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180052ac7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180052ac7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800529ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052ada`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800529ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052ada`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005296d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005296d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052a1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052a1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180052a91`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180052a91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052ab2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052ab2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052a4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052a4e`

## string_xrefs

- `0x180052949`: `DXCaptureReplay.dll`
- `0x180052abb`: `DXCaptureReplay.dll`

## pseudocode

```c
FARPROC __fastcall DXCapture::IsCaptureEnabled<long (unsigned int,_GUID const &,void * *)>(__int64 a1, const CHAR *a2, const CHAR *a3)
{
  BOOL ModuleHandle; // r14d
  HANDLE v7; // rax
  HMODULE Library; // rax
  int (*ProcAddress)(void); // rax
  __int64 (*v11)(void); // rdi
  FARPROC v12; // rax
  FARPROC v13; // rbx
  int v14; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-28h] BYREF
  int pvData; // [rsp+44h] [rbp-24h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-20h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-18h] BYREF
  DWORD pdwType; // [rsp+B8h] [rbp+50h] BYREF

  phModule = 0;
  ModuleHandle = GetModuleHandleExW(0, L"DXCaptureReplay.dll", &phModule);
  if ( !ModuleHandle || (Library = phModule) == 0 )
  {
    v7 = OpenSemaphoreW(0x100000u, 0, L"DXEnableCapture");
    if ( v7 )
    {
      CloseHandle(v7);
      hkey = 0;
      v14 = 1;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DXTools", 0, 0x20019u, &hkey) )
      {
        pdwType = 0;
        pvData = 0;
        pcbData = 4;
        if ( !RegGetValueW(hkey, 0, L"LoadFromAnywhere", 0x10u, &pdwType, &pvData, &pcbData)
          && pdwType == 4
          && pcbData == 4 )
        {
          v14 = pvData == 0;
        }
        RegCloseKey(hkey);
      }
      Library = LoadLibraryExW(L"DXCaptureReplay.dll", 0, v14 << 11);
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
    || (v11 = GetProcAddress(phModule, a2), v12 = GetProcAddress(phModule, a3), v13 = v12, !v11)
    || !v12 )
  {
    FreeLibrary(phModule);
    return (FARPROC)a1;
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v11() = a1;
  return v13;
}

```

## disassembly

```asm
0x180052924  push    rbp
0x180052926  push    rbx
0x180052927  push    rsi
0x180052928  push    rdi
0x180052929  push    r14
0x18005292b  push    r15
0x18005292d  mov     rbp, rsp
0x180052930  sub     rsp, 68h
0x180052934  mov     r15, r8
0x180052937  mov     [rbp+phModule], 0
0x18005293f  mov     rdi, rdx
0x180052942  lea     r8, [rbp+phModule]; phModule
0x180052946  mov     rsi, rcx
0x180052949  lea     rdx, aDxcapturerepla; "DXCaptureReplay.dll"
0x180052950  xor     ecx, ecx; dwFlags
0x180052952  call    cs:__imp_GetModuleHandleExW
0x180052958  mov     r14d, eax
0x18005295b  test    eax, eax
0x18005295d  jnz     short loc_180052995
0x18005295f  lea     r8, Name; "DXEnableCapture"
0x180052966  xor     edx, edx; bInheritHandle
0x180052968  mov     ecx, 100000h; dwDesiredAccess
0x18005296d  call    cs:__imp_OpenSemaphoreW
0x180052973  test    rax, rax
0x180052976  jnz     loc_180052A18
0x18005297c  mov     rax, [rbp+phModule]
0x180052980  test    rax, rax
0x180052983  jnz     short loc_18005299E
0x180052985  mov     rax, rsi
0x180052988  add     rsp, 68h
0x18005298c  pop     r15
0x18005298e  pop     r14
0x180052990  pop     rdi
0x180052991  pop     rsi
0x180052992  pop     rbx
0x180052993  pop     rbp
0x180052994  retn
0x180052995  mov     rax, [rbp+phModule]
0x180052999  test    rax, rax
0x18005299c  jz      short loc_18005295F
0x18005299e  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x1800529a5  mov     rcx, rax; hModule
0x1800529a8  call    cs:__imp_GetProcAddress
0x1800529ae  test    rax, rax
0x1800529b1  jz      loc_180052AD6
0x1800529b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529bc  test    eax, eax
0x1800529be  js      loc_180052AD6
0x1800529c4  mov     rcx, [rbp+phModule]; hModule
0x1800529c8  mov     rdx, rdi; lpProcName
0x1800529cb  call    cs:__imp_GetProcAddress
0x1800529d1  mov     rcx, [rbp+phModule]; hModule
0x1800529d5  mov     rdx, r15; lpProcName
0x1800529d8  mov     rdi, rax
0x1800529db  call    cs:__imp_GetProcAddress
0x1800529e1  mov     rbx, rax
0x1800529e4  test    rdi, rdi
0x1800529e7  jz      loc_180052AD6
0x1800529ed  test    rax, rax
0x1800529f0  jz      loc_180052AD6
0x1800529f6  test    r14d, r14d
0x1800529f9  jz      short loc_180052A05
0x1800529fb  mov     rcx, [rbp+phModule]; hLibModule
0x1800529ff  call    cs:__imp_FreeLibrary
0x180052a05  mov     rax, rdi
0x180052a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a0d  mov     [rax], rsi
0x180052a10  mov     rax, rbx
0x180052a13  jmp     loc_180052988
0x180052a18  mov     rcx, rax; hObject
0x180052a1b  call    cs:__imp_CloseHandle
0x180052a21  lea     rax, [rbp+hkey]
0x180052a25  mov     [rbp+hkey], 0
0x180052a2d  mov     r9d, 20019h; samDesired
0x180052a33  mov     [rsp+68h+phkResult], rax; phkResult
0x180052a38  xor     r8d, r8d; ulOptions
0x180052a3b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\DXTools"
0x180052a42  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052a49  mov     ebx, 1
0x180052a4e  call    cs:__imp_RegOpenKeyExW
0x180052a54  test    eax, eax
0x180052a56  jnz     short loc_180052AB8
0x180052a58  mov     rcx, [rbp+hkey]; hkey
0x180052a5c  lea     r9d, [rbx+0Fh]; dwFlags
0x180052a60  mov     [rbp+pdwType], eax
0x180052a63  lea     r8, Value; "LoadFromAnywhere"
0x180052a6a  mov     [rbp+var_24], eax
0x180052a6d  xor     edx, edx; lpSubKey
0x180052a6f  lea     rax, [rbp+var_28]
0x180052a73  mov     [rbp+var_28], 4
0x180052a7a  mov     [rsp+68h+pcbData], rax; pcbData
0x180052a7f  lea     rax, [rbp+var_24]
0x180052a83  mov     [rsp+68h+pvData], rax; pvData
0x180052a88  lea     rax, [rbp+pdwType]
0x180052a8c  mov     [rsp+68h+phkResult], rax; pdwType
0x180052a91  call    cs:__imp_RegGetValueW
0x180052a97  test    eax, eax
0x180052a99  jnz     short loc_180052AAE
0x180052a9b  cmp     [rbp+pdwType], 4
0x180052a9f  jnz     short loc_180052AAE
0x180052aa1  cmp     [rbp+var_28], 4
0x180052aa5  jnz     short loc_180052AAE
0x180052aa7  cmp     [rbp+var_24], eax
0x180052aaa  jz      short loc_180052AAE
0x180052aac  xor     ebx, ebx
0x180052aae  mov     rcx, [rbp+hkey]; hKey
0x180052ab2  call    cs:__imp_RegCloseKey
0x180052ab8  shl     ebx, 0Bh
0x180052abb  lea     rcx, aDxcapturerepla; "DXCaptureReplay.dll"
0x180052ac2  mov     r8d, ebx; dwFlags
0x180052ac5  xor     edx, edx; hFile
0x180052ac7  call    cs:__imp_LoadLibraryExW
0x180052acd  mov     [rbp+phModule], rax
0x180052ad1  jmp     loc_180052980
0x180052ad6  mov     rcx, [rbp+phModule]; hLibModule
0x180052ada  call    cs:__imp_FreeLibrary
0x180052ae0  jmp     loc_180052985
```

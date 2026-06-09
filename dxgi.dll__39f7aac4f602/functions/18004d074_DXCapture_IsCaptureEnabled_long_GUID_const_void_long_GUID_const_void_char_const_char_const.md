# DXCapture::IsCaptureEnabled<long (_GUID const &,void * *)>(long (*)(_GUID const &,void * *),char const *,char const *)

- ea: `0x18004d074`
- end: `0x18004d222`
- name: `??$IsCaptureEnabled@$$A6AJAEBU_GUID@@PEAPEAX@Z@DXCapture@@YAP6AJAEBU_GUID@@PEAPEAX@ZP6AJ01@ZPEBD3@Z`
- size: `430`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004cde0`
- `0x18004cf10`

## callees

- `0x18004d074`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18004d0a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18004d0a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d0f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d113`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d123`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d0f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d113`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004d123`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004d213`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004d213`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004d13f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004d159`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004d13f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004d159`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004d0bd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004d0bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d167`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d167`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004d1dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004d1dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d1fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d1fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d19a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d19a`

## string_xrefs

- `0x18004d099`: `DXCaptureReplay.dll`
- `0x18004d207`: `DXCaptureReplay.dll`

## pseudocode

```c
FARPROC __fastcall DXCapture::IsCaptureEnabled<long (_GUID const &,void * *)>(__int64 a1, const CHAR *a2, const CHAR *a3)
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
0x18004d074  push    rbp
0x18004d076  push    rbx
0x18004d077  push    rsi
0x18004d078  push    rdi
0x18004d079  push    r14
0x18004d07b  push    r15
0x18004d07d  mov     rbp, rsp
0x18004d080  sub     rsp, 68h
0x18004d084  mov     r15, r8
0x18004d087  mov     [rbp+phModule], 0
0x18004d08f  mov     rdi, rdx
0x18004d092  lea     r8, [rbp+phModule]; phModule
0x18004d096  mov     rsi, rcx
0x18004d099  lea     rdx, aDxcapturerepla; "DXCaptureReplay.dll"
0x18004d0a0  xor     ecx, ecx; dwFlags
0x18004d0a2  call    cs:__imp_GetModuleHandleExW
0x18004d0a8  mov     r14d, eax
0x18004d0ab  test    eax, eax
0x18004d0ad  jnz     short loc_18004D0E5
0x18004d0af  lea     r8, Name; "DXEnableCapture"
0x18004d0b6  xor     edx, edx; bInheritHandle
0x18004d0b8  mov     ecx, 100000h; dwDesiredAccess
0x18004d0bd  call    cs:__imp_OpenSemaphoreW
0x18004d0c3  test    rax, rax
0x18004d0c6  jnz     loc_18004D164
0x18004d0cc  mov     rax, [rbp+phModule]
0x18004d0d0  test    rax, rax
0x18004d0d3  jnz     short loc_18004D0EE
0x18004d0d5  mov     rax, rsi
0x18004d0d8  add     rsp, 68h
0x18004d0dc  pop     r15
0x18004d0de  pop     r14
0x18004d0e0  pop     rdi
0x18004d0e1  pop     rsi
0x18004d0e2  pop     rbx
0x18004d0e3  pop     rbp
0x18004d0e4  retn
0x18004d0e5  mov     rax, [rbp+phModule]
0x18004d0e9  test    rax, rax
0x18004d0ec  jz      short loc_18004D0AF
0x18004d0ee  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x18004d0f5  mov     rcx, rax; hModule
0x18004d0f8  call    cs:__imp_GetProcAddress
0x18004d0fe  test    rax, rax
0x18004d101  jz      short loc_18004D155
0x18004d103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d108  test    eax, eax
0x18004d10a  js      short loc_18004D155
0x18004d10c  mov     rcx, [rbp+phModule]; hModule
0x18004d110  mov     rdx, rdi; lpProcName
0x18004d113  call    cs:__imp_GetProcAddress
0x18004d119  mov     rcx, [rbp+phModule]; hModule
0x18004d11d  mov     rdx, r15; lpProcName
0x18004d120  mov     rdi, rax
0x18004d123  call    cs:__imp_GetProcAddress
0x18004d129  mov     rbx, rax
0x18004d12c  test    rdi, rdi
0x18004d12f  jz      short loc_18004D155
0x18004d131  test    rax, rax
0x18004d134  jz      short loc_18004D155
0x18004d136  test    r14d, r14d
0x18004d139  jz      short loc_18004D145
0x18004d13b  mov     rcx, [rbp+phModule]; hLibModule
0x18004d13f  call    cs:__imp_FreeLibrary
0x18004d145  mov     rax, rdi
0x18004d148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d14d  mov     [rax], rsi
0x18004d150  mov     rax, rbx
0x18004d153  jmp     short loc_18004D0D8
0x18004d155  mov     rcx, [rbp+phModule]; hLibModule
0x18004d159  call    cs:__imp_FreeLibrary
0x18004d15f  jmp     loc_18004D0D5
0x18004d164  mov     rcx, rax; hObject
0x18004d167  call    cs:__imp_CloseHandle
0x18004d16d  lea     rax, [rbp+hkey]
0x18004d171  mov     [rbp+hkey], 0
0x18004d179  mov     r9d, 20019h; samDesired
0x18004d17f  mov     [rsp+68h+phkResult], rax; phkResult
0x18004d184  xor     r8d, r8d; ulOptions
0x18004d187  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\DXTools"
0x18004d18e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004d195  mov     ebx, 1
0x18004d19a  call    cs:__imp_RegOpenKeyExW
0x18004d1a0  test    eax, eax
0x18004d1a2  jnz     short loc_18004D204
0x18004d1a4  mov     rcx, [rbp+hkey]; hkey
0x18004d1a8  lea     r9d, [rbx+0Fh]; dwFlags
0x18004d1ac  mov     [rbp+pdwType], eax
0x18004d1af  lea     r8, Value; "LoadFromAnywhere"
0x18004d1b6  mov     [rbp+var_24], eax
0x18004d1b9  xor     edx, edx; lpSubKey
0x18004d1bb  lea     rax, [rbp+var_28]
0x18004d1bf  mov     [rbp+var_28], 4
0x18004d1c6  mov     [rsp+68h+pcbData], rax; pcbData
0x18004d1cb  lea     rax, [rbp+var_24]
0x18004d1cf  mov     [rsp+68h+pvData], rax; pvData
0x18004d1d4  lea     rax, [rbp+pdwType]
0x18004d1d8  mov     [rsp+68h+phkResult], rax; pdwType
0x18004d1dd  call    cs:__imp_RegGetValueW
0x18004d1e3  test    eax, eax
0x18004d1e5  jnz     short loc_18004D1FA
0x18004d1e7  cmp     [rbp+pdwType], 4
0x18004d1eb  jnz     short loc_18004D1FA
0x18004d1ed  cmp     [rbp+var_28], 4
0x18004d1f1  jnz     short loc_18004D1FA
0x18004d1f3  cmp     [rbp+var_24], eax
0x18004d1f6  jz      short loc_18004D1FA
0x18004d1f8  xor     ebx, ebx
0x18004d1fa  mov     rcx, [rbp+hkey]; hKey
0x18004d1fe  call    cs:__imp_RegCloseKey
0x18004d204  shl     ebx, 0Bh
0x18004d207  lea     rcx, aDxcapturerepla; "DXCaptureReplay.dll"
0x18004d20e  mov     r8d, ebx; dwFlags
0x18004d211  xor     edx, edx; hFile
0x18004d213  call    cs:__imp_LoadLibraryExW
0x18004d219  mov     [rbp+phModule], rax
0x18004d21d  jmp     loc_18004D0D0
```

# DWriteCreateFactory

- ea: `0x180159950`
- end: `0x1801599f2`
- name: `DWriteCreateFactory`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004671c`
- `0x180159838`
- `0x1801e6ff8`

## callees

- `0x180159950`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1803002ac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1803002cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1803002ac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1803002cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18030025e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18030027d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180300291`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18030025e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18030027d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180300291`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180300245`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180300245`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180159982`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180159982`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18015999c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18015999c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180300199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180300199`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1803001cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1803001cc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18030020f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18030020f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180300230`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180300230`

## string_xrefs

- `0x180159979`: `DXCaptureReplay.dll`
- `0x180300239`: `DXCaptureReplay.dll`
- `0x180300276`: `GetRealPtrPtrDWriteCreateFactory`
- `0x180300287`: `DWriteCreateFactoryGenerated`

## pseudocode

```c
__int64 __fastcall DWriteCreateFactory(DWORD a1, __int64 a2, __int64 a3)
{
  BOOL ModuleHandle; // esi
  HANDLE v6; // rax
  HMODULE Library; // rax
  FARPROC v8; // rbx
  int v10; // ebx
  int (*ProcAddress)(void); // rax
  __int64 (*v12)(void); // rdi
  FARPROC v13; // rax
  int pvData; // [rsp+40h] [rbp-20h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-18h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-10h] BYREF
  DWORD pdwType; // [rsp+90h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+A8h] [rbp+48h] BYREF

  pdwType = a1;
  phModule = 0;
  ModuleHandle = GetModuleHandleExW(0, L"DXCaptureReplay.dll", &phModule);
  if ( !ModuleHandle || (Library = phModule) == 0 )
  {
    v6 = OpenSemaphoreW(0x100000u, 0, L"DXEnableCapture");
    if ( v6 )
    {
      CloseHandle(v6);
      hkey = 0;
      v10 = 1;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DXTools", 0, 0x20019u, &hkey) )
      {
        pdwType = 0;
        pvData = 0;
        pcbData = 4;
        if ( !RegGetValueW(hkey, 0, L"LoadFromAnywhere", 0x10u, &pdwType, &pvData, &pcbData)
          && pdwType == 4
          && pcbData == 4 )
        {
          v10 = pvData == 0;
        }
        RegCloseKey(hkey);
      }
      Library = LoadLibraryExW(L"DXCaptureReplay.dll", 0, v10 << 11);
      phModule = Library;
    }
    else
    {
      Library = phModule;
    }
    if ( !Library )
      goto LABEL_5;
  }
  ProcAddress = (int (*)(void))GetProcAddress(Library, "LazyAttachToMonitor");
  if ( !ProcAddress
    || ProcAddress() < 0
    || (v12 = GetProcAddress(phModule, "GetRealPtrPtrDWriteCreateFactory"),
        v13 = GetProcAddress(phModule, "DWriteCreateFactoryGenerated"),
        v8 = v13,
        !v12)
    || !v13 )
  {
    FreeLibrary(phModule);
LABEL_5:
    v8 = (FARPROC)&DWriteCreateFactoryImpl;
    return ((__int64 (__fastcall *)(_QWORD, __int64, __int64))v8)(0, a2, a3);
  }
  if ( ModuleHandle )
    FreeLibrary(phModule);
  *(_QWORD *)v12() = &DWriteCreateFactoryImpl;
  return ((__int64 (__fastcall *)(_QWORD, __int64, __int64))v8)(0, a2, a3);
}

```

## disassembly

```asm
0x180159950  mov     [rsp-28h+arg_8], rbx
0x180159955  mov     [rsp-28h+pdwType], ecx
0x180159959  push    rbp
0x18015995a  push    rsi
0x18015995b  push    rdi
0x18015995c  push    r14
0x18015995e  push    r15
0x180159960  mov     rbp, rsp
0x180159963  sub     rsp, 60h
0x180159967  mov     r14, r8
0x18015996a  mov     [rbp+phModule], 0
0x180159972  mov     r15, rdx
0x180159975  lea     r8, [rbp+phModule]; phModule
0x180159979  lea     rdx, ModuleName; "DXCaptureReplay.dll"
0x180159980  xor     ecx, ecx; dwFlags
0x180159982  call    cs:__imp_GetModuleHandleExW
0x180159988  mov     esi, eax
0x18015998a  test    eax, eax
0x18015998c  jnz     short loc_1801599E3
0x18015998e  lea     r8, aDxenablecaptur; "DXEnableCapture"
0x180159995  xor     edx, edx; bInheritHandle
0x180159997  mov     ecx, 100000h; dwDesiredAccess
0x18015999c  call    cs:__imp_OpenSemaphoreW
0x1801599a2  test    rax, rax
0x1801599a5  jnz     loc_180300196
0x1801599ab  mov     rax, [rbp+phModule]
0x1801599af  test    rax, rax
0x1801599b2  jnz     loc_180300254
0x1801599b8  lea     rbx, ?DWriteCreateFactoryImpl@@YAJW4DWRITE_FACTORY_TYPE@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; DWriteCreateFactoryImpl(DWRITE_FACTORY_TYPE,_GUID const &,IUnknown * *)
0x1801599bf  mov     r8, r14
0x1801599c2  mov     rdx, r15
0x1801599c5  xor     ecx, ecx
0x1801599c7  mov     rax, rbx
0x1801599ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801599cf  mov     rbx, [rsp+60h+arg_8]
0x1801599d7  add     rsp, 60h
0x1801599db  pop     r15
0x1801599dd  pop     r14
0x1801599df  pop     rdi
0x1801599e0  pop     rsi
0x1801599e1  pop     rbp
0x1801599e2  retn
0x1801599e3  mov     rax, [rbp+phModule]
0x1801599e7  test    rax, rax
0x1801599ea  jnz     loc_180300254
0x1801599f0  jmp     short loc_18015998E
0x180300196  mov     rcx, rax; hObject
0x180300199  call    cs:__imp_CloseHandle
0x18030019f  lea     rax, [rbp+hkey]
0x1803001a3  mov     [rbp+hkey], 0
0x1803001ab  mov     r9d, 20019h; samDesired
0x1803001b1  mov     [rsp+60h+phkResult], rax; phkResult
0x1803001b6  xor     r8d, r8d; ulOptions
0x1803001b9  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\DXTools"
0x1803001c0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1803001c7  mov     ebx, 1
0x1803001cc  call    cs:__imp_RegOpenKeyExW
0x1803001d2  test    eax, eax
0x1803001d4  jnz     short loc_180300236
0x1803001d6  mov     rcx, [rbp+hkey]; hkey
0x1803001da  lea     r9d, [rbx+0Fh]; dwFlags
0x1803001de  mov     [rbp+pdwType], eax
0x1803001e1  lea     r8, Value; "LoadFromAnywhere"
0x1803001e8  mov     [rbp+var_20], eax
0x1803001eb  xor     edx, edx; lpSubKey
0x1803001ed  lea     rax, [rbp+arg_18]
0x1803001f1  mov     [rbp+arg_18], 4
0x1803001f8  mov     [rsp+60h+pcbData], rax; pcbData
0x1803001fd  lea     rax, [rbp+var_20]
0x180300201  mov     [rsp+60h+pvData], rax; pvData
0x180300206  lea     rax, [rbp+pdwType]
0x18030020a  mov     [rsp+60h+phkResult], rax; pdwType
0x18030020f  call    cs:__imp_RegGetValueW
0x180300215  test    eax, eax
0x180300217  jnz     short loc_18030022C
0x180300219  cmp     [rbp+pdwType], 4
0x18030021d  jnz     short loc_18030022C
0x18030021f  cmp     [rbp+arg_18], 4
0x180300223  jnz     short loc_18030022C
0x180300225  cmp     [rbp+var_20], eax
0x180300228  jz      short loc_18030022C
0x18030022a  xor     ebx, ebx
0x18030022c  mov     rcx, [rbp+hkey]; hKey
0x180300230  call    cs:__imp_RegCloseKey
0x180300236  shl     ebx, 0Bh
0x180300239  lea     rcx, ModuleName; "DXCaptureReplay.dll"
0x180300240  mov     r8d, ebx; dwFlags
0x180300243  xor     edx, edx; hFile
0x180300245  call    cs:__imp_LoadLibraryExW
0x18030024b  mov     [rbp+phModule], rax
0x18030024f  jmp     loc_1801599AF
0x180300254  lea     rdx, aLazyattachtomo; "LazyAttachToMonitor"
0x18030025b  mov     rcx, rax; hModule
0x18030025e  call    cs:__imp_GetProcAddress
0x180300264  test    rax, rax
0x180300267  jz      short loc_1803002C9
0x180300269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030026e  test    eax, eax
0x180300270  js      short loc_1803002C9
0x180300272  mov     rcx, [rbp+phModule]; hModule
0x180300276  lea     rdx, aGetrealptrptrd_2; "GetRealPtrPtrDWriteCreateFactory"
0x18030027d  call    cs:__imp_GetProcAddress
0x180300283  mov     rcx, [rbp+phModule]; hModule
0x180300287  lea     rdx, aDwritecreatefa; "DWriteCreateFactoryGenerated"
0x18030028e  mov     rdi, rax
0x180300291  call    cs:__imp_GetProcAddress
0x180300297  mov     rbx, rax
0x18030029a  test    rdi, rdi
0x18030029d  jz      short loc_1803002C9
0x18030029f  test    rax, rax
0x1803002a2  jz      short loc_1803002C9
0x1803002a4  test    esi, esi
0x1803002a6  jz      short loc_1803002B2
0x1803002a8  mov     rcx, [rbp+phModule]; hLibModule
0x1803002ac  call    cs:__imp_FreeLibrary
0x1803002b2  mov     rax, rdi
0x1803002b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803002ba  lea     rcx, ?DWriteCreateFactoryImpl@@YAJW4DWRITE_FACTORY_TYPE@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; DWriteCreateFactoryImpl(DWRITE_FACTORY_TYPE,_GUID const &,IUnknown * *)
0x1803002c1  mov     [rax], rcx
0x1803002c4  jmp     loc_1801599BF
0x1803002c9  mov     rcx, [rbp+phModule]; hLibModule
0x1803002cd  call    cs:__imp_FreeLibrary
0x1803002d3  nop
0x1803002d4  jmp     loc_1801599B8
```

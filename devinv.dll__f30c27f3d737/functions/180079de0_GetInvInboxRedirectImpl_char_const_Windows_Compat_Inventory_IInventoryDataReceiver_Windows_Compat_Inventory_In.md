# GetInvInboxRedirectImpl(char const *,Windows::Compat::Inventory::IInventoryDataReceiver *,Windows::Compat::Inventory::InventoryControlParams *,char const *)

- ea: `0x180079de0`
- end: `0x18007a10c`
- name: `?GetInvInboxRedirectImpl@@YAJPEBDPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAUInventoryControlParams@234@0@Z`
- size: `812`
- prototype: `__int64 __fastcall(LPCSTR lpProcName, struct Windows::Compat::Inventory::IInventoryDataReceiver *, struct Windows::Compat::Inventory::InventoryControlParams *, const char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a500`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x18000dbc8`
- `0x180066c10`
- `0x180066d20`
- `0x180079d30`
- `0x180079de0`
- `0x18007a120`
- `0x18007a5cc`
- `0x180116010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180079fb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180079fb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180079f24`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180079f24`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180079ee4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180079ee4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180079ffe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180079ffe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a084`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a084`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a016`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a08c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a0b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a08c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a0b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180079e63`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180079e63`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180079f4c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180079f4c`

## string_xrefs

- `0x18007a0c5`: `GetSystemDirectory failed %#x`
- `0x180079e8a`: `GetInvModuleInPath failed %#x`
- `0x180079faa`: `aeinv.dll`

## pseudocode

```c
__int64 __fastcall GetInvInboxRedirectImpl(
        LPCSTR lpProcName,
        struct Windows::Compat::Inventory::IInventoryDataReceiver *a2,
        struct Windows::Compat::Inventory::InventoryControlParams *a3,
        const char *a4)
{
  int InvModuleInPath; // eax
  unsigned __int64 v8; // rdx
  unsigned int v9; // ebx
  int v10; // eax
  signed int v11; // eax
  const char *v12; // r9
  __int64 v13; // r8
  DWORD ModuleFileNameW; // eax
  const unsigned __int16 *FileNameW; // rdi
  unsigned __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  unsigned int v19; // ebx
  HMODULE Library; // rax
  HMODULE v21; // rsi
  FARPROC ProcAddress; // r14
  signed int v23; // eax
  signed int LastError; // eax
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v27; // [rsp+34h] [rbp-CCh] BYREF
  int v28; // [rsp+38h] [rbp-C8h] BYREF
  HMODULE phModule; // [rsp+40h] [rbp-C0h] BYREF
  const char *v30; // [rsp+48h] [rbp-B8h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+260h] [rbp+160h] BYREF

  v30 = a4;
  memset_0(Filename, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  v26 = 0;
  v28 = 0;
  v27 = 0;
  phModule = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v12 = "GetSystemDirectory failed %#x";
    v13 = 171;
    goto LABEL_36;
  }
  InvModuleInPath = GetInvModuleInPath(Buffer);
  v9 = InvModuleInPath;
  if ( InvModuleInPath < 0 )
  {
    AslLogCallPrintf(1, "GetInvInboxRedirectImpl", 178, "GetInvModuleInPath failed %#x", InvModuleInPath);
    return v9;
  }
  if ( !InvModuleInPath )
    return 1;
  v10 = StringCchCatW(Buffer, v8, L"\\");
  v9 = v10;
  if ( v10 < 0 )
  {
    AslLogCallPrintf(1, "GetInvInboxRedirectImpl", 194, "StringCchCat failed %#x", v10);
    return v9;
  }
  if ( !GetModuleHandleExW(6u, (LPCWSTR)GetInvInboxRedirectImpl, &phModule) )
  {
    v11 = GetLastError();
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    v12 = "GetModuleHandleEx failed %#x";
    v13 = 201;
LABEL_36:
    AslLogCallPrintf(1, "GetInvInboxRedirectImpl", v13, v12, v9);
    return v9;
  }
  ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW >= 0x104 && GetLastError() == 122 )
  {
    v23 = GetLastError();
    v9 = v23;
    if ( v23 > 0 )
      v9 = (unsigned __int16)v23 | 0x80070000;
    v12 = "GetModuleFileName failed %#x";
    v13 = 210;
    goto LABEL_36;
  }
  FileNameW = PathFindFileNameW(Filename);
  v17 = StringCchCatW(Buffer, v16, FileNameW);
  v9 = v17;
  if ( v17 < 0 )
  {
    AslLogCallPrintf(1, "GetInvInboxRedirectImpl", 219, "StringCchCat failed %#x", v17);
    return v9;
  }
  if ( (int)AslFileGetVersionForPath(&v26, &v28, &v27, Buffer) < 0 )
    return 1;
  if ( v26 != 10 )
    return 1;
  v18 = _o__wcsicmp(FileNameW, L"aeinv.dll");
  v19 = v27;
  if ( !v18 && (v27 - 15157 <= 0x468 || v27 - 16350 <= 9 || v27 - 18895 <= 0x24) )
    return 1;
  Library = LoadLibraryExW(Buffer, 0, 0x800u);
  v21 = Library;
  if ( !Library )
    return 1;
  ProcAddress = GetProcAddress(Library, lpProcName);
  if ( ProcAddress )
  {
    v9 = ShouldRedirectProceed(FileNameW, v19);
    if ( !v9 )
    {
      v9 = ((__int64 (__fastcall *)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, struct Windows::Compat::Inventory::InventoryControlParams *, const char *))ProcAddress)(
             a2,
             a3,
             v30);
      ClearAbortRedirect(FileNameW);
      if ( (v9 & 0x80000000) != 0 )
        AslLogCallPrintf(1, "GetInvInboxRedirectImpl", 288, "%s failed %#x", lpProcName, v9);
    }
  }
  else
  {
    v9 = 1;
  }
  FreeLibrary(v21);
  return v9;
}

```

## disassembly

```asm
0x180079de0  push    rbp
0x180079de2  push    rbx
0x180079de3  push    rsi
0x180079de4  push    rdi
0x180079de5  push    r12
0x180079de7  push    r13
0x180079de9  push    r14
0x180079deb  push    r15
0x180079ded  lea     rbp, [rsp-388h]
0x180079df5  sub     rsp, 488h
0x180079dfc  mov     rax, cs:__security_cookie
0x180079e03  xor     rax, rsp
0x180079e06  mov     [rbp+3C0h+var_50], rax
0x180079e0d  mov     r13, r8
0x180079e10  mov     [rsp+4C0h+var_478], r9
0x180079e15  mov     r12, rdx
0x180079e18  mov     r15, rcx
0x180079e1b  mov     ebx, 208h
0x180079e20  lea     rcx, [rbp+3C0h+Filename]; void *
0x180079e27  mov     r8d, ebx; Size
0x180079e2a  xor     edx, edx; Val
0x180079e2c  call    memset_0
0x180079e31  mov     r8d, ebx; Size
0x180079e34  lea     rcx, [rsp+4C0h+Buffer]; void *
0x180079e39  xor     edx, edx; Val
0x180079e3b  call    memset_0
0x180079e40  xor     r14d, r14d
0x180079e43  lea     rcx, [rsp+4C0h+Buffer]; lpBuffer
0x180079e48  mov     edi, 104h
0x180079e4d  mov     [rsp+4C0h+var_490], r14d
0x180079e52  mov     edx, edi; uSize
0x180079e54  mov     [rsp+4C0h+var_488], r14d
0x180079e59  mov     [rsp+4C0h+var_48C], r14d
0x180079e5e  mov     [rsp+4C0h+phModule], r14
0x180079e63  call    cs:__imp_GetSystemDirectoryW
0x180079e69  dec     eax
0x180079e6b  cmp     eax, 102h
0x180079e70  ja      loc_18007A0B0
0x180079e76  lea     rcx, [rsp+4C0h+Buffer]; pszFile2
0x180079e7b  call    ?GetInvModuleInPath@@YAJPEBG@Z; GetInvModuleInPath(ushort const *)
0x180079e80  mov     ebx, eax
0x180079e82  test    eax, eax
0x180079e84  jns     short loc_180079E9A
0x180079e86  mov     dword ptr [rsp+4C0h+var_4A0], eax
0x180079e8a  lea     r9, aGetinvmodulein; "GetInvModuleInPath failed %#x"
0x180079e91  lea     r8d, [rdi-52h]
0x180079e95  jmp     loc_18007A0D6
0x180079e9a  jnz     short loc_180079EA6
0x180079e9c  mov     ebx, 1
0x180079ea1  jmp     loc_18007A0E7
0x180079ea6  lea     r8, SubBlock; "\\"
0x180079ead  lea     rcx, [rsp+4C0h+Buffer]; unsigned __int16 *
0x180079eb2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180079eb7  mov     ebx, eax
0x180079eb9  test    eax, eax
0x180079ebb  jns     short loc_180079ED3
0x180079ebd  mov     dword ptr [rsp+4C0h+var_4A0], eax
0x180079ec1  lea     r9, aStringcchcatFa; "StringCchCat failed %#x"
0x180079ec8  mov     r8d, 0C2h
0x180079ece  jmp     loc_18007A0D6
0x180079ed3  lea     r8, [rsp+4C0h+phModule]; phModule
0x180079ed8  mov     ecx, 6; dwFlags
0x180079edd  lea     rdx, ?GetInvInboxRedirectImpl@@YAJPEBDPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAUInventoryControlParams@234@0@Z; lpModuleName
0x180079ee4  call    cs:__imp_GetModuleHandleExW
0x180079eea  test    eax, eax
0x180079eec  jnz     short loc_180079F15
0x180079eee  call    cs:__imp_GetLastError
0x180079ef4  mov     ebx, eax
0x180079ef6  test    eax, eax
0x180079ef8  jle     short loc_180079F03
0x180079efa  movzx   ebx, ax
0x180079efd  or      ebx, 80070000h
0x180079f03  lea     r9, aGetmodulehandl_0; "GetModuleHandleEx failed %#x"
0x180079f0a  mov     r8d, 0C9h
0x180079f10  jmp     loc_18007A0D2
0x180079f15  mov     rcx, [rsp+4C0h+phModule]; hModule
0x180079f1a  lea     rdx, [rbp+3C0h+Filename]; lpFilename
0x180079f21  mov     r8d, edi; nSize
0x180079f24  call    cs:__imp_GetModuleFileNameW
0x180079f2a  test    eax, eax
0x180079f2c  jz      loc_18007A08C
0x180079f32  cmp     eax, edi
0x180079f34  jb      short loc_180079F45
0x180079f36  call    cs:__imp_GetLastError
0x180079f3c  cmp     eax, 7Ah ; 'z'
0x180079f3f  jz      loc_18007A08C
0x180079f45  lea     rcx, [rbp+3C0h+Filename]; pszPath
0x180079f4c  call    cs:__imp_PathFindFileNameW
0x180079f52  mov     r8, rax; unsigned __int16 *
0x180079f55  lea     rcx, [rsp+4C0h+Buffer]; unsigned __int16 *
0x180079f5a  mov     rdi, rax
0x180079f5d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180079f62  mov     ebx, eax
0x180079f64  test    eax, eax
0x180079f66  jns     short loc_180079F7E
0x180079f68  mov     dword ptr [rsp+4C0h+var_4A0], eax
0x180079f6c  lea     r9, aStringcchcatFa; "StringCchCat failed %#x"
0x180079f73  mov     r8d, 0DBh
0x180079f79  jmp     loc_18007A0D6
0x180079f7e  lea     r9, [rsp+4C0h+Buffer]
0x180079f83  lea     r8, [rsp+4C0h+var_48C]
0x180079f88  lea     rdx, [rsp+4C0h+var_488]
0x180079f8d  lea     rcx, [rsp+4C0h+var_490]
0x180079f92  call    AslFileGetVersionForPath
0x180079f97  test    eax, eax
0x180079f99  js      loc_180079E9C
0x180079f9f  cmp     [rsp+4C0h+var_490], 0Ah
0x180079fa4  jnz     loc_180079E9C
0x180079faa  lea     rdx, aAeinvDll; "aeinv.dll"
0x180079fb1  mov     rcx, rdi
0x180079fb4  call    cs:__imp__o__wcsicmp
0x180079fba  mov     ebx, [rsp+4C0h+var_48C]
0x180079fbe  test    eax, eax
0x180079fc0  jnz     short loc_180079FF1
0x180079fc2  lea     eax, [rbx-3B35h]
0x180079fc8  cmp     eax, 468h
0x180079fcd  jbe     loc_180079E9C
0x180079fd3  lea     eax, [rbx-3FDEh]
0x180079fd9  cmp     eax, 9
0x180079fdc  jbe     loc_180079E9C
0x180079fe2  lea     eax, [rbx-49CFh]
0x180079fe8  cmp     eax, 24h ; '$'
0x180079feb  jbe     loc_180079E9C
0x180079ff1  xor     edx, edx; hFile
0x180079ff3  lea     rcx, [rsp+4C0h+Buffer]; lpLibFileName
0x180079ff8  mov     r8d, 800h; dwFlags
0x180079ffe  call    cs:__imp_LoadLibraryExW
0x18007a004  mov     rsi, rax
0x18007a007  test    rax, rax
0x18007a00a  jz      loc_180079E9C
0x18007a010  mov     rdx, r15; lpProcName
0x18007a013  mov     rcx, rax; hModule
0x18007a016  call    cs:__imp_GetProcAddress
0x18007a01c  mov     r14, rax
0x18007a01f  test    rax, rax
0x18007a022  jnz     short loc_18007A029
0x18007a024  lea     ebx, [rax+1]
0x18007a027  jmp     short loc_18007A081
0x18007a029  mov     edx, ebx; unsigned int
0x18007a02b  mov     rcx, rdi; unsigned __int16 *
0x18007a02e  call    ?ShouldRedirectProceed@@YAJPEBGK@Z; ShouldRedirectProceed(ushort const *,ulong)
0x18007a033  mov     ebx, eax
0x18007a035  test    eax, eax
0x18007a037  jnz     short loc_18007A081
0x18007a039  mov     r8, [rsp+4C0h+var_478]
0x18007a03e  mov     rdx, r13
0x18007a041  mov     rcx, r12
0x18007a044  mov     rax, r14
0x18007a047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a04c  mov     rcx, rdi; unsigned __int16 *
0x18007a04f  mov     ebx, eax
0x18007a051  call    ?ClearAbortRedirect@@YAXPEBG@Z; ClearAbortRedirect(ushort const *)
0x18007a056  test    ebx, ebx
0x18007a058  jns     short loc_18007A081
0x18007a05a  mov     [rsp+4C0h+var_498], ebx
0x18007a05e  lea     r9, aSFailedX; "%s failed %#x"
0x18007a065  mov     r8d, 120h
0x18007a06b  mov     [rsp+4C0h+var_4A0], r15
0x18007a070  lea     rdx, aGetinvinboxred; "GetInvInboxRedirectImpl"
0x18007a077  mov     ecx, 1
0x18007a07c  call    AslLogCallPrintf
0x18007a081  mov     rcx, rsi; hLibModule
0x18007a084  call    cs:__imp_FreeLibrary
0x18007a08a  jmp     short loc_18007A0E7
0x18007a08c  call    cs:__imp_GetLastError
0x18007a092  mov     ebx, eax
0x18007a094  test    eax, eax
0x18007a096  jle     short loc_18007A0A1
0x18007a098  movzx   ebx, ax
0x18007a09b  or      ebx, 80070000h
0x18007a0a1  lea     r9, aGetmodulefilen; "GetModuleFileName failed %#x"
0x18007a0a8  mov     r8d, 0D2h
0x18007a0ae  jmp     short loc_18007A0D2
0x18007a0b0  call    cs:__imp_GetLastError
0x18007a0b6  mov     ebx, eax
0x18007a0b8  test    eax, eax
0x18007a0ba  jle     short loc_18007A0C5
0x18007a0bc  movzx   ebx, ax
0x18007a0bf  or      ebx, 80070000h
0x18007a0c5  lea     r9, aGetsystemdirec_0; "GetSystemDirectory failed %#x"
0x18007a0cc  mov     r8d, 0ABh
0x18007a0d2  mov     dword ptr [rsp+4C0h+var_4A0], ebx
0x18007a0d6  lea     rdx, aGetinvinboxred; "GetInvInboxRedirectImpl"
0x18007a0dd  mov     ecx, 1
0x18007a0e2  call    AslLogCallPrintf
0x18007a0e7  mov     eax, ebx
0x18007a0e9  mov     rcx, [rbp+3C0h+var_50]
0x18007a0f0  xor     rcx, rsp; StackCookie
0x18007a0f3  call    __security_check_cookie
0x18007a0f8  add     rsp, 488h
0x18007a0ff  pop     r15
0x18007a101  pop     r14
0x18007a103  pop     r13
0x18007a105  pop     r12
0x18007a107  pop     rdi
0x18007a108  pop     rsi
0x18007a109  pop     rbx
0x18007a10a  pop     rbp
0x18007a10b  retn
```

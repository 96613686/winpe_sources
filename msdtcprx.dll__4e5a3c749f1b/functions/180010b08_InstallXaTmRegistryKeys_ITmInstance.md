# InstallXaTmRegistryKeys(ITmInstance *)

- ea: `0x180010b08`
- end: `0x180010d82`
- name: `?InstallXaTmRegistryKeys@@YAJPEAUITmInstance@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(struct ITmInstance *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047dc8`
- `0x180051b40`

## callees

- `0x18000fe94`
- `0x180010b08`
- `0x18001156c`
- `0x180011ac0`
- `0x18002f534`
- `0x180081d9e`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180010cab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180010cab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010cd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010cd3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010d34`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d04`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180010c24`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180010c31`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180010cbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180010c24`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180010c31`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180010cbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180010c5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180010c5e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180010bea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180010bea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c1c`

## string_xrefs

- `0x180010ced`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180010d4f`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180010bca`: `Software\Microsoft\MSDTC\XADLL`
- `0x180010b72`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180010d1c`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180010d56`: `Failed to load MTXOCI.dll`
- `0x180010d23`: `GetProcAccess for MTXOCI!DllRegisterServer failed`
- `0x180010b69`: `InstallXaTmRegistryKeys, pTmInstance->GetContactId failed`
- `0x180010b9c`: `InstallXaTm: failed to install the XATmSecurityKey.`
- `0x180010c09`: `Failed To create  XATM DLL key`
- `0x180010c78`: `%s\mtxoci.dll`
- `0x180010c95`: `Failed to create mtxoci.dll full path`
- `0x180010cc9`: `DllRegisterServer`
- `0x180010cf4`: `Error while calling MTXOCI!DllRegisterServer`

## pseudocode

```c
__int64 __fastcall InstallXaTmRegistryKeys(struct ITmInstance *a1)
{
  __int64 v1; // rax
  __int64 (__fastcall *v3)(struct ITmInstance *, const WCHAR *, struct _GUID *); // rax
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // r9d
  unsigned __int16 *v7; // rdx
  int v8; // ecx
  LSTATUS v9; // eax
  UINT v10; // ebp
  HMODULE Library; // rsi
  signed int LastError; // edi
  __int64 (*ProcAddress)(void); // rax
  int v14; // eax
  signed int v15; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-168h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-160h] BYREF
  struct _GUID v19; // [rsp+60h] [rbp-158h] BYREF
  CHAR LibFileName[272]; // [rsp+70h] [rbp-148h] BYREF

  v1 = *(_QWORD *)a1;
  hKey = 0;
  dwDisposition = 0;
  v3 = *(__int64 (__fastcall **)(struct ITmInstance *, const WCHAR *, struct _GUID *))(v1 + 232);
  v19 = 0;
  v4 = v3(a1, L"MSDTCXATM", &v19);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 159;
    v7 = L"InstallXaTmRegistryKeys, pTmInstance->GetContactId failed";
LABEL_3:
    v8 = v4;
LABEL_4:
    TraceFileW(v8, v7, L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v6);
    return v5;
  }
  v4 = InstallXATmSecurityKey(a1, &v19);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 165;
    v7 = L"InstallXaTm: failed to install the XATmSecurityKey.";
    goto LABEL_3;
  }
  v9 = RegCreateKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\MSDTC\\XADLL",
         0,
         (LPSTR)Class,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition);
  v5 = v9;
  if ( v9 > 0 )
    v5 = (unsigned __int16)v9 | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 180;
    v7 = L"Failed To create  XATM DLL key";
    v8 = v5;
    goto LABEL_4;
  }
  RegCloseKey(hKey);
  v10 = SetErrorMode(0);
  SetErrorMode(v10 | 1);
  memset_0(LibFileName, 0, 0x105u);
  if ( !dword_1800D7998 )
  {
    GetSystemDirectoryA(byte_1800D7680, 0x104u);
    dword_1800D7998 = 1;
  }
  v4 = StringCchPrintfA(LibFileName, 0x105u, "%s\\mtxoci.dll", byte_1800D7680);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 194;
    v7 = L"Failed to create mtxoci.dll full path";
    goto LABEL_3;
  }
  Library = LoadLibraryExA(LibFileName, 0, 0);
  LastError = GetLastError();
  SetErrorMode(v10);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DllRegisterServer");
    if ( ProcAddress )
    {
      v14 = ProcAddress();
      if ( v14 < 0 )
        TraceFile(
          v14,
          "Error while calling MTXOCI!DllRegisterServer",
          "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
          0xD2u);
    }
    else
    {
      v15 = GetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      TraceFileW(
        v15,
        L"GetProcAccess for MTXOCI!DllRegisterServer failed",
        L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
        0xD8u);
    }
    FreeLibrary(Library);
  }
  else
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    TraceFile(LastError, "Failed to load MTXOCI.dll", "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", 0xDEu);
  }
  return v5;
}

```

## disassembly

```asm
0x180010b08  push    rbx
0x180010b0a  push    rbp
0x180010b0b  push    rsi
0x180010b0c  push    rdi
0x180010b0d  sub     rsp, 198h
0x180010b14  mov     rax, cs:__security_cookie
0x180010b1b  xor     rax, rsp
0x180010b1e  mov     [rsp+1B8h+var_38], rax
0x180010b26  mov     rax, [rcx]
0x180010b29  lea     r8, [rsp+1B8h+var_158]
0x180010b2e  xorps   xmm0, xmm0
0x180010b31  mov     [rsp+1B8h+hKey], 0
0x180010b3a  lea     rdx, aMsdtcxatm; "MSDTCXATM"
0x180010b41  mov     [rsp+1B8h+dwDisposition], 0
0x180010b49  mov     rdi, rcx
0x180010b4c  mov     rax, [rax+0E8h]
0x180010b53  movups  xmmword ptr [rsp+1B8h+var_158.Data1], xmm0
0x180010b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b5d  mov     ebx, eax
0x180010b5f  test    eax, eax
0x180010b61  jns     short loc_180010B83
0x180010b63  mov     r9d, 9Fh; unsigned int
0x180010b69  lea     rdx, aInstallxatmreg; "InstallXaTmRegistryKeys, pTmInstance->G"...
0x180010b70  mov     ecx, eax; int
0x180010b72  lea     r8, aComComplusDtcD_8; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180010b79  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180010b7e  jmp     loc_180010D64
0x180010b83  lea     rdx, [rsp+1B8h+var_158]; struct _GUID *
0x180010b88  mov     rcx, rdi; struct ITmInstance *
0x180010b8b  call    ?InstallXATmSecurityKey@@YAJPEAUITmInstance@@PEAU_GUID@@@Z; InstallXATmSecurityKey(ITmInstance *,_GUID *)
0x180010b90  mov     ebx, eax
0x180010b92  test    eax, eax
0x180010b94  jns     short loc_180010BA5
0x180010b96  mov     r9d, 0A5h
0x180010b9c  lea     rdx, aInstallxatmFai; "InstallXaTm: failed to install the XATm"...
0x180010ba3  jmp     short loc_180010B70
0x180010ba5  lea     rax, [rsp+1B8h+dwDisposition]
0x180010baa  xor     r8d, r8d; Reserved
0x180010bad  mov     [rsp+1B8h+lpdwDisposition], rax; lpdwDisposition
0x180010bb2  lea     r9, Class; lpClass
0x180010bb9  lea     rax, [rsp+1B8h+hKey]
0x180010bbe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010bc5  mov     [rsp+1B8h+phkResult], rax; phkResult
0x180010bca  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\MSDTC\\XADLL"
0x180010bd1  mov     [rsp+1B8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010bda  mov     [rsp+1B8h+samDesired], 0F003Fh; samDesired
0x180010be2  mov     [rsp+1B8h+dwOptions], 0; dwOptions
0x180010bea  call    cs:__imp_RegCreateKeyExA
0x180010bf0  mov     ebx, eax
0x180010bf2  test    eax, eax
0x180010bf4  jle     short loc_180010BFF
0x180010bf6  movzx   ebx, ax
0x180010bf9  or      ebx, 80070000h
0x180010bff  test    ebx, ebx
0x180010c01  jns     short loc_180010C17
0x180010c03  mov     r9d, 0B4h
0x180010c09  lea     rdx, aFailedToCreate_3; "Failed To create  XATM DLL key"
0x180010c10  mov     ecx, ebx
0x180010c12  jmp     loc_180010B72
0x180010c17  mov     rcx, [rsp+1B8h+hKey]; hKey
0x180010c1c  call    cs:__imp_RegCloseKey
0x180010c22  xor     ecx, ecx; uMode
0x180010c24  call    cs:__imp_SetErrorMode
0x180010c2a  mov     ecx, eax
0x180010c2c  mov     ebp, eax
0x180010c2e  or      ecx, 1; uMode
0x180010c31  call    cs:__imp_SetErrorMode
0x180010c37  mov     ebx, 105h
0x180010c3c  lea     rcx, [rsp+1B8h+LibFileName]; void *
0x180010c41  mov     r8d, ebx; Size
0x180010c44  xor     edx, edx; Val
0x180010c46  call    memset_0
0x180010c4b  cmp     cs:dword_1800D7998, 0
0x180010c52  jnz     short loc_180010C6E
0x180010c54  lea     edx, [rbx-1]; uSize
0x180010c57  lea     rcx, byte_1800D7680; lpBuffer
0x180010c5e  call    cs:__imp_GetSystemDirectoryA
0x180010c64  mov     cs:dword_1800D7998, 1
0x180010c6e  lea     r9, byte_1800D7680
0x180010c75  mov     rdx, rbx; unsigned __int64
0x180010c78  lea     r8, aSMtxociDll; "%s\\mtxoci.dll"
0x180010c7f  lea     rcx, [rsp+1B8h+LibFileName]; char *
0x180010c84  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180010c89  mov     ebx, eax
0x180010c8b  test    eax, eax
0x180010c8d  jns     short loc_180010CA1
0x180010c8f  mov     r9d, 0C2h
0x180010c95  lea     rdx, aFailedToCreate_4; "Failed to create mtxoci.dll full path"
0x180010c9c  jmp     loc_180010B70
0x180010ca1  xor     r8d, r8d; dwFlags
0x180010ca4  lea     rcx, [rsp+1B8h+LibFileName]; lpLibFileName
0x180010ca9  xor     edx, edx; hFile
0x180010cab  call    cs:__imp_LoadLibraryExA
0x180010cb1  mov     rsi, rax
0x180010cb4  call    cs:__imp_GetLastError
0x180010cba  mov     ecx, ebp; uMode
0x180010cbc  mov     edi, eax
0x180010cbe  call    cs:__imp_SetErrorMode
0x180010cc4  test    rsi, rsi
0x180010cc7  jz      short loc_180010D3C
0x180010cc9  lea     rdx, ProcName; "DllRegisterServer"
0x180010cd0  mov     rcx, rsi; hModule
0x180010cd3  call    cs:__imp_GetProcAddress
0x180010cd9  test    rax, rax
0x180010cdc  jz      short loc_180010D04
0x180010cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ce3  test    eax, eax
0x180010ce5  jns     short loc_180010D31
0x180010ce7  mov     r9d, 0D2h; unsigned int
0x180010ced  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180010cf4  lea     rdx, aErrorWhileCall; "Error while calling MTXOCI!DllRegisterS"...
0x180010cfb  mov     ecx, eax; int
0x180010cfd  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180010d02  jmp     short loc_180010D31
0x180010d04  call    cs:__imp_GetLastError
0x180010d0a  test    eax, eax
0x180010d0c  jle     short loc_180010D16
0x180010d0e  movzx   eax, ax
0x180010d11  or      eax, 80070000h
0x180010d16  mov     r9d, 0D8h; unsigned int
0x180010d1c  lea     r8, aComComplusDtcD_8; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180010d23  lea     rdx, aGetprocaccessF; "GetProcAccess for MTXOCI!DllRegisterSer"...
0x180010d2a  mov     ecx, eax; int
0x180010d2c  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180010d31  mov     rcx, rsi; hLibModule
0x180010d34  call    cs:__imp_FreeLibrary
0x180010d3a  jmp     short loc_180010D64
0x180010d3c  test    edi, edi
0x180010d3e  jle     short loc_180010D49
0x180010d40  movzx   edi, di
0x180010d43  or      edi, 80070000h
0x180010d49  mov     r9d, 0DEh; unsigned int
0x180010d4f  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180010d56  lea     rdx, aFailedToLoadMt_0; "Failed to load MTXOCI.dll"
0x180010d5d  mov     ecx, edi; int
0x180010d5f  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180010d64  mov     eax, ebx
0x180010d66  mov     rcx, [rsp+1B8h+var_38]
0x180010d6e  xor     rcx, rsp; StackCookie
0x180010d71  call    __security_check_cookie
0x180010d76  add     rsp, 198h
0x180010d7d  pop     rdi
0x180010d7e  pop     rsi
0x180010d7f  pop     rbp
0x180010d80  pop     rbx
0x180010d81  retn
```

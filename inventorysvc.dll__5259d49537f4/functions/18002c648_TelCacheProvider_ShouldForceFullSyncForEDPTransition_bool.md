# TelCacheProvider::ShouldForceFullSyncForEDPTransition(bool)

- ea: `0x18002c648`
- end: `0x18002c828`
- name: `?ShouldForceFullSyncForEDPTransition@TelCacheProvider@@AEAAH_N@Z`
- size: `480`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c1a4`

## callees

- `0x180002bf0`
- `0x1800152d0`
- `0x18002c648`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c6aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c6aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c68d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c68d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c800`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c800`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c717`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c761`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c717`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c761`

## string_xrefs

- `0x18002c686`: `DiagnosticDataSettings.dll`
- `0x18002c6ff`: `RedirectedRegistryRoot`
- `0x18002c7e6`: `TelCacheProvider::ShouldForceFullSyncForEDPTransition`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TelCacheProvider::ShouldForceFullSyncForEDPTransition(TelCacheProvider *this, char a2)
{
  unsigned int v4; // edi
  HMODULE Library; // rax
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rax
  __int64 v8; // r8
  bool v9; // zf
  LSTATUS ValueW; // eax
  const WCHAR *v11; // rdx
  __int64 v12; // rax
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v15[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pvData[528]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = 0;
  v15[0] = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings.dll", 0, 0x800u);
  v6 = Library;
  v15[1] = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "TelIsOsInProcessorMode"), pcbData[0] = 0, ProcAddress)
    && ((int (__fastcall *)(DWORD *))ProcAddress)(pcbData) >= 0 )
  {
    v8 = 0;
    v9 = pcbData[0] == 0;
  }
  else
  {
    pcbData[0] = 520;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack",
               L"RedirectedRegistryRoot",
               2u,
               0,
               pvData,
               pcbData);
    v11 = (const WCHAR *)pvData;
    if ( ValueW )
      v11 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack";
    pcbData[0] = 8;
    RegGetValueW(HKEY_LOCAL_MACHINE, v11, L"mspflags", 0x20000040u, 0, v15, pcbData);
    v8 = 0;
    v9 = v15[0] == 0;
  }
  LOBYTE(v8) = !v9;
  v15[0] = v8;
  if ( !a2 )
  {
    *(_QWORD *)pcbData = 0;
    if ( (*(int (__fastcall **)(_QWORD, const WCHAR *, DWORD *))(**((_QWORD **)this + 11) + 64LL))(
           *((_QWORD *)this + 11),
           L"mspflags",
           pcbData) >= 0 )
      v12 = *(_QWORD *)pcbData;
    else
      v12 = 0;
    if ( v12 == v15[0] )
      goto LABEL_16;
    v4 = 1;
  }
  (*(void (__fastcall **)(_QWORD, const WCHAR *))(**((_QWORD **)this + 11) + 88LL))(*((_QWORD *)this + 11), L"mspflags");
  if ( v4 )
    AslLogCallPrintf(
      3,
      "TelCacheProvider::ShouldForceFullSyncForEDPTransition",
      2136,
      "Full sync may be needed because of EDP");
LABEL_16:
  if ( v6 )
    FreeLibrary(v6);
  return v4;
}

```

## disassembly

```asm
0x18002c648  push    rbp
0x18002c64a  push    rbx
0x18002c64b  push    rsi
0x18002c64c  push    rdi
0x18002c64d  push    r14
0x18002c64f  push    r15
0x18002c651  lea     rbp, [rsp-188h]
0x18002c659  sub     rsp, 288h
0x18002c660  mov     rax, cs:__security_cookie
0x18002c667  xor     rax, rsp
0x18002c66a  mov     [rbp+1B0h+var_40], rax
0x18002c671  mov     r14b, dl
0x18002c674  mov     rsi, rcx
0x18002c677  xor     edi, edi
0x18002c679  mov     [rsp+2B0h+var_268], rdi
0x18002c67e  xor     edx, edx; hFile
0x18002c680  mov     r8d, 800h; dwFlags
0x18002c686  lea     rcx, aDiagnosticdata_0; "DiagnosticDataSettings.dll"
0x18002c68d  call    cs:__imp_LoadLibraryExW
0x18002c693  mov     rbx, rax
0x18002c696  mov     [rsp+2B0h+var_260], rax
0x18002c69b  test    rax, rax
0x18002c69e  jz      short loc_18002C6D4
0x18002c6a0  lea     rdx, aTelisosinproce; "TelIsOsInProcessorMode"
0x18002c6a7  mov     rcx, rax; hModule
0x18002c6aa  call    cs:__imp_GetProcAddress
0x18002c6b0  mov     [rsp+2B0h+var_270], edi
0x18002c6b4  test    rax, rax
0x18002c6b7  jz      short loc_18002C6D4
0x18002c6b9  lea     rcx, [rsp+2B0h+var_270]
0x18002c6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6c3  test    eax, eax
0x18002c6c5  js      short loc_18002C6D4
0x18002c6c7  xor     r8d, r8d
0x18002c6ca  cmp     [rsp+2B0h+var_270], r8d
0x18002c6cf  jmp     loc_18002C76F
0x18002c6d4  mov     [rsp+2B0h+var_270], 208h
0x18002c6dc  lea     rax, [rsp+2B0h+var_270]
0x18002c6e1  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18002c6e6  lea     rax, [rsp+2B0h+var_250]
0x18002c6eb  mov     [rsp+2B0h+pvData], rax; pvData
0x18002c6f0  mov     [rsp+2B0h+pdwType], 0; pdwType
0x18002c6f9  mov     r9d, 2; dwFlags
0x18002c6ff  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x18002c706  lea     r15, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002c70d  mov     rdx, r15; lpSubKey
0x18002c710  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002c717  call    cs:__imp_RegGetValueW
0x18002c71d  lea     rdx, [rsp+2B0h+var_250]
0x18002c722  test    eax, eax
0x18002c724  cmovnz  rdx, r15; lpSubKey
0x18002c728  mov     [rsp+2B0h+var_270], 8
0x18002c730  lea     rax, [rsp+2B0h+var_270]
0x18002c735  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18002c73a  lea     rax, [rsp+2B0h+var_268]
0x18002c73f  mov     [rsp+2B0h+pvData], rax; pvData
0x18002c744  mov     [rsp+2B0h+pdwType], 0; pdwType
0x18002c74d  mov     r9d, 20000040h; dwFlags
0x18002c753  lea     r8, aMspflags; "mspflags"
0x18002c75a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002c761  call    cs:__imp_RegGetValueW
0x18002c767  xor     r8d, r8d
0x18002c76a  cmp     [rsp+2B0h+var_268], r8
0x18002c76f  setnz   r8b
0x18002c773  mov     [rsp+2B0h+var_268], r8
0x18002c778  test    r14b, r14b
0x18002c77b  jnz     short loc_18002C7BE
0x18002c77d  mov     qword ptr [rsp+2B0h+var_270], 0
0x18002c786  mov     rcx, [rsi+58h]
0x18002c78a  mov     rax, [rcx]
0x18002c78d  lea     r8, [rsp+2B0h+var_270]
0x18002c792  lea     rdx, aMspflags; "mspflags"
0x18002c799  mov     rax, [rax+40h]
0x18002c79d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7a2  test    eax, eax
0x18002c7a4  jns     short loc_18002C7AA
0x18002c7a6  xor     eax, eax
0x18002c7a8  jmp     short loc_18002C7AF
0x18002c7aa  mov     rax, qword ptr [rsp+2B0h+var_270]
0x18002c7af  mov     r8, [rsp+2B0h+var_268]
0x18002c7b4  cmp     rax, r8
0x18002c7b7  jz      short loc_18002C7F8
0x18002c7b9  mov     edi, 1
0x18002c7be  mov     rcx, [rsi+58h]
0x18002c7c2  mov     rax, [rcx]
0x18002c7c5  lea     rdx, aMspflags; "mspflags"
0x18002c7cc  mov     rax, [rax+58h]
0x18002c7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7d5  test    edi, edi
0x18002c7d7  jz      short loc_18002C7F8
0x18002c7d9  lea     r9, aFullSyncMayBeN_1; "Full sync may be needed because of EDP"
0x18002c7e0  mov     r8d, 858h
0x18002c7e6  lea     rdx, aTelcacheprovid_1; "TelCacheProvider::ShouldForceFullSyncFo"...
0x18002c7ed  mov     ecx, 3
0x18002c7f2  call    AslLogCallPrintf
0x18002c7f7  nop
0x18002c7f8  test    rbx, rbx
0x18002c7fb  jz      short loc_18002C807
0x18002c7fd  mov     rcx, rbx; hLibModule
0x18002c800  call    cs:__imp_FreeLibrary
0x18002c806  nop
0x18002c807  mov     eax, edi
0x18002c809  mov     rcx, [rbp+1B0h+var_40]
0x18002c810  xor     rcx, rsp; StackCookie
0x18002c813  call    __security_check_cookie
0x18002c818  add     rsp, 288h
0x18002c81f  pop     r15
0x18002c821  pop     r14
0x18002c823  pop     rdi
0x18002c824  pop     rsi
0x18002c825  pop     rbx
0x18002c826  pop     rbp
0x18002c827  retn
```

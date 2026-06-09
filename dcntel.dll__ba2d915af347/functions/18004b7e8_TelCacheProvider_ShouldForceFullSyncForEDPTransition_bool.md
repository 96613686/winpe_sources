# TelCacheProvider::ShouldForceFullSyncForEDPTransition(bool)

- ea: `0x18004b7e8`
- end: `0x18004b9c7`
- name: `?ShouldForceFullSyncForEDPTransition@TelCacheProvider@@AEAAH_N@Z`
- size: `479`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b3e8`

## callees

- `0x180008dc0`
- `0x18004b7e8`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004b82d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004b82d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004b9a0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004b9a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b84a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b84a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b8b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b901`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b8b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b901`

## string_xrefs

- `0x18004b826`: `DiagnosticDataSettings.dll`
- `0x18004b986`: `TelCacheProvider::ShouldForceFullSyncForEDPTransition`
- `0x18004b89f`: `RedirectedRegistryRoot`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18004b7e8  push    rbp
0x18004b7ea  push    rbx
0x18004b7eb  push    rsi
0x18004b7ec  push    rdi
0x18004b7ed  push    r14
0x18004b7ef  push    r15
0x18004b7f1  lea     rbp, [rsp-188h]
0x18004b7f9  sub     rsp, 288h
0x18004b800  mov     rax, cs:__security_cookie
0x18004b807  xor     rax, rsp
0x18004b80a  mov     [rbp+1B0h+var_40], rax
0x18004b811  mov     r14b, dl
0x18004b814  mov     rsi, rcx
0x18004b817  xor     edi, edi
0x18004b819  mov     [rsp+2B0h+var_268], rdi
0x18004b81e  xor     edx, edx; hFile
0x18004b820  mov     r8d, 800h; dwFlags
0x18004b826  lea     rcx, aDiagnosticdata_1; "DiagnosticDataSettings.dll"
0x18004b82d  call    cs:__imp_LoadLibraryExW
0x18004b833  mov     rbx, rax
0x18004b836  mov     [rsp+2B0h+var_260], rax
0x18004b83b  test    rax, rax
0x18004b83e  jz      short loc_18004B874
0x18004b840  lea     rdx, aTelisosinproce; "TelIsOsInProcessorMode"
0x18004b847  mov     rcx, rax; hModule
0x18004b84a  call    cs:__imp_GetProcAddress
0x18004b850  mov     [rsp+2B0h+var_270], edi
0x18004b854  test    rax, rax
0x18004b857  jz      short loc_18004B874
0x18004b859  lea     rcx, [rsp+2B0h+var_270]
0x18004b85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b863  test    eax, eax
0x18004b865  js      short loc_18004B874
0x18004b867  xor     r8d, r8d
0x18004b86a  cmp     [rsp+2B0h+var_270], r8d
0x18004b86f  jmp     loc_18004B90F
0x18004b874  mov     [rsp+2B0h+var_270], 208h
0x18004b87c  lea     rax, [rsp+2B0h+var_270]
0x18004b881  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18004b886  lea     rax, [rsp+2B0h+var_250]
0x18004b88b  mov     [rsp+2B0h+pvData], rax; pvData
0x18004b890  mov     [rsp+2B0h+pdwType], 0; pdwType
0x18004b899  mov     r9d, 2; dwFlags
0x18004b89f  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x18004b8a6  lea     r15, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004b8ad  mov     rdx, r15; lpSubKey
0x18004b8b0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18004b8b7  call    cs:__imp_RegGetValueW
0x18004b8bd  lea     rdx, [rsp+2B0h+var_250]
0x18004b8c2  test    eax, eax
0x18004b8c4  cmovnz  rdx, r15; lpSubKey
0x18004b8c8  mov     [rsp+2B0h+var_270], 8
0x18004b8d0  lea     rax, [rsp+2B0h+var_270]
0x18004b8d5  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18004b8da  lea     rax, [rsp+2B0h+var_268]
0x18004b8df  mov     [rsp+2B0h+pvData], rax; pvData
0x18004b8e4  mov     [rsp+2B0h+pdwType], 0; pdwType
0x18004b8ed  mov     r9d, 20000040h; dwFlags
0x18004b8f3  lea     r8, aMspflags; "mspflags"
0x18004b8fa  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18004b901  call    cs:__imp_RegGetValueW
0x18004b907  xor     r8d, r8d
0x18004b90a  cmp     [rsp+2B0h+var_268], r8
0x18004b90f  setnz   r8b
0x18004b913  mov     [rsp+2B0h+var_268], r8
0x18004b918  test    r14b, r14b
0x18004b91b  jnz     short loc_18004B95E
0x18004b91d  mov     qword ptr [rsp+2B0h+var_270], 0
0x18004b926  mov     rcx, [rsi+58h]
0x18004b92a  mov     rax, [rcx]
0x18004b92d  lea     r8, [rsp+2B0h+var_270]
0x18004b932  lea     rdx, aMspflags; "mspflags"
0x18004b939  mov     rax, [rax+40h]
0x18004b93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b942  test    eax, eax
0x18004b944  jns     short loc_18004B94A
0x18004b946  xor     eax, eax
0x18004b948  jmp     short loc_18004B94F
0x18004b94a  mov     rax, qword ptr [rsp+2B0h+var_270]
0x18004b94f  mov     r8, [rsp+2B0h+var_268]
0x18004b954  cmp     rax, r8
0x18004b957  jz      short loc_18004B998
0x18004b959  mov     edi, 1
0x18004b95e  mov     rcx, [rsi+58h]
0x18004b962  mov     rax, [rcx]
0x18004b965  lea     rdx, aMspflags; "mspflags"
0x18004b96c  mov     rax, [rax+58h]
0x18004b970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b975  test    edi, edi
0x18004b977  jz      short loc_18004B998
0x18004b979  lea     r9, aFullSyncMayBeN_1; "Full sync may be needed because of EDP"
0x18004b980  mov     r8d, 858h
0x18004b986  lea     rdx, aTelcacheprovid_3; "TelCacheProvider::ShouldForceFullSyncFo"...
0x18004b98d  mov     ecx, 3
0x18004b992  call    AslLogCallPrintf
0x18004b997  nop
0x18004b998  test    rbx, rbx
0x18004b99b  jz      short loc_18004B9A6
0x18004b99d  mov     rcx, rbx; hLibModule
0x18004b9a0  call    cs:__imp_FreeLibrary
0x18004b9a6  mov     eax, edi
0x18004b9a8  mov     rcx, [rbp+1B0h+var_40]
0x18004b9af  xor     rcx, rsp; StackCookie
0x18004b9b2  call    __security_check_cookie
0x18004b9b7  add     rsp, 288h
0x18004b9be  pop     r15
0x18004b9c0  pop     r14
0x18004b9c2  pop     rdi
0x18004b9c3  pop     rsi
0x18004b9c4  pop     rbx
0x18004b9c5  pop     rbp
0x18004b9c6  retn
```

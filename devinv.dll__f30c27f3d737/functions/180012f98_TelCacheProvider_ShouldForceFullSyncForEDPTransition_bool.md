# TelCacheProvider::ShouldForceFullSyncForEDPTransition(bool)

- ea: `0x180012f98`
- end: `0x180013177`
- name: `?ShouldForceFullSyncForEDPTransition@TelCacheProvider@@AEAAH_N@Z`
- size: `479`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012af4`

## callees

- `0x180005e40`
- `0x180012f98`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012fdd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012fdd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013150`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013150`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012ffa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012ffa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013067`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800130b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013067`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800130b1`

## string_xrefs

- `0x180012fd6`: `DiagnosticDataSettings.dll`
- `0x18001304f`: `RedirectedRegistryRoot`
- `0x180013136`: `TelCacheProvider::ShouldForceFullSyncForEDPTransition`

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
0x180012f98  push    rbp
0x180012f9a  push    rbx
0x180012f9b  push    rsi
0x180012f9c  push    rdi
0x180012f9d  push    r14
0x180012f9f  push    r15
0x180012fa1  lea     rbp, [rsp-188h]
0x180012fa9  sub     rsp, 288h
0x180012fb0  mov     rax, cs:__security_cookie
0x180012fb7  xor     rax, rsp
0x180012fba  mov     [rbp+1B0h+var_40], rax
0x180012fc1  mov     r14b, dl
0x180012fc4  mov     rsi, rcx
0x180012fc7  xor     edi, edi
0x180012fc9  mov     [rsp+2B0h+var_268], rdi
0x180012fce  xor     edx, edx; hFile
0x180012fd0  mov     r8d, 800h; dwFlags
0x180012fd6  lea     rcx, aDiagnosticdata_0; "DiagnosticDataSettings.dll"
0x180012fdd  call    cs:__imp_LoadLibraryExW
0x180012fe3  mov     rbx, rax
0x180012fe6  mov     [rsp+2B0h+var_260], rax
0x180012feb  test    rax, rax
0x180012fee  jz      short loc_180013024
0x180012ff0  lea     rdx, aTelisosinproce; "TelIsOsInProcessorMode"
0x180012ff7  mov     rcx, rax; hModule
0x180012ffa  call    cs:__imp_GetProcAddress
0x180013000  mov     [rsp+2B0h+var_270], edi
0x180013004  test    rax, rax
0x180013007  jz      short loc_180013024
0x180013009  lea     rcx, [rsp+2B0h+var_270]
0x18001300e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013013  test    eax, eax
0x180013015  js      short loc_180013024
0x180013017  xor     r8d, r8d
0x18001301a  cmp     [rsp+2B0h+var_270], r8d
0x18001301f  jmp     loc_1800130BF
0x180013024  mov     [rsp+2B0h+var_270], 208h
0x18001302c  lea     rax, [rsp+2B0h+var_270]
0x180013031  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180013036  lea     rax, [rsp+2B0h+var_250]
0x18001303b  mov     [rsp+2B0h+pvData], rax; pvData
0x180013040  mov     [rsp+2B0h+pdwType], 0; pdwType
0x180013049  mov     r9d, 2; dwFlags
0x18001304f  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x180013056  lea     r15, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001305d  mov     rdx, r15; lpSubKey
0x180013060  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180013067  call    cs:__imp_RegGetValueW
0x18001306d  lea     rdx, [rsp+2B0h+var_250]
0x180013072  test    eax, eax
0x180013074  cmovnz  rdx, r15; lpSubKey
0x180013078  mov     [rsp+2B0h+var_270], 8
0x180013080  lea     rax, [rsp+2B0h+var_270]
0x180013085  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18001308a  lea     rax, [rsp+2B0h+var_268]
0x18001308f  mov     [rsp+2B0h+pvData], rax; pvData
0x180013094  mov     [rsp+2B0h+pdwType], 0; pdwType
0x18001309d  mov     r9d, 20000040h; dwFlags
0x1800130a3  lea     r8, aMspflags; "mspflags"
0x1800130aa  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800130b1  call    cs:__imp_RegGetValueW
0x1800130b7  xor     r8d, r8d
0x1800130ba  cmp     [rsp+2B0h+var_268], r8
0x1800130bf  setnz   r8b
0x1800130c3  mov     [rsp+2B0h+var_268], r8
0x1800130c8  test    r14b, r14b
0x1800130cb  jnz     short loc_18001310E
0x1800130cd  mov     qword ptr [rsp+2B0h+var_270], 0
0x1800130d6  mov     rcx, [rsi+58h]
0x1800130da  mov     rax, [rcx]
0x1800130dd  lea     r8, [rsp+2B0h+var_270]
0x1800130e2  lea     rdx, aMspflags; "mspflags"
0x1800130e9  mov     rax, [rax+40h]
0x1800130ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130f2  test    eax, eax
0x1800130f4  jns     short loc_1800130FA
0x1800130f6  xor     eax, eax
0x1800130f8  jmp     short loc_1800130FF
0x1800130fa  mov     rax, qword ptr [rsp+2B0h+var_270]
0x1800130ff  mov     r8, [rsp+2B0h+var_268]
0x180013104  cmp     rax, r8
0x180013107  jz      short loc_180013148
0x180013109  mov     edi, 1
0x18001310e  mov     rcx, [rsi+58h]
0x180013112  mov     rax, [rcx]
0x180013115  lea     rdx, aMspflags; "mspflags"
0x18001311c  mov     rax, [rax+58h]
0x180013120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013125  test    edi, edi
0x180013127  jz      short loc_180013148
0x180013129  lea     r9, aFullSyncMayBeN_1; "Full sync may be needed because of EDP"
0x180013130  mov     r8d, 858h
0x180013136  lea     rdx, aTelcacheprovid_3; "TelCacheProvider::ShouldForceFullSyncFo"...
0x18001313d  mov     ecx, 3
0x180013142  call    AslLogCallPrintf
0x180013147  nop
0x180013148  test    rbx, rbx
0x18001314b  jz      short loc_180013156
0x18001314d  mov     rcx, rbx; hLibModule
0x180013150  call    cs:__imp_FreeLibrary
0x180013156  mov     eax, edi
0x180013158  mov     rcx, [rbp+1B0h+var_40]
0x18001315f  xor     rcx, rsp; StackCookie
0x180013162  call    __security_check_cookie
0x180013167  add     rsp, 288h
0x18001316e  pop     r15
0x180013170  pop     r14
0x180013172  pop     rdi
0x180013173  pop     rsi
0x180013174  pop     rbx
0x180013175  pop     rbp
0x180013176  retn
```

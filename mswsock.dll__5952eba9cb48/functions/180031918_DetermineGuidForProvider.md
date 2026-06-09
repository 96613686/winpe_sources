# DetermineGuidForProvider

- ea: `0x180031918`
- end: `0x180031b44`
- name: `DetermineGuidForProvider`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180032294`

## callees

- `0x180031918`
- `0x1800327cc`
- `0x18003439c`
- `0x180034d30`
- `0x1800384d4`
- `0x18003ae8c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800319ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800319ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800319f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800319f5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031a56`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031a6c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031a56`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031a6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031ae8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031ae8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031994`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031994`
- `RPCRT4!UuidCreate` at `0x180031abc`
- `RPCRT4!UuidCreate` at `0x180031abc`

## string_xrefs

- `0x18003195c`: `Failed to open provider parameters key`
- `0x1800319ab`: `Failed to read provider GUID from offline capable provider`
- `0x180031afb`: `Failed to create GUID for provider`

## pseudocode

```c
__int64 __fastcall DetermineGuidForProvider(
        __int64 a1,
        HKEY a2,
        int a3,
        const WCHAR *a4,
        const WCHAR *lpLibFileName,
        UUID *Uuid)
{
  unsigned int v8; // eax
  unsigned int v9; // edi
  unsigned int Guid; // edi
  HMODULE Library; // rax
  int v12; // ecx
  HMODULE v13; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v16; // eax
  HKEY hKey[3]; // [rsp+38h] [rbp-30h] BYREF

  hKey[0] = 0;
  if ( !a3 )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 0);
    v13 = Library;
    hKey[1] = (HKEY)Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "WSHGetProviderGuid");
      if ( ProcAddress && !((unsigned int (__fastcall *)(const WCHAR *, UUID *))ProcAddress)(a4, Uuid) )
      {
        FreeLibrary(v13);
        return 0;
      }
      FreeLibrary(v13);
    }
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_SS(
        v12,
        51,
        (unsigned int)WPP_4593deb55ead3582b257adde53a3fabd_Traceguids,
        (_DWORD)lpLibFileName,
        (__int64)a4);
LABEL_16:
    if ( (unsigned int)ReadGuid(a2, a4, Uuid) )
    {
      v16 = UuidCreate(Uuid);
      v9 = v16;
      if ( v16 )
      {
        LogErrorWithProvider(v16, L"Failed to create GUID for provider", a4);
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_d(1025, 52, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v9);
      }
      else
      {
        return (unsigned int)RegSetValueExW(a2, a4, 0, 3u, (const BYTE *)Uuid, 0x10u);
      }
      return v9;
    }
    return 0;
  }
  v8 = OpenProviderParametersKey(a1, a4, hKey);
  v9 = v8;
  if ( !v8 )
  {
    Guid = ReadGuid(hKey[0], L"ProviderGUID", Uuid);
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    if ( !Guid )
      return 0;
    LogErrorWithProvider(Guid, L"Failed to read provider GUID from offline capable provider", a4);
    goto LABEL_16;
  }
  LogErrorWithProvider(v8, L"Failed to open provider parameters key", a4);
  return v9;
}

```

## disassembly

```asm
0x180031918  mov     rax, rsp
0x18003191b  mov     [rax+8], rbx
0x18003191f  mov     [rax+18h], rsi
0x180031923  mov     [rax+20h], r9
0x180031927  mov     [rax+10h], rdx
0x18003192b  push    rdi
0x18003192c  push    r14
0x18003192e  push    r15
0x180031930  sub     rsp, 50h
0x180031934  mov     rbx, r9
0x180031937  mov     r15, rdx
0x18003193a  mov     qword ptr [rax-30h], 0
0x180031942  test    r8d, r8d
0x180031945  jz      short loc_1800319BE
0x180031947  lea     r8, [rax-30h]
0x18003194b  mov     rdx, rbx
0x18003194e  call    OpenProviderParametersKey
0x180031953  mov     edi, eax
0x180031955  test    eax, eax
0x180031957  jz      short loc_18003196F
0x180031959  mov     r8, rbx
0x18003195c  lea     rdx, aFailedToOpenPr_1; "Failed to open provider parameters key"
0x180031963  mov     ecx, eax
0x180031965  call    LogErrorWithProvider
0x18003196a  jmp     loc_180031B2B
0x18003196f  mov     r8, [rsp+68h+Uuid]
0x180031977  lea     rdx, aProviderguid; "ProviderGUID"
0x18003197e  mov     rcx, [rsp+68h+hKey]
0x180031983  call    ReadGuid
0x180031988  mov     edi, eax
0x18003198a  mov     rcx, [rsp+68h+hKey]; hKey
0x18003198f  test    rcx, rcx
0x180031992  jz      short loc_1800319A0
0x180031994  call    cs:__imp_RegCloseKey
0x18003199b  nop     dword ptr [rax+rax+00h]
0x1800319a0  test    edi, edi
0x1800319a2  jz      loc_180031A62
0x1800319a8  mov     r8, rbx
0x1800319ab  lea     rdx, aFailedToReadPr_1; "Failed to read provider GUID from offli"...
0x1800319b2  mov     ecx, edi
0x1800319b4  call    LogErrorWithProvider
0x1800319b9  jmp     loc_180031A9A
0x1800319be  xor     r8d, r8d; dwFlags
0x1800319c1  xor     edx, edx; hFile
0x1800319c3  mov     r14, [rsp+68h+lpLibFileName]
0x1800319cb  mov     rcx, r14; lpLibFileName
0x1800319ce  call    cs:__imp_LoadLibraryExW
0x1800319d5  nop     dword ptr [rax+rax+00h]
0x1800319da  mov     rdi, rax
0x1800319dd  mov     [rsp+68h+var_28], rax
0x1800319e2  test    rax, rax
0x1800319e5  jz      loc_180031A78
0x1800319eb  lea     rdx, aWshgetprovider; "WSHGetProviderGuid"
0x1800319f2  mov     rcx, rax; hModule
0x1800319f5  call    cs:__imp_GetProcAddress
0x1800319fc  nop     dword ptr [rax+rax+00h]
0x180031a01  test    rax, rax
0x180031a04  jz      short loc_180031A69
0x180031a06  mov     rdx, [rsp+68h+Uuid]
0x180031a0e  mov     rcx, rbx
0x180031a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a16  mov     esi, eax
0x180031a18  mov     [rsp+68h+var_38], eax
0x180031a1c  jmp     short loc_180031A4F
0x180031a1e  mov     esi, eax
0x180031a20  mov     [rsp+68h+var_38], eax
0x180031a24  mov     rbx, [rsp+68h+arg_18]
0x180031a2c  mov     r8, rbx
0x180031a2f  lea     rdx, aCaughException; "Caugh exception while trying to get pro"...
0x180031a36  mov     ecx, eax
0x180031a38  call    LogErrorWithProvider
0x180031a3d  mov     r14, [rsp+68h+lpLibFileName]
0x180031a45  mov     r15, [rsp+68h+arg_8]
0x180031a4a  mov     rdi, [rsp+68h+var_28]
0x180031a4f  test    esi, esi
0x180031a51  jnz     short loc_180031A69
0x180031a53  mov     rcx, rdi; hLibModule
0x180031a56  call    cs:__imp_FreeLibrary
0x180031a5d  nop     dword ptr [rax+rax+00h]
0x180031a62  xor     eax, eax
0x180031a64  jmp     loc_180031B2D
0x180031a69  mov     rcx, rdi; hLibModule
0x180031a6c  call    cs:__imp_FreeLibrary
0x180031a73  nop     dword ptr [rax+rax+00h]
0x180031a78  test    byte ptr cs:xmmword_180063D60, 2
0x180031a7f  jz      short loc_180031A9A
0x180031a81  mov     edx, 33h ; '3'
0x180031a86  mov     [rsp+68h+lpData], rbx
0x180031a8b  mov     r9, r14
0x180031a8e  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180031a95  call    WPP_SF_SS
0x180031a9a  mov     r8, [rsp+68h+Uuid]
0x180031aa2  mov     rdx, rbx
0x180031aa5  mov     rcx, r15
0x180031aa8  call    ReadGuid
0x180031aad  test    eax, eax
0x180031aaf  jz      short loc_180031A62
0x180031ab1  mov     rsi, [rsp+68h+Uuid]
0x180031ab9  mov     rcx, rsi; Uuid
0x180031abc  call    cs:__imp_UuidCreate
0x180031ac3  nop     dword ptr [rax+rax+00h]
0x180031ac8  mov     edi, eax
0x180031aca  test    eax, eax
0x180031acc  jnz     short loc_180031AF8
0x180031ace  mov     [rsp+68h+cbData], 10h; cbData
0x180031ad6  mov     [rsp+68h+lpData], rsi; lpData
0x180031adb  lea     r9d, [rax+3]; dwType
0x180031adf  xor     r8d, r8d; Reserved
0x180031ae2  mov     rdx, rbx; lpValueName
0x180031ae5  mov     rcx, r15; hKey
0x180031ae8  call    cs:__imp_RegSetValueExW
0x180031aef  nop     dword ptr [rax+rax+00h]
0x180031af4  mov     edi, eax
0x180031af6  jmp     short loc_180031B2B
0x180031af8  mov     r8, rbx
0x180031afb  lea     rdx, aFailedToCreate_3; "Failed to create GUID for provider"
0x180031b02  mov     ecx, edi
0x180031b04  call    LogErrorWithProvider
0x180031b09  test    byte ptr cs:xmmword_180063D60, 2
0x180031b10  jz      short loc_180031B2B
0x180031b12  mov     edx, 34h ; '4'
0x180031b17  mov     ecx, 401h
0x180031b1c  mov     r9d, edi
0x180031b1f  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180031b26  call    WPP_SF_d
0x180031b2b  mov     eax, edi
0x180031b2d  lea     r11, [rsp+68h+var_18]
0x180031b32  mov     rbx, [r11+20h]
0x180031b36  mov     rsi, [r11+30h]
0x180031b3a  mov     rsp, r11
0x180031b3d  pop     r15
0x180031b3f  pop     r14
0x180031b41  pop     rdi
0x180031b42  retn
```

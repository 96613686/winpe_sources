# RestoreParametersForUpgrade(void *,ulong,ushort * *,ushort * *,ulong *,ulong *,_DRIVER_INFO_8W * *)

- ea: `0x1800288e4`
- end: `0x180028ebd`
- name: `?RestoreParametersForUpgrade@@YAHPEAXKPEAPEAG1PEAK2PEAPEAU_DRIVER_INFO_8W@@@Z`
- size: `1497`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, DWORD dwIndex@<edx>, unsigned __int16 **@<r8>, unsigned __int16 **@<r9>, unsigned int *, unsigned int *, struct _DRIVER_INFO_8W **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180028360`

## callees

- `0x1800288e4`
- `0x18004032c`
- `0x18006d330`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028a16`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028a16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028bd8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028c0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028c43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028c77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028bd8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028c0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028c43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028c77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028e9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028e9c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180028975`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800289d1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180028975`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800289d1`
- `SPOOLSS!DllFreeSplMem` at `0x18002898b`
- `SPOOLSS!DllFreeSplMem` at `0x180028e7b`
- `SPOOLSS!DllFreeSplMem` at `0x180028e8d`
- `SPOOLSS!DllFreeSplMem` at `0x18002898b`
- `SPOOLSS!DllFreeSplMem` at `0x180028e7b`
- `SPOOLSS!DllFreeSplMem` at `0x180028e8d`
- `SPOOLSS!DllAllocSplMem` at `0x18002892b`
- `SPOOLSS!DllAllocSplMem` at `0x180028942`
- `SPOOLSS!DllAllocSplMem` at `0x18002899c`
- `SPOOLSS!DllAllocSplMem` at `0x18002892b`
- `SPOOLSS!DllAllocSplMem` at `0x180028942`
- `SPOOLSS!DllAllocSplMem` at `0x18002899c`

## string_xrefs

- `0x180028b58`: `InfPath`
- `0x180028a5a`: `DriverMoved`
- `0x180028df4`: `pDriverPath`
- `0x180028db8`: `pConfigFile`

## pseudocode

```c
__int64 __fastcall RestoreParametersForUpgrade(
        HKEY hKey,
        DWORD dwIndex,
        unsigned __int16 **a3,
        unsigned __int8 **a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        struct _DRIVER_INFO_8W **a7)
{
  struct _DRIVER_INFO_8W **v7; // rax
  __int64 v12; // rbx
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  LSTATUS v15; // eax
  unsigned int v16; // r15d
  struct _DRIVER_INFO_8W **v17; // rax
  HKEY phkResult; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int8 *v20; // [rsp+58h] [rbp-8h] BYREF
  unsigned int v21; // [rsp+B0h] [rbp+50h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp+58h] BYREF

  v7 = a7;
  v21 = 0;
  phkResult = 0;
  *a4 = 0;
  *v7 = 0;
  *a3 = 0;
  cchName = 261;
  v12 = DllAllocSplMem(200);
  if ( !v12 )
  {
    v14 = 0;
    goto LABEL_46;
  }
  v13 = (WCHAR *)DllAllocSplMem(2 * cchName);
  v14 = v13;
  if ( v13 )
  {
    v15 = RegEnumKeyExW(hKey, dwIndex, v13, &cchName, 0, 0, 0, 0);
    v16 = 1;
    if ( v15 == 234 )
    {
      DllFreeSplMem(v14);
      ++cchName;
      v14 = (WCHAR *)DllAllocSplMem(2 * cchName);
      if ( !v14 )
        goto LABEL_46;
      v15 = RegEnumKeyExW(hKey, dwIndex, v14, &cchName, 0, 0, 0, 0);
    }
    if ( !v15
      && !RegCreateKeyExW(hKey, v14, 0, 0, 0, 0x20019u, 0, &phkResult, 0)
      && (unsigned int)RegGetAllocatedValue(phkResult, L"Level", &a5, &v21)
      && v21 == 4
      && (unsigned int)RegGetAllocatedValue(phkResult, L"DriverMoved", &a6, &v21)
      && (unsigned int)RegGetAllocatedValue(phkResult, L"SplName", a4, &v21)
      && (v21 == 1 || v21 == 7) )
    {
      if ( *(_DWORD *)a5 == 2
        || (*(_DWORD *)a5 == 3
         || (*(_DWORD *)a5 == 4
          || (*(_DWORD *)a5 == 6
           || *(_DWORD *)a5 == 8
           && (v20 = (unsigned __int8 *)(v12 + 168),
               (unsigned int)RegGetAllocatedValue(phkResult, L"Print Processor", (unsigned __int8 **)(v12 + 136), &v21))
           && (unsigned int)RegGetAllocatedValue(phkResult, L"VendorSetup", (unsigned __int8 **)(v12 + 144), &v21)
           && (unsigned int)RegGetAllocatedValue(phkResult, L"ColorProfiles", (unsigned __int8 **)(v12 + 152), &v21)
           && (unsigned int)RegGetAllocatedValue(phkResult, L"InfPath", (unsigned __int8 **)(v12 + 160), &v21)
           && (unsigned int)RegGetAllocatedValue(phkResult, L"PrinterDriverAttributes", &v20, &v21)
           && (unsigned int)RegGetAllocatedValue(phkResult, L"CoreDependencies", (unsigned __int8 **)(v12 + 176), &v21)
           && (cchName = 8, !RegQueryValueExW(phkResult, L"MinInboxDriverVerDate", 0, 0, (LPBYTE)(v12 + 184), &cchName))
           && (cchName = 8,
               !RegQueryValueExW(phkResult, L"MinInboxDriverVerVersion", 0, 0, (LPBYTE)(v12 + 192), &cchName)))
          && (cchName = 8, !RegQueryValueExW(phkResult, L"ftDriverDate", 0, 0, (LPBYTE)(v12 + 88), &cchName))
          && (cchName = 8, !RegQueryValueExW(phkResult, L"dwlDriverVersion", 0, 0, (LPBYTE)(v12 + 96), &cchName))
          && (unsigned int)RegGetAllocatedValue(phkResult, L"pszMfgName", (unsigned __int8 **)(v12 + 104), &v21)
          && (unsigned int)RegGetAllocatedValue(phkResult, L"pszOEMUrl", (unsigned __int8 **)(v12 + 112), &v21)
          && (unsigned int)RegGetAllocatedValue(phkResult, L"pszHardwareID", (unsigned __int8 **)(v12 + 120), &v21)
          && (unsigned int)RegGetAllocatedValue(phkResult, L"pszProvider", (unsigned __int8 **)(v12 + 128), &v21))
         && (unsigned int)RegGetAllocatedValue(phkResult, L"pszzPreviousNames", (unsigned __int8 **)(v12 + 80), &v21))
        && (unsigned int)RegGetAllocatedValue(phkResult, L"pDefaultDataType", (unsigned __int8 **)(v12 + 72), &v21)
        && (unsigned int)RegGetAllocatedValue(phkResult, L"pMonitorName", (unsigned __int8 **)(v12 + 64), &v21)
        && (unsigned int)RegGetAllocatedValue(phkResult, L"pDependentFiles", (unsigned __int8 **)(v12 + 56), &v21)
        && (unsigned int)RegGetAllocatedValue(phkResult, L"pHelpFile", (unsigned __int8 **)(v12 + 48), &v21) )
      {
        v20 = (unsigned __int8 *)v12;
        if ( (unsigned int)RegGetAllocatedValue(phkResult, L"pConfigFile", (unsigned __int8 **)(v12 + 40), &v21) )
        {
          if ( (unsigned int)RegGetAllocatedValue(phkResult, L"pDataFile", (unsigned __int8 **)(v12 + 32), &v21)
            && (unsigned int)RegGetAllocatedValue(phkResult, L"pDriverPath", (unsigned __int8 **)(v12 + 24), &v21)
            && (unsigned int)RegGetAllocatedValue(phkResult, L"pName", (unsigned __int8 **)(v12 + 8), &v21)
            && (unsigned int)RegGetAllocatedValue(phkResult, L"pEnvironment", (unsigned __int8 **)(v12 + 16), &v21)
            && (unsigned int)RegGetAllocatedValue(phkResult, L"cVersion", &v20, &v21) )
          {
            v17 = a7;
            *a3 = v14;
            *v17 = (struct _DRIVER_INFO_8W *)v12;
            goto LABEL_50;
          }
        }
      }
    }
  }
LABEL_46:
  v16 = 0;
  FreeDriverInfo8((struct _DRIVER_INFO_8W *)v12);
  if ( *a4 )
  {
    DllFreeSplMem(*a4);
    *a4 = 0;
  }
  if ( v14 )
    DllFreeSplMem(v14);
LABEL_50:
  if ( phkResult )
    RegCloseKey(phkResult);
  return v16;
}

```

## disassembly

```asm
0x1800288e4  mov     [rsp-38h+arg_0], rbx
0x1800288e9  push    rbp
0x1800288ea  push    rsi
0x1800288eb  push    rdi
0x1800288ec  push    r12
0x1800288ee  push    r13
0x1800288f0  push    r14
0x1800288f2  push    r15
0x1800288f4  mov     rbp, rsp
0x1800288f7  sub     rsp, 60h
0x1800288fb  mov     rax, [rbp+arg_30]
0x1800288ff  xor     r15d, r15d
0x180028902  mov     rsi, rcx
0x180028905  mov     [rbp+arg_10], r15d
0x180028909  mov     ecx, 0C8h
0x18002890e  mov     [rbp+phkResult], r15
0x180028912  mov     r12, r9
0x180028915  mov     [r9], r15
0x180028918  mov     [rax], r15
0x18002891b  mov     r13, r8
0x18002891e  mov     r14d, edx
0x180028921  mov     [r8], r15
0x180028924  mov     [rbp+cchName], 105h
0x18002892b  call    cs:__imp_DllAllocSplMem
0x180028931  mov     rbx, rax
0x180028934  test    rax, rax
0x180028937  jz      loc_180028E65
0x18002893d  mov     ecx, [rbp+cchName]
0x180028940  add     ecx, ecx
0x180028942  call    cs:__imp_DllAllocSplMem
0x180028948  mov     rdi, rax
0x18002894b  test    rax, rax
0x18002894e  jz      loc_180028E67
0x180028954  mov     [rsp+60h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180028959  lea     r9, [rbp+cchName]; lpcchName
0x18002895d  mov     [rsp+60h+lpcchClass], r15; lpcchClass
0x180028962  mov     r8, rax; lpName
0x180028965  mov     [rsp+60h+lpClass], r15; lpClass
0x18002896a  mov     edx, r14d; dwIndex
0x18002896d  mov     rcx, rsi; hKey
0x180028970  mov     [rsp+60h+lpReserved], r15; lpReserved
0x180028975  call    cs:__imp_RegEnumKeyExW
0x18002897b  mov     r15d, 1
0x180028981  cmp     eax, 0EAh
0x180028986  jnz     short loc_1800289D7
0x180028988  mov     rcx, rdi
0x18002898b  call    cs:__imp_DllFreeSplMem
0x180028991  mov     ecx, [rbp+cchName]
0x180028994  add     ecx, r15d
0x180028997  mov     [rbp+cchName], ecx
0x18002899a  add     ecx, ecx
0x18002899c  call    cs:__imp_DllAllocSplMem
0x1800289a2  mov     rdi, rax
0x1800289a5  xor     eax, eax
0x1800289a7  test    rdi, rdi
0x1800289aa  jz      loc_180028E67
0x1800289b0  mov     [rsp+60h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800289b5  lea     r9, [rbp+cchName]; lpcchName
0x1800289b9  mov     [rsp+60h+lpcchClass], rax; lpcchClass
0x1800289be  mov     r8, rdi; lpName
0x1800289c1  mov     [rsp+60h+lpClass], rax; lpClass
0x1800289c6  mov     edx, r14d; dwIndex
0x1800289c9  mov     rcx, rsi; hKey
0x1800289cc  mov     [rsp+60h+lpReserved], rax; lpReserved
0x1800289d1  call    cs:__imp_RegEnumKeyExW
0x1800289d7  test    eax, eax
0x1800289d9  jnz     loc_180028E67
0x1800289df  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800289e8  lea     rax, [rbp+phkResult]
0x1800289ec  mov     [rsp+60h+lpftLastWriteTime], rax; phkResult
0x1800289f1  xor     r9d, r9d; lpClass
0x1800289f4  mov     [rsp+60h+lpcchClass], 0; lpSecurityAttributes
0x1800289fd  xor     r8d, r8d; Reserved
0x180028a00  mov     dword ptr [rsp+60h+lpClass], 20019h; samDesired
0x180028a08  mov     rdx, rdi; lpSubKey
0x180028a0b  mov     rcx, rsi; hKey
0x180028a0e  mov     dword ptr [rsp+60h+lpReserved], 0; dwOptions
0x180028a16  call    cs:__imp_RegCreateKeyExW
0x180028a1c  test    eax, eax
0x180028a1e  jnz     loc_180028E67
0x180028a24  mov     rcx, [rbp+phkResult]; void *
0x180028a28  lea     r9, [rbp+arg_10]; unsigned int *
0x180028a2c  lea     r8, [rbp+arg_20]; unsigned __int8 **
0x180028a30  lea     rdx, aLevel; "Level"
0x180028a37  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028a3c  test    eax, eax
0x180028a3e  jz      loc_180028E67
0x180028a44  cmp     [rbp+arg_10], 4
0x180028a48  jnz     loc_180028E67
0x180028a4e  mov     rcx, [rbp+phkResult]; void *
0x180028a52  lea     r9, [rbp+arg_10]; unsigned int *
0x180028a56  lea     r8, [rbp+arg_28]; unsigned __int8 **
0x180028a5a  lea     rdx, aDrivermoved; "DriverMoved"
0x180028a61  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028a66  test    eax, eax
0x180028a68  jz      loc_180028E67
0x180028a6e  mov     rcx, [rbp+phkResult]; void *
0x180028a72  lea     r9, [rbp+arg_10]; unsigned int *
0x180028a76  mov     r8, r12; unsigned __int8 **
0x180028a79  lea     rdx, aSplname; "SplName"
0x180028a80  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028a85  test    eax, eax
0x180028a87  jz      loc_180028E67
0x180028a8d  cmp     [rbp+arg_10], r15d
0x180028a91  jz      short loc_180028A9D
0x180028a93  cmp     [rbp+arg_10], 7
0x180028a97  jnz     loc_180028E67
0x180028a9d  mov     rcx, [rbp+arg_20]
0x180028aa1  mov     edx, [rcx]
0x180028aa3  sub     edx, 2
0x180028aa6  jz      loc_180028DA8
0x180028aac  sub     edx, r15d
0x180028aaf  jz      loc_180028D28
0x180028ab5  sub     edx, r15d
0x180028ab8  jz      loc_180028D08
0x180028abe  mov     esi, 8
0x180028ac3  sub     edx, 2
0x180028ac6  jz      loc_180028C1D
0x180028acc  cmp     edx, 2
0x180028acf  jnz     loc_180028E67
0x180028ad5  mov     rcx, [rbp+phkResult]; void *
0x180028ad9  lea     rax, [rbx+0A8h]
0x180028ae0  lea     r8, [rbx+88h]; unsigned __int8 **
0x180028ae7  mov     [rbp+var_8], rax
0x180028aeb  lea     r9, [rbp+arg_10]; unsigned int *
0x180028aef  lea     rdx, szPrintProcessor; "Print Processor"
0x180028af6  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028afb  test    eax, eax
0x180028afd  jz      loc_180028E67
0x180028b03  mov     rcx, [rbp+phkResult]; void *
0x180028b07  lea     r8, [rbx+90h]; unsigned __int8 **
0x180028b0e  lea     r9, [rbp+arg_10]; unsigned int *
0x180028b12  lea     rdx, szVendorSetup; "VendorSetup"
0x180028b19  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028b1e  test    eax, eax
0x180028b20  jz      loc_180028E67
0x180028b26  mov     rcx, [rbp+phkResult]; void *
0x180028b2a  lea     r8, [rbx+98h]; unsigned __int8 **
0x180028b31  lea     r9, [rbp+arg_10]; unsigned int *
0x180028b35  lea     rdx, szColorProfiles; "ColorProfiles"
0x180028b3c  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028b41  test    eax, eax
0x180028b43  jz      loc_180028E67
0x180028b49  mov     rcx, [rbp+phkResult]; void *
0x180028b4d  lea     r8, [rbx+0A0h]; unsigned __int8 **
0x180028b54  lea     r9, [rbp+arg_10]; unsigned int *
0x180028b58  lea     rdx, szInfPath; "InfPath"
0x180028b5f  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028b64  test    eax, eax
0x180028b66  jz      loc_180028E67
0x180028b6c  mov     rcx, [rbp+phkResult]; void *
0x180028b70  lea     r9, [rbp+arg_10]; unsigned int *
0x180028b74  lea     r8, [rbp+var_8]; unsigned __int8 **
0x180028b78  lea     rdx, szPrinterDriverAttributes; "PrinterDriverAttributes"
0x180028b7f  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028b84  test    eax, eax
0x180028b86  jz      loc_180028E67
0x180028b8c  mov     rcx, [rbp+phkResult]; void *
0x180028b90  lea     r8, [rbx+0B0h]; unsigned __int8 **
0x180028b97  lea     r9, [rbp+arg_10]; unsigned int *
0x180028b9b  lea     rdx, szCoreDependencies; "CoreDependencies"
0x180028ba2  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028ba7  test    eax, eax
0x180028ba9  jz      loc_180028E67
0x180028baf  lea     rcx, [rbp+cchName]
0x180028bb3  mov     [rbp+cchName], esi
0x180028bb6  mov     [rsp+60h+lpClass], rcx; lpcbData
0x180028bbb  lea     rax, [rbx+0B8h]
0x180028bc2  mov     rcx, [rbp+phkResult]; hKey
0x180028bc6  lea     rdx, szMinInboxDriverVerDate; "MinInboxDriverVerDate"
0x180028bcd  xor     r9d, r9d; lpType
0x180028bd0  mov     [rsp+60h+lpReserved], rax; lpData
0x180028bd5  xor     r8d, r8d; lpReserved
0x180028bd8  call    cs:__imp_RegQueryValueExW
0x180028bde  test    eax, eax
0x180028be0  jnz     loc_180028E67
0x180028be6  lea     rcx, [rbp+cchName]
0x180028bea  mov     [rbp+cchName], esi
0x180028bed  mov     [rsp+60h+lpClass], rcx; lpcbData
0x180028bf2  lea     rax, [rbx+0C0h]
0x180028bf9  mov     rcx, [rbp+phkResult]; hKey
0x180028bfd  lea     rdx, szMinInboxDriverVerVersion; "MinInboxDriverVerVersion"
0x180028c04  xor     r9d, r9d; lpType
0x180028c07  mov     [rsp+60h+lpReserved], rax; lpData
0x180028c0c  xor     r8d, r8d; lpReserved
0x180028c0f  call    cs:__imp_RegQueryValueExW
0x180028c15  test    eax, eax
0x180028c17  jnz     loc_180028E67
0x180028c1d  lea     rcx, [rbp+cchName]
0x180028c21  mov     [rbp+cchName], esi
0x180028c24  mov     [rsp+60h+lpClass], rcx; lpcbData
0x180028c29  lea     rax, [rbx+58h]
0x180028c2d  mov     rcx, [rbp+phkResult]; hKey
0x180028c31  lea     rdx, aFtdriverdate; "ftDriverDate"
0x180028c38  xor     r9d, r9d; lpType
0x180028c3b  mov     [rsp+60h+lpReserved], rax; lpData
0x180028c40  xor     r8d, r8d; lpReserved
0x180028c43  call    cs:__imp_RegQueryValueExW
0x180028c49  test    eax, eax
0x180028c4b  jnz     loc_180028E67
0x180028c51  lea     rcx, [rbp+cchName]
0x180028c55  mov     [rbp+cchName], esi
0x180028c58  mov     [rsp+60h+lpClass], rcx; lpcbData
0x180028c5d  lea     rax, [rbx+60h]
0x180028c61  mov     rcx, [rbp+phkResult]; hKey
0x180028c65  lea     rdx, aDwldriverversi; "dwlDriverVersion"
0x180028c6c  xor     r9d, r9d; lpType
0x180028c6f  mov     [rsp+60h+lpReserved], rax; lpData
0x180028c74  xor     r8d, r8d; lpReserved
0x180028c77  call    cs:__imp_RegQueryValueExW
0x180028c7d  test    eax, eax
0x180028c7f  jnz     loc_180028E67
0x180028c85  mov     rcx, [rbp+phkResult]; void *
0x180028c89  lea     r8, [rbx+68h]; unsigned __int8 **
0x180028c8d  lea     r9, [rbp+arg_10]; unsigned int *
0x180028c91  lea     rdx, aPszmfgname; "pszMfgName"
0x180028c98  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028c9d  test    eax, eax
0x180028c9f  jz      loc_180028E67
0x180028ca5  mov     rcx, [rbp+phkResult]; void *
0x180028ca9  lea     r8, [rbx+70h]; unsigned __int8 **
0x180028cad  lea     r9, [rbp+arg_10]; unsigned int *
0x180028cb1  lea     rdx, aPszoemurl; "pszOEMUrl"
0x180028cb8  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028cbd  test    eax, eax
0x180028cbf  jz      loc_180028E67
0x180028cc5  mov     rcx, [rbp+phkResult]; void *
0x180028cc9  lea     r8, [rbx+78h]; unsigned __int8 **
0x180028ccd  lea     r9, [rbp+arg_10]; unsigned int *
0x180028cd1  lea     rdx, aPszhardwareid; "pszHardwareID"
0x180028cd8  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028cdd  test    eax, eax
0x180028cdf  jz      loc_180028E67
0x180028ce5  mov     rcx, [rbp+phkResult]; void *
0x180028ce9  lea     r8, [rbx+80h]; unsigned __int8 **
0x180028cf0  lea     r9, [rbp+arg_10]; unsigned int *
0x180028cf4  lea     rdx, aPszprovider; "pszProvider"
0x180028cfb  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028d00  test    eax, eax
0x180028d02  jz      loc_180028E67
0x180028d08  mov     rcx, [rbp+phkResult]; void *
0x180028d0c  lea     r8, [rbx+50h]; unsigned __int8 **
0x180028d10  lea     r9, [rbp+arg_10]; unsigned int *
0x180028d14  lea     rdx, aPszzpreviousna; "pszzPreviousNames"
0x180028d1b  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028d20  test    eax, eax
0x180028d22  jz      loc_180028E67
0x180028d28  mov     rcx, [rbp+phkResult]; void *
0x180028d2c  lea     r8, [rbx+48h]; unsigned __int8 **
0x180028d30  lea     r9, [rbp+arg_10]; unsigned int *
0x180028d34  lea     rdx, aPdefaultdataty; "pDefaultDataType"
0x180028d3b  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028d40  test    eax, eax
0x180028d42  jz      loc_180028E67
0x180028d48  mov     rcx, [rbp+phkResult]; void *
0x180028d4c  lea     r8, [rbx+40h]; unsigned __int8 **
0x180028d50  lea     r9, [rbp+arg_10]; unsigned int *
0x180028d54  lea     rdx, aPmonitorname; "pMonitorName"
0x180028d5b  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028d60  test    eax, eax
0x180028d62  jz      loc_180028E67
0x180028d68  mov     rcx, [rbp+phkResult]; void *
0x180028d6c  lea     r8, [rbx+38h]; unsigned __int8 **
0x180028d70  lea     r9, [rbp+arg_10]; unsigned int *
0x180028d74  lea     rdx, aPdependentfile_0; "pDependentFiles"
0x180028d7b  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028d80  test    eax, eax
0x180028d82  jz      loc_180028E67
0x180028d88  mov     rcx, [rbp+phkResult]; void *
0x180028d8c  lea     r8, [rbx+30h]; unsigned __int8 **
0x180028d90  lea     r9, [rbp+arg_10]; unsigned int *
0x180028d94  lea     rdx, aPhelpfile; "pHelpFile"
0x180028d9b  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028da0  test    eax, eax
0x180028da2  jz      loc_180028E67
0x180028da8  mov     rcx, [rbp+phkResult]; void *
0x180028dac  lea     r8, [rbx+28h]; unsigned __int8 **
0x180028db0  lea     r9, [rbp+arg_10]; unsigned int *
0x180028db4  mov     [rbp+var_8], rbx
0x180028db8  lea     rdx, aPconfigfile; "pConfigFile"
0x180028dbf  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028dc4  test    eax, eax
0x180028dc6  jz      loc_180028E67
0x180028dcc  mov     rcx, [rbp+phkResult]; void *
0x180028dd0  lea     r8, [rbx+20h]; unsigned __int8 **
0x180028dd4  lea     r9, [rbp+arg_10]; unsigned int *
0x180028dd8  lea     rdx, aPdatafile; "pDataFile"
0x180028ddf  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028de4  test    eax, eax
0x180028de6  jz      short loc_180028E67
0x180028de8  mov     rcx, [rbp+phkResult]; void *
0x180028dec  lea     r8, [rbx+18h]; unsigned __int8 **
0x180028df0  lea     r9, [rbp+arg_10]; unsigned int *
0x180028df4  lea     rdx, aPdriverpath; "pDriverPath"
0x180028dfb  call    ?RegGetAllocatedValue@@YAHPEAXPEBGPEAPEAEPEAK@Z; RegGetAllocatedValue(void *,ushort const *,uchar * *,ulong *)
0x180028e00  test    eax, eax
0x180028e02  jz      short loc_180028E67
0x180028e04  mov     rcx, [rbp+phkResult]; void *
0x180028e08  lea     r8, [rbx+8]; unsigned __int8 **
0x180028e0c  lea     r9, [rbp+arg_10]; unsigned int *
  ... truncated ...
```

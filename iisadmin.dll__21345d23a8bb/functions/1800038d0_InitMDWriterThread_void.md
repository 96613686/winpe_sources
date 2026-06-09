# InitMDWriterThread(void *)

- ea: `0x1800038d0`
- end: `0x180003b25`
- name: `?InitMDWriterThread@@YAKPEAX@Z`
- size: `597`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x180001008`
- `0x1800038d0`
- `0x180003b2c`
- `0x180005010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000398d`
- `ADVAPI32!RegCloseKey` at `0x1800039e2`
- `ADVAPI32!RegCloseKey` at `0x18000398d`
- `ADVAPI32!RegCloseKey` at `0x1800039e2`
- `ADVAPI32!RegQueryValueExA` at `0x18000396e`
- `ADVAPI32!RegQueryValueExA` at `0x1800039c3`
- `ADVAPI32!RegQueryValueExA` at `0x18000396e`
- `ADVAPI32!RegQueryValueExA` at `0x1800039c3`
- `ADVAPI32!RegOpenKeyExA` at `0x180003935`
- `ADVAPI32!RegOpenKeyExA` at `0x180003935`
- `ole32!CoInitializeEx` at `0x180003905`
- `ole32!CoInitializeEx` at `0x180003905`
- `ole32!CoUninitialize` at `0x180003b12`
- `ole32!CoUninitialize` at `0x180003b12`
- `IisRTL!PuDbgPrint` at `0x180003aa2`
- `IisRTL!PuDbgPrint` at `0x180003b0c`
- `IisRTL!PuDbgPrint` at `0x180003aa2`
- `IisRTL!PuDbgPrint` at `0x180003b0c`

## string_xrefs

- `0x180003a96`: `inetsrv\iis\mb\iisadmin\mdwriter.cxx`
- `0x180003b05`: `inetsrv\iis\mb\iisadmin\mdwriter.cxx`
- `0x180003aec`: `Error on creating the writer object, out of memory\n`
- `0x180003a8f`: `InitMDWriterThread`
- `0x180003af3`: `InitMDWriterThread`
- `0x180003a2e`: `Error on initializing the writer object\n`
- `0x180003a7b`: `Error on subscribing the writer object\n`

## pseudocode

```c
__int64 __fastcall InitMDWriterThread(LPVOID lpThreadParameter)
{
  HRESULT v1; // ebx
  struct CIISVssWriter *v2; // rax
  __int64 v3; // rcx
  BYTE v5[8]; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+18h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  *(_DWORD *)v5 = 0;
  v1 = CoInitializeEx(0, 0);
  if ( v1 >= 0 )
  {
    if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\Setup", 0, 1u, &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExA(hKey, "SystemSetupInProgress", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4
        && cbData == 4
        && Data
        || (cbData = 4, !RegQueryValueExA(hKey, "UpgradeInProgress", 0, &Type, v5, &cbData))
        && Type == 4
        && cbData == 4
        && *(_DWORD *)v5 )
      {
        RegCloseKey(hKey);
        goto LABEL_27;
      }
      RegCloseKey(hKey);
    }
    v2 = (struct CIISVssWriter *)operator new(0x18u);
    if ( !v2 )
    {
      g_pIISVssWriter = 0;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cxx",
          532,
          "InitMDWriterThread",
          "Error on creating the writer object, out of memory\n");
      goto LABEL_27;
    }
    *((_QWORD *)v2 + 1) = 0;
    *(_QWORD *)v2 = &CIISVssWriter::`vftable';
    *((_QWORD *)v2 + 2) = 0;
    g_pIISVssWriter = v2;
    if ( !(unsigned int)CIISVssWriter::Initialize((CIISVssWriter *)&CIISVssWriter::`vftable') )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cxx",
          546,
          "InitMDWriterThread",
          "Error on initializing the writer object\n");
LABEL_22:
      if ( g_pIISVssWriter )
        (**(void (__fastcall ***)(struct CIISVssWriter *, __int64))g_pIISVssWriter)(g_pIISVssWriter, 1);
      g_pIISVssWriter = 0;
      goto LABEL_27;
    }
    v3 = *((_QWORD *)g_pIISVssWriter + 1);
    if ( !v3 || (*(int (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v3 + 32LL))(v3, 0, 6) < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cxx",
          562,
          "InitMDWriterThread",
          "Error on subscribing the writer object\n");
      goto LABEL_22;
    }
    g_fWriterSubscribed = 1;
LABEL_27:
    CoUninitialize();
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800038d0  mov     [rsp-8+arg_0], rbx
0x1800038d5  push    rbp
0x1800038d6  mov     rbp, rsp
0x1800038d9  sub     rsp, 40h
0x1800038dd  xor     edx, edx; dwCoInit
0x1800038df  mov     [rbp+hKey], 0
0x1800038e7  xor     ecx, ecx; pvReserved
0x1800038e9  mov     [rbp+Type], 0
0x1800038f0  mov     [rbp+cbData], 0
0x1800038f7  mov     [rbp+Data], 0
0x1800038fe  mov     dword ptr [rbp+var_10], 0
0x180003905  call    cs:__imp_CoInitializeEx
0x18000390b  mov     ebx, eax
0x18000390d  test    eax, eax
0x18000390f  js      loc_180003B18
0x180003915  lea     rax, [rbp+hKey]
0x180003919  mov     r9d, 1; samDesired
0x18000391f  xor     r8d, r8d; ulOptions
0x180003922  mov     [rsp+40h+phkResult], rax; phkResult
0x180003927  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18000392e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003935  call    cs:__imp_RegOpenKeyExA
0x18000393b  test    eax, eax
0x18000393d  jnz     loc_1800039E8
0x180003943  mov     rcx, [rbp+hKey]; hKey
0x180003947  lea     rax, [rbp+cbData]
0x18000394b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180003950  lea     r9, [rbp+Type]; lpType
0x180003954  lea     rax, [rbp+Data]
0x180003958  mov     [rbp+cbData], 4
0x18000395f  xor     r8d, r8d; lpReserved
0x180003962  mov     [rsp+40h+phkResult], rax; lpData
0x180003967  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x18000396e  call    cs:__imp_RegQueryValueExA
0x180003974  test    eax, eax
0x180003976  jnz     short loc_180003998
0x180003978  cmp     [rbp+Type], 4
0x18000397c  jnz     short loc_180003998
0x18000397e  cmp     [rbp+cbData], 4
0x180003982  jnz     short loc_180003998
0x180003984  cmp     [rbp+Data], eax
0x180003987  jz      short loc_180003998
0x180003989  mov     rcx, [rbp+hKey]; hKey
0x18000398d  call    cs:__imp_RegCloseKey
0x180003993  jmp     loc_180003B12
0x180003998  mov     rcx, [rbp+hKey]; hKey
0x18000399c  lea     rax, [rbp+cbData]
0x1800039a0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800039a5  lea     r9, [rbp+Type]; lpType
0x1800039a9  lea     rax, [rbp+var_10]
0x1800039ad  mov     [rbp+cbData], 4
0x1800039b4  xor     r8d, r8d; lpReserved
0x1800039b7  mov     [rsp+40h+phkResult], rax; lpData
0x1800039bc  lea     rdx, aUpgradeinprogr; "UpgradeInProgress"
0x1800039c3  call    cs:__imp_RegQueryValueExA
0x1800039c9  test    eax, eax
0x1800039cb  jnz     short loc_1800039DE
0x1800039cd  cmp     [rbp+Type], 4
0x1800039d1  jnz     short loc_1800039DE
0x1800039d3  cmp     [rbp+cbData], 4
0x1800039d7  jnz     short loc_1800039DE
0x1800039d9  cmp     dword ptr [rbp+var_10], eax
0x1800039dc  jnz     short loc_180003989
0x1800039de  mov     rcx, [rbp+hKey]; hKey
0x1800039e2  call    cs:__imp_RegCloseKey
0x1800039e8  mov     ecx, 18h; Size
0x1800039ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800039f2  test    rax, rax
0x1800039f5  jz      loc_180003AD1
0x1800039fb  lea     rcx, ??_7CIISVssWriter@@6B@; this
0x180003a02  mov     qword ptr [rax+8], 0
0x180003a0a  mov     [rax], rcx
0x180003a0d  mov     qword ptr [rax+10h], 0
0x180003a15  mov     cs:?g_pIISVssWriter@@3PEAVCIISVssWriter@@EA, rax; CIISVssWriter * g_pIISVssWriter
0x180003a1c  call    ?Initialize@CIISVssWriter@@QEAAHXZ; CIISVssWriter::Initialize(void)
0x180003a21  test    eax, eax
0x180003a23  jnz     short loc_180003A3D
0x180003a25  test    byte ptr cs:g_dwDebugFlags, 3
0x180003a2c  jz      short loc_180003AA8
0x180003a2e  lea     rax, aErrorOnInitial; "Error on initializing the writer object"...
0x180003a35  mov     r8d, 222h
0x180003a3b  jmp     short loc_180003A88
0x180003a3d  mov     rax, cs:?g_pIISVssWriter@@3PEAVCIISVssWriter@@EA; CIISVssWriter * g_pIISVssWriter
0x180003a44  mov     rcx, [rax+8]
0x180003a48  test    rcx, rcx
0x180003a4b  jz      short loc_180003A72
0x180003a4d  mov     rax, [rcx]
0x180003a50  xor     edx, edx
0x180003a52  mov     rax, [rax+20h]
0x180003a56  lea     r8d, [rdx+6]
0x180003a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a5f  test    eax, eax
0x180003a61  js      short loc_180003A72
0x180003a63  mov     cs:?g_fWriterSubscribed@@3HA, 1; int g_fWriterSubscribed
0x180003a6d  jmp     loc_180003B12
0x180003a72  test    byte ptr cs:g_dwDebugFlags, 3
0x180003a79  jz      short loc_180003AA8
0x180003a7b  lea     rax, aErrorOnSubscri; "Error on subscribing the writer object"...
0x180003a82  mov     r8d, 232h
0x180003a88  mov     rcx, cs:g_pDebug
0x180003a8f  lea     r9, aInitmdwriterth; "InitMDWriterThread"
0x180003a96  lea     rdx, aInetsrvIisMbIi; "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cx"...
0x180003a9d  mov     [rsp+40h+phkResult], rax
0x180003aa2  call    cs:__imp_PuDbgPrint
0x180003aa8  mov     rcx, cs:?g_pIISVssWriter@@3PEAVCIISVssWriter@@EA; CIISVssWriter * g_pIISVssWriter
0x180003aaf  test    rcx, rcx
0x180003ab2  jz      short loc_180003AC4
0x180003ab4  mov     rax, [rcx]
0x180003ab7  mov     edx, 1
0x180003abc  mov     rax, [rax]
0x180003abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac4  mov     cs:?g_pIISVssWriter@@3PEAVCIISVssWriter@@EA, 0; CIISVssWriter * g_pIISVssWriter
0x180003acf  jmp     short loc_180003B12
0x180003ad1  test    byte ptr cs:g_dwDebugFlags, 3
0x180003ad8  mov     cs:?g_pIISVssWriter@@3PEAVCIISVssWriter@@EA, 0; CIISVssWriter * g_pIISVssWriter
0x180003ae3  jz      short loc_180003B12
0x180003ae5  mov     rcx, cs:g_pDebug
0x180003aec  lea     rax, aErrorOnCreatin; "Error on creating the writer object, ou"...
0x180003af3  lea     r9, aInitmdwriterth; "InitMDWriterThread"
0x180003afa  mov     [rsp+40h+phkResult], rax
0x180003aff  mov     r8d, 214h
0x180003b05  lea     rdx, aInetsrvIisMbIi; "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cx"...
0x180003b0c  call    cs:__imp_PuDbgPrint
0x180003b12  call    cs:__imp_CoUninitialize
0x180003b18  mov     eax, ebx
0x180003b1a  mov     rbx, [rsp+40h+arg_0]
0x180003b1f  add     rsp, 40h
0x180003b23  pop     rbp
0x180003b24  retn
```

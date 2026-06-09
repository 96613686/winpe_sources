# DllRegisterServer()

- ea: `0x10045b50`
- end: `0x10045d66`
- name: `_DllRegisterServer@0`
- size: `534`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x10045b50`
- `0x10047820`
- `0x10120150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045b80`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045c3e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045cb5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045b80`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045c3e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045cb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045c06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045d1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045d26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045c06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045d1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045d26`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045bbe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045be4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045bfd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045c77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045c92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045cee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045d14`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045bbe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045be4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045bfd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045c77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045c92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045cee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045d14`

## string_xrefs

- `0x10045c6f`: `CompactByPKey`
- `0x10045c8a`: `PrevFormatCompactWithUNICODECompression`
- `0x10045bdc`: `UserCommitSync`
- `0x10045bf5`: `ImplicitCommitSync`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  int v0; // esi
  int v1; // edi
  int v2; // esi
  STRSAFE_LPSTR *v3; // ecx
  DWORD v5; // [esp+8h] [ebp-10h] BYREF
  BYTE Data[4]; // [esp+Ch] [ebp-Ch] BYREF
  DWORD dwDisposition; // [esp+10h] [ebp-8h] BYREF
  HKEY phkResult; // [esp+14h] [ebp-4h] BYREF

  phkResult = 0;
  if ( RegCreateKeyExA(
         HKEY_LOCAL_MACHINE,
         "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines\\Jet 4.0",
         0,
         0,
         0,
         0x20006u,
         0,
         &phkResult,
         &dwDisposition) )
  {
    return -2147467259;
  }
  v0 = 0;
  if ( lpValueName )
  {
    do
    {
      *(_DWORD *)Data = dword_1012C054[2 * v0];
      RegSetValueExA(phkResult, (&lpValueName)[2 * v0++], 0, 4u, Data, 4u);
    }
    while ( (&lpValueName)[2 * v0] );
  }
  RegSetValueExA(phkResult, "UserCommitSync", 0, 1u, "yes", 4u);
  RegSetValueExA(phkResult, "ImplicitCommitSync", 0, 1u, "no", 3u);
  RegCloseKey(phkResult);
  phkResult = 0;
  *(_DWORD *)Data = 0;
  v1 = 1;
  if ( RegCreateKeyExA(
         HKEY_LOCAL_MACHINE,
         "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &phkResult,
         &v5) )
  {
    return -2147467259;
  }
  JetRegSetValueExW(phkResult, L"SystemDB", 0, 1u, (BYTE *)L"system.mdb", 0x14u);
  dwDisposition = 1;
  RegSetValueExA(phkResult, "CompactByPKey", 0, 4u, (const BYTE *)&dwDisposition, 4u);
  dwDisposition = 1;
  RegSetValueExA(phkResult, "PrevFormatCompactWithUNICODECompression", 0, 4u, (const BYTE *)&dwDisposition, 4u);
  if ( RegCreateKeyExA(phkResult, "ODBC", 0, 0, 0, 0x2001Fu, 0, (PHKEY)Data, &v5) )
  {
    v1 = 0;
  }
  else
  {
    v2 = 0;
    if ( ODBCDefaults )
    {
      do
      {
        dwDisposition = dword_10004334[2 * v2];
        RegSetValueExA(*(HKEY *)Data, (&ODBCDefaults)[2 * v2++], 0, 4u, (const BYTE *)&dwDisposition, 4u);
      }
      while ( (&ODBCDefaults)[2 * v2] );
    }
    RegSetValueExA(*(HKEY *)Data, "AttachableObjects", 0, 1u, "'TABLE','VIEW','SYSTEM TABLE','ALIAS','SYNONYM'", 0x2Fu);
    RegCloseKey(*(HKEY *)Data);
  }
  RegCloseKey(phkResult);
  if ( !v1 || !RegisterReplDefaults(v3, 0) )
    return -2147467259;
  else
    return 0;
}

```

## disassembly

```asm
0x10045b50  mov     edi, edi
0x10045b52  push    ebp
0x10045b53  mov     ebp, esp
0x10045b55  sub     esp, 10h
0x10045b58  push    esi
0x10045b59  push    edi
0x10045b5a  lea     eax, [ebp+dwDisposition]
0x10045b5d  mov     [ebp+phkResult], 0
0x10045b64  push    eax; lpdwDisposition
0x10045b65  lea     eax, [ebp+phkResult]
0x10045b68  push    eax; phkResult
0x10045b69  push    0; lpSecurityAttributes
0x10045b6b  push    20006h; samDesired
0x10045b70  push    0; dwOptions
0x10045b72  push    0; lpClass
0x10045b74  push    0; Reserved
0x10045b76  push    offset SubKey; "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines"...
0x10045b7b  push    80000002h; hKey
0x10045b80  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x10045b86  test    eax, eax
0x10045b88  jnz     loc_10045D52
0x10045b8e  xor     esi, esi
0x10045b90  cmp     lpValueName, esi
0x10045b96  jz      short loc_10045BD1
0x10045b98  nop     dword ptr [eax+eax+00000000h]
0x10045ba0  mov     eax, dword_1012C054[esi*8]
0x10045ba7  push    4; cbData
0x10045ba9  mov     dword ptr [ebp+Data], eax
0x10045bac  lea     eax, [ebp+Data]
0x10045baf  push    eax; lpData
0x10045bb0  push    4; dwType
0x10045bb2  push    0; Reserved
0x10045bb4  push    lpValueName[esi*8]; lpValueName
0x10045bbb  push    [ebp+phkResult]; hKey
0x10045bbe  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045bc4  lea     esi, [esi+1]
0x10045bc7  cmp     lpValueName[esi*8], 0
0x10045bcf  jnz     short loc_10045BA0
0x10045bd1  push    4; cbData
0x10045bd3  push    offset Data; "yes"
0x10045bd8  push    1; dwType
0x10045bda  push    0; Reserved
0x10045bdc  push    offset ValueName; "UserCommitSync"
0x10045be1  push    [ebp+phkResult]; hKey
0x10045be4  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045bea  push    3; cbData
0x10045bec  push    offset aNo_0; "no"
0x10045bf1  push    1; dwType
0x10045bf3  push    0; Reserved
0x10045bf5  push    offset aImplicitcommit; "ImplicitCommitSync"
0x10045bfa  push    [ebp+phkResult]; hKey
0x10045bfd  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045c03  push    [ebp+phkResult]; hKey
0x10045c06  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10045c0c  lea     eax, [ebp+var_10]
0x10045c0f  mov     [ebp+phkResult], 0
0x10045c16  push    eax; lpdwDisposition
0x10045c17  lea     eax, [ebp+phkResult]
0x10045c1a  mov     dword ptr [ebp+Data], 0
0x10045c21  push    eax; phkResult
0x10045c22  push    0; lpSecurityAttributes
0x10045c24  push    2001Fh; samDesired
0x10045c29  push    0; dwOptions
0x10045c2b  push    0; lpClass
0x10045c2d  push    0; Reserved
0x10045c2f  push    offset _szDefaultJetTree; "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines"
0x10045c34  push    80000002h; hKey
0x10045c39  mov     edi, 1
0x10045c3e  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x10045c44  test    eax, eax
0x10045c46  jnz     loc_10045D52
0x10045c4c  push    14h; cbData
0x10045c4e  push    offset aSystemMdb; "system.mdb"
0x10045c53  push    edi; dwType
0x10045c54  push    eax; Reserved
0x10045c55  push    offset _wszSystemDB; "SystemDB"
0x10045c5a  push    [ebp+phkResult]; hKey
0x10045c5d  call    _JetRegSetValueExW@24; JetRegSetValueExW(x,x,x,x,x,x)
0x10045c62  push    4; cbData
0x10045c64  lea     eax, [ebp+dwDisposition]
0x10045c67  mov     [ebp+dwDisposition], edi
0x10045c6a  push    eax; lpData
0x10045c6b  push    4; dwType
0x10045c6d  push    0; Reserved
0x10045c6f  push    offset _szCompactByPKey; "CompactByPKey"
0x10045c74  push    [ebp+phkResult]; hKey
0x10045c77  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045c7d  push    4; cbData
0x10045c7f  lea     eax, [ebp+dwDisposition]
0x10045c82  mov     [ebp+dwDisposition], edi
0x10045c85  push    eax; lpData
0x10045c86  push    4; dwType
0x10045c88  push    0; Reserved
0x10045c8a  push    offset _szCompressOldText; "PrevFormatCompactWithUNICODECompression"
0x10045c8f  push    [ebp+phkResult]; hKey
0x10045c92  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045c98  lea     eax, [ebp+var_10]
0x10045c9b  push    eax; lpdwDisposition
0x10045c9c  lea     eax, [ebp+Data]
0x10045c9f  push    eax; phkResult
0x10045ca0  push    0; lpSecurityAttributes
0x10045ca2  push    2001Fh; samDesired
0x10045ca7  push    0; dwOptions
0x10045ca9  push    0; lpClass
0x10045cab  push    0; Reserved
0x10045cad  push    offset _szODBCSection; "ODBC"
0x10045cb2  push    [ebp+phkResult]; hKey
0x10045cb5  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x10045cbb  test    eax, eax
0x10045cbd  jz      short loc_10045CC3
0x10045cbf  xor     edi, edi
0x10045cc1  jmp     short loc_10045D23
0x10045cc3  xor     esi, esi
0x10045cc5  cmp     ds:_ODBCDefaults, esi
0x10045ccb  jz      short loc_10045D01
0x10045ccd  nop     dword ptr [eax]
0x10045cd0  mov     eax, ds:dword_10004334[esi*8]
0x10045cd7  push    4; cbData
0x10045cd9  mov     [ebp+dwDisposition], eax
0x10045cdc  lea     eax, [ebp+dwDisposition]
0x10045cdf  push    eax; lpData
0x10045ce0  push    4; dwType
0x10045ce2  push    0; Reserved
0x10045ce4  push    ds:_ODBCDefaults[esi*8]; lpValueName
0x10045ceb  push    dword ptr [ebp+Data]; hKey
0x10045cee  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045cf4  lea     esi, [esi+1]
0x10045cf7  cmp     ds:_ODBCDefaults[esi*8], 0
0x10045cff  jnz     short loc_10045CD0
0x10045d01  push    2Fh ; '/'; cbData
0x10045d03  push    offset _szDefaultAttObj; "'TABLE','VIEW','SYSTEM TABLE','ALIAS','"...
0x10045d08  push    1; dwType
0x10045d0a  push    0; Reserved
0x10045d0c  push    offset _szAttachableObjects; "AttachableObjects"
0x10045d11  push    dword ptr [ebp+Data]; hKey
0x10045d14  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045d1a  push    dword ptr [ebp+Data]; hKey
0x10045d1d  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10045d23  push    [ebp+phkResult]; hKey
0x10045d26  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10045d2c  test    edi, edi
0x10045d2e  jz      short loc_10045D52
0x10045d30  push    0; Stream
0x10045d32  call    _RegisterReplDefaults@4; RegisterReplDefaults(x)
0x10045d37  test    eax, eax
0x10045d39  jz      short loc_10045D52
0x10045d3b  mov     ecx, 1
0x10045d40  xor     edx, edx
0x10045d42  test    ecx, ecx
0x10045d44  mov     eax, 80004005h
0x10045d49  pop     edi
0x10045d4a  cmovnz  eax, edx
0x10045d4d  pop     esi
0x10045d4e  mov     esp, ebp
0x10045d50  pop     ebp
0x10045d51  retn
0x10045d52  xor     ecx, ecx
0x10045d54  xor     edx, edx
0x10045d56  test    ecx, ecx
0x10045d58  mov     eax, 80004005h
0x10045d5d  pop     edi
0x10045d5e  cmovnz  eax, edx
0x10045d61  pop     esi
0x10045d62  mov     esp, ebp
0x10045d64  pop     ebp
0x10045d65  retn
```

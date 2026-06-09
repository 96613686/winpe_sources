# DllRegisterServer()

- ea: `0x100459d0`
- end: `0x10045be6`
- name: `_DllRegisterServer@0`
- size: `534`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x100459d0`
- `0x100476a0`
- `0x1011ffa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045a00`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045abe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045b35`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045a00`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045abe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10045b35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045a86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045b9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045ba6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045a86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045b9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10045ba6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045a3e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045a64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045a7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045af7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045b12`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045b6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045b94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045a3e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045a64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045a7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045af7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045b12`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045b6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10045b94`

## string_xrefs

- `0x10045aef`: `CompactByPKey`
- `0x10045b0a`: `PrevFormatCompactWithUNICODECompression`
- `0x10045a5c`: `UserCommitSync`
- `0x10045a75`: `ImplicitCommitSync`

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
      *(_DWORD *)Data = dword_1012C03C[2 * v0];
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
        dwDisposition = dword_10004324[2 * v2];
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
0x100459d0  mov     edi, edi
0x100459d2  push    ebp
0x100459d3  mov     ebp, esp
0x100459d5  sub     esp, 10h
0x100459d8  push    esi
0x100459d9  push    edi
0x100459da  lea     eax, [ebp+dwDisposition]
0x100459dd  mov     [ebp+phkResult], 0
0x100459e4  push    eax; lpdwDisposition
0x100459e5  lea     eax, [ebp+phkResult]
0x100459e8  push    eax; phkResult
0x100459e9  push    0; lpSecurityAttributes
0x100459eb  push    20006h; samDesired
0x100459f0  push    0; dwOptions
0x100459f2  push    0; lpClass
0x100459f4  push    0; Reserved
0x100459f6  push    offset SubKey; "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines"...
0x100459fb  push    80000002h; hKey
0x10045a00  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x10045a06  test    eax, eax
0x10045a08  jnz     loc_10045BD2
0x10045a0e  xor     esi, esi
0x10045a10  cmp     lpValueName, esi
0x10045a16  jz      short loc_10045A51
0x10045a18  nop     dword ptr [eax+eax+00000000h]
0x10045a20  mov     eax, dword_1012C03C[esi*8]
0x10045a27  push    4; cbData
0x10045a29  mov     dword ptr [ebp+Data], eax
0x10045a2c  lea     eax, [ebp+Data]
0x10045a2f  push    eax; lpData
0x10045a30  push    4; dwType
0x10045a32  push    0; Reserved
0x10045a34  push    lpValueName[esi*8]; lpValueName
0x10045a3b  push    [ebp+phkResult]; hKey
0x10045a3e  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045a44  lea     esi, [esi+1]
0x10045a47  cmp     lpValueName[esi*8], 0
0x10045a4f  jnz     short loc_10045A20
0x10045a51  push    4; cbData
0x10045a53  push    offset Data; "yes"
0x10045a58  push    1; dwType
0x10045a5a  push    0; Reserved
0x10045a5c  push    offset ValueName; "UserCommitSync"
0x10045a61  push    [ebp+phkResult]; hKey
0x10045a64  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045a6a  push    3; cbData
0x10045a6c  push    offset aNo_0; "no"
0x10045a71  push    1; dwType
0x10045a73  push    0; Reserved
0x10045a75  push    offset aImplicitcommit; "ImplicitCommitSync"
0x10045a7a  push    [ebp+phkResult]; hKey
0x10045a7d  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045a83  push    [ebp+phkResult]; hKey
0x10045a86  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10045a8c  lea     eax, [ebp+var_10]
0x10045a8f  mov     [ebp+phkResult], 0
0x10045a96  push    eax; lpdwDisposition
0x10045a97  lea     eax, [ebp+phkResult]
0x10045a9a  mov     dword ptr [ebp+Data], 0
0x10045aa1  push    eax; phkResult
0x10045aa2  push    0; lpSecurityAttributes
0x10045aa4  push    2001Fh; samDesired
0x10045aa9  push    0; dwOptions
0x10045aab  push    0; lpClass
0x10045aad  push    0; Reserved
0x10045aaf  push    offset _szDefaultJetTree; "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines"
0x10045ab4  push    80000002h; hKey
0x10045ab9  mov     edi, 1
0x10045abe  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x10045ac4  test    eax, eax
0x10045ac6  jnz     loc_10045BD2
0x10045acc  push    14h; cbData
0x10045ace  push    offset aSystemMdb; "system.mdb"
0x10045ad3  push    edi; dwType
0x10045ad4  push    eax; Reserved
0x10045ad5  push    offset _wszSystemDB; "SystemDB"
0x10045ada  push    [ebp+phkResult]; hKey
0x10045add  call    _JetRegSetValueExW@24; JetRegSetValueExW(x,x,x,x,x,x)
0x10045ae2  push    4; cbData
0x10045ae4  lea     eax, [ebp+dwDisposition]
0x10045ae7  mov     [ebp+dwDisposition], edi
0x10045aea  push    eax; lpData
0x10045aeb  push    4; dwType
0x10045aed  push    0; Reserved
0x10045aef  push    offset _szCompactByPKey; "CompactByPKey"
0x10045af4  push    [ebp+phkResult]; hKey
0x10045af7  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045afd  push    4; cbData
0x10045aff  lea     eax, [ebp+dwDisposition]
0x10045b02  mov     [ebp+dwDisposition], edi
0x10045b05  push    eax; lpData
0x10045b06  push    4; dwType
0x10045b08  push    0; Reserved
0x10045b0a  push    offset _szCompressOldText; "PrevFormatCompactWithUNICODECompression"
0x10045b0f  push    [ebp+phkResult]; hKey
0x10045b12  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045b18  lea     eax, [ebp+var_10]
0x10045b1b  push    eax; lpdwDisposition
0x10045b1c  lea     eax, [ebp+Data]
0x10045b1f  push    eax; phkResult
0x10045b20  push    0; lpSecurityAttributes
0x10045b22  push    2001Fh; samDesired
0x10045b27  push    0; dwOptions
0x10045b29  push    0; lpClass
0x10045b2b  push    0; Reserved
0x10045b2d  push    offset _szODBCSection; "ODBC"
0x10045b32  push    [ebp+phkResult]; hKey
0x10045b35  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x10045b3b  test    eax, eax
0x10045b3d  jz      short loc_10045B43
0x10045b3f  xor     edi, edi
0x10045b41  jmp     short loc_10045BA3
0x10045b43  xor     esi, esi
0x10045b45  cmp     ds:_ODBCDefaults, esi
0x10045b4b  jz      short loc_10045B81
0x10045b4d  nop     dword ptr [eax]
0x10045b50  mov     eax, ds:dword_10004324[esi*8]
0x10045b57  push    4; cbData
0x10045b59  mov     [ebp+dwDisposition], eax
0x10045b5c  lea     eax, [ebp+dwDisposition]
0x10045b5f  push    eax; lpData
0x10045b60  push    4; dwType
0x10045b62  push    0; Reserved
0x10045b64  push    ds:_ODBCDefaults[esi*8]; lpValueName
0x10045b6b  push    dword ptr [ebp+Data]; hKey
0x10045b6e  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045b74  lea     esi, [esi+1]
0x10045b77  cmp     ds:_ODBCDefaults[esi*8], 0
0x10045b7f  jnz     short loc_10045B50
0x10045b81  push    2Fh ; '/'; cbData
0x10045b83  push    offset _szDefaultAttObj; "'TABLE','VIEW','SYSTEM TABLE','ALIAS','"...
0x10045b88  push    1; dwType
0x10045b8a  push    0; Reserved
0x10045b8c  push    offset _szAttachableObjects; "AttachableObjects"
0x10045b91  push    dword ptr [ebp+Data]; hKey
0x10045b94  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10045b9a  push    dword ptr [ebp+Data]; hKey
0x10045b9d  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10045ba3  push    [ebp+phkResult]; hKey
0x10045ba6  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10045bac  test    edi, edi
0x10045bae  jz      short loc_10045BD2
0x10045bb0  push    0; Stream
0x10045bb2  call    _RegisterReplDefaults@4; RegisterReplDefaults(x)
0x10045bb7  test    eax, eax
0x10045bb9  jz      short loc_10045BD2
0x10045bbb  mov     ecx, 1
0x10045bc0  xor     edx, edx
0x10045bc2  test    ecx, ecx
0x10045bc4  mov     eax, 80004005h
0x10045bc9  pop     edi
0x10045bca  cmovnz  eax, edx
0x10045bcd  pop     esi
0x10045bce  mov     esp, ebp
0x10045bd0  pop     ebp
0x10045bd1  retn
0x10045bd2  xor     ecx, ecx
0x10045bd4  xor     edx, edx
0x10045bd6  test    ecx, ecx
0x10045bd8  mov     eax, 80004005h
0x10045bdd  pop     edi
0x10045bde  cmovnz  eax, edx
0x10045be1  pop     esi
0x10045be2  mov     esp, ebp
0x10045be4  pop     ebp
0x10045be5  retn
```

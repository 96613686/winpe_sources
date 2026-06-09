# FCachePassword()

- ea: `0x10046568`
- end: `0x10046698`
- name: `_FCachePassword@0`
- size: `304`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10096cac`

## callees

- `0x10046568`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100465e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1004666a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100465e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1004666a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100465c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10046646`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100465c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10046646`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100465f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10046676`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100465f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10046676`

## string_xrefs

- `0x10046583`: `SOFTWARE\Microsoft\Office\9.0\Common\Security`

## pseudocode

```c
BOOL __stdcall FCachePassword()
{
  BOOL v0; // ecx
  DWORD cbData; // [esp+Ch] [ebp-A4h] BYREF
  BYTE Data[4]; // [esp+10h] [ebp-A0h] BYREF
  HKEY phkResult; // [esp+14h] [ebp-9Ch] BYREF
  char v5[60]; // [esp+18h] [ebp-98h] BYREF
  CHAR SubKey[48]; // [esp+54h] [ebp-5Ch] BYREF
  char v7[20]; // [esp+84h] [ebp-2Ch] BYREF
  CHAR ValueName[20]; // [esp+98h] [ebp-18h] BYREF

  cbData = 4;
  strcpy(SubKey, "SOFTWARE\\Microsoft\\Office\\9.0\\Common\\Security");
  *(_DWORD *)Data = 0;
  strcpy(ValueName, "DisablePwdCaching");
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &phkResult) )
  {
    RegQueryValueExA(phkResult, ValueName, 0, 0, Data, &cbData);
    RegCloseKey(phkResult);
  }
  v0 = *(_DWORD *)Data == 0;
  if ( !*(_DWORD *)Data )
  {
    *(_DWORD *)Data = 0;
    strcpy(v5, "SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\Network");
    strcpy(v7, "DisablePwdCaching");
    if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, v5, 0, 1u, &phkResult) )
    {
      RegQueryValueExA(phkResult, v7, 0, 0, Data, &cbData);
      RegCloseKey(phkResult);
    }
    return *(_DWORD *)Data == 0;
  }
  return v0;
}

```

## disassembly

```asm
0x10046568  mov     edi, edi
0x1004656a  push    ebp
0x1004656b  mov     ebp, esp
0x1004656d  sub     esp, 0A4h
0x10046573  mov     eax, ___security_cookie
0x10046578  xor     eax, ebp
0x1004657a  mov     [ebp+var_4], eax
0x1004657d  push    ebx
0x1004657e  push    esi
0x1004657f  push    edi
0x10046580  push    0Bh
0x10046582  pop     ecx
0x10046583  mov     esi, offset aSoftwareMicros; "SOFTWARE\\Microsoft\\Office\\9.0\\Commo"...
0x10046588  mov     [ebp+cbData], 4
0x10046592  lea     edi, [ebp+SubKey]
0x10046595  xor     ebx, ebx
0x10046597  rep movsd
0x10046599  lea     eax, [ebp+phkResult]
0x1004659f  mov     dword ptr [ebp+Data], ebx
0x100465a5  push    eax; phkResult
0x100465a6  push    1; samDesired
0x100465a8  movsw
0x100465aa  lea     eax, [ebp+SubKey]
0x100465ad  mov     esi, offset aDisablepwdcach; "DisablePwdCaching"
0x100465b2  lea     edi, [ebp+ValueName]
0x100465b5  push    ebx; ulOptions
0x100465b6  push    eax; lpSubKey
0x100465b7  push    80000002h; hKey
0x100465bc  movsd
0x100465bd  movsd
0x100465be  movsd
0x100465bf  movsd
0x100465c0  movsw
0x100465c2  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x100465c8  test    eax, eax
0x100465ca  jnz     short loc_100465F8
0x100465cc  lea     eax, [ebp+cbData]
0x100465d2  push    eax; lpcbData
0x100465d3  lea     eax, [ebp+Data]
0x100465d9  push    eax; lpData
0x100465da  push    ebx; lpType
0x100465db  push    ebx; lpReserved
0x100465dc  lea     eax, [ebp+ValueName]
0x100465df  push    eax; lpValueName
0x100465e0  push    [ebp+phkResult]; hKey
0x100465e6  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100465ec  push    [ebp+phkResult]; hKey
0x100465f2  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100465f8  mov     eax, dword ptr [ebp+Data]
0x100465fe  xor     ecx, ecx
0x10046600  test    eax, eax
0x10046602  setz    cl
0x10046605  test    eax, eax
0x10046607  jnz     short loc_10046687
0x10046609  push    0Eh
0x1004660b  pop     ecx
0x1004660c  mov     esi, offset aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x10046611  mov     dword ptr [ebp+Data], ebx
0x10046617  lea     edi, [ebp+var_98]
0x1004661d  rep movsd
0x1004661f  lea     eax, [ebp+phkResult]
0x10046625  push    eax; phkResult
0x10046626  push    1; samDesired
0x10046628  movsw
0x1004662a  lea     eax, [ebp+var_98]
0x10046630  push    ebx; ulOptions
0x10046631  push    eax; lpSubKey
0x10046632  push    80000002h; hKey
0x10046637  movsb
0x10046638  mov     esi, offset aDisablepwdcach; "DisablePwdCaching"
0x1004663d  lea     edi, [ebp+var_2C]
0x10046640  movsd
0x10046641  movsd
0x10046642  movsd
0x10046643  movsd
0x10046644  movsw
0x10046646  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x1004664c  test    eax, eax
0x1004664e  jnz     short loc_1004667C
0x10046650  lea     eax, [ebp+cbData]
0x10046656  push    eax; lpcbData
0x10046657  lea     eax, [ebp+Data]
0x1004665d  push    eax; lpData
0x1004665e  push    ebx; lpType
0x1004665f  push    ebx; lpReserved
0x10046660  lea     eax, [ebp+var_2C]
0x10046663  push    eax; lpValueName
0x10046664  push    [ebp+phkResult]; hKey
0x1004666a  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10046670  push    [ebp+phkResult]; hKey
0x10046676  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1004667c  xor     ecx, ecx
0x1004667e  cmp     dword ptr [ebp+Data], ecx
0x10046684  setz    cl
0x10046687  mov     eax, ecx
0x10046689  mov     ecx, [ebp+var_4]
0x1004668c  pop     edi
0x1004668d  pop     esi
0x1004668e  xor     ecx, ebp; StackCookie
0x10046690  pop     ebx
0x10046691  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10046696  leave
0x10046697  retn
```

# FCachePassword()

- ea: `0x100463e8`
- end: `0x10046518`
- name: `_FCachePassword@0`
- size: `304`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10096b1c`

## callees

- `0x100463e8`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10046466`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100464ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10046466`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100464ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10046442`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100464c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10046442`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100464c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10046472`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100464f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10046472`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100464f6`

## string_xrefs

- `0x10046403`: `SOFTWARE\Microsoft\Office\9.0\Common\Security`

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
0x100463e8  mov     edi, edi
0x100463ea  push    ebp
0x100463eb  mov     ebp, esp
0x100463ed  sub     esp, 0A4h
0x100463f3  mov     eax, ___security_cookie
0x100463f8  xor     eax, ebp
0x100463fa  mov     [ebp+var_4], eax
0x100463fd  push    ebx
0x100463fe  push    esi
0x100463ff  push    edi
0x10046400  push    0Bh
0x10046402  pop     ecx
0x10046403  mov     esi, offset aSoftwareMicros; "SOFTWARE\\Microsoft\\Office\\9.0\\Commo"...
0x10046408  mov     [ebp+cbData], 4
0x10046412  lea     edi, [ebp+SubKey]
0x10046415  xor     ebx, ebx
0x10046417  rep movsd
0x10046419  lea     eax, [ebp+phkResult]
0x1004641f  mov     dword ptr [ebp+Data], ebx
0x10046425  push    eax; phkResult
0x10046426  push    1; samDesired
0x10046428  movsw
0x1004642a  lea     eax, [ebp+SubKey]
0x1004642d  mov     esi, offset aDisablepwdcach; "DisablePwdCaching"
0x10046432  lea     edi, [ebp+ValueName]
0x10046435  push    ebx; ulOptions
0x10046436  push    eax; lpSubKey
0x10046437  push    80000002h; hKey
0x1004643c  movsd
0x1004643d  movsd
0x1004643e  movsd
0x1004643f  movsd
0x10046440  movsw
0x10046442  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10046448  test    eax, eax
0x1004644a  jnz     short loc_10046478
0x1004644c  lea     eax, [ebp+cbData]
0x10046452  push    eax; lpcbData
0x10046453  lea     eax, [ebp+Data]
0x10046459  push    eax; lpData
0x1004645a  push    ebx; lpType
0x1004645b  push    ebx; lpReserved
0x1004645c  lea     eax, [ebp+ValueName]
0x1004645f  push    eax; lpValueName
0x10046460  push    [ebp+phkResult]; hKey
0x10046466  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x1004646c  push    [ebp+phkResult]; hKey
0x10046472  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10046478  mov     eax, dword ptr [ebp+Data]
0x1004647e  xor     ecx, ecx
0x10046480  test    eax, eax
0x10046482  setz    cl
0x10046485  test    eax, eax
0x10046487  jnz     short loc_10046507
0x10046489  push    0Eh
0x1004648b  pop     ecx
0x1004648c  mov     esi, offset aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x10046491  mov     dword ptr [ebp+Data], ebx
0x10046497  lea     edi, [ebp+var_98]
0x1004649d  rep movsd
0x1004649f  lea     eax, [ebp+phkResult]
0x100464a5  push    eax; phkResult
0x100464a6  push    1; samDesired
0x100464a8  movsw
0x100464aa  lea     eax, [ebp+var_98]
0x100464b0  push    ebx; ulOptions
0x100464b1  push    eax; lpSubKey
0x100464b2  push    80000002h; hKey
0x100464b7  movsb
0x100464b8  mov     esi, offset aDisablepwdcach; "DisablePwdCaching"
0x100464bd  lea     edi, [ebp+var_2C]
0x100464c0  movsd
0x100464c1  movsd
0x100464c2  movsd
0x100464c3  movsd
0x100464c4  movsw
0x100464c6  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x100464cc  test    eax, eax
0x100464ce  jnz     short loc_100464FC
0x100464d0  lea     eax, [ebp+cbData]
0x100464d6  push    eax; lpcbData
0x100464d7  lea     eax, [ebp+Data]
0x100464dd  push    eax; lpData
0x100464de  push    ebx; lpType
0x100464df  push    ebx; lpReserved
0x100464e0  lea     eax, [ebp+var_2C]
0x100464e3  push    eax; lpValueName
0x100464e4  push    [ebp+phkResult]; hKey
0x100464ea  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100464f0  push    [ebp+phkResult]; hKey
0x100464f6  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100464fc  xor     ecx, ecx
0x100464fe  cmp     dword ptr [ebp+Data], ecx
0x10046504  setz    cl
0x10046507  mov     eax, ecx
0x10046509  mov     ecx, [ebp+var_4]
0x1004650c  pop     edi
0x1004650d  pop     esi
0x1004650e  xor     ecx, ebp; StackCookie
0x10046510  pop     ebx
0x10046511  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10046516  leave
0x10046517  retn
```

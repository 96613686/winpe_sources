# Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)

- ea: `0x10018900`
- end: `0x1001897c`
- name: `?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z`
- size: `124`
- prototype: `int __thiscall(Connection *__hidden this, HKEY hKey, LPCSTR lpSubKey, LPCSTR lpValueName, unsigned int, LPBYTE lpData, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x10018990`

## callees

- `0x10018900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1001892b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1001892b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1001896b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1001896b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1001894b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1001894b`

## pseudocode

```c
LSTATUS __thiscall Connection::ReadConfigEntry(
        Connection *this,
        HKEY hKey,
        LPCSTR lpSubKey,
        LPCSTR lpValueName,
        unsigned int a5,
        LPBYTE lpData,
        DWORD a7)
{
  HKEY v7; // ecx
  LSTATUS result; // eax
  LSTATUS v9; // esi
  DWORD Type; // [esp+4h] [ebp-Ch] BYREF
  HKEY phkResult; // [esp+8h] [ebp-8h] BYREF
  DWORD cbData; // [esp+Ch] [ebp-4h] BYREF

  v7 = HKEY_LOCAL_MACHINE;
  cbData = a7;
  if ( hKey )
    v7 = hKey;
  result = RegOpenKeyExA(v7, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !result )
  {
    v9 = RegQueryValueExA(phkResult, lpValueName, 0, &Type, lpData, &cbData);
    if ( cbData < a7 && Type == 1 && !v9 )
      lpData[cbData] = 0;
    RegCloseKey(phkResult);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x10018900  mov     edi, edi
0x10018902  push    ebp
0x10018903  mov     ebp, esp
0x10018905  sub     esp, 0Ch
0x10018908  push    ebx
0x10018909  mov     ebx, [ebp+arg_14]
0x1001890c  lea     eax, [ebp+phkResult]
0x1001890f  push    eax; phkResult
0x10018910  mov     eax, [ebp+hKey]
0x10018913  mov     ecx, 80000002h
0x10018918  push    20019h; samDesired
0x1001891d  push    0; ulOptions
0x1001891f  push    [ebp+lpSubKey]; lpSubKey
0x10018922  test    eax, eax
0x10018924  mov     [ebp+cbData], ebx
0x10018927  cmovnz  ecx, eax
0x1001892a  push    ecx; hKey
0x1001892b  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10018931  test    eax, eax
0x10018933  jnz     short loc_10018975
0x10018935  push    esi
0x10018936  push    edi
0x10018937  mov     edi, [ebp+lpData]
0x1001893a  lea     eax, [ebp+cbData]
0x1001893d  push    eax; lpcbData
0x1001893e  push    edi; lpData
0x1001893f  lea     eax, [ebp+Type]
0x10018942  push    eax; lpType
0x10018943  push    0; lpReserved
0x10018945  push    [ebp+lpValueName]; lpValueName
0x10018948  push    [ebp+phkResult]; hKey
0x1001894b  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10018951  mov     esi, eax
0x10018953  mov     eax, [ebp+cbData]
0x10018956  cmp     eax, ebx
0x10018958  jnb     short loc_10018968
0x1001895a  cmp     [ebp+Type], 1
0x1001895e  jnz     short loc_10018968
0x10018960  test    esi, esi
0x10018962  jnz     short loc_10018968
0x10018964  mov     byte ptr [eax+edi], 0
0x10018968  push    [ebp+phkResult]; hKey
0x1001896b  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10018971  pop     edi
0x10018972  mov     eax, esi
0x10018974  pop     esi
0x10018975  pop     ebx
0x10018976  mov     esp, ebp
0x10018978  pop     ebp
0x10018979  retn    18h
```

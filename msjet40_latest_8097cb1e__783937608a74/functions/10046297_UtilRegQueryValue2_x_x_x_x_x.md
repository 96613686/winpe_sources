# UtilRegQueryValue2(x,x,x,x,x)

- ea: `0x10046297`
- end: `0x10046312`
- name: `_UtilRegQueryValue2@20`
- size: `123`
- prototype: `int __fastcall(HKEY hKey, LPCSTR lpSubKey, LPCSTR lpValueName, LPBYTE lpData, LPDWORD lpcbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x100aab45`
- `0x1012011e`

## callees

- `0x10046297`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100462dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100462dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100462b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100462b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10046303`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10046303`

## pseudocode

```c
LSTATUS __fastcall UtilRegQueryValue2(
        HKEY hKey,
        LPCSTR lpSubKey,
        LPCSTR lpValueName,
        LPBYTE lpData,
        signed int *lpcbData)
{
  int v5; // edi
  LSTATUS v6; // esi
  LSTATUS v7; // eax
  DWORD Type; // [esp+Ch] [ebp-Ch] BYREF
  signed int v10; // [esp+10h] [ebp-8h]
  HKEY phkResult; // [esp+14h] [ebp-4h] BYREF

  v5 = 0;
  v10 = *lpcbData;
  if ( lpSubKey )
  {
    v6 = RegOpenKeyExA(hKey, lpSubKey, 0, 1u, &phkResult);
    if ( v6 )
      return v6;
    hKey = phkResult;
    v5 = 1;
  }
  else
  {
    phkResult = hKey;
  }
  v7 = RegQueryValueExA(hKey, lpValueName, 0, &Type, lpData, (LPDWORD)lpcbData);
  v6 = v7;
  if ( *lpcbData < v10 && Type == 1 && !v7 )
    lpData[*lpcbData] = 0;
  if ( v5 )
    RegCloseKey(phkResult);
  return v6;
}

```

## disassembly

```asm
0x10046297  mov     edi, edi
0x10046299  push    ebp
0x1004629a  mov     ebp, esp
0x1004629c  sub     esp, 0Ch
0x1004629f  push    ebx
0x100462a0  mov     ebx, [ebp+lpcbData]
0x100462a3  push    esi
0x100462a4  push    edi
0x100462a5  xor     edi, edi
0x100462a7  mov     eax, [ebx]
0x100462a9  mov     [ebp+var_8], eax
0x100462ac  test    edx, edx
0x100462ae  jz      short loc_100462CB
0x100462b0  lea     eax, [ebp+phkResult]
0x100462b3  push    eax; phkResult
0x100462b4  push    1; samDesired
0x100462b6  push    edi; ulOptions
0x100462b7  push    edx; lpSubKey
0x100462b8  push    ecx; hKey
0x100462b9  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x100462bf  mov     esi, eax
0x100462c1  test    esi, esi
0x100462c3  jnz     short loc_10046309
0x100462c5  mov     ecx, [ebp+phkResult]
0x100462c8  inc     edi
0x100462c9  jmp     short loc_100462CE
0x100462cb  mov     [ebp+phkResult], ecx
0x100462ce  push    ebx; lpcbData
0x100462cf  push    [ebp+lpData]; lpData
0x100462d2  lea     eax, [ebp+Type]
0x100462d5  push    eax; lpType
0x100462d6  push    0; lpReserved
0x100462d8  push    [ebp+lpValueName]; lpValueName
0x100462db  push    ecx; hKey
0x100462dc  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x100462e2  mov     ecx, [ebx]
0x100462e4  mov     esi, eax
0x100462e6  cmp     ecx, [ebp+var_8]
0x100462e9  jge     short loc_100462FC
0x100462eb  cmp     [ebp+Type], 1
0x100462ef  jnz     short loc_100462FC
0x100462f1  test    esi, esi
0x100462f3  jnz     short loc_100462FC
0x100462f5  mov     eax, [ebp+lpData]
0x100462f8  mov     byte ptr [ecx+eax], 0
0x100462fc  test    edi, edi
0x100462fe  jz      short loc_10046309
0x10046300  push    [ebp+phkResult]; hKey
0x10046303  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10046309  pop     edi
0x1004630a  mov     eax, esi
0x1004630c  pop     esi
0x1004630d  pop     ebx
0x1004630e  leave
0x1004630f  retn    0Ch
```

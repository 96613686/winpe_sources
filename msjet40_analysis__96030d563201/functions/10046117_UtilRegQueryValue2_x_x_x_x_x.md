# UtilRegQueryValue2(x,x,x,x,x)

- ea: `0x10046117`
- end: `0x10046192`
- name: `_UtilRegQueryValue2@20`
- size: `123`
- prototype: `int __fastcall(HKEY hKey, LPCSTR lpSubKey, LPCSTR lpValueName, LPBYTE lpData, LPDWORD lpcbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x100aa9b5`
- `0x1011ff6e`

## callees

- `0x10046117`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1004615c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1004615c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10046139`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10046139`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10046183`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10046183`

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
0x10046117  mov     edi, edi
0x10046119  push    ebp
0x1004611a  mov     ebp, esp
0x1004611c  sub     esp, 0Ch
0x1004611f  push    ebx
0x10046120  mov     ebx, [ebp+lpcbData]
0x10046123  push    esi
0x10046124  push    edi
0x10046125  xor     edi, edi
0x10046127  mov     eax, [ebx]
0x10046129  mov     [ebp+var_8], eax
0x1004612c  test    edx, edx
0x1004612e  jz      short loc_1004614B
0x10046130  lea     eax, [ebp+phkResult]
0x10046133  push    eax; phkResult
0x10046134  push    1; samDesired
0x10046136  push    edi; ulOptions
0x10046137  push    edx; lpSubKey
0x10046138  push    ecx; hKey
0x10046139  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x1004613f  mov     esi, eax
0x10046141  test    esi, esi
0x10046143  jnz     short loc_10046189
0x10046145  mov     ecx, [ebp+phkResult]
0x10046148  inc     edi
0x10046149  jmp     short loc_1004614E
0x1004614b  mov     [ebp+phkResult], ecx
0x1004614e  push    ebx; lpcbData
0x1004614f  push    [ebp+lpData]; lpData
0x10046152  lea     eax, [ebp+Type]
0x10046155  push    eax; lpType
0x10046156  push    0; lpReserved
0x10046158  push    [ebp+lpValueName]; lpValueName
0x1004615b  push    ecx; hKey
0x1004615c  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10046162  mov     ecx, [ebx]
0x10046164  mov     esi, eax
0x10046166  cmp     ecx, [ebp+var_8]
0x10046169  jge     short loc_1004617C
0x1004616b  cmp     [ebp+Type], 1
0x1004616f  jnz     short loc_1004617C
0x10046171  test    esi, esi
0x10046173  jnz     short loc_1004617C
0x10046175  mov     eax, [ebp+lpData]
0x10046178  mov     byte ptr [ecx+eax], 0
0x1004617c  test    edi, edi
0x1004617e  jz      short loc_10046189
0x10046180  push    [ebp+phkResult]; hKey
0x10046183  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10046189  pop     edi
0x1004618a  mov     eax, esi
0x1004618c  pop     esi
0x1004618d  pop     ebx
0x1004618e  leave
0x1004618f  retn    0Ch
```

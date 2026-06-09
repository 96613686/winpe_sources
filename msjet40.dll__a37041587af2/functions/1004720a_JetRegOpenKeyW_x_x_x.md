# JetRegOpenKeyW(x,x,x)

- ea: `0x1004720a`
- end: `0x1004727c`
- name: `_JetRegOpenKeyW@12`
- size: `114`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x10029510`
- `0x10046318`

## callees

- `0x10046833`
- `0x10046864`
- `0x1004720a`
- `0x10123110`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x10047235`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x10047235`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10047258`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10047258`

## pseudocode

```c
LSTATUS __stdcall JetRegOpenKeyW(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)
{
  LSTATUS v4; // esi
  _BYTE v5[4]; // [esp+10h] [ebp-224h] BYREF
  LPCSTR v6; // [esp+14h] [ebp-220h]
  int v7; // [esp+230h] [ebp-4h]

  if ( wrap )
    return RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, phkResult);
  CStrIn::CStrIn((CStrIn *)v5, lpSubKey);
  v4 = RegOpenKeyExA(hKey, v6, 0, 0x20019u, phkResult);
  v7 = 0;
  CConvertStr::Free((CConvertStr *)v5);
  return v4;
}

```

## disassembly

```asm
0x1004720a  push    218h
0x1004720f  mov     eax, offset loc_10124C69
0x10047214  call    __EH_prolog3_GS
0x10047219  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10047220  mov     esi, [ebp+hKey]
0x10047223  mov     eax, [ebp+lpSubKey]
0x10047226  mov     edi, [ebp+phkResult]
0x10047229  jz      short loc_1004723D
0x1004722b  push    edi; phkResult
0x1004722c  push    20019h; samDesired
0x10047231  push    0; ulOptions
0x10047233  push    eax; lpSubKey
0x10047234  push    esi; hKey
0x10047235  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x1004723b  jmp     short loc_10047274
0x1004723d  push    eax; unsigned __int16 *
0x1004723e  lea     ecx, [ebp+var_224]; this
0x10047244  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10047249  push    edi; phkResult
0x1004724a  push    20019h; samDesired
0x1004724f  push    0; ulOptions
0x10047251  push    [ebp+var_220]; lpSubKey
0x10047257  push    esi; hKey
0x10047258  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x1004725e  mov     esi, eax
0x10047260  lea     ecx, [ebp+var_224]; this
0x10047266  mov     [ebp+var_4], 0
0x1004726d  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10047272  mov     eax, esi
0x10047274  call    __EH_epilog3_GS
0x10047279  retn    0Ch
0x10124060  jmp     ds:__imp____std_terminate
0x10124c69  nop
0x10124c6a  nop
0x10124c6b  mov     edx, [esp-4+hFile]
0x10124c6f  lea     eax, [edx+0Ch]
0x10124c72  mov     ecx, [edx-228h]
0x10124c78  xor     ecx, eax; StackCookie
0x10124c7a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124c7f  mov     ecx, [edx-4]
0x10124c82  xor     ecx, eax; StackCookie
0x10124c84  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124c89  mov     eax, offset stru_10127AA8
0x10124c8e  jmp     ___CxxFrameHandler3
```

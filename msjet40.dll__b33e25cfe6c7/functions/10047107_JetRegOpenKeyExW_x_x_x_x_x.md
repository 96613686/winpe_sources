# JetRegOpenKeyExW(x,x,x,x,x)

- ea: `0x10047107`
- end: `0x10047179`
- name: `_JetRegOpenKeyExW@20`
- size: `114`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x10120c6b`

## callees

- `0x100466b3`
- `0x100466e4`
- `0x10047107`
- `0x10122f60`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x10047131`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x10047131`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10047155`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10047155`

## pseudocode

```c
LSTATUS __stdcall JetRegOpenKeyExW(HKEY hKey, LPCWSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult)
{
  LSTATUS v5; // esi
  _BYTE v7[4]; // [esp+10h] [ebp-224h] BYREF
  LPCSTR v8; // [esp+14h] [ebp-220h]
  int v9; // [esp+230h] [ebp-4h]

  if ( wrap )
    return RegOpenKeyExW(hKey, lpSubKey, ulOptions, samDesired, phkResult);
  CStrIn::CStrIn((CStrIn *)v7, lpSubKey);
  v5 = RegOpenKeyExA(hKey, v8, ulOptions, samDesired, phkResult);
  v9 = 0;
  CConvertStr::Free((CConvertStr *)v7);
  return v5;
}

```

## disassembly

```asm
0x10047107  push    218h
0x1004710c  mov     eax, offset loc_10124AB9
0x10047111  call    __EH_prolog3_GS
0x10047116  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1004711d  mov     esi, [ebp+hKey]
0x10047120  mov     eax, [ebp+lpSubKey]
0x10047123  mov     edi, [ebp+phkResult]
0x10047126  jz      short loc_1004713B
0x10047128  push    edi; phkResult
0x10047129  push    [ebp+samDesired]; samDesired
0x1004712c  push    [ebp+ulOptions]; ulOptions
0x1004712f  push    eax; lpSubKey
0x10047130  push    esi; hKey
0x10047131  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10047137  mov     esi, eax
0x10047139  jmp     short loc_1004716F
0x1004713b  push    eax; unsigned __int16 *
0x1004713c  lea     ecx, [ebp+var_224]; this
0x10047142  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10047147  push    edi; phkResult
0x10047148  push    [ebp+samDesired]; samDesired
0x1004714b  push    [ebp+ulOptions]; ulOptions
0x1004714e  push    [ebp+var_220]; lpSubKey
0x10047154  push    esi; hKey
0x10047155  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x1004715b  mov     esi, eax
0x1004715d  lea     ecx, [ebp+var_224]; this
0x10047163  mov     [ebp+var_4], 0
0x1004716a  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1004716f  mov     eax, esi
0x10047171  call    __EH_epilog3_GS
0x10047176  retn    14h
0x10123eb0  jmp     ds:__imp____std_terminate
0x10124ab9  nop
0x10124aba  nop
0x10124abb  mov     edx, [esp-4+hFile]
0x10124abf  lea     eax, [edx+0Ch]
0x10124ac2  mov     ecx, [edx-228h]
0x10124ac8  xor     ecx, eax; StackCookie
0x10124aca  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124acf  mov     ecx, [edx-4]
0x10124ad2  xor     ecx, eax; StackCookie
0x10124ad4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124ad9  mov     eax, offset stru_101278F8
0x10124ade  jmp     ___CxxFrameHandler3
```

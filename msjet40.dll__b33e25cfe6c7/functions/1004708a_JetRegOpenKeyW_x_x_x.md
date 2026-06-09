# JetRegOpenKeyW(x,x,x)

- ea: `0x1004708a`
- end: `0x100470fc`
- name: `_JetRegOpenKeyW@12`
- size: `114`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x10029340`
- `0x10046198`

## callees

- `0x100466b3`
- `0x100466e4`
- `0x1004708a`
- `0x10122f60`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100470b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100470b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100470d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100470d8`

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
0x1004708a  push    218h
0x1004708f  mov     eax, offset loc_10124AB9
0x10047094  call    __EH_prolog3_GS
0x10047099  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x100470a0  mov     esi, [ebp+hKey]
0x100470a3  mov     eax, [ebp+lpSubKey]
0x100470a6  mov     edi, [ebp+phkResult]
0x100470a9  jz      short loc_100470BD
0x100470ab  push    edi; phkResult
0x100470ac  push    20019h; samDesired
0x100470b1  push    0; ulOptions
0x100470b3  push    eax; lpSubKey
0x100470b4  push    esi; hKey
0x100470b5  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x100470bb  jmp     short loc_100470F4
0x100470bd  push    eax; unsigned __int16 *
0x100470be  lea     ecx, [ebp+var_224]; this
0x100470c4  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x100470c9  push    edi; phkResult
0x100470ca  push    20019h; samDesired
0x100470cf  push    0; ulOptions
0x100470d1  push    [ebp+var_220]; lpSubKey
0x100470d7  push    esi; hKey
0x100470d8  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x100470de  mov     esi, eax
0x100470e0  lea     ecx, [ebp+var_224]; this
0x100470e6  mov     [ebp+var_4], 0
0x100470ed  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x100470f2  mov     eax, esi
0x100470f4  call    __EH_epilog3_GS
0x100470f9  retn    0Ch
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

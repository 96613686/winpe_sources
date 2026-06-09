# JetRegOpenKeyExW(x,x,x,x,x)

- ea: `0x10047287`
- end: `0x100472f9`
- name: `_JetRegOpenKeyExW@20`
- size: `114`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x10120e1b`

## callees

- `0x10046833`
- `0x10046864`
- `0x10047287`
- `0x10123110`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100472b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x100472b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100472d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100472d5`

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
0x10047287  push    218h
0x1004728c  mov     eax, offset loc_10124C69
0x10047291  call    __EH_prolog3_GS
0x10047296  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1004729d  mov     esi, [ebp+hKey]
0x100472a0  mov     eax, [ebp+lpSubKey]
0x100472a3  mov     edi, [ebp+phkResult]
0x100472a6  jz      short loc_100472BB
0x100472a8  push    edi; phkResult
0x100472a9  push    [ebp+samDesired]; samDesired
0x100472ac  push    [ebp+ulOptions]; ulOptions
0x100472af  push    eax; lpSubKey
0x100472b0  push    esi; hKey
0x100472b1  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x100472b7  mov     esi, eax
0x100472b9  jmp     short loc_100472EF
0x100472bb  push    eax; unsigned __int16 *
0x100472bc  lea     ecx, [ebp+var_224]; this
0x100472c2  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x100472c7  push    edi; phkResult
0x100472c8  push    [ebp+samDesired]; samDesired
0x100472cb  push    [ebp+ulOptions]; ulOptions
0x100472ce  push    [ebp+var_220]; lpSubKey
0x100472d4  push    esi; hKey
0x100472d5  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x100472db  mov     esi, eax
0x100472dd  lea     ecx, [ebp+var_224]; this
0x100472e3  mov     [ebp+var_4], 0
0x100472ea  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x100472ef  mov     eax, esi
0x100472f1  call    __EH_epilog3_GS
0x100472f6  retn    14h
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

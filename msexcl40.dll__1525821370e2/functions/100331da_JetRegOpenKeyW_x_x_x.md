# JetRegOpenKeyW(x,x,x)

- ea: `0x100331da`
- end: `0x10033255`
- name: `_JetRegOpenKeyW@12`
- size: `123`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x100249dd`
- `0x100252b0`

## callees

- `0x10032925`
- `0x10032956`
- `0x100331da`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1003320d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1003320d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10033230`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10033230`

## pseudocode

```c
LSTATUS __stdcall JetRegOpenKeyW(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)
{
  LSTATUS v4; // esi
  _BYTE v5[4]; // [esp+8h] [ebp-218h] BYREF
  LPCSTR v6; // [esp+Ch] [ebp-214h]

  if ( wrap )
    return RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, phkResult);
  CStrIn::CStrIn((CStrIn *)v5, lpSubKey);
  v4 = RegOpenKeyExA(hKey, v6, 0, 0x20019u, phkResult);
  CConvertStr::Free((CConvertStr *)v5);
  return v4;
}

```

## disassembly

```asm
0x100331da  mov     edi, edi
0x100331dc  push    ebp
0x100331dd  mov     ebp, esp
0x100331df  sub     esp, 218h
0x100331e5  mov     eax, ___security_cookie
0x100331ea  xor     eax, ebp
0x100331ec  mov     [ebp+var_4], eax
0x100331ef  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x100331f6  mov     eax, [ebp+lpSubKey]
0x100331f9  push    esi
0x100331fa  mov     esi, [ebp+hKey]
0x100331fd  push    edi
0x100331fe  mov     edi, [ebp+phkResult]
0x10033201  jz      short loc_10033215
0x10033203  push    edi; phkResult
0x10033204  push    20019h; samDesired
0x10033209  push    0; ulOptions
0x1003320b  push    eax; lpSubKey
0x1003320c  push    esi; hKey
0x1003320d  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10033213  jmp     short loc_10033245
0x10033215  push    eax; unsigned __int16 *
0x10033216  lea     ecx, [ebp+var_218]; this
0x1003321c  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10033221  push    edi; phkResult
0x10033222  push    20019h; samDesired
0x10033227  push    0; ulOptions
0x10033229  push    [ebp+var_214]; lpSubKey
0x1003322f  push    esi; hKey
0x10033230  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10033236  lea     ecx, [ebp+var_218]; this
0x1003323c  mov     esi, eax
0x1003323e  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10033243  mov     eax, esi
0x10033245  mov     ecx, [ebp+var_4]
0x10033248  pop     edi
0x10033249  xor     ecx, ebp; StackCookie
0x1003324b  pop     esi
0x1003324c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033251  leave
0x10033252  retn    0Ch
```

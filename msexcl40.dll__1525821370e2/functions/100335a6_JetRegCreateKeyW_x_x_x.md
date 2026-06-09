# JetRegCreateKeyW(x,x,x)

- ea: `0x100335a6`
- end: `0x10033637`
- name: `_JetRegCreateKeyW@12`
- size: `145`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x10024d8e`

## callees

- `0x10032925`
- `0x10032956`
- `0x100335a6`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x100335e4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x100335e4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10033612`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10033612`

## pseudocode

```c
LSTATUS __stdcall JetRegCreateKeyW(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)
{
  LSTATUS v4; // esi
  DWORD dwDisposition; // [esp+8h] [ebp-21Ch] BYREF
  _BYTE v6[4]; // [esp+Ch] [ebp-218h] BYREF
  LPCSTR v7; // [esp+10h] [ebp-214h]

  if ( wrap )
    return RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
  CStrIn::CStrIn((CStrIn *)v6, lpSubKey);
  v4 = RegCreateKeyExA(hKey, v7, 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
  CConvertStr::Free((CConvertStr *)v6);
  return v4;
}

```

## disassembly

```asm
0x100335a6  mov     edi, edi
0x100335a8  push    ebp
0x100335a9  mov     ebp, esp
0x100335ab  sub     esp, 21Ch
0x100335b1  mov     eax, ___security_cookie
0x100335b6  xor     eax, ebp
0x100335b8  mov     [ebp+var_4], eax
0x100335bb  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x100335c2  mov     ecx, [ebp+lpSubKey]
0x100335c5  push    esi
0x100335c6  mov     esi, [ebp+hKey]
0x100335c9  push    edi
0x100335ca  mov     edi, [ebp+phkResult]
0x100335cd  jz      short loc_100335EC
0x100335cf  lea     eax, [ebp+dwDisposition]
0x100335d5  push    eax; lpdwDisposition
0x100335d6  push    edi; phkResult
0x100335d7  xor     eax, eax
0x100335d9  push    eax; lpSecurityAttributes
0x100335da  push    2001Fh; samDesired
0x100335df  push    eax; dwOptions
0x100335e0  push    eax; lpClass
0x100335e1  push    eax; Reserved
0x100335e2  push    ecx; lpSubKey
0x100335e3  push    esi; hKey
0x100335e4  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x100335ea  jmp     short loc_10033627
0x100335ec  push    ecx; unsigned __int16 *
0x100335ed  lea     ecx, [ebp+var_218]; this
0x100335f3  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x100335f8  lea     eax, [ebp+dwDisposition]
0x100335fe  push    eax; lpdwDisposition
0x100335ff  push    edi; phkResult
0x10033600  xor     eax, eax
0x10033602  push    eax; lpSecurityAttributes
0x10033603  push    2001Fh; samDesired
0x10033608  push    eax; dwOptions
0x10033609  push    eax; lpClass
0x1003360a  push    eax; Reserved
0x1003360b  push    [ebp+var_214]; lpSubKey
0x10033611  push    esi; hKey
0x10033612  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x10033618  lea     ecx, [ebp+var_218]; this
0x1003361e  mov     esi, eax
0x10033620  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10033625  mov     eax, esi
0x10033627  mov     ecx, [ebp+var_4]
0x1003362a  pop     edi
0x1003362b  xor     ecx, ebp; StackCookie
0x1003362d  pop     esi
0x1003362e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033633  leave
0x10033634  retn    0Ch
```

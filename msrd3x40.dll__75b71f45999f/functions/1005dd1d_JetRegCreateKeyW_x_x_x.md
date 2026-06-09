# JetRegCreateKeyW(x,x,x)

- ea: `0x1005dd1d`
- end: `0x1005ddae`
- name: `_JetRegCreateKeyW@12`
- size: `145`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x10038080`

## callees

- `0x1005d64e`
- `0x1005d67f`
- `0x1005dd1d`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1005dd5b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1005dd5b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1005dd89`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1005dd89`

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
0x1005dd1d  mov     edi, edi
0x1005dd1f  push    ebp
0x1005dd20  mov     ebp, esp
0x1005dd22  sub     esp, 21Ch
0x1005dd28  mov     eax, ___security_cookie
0x1005dd2d  xor     eax, ebp
0x1005dd2f  mov     [ebp+var_4], eax
0x1005dd32  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1005dd39  mov     ecx, [ebp+lpSubKey]
0x1005dd3c  push    esi
0x1005dd3d  mov     esi, [ebp+hKey]
0x1005dd40  push    edi
0x1005dd41  mov     edi, [ebp+phkResult]
0x1005dd44  jz      short loc_1005DD63
0x1005dd46  lea     eax, [ebp+dwDisposition]
0x1005dd4c  push    eax; lpdwDisposition
0x1005dd4d  push    edi; phkResult
0x1005dd4e  xor     eax, eax
0x1005dd50  push    eax; lpSecurityAttributes
0x1005dd51  push    2001Fh; samDesired
0x1005dd56  push    eax; dwOptions
0x1005dd57  push    eax; lpClass
0x1005dd58  push    eax; Reserved
0x1005dd59  push    ecx; lpSubKey
0x1005dd5a  push    esi; hKey
0x1005dd5b  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x1005dd61  jmp     short loc_1005DD9E
0x1005dd63  push    ecx; unsigned __int16 *
0x1005dd64  lea     ecx, [ebp+var_218]; this
0x1005dd6a  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x1005dd6f  lea     eax, [ebp+dwDisposition]
0x1005dd75  push    eax; lpdwDisposition
0x1005dd76  push    edi; phkResult
0x1005dd77  xor     eax, eax
0x1005dd79  push    eax; lpSecurityAttributes
0x1005dd7a  push    2001Fh; samDesired
0x1005dd7f  push    eax; dwOptions
0x1005dd80  push    eax; lpClass
0x1005dd81  push    eax; Reserved
0x1005dd82  push    [ebp+var_214]; lpSubKey
0x1005dd88  push    esi; hKey
0x1005dd89  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x1005dd8f  lea     ecx, [ebp+var_218]; this
0x1005dd95  mov     esi, eax
0x1005dd97  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005dd9c  mov     eax, esi
0x1005dd9e  mov     ecx, [ebp+var_4]
0x1005dda1  pop     edi
0x1005dda2  xor     ecx, ebp; StackCookie
0x1005dda4  pop     esi
0x1005dda5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005ddaa  leave
0x1005ddab  retn    0Ch
```

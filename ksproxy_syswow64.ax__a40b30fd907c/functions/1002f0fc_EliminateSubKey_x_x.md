# EliminateSubKey(x,x)

- ea: `0x1002f0fc`
- end: `0x1002f1d2`
- name: `_EliminateSubKey@8`
- size: `214`
- prototype: `unsigned int __fastcall(HKEY hKey, WCHAR *lpSubKey)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1002f0fc`
- `0x1002f44b`

## callees

- `0x1002f0a0`
- `0x1002f0fc`
- `0x1003aba0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1002f199`
- `ADVAPI32!RegCloseKey` at `0x1002f199`
- `ADVAPI32!RegOpenKeyExW` at `0x1002f14d`
- `ADVAPI32!RegOpenKeyExW` at `0x1002f14d`
- `ADVAPI32!RegEnumKeyExW` at `0x1002f18b`
- `ADVAPI32!RegEnumKeyExW` at `0x1002f18b`
- `ADVAPI32!RegDeleteKeyW` at `0x1002f1a1`
- `ADVAPI32!RegDeleteKeyW` at `0x1002f1a1`

## pseudocode

```c
unsigned int __fastcall EliminateSubKey(HKEY hKey, WCHAR *lpSubKey)
{
  LSTATUS v4; // ecx
  unsigned int result; // eax
  unsigned int v6; // [esp+0h] [ebp-230h]
  unsigned int *v7; // [esp+4h] [ebp-22Ch]
  DWORD cchName; // [esp+10h] [ebp-220h] BYREF
  HKEY hKeya; // [esp+14h] [ebp-21Ch] BYREF
  struct _FILETIME ftLastWriteTime; // [esp+18h] [ebp-218h] BYREF
  WCHAR SubKey[262]; // [esp+20h] [ebp-210h] BYREF

  cchName = 0;
  if ( StringCchLengthW(0x7FFFFFFF, lpSubKey, (unsigned __int16 *)&cchName, v6, v7) < 0 || !cchName )
    return -2147467259;
  v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x2000000u, &hKeya);
  if ( !v4 )
  {
    do
      cchName = 260;
    while ( !RegEnumKeyExW(hKeya, 0, SubKey, &cchName, 0, 0, 0, &ftLastWriteTime) && !EliminateSubKey(hKeya, SubKey) );
    RegCloseKey(hKeya);
    v4 = RegDeleteKeyW(hKey, lpSubKey);
  }
  result = (unsigned __int16)v4 | 0x80070000;
  if ( v4 <= 0 )
    return v4;
  return result;
}

```

## disassembly

```asm
0x1002f0fc  mov     edi, edi
0x1002f0fe  push    ebp
0x1002f0ff  mov     ebp, esp
0x1002f101  and     esp, 0FFFFFFF8h
0x1002f104  sub     esp, 224h
0x1002f10a  mov     eax, ___security_cookie
0x1002f10f  xor     eax, esp
0x1002f111  mov     [esp+224h+var_4], eax
0x1002f118  push    ebx
0x1002f119  push    esi; unsigned int *
0x1002f11a  push    edi; unsigned int
0x1002f11b  mov     esi, edx
0x1002f11d  lea     eax, [esp+230h+cchName]
0x1002f121  mov     edi, ecx
0x1002f123  xor     ebx, ebx
0x1002f125  push    eax; unsigned __int16 *
0x1002f126  mov     edx, 7FFFFFFFh
0x1002f12b  mov     [esp+234h+cchName], ebx
0x1002f12f  mov     ecx, esi
0x1002f131  call    ?StringCchLengthW@@YGJPBGIPAI@Z; StringCchLengthW(ushort const *,uint,uint *)
0x1002f136  test    eax, eax
0x1002f138  js      short loc_1002F1B8
0x1002f13a  cmp     [esp+230h+cchName], ebx
0x1002f13e  jz      short loc_1002F1B8
0x1002f140  lea     eax, [esp+230h+hKey]
0x1002f144  push    eax; phkResult
0x1002f145  push    2000000h; samDesired
0x1002f14a  push    ebx; ulOptions
0x1002f14b  push    esi; lpSubKey
0x1002f14c  push    edi; hKey
0x1002f14d  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x1002f153  mov     ecx, eax
0x1002f155  test    ecx, ecx
0x1002f157  jnz     short loc_1002F1A9
0x1002f159  jmp     short loc_1002F16C
0x1002f15b  mov     ecx, [esp+230h+hKey]; hKey
0x1002f15f  lea     edx, [esp+230h+SubKey]; lpSubKey
0x1002f163  call    _EliminateSubKey@8; EliminateSubKey(x,x)
0x1002f168  test    eax, eax
0x1002f16a  jnz     short loc_1002F195
0x1002f16c  lea     eax, [esp+230h+ftLastWriteTime]
0x1002f170  mov     [esp+230h+cchName], 104h
0x1002f178  push    eax; lpftLastWriteTime
0x1002f179  push    ebx; lpcchClass
0x1002f17a  push    ebx; lpClass
0x1002f17b  push    ebx; lpReserved
0x1002f17c  lea     eax, [esp+240h+cchName]
0x1002f180  push    eax; lpcchName
0x1002f181  lea     eax, [esp+244h+SubKey]
0x1002f185  push    eax; lpName
0x1002f186  push    ebx; dwIndex
0x1002f187  push    [esp+24Ch+hKey]; hKey
0x1002f18b  call    ds:__imp__RegEnumKeyExW@32; RegEnumKeyExW(x,x,x,x,x,x,x,x)
0x1002f191  test    eax, eax
0x1002f193  jz      short loc_1002F15B
0x1002f195  push    [esp+230h+hKey]; hKey
0x1002f199  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1002f19f  push    esi; lpSubKey
0x1002f1a0  push    edi; hKey
0x1002f1a1  call    ds:__imp__RegDeleteKeyW@8; RegDeleteKeyW(x,x)
0x1002f1a7  mov     ecx, eax
0x1002f1a9  movzx   eax, cx
0x1002f1ac  or      eax, 80070000h
0x1002f1b1  test    ecx, ecx
0x1002f1b3  cmovle  eax, ecx
0x1002f1b6  jmp     short loc_1002F1BD
0x1002f1b8  mov     eax, 80004005h
0x1002f1bd  mov     ecx, [esp+230h+var_4]
0x1002f1c4  pop     edi
0x1002f1c5  pop     esi
0x1002f1c6  pop     ebx
0x1002f1c7  xor     ecx, esp; StackCookie
0x1002f1c9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002f1ce  mov     esp, ebp
0x1002f1d0  pop     ebp
0x1002f1d1  retn
```

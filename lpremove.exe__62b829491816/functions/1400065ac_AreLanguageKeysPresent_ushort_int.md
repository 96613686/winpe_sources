# AreLanguageKeysPresent(ushort *,int)

- ea: `0x1400065ac`
- end: `0x1400066bd`
- name: `?AreLanguageKeysPresent@@YAHPEAGH@Z`
- size: `273`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000d8b8`

## callees

- `0x1400065ac`
- `0x140006a50`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140006680`
- `ADVAPI32!RegCloseKey` at `0x1400066aa`
- `ADVAPI32!RegCloseKey` at `0x140006680`
- `ADVAPI32!RegCloseKey` at `0x1400066aa`
- `ADVAPI32!RegOpenKeyExW` at `0x1400065e8`
- `ADVAPI32!RegOpenKeyExW` at `0x1400065e8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140006663`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140006663`
- `ADVAPI32!RegDeleteKeyW` at `0x140006697`
- `ADVAPI32!RegDeleteKeyW` at `0x140006697`

## pseudocode

```c
__int64 __fastcall AreLanguageKeysPresent(LPCWSTR lpSubKey, int a2)
{
  DWORD cSubKeys; // [rsp+80h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  cSubKeys = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hKey) )
  {
    if ( a2 )
      DeleteInUseLanguagesFromPendingKey(hKey);
    RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( cSubKeys )
    {
      if ( hKey )
        RegCloseKey(hKey);
      return 1;
    }
    RegDeleteKeyW(HKEY_LOCAL_MACHINE, lpSubKey);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1400065ac  mov     rax, rsp
0x1400065af  mov     [rax+8], rbx
0x1400065b3  push    rdi
0x1400065b4  sub     rsp, 60h
0x1400065b8  mov     edi, edx
0x1400065ba  mov     qword ptr [rax+20h], 0
0x1400065c2  mov     dword ptr [rax+18h], 0
0x1400065c9  lea     rax, [rax+20h]
0x1400065cd  mov     rdx, rcx; lpSubKey
0x1400065d0  mov     [rsp+68h+phkResult], rax; phkResult
0x1400065d5  mov     rbx, rcx
0x1400065d8  mov     r9d, 2001Fh; samDesired
0x1400065de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400065e5  xor     r8d, r8d; ulOptions
0x1400065e8  call    cs:__imp_RegOpenKeyExW
0x1400065ee  test    eax, eax
0x1400065f0  jnz     loc_14000669D
0x1400065f6  test    edi, edi
0x1400065f8  jz      short loc_140006607
0x1400065fa  mov     rcx, [rsp+68h+hKey]; hKey
0x140006602  call    ?DeleteInUseLanguagesFromPendingKey@@YAJPEAUHKEY__@@@Z; DeleteInUseLanguagesFromPendingKey(HKEY__ *)
0x140006607  mov     rcx, [rsp+68h+hKey]; hKey
0x14000660f  lea     rax, [rsp+68h+cSubKeys]
0x140006617  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140006620  xor     r9d, r9d; lpReserved
0x140006623  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x14000662c  xor     r8d, r8d; lpcchClass
0x14000662f  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x140006638  xor     edx, edx; lpClass
0x14000663a  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x140006643  mov     [rsp+68h+lpcValues], 0; lpcValues
0x14000664c  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x140006655  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x14000665e  mov     [rsp+68h+phkResult], rax; lpcSubKeys
0x140006663  call    cs:__imp_RegQueryInfoKeyW
0x140006669  cmp     [rsp+68h+cSubKeys], 0
0x140006671  jbe     short loc_14000668D
0x140006673  mov     rcx, [rsp+68h+hKey]; hKey
0x14000667b  test    rcx, rcx
0x14000667e  jz      short loc_140006686
0x140006680  call    cs:__imp_RegCloseKey
0x140006686  mov     eax, 1
0x14000668b  jmp     short loc_1400066B2
0x14000668d  mov     rdx, rbx; lpSubKey
0x140006690  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006697  call    cs:__imp_RegDeleteKeyW
0x14000669d  mov     rcx, [rsp+68h+hKey]; hKey
0x1400066a5  test    rcx, rcx
0x1400066a8  jz      short loc_1400066B0
0x1400066aa  call    cs:__imp_RegCloseKey
0x1400066b0  xor     eax, eax
0x1400066b2  mov     rbx, [rsp+68h+arg_0]
0x1400066b7  add     rsp, 60h
0x1400066bb  pop     rdi
0x1400066bc  retn
```

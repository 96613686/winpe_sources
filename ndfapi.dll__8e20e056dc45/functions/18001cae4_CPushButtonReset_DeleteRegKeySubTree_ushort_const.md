# CPushButtonReset::DeleteRegKeySubTree(ushort const *)

- ea: `0x18001cae4`
- end: `0x18001cc33`
- name: `?DeleteRegKeySubTree@CPushButtonReset@@CAKPEBG@Z`
- size: `335`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001cc3c`

## callees

- `0x18001cae4`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `ADVAPI32!RegEnumKeyW` at `0x18001cbd7`
- `ADVAPI32!RegEnumKeyW` at `0x18001cbd7`
- `ADVAPI32!RegOpenKeyExW` at `0x18001cb3d`
- `ADVAPI32!RegOpenKeyExW` at `0x18001cb3d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001cba3`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001cba3`
- `ADVAPI32!RegCloseKey` at `0x18001cc07`
- `ADVAPI32!RegCloseKey` at `0x18001cc07`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001cbeb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001cbeb`

## pseudocode

```c
__int64 __fastcall CPushButtonReset::DeleteRegKeySubTree(LPCWSTR lpSubKey)
{
  unsigned int v1; // edi
  DWORD v2; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  cSubKeys = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( !v1 )
  {
    RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v2 = cSubKeys;
    if ( cSubKeys )
    {
      while ( (--v2 & 0x80000000) == 0 )
      {
        memset_0(Name, 0, 0x20Au);
        if ( !RegEnumKeyW(hKey, v2, Name, 0x105u) )
          v1 = RegDeleteTreeW(hKey, Name);
      }
    }
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x18001cae4  mov     [rsp-8+arg_8], rbx
0x18001cae9  mov     [rsp-8+arg_10], rdi
0x18001caee  push    rbp
0x18001caef  lea     rbp, [rsp-190h]
0x18001caf7  sub     rsp, 290h
0x18001cafe  mov     rax, cs:__security_cookie
0x18001cb05  xor     rax, rsp
0x18001cb08  mov     [rbp+190h+var_10], rax
0x18001cb0f  lea     rax, [rsp+290h+hKey]
0x18001cb14  mov     [rsp+290h+hKey], 0
0x18001cb1d  mov     rdx, rcx; lpSubKey
0x18001cb20  mov     [rsp+290h+phkResult], rax; phkResult
0x18001cb25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cb2c  mov     [rsp+290h+cSubKeys], 0
0x18001cb34  mov     r9d, 20019h; samDesired
0x18001cb3a  xor     r8d, r8d; ulOptions
0x18001cb3d  call    cs:__imp_RegOpenKeyExW
0x18001cb43  mov     edi, eax
0x18001cb45  test    eax, eax
0x18001cb47  jnz     loc_18001CC0D
0x18001cb4d  mov     rcx, [rsp+290h+hKey]; hKey
0x18001cb52  lea     rax, [rsp+290h+cSubKeys]
0x18001cb57  mov     [rsp+290h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001cb60  xor     r9d, r9d; lpReserved
0x18001cb63  mov     [rsp+290h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18001cb6c  xor     r8d, r8d; lpcchClass
0x18001cb6f  mov     [rsp+290h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18001cb78  xor     edx, edx; lpClass
0x18001cb7a  mov     [rsp+290h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18001cb83  mov     [rsp+290h+lpcValues], 0; lpcValues
0x18001cb8c  mov     [rsp+290h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18001cb95  mov     [rsp+290h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18001cb9e  mov     [rsp+290h+phkResult], rax; lpcSubKeys
0x18001cba3  call    cs:__imp_RegQueryInfoKeyW
0x18001cba9  mov     ebx, [rsp+290h+cSubKeys]
0x18001cbad  test    ebx, ebx
0x18001cbaf  jz      short loc_18001CBF8
0x18001cbb1  jmp     short loc_18001CBF3
0x18001cbb3  xor     edx, edx; Val
0x18001cbb5  lea     rcx, [rsp+290h+Name]; void *
0x18001cbba  mov     r8d, 20Ah; Size
0x18001cbc0  call    memset_0
0x18001cbc5  mov     rcx, [rsp+290h+hKey]; hKey
0x18001cbca  lea     r8, [rsp+290h+Name]; lpName
0x18001cbcf  mov     r9d, 105h; cchName
0x18001cbd5  mov     edx, ebx; dwIndex
0x18001cbd7  call    cs:__imp_RegEnumKeyW
0x18001cbdd  test    eax, eax
0x18001cbdf  jnz     short loc_18001CBF3
0x18001cbe1  mov     rcx, [rsp+290h+hKey]; hKey
0x18001cbe6  lea     rdx, [rsp+290h+Name]; lpSubKey
0x18001cbeb  call    cs:__imp_RegDeleteTreeW
0x18001cbf1  mov     edi, eax
0x18001cbf3  sub     ebx, 1
0x18001cbf6  jns     short loc_18001CBB3
0x18001cbf8  mov     rcx, [rsp+290h+hKey]; hKey
0x18001cbfd  lea     rax, [rcx-1]
0x18001cc01  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001cc05  ja      short loc_18001CC0D
0x18001cc07  call    cs:__imp_RegCloseKey
0x18001cc0d  mov     eax, edi
0x18001cc0f  mov     rcx, [rbp+190h+var_10]
0x18001cc16  xor     rcx, rsp; StackCookie
0x18001cc19  call    __security_check_cookie
0x18001cc1e  lea     r11, [rsp+290h+var_s0]
0x18001cc26  mov     rbx, [r11+18h]
0x18001cc2a  mov     rdi, [r11+20h]
0x18001cc2e  mov     rsp, r11
0x18001cc31  pop     rbp
0x18001cc32  retn
```

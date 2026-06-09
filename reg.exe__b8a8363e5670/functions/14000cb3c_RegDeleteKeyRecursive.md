# RegDeleteKeyRecursive

- ea: `0x14000cb3c`
- end: `0x14000cd1d`
- name: `RegDeleteKeyRecursive`
- size: `481`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000ae58`
- `0x14000cb3c`

## callees

- `0x14000cb3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000cba1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000cba1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000cc8f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000cc8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000cc50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ccdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000cc50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ccdc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14000ccf4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14000ccf4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000cc0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000cc0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000cccc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000cccc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000cc35`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000cc35`

## pseudocode

```c
LSTATUS __fastcall RegDeleteKeyRecursive(HKEY a1, const WCHAR *a2, REGSAM a3)
{
  LSTATUS v6; // eax
  int v7; // ebx
  WCHAR *v8; // rdi
  DWORD v10; // ebx
  LSTATUS v11; // ecx
  DWORD v12; // eax
  HKEY hKey; // [rsp+60h] [rbp+7h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+68h] [rbp+Fh] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp+13h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+70h] [rbp+17h] BYREF
  DWORD cValues; // [rsp+74h] [rbp+1Bh] BYREF
  DWORD cbMaxClassLen; // [rsp+78h] [rbp+1Fh] BYREF
  DWORD cchClass; // [rsp+7Ch] [rbp+23h] BYREF
  DWORD cchName; // [rsp+80h] [rbp+27h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+88h] [rbp+2Fh] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+D0h] [rbp+77h] BYREF
  DWORD cSubKeys; // [rsp+D8h] [rbp+7Fh] BYREF

  hKey = 0;
  cchClass = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  if ( !RegOpenKeyExW(a1, a2, 0, a3 | 9, &hKey) )
  {
    v6 = RegQueryInfoKeyW(
           hKey,
           0,
           &cchClass,
           0,
           &cSubKeys,
           &cbMaxSubKeyLen,
           &cbMaxClassLen,
           &cValues,
           &cbMaxValueNameLen,
           &cbMaxValueLen,
           &cbSecurityDescriptor,
           &ftLastWriteTime);
    v7 = v6;
    if ( v6 && v6 != 234 && v6 != 122 )
      goto LABEL_7;
    v8 = (WCHAR *)LocalAlloc(0x40u, 2LL * (cbMaxSubKeyLen + 1));
    if ( !v8 )
    {
      v7 = 8;
LABEL_7:
      RegCloseKey(hKey);
      return v7;
    }
    v10 = 0;
    do
    {
      cchName = cbMaxSubKeyLen + 1;
      v11 = RegEnumKeyExW(hKey, v10, v8, &cchName, 0, 0, 0, 0);
      if ( !v11 )
        v11 = RegDeleteKeyRecursive(hKey, v8, a3);
      v12 = v10 + 1;
      if ( !v11 )
        v12 = v10;
      v10 = v12;
    }
    while ( v11 != 259 && v12 < cSubKeys );
    LocalFree(v8);
    RegCloseKey(hKey);
  }
  return RegDeleteKeyExW(a1, a2, a3, 0);
}

```

## disassembly

```asm
0x14000cb3c  mov     [rsp-8+arg_0], rbx
0x14000cb41  mov     [rsp-8+arg_8], rsi
0x14000cb46  push    rbp
0x14000cb47  push    rdi
0x14000cb48  push    r12
0x14000cb4a  push    r14
0x14000cb4c  push    r15
0x14000cb4e  lea     rbp, [rsp-37h]
0x14000cb53  sub     rsp, 90h
0x14000cb5a  xor     r12d, r12d
0x14000cb5d  lea     rax, [rbp+57h+hKey]
0x14000cb61  mov     r9d, r8d
0x14000cb64  mov     [rbp+57h+hKey], r12
0x14000cb68  mov     esi, r8d
0x14000cb6b  mov     [rbp+57h+cchClass], r12d
0x14000cb6f  or      r9d, 9; samDesired
0x14000cb73  mov     [rbp+57h+cSubKeys], r12d
0x14000cb77  xor     r8d, r8d; ulOptions
0x14000cb7a  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x14000cb7e  mov     r14, rdx
0x14000cb81  mov     [rbp+57h+cbMaxClassLen], r12d
0x14000cb85  mov     r15, rcx
0x14000cb88  mov     [rbp+57h+cValues], r12d
0x14000cb8c  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x14000cb90  mov     [rbp+57h+cbMaxValueLen], r12d
0x14000cb94  mov     [rbp+57h+cbSecurityDescriptor], r12d
0x14000cb98  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r12
0x14000cb9c  mov     [rsp+0B0h+phkResult], rax; phkResult
0x14000cba1  call    cs:__imp_RegOpenKeyExW
0x14000cba8  nop     dword ptr [rax+rax+00h]
0x14000cbad  test    eax, eax
0x14000cbaf  jnz     loc_14000CCE8
0x14000cbb5  mov     rcx, [rbp+57h+hKey]; hKey
0x14000cbb9  lea     rax, [rbp+57h+ftLastWriteTime]
0x14000cbbd  mov     [rsp+0B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14000cbc2  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x14000cbc6  lea     rax, [rbp+57h+cbSecurityDescriptor]
0x14000cbca  xor     r9d, r9d; lpReserved
0x14000cbcd  mov     [rsp+0B0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x14000cbd2  xor     edx, edx; lpClass
0x14000cbd4  lea     rax, [rbp+57h+cbMaxValueLen]
0x14000cbd8  mov     [rsp+0B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x14000cbdd  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x14000cbe1  mov     [rsp+0B0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x14000cbe6  lea     rax, [rbp+57h+cValues]
0x14000cbea  mov     [rsp+0B0h+lpcValues], rax; lpcValues
0x14000cbef  lea     rax, [rbp+57h+cbMaxClassLen]
0x14000cbf3  mov     [rsp+0B0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x14000cbf8  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14000cbfc  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14000cc01  lea     rax, [rbp+57h+cSubKeys]
0x14000cc05  mov     [rsp+0B0h+phkResult], rax; lpcSubKeys
0x14000cc0a  call    cs:__imp_RegQueryInfoKeyW
0x14000cc11  nop     dword ptr [rax+rax+00h]
0x14000cc16  mov     ebx, eax
0x14000cc18  test    eax, eax
0x14000cc1a  jz      short loc_14000CC28
0x14000cc1c  cmp     eax, 0EAh
0x14000cc21  jz      short loc_14000CC28
0x14000cc23  cmp     eax, 7Ah ; 'z'
0x14000cc26  jnz     short loc_14000CC4C
0x14000cc28  mov     edx, [rbp+57h+cbMaxSubKeyLen]
0x14000cc2b  mov     ecx, 40h ; '@'; uFlags
0x14000cc30  inc     edx
0x14000cc32  add     rdx, rdx; uBytes
0x14000cc35  call    cs:__imp_LocalAlloc
0x14000cc3c  nop     dword ptr [rax+rax+00h]
0x14000cc41  mov     rdi, rax
0x14000cc44  test    rax, rax
0x14000cc47  jnz     short loc_14000CC63
0x14000cc49  lea     ebx, [rax+8]
0x14000cc4c  mov     rcx, [rbp+57h+hKey]; hKey
0x14000cc50  call    cs:__imp_RegCloseKey
0x14000cc57  nop     dword ptr [rax+rax+00h]
0x14000cc5c  mov     eax, ebx
0x14000cc5e  jmp     loc_14000CD00
0x14000cc63  mov     ebx, r12d
0x14000cc66  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x14000cc69  lea     r9, [rbp+57h+cchName]; lpcchName
0x14000cc6d  mov     rcx, [rbp+57h+hKey]; hKey
0x14000cc71  inc     eax
0x14000cc73  mov     [rsp+0B0h+lpcValues], r12; lpftLastWriteTime
0x14000cc78  mov     r8, rdi; lpName
0x14000cc7b  mov     [rsp+0B0h+lpcbMaxClassLen], r12; lpcchClass
0x14000cc80  mov     edx, ebx; dwIndex
0x14000cc82  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r12; lpClass
0x14000cc87  mov     [rbp+57h+cchName], eax
0x14000cc8a  mov     [rsp+0B0h+phkResult], r12; lpReserved
0x14000cc8f  call    cs:__imp_RegEnumKeyExW
0x14000cc96  nop     dword ptr [rax+rax+00h]
0x14000cc9b  mov     ecx, eax
0x14000cc9d  test    eax, eax
0x14000cc9f  jnz     short loc_14000CCB2
0x14000cca1  mov     rcx, [rbp+57h+hKey]
0x14000cca5  mov     r8d, esi
0x14000cca8  mov     rdx, rdi
0x14000ccab  call    RegDeleteKeyRecursive
0x14000ccb0  mov     ecx, eax
0x14000ccb2  test    ecx, ecx
0x14000ccb4  lea     eax, [rbx+1]
0x14000ccb7  cmovz   eax, ebx
0x14000ccba  mov     ebx, eax
0x14000ccbc  cmp     ecx, 103h
0x14000ccc2  jz      short loc_14000CCC9
0x14000ccc4  cmp     eax, [rbp+57h+cSubKeys]
0x14000ccc7  jb      short loc_14000CC66
0x14000ccc9  mov     rcx, rdi; hMem
0x14000cccc  call    cs:__imp_LocalFree
0x14000ccd3  nop     dword ptr [rax+rax+00h]
0x14000ccd8  mov     rcx, [rbp+57h+hKey]; hKey
0x14000ccdc  call    cs:__imp_RegCloseKey
0x14000cce3  nop     dword ptr [rax+rax+00h]
0x14000cce8  xor     r9d, r9d; Reserved
0x14000cceb  mov     r8d, esi; samDesired
0x14000ccee  mov     rdx, r14; lpSubKey
0x14000ccf1  mov     rcx, r15; hKey
0x14000ccf4  call    cs:__imp_RegDeleteKeyExW
0x14000ccfb  nop     dword ptr [rax+rax+00h]
0x14000cd00  lea     r11, [rsp+0B0h+var_20]
0x14000cd08  mov     rbx, [r11+30h]
0x14000cd0c  mov     rsi, [r11+38h]
0x14000cd10  mov     rsp, r11
0x14000cd13  pop     r15
0x14000cd15  pop     r14
0x14000cd17  pop     r12
0x14000cd19  pop     rdi
0x14000cd1a  pop     rbp
0x14000cd1b  retn
```

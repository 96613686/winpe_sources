# Intl_CopyRegKeyValues(HKEY__ *,HKEY__ *)

- ea: `0x180024c0c`
- end: `0x180024d9d`
- name: `?Intl_CopyRegKeyValues@@YAKPEAUHKEY__@@0@Z`
- size: `401`
- prototype: `unsigned int __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180024da4`

## callees

- `0x180024c0c`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024cb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024cb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024cc8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024cc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024d6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024d6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024d48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024d48`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180024d20`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180024d20`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180024c9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180024c9a`

## pseudocode

```c
__int64 __fastcall Intl_CopyRegKeyValues(HKEY hKey, HKEY a2)
{
  unsigned int v4; // edi
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v7; // rsi
  DWORD i; // ebx
  HANDLE v9; // rax
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD Type[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[256]; // [rsp+80h] [rbp-80h] BYREF

  cchValueName = 0;
  Type[0] = 0;
  cbData = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, &cbMaxValueLen, 0, 0);
  if ( !v4 )
  {
    if ( cValues )
    {
      v5 = cbMaxValueLen;
      ProcessHeap = GetProcessHeap();
      v7 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v5);
      if ( v7 )
      {
        for ( i = 0; i < cValues; ++i )
        {
          cbData = cbMaxValueLen;
          cchValueName = 256;
          v4 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, Type, v7, &cbData);
          if ( v4 )
            break;
          v4 = RegSetValueExW(a2, ValueName, 0, Type[0], v7, cbData);
          if ( v4 )
            break;
        }
        v9 = GetProcessHeap();
        HeapFree(v9, 0, v7);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180024c0c  mov     [rsp-8+arg_10], rbx
0x180024c11  mov     [rsp-8+arg_18], rsi
0x180024c16  push    rbp
0x180024c17  push    rdi
0x180024c18  push    r12
0x180024c1a  push    r14
0x180024c1c  push    r15
0x180024c1e  lea     rbp, [rsp-190h]
0x180024c26  sub     rsp, 290h
0x180024c2d  mov     rax, cs:__security_cookie
0x180024c34  xor     rax, rsp
0x180024c37  mov     [rbp+1B0h+var_30], rax
0x180024c3e  xor     r12d, r12d
0x180024c41  lea     rax, [rsp+2B0h+cbMaxValueLen]
0x180024c46  mov     [rsp+2B0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180024c4b  mov     r15, rdx
0x180024c4e  mov     [rsp+2B0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180024c53  xor     r9d, r9d; lpReserved
0x180024c56  mov     [rsp+2B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180024c5b  xor     r8d, r8d; lpcchClass
0x180024c5e  mov     [rsp+2B0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180024c63  lea     rax, [rsp+2B0h+cValues]
0x180024c68  mov     [rsp+2B0h+lpcValues], rax; lpcValues
0x180024c6d  xor     edx, edx; lpClass
0x180024c6f  mov     [rsp+2B0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180024c74  mov     r14, rcx
0x180024c77  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180024c7c  mov     [rsp+2B0h+lpcSubKeys], r12; lpcSubKeys
0x180024c81  mov     [rsp+2B0h+cchValueName], r12d
0x180024c86  mov     [rsp+2B0h+Type], r12d
0x180024c8b  mov     [rsp+2B0h+cbData], r12d
0x180024c90  mov     [rsp+2B0h+cValues], r12d
0x180024c95  mov     [rsp+2B0h+cbMaxValueLen], r12d
0x180024c9a  call    cs:__imp_RegQueryInfoKeyW
0x180024ca0  mov     edi, eax
0x180024ca2  test    eax, eax
0x180024ca4  jnz     loc_180024D70
0x180024caa  cmp     [rsp+2B0h+cValues], r12d
0x180024caf  jz      loc_180024D70
0x180024cb5  mov     ebx, [rsp+2B0h+cbMaxValueLen]
0x180024cb9  call    cs:__imp_GetProcessHeap
0x180024cbf  mov     r8d, ebx; dwBytes
0x180024cc2  lea     edx, [rdi+8]; dwFlags
0x180024cc5  mov     rcx, rax; hHeap
0x180024cc8  call    cs:__imp_HeapAlloc
0x180024cce  mov     rsi, rax
0x180024cd1  test    rax, rax
0x180024cd4  jz      loc_180024D70
0x180024cda  mov     ebx, r12d
0x180024cdd  cmp     [rsp+2B0h+cValues], r12d
0x180024ce2  jbe     short loc_180024D5C
0x180024ce4  mov     ecx, [rsp+2B0h+cbMaxValueLen]
0x180024ce8  lea     rax, [rsp+2B0h+cbData]
0x180024ced  mov     [rsp+2B0h+lpcValues], rax; lpcbData
0x180024cf2  lea     r9, [rsp+2B0h+cchValueName]; lpcchValueName
0x180024cf7  lea     rax, [rsp+2B0h+Type]
0x180024cfc  mov     [rsp+2B0h+cbData], ecx
0x180024d00  mov     [rsp+2B0h+lpcbMaxClassLen], rsi; lpData
0x180024d05  lea     r8, [rbp+1B0h+ValueName]; lpValueName
0x180024d09  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rax; lpType
0x180024d0e  mov     edx, ebx; dwIndex
0x180024d10  mov     rcx, r14; hKey
0x180024d13  mov     [rsp+2B0h+lpcSubKeys], r12; lpReserved
0x180024d18  mov     [rsp+2B0h+cchValueName], 100h
0x180024d20  call    cs:__imp_RegEnumValueW
0x180024d26  mov     edi, eax
0x180024d28  test    eax, eax
0x180024d2a  jnz     short loc_180024D5C
0x180024d2c  mov     eax, [rsp+2B0h+cbData]
0x180024d30  lea     rdx, [rbp+1B0h+ValueName]; lpValueName
0x180024d34  mov     r9d, [rsp+2B0h+Type]; dwType
0x180024d39  xor     r8d, r8d; Reserved
0x180024d3c  mov     dword ptr [rsp+2B0h+lpcbMaxSubKeyLen], eax; cbData
0x180024d40  mov     rcx, r15; hKey
0x180024d43  mov     [rsp+2B0h+lpcSubKeys], rsi; lpData
0x180024d48  call    cs:__imp_RegSetValueExW
0x180024d4e  mov     edi, eax
0x180024d50  test    eax, eax
0x180024d52  jnz     short loc_180024D5C
0x180024d54  inc     ebx
0x180024d56  cmp     ebx, [rsp+2B0h+cValues]
0x180024d5a  jb      short loc_180024CE4
0x180024d5c  call    cs:__imp_GetProcessHeap
0x180024d62  mov     r8, rsi; lpMem
0x180024d65  xor     edx, edx; dwFlags
0x180024d67  mov     rcx, rax; hHeap
0x180024d6a  call    cs:__imp_HeapFree
0x180024d70  mov     eax, edi
0x180024d72  mov     rcx, [rbp+1B0h+var_30]
0x180024d79  xor     rcx, rsp; StackCookie
0x180024d7c  call    __security_check_cookie
0x180024d81  lea     r11, [rsp+2B0h+var_20]
0x180024d89  mov     rbx, [r11+40h]
0x180024d8d  mov     rsi, [r11+48h]
0x180024d91  mov     rsp, r11
0x180024d94  pop     r15
0x180024d96  pop     r14
0x180024d98  pop     r12
0x180024d9a  pop     rdi
0x180024d9b  pop     rbp
0x180024d9c  retn
```

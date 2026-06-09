# DeleteRegistryTree

- ea: `0x180017c34`
- end: `0x180017df0`
- name: `DeleteRegistryTree`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180017c34`
- `0x1800294a4`

## callees

- `0x180017c34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017cb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017dc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017cb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017dc8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017cc7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017cc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017dd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017dd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d62`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017c8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017c8e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180017db8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180017db8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017d11`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017da2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017d11`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017da2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017d4b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017d4b`

## pseudocode

```c
LSTATUS __fastcall DeleteRegistryTree(HKEY a1)
{
  LSTATUS result; // eax
  DWORD v3; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v5; // rdi
  int v6; // ebx
  DWORD v7; // eax
  DWORD i; // ebx
  DWORD v9; // ebx
  HANDLE v10; // rax
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-10h] BYREF
  DWORD cValues[2]; // [rsp+68h] [rbp-8h] BYREF
  DWORD lpcbMaxSubKeyLen; // [rsp+A8h] [rbp+38h] BYREF
  DWORD cchName; // [rsp+B0h] [rbp+40h] BYREF
  DWORD lpcSubKeys; // [rsp+B8h] [rbp+48h] BYREF

  lpcSubKeys = 0;
  lpcbMaxSubKeyLen = 0;
  cbMaxValueNameLen = 0;
  cchName = 0;
  *(_QWORD *)cValues = 0;
  result = RegQueryInfoKeyW(a1, 0, 0, 0, &lpcSubKeys, &lpcbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( !result )
  {
    if ( 2 * (unsigned __int64)++lpcbMaxSubKeyLen > 0xFFFFFFFF )
      return 534;
    v3 = 2 * lpcbMaxSubKeyLen;
    ProcessHeap = GetProcessHeap();
    v5 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v3);
    if ( !v5 )
      return 8;
    v7 = lpcSubKeys;
    for ( i = 0; i < lpcSubKeys; ++i )
    {
      cchName = lpcbMaxSubKeyLen;
      if ( !RegEnumKeyExW(a1, i, v5, &cchName, 0, 0, 0, 0)
        && !RegCreateKeyExW(a1, v5, 0, 0, 0, 0x3001Fu, 0, (PHKEY)cValues, &cbMaxValueNameLen) )
      {
        DeleteRegistryTree(*(_QWORD *)cValues);
        RegCloseKey(*(HKEY *)cValues);
      }
      v7 = lpcSubKeys;
    }
    v9 = 0;
    if ( v7 )
    {
      do
      {
        cchName = lpcbMaxSubKeyLen;
        if ( !RegEnumKeyExW(a1, 0, v5, &cchName, 0, 0, 0, 0) )
          RegDeleteKeyExW(a1, v5, 0, 0);
        ++v9;
      }
      while ( v9 < lpcSubKeys );
    }
    v6 = 0;
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v5);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180017c34  mov     r11, rsp
0x180017c37  push    rbp
0x180017c38  push    rbx
0x180017c39  push    rsi
0x180017c3a  push    rdi
0x180017c3b  push    r14
0x180017c3d  mov     rbp, rsp
0x180017c40  sub     rsp, 70h
0x180017c44  xor     r14d, r14d
0x180017c47  lea     rax, [rbp+arg_8]
0x180017c4b  mov     [r11-40h], r14
0x180017c4f  xor     r9d, r9d; lpReserved
0x180017c52  mov     [r11-48h], r14
0x180017c56  xor     r8d, r8d; lpcchClass
0x180017c59  mov     [r11-50h], r14
0x180017c5d  xor     edx, edx; lpClass
0x180017c5f  mov     [r11-58h], r14
0x180017c63  mov     rsi, rcx
0x180017c66  mov     [r11-60h], r14
0x180017c6a  mov     [r11-68h], r14
0x180017c6e  mov     [r11-70h], rax
0x180017c72  lea     rax, [rbp+arg_18]
0x180017c76  mov     [r11-78h], rax
0x180017c7a  mov     [rbp+arg_18], r14d
0x180017c7e  mov     [rbp+arg_8], r14d
0x180017c82  mov     [rbp+cbMaxValueNameLen], r14d
0x180017c86  mov     [rbp+cchName], r14d
0x180017c8a  mov     qword ptr [rbp+cValues], r14
0x180017c8e  call    cs:__imp_RegQueryInfoKeyW
0x180017c94  test    eax, eax
0x180017c96  jnz     loc_180017DE5
0x180017c9c  mov     eax, [rbp+arg_8]
0x180017c9f  inc     eax
0x180017ca1  mov     ecx, eax
0x180017ca3  mov     [rbp+arg_8], eax
0x180017ca6  add     rcx, rcx
0x180017ca9  mov     eax, 0FFFFFFFFh
0x180017cae  cmp     rcx, rax
0x180017cb1  ja      loc_180017DDE
0x180017cb7  mov     ebx, ecx
0x180017cb9  call    cs:__imp_GetProcessHeap
0x180017cbf  mov     r8d, ebx; dwBytes
0x180017cc2  xor     edx, edx; dwFlags
0x180017cc4  mov     rcx, rax; hHeap
0x180017cc7  call    cs:__imp_HeapAlloc
0x180017ccd  mov     rdi, rax
0x180017cd0  test    rax, rax
0x180017cd3  jnz     short loc_180017CDD
0x180017cd5  lea     ebx, [rax+8]
0x180017cd8  jmp     loc_180017DE3
0x180017cdd  mov     eax, [rbp+arg_18]
0x180017ce0  mov     ebx, r14d
0x180017ce3  test    eax, eax
0x180017ce5  jz      loc_180017D75
0x180017ceb  mov     eax, [rbp+arg_8]
0x180017cee  lea     r9, [rbp+cchName]; lpcchName
0x180017cf2  mov     [rsp+70h+lpcValues], r14; lpftLastWriteTime
0x180017cf7  mov     r8, rdi; lpName
0x180017cfa  mov     [rsp+70h+lpcbMaxClassLen], r14; lpcchClass
0x180017cff  mov     edx, ebx; dwIndex
0x180017d01  mov     [rsp+70h+lpcbMaxSubKeyLen], r14; lpClass
0x180017d06  mov     rcx, rsi; hKey
0x180017d09  mov     [rsp+70h+lpcSubKeys], r14; lpReserved
0x180017d0e  mov     [rbp+cchName], eax
0x180017d11  call    cs:__imp_RegEnumKeyExW
0x180017d17  test    eax, eax
0x180017d19  jnz     short loc_180017D68
0x180017d1b  lea     rax, [rbp+cbMaxValueNameLen]
0x180017d1f  xor     r9d, r9d; lpClass
0x180017d22  mov     [rsp+70h+lpcbMaxValueNameLen], rax; lpdwDisposition
0x180017d27  xor     r8d, r8d; Reserved
0x180017d2a  lea     rax, [rbp+cValues]
0x180017d2e  mov     rdx, rdi; lpSubKey
0x180017d31  mov     [rsp+70h+lpcValues], rax; phkResult
0x180017d36  mov     rcx, rsi; hKey
0x180017d39  mov     [rsp+70h+lpcbMaxClassLen], r14; lpSecurityAttributes
0x180017d3e  mov     dword ptr [rsp+70h+lpcbMaxSubKeyLen], 3001Fh; samDesired
0x180017d46  mov     dword ptr [rsp+70h+lpcSubKeys], r14d; dwOptions
0x180017d4b  call    cs:__imp_RegCreateKeyExW
0x180017d51  test    eax, eax
0x180017d53  jnz     short loc_180017D68
0x180017d55  mov     rcx, qword ptr [rbp+cValues]
0x180017d59  call    DeleteRegistryTree
0x180017d5e  mov     rcx, qword ptr [rbp+cValues]; hKey
0x180017d62  call    cs:__imp_RegCloseKey
0x180017d68  mov     eax, [rbp+arg_18]
0x180017d6b  inc     ebx
0x180017d6d  cmp     ebx, eax
0x180017d6f  jb      loc_180017CEB
0x180017d75  mov     ebx, r14d
0x180017d78  test    eax, eax
0x180017d7a  jz      short loc_180017DC5
0x180017d7c  mov     eax, [rbp+arg_8]
0x180017d7f  lea     r9, [rbp+cchName]; lpcchName
0x180017d83  mov     [rsp+70h+lpcValues], r14; lpftLastWriteTime
0x180017d88  mov     r8, rdi; lpName
0x180017d8b  mov     [rsp+70h+lpcbMaxClassLen], r14; lpcchClass
0x180017d90  xor     edx, edx; dwIndex
0x180017d92  mov     [rsp+70h+lpcbMaxSubKeyLen], r14; lpClass
0x180017d97  mov     rcx, rsi; hKey
0x180017d9a  mov     [rsp+70h+lpcSubKeys], r14; lpReserved
0x180017d9f  mov     [rbp+cchName], eax
0x180017da2  call    cs:__imp_RegEnumKeyExW
0x180017da8  test    eax, eax
0x180017daa  jnz     short loc_180017DBE
0x180017dac  xor     r9d, r9d; Reserved
0x180017daf  xor     r8d, r8d; samDesired
0x180017db2  mov     rdx, rdi; lpSubKey
0x180017db5  mov     rcx, rsi; hKey
0x180017db8  call    cs:__imp_RegDeleteKeyExW
0x180017dbe  inc     ebx
0x180017dc0  cmp     ebx, [rbp+arg_18]
0x180017dc3  jb      short loc_180017D7C
0x180017dc5  mov     ebx, r14d
0x180017dc8  call    cs:__imp_GetProcessHeap
0x180017dce  mov     r8, rdi; lpMem
0x180017dd1  xor     edx, edx; dwFlags
0x180017dd3  mov     rcx, rax; hHeap
0x180017dd6  call    cs:__imp_HeapFree
0x180017ddc  jmp     short loc_180017DE3
0x180017dde  mov     ebx, 216h
0x180017de3  mov     eax, ebx
0x180017de5  add     rsp, 70h
0x180017de9  pop     r14
0x180017deb  pop     rdi
0x180017dec  pop     rsi
0x180017ded  pop     rbx
0x180017dee  pop     rbp
0x180017def  retn
```

# GPRegDelnode(HKEY__ *,ushort const *)

- ea: `0x18002f6e0`
- end: `0x18002f874`
- name: `?GPRegDelnode@@YAKPEAUHKEY__@@PEBG@Z`
- size: `404`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009a90`
- `0x18002d9b8`
- `0x18002ddc4`
- `0x18002e188`
- `0x18002e5a0`
- `0x18002f6e0`
- `0x180034870`
- `0x1800631a8`
- `0x18009d1f8`
- `0x18009d4a8`
- `0x18009fbb0`

## callees

- `0x18002f6e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f7b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f7b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f821`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f821`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f818`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f818`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002f78a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002f78a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002f708`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002f833`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002f708`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002f833`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f732`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f732`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f806`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f806`

## pseudocode

```c
unsigned int __fastcall GPRegDelnode(HKEY a1, const unsigned __int16 *a2)
{
  unsigned int result; // eax
  WCHAR *v5; // rdi
  unsigned __int64 v6; // rcx
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-28h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+98h] [rbp+10h] BYREF
  DWORD cchName; // [rsp+A0h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+20h] BYREF

  hKey = 0;
  cbMaxSubKeyLen = 0;
  if ( !a2 || !RegDeleteKeyExW(a1, a2, 0, 0) )
    return 0;
  result = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  if ( result )
  {
    if ( result == 2 )
      return 0;
  }
  else
  {
    v5 = 0;
    if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
    {
      v6 = 2LL * ++cbMaxSubKeyLen;
      if ( v6 <= 0xFFFFFFFF )
      {
        v5 = (WCHAR *)LocalAlloc(0, (unsigned int)v6);
        if ( v5 )
        {
          do
          {
            cchName = cbMaxSubKeyLen;
            ftLastWriteTime = 0;
          }
          while ( !RegEnumKeyExW(hKey, 0, v5, &cchName, 0, 0, 0, &ftLastWriteTime) && !GPRegDelnode(hKey, v5) );
        }
      }
    }
    RegCloseKey(hKey);
    LocalFree(v5);
    return RegDeleteKeyExW(a1, a2, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18002f6e0  mov     rax, rsp
0x18002f6e3  push    rbx
0x18002f6e4  push    rbp
0x18002f6e5  push    rsi
0x18002f6e6  sub     rsp, 70h
0x18002f6ea  xor     ebp, ebp
0x18002f6ec  mov     rbx, rdx
0x18002f6ef  mov     [rax+20h], rbp
0x18002f6f3  mov     rsi, rcx
0x18002f6f6  mov     [rax+10h], ebp
0x18002f6f9  test    rdx, rdx
0x18002f6fc  jz      loc_18002F849
0x18002f702  xor     r9d, r9d; Reserved
0x18002f705  xor     r8d, r8d; samDesired
0x18002f708  call    cs:__imp_RegDeleteKeyExW
0x18002f70e  test    eax, eax
0x18002f710  jz      loc_18002F849
0x18002f716  lea     rax, [rsp+88h+hKey]
0x18002f71e  mov     r9d, 20019h; samDesired
0x18002f724  xor     r8d, r8d; ulOptions
0x18002f727  mov     [rsp+88h+phkResult], rax; phkResult
0x18002f72c  mov     rdx, rbx; lpSubKey
0x18002f72f  mov     rcx, rsi; hKey
0x18002f732  call    cs:__imp_RegOpenKeyExW
0x18002f738  test    eax, eax
0x18002f73a  jnz     loc_18002F84D
0x18002f740  mov     rcx, [rsp+88h+hKey]; hKey
0x18002f748  lea     rax, [rsp+88h+cbMaxSubKeyLen]
0x18002f750  mov     [rsp+88h+lpftLastWriteTime], rbp; lpftLastWriteTime
0x18002f755  xor     r9d, r9d; lpReserved
0x18002f758  mov     [rsp+88h+lpcbSecurityDescriptor], rbp; lpcbSecurityDescriptor
0x18002f75d  xor     r8d, r8d; lpcchClass
0x18002f760  mov     [rsp+88h+lpcbMaxValueLen], rbp; lpcbMaxValueLen
0x18002f765  xor     edx, edx; lpClass
0x18002f767  mov     [rsp+88h+lpcbMaxValueNameLen], rbp; lpcbMaxValueNameLen
0x18002f76c  mov     [rsp+88h+lpcValues], rbp; lpcValues
0x18002f771  mov     [rsp+88h+lpcbMaxClassLen], rbp; lpcbMaxClassLen
0x18002f776  mov     [rsp+88h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18002f77b  mov     [rsp+88h+arg_0], rdi
0x18002f783  mov     edi, ebp
0x18002f785  mov     [rsp+88h+phkResult], rbp; lpcSubKeys
0x18002f78a  call    cs:__imp_RegQueryInfoKeyW
0x18002f790  test    eax, eax
0x18002f792  jnz     short loc_18002F810
0x18002f794  mov     eax, [rsp+88h+cbMaxSubKeyLen]
0x18002f79b  inc     eax
0x18002f79d  mov     ecx, eax
0x18002f79f  mov     [rsp+88h+cbMaxSubKeyLen], eax
0x18002f7a6  add     rcx, rcx
0x18002f7a9  mov     eax, 0FFFFFFFFh
0x18002f7ae  cmp     rcx, rax
0x18002f7b1  ja      short loc_18002F810
0x18002f7b3  mov     edx, ecx; uBytes
0x18002f7b5  xor     ecx, ecx; uFlags
0x18002f7b7  call    cs:__imp_LocalAlloc
0x18002f7bd  mov     rdi, rax
0x18002f7c0  test    rax, rax
0x18002f7c3  jz      short loc_18002F810
0x18002f7c5  mov     ecx, [rsp+88h+cbMaxSubKeyLen]
0x18002f7cc  lea     rax, [rsp+88h+ftLastWriteTime]
0x18002f7d1  mov     [rsp+88h+lpcValues], rax; lpftLastWriteTime
0x18002f7d6  lea     r9, [rsp+88h+cchName]; lpcchName
0x18002f7de  mov     [rsp+88h+lpcbMaxClassLen], rbp; lpcchClass
0x18002f7e3  mov     r8, rdi; lpName
0x18002f7e6  mov     [rsp+88h+cchName], ecx
0x18002f7ed  xor     edx, edx; dwIndex
0x18002f7ef  mov     rcx, [rsp+88h+hKey]; hKey
0x18002f7f7  mov     [rsp+88h+lpcbMaxSubKeyLen], rbp; lpClass
0x18002f7fc  mov     [rsp+88h+phkResult], rbp; lpReserved
0x18002f801  mov     qword ptr [rsp+88h+ftLastWriteTime.dwLowDateTime], rbp
0x18002f806  call    cs:__imp_RegEnumKeyExW
0x18002f80c  test    eax, eax
0x18002f80e  jz      short loc_18002F85B
0x18002f810  mov     rcx, [rsp+88h+hKey]; hKey
0x18002f818  call    cs:__imp_RegCloseKey
0x18002f81e  mov     rcx, rdi; hMem
0x18002f821  call    cs:__imp_LocalFree
0x18002f827  xor     r9d, r9d; Reserved
0x18002f82a  xor     r8d, r8d; samDesired
0x18002f82d  mov     rdx, rbx; lpSubKey
0x18002f830  mov     rcx, rsi; hKey
0x18002f833  call    cs:__imp_RegDeleteKeyExW
0x18002f839  mov     rdi, [rsp+88h+arg_0]
0x18002f841  add     rsp, 70h
0x18002f845  pop     rsi
0x18002f846  pop     rbp
0x18002f847  pop     rbx
0x18002f848  retn
0x18002f849  xor     eax, eax
0x18002f84b  jmp     short loc_18002F841
0x18002f84d  cmp     eax, 2
0x18002f850  cmovz   eax, ebp
0x18002f853  add     rsp, 70h
0x18002f857  pop     rsi
0x18002f858  pop     rbp
0x18002f859  pop     rbx
0x18002f85a  retn
0x18002f85b  mov     rcx, [rsp+88h+hKey]; HKEY
0x18002f863  mov     rdx, rdi; unsigned __int16 *
0x18002f866  call    ?GPRegDelnode@@YAKPEAUHKEY__@@PEBG@Z; GPRegDelnode(HKEY__ *,ushort const *)
0x18002f86b  test    eax, eax
0x18002f86d  jnz     short loc_18002F810
0x18002f86f  jmp     loc_18002F7C5
```

# CDims::_CSessionBounceLock::Lock(void)

- ea: `0x180002cc0`
- end: `0x180002d57`
- name: `?Lock@_CSessionBounceLock@CDims@@QEAA_NXZ`
- size: `151`
- prototype: `_BOOL8 __fastcall(CDims::_CSessionBounceLock *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800078e0`

## callees

- `0x180002cc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d39`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002d14`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002d14`

## pseudocode

```c
_BOOL8 __fastcall CDims::_CSessionBounceLock::Lock(CDims::_CSessionBounceLock *this)
{
  bool v2; // bl
  HKEY v3; // rcx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  dwDisposition = 0;
  if ( RegCreateKeyExW(
         (HKEY)((*((_BYTE *)this + 9) != 0) - 0x7FFFFFFFLL),
         *(LPCWSTR *)this,
         0,
         0,
         1u,
         0x20006u,
         0,
         &hKey,
         &dwDisposition) )
  {
    v3 = 0;
    hKey = 0;
  }
  else
  {
    v3 = hKey;
    if ( hKey )
      v2 = dwDisposition == 1;
  }
  *((_BYTE *)this + 8) = v2;
  if ( v3 )
    RegCloseKey(v3);
  return v2;
}

```

## disassembly

```asm
0x180002cc0  mov     [rsp+arg_10], rbx
0x180002cc5  push    rdi
0x180002cc6  sub     rsp, 50h
0x180002cca  mov     rdi, rcx
0x180002ccd  lea     rax, [rsp+58h+dwDisposition]
0x180002cd2  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180002cd7  xor     ebx, ebx
0x180002cd9  mov     ecx, ebx
0x180002cdb  mov     [rsp+58h+dwDisposition], ebx
0x180002cdf  lea     rax, [rsp+58h+hKey]
0x180002ce4  cmp     [rdi+9], cl
0x180002ce7  mov     rdx, [rdi]; lpSubKey
0x180002cea  setnz   cl
0x180002ced  mov     [rsp+58h+phkResult], rax; phkResult
0x180002cf2  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180002cf7  add     rcx, 0FFFFFFFF80000001h; hKey
0x180002cfe  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180002d06  xor     r9d, r9d; lpClass
0x180002d09  xor     r8d, r8d; Reserved
0x180002d0c  mov     [rsp+58h+dwOptions], 1; dwOptions
0x180002d14  call    cs:__imp_RegCreateKeyExW
0x180002d1a  test    eax, eax
0x180002d1c  jnz     short loc_180002D4D
0x180002d1e  mov     rcx, [rsp+58h+hKey]; hKey
0x180002d23  test    rcx, rcx
0x180002d26  jz      short loc_180002D31
0x180002d28  cmp     [rsp+58h+dwDisposition], 1
0x180002d2d  jnz     short loc_180002D31
0x180002d2f  mov     bl, 1
0x180002d31  mov     [rdi+8], bl
0x180002d34  test    rcx, rcx
0x180002d37  jz      short loc_180002D3F
0x180002d39  call    cs:__imp_RegCloseKey
0x180002d3f  movzx   eax, bl
0x180002d42  mov     rbx, [rsp+58h+arg_10]
0x180002d47  add     rsp, 50h
0x180002d4b  pop     rdi
0x180002d4c  retn
0x180002d4d  mov     rcx, rbx
0x180002d50  mov     [rsp+58h+hKey], rbx
0x180002d55  jmp     short loc_180002D31
```

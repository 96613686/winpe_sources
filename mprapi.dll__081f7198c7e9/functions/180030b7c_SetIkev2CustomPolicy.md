# SetIkev2CustomPolicy

- ea: `0x180030b7c`
- end: `0x180030c28`
- name: `SetIkev2CustomPolicy`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180024c10`
- `0x180030648`

## callees

- `0x180030534`
- `0x180030b7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030c15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030c15`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030bb8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030bb8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030bf0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030bf0`

## pseudocode

```c
__int64 __fastcall SetIkev2CustomPolicy(HKEY a1, BYTE *a2)
{
  unsigned int v3; // ebx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  dwDisposition = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v3 = RegCreateKeyExW(a1, L"IKEv2CustomPolicy", 0, 0, 0, 0x3001Fu, 0, &hKey, &dwDisposition);
      if ( !v3 )
        v3 = SetCustomPolicyRegParams(hKey, a2);
    }
    else
    {
      v3 = 0;
      RegDeleteKeyExW(a1, L"IKEv2CustomPolicy", 0, 0);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x180030b7c  mov     [rsp+arg_8], rbx
0x180030b81  push    rdi
0x180030b82  sub     rsp, 50h
0x180030b86  mov     [rsp+58h+hKey], 0
0x180030b8f  mov     rdi, rdx
0x180030b92  mov     [rsp+58h+dwDisposition], 0
0x180030b9a  test    rcx, rcx
0x180030b9d  jnz     short loc_180030BA4
0x180030b9f  lea     ebx, [rcx+57h]
0x180030ba2  jmp     short loc_180030C1B
0x180030ba4  xor     r8d, r8d; Reserved
0x180030ba7  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x180030bae  test    rdi, rdi
0x180030bb1  jnz     short loc_180030BC0
0x180030bb3  xor     ebx, ebx
0x180030bb5  xor     r9d, r9d; Reserved
0x180030bb8  call    cs:__imp_RegDeleteKeyExW
0x180030bbe  jmp     short loc_180030C0B
0x180030bc0  lea     rax, [rsp+58h+dwDisposition]
0x180030bc5  xor     r9d, r9d; lpClass
0x180030bc8  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180030bcd  lea     rax, [rsp+58h+hKey]
0x180030bd2  mov     [rsp+58h+phkResult], rax; phkResult
0x180030bd7  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180030be0  mov     [rsp+58h+samDesired], 3001Fh; samDesired
0x180030be8  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180030bf0  call    cs:__imp_RegCreateKeyExW
0x180030bf6  mov     ebx, eax
0x180030bf8  test    eax, eax
0x180030bfa  jnz     short loc_180030C0B
0x180030bfc  mov     rcx, [rsp+58h+hKey]; hKey
0x180030c01  mov     rdx, rdi; lpData
0x180030c04  call    SetCustomPolicyRegParams
0x180030c09  mov     ebx, eax
0x180030c0b  mov     rcx, [rsp+58h+hKey]; hKey
0x180030c10  test    rcx, rcx
0x180030c13  jz      short loc_180030C1B
0x180030c15  call    cs:__imp_RegCloseKey
0x180030c1b  mov     eax, ebx
0x180030c1d  mov     rbx, [rsp+58h+arg_8]
0x180030c22  add     rsp, 50h
0x180030c26  pop     rdi
0x180030c27  retn
```

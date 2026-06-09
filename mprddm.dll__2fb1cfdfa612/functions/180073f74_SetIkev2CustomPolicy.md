# SetIkev2CustomPolicy

- ea: `0x180073f74`
- end: `0x180074020`
- name: `SetIkev2CustomPolicy`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180073a40`

## callees

- `0x18007392c`
- `0x180073f74`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18007400d`
- `ADVAPI32!RegCloseKey` at `0x18007400d`
- `ADVAPI32!RegCreateKeyExW` at `0x180073fe8`
- `ADVAPI32!RegCreateKeyExW` at `0x180073fe8`
- `ADVAPI32!RegDeleteKeyExW` at `0x180073fb0`
- `ADVAPI32!RegDeleteKeyExW` at `0x180073fb0`

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
0x180073f74  mov     [rsp+arg_8], rbx
0x180073f79  push    rdi
0x180073f7a  sub     rsp, 50h
0x180073f7e  mov     [rsp+58h+hKey], 0
0x180073f87  mov     rdi, rdx
0x180073f8a  mov     [rsp+58h+dwDisposition], 0
0x180073f92  test    rcx, rcx
0x180073f95  jnz     short loc_180073F9C
0x180073f97  lea     ebx, [rcx+57h]
0x180073f9a  jmp     short loc_180074013
0x180073f9c  xor     r8d, r8d; Reserved
0x180073f9f  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x180073fa6  test    rdi, rdi
0x180073fa9  jnz     short loc_180073FB8
0x180073fab  xor     ebx, ebx
0x180073fad  xor     r9d, r9d; Reserved
0x180073fb0  call    cs:__imp_RegDeleteKeyExW
0x180073fb6  jmp     short loc_180074003
0x180073fb8  lea     rax, [rsp+58h+dwDisposition]
0x180073fbd  xor     r9d, r9d; lpClass
0x180073fc0  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180073fc5  lea     rax, [rsp+58h+hKey]
0x180073fca  mov     [rsp+58h+phkResult], rax; phkResult
0x180073fcf  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180073fd8  mov     [rsp+58h+samDesired], 3001Fh; samDesired
0x180073fe0  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180073fe8  call    cs:__imp_RegCreateKeyExW
0x180073fee  mov     ebx, eax
0x180073ff0  test    eax, eax
0x180073ff2  jnz     short loc_180074003
0x180073ff4  mov     rcx, [rsp+58h+hKey]; hKey
0x180073ff9  mov     rdx, rdi; lpData
0x180073ffc  call    SetCustomPolicyRegParams
0x180074001  mov     ebx, eax
0x180074003  mov     rcx, [rsp+58h+hKey]; hKey
0x180074008  test    rcx, rcx
0x18007400b  jz      short loc_180074013
0x18007400d  call    cs:__imp_RegCloseKey
0x180074013  mov     eax, ebx
0x180074015  mov     rbx, [rsp+58h+arg_8]
0x18007401a  add     rsp, 50h
0x18007401e  pop     rdi
0x18007401f  retn
```

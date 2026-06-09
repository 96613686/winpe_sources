# SetIkev2CustomPolicy

- ea: `0x180077bb8`
- end: `0x180077c67`
- name: `SetIkev2CustomPolicy`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800775f0`

## callees

- `0x1800774b8`
- `0x180077bb8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180077c4d`
- `ADVAPI32!RegCloseKey` at `0x180077c4d`
- `ADVAPI32!RegCreateKeyExW` at `0x180077c22`
- `ADVAPI32!RegCreateKeyExW` at `0x180077c22`
- `ADVAPI32!RegDeleteKeyExW` at `0x180077bec`
- `ADVAPI32!RegDeleteKeyExW` at `0x180077bec`

## pseudocode

```c
__int64 __fastcall SetIkev2CustomPolicy(HKEY a1, BYTE *a2)
{
  unsigned int v2; // ebx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  hKey = 0;
  dwDisposition = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v2 = RegCreateKeyExW(a1, L"IKEv2CustomPolicy", 0, 0, 0, 0x3001Fu, 0, &hKey, &dwDisposition);
      if ( !v2 )
        v2 = SetCustomPolicyRegParams(hKey, a2);
    }
    else
    {
      RegDeleteKeyExW(a1, L"IKEv2CustomPolicy", 0, 0);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return 87;
  }
  return v2;
}

```

## disassembly

```asm
0x180077bb8  mov     [rsp+arg_8], rbx
0x180077bbd  push    rdi
0x180077bbe  sub     rsp, 50h
0x180077bc2  xor     ebx, ebx
0x180077bc4  mov     rdi, rdx
0x180077bc7  and     [rsp+58h+hKey], rbx
0x180077bcc  and     [rsp+58h+dwDisposition], ebx
0x180077bd0  test    rcx, rcx
0x180077bd3  jnz     short loc_180077BDA
0x180077bd5  lea     ebx, [rcx+57h]
0x180077bd8  jmp     short loc_180077C59
0x180077bda  xor     r8d, r8d; Reserved
0x180077bdd  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x180077be4  test    rdi, rdi
0x180077be7  jnz     short loc_180077BFA
0x180077be9  xor     r9d, r9d; Reserved
0x180077bec  call    cs:__imp_RegDeleteKeyExW
0x180077bf3  nop     dword ptr [rax+rax+00h]
0x180077bf8  jmp     short loc_180077C43
0x180077bfa  lea     rax, [rsp+58h+dwDisposition]
0x180077bff  xor     r9d, r9d; lpClass
0x180077c02  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180077c07  lea     rax, [rsp+58h+hKey]
0x180077c0c  mov     [rsp+58h+phkResult], rax; phkResult
0x180077c11  and     [rsp+58h+var_28], rbx
0x180077c16  mov     [rsp+58h+samDesired], 3001Fh; samDesired
0x180077c1e  and     [rsp+58h+var_38], ebx
0x180077c22  call    cs:__imp_RegCreateKeyExW
0x180077c29  nop     dword ptr [rax+rax+00h]
0x180077c2e  mov     ebx, eax
0x180077c30  test    eax, eax
0x180077c32  jnz     short loc_180077C43
0x180077c34  mov     rcx, [rsp+58h+hKey]; hKey
0x180077c39  mov     rdx, rdi; lpData
0x180077c3c  call    SetCustomPolicyRegParams
0x180077c41  mov     ebx, eax
0x180077c43  mov     rcx, [rsp+58h+hKey]; hKey
0x180077c48  test    rcx, rcx
0x180077c4b  jz      short loc_180077C59
0x180077c4d  call    cs:__imp_RegCloseKey
0x180077c54  nop     dword ptr [rax+rax+00h]
0x180077c59  mov     eax, ebx
0x180077c5b  mov     rbx, [rsp+58h+arg_8]
0x180077c60  add     rsp, 50h
0x180077c64  pop     rdi
0x180077c65  retn
```

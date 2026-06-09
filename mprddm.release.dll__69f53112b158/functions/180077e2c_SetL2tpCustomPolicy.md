# SetL2tpCustomPolicy

- ea: `0x180077e2c`
- end: `0x180077edb`
- name: `SetL2tpCustomPolicy`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180077c70`

## callees

- `0x1800774b8`
- `0x180077e2c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180077ec1`
- `ADVAPI32!RegCloseKey` at `0x180077ec1`
- `ADVAPI32!RegCreateKeyExW` at `0x180077e96`
- `ADVAPI32!RegCreateKeyExW` at `0x180077e96`
- `ADVAPI32!RegDeleteKeyExW` at `0x180077e60`
- `ADVAPI32!RegDeleteKeyExW` at `0x180077e60`

## pseudocode

```c
__int64 __fastcall SetL2tpCustomPolicy(HKEY a1, BYTE *a2)
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
      v2 = RegCreateKeyExW(a1, L"L2TPCustomPolicy", 0, 0, 0, 0x3001Fu, 0, &hKey, &dwDisposition);
      if ( !v2 )
        v2 = SetCustomPolicyRegParams(hKey, a2);
    }
    else
    {
      RegDeleteKeyExW(a1, L"L2TPCustomPolicy", 0, 0);
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
0x180077e2c  mov     [rsp+arg_8], rbx
0x180077e31  push    rdi
0x180077e32  sub     rsp, 50h
0x180077e36  xor     ebx, ebx
0x180077e38  mov     rdi, rdx
0x180077e3b  and     [rsp+58h+hKey], rbx
0x180077e40  and     [rsp+58h+dwDisposition], ebx
0x180077e44  test    rcx, rcx
0x180077e47  jnz     short loc_180077E4E
0x180077e49  lea     ebx, [rcx+57h]
0x180077e4c  jmp     short loc_180077ECD
0x180077e4e  xor     r8d, r8d; Reserved
0x180077e51  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x180077e58  test    rdi, rdi
0x180077e5b  jnz     short loc_180077E6E
0x180077e5d  xor     r9d, r9d; Reserved
0x180077e60  call    cs:__imp_RegDeleteKeyExW
0x180077e67  nop     dword ptr [rax+rax+00h]
0x180077e6c  jmp     short loc_180077EB7
0x180077e6e  lea     rax, [rsp+58h+dwDisposition]
0x180077e73  xor     r9d, r9d; lpClass
0x180077e76  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180077e7b  lea     rax, [rsp+58h+hKey]
0x180077e80  mov     [rsp+58h+phkResult], rax; phkResult
0x180077e85  and     [rsp+58h+var_28], rbx
0x180077e8a  mov     [rsp+58h+samDesired], 3001Fh; samDesired
0x180077e92  and     [rsp+58h+var_38], ebx
0x180077e96  call    cs:__imp_RegCreateKeyExW
0x180077e9d  nop     dword ptr [rax+rax+00h]
0x180077ea2  mov     ebx, eax
0x180077ea4  test    eax, eax
0x180077ea6  jnz     short loc_180077EB7
0x180077ea8  mov     rcx, [rsp+58h+hKey]; hKey
0x180077ead  mov     rdx, rdi; lpData
0x180077eb0  call    SetCustomPolicyRegParams
0x180077eb5  mov     ebx, eax
0x180077eb7  mov     rcx, [rsp+58h+hKey]; hKey
0x180077ebc  test    rcx, rcx
0x180077ebf  jz      short loc_180077ECD
0x180077ec1  call    cs:__imp_RegCloseKey
0x180077ec8  nop     dword ptr [rax+rax+00h]
0x180077ecd  mov     eax, ebx
0x180077ecf  mov     rbx, [rsp+58h+arg_8]
0x180077ed4  add     rsp, 50h
0x180077ed8  pop     rdi
0x180077ed9  retn
```

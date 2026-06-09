# GetRegValueDword(char const *,char const *,ulong *)

- ea: `0x180011cc0`
- end: `0x180011d66`
- name: `?GetRegValueDword@@YAHPEBD0PEAK@Z`
- size: `166`
- prototype: `int(const char *, const char *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f010`
- `0x18000ff10`

## callees

- `0x180011cc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180011d09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180011d09`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011d3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011d3a`

## pseudocode

```c
_BOOL8 __fastcall GetRegValueDword(const char *a1, const char *a2, BYTE *a3)
{
  BOOL v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+8h] BYREF
  int v9; // [rsp+64h] [rbp+Ch]
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  v9 = HIDWORD(a1);
  v3 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\DirectMusic", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExA(hKey, a2, 0, &Type, a3, &cbData) )
      v3 = Type == 4;
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x180011cc0  mov     [rsp+arg_8], rbx
0x180011cc5  mov     qword ptr [rsp+cbData], rcx
0x180011cca  push    rbp
0x180011ccb  push    rsi
0x180011ccc  push    rdi
0x180011ccd  sub     rsp, 40h
0x180011cd1  xor     ebx, ebx
0x180011cd3  lea     rax, [rsp+58h+hKey]
0x180011cd8  mov     rdi, r8
0x180011cdb  mov     [rsp+58h+hKey], rbx
0x180011ce0  mov     rsi, rdx
0x180011ce3  mov     [rsp+58h+Type], ebx
0x180011ce7  mov     ebp, 1
0x180011cec  mov     [rsp+58h+cbData], ebx
0x180011cf0  mov     r9d, ebp; samDesired
0x180011cf3  mov     [rsp+58h+phkResult], rax; phkResult
0x180011cf8  xor     r8d, r8d; ulOptions
0x180011cfb  lea     rdx, SubKey; "Software\\Microsoft\\DirectMusic"
0x180011d02  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011d09  call    cs:__imp_RegOpenKeyExA
0x180011d0f  test    eax, eax
0x180011d11  jnz     short loc_180011D57
0x180011d13  mov     rcx, [rsp+58h+hKey]; hKey
0x180011d18  lea     rax, [rsp+58h+cbData]
0x180011d1d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180011d22  lea     r9, [rsp+58h+Type]; lpType
0x180011d27  xor     r8d, r8d; lpReserved
0x180011d2a  mov     [rsp+58h+phkResult], rdi; lpData
0x180011d2f  mov     rdx, rsi; lpValueName
0x180011d32  mov     [rsp+58h+cbData], 4
0x180011d3a  call    cs:__imp_RegQueryValueExA
0x180011d40  test    eax, eax
0x180011d42  jnz     short loc_180011D4C
0x180011d44  cmp     [rsp+58h+Type], 4
0x180011d49  cmovz   ebx, ebp
0x180011d4c  mov     rcx, [rsp+58h+hKey]; hKey
0x180011d51  call    cs:__imp_RegCloseKey
0x180011d57  mov     eax, ebx
0x180011d59  mov     rbx, [rsp+58h+arg_8]
0x180011d5e  add     rsp, 40h
0x180011d62  pop     rdi
0x180011d63  pop     rsi
0x180011d64  pop     rbp
0x180011d65  retn
```

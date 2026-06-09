# configWriteConfiguration

- ea: `0x180006328`
- end: `0x1800063a2`
- name: `configWriteConfiguration`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005920`
- `0x180005ce4`

## callees

- `0x180006328`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006363`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006396`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006363`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006396`

## pseudocode

```c
LSTATUS __fastcall configWriteConfiguration(__int64 a1)
{
  HKEY v2; // rcx
  HKEY v3; // rcx
  LSTATUS result; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(HKEY *)(a1 + 48);
  if ( v2 )
  {
    Data = *(_DWORD *)(a1 + 56);
    RegSetValueExW(v2, L"MaxRTEncodeSetting", 0, 4u, (const BYTE *)&Data, 4u);
    v3 = *(HKEY *)(a1 + 48);
    Data = *(_DWORD *)(a1 + 60);
    return RegSetValueExW(v3, L"MaxRTDecodeSetting", 0, 4u, (const BYTE *)&Data, 4u);
  }
  return result;
}

```

## disassembly

```asm
0x180006328  push    rbx
0x18000632a  sub     rsp, 30h
0x18000632e  mov     rbx, rcx
0x180006331  mov     rcx, [rcx+30h]; hKey
0x180006335  test    rcx, rcx
0x180006338  jz      short loc_18000639C
0x18000633a  mov     eax, [rbx+38h]
0x18000633d  lea     rdx, gszMaxRTEncodeSetting; "MaxRTEncodeSetting"
0x180006344  mov     [rsp+38h+Data], eax
0x180006348  mov     r9d, 4; dwType
0x18000634e  lea     rax, [rsp+38h+Data]
0x180006353  mov     [rsp+38h+cbData], 4; cbData
0x18000635b  xor     r8d, r8d; Reserved
0x18000635e  mov     [rsp+38h+lpData], rax; lpData
0x180006363  call    cs:__imp_RegSetValueExW
0x180006369  mov     eax, [rbx+3Ch]
0x18000636c  lea     rdx, gszMaxRTDecodeSetting; "MaxRTDecodeSetting"
0x180006373  mov     rcx, [rbx+30h]; hKey
0x180006377  mov     r9d, 4; dwType
0x18000637d  mov     [rsp+38h+Data], eax
0x180006381  xor     r8d, r8d; Reserved
0x180006384  lea     rax, [rsp+38h+Data]
0x180006389  mov     [rsp+38h+cbData], 4; cbData
0x180006391  mov     [rsp+38h+lpData], rax; lpData
0x180006396  call    cs:__imp_RegSetValueExW
0x18000639c  add     rsp, 30h
0x1800063a0  pop     rbx
0x1800063a1  retn
```

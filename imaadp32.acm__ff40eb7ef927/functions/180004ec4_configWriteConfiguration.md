# configWriteConfiguration

- ea: `0x180004ec4`
- end: `0x180004f3e`
- name: `configWriteConfiguration`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004300`
- `0x180004700`

## callees

- `0x180004ec4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004eff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004f32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004eff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004f32`

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
0x180004ec4  push    rbx
0x180004ec6  sub     rsp, 30h
0x180004eca  mov     rbx, rcx
0x180004ecd  mov     rcx, [rcx+30h]; hKey
0x180004ed1  test    rcx, rcx
0x180004ed4  jz      short loc_180004F38
0x180004ed6  mov     eax, [rbx+38h]
0x180004ed9  lea     rdx, gszMaxRTEncodeSetting; "MaxRTEncodeSetting"
0x180004ee0  mov     [rsp+38h+Data], eax
0x180004ee4  mov     r9d, 4; dwType
0x180004eea  lea     rax, [rsp+38h+Data]
0x180004eef  mov     [rsp+38h+cbData], 4; cbData
0x180004ef7  xor     r8d, r8d; Reserved
0x180004efa  mov     [rsp+38h+lpData], rax; lpData
0x180004eff  call    cs:__imp_RegSetValueExW
0x180004f05  mov     eax, [rbx+3Ch]
0x180004f08  lea     rdx, gszMaxRTDecodeSetting; "MaxRTDecodeSetting"
0x180004f0f  mov     rcx, [rbx+30h]; hKey
0x180004f13  mov     r9d, 4; dwType
0x180004f19  mov     [rsp+38h+Data], eax
0x180004f1d  xor     r8d, r8d; Reserved
0x180004f20  lea     rax, [rsp+38h+Data]
0x180004f25  mov     [rsp+38h+cbData], 4; cbData
0x180004f2d  mov     [rsp+38h+lpData], rax; lpData
0x180004f32  call    cs:__imp_RegSetValueExW
0x180004f38  add     rsp, 30h
0x180004f3c  pop     rbx
0x180004f3d  retn
```

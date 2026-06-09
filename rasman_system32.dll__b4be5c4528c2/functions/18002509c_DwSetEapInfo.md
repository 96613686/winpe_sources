# DwSetEapInfo

- ea: `0x18002509c`
- end: `0x1800250cc`
- name: `DwSetEapInfo`
- size: `48`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180024ea0`
- `0x180024f6c`
- `0x1800250d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800250ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800250ba`

## pseudocode

```c
LSTATUS __fastcall DwSetEapInfo(HKEY a1, const BYTE *lpData, DWORD cbData)
{
  return RegSetValueExW(a1, L"EapInfo", 0, 3u, lpData, cbData);
}

```

## disassembly

```asm
0x18002509c  sub     rsp, 38h
0x1800250a0  mov     [rsp+38h+cbData], r8d; cbData
0x1800250a5  mov     r9d, 3; dwType
0x1800250ab  mov     [rsp+38h+lpData], rdx; lpData
0x1800250b0  xor     r8d, r8d; Reserved
0x1800250b3  lea     rdx, aEapinfo; "EapInfo"
0x1800250ba  call    cs:__imp_RegSetValueExW
0x1800250c1  nop     dword ptr [rax+rax+00h]
0x1800250c6  add     rsp, 38h
0x1800250ca  retn
```

# lrRasEnableDevice

- ea: `0x180020c5c`
- end: `0x180020c8f`
- name: `lrRasEnableDevice`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800166e0`
- `0x180016d40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020c84`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020c84`

## pseudocode

```c
LSTATUS __fastcall lrRasEnableDevice(HKEY a1, const WCHAR *a2, int a3)
{
  BOOL Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3 != 0;
  return RegSetValueExW(a1, a2, 0, 4u, (const BYTE *)&Data, 4u);
}

```

## disassembly

```asm
0x180020c5c  sub     rsp, 38h
0x180020c60  xor     eax, eax
0x180020c62  mov     r9d, 4; dwType
0x180020c68  test    r8d, r8d
0x180020c6b  mov     [rsp+38h+cbData], r9d; cbData
0x180020c70  setnz   al
0x180020c73  xor     r8d, r8d; Reserved
0x180020c76  mov     [rsp+38h+Data], eax
0x180020c7a  lea     rax, [rsp+38h+Data]
0x180020c7f  mov     [rsp+38h+lpData], rax; lpData
0x180020c84  call    cs:__imp_RegSetValueExW
0x180020c8a  add     rsp, 38h
0x180020c8e  retn
```

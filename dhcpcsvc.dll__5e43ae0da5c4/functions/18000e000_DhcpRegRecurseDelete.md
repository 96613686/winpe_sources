# DhcpRegRecurseDelete

- ea: `0x18000e000`
- end: `0x18000e043`
- name: `DhcpRegRecurseDelete`
- size: `67`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006300`
- `0x18000e04c`

## callees

- `0x18000e04c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000e028`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000e028`

## pseudocode

```c
LSTATUS __fastcall DhcpRegRecurseDelete(HKEY hKey, LPCWSTR lpSubKey)
{
  LSTATUS v4; // esi
  LSTATUS result; // eax

  v4 = DhcpRegRecurseDeleteSub(hKey, lpSubKey);
  result = RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
  if ( v4 )
    return v4;
  return result;
}

```

## disassembly

```asm
0x18000e000  mov     [rsp+arg_0], rbx
0x18000e005  mov     [rsp+arg_8], rsi
0x18000e00a  push    rdi
0x18000e00b  sub     rsp, 20h
0x18000e00f  mov     rbx, rdx
0x18000e012  mov     rdi, rcx
0x18000e015  call    DhcpRegRecurseDeleteSub
0x18000e01a  xor     r9d, r9d; Reserved
0x18000e01d  xor     r8d, r8d; samDesired
0x18000e020  mov     rdx, rbx; lpSubKey
0x18000e023  mov     rcx, rdi; hKey
0x18000e026  mov     esi, eax
0x18000e028  call    cs:__imp_RegDeleteKeyExW
0x18000e02e  mov     rbx, [rsp+28h+arg_0]
0x18000e033  test    esi, esi
0x18000e035  cmovnz  eax, esi
0x18000e038  mov     rsi, [rsp+28h+arg_8]
0x18000e03d  add     rsp, 20h
0x18000e041  pop     rdi
0x18000e042  retn
```

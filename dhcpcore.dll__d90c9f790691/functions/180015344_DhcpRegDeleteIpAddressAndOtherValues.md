# DhcpRegDeleteIpAddressAndOtherValues

- ea: `0x180015344`
- end: `0x180015380`
- name: `DhcpRegDeleteIpAddressAndOtherValues`
- size: `60`
- prototype: `LSTATUS __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800210a4`
- `0x18003f140`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015358`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001536a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015358`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001536a`

## pseudocode

```c
LSTATUS __fastcall DhcpRegDeleteIpAddressAndOtherValues(HKEY hKey)
{
  LSTATUS v2; // edi
  LSTATUS result; // eax

  v2 = RegDeleteValueW(hKey, L"DhcpIPAddress");
  result = RegDeleteValueW(hKey, L"DhcpSubnetMask");
  if ( v2 )
    return v2;
  return result;
}

```

## disassembly

```asm
0x180015344  mov     [rsp+arg_0], rbx
0x180015349  push    rdi
0x18001534a  sub     rsp, 20h
0x18001534e  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x180015355  mov     rbx, rcx
0x180015358  call    cs:__imp_RegDeleteValueW
0x18001535e  lea     rdx, aDhcpsubnetmask_0; "DhcpSubnetMask"
0x180015365  mov     rcx, rbx; hKey
0x180015368  mov     edi, eax
0x18001536a  call    cs:__imp_RegDeleteValueW
0x180015370  mov     rbx, [rsp+28h+arg_0]
0x180015375  test    edi, edi
0x180015377  cmovnz  eax, edi
0x18001537a  add     rsp, 20h
0x18001537e  pop     rdi
0x18001537f  retn
```

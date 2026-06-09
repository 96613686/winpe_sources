# Dhcpv6RegDeleteInterfaceOptionsCache

- ea: `0x180008274`
- end: `0x1800082b7`
- name: `Dhcpv6RegDeleteInterfaceOptionsCache`
- size: `67`
- prototype: `unsigned int __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007efc`

## callees

- `0x180008274`
- `0x1800338c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000827f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000827f`

## pseudocode

```c
unsigned int __fastcall Dhcpv6RegDeleteInterfaceOptionsCache(HKEY a1)
{
  unsigned int result; // eax

  result = RegDeleteValueW(a1, L"Dhcpv6InterfaceOptions");
  if ( result )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      return WPP_SF_D(1025, 44, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids, result);
  }
  return result;
}

```

## disassembly

```asm
0x180008274  sub     rsp, 28h
0x180008278  lea     rdx, aDhcpv6interfac; "Dhcpv6InterfaceOptions"
0x18000827f  call    cs:__imp_RegDeleteValueW
0x180008286  nop     dword ptr [rax+rax+00h]
0x18000828b  test    eax, eax
0x18000828d  jz      short loc_1800082B1
0x18000828f  test    byte ptr cs:xmmword_1800423E0, 2
0x180008296  jz      short loc_1800082B1
0x180008298  mov     edx, 2Ch ; ','
0x18000829d  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x1800082a4  mov     ecx, 401h
0x1800082a9  mov     r9d, eax
0x1800082ac  call    WPP_SF_D
0x1800082b1  add     rsp, 28h
0x1800082b5  retn
```

# GetStringFromSockAddr

- ea: `0x140003d58`
- end: `0x140003d93`
- name: `GetStringFromSockAddr`
- size: `59`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f224`
- `0x14000f588`
- `0x14000f8d8`
- `0x14000fbac`
- `0x1400102fc`
- `0x140010c14`
- `0x1400114c8`
- `0x140011d04`
- `0x1400122b0`
- `0x140012798`
- `0x140012ac0`
- `0x1400137ac`
- `0x140013954`
- `0x140015338`
- `0x1400154b8`
- `0x1400162f0`
- `0x140016db0`

## callees

- `0x140003d58`

## import_xrefs

- `ntoskrnl!RtlIpv4AddressToStringA` at `0x140003d6b`
- `ntoskrnl!RtlIpv4AddressToStringA` at `0x140003d6b`
- `ntoskrnl!RtlIpv6AddressToStringA` at `0x140003d7d`
- `ntoskrnl!RtlIpv6AddressToStringA` at `0x140003d7d`

## pseudocode

```c
CHAR *__fastcall GetStringFromSockAddr(__int64 a1, CHAR *a2)
{
  if ( *(_WORD *)a1 == 2 )
    RtlIpv4AddressToStringA((const struct in_addr *)(a1 + 4), a2);
  else
    RtlIpv6AddressToStringA((const struct in6_addr *)(a1 + 8), a2);
  return a2;
}

```

## disassembly

```asm
0x140003d58  push    rbx
0x140003d5a  sub     rsp, 20h
0x140003d5e  cmp     word ptr [rcx], 2
0x140003d62  mov     rbx, rdx
0x140003d65  jnz     short loc_140003D79
0x140003d67  add     rcx, 4; Addr
0x140003d6b  call    cs:__imp_RtlIpv4AddressToStringA
0x140003d72  nop     dword ptr [rax+rax+00h]
0x140003d77  jmp     short loc_140003D89
0x140003d79  add     rcx, 8; Addr
0x140003d7d  call    cs:__imp_RtlIpv6AddressToStringA
0x140003d84  nop     dword ptr [rax+rax+00h]
0x140003d89  mov     rax, rbx
0x140003d8c  add     rsp, 20h
0x140003d90  pop     rbx
0x140003d91  retn
```

# GetStringFromSockAddr

- ea: `0x140001e1c`
- end: `0x140001e57`
- name: `GetStringFromSockAddr`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140011288`
- `0x1400154b8`
- `0x1400189fc`
- `0x14001b1e0`
- `0x14001c1b0`

## callees

- `0x140001e1c`

## import_xrefs

- `ntoskrnl!RtlIpv4AddressToStringA` at `0x140001e2f`
- `ntoskrnl!RtlIpv4AddressToStringA` at `0x140001e2f`
- `ntoskrnl!RtlIpv6AddressToStringA` at `0x140001e41`
- `ntoskrnl!RtlIpv6AddressToStringA` at `0x140001e41`

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
0x140001e1c  push    rbx
0x140001e1e  sub     rsp, 20h
0x140001e22  cmp     word ptr [rcx], 2
0x140001e26  mov     rbx, rdx
0x140001e29  jnz     short loc_140001E3D
0x140001e2b  add     rcx, 4; Addr
0x140001e2f  call    cs:__imp_RtlIpv4AddressToStringA
0x140001e36  nop     dword ptr [rax+rax+00h]
0x140001e3b  jmp     short loc_140001E4D
0x140001e3d  add     rcx, 8; Addr
0x140001e41  call    cs:__imp_RtlIpv6AddressToStringA
0x140001e48  nop     dword ptr [rax+rax+00h]
0x140001e4d  mov     rax, rbx
0x140001e50  add     rsp, 20h
0x140001e54  pop     rbx
0x140001e55  retn
```

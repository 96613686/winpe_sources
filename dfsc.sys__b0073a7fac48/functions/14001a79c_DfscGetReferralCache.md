# DfscGetReferralCache

- ea: `0x14001a79c`
- end: `0x14001a7b2`
- name: `DfscGetReferralCache`
- size: `22`
- prototype: `PSECURITY_DESCRIPTOR __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140014910`
- `0x140014d30`
- `0x14001520c`
- `0x1400158f0`
- `0x1400169f8`
- `0x14001a718`

## callees

- `0x14001a79c`

## pseudocode

```c
PSECURITY_DESCRIPTOR __fastcall DfscGetReferralCache(__int64 a1)
{
  if ( a1 )
    return *(PSECURITY_DESCRIPTOR *)(a1 + 136);
  else
    return WPP_MAIN_CB.SecurityDescriptor;
}

```

## disassembly

```asm
0x14001a79c  test    rcx, rcx
0x14001a79f  jnz     short loc_14001A7AA
0x14001a7a1  mov     rax, cs:WPP_MAIN_CB.SecurityDescriptor
0x14001a7a8  retn
0x14001a7aa  mov     rax, [rcx+88h]
0x14001a7b1  retn
```

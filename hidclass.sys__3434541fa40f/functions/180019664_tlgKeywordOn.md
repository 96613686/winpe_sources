# _tlgKeywordOn

- ea: `0x180019664`
- end: `0x18001968b`
- name: `_tlgKeywordOn`
- size: `39`
- prototype: ``
- caller_count: `44`
- callee_count: `1`
- tags: ``

## callers

- `0x180003090`
- `0x180008650`
- `0x180009664`
- `0x18000c948`
- `0x1800115f8`
- `0x18001acb8`
- `0x18001d2f8`
- `0x18001d374`
- `0x18001d43c`
- `0x18001d4d4`
- `0x18001d550`
- `0x18001d630`
- `0x18001e538`
- `0x18001eb28`
- `0x18001ec30`
- `0x18001ed14`
- `0x18001ee14`
- `0x18001fabc`
- `0x18001fba0`
- `0x18001ffbc`
- `0x180021940`
- `0x1800219bc`
- `0x180021ac0`
- `0x180021bb0`
- `0x180021ca0`
- `0x180021d38`
- `0x180021e1c`
- `0x180021f1c`
- `0x18002204c`
- `0x180023e50`
- `0x180023f18`
- `0x180023fe0`
- `0x180024124`
- `0x18002423c`
- `0x18002432c`
- `0x180024408`
- `0x1800245b4`
- `0x18002497c`
- `0x180024ef0`
- `0x1800251f0`
- `0x180025330`
- `0x180025940`
- `0x1800268d8`
- `0x18003cb80`

## callees

- `0x180019664`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  bool result; // al

  result = 1;
  if ( a2 )
  {
    v3 = *(_QWORD *)(a1 + 24);
    if ( (*(_QWORD *)(a1 + 16) & a2) == 0 || (a2 & v3) != v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180019664  mov     rax, rcx
0x180019667  test    rdx, rdx
0x18001966a  jz      short loc_180019684
0x18001966c  mov     rcx, [rcx+18h]
0x180019670  mov     rax, [rax+10h]
0x180019674  test    rdx, rax
0x180019677  jz      short loc_180019688
0x180019679  mov     rax, rcx
0x18001967c  and     rax, rdx
0x18001967f  cmp     rax, rcx
0x180019682  jnz     short loc_180019688
0x180019684  mov     al, 1
0x180019686  retn
0x180019688  xor     al, al
0x18001968a  retn
```

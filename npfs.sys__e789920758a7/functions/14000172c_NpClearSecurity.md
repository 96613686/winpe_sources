# NpClearSecurity

- ea: `0x14000172c`
- end: `0x140001745`
- name: `NpClearSecurity`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000efb0`
- `0x14000fdc4`
- `0x14001070c`

## callees

- `0x14000172c`

## pseudocode

```c
__int64 __fastcall NpClearSecurity(__int64 a1)
{
  __int64 result; // rax

  result = *(_QWORD *)(a1 + 264);
  if ( result != -1 )
    *(_QWORD *)(a1 + 264) = 0;
  return result;
}

```

## disassembly

```asm
0x14000172c  mov     rax, [rcx+108h]
0x140001733  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140001737  jz      short locret_140001744
0x140001739  mov     qword ptr [rcx+108h], 0
0x140001744  retn
```

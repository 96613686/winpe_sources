# DisconnectLinkInfo

- ea: `0x180005550`
- end: `0x18000555e`
- name: `DisconnectLinkInfo`
- size: `14`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004760`

## pseudocode

```c
_BOOL8 __fastcall DisconnectLinkInfo(__int64 a1)
{
  return DisconnectFromCNR((const struct _cnrlink *)(a1 + *(unsigned int *)(a1 + 20)));
}

```

## disassembly

```asm
0x180005550  mov     rdx, rcx
0x180005553  mov     ecx, [rcx+14h]
0x180005556  add     rcx, rdx; struct _cnrlink *
0x180005559  jmp     ?DisconnectFromCNR@@YAHPEBU_cnrlink@@@Z; DisconnectFromCNR(_cnrlink const *)
```

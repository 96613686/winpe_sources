# PartitionOffset(_PARTITION_EXTENSION *,uchar)

- ea: `0x140005a84`
- end: `0x140005aa8`
- name: `?PartitionOffset@@YA_KPEAU_PARTITION_EXTENSION@@E@Z`
- size: `36`
- prototype: `unsigned __int64 __fastcall(struct _PARTITION_EXTENSION *, unsigned __int8)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000c47c`
- `0x14000c730`
- `0x14000e018`
- `0x140023ecc`
- `0x14002532c`

## callees

- `0x140005a84`

## pseudocode

```c
unsigned __int64 __fastcall PartitionOffset(struct _PARTITION_EXTENSION *a1, char a2)
{
  char *v2; // rax

  v2 = (char *)a1 + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF0uLL) + 328;
  if ( *(char **)v2 == v2 )
    return 0;
  else
    return *(_QWORD *)(*(_QWORD *)v2 + 24LL);
}

```

## disassembly

```asm
0x140005a84  neg     dl
0x140005a86  sbb     rax, rax
0x140005a89  add     rcx, 148h
0x140005a90  and     rax, 0FFFFFFFFFFFFFFF0h
0x140005a94  add     rax, rcx
0x140005a97  mov     rcx, [rax]
0x140005a9a  cmp     rcx, rax
0x140005a9d  jnz     short loc_140005AA3
0x140005a9f  xor     eax, eax
0x140005aa1  retn
0x140005aa3  mov     rax, [rcx+18h]
0x140005aa7  retn
```

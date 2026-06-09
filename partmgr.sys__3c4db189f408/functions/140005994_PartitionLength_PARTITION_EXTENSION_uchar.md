# PartitionLength(_PARTITION_EXTENSION *,uchar)

- ea: `0x140005994`
- end: `0x1400059bc`
- name: `?PartitionLength@@YA_KPEAU_PARTITION_EXTENSION@@E@Z`
- size: `40`
- prototype: `unsigned __int64 __fastcall(struct _PARTITION_EXTENSION *, unsigned __int8)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400084d0`
- `0x14000c47c`
- `0x14001d25c`
- `0x140022df0`
- `0x140024b3c`
- `0x140024d04`
- `0x14002532c`

## callees

- `0x140005994`

## pseudocode

```c
unsigned __int64 __fastcall PartitionLength(struct _PARTITION_EXTENSION *a1, char a2)
{
  _QWORD *v2; // rcx

  v2 = (_QWORD *)((char *)a1 + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF0uLL) + 328);
  if ( (_QWORD *)*v2 == v2 )
    return 0;
  else
    return *(_QWORD *)(v2[1] + 16LL) + *(_QWORD *)(v2[1] + 32LL);
}

```

## disassembly

```asm
0x140005994  neg     dl
0x140005996  sbb     rax, rax
0x140005999  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000599d  add     rax, 148h
0x1400059a3  add     rcx, rax
0x1400059a6  cmp     [rcx], rcx
0x1400059a9  jz      short loc_1400059B9
0x1400059ab  mov     rcx, [rcx+8]
0x1400059af  mov     rax, [rcx+20h]
0x1400059b3  add     rax, [rcx+10h]
0x1400059b7  retn
0x1400059b9  xor     eax, eax
0x1400059bb  retn
```

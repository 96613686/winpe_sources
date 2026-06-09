# PmFindPartition(_DEVICE_EXTENSION *,unsigned __int64,unsigned __int64)

- ea: `0x140020924`
- end: `0x140020964`
- name: `?PmFindPartition@@YAPEAU_PARTITION_EXTENSION@@PEAU_DEVICE_EXTENSION@@_K1@Z`
- size: `64`
- prototype: `struct _PARTITION_EXTENSION *__fastcall(struct _DEVICE_EXTENSION *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000b204`

## callees

- `0x140020924`

## pseudocode

```c
struct _PARTITION_EXTENSION *__fastcall PmFindPartition(struct _DEVICE_EXTENSION *a1, __int64 a2, __int64 a3)
{
  char v3; // r10
  unsigned __int64 v4; // r9
  _QWORD **v5; // rcx
  _QWORD *i; // rax

  v3 = 0;
  v4 = 0;
  v5 = (_QWORD **)((char *)a1 + 896);
  for ( i = *v5; i != v5; i = (_QWORD *)*i )
  {
    v4 = (unsigned __int64)(i - 18);
    if ( i[4] == a2 && *(_QWORD *)(v4 + 184) == a3 )
    {
      v3 = 1;
      return (struct _PARTITION_EXTENSION *)(v4 & -(__int64)(v3 != 0));
    }
  }
  return (struct _PARTITION_EXTENSION *)(v4 & -(__int64)(v3 != 0));
}

```

## disassembly

```asm
0x140020924  xor     r10b, r10b
0x140020927  xor     r9d, r9d
0x14002092a  add     rcx, 380h
0x140020931  mov     rax, [rcx]
0x140020934  cmp     rax, rcx
0x140020937  jz      short loc_14002095A
0x140020939  lea     r9, [rax-90h]
0x140020940  cmp     [r9+0B0h], rdx
0x140020947  jnz     short loc_140020952
0x140020949  cmp     [r9+0B8h], r8
0x140020950  jz      short loc_140020957
0x140020952  mov     rax, [rax]
0x140020955  jmp     short loc_140020934
0x140020957  mov     r10b, 1
0x14002095a  neg     r10b
0x14002095d  sbb     rax, rax
0x140020960  and     rax, r9
0x140020963  retn
```

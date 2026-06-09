# PmAssociatePartition(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)

- ea: `0x14000a21c`
- end: `0x14000a2ab`
- name: `?PmAssociatePartition@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _PARTITION_EXTENSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140005c50`

## callees

- `0x140004db8`
- `0x14000a21c`
- `0x14000cc88`

## pseudocode

```c
__int64 __fastcall PmAssociatePartition(struct _DEVICE_EXTENSION *a1, struct _PARTITION_EXTENSION *a2)
{
  unsigned int v2; // ebp
  char *v3; // r15
  char *v4; // rdi
  char v5; // si
  unsigned __int64 v6; // r14
  struct _PARTITION_EXTENSION *v8; // rcx

  v2 = 0;
  v3 = (char *)a1 + 896;
  v4 = (char *)*((_QWORD *)a1 + 112);
  v5 = 0;
  v6 = 0;
  while ( v4 != v3 )
  {
    v6 = (unsigned __int64)(v4 - 144);
    if ( PmIsEqualName((const struct _GUID *)(v4 + 72), (const unsigned __int16 *)a2 + 120) )
    {
      v5 = 1;
      break;
    }
    v4 = *(char **)v4;
  }
  v8 = (struct _PARTITION_EXTENSION *)(v6 & -(__int64)(v5 != 0));
  *((_QWORD *)a2 + 4) = v8;
  if ( v8 )
    return (unsigned int)PartitionInsertPatch(
                           v8,
                           *((_QWORD *)a2 + 29) & 0xFFFFFFFFFFFFFF00uLL,
                           *((_QWORD *)a2 + 22),
                           *((_QWORD *)a2 + 23));
  return v2;
}

```

## disassembly

```asm
0x14000a21c  push    rbx
0x14000a21e  push    rbp
0x14000a21f  push    rsi
0x14000a220  push    rdi
0x14000a221  push    r14
0x14000a223  push    r15
0x14000a225  sub     rsp, 28h
0x14000a229  xor     ebp, ebp
0x14000a22b  lea     r15, [rcx+380h]
0x14000a232  mov     rdi, [r15]
0x14000a235  xor     sil, sil
0x14000a238  xor     r14d, r14d
0x14000a23b  mov     rbx, rdx
0x14000a23e  cmp     rdi, r15
0x14000a241  jz      short loc_14000A269
0x14000a243  lea     r14, [rdi-90h]
0x14000a24a  lea     rcx, [r14+0D8h]; struct _GUID *
0x14000a251  lea     rdx, [rbx+0F0h]; Source2
0x14000a258  call    ?PmIsEqualName@@YAEPEBU_GUID@@PEBG@Z; PmIsEqualName(_GUID const *,ushort const *)
0x14000a25d  test    al, al
0x14000a25f  jnz     short loc_14000A266
0x14000a261  mov     rdi, [rdi]
0x14000a264  jmp     short loc_14000A23E
0x14000a266  mov     sil, 1
0x14000a269  neg     sil
0x14000a26c  sbb     rcx, rcx
0x14000a26f  and     rcx, r14; struct _PARTITION_EXTENSION *
0x14000a272  mov     [rbx+20h], rcx
0x14000a276  jz      short loc_14000A29B
0x14000a278  mov     rdx, [rbx+0E8h]
0x14000a27f  mov     r9, [rbx+0B8h]; unsigned __int64
0x14000a286  and     rdx, 0FFFFFFFFFFFFFF00h; unsigned __int64
0x14000a28d  mov     r8, [rbx+0B0h]; unsigned __int64
0x14000a294  call    ?PartitionInsertPatch@@YAJPEAU_PARTITION_EXTENSION@@_K11@Z; PartitionInsertPatch(_PARTITION_EXTENSION *,unsigned __int64,unsigned __int64,unsigned __int64)
0x14000a299  mov     ebp, eax
0x14000a29b  mov     eax, ebp
0x14000a29d  add     rsp, 28h
0x14000a2a1  pop     r15
0x14000a2a3  pop     r14
0x14000a2a5  pop     rdi
0x14000a2a6  pop     rsi
0x14000a2a7  pop     rbp
0x14000a2a8  pop     rbx
0x14000a2a9  retn
```

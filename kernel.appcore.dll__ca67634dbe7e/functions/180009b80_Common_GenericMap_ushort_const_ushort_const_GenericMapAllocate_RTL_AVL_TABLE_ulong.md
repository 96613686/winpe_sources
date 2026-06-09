# Common::GenericMap<ushort const *,ushort const *>::GenericMapAllocate(_RTL_AVL_TABLE *,ulong)

- ea: `0x180009b80`
- end: `0x180009ba3`
- name: `?GenericMapAllocate@?$GenericMap@PEBGPEBG@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z`
- size: `35`
- prototype: `RTL_AVL_ALLOCATE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009c4c`

## pseudocode

```c
PVOID __fastcall Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapAllocate(
        struct _RTL_AVL_TABLE *Table,
        CLONG ByteSize)
{
  void *v3; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  Common::GlobalHeap::Alloc((ReservedForLocalUse *)ByteSize, &v3);
  return v3;
}

```

## disassembly

```asm
0x180009b80  sub     rsp, 28h
0x180009b84  mov     ecx, edx; unsigned __int64
0x180009b86  lea     rdx, [rsp+28h+arg_10]; void **
0x180009b8b  mov     [rsp+28h+arg_10], 0
0x180009b94  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x180009b99  mov     rax, [rsp+28h+arg_10]
0x180009b9e  add     rsp, 28h
0x180009ba2  retn
```

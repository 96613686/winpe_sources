# Common::DeallocateArray<ushort const *>(ushort const *)

- ea: `0x180009a80`
- end: `0x180009a93`
- name: `??$DeallocateArray@PEBG@Common@@YAXPEBG@Z`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x180009a80`

## pseudocode

```c
void __fastcall Common::DeallocateArray<unsigned short const *>(void *a1)
{
  if ( a1 )
    Common::GlobalHeap::Free(a1);
}

```

## disassembly

```asm
0x180009a80  sub     rsp, 28h
0x180009a84  test    rcx, rcx
0x180009a87  jz      short loc_180009A8E
0x180009a89  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180009a8e  add     rsp, 28h
0x180009a92  retn
```

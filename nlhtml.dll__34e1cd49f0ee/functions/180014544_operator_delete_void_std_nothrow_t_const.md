# operator delete(void *,std::nothrow_t const &)

- ea: `0x180014544`
- end: `0x180014549`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `63`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006834`
- `0x180006914`
- `0x180006d10`
- `0x180007094`
- `0x18000b68c`
- `0x18000c5f0`
- `0x18000cc6c`
- `0x18000d040`
- `0x18000d6c0`
- `0x18000d7f0`
- `0x18000d82c`
- `0x18000d9f0`
- `0x18000da18`
- `0x18000dad4`
- `0x18000e1b4`
- `0x18000e8b0`
- `0x18000e900`
- `0x18000f614`
- `0x180011980`
- `0x180011c70`
- `0x180011d24`
- `0x180011ec0`
- `0x180011ef4`
- `0x180011ff0`
- `0x18001202c`
- `0x180012090`
- `0x1800120e0`
- `0x1800126a0`
- `0x1800126f0`
- `0x180012740`
- `0x1800127a0`
- `0x1800128f0`
- `0x180014680`
- `0x180015b6c`
- `0x180016560`
- `0x1800165a0`
- `0x1800165e0`
- `0x180016620`
- `0x18001b410`
- `0x18001b450`
- `0x18001c6f0`
- `0x18001c730`
- `0x18001cff0`
- `0x18001d030`
- `0x18001e750`
- `0x18001f360`
- `0x18001f570`
- `0x1800212d0`
- `0x180021310`
- `0x1800213a0`

## callees

- `0x180014114`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180014544  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

# operator delete(void *,unsigned __int64)

- ea: `0x14001374c`
- end: `0x140013751`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000c7b0`
- `0x14000cb40`
- `0x14000cc30`
- `0x14000e2d0`
- `0x14000f46c`
- `0x1400121ec`
- `0x140012e18`
- `0x140012e68`
- `0x140012eb8`
- `0x140012f08`
- `0x140013720`
- `0x14001567b`
- `0x1400156a4`
- `0x140015755`
- `0x140015772`
- `0x14001578f`
- `0x140015c77`

## callees

- `0x14000a10c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x14001374c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

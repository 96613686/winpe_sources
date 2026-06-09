# operator delete(void *,unsigned __int64)

- ea: `0x180002644`
- end: `0x180002649`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004360`
- `0x1800043a0`
- `0x1800043d4`
- `0x18000af4c`
- `0x18000af80`
- `0x18000afc0`
- `0x18000c680`
- `0x18000c6d0`
- `0x18000d2a0`
- `0x18000f170`
- `0x18000fb80`
- `0x18000fbc0`
- `0x180010d10`
- `0x180011c7c`
- `0x180011f50`

## callees

- `0x180011e2c`

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
0x180002644  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

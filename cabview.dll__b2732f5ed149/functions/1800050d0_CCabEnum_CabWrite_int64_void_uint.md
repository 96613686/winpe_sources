# CCabEnum::CabWrite(__int64,void *,uint)

- ea: `0x1800050d0`
- end: `0x1800050d5`
- name: `?CabWrite@CCabEnum@@KAI_JPEAXI@Z`
- size: `5`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000990c`

## pseudocode

```c
// attributes: thunk
UINT __fastcall CCabEnum::CabWrite(CMemFile *hf, const CHAR *pv, UINT cb)
{
  return CMemFile::Write(hf, pv, cb);
}

```

## disassembly

```asm
0x1800050d0  jmp     ?Write@CMemFile@@QEAAIPEBXI@Z; CMemFile::Write(void const *,uint)
```

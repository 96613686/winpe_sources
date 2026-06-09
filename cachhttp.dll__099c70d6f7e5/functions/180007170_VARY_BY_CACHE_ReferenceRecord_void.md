# VARY_BY_CACHE::ReferenceRecord(void *)

- ea: `0x180007170`
- end: `0x180007175`
- name: `?ReferenceRecord@VARY_BY_CACHE@@UEAAXPEAX@Z`
- size: `5`
- prototype: `void __fastcall(VARY_BY_CACHE *__hidden this, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall VARY_BY_CACHE::ReferenceRecord(VARY_BY_CACHE *this, volatile signed __int32 *a2)
{
  _InterlockedIncrement(a2 + 3);
}

```

## disassembly

```asm
0x180007170  lock inc dword ptr [rdx+0Ch]
0x180007174  retn
```

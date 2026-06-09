# VARY_BY_CACHE::CacheFlushByTTL(void *,void *)

- ea: `0x1800076a0`
- end: `0x1800076ae`
- name: `?CacheFlushByTTL@VARY_BY_CACHE@@CAHPEAX0@Z`
- size: `14`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
_BOOL8 __fastcall VARY_BY_CACHE::CacheFlushByTTL(volatile signed __int32 *a1, void *a2)
{
  return _InterlockedAdd(a1 + 4, 0xFFFFFFFF) == 0;
}

```

## disassembly

```asm
0x1800076a0  lock add dword ptr [rcx+10h], 0FFFFFFFFh
0x1800076a5  mov     eax, 0
0x1800076aa  setz    al
0x1800076ad  retn
```

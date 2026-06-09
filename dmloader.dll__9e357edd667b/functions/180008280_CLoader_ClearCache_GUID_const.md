# CLoader::ClearCache(_GUID const &)

- ea: `0x180008280`
- end: `0x180008285`
- name: `?ClearCache@CLoader@@UEAAJAEBU_GUID@@@Z`
- size: `5`
- prototype: `__int64 __fastcall(CLoader *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000828c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CLoader::ClearCache(CClass **this, const struct _GUID *a2)
{
  return CLoader::ClearCacheInternal(this, a2);
}

```

## disassembly

```asm
0x180008280  jmp     ?ClearCacheInternal@CLoader@@AEAAJAEBU_GUID@@_N@Z; CLoader::ClearCacheInternal(_GUID const &,bool)
```

# CreateContext_Dc

- ea: `0x180011930`
- end: `0x180011935`
- name: `CreateContext_Dc`
- size: `5`
- prototype: `__int64 __fastcall(void *, UUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010098`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CreateContext_Dc(void *a1, UUID **a2)
{
  return CreateContext(a1, a2);
}

```

## disassembly

```asm
0x180011930  jmp     ?CreateContext@@YAJPEAXPEAPEAX@Z; CreateContext(void *,void * *)
```

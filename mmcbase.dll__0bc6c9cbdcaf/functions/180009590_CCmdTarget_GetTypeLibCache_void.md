# CCmdTarget::GetTypeLibCache(void)

- ea: `0x180009590`
- end: `0x180009596`
- name: `?GetTypeLibCache@CCmdTarget@@UEAAPEAVCTypeLibCache@@XZ_0`
- size: `6`
- prototype: `struct CTypeLibCache *(CCmdTarget *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MFC42u!__imp_?GetTypeLibCache@CCmdTarget@@UEAAPEAVCTypeLibCache@@XZ` at `0x180009590`

## pseudocode

```c
// attributes: thunk
struct CTypeLibCache *__fastcall CCmdTarget::GetTypeLibCache(CCmdTarget *this)
{
  return __imp_?GetTypeLibCache@CCmdTarget@@UEAAPEAVCTypeLibCache@@XZ(this);
}

```

## disassembly

```asm
0x180009590  jmp     cs:__imp_?GetTypeLibCache@CCmdTarget@@UEAAPEAVCTypeLibCache@@XZ
```

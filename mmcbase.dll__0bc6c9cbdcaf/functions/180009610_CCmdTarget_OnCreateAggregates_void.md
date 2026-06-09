# CCmdTarget::OnCreateAggregates(void)

- ea: `0x180009610`
- end: `0x180009616`
- name: `?OnCreateAggregates@CCmdTarget@@UEAAHXZ_0`
- size: `6`
- prototype: `int(CCmdTarget *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MFC42u!__imp_?OnCreateAggregates@CCmdTarget@@UEAAHXZ` at `0x180009610`

## pseudocode

```c
// attributes: thunk
int __fastcall CCmdTarget::OnCreateAggregates(CCmdTarget *this)
{
  return __imp_?OnCreateAggregates@CCmdTarget@@UEAAHXZ(this);
}

```

## disassembly

```asm
0x180009610  jmp     cs:__imp_?OnCreateAggregates@CCmdTarget@@UEAAHXZ
```

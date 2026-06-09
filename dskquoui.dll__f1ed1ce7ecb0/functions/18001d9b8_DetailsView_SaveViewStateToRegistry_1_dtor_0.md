# _DetailsView::SaveViewStateToRegistry_::_1_::dtor$0

- ea: `0x18001d9b8`
- end: `0x18001d9c4`
- name: `_DetailsView::SaveViewStateToRegistry_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18001b8bc`

## pseudocode

```c
void __fastcall DetailsView::SaveViewStateToRegistry_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  RegKey::~RegKey((RegKey *)(a2 + 144));
}

```

## disassembly

```asm
0x18001d9b8  lea     rcx, [rdx+90h]; this
0x18001d9bf  jmp     ??1RegKey@@UEAA@XZ; RegKey::~RegKey(void)
```

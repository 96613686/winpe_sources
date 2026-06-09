# _DetailsView::CreateToolBar_::_1_::dtor$0

- ea: `0x18001d379`
- end: `0x18001d385`
- name: `_DetailsView::CreateToolBar_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001b8bc`

## pseudocode

```c
void __fastcall DetailsView::CreateToolBar_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  RegKey::~RegKey((RegKey *)(a2 + 248));
}

```

## disassembly

```asm
0x18001d379  lea     rcx, [rdx+0F8h]; this
0x18001d380  jmp     ??1RegKey@@UEAA@XZ; RegKey::~RegKey(void)
```

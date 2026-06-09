# _DetailsView::CreateToolBar_::_1_::dtor$4

- ea: `0x18001d3af`
- end: `0x18001d3bb`
- name: `_DetailsView::CreateToolBar_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180019ee0`

## pseudocode

```c
void __fastcall DetailsView::CreateToolBar_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  CString::~CString((CString *)(a2 + 208));
}

```

## disassembly

```asm
0x18001d3af  lea     rcx, [rdx+0D0h]; this
0x18001d3b6  jmp     ??1CString@@UEAA@XZ; CString::~CString(void)
```

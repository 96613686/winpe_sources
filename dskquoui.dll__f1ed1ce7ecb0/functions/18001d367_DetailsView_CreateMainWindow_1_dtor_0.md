# _DetailsView::CreateMainWindow_::_1_::dtor$0

- ea: `0x18001d367`
- end: `0x18001d373`
- name: `_DetailsView::CreateMainWindow_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180019ee0`

## pseudocode

```c
void __fastcall DetailsView::CreateMainWindow_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CString::~CString((CString *)(a2 + 112));
}

```

## disassembly

```asm
0x18001d367  lea     rcx, [rdx+70h]; this
0x18001d36e  jmp     ??1CString@@UEAA@XZ; CString::~CString(void)
```

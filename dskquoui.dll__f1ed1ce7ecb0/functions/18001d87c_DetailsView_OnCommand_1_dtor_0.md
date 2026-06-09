# _DetailsView::OnCommand_::_1_::dtor$0

- ea: `0x18001d87c`
- end: `0x18001d888`
- name: `_DetailsView::OnCommand_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005cb0`

## pseudocode

```c
void __fastcall DetailsView::OnCommand_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CAutoWaitCursor::~CAutoWaitCursor((CAutoWaitCursor *)(a2 + 48));
}

```

## disassembly

```asm
0x18001d87c  lea     rcx, [rdx+30h]; this
0x18001d883  jmp     ??1CAutoWaitCursor@@QEAA@XZ; CAutoWaitCursor::~CAutoWaitCursor(void)
```

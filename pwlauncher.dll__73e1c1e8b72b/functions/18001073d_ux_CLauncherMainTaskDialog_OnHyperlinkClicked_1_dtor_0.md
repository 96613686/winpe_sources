# _ux::CLauncherMainTaskDialog::OnHyperlinkClicked_::_1_::dtor$0

- ea: `0x18001073d`
- end: `0x180010749`
- name: `_ux::CLauncherMainTaskDialog::OnHyperlinkClicked_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000266c`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::OnHyperlinkClicked_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 64));
}

```

## disassembly

```asm
0x18001073d  lea     rcx, [rdx+40h]; this
0x180010744  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

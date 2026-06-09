# _ux::CLauncherMainTaskDialog::CLauncherMainTaskDialog_::_1_::dtor$2

- ea: `0x18001064a`
- end: `0x180010656`
- name: `_ux::CLauncherMainTaskDialog::CLauncherMainTaskDialog_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800098a0`

## pseudocode

```c
__int64 __fastcall ux::CLauncherMainTaskDialog::CLauncherMainTaskDialog_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IHxHelpPane>::~CComPtr<IHxHelpPane>((__int64 *)(a2 + 128));
}

```

## disassembly

```asm
0x18001064a  lea     rcx, [rdx+80h]
0x180010651  jmp     ??1?$CComPtr@UIHxHelpPane@@@ATL@@QEAA@XZ; ATL::CComPtr<IHxHelpPane>::~CComPtr<IHxHelpPane>(void)
```

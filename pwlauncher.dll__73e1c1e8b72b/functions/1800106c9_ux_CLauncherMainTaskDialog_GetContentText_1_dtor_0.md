# _ux::CLauncherMainTaskDialog::GetContentText_::_1_::dtor$0

- ea: `0x1800106c9`
- end: `0x1800106d5`
- name: `_ux::CLauncherMainTaskDialog::GetContentText_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800098ec`

## pseudocode

```c
__int64 __fastcall ux::CLauncherMainTaskDialog::GetContentText_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(a2 + 136));
}

```

## disassembly

```asm
0x1800106c9  lea     rcx, [rdx+88h]
0x1800106d0  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```

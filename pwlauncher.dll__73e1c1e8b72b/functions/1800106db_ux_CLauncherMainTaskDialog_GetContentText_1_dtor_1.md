# _ux::CLauncherMainTaskDialog::GetContentText_::_1_::dtor$1

- ea: `0x1800106db`
- end: `0x1800106e7`
- name: `_ux::CLauncherMainTaskDialog::GetContentText_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800098ec`

## pseudocode

```c
__int64 __fastcall ux::CLauncherMainTaskDialog::GetContentText_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(a2 + 128));
}

```

## disassembly

```asm
0x1800106db  lea     rcx, [rdx+80h]
0x1800106e2  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```

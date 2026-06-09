# _ux::CLauncherMainTaskDialog::CLauncherMainTaskDialog_::_1_::dtor$0

- ea: `0x18001061f`
- end: `0x180010632`
- name: `_ux::CLauncherMainTaskDialog::CLauncherMainTaskDialog_::_1_::dtor$0`
- size: `19`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800098ec`

## pseudocode

```c
__int64 __fastcall ux::CLauncherMainTaskDialog::CLauncherMainTaskDialog_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(*(_QWORD *)(a2 + 112) + 184LL));
}

```

## disassembly

```asm
0x18001061f  mov     rcx, [rdx+70h]
0x180010626  add     rcx, 0B8h
0x18001062d  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```

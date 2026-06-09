# _ux::CLauncherMainTaskDialog::SetLauncherEnabled_::_1_::dtor$2

- ea: `0x180010763`
- end: `0x18001076f`
- name: `_ux::CLauncherMainTaskDialog::SetLauncherEnabled_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009920`

## pseudocode

```c
__int64 __fastcall ux::CLauncherMainTaskDialog::SetLauncherEnabled_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::tr1::shared_ptr<utils::CAsyncResultNoResult>::~shared_ptr<utils::CAsyncResultNoResult>(a2 + 48);
}

```

## disassembly

```asm
0x180010763  lea     rcx, [rdx+30h]
0x18001076a  jmp     ??1?$shared_ptr@VCAsyncResultNoResult@utils@@@tr1@std@@QEAA@XZ; std::tr1::shared_ptr<utils::CAsyncResultNoResult>::~shared_ptr<utils::CAsyncResultNoResult>(void)
```

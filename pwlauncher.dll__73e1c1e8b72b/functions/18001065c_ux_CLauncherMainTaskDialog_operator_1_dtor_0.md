# _ux::CLauncherMainTaskDialog::operator()_::_1_::dtor$0

- ea: `0x18001065c`
- end: `0x180010668`
- name: `_ux::CLauncherMainTaskDialog::operator()_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009920`

## pseudocode

```c
__int64 __fastcall ux::CLauncherMainTaskDialog::operator()_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::tr1::shared_ptr<utils::CAsyncResultNoResult>::~shared_ptr<utils::CAsyncResultNoResult>(*(_QWORD *)(a2 + 120));
}

```

## disassembly

```asm
0x18001065c  mov     rcx, [rdx+78h]
0x180010663  jmp     ??1?$shared_ptr@VCAsyncResultNoResult@utils@@@tr1@std@@QEAA@XZ; std::tr1::shared_ptr<utils::CAsyncResultNoResult>::~shared_ptr<utils::CAsyncResultNoResult>(void)
```

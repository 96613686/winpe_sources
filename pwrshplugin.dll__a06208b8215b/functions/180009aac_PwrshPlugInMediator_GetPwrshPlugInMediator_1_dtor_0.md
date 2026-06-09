# _PwrshPlugInMediator::GetPwrshPlugInMediator_::_1_::dtor$0

- ea: `0x180009aac`
- end: `0x180009ab8`
- name: `_PwrshPlugInMediator::GetPwrshPlugInMediator_::_1_::dtor$0`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001818`

## pseudocode

```c
void PwrshPlugInMediator::GetPwrshPlugInMediator_::_1_::dtor_0()
{
  Init_thread_abort(&__TSS0__1__GetPwrshPlugInMediator_PwrshPlugInMediator__SAPEAV2_PEBG_Z_4HA);
}

```

## disassembly

```asm
0x180009aac  lea     rcx, ?$TSS0@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV2@PEBG@Z@4HA
0x180009ab3  jmp     _Init_thread_abort
```

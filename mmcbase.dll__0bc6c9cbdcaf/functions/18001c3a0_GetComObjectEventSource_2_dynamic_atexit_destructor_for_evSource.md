# _GetComObjectEventSource_::_2_::_dynamic_atexit_destructor_for__evSource__

- ea: `0x18001c3a0`
- end: `0x18001c3ac`
- name: `_GetComObjectEventSource_::_2_::_dynamic_atexit_destructor_for__evSource__`
- size: `12`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005590`

## pseudocode

```c
void __fastcall GetComObjectEventSource_::_2_::_dynamic_atexit_destructor_for__evSource__()
{
  _CEventSource<CComObjectObserver>::~_CEventSource<CComObjectObserver>((struct CEventSourceBase *)&off_18002B400);
}

```

## disassembly

```asm
0x18001c3a0  lea     rcx, off_18002B400; struct CEventSourceBase *
0x18001c3a7  jmp     ??1?$_CEventSource@VCComObjectObserver@@@@UEAA@XZ; _CEventSource<CComObjectObserver>::~_CEventSource<CComObjectObserver>(void)
```

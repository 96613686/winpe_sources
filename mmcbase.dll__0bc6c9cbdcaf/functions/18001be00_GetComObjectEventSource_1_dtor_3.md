# _GetComObjectEventSource_::_1_::dtor$3

- ea: `0x18001be00`
- end: `0x18001be0c`
- name: `_GetComObjectEventSource_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800082c4`

## pseudocode

```c
void GetComObjectEventSource_::_1_::dtor_3()
{
  CEventSourceBase::~CEventSourceBase((CEventSourceBase *)&off_18002B400);
}

```

## disassembly

```asm
0x18001be00  lea     rcx, off_18002B400; this
0x18001be07  jmp     ??1CEventSourceBase@@UEAA@XZ; CEventSourceBase::~CEventSourceBase(void)
```

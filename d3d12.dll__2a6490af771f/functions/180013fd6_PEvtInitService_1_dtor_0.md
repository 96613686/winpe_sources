# _PEvtInitService_::_1_::dtor$0

- ea: `0x180013fd6`
- end: `0x180013fe2`
- name: `_PEvtInitService_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001250c`

## pseudocode

```c
void __fastcall PEvtInitService_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  AutoLock::~AutoLock((AutoLock *)(a2 + 120));
}

```

## disassembly

```asm
0x180013fd6  lea     rcx, [rdx+78h]; this
0x180013fdd  jmp     ??1AutoLock@@QEAA@XZ; AutoLock::~AutoLock(void)
```

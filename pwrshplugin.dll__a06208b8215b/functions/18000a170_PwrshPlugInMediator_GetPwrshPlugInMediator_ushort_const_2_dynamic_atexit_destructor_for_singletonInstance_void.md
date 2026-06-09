# `PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)'::`2'::`dynamic atexit destructor for 'singletonInstance''(void)

- ea: `0x18000a170`
- end: `0x18000a17c`
- name: `??__FsingletonInstance@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z@YAXXZ`
- size: `12`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800020a0`

## pseudocode

```c
void __fastcall `PwrshPlugInMediator::GetPwrshPlugInMediator'::`2'::`dynamic atexit destructor for 'singletonInstance''()
{
  PwrshPlugInMediator::~PwrshPlugInMediator((PwrshPlugInMediator *)&`PwrshPlugInMediator::GetPwrshPlugInMediator'::`2'::singletonInstance);
}

```

## disassembly

```asm
0x18000a170  lea     rcx, ?singletonInstance@?1??GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV2@PEBG@Z@4V2@A; this
0x18000a177  jmp     ??1PwrshPlugInMediator@@QEAA@XZ; PwrshPlugInMediator::~PwrshPlugInMediator(void)
```

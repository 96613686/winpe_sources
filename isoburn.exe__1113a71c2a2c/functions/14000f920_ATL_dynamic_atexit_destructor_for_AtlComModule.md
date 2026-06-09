# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x14000f920`
- end: `0x14000f92c`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000eefc`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  ATL::CAtlComModule::~CAtlComModule((ATL::CAtlComModule *)&ATL::_AtlComModule);
}

```

## disassembly

```asm
0x14000f920  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; this
0x14000f927  jmp     ??1CAtlComModule@ATL@@QEAA@XZ; ATL::CAtlComModule::~CAtlComModule(void)
```

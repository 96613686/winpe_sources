# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x1800420d0`
- end: `0x1800420f1`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a6f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800420db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800420db`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_180060138);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)&ATL::_AtlBaseModule);
}

```

## disassembly

```asm
0x1800420d0  sub     rsp, 28h
0x1800420d4  lea     rcx, stru_180060138; lpCriticalSection
0x1800420db  call    cs:__imp_DeleteCriticalSection
0x1800420e1  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x1800420e8  add     rsp, 28h
0x1800420ec  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

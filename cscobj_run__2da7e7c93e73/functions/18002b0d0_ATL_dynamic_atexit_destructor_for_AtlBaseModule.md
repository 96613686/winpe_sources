# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x18002b0d0`
- end: `0x18002b0f1`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800096bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b0db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b0db`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&CriticalSection);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)&ATL::_AtlBaseModule);
}

```

## disassembly

```asm
0x18002b0d0  sub     rsp, 28h
0x18002b0d4  lea     rcx, CriticalSection; lpCriticalSection
0x18002b0db  call    cs:__imp_DeleteCriticalSection
0x18002b0e1  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x18002b0e8  add     rsp, 28h
0x18002b0ec  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

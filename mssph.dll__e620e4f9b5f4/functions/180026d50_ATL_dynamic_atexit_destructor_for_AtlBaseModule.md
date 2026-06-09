# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x180026d50`
- end: `0x180026d71`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e07c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026d5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026d5b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_180036558);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)&ATL::_AtlBaseModule);
}

```

## disassembly

```asm
0x180026d50  sub     rsp, 28h
0x180026d54  lea     rcx, stru_180036558; lpCriticalSection
0x180026d5b  call    cs:__imp_DeleteCriticalSection
0x180026d61  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x180026d68  add     rsp, 28h
0x180026d6c  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

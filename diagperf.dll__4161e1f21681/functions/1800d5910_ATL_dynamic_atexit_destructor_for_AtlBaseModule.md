# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x1800d5910`
- end: `0x1800d5931`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800422b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d591b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d591b`

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
0x1800d5910  sub     rsp, 28h
0x1800d5914  lea     rcx, CriticalSection; lpCriticalSection
0x1800d591b  call    cs:__imp_DeleteCriticalSection
0x1800d5921  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x1800d5928  add     rsp, 28h
0x1800d592c  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

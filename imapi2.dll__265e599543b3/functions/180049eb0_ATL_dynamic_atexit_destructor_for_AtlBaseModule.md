# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x180049eb0`
- end: `0x180049ed1`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000eb34`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180049ebb`
- `KERNEL32!DeleteCriticalSection` at `0x180049ebb`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_180062748);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)&ATL::_AtlBaseModule);
}

```

## disassembly

```asm
0x180049eb0  sub     rsp, 28h
0x180049eb4  lea     rcx, stru_180062748; lpCriticalSection
0x180049ebb  call    cs:__imp_DeleteCriticalSection
0x180049ec1  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x180049ec8  add     rsp, 28h
0x180049ecc  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

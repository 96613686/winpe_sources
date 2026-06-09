# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x180022790`
- end: `0x1800227b1`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000deb4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002279b`
- `KERNEL32!DeleteCriticalSection` at `0x18002279b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_1800324A8);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)&ATL::_AtlBaseModule);
}

```

## disassembly

```asm
0x180022790  sub     rsp, 28h
0x180022794  lea     rcx, stru_1800324A8; lpCriticalSection
0x18002279b  call    cs:__imp_DeleteCriticalSection
0x1800227a1  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x1800227a8  add     rsp, 28h
0x1800227ac  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

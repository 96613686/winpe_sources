# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18002a408`
- end: `0x18002a428`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180033cd0`

## callees

- `0x18002a470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a415`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a415`

## pseudocode

```c
void __fastcall ATL::CAtlBaseModule::~CAtlBaseModule(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this + 1);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)this);
}

```

## disassembly

```asm
0x18002a408  push    rbx
0x18002a40a  sub     rsp, 20h
0x18002a40e  mov     rbx, rcx
0x18002a411  add     rcx, 28h ; '('; lpCriticalSection
0x18002a415  call    cs:__imp_DeleteCriticalSection
0x18002a41b  mov     rcx, rbx; this
0x18002a41e  add     rsp, 20h
0x18002a422  pop     rbx
0x18002a423  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

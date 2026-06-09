# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180031c90`
- end: `0x180031cb0`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180037520`

## callees

- `0x180031cf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031c9d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031c9d`

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
0x180031c90  push    rbx
0x180031c92  sub     rsp, 20h
0x180031c96  mov     rbx, rcx
0x180031c99  add     rcx, 28h ; '('; lpCriticalSection
0x180031c9d  call    cs:__imp_DeleteCriticalSection
0x180031ca3  mov     rcx, rbx; this
0x180031ca6  add     rsp, 20h
0x180031caa  pop     rbx
0x180031cab  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

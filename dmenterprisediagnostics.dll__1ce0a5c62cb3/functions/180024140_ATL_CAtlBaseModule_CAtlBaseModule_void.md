# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180024140`
- end: `0x180024160`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180025c40`

## callees

- `0x1800241a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002414d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002414d`

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
0x180024140  push    rbx
0x180024142  sub     rsp, 20h
0x180024146  mov     rbx, rcx
0x180024149  add     rcx, 28h ; '('; lpCriticalSection
0x18002414d  call    cs:__imp_DeleteCriticalSection
0x180024153  mov     rcx, rbx; this
0x180024156  add     rsp, 20h
0x18002415a  pop     rbx
0x18002415b  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

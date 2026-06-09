# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800143a8`
- end: `0x1800143c8`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b350`

## callees

- `0x1800143fc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800143b5`
- `KERNEL32!DeleteCriticalSection` at `0x1800143b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlBaseModule::~CAtlBaseModule(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this + 1);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)this);
}

```

## disassembly

```asm
0x1800143a8  push    rbx
0x1800143aa  sub     rsp, 20h
0x1800143ae  mov     rbx, rcx
0x1800143b1  add     rcx, 28h ; '('; lpCriticalSection
0x1800143b5  call    cs:__imp_DeleteCriticalSection
0x1800143bb  mov     rcx, rbx; this
0x1800143be  add     rsp, 20h
0x1800143c2  pop     rbx
0x1800143c3  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

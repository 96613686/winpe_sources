# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000c5d4`
- end: `0x18000c5f4`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002d430`

## callees

- `0x18000c688`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c5e1`
- `KERNEL32!DeleteCriticalSection` at `0x18000c5e1`

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
0x18000c5d4  push    rbx
0x18000c5d6  sub     rsp, 20h
0x18000c5da  mov     rbx, rcx
0x18000c5dd  add     rcx, 28h ; '('; lpCriticalSection
0x18000c5e1  call    cs:__imp_DeleteCriticalSection
0x18000c5e7  mov     rcx, rbx; this
0x18000c5ea  add     rsp, 20h
0x18000c5ee  pop     rbx
0x18000c5ef  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

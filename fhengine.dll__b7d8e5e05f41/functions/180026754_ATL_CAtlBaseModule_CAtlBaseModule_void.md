# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180026754`
- end: `0x180026774`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180033730`

## callees

- `0x1800267a8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180026761`
- `KERNEL32!DeleteCriticalSection` at `0x180026761`

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
0x180026754  push    rbx
0x180026756  sub     rsp, 20h
0x18002675a  mov     rbx, rcx
0x18002675d  add     rcx, 28h ; '('; lpCriticalSection
0x180026761  call    cs:__imp_DeleteCriticalSection
0x180026767  mov     rcx, rbx; this
0x18002676a  add     rsp, 20h
0x18002676e  pop     rbx
0x18002676f  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180007910`
- end: `0x180007930`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ea80`

## callees

- `0x180007964`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000791d`
- `KERNEL32!DeleteCriticalSection` at `0x18000791d`

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
0x180007910  push    rbx
0x180007912  sub     rsp, 20h
0x180007916  mov     rbx, rcx
0x180007919  add     rcx, 28h ; '('; lpCriticalSection
0x18000791d  call    cs:__imp_DeleteCriticalSection
0x180007923  mov     rcx, rbx; this
0x180007926  add     rsp, 20h
0x18000792a  pop     rbx
0x18000792b  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

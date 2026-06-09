# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18001cedc`
- end: `0x18001cefc`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002fe00`

## callees

- `0x18001cf90`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001cee9`
- `KERNEL32!DeleteCriticalSection` at `0x18001cee9`

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
0x18001cedc  push    rbx
0x18001cede  sub     rsp, 20h
0x18001cee2  mov     rbx, rcx
0x18001cee5  add     rcx, 28h ; '('; lpCriticalSection
0x18001cee9  call    cs:__imp_DeleteCriticalSection
0x18001ceef  mov     rcx, rbx; this
0x18001cef2  add     rsp, 20h
0x18001cef6  pop     rbx
0x18001cef7  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

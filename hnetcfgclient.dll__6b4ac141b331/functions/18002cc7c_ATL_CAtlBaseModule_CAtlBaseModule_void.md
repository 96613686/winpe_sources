# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18002cc7c`
- end: `0x18002cc9c`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002e1c0`

## callees

- `0x18002cce4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002cc89`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002cc89`

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
0x18002cc7c  push    rbx
0x18002cc7e  sub     rsp, 20h
0x18002cc82  mov     rbx, rcx
0x18002cc85  add     rcx, 28h ; '('; lpCriticalSection
0x18002cc89  call    cs:__imp_DeleteCriticalSection
0x18002cc8f  mov     rcx, rbx; this
0x18002cc92  add     rsp, 20h
0x18002cc96  pop     rbx
0x18002cc97  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

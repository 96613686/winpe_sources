# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18001b3d8`
- end: `0x18001b3f8`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180022e70`

## callees

- `0x18001b42c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b3e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b3e5`

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
0x18001b3d8  push    rbx
0x18001b3da  sub     rsp, 20h
0x18001b3de  mov     rbx, rcx
0x18001b3e1  add     rcx, 28h ; '('; lpCriticalSection
0x18001b3e5  call    cs:__imp_DeleteCriticalSection
0x18001b3eb  mov     rcx, rbx; this
0x18001b3ee  add     rsp, 20h
0x18001b3f2  pop     rbx
0x18001b3f3  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

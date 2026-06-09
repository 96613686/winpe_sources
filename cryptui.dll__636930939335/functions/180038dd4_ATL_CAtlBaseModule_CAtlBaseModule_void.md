# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180038dd4`
- end: `0x180038df4`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180040a50`

## callees

- `0x180038e3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038de1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038de1`

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
0x180038dd4  push    rbx
0x180038dd6  sub     rsp, 20h
0x180038dda  mov     rbx, rcx
0x180038ddd  add     rcx, 28h ; '('; lpCriticalSection
0x180038de1  call    cs:__imp_DeleteCriticalSection
0x180038de7  mov     rcx, rbx; this
0x180038dea  add     rsp, 20h
0x180038dee  pop     rbx
0x180038def  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

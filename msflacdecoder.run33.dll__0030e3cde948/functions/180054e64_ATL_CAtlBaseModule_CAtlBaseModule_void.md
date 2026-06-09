# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180054e64`
- end: `0x180054e84`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180055d40`

## callees

- `0x180054ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054e71`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054e71`

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
0x180054e64  push    rbx
0x180054e66  sub     rsp, 20h
0x180054e6a  mov     rbx, rcx
0x180054e6d  add     rcx, 28h ; '('; lpCriticalSection
0x180054e71  call    cs:__imp_DeleteCriticalSection
0x180054e77  mov     rcx, rbx; this
0x180054e7a  add     rsp, 20h
0x180054e7e  pop     rbx
0x180054e7f  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000c228`
- end: `0x18000c248`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ce30`

## callees

- `0x18000c27c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c235`
- `KERNEL32!DeleteCriticalSection` at `0x18000c235`

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
0x18000c228  push    rbx
0x18000c22a  sub     rsp, 20h
0x18000c22e  mov     rbx, rcx
0x18000c231  add     rcx, 28h ; '('; lpCriticalSection
0x18000c235  call    cs:__imp_DeleteCriticalSection
0x18000c23b  mov     rcx, rbx; this
0x18000c23e  add     rsp, 20h
0x18000c242  pop     rbx
0x18000c243  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18002e364`
- end: `0x18002e384`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800359a0`

## callees

- `0x18002e3cc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002e371`
- `KERNEL32!DeleteCriticalSection` at `0x18002e371`

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
0x18002e364  push    rbx
0x18002e366  sub     rsp, 20h
0x18002e36a  mov     rbx, rcx
0x18002e36d  add     rcx, 28h ; '('; lpCriticalSection
0x18002e371  call    cs:__imp_DeleteCriticalSection
0x18002e377  mov     rcx, rbx; this
0x18002e37a  add     rsp, 20h
0x18002e37e  pop     rbx
0x18002e37f  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

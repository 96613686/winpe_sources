# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x14001bca0`
- end: `0x14001bcc0`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140026830`

## callees

- `0x14001bcf4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001bcad`
- `KERNEL32!DeleteCriticalSection` at `0x14001bcad`

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
0x14001bca0  push    rbx
0x14001bca2  sub     rsp, 20h
0x14001bca6  mov     rbx, rcx
0x14001bca9  add     rcx, 28h ; '('; lpCriticalSection
0x14001bcad  call    cs:__imp_DeleteCriticalSection
0x14001bcb3  mov     rcx, rbx; this
0x14001bcb6  add     rsp, 20h
0x14001bcba  pop     rbx
0x14001bcbb  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

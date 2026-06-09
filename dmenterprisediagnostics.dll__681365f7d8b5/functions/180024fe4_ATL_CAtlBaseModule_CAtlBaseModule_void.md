# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180024fe4`
- end: `0x18002500a`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026b00`

## callees

- `0x180025058`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024ff1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024ff1`

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
0x180024fe4  push    rbx
0x180024fe6  sub     rsp, 20h
0x180024fea  mov     rbx, rcx
0x180024fed  add     rcx, 28h ; '('; lpCriticalSection
0x180024ff1  call    cs:__imp_DeleteCriticalSection
0x180024ff8  nop     dword ptr [rax+rax+00h]
0x180024ffd  mov     rcx, rbx; this
0x180025000  add     rsp, 20h
0x180025004  pop     rbx
0x180025005  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

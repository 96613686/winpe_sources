# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180032ecc`
- end: `0x180032ef2`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180038920`

## callees

- `0x180032f40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032ed9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032ed9`

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
0x180032ecc  push    rbx
0x180032ece  sub     rsp, 20h
0x180032ed2  mov     rbx, rcx
0x180032ed5  add     rcx, 28h ; '('; lpCriticalSection
0x180032ed9  call    cs:__imp_DeleteCriticalSection
0x180032ee0  nop     dword ptr [rax+rax+00h]
0x180032ee5  mov     rcx, rbx; this
0x180032ee8  add     rsp, 20h
0x180032eec  pop     rbx
0x180032eed  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```

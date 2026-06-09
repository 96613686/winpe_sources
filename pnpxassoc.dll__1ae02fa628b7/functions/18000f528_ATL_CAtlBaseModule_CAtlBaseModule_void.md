# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000f528`
- end: `0x18000f560`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800132c0`

## callees

- `0x18000f528`

## import_xrefs

- `msvcrt!free` at `0x18000f544`
- `msvcrt!free` at `0x18000f544`
- `KERNEL32!DeleteCriticalSection` at `0x18000f535`
- `KERNEL32!DeleteCriticalSection` at `0x18000f535`

## pseudocode

```c
void __fastcall ATL::CAtlBaseModule::~CAtlBaseModule(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  DeleteCriticalSection(this + 1);
  DebugInfo = this[2].DebugInfo;
  if ( DebugInfo )
  {
    free(DebugInfo);
    this[2].DebugInfo = 0;
  }
  *(_QWORD *)&this[2].LockCount = 0;
}

```

## disassembly

```asm
0x18000f528  push    rbx
0x18000f52a  sub     rsp, 20h
0x18000f52e  mov     rbx, rcx
0x18000f531  add     rcx, 28h ; '('; lpCriticalSection
0x18000f535  call    cs:__imp_DeleteCriticalSection
0x18000f53b  mov     rcx, [rbx+50h]; Block
0x18000f53f  test    rcx, rcx
0x18000f542  jz      short loc_18000F552
0x18000f544  call    cs:__imp_free
0x18000f54a  mov     qword ptr [rbx+50h], 0
0x18000f552  mov     qword ptr [rbx+58h], 0
0x18000f55a  add     rsp, 20h
0x18000f55e  pop     rbx
0x18000f55f  retn
```

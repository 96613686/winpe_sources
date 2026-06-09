# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180009638`
- end: `0x180009670`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a0b0`

## callees

- `0x180009638`

## import_xrefs

- `msvcrt!free` at `0x180009654`
- `msvcrt!free` at `0x180009654`
- `KERNEL32!DeleteCriticalSection` at `0x180009645`
- `KERNEL32!DeleteCriticalSection` at `0x180009645`

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
0x180009638  push    rbx
0x18000963a  sub     rsp, 20h
0x18000963e  mov     rbx, rcx
0x180009641  add     rcx, 28h ; '('; lpCriticalSection
0x180009645  call    cs:__imp_DeleteCriticalSection
0x18000964b  mov     rcx, [rbx+50h]; Block
0x18000964f  test    rcx, rcx
0x180009652  jz      short loc_180009662
0x180009654  call    cs:__imp_free
0x18000965a  mov     qword ptr [rbx+50h], 0
0x180009662  mov     qword ptr [rbx+58h], 0
0x18000966a  add     rsp, 20h
0x18000966e  pop     rbx
0x18000966f  retn
```

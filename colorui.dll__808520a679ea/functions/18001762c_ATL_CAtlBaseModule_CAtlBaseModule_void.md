# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18001762c`
- end: `0x180017664`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018ac0`

## callees

- `0x18001762c`

## import_xrefs

- `msvcrt!free` at `0x180017648`
- `msvcrt!free` at `0x180017648`
- `KERNEL32!DeleteCriticalSection` at `0x180017639`
- `KERNEL32!DeleteCriticalSection` at `0x180017639`

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
0x18001762c  push    rbx
0x18001762e  sub     rsp, 20h
0x180017632  mov     rbx, rcx
0x180017635  add     rcx, 28h ; '('; lpCriticalSection
0x180017639  call    cs:__imp_DeleteCriticalSection
0x18001763f  mov     rcx, [rbx+50h]; Block
0x180017643  test    rcx, rcx
0x180017646  jz      short loc_180017656
0x180017648  call    cs:__imp_free
0x18001764e  mov     qword ptr [rbx+50h], 0
0x180017656  mov     qword ptr [rbx+58h], 0
0x18001765e  add     rsp, 20h
0x180017662  pop     rbx
0x180017663  retn
```

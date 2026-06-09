# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800071f8`
- end: `0x180007230`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eff0`

## callees

- `0x1800071f8`

## import_xrefs

- `msvcrt!free` at `0x180007214`
- `msvcrt!free` at `0x180007214`
- `KERNEL32!DeleteCriticalSection` at `0x180007205`
- `KERNEL32!DeleteCriticalSection` at `0x180007205`

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
0x1800071f8  push    rbx
0x1800071fa  sub     rsp, 20h
0x1800071fe  mov     rbx, rcx
0x180007201  add     rcx, 28h ; '('; lpCriticalSection
0x180007205  call    cs:__imp_DeleteCriticalSection
0x18000720b  mov     rcx, [rbx+50h]; Block
0x18000720f  test    rcx, rcx
0x180007212  jz      short loc_180007222
0x180007214  call    cs:__imp_free
0x18000721a  mov     qword ptr [rbx+50h], 0
0x180007222  mov     qword ptr [rbx+58h], 0
0x18000722a  add     rsp, 20h
0x18000722e  pop     rbx
0x18000722f  retn
```

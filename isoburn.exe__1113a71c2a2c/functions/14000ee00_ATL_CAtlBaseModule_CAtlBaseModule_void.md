# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x14000ee00`
- end: `0x14000ee37`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f8e0`

## callees

- `0x140002b8a`
- `0x14000ee00`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000ee0d`
- `KERNEL32!DeleteCriticalSection` at `0x14000ee0d`

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
0x14000ee00  push    rbx
0x14000ee02  sub     rsp, 20h
0x14000ee06  mov     rbx, rcx
0x14000ee09  add     rcx, 28h ; '('; lpCriticalSection
0x14000ee0d  call    cs:__imp_DeleteCriticalSection
0x14000ee13  mov     rcx, [rbx+50h]; Block
0x14000ee17  test    rcx, rcx
0x14000ee1a  jz      short loc_14000EE29
0x14000ee1c  call    free
0x14000ee21  mov     qword ptr [rbx+50h], 0
0x14000ee29  mov     qword ptr [rbx+58h], 0
0x14000ee31  add     rsp, 20h
0x14000ee35  pop     rbx
0x14000ee36  retn
```

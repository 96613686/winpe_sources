# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180016ea8`
- end: `0x180016ee0`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018950`

## callees

- `0x180016ea8`

## import_xrefs

- `msvcrt!free` at `0x180016ec4`
- `msvcrt!free` at `0x180016ec4`
- `KERNEL32!DeleteCriticalSection` at `0x180016eb5`
- `KERNEL32!DeleteCriticalSection` at `0x180016eb5`

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
0x180016ea8  push    rbx
0x180016eaa  sub     rsp, 20h
0x180016eae  mov     rbx, rcx
0x180016eb1  add     rcx, 28h ; '('; lpCriticalSection
0x180016eb5  call    cs:__imp_DeleteCriticalSection
0x180016ebb  mov     rcx, [rbx+50h]; Block
0x180016ebf  test    rcx, rcx
0x180016ec2  jz      short loc_180016ED2
0x180016ec4  call    cs:__imp_free
0x180016eca  mov     qword ptr [rbx+50h], 0
0x180016ed2  mov     qword ptr [rbx+58h], 0
0x180016eda  add     rsp, 20h
0x180016ede  pop     rbx
0x180016edf  retn
```

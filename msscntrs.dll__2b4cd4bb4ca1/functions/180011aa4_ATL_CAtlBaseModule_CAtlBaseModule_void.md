# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180011aa4`
- end: `0x180011adb`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017090`

## callees

- `0x1800032e4`
- `0x180011aa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011ab1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011ab1`

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
0x180011aa4  push    rbx
0x180011aa6  sub     rsp, 20h
0x180011aaa  mov     rbx, rcx
0x180011aad  add     rcx, 28h ; '('; lpCriticalSection
0x180011ab1  call    cs:__imp_DeleteCriticalSection
0x180011ab7  mov     rcx, [rbx+50h]; Block
0x180011abb  test    rcx, rcx
0x180011abe  jz      short loc_180011ACD
0x180011ac0  call    free
0x180011ac5  mov     qword ptr [rbx+50h], 0
0x180011acd  mov     qword ptr [rbx+58h], 0
0x180011ad5  add     rsp, 20h
0x180011ad9  pop     rbx
0x180011ada  retn
```

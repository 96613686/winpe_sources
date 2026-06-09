# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x14002bec0`
- end: `0x14002bef7`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002ff70`

## callees

- `0x1400027c0`
- `0x14002bec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002becd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002becd`

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
0x14002bec0  push    rbx
0x14002bec2  sub     rsp, 20h
0x14002bec6  mov     rbx, rcx
0x14002bec9  add     rcx, 28h ; '('; lpCriticalSection
0x14002becd  call    cs:__imp_DeleteCriticalSection
0x14002bed3  mov     rcx, [rbx+50h]; Block
0x14002bed7  test    rcx, rcx
0x14002beda  jz      short loc_14002BEE9
0x14002bedc  call    free
0x14002bee1  mov     qword ptr [rbx+50h], 0
0x14002bee9  mov     qword ptr [rbx+58h], 0
0x14002bef1  add     rsp, 20h
0x14002bef5  pop     rbx
0x14002bef6  retn
```

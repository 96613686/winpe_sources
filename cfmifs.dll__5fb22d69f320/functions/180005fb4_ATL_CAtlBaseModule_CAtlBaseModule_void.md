# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180005fb4`
- end: `0x180005fec`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006480`

## callees

- `0x180005fb4`

## import_xrefs

- `msvcrt!free` at `0x180005fd0`
- `msvcrt!free` at `0x180005fd0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005fc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005fc1`

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
0x180005fb4  push    rbx
0x180005fb6  sub     rsp, 20h
0x180005fba  mov     rbx, rcx
0x180005fbd  add     rcx, 28h ; '('; lpCriticalSection
0x180005fc1  call    cs:__imp_DeleteCriticalSection
0x180005fc7  mov     rcx, [rbx+50h]; Block
0x180005fcb  test    rcx, rcx
0x180005fce  jz      short loc_180005FDE
0x180005fd0  call    cs:__imp_free
0x180005fd6  mov     qword ptr [rbx+50h], 0
0x180005fde  mov     qword ptr [rbx+58h], 0
0x180005fe6  add     rsp, 20h
0x180005fea  pop     rbx
0x180005feb  retn
```

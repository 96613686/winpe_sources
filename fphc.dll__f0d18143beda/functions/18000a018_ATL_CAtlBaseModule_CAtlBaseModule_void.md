# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000a018`
- end: `0x18000a050`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011cd0`

## callees

- `0x18000a018`

## import_xrefs

- `msvcrt!free` at `0x18000a034`
- `msvcrt!free` at `0x18000a034`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a025`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a025`

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
0x18000a018  push    rbx
0x18000a01a  sub     rsp, 20h
0x18000a01e  mov     rbx, rcx
0x18000a021  add     rcx, 28h ; '('; lpCriticalSection
0x18000a025  call    cs:__imp_DeleteCriticalSection
0x18000a02b  mov     rcx, [rbx+50h]; Block
0x18000a02f  test    rcx, rcx
0x18000a032  jz      short loc_18000A042
0x18000a034  call    cs:__imp_free
0x18000a03a  mov     qword ptr [rbx+50h], 0
0x18000a042  mov     qword ptr [rbx+58h], 0
0x18000a04a  add     rsp, 20h
0x18000a04e  pop     rbx
0x18000a04f  retn
```

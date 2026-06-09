# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800040cc`
- end: `0x180004104`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009250`

## callees

- `0x1800040cc`

## import_xrefs

- `msvcrt!free` at `0x1800040e8`
- `msvcrt!free` at `0x1800040e8`
- `KERNEL32!DeleteCriticalSection` at `0x1800040d9`
- `KERNEL32!DeleteCriticalSection` at `0x1800040d9`

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
0x1800040cc  push    rbx
0x1800040ce  sub     rsp, 20h
0x1800040d2  mov     rbx, rcx
0x1800040d5  add     rcx, 28h ; '('; lpCriticalSection
0x1800040d9  call    cs:__imp_DeleteCriticalSection
0x1800040df  mov     rcx, [rbx+50h]; Block
0x1800040e3  test    rcx, rcx
0x1800040e6  jz      short loc_1800040F6
0x1800040e8  call    cs:__imp_free
0x1800040ee  mov     qword ptr [rbx+50h], 0
0x1800040f6  mov     qword ptr [rbx+58h], 0
0x1800040fe  add     rsp, 20h
0x180004102  pop     rbx
0x180004103  retn
```

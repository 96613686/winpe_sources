# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000791c`
- end: `0x180007954`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b6f0`

## callees

- `0x18000791c`

## import_xrefs

- `msvcrt!free` at `0x180007938`
- `msvcrt!free` at `0x180007938`
- `KERNEL32!DeleteCriticalSection` at `0x180007929`
- `KERNEL32!DeleteCriticalSection` at `0x180007929`

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
0x18000791c  push    rbx
0x18000791e  sub     rsp, 20h
0x180007922  mov     rbx, rcx
0x180007925  add     rcx, 28h ; '('; lpCriticalSection
0x180007929  call    cs:__imp_DeleteCriticalSection
0x18000792f  mov     rcx, [rbx+50h]; Block
0x180007933  test    rcx, rcx
0x180007936  jz      short loc_180007946
0x180007938  call    cs:__imp_free
0x18000793e  mov     qword ptr [rbx+50h], 0
0x180007946  mov     qword ptr [rbx+58h], 0
0x18000794e  add     rsp, 20h
0x180007952  pop     rbx
0x180007953  retn
```

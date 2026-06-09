# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000d7a4`
- end: `0x18000d7dc`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010d90`

## callees

- `0x18000d7a4`

## import_xrefs

- `msvcrt!free` at `0x18000d7c0`
- `msvcrt!free` at `0x18000d7c0`
- `KERNEL32!DeleteCriticalSection` at `0x18000d7b1`
- `KERNEL32!DeleteCriticalSection` at `0x18000d7b1`

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
0x18000d7a4  push    rbx
0x18000d7a6  sub     rsp, 20h
0x18000d7aa  mov     rbx, rcx
0x18000d7ad  add     rcx, 28h ; '('; lpCriticalSection
0x18000d7b1  call    cs:__imp_DeleteCriticalSection
0x18000d7b7  mov     rcx, [rbx+50h]; Block
0x18000d7bb  test    rcx, rcx
0x18000d7be  jz      short loc_18000D7CE
0x18000d7c0  call    cs:__imp_free
0x18000d7c6  mov     qword ptr [rbx+50h], 0
0x18000d7ce  mov     qword ptr [rbx+58h], 0
0x18000d7d6  add     rsp, 20h
0x18000d7da  pop     rbx
0x18000d7db  retn
```

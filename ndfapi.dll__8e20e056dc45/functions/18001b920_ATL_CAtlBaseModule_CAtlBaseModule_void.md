# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18001b920`
- end: `0x18001b958`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020a70`

## callees

- `0x18001b920`

## import_xrefs

- `msvcrt!free` at `0x18001b93c`
- `msvcrt!free` at `0x18001b93c`
- `KERNEL32!DeleteCriticalSection` at `0x18001b92d`
- `KERNEL32!DeleteCriticalSection` at `0x18001b92d`

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
0x18001b920  push    rbx
0x18001b922  sub     rsp, 20h
0x18001b926  mov     rbx, rcx
0x18001b929  add     rcx, 28h ; '('; lpCriticalSection
0x18001b92d  call    cs:__imp_DeleteCriticalSection
0x18001b933  mov     rcx, [rbx+50h]; Block
0x18001b937  test    rcx, rcx
0x18001b93a  jz      short loc_18001B94A
0x18001b93c  call    cs:__imp_free
0x18001b942  mov     qword ptr [rbx+50h], 0
0x18001b94a  mov     qword ptr [rbx+58h], 0
0x18001b952  add     rsp, 20h
0x18001b956  pop     rbx
0x18001b957  retn
```

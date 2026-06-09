# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x140006448`
- end: `0x140006480`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400067c0`

## callees

- `0x140006448`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140006455`
- `KERNEL32!DeleteCriticalSection` at `0x140006455`
- `msvcrt!free` at `0x140006464`
- `msvcrt!free` at `0x140006464`

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
0x140006448  push    rbx
0x14000644a  sub     rsp, 20h
0x14000644e  mov     rbx, rcx
0x140006451  add     rcx, 28h ; '('; lpCriticalSection
0x140006455  call    cs:__imp_DeleteCriticalSection
0x14000645b  mov     rcx, [rbx+50h]; Block
0x14000645f  test    rcx, rcx
0x140006462  jz      short loc_140006472
0x140006464  call    cs:__imp_free
0x14000646a  mov     qword ptr [rbx+50h], 0
0x140006472  mov     qword ptr [rbx+58h], 0
0x14000647a  add     rsp, 20h
0x14000647e  pop     rbx
0x14000647f  retn
```

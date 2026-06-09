# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000cbc0`
- end: `0x18000cc05`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e650`

## callees

- `0x18000cbc0`

## import_xrefs

- `msvcrt!free` at `0x18000cbe2`
- `msvcrt!free` at `0x18000cbe2`
- `KERNEL32!DeleteCriticalSection` at `0x18000cbcd`
- `KERNEL32!DeleteCriticalSection` at `0x18000cbcd`

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
0x18000cbc0  push    rbx
0x18000cbc2  sub     rsp, 20h
0x18000cbc6  mov     rbx, rcx
0x18000cbc9  add     rcx, 28h ; '('; lpCriticalSection
0x18000cbcd  call    cs:__imp_DeleteCriticalSection
0x18000cbd4  nop     dword ptr [rax+rax+00h]
0x18000cbd9  mov     rcx, [rbx+50h]; Block
0x18000cbdd  test    rcx, rcx
0x18000cbe0  jz      short loc_18000CBF6
0x18000cbe2  call    cs:__imp_free
0x18000cbe9  nop     dword ptr [rax+rax+00h]
0x18000cbee  mov     qword ptr [rbx+50h], 0
0x18000cbf6  mov     qword ptr [rbx+58h], 0
0x18000cbfe  add     rsp, 20h
0x18000cc02  pop     rbx
0x18000cc03  retn
```

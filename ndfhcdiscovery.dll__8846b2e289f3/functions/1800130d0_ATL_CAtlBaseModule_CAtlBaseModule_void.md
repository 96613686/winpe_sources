# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800130d0`
- end: `0x180013115`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800144c0`

## callees

- `0x1800130d0`

## import_xrefs

- `msvcrt!free` at `0x1800130f2`
- `msvcrt!free` at `0x1800130f2`
- `KERNEL32!DeleteCriticalSection` at `0x1800130dd`
- `KERNEL32!DeleteCriticalSection` at `0x1800130dd`

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
0x1800130d0  push    rbx
0x1800130d2  sub     rsp, 20h
0x1800130d6  mov     rbx, rcx
0x1800130d9  add     rcx, 28h ; '('; lpCriticalSection
0x1800130dd  call    cs:__imp_DeleteCriticalSection
0x1800130e4  nop     dword ptr [rax+rax+00h]
0x1800130e9  mov     rcx, [rbx+50h]; Block
0x1800130ed  test    rcx, rcx
0x1800130f0  jz      short loc_180013106
0x1800130f2  call    cs:__imp_free
0x1800130f9  nop     dword ptr [rax+rax+00h]
0x1800130fe  mov     qword ptr [rbx+50h], 0
0x180013106  mov     qword ptr [rbx+58h], 0
0x18001310e  add     rsp, 20h
0x180013112  pop     rbx
0x180013113  retn
```

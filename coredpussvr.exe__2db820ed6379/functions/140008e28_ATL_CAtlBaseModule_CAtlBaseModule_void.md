# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x140008e28`
- end: `0x140008e66`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009390`

## callees

- `0x140002114`
- `0x140008e28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008e35`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008e35`

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
0x140008e28  push    rbx
0x140008e2a  sub     rsp, 20h
0x140008e2e  mov     rbx, rcx
0x140008e31  add     rcx, 28h ; '('; lpCriticalSection
0x140008e35  call    cs:__imp_DeleteCriticalSection
0x140008e3c  nop     dword ptr [rax+rax+00h]
0x140008e41  mov     rcx, [rbx+50h]; Block
0x140008e45  test    rcx, rcx
0x140008e48  jz      short loc_140008E57
0x140008e4a  call    free
0x140008e4f  mov     qword ptr [rbx+50h], 0
0x140008e57  mov     qword ptr [rbx+58h], 0
0x140008e5f  add     rsp, 20h
0x140008e63  pop     rbx
0x140008e64  retn
```

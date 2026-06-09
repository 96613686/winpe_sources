# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180007dc8`
- end: `0x180007dff`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012860`

## callees

- `0x180002a34`
- `0x180007dc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007dd5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007dd5`

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
0x180007dc8  push    rbx
0x180007dca  sub     rsp, 20h
0x180007dce  mov     rbx, rcx
0x180007dd1  add     rcx, 28h ; '('; lpCriticalSection
0x180007dd5  call    cs:__imp_DeleteCriticalSection
0x180007ddb  mov     rcx, [rbx+50h]; Block
0x180007ddf  test    rcx, rcx
0x180007de2  jz      short loc_180007DF1
0x180007de4  call    free
0x180007de9  mov     qword ptr [rbx+50h], 0
0x180007df1  mov     qword ptr [rbx+58h], 0
0x180007df9  add     rsp, 20h
0x180007dfd  pop     rbx
0x180007dfe  retn
```

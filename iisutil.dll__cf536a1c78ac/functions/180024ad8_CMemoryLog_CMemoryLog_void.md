# CMemoryLog::~CMemoryLog(void)

- ea: `0x180024ad8`
- end: `0x180024b2a`
- name: `??1CMemoryLog@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(CMemoryLog *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ffd0`

## callees

- `0x1800034f0`
- `0x180024ad8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024b09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024b09`

## pseudocode

```c
void __fastcall CMemoryLog::~CMemoryLog(struct _RTL_CRITICAL_SECTION *this)
{
  bool v1; // zf

  v1 = LODWORD(this[3].DebugInfo) == 0;
  this->DebugInfo = 0;
  *(_QWORD *)&this->LockCount = 0;
  this->OwningThread = 0;
  LODWORD(this[1].SpinCount) = 0;
  if ( !v1 )
  {
    DeleteCriticalSection(this + 2);
    LODWORD(this[3].DebugInfo) = 0;
  }
  BUFFER::~BUFFER((BUFFER *)&this->LockSemaphore);
}

```

## disassembly

```asm
0x180024ad8  push    rbx
0x180024ada  sub     rsp, 20h
0x180024ade  cmp     dword ptr [rcx+78h], 0
0x180024ae2  mov     rbx, rcx
0x180024ae5  mov     qword ptr [rcx], 0
0x180024aec  mov     qword ptr [rcx+8], 0
0x180024af4  mov     qword ptr [rcx+10h], 0
0x180024afc  mov     dword ptr [rcx+48h], 0
0x180024b03  jz      short loc_180024B1C
0x180024b05  add     rcx, 50h ; 'P'; lpCriticalSection
0x180024b09  call    cs:__imp_DeleteCriticalSection
0x180024b10  nop     dword ptr [rax+rax+00h]
0x180024b15  mov     dword ptr [rbx+78h], 0
0x180024b1c  lea     rcx, [rbx+18h]; this
0x180024b20  add     rsp, 20h
0x180024b24  pop     rbx
0x180024b25  jmp     ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```

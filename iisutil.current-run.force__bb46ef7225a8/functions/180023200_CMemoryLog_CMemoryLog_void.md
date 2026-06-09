# CMemoryLog::~CMemoryLog(void)

- ea: `0x180023200`
- end: `0x18002324c`
- name: `??1CMemoryLog@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(CMemoryLog *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001edb0`

## callees

- `0x180002b60`
- `0x180023200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023231`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023231`

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
0x180023200  push    rbx
0x180023202  sub     rsp, 20h
0x180023206  cmp     dword ptr [rcx+78h], 0
0x18002320a  mov     rbx, rcx
0x18002320d  mov     qword ptr [rcx], 0
0x180023214  mov     qword ptr [rcx+8], 0
0x18002321c  mov     qword ptr [rcx+10h], 0
0x180023224  mov     dword ptr [rcx+48h], 0
0x18002322b  jz      short loc_18002323E
0x18002322d  add     rcx, 50h ; 'P'; lpCriticalSection
0x180023231  call    cs:__imp_DeleteCriticalSection
0x180023237  mov     dword ptr [rbx+78h], 0
0x18002323e  lea     rcx, [rbx+18h]; this
0x180023242  add     rsp, 20h
0x180023246  pop     rbx
0x180023247  jmp     ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```

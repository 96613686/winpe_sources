# CMemoryLog::~CMemoryLog(void)

- ea: `0x1800028a4`
- end: `0x180002906`
- name: `??1CMemoryLog@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CMemoryLog *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002788`

## callees

- `0x1800028a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800028d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800028d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800028fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800028fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800028ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800028ec`

## pseudocode

```c
void __fastcall CMemoryLog::~CMemoryLog(struct _RTL_CRITICAL_SECTION *this)
{
  bool v1; // zf
  HANDLE OwningThread; // rbx
  HANDLE ProcessHeap; // rax

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
  if ( BYTE4(this[1].LockSemaphore) )
  {
    OwningThread = this[1].OwningThread;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, OwningThread);
  }
}

```

## disassembly

```asm
0x1800028a4  push    rbx
0x1800028a6  sub     rsp, 20h
0x1800028aa  cmp     dword ptr [rcx+78h], 0
0x1800028ae  mov     rbx, rcx
0x1800028b1  mov     qword ptr [rcx], 0
0x1800028b8  mov     qword ptr [rcx+8], 0
0x1800028c0  mov     qword ptr [rcx+10h], 0
0x1800028c8  mov     dword ptr [rcx+48h], 0
0x1800028cf  jz      short loc_1800028E2
0x1800028d1  add     rcx, 50h ; 'P'; lpCriticalSection
0x1800028d5  call    cs:__imp_DeleteCriticalSection
0x1800028db  mov     dword ptr [rbx+78h], 0
0x1800028e2  cmp     byte ptr [rbx+44h], 0
0x1800028e6  jz      short loc_180002900
0x1800028e8  mov     rbx, [rbx+38h]
0x1800028ec  call    cs:__imp_GetProcessHeap
0x1800028f2  mov     r8, rbx; lpMem
0x1800028f5  xor     edx, edx; dwFlags
0x1800028f7  mov     rcx, rax; hHeap
0x1800028fa  call    cs:__imp_HeapFree
0x180002900  add     rsp, 20h
0x180002904  pop     rbx
0x180002905  retn
```

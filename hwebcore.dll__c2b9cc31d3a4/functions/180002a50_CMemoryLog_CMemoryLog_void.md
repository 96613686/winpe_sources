# CMemoryLog::~CMemoryLog(void)

- ea: `0x180002a50`
- end: `0x180002ac5`
- name: `??1CMemoryLog@@QEAA@XZ`
- size: `117`
- prototype: `void __fastcall(CMemoryLog *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000290c`

## callees

- `0x180002a50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002a81`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002a81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ab2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ab2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a9e`

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
0x180002a50  push    rbx
0x180002a52  sub     rsp, 20h
0x180002a56  cmp     dword ptr [rcx+78h], 0
0x180002a5a  mov     rbx, rcx
0x180002a5d  mov     qword ptr [rcx], 0
0x180002a64  mov     qword ptr [rcx+8], 0
0x180002a6c  mov     qword ptr [rcx+10h], 0
0x180002a74  mov     dword ptr [rcx+48h], 0
0x180002a7b  jz      short loc_180002A94
0x180002a7d  add     rcx, 50h ; 'P'; lpCriticalSection
0x180002a81  call    cs:__imp_DeleteCriticalSection
0x180002a88  nop     dword ptr [rax+rax+00h]
0x180002a8d  mov     dword ptr [rbx+78h], 0
0x180002a94  cmp     byte ptr [rbx+44h], 0
0x180002a98  jz      short loc_180002ABE
0x180002a9a  mov     rbx, [rbx+38h]
0x180002a9e  call    cs:__imp_GetProcessHeap
0x180002aa5  nop     dword ptr [rax+rax+00h]
0x180002aaa  mov     r8, rbx; lpMem
0x180002aad  xor     edx, edx; dwFlags
0x180002aaf  mov     rcx, rax; hHeap
0x180002ab2  call    cs:__imp_HeapFree
0x180002ab9  nop     dword ptr [rax+rax+00h]
0x180002abe  add     rsp, 20h
0x180002ac2  pop     rbx
0x180002ac3  retn
```

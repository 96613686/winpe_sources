# QUEUE::Enqueue(QUEUE_RECORD *)

- ea: `0x1800040c0`
- end: `0x18000412e`
- name: `?Enqueue@QUEUE@@QEAAXPEAVQUEUE_RECORD@@@Z`
- size: `110`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, struct QUEUE_RECORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800041dc`
- `0x180005568`

## callees

- `0x1800040c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004127`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800040d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800040d0`
- `iisutil!WriteRefTraceLog` at `0x1800040e8`
- `iisutil!WriteRefTraceLog` at `0x1800040e8`

## pseudocode

```c
void __fastcall QUEUE::Enqueue(struct _RTL_CRITICAL_SECTION *this, struct QUEUE_RECORD *a2)
{
  HANDLE LockSemaphore; // rcx
  QUEUE **v5; // rdx

  EnterCriticalSection(this);
  LockSemaphore = this[1].LockSemaphore;
  ++LODWORD(this[1].OwningThread);
  if ( LockSemaphore )
    WriteRefTraceLog(LockSemaphore, LODWORD(this[1].OwningThread), this);
  v5 = *(QUEUE ***)&this[1].LockCount;
  if ( *v5 != (QUEUE *)&this[1] )
    __fastfail(3u);
  *((_QWORD *)a2 + 1) = this + 1;
  *((_QWORD *)a2 + 2) = v5;
  *v5 = (struct QUEUE_RECORD *)((char *)a2 + 8);
  *(_QWORD *)&this[1].LockCount = (char *)a2 + 8;
  HIDWORD(this[1].OwningThread) += *((_DWORD *)a2 + 6);
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x1800040c0  mov     [rsp+arg_0], rbx
0x1800040c5  push    rdi
0x1800040c6  sub     rsp, 20h
0x1800040ca  mov     rdi, rdx
0x1800040cd  mov     rbx, rcx
0x1800040d0  call    cs:__imp_EnterCriticalSection
0x1800040d6  mov     rcx, [rbx+40h]
0x1800040da  inc     dword ptr [rbx+38h]
0x1800040dd  test    rcx, rcx
0x1800040e0  jz      short loc_1800040EE
0x1800040e2  mov     edx, [rbx+38h]
0x1800040e5  mov     r8, rbx
0x1800040e8  call    cs:__imp_WriteRefTraceLog
0x1800040ee  lea     rcx, [rbx+28h]
0x1800040f2  mov     rdx, [rcx+8]
0x1800040f6  cmp     [rdx], rcx
0x1800040f9  jz      short loc_180004102
0x1800040fb  mov     ecx, 3
0x180004100  int     29h; Win8: RtlFailFast(ecx)
0x180004102  lea     rax, [rdi+8]
0x180004106  mov     [rax], rcx
0x180004109  mov     [rax+8], rdx
0x18000410d  mov     [rdx], rax
0x180004110  mov     [rcx+8], rax
0x180004114  mov     rcx, rbx
0x180004117  mov     eax, [rdi+18h]
0x18000411a  add     [rbx+3Ch], eax
0x18000411d  mov     rbx, [rsp+28h+arg_0]
0x180004122  add     rsp, 20h
0x180004126  pop     rdi
0x180004127  jmp     cs:__imp_LeaveCriticalSection
```

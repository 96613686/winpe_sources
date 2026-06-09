# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140009b30`
- end: `0x140009b78`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `72`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140013f24`

## callees

- `0x140009b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140009b5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009b62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009b62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009b70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009b70`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rdi
  HANDLE ProcessHeap; // rax

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, LockSemaphore);
  }
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x140009b30  mov     [rsp+arg_0], rbx
0x140009b35  push    rdi
0x140009b36  sub     rsp, 20h
0x140009b3a  mov     rdi, [rcx+40h]
0x140009b3e  mov     rbx, rcx
0x140009b41  mov     qword ptr [rcx+40h], 0
0x140009b49  test    rdi, rdi
0x140009b4c  jnz     short loc_140009B62
0x140009b4e  mov     rcx, rbx
0x140009b51  mov     rbx, [rsp+28h+arg_0]
0x140009b56  add     rsp, 20h
0x140009b5a  pop     rdi
0x140009b5b  jmp     cs:__imp_DeleteCriticalSection
0x140009b62  call    cs:__imp_GetProcessHeap
0x140009b68  mov     r8, rdi; lpMem
0x140009b6b  xor     edx, edx; dwFlags
0x140009b6d  mov     rcx, rax; hHeap
0x140009b70  call    cs:__imp_HeapFree
0x140009b76  jmp     short loc_140009B4E
```

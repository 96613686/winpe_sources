# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180016290`
- end: `0x180016306`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `118`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800188f0`

## callees

- `0x180016290`
- `0x18001651c`
- `0x180017860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800162e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800162e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162d3`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::~FeatureStateData(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rsi
  HANDLE ProcessHeap; // rax

  wil::details_abi::FeatureStateData::ProcessShutdown((wil::details_abi::FeatureStateData *)this);
  LockSemaphore = this[6].LockSemaphore;
  this[6].LockSemaphore = 0;
  if ( LockSemaphore )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, LockSemaphore);
  }
  DeleteCriticalSection(this + 5);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)&this->LockCount);
}

```

## disassembly

```asm
0x180016290  mov     [rsp+arg_0], rbx
0x180016295  mov     [rsp+arg_8], rsi
0x18001629a  push    rdi
0x18001629b  sub     rsp, 20h
0x18001629f  mov     rbx, rcx
0x1800162a2  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x1800162a7  lea     rdi, [rbx+0C8h]
0x1800162ae  mov     rsi, [rdi+40h]
0x1800162b2  mov     qword ptr [rdi+40h], 0
0x1800162ba  test    rsi, rsi
0x1800162bd  jz      short loc_1800162DF
0x1800162bf  call    cs:__imp_GetProcessHeap
0x1800162c6  nop     dword ptr [rax+rax+00h]
0x1800162cb  mov     rcx, rax; hHeap
0x1800162ce  mov     r8, rsi; lpMem
0x1800162d1  xor     edx, edx; dwFlags
0x1800162d3  call    cs:__imp_HeapFree
0x1800162da  nop     dword ptr [rax+rax+00h]
0x1800162df  mov     rcx, rdi; lpCriticalSection
0x1800162e2  call    cs:__imp_DeleteCriticalSection
0x1800162e9  nop     dword ptr [rax+rax+00h]
0x1800162ee  lea     rcx, [rbx+8]; this
0x1800162f2  mov     rbx, [rsp+28h+arg_0]
0x1800162f7  mov     rsi, [rsp+28h+arg_8]
0x1800162fc  add     rsp, 20h
0x180016300  pop     rdi
0x180016301  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

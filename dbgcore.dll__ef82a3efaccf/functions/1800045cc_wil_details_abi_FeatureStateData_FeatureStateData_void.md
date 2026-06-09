# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800045cc`
- end: `0x18000463a`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004208`

## callees

- `0x1800045cc`
- `0x1800049e8`
- `0x180008c44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000461c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000461c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004605`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004605`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004613`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004613`

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
0x1800045cc  push    rdi
0x1800045ce  sub     rsp, 30h
0x1800045d2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800045db  mov     [rsp+38h+arg_0], rbx
0x1800045e0  mov     [rsp+38h+arg_8], rsi
0x1800045e5  mov     rbx, rcx
0x1800045e8  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x1800045ed  lea     rdi, [rbx+0C8h]
0x1800045f4  mov     rsi, [rdi+40h]
0x1800045f8  mov     qword ptr [rdi+40h], 0
0x180004600  test    rsi, rsi
0x180004603  jz      short loc_180004619
0x180004605  call    cs:__imp_GetProcessHeap
0x18000460b  mov     rcx, rax; hHeap
0x18000460e  mov     r8, rsi; lpMem
0x180004611  xor     edx, edx; dwFlags
0x180004613  call    cs:__imp_HeapFree
0x180004619  mov     rcx, rdi; lpCriticalSection
0x18000461c  call    cs:__imp_DeleteCriticalSection
0x180004622  lea     rcx, [rbx+8]; this
0x180004626  mov     rbx, [rsp+38h+arg_0]
0x18000462b  mov     rsi, [rsp+38h+arg_8]
0x180004630  add     rsp, 30h
0x180004634  pop     rdi
0x180004635  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800077fc`
- end: `0x1800078cc`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000751c`

## callees

- `0x1800073e8`
- `0x1800077fc`
- `0x180007b7c`
- `0x18000f358`
- `0x18001164c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800078a9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800078a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000789c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000789c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000788e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000788e`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::~FeatureStateData(wil::details_abi::FeatureStateData *this)
{
  void *v2; // rsi
  HANDLE ProcessHeap; // rax
  _BYTE v4[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v5[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v6[64]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v4);
  if ( *((_BYTE *)this + 64) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v4,
      (wil::details_abi::FeatureStateData *)((char *)this + 8));
  if ( *((_BYTE *)this + 128) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v5,
      (wil::details_abi::FeatureStateData *)((char *)this + 72));
  if ( *((_BYTE *)this + 192) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v6,
      (wil::details_abi::FeatureStateData *)((char *)this + 136));
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v4);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v4);
  v2 = (void *)*((_QWORD *)this + 33);
  *((_QWORD *)this + 33) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::FeatureStateData *)((char *)this + 8));
}

```

## disassembly

```asm
0x1800077fc  mov     [rsp+arg_0], rbx
0x180007801  mov     [rsp+arg_8], rsi
0x180007806  push    rdi
0x180007807  sub     rsp, 0E0h
0x18000780e  mov     rbx, rcx
0x180007811  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007816  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000781b  cmp     byte ptr [rbx+40h], 0
0x18000781f  jz      short loc_18000782F
0x180007821  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180007825  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000782a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000782f  cmp     byte ptr [rbx+80h], 0
0x180007836  jz      short loc_180007846
0x180007838  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000783c  lea     rcx, [rsp+0E8h+var_88]; this
0x180007841  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180007846  cmp     byte ptr [rbx+0C0h], 0
0x18000784d  jz      short loc_180007863
0x18000784f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180007856  lea     rcx, [rsp+0E8h+var_48]; this
0x18000785e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180007863  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007868  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000786d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007872  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180007877  mov     rsi, [rbx+108h]
0x18000787e  mov     qword ptr [rbx+108h], 0
0x180007889  test    rsi, rsi
0x18000788c  jz      short loc_1800078A2
0x18000788e  call    cs:__imp_GetProcessHeap
0x180007894  mov     rcx, rax; hHeap
0x180007897  mov     r8, rsi; lpMem
0x18000789a  xor     edx, edx; dwFlags
0x18000789c  call    cs:__imp_HeapFree
0x1800078a2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800078a9  call    cs:__imp_DeleteCriticalSection
0x1800078af  lea     rcx, [rbx+8]; this
0x1800078b3  lea     r11, [rsp+0E8h+var_8]
0x1800078bb  mov     rbx, [r11+10h]
0x1800078bf  mov     rsi, [r11+18h]
0x1800078c3  mov     rsp, r11
0x1800078c6  pop     rdi
0x1800078c7  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

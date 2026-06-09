# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800036a4`
- end: `0x180003774`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003464`

## callees

- `0x1800032d0`
- `0x1800036a4`
- `0x1800039f4`
- `0x180006918`
- `0x1800082f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003744`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003744`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003736`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003736`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003751`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003751`

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
0x1800036a4  mov     [rsp+arg_0], rbx
0x1800036a9  mov     [rsp+arg_8], rsi
0x1800036ae  push    rdi
0x1800036af  sub     rsp, 0E0h
0x1800036b6  mov     rbx, rcx
0x1800036b9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800036be  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800036c3  cmp     byte ptr [rbx+40h], 0
0x1800036c7  jz      short loc_1800036D7
0x1800036c9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800036cd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800036d2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800036d7  cmp     byte ptr [rbx+80h], 0
0x1800036de  jz      short loc_1800036EE
0x1800036e0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800036e4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800036e9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800036ee  cmp     byte ptr [rbx+0C0h], 0
0x1800036f5  jz      short loc_18000370B
0x1800036f7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800036fe  lea     rcx, [rsp+0E8h+var_48]; this
0x180003706  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000370b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003710  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003715  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000371a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000371f  mov     rsi, [rbx+108h]
0x180003726  mov     qword ptr [rbx+108h], 0
0x180003731  test    rsi, rsi
0x180003734  jz      short loc_18000374A
0x180003736  call    cs:__imp_GetProcessHeap
0x18000373c  mov     r8, rsi; lpMem
0x18000373f  xor     edx, edx; dwFlags
0x180003741  mov     rcx, rax; hHeap
0x180003744  call    cs:__imp_HeapFree
0x18000374a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003751  call    cs:__imp_DeleteCriticalSection
0x180003757  lea     rcx, [rbx+8]; this
0x18000375b  lea     r11, [rsp+0E8h+var_8]
0x180003763  mov     rbx, [r11+10h]
0x180003767  mov     rsi, [r11+18h]
0x18000376b  mov     rsp, r11
0x18000376e  pop     rdi
0x18000376f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

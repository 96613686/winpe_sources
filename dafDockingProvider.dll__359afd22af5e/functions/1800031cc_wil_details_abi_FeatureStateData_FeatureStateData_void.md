# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800031cc`
- end: `0x18000329c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800030b4`

## callees

- `0x180002f20`
- `0x1800031cc`
- `0x180003638`
- `0x180005afc`
- `0x180007618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003279`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003279`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000326c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000326c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000325e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000325e`

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
0x1800031cc  mov     [rsp+arg_0], rbx
0x1800031d1  mov     [rsp+arg_8], rsi
0x1800031d6  push    rdi
0x1800031d7  sub     rsp, 0E0h
0x1800031de  mov     rbx, rcx
0x1800031e1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800031e6  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800031eb  cmp     byte ptr [rbx+40h], 0
0x1800031ef  jz      short loc_1800031FF
0x1800031f1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800031f5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800031fa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800031ff  cmp     byte ptr [rbx+80h], 0
0x180003206  jz      short loc_180003216
0x180003208  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000320c  lea     rcx, [rsp+0E8h+var_88]; this
0x180003211  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003216  cmp     byte ptr [rbx+0C0h], 0
0x18000321d  jz      short loc_180003233
0x18000321f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003226  lea     rcx, [rsp+0E8h+var_48]; this
0x18000322e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003233  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003238  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000323d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003242  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003247  mov     rsi, [rbx+108h]
0x18000324e  mov     qword ptr [rbx+108h], 0
0x180003259  test    rsi, rsi
0x18000325c  jz      short loc_180003272
0x18000325e  call    cs:__imp_GetProcessHeap
0x180003264  mov     rcx, rax; hHeap
0x180003267  mov     r8, rsi; lpMem
0x18000326a  xor     edx, edx; dwFlags
0x18000326c  call    cs:__imp_HeapFree
0x180003272  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003279  call    cs:__imp_DeleteCriticalSection
0x18000327f  lea     rcx, [rbx+8]; this
0x180003283  lea     r11, [rsp+0E8h+var_8]
0x18000328b  mov     rbx, [r11+10h]
0x18000328f  mov     rsi, [r11+18h]
0x180003293  mov     rsp, r11
0x180003296  pop     rdi
0x180003297  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

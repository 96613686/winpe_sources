# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003448`
- end: `0x180003518`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800031d0`

## callees

- `0x180003004`
- `0x180003448`
- `0x1800038bc`
- `0x1800064a8`
- `0x1800084f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034da`

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
0x180003448  mov     [rsp+arg_0], rbx
0x18000344d  mov     [rsp+arg_8], rsi
0x180003452  push    rdi
0x180003453  sub     rsp, 0E0h
0x18000345a  mov     rbx, rcx
0x18000345d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003462  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003467  cmp     byte ptr [rbx+40h], 0
0x18000346b  jz      short loc_18000347B
0x18000346d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003471  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003476  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000347b  cmp     byte ptr [rbx+80h], 0
0x180003482  jz      short loc_180003492
0x180003484  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003488  lea     rcx, [rsp+0E8h+var_88]; this
0x18000348d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003492  cmp     byte ptr [rbx+0C0h], 0
0x180003499  jz      short loc_1800034AF
0x18000349b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800034a2  lea     rcx, [rsp+0E8h+var_48]; this
0x1800034aa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800034af  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800034b4  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800034b9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800034be  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800034c3  mov     rsi, [rbx+108h]
0x1800034ca  mov     qword ptr [rbx+108h], 0
0x1800034d5  test    rsi, rsi
0x1800034d8  jz      short loc_1800034EE
0x1800034da  call    cs:__imp_GetProcessHeap
0x1800034e0  mov     rcx, rax; hHeap
0x1800034e3  mov     r8, rsi; lpMem
0x1800034e6  xor     edx, edx; dwFlags
0x1800034e8  call    cs:__imp_HeapFree
0x1800034ee  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800034f5  call    cs:__imp_DeleteCriticalSection
0x1800034fb  lea     rcx, [rbx+8]; this
0x1800034ff  lea     r11, [rsp+0E8h+var_8]
0x180003507  mov     rbx, [r11+10h]
0x18000350b  mov     rsi, [r11+18h]
0x18000350f  mov     rsp, r11
0x180003512  pop     rdi
0x180003513  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

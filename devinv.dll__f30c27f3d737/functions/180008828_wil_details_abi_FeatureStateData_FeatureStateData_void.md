# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180008828`
- end: `0x1800088f8`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008570`

## callees

- `0x1800083a4`
- `0x180008828`
- `0x180008c9c`
- `0x18000bcbc`
- `0x18000e0e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800088d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800088d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088ba`

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
0x180008828  mov     [rsp+arg_0], rbx
0x18000882d  mov     [rsp+arg_8], rsi
0x180008832  push    rdi
0x180008833  sub     rsp, 0E0h
0x18000883a  mov     rbx, rcx
0x18000883d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008842  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008847  cmp     byte ptr [rbx+40h], 0
0x18000884b  jz      short loc_18000885B
0x18000884d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008851  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008856  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000885b  cmp     byte ptr [rbx+80h], 0
0x180008862  jz      short loc_180008872
0x180008864  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180008868  lea     rcx, [rsp+0E8h+var_88]; this
0x18000886d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008872  cmp     byte ptr [rbx+0C0h], 0
0x180008879  jz      short loc_18000888F
0x18000887b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180008882  lea     rcx, [rsp+0E8h+var_48]; this
0x18000888a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000888f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008894  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180008899  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000889e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800088a3  mov     rsi, [rbx+108h]
0x1800088aa  mov     qword ptr [rbx+108h], 0
0x1800088b5  test    rsi, rsi
0x1800088b8  jz      short loc_1800088CE
0x1800088ba  call    cs:__imp_GetProcessHeap
0x1800088c0  mov     rcx, rax; hHeap
0x1800088c3  mov     r8, rsi; lpMem
0x1800088c6  xor     edx, edx; dwFlags
0x1800088c8  call    cs:__imp_HeapFree
0x1800088ce  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800088d5  call    cs:__imp_DeleteCriticalSection
0x1800088db  lea     rcx, [rbx+8]; this
0x1800088df  lea     r11, [rsp+0E8h+var_8]
0x1800088e7  mov     rbx, [r11+10h]
0x1800088eb  mov     rsi, [r11+18h]
0x1800088ef  mov     rsp, r11
0x1800088f2  pop     rdi
0x1800088f3  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

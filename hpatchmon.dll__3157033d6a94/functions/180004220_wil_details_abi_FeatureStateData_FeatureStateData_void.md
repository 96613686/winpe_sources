# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180004220`
- end: `0x1800042f0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003f60`

## callees

- `0x180003d94`
- `0x180004220`
- `0x180004694`
- `0x18000841c`
- `0x18000bbd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800042cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800042cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800042c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800042c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800042b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800042b2`

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
0x180004220  mov     [rsp+arg_0], rbx
0x180004225  mov     [rsp+arg_8], rsi
0x18000422a  push    rdi
0x18000422b  sub     rsp, 0E0h
0x180004232  mov     rbx, rcx
0x180004235  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000423a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000423f  cmp     byte ptr [rbx+40h], 0
0x180004243  jz      short loc_180004253
0x180004245  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180004249  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000424e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004253  cmp     byte ptr [rbx+80h], 0
0x18000425a  jz      short loc_18000426A
0x18000425c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180004260  lea     rcx, [rsp+0E8h+var_88]; this
0x180004265  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000426a  cmp     byte ptr [rbx+0C0h], 0
0x180004271  jz      short loc_180004287
0x180004273  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000427a  lea     rcx, [rsp+0E8h+var_48]; this
0x180004282  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004287  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000428c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180004291  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004296  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000429b  mov     rsi, [rbx+108h]
0x1800042a2  mov     qword ptr [rbx+108h], 0
0x1800042ad  test    rsi, rsi
0x1800042b0  jz      short loc_1800042C6
0x1800042b2  call    cs:__imp_GetProcessHeap
0x1800042b8  mov     rcx, rax; hHeap
0x1800042bb  mov     r8, rsi; lpMem
0x1800042be  xor     edx, edx; dwFlags
0x1800042c0  call    cs:__imp_HeapFree
0x1800042c6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800042cd  call    cs:__imp_DeleteCriticalSection
0x1800042d3  lea     rcx, [rbx+8]; this
0x1800042d7  lea     r11, [rsp+0E8h+var_8]
0x1800042df  mov     rbx, [r11+10h]
0x1800042e3  mov     rsi, [r11+18h]
0x1800042e7  mov     rsp, r11
0x1800042ea  pop     rdi
0x1800042eb  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

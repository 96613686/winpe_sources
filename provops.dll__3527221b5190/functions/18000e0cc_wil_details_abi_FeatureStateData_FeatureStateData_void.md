# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000e0cc`
- end: `0x18000e19c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015d6c`

## callees

- `0x18000d034`
- `0x18000e0cc`
- `0x18000e700`
- `0x180014f28`
- `0x18001b2c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e179`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e179`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e16c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e16c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e15e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e15e`

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
0x18000e0cc  mov     [rsp+arg_0], rbx
0x18000e0d1  mov     [rsp+arg_8], rsi
0x18000e0d6  push    rdi
0x18000e0d7  sub     rsp, 0E0h
0x18000e0de  mov     rbx, rcx
0x18000e0e1  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000e0e6  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000e0eb  cmp     byte ptr [rbx+40h], 0
0x18000e0ef  jz      short loc_18000E0FF
0x18000e0f1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000e0f5  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000e0fa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000e0ff  cmp     byte ptr [rbx+80h], 0
0x18000e106  jz      short loc_18000E116
0x18000e108  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000e10c  lea     rcx, [rsp+0E8h+var_88]; this
0x18000e111  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000e116  cmp     byte ptr [rbx+0C0h], 0
0x18000e11d  jz      short loc_18000E133
0x18000e11f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000e126  lea     rcx, [rsp+0E8h+var_48]; this
0x18000e12e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000e133  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000e138  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000e13d  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000e142  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000e147  mov     rsi, [rbx+108h]
0x18000e14e  mov     qword ptr [rbx+108h], 0
0x18000e159  test    rsi, rsi
0x18000e15c  jz      short loc_18000E172
0x18000e15e  call    cs:__imp_GetProcessHeap
0x18000e164  mov     rcx, rax; hHeap
0x18000e167  mov     r8, rsi; lpMem
0x18000e16a  xor     edx, edx; dwFlags
0x18000e16c  call    cs:__imp_HeapFree
0x18000e172  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000e179  call    cs:__imp_DeleteCriticalSection
0x18000e17f  lea     rcx, [rbx+8]; this
0x18000e183  lea     r11, [rsp+0E8h+var_8]
0x18000e18b  mov     rbx, [r11+10h]
0x18000e18f  mov     rsi, [r11+18h]
0x18000e193  mov     rsp, r11
0x18000e196  pop     rdi
0x18000e197  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

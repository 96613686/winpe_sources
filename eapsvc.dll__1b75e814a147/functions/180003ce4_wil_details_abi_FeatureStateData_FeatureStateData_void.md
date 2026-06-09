# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003ce4`
- end: `0x180003db4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003990`

## callees

- `0x1800037c4`
- `0x180003ce4`
- `0x180004158`
- `0x180006c6c`
- `0x1800090a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003d91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003d91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d76`

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
0x180003ce4  mov     [rsp+arg_0], rbx
0x180003ce9  mov     [rsp+arg_8], rsi
0x180003cee  push    rdi
0x180003cef  sub     rsp, 0E0h
0x180003cf6  mov     rbx, rcx
0x180003cf9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003cfe  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003d03  cmp     byte ptr [rbx+40h], 0
0x180003d07  jz      short loc_180003D17
0x180003d09  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003d0d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003d12  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003d17  cmp     byte ptr [rbx+80h], 0
0x180003d1e  jz      short loc_180003D2E
0x180003d20  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003d24  lea     rcx, [rsp+0E8h+var_88]; this
0x180003d29  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003d2e  cmp     byte ptr [rbx+0C0h], 0
0x180003d35  jz      short loc_180003D4B
0x180003d37  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003d3e  lea     rcx, [rsp+0E8h+var_48]; this
0x180003d46  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003d4b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003d50  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003d55  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003d5a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003d5f  mov     rsi, [rbx+108h]
0x180003d66  mov     qword ptr [rbx+108h], 0
0x180003d71  test    rsi, rsi
0x180003d74  jz      short loc_180003D8A
0x180003d76  call    cs:__imp_GetProcessHeap
0x180003d7c  mov     rcx, rax; hHeap
0x180003d7f  mov     r8, rsi; lpMem
0x180003d82  xor     edx, edx; dwFlags
0x180003d84  call    cs:__imp_HeapFree
0x180003d8a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003d91  call    cs:__imp_DeleteCriticalSection
0x180003d97  lea     rcx, [rbx+8]; this
0x180003d9b  lea     r11, [rsp+0E8h+var_8]
0x180003da3  mov     rbx, [r11+10h]
0x180003da7  mov     rsi, [r11+18h]
0x180003dab  mov     rsp, r11
0x180003dae  pop     rdi
0x180003daf  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

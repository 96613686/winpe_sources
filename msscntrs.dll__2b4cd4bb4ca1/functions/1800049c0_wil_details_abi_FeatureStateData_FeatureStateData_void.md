# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800049c0`
- end: `0x180004a90`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004674`

## callees

- `0x18000432c`
- `0x1800049c0`
- `0x180004e34`
- `0x1800077f4`
- `0x1800099f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004a6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004a6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a60`

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
0x1800049c0  mov     [rsp+arg_0], rbx
0x1800049c5  mov     [rsp+arg_8], rsi
0x1800049ca  push    rdi
0x1800049cb  sub     rsp, 0E0h
0x1800049d2  mov     rbx, rcx
0x1800049d5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800049da  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800049df  cmp     byte ptr [rbx+40h], 0
0x1800049e3  jz      short loc_1800049F3
0x1800049e5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800049e9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800049ee  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800049f3  cmp     byte ptr [rbx+80h], 0
0x1800049fa  jz      short loc_180004A0A
0x1800049fc  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180004a00  lea     rcx, [rsp+0E8h+var_88]; this
0x180004a05  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004a0a  cmp     byte ptr [rbx+0C0h], 0
0x180004a11  jz      short loc_180004A27
0x180004a13  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180004a1a  lea     rcx, [rsp+0E8h+var_48]; this
0x180004a22  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004a27  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004a2c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180004a31  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004a36  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180004a3b  mov     rsi, [rbx+108h]
0x180004a42  mov     qword ptr [rbx+108h], 0
0x180004a4d  test    rsi, rsi
0x180004a50  jz      short loc_180004A66
0x180004a52  call    cs:__imp_GetProcessHeap
0x180004a58  mov     rcx, rax; hHeap
0x180004a5b  mov     r8, rsi; lpMem
0x180004a5e  xor     edx, edx; dwFlags
0x180004a60  call    cs:__imp_HeapFree
0x180004a66  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180004a6d  call    cs:__imp_DeleteCriticalSection
0x180004a73  lea     rcx, [rbx+8]; this
0x180004a77  lea     r11, [rsp+0E8h+var_8]
0x180004a7f  mov     rbx, [r11+10h]
0x180004a83  mov     rsi, [r11+18h]
0x180004a87  mov     rsp, r11
0x180004a8a  pop     rdi
0x180004a8b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

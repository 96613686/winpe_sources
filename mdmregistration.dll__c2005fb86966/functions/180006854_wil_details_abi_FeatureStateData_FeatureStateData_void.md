# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180006854`
- end: `0x180006936`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000acbc`

## callees

- `0x180006410`
- `0x180006854`
- `0x180006d54`
- `0x180009ca8`
- `0x18000c1b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000690d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000690d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068e6`

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
0x180006854  mov     [rsp+arg_0], rbx
0x180006859  mov     [rsp+arg_8], rsi
0x18000685e  push    rdi
0x18000685f  sub     rsp, 0E0h
0x180006866  mov     rbx, rcx
0x180006869  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000686e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006873  cmp     byte ptr [rbx+40h], 0
0x180006877  jz      short loc_180006887
0x180006879  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000687d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006882  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006887  cmp     byte ptr [rbx+80h], 0
0x18000688e  jz      short loc_18000689E
0x180006890  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180006894  lea     rcx, [rsp+0E8h+var_88]; this
0x180006899  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000689e  cmp     byte ptr [rbx+0C0h], 0
0x1800068a5  jz      short loc_1800068BB
0x1800068a7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800068ae  lea     rcx, [rsp+0E8h+var_48]; this
0x1800068b6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800068bb  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800068c0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800068c5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800068ca  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800068cf  mov     rsi, [rbx+108h]
0x1800068d6  mov     qword ptr [rbx+108h], 0
0x1800068e1  test    rsi, rsi
0x1800068e4  jz      short loc_180006906
0x1800068e6  call    cs:__imp_GetProcessHeap
0x1800068ed  nop     dword ptr [rax+rax+00h]
0x1800068f2  mov     rcx, rax; hHeap
0x1800068f5  mov     r8, rsi; lpMem
0x1800068f8  xor     edx, edx; dwFlags
0x1800068fa  call    cs:__imp_HeapFree
0x180006901  nop     dword ptr [rax+rax+00h]
0x180006906  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000690d  call    cs:__imp_DeleteCriticalSection
0x180006914  nop     dword ptr [rax+rax+00h]
0x180006919  lea     rcx, [rbx+8]; this
0x18000691d  lea     r11, [rsp+0E8h+var_8]
0x180006925  mov     rbx, [r11+10h]
0x180006929  mov     rsi, [r11+18h]
0x18000692d  mov     rsp, r11
0x180006930  pop     rdi
0x180006931  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

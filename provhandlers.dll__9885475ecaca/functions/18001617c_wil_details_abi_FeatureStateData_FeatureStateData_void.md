# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18001617c`
- end: `0x18001624c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015e24`

## callees

- `0x180015d5c`
- `0x18001617c`
- `0x180016494`
- `0x180022cb8`
- `0x1800242b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016229`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016229`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001620e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001620e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001621c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001621c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001617c  mov     [rsp+arg_0], rbx
0x180016181  mov     [rsp+arg_8], rsi
0x180016186  push    rdi
0x180016187  sub     rsp, 0E0h
0x18001618e  mov     rbx, rcx
0x180016191  lea     rcx, [rsp+0E8h+var_C8]; this
0x180016196  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001619b  cmp     byte ptr [rbx+40h], 0
0x18001619f  jz      short loc_1800161AF
0x1800161a1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800161a5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800161aa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800161af  cmp     byte ptr [rbx+80h], 0
0x1800161b6  jz      short loc_1800161C6
0x1800161b8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800161bc  lea     rcx, [rsp+0E8h+var_88]; this
0x1800161c1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800161c6  cmp     byte ptr [rbx+0C0h], 0
0x1800161cd  jz      short loc_1800161E3
0x1800161cf  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800161d6  lea     rcx, [rsp+0E8h+var_48]; this
0x1800161de  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800161e3  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800161e8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800161ed  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800161f2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800161f7  mov     rsi, [rbx+108h]
0x1800161fe  mov     qword ptr [rbx+108h], 0
0x180016209  test    rsi, rsi
0x18001620c  jz      short loc_180016222
0x18001620e  call    cs:__imp_GetProcessHeap
0x180016214  mov     rcx, rax; hHeap
0x180016217  mov     r8, rsi; lpMem
0x18001621a  xor     edx, edx; dwFlags
0x18001621c  call    cs:__imp_HeapFree
0x180016222  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180016229  call    cs:__imp_DeleteCriticalSection
0x18001622f  lea     rcx, [rbx+8]; this
0x180016233  lea     r11, [rsp+0E8h+var_8]
0x18001623b  mov     rbx, [r11+10h]
0x18001623f  mov     rsi, [r11+18h]
0x180016243  mov     rsp, r11
0x180016246  pop     rdi
0x180016247  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000785c`
- end: `0x18000792c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000757c`

## callees

- `0x1800073b0`
- `0x18000785c`
- `0x180007cd0`
- `0x18000a770`
- `0x18000c9a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800078fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800078fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800078ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800078ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007909`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007909`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18000785c  mov     [rsp+arg_0], rbx
0x180007861  mov     [rsp+arg_8], rsi
0x180007866  push    rdi
0x180007867  sub     rsp, 0E0h
0x18000786e  mov     rbx, rcx
0x180007871  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007876  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000787b  cmp     byte ptr [rbx+40h], 0
0x18000787f  jz      short loc_18000788F
0x180007881  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180007885  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000788a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000788f  cmp     byte ptr [rbx+80h], 0
0x180007896  jz      short loc_1800078A6
0x180007898  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000789c  lea     rcx, [rsp+0E8h+var_88]; this
0x1800078a1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800078a6  cmp     byte ptr [rbx+0C0h], 0
0x1800078ad  jz      short loc_1800078C3
0x1800078af  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800078b6  lea     rcx, [rsp+0E8h+var_48]; this
0x1800078be  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800078c3  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800078c8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800078cd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800078d2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800078d7  mov     rsi, [rbx+108h]
0x1800078de  mov     qword ptr [rbx+108h], 0
0x1800078e9  test    rsi, rsi
0x1800078ec  jz      short loc_180007902
0x1800078ee  call    cs:__imp_GetProcessHeap
0x1800078f4  mov     rcx, rax; hHeap
0x1800078f7  mov     r8, rsi; lpMem
0x1800078fa  xor     edx, edx; dwFlags
0x1800078fc  call    cs:__imp_HeapFree
0x180007902  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180007909  call    cs:__imp_DeleteCriticalSection
0x18000790f  lea     rcx, [rbx+8]; this
0x180007913  lea     r11, [rsp+0E8h+var_8]
0x18000791b  mov     rbx, [r11+10h]
0x18000791f  mov     rsi, [r11+18h]
0x180007923  mov     rsp, r11
0x180007926  pop     rdi
0x180007927  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

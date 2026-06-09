# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180011e10`
- end: `0x180011ee0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011bd8`

## callees

- `0x180011b10`
- `0x180011e10`
- `0x1800120dc`
- `0x180017e34`
- `0x18001bf8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011ebd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011ebd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ea2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ea2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011eb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011eb0`

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
0x180011e10  mov     [rsp+arg_0], rbx
0x180011e15  mov     [rsp+arg_8], rsi
0x180011e1a  push    rdi
0x180011e1b  sub     rsp, 0E0h
0x180011e22  mov     rbx, rcx
0x180011e25  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011e2a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180011e2f  cmp     byte ptr [rbx+40h], 0
0x180011e33  jz      short loc_180011E43
0x180011e35  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180011e39  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011e3e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180011e43  cmp     byte ptr [rbx+80h], 0
0x180011e4a  jz      short loc_180011E5A
0x180011e4c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180011e50  lea     rcx, [rsp+0E8h+var_88]; this
0x180011e55  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180011e5a  cmp     byte ptr [rbx+0C0h], 0
0x180011e61  jz      short loc_180011E77
0x180011e63  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180011e6a  lea     rcx, [rsp+0E8h+var_48]; this
0x180011e72  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180011e77  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011e7c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180011e81  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011e86  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180011e8b  mov     rsi, [rbx+108h]
0x180011e92  mov     qword ptr [rbx+108h], 0
0x180011e9d  test    rsi, rsi
0x180011ea0  jz      short loc_180011EB6
0x180011ea2  call    cs:__imp_GetProcessHeap
0x180011ea8  mov     r8, rsi; lpMem
0x180011eab  xor     edx, edx; dwFlags
0x180011ead  mov     rcx, rax; hHeap
0x180011eb0  call    cs:__imp_HeapFree
0x180011eb6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180011ebd  call    cs:__imp_DeleteCriticalSection
0x180011ec3  lea     rcx, [rbx+8]; this
0x180011ec7  lea     r11, [rsp+0E8h+var_8]
0x180011ecf  mov     rbx, [r11+10h]
0x180011ed3  mov     rsi, [r11+18h]
0x180011ed7  mov     rsp, r11
0x180011eda  pop     rdi
0x180011edb  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

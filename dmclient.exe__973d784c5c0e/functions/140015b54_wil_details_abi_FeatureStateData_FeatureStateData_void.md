# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140015b54`
- end: `0x140015c36`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140017c4c`

## callees

- `0x140015a64`
- `0x140015b54`
- `0x140015e4c`
- `0x140016fe4`
- `0x14001822c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015c0d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015c0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015be6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015be6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015bfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015bfa`

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
0x140015b54  mov     [rsp+arg_0], rbx
0x140015b59  mov     [rsp+arg_8], rsi
0x140015b5e  push    rdi
0x140015b5f  sub     rsp, 0E0h
0x140015b66  mov     rbx, rcx
0x140015b69  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015b6e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140015b73  cmp     byte ptr [rbx+40h], 0
0x140015b77  jz      short loc_140015B87
0x140015b79  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140015b7d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015b82  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140015b87  cmp     byte ptr [rbx+80h], 0
0x140015b8e  jz      short loc_140015B9E
0x140015b90  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140015b94  lea     rcx, [rsp+0E8h+var_88]; this
0x140015b99  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140015b9e  cmp     byte ptr [rbx+0C0h], 0
0x140015ba5  jz      short loc_140015BBB
0x140015ba7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140015bae  lea     rcx, [rsp+0E8h+var_48]; this
0x140015bb6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140015bbb  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015bc0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140015bc5  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015bca  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140015bcf  mov     rsi, [rbx+108h]
0x140015bd6  mov     qword ptr [rbx+108h], 0
0x140015be1  test    rsi, rsi
0x140015be4  jz      short loc_140015C06
0x140015be6  call    cs:__imp_GetProcessHeap
0x140015bed  nop     dword ptr [rax+rax+00h]
0x140015bf2  mov     rcx, rax; hHeap
0x140015bf5  mov     r8, rsi; lpMem
0x140015bf8  xor     edx, edx; dwFlags
0x140015bfa  call    cs:__imp_HeapFree
0x140015c01  nop     dword ptr [rax+rax+00h]
0x140015c06  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140015c0d  call    cs:__imp_DeleteCriticalSection
0x140015c14  nop     dword ptr [rax+rax+00h]
0x140015c19  lea     rcx, [rbx+8]; this
0x140015c1d  lea     r11, [rsp+0E8h+var_8]
0x140015c25  mov     rbx, [r11+10h]
0x140015c29  mov     rsi, [r11+18h]
0x140015c2d  mov     rsp, r11
0x140015c30  pop     rdi
0x140015c31  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

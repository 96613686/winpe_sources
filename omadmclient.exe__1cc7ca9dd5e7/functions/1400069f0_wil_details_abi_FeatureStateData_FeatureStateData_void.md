# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1400069f0`
- end: `0x140006ad2`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000ad1c`

## callees

- `0x14000669c`
- `0x1400069f0`
- `0x140006f18`
- `0x140009c08`
- `0x14000c388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006aa9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006aa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006a82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006a82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006a96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006a96`

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
0x1400069f0  mov     [rsp+arg_0], rbx
0x1400069f5  mov     [rsp+arg_8], rsi
0x1400069fa  push    rdi
0x1400069fb  sub     rsp, 0E0h
0x140006a02  mov     rbx, rcx
0x140006a05  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006a0a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140006a0f  cmp     byte ptr [rbx+40h], 0
0x140006a13  jz      short loc_140006A23
0x140006a15  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140006a19  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006a1e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140006a23  cmp     byte ptr [rbx+80h], 0
0x140006a2a  jz      short loc_140006A3A
0x140006a2c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140006a30  lea     rcx, [rsp+0E8h+var_88]; this
0x140006a35  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140006a3a  cmp     byte ptr [rbx+0C0h], 0
0x140006a41  jz      short loc_140006A57
0x140006a43  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140006a4a  lea     rcx, [rsp+0E8h+var_48]; this
0x140006a52  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140006a57  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006a5c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140006a61  lea     rcx, [rsp+0E8h+var_C8]; this
0x140006a66  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140006a6b  mov     rsi, [rbx+108h]
0x140006a72  mov     qword ptr [rbx+108h], 0
0x140006a7d  test    rsi, rsi
0x140006a80  jz      short loc_140006AA2
0x140006a82  call    cs:__imp_GetProcessHeap
0x140006a89  nop     dword ptr [rax+rax+00h]
0x140006a8e  mov     rcx, rax; hHeap
0x140006a91  mov     r8, rsi; lpMem
0x140006a94  xor     edx, edx; dwFlags
0x140006a96  call    cs:__imp_HeapFree
0x140006a9d  nop     dword ptr [rax+rax+00h]
0x140006aa2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140006aa9  call    cs:__imp_DeleteCriticalSection
0x140006ab0  nop     dword ptr [rax+rax+00h]
0x140006ab5  lea     rcx, [rbx+8]; this
0x140006ab9  lea     r11, [rsp+0E8h+var_8]
0x140006ac1  mov     rbx, [r11+10h]
0x140006ac5  mov     rsi, [r11+18h]
0x140006ac9  mov     rsp, r11
0x140006acc  pop     rdi
0x140006acd  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

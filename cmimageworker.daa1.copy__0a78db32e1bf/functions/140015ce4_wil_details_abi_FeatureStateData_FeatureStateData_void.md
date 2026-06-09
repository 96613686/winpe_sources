# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140015ce4`
- end: `0x140015dc6`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001d8e0`

## callees

- `0x140015500`
- `0x140015ce4`
- `0x140016080`
- `0x14001c6e4`
- `0x14001ebcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015d9d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015d9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015d76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015d76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015d8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015d8a`

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
0x140015ce4  mov     [rsp+arg_0], rbx
0x140015ce9  mov     [rsp+arg_8], rsi
0x140015cee  push    rdi
0x140015cef  sub     rsp, 0E0h
0x140015cf6  mov     rbx, rcx
0x140015cf9  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015cfe  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140015d03  cmp     byte ptr [rbx+40h], 0
0x140015d07  jz      short loc_140015D17
0x140015d09  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140015d0d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015d12  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140015d17  cmp     byte ptr [rbx+80h], 0
0x140015d1e  jz      short loc_140015D2E
0x140015d20  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140015d24  lea     rcx, [rsp+0E8h+var_88]; this
0x140015d29  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140015d2e  cmp     byte ptr [rbx+0C0h], 0
0x140015d35  jz      short loc_140015D4B
0x140015d37  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140015d3e  lea     rcx, [rsp+0E8h+var_48]; this
0x140015d46  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140015d4b  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015d50  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140015d55  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015d5a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140015d5f  mov     rsi, [rbx+108h]
0x140015d66  mov     qword ptr [rbx+108h], 0
0x140015d71  test    rsi, rsi
0x140015d74  jz      short loc_140015D96
0x140015d76  call    cs:__imp_GetProcessHeap
0x140015d7d  nop     dword ptr [rax+rax+00h]
0x140015d82  mov     rcx, rax; hHeap
0x140015d85  mov     r8, rsi; lpMem
0x140015d88  xor     edx, edx; dwFlags
0x140015d8a  call    cs:__imp_HeapFree
0x140015d91  nop     dword ptr [rax+rax+00h]
0x140015d96  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140015d9d  call    cs:__imp_DeleteCriticalSection
0x140015da4  nop     dword ptr [rax+rax+00h]
0x140015da9  lea     rcx, [rbx+8]; this
0x140015dad  lea     r11, [rsp+0E8h+var_8]
0x140015db5  mov     rbx, [r11+10h]
0x140015db9  mov     rsi, [r11+18h]
0x140015dbd  mov     rsp, r11
0x140015dc0  pop     rdi
0x140015dc1  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18001c13c`
- end: `0x18001c21b`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800249c4`

## callees

- `0x18001be44`
- `0x18001c13c`
- `0x18001c528`
- `0x180023964`
- `0x1800259b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c1f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c1f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c1cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c1cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c1df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c1df`

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
0x18001c13c  mov     [rsp+arg_0], rbx
0x18001c141  mov     [rsp+arg_8], rsi
0x18001c146  push    rdi
0x18001c147  sub     rsp, 0E0h
0x18001c14e  mov     rbx, rcx
0x18001c151  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001c156  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001c15b  cmp     byte ptr [rbx+40h], 0
0x18001c15f  jz      short loc_18001C16F
0x18001c161  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18001c165  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001c16a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001c16f  cmp     byte ptr [rbx+80h], 0
0x18001c176  jz      short loc_18001C186
0x18001c178  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18001c17c  lea     rcx, [rsp+0E8h+var_88]; this
0x18001c181  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001c186  cmp     byte ptr [rbx+0C0h], 0
0x18001c18d  jz      short loc_18001C1A3
0x18001c18f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18001c196  lea     rcx, [rsp+0E8h+var_48]; this
0x18001c19e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001c1a3  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001c1a8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18001c1ad  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001c1b2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001c1b7  mov     rsi, [rbx+108h]
0x18001c1be  and     qword ptr [rbx+108h], 0
0x18001c1c6  test    rsi, rsi
0x18001c1c9  jz      short loc_18001C1EB
0x18001c1cb  call    cs:__imp_GetProcessHeap
0x18001c1d2  nop     dword ptr [rax+rax+00h]
0x18001c1d7  mov     r8, rsi; lpMem
0x18001c1da  xor     edx, edx; dwFlags
0x18001c1dc  mov     rcx, rax; hHeap
0x18001c1df  call    cs:__imp_HeapFree
0x18001c1e6  nop     dword ptr [rax+rax+00h]
0x18001c1eb  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001c1f2  call    cs:__imp_DeleteCriticalSection
0x18001c1f9  nop     dword ptr [rax+rax+00h]
0x18001c1fe  lea     rcx, [rbx+8]; this
0x18001c202  lea     r11, [rsp+0E8h+var_8]
0x18001c20a  mov     rbx, [r11+10h]
0x18001c20e  mov     rsi, [r11+18h]
0x18001c212  mov     rsp, r11
0x18001c215  pop     rdi
0x18001c216  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

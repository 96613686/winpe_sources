# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180002c44`
- end: `0x180002d14`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002b50`

## callees

- `0x1800029bc`
- `0x180002c44`
- `0x180002f94`
- `0x1800057a0`
- `0x180006f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002cf1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002cf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ce4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ce4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cd6`

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
0x180002c44  mov     [rsp+arg_0], rbx
0x180002c49  mov     [rsp+arg_8], rsi
0x180002c4e  push    rdi
0x180002c4f  sub     rsp, 0E0h
0x180002c56  mov     rbx, rcx
0x180002c59  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002c5e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180002c63  cmp     byte ptr [rbx+40h], 0
0x180002c67  jz      short loc_180002C77
0x180002c69  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180002c6d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002c72  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002c77  cmp     byte ptr [rbx+80h], 0
0x180002c7e  jz      short loc_180002C8E
0x180002c80  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180002c84  lea     rcx, [rsp+0E8h+var_88]; this
0x180002c89  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002c8e  cmp     byte ptr [rbx+0C0h], 0
0x180002c95  jz      short loc_180002CAB
0x180002c97  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180002c9e  lea     rcx, [rsp+0E8h+var_48]; this
0x180002ca6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180002cab  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002cb0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180002cb5  lea     rcx, [rsp+0E8h+var_C8]; this
0x180002cba  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180002cbf  mov     rsi, [rbx+108h]
0x180002cc6  mov     qword ptr [rbx+108h], 0
0x180002cd1  test    rsi, rsi
0x180002cd4  jz      short loc_180002CEA
0x180002cd6  call    cs:__imp_GetProcessHeap
0x180002cdc  mov     r8, rsi; lpMem
0x180002cdf  xor     edx, edx; dwFlags
0x180002ce1  mov     rcx, rax; hHeap
0x180002ce4  call    cs:__imp_HeapFree
0x180002cea  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180002cf1  call    cs:__imp_DeleteCriticalSection
0x180002cf7  lea     rcx, [rbx+8]; this
0x180002cfb  lea     r11, [rsp+0E8h+var_8]
0x180002d03  mov     rbx, [r11+10h]
0x180002d07  mov     rsi, [r11+18h]
0x180002d0b  mov     rsp, r11
0x180002d0e  pop     rdi
0x180002d0f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

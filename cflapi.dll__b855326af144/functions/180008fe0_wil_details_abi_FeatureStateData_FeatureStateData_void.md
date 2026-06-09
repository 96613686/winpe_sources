# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180008fe0`
- end: `0x1800090b0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800089e0`

## callees

- `0x180008678`
- `0x180008fe0`
- `0x180009364`
- `0x18000b140`
- `0x18000f5fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000908d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000908d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009080`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009080`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009072`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009072`

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
0x180008fe0  mov     [rsp+arg_0], rbx
0x180008fe5  mov     [rsp+arg_8], rsi
0x180008fea  push    rdi
0x180008feb  sub     rsp, 0E0h
0x180008ff2  mov     rbx, rcx
0x180008ff5  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008ffa  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008fff  cmp     byte ptr [rbx+40h], 0
0x180009003  jz      short loc_180009013
0x180009005  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180009009  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000900e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009013  cmp     byte ptr [rbx+80h], 0
0x18000901a  jz      short loc_18000902A
0x18000901c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180009020  lea     rcx, [rsp+0E8h+var_88]; this
0x180009025  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000902a  cmp     byte ptr [rbx+0C0h], 0
0x180009031  jz      short loc_180009047
0x180009033  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000903a  lea     rcx, [rsp+0E8h+var_48]; this
0x180009042  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009047  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000904c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180009051  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009056  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000905b  mov     rsi, [rbx+108h]
0x180009062  mov     qword ptr [rbx+108h], 0
0x18000906d  test    rsi, rsi
0x180009070  jz      short loc_180009086
0x180009072  call    cs:__imp_GetProcessHeap
0x180009078  mov     rcx, rax; hHeap
0x18000907b  mov     r8, rsi; lpMem
0x18000907e  xor     edx, edx; dwFlags
0x180009080  call    cs:__imp_HeapFree
0x180009086  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000908d  call    cs:__imp_DeleteCriticalSection
0x180009093  lea     rcx, [rbx+8]; this
0x180009097  lea     r11, [rsp+0E8h+var_8]
0x18000909f  mov     rbx, [r11+10h]
0x1800090a3  mov     rsi, [r11+18h]
0x1800090a7  mov     rsp, r11
0x1800090aa  pop     rdi
0x1800090ab  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

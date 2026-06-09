# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180004894`
- end: `0x180004964`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004654`

## callees

- `0x1800044c0`
- `0x180004894`
- `0x180004be4`
- `0x1800083f8`
- `0x180009bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004941`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004926`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004926`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004934`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004934`

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
0x180004894  mov     [rsp+arg_0], rbx
0x180004899  mov     [rsp+arg_8], rsi
0x18000489e  push    rdi
0x18000489f  sub     rsp, 0E0h
0x1800048a6  mov     rbx, rcx
0x1800048a9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800048ae  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800048b3  cmp     byte ptr [rbx+40h], 0
0x1800048b7  jz      short loc_1800048C7
0x1800048b9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800048bd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800048c2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800048c7  cmp     byte ptr [rbx+80h], 0
0x1800048ce  jz      short loc_1800048DE
0x1800048d0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800048d4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800048d9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800048de  cmp     byte ptr [rbx+0C0h], 0
0x1800048e5  jz      short loc_1800048FB
0x1800048e7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800048ee  lea     rcx, [rsp+0E8h+var_48]; this
0x1800048f6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800048fb  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004900  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180004905  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000490a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000490f  mov     rsi, [rbx+108h]
0x180004916  mov     qword ptr [rbx+108h], 0
0x180004921  test    rsi, rsi
0x180004924  jz      short loc_18000493A
0x180004926  call    cs:__imp_GetProcessHeap
0x18000492c  mov     r8, rsi; lpMem
0x18000492f  xor     edx, edx; dwFlags
0x180004931  mov     rcx, rax; hHeap
0x180004934  call    cs:__imp_HeapFree
0x18000493a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180004941  call    cs:__imp_DeleteCriticalSection
0x180004947  lea     rcx, [rbx+8]; this
0x18000494b  lea     r11, [rsp+0E8h+var_8]
0x180004953  mov     rbx, [r11+10h]
0x180004957  mov     rsi, [r11+18h]
0x18000495b  mov     rsp, r11
0x18000495e  pop     rdi
0x18000495f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

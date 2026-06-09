# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800094d0`
- end: `0x1800095a0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009258`

## callees

- `0x180009190`
- `0x1800094d0`
- `0x1800097d4`
- `0x18000aa00`
- `0x18000be90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000957d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000957d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009562`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009562`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009570`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009570`

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
0x1800094d0  mov     [rsp+arg_0], rbx
0x1800094d5  mov     [rsp+arg_8], rsi
0x1800094da  push    rdi
0x1800094db  sub     rsp, 0E0h
0x1800094e2  mov     rbx, rcx
0x1800094e5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800094ea  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800094ef  cmp     byte ptr [rbx+40h], 0
0x1800094f3  jz      short loc_180009503
0x1800094f5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800094f9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800094fe  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009503  cmp     byte ptr [rbx+80h], 0
0x18000950a  jz      short loc_18000951A
0x18000950c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180009510  lea     rcx, [rsp+0E8h+var_88]; this
0x180009515  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000951a  cmp     byte ptr [rbx+0C0h], 0
0x180009521  jz      short loc_180009537
0x180009523  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000952a  lea     rcx, [rsp+0E8h+var_48]; this
0x180009532  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009537  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000953c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180009541  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009546  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000954b  mov     rsi, [rbx+108h]
0x180009552  mov     qword ptr [rbx+108h], 0
0x18000955d  test    rsi, rsi
0x180009560  jz      short loc_180009576
0x180009562  call    cs:__imp_GetProcessHeap
0x180009568  mov     rcx, rax; hHeap
0x18000956b  mov     r8, rsi; lpMem
0x18000956e  xor     edx, edx; dwFlags
0x180009570  call    cs:__imp_HeapFree
0x180009576  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000957d  call    cs:__imp_DeleteCriticalSection
0x180009583  lea     rcx, [rbx+8]; this
0x180009587  lea     r11, [rsp+0E8h+var_8]
0x18000958f  mov     rbx, [r11+10h]
0x180009593  mov     rsi, [r11+18h]
0x180009597  mov     rsp, r11
0x18000959a  pop     rdi
0x18000959b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

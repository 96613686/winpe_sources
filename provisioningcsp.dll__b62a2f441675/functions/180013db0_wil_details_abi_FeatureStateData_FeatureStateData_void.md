# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180013db0`
- end: `0x180013e92`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180021b34`

## callees

- `0x180013c58`
- `0x180013db0`
- `0x1800140a8`
- `0x180020ecc`
- `0x180022400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013e69`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013e69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013e56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013e56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013e42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013e42`

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
0x180013db0  mov     [rsp+arg_0], rbx
0x180013db5  mov     [rsp+arg_8], rsi
0x180013dba  push    rdi
0x180013dbb  sub     rsp, 0E0h
0x180013dc2  mov     rbx, rcx
0x180013dc5  lea     rcx, [rsp+0E8h+var_C8]; this
0x180013dca  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180013dcf  cmp     byte ptr [rbx+40h], 0
0x180013dd3  jz      short loc_180013DE3
0x180013dd5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180013dd9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180013dde  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180013de3  cmp     byte ptr [rbx+80h], 0
0x180013dea  jz      short loc_180013DFA
0x180013dec  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180013df0  lea     rcx, [rsp+0E8h+var_88]; this
0x180013df5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180013dfa  cmp     byte ptr [rbx+0C0h], 0
0x180013e01  jz      short loc_180013E17
0x180013e03  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180013e0a  lea     rcx, [rsp+0E8h+var_48]; this
0x180013e12  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180013e17  lea     rcx, [rsp+0E8h+var_C8]; this
0x180013e1c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180013e21  lea     rcx, [rsp+0E8h+var_C8]; this
0x180013e26  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180013e2b  mov     rsi, [rbx+108h]
0x180013e32  mov     qword ptr [rbx+108h], 0
0x180013e3d  test    rsi, rsi
0x180013e40  jz      short loc_180013E62
0x180013e42  call    cs:__imp_GetProcessHeap
0x180013e49  nop     dword ptr [rax+rax+00h]
0x180013e4e  mov     rcx, rax; hHeap
0x180013e51  mov     r8, rsi; lpMem
0x180013e54  xor     edx, edx; dwFlags
0x180013e56  call    cs:__imp_HeapFree
0x180013e5d  nop     dword ptr [rax+rax+00h]
0x180013e62  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180013e69  call    cs:__imp_DeleteCriticalSection
0x180013e70  nop     dword ptr [rax+rax+00h]
0x180013e75  lea     rcx, [rbx+8]; this
0x180013e79  lea     r11, [rsp+0E8h+var_8]
0x180013e81  mov     rbx, [r11+10h]
0x180013e85  mov     rsi, [r11+18h]
0x180013e89  mov     rsp, r11
0x180013e8c  pop     rdi
0x180013e8d  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

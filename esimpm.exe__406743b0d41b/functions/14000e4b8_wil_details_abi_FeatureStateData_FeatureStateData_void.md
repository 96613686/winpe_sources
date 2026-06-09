# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x14000e4b8`
- end: `0x14000e588`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e234`

## callees

- `0x14000dfb8`
- `0x14000e4b8`
- `0x14000e92c`
- `0x140011224`
- `0x1400133b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e565`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e565`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e558`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e558`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e54a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e54a`

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
0x14000e4b8  mov     [rsp+arg_0], rbx
0x14000e4bd  mov     [rsp+arg_8], rsi
0x14000e4c2  push    rdi
0x14000e4c3  sub     rsp, 0E0h
0x14000e4ca  mov     rbx, rcx
0x14000e4cd  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000e4d2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000e4d7  cmp     byte ptr [rbx+40h], 0
0x14000e4db  jz      short loc_14000E4EB
0x14000e4dd  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14000e4e1  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000e4e6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000e4eb  cmp     byte ptr [rbx+80h], 0
0x14000e4f2  jz      short loc_14000E502
0x14000e4f4  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14000e4f8  lea     rcx, [rsp+0E8h+var_88]; this
0x14000e4fd  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000e502  cmp     byte ptr [rbx+0C0h], 0
0x14000e509  jz      short loc_14000E51F
0x14000e50b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000e512  lea     rcx, [rsp+0E8h+var_48]; this
0x14000e51a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000e51f  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000e524  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000e529  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000e52e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000e533  mov     rsi, [rbx+108h]
0x14000e53a  mov     qword ptr [rbx+108h], 0
0x14000e545  test    rsi, rsi
0x14000e548  jz      short loc_14000E55E
0x14000e54a  call    cs:__imp_GetProcessHeap
0x14000e550  mov     rcx, rax; hHeap
0x14000e553  mov     r8, rsi; lpMem
0x14000e556  xor     edx, edx; dwFlags
0x14000e558  call    cs:__imp_HeapFree
0x14000e55e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000e565  call    cs:__imp_DeleteCriticalSection
0x14000e56b  lea     rcx, [rbx+8]; this
0x14000e56f  lea     r11, [rsp+0E8h+var_8]
0x14000e577  mov     rbx, [r11+10h]
0x14000e57b  mov     rsi, [r11+18h]
0x14000e57f  mov     rsp, r11
0x14000e582  pop     rdi
0x14000e583  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

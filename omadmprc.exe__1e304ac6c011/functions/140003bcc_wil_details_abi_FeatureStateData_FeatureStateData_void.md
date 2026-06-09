# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140003bcc`
- end: `0x140003cae`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140007f30`

## callees

- `0x1400038d8`
- `0x140003bcc`
- `0x1400040c8`
- `0x140006f7c`
- `0x1400092ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003c85`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003c85`

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
0x140003bcc  mov     [rsp+arg_0], rbx
0x140003bd1  mov     [rsp+arg_8], rsi
0x140003bd6  push    rdi
0x140003bd7  sub     rsp, 0E0h
0x140003bde  mov     rbx, rcx
0x140003be1  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003be6  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140003beb  cmp     byte ptr [rbx+40h], 0
0x140003bef  jz      short loc_140003BFF
0x140003bf1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140003bf5  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003bfa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003bff  cmp     byte ptr [rbx+80h], 0
0x140003c06  jz      short loc_140003C16
0x140003c08  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140003c0c  lea     rcx, [rsp+0E8h+var_88]; this
0x140003c11  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003c16  cmp     byte ptr [rbx+0C0h], 0
0x140003c1d  jz      short loc_140003C33
0x140003c1f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140003c26  lea     rcx, [rsp+0E8h+var_48]; this
0x140003c2e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003c33  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003c38  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140003c3d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003c42  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140003c47  mov     rsi, [rbx+108h]
0x140003c4e  mov     qword ptr [rbx+108h], 0
0x140003c59  test    rsi, rsi
0x140003c5c  jz      short loc_140003C7E
0x140003c5e  call    cs:__imp_GetProcessHeap
0x140003c65  nop     dword ptr [rax+rax+00h]
0x140003c6a  mov     rcx, rax; hHeap
0x140003c6d  mov     r8, rsi; lpMem
0x140003c70  xor     edx, edx; dwFlags
0x140003c72  call    cs:__imp_HeapFree
0x140003c79  nop     dword ptr [rax+rax+00h]
0x140003c7e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140003c85  call    cs:__imp_DeleteCriticalSection
0x140003c8c  nop     dword ptr [rax+rax+00h]
0x140003c91  lea     rcx, [rbx+8]; this
0x140003c95  lea     r11, [rsp+0E8h+var_8]
0x140003c9d  mov     rbx, [r11+10h]
0x140003ca1  mov     rsi, [r11+18h]
0x140003ca5  mov     rsp, r11
0x140003ca8  pop     rdi
0x140003ca9  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

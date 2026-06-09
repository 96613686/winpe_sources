# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003c80`
- end: `0x180003d5f`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007c50`

## callees

- `0x1800038b4`
- `0x180003c80`
- `0x1800041ac`
- `0x180006b98`
- `0x180008ee4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003d36`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003d36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d23`

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
0x180003c80  mov     [rsp+arg_0], rbx
0x180003c85  mov     [rsp+arg_8], rsi
0x180003c8a  push    rdi
0x180003c8b  sub     rsp, 0E0h
0x180003c92  mov     rbx, rcx
0x180003c95  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003c9a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003c9f  cmp     byte ptr [rbx+40h], 0
0x180003ca3  jz      short loc_180003CB3
0x180003ca5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003ca9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003cae  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003cb3  cmp     byte ptr [rbx+80h], 0
0x180003cba  jz      short loc_180003CCA
0x180003cbc  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003cc0  lea     rcx, [rsp+0E8h+var_88]; this
0x180003cc5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003cca  cmp     byte ptr [rbx+0C0h], 0
0x180003cd1  jz      short loc_180003CE7
0x180003cd3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003cda  lea     rcx, [rsp+0E8h+var_48]; this
0x180003ce2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003ce7  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003cec  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003cf1  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003cf6  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003cfb  mov     rsi, [rbx+108h]
0x180003d02  and     qword ptr [rbx+108h], 0
0x180003d0a  test    rsi, rsi
0x180003d0d  jz      short loc_180003D2F
0x180003d0f  call    cs:__imp_GetProcessHeap
0x180003d16  nop     dword ptr [rax+rax+00h]
0x180003d1b  mov     rcx, rax; hHeap
0x180003d1e  mov     r8, rsi; lpMem
0x180003d21  xor     edx, edx; dwFlags
0x180003d23  call    cs:__imp_HeapFree
0x180003d2a  nop     dword ptr [rax+rax+00h]
0x180003d2f  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003d36  call    cs:__imp_DeleteCriticalSection
0x180003d3d  nop     dword ptr [rax+rax+00h]
0x180003d42  lea     rcx, [rbx+8]; this
0x180003d46  lea     r11, [rsp+0E8h+var_8]
0x180003d4e  mov     rbx, [r11+10h]
0x180003d52  mov     rsi, [r11+18h]
0x180003d56  mov     rsp, r11
0x180003d59  pop     rdi
0x180003d5a  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```

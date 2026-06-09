# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x18000ae1c`
- end: `0x18000aea9`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007690`
- `0x18000ac64`
- `0x18000c560`

## callees

- `0x180007ffc`
- `0x1800085d4`
- `0x18000ab1c`
- `0x18000ae1c`
- `0x18000c1a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae35`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::RecordUsage(PSRWLOCK SRWLock)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  const struct wil::details_abi::RawUsageIndex *v4; // r9
  _BYTE v5[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v6[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v7[72]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v5);
  AcquireSRWLockExclusive(SRWLock);
  if ( LOBYTE(SRWLock[8].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v5,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[1]);
  if ( LOBYTE(SRWLock[16].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v6,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[9]);
  if ( LOBYTE(SRWLock[24].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v7,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[17]);
  ReleaseSRWLockExclusive(SRWLock);
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v5, v2, v3, v4);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v5);
}

```

## disassembly

```asm
0x18000ae1c  push    rbx
0x18000ae1e  sub     rsp, 0E0h
0x18000ae25  mov     rbx, rcx
0x18000ae28  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ae2d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000ae32  mov     rcx, rbx; SRWLock
0x18000ae35  call    cs:__imp_AcquireSRWLockExclusive
0x18000ae3b  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000ae3f  cmp     byte ptr [rdx+38h], 0
0x18000ae43  jz      short loc_18000AE4F
0x18000ae45  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ae4a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000ae4f  cmp     byte ptr [rbx+80h], 0
0x18000ae56  jz      short loc_18000AE66
0x18000ae58  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000ae5c  lea     rcx, [rsp+0E8h+var_88]; this
0x18000ae61  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000ae66  cmp     byte ptr [rbx+0C0h], 0
0x18000ae6d  jz      short loc_18000AE83
0x18000ae6f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000ae76  lea     rcx, [rsp+0E8h+var_48]; this
0x18000ae7e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000ae83  mov     rcx, rbx; SRWLock
0x18000ae86  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ae8c  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ae91  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000ae96  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ae9b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000aea0  add     rsp, 0E0h
0x18000aea7  pop     rbx
0x18000aea8  retn
```

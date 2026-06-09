# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x18000f7e0`
- end: `0x18000f86f`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800070c0`
- `0x18000f624`
- `0x180011810`

## callees

- `0x1800073e8`
- `0x180007b7c`
- `0x18000f358`
- `0x18000f7e0`
- `0x18001164c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f84b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f84b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f7fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f7fa`

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
0x18000f7e0  push    rbx
0x18000f7e2  sub     rsp, 0E0h
0x18000f7e9  mov     rbx, rcx
0x18000f7ec  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000f7f1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000f7f6  nop
0x18000f7f7  mov     rcx, rbx; SRWLock
0x18000f7fa  call    cs:__imp_AcquireSRWLockExclusive
0x18000f800  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000f804  cmp     byte ptr [rdx+38h], 0
0x18000f808  jz      short loc_18000F814
0x18000f80a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000f80f  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000f814  cmp     byte ptr [rbx+80h], 0
0x18000f81b  jz      short loc_18000F82B
0x18000f81d  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000f821  lea     rcx, [rsp+0E8h+var_88]; this
0x18000f826  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000f82b  cmp     byte ptr [rbx+0C0h], 0
0x18000f832  jz      short loc_18000F848
0x18000f834  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000f83b  lea     rcx, [rsp+0E8h+var_48]; this
0x18000f843  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000f848  mov     rcx, rbx; SRWLock
0x18000f84b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f851  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000f856  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000f85b  nop
0x18000f85c  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000f861  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000f866  add     rsp, 0E0h
0x18000f86d  pop     rbx
0x18000f86e  retn
```

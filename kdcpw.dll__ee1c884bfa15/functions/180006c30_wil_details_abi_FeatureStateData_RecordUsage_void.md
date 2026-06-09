# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180006c30`
- end: `0x180006cbd`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002740`
- `0x180006a44`
- `0x180008960`

## callees

- `0x180003140`
- `0x180003864`
- `0x180006744`
- `0x180006c30`
- `0x180008530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c9a`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::RecordUsage(PSRWLOCK SRWLock)
{
  _BYTE v2[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v3[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v4[72]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v2);
  AcquireSRWLockExclusive(SRWLock);
  if ( LOBYTE(SRWLock[8].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v2,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[1]);
  if ( LOBYTE(SRWLock[16].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v3,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[9]);
  if ( LOBYTE(SRWLock[24].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v4,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[17]);
  ReleaseSRWLockExclusive(SRWLock);
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v2);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v2);
}

```

## disassembly

```asm
0x180006c30  push    rbx
0x180006c32  sub     rsp, 0E0h
0x180006c39  mov     rbx, rcx
0x180006c3c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006c41  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006c46  mov     rcx, rbx; SRWLock
0x180006c49  call    cs:__imp_AcquireSRWLockExclusive
0x180006c4f  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180006c53  cmp     byte ptr [rdx+38h], 0
0x180006c57  jz      short loc_180006C63
0x180006c59  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006c5e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006c63  cmp     byte ptr [rbx+80h], 0
0x180006c6a  jz      short loc_180006C7A
0x180006c6c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180006c70  lea     rcx, [rsp+0E8h+var_88]; this
0x180006c75  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006c7a  cmp     byte ptr [rbx+0C0h], 0
0x180006c81  jz      short loc_180006C97
0x180006c83  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180006c8a  lea     rcx, [rsp+0E8h+var_48]; this
0x180006c92  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006c97  mov     rcx, rbx; SRWLock
0x180006c9a  call    cs:__imp_ReleaseSRWLockExclusive
0x180006ca0  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006ca5  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180006caa  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006caf  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180006cb4  add     rsp, 0E0h
0x180006cbb  pop     rbx
0x180006cbc  retn
```

# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x14000b4c0`
- end: `0x14000b54f`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400033c0`
- `0x14000b304`
- `0x14000f6f0`

## callees

- `0x140005c9c`
- `0x140006d54`
- `0x14000b1bc`
- `0x14000b4c0`
- `0x14000dd34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b4da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b4da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b52b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b52b`

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
0x14000b4c0  push    rbx
0x14000b4c2  sub     rsp, 0E0h
0x14000b4c9  mov     rbx, rcx
0x14000b4cc  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b4d1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000b4d6  nop
0x14000b4d7  mov     rcx, rbx; SRWLock
0x14000b4da  call    cs:__imp_AcquireSRWLockExclusive
0x14000b4e0  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14000b4e4  cmp     byte ptr [rdx+38h], 0
0x14000b4e8  jz      short loc_14000B4F4
0x14000b4ea  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b4ef  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b4f4  cmp     byte ptr [rbx+80h], 0
0x14000b4fb  jz      short loc_14000B50B
0x14000b4fd  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14000b501  lea     rcx, [rsp+0E8h+var_88]; this
0x14000b506  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b50b  cmp     byte ptr [rbx+0C0h], 0
0x14000b512  jz      short loc_14000B528
0x14000b514  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000b51b  lea     rcx, [rsp+0E8h+var_48]; this
0x14000b523  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000b528  mov     rcx, rbx; SRWLock
0x14000b52b  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b531  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b536  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000b53b  nop
0x14000b53c  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000b541  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000b546  add     rsp, 0E0h
0x14000b54d  pop     rbx
0x14000b54e  retn
```

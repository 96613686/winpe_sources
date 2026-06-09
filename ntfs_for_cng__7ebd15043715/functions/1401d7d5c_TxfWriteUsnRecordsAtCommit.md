# TxfWriteUsnRecordsAtCommit

- ea: `0x1401d7d5c`
- end: `0x1401d8337`
- name: `TxfWriteUsnRecordsAtCommit`
- size: `1499`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140133f30`
- `0x1401da21c`

## callees

- `0x140007ea0`
- `0x140010be0`
- `0x1400593c0`
- `0x140190b80`
- `0x1401d7d5c`
- `0x1401d90dc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401d81b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402cc919`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d81b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402cc919`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d7e17`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402cc8e5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d7e17`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402cc8e5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d7d97`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d7f5a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d7d97`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d7f5a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1401d7dc8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1401d7dc8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d7efe`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d7efe`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d7ea2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d7ea2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d7fc9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d80d0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d7fc9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d80d0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d815b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d8281`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d8313`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d815b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d8281`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d8313`

## pseudocode

```c
__int64 __fastcall TxfWriteUsnRecordsAtCommit(__int64 a1, __int64 a2)
{
  CLFS_LSN *v2; // rbx
  CLFS_LSN *PoolWithTag; // r15
  unsigned int v7; // r12d
  char v8; // r14
  PVOID v9; // rcx
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // r8d
  __int64 v15; // rdx
  __int64 v16; // rcx
  NTSTATUS v17; // eax
  unsigned int v18; // r8d
  unsigned int i; // r14d
  CLFS_LSN v20; // rcx
  NTSTATUS v21; // eax
  int v22; // eax
  PVOID v23; // rcx
  PVOID v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // rdx
  PVOID v27; // rcx
  CLFS_LSN *v28; // rax
  CLFS_LSN *v29; // rbx
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rax
  __int64 v33; // rdx
  int v34; // edx
  unsigned __int64 v35; // rax
  __int64 v36; // rdx
  unsigned __int64 v37; // rax
  __int64 v38; // rdx
  int v39; // edx
  PVOID pvReadContext; // [rsp+50h] [rbp-29h] BYREF
  CLFS_LSN plsn2; // [rsp+58h] [rbp-21h] BYREF
  PVOID ppvBuffer; // [rsp+60h] [rbp-19h] BYREF
  ULONG pcbReadBuffer; // [rsp+68h] [rbp-11h] BYREF
  _DWORD plsnUndoNext[3]; // [rsp+6Ch] [rbp-Dh] BYREF
  PVOID ppvReadBuffer; // [rsp+78h] [rbp-1h] BYREF
  CLFS_LSN plsnPrevious; // [rsp+80h] [rbp+7h] BYREF
  CLFS_LSN v47; // [rsp+88h] [rbp+Fh] BYREF
  CLFS_LSN v48; // [rsp+90h] [rbp+17h] BYREF
  CLS_RECORD_TYPE peRecordType; // [rsp+E8h] [rbp+6Fh] BYREF
  CLS_RECORD_TYPE v50; // [rsp+F0h] [rbp+77h] BYREF
  ULONG pcbBuffer; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = (CLFS_LSN *)(a2 + 384);
  plsnUndoNext[0] = 0;
  plsn2.ullOffset = 0;
  pvReadContext = 0;
  if ( ClfsLsnNull((const CLFS_LSN *)(a2 + 384))
    || ClfsLsnInvalid(v2)
    || (*(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL) & 0x80000) == 0 )
  {
    return 0;
  }
  if ( (*(_DWORD *)(a2 + 16) & 0x20) != 0 )
    *(_WORD *)(a2 + 414) += 5;
  if ( *(_WORD *)(a2 + 414) == 1 )
    return TxfWriteUsnRecordsAtCommitHelper(
             a1,
             (const CLFS_LSN *)a2,
             *(_QWORD **)(a2 + 400),
             *(_WORD *)(a2 + 410),
             plsnUndoNext);
  PoolWithTag = (CLFS_LSN *)ExAllocatePoolWithTag(PoolType, 8LL * *(unsigned __int16 *)(a2 + 414), 0x31667854u);
  if ( PoolWithTag )
  {
    v7 = 0;
    plsn2 = *v2;
    v8 = 0;
    while ( 1 )
    {
      ppvBuffer = 0;
      pcbBuffer = 0;
      peRecordType = 0;
      *(_QWORD *)&plsnUndoNext[1] = 0;
      plsnPrevious.ullOffset = 0;
      *(_DWORD *)(a1 + 436) |= 0x10u;
      if ( pvReadContext )
      {
        NtfsPurgeFileRecordCache(a1);
        v9 = pvReadContext;
        *(_DWORD *)(a1 + 4) |= 0x200u;
        v10 = ClfsReadNextLogRecord(
                v9,
                &ppvBuffer,
                &pcbBuffer,
                &peRecordType,
                &plsn2,
                (PCLFS_LSN)&plsnUndoNext[1],
                &plsnPrevious,
                (PCLFS_LSN)&plsnUndoNext[1]);
        *(_DWORD *)(a1 + 436) &= ~0x10u;
        v11 = v10;
        *(_DWORD *)(a1 + 4) &= ~0x200u;
      }
      else
      {
        NtfsPurgeFileRecordCache(a1);
        *(_DWORD *)(a1 + 4) |= 0x200u;
        v17 = ClfsReadLogRecord(
                *(PVOID *)(*(_QWORD *)(a2 + 208) + 512LL),
                &plsn2,
                ClfsContextPrevious,
                &ppvBuffer,
                &pcbBuffer,
                &peRecordType,
                (PCLFS_LSN)&plsnUndoNext[1],
                &plsnPrevious,
                &pvReadContext);
        *(_DWORD *)(a1 + 436) &= ~0x10u;
        v11 = v17;
        *(_DWORD *)(a1 + 4) &= ~0x200u;
        if ( v17 >= 0 )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 208) + 528LL));
      }
      v12 = 0x408000001LL;
      v13 = 0x800000041LL;
      v14 = 2097219;
      if ( v11 )
        break;
      if ( !(unsigned __int8)TxfValidateLogRecord(ppvBuffer, pcbBuffer)
        || !ClfsLsnLess((const CLFS_LSN *)ppvBuffer + 10, &plsn2)
        || (*(_BYTE *)ppvBuffer & 1) == 0
        || *((_DWORD *)ppvBuffer + 1) != 23 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC0190030, 0x313DEFu);
        v11 = -1072103376;
        goto LABEL_26;
      }
      v15 = *(unsigned __int16 *)(a2 + 414);
      if ( (_DWORD)v15 == v7 )
      {
        if ( (*(_DWORD *)(a2 + 16) & 0x20) == 0 )
        {
          v11 = -1073741595;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_26;
          v18 = 3227134;
LABEL_25:
          NtfsStatusTraceAndDebugInternal(0, v11, v18);
          goto LABEL_26;
        }
        v28 = (CLFS_LSN *)ExAllocatePoolWithTag(PoolType, 16 * v15, 0x31667854u);
        v29 = v28;
        if ( !v28 )
        {
          v11 = -1073741670;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_26;
          v18 = 3227142;
          goto LABEL_25;
        }
        memmove(v28, PoolWithTag, 8LL * *(unsigned __int16 *)(a2 + 414));
        ExFreePoolWithTag(PoolWithTag, 0);
        PoolWithTag = v29;
        *(_WORD *)(a2 + 414) *= 2;
      }
      v11 = 0;
      v16 = v7++;
      PoolWithTag[v16] = plsn2;
      plsn2 = *(CLFS_LSN *)((char *)ppvBuffer + 80);
      if ( ClfsLsnNull(&plsn2) )
      {
        v8 = 1;
        goto LABEL_26;
      }
    }
    if ( (*(_DWORD *)(a2 + 16) & 0x20) != 0 )
    {
      v11 = 0;
    }
    else if ( v11 == -1073741801 || (v30 = v11 + 1073741697, (unsigned int)v30 <= 0x22) && _bittest64(&v12, v30) )
    {
      ++HIDWORD((*TxfData)[1]);
    }
    else if ( v11 == -1072037845
           || v11 == -1073741202
           || v11 == -1073741435
           || v11 == -1073741496
           || (v31 = v11 + 1073741667, (unsigned int)v31 <= 0x23) && _bittest64(&v13, v31)
           || v11 + 1073741811 <= 0x15 && _bittest(&v14, v11 + 1073741811)
           || v11 == -2147483626
           || v11 == -1072037841 )
    {
      ++LODWORD((*TxfData)[2]);
    }
LABEL_26:
    if ( pvReadContext )
    {
      NtfsPurgeFileRecordCache(a1);
      v24 = pvReadContext;
      *(_DWORD *)(a1 + 4) |= 0x200u;
      ClfsTerminateReadLog(v24);
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 208) + 528LL));
      pvReadContext = 0;
    }
    if ( v8 )
    {
      for ( i = 0; i < v7; ++i )
      {
        ppvReadBuffer = 0;
        pcbReadBuffer = 0;
        v50 = 0;
        v48.ullOffset = 0;
        v47.ullOffset = 0;
        v20 = PoolWithTag[v7 - i - 1];
        *(_DWORD *)(a1 + 436) |= 0x10u;
        plsn2 = v20;
        NtfsPurgeFileRecordCache(a1);
        *(_DWORD *)(a1 + 4) |= 0x200u;
        v21 = ClfsReadLogRecord(
                *(PVOID *)(*(_QWORD *)(a2 + 208) + 512LL),
                &plsn2,
                ClfsContextForward,
                &ppvReadBuffer,
                &pcbReadBuffer,
                &v50,
                &v48,
                &v47,
                &pvReadContext);
        *(_DWORD *)(a1 + 436) &= ~0x10u;
        *(_DWORD *)(a1 + 4) &= ~0x200u;
        v11 = v21;
        if ( v21 >= 0 )
          _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a2 + 208) + 528LL), 1u);
        if ( v21 )
        {
          if ( (*(_DWORD *)(a2 + 16) & 0x20) != 0 )
          {
            v11 = 0;
          }
          else if ( v21 == -1073741801
                 || (v35 = (unsigned int)(v21 + 1073741697), (unsigned int)v35 <= 0x22)
                 && (v36 = 0x408000001LL, _bittest64(&v36, v35)) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( v11 == -1072037845
                 || v11 == -1073741202
                 || v11 == -1073741435
                 || v11 == -1073741496
                 || (v37 = v11 + 1073741667, (unsigned int)v37 <= 0x23) && (v38 = 0x800000041LL, _bittest64(&v38, v37))
                 || v11 + 1073741811 <= 0x15 && (v39 = 2097219, _bittest(&v39, v11 + 1073741811))
                 || v11 == -2147483626
                 || v11 == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          break;
        }
        if ( !(unsigned __int8)TxfValidateLogRecord(ppvReadBuffer, pcbReadBuffer)
          || (*(_BYTE *)ppvReadBuffer & 1) == 0
          || *((_DWORD *)ppvReadBuffer + 1) != 23 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xC0190030, 0x313E95u);
          v11 = -1072103376;
          break;
        }
        v22 = TxfWriteUsnRecordsAtCommitHelper(
                a1,
                (const CLFS_LSN *)a2,
                (char *)ppvReadBuffer + *((unsigned int *)ppvReadBuffer + 22),
                *((_WORD *)ppvReadBuffer + 46),
                plsnUndoNext);
        v11 = v22;
        if ( v22 < 0 )
        {
          if ( v22 == -1073741801
            || (v25 = (unsigned int)(v22 + 1073741697), (unsigned int)v25 <= 0x22)
            && (v26 = 0x408000001LL, _bittest64(&v26, v25)) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( v11 == -1072037845
                 || v11 == -1073741202
                 || v11 == -1073741435
                 || v11 == -1073741496
                 || (v32 = v11 + 1073741667, (unsigned int)v32 <= 0x23) && (v33 = 0x800000041LL, _bittest64(&v33, v32))
                 || v11 + 1073741811 <= 0x15 && (v34 = 2097219, _bittest(&v34, v11 + 1073741811))
                 || v11 == -2147483626
                 || v11 == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          break;
        }
        NtfsPurgeFileRecordCache(a1);
        v23 = pvReadContext;
        *(_DWORD *)(a1 + 4) |= 0x200u;
        ClfsTerminateReadLog(v23);
        *(_DWORD *)(a1 + 4) &= ~0x200u;
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 208) + 528LL));
        pvReadContext = 0;
      }
      if ( pvReadContext )
      {
        NtfsPurgeFileRecordCache(a1);
        v27 = pvReadContext;
        *(_DWORD *)(a1 + 4) |= 0x200u;
        ClfsTerminateReadLog(v27);
        *(_DWORD *)(a1 + 4) &= ~0x200u;
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 208) + 528LL));
      }
    }
    if ( PoolWithTag )
      ExFreePoolWithTag(PoolWithTag, 0);
  }
  else
  {
    v11 = -1073741670;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x313D7Du);
  }
  return v11;
}

```

## disassembly

```asm
0x1401d7d5c  mov     [rsp-8+arg_0], rbx
0x1401d7d61  push    rbp
0x1401d7d62  push    rsi
0x1401d7d63  push    rdi
0x1401d7d64  push    r12
0x1401d7d66  push    r13
0x1401d7d68  push    r14
0x1401d7d6a  push    r15
0x1401d7d6c  lea     rbp, [rsp-27h]
0x1401d7d71  sub     rsp, 0A0h
0x1401d7d78  xor     r13d, r13d
0x1401d7d7b  lea     rbx, [rdx+180h]
0x1401d7d82  mov     rdi, rcx
0x1401d7d85  mov     dword ptr [rbp+57h+var_64], r13d
0x1401d7d89  mov     rcx, rbx; plsn
0x1401d7d8c  mov     qword ptr [rbp+57h+plsn2], r13
0x1401d7d90  mov     rsi, rdx
0x1401d7d93  mov     [rbp+57h+pvReadContext], r13
0x1401d7d97  call    cs:__imp_ClfsLsnNull
0x1401d7d9e  nop     dword ptr [rax+rax+00h]
0x1401d7da3  test    al, al
0x1401d7da5  jz      short loc_1401D7DC5
0x1401d7da7  xor     eax, eax
0x1401d7da9  mov     rbx, [rsp+0D0h+arg_0]
0x1401d7db1  add     rsp, 0A0h
0x1401d7db8  pop     r15
0x1401d7dba  pop     r14
0x1401d7dbc  pop     r13
0x1401d7dbe  pop     r12
0x1401d7dc0  pop     rdi
0x1401d7dc1  pop     rsi
0x1401d7dc2  pop     rbp
0x1401d7dc3  retn
0x1401d7dc5  mov     rcx, rbx; plsn
0x1401d7dc8  call    cs:__imp_ClfsLsnInvalid
0x1401d7dcf  nop     dword ptr [rax+rax+00h]
0x1401d7dd4  test    al, al
0x1401d7dd6  jnz     short loc_1401D7DA7
0x1401d7dd8  mov     rax, [rdi+68h]
0x1401d7ddc  test    dword ptr [rax+4], 80000h
0x1401d7de3  jz      short loc_1401D7DA7
0x1401d7de5  mov     eax, [rsi+10h]
0x1401d7de8  test    al, 20h
0x1401d7dea  jnz     loc_1401D8228
0x1401d7df0  movzx   eax, word ptr [rsi+19Eh]
0x1401d7df7  mov     ecx, 1
0x1401d7dfc  cmp     ax, cx
0x1401d7dff  jz      loc_1401D8235
0x1401d7e05  mov     ecx, cs:PoolType; PoolType
0x1401d7e0b  mov     edx, eax
0x1401d7e0d  shl     rdx, 3; NumberOfBytes
0x1401d7e11  mov     r8d, 31667854h; Tag
0x1401d7e17  call    cs:__imp_ExAllocatePoolWithTag
0x1401d7e1e  nop     dword ptr [rax+rax+00h]
0x1401d7e23  mov     r15, rax
0x1401d7e26  test    rax, rax
0x1401d7e29  jz      loc_1401D81D2
0x1401d7e2f  mov     rax, [rbx]
0x1401d7e32  mov     r12d, r13d
0x1401d7e35  mov     qword ptr [rbp+57h+plsn2], rax
0x1401d7e39  mov     r14b, r13b
0x1401d7e3c  mov     [rbp+57h+ppvBuffer], r13
0x1401d7e40  mov     rcx, rdi
0x1401d7e43  mov     [rbp+57h+pcbBuffer], r13d
0x1401d7e47  mov     [rbp+57h+peRecordType], r13b
0x1401d7e4b  mov     qword ptr [rbp+57h+var_64+4], r13
0x1401d7e4f  mov     qword ptr [rbp+57h+var_50], r13
0x1401d7e53  or      dword ptr [rdi+1B4h], 10h
0x1401d7e5a  cmp     [rbp+57h+pvReadContext], r13
0x1401d7e5e  jz      loc_1401D7F76
0x1401d7e64  call    NtfsPurgeFileRecordCache
0x1401d7e69  mov     rcx, [rbp+57h+pvReadContext]; pvReadContext
0x1401d7e6d  lea     rax, [rbp+57h+var_64+4]
0x1401d7e71  bts     dword ptr [rdi+4], 9
0x1401d7e76  lea     r9, [rbp+57h+peRecordType]; peRecordType
0x1401d7e7a  mov     [rsp+0D0h+plsnRecord], rax; plsnRecord
0x1401d7e7f  lea     r8, [rbp+57h+pcbBuffer]; pcbBuffer
0x1401d7e83  lea     rax, [rbp+57h+var_50]
0x1401d7e87  mov     [rsp+0D0h+plsnPrevious], rax; plsnPrevious
0x1401d7e8c  lea     rdx, [rbp+57h+ppvBuffer]; ppvBuffer
0x1401d7e90  lea     rax, [rbp+57h+var_64+4]
0x1401d7e94  mov     [rsp+0D0h+plsnUndoNext], rax; plsnUndoNext
0x1401d7e99  lea     rax, [rbp+57h+plsn2]
0x1401d7e9d  mov     [rsp+0D0h+plsnUser], rax; plsnUser
0x1401d7ea2  call    cs:__imp_ClfsReadNextLogRecord
0x1401d7ea9  nop     dword ptr [rax+rax+00h]
0x1401d7eae  and     dword ptr [rdi+1B4h], 0FFFFFFEFh
0x1401d7eb5  mov     ebx, eax
0x1401d7eb7  btr     dword ptr [rdi+4], 9
0x1401d7ebc  mov     rcx, 408000001h
0x1401d7ec6  mov     rdx, 800000041h
0x1401d7ed0  mov     r8d, 200043h
0x1401d7ed6  test    ebx, ebx
0x1401d7ed8  jnz     loc_1401D825D
0x1401d7ede  mov     edx, [rbp+57h+pcbBuffer]
0x1401d7ee1  mov     rcx, [rbp+57h+ppvBuffer]
0x1401d7ee5  call    TxfValidateLogRecord
0x1401d7eea  test    al, al
0x1401d7eec  jz      loc_1401D7FFE
0x1401d7ef2  mov     rcx, [rbp+57h+ppvBuffer]
0x1401d7ef6  lea     rdx, [rbp+57h+plsn2]; plsn2
0x1401d7efa  add     rcx, 50h ; 'P'; plsn1
0x1401d7efe  call    cs:__imp_ClfsLsnLess
0x1401d7f05  nop     dword ptr [rax+rax+00h]
0x1401d7f0a  test    al, al
0x1401d7f0c  jz      loc_1401D7FFE
0x1401d7f12  mov     rcx, [rbp+57h+ppvBuffer]
0x1401d7f16  test    byte ptr [rcx], 1
0x1401d7f19  jz      loc_1401D7FFE
0x1401d7f1f  cmp     dword ptr [rcx+4], 17h
0x1401d7f23  jnz     loc_1401D7FFE
0x1401d7f29  movzx   edx, word ptr [rsi+19Eh]
0x1401d7f30  cmp     edx, r12d
0x1401d7f33  jz      loc_1402CC8CA
0x1401d7f39  mov     rax, qword ptr [rbp+57h+plsn2]
0x1401d7f3d  mov     ebx, r13d
0x1401d7f40  mov     ecx, r12d
0x1401d7f43  inc     r12d
0x1401d7f46  mov     [r15+rcx*8], rax
0x1401d7f4a  mov     rax, [rbp+57h+ppvBuffer]
0x1401d7f4e  mov     rcx, [rax+50h]
0x1401d7f52  mov     qword ptr [rbp+57h+plsn2], rcx
0x1401d7f56  lea     rcx, [rbp+57h+plsn2]; plsn
0x1401d7f5a  call    cs:__imp_ClfsLsnNull
0x1401d7f61  nop     dword ptr [rax+rax+00h]
0x1401d7f66  test    al, al
0x1401d7f68  jz      loc_1401D7E3C
0x1401d7f6e  mov     r14b, 1
0x1401d7f71  jmp     loc_1401D8030
0x1401d7f76  call    NtfsPurgeFileRecordCache
0x1401d7f7b  bts     dword ptr [rdi+4], 9
0x1401d7f80  lea     rax, [rbp+57h+pvReadContext]
0x1401d7f84  mov     rcx, [rsi+0D0h]
0x1401d7f8b  lea     r9, [rbp+57h+ppvBuffer]; ppvReadBuffer
0x1401d7f8f  mov     [rsp+0D0h+ppvReadContext], rax; ppvReadContext
0x1401d7f94  lea     rdx, [rbp+57h+plsn2]; plsnFirst
0x1401d7f98  lea     rax, [rbp+57h+var_50]
0x1401d7f9c  mov     r8d, 2; peContextMode
0x1401d7fa2  mov     [rsp+0D0h+plsnRecord], rax; plsnPrevious
0x1401d7fa7  lea     rax, [rbp+57h+var_64+4]
0x1401d7fab  mov     rcx, [rcx+200h]; pvMarshalContext
0x1401d7fb2  mov     [rsp+0D0h+plsnPrevious], rax; plsnUndoNext
0x1401d7fb7  lea     rax, [rbp+57h+peRecordType]
0x1401d7fbb  mov     [rsp+0D0h+plsnUndoNext], rax; peRecordType
0x1401d7fc0  lea     rax, [rbp+57h+pcbBuffer]
0x1401d7fc4  mov     [rsp+0D0h+plsnUser], rax; pcbReadBuffer
0x1401d7fc9  call    cs:__imp_ClfsReadLogRecord
0x1401d7fd0  nop     dword ptr [rax+rax+00h]
0x1401d7fd5  and     dword ptr [rdi+1B4h], 0FFFFFFEFh
0x1401d7fdc  mov     ebx, eax
0x1401d7fde  btr     dword ptr [rdi+4], 9
0x1401d7fe3  test    eax, eax
0x1401d7fe5  js      loc_1401D7EBC
0x1401d7feb  mov     rcx, [rsi+0D0h]
0x1401d7ff2  lock inc dword ptr [rcx+210h]
0x1401d7ff9  jmp     loc_1401D7EBC
0x1401d7ffe  mov     al, cs:NtfsStatusDebugFlags
0x1401d8004  test    al, al
0x1401d8006  jz      short loc_1401D801A
0x1401d8008  mov     edx, 0C0190030h
0x1401d800d  xor     ecx, ecx
0x1401d800f  mov     r8d, 313DEFh
0x1401d8015  call    NtfsStatusTraceAndDebugInternal
0x1401d801a  mov     ebx, 0C0190030h
0x1401d801f  jmp     short loc_1401D8030
0x1401d8021  mov     r8d, 313E06h
0x1401d8027  mov     edx, ebx
0x1401d8029  xor     ecx, ecx
0x1401d802b  call    NtfsStatusTraceAndDebugInternal
0x1401d8030  cmp     [rbp+57h+pvReadContext], r13
0x1401d8034  jnz     loc_1401D8270
0x1401d803a  test    r14b, r14b
0x1401d803d  jz      loc_1401D819F
0x1401d8043  mov     r14d, r13d
0x1401d8046  cmp     r14d, r12d
0x1401d8049  jnb     loc_1401D8195
0x1401d804f  mov     eax, r12d
0x1401d8052  mov     [rbp+57h+ppvReadBuffer], r13
0x1401d8056  sub     eax, r14d
0x1401d8059  mov     [rbp+57h+pcbReadBuffer], r13d
0x1401d805d  dec     eax
0x1401d805f  mov     [rbp+57h+arg_10], r13b
0x1401d8063  mov     qword ptr [rbp+57h+var_40], r13
0x1401d8067  mov     qword ptr [rbp+57h+var_48], r13
0x1401d806b  mov     rcx, [r15+rax*8]
0x1401d806f  or      dword ptr [rdi+1B4h], 10h
0x1401d8076  mov     qword ptr [rbp+57h+plsn2], rcx
0x1401d807a  mov     rcx, rdi
0x1401d807d  call    NtfsPurgeFileRecordCache
0x1401d8082  bts     dword ptr [rdi+4], 9
0x1401d8087  lea     rax, [rbp+57h+pvReadContext]
0x1401d808b  mov     rcx, [rsi+0D0h]
0x1401d8092  lea     r9, [rbp+57h+ppvReadBuffer]; ppvReadBuffer
0x1401d8096  mov     [rsp+0D0h+ppvReadContext], rax; ppvReadContext
0x1401d809b  lea     rdx, [rbp+57h+plsn2]; plsnFirst
0x1401d809f  lea     rax, [rbp+57h+var_48]
0x1401d80a3  mov     r8d, 3; peContextMode
0x1401d80a9  mov     [rsp+0D0h+plsnRecord], rax; plsnPrevious
0x1401d80ae  lea     rax, [rbp+57h+var_40]
0x1401d80b2  mov     rcx, [rcx+200h]; pvMarshalContext
0x1401d80b9  mov     [rsp+0D0h+plsnPrevious], rax; plsnUndoNext
0x1401d80be  lea     rax, [rbp+57h+arg_10]
0x1401d80c2  mov     [rsp+0D0h+plsnUndoNext], rax; peRecordType
0x1401d80c7  lea     rax, [rbp+57h+pcbReadBuffer]
0x1401d80cb  mov     [rsp+0D0h+plsnUser], rax; pcbReadBuffer
0x1401d80d0  call    cs:__imp_ClfsReadLogRecord
0x1401d80d7  nop     dword ptr [rax+rax+00h]
0x1401d80dc  and     dword ptr [rdi+1B4h], 0FFFFFFEFh
0x1401d80e3  mov     ecx, 1
0x1401d80e8  btr     dword ptr [rdi+4], 9
0x1401d80ed  mov     ebx, eax
0x1401d80ef  test    eax, eax
0x1401d80f1  jns     loc_1401D82A9
0x1401d80f7  test    ebx, ebx
0x1401d80f9  jnz     loc_1401D82EF
0x1401d80ff  mov     edx, [rbp+57h+pcbReadBuffer]
0x1401d8102  mov     rcx, [rbp+57h+ppvReadBuffer]
0x1401d8106  call    TxfValidateLogRecord
0x1401d810b  test    al, al
0x1401d810d  jz      short loc_1401D8186
0x1401d810f  mov     r9, [rbp+57h+ppvReadBuffer]
0x1401d8113  test    byte ptr [r9], 1
0x1401d8117  jz      short loc_1401D8186
0x1401d8119  cmp     dword ptr [r9+4], 17h
0x1401d811e  jnz     short loc_1401D8186
0x1401d8120  mov     r8d, [r9+58h]
0x1401d8124  lea     rax, [rbp+57h+var_64]
0x1401d8128  add     r8, r9
0x1401d812b  mov     [rsp+0D0h+plsnUser], rax; __int64
0x1401d8130  movzx   r9d, word ptr [r9+5Ch]
0x1401d8135  mov     rdx, rsi
0x1401d8138  mov     rcx, rdi; int
0x1401d813b  call    TxfWriteUsnRecordsAtCommitHelper
0x1401d8140  mov     ebx, eax
0x1401d8142  test    eax, eax
0x1401d8144  js      loc_1401D82BC
0x1401d814a  mov     rcx, rdi
0x1401d814d  call    NtfsPurgeFileRecordCache
0x1401d8152  mov     rcx, [rbp+57h+pvReadContext]; pvCursorContext
0x1401d8156  bts     dword ptr [rdi+4], 9
0x1401d815b  call    cs:__imp_ClfsTerminateReadLog
0x1401d8162  nop     dword ptr [rax+rax+00h]
0x1401d8167  btr     dword ptr [rdi+4], 9
0x1401d816c  mov     rax, [rsi+0D0h]
0x1401d8173  lock dec dword ptr [rax+210h]
0x1401d817a  inc     r14d
0x1401d817d  mov     [rbp+57h+pvReadContext], r13
0x1401d8181  jmp     loc_1401D8046
0x1401d8186  mov     al, cs:NtfsStatusDebugFlags
0x1401d818c  test    al, al
0x1401d818e  jnz     short loc_1401D81BE
0x1401d8190  mov     ebx, 0C0190030h
0x1401d8195  cmp     [rbp+57h+pvReadContext], r13
0x1401d8199  jnz     loc_1401D8302
0x1401d819f  test    r15, r15
0x1401d81a2  jnz     short loc_1401D81AB
0x1401d81a4  mov     eax, ebx
0x1401d81a6  jmp     loc_1401D7DA9
0x1401d81ab  xor     edx, edx; Tag
0x1401d81ad  mov     rcx, r15; P
0x1401d81b0  call    cs:__imp_ExFreePoolWithTag
0x1401d81b7  nop     dword ptr [rax+rax+00h]
0x1401d81bc  jmp     short loc_1401D81A4
0x1401d81be  mov     edx, 0C0190030h
0x1401d81c3  xor     ecx, ecx
0x1401d81c5  mov     r8d, 313E95h
0x1401d81cb  call    NtfsStatusTraceAndDebugInternal
0x1401d81d0  jmp     short loc_1401D8190
0x1401d81d2  mov     al, cs:NtfsStatusDebugFlags
0x1401d81d8  mov     ebx, 0C000009Ah
0x1401d81dd  test    al, al
0x1401d81df  jz      short loc_1401D81A4
0x1401d81e1  mov     r8d, 313D7Dh
0x1401d81e7  mov     edx, ebx
0x1401d81e9  xor     ecx, ecx
0x1401d81eb  call    NtfsStatusTraceAndDebugInternal
0x1401d81f0  jmp     short loc_1401D81A4
0x1401d81f2  mov     al, cs:NtfsStatusDebugFlags
0x1401d81f8  mov     ebx, 0C000009Ah
0x1401d81fd  test    al, al
0x1401d81ff  jz      loc_1401D8030
0x1401d8205  jmp     loc_1401D8021
0x1401d820a  mov     al, cs:NtfsStatusDebugFlags
0x1401d8210  mov     ebx, 0C00000E5h
0x1401d8215  test    al, al
0x1401d8217  jz      loc_1401D8030
0x1401d821d  mov     r8d, 313DFEh
0x1401d8223  jmp     loc_1401D8027
0x1401d8228  add     word ptr [rsi+19Eh], 5
0x1401d8230  jmp     loc_1401D7DF0
0x1401d8235  movzx   r9d, word ptr [rsi+19Ah]
0x1401d823d  lea     rax, [rbp+57h+var_64]
0x1401d8241  mov     r8, [rsi+190h]
0x1401d8248  mov     rdx, rsi
0x1401d824b  mov     rcx, rdi; int
0x1401d824e  mov     [rsp+0D0h+plsnUser], rax; __int64
0x1401d8253  call    TxfWriteUsnRecordsAtCommitHelper
0x1401d8258  jmp     loc_1401D7DA9
0x1401d825d  mov     eax, [rsi+10h]
0x1401d8260  test    al, 20h
  ... truncated ...
```

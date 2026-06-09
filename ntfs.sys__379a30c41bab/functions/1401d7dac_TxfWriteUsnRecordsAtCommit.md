# TxfWriteUsnRecordsAtCommit

- ea: `0x1401d7dac`
- end: `0x1401d8387`
- name: `TxfWriteUsnRecordsAtCommit`
- size: `1499`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140133f80`
- `0x1401da26c`

## callees

- `0x140007ea0`
- `0x140010be0`
- `0x140059440`
- `0x140190bd0`
- `0x1401d7dac`
- `0x1401d912c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401d8200`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402cc969`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d8200`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402cc969`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d7e67`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402cc935`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d7e67`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402cc935`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d7de7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d7faa`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d7de7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d7faa`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1401d7e18`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1401d7e18`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d7f4e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d7f4e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d7ef2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d7ef2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d8019`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d8120`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d8019`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d8120`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d81ab`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d82d1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d8363`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d81ab`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d82d1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d8363`

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
  __int64 v18; // r8
  unsigned int i; // r14d
  CLFS_LSN v20; // rcx
  NTSTATUS v21; // eax
  __int64 v22; // r8
  int v23; // eax
  PVOID v24; // rcx
  PVOID v25; // rcx
  unsigned __int64 v26; // rax
  __int64 v27; // rdx
  PVOID v28; // rcx
  CLFS_LSN *v29; // rax
  CLFS_LSN *v30; // rbx
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rax
  __int64 v34; // rdx
  int v35; // edx
  unsigned __int64 v36; // rax
  __int64 v37; // rdx
  unsigned __int64 v38; // rax
  __int64 v39; // rdx
  int v40; // edx
  PVOID pvReadContext; // [rsp+50h] [rbp-29h] BYREF
  CLFS_LSN plsn2; // [rsp+58h] [rbp-21h] BYREF
  PVOID ppvBuffer; // [rsp+60h] [rbp-19h] BYREF
  ULONG pcbReadBuffer; // [rsp+68h] [rbp-11h] BYREF
  _DWORD plsnUndoNext[3]; // [rsp+6Ch] [rbp-Dh] BYREF
  PVOID ppvReadBuffer; // [rsp+78h] [rbp-1h] BYREF
  CLFS_LSN plsnPrevious; // [rsp+80h] [rbp+7h] BYREF
  CLFS_LSN v48; // [rsp+88h] [rbp+Fh] BYREF
  CLFS_LSN v49; // [rsp+90h] [rbp+17h] BYREF
  CLS_RECORD_TYPE peRecordType; // [rsp+E8h] [rbp+6Fh] BYREF
  CLS_RECORD_TYPE v51; // [rsp+F0h] [rbp+77h] BYREF
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
    return TxfWriteUsnRecordsAtCommitHelper(a1, (__int64)plsnUndoNext);
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
      if ( !(unsigned __int8)TxfValidateLogRecord(ppvBuffer, pcbBuffer, 2097219)
        || !ClfsLsnLess((const CLFS_LSN *)ppvBuffer + 10, &plsn2)
        || (*(_BYTE *)ppvBuffer & 1) == 0
        || *((_DWORD *)ppvBuffer + 1) != 23 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3222863920LL, 3227119);
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
        v29 = (CLFS_LSN *)ExAllocatePoolWithTag(PoolType, 16 * v15, 0x31667854u);
        v30 = v29;
        if ( !v29 )
        {
          v11 = -1073741670;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_26;
          v18 = 3227142;
          goto LABEL_25;
        }
        memmove(v29, PoolWithTag, 8LL * *(unsigned __int16 *)(a2 + 414));
        ExFreePoolWithTag(PoolWithTag, 0);
        PoolWithTag = v30;
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
    else if ( v11 == -1073741801 || (v31 = v11 + 1073741697, (unsigned int)v31 <= 0x22) && _bittest64(&v12, v31) )
    {
      ++HIDWORD((*TxfData)[1]);
    }
    else if ( v11 == -1072037845
           || v11 == -1073741202
           || v11 == -1073741435
           || v11 == -1073741496
           || (v32 = v11 + 1073741667, (unsigned int)v32 <= 0x23) && _bittest64(&v13, v32)
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
      v25 = pvReadContext;
      *(_DWORD *)(a1 + 4) |= 0x200u;
      ClfsTerminateReadLog(v25);
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
        v51 = 0;
        v49.ullOffset = 0;
        v48.ullOffset = 0;
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
                &v51,
                &v49,
                &v48,
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
                 || (v36 = (unsigned int)(v21 + 1073741697), (unsigned int)v36 <= 0x22)
                 && (v37 = 0x408000001LL, _bittest64(&v37, v36)) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( v11 == -1072037845
                 || v11 == -1073741202
                 || v11 == -1073741435
                 || v11 == -1073741496
                 || (v38 = v11 + 1073741667, (unsigned int)v38 <= 0x23) && (v39 = 0x800000041LL, _bittest64(&v39, v38))
                 || v11 + 1073741811 <= 0x15 && (v40 = 2097219, _bittest(&v40, v11 + 1073741811))
                 || v11 == -2147483626
                 || v11 == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          break;
        }
        if ( !(unsigned __int8)TxfValidateLogRecord(ppvReadBuffer, pcbReadBuffer, v22)
          || (*(_BYTE *)ppvReadBuffer & 1) == 0
          || *((_DWORD *)ppvReadBuffer + 1) != 23 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3222863920LL, 3227285);
          v11 = -1072103376;
          break;
        }
        v23 = TxfWriteUsnRecordsAtCommitHelper(a1, (__int64)plsnUndoNext);
        v11 = v23;
        if ( v23 < 0 )
        {
          if ( v23 == -1073741801
            || (v26 = (unsigned int)(v23 + 1073741697), (unsigned int)v26 <= 0x22)
            && (v27 = 0x408000001LL, _bittest64(&v27, v26)) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( v11 == -1072037845
                 || v11 == -1073741202
                 || v11 == -1073741435
                 || v11 == -1073741496
                 || (v33 = v11 + 1073741667, (unsigned int)v33 <= 0x23) && (v34 = 0x800000041LL, _bittest64(&v34, v33))
                 || v11 + 1073741811 <= 0x15 && (v35 = 2097219, _bittest(&v35, v11 + 1073741811))
                 || v11 == -2147483626
                 || v11 == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          break;
        }
        NtfsPurgeFileRecordCache(a1);
        v24 = pvReadContext;
        *(_DWORD *)(a1 + 4) |= 0x200u;
        ClfsTerminateReadLog(v24);
        *(_DWORD *)(a1 + 4) &= ~0x200u;
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 208) + 528LL));
        pvReadContext = 0;
      }
      if ( pvReadContext )
      {
        NtfsPurgeFileRecordCache(a1);
        v28 = pvReadContext;
        *(_DWORD *)(a1 + 4) |= 0x200u;
        ClfsTerminateReadLog(v28);
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
      NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 3227005);
  }
  return v11;
}

```

## disassembly

```asm
0x1401d7dac  mov     [rsp-8+arg_0], rbx
0x1401d7db1  push    rbp
0x1401d7db2  push    rsi
0x1401d7db3  push    rdi
0x1401d7db4  push    r12
0x1401d7db6  push    r13
0x1401d7db8  push    r14
0x1401d7dba  push    r15
0x1401d7dbc  lea     rbp, [rsp-27h]
0x1401d7dc1  sub     rsp, 0A0h
0x1401d7dc8  xor     r13d, r13d
0x1401d7dcb  lea     rbx, [rdx+180h]
0x1401d7dd2  mov     rdi, rcx
0x1401d7dd5  mov     dword ptr [rbp+57h+var_64], r13d
0x1401d7dd9  mov     rcx, rbx; plsn
0x1401d7ddc  mov     qword ptr [rbp+57h+plsn2], r13
0x1401d7de0  mov     rsi, rdx
0x1401d7de3  mov     [rbp+57h+pvReadContext], r13
0x1401d7de7  call    cs:__imp_ClfsLsnNull
0x1401d7dee  nop     dword ptr [rax+rax+00h]
0x1401d7df3  test    al, al
0x1401d7df5  jz      short loc_1401D7E15
0x1401d7df7  xor     eax, eax
0x1401d7df9  mov     rbx, [rsp+0D0h+arg_0]
0x1401d7e01  add     rsp, 0A0h
0x1401d7e08  pop     r15
0x1401d7e0a  pop     r14
0x1401d7e0c  pop     r13
0x1401d7e0e  pop     r12
0x1401d7e10  pop     rdi
0x1401d7e11  pop     rsi
0x1401d7e12  pop     rbp
0x1401d7e13  retn
0x1401d7e15  mov     rcx, rbx; plsn
0x1401d7e18  call    cs:__imp_ClfsLsnInvalid
0x1401d7e1f  nop     dword ptr [rax+rax+00h]
0x1401d7e24  test    al, al
0x1401d7e26  jnz     short loc_1401D7DF7
0x1401d7e28  mov     rax, [rdi+68h]
0x1401d7e2c  test    dword ptr [rax+4], 80000h
0x1401d7e33  jz      short loc_1401D7DF7
0x1401d7e35  mov     eax, [rsi+10h]
0x1401d7e38  test    al, 20h
0x1401d7e3a  jnz     loc_1401D8278
0x1401d7e40  movzx   eax, word ptr [rsi+19Eh]
0x1401d7e47  mov     ecx, 1
0x1401d7e4c  cmp     ax, cx
0x1401d7e4f  jz      loc_1401D8285
0x1401d7e55  mov     ecx, cs:PoolType; PoolType
0x1401d7e5b  mov     edx, eax
0x1401d7e5d  shl     rdx, 3; NumberOfBytes
0x1401d7e61  mov     r8d, 31667854h; Tag
0x1401d7e67  call    cs:__imp_ExAllocatePoolWithTag
0x1401d7e6e  nop     dword ptr [rax+rax+00h]
0x1401d7e73  mov     r15, rax
0x1401d7e76  test    rax, rax
0x1401d7e79  jz      loc_1401D8222
0x1401d7e7f  mov     rax, [rbx]
0x1401d7e82  mov     r12d, r13d
0x1401d7e85  mov     qword ptr [rbp+57h+plsn2], rax
0x1401d7e89  mov     r14b, r13b
0x1401d7e8c  mov     [rbp+57h+ppvBuffer], r13
0x1401d7e90  mov     rcx, rdi
0x1401d7e93  mov     [rbp+57h+pcbBuffer], r13d
0x1401d7e97  mov     [rbp+57h+peRecordType], r13b
0x1401d7e9b  mov     qword ptr [rbp+57h+var_64+4], r13
0x1401d7e9f  mov     qword ptr [rbp+57h+var_50], r13
0x1401d7ea3  or      dword ptr [rdi+1B4h], 10h
0x1401d7eaa  cmp     [rbp+57h+pvReadContext], r13
0x1401d7eae  jz      loc_1401D7FC6
0x1401d7eb4  call    NtfsPurgeFileRecordCache
0x1401d7eb9  mov     rcx, [rbp+57h+pvReadContext]; pvReadContext
0x1401d7ebd  lea     rax, [rbp+57h+var_64+4]
0x1401d7ec1  bts     dword ptr [rdi+4], 9
0x1401d7ec6  lea     r9, [rbp+57h+peRecordType]; peRecordType
0x1401d7eca  mov     [rsp+0D0h+plsnRecord], rax; plsnRecord
0x1401d7ecf  lea     r8, [rbp+57h+pcbBuffer]; pcbBuffer
0x1401d7ed3  lea     rax, [rbp+57h+var_50]
0x1401d7ed7  mov     [rsp+0D0h+plsnPrevious], rax; plsnPrevious
0x1401d7edc  lea     rdx, [rbp+57h+ppvBuffer]; ppvBuffer
0x1401d7ee0  lea     rax, [rbp+57h+var_64+4]
0x1401d7ee4  mov     [rsp+0D0h+plsnUndoNext], rax; plsnUndoNext
0x1401d7ee9  lea     rax, [rbp+57h+plsn2]
0x1401d7eed  mov     [rsp+0D0h+plsnUser], rax; plsnUser
0x1401d7ef2  call    cs:__imp_ClfsReadNextLogRecord
0x1401d7ef9  nop     dword ptr [rax+rax+00h]
0x1401d7efe  and     dword ptr [rdi+1B4h], 0FFFFFFEFh
0x1401d7f05  mov     ebx, eax
0x1401d7f07  btr     dword ptr [rdi+4], 9
0x1401d7f0c  mov     rcx, 408000001h
0x1401d7f16  mov     rdx, 800000041h
0x1401d7f20  mov     r8d, 200043h
0x1401d7f26  test    ebx, ebx
0x1401d7f28  jnz     loc_1401D82AD
0x1401d7f2e  mov     edx, [rbp+57h+pcbBuffer]
0x1401d7f31  mov     rcx, [rbp+57h+ppvBuffer]
0x1401d7f35  call    TxfValidateLogRecord
0x1401d7f3a  test    al, al
0x1401d7f3c  jz      loc_1401D804E
0x1401d7f42  mov     rcx, [rbp+57h+ppvBuffer]
0x1401d7f46  lea     rdx, [rbp+57h+plsn2]; plsn2
0x1401d7f4a  add     rcx, 50h ; 'P'; plsn1
0x1401d7f4e  call    cs:__imp_ClfsLsnLess
0x1401d7f55  nop     dword ptr [rax+rax+00h]
0x1401d7f5a  test    al, al
0x1401d7f5c  jz      loc_1401D804E
0x1401d7f62  mov     rcx, [rbp+57h+ppvBuffer]
0x1401d7f66  test    byte ptr [rcx], 1
0x1401d7f69  jz      loc_1401D804E
0x1401d7f6f  cmp     dword ptr [rcx+4], 17h
0x1401d7f73  jnz     loc_1401D804E
0x1401d7f79  movzx   edx, word ptr [rsi+19Eh]
0x1401d7f80  cmp     edx, r12d
0x1401d7f83  jz      loc_1402CC91A
0x1401d7f89  mov     rax, qword ptr [rbp+57h+plsn2]
0x1401d7f8d  mov     ebx, r13d
0x1401d7f90  mov     ecx, r12d
0x1401d7f93  inc     r12d
0x1401d7f96  mov     [r15+rcx*8], rax
0x1401d7f9a  mov     rax, [rbp+57h+ppvBuffer]
0x1401d7f9e  mov     rcx, [rax+50h]
0x1401d7fa2  mov     qword ptr [rbp+57h+plsn2], rcx
0x1401d7fa6  lea     rcx, [rbp+57h+plsn2]; plsn
0x1401d7faa  call    cs:__imp_ClfsLsnNull
0x1401d7fb1  nop     dword ptr [rax+rax+00h]
0x1401d7fb6  test    al, al
0x1401d7fb8  jz      loc_1401D7E8C
0x1401d7fbe  mov     r14b, 1
0x1401d7fc1  jmp     loc_1401D8080
0x1401d7fc6  call    NtfsPurgeFileRecordCache
0x1401d7fcb  bts     dword ptr [rdi+4], 9
0x1401d7fd0  lea     rax, [rbp+57h+pvReadContext]
0x1401d7fd4  mov     rcx, [rsi+0D0h]
0x1401d7fdb  lea     r9, [rbp+57h+ppvBuffer]; ppvReadBuffer
0x1401d7fdf  mov     [rsp+0D0h+ppvReadContext], rax; ppvReadContext
0x1401d7fe4  lea     rdx, [rbp+57h+plsn2]; plsnFirst
0x1401d7fe8  lea     rax, [rbp+57h+var_50]
0x1401d7fec  mov     r8d, 2; peContextMode
0x1401d7ff2  mov     [rsp+0D0h+plsnRecord], rax; plsnPrevious
0x1401d7ff7  lea     rax, [rbp+57h+var_64+4]
0x1401d7ffb  mov     rcx, [rcx+200h]; pvMarshalContext
0x1401d8002  mov     [rsp+0D0h+plsnPrevious], rax; plsnUndoNext
0x1401d8007  lea     rax, [rbp+57h+peRecordType]
0x1401d800b  mov     [rsp+0D0h+plsnUndoNext], rax; peRecordType
0x1401d8010  lea     rax, [rbp+57h+pcbBuffer]
0x1401d8014  mov     [rsp+0D0h+plsnUser], rax; pcbReadBuffer
0x1401d8019  call    cs:__imp_ClfsReadLogRecord
0x1401d8020  nop     dword ptr [rax+rax+00h]
0x1401d8025  and     dword ptr [rdi+1B4h], 0FFFFFFEFh
0x1401d802c  mov     ebx, eax
0x1401d802e  btr     dword ptr [rdi+4], 9
0x1401d8033  test    eax, eax
0x1401d8035  js      loc_1401D7F0C
0x1401d803b  mov     rcx, [rsi+0D0h]
0x1401d8042  lock inc dword ptr [rcx+210h]
0x1401d8049  jmp     loc_1401D7F0C
0x1401d804e  mov     al, cs:NtfsStatusDebugFlags
0x1401d8054  test    al, al
0x1401d8056  jz      short loc_1401D806A
0x1401d8058  mov     edx, 0C0190030h
0x1401d805d  xor     ecx, ecx
0x1401d805f  mov     r8d, 313DEFh
0x1401d8065  call    NtfsStatusTraceAndDebugInternal
0x1401d806a  mov     ebx, 0C0190030h
0x1401d806f  jmp     short loc_1401D8080
0x1401d8071  mov     r8d, 313E06h
0x1401d8077  mov     edx, ebx
0x1401d8079  xor     ecx, ecx
0x1401d807b  call    NtfsStatusTraceAndDebugInternal
0x1401d8080  cmp     [rbp+57h+pvReadContext], r13
0x1401d8084  jnz     loc_1401D82C0
0x1401d808a  test    r14b, r14b
0x1401d808d  jz      loc_1401D81EF
0x1401d8093  mov     r14d, r13d
0x1401d8096  cmp     r14d, r12d
0x1401d8099  jnb     loc_1401D81E5
0x1401d809f  mov     eax, r12d
0x1401d80a2  mov     [rbp+57h+ppvReadBuffer], r13
0x1401d80a6  sub     eax, r14d
0x1401d80a9  mov     [rbp+57h+pcbReadBuffer], r13d
0x1401d80ad  dec     eax
0x1401d80af  mov     [rbp+57h+arg_10], r13b
0x1401d80b3  mov     qword ptr [rbp+57h+var_40], r13
0x1401d80b7  mov     qword ptr [rbp+57h+var_48], r13
0x1401d80bb  mov     rcx, [r15+rax*8]
0x1401d80bf  or      dword ptr [rdi+1B4h], 10h
0x1401d80c6  mov     qword ptr [rbp+57h+plsn2], rcx
0x1401d80ca  mov     rcx, rdi
0x1401d80cd  call    NtfsPurgeFileRecordCache
0x1401d80d2  bts     dword ptr [rdi+4], 9
0x1401d80d7  lea     rax, [rbp+57h+pvReadContext]
0x1401d80db  mov     rcx, [rsi+0D0h]
0x1401d80e2  lea     r9, [rbp+57h+ppvReadBuffer]; ppvReadBuffer
0x1401d80e6  mov     [rsp+0D0h+ppvReadContext], rax; ppvReadContext
0x1401d80eb  lea     rdx, [rbp+57h+plsn2]; plsnFirst
0x1401d80ef  lea     rax, [rbp+57h+var_48]
0x1401d80f3  mov     r8d, 3; peContextMode
0x1401d80f9  mov     [rsp+0D0h+plsnRecord], rax; plsnPrevious
0x1401d80fe  lea     rax, [rbp+57h+var_40]
0x1401d8102  mov     rcx, [rcx+200h]; pvMarshalContext
0x1401d8109  mov     [rsp+0D0h+plsnPrevious], rax; plsnUndoNext
0x1401d810e  lea     rax, [rbp+57h+arg_10]
0x1401d8112  mov     [rsp+0D0h+plsnUndoNext], rax; peRecordType
0x1401d8117  lea     rax, [rbp+57h+pcbReadBuffer]
0x1401d811b  mov     [rsp+0D0h+plsnUser], rax; pcbReadBuffer
0x1401d8120  call    cs:__imp_ClfsReadLogRecord
0x1401d8127  nop     dword ptr [rax+rax+00h]
0x1401d812c  and     dword ptr [rdi+1B4h], 0FFFFFFEFh
0x1401d8133  mov     ecx, 1
0x1401d8138  btr     dword ptr [rdi+4], 9
0x1401d813d  mov     ebx, eax
0x1401d813f  test    eax, eax
0x1401d8141  jns     loc_1401D82F9
0x1401d8147  test    ebx, ebx
0x1401d8149  jnz     loc_1401D833F
0x1401d814f  mov     edx, [rbp+57h+pcbReadBuffer]
0x1401d8152  mov     rcx, [rbp+57h+ppvReadBuffer]
0x1401d8156  call    TxfValidateLogRecord
0x1401d815b  test    al, al
0x1401d815d  jz      short loc_1401D81D6
0x1401d815f  mov     r9, [rbp+57h+ppvReadBuffer]
0x1401d8163  test    byte ptr [r9], 1
0x1401d8167  jz      short loc_1401D81D6
0x1401d8169  cmp     dword ptr [r9+4], 17h
0x1401d816e  jnz     short loc_1401D81D6
0x1401d8170  mov     r8d, [r9+58h]
0x1401d8174  lea     rax, [rbp+57h+var_64]
0x1401d8178  add     r8, r9
0x1401d817b  mov     [rsp+0D0h+plsnUser], rax; __int64
0x1401d8180  movzx   r9d, word ptr [r9+5Ch]
0x1401d8185  mov     rdx, rsi
0x1401d8188  mov     rcx, rdi; int
0x1401d818b  call    TxfWriteUsnRecordsAtCommitHelper
0x1401d8190  mov     ebx, eax
0x1401d8192  test    eax, eax
0x1401d8194  js      loc_1401D830C
0x1401d819a  mov     rcx, rdi
0x1401d819d  call    NtfsPurgeFileRecordCache
0x1401d81a2  mov     rcx, [rbp+57h+pvReadContext]; pvCursorContext
0x1401d81a6  bts     dword ptr [rdi+4], 9
0x1401d81ab  call    cs:__imp_ClfsTerminateReadLog
0x1401d81b2  nop     dword ptr [rax+rax+00h]
0x1401d81b7  btr     dword ptr [rdi+4], 9
0x1401d81bc  mov     rax, [rsi+0D0h]
0x1401d81c3  lock dec dword ptr [rax+210h]
0x1401d81ca  inc     r14d
0x1401d81cd  mov     [rbp+57h+pvReadContext], r13
0x1401d81d1  jmp     loc_1401D8096
0x1401d81d6  mov     al, cs:NtfsStatusDebugFlags
0x1401d81dc  test    al, al
0x1401d81de  jnz     short loc_1401D820E
0x1401d81e0  mov     ebx, 0C0190030h
0x1401d81e5  cmp     [rbp+57h+pvReadContext], r13
0x1401d81e9  jnz     loc_1401D8352
0x1401d81ef  test    r15, r15
0x1401d81f2  jnz     short loc_1401D81FB
0x1401d81f4  mov     eax, ebx
0x1401d81f6  jmp     loc_1401D7DF9
0x1401d81fb  xor     edx, edx; Tag
0x1401d81fd  mov     rcx, r15; P
0x1401d8200  call    cs:__imp_ExFreePoolWithTag
0x1401d8207  nop     dword ptr [rax+rax+00h]
0x1401d820c  jmp     short loc_1401D81F4
0x1401d820e  mov     edx, 0C0190030h
0x1401d8213  xor     ecx, ecx
0x1401d8215  mov     r8d, 313E95h
0x1401d821b  call    NtfsStatusTraceAndDebugInternal
0x1401d8220  jmp     short loc_1401D81E0
0x1401d8222  mov     al, cs:NtfsStatusDebugFlags
0x1401d8228  mov     ebx, 0C000009Ah
0x1401d822d  test    al, al
0x1401d822f  jz      short loc_1401D81F4
0x1401d8231  mov     r8d, 313D7Dh
0x1401d8237  mov     edx, ebx
0x1401d8239  xor     ecx, ecx
0x1401d823b  call    NtfsStatusTraceAndDebugInternal
0x1401d8240  jmp     short loc_1401D81F4
0x1401d8242  mov     al, cs:NtfsStatusDebugFlags
0x1401d8248  mov     ebx, 0C000009Ah
0x1401d824d  test    al, al
0x1401d824f  jz      loc_1401D8080
0x1401d8255  jmp     loc_1401D8071
0x1401d825a  mov     al, cs:NtfsStatusDebugFlags
0x1401d8260  mov     ebx, 0C00000E5h
0x1401d8265  test    al, al
0x1401d8267  jz      loc_1401D8080
0x1401d826d  mov     r8d, 313DFEh
0x1401d8273  jmp     loc_1401D8077
0x1401d8278  add     word ptr [rsi+19Eh], 5
0x1401d8280  jmp     loc_1401D7E40
0x1401d8285  movzx   r9d, word ptr [rsi+19Ah]
0x1401d828d  lea     rax, [rbp+57h+var_64]
0x1401d8291  mov     r8, [rsi+190h]
0x1401d8298  mov     rdx, rsi
0x1401d829b  mov     rcx, rdi; int
0x1401d829e  mov     [rsp+0D0h+plsnUser], rax; __int64
0x1401d82a3  call    TxfWriteUsnRecordsAtCommitHelper
0x1401d82a8  jmp     loc_1401D7DF9
0x1401d82ad  mov     eax, [rsi+10h]
0x1401d82b0  test    al, 20h
  ... truncated ...
```

# TxfFlushUndoPriorToDiskWrite

- ea: `0x140208f3c`
- end: `0x140209506`
- name: `TxfFlushUndoPriorToDiskWrite`
- size: `1482`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1400177d0`
- `0x14010adfc`
- `0x140268608`
- `0x140296da4`

## callees

- `0x140007ea0`
- `0x14002f45c`
- `0x14002f6d8`
- `0x140034560`
- `0x140059250`
- `0x1400b6e90`
- `0x14018a850`
- `0x140208f3c`
- `0x140209910`
- `0x140214de8`

## import_xrefs

- `ntoskrnl!CcPinRead` at `0x14020935e`
- `ntoskrnl!CcPinRead` at `0x14020935e`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x1402090bc`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x1402090bc`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402092cb`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402092cb`
- `ntoskrnl!CcUnpinData` at `0x14020939c`
- `ntoskrnl!CcUnpinData` at `0x14020939c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402093f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b3c37`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ce7fc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402093f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b3c37`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ce7fc`
- `ntoskrnl!ExAcquireFastMutex` at `0x14020906f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140209473`
- `ntoskrnl!ExAcquireFastMutex` at `0x14020906f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140209473`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402090db`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020928f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402090db`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020928f`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1402090f8`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14020911e`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1402090f8`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14020911e`
- `ntoskrnl!ExRaiseStatus` at `0x140209106`
- `ntoskrnl!ExRaiseStatus` at `0x14020912c`
- `ntoskrnl!ExRaiseStatus` at `0x140209106`
- `ntoskrnl!ExRaiseStatus` at `0x14020912c`
- `ntoskrnl!CcFlushCache` at `0x14020938b`
- `ntoskrnl!CcFlushCache` at `0x14020938b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140209271`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140209271`

## pseudocode

```c
void __fastcall TxfFlushUndoPriorToDiskWrite(_DWORD *a1, __int64 a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v5; // r15
  __int64 v7; // r12
  _QWORD *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // r14
  _QWORD *v11; // r13
  ULONG i; // eax
  const CLFS_LSN *v13; // rax
  const CLFS_LSN *v14; // r12
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  unsigned __int64 v17; // r8
  __int64 v18; // rdx
  CLFS_LSN *v19; // r15
  CLFS_LSN v20; // rbx
  ULONGLONG v21; // rax
  char v22; // r15
  __int64 j; // rcx
  __int64 v24; // rdx
  __int64 k; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 m; // rdx
  char v29; // [rsp+40h] [rbp-E8h]
  int v30; // [rsp+44h] [rbp-E4h]
  ULONG DeleteCount; // [rsp+54h] [rbp-D4h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+58h] [rbp-D0h] BYREF
  PVOID Bcb; // [rsp+60h] [rbp-C8h] BYREF
  _QWORD *v34; // [rsp+68h] [rbp-C0h]
  _QWORD *v35; // [rsp+70h] [rbp-B8h]
  __int64 v36; // [rsp+78h] [rbp-B0h]
  NTSTATUS Exception[4]; // [rsp+80h] [rbp-A8h] BYREF
  int v38; // [rsp+90h] [rbp-98h]
  PVOID RestartKey; // [rsp+98h] [rbp-90h] BYREF
  PVOID v40[2]; // [rsp+A0h] [rbp-88h] BYREF
  __int128 MatchData; // [rsp+B0h] [rbp-78h] BYREF
  __int128 v42; // [rsp+C0h] [rbp-68h]
  __int128 v43; // [rsp+D0h] [rbp-58h]
  int v44; // [rsp+E0h] [rbp-48h]

  v5 = a3;
  v40[1] = a1;
  v7 = *(_QWORD *)(a2 + 24);
  MatchData = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  FileOffset.QuadPart = 0;
  DeleteCount = 0;
  *(_OWORD *)Exception = 0;
  v36 = 0;
  v35 = 0;
  v30 = -1;
  RestartKey = 0;
  Bcb = 0;
  v40[0] = 0;
  v29 = 0;
  v8 = 0;
  v34 = 0;
  LOBYTE(a3) = 1;
  v9 = TxfCurrentWritableVersion(*(_QWORD *)(v7 + 528), 0, a3);
  v10 = v9;
  v36 = v9;
  if ( v9 && (*(_DWORD *)(v9 + 8) & 1) == 0 )
  {
    v11 = *(_QWORD **)(*(_QWORD *)(v7 + 184) + 320LL);
    v35 = v11;
    v8 = v11 + 35;
    v34 = v11 + 35;
    LfsFlushToLsn(*(_QWORD *)(v11[2] + 232LL), v11[45]);
    if ( *(_BYTE *)(v7 + 460) )
    {
      v17 = v5;
      v18 = -*(_DWORD *)(v7 + 452);
      v5 &= v18;
      a4 = (v18 & (v17 + *(_DWORD *)(v7 + 452) - 1 + a4)) - v5;
    }
    *(_QWORD *)&MatchData = v5 >> 12;
    DWORD2(v42) = (a4 + 4095) >> 12;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(v10 + 256));
    for ( i = 0; ; i = 1 )
    {
      v13 = (const CLFS_LSN *)RtlEnumerateGenericTableLikeADirectory(
                                (PRTL_AVL_TABLE)(v10 + 152),
                                TxfMatchPageRange,
                                &MatchData,
                                i,
                                &RestartKey,
                                &DeleteCount,
                                &MatchData);
      v14 = v13;
      if ( !v13 )
        break;
      v19 = (CLFS_LSN *)&v13[2];
      if ( !ClfsLsnInvalid(v13 + 2) )
      {
        v20 = *v19;
        ExReleaseFastMutex(*(PFAST_MUTEX *)(v10 + 256));
        v21 = v14[1].ullOffset >> 4;
        if ( (_DWORD)v21 != v30 )
        {
          v30 = v14[1].ullOffset >> 4;
          FileOffset.QuadPart = (unsigned int)((_DWORD)v21 << 16);
          v22 = v29;
          if ( !v29 && !ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(*v8 + 16LL)) )
          {
            v22 = NtfsAcquireScbPagingResourceShared(a1, *v8);
            v29 = v22;
            for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
            {
              v24 = *(_QWORD *)&a1[2 * j + 12];
              if ( !v24 || v24 == *(_QWORD *)(*v8 + 184LL) )
              {
                *(_QWORD *)&a1[2 * (unsigned int)j + 12] = *(_QWORD *)(*v8 + 184LL);
                break;
              }
            }
          }
          CcPinRead(*(PFILE_OBJECT *)(*v8 + 280LL), &FileOffset, 0x10000u, 5u, &Bcb, v40);
          CcFlushCache(
            (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*v8 + 288LL) + 16LL),
            &FileOffset,
            0x10000u,
            (PIO_STATUS_BLOCK)Exception);
          CcUnpinData(Bcb);
          Bcb = 0;
          if ( v22 )
          {
            if ( a1 )
            {
              for ( k = 0; (unsigned int)k < 2; k = (unsigned int)(k + 1) )
              {
                if ( *(_QWORD *)&a1[2 * k + 12] == *(_QWORD *)(*v8 + 184LL) )
                  *(_QWORD *)&a1[2 * k + 12] = 0;
              }
            }
            ExReleaseResourceLite(*(PERESOURCE *)(*v8 + 16LL));
            v29 = 0;
          }
          v26 = (unsigned int)Exception[0];
          if ( Exception[0] < 0 )
          {
            a1[6] = Exception[0];
            if ( NtfsStatusDebugFlags
              && (_DWORD)v26
              && (_DWORD)v26 != 294
              && (unsigned int)(v26 - 298) > 1
              && (unsigned int)v26 < 0xFFFFFFED
              && (_DWORD)v26 != -1073741608
              && (_DWORD)v26 != -1073741802
              && (_DWORD)v26 != -1073741807
              && (unsigned int)(v26 + 2147483643) > 1
              && (_DWORD)v26 != 259 )
            {
              NtfsStatusTraceAndDebugInternal(a1, v26, 3411316);
            }
            v15 = FsRtlNormalizeNtstatus(Exception[0], -1073741591);
            ExRaiseStatus(v15);
          }
          v38 = v30;
          v19 = (CLFS_LSN *)&v14[2];
        }
        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 16) + 64LL) + 4LL) & 0x1000) == 0
          && (unsigned __int8)TxfTryEnterFlushSyncRegion(v11) )
        {
          ((void (__fastcall *)(_QWORD, _QWORD))TxfFlushToLsn)(v11, (CLFS_LSN)v20.ullOffset);
          TxfLeaveFlushSyncRegion(v11);
        }
        v27 = (unsigned int)Exception[0];
        if ( Exception[0] < 0 )
        {
          a1[6] = Exception[0];
          if ( NtfsStatusDebugFlags
            && (_DWORD)v27
            && (_DWORD)v27 != 294
            && (unsigned int)(v27 - 298) > 1
            && (unsigned int)v27 < 0xFFFFFFED
            && (_DWORD)v27 != -1073741608
            && (_DWORD)v27 != -1073741802
            && (_DWORD)v27 != -1073741807
            && (unsigned int)(v27 + 2147483643) > 1
            && (_DWORD)v27 != 259 )
          {
            NtfsStatusTraceAndDebugInternal(a1, v27, 3411346);
          }
          v16 = FsRtlNormalizeNtstatus(Exception[0], -1073741591);
          ExRaiseStatus(v16);
        }
        ExAcquireFastMutex(*(PFAST_MUTEX *)(v10 + 256));
        BYTE6(v14[3].ullOffset) |= 0x20u;
        *v19 = CLFS_LSN_INVALID_EXT;
      }
      DWORD2(v42) += MatchData - v14->offset.idxRecord;
      *(CLFS_LSN *)&MatchData = *v14;
    }
    ExReleaseFastMutex(*(PFAST_MUTEX *)(v10 + 256));
  }
  if ( v29 )
  {
    if ( a1 )
    {
      for ( m = 0; m != 2; ++m )
      {
        if ( *(_QWORD *)&a1[2 * m + 12] == *(_QWORD *)(*v8 + 184LL) )
          *(_QWORD *)&a1[2 * m + 12] = 0;
      }
    }
    ExReleaseResourceLite(*(PERESOURCE *)(*v8 + 16LL));
  }
  if ( v10 )
    TxfDereferenceTxfVscb((PVOID)v10);
}

```

## disassembly

```asm
0x140208f3c  mov     r11, rsp
0x140208f3f  push    rbx
0x140208f40  push    rsi
0x140208f41  push    rdi
0x140208f42  push    r12
0x140208f44  push    r13
0x140208f46  push    r14
0x140208f48  push    r15
0x140208f4a  sub     rsp, 0F0h
0x140208f51  mov     rax, cs:__security_cookie
0x140208f58  xor     rax, rsp
0x140208f5b  mov     [rsp+128h+var_40], rax
0x140208f63  mov     rbx, r9
0x140208f66  mov     r15, r8
0x140208f69  mov     rdi, rcx
0x140208f6c  mov     [rsp+128h+var_80], rcx
0x140208f74  mov     r12, [rdx+18h]
0x140208f78  xorps   xmm0, xmm0
0x140208f7b  xor     eax, eax
0x140208f7d  movups  xmmword ptr [r11-78h], xmm0
0x140208f82  movups  xmmword ptr [r11-68h], xmm0
0x140208f87  movups  xmmword ptr [r11-58h], xmm0
0x140208f8c  mov     [r11-48h], eax
0x140208f90  mov     qword ptr [rsp+128h+FileOffset], rax
0x140208f95  mov     [rsp+128h+var_D4], eax
0x140208f99  movups  xmmword ptr [rsp+128h+Exception], xmm0
0x140208fa1  mov     [rsp+128h+var_B0], rax
0x140208fa6  mov     [rsp+128h+var_B8], rax
0x140208fab  mov     [rsp+128h+var_E4], 0FFFFFFFFh
0x140208fb3  mov     [r11-90h], rax
0x140208fba  mov     [rsp+128h+NextFlag], eax
0x140208fbe  mov     [rsp+128h+Bcb], rax
0x140208fc3  mov     [r11-88h], rax
0x140208fca  mov     [rsp+128h+var_E8], al
0x140208fce  mov     [rsp+128h+var_E7], al
0x140208fd2  mov     esi, eax
0x140208fd4  mov     [rsp+128h+var_C0], rax
0x140208fd9  mov     r8b, 1
0x140208fdc  xor     edx, edx
0x140208fde  mov     rcx, [r12+210h]
0x140208fe6  call    TxfCurrentWritableVersion
0x140208feb  mov     r14, rax
0x140208fee  mov     [rsp+128h+var_B0], rax
0x140208ff3  test    rax, rax
0x140208ff6  jz      loc_1402094B7
0x140208ffc  mov     eax, [rax+8]
0x140208fff  test    al, 1
0x140209001  jnz     loc_1402094B7
0x140209007  mov     rax, [r12+0B8h]
0x14020900f  mov     r13, [rax+140h]
0x140209016  mov     [rsp+128h+var_B8], r13
0x14020901b  lea     rsi, [r13+118h]
0x140209022  mov     [rsp+128h+var_C0], rsi
0x140209027  mov     rcx, [r13+10h]
0x14020902b  mov     rdx, [rsi+50h]
0x14020902f  mov     rcx, [rcx+0E8h]
0x140209036  call    LfsFlushToLsn
0x14020903b  cmp     byte ptr [r12+1CCh], 0
0x140209044  jnz     loc_14020923E
0x14020904a  shr     r15, 0Ch
0x14020904e  mov     qword ptr [rsp+128h+MatchData], r15
0x140209056  lea     rax, [rbx+0FFFh]
0x14020905d  shr     rax, 0Ch
0x140209061  mov     [rsp+128h+var_60], eax
0x140209068  mov     rcx, [r14+100h]; FastMutex
0x14020906f  call    cs:__imp_ExAcquireFastMutex
0x140209076  nop     dword ptr [rax+rax+00h]
0x14020907b  mov     eax, [rsp+128h+NextFlag]
0x14020907f  lea     rcx, [r14+98h]; Table
0x140209086  lea     rdx, [rsp+128h+MatchData]
0x14020908e  mov     [rsp+128h+Buffer], rdx; Buffer
0x140209093  lea     rdx, [rsp+128h+var_D4]
0x140209098  mov     [rsp+128h+DeleteCount], rdx; DeleteCount
0x14020909d  lea     rdx, [rsp+128h+var_90]
0x1402090a5  mov     [rsp+128h+RestartKey], rdx; RestartKey
0x1402090aa  mov     r9d, eax; NextFlag
0x1402090ad  lea     r8, [rsp+128h+MatchData]; MatchData
0x1402090b5  lea     rdx, TxfMatchPageRange; MatchFunction
0x1402090bc  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x1402090c3  nop     dword ptr [rax+rax+00h]
0x1402090c8  mov     r12, rax
0x1402090cb  test    rax, rax
0x1402090ce  jnz     loc_14020926A
0x1402090d4  mov     rcx, [r14+100h]; FastMutex
0x1402090db  call    cs:__imp_ExReleaseFastMutex
0x1402090e2  nop     dword ptr [rax+rax+00h]
0x1402090e7  jmp     loc_1402094B7
0x1402090ec  mov     edx, 0C00000E9h; GenericException
0x1402090f1  mov     ecx, [rsp+128h+Exception]; Exception
0x1402090f8  call    cs:__imp_FsRtlNormalizeNtstatus
0x1402090ff  nop     dword ptr [rax+rax+00h]
0x140209104  mov     ecx, eax; Status
0x140209106  call    cs:__imp_ExRaiseStatus
0x140209112  mov     edx, 0C00000E9h; GenericException
0x140209117  mov     ecx, [rsp+128h+Exception]; Exception
0x14020911e  call    cs:__imp_FsRtlNormalizeNtstatus
0x140209125  nop     dword ptr [rax+rax+00h]
0x14020912a  mov     ecx, eax; Status
0x14020912c  call    cs:__imp_ExRaiseStatus
0x140209138  mov     [rdi+18h], edx
0x14020913b  mov     al, cs:NtfsStatusDebugFlags
0x140209141  test    al, al
0x140209143  jz      short loc_1402090EC
0x140209145  test    edx, edx
0x140209147  jz      short loc_1402090EC
0x140209149  cmp     edx, 126h
0x14020914f  jz      short loc_1402090EC
0x140209151  lea     eax, [rdx-12Ah]
0x140209157  cmp     eax, 1
0x14020915a  jbe     short loc_1402090EC
0x14020915c  cmp     edx, 0FFFFFFEDh
0x14020915f  jnb     short loc_1402090EC
0x140209161  cmp     edx, 0C00000D8h
0x140209167  jz      short loc_1402090EC
0x140209169  cmp     edx, 0C0000016h
0x14020916f  jz      loc_1402090EC
0x140209175  cmp     edx, 0C0000011h
0x14020917b  jz      loc_1402090EC
0x140209181  lea     eax, [rdx+7FFFFFFBh]
0x140209187  cmp     eax, 1
0x14020918a  jbe     loc_1402090EC
0x140209190  cmp     edx, 103h
0x140209196  jz      loc_1402090EC
0x14020919c  mov     r8d, 340D74h
0x1402091a2  mov     rcx, rdi
0x1402091a5  call    NtfsStatusTraceAndDebugInternal
0x1402091aa  jmp     loc_1402090EC
0x1402091af  mov     [rdi+18h], edx
0x1402091b2  mov     al, cs:NtfsStatusDebugFlags
0x1402091b8  test    al, al
0x1402091ba  jz      loc_140209112
0x1402091c0  test    edx, edx
0x1402091c2  jz      loc_140209112
0x1402091c8  cmp     edx, 126h
0x1402091ce  jz      loc_140209112
0x1402091d4  lea     eax, [rdx-12Ah]
0x1402091da  cmp     eax, 1
0x1402091dd  jbe     loc_140209112
0x1402091e3  cmp     edx, 0FFFFFFEDh
0x1402091e6  jnb     loc_140209112
0x1402091ec  cmp     edx, 0C00000D8h
0x1402091f2  jz      loc_140209112
0x1402091f8  cmp     edx, 0C0000016h
0x1402091fe  jz      loc_140209112
0x140209204  cmp     edx, 0C0000011h
0x14020920a  jz      loc_140209112
0x140209210  lea     eax, [rdx+7FFFFFFBh]
0x140209216  cmp     eax, 1
0x140209219  jbe     loc_140209112
0x14020921f  cmp     edx, 103h
0x140209225  jz      loc_140209112
0x14020922b  mov     r8d, 340D92h
0x140209231  mov     rcx, rdi
0x140209234  call    NtfsStatusTraceAndDebugInternal
0x140209239  jmp     loc_140209112
0x14020923e  mov     r8, r15
0x140209241  mov     ecx, [r12+1C4h]
0x140209249  mov     eax, ecx
0x14020924b  neg     eax
0x14020924d  movsxd  rdx, eax
0x140209250  and     r15, rdx
0x140209253  lea     eax, [rcx-1]
0x140209256  movsxd  rcx, eax
0x140209259  add     rbx, rcx
0x14020925c  add     rbx, r8
0x14020925f  and     rbx, rdx
0x140209262  sub     rbx, r15
0x140209265  jmp     loc_14020904A
0x14020926a  lea     r15, [rax+10h]
0x14020926e  mov     rcx, r15; plsn
0x140209271  call    cs:__imp_ClfsLsnInvalid
0x140209278  nop     dword ptr [rax+rax+00h]
0x14020927d  test    al, al
0x14020927f  jnz     loc_14020948F
0x140209285  mov     rbx, [r15]
0x140209288  mov     rcx, [r14+100h]; FastMutex
0x14020928f  call    cs:__imp_ExReleaseFastMutex
0x140209296  nop     dword ptr [rax+rax+00h]
0x14020929b  mov     rax, [r12+8]
0x1402092a0  shr     rax, 4
0x1402092a4  cmp     eax, [rsp+128h+var_E4]
0x1402092a8  jz      loc_140209423
0x1402092ae  mov     [rsp+128h+var_E4], eax
0x1402092b2  shl     eax, 10h
0x1402092b5  mov     qword ptr [rsp+128h+FileOffset], rax
0x1402092ba  mov     r15b, [rsp+128h+var_E8]
0x1402092bf  test    r15b, r15b
0x1402092c2  jnz     short loc_14020932C
0x1402092c4  mov     rcx, [rsi]
0x1402092c7  mov     rcx, [rcx+10h]; Resource
0x1402092cb  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1402092d2  nop     dword ptr [rax+rax+00h]
0x1402092d7  test    eax, eax
0x1402092d9  jnz     short loc_14020932C
0x1402092db  mov     rdx, [rsi]
0x1402092de  mov     rcx, rdi
0x1402092e1  call    NtfsAcquireScbPagingResourceShared
0x1402092e6  mov     r15b, al
0x1402092e9  mov     [rsp+128h+var_E8], al
0x1402092ed  mov     [rsp+128h+var_E0], 0
0x1402092f5  xor     ecx, ecx
0x1402092f7  mov     [rsp+128h+var_E0], ecx
0x1402092fb  cmp     ecx, 2
0x1402092fe  jnb     short loc_14020932C
0x140209300  mov     r8d, ecx
0x140209303  mov     rdx, [rdi+rcx*8+30h]
0x140209308  test    rdx, rdx
0x14020930b  jz      short loc_14020931D
0x14020930d  mov     rax, [rsi]
0x140209310  cmp     rdx, [rax+0B8h]
0x140209317  jz      short loc_14020931D
0x140209319  inc     ecx
0x14020931b  jmp     short loc_1402092F7
0x14020931d  mov     rax, [rsi]
0x140209320  mov     rcx, [rax+0B8h]
0x140209327  mov     [rdi+r8*8+30h], rcx
0x14020932c  mov     rcx, [rsi]
0x14020932f  lea     rax, [rsp+128h+var_88]
0x140209337  mov     [rsp+128h+DeleteCount], rax; Buffer
0x14020933c  lea     rax, [rsp+128h+Bcb]
0x140209341  mov     [rsp+128h+RestartKey], rax; Bcb
0x140209346  mov     r9d, 5; Flags
0x14020934c  mov     r8d, 10000h; Length
0x140209352  lea     rdx, [rsp+128h+FileOffset]; FileOffset
0x140209357  mov     rcx, [rcx+118h]; FileObject
0x14020935e  call    cs:__imp_CcPinRead
0x140209365  nop     dword ptr [rax+rax+00h]
0x14020936a  mov     rax, [rsi]
0x14020936d  mov     rcx, [rax+120h]
0x140209374  add     rcx, 10h; SectionObjectPointer
0x140209378  lea     r9, [rsp+128h+Exception]; IoStatus
0x140209380  mov     r8d, 10000h; Length
0x140209386  lea     rdx, [rsp+128h+FileOffset]; FileOffset
0x14020938b  call    cs:__imp_CcFlushCache
0x140209392  nop     dword ptr [rax+rax+00h]
0x140209397  mov     rcx, [rsp+128h+Bcb]; Bcb
0x14020939c  call    cs:__imp_CcUnpinData
0x1402093a3  nop     dword ptr [rax+rax+00h]
0x1402093a8  mov     [rsp+128h+Bcb], 0
0x1402093b1  test    r15b, r15b
0x1402093b4  jz      short loc_140209404
0x1402093b6  test    rdi, rdi
0x1402093b9  jz      short loc_1402093EC
0x1402093bb  mov     [rsp+128h+var_DC], 0
0x1402093c3  xor     edx, edx
0x1402093c5  mov     [rsp+128h+var_DC], edx
0x1402093c9  cmp     edx, 2
0x1402093cc  jnb     short loc_1402093EC
0x1402093ce  mov     rax, [rsi]
0x1402093d1  mov     rcx, [rax+0B8h]
0x1402093d8  cmp     [rdi+rdx*8+30h], rcx
0x1402093dd  jnz     short loc_1402093E8
0x1402093df  mov     qword ptr [rdi+rdx*8+30h], 0
0x1402093e8  inc     edx
0x1402093ea  jmp     short loc_1402093C5
0x1402093ec  mov     rcx, [rsi]
0x1402093ef  mov     rcx, [rcx+10h]; Resource
0x1402093f3  call    cs:__imp_ExReleaseResourceLite
0x1402093fa  nop     dword ptr [rax+rax+00h]
0x1402093ff  mov     [rsp+128h+var_E8], 0
0x140209404  mov     edx, [rsp+128h+Exception]
0x14020940b  test    edx, edx
0x14020940d  js      loc_140209138
0x140209413  mov     eax, [rsp+128h+var_E4]
0x140209417  mov     [rsp+128h+var_98], eax
0x14020941e  lea     r15, [r12+10h]
0x140209423  mov     rax, [r14+10h]
0x140209427  mov     rcx, [rax+40h]
0x14020942b  test    dword ptr [rcx+4], 1000h
0x140209432  jnz     short loc_14020945D
0x140209434  mov     rcx, r13
0x140209437  call    TxfTryEnterFlushSyncRegion
0x14020943c  test    al, al
0x14020943e  jz      short loc_14020945D
0x140209440  mov     [rsp+128h+var_E7], 1
0x140209445  mov     rdx, rbx
0x140209448  mov     rcx, r13
0x14020944b  call    TxfFlushToLsn
0x140209450  mov     rcx, r13
0x140209453  call    TxfLeaveFlushSyncRegion
0x140209458  mov     [rsp+128h+var_E7], 0
0x14020945d  mov     edx, [rsp+128h+Exception]
0x140209464  test    edx, edx
0x140209466  js      loc_1402091AF
0x14020946c  mov     rcx, [r14+100h]; FastMutex
0x140209473  call    cs:__imp_ExAcquireFastMutex
0x14020947a  nop     dword ptr [rax+rax+00h]
0x14020947f  or      byte ptr [r12+1Eh], 20h
0x140209485  mov     rax, qword ptr cs:CLFS_LSN_INVALID_EXT
0x14020948c  mov     [r15], rax
0x14020948f  mov     eax, dword ptr [rsp+128h+MatchData]
0x140209496  sub     eax, [r12]
0x14020949a  add     [rsp+128h+var_60], eax
0x1402094a1  mov     rax, [r12]
0x1402094a5  mov     qword ptr [rsp+128h+MatchData], rax
0x1402094ad  mov     eax, 1
0x1402094b2  jmp     loc_14020907F
0x1402094b7  cmp     [rsp+128h+var_E8], 0
0x1402094bc  jnz     short loc_1402094E7
0x1402094be  test    r14, r14
  ... truncated ...
```

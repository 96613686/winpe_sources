# TxfRedoCreateBackupFile

- ea: `0x140107fdc`
- end: `0x1401085ba`
- name: `TxfRedoCreateBackupFile`
- size: `1502`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140133f30`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000c450`
- `0x14000cb00`
- `0x14000d1e0`
- `0x140012e70`
- `0x14001c8c0`
- `0x140020de0`
- `0x1400f957c`
- `0x140107fdc`
- `0x14012b220`
- `0x1401331f4`
- `0x140140380`
- `0x140140f5c`
- `0x140191158`
- `0x1401913d4`
- `0x140194c68`
- `0x1401d2c34`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402c56ee`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402c56ee`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c56cc`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c56cc`
- `ntoskrnl!DbgPrintEx` at `0x14010810a`
- `ntoskrnl!DbgPrintEx` at `0x14010827b`
- `ntoskrnl!DbgPrintEx` at `0x14010810a`
- `ntoskrnl!DbgPrintEx` at `0x14010827b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402c5729`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402c5729`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14010859a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c577d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14010859a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c577d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14010814b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14010814b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140108500`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140108500`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401084dd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401084dd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140108517`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140108517`
- `ntoskrnl!ExReleaseResourceLite` at `0x140108552`
- `ntoskrnl!ExReleaseResourceLite` at `0x140108552`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010804a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010804a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010807c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010807c`
- `ntoskrnl!ExRaiseStatus` at `0x140108132`
- `ntoskrnl!ExRaiseStatus` at `0x140108368`
- `ntoskrnl!ExRaiseStatus` at `0x140108132`
- `ntoskrnl!ExRaiseStatus` at `0x140108368`

## pseudocode

```c
void __fastcall TxfRedoCreateBackupFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r15
  _QWORD *v8; // r14
  __int64 v9; // rcx
  char TxfDataAttribute; // bl
  _OWORD *v11; // rdi
  int v12; // eax
  int v13; // ebx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // ecx
  __int64 v19; // r15
  _QWORD *v20; // r13
  int v21; // eax
  __int64 v22; // rax
  _QWORD *v23; // rcx
  void *v24; // rcx
  int v25; // [rsp+20h] [rbp-F8h]
  char v26; // [rsp+70h] [rbp-A8h]
  __int64 v27; // [rsp+78h] [rbp-A0h] BYREF
  _QWORD *v28; // [rsp+80h] [rbp-98h]
  _OWORD *v29; // [rsp+88h] [rbp-90h]
  _QWORD *v30; // [rsp+90h] [rbp-88h]
  __int128 v31; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v32[16]; // [rsp+A8h] [rbp-70h] BYREF
  __int128 v33; // [rsp+B8h] [rbp-60h]
  __int64 v34; // [rsp+128h] [rbp+10h] BYREF
  __int64 v35; // [rsp+130h] [rbp+18h] BYREF
  __int64 v36; // [rsp+138h] [rbp+20h]

  v36 = a4;
  v7 = 0;
  v35 = 0;
  v34 = 0;
  v27 = 0;
  v31 = 0;
  v33 = 0;
  if ( *(_DWORD *)(a3 + 64) < 0x68u )
    TxfRaiseBoundsCheckFailure();
  v8 = *(_QWORD **)(a2 + 208);
  v30 = v8;
  ExAcquireFastMutex((PFAST_MUTEX)(v8[3] + 472LL));
  v28 = (_QWORD *)(a3 + 80);
  v9 = *(_QWORD *)(a3 + 80);
  if ( v8[86] < v9 )
    v8[86] = v9;
  ExReleaseFastMutex((PFAST_MUTEX)(v8[3] + 472LL));
  NtfsAcquireSharedFcb(a1, *(_QWORD *)(v8[10] + 184LL), v8[10], 0);
  TxfDataAttribute = TxfReadTxfDataAttribute(a1, *(_QWORD *)(v8[10] + 184LL), v32);
  NtfsReleaseFcbEx(a1, *(_QWORD *)(v8[10] + 184LL), 0);
  if ( !TxfDataAttribute )
  {
    DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 18089, "Status", -1073741566);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3229354);
    ExRaiseStatus(-1073741566);
  }
  v26 = 0;
  v11 = ExAllocateFromLookasideListEx(&TxfDeletedLinkLookasideList);
  v29 = v11;
  *v11 = 0;
  v11[1] = 0;
  *((_QWORD *)v11 + 4) = 0;
  *((_QWORD *)&v31 + 1) = 0;
  *(_QWORD *)&v31 = *(_QWORD *)(a3 + 80);
  if ( (int)TxfOpenFileCheckId(
              a1,
              (PRTL_AVL_TABLE *)a2,
              a3,
              (unsigned __int64 *)&v31,
              0,
              2,
              *(_BYTE *)(a3 + 74) & 8,
              0,
              &v27,
              &v34) >= 0 )
  {
    v20 = v28;
  }
  else
  {
    if ( (__int64)v33 >= *(_QWORD *)(a3 + 80) )
      goto LABEL_48;
    v12 = TxfOpenFileCheckId(
            a1,
            (PRTL_AVL_TABLE *)a2,
            a3,
            (unsigned __int64 *)(a3 + 88),
            0,
            2,
            *(_BYTE *)(a3 + 74) & 8,
            0,
            &v27,
            &v34);
    v13 = v12;
    if ( v12 == -1072103368 )
      goto LABEL_48;
    if ( v12 < 0 )
    {
      DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 18181, "Status", v12);
      if ( v13 == -1073741801
        || (v14 = (unsigned int)(v13 + 1073741697), (unsigned int)v14 <= 0x22)
        && (v15 = 0x408000001LL, _bittest64(&v15, v14)) )
      {
        ++HIDWORD((*TxfData)[1]);
      }
      else if ( v13 == -1072037845
             || v13 == -1073741202
             || v13 == -1073741435
             || v13 == -1073741496
             || (v16 = (unsigned int)(v13 + 1073741667), (unsigned int)v16 <= 0x23)
             && (v17 = 0x800000041LL, _bittest64(&v17, v16))
             || (unsigned int)(v13 + 1073741811) <= 0x15 && (v18 = 2097219, _bittest(&v18, v13 + 1073741811))
             || v13 == -2147483626
             || v13 == -1072037841 )
      {
        ++LODWORD((*TxfData)[2]);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225730LL, 3229446);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3229447);
      ExRaiseStatus(-1073741566);
    }
    v19 = *(_QWORD *)(*(_QWORD *)(v34 + 24) + 184LL);
    NtfsAcquireExclusiveVcb(a1, v8[2], 0);
    v26 = 1;
    if ( (*(_DWORD *)(v8[2] + 4LL) & 1) == 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221226094LL, 3229465);
      NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 3229465);
    }
    NtfsAcquireExclusiveFcb(a1, v19, 0, 0);
    NtfsAcquireExclusiveScbEx(a1, v8[10], 0);
    v34 = 0;
    v20 = v28;
    TxfCreateBackupFileInternal(a1, (__int64)&v34, (__int64)&v35);
    if ( !v36 || (v21 = 1, (*(_DWORD *)(v19 + 4) & 0x100000) != 0) )
      v21 = 0;
    TxfUpdateTxfDataAttributeMembers(a1, v19, v25, 0, v21, v36, 0, 0, 0, 0, 0);
    NtfsCheckpointCurrentTransaction(a1);
    v7 = v35;
  }
  *((_QWORD *)v11 + 3) = *v20;
  if ( v7 )
  {
    v22 = *(_QWORD *)(v7 + 328);
    if ( v22 )
    {
      *((_QWORD *)v11 + 4) = v22;
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v22 + 40) + 16LL) + 6176LL));
      ++*(_WORD *)(*((_QWORD *)v11 + 4) + 16LL);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v11 + 4) + 40LL) + 16LL) + 6176LL));
    }
  }
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(a2 + 24) + 80LL), 1u);
  v23 = *(_QWORD **)(a2 + 184);
  if ( *v23 != a2 + 176 )
    __fastfail(3u);
  *(_QWORD *)v11 = a2 + 176;
  *((_QWORD *)v11 + 1) = v23;
  *v23 = v11;
  *(_QWORD *)(a2 + 184) = v11;
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a2 + 24) + 80LL));
  v11 = 0;
  v29 = 0;
LABEL_48:
  if ( v26 )
    NtfsReleaseVcb(a1, v8[2]);
  if ( v11 )
  {
    v24 = (void *)*((_QWORD *)v11 + 4);
    if ( v24 )
      TxfDereferenceTxfFcb(v24);
    ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, v11);
  }
}

```

## disassembly

```asm
0x140107fdc  mov     rax, rsp
0x140107fdf  mov     [rax+20h], r9
0x140107fe3  mov     [rax+8], rcx
0x140107fe7  push    rbx
0x140107fe8  push    rsi
0x140107fe9  push    rdi
0x140107fea  push    r12
0x140107fec  push    r13
0x140107fee  push    r14
0x140107ff0  push    r15
0x140107ff2  sub     rsp, 0E0h
0x140107ff9  mov     r13, r8
0x140107ffc  mov     r12, rdx
0x140107fff  mov     rsi, rcx
0x140108002  xor     edi, edi
0x140108004  mov     r15d, edi
0x140108007  mov     [rax+18h], rdi
0x14010800b  mov     [rax+10h], rdi
0x14010800f  mov     [rsp+118h+var_A0], rdi
0x140108014  xorps   xmm0, xmm0
0x140108017  movups  xmmword ptr [rax-80h], xmm0
0x14010801b  xorps   xmm1, xmm1
0x14010801e  movups  xmmword ptr [rax-60h], xmm1
0x140108022  cmp     dword ptr [r8+40h], 68h ; 'h'
0x140108027  jnb     short loc_14010802F
0x140108029  call    TxfRaiseBoundsCheckFailure
0x14010802f  mov     r14, [rdx+0D0h]
0x140108036  mov     [rsp+118h+var_88], r14
0x14010803e  mov     rcx, [r14+18h]
0x140108042  mov     ebx, 1D8h
0x140108047  add     rcx, rbx; FastMutex
0x14010804a  call    cs:__imp_ExAcquireFastMutex
0x140108051  nop     dword ptr [rax+rax+00h]
0x140108056  lea     rax, [r13+50h]
0x14010805a  mov     [rsp+118h+var_98], rax
0x140108062  mov     rcx, [rax]
0x140108065  cmp     [r14+2B0h], rcx
0x14010806c  jge     short loc_140108075
0x14010806e  mov     [r14+2B0h], rcx
0x140108075  mov     rcx, [r14+18h]
0x140108079  add     rcx, rbx; FastMutex
0x14010807c  call    cs:__imp_ExReleaseFastMutex
0x140108083  nop     dword ptr [rax+rax+00h]
0x140108088  mov     rdx, [r14+50h]
0x14010808c  xor     r9d, r9d
0x14010808f  mov     r8, rdx
0x140108092  mov     rdx, [rdx+0B8h]
0x140108099  mov     rcx, rsi
0x14010809c  call    NtfsAcquireSharedFcb
0x1401080a1  mov     rdx, [r14+50h]
0x1401080a5  lea     r8, [rsp+118h+var_70]
0x1401080ad  mov     rdx, [rdx+0B8h]
0x1401080b4  mov     rcx, rsi
0x1401080b7  call    TxfReadTxfDataAttribute
0x1401080bc  mov     bl, al
0x1401080be  mov     rdx, [r14+50h]
0x1401080c2  xor     r8d, r8d
0x1401080c5  mov     rdx, [rdx+0B8h]
0x1401080cc  mov     rcx, rsi
0x1401080cf  call    NtfsReleaseFcbEx
0x1401080d4  test    bl, bl
0x1401080d6  jnz     short loc_14010813F
0x1401080d8  mov     ebx, 0C0000102h
0x1401080dd  mov     [rsp+118h+var_E8], ebx
0x1401080e1  lea     rax, aStatus; "Status"
0x1401080e8  mov     [rsp+118h+var_F0], rax
0x1401080ed  mov     dword ptr [rsp+118h+var_F8], 46A9h
0x1401080f5  lea     r9, aTxftransC; "txftrans.c"
0x1401080fc  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x140108103  xor     edx, edx; Level
0x140108105  mov     ecx, 82h; ComponentId
0x14010810a  call    cs:__imp_DbgPrintEx
0x140108111  nop     dword ptr [rax+rax+00h]
0x140108116  mov     al, cs:NtfsStatusDebugFlags
0x14010811c  test    al, al
0x14010811e  jz      short loc_140108130
0x140108120  mov     r8d, 3146AAh
0x140108126  mov     edx, ebx
0x140108128  mov     rcx, rsi
0x14010812b  call    NtfsStatusTraceAndDebugInternal
0x140108130  mov     ecx, ebx; Status
0x140108132  call    cs:__imp_ExRaiseStatus
0x14010813f  mov     [rsp+118h+var_A8], dil
0x140108144  lea     rcx, TxfDeletedLinkLookasideList; Lookaside
0x14010814b  call    cs:__imp_ExAllocateFromLookasideListEx
0x140108152  nop     dword ptr [rax+rax+00h]
0x140108157  mov     rdi, rax
0x14010815a  mov     [rsp+118h+var_90], rax
0x140108162  xorps   xmm0, xmm0
0x140108165  xor     eax, eax
0x140108167  movups  xmmword ptr [rdi], xmm0
0x14010816a  movups  xmmword ptr [rdi+10h], xmm0
0x14010816e  mov     [rdi+20h], rax
0x140108172  xor     edx, edx
0x140108174  mov     [rsp+118h+var_78], rdx
0x14010817c  mov     rax, [r13+50h]
0x140108180  mov     [rsp+118h+var_80], rax
0x140108188  mov     al, [r13+4Ah]
0x14010818c  and     al, 8
0x14010818e  lea     rcx, [rsp+118h+arg_8]
0x140108196  mov     [rsp+118h+var_D0], rcx
0x14010819b  lea     rcx, [rsp+118h+var_A0]
0x1401081a0  mov     [rsp+118h+var_D8], rcx
0x1401081a5  mov     [rsp+118h+var_E0], rdx
0x1401081aa  mov     byte ptr [rsp+118h+var_E8], al
0x1401081ae  mov     dword ptr [rsp+118h+var_F0], 2
0x1401081b6  mov     [rsp+118h+var_F8], rdx
0x1401081bb  lea     r9, [rsp+118h+var_80]
0x1401081c3  mov     r8, r13
0x1401081c6  mov     rdx, r12
0x1401081c9  mov     rcx, rsi
0x1401081cc  call    TxfOpenFileCheckId
0x1401081d1  nop
0x1401081d2  test    eax, eax
0x1401081d4  jns     loc_1401084A2
0x1401081da  mov     rax, qword ptr [rsp+118h+var_60]
0x1401081e2  cmp     rax, [r13+50h]
0x1401081e6  jge     loc_140108568
0x1401081ec  mov     al, [r13+4Ah]
0x1401081f0  and     al, 8
0x1401081f2  lea     r9, [r13+58h]
0x1401081f6  lea     rcx, [rsp+118h+arg_8]
0x1401081fe  mov     [rsp+118h+var_D0], rcx
0x140108203  lea     rcx, [rsp+118h+var_A0]
0x140108208  mov     [rsp+118h+var_D8], rcx
0x14010820d  mov     [rsp+118h+var_E0], 0
0x140108216  mov     byte ptr [rsp+118h+var_E8], al
0x14010821a  mov     dword ptr [rsp+118h+var_F0], 2
0x140108222  mov     [rsp+118h+var_F8], 0
0x14010822b  mov     r8, r13
0x14010822e  mov     rdx, r12
0x140108231  mov     rcx, rsi
0x140108234  call    TxfOpenFileCheckId
0x140108239  mov     ebx, eax
0x14010823b  cmp     eax, 0C0190038h
0x140108240  jz      loc_140108568
0x140108246  test    eax, eax
0x140108248  jns     loc_140108374
0x14010824e  mov     [rsp+118h+var_E8], eax
0x140108252  lea     rax, aStatus; "Status"
0x140108259  mov     [rsp+118h+var_F0], rax
0x14010825e  mov     dword ptr [rsp+118h+var_F8], 4705h
0x140108266  lea     r9, aTxftransC; "txftrans.c"
0x14010826d  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x140108274  xor     edx, edx; Level
0x140108276  mov     ecx, 82h; ComponentId
0x14010827b  call    cs:__imp_DbgPrintEx
0x140108282  nop     dword ptr [rax+rax+00h]
0x140108287  cmp     ebx, 0C0000017h
0x14010828d  jz      loc_14010831F
0x140108293  lea     eax, [rbx+3FFFFF81h]
0x140108299  cmp     eax, 22h ; '"'
0x14010829c  ja      short loc_1401082AE
0x14010829e  mov     rcx, 408000001h
0x1401082a8  bt      rcx, rax
0x1401082ac  jb      short loc_14010831F
0x1401082ae  cmp     ebx, 0C01A002Bh
0x1401082b4  jz      short loc_14010830E
0x1401082b6  cmp     ebx, 0C000026Eh
0x1401082bc  jz      short loc_14010830E
0x1401082be  cmp     ebx, 0C0000185h
0x1401082c4  jz      short loc_14010830E
0x1401082c6  cmp     ebx, 0C0000148h
0x1401082cc  jz      short loc_14010830E
0x1401082ce  lea     eax, [rbx+3FFFFF63h]
0x1401082d4  cmp     eax, 23h ; '#'
0x1401082d7  ja      short loc_1401082E9
0x1401082d9  mov     rcx, 800000041h
0x1401082e3  bt      rcx, rax
0x1401082e7  jb      short loc_14010830E
0x1401082e9  lea     eax, [rbx+3FFFFFF3h]
0x1401082ef  cmp     eax, 15h
0x1401082f2  ja      short loc_1401082FE
0x1401082f4  mov     ecx, 200043h
0x1401082f9  bt      ecx, eax
0x1401082fc  jb      short loc_14010830E
0x1401082fe  cmp     ebx, 80000016h
0x140108304  jz      short loc_14010830E
0x140108306  cmp     ebx, 0C01A002Fh
0x14010830c  jnz     short loc_14010832E
0x14010830e  mov     rax, cs:TxfData
0x140108315  mov     ebx, 1
0x14010831a  add     [rax+10h], ebx
0x14010831d  jmp     short loc_14010832E
0x14010831f  mov     rax, cs:TxfData
0x140108326  mov     ebx, 1
0x14010832b  add     [rax+0Ch], ebx
0x14010832e  mov     al, cs:NtfsStatusDebugFlags
0x140108334  mov     ebx, 0C0000102h
0x140108339  test    al, al
0x14010833b  jz      short loc_14010834C
0x14010833d  mov     r8d, 314706h
0x140108343  mov     edx, ebx
0x140108345  xor     ecx, ecx
0x140108347  call    NtfsStatusTraceAndDebugInternal
0x14010834c  mov     al, cs:NtfsStatusDebugFlags
0x140108352  test    al, al
0x140108354  jz      short loc_140108366
0x140108356  mov     r8d, 314707h
0x14010835c  mov     edx, ebx
0x14010835e  mov     rcx, rsi
0x140108361  call    NtfsStatusTraceAndDebugInternal
0x140108366  mov     ecx, ebx; Status
0x140108368  call    cs:__imp_ExRaiseStatus
0x140108374  mov     rax, [rsp+118h+arg_8]
0x14010837c  mov     rcx, [rax+18h]
0x140108380  mov     r15, [rcx+0B8h]
0x140108387  xor     r8d, r8d
0x14010838a  mov     rdx, [r14+10h]
0x14010838e  mov     rcx, rsi
0x140108391  call    NtfsAcquireExclusiveVcb
0x140108396  mov     ebx, 1
0x14010839b  mov     [rsp+118h+var_A8], bl
0x14010839f  mov     rax, [r14+10h]
0x1401083a3  mov     ecx, [rax+4]
0x1401083a6  test    bl, cl
0x1401083a8  jnz     short loc_1401083E3
0x1401083aa  mov     al, cs:NtfsStatusDebugFlags
0x1401083b0  test    al, al
0x1401083b2  jz      short loc_1401083C7
0x1401083b4  mov     edx, 0C000026Eh
0x1401083b9  mov     r8d, 314719h
0x1401083bf  mov     rcx, rsi
0x1401083c2  call    NtfsStatusTraceAndDebugInternal
0x1401083c7  mov     [rsp+118h+var_F8], 314719h
0x1401083d0  xor     r9d, r9d
0x1401083d3  xor     r8d, r8d
0x1401083d6  mov     edx, 0C000026Eh
0x1401083db  mov     rcx, rsi
0x1401083de  call    NtfsRaiseStatusInternal
0x1401083e3  xor     r9d, r9d
0x1401083e6  xor     r8d, r8d
0x1401083e9  mov     rdx, r15
0x1401083ec  mov     rcx, rsi
0x1401083ef  call    NtfsAcquireExclusiveFcb
0x1401083f4  xor     r8d, r8d
0x1401083f7  mov     rdx, [r14+50h]
0x1401083fb  mov     rcx, rsi
0x1401083fe  call    NtfsAcquireExclusiveScbEx
0x140108403  mov     [rsp+118h+arg_8], 0
0x14010840f  lea     rax, [rsp+118h+arg_10]
0x140108417  mov     [rsp+118h+var_F0], rax; __int64
0x14010841c  lea     rax, [rsp+118h+arg_8]
0x140108424  mov     [rsp+118h+var_F8], rax; int
0x140108429  mov     r9, r15
0x14010842c  mov     r13, [rsp+118h+var_98]
0x140108434  mov     r8, r13
0x140108437  mov     rdx, r14
0x14010843a  mov     rcx, rsi; int
0x14010843d  call    TxfCreateBackupFileInternal
0x140108442  mov     rcx, [rsp+118h+arg_18]
0x14010844a  xor     edx, edx
0x14010844c  test    rcx, rcx
0x14010844f  jz      short loc_14010845D
0x140108451  test    dword ptr [r15+4], 100000h
0x140108459  mov     eax, ebx
0x14010845b  jz      short loc_14010845F
0x14010845d  mov     eax, edx
0x14010845f  mov     [rsp+118h+var_B8], rdx; __int64
0x140108464  mov     [rsp+118h+var_C0], rdx; __int64
0x140108469  mov     [rsp+118h+var_C8], rdx; __int64
0x14010846e  mov     [rsp+118h+var_D0], rdx; __int64
0x140108473  mov     [rsp+118h+var_D8], rdx; __int64
0x140108478  mov     [rsp+118h+var_E0], rcx; __int64
0x14010847d  mov     [rsp+118h+var_E8], eax; int
0x140108481  mov     dword ptr [rsp+118h+var_F0], edx; int
0x140108485  mov     rdx, r15; int
0x140108488  mov     rcx, rsi; int
0x14010848b  call    TxfUpdateTxfDataAttributeMembers
0x140108490  mov     rcx, rsi
0x140108493  call    NtfsCheckpointCurrentTransaction
0x140108498  mov     r15, [rsp+118h+arg_10]
0x1401084a0  jmp     short loc_1401084AF
0x1401084a2  mov     ebx, 1
0x1401084a7  mov     r13, [rsp+118h+var_98]
0x1401084af  mov     rax, [r13+0]
0x1401084b3  mov     [rdi+18h], rax
0x1401084b7  test    r15, r15
0x1401084ba  jz      short loc_14010850C
0x1401084bc  mov     rax, [r15+148h]
0x1401084c3  test    rax, rax
0x1401084c6  jz      short loc_14010850C
0x1401084c8  mov     [rdi+20h], rax
0x1401084cc  mov     rax, [rax+28h]
0x1401084d0  mov     rcx, [rax+10h]
0x1401084d4  mov     r15d, 1820h
0x1401084da  add     rcx, r15; FastMutex
0x1401084dd  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1401084e4  nop     dword ptr [rax+rax+00h]
0x1401084e9  mov     rax, [rdi+20h]
0x1401084ed  add     [rax+10h], bx
0x1401084f1  mov     rax, [rdi+20h]
0x1401084f5  mov     rcx, [rax+28h]
0x1401084f9  mov     rcx, [rcx+10h]
0x1401084fd  add     rcx, r15; FastMutex
0x140108500  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140108507  nop     dword ptr [rax+rax+00h]
0x14010850c  mov     rcx, [r12+18h]
0x140108511  add     rcx, 50h ; 'P'; Resource
0x140108515  mov     dl, bl; Wait
  ... truncated ...
```

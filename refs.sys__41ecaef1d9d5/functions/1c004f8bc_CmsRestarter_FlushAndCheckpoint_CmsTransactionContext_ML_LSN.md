# CmsRestarter::FlushAndCheckpoint(CmsTransactionContext *,_ML_LSN)

- ea: `0x1c004f8bc`
- end: `0x1c004fa99`
- name: `?FlushAndCheckpoint@CmsRestarter@@AEAAJPEAVCmsTransactionContext@@T_ML_LSN@@@Z`
- size: `477`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c004bc94`
- `0x1c00e4720`

## callees

- `0x1c00224d0`
- `0x1c004785c`
- `0x1c004ca38`
- `0x1c004ef58`
- `0x1c004f8bc`
- `0x1c0052880`
- `0x1c00534c4`
- `0x1c006af80`
- `0x1c00e4bbc`
- `0x1c00e5b4c`
- `0x1c00f72c8`
- `0x1c00f740c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0087329`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c008749d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0087329`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c008749d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c004f9c1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0087394`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0087504`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c004f9c1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0087394`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0087504`
- `ntoskrnl!KeClearEvent` at `0x1c00873c9`
- `ntoskrnl!KeClearEvent` at `0x1c00873dc`
- `ntoskrnl!KeClearEvent` at `0x1c0087539`
- `ntoskrnl!KeClearEvent` at `0x1c008754c`
- `ntoskrnl!KeClearEvent` at `0x1c00873c9`
- `ntoskrnl!KeClearEvent` at `0x1c00873dc`
- `ntoskrnl!KeClearEvent` at `0x1c0087539`
- `ntoskrnl!KeClearEvent` at `0x1c008754c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0087274`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c008765a`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0087274`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c008765a`
- `ntoskrnl!KeSetEvent` at `0x1c004f950`
- `ntoskrnl!KeSetEvent` at `0x1c004f968`
- `ntoskrnl!KeSetEvent` at `0x1c004f950`
- `ntoskrnl!KeSetEvent` at `0x1c004f968`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0087353`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00873a3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00874c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0087513`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0087353`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00873a3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00874c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0087513`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0087374`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00873ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00874e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c008755e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0087374`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00873ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00874e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c008755e`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1c004f922`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1c004f922`

## pseudocode

```c
__int64 __fastcall CmsRestarter::FlushAndCheckpoint(__int64 *a1, struct CmsTransactionCore *a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx
  struct CmsTransactionCore *v4; // r13
  unsigned __int8 v6; // r9
  unsigned int v7; // r14d
  CmsAvlTableFlex *v8; // rcx
  unsigned __int8 v9; // r9
  int DiscardLogLsn; // r12d
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v14; // edi
  __int64 v15; // rsi
  __int64 v16; // r14
  int ActivityIdThread; // eax
  int i; // eax
  __int64 v19; // rsi
  __int64 v20; // rcx
  unsigned __int8 v21; // r9
  struct _MS_WORK_QUEUE_ITEM *PoolWithTag; // rax
  struct _MS_WORK_QUEUE_ITEM *v23; // rdi
  KIRQL v24; // r12
  unsigned int v25; // eax
  unsigned int v26; // edx
  CmsAvlTableFlex *v27; // rcx
  unsigned __int16 j; // si
  __int64 v29; // rdi
  CmsBPlusTable *v30; // rcx
  struct _MS_WORK_QUEUE_ITEM *v31; // rax
  struct _MS_WORK_QUEUE_ITEM *v32; // r13
  KIRQL v33; // r12
  unsigned int v34; // eax
  unsigned __int16 v35; // si
  unsigned __int16 v36; // di
  __int64 v37; // rdx
  __int64 v38; // rax
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int64 v41; // rax
  unsigned __int8 v42; // r9
  __int64 v43; // rax
  int v44; // ebx
  __int64 v45; // rdi
  __int64 v46; // rsi
  int v47; // eax
  __m256i v48; // [rsp+40h] [rbp-89h] BYREF
  __int128 v49; // [rsp+60h] [rbp-69h] BYREF
  __int64 v50; // [rsp+70h] [rbp-59h]
  _OWORD v51[2]; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v52[128]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v53; // [rsp+130h] [rbp+67h] BYREF
  struct CmsTransactionCore *v54; // [rsp+138h] [rbp+6Fh]
  unsigned __int64 v55; // [rsp+140h] [rbp+77h]

  v54 = a2;
  v3 = a3;
  v55 = a3;
  v50 = 0;
  v4 = a2;
  v49 = 0;
  memset(v51, 0, sizeof(v51));
  memset((char *)v48.m256i_i64 + 4, 0, 28);
  memset(v52, 0, 0x48u);
  LODWORD(v53) = 2 * KeQueryActiveProcessorCountEx(0xFFFFu);
  if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    v14 = *((_DWORD *)a1 + 44);
    v15 = a1[12];
    v16 = a1[13];
    ActivityIdThread = IoGetActivityIdThread();
    McTemplateK0iix_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)RedoPassFlushAndCheckpointStart,
      ActivityIdThread,
      v16,
      v15,
      v14);
  }
  KeSetEvent((PRKEVENT)(a1 + 44), 0, 0);
  KeSetEvent((PRKEVENT)(a1 + 41), 0, 0);
  v7 = 0;
  if ( v3 && v3 > a1[13] )
  {
    a1[13] = v3;
    ++*((_DWORD *)a1 + 26);
  }
  v8 = (CmsAvlTableFlex *)a1[15];
  if ( v8 )
  {
    for ( i = CmsAvlTableFlex::PinInIndex(
                v8,
                v4,
                (struct _SmsPropertyDef *)&dword_1C0136ED8,
                (struct _CmsRow *)v51,
                2,
                (struct _CmsRow *)&v48,
                (struct _SmsLookupStack *)v52,
                (struct _SmsQuickIndex *)&v49);
          i >= 0;
          i = CmsAvlTableFlex::PinNextInIndex(
                v27,
                v26,
                (struct _CmsRow *)&v48,
                (struct _SmsLookupStack *)v52,
                (struct _SmsQuickIndex *)&v49) )
    {
      v19 = v48.m256i_i64[3];
      if ( CmsBPlusTable::IsRootOfBindableUnit(*(CmsBPlusTable **)(v48.m256i_i64[3] + 16))
        && (*(_DWORD *)(v20 + 16) & 0x40000) == 0 )
      {
        PoolWithTag = (struct _MS_WORK_QUEUE_ITEM *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x50u, 0x6950534Du);
        v23 = PoolWithTag;
        if ( !PoolWithTag )
        {
LABEL_30:
          DiscardLogLsn = -1073741670;
          goto LABEL_14;
        }
        *((_QWORD *)PoolWithTag + 8) = v19;
        *((_QWORD *)PoolWithTag + 9) = a1;
        v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 47);
        v25 = *((_DWORD *)a1 + 80);
        if ( v25 >= (unsigned int)v53 )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)a1 + 47, v24);
          KeWaitForSingleObject(a1 + 41, Executive, 0, 0, 0);
          v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 47);
          v25 = *((_DWORD *)a1 + 80);
        }
        *((_DWORD *)a1 + 80) = v25 + 1;
        KeClearEvent((PRKEVENT)(a1 + 41));
        KeClearEvent((PRKEVENT)(a1 + 44));
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 47, v24);
        MsInitializeAndQueueWorkItem(v23, (void (*)(void *))CmsRestarter::RedoTUTables, v23, SuperCriticalWorkQueue);
      }
      CmsTransactionContext::Commit(v4, 0, 0, v21);
    }
  }
  CmsTransactionContext::Commit(v4, 0, 0, v6);
  if ( a1[16] )
  {
    for ( j = 0; j < *((_WORD *)a1 + 68); ++j )
    {
      v29 = a1[16] + 32LL * j;
      v30 = *(CmsBPlusTable **)(v29 + 16);
      if ( (*((_DWORD *)v30 + 4) & 0x40000) == 0 && CmsBPlusTable::IsRootOfBindableUnit(v30) )
      {
        v31 = (struct _MS_WORK_QUEUE_ITEM *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x50u, 0x6950534Du);
        v32 = v31;
        if ( !v31 )
          goto LABEL_30;
        *((_QWORD *)v31 + 8) = v29;
        *((_QWORD *)v31 + 9) = a1;
        v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 47);
        v34 = *((_DWORD *)a1 + 80);
        if ( v34 >= (unsigned int)v53 )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)a1 + 47, v33);
          KeWaitForSingleObject(a1 + 41, Executive, 0, 0, 0);
          v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 47);
          v34 = *((_DWORD *)a1 + 80);
        }
        *((_DWORD *)a1 + 80) = v34 + 1;
        KeClearEvent((PRKEVENT)(a1 + 44));
        KeClearEvent((PRKEVENT)(a1 + 41));
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 47, v33);
        MsInitializeAndQueueWorkItem(v32, (void (*)(void *))CmsRestarter::RedoTUTables, v32, SuperCriticalWorkQueue);
        v4 = v54;
      }
      CmsTransactionContext::Commit(v4, 0, 0, v9);
    }
  }
  KeWaitForSingleObject(a1 + 44, Executive, 0, 0, 0);
  DiscardLogLsn = *((_DWORD *)a1 + 81);
  if ( a1[16] )
  {
    v35 = 0;
    v36 = 0;
    if ( *((_WORD *)a1 + 68) )
    {
      do
      {
        v37 = a1[16];
        v38 = 32LL * v36;
        v39 = *(_OWORD *)(v38 + v37 + 16);
        v40 = *(_OWORD *)(v38 + v37);
        v41 = *(_QWORD *)(v38 + v37 + 16);
        *(_OWORD *)v48.m256i_i8 = v40;
        *(_OWORD *)&v48.m256i_u64[2] = v39;
        if ( (*(_DWORD *)(v41 + 16) & 0x40000) != 0 )
        {
          v43 = 32LL * v35++;
          *(_OWORD *)(v43 + v37) = v40;
          *(_OWORD *)(v43 + v37 + 16) = v39;
        }
        else
        {
          CmsRestarter::ReleaseOpenTable((CmsRestarter *)a1, v4, (struct _SmsOpenTable *)&v48);
          CmsTransactionContext::Commit(v4, 0, 0, v42);
        }
        ++v36;
      }
      while ( v36 < *((_WORD *)a1 + 68) );
      v3 = v55;
    }
    *((_WORD *)a1 + 68) = v35;
  }
  if ( DiscardLogLsn >= 0 )
  {
    if ( !v3
      || (v11 = *a1, v53 = 0, DiscardLogLsn = MlLogGetDiscardLogLsn(*(_QWORD *)(v11 + 72), v3, &v53), DiscardLogLsn >= 0)
      && (v12 = *a1, a1[13] = v53, DiscardLogLsn = MlLogSetEndOfLog(*(void **)(v12 + 72)), DiscardLogLsn >= 0) )
    {
      DiscardLogLsn = CmsVolume::Flush((CmsVolume *)a1[1], 0x811u, 0, 0, 0, 0, 0);
      if ( DiscardLogLsn == -1073741772 )
        DiscardLogLsn = -1073741072;
    }
  }
LABEL_14:
  if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    v44 = *((_DWORD *)a1 + 44);
    v45 = a1[12];
    v46 = a1[13];
    v47 = IoGetActivityIdThread();
    McTemplateK0iix_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)RedoPassFlushAndCheckpointEnd,
      v47,
      v46,
      v45,
      v44);
  }
  if ( DiscardLogLsn != -1073741772 )
    return (unsigned int)DiscardLogLsn;
  return v7;
}

```

## disassembly

```asm
0x1c004f8bc  mov     [rsp-8+arg_18], rbx
0x1c004f8c1  mov     [rsp-8+arg_8], rdx
0x1c004f8c6  push    rbp
0x1c004f8c7  push    rsi
0x1c004f8c8  push    rdi
0x1c004f8c9  push    r12
0x1c004f8cb  push    r13
0x1c004f8cd  push    r14
0x1c004f8cf  push    r15
0x1c004f8d1  lea     rbp, [rsp-27h]
0x1c004f8d6  sub     rsp, 0F0h
0x1c004f8dd  xor     eax, eax
0x1c004f8df  mov     rbx, r8
0x1c004f8e2  xorps   xmm0, xmm0
0x1c004f8e5  mov     [rbp+57h+arg_10], rbx
0x1c004f8e9  xorps   xmm1, xmm1
0x1c004f8ec  mov     [rbp+57h+var_B0], rax
0x1c004f8f0  mov     r13, rdx
0x1c004f8f3  mov     [rbp+57h+var_CC], rax
0x1c004f8f7  mov     r15, rcx
0x1c004f8fa  mov     [rbp+57h+var_C4], eax
0x1c004f8fd  lea     r8d, [rax+48h]; Size
0x1c004f901  xor     edx, edx; Val
0x1c004f903  lea     rcx, [rbp+57h+var_80]; void *
0x1c004f907  movups  [rbp+57h+var_C0], xmm0
0x1c004f90b  movups  [rbp+57h+var_A8], xmm1
0x1c004f90f  movups  [rbp+57h+var_98], xmm1
0x1c004f913  movups  [rsp+120h+var_E0+4], xmm0
0x1c004f918  call    memset
0x1c004f91d  mov     ecx, 0FFFFh; GroupNumber
0x1c004f922  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1c004f929  nop     dword ptr [rax+rax+00h]
0x1c004f92e  add     eax, eax
0x1c004f930  mov     edi, 1
0x1c004f935  cmp     cs:dword_1C012D0B4, edi
0x1c004f93b  mov     dword ptr [rbp+57h+arg_0], eax
0x1c004f93e  jz      loc_1C0087258
0x1c004f944  lea     rcx, [r15+160h]; Event
0x1c004f94b  xor     r8d, r8d; Wait
0x1c004f94e  xor     edx, edx; Increment
0x1c004f950  call    cs:__imp_KeSetEvent
0x1c004f957  nop     dword ptr [rax+rax+00h]
0x1c004f95c  lea     rcx, [r15+148h]; Event
0x1c004f963  xor     r8d, r8d; Wait
0x1c004f966  xor     edx, edx; Increment
0x1c004f968  call    cs:__imp_KeSetEvent
0x1c004f96f  nop     dword ptr [rax+rax+00h]
0x1c004f974  xor     r14d, r14d
0x1c004f977  test    rbx, rbx
0x1c004f97a  jz      short loc_1C004F986
0x1c004f97c  cmp     rbx, [r15+68h]
0x1c004f980  ja      loc_1C00872AD
0x1c004f986  mov     rcx, [r15+78h]; this
0x1c004f98a  test    rcx, rcx
0x1c004f98d  jnz     loc_1C00872BA
0x1c004f993  xor     r8d, r8d; struct _SmsLsn *
0x1c004f996  xor     edx, edx; unsigned __int8
0x1c004f998  mov     rcx, r13; this
0x1c004f99b  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x1c004f9a0  cmp     [r15+80h], r14
0x1c004f9a7  jnz     loc_1C008744E
0x1c004f9ad  xor     r9d, r9d; Alertable
0x1c004f9b0  mov     [rsp+120h+Timeout], r14; Timeout
0x1c004f9b5  xor     r8d, r8d; WaitMode
0x1c004f9b8  lea     rcx, [r15+160h]; Object
0x1c004f9bf  xor     edx, edx; WaitReason
0x1c004f9c1  call    cs:__imp_KeWaitForSingleObject
0x1c004f9c8  nop     dword ptr [rax+rax+00h]
0x1c004f9cd  mov     r12d, [r15+144h]
0x1c004f9d4  cmp     [r15+80h], r14
0x1c004f9db  jnz     loc_1C00875A9
0x1c004f9e1  test    r12d, r12d
0x1c004f9e4  js      short loc_1C004FA5E
0x1c004f9e6  test    rbx, rbx
0x1c004f9e9  jz      short loc_1C004FA28
0x1c004f9eb  mov     rcx, [r15]
0x1c004f9ee  lea     r8, [rbp+57h+arg_0]
0x1c004f9f2  mov     rdx, rbx
0x1c004f9f5  mov     [rbp+57h+arg_0], r14
0x1c004f9f9  mov     rcx, [rcx+48h]
0x1c004f9fd  call    MlLogGetDiscardLogLsn
0x1c004fa02  mov     r12d, eax
0x1c004fa05  test    eax, eax
0x1c004fa07  js      short loc_1C004FA5E
0x1c004fa09  mov     rcx, [r15]
0x1c004fa0c  mov     r8, [rbp+57h+arg_0]
0x1c004fa10  mov     rdx, [r15+8]
0x1c004fa14  mov     [r15+68h], r8
0x1c004fa18  mov     rcx, [rcx+48h]; Src
0x1c004fa1c  call    MlLogSetEndOfLog
0x1c004fa21  mov     r12d, eax
0x1c004fa24  test    eax, eax
0x1c004fa26  js      short loc_1C004FA5E
0x1c004fa28  mov     rcx, [r15+8]; this
0x1c004fa2c  xor     r9d, r9d; unsigned int
0x1c004fa2f  mov     [rsp+120h+var_F0], r14; struct _KEVENT *
0x1c004fa34  xor     r8d, r8d; void *
0x1c004fa37  mov     [rsp+120h+var_F8], r14; unsigned __int8 *
0x1c004fa3c  mov     edx, 811h; unsigned int
0x1c004fa41  mov     [rsp+120h+Timeout], r14; unsigned __int8 *
0x1c004fa46  call    ?Flush@CmsVolume@@QEAAJKPEAXKPEAE1PEAU_KEVENT@@@Z; CmsVolume::Flush(ulong,void *,ulong,uchar *,uchar *,_KEVENT *)
0x1c004fa4b  mov     r12d, eax
0x1c004fa4e  mov     eax, 0C00002F0h
0x1c004fa53  cmp     r12d, 0C0000034h
0x1c004fa5a  cmovz   r12d, eax
0x1c004fa5e  mov     ecx, 1
0x1c004fa63  cmp     cs:dword_1C012D0B4, ecx
0x1c004fa69  jz      loc_1C008763F
0x1c004fa6f  mov     rbx, [rsp+120h+arg_18]
0x1c004fa77  cmp     r12d, 0C0000034h
0x1c004fa7e  cmovnz  r14d, r12d
0x1c004fa82  mov     eax, r14d
0x1c004fa85  add     rsp, 0F0h
0x1c004fa8c  pop     r15
0x1c004fa8e  pop     r14
0x1c004fa90  pop     r13
0x1c004fa92  pop     r12
0x1c004fa94  pop     rdi
0x1c004fa95  pop     rsi
0x1c004fa96  pop     rbp
0x1c004fa97  retn
0x1c0087258  test    cs:Microsoft_Windows_MinstoreEnableBits, dil
0x1c008725f  jz      loc_1C004F944
0x1c0087265  mov     edi, [r15+0B0h]
0x1c008726c  mov     rsi, [r15+60h]
0x1c0087270  mov     r14, [r15+68h]
0x1c0087274  call    cs:__imp_IoGetActivityIdThread
0x1c008727b  nop     dword ptr [rax+rax+00h]
0x1c0087280  mov     [rsp+120h+var_F8], rdi
0x1c0087285  lea     rdx, RedoPassFlushAndCheckpointStart
0x1c008728c  mov     r8, rax
0x1c008728f  mov     [rsp+120h+Timeout], rsi
0x1c0087294  mov     r9, r14
0x1c0087297  lea     rcx, MinstoreEventProvider_Context
0x1c008729e  call    McTemplateK0iix_EtwWriteTransfer
0x1c00872a3  mov     edi, 1
0x1c00872a8  jmp     loc_1C004F944
0x1c00872ad  mov     [r15+68h], rbx
0x1c00872b1  add     [r15+68h], edi
0x1c00872b5  jmp     loc_1C004F986
0x1c00872ba  lea     rax, [rbp+57h+var_C0]
0x1c00872be  mov     rdx, r13; struct CmsTransactionCore *
0x1c00872c1  mov     [rsp+120h+var_E8], rax; struct _SmsQuickIndex *
0x1c00872c6  lea     r9, [rbp+57h+var_A8]; struct _CmsRow *
0x1c00872ca  lea     rax, [rbp+57h+var_80]
0x1c00872ce  mov     [rsp+120h+var_F0], rax; struct _SmsLookupStack *
0x1c00872d3  lea     r8, dword_1C0136ED8; struct _SmsPropertyDef *
0x1c00872da  lea     rax, [rsp+120h+var_E0]
0x1c00872df  mov     [rsp+120h+var_F8], rax; struct _CmsRow *
0x1c00872e4  mov     dword ptr [rsp+120h+Timeout], 2; char
0x1c00872ec  call    ?PinInIndex@CmsAvlTableFlex@@QEAAJPEAVCmsTransactionCore@@PEAU_SmsPropertyDef@@PEAU_CmsRow@@K2PEAU_SmsLookupStack@@PEAU_SmsQuickIndex@@@Z; CmsAvlTableFlex::PinInIndex(CmsTransactionCore *,_SmsPropertyDef *,_CmsRow *,ulong,_CmsRow *,_SmsLookupStack *,_SmsQuickIndex *)
0x1c00872f1  jmp     loc_1C0087436
0x1c00872f6  mov     rsi, [rbp+57h+var_CC+4]
0x1c00872fa  mov     rcx, [rsi+10h]; this
0x1c00872fe  call    ?IsRootOfBindableUnit@CmsBPlusTable@@QEAAEXZ; CmsBPlusTable::IsRootOfBindableUnit(void)
0x1c0087303  test    al, al
0x1c0087305  jz      loc_1C0087412
0x1c008730b  mov     eax, [rcx+10h]
0x1c008730e  bt      rax, 12h
0x1c0087313  jb      loc_1C0087412
0x1c0087319  mov     edx, 50h ; 'P'; NumberOfBytes
0x1c008731e  mov     ecx, 200h; PoolType
0x1c0087323  mov     r8d, 6950534Dh; Tag
0x1c0087329  call    cs:__imp_ExAllocatePoolWithTag
0x1c0087330  nop     dword ptr [rax+rax+00h]
0x1c0087335  mov     rdi, rax
0x1c0087338  test    rax, rax
0x1c008733b  jz      loc_1C0087443
0x1c0087341  mov     [rax+40h], rsi
0x1c0087345  lea     rsi, [r15+178h]
0x1c008734c  mov     rcx, rsi; SpinLock
0x1c008734f  mov     [rax+48h], r15
0x1c0087353  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c008735a  nop     dword ptr [rax+rax+00h]
0x1c008735f  mov     r12b, al
0x1c0087362  mov     eax, [r15+140h]
0x1c0087369  cmp     eax, dword ptr [rbp+57h+arg_0]
0x1c008736c  jb      short loc_1C00873B9
0x1c008736e  mov     dl, r12b; NewIrql
0x1c0087371  mov     rcx, rsi; SpinLock
0x1c0087374  call    cs:__imp_KeReleaseSpinLock
0x1c008737b  nop     dword ptr [rax+rax+00h]
0x1c0087380  xor     r9d, r9d; Alertable
0x1c0087383  mov     [rsp+120h+Timeout], r14; Timeout
0x1c0087388  xor     r8d, r8d; WaitMode
0x1c008738b  lea     rcx, [r15+148h]; Object
0x1c0087392  xor     edx, edx; WaitReason
0x1c0087394  call    cs:__imp_KeWaitForSingleObject
0x1c008739b  nop     dword ptr [rax+rax+00h]
0x1c00873a0  mov     rcx, rsi; SpinLock
0x1c00873a3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c00873aa  nop     dword ptr [rax+rax+00h]
0x1c00873af  mov     r12b, al
0x1c00873b2  mov     eax, [r15+140h]
0x1c00873b9  inc     eax
0x1c00873bb  lea     rcx, [r15+148h]; Event
0x1c00873c2  mov     [r15+140h], eax
0x1c00873c9  call    cs:__imp_KeClearEvent
0x1c00873d0  nop     dword ptr [rax+rax+00h]
0x1c00873d5  lea     rcx, [r15+160h]; Event
0x1c00873dc  call    cs:__imp_KeClearEvent
0x1c00873e3  nop     dword ptr [rax+rax+00h]
0x1c00873e8  mov     dl, r12b; NewIrql
0x1c00873eb  mov     rcx, rsi; SpinLock
0x1c00873ee  call    cs:__imp_KeReleaseSpinLock
0x1c00873f5  nop     dword ptr [rax+rax+00h]
0x1c00873fa  mov     r9d, 6; enum _WORK_QUEUE_TYPE
0x1c0087400  lea     rdx, ?RedoTUTables@CmsRestarter@@CAXPEAX@Z; void (*)(void *)
0x1c0087407  mov     r8, rdi; void *
0x1c008740a  mov     rcx, rdi; struct _MS_WORK_QUEUE_ITEM *
0x1c008740d  call    ?MsInitializeAndQueueWorkItem@@YAXPEAU_MS_WORK_QUEUE_ITEM@@P6AXPEAX@Z1W4_WORK_QUEUE_TYPE@@@Z; MsInitializeAndQueueWorkItem(_MS_WORK_QUEUE_ITEM *,void (*)(void *),void *,_WORK_QUEUE_TYPE)
0x1c0087412  xor     r8d, r8d; struct _SmsLsn *
0x1c0087415  xor     edx, edx; unsigned __int8
0x1c0087417  mov     rcx, r13; this
0x1c008741a  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x1c008741f  lea     rax, [rbp+57h+var_C0]
0x1c0087423  lea     r9, [rbp+57h+var_80]; struct _SmsLookupStack *
0x1c0087427  mov     [rsp+120h+Timeout], rax; struct _SmsQuickIndex *
0x1c008742c  lea     r8, [rsp+120h+var_E0]; struct _CmsRow *
0x1c0087431  call    ?PinNextInIndex@CmsAvlTableFlex@@QEAAJKPEAU_CmsRow@@PEAU_SmsLookupStack@@PEAU_SmsQuickIndex@@@Z; CmsAvlTableFlex::PinNextInIndex(ulong,_CmsRow *,_SmsLookupStack *,_SmsQuickIndex *)
0x1c0087436  test    eax, eax
0x1c0087438  jns     loc_1C00872F6
0x1c008743e  jmp     loc_1C004F993
0x1c0087443  mov     r12d, 0C000009Ah
0x1c0087449  jmp     loc_1C004FA5E
0x1c008744e  movzx   esi, r14w
0x1c0087452  cmp     r14w, [r15+88h]
0x1c008745a  jnb     loc_1C004F9AD
0x1c0087460  movzx   edi, si
0x1c0087463  shl     rdi, 5
0x1c0087467  add     rdi, [r15+80h]
0x1c008746e  mov     rcx, [rdi+10h]; this
0x1c0087472  mov     eax, [rcx+10h]
0x1c0087475  bt      rax, 12h
0x1c008747a  jb      loc_1C0087586
0x1c0087480  call    ?IsRootOfBindableUnit@CmsBPlusTable@@QEAAEXZ; CmsBPlusTable::IsRootOfBindableUnit(void)
0x1c0087485  test    al, al
0x1c0087487  jz      loc_1C0087586
0x1c008748d  mov     edx, 50h ; 'P'; NumberOfBytes
0x1c0087492  mov     ecx, 200h; PoolType
0x1c0087497  mov     r8d, 6950534Dh; Tag
0x1c008749d  call    cs:__imp_ExAllocatePoolWithTag
0x1c00874a4  nop     dword ptr [rax+rax+00h]
0x1c00874a9  mov     r13, rax
0x1c00874ac  test    rax, rax
0x1c00874af  jz      short loc_1C0087443
0x1c00874b1  mov     [rax+40h], rdi
0x1c00874b5  lea     rdi, [r15+178h]
0x1c00874bc  mov     rcx, rdi; SpinLock
0x1c00874bf  mov     [rax+48h], r15
0x1c00874c3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c00874ca  nop     dword ptr [rax+rax+00h]
0x1c00874cf  mov     r12b, al
0x1c00874d2  mov     eax, [r15+140h]
0x1c00874d9  cmp     eax, dword ptr [rbp+57h+arg_0]
0x1c00874dc  jb      short loc_1C0087529
0x1c00874de  mov     dl, r12b; NewIrql
0x1c00874e1  mov     rcx, rdi; SpinLock
0x1c00874e4  call    cs:__imp_KeReleaseSpinLock
0x1c00874eb  nop     dword ptr [rax+rax+00h]
0x1c00874f0  xor     r9d, r9d; Alertable
0x1c00874f3  mov     [rsp+120h+Timeout], r14; Timeout
0x1c00874f8  xor     r8d, r8d; WaitMode
0x1c00874fb  lea     rcx, [r15+148h]; Object
0x1c0087502  xor     edx, edx; WaitReason
0x1c0087504  call    cs:__imp_KeWaitForSingleObject
0x1c008750b  nop     dword ptr [rax+rax+00h]
0x1c0087510  mov     rcx, rdi; SpinLock
0x1c0087513  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c008751a  nop     dword ptr [rax+rax+00h]
0x1c008751f  mov     r12b, al
0x1c0087522  mov     eax, [r15+140h]
0x1c0087529  inc     eax
0x1c008752b  lea     rcx, [r15+160h]; Event
0x1c0087532  mov     [r15+140h], eax
0x1c0087539  call    cs:__imp_KeClearEvent
0x1c0087540  nop     dword ptr [rax+rax+00h]
0x1c0087545  lea     rcx, [r15+148h]; Event
0x1c008754c  call    cs:__imp_KeClearEvent
0x1c0087553  nop     dword ptr [rax+rax+00h]
0x1c0087558  mov     dl, r12b; NewIrql
0x1c008755b  mov     rcx, rdi; SpinLock
0x1c008755e  call    cs:__imp_KeReleaseSpinLock
0x1c0087565  nop     dword ptr [rax+rax+00h]
0x1c008756a  mov     r9d, 6; enum _WORK_QUEUE_TYPE
0x1c0087570  lea     rdx, ?RedoTUTables@CmsRestarter@@CAXPEAX@Z; void (*)(void *)
0x1c0087577  mov     r8, r13; void *
0x1c008757a  mov     rcx, r13; struct _MS_WORK_QUEUE_ITEM *
0x1c008757d  call    ?MsInitializeAndQueueWorkItem@@YAXPEAU_MS_WORK_QUEUE_ITEM@@P6AXPEAX@Z1W4_WORK_QUEUE_TYPE@@@Z; MsInitializeAndQueueWorkItem(_MS_WORK_QUEUE_ITEM *,void (*)(void *),void *,_WORK_QUEUE_TYPE)
0x1c0087582  mov     r13, [rbp+57h+arg_8]
0x1c0087586  xor     r8d, r8d; struct _SmsLsn *
0x1c0087589  xor     edx, edx; unsigned __int8
0x1c008758b  mov     rcx, r13; this
0x1c008758e  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x1c0087593  inc     si
0x1c0087596  cmp     si, [r15+88h]
0x1c008759e  jb      loc_1C0087460
0x1c00875a4  jmp     loc_1C004F9AD
0x1c00875a9  movzx   esi, r14w
0x1c00875ad  movzx   edi, r14w
  ... truncated ...
```

# CmsDurableLog::WriteLog(void)

- ea: `0x1400602cc`
- end: `0x140060971`
- name: `?WriteLog@CmsDurableLog@@QEAAJXZ`
- size: `1701`
- prototype: `__int64 __fastcall(CmsDurableLog *__hidden this)`
- caller_count: `5`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005f2e0`
- `0x14005ff20`
- `0x1400cb4e4`
- `0x1401408c0`
- `0x140154ae0`

## callees

- `0x14005e910`
- `0x14005f030`
- `0x14005f0d4`
- `0x14005f100`
- `0x14005f210`
- `0x1400602cc`
- `0x140060b80`
- `0x140060d48`
- `0x140060d80`
- `0x1400612d0`
- `0x140061640`
- `0x140062510`
- `0x14007fba0`
- `0x14008e780`
- `0x1400930d0`
- `0x1400bcf80`
- `0x1400c4acc`
- `0x14012084c`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x14006094e`
- `ntoskrnl!IoClearActivityIdThread` at `0x14006094e`
- `ntoskrnl!IoSetActivityIdThread` at `0x140060315`
- `ntoskrnl!IoSetActivityIdThread` at `0x140060315`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060362`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006046f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060546`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006061f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400606dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060897`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060362`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006046f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060546`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006061f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400606dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060897`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060385`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400603bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400604d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400605b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060741`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400608f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060931`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060385`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400603bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400604d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400605b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060741`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400608f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060931`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x140060812`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x140060812`
- `ntoskrnl!IoTransferActivityId` at `0x140060332`
- `ntoskrnl!IoTransferActivityId` at `0x140060349`
- `ntoskrnl!IoTransferActivityId` at `0x140060332`
- `ntoskrnl!IoTransferActivityId` at `0x140060349`

## pseudocode

```c
__int64 __fastcall CmsDurableLog::WriteLog(CmsDurableLog *this)
{
  char *v3; // rdi
  __int64 v4; // rsi
  KIRQL v5; // al
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rcx
  struct _SmsMergeState *v9; // rsi
  void *IoRequest; // r15
  unsigned int RunCount; // eax
  __int64 v12; // rcx
  unsigned int v13; // r14d
  KSPIN_LOCK *v14; // r12
  unsigned int i; // eax
  _QWORD *v16; // r14
  int v17; // eax
  __int64 v18; // rdi
  KIRQL v19; // al
  bool v20; // zf
  KIRQL v21; // dl
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // rcx
  int v25; // eax
  void *v26; // rax
  _QWORD *IoRun; // rdi
  unsigned int v28; // r13d
  struct _MS_IO_RUN *Run; // rax
  struct _MS_IO_RUN *v30; // r12
  _QWORD *v31; // r14
  __int64 v32; // rdx
  unsigned int v33; // ecx
  size_t Size; // [rsp+28h] [rbp-61h]
  int v35; // [rsp+30h] [rbp-59h]
  int v36; // [rsp+30h] [rbp-59h]
  char v37; // [rsp+38h] [rbp-51h]
  unsigned __int64 v38; // [rsp+38h] [rbp-51h]
  int v39; // [rsp+60h] [rbp-29h]
  __int64 v40; // [rsp+68h] [rbp-21h] BYREF
  __int64 v41; // [rsp+70h] [rbp-19h]
  void *Src; // [rsp+78h] [rbp-11h]
  int v43[2]; // [rsp+80h] [rbp-9h]
  PKSPIN_LOCK SpinLock; // [rsp+88h] [rbp-1h]
  __int64 v45; // [rsp+90h] [rbp+7h] BYREF
  __int64 v46; // [rsp+98h] [rbp+Fh]
  KIRQL NewIrql; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v48; // [rsp+F8h] [rbp+6Fh]
  unsigned int v49; // [rsp+100h] [rbp+77h]
  size_t v50; // [rsp+108h] [rbp+7Fh]

  v40 = 0;
  if ( _InterlockedExchange((volatile __int32 *)this + 50, 1) == 1 )
    return 259;
  v3 = (char *)this + 300;
  v4 = IoSetActivityIdThread((char *)this + 300);
  v46 = v4;
  IoTransferActivityId(v3, &MsActivityIdLogWrite);
  if ( v4 )
    IoTransferActivityId(v3, v4);
  if ( *((_QWORD *)this + 11) )
    goto LABEL_11;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
  *((_BYTE *)this + 48) = v5;
  if ( *((_QWORD *)this + 11) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)this + 5, v5);
LABEL_11:
    v7 = *((_QWORD *)this + 10);
    if ( (*(_DWORD *)(v7 + 3460) & 0x20000000) != 0 || (*((_DWORD *)this + 74) & 4) == 0 )
    {
      IoRequest = 0;
      CmsDurableLog::DeleteOutstandingWrites(this);
      v6 = -1073741202;
LABEL_65:
      CmsDurableLog::ReleaseActiveLogWriter(this);
      if ( IoRequest )
        MsKmeReleaseIoRequest(IoRequest);
      goto LABEL_67;
    }
    v8 = *(_QWORD *)(v7 + 48);
    v9 = 0;
    v48 = 0;
    v6 = 0;
    IoRequest = (void *)MsKmeAllocateIoRequest(v8, (unsigned int)MsPerfParams, 516);
    RunCount = MsKmeGetRunCount((struct _MSENV_IO_REQUEST *)IoRequest, 0);
    v12 = *((_QWORD *)this + 10);
    v13 = RunCount;
    v49 = RunCount;
    _InterlockedIncrement64((volatile signed __int64 *)(v12 + 920));
    if ( RunCount > 1 )
    {
      v9 = CmsDurableLog::ShouldDoubleBufferWrites((KSPIN_LOCK *)this);
      if ( v9 )
        v49 = v13 - 1;
    }
    MsKmeSetCallbackIoRequest(
      (struct _MSENV_IO_REQUEST *)IoRequest,
      (int (*)(struct _MSENV_IO_REQUEST *, int, void *, void *, void *, void *))CmsDurableLog::LogWriteBatchCompletion,
      this,
      v9,
      0,
      0);
    v14 = (KSPIN_LOCK *)((char *)this + 40);
    *((_BYTE *)this + 48) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
    for ( i = 0; ; i = ++v48 )
    {
      v16 = (_QWORD *)*((_QWORD *)this + 11);
      if ( !v16 || i >= v49 )
      {
        if ( v6 >= 0 )
          goto LABEL_45;
LABEL_44:
        v14 = (KSPIN_LOCK *)((char *)this + 40);
        goto LABEL_45;
      }
      if ( v6 < 0 )
        goto LABEL_44;
      v45 = v16[7];
      *((_QWORD *)this + 11) = v16[6];
      v16[6] = 0;
      if ( *((_QWORD **)this + 12) == v16 )
        *((_QWORD *)this + 12) = 0;
      v14 = (KSPIN_LOCK *)((char *)this + 40);
      KeReleaseSpinLock((PKSPIN_LOCK)this + 5, *((_BYTE *)this + 48));
      v17 = *((_DWORD *)this + 74);
      if ( (v17 & 2) == 0 )
        *((_DWORD *)this + 74) = v17 | 2;
      memset(
        (void *)(v16[1] + *((unsigned int *)v16 + 8)),
        0,
        (unsigned int)(*((_DWORD *)v16 + 6) - *((_DWORD *)v16 + 8)));
      v18 = *((_QWORD *)this + 9);
      v41 = v16[7];
      LODWORD(v50) = *((_DWORD *)v16 + 6);
      Src = (void *)v16[1];
      v39 = *((_DWORD *)v16 + 9);
      *(_QWORD *)v43 = *v16;
      v40 = -1;
      SpinLock = (PKSPIN_LOCK)(v18 + 3776);
      v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v18 + 3776));
      v20 = *(_DWORD *)(v18 + 3656) == 6;
      v21 = v19;
      NewIrql = v19;
      if ( !v20 || (*(_DWORD *)(v18 + 12256) & 0x10) != 0 )
      {
        v6 = -1073741436;
      }
      else
      {
        LODWORD(Size) = v50;
        v22 = LogCoreWriteDataRecord(
                v18,
                (int)IoRequest,
                v43[0],
                v39,
                Src,
                Size,
                v35,
                v37,
                v41,
                (__int64)&v40,
                (__int64)&NewIrql);
        v21 = NewIrql;
        v6 = v22;
      }
      KeReleaseSpinLock(SpinLock, v21);
      if ( v6 == -1073741670 )
        break;
      _InterlockedAdd((volatile signed __int32 *)this + 73, -*((_DWORD *)v16 + 11));
      if ( v6 < 0 )
      {
        if ( v6 != -1073741802 )
        {
          v24 = *((_QWORD *)this + 10);
          if ( (*(_DWORD *)(v24 + 3460) & 0x20000000) == 0 )
          {
            LOBYTE(v23) = 1;
            CmsVolume::ChangeVolumeOptionDynamically(v24, 0x20000000, v23);
          }
          LOBYTE(Size) = 1;
          CmsVolume::NotifyUnrecoverableMetadata(*((_QWORD *)this + 10), (unsigned int)v6, 0xC40170F41LL, 0, 0, Size);
          v25 = *((_DWORD *)v16 + 11);
          if ( v25 )
          {
            _InterlockedAdd((volatile signed __int32 *)this + 72, -v25);
            *((_DWORD *)v16 + 11) = 0;
          }
          CmsTxMemLog::FreeRedoBlock(v16);
          CmsDurableLog::DeleteOutstandingWrites(this);
          if ( v9 )
          {
            if ( *(_QWORD *)v9 )
              CmsLookasides::Free(*(void **)v9);
            CmsLookasides::Free(v9);
          }
          goto LABEL_65;
        }
        v14 = (KSPIN_LOCK *)((char *)this + 40);
      }
      *((_QWORD *)MsKmeGetRun((struct _MSENV_IO_REQUEST *)IoRequest, v48) + 6) = v16;
      v16[8] = v40;
      CmsDurableLog::CheckForVirtualWaiterMigration(this, (struct _SmsLsn *)&v45, (union _ML_LSN *)&v40, 0);
      *((_BYTE *)this + 48) = KeAcquireSpinLockRaiseToDpc(v14);
      *((_QWORD *)this + 14) = v16[7];
      *((_QWORD *)this + 16) = v40;
    }
    *((_BYTE *)this + 48) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
    v16[6] = *((_QWORD *)this + 11);
    v20 = *((_QWORD *)this + 12) == 0;
    *((_QWORD *)this + 11) = v16;
    if ( v20 )
      *((_QWORD *)this + 12) = v16;
LABEL_45:
    if ( v9 && v48 >= dword_14026214C )
    {
      KeReleaseSpinLock(v14, *((_BYTE *)this + 48));
      v26 = *(void **)v9;
      v38 = ~(unsigned __int64)(unsigned int)(*((_DWORD *)v9 + 2) + 256);
      v36 = *((_DWORD *)v9 + 2);
      *((_QWORD *)v9 + 2) = v38;
      IoRun = (_QWORD *)MsKmeAllocateIoRun(IoRequest, 0, 0, 0, 3, v26, v36, v38);
      if ( IoRun )
      {
        IoRun[5] = 0;
        IoRun[4] = LogWriteDoubleBufferWriteCompletion;
        IoRun[6] = 0;
        IoRun[7] = 0;
        v28 = 0;
        if ( MsKmeGetRunCount((struct _MSENV_IO_REQUEST *)IoRequest, 1u) != 1 )
        {
          do
          {
            Run = MsKmeGetRun((struct _MSENV_IO_REQUEST *)IoRequest, v28);
            v30 = Run;
            v31 = (_QWORD *)((char *)Run + 16);
            if ( !*((_DWORD *)v9 + 6) )
              *((_QWORD *)v9 + 2) = *v31;
            v32 = *((unsigned int *)v9 + 3);
            if ( *v31 != v32 + *((_QWORD *)v9 + 2) )
              break;
            v33 = *((_DWORD *)Run + 2);
            if ( v33 > *((_DWORD *)v9 + 2) - (int)v32 )
              break;
            RtlCopyMemoryNonTemporal((void *)(v32 + *(_QWORD *)v9), *(const void **)Run, v33);
            *((_DWORD *)v9 + 3) += *((_DWORD *)v30 + 2);
            ++*((_DWORD *)v9 + 6);
            MsKmeSetIoRun(IoRequest, v30, 0, 2, *((_DWORD *)v30 + 2), *v31);
            ++v28;
          }
          while ( v28 < MsKmeGetRunCount((struct _MSENV_IO_REQUEST *)IoRequest, 1u) - 1 );
          v14 = (KSPIN_LOCK *)((char *)this + 40);
        }
      }
      if ( *((_DWORD *)v9 + 6) )
        MsKmeSetIoRun(IoRequest, IoRun, 0, 1, *((_DWORD *)v9 + 3), *((_QWORD *)v9 + 2));
      *((_BYTE *)this + 48) = KeAcquireSpinLockRaiseToDpc(v14);
    }
    _InterlockedAdd((volatile signed __int32 *)this + 48, MsKmeGetRunCount((struct _MSENV_IO_REQUEST *)IoRequest, 1u));
    if ( MsPerfStats < v48 )
      MsPerfStats = v48;
    if ( (unsigned int)dword_140261EC4 < *((_DWORD *)this + 48) )
      dword_140261EC4 = *((_DWORD *)this + 48);
    CmsDurableLog::ReleaseActiveLogWriter(this);
    KeReleaseSpinLock(v14, *((_BYTE *)this + 48));
    MsKmeSubmitIoRequest((struct _MSENV_IO_REQUEST *)IoRequest);
    goto LABEL_63;
  }
  CmsDurableLog::ReleaseActiveLogWriter(this);
  KeReleaseSpinLock((PKSPIN_LOCK)this + 5, *((_BYTE *)this + 48));
  if ( !_bittest((const signed __int32 *)(*((_QWORD *)this + 10) + 3460LL), 0x1Du) && (*((_DWORD *)this + 74) & 4) != 0 )
  {
LABEL_63:
    v6 = 259;
    goto LABEL_67;
  }
  v6 = -1073741202;
LABEL_67:
  IoClearActivityIdThread(v46);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400602cc  push    rbp
0x1400602ce  push    rbx
0x1400602cf  push    rsi
0x1400602d0  push    rdi
0x1400602d1  push    r12
0x1400602d3  push    r13
0x1400602d5  push    r14
0x1400602d7  push    r15
0x1400602d9  lea     rbp, [rsp-1Fh]
0x1400602de  sub     rsp, 0A8h
0x1400602e5  xor     r12d, r12d
0x1400602e8  mov     rbx, rcx
0x1400602eb  mov     [rbp+57h+var_78], r12
0x1400602ef  nop
0x1400602f0  lea     eax, [r12+1]
0x1400602f5  xchg    eax, [rcx+0C8h]
0x1400602fb  nop
0x1400602fc  cmp     eax, 1
0x1400602ff  jnz     short loc_14006030B
0x140060301  mov     eax, 103h
0x140060306  jmp     loc_14006095C
0x14006030b  lea     rdi, [rcx+12Ch]
0x140060312  mov     rcx, rdi
0x140060315  call    cs:__imp_IoSetActivityIdThread
0x14006031c  nop     dword ptr [rax+rax+00h]
0x140060321  lea     rdx, ?MsActivityIdLogWrite@@3U_GUID@@B; _GUID const MsActivityIdLogWrite
0x140060328  mov     rcx, rdi
0x14006032b  mov     rsi, rax
0x14006032e  mov     [rbp+57h+var_48], rax
0x140060332  call    cs:__imp_IoTransferActivityId
0x140060339  nop     dword ptr [rax+rax+00h]
0x14006033e  test    rsi, rsi
0x140060341  jz      short loc_140060355
0x140060343  mov     rdx, rsi
0x140060346  mov     rcx, rdi
0x140060349  call    cs:__imp_IoTransferActivityId
0x140060350  nop     dword ptr [rax+rax+00h]
0x140060355  cmp     [rbx+58h], r12
0x140060359  jnz     short loc_1400603C8
0x14006035b  lea     rdi, [rbx+28h]
0x14006035f  mov     rcx, rdi; SpinLock
0x140060362  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140060369  nop     dword ptr [rax+rax+00h]
0x14006036e  mov     [rbx+30h], al
0x140060371  cmp     [rbx+58h], r12
0x140060375  jnz     short loc_1400603B7
0x140060377  mov     rcx, rbx; this
0x14006037a  call    ?ReleaseActiveLogWriter@CmsDurableLog@@AEAAXXZ; CmsDurableLog::ReleaseActiveLogWriter(void)
0x14006037f  mov     dl, [rbx+30h]; NewIrql
0x140060382  mov     rcx, rdi; SpinLock
0x140060385  call    cs:__imp_KeReleaseSpinLock
0x14006038c  nop     dword ptr [rax+rax+00h]
0x140060391  mov     rax, [rbx+50h]
0x140060395  bt      dword ptr [rax+0D84h], 1Dh
0x14006039d  jb      short loc_1400603AD
0x14006039f  mov     eax, [rbx+128h]
0x1400603a5  test    al, 4
0x1400603a7  jnz     loc_140060906
0x1400603ad  mov     edi, 0C000026Eh
0x1400603b2  jmp     loc_14006094A
0x1400603b7  mov     dl, al; NewIrql
0x1400603b9  mov     rcx, rdi; SpinLock
0x1400603bc  call    cs:__imp_KeReleaseSpinLock
0x1400603c3  nop     dword ptr [rax+rax+00h]
0x1400603c8  mov     rcx, [rbx+50h]
0x1400603cc  mov     r13d, 20000000h
0x1400603d2  test    [rcx+0D84h], r13d
0x1400603d9  jnz     loc_14006090D
0x1400603df  mov     eax, [rbx+128h]
0x1400603e5  test    al, 4
0x1400603e7  jz      loc_14006090D
0x1400603ed  mov     edx, cs:MsPerfParams
0x1400603f3  mov     r8d, 204h
0x1400603f9  mov     rcx, [rcx+30h]
0x1400603fd  mov     rsi, r12
0x140060400  mov     [rbp+57h+arg_8], r12d
0x140060404  mov     edi, r12d
0x140060407  call    ?MsKmeAllocateIoRequest@@YAPEAU_MSENV_IO_REQUEST@@PEAU_VCB@@KW4_EMS_IO_REQUEST_FLAGS@@@Z; MsKmeAllocateIoRequest(_VCB *,ulong,_EMS_IO_REQUEST_FLAGS)
0x14006040c  xor     edx, edx; unsigned __int8
0x14006040e  mov     rcx, rax; struct _MSENV_IO_REQUEST *
0x140060411  mov     r15, rax
0x140060414  call    ?MsKmeGetRunCount@@YAKPEAU_MSENV_IO_REQUEST@@E@Z; MsKmeGetRunCount(_MSENV_IO_REQUEST *,uchar)
0x140060419  mov     rcx, [rbx+50h]
0x14006041d  mov     r14d, eax
0x140060420  nop
0x140060421  mov     [rbp+57h+arg_10], eax
0x140060424  lock inc qword ptr [rcx+398h]
0x14006042c  nop
0x14006042d  cmp     eax, 1
0x140060430  jbe     short loc_140060449
0x140060432  mov     rcx, rbx; this
0x140060435  call    ?ShouldDoubleBufferWrites@CmsDurableLog@@AEAAPEAU_SmsMergeState@@XZ; CmsDurableLog::ShouldDoubleBufferWrites(void)
0x14006043a  mov     rsi, rax
0x14006043d  test    rax, rax
0x140060440  jz      short loc_140060449
0x140060442  dec     r14d
0x140060445  mov     [rbp+57h+arg_10], r14d
0x140060449  mov     [rsp+0E0h+Size], r12; void *
0x14006044e  lea     rdx, ?LogWriteBatchCompletion@CmsDurableLog@@CAJPEAU_MSENV_IO_REQUEST@@JPEAX111@Z; int (*)(struct _MSENV_IO_REQUEST *, int, void *, void *, void *, void *)
0x140060455  mov     r9, rsi; void *
0x140060458  mov     [rsp+0E0h+Src], r12; void *
0x14006045d  mov     r8, rbx; void *
0x140060460  mov     rcx, r15; struct _MSENV_IO_REQUEST *
0x140060463  call    ?MsKmeSetCallbackIoRequest@@YAXPEAU_MSENV_IO_REQUEST@@P6AJ0JPEAX111@Z1111@Z; MsKmeSetCallbackIoRequest(_MSENV_IO_REQUEST *,long (*)(_MSENV_IO_REQUEST *,long,void *,void *,void *,void *),void *,void *,void *,void *)
0x140060468  lea     r12, [rbx+28h]
0x14006046c  mov     rcx, r12; SpinLock
0x14006046f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140060476  nop     dword ptr [rax+rax+00h]
0x14006047b  mov     [rbx+30h], al
0x14006047e  mov     eax, edi
0x140060480  mov     r14, [rbx+58h]
0x140060484  test    r14, r14
0x140060487  jz      loc_140060704
0x14006048d  cmp     eax, [rbp+57h+arg_10]
0x140060490  jnb     loc_140060704
0x140060496  mov     r12b, 1
0x140060499  test    edi, edi
0x14006049b  js      loc_14006070B
0x1400604a1  mov     rax, [r14+38h]
0x1400604a5  mov     [rbp+57h+var_50], rax
0x1400604a9  mov     rax, [r14+30h]
0x1400604ad  mov     [rbx+58h], rax
0x1400604b1  mov     qword ptr [r14+30h], 0
0x1400604b9  cmp     [rbx+60h], r14
0x1400604bd  jnz     short loc_1400604C7
0x1400604bf  mov     qword ptr [rbx+60h], 0
0x1400604c7  mov     dl, [rbx+30h]; NewIrql
0x1400604ca  lea     r12, [rbx+28h]
0x1400604ce  mov     rcx, r12; SpinLock
0x1400604d1  call    cs:__imp_KeReleaseSpinLock
0x1400604d8  nop     dword ptr [rax+rax+00h]
0x1400604dd  mov     eax, [rbx+128h]
0x1400604e3  test    al, 2
0x1400604e5  jnz     short loc_1400604F0
0x1400604e7  or      eax, 2
0x1400604ea  mov     [rbx+128h], eax
0x1400604f0  mov     ecx, [r14+20h]
0x1400604f4  xor     edx, edx; Val
0x1400604f6  mov     r8d, [r14+18h]
0x1400604fa  sub     r8d, ecx; Size
0x1400604fd  add     rcx, [r14+8]; void *
0x140060501  call    memset
0x140060506  mov     rax, [r14+38h]
0x14006050a  mov     rdi, [rbx+48h]
0x14006050e  mov     [rbp+57h+var_70], rax
0x140060512  mov     eax, [r14+18h]
0x140060516  mov     dword ptr [rbp+57h+arg_18], eax
0x140060519  mov     rax, [r14+8]
0x14006051d  mov     [rbp+57h+var_68], rax
0x140060521  mov     eax, [r14+24h]
0x140060525  mov     [rbp+57h+var_80], eax
0x140060528  mov     rax, [r14]
0x14006052b  mov     qword ptr [rbp+57h+var_60], rax
0x14006052f  or      eax, 0FFFFFFFFh
0x140060532  mov     dword ptr [rbp+57h+var_78], eax
0x140060535  mov     dword ptr [rbp+57h+var_78+4], eax
0x140060538  lea     rax, [rdi+0EC0h]
0x14006053f  mov     rcx, rax; SpinLock
0x140060542  mov     [rbp+57h+SpinLock], rax
0x140060546  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006054d  nop     dword ptr [rax+rax+00h]
0x140060552  cmp     dword ptr [rdi+0E48h], 6
0x140060559  mov     dl, al
0x14006055b  mov     [rbp+57h+NewIrql], al
0x14006055e  jz      short loc_140060567
0x140060560  mov     edi, 0C0000184h
0x140060565  jmp     short loc_1400605B4
0x140060567  mov     eax, [rdi+2FE0h]
0x14006056d  test    al, 10h
0x14006056f  jnz     short loc_140060560
0x140060571  mov     r9d, [rbp+57h+var_80]; int
0x140060575  lea     rax, [rbp+57h+NewIrql]
0x140060579  mov     r8, qword ptr [rbp+57h+var_60]; int
0x14006057d  mov     rdx, r15; int
0x140060580  mov     [rsp+0E0h+var_90], rax; __int64
0x140060585  mov     rcx, rdi; int
0x140060588  lea     rax, [rbp+57h+var_78]
0x14006058c  mov     [rsp+0E0h+var_98], rax; __int64
0x140060591  mov     rax, [rbp+57h+var_70]
0x140060595  mov     [rsp+0E0h+var_A0], rax; __int64
0x14006059a  mov     eax, dword ptr [rbp+57h+arg_18]
0x14006059d  mov     dword ptr [rsp+0E0h+Size], eax; Size
0x1400605a1  mov     rax, [rbp+57h+var_68]
0x1400605a5  mov     [rsp+0E0h+Src], rax; Src
0x1400605aa  call    LogCoreWriteDataRecord
0x1400605af  mov     dl, [rbp+57h+NewIrql]; NewIrql
0x1400605b2  mov     edi, eax
0x1400605b4  mov     rcx, [rbp+57h+SpinLock]; SpinLock
0x1400605b8  call    cs:__imp_KeReleaseSpinLock
0x1400605bf  nop     dword ptr [rax+rax+00h]
0x1400605c4  cmp     edi, 0C000009Ah
0x1400605ca  jz      loc_1400606D9
0x1400605d0  mov     eax, [r14+2Ch]
0x1400605d4  nop
0x1400605d5  neg     eax
0x1400605d7  lock add [rbx+124h], eax
0x1400605de  nop
0x1400605df  test    edi, edi
0x1400605e1  jns     short loc_1400605F2
0x1400605e3  xor     r12b, r12b
0x1400605e6  cmp     edi, 0C0000016h
0x1400605ec  jnz     short loc_14006064E
0x1400605ee  lea     r12, [rbx+28h]
0x1400605f2  mov     edx, [rbp+57h+arg_8]; unsigned int
0x1400605f5  mov     rcx, r15; struct _MSENV_IO_REQUEST *
0x1400605f8  call    ?MsKmeGetRun@@YAPEAU_MS_IO_RUN@@PEAU_MSENV_IO_REQUEST@@K@Z; MsKmeGetRun(_MSENV_IO_REQUEST *,ulong)
0x1400605fd  xor     r9d, r9d; unsigned __int8
0x140060600  lea     r8, [rbp+57h+var_78]; union _ML_LSN *
0x140060604  lea     rdx, [rbp+57h+var_50]; struct _SmsLsn *
0x140060608  mov     rcx, rbx; this
0x14006060b  mov     [rax+30h], r14
0x14006060f  mov     rax, [rbp+57h+var_78]
0x140060613  mov     [r14+40h], rax
0x140060617  call    ?CheckForVirtualWaiterMigration@CmsDurableLog@@AEAAXPEAU_SmsLsn@@PEAT_ML_LSN@@E@Z; CmsDurableLog::CheckForVirtualWaiterMigration(_SmsLsn *,_ML_LSN *,uchar)
0x14006061c  mov     rcx, r12; SpinLock
0x14006061f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140060626  nop     dword ptr [rax+rax+00h]
0x14006062b  mov     [rbx+30h], al
0x14006062e  mov     rax, [r14+38h]
0x140060632  mov     [rbx+70h], rax
0x140060636  mov     rax, [rbp+57h+var_78]
0x14006063a  mov     [rbx+80h], rax
0x140060641  mov     eax, [rbp+57h+arg_8]
0x140060644  inc     eax
0x140060646  mov     [rbp+57h+arg_8], eax
0x140060649  jmp     loc_140060480
0x14006064e  mov     rcx, [rbx+50h]
0x140060652  test    [rcx+0D84h], r13d
0x140060659  jnz     short loc_140060666
0x14006065b  mov     r8b, 1
0x14006065e  mov     edx, r13d
0x140060661  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x140060666  mov     rcx, [rbx+50h]
0x14006066a  xor     r9d, r9d
0x14006066d  mov     byte ptr [rsp+0E0h+Size], 1
0x140060672  mov     r8, 0C40170F41h
0x14006067c  mov     edx, edi
0x14006067e  mov     dword ptr [rsp+0E0h+Src], 0
0x140060686  call    ?NotifyUnrecoverableMetadata@CmsVolume@@QEAAXJ_KPEATSmsBigIdentifier@@W4_MS_METADATA_EVENT_NOTIFY_TYPE@@E@Z; CmsVolume::NotifyUnrecoverableMetadata(long,unsigned __int64,SmsBigIdentifier *,_MS_METADATA_EVENT_NOTIFY_TYPE,uchar)
0x14006068b  mov     eax, [r14+2Ch]
0x14006068f  test    eax, eax
0x140060691  jz      short loc_1400606A6
0x140060693  neg     eax
0x140060695  nop
0x140060696  lock add [rbx+120h], eax
0x14006069d  nop
0x14006069e  mov     dword ptr [r14+2Ch], 0
0x1400606a6  mov     rcx, r14; P
0x1400606a9  call    ?FreeRedoBlock@CmsTxMemLog@@SAXPEAU_SmsRedoBlock@@@Z; CmsTxMemLog::FreeRedoBlock(_SmsRedoBlock *)
0x1400606ae  mov     rcx, rbx; this
0x1400606b1  call    ?DeleteOutstandingWrites@CmsDurableLog@@AEAAXXZ; CmsDurableLog::DeleteOutstandingWrites(void)
0x1400606b6  test    rsi, rsi
0x1400606b9  jz      loc_14006091D
0x1400606bf  mov     rcx, [rsi]; void *
0x1400606c2  test    rcx, rcx
0x1400606c5  jz      short loc_1400606CC
0x1400606c7  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x1400606cc  mov     rcx, rsi; void *
0x1400606cf  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x1400606d4  jmp     loc_14006091D
0x1400606d9  mov     rcx, r12; SpinLock
0x1400606dc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400606e3  nop     dword ptr [rax+rax+00h]
0x1400606e8  mov     [rbx+30h], al
0x1400606eb  mov     rax, [rbx+58h]
0x1400606ef  mov     [r14+30h], rax
0x1400606f3  cmp     qword ptr [rbx+60h], 0
0x1400606f8  mov     [rbx+58h], r14
0x1400606fc  jnz     short loc_140060723
0x1400606fe  mov     [rbx+60h], r14
0x140060702  jmp     short loc_140060723
0x140060704  test    edi, edi
0x140060706  jns     short loc_140060723
0x140060708  mov     r12b, 1
0x14006070b  cmp     edi, 0C000009Ah
0x140060711  jz      short loc_14006071F
0x140060713  cmp     edi, 0C0000016h
0x140060719  jnz     loc_14006091D
0x14006071f  lea     r12, [rbx+28h]
0x140060723  test    rsi, rsi
0x140060726  jz      loc_1400608A6
0x14006072c  mov     eax, [rbp+57h+arg_8]
0x14006072f  cmp     eax, cs:dword_14026214C
0x140060735  jb      loc_1400608A6
0x14006073b  mov     dl, [rbx+30h]; NewIrql
0x14006073e  mov     rcx, r12; SpinLock
0x140060741  call    cs:__imp_KeReleaseSpinLock
0x140060748  nop     dword ptr [rax+rax+00h]
0x14006074d  mov     edx, [rsi+8]
0x140060750  xor     r9d, r9d
0x140060753  mov     rax, [rsi]
0x140060756  xor     r8d, r8d
0x140060759  lea     ecx, [rdx+100h]
0x14006075f  not     rcx
0x140060762  mov     [rsp+0E0h+var_A8], rcx
0x140060767  mov     [rsp+0E0h+var_B0], edx
0x14006076b  xor     edx, edx
0x14006076d  mov     [rsi+10h], rcx
0x140060771  mov     rcx, r15
0x140060774  mov     [rsp+0E0h+Size], rax
  ... truncated ...
```

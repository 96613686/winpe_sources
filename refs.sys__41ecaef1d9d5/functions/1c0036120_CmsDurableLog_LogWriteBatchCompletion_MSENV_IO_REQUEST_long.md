# CmsDurableLog::LogWriteBatchCompletion(_MSENV_IO_REQUEST *,long)

- ea: `0x1c0036120`
- end: `0x1c00363ae`
- name: `?LogWriteBatchCompletion@CmsDurableLog@@CAJPEAU_MSENV_IO_REQUEST@@J@Z`
- size: `654`
- prototype: `__int64 __fastcall(struct _MSENV_IO_REQUEST *, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1c0036120`
- `0x1c0036a10`
- `0x1c0037038`
- `0x1c003724c`
- `0x1c00372e4`
- `0x1c0037768`
- `0x1c0037df4`
- `0x1c004e92c`
- `0x1c0052a54`
- `0x1c006ac80`
- `0x1c00dfe1c`
- `0x1c00e5bcc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c0036223`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007fdee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0036223`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007fdee`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c007fe42`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c007fe42`
- `ntoskrnl!KeSetEvent` at `0x1c007fe97`
- `ntoskrnl!KeSetEvent` at `0x1c007fe97`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0036278`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00362b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0036278`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00362b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00362a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00362dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00362a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00362dc`

## pseudocode

```c
__int64 __fastcall CmsDurableLog::LogWriteBatchCompletion(struct _MSENV_IO_REQUEST *a1, int a2)
{
  unsigned __int64 v2; // rdi
  int v5; // r13d
  __int64 v6; // r8
  __int64 v7; // rax
  CmsDurableLog *v8; // rbx
  __int64 v9; // rsi
  void *v10; // rcx
  __int64 v11; // r14
  int v12; // ecx
  void *v13; // rcx
  CmsDurableLog *v14; // rdi
  CmsDurableLog *v15; // rax
  CmsDurableLog *v16; // rdi
  KIRQL v17; // al
  __int64 v18; // rdx
  int v19; // eax
  unsigned int LogFullPercentage; // r14d
  CmsDurableLog *v22; // rcx
  __int64 v23; // rsi
  __int64 v24; // rbx
  int v25; // edi
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  int ActivityIdThread; // eax
  int v31; // [rsp+20h] [rbp-60h]
  __int64 v32; // [rsp+50h] [rbp-30h] BYREF
  __int64 v33; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v34[8]; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v35[8]; // [rsp+68h] [rbp-18h] BYREF
  _BYTE v36[16]; // [rsp+70h] [rbp-10h] BYREF
  CmsDurableLog *v37; // [rsp+D0h] [rbp+50h] BYREF
  void *v38; // [rsp+D8h] [rbp+58h] BYREF

  v2 = ML_LSN_NULL;
  v37 = 0;
  v38 = 0;
  v5 = 0;
  if ( dword_1C0136910 && DbgRedoCreatedCount > (unsigned int)qword_1C0136914 )
    a2 = dword_1C0136910;
  ((void (__fastcall *)(struct _MSENV_IO_REQUEST *, CmsDurableLog **, void **, _QWORD, _QWORD))qword_1C0136D10)(
    a1,
    &v37,
    &v38,
    0,
    0);
  v6 = 1;
  if ( a2 < 0 )
  {
    v22 = v37;
    if ( (*(_DWORD *)(*((_QWORD *)v37 + 10) + 3116LL) & 0x20000000) == 0 )
    {
      CmsVolume::ChangeVolumeOptionDynamically(*((CmsVolume **)v37 + 10), 0x20000000u, 1u);
      v22 = v37;
      v6 = 1;
    }
    if ( qword_1C0136B38 )
    {
      LOBYTE(v31) = 1;
      qword_1C0136B38(
        *(_QWORD *)(*((_QWORD *)v22 + 10) + 48LL),
        0,
        (unsigned int)a2,
        0,
        v31,
        0xD40170CB1LL,
        0,
        (*(_DWORD *)(*((_QWORD *)v22 + 10) + 3116LL) & 0x40000000) != 0);
    }
  }
  v7 = ((__int64 (__fastcall *)(struct _MSENV_IO_REQUEST *, _QWORD, __int64))qword_1C0136CF0)(a1, 0, v6);
  v8 = v37;
  while ( 1 )
  {
    v9 = v7;
    if ( !v7 )
      break;
    (*(void (__fastcall **)(struct _MSENV_IO_REQUEST *, _QWORD, _QWORD, _QWORD, _QWORD))(v7 + 32))(
      a1,
      *(_QWORD *)v7,
      *(unsigned int *)(v7 + 8),
      (unsigned int)a2,
      *(_QWORD *)(v7 + 40));
    v10 = *(void **)(v9 + 56);
    if ( v10 )
    {
      ExFreePoolWithTag(v10, 0);
      *(_QWORD *)(v9 + 56) = 0;
    }
    v11 = *(_QWORD *)(v9 + 48);
    if ( v11 )
    {
      v12 = *(_DWORD *)(v11 + 44);
      v8 = *(CmsDurableLog **)(v11 + 56);
      v2 = *(_QWORD *)(v11 + 64);
      if ( v12 )
      {
        _InterlockedExchangeAdd((volatile signed __int32 *)v37 + 72, -v12);
        *(_DWORD *)(v11 + 44) = 0;
      }
      if ( *(_QWORD *)v11 )
        CmsLookasides::Free(*(void **)v11);
      ExFreePoolWithTag((PVOID)v11, 0);
      *(_QWORD *)(v9 + 48) = 0;
    }
    v7 = ((__int64 (__fastcall *)(struct _MSENV_IO_REQUEST *, _QWORD))qword_1C0136CF0)(a1, (unsigned int)++v5);
  }
  v13 = v38;
  if ( v38 )
  {
    if ( *(_QWORD *)v38 )
    {
      CmsLookasides::Free(*(void **)v38);
      v13 = v38;
    }
    CmsLookasides::Free(v13);
  }
  if ( *(_QWORD *)CmsDurableLog::GetRecoveryDurableLsn(v37, v34) > v2 )
  {
    v14 = v37;
    *((_BYTE *)v14 + 48) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v37 + 5);
    v15 = v37;
    if ( (unsigned __int64)v8 > *((_QWORD *)v37 + 15) )
    {
      *((_QWORD *)v37 + 15) = v8;
      v15 = v37;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)v15 + 5, *((_BYTE *)v15 + 48));
  }
  v16 = v37;
  v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v37 + 5);
  v32 = *((_QWORD *)v16 + 16);
  v33 = *((_QWORD *)v16 + 14);
  *((_BYTE *)v16 + 48) = v17;
  KeReleaseSpinLock((PKSPIN_LOCK)v16 + 5, v17);
  CmsDurableLog::CheckForVirtualWaiterMigration(v16, (struct _SmsLsn *)&v33, (union _ML_LSN *)&v32, 0);
  CmsDurableLog::CheckForDurableWaiterMigration(v37);
  LOBYTE(v18) = 1;
  v19 = ((__int64 (__fastcall *)(struct _MSENV_IO_REQUEST *, __int64))qword_1C0136CF8)(a1, v18);
  _InterlockedExchangeAdd((volatile signed __int32 *)v37 + 48, -v19);
  ((void (__fastcall *)(struct _MSENV_IO_REQUEST *))qword_1C0136CC0)(a1);
  CmsDurableLog::AttemptQueueWriteWorker(v37);
  if ( !*((_DWORD *)v37 + 49) )
  {
    LogFullPercentage = CmsDurableLog::GetLogFullPercentage(v37);
    if ( LogFullPercentage >= (unsigned __int8)byte_1C0136C5C )
    {
      if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
      {
        v23 = *(_QWORD *)CmsDurableLog::GetOldestRecordReference(v37, v35, 0);
        v24 = *(_QWORD *)CmsDurableLog::BaseLsn(v37, v36);
        v25 = *((_DWORD *)v37 + 72);
        ActivityIdThread = IoGetActivityIdThread(v27, v26, v28, v29);
        McTemplateK0qqiii_EtwWriteTransfer(
          (unsigned int)MinstoreEventProvider_Context,
          (unsigned int)LogPulseLazyWriter,
          ActivityIdThread,
          v25,
          LogFullPercentage,
          v24,
          v23,
          0);
      }
      _InterlockedCompareExchange((volatile signed __int32 *)v37 + 49, 1, 0);
      KeSetEvent(&LazyWriterScanEvent, 0, 0);
    }
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x1c0036120  mov     [rsp-38h+arg_0], rbx
0x1c0036125  push    rbp
0x1c0036126  push    rsi
0x1c0036127  push    rdi
0x1c0036128  push    r12
0x1c003612a  push    r13
0x1c003612c  push    r14
0x1c003612e  push    r15
0x1c0036130  mov     rbp, rsp
0x1c0036133  sub     rsp, 80h
0x1c003613a  mov     rdi, cs:ML_LSN_NULL
0x1c0036141  xor     r14d, r14d
0x1c0036144  mov     r12, rcx
0x1c0036147  mov     [rbp+arg_10], r14
0x1c003614b  mov     ecx, cs:dword_1C0136910
0x1c0036151  mov     r15d, edx
0x1c0036154  mov     [rbp+arg_18], r14
0x1c0036158  mov     r13d, r14d
0x1c003615b  test    ecx, ecx
0x1c003615d  jnz     loc_1C007FD5A
0x1c0036163  mov     rax, cs:qword_1C0136D10
0x1c003616a  lea     r8, [rbp+arg_18]
0x1c003616e  xor     r9d, r9d
0x1c0036171  mov     [rsp+80h+var_60], r14
0x1c0036176  lea     rdx, [rbp+arg_10]
0x1c003617a  mov     rcx, r12
0x1c003617d  call    cs:__guard_dispatch_icall_fptr
0x1c0036183  mov     r8d, 1; unsigned __int8
0x1c0036189  test    r15d, r15d
0x1c003618c  js      loc_1C007FD6F
0x1c0036192  mov     rax, cs:qword_1C0136CF0
0x1c0036199  xor     edx, edx
0x1c003619b  mov     rcx, r12
0x1c003619e  call    cs:__guard_dispatch_icall_fptr
0x1c00361a4  mov     rbx, [rbp+arg_10]
0x1c00361a8  mov     rsi, rax
0x1c00361ab  test    rax, rax
0x1c00361ae  jz      loc_1C0036251
0x1c00361b4  mov     rcx, [rsi+28h]
0x1c00361b8  mov     r9d, r15d
0x1c00361bb  mov     rax, [rax+20h]
0x1c00361bf  mov     r8d, [rsi+8]
0x1c00361c3  mov     rdx, [rsi]
0x1c00361c6  mov     [rsp+80h+var_60], rcx
0x1c00361cb  mov     rcx, r12
0x1c00361ce  call    cs:__guard_dispatch_icall_fptr
0x1c00361d4  mov     rcx, [rsi+38h]; P
0x1c00361d8  test    rcx, rcx
0x1c00361db  jnz     loc_1C007FDEC
0x1c00361e1  mov     r14, [rsi+30h]
0x1c00361e5  test    r14, r14
0x1c00361e8  jz      loc_1C003638B
0x1c00361ee  mov     ecx, [r14+2Ch]
0x1c00361f2  mov     rbx, [r14+38h]
0x1c00361f6  mov     rdi, [r14+40h]
0x1c00361fa  test    ecx, ecx
0x1c00361fc  jz      short loc_1C0036211
0x1c00361fe  mov     rax, [rbp+arg_10]
0x1c0036202  neg     ecx
0x1c0036204  lock xadd [rax+120h], ecx
0x1c003620c  and     dword ptr [r14+2Ch], 0
0x1c0036211  mov     rcx, [r14]; void *
0x1c0036214  test    rcx, rcx
0x1c0036217  jz      short loc_1C003621E
0x1c0036219  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x1c003621e  xor     edx, edx; Tag
0x1c0036220  mov     rcx, r14; P
0x1c0036223  call    cs:__imp_ExFreePoolWithTag
0x1c003622a  nop     dword ptr [rax+rax+00h]
0x1c003622f  xor     r14d, r14d
0x1c0036232  mov     [rsi+30h], r14
0x1c0036236  mov     rax, cs:qword_1C0136CF0
0x1c003623d  inc     r13d
0x1c0036240  mov     edx, r13d
0x1c0036243  mov     rcx, r12
0x1c0036246  call    cs:__guard_dispatch_icall_fptr
0x1c003624c  jmp     loc_1C00361A8
0x1c0036251  mov     rcx, [rbp+arg_18]
0x1c0036255  test    rcx, rcx
0x1c0036258  jnz     loc_1C0036390
0x1c003625e  mov     rcx, [rbp+arg_10]
0x1c0036262  lea     rdx, [rbp+var_20]
0x1c0036266  call    ?GetRecoveryDurableLsn@CmsDurableLog@@QEAA?AT_ML_LSN@@XZ; CmsDurableLog::GetRecoveryDurableLsn(void)
0x1c003626b  cmp     [rax], rdi
0x1c003626e  jbe     short loc_1C00362AC
0x1c0036270  mov     rdi, [rbp+arg_10]
0x1c0036274  lea     rcx, [rdi+28h]; SpinLock
0x1c0036278  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c003627f  nop     dword ptr [rax+rax+00h]
0x1c0036284  mov     [rdi+30h], al
0x1c0036287  mov     rax, [rbp+arg_10]
0x1c003628b  cmp     rbx, [rax+78h]
0x1c003628f  jbe     short loc_1C0036299
0x1c0036291  mov     [rax+78h], rbx
0x1c0036295  mov     rax, [rbp+arg_10]
0x1c0036299  mov     dl, [rax+30h]; NewIrql
0x1c003629c  lea     rcx, [rax+28h]; SpinLock
0x1c00362a0  call    cs:__imp_KeReleaseSpinLock
0x1c00362a7  nop     dword ptr [rax+rax+00h]
0x1c00362ac  mov     rdi, [rbp+arg_10]
0x1c00362b0  lea     rcx, [rdi+28h]; SpinLock
0x1c00362b4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c00362bb  nop     dword ptr [rax+rax+00h]
0x1c00362c0  mov     rdx, [rdi+80h]
0x1c00362c7  lea     rcx, [rdi+28h]; SpinLock
0x1c00362cb  mov     [rbp+var_30], rdx
0x1c00362cf  mov     rdx, [rdi+70h]
0x1c00362d3  mov     [rbp+var_28], rdx
0x1c00362d7  mov     dl, al; NewIrql
0x1c00362d9  mov     [rdi+30h], al
0x1c00362dc  call    cs:__imp_KeReleaseSpinLock
0x1c00362e3  nop     dword ptr [rax+rax+00h]
0x1c00362e8  xor     r9d, r9d; unsigned __int8
0x1c00362eb  lea     r8, [rbp+var_30]; union _ML_LSN *
0x1c00362ef  lea     rdx, [rbp+var_28]; struct _SmsLsn *
0x1c00362f3  mov     rcx, rdi; this
0x1c00362f6  call    ?CheckForVirtualWaiterMigration@CmsDurableLog@@AEAAXPEAU_SmsLsn@@PEAT_ML_LSN@@E@Z; CmsDurableLog::CheckForVirtualWaiterMigration(_SmsLsn *,_ML_LSN *,uchar)
0x1c00362fb  mov     rcx, [rbp+arg_10]; this
0x1c00362ff  call    ?CheckForDurableWaiterMigration@CmsDurableLog@@AEAAXXZ; CmsDurableLog::CheckForDurableWaiterMigration(void)
0x1c0036304  mov     rax, cs:qword_1C0136CF8
0x1c003630b  mov     r15d, 1
0x1c0036311  mov     dl, r15b
0x1c0036314  mov     rcx, r12
0x1c0036317  call    cs:__guard_dispatch_icall_fptr
0x1c003631d  mov     rcx, [rbp+arg_10]
0x1c0036321  neg     eax
0x1c0036323  lock xadd [rcx+0C0h], eax
0x1c003632b  mov     rax, cs:qword_1C0136CC0
0x1c0036332  mov     rcx, r12
0x1c0036335  call    cs:__guard_dispatch_icall_fptr
0x1c003633b  mov     rcx, [rbp+arg_10]; this
0x1c003633f  call    ?AttemptQueueWriteWorker@CmsDurableLog@@QEAAXXZ; CmsDurableLog::AttemptQueueWriteWorker(void)
0x1c0036344  mov     rcx, [rbp+arg_10]; this
0x1c0036348  cmp     [rcx+0C4h], r14d
0x1c003634f  jnz     short loc_1C003636A
0x1c0036351  call    ?GetLogFullPercentage@CmsDurableLog@@QEAAEXZ; CmsDurableLog::GetLogFullPercentage(void)
0x1c0036356  movzx   r14d, al
0x1c003635a  movzx   eax, cs:byte_1C0136C5C
0x1c0036361  cmp     r14d, eax
0x1c0036364  jnb     loc_1C007FE03
0x1c003636a  mov     rbx, [rsp+80h+arg_0]
0x1c0036372  mov     eax, 0C0000016h
0x1c0036377  add     rsp, 80h
0x1c003637e  pop     r15
0x1c0036380  pop     r14
0x1c0036382  pop     r13
0x1c0036384  pop     r12
0x1c0036386  pop     rdi
0x1c0036387  pop     rsi
0x1c0036388  pop     rbp
0x1c0036389  retn
0x1c003638b  jmp     loc_1C0036236
0x1c0036390  mov     rax, [rcx]
0x1c0036393  test    rax, rax
0x1c0036396  jz      short loc_1C00363A4
0x1c0036398  mov     rcx, rax; void *
0x1c003639b  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x1c00363a0  mov     rcx, [rbp+arg_18]; void *
0x1c00363a4  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x1c00363a9  jmp     loc_1C003625E
0x1c007fd5a  mov     eax, dword ptr cs:qword_1C0136914
0x1c007fd60  cmp     cs:?DbgRedoCreatedCount@@3KA, eax; ulong DbgRedoCreatedCount
0x1c007fd66  cmova   r15d, ecx
0x1c007fd6a  jmp     loc_1C0036163
0x1c007fd6f  mov     rcx, [rbp+arg_10]
0x1c007fd73  mov     edx, 20000000h; unsigned int
0x1c007fd78  mov     r9, [rcx+50h]
0x1c007fd7c  test    [r9+0C2Ch], edx
0x1c007fd83  jnz     short loc_1C007FD97
0x1c007fd85  mov     rcx, r9; this
0x1c007fd88  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXKE@Z; CmsVolume::ChangeVolumeOptionDynamically(ulong,uchar)
0x1c007fd8d  mov     rcx, [rbp+arg_10]
0x1c007fd91  mov     r8d, 1
0x1c007fd97  mov     rax, cs:qword_1C0136B38
0x1c007fd9e  test    rax, rax
0x1c007fda1  jz      loc_1C0036192
0x1c007fda7  mov     rcx, [rcx+50h]
0x1c007fdab  xor     r9d, r9d
0x1c007fdae  mov     edx, [rcx+0C2Ch]
0x1c007fdb4  mov     rcx, [rcx+30h]
0x1c007fdb8  shr     edx, 1Eh
0x1c007fdbb  and     dl, r8b
0x1c007fdbe  mov     byte ptr [rsp+80h+var_48], dl
0x1c007fdc2  mov     rdx, 0D40170CB1h
0x1c007fdcc  mov     [rsp+80h+var_50], r14
0x1c007fdd1  mov     [rsp+80h+var_58], rdx
0x1c007fdd6  xor     edx, edx
0x1c007fdd8  mov     byte ptr [rsp+80h+var_60], r8b
0x1c007fddd  mov     r8d, r15d
0x1c007fde0  call    cs:__guard_dispatch_icall_fptr
0x1c007fde6  nop
0x1c007fde7  jmp     loc_1C0036192
0x1c007fdec  xor     edx, edx; Tag
0x1c007fdee  call    cs:__imp_ExFreePoolWithTag
0x1c007fdf5  nop     dword ptr [rax+rax+00h]
0x1c007fdfa  mov     [rsi+38h], r14
0x1c007fdfe  jmp     loc_1C00361E1
0x1c007fe03  cmp     cs:dword_1C012D0B4, r15d
0x1c007fe0a  jnz     short loc_1C007FE7C
0x1c007fe0c  test    cs:Microsoft_Windows_MinstoreEnableBits, r15b
0x1c007fe13  jz      short loc_1C007FE7C
0x1c007fe15  mov     rcx, [rbp+arg_10]
0x1c007fe19  lea     rdx, [rbp+var_18]
0x1c007fe1d  xor     r8d, r8d
0x1c007fe20  call    ?GetOldestRecordReference@CmsDurableLog@@QEAA?AT_ML_LSN@@E@Z; CmsDurableLog::GetOldestRecordReference(uchar)
0x1c007fe25  mov     rcx, [rbp+arg_10]
0x1c007fe29  lea     rdx, [rbp+var_10]
0x1c007fe2d  mov     rsi, [rax]
0x1c007fe30  call    ?BaseLsn@CmsDurableLog@@AEAA?AT_ML_LSN@@XZ; CmsDurableLog::BaseLsn(void)
0x1c007fe35  mov     rbx, [rax]
0x1c007fe38  mov     rax, [rbp+arg_10]
0x1c007fe3c  mov     edi, [rax+120h]
0x1c007fe42  call    cs:__imp_IoGetActivityIdThread
0x1c007fe49  nop     dword ptr [rax+rax+00h]
0x1c007fe4e  and     [rsp+80h+var_48], 0
0x1c007fe54  lea     rdx, LogPulseLazyWriter
0x1c007fe5b  mov     [rsp+80h+var_50], rsi
0x1c007fe60  lea     rcx, MinstoreEventProvider_Context
0x1c007fe67  mov     [rsp+80h+var_58], rbx
0x1c007fe6c  mov     r8, rax
0x1c007fe6f  mov     r9d, edi
0x1c007fe72  mov     dword ptr [rsp+80h+var_60], r14d
0x1c007fe77  call    McTemplateK0qqiii_EtwWriteTransfer
0x1c007fe7c  mov     rcx, [rbp+arg_10]
0x1c007fe80  xor     eax, eax
0x1c007fe82  lock cmpxchg [rcx+0C4h], r15d
0x1c007fe8b  xor     r8d, r8d; Wait
0x1c007fe8e  lea     rcx, ?LazyWriterScanEvent@@3U_KEVENT@@A; Event
0x1c007fe95  xor     edx, edx; Increment
0x1c007fe97  call    cs:__imp_KeSetEvent
0x1c007fe9e  nop     dword ptr [rax+rax+00h]
0x1c007fea3  nop
0x1c007fea4  jmp     loc_1C003636A
```

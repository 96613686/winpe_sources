# CmsDurableLog::WriteLog(void)

- ea: `0x1c0037844`
- end: `0x1c0037dee`
- name: `?WriteLog@CmsDurableLog@@QEAAJXZ`
- size: `1450`
- prototype: `__int64 __fastcall(CmsDurableLog *__hidden this)`
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c001e400`
- `0x1c0034a40`
- `0x1c0039850`
- `0x1c003a080`
- `0x1c0053620`

## callees

- `0x1c0036a10`
- `0x1c0037844`
- `0x1c0037df4`
- `0x1c0038000`
- `0x1c00388c8`
- `0x1c003891c`
- `0x1c0052a54`
- `0x1c006ac80`
- `0x1c006af80`
- `0x1c00e00c4`
- `0x1c00e0800`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x1c0037b7a`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0037b7a`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c003788d`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c003788d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003797a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0037aa9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0037bd3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0037db4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c008050a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c003797a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0037aa9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0037bd3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0037db4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c008050a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00379db`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0037b51`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0037bfa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0037c49`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0080441`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0080576`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00379db`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0037b51`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0037bfa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0037c49`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0080441`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0080576`
- `ntoskrnl!IoTransferActivityId` at `0x1c00378ae`
- `ntoskrnl!IoTransferActivityId` at `0x1c0037bbb`
- `ntoskrnl!IoTransferActivityId` at `0x1c00378ae`
- `ntoskrnl!IoTransferActivityId` at `0x1c0037bbb`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x1c0037d22`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x1c0037d22`

## pseudocode

```c
__int64 __fastcall CmsDurableLog::WriteLog(CmsDurableLog *this)
{
  __int64 v1; // rbp
  struct _SmsMergeState *v2; // rsi
  int v4; // edi
  char *v5; // r14
  __int64 v6; // r15
  __int64 v7; // rcx
  unsigned int v8; // r13d
  KSPIN_LOCK *v9; // r12
  KIRQL v10; // al
  __int64 v11; // rdx
  unsigned int *v12; // r14
  unsigned int v13; // eax
  char v14; // r12
  KIRQL v16; // al
  int v17; // edx
  _QWORD *v18; // rax
  __int64 v19; // rdx
  _QWORD *v20; // rdi
  unsigned int i; // r15d
  __int64 v22; // rax
  __int64 v23; // r14
  __int64 v24; // rax
  __int64 v25; // rcx
  unsigned int v26; // edx
  CmsVolume *v27; // rcx
  __int64 v28; // rcx
  unsigned int v29; // eax
  bool v30; // zf
  int v31; // [rsp+20h] [rbp-78h]
  size_t v32; // [rsp+28h] [rbp-70h]
  int v33; // [rsp+30h] [rbp-68h]
  int v34; // [rsp+38h] [rbp-60h]
  unsigned __int64 v35; // [rsp+38h] [rbp-60h]
  unsigned int v36; // [rsp+A0h] [rbp+8h]
  __int64 v37; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v38; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v39; // [rsp+B8h] [rbp+20h]

  v1 = 0;
  v2 = 0;
  v36 = 0;
  v37 = 0;
  v4 = 0;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 50, 1, 0) != 1 )
  {
    v5 = (char *)this + 300;
    v6 = IoSetActivityIdThread((char *)this + 300);
    v39 = v6;
    IoTransferActivityId(v5, &MsActivityIdLogWrite);
    if ( v6 )
      IoTransferActivityId(v5, v6);
    if ( !*((_QWORD *)this + 11) )
    {
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
      *((_BYTE *)this + 48) = v16;
      if ( !*((_QWORD *)this + 11) )
      {
        CmsDurableLog::ReleaseActiveLogWriter(this);
        KeReleaseSpinLock((PKSPIN_LOCK)this + 5, *((_BYTE *)this + 48));
        if ( (*(_DWORD *)(*((_QWORD *)this + 10) + 3116LL) & 0x20000000) != 0 || (*((_DWORD *)this + 74) & 4) == 0 )
        {
          v4 = -1073741202;
          goto LABEL_28;
        }
LABEL_27:
        v4 = 259;
LABEL_28:
        IoClearActivityIdThread(v39);
        return (unsigned int)v4;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)this + 5, v16);
    }
    v7 = *((_QWORD *)this + 10);
    if ( (*(_DWORD *)(v7 + 3116) & 0x20000000) != 0 || (*((_DWORD *)this + 74) & 4) == 0 )
    {
      CmsDurableLog::DeleteOutstandingWrites(this);
      v14 = 0;
      v4 = -1073741202;
LABEL_66:
      CmsDurableLog::ReleaseActiveLogWriter(this);
      if ( v14 )
        KeReleaseSpinLock((PKSPIN_LOCK)this + 5, *((_BYTE *)this + 48));
      if ( v1 )
        ((void (__fastcall *)(__int64))qword_1C0136CC0)(v1);
      goto LABEL_28;
    }
    v1 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))qword_1C0136CB8)(
           *(_QWORD *)(v7 + 48),
           (unsigned int)MsPerfParams,
           516);
    v8 = ((__int64 (__fastcall *)(__int64, _QWORD))qword_1C0136CF8)(v1, 0);
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 10) + 868LL), 1u);
    if ( v8 > 1 )
    {
      v2 = CmsDurableLog::ShouldDoubleBufferWrites(this);
      if ( v2 )
        --v8;
    }
    ((void (__fastcall *)(__int64, __int64 (__fastcall *)(struct _MSENV_IO_REQUEST *, int), CmsDurableLog *, struct _SmsMergeState *, _QWORD, _QWORD))qword_1C0136D08)(
      v1,
      CmsDurableLog::LogWriteBatchCompletion,
      this,
      v2,
      0,
      0);
    v9 = (KSPIN_LOCK *)((char *)this + 40);
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
    v12 = (unsigned int *)*((_QWORD *)this + 11);
    *((_BYTE *)this + 48) = v10;
    if ( v12 )
    {
      v13 = 0;
      while ( 1 )
      {
        v14 = 1;
        if ( v13 >= v8 )
          goto LABEL_19;
        if ( v4 < 0 )
          goto LABEL_63;
        v38 = *((_QWORD *)v12 + 7);
        *((_QWORD *)this + 11) = *((_QWORD *)v12 + 6);
        *((_QWORD *)v12 + 6) = 0;
        if ( *((unsigned int **)this + 12) == v12 )
          *((_QWORD *)this + 12) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)this + 5, *((_BYTE *)this + 48));
        *((_DWORD *)this + 74) |= 2u;
        v14 = 0;
        memset((void *)(*((_QWORD *)v12 + 1) + v12[8]), 0, v12[6] - v12[8]);
        LODWORD(v32) = v12[6];
        v4 = MlLogWriteLogRecord(
               *((_QWORD *)this + 9),
               v1,
               *(_QWORD *)v12,
               v12[9],
               *((void **)v12 + 1),
               v32,
               v33,
               v34,
               (__int64)&v37);
        if ( v4 == -1073741670 )
        {
          v9 = (KSPIN_LOCK *)((char *)this + 40);
          *((_BYTE *)this + 48) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
          *((_QWORD *)v12 + 6) = *((_QWORD *)this + 11);
          v30 = *((_QWORD *)this + 12) == 0;
          *((_QWORD *)this + 11) = v12;
          if ( v30 )
            *((_QWORD *)this + 12) = v12;
          goto LABEL_21;
        }
        _InterlockedExchangeAdd((volatile signed __int32 *)this + 73, -v12[11]);
        if ( (int)(v4 + 0x80000000) >= 0 && v4 != -1073741802 )
          break;
        *(_QWORD *)(((__int64 (__fastcall *)(__int64, _QWORD))qword_1C0136CF0)(v1, v36) + 48) = v12;
        *((_QWORD *)v12 + 8) = v37;
        CmsDurableLog::CheckForVirtualWaiterMigration(this, (struct _SmsLsn *)&v38, (union _ML_LSN *)&v37, 0);
        *((_BYTE *)this + 48) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
        v14 = 1;
        *((_QWORD *)this + 14) = *((_QWORD *)v12 + 7);
        *((_QWORD *)this + 16) = v37;
        v12 = (unsigned int *)*((_QWORD *)this + 11);
        v13 = ++v36;
        if ( !v12 )
          goto LABEL_19;
      }
      v27 = (CmsVolume *)*((_QWORD *)this + 10);
      if ( (*((_DWORD *)v27 + 779) & 0x20000000) == 0 )
        CmsVolume::ChangeVolumeOptionDynamically(v27, 0x20000000u, 1u);
      if ( qword_1C0136B38 )
      {
        v28 = *((_QWORD *)this + 10);
        LOBYTE(v34) = (*(_DWORD *)(v28 + 3116) & 0x40000000) != 0;
        LOBYTE(v31) = 1;
        qword_1C0136B38(*(_QWORD *)(v28 + 48), 0, (unsigned int)v4, 0, v31, 0xC40170A19LL, 0, v34);
      }
      v29 = v12[11];
      if ( v29 )
      {
        _InterlockedExchangeAdd((volatile signed __int32 *)this + 72, -v29);
        v12[11] = 0;
      }
      CmsTxMemLog::FreeRedoBlock(v12);
      CmsDurableLog::DeleteOutstandingWrites(this);
      if ( v2 )
      {
        if ( *(_QWORD *)v2 )
          CmsLookasides::Free(*(void **)v2);
        CmsLookasides::Free(v2);
        v2 = 0;
      }
LABEL_19:
      if ( v4 >= 0 )
      {
LABEL_20:
        v9 = (KSPIN_LOCK *)((char *)this + 40);
        goto LABEL_21;
      }
LABEL_63:
      if ( v4 == -1073741802 )
        goto LABEL_20;
      goto LABEL_66;
    }
LABEL_21:
    if ( v2 && v36 >= dword_1C013685C )
    {
      KeReleaseSpinLock(v9, *((_BYTE *)this + 48));
      v17 = *((_DWORD *)v2 + 2);
      v35 = ~(unsigned __int64)(unsigned int)(v17 + 256);
      *((_QWORD *)v2 + 2) = v35;
      LOWORD(v31) = 3;
      v18 = (_QWORD *)((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, int, _QWORD, int, unsigned __int64))qword_1C0136CC8)(
                        v1,
                        0,
                        0,
                        0,
                        v31,
                        *(_QWORD *)v2,
                        v17,
                        v35);
      v20 = v18;
      if ( v18 )
      {
        v18[5] = 0;
        v18[6] = 0;
        v18[7] = 0;
        v18[4] = LogWriteDoubleBufferWriteCompletion;
        for ( i = 0; ; ++i )
        {
          LOBYTE(v19) = 1;
          if ( i >= (unsigned int)((__int64 (__fastcall *)(__int64, __int64))qword_1C0136CF8)(v1, v19) - 1 )
            break;
          v22 = ((__int64 (__fastcall *)(__int64, _QWORD))qword_1C0136CF0)(v1, i);
          v23 = v22;
          if ( *((_DWORD *)v2 + 6) )
          {
            v24 = *((_QWORD *)v2 + 2);
          }
          else
          {
            v24 = *(_QWORD *)(v22 + 16);
            *((_QWORD *)v2 + 2) = v24;
          }
          v25 = *((unsigned int *)v2 + 3);
          if ( *(_QWORD *)(v23 + 16) != v25 + v24 )
            break;
          v26 = *(_DWORD *)(v23 + 8);
          if ( v26 > *((_DWORD *)v2 + 2) - (int)v25 )
            break;
          RtlCopyMemoryNonTemporal((void *)(*(_QWORD *)v2 + v25), *(const void **)v23, v26);
          *((_DWORD *)v2 + 3) += *(_DWORD *)(v23 + 8);
          ++*((_DWORD *)v2 + 6);
          ((void (__fastcall *)(__int64, __int64, _QWORD, __int64, _DWORD, _QWORD))qword_1C0136CD0)(
            v1,
            v23,
            0,
            2,
            *(_DWORD *)(v23 + 8),
            *(_QWORD *)(v23 + 16));
        }
      }
      if ( *((_DWORD *)v2 + 6) )
        ((void (__fastcall *)(__int64, _QWORD *, _QWORD, __int64, _DWORD, _QWORD))qword_1C0136CD0)(
          v1,
          v20,
          0,
          1,
          *((_DWORD *)v2 + 3),
          *((_QWORD *)v2 + 2));
      *((_BYTE *)this + 48) = KeAcquireSpinLockRaiseToDpc(v9);
    }
    LOBYTE(v11) = 1;
    _InterlockedExchangeAdd(
      (volatile signed __int32 *)this + 48,
      ((__int64 (__fastcall *)(__int64, __int64))qword_1C0136CF8)(v1, v11));
    if ( MsPerfStats < v36 )
      MsPerfStats = v36;
    if ( (unsigned int)dword_1C01368B4 < *((_DWORD *)this + 48) )
      dword_1C01368B4 = *((_DWORD *)this + 48);
    CmsDurableLog::ReleaseActiveLogWriter(this);
    KeReleaseSpinLock(v9, *((_BYTE *)this + 48));
    ((void (__fastcall *)(__int64))qword_1C0136CD8)(v1);
    goto LABEL_27;
  }
  return 259;
}

```

## disassembly

```asm
0x1c0037844  mov     r11, rsp
0x1c0037847  push    rbx
0x1c0037848  push    rbp
0x1c0037849  push    rsi
0x1c003784a  push    rdi
0x1c003784b  push    r12
0x1c003784d  push    r13
0x1c003784f  push    r14
0x1c0037851  push    r15
0x1c0037853  sub     rsp, 58h
0x1c0037857  xor     ebp, ebp
0x1c0037859  xor     esi, esi
0x1c003785b  and     [rsp+98h+arg_0], esi
0x1c0037862  xor     eax, eax
0x1c0037864  mov     rbx, rcx
0x1c0037867  mov     [r11+10h], rax
0x1c003786b  xor     edi, edi
0x1c003786d  lea     r12d, [rbp+1]
0x1c0037871  lock cmpxchg [rcx+0C8h], r12d
0x1c003787a  cmp     eax, r12d
0x1c003787d  jz      loc_1C0037DC8
0x1c0037883  lea     r14, [rcx+12Ch]
0x1c003788a  mov     rcx, r14
0x1c003788d  call    cs:__imp_IoSetActivityIdThread
0x1c0037894  nop     dword ptr [rax+rax+00h]
0x1c0037899  lea     rdx, ?MsActivityIdLogWrite@@3U_GUID@@B; _GUID const MsActivityIdLogWrite
0x1c00378a0  mov     rcx, r14
0x1c00378a3  mov     r15, rax
0x1c00378a6  mov     [rsp+98h+arg_18], rax
0x1c00378ae  call    cs:__imp_IoTransferActivityId
0x1c00378b5  nop     dword ptr [rax+rax+00h]
0x1c00378ba  test    r15, r15
0x1c00378bd  jnz     loc_1C0037BB5
0x1c00378c3  cmp     [rbx+58h], rsi
0x1c00378c7  jz      loc_1C0037BCC
0x1c00378cd  mov     rcx, [rbx+50h]
0x1c00378d1  mov     r15d, 20000000h
0x1c00378d7  test    [rcx+0C2Ch], r15d
0x1c00378de  jnz     loc_1C0080552
0x1c00378e4  mov     eax, [rbx+128h]
0x1c00378ea  test    al, 4
0x1c00378ec  jz      loc_1C0080552
0x1c00378f2  mov     rax, cs:qword_1C0136CB8
0x1c00378f9  mov     r8d, 204h
0x1c00378ff  mov     edx, cs:MsPerfParams
0x1c0037905  mov     rcx, [rcx+30h]
0x1c0037909  call    cs:__guard_dispatch_icall_fptr
0x1c003790f  mov     rbp, rax
0x1c0037912  xor     edx, edx
0x1c0037914  mov     rax, cs:qword_1C0136CF8
0x1c003791b  mov     rcx, rbp
0x1c003791e  call    cs:__guard_dispatch_icall_fptr
0x1c0037924  mov     rcx, [rbx+50h]
0x1c0037928  mov     r13d, eax
0x1c003792b  lock add [rcx+364h], r12d
0x1c0037933  cmp     eax, r12d
0x1c0037936  jbe     short loc_1C003794C
0x1c0037938  mov     rcx, rbx; this
0x1c003793b  call    ?ShouldDoubleBufferWrites@CmsDurableLog@@AEAAPEAU_SmsMergeState@@XZ; CmsDurableLog::ShouldDoubleBufferWrites(void)
0x1c0037940  mov     rsi, rax
0x1c0037943  test    rax, rax
0x1c0037946  jnz     loc_1C0037D6D
0x1c003794c  mov     rax, cs:qword_1C0136D08
0x1c0037953  lea     rdx, ?LogWriteBatchCompletion@CmsDurableLog@@CAJPEAU_MSENV_IO_REQUEST@@J@Z; CmsDurableLog::LogWriteBatchCompletion(_MSENV_IO_REQUEST *,long)
0x1c003795a  and     [rsp+98h+var_70], rdi
0x1c003795f  mov     r9, rsi
0x1c0037962  and     [rsp+98h+var_78], rdi
0x1c0037967  mov     r8, rbx
0x1c003796a  mov     rcx, rbp
0x1c003796d  call    cs:__guard_dispatch_icall_fptr
0x1c0037973  lea     r12, [rbx+28h]
0x1c0037977  mov     rcx, r12; SpinLock
0x1c003797a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c0037981  nop     dword ptr [rax+rax+00h]
0x1c0037986  mov     r14, [rbx+58h]
0x1c003798a  mov     [rbx+30h], al
0x1c003798d  test    r14, r14
0x1c0037990  jz      loc_1C0037AFB
0x1c0037996  mov     eax, [rsp+98h+arg_0]
0x1c003799d  mov     r12b, 1
0x1c00379a0  cmp     eax, r13d
0x1c00379a3  jnb     loc_1C0037AEF
0x1c00379a9  test    edi, edi
0x1c00379ab  js      loc_1C0080539
0x1c00379b1  mov     rax, [r14+38h]
0x1c00379b5  mov     [rsp+98h+arg_10], rax
0x1c00379bd  mov     rax, [r14+30h]
0x1c00379c1  mov     [rbx+58h], rax
0x1c00379c5  and     qword ptr [r14+30h], 0
0x1c00379ca  cmp     [rbx+60h], r14
0x1c00379ce  jz      loc_1C0037BAB
0x1c00379d4  mov     dl, [rbx+30h]; NewIrql
0x1c00379d7  lea     rcx, [rbx+28h]; SpinLock
0x1c00379db  call    cs:__imp_KeReleaseSpinLock
0x1c00379e2  nop     dword ptr [rax+rax+00h]
0x1c00379e7  or      dword ptr [rbx+128h], 2
0x1c00379ee  xor     edx, edx; Val
0x1c00379f0  mov     ecx, [r14+20h]
0x1c00379f4  xor     r12b, r12b
0x1c00379f7  mov     r8d, [r14+18h]
0x1c00379fb  sub     r8d, ecx; Size
0x1c00379fe  add     rcx, [r14+8]; void *
0x1c0037a02  call    memset
0x1c0037a07  mov     r9d, [r14+24h]; int
0x1c0037a0b  lea     rax, [rsp+98h+arg_8]
0x1c0037a13  mov     r8, [r14]; int
0x1c0037a16  mov     rdx, rbp; int
0x1c0037a19  mov     rcx, [rbx+48h]; int
0x1c0037a1d  mov     [rsp+98h+var_58], rax; __int64
0x1c0037a22  mov     eax, [r14+18h]
0x1c0037a26  mov     dword ptr [rsp+98h+var_70], eax; size_t
0x1c0037a2a  mov     rax, [r14+8]
0x1c0037a2e  mov     [rsp+98h+var_78], rax; void *
0x1c0037a33  call    MlLogWriteLogRecord
0x1c0037a38  mov     edi, eax
0x1c0037a3a  cmp     eax, 0C000009Ah
0x1c0037a3f  jz      loc_1C0080503
0x1c0037a45  mov     ecx, [r14+2Ch]
0x1c0037a49  neg     ecx
0x1c0037a4b  lock xadd [rbx+124h], ecx
0x1c0037a53  mov     eax, 80000000h
0x1c0037a58  lea     ecx, [rdi+rax]
0x1c0037a5b  test    eax, ecx
0x1c0037a5d  jz      loc_1C0037B9A
0x1c0037a63  mov     rax, cs:qword_1C0136CF0
0x1c0037a6a  mov     rcx, rbp
0x1c0037a6d  mov     edx, [rsp+98h+arg_0]
0x1c0037a74  call    cs:__guard_dispatch_icall_fptr
0x1c0037a7a  xor     r9d, r9d; unsigned __int8
0x1c0037a7d  lea     r8, [rsp+98h+arg_8]; union _ML_LSN *
0x1c0037a85  lea     rdx, [rsp+98h+arg_10]; struct _SmsLsn *
0x1c0037a8d  mov     rcx, rbx; this
0x1c0037a90  mov     [rax+30h], r14
0x1c0037a94  mov     rax, [rsp+98h+arg_8]
0x1c0037a9c  mov     [r14+40h], rax
0x1c0037aa0  call    ?CheckForVirtualWaiterMigration@CmsDurableLog@@AEAAXPEAU_SmsLsn@@PEAT_ML_LSN@@E@Z; CmsDurableLog::CheckForVirtualWaiterMigration(_SmsLsn *,_ML_LSN *,uchar)
0x1c0037aa5  lea     rcx, [rbx+28h]; SpinLock
0x1c0037aa9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c0037ab0  nop     dword ptr [rax+rax+00h]
0x1c0037ab5  mov     [rbx+30h], al
0x1c0037ab8  mov     r12b, 1
0x1c0037abb  mov     rax, [r14+38h]
0x1c0037abf  mov     [rbx+70h], rax
0x1c0037ac3  mov     rax, [rsp+98h+arg_8]
0x1c0037acb  mov     [rbx+80h], rax
0x1c0037ad2  mov     eax, [rsp+98h+arg_0]
0x1c0037ad9  mov     r14, [rbx+58h]
0x1c0037add  inc     eax
0x1c0037adf  mov     [rsp+98h+arg_0], eax
0x1c0037ae6  test    r14, r14
0x1c0037ae9  jnz     loc_1C003799D
0x1c0037aef  test    edi, edi
0x1c0037af1  js      loc_1C0080539
0x1c0037af7  lea     r12, [rbx+28h]
0x1c0037afb  test    rsi, rsi
0x1c0037afe  jnz     loc_1C0037C30
0x1c0037b04  mov     rax, cs:qword_1C0136CF8
0x1c0037b0b  mov     dl, 1
0x1c0037b0d  mov     rcx, rbp
0x1c0037b10  call    cs:__guard_dispatch_icall_fptr
0x1c0037b16  lock xadd [rbx+0C0h], eax
0x1c0037b1e  mov     eax, [rsp+98h+arg_0]
0x1c0037b25  cmp     cs:MsPerfStats, eax
0x1c0037b2b  jb      loc_1C0037DE3
0x1c0037b31  mov     eax, [rbx+0C0h]
0x1c0037b37  cmp     cs:dword_1C01368B4, eax
0x1c0037b3d  jb      loc_1C0037DD2
0x1c0037b43  mov     rcx, rbx; this
0x1c0037b46  call    ?ReleaseActiveLogWriter@CmsDurableLog@@AEAAXXZ; CmsDurableLog::ReleaseActiveLogWriter(void)
0x1c0037b4b  mov     dl, [rbx+30h]; NewIrql
0x1c0037b4e  mov     rcx, r12; SpinLock
0x1c0037b51  call    cs:__imp_KeReleaseSpinLock
0x1c0037b58  nop     dword ptr [rax+rax+00h]
0x1c0037b5d  mov     rax, cs:qword_1C0136CD8
0x1c0037b64  mov     rcx, rbp
0x1c0037b67  call    cs:__guard_dispatch_icall_fptr
0x1c0037b6d  mov     edi, 103h
0x1c0037b72  mov     rcx, [rsp+98h+arg_18]
0x1c0037b7a  call    cs:__imp_IoClearActivityIdThread
0x1c0037b81  nop     dword ptr [rax+rax+00h]
0x1c0037b86  mov     eax, edi
0x1c0037b88  add     rsp, 58h
0x1c0037b8c  pop     r15
0x1c0037b8e  pop     r14
0x1c0037b90  pop     r13
0x1c0037b92  pop     r12
0x1c0037b94  pop     rdi
0x1c0037b95  pop     rsi
0x1c0037b96  pop     rbp
0x1c0037b97  pop     rbx
0x1c0037b98  retn
0x1c0037b9a  cmp     edi, 0C0000016h
0x1c0037ba0  jz      loc_1C0037A63
0x1c0037ba6  jmp     loc_1C0080453
0x1c0037bab  and     qword ptr [rbx+60h], 0
0x1c0037bb0  jmp     loc_1C00379D4
0x1c0037bb5  mov     rdx, r15
0x1c0037bb8  mov     rcx, r14
0x1c0037bbb  call    cs:__imp_IoTransferActivityId
0x1c0037bc2  nop     dword ptr [rax+rax+00h]
0x1c0037bc7  jmp     loc_1C00378C3
0x1c0037bcc  lea     r14, [rbx+28h]
0x1c0037bd0  mov     rcx, r14; SpinLock
0x1c0037bd3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c0037bda  nop     dword ptr [rax+rax+00h]
0x1c0037bdf  mov     [rbx+30h], al
0x1c0037be2  cmp     [rbx+58h], rsi
0x1c0037be6  jnz     loc_1C008043C
0x1c0037bec  mov     rcx, rbx; this
0x1c0037bef  call    ?ReleaseActiveLogWriter@CmsDurableLog@@AEAAXXZ; CmsDurableLog::ReleaseActiveLogWriter(void)
0x1c0037bf4  mov     dl, [rbx+30h]; NewIrql
0x1c0037bf7  mov     rcx, r14; SpinLock
0x1c0037bfa  call    cs:__imp_KeReleaseSpinLock
0x1c0037c01  nop     dword ptr [rax+rax+00h]
0x1c0037c06  mov     rax, [rbx+50h]
0x1c0037c0a  mov     r15d, 20000000h
0x1c0037c10  test    [rax+0C2Ch], r15d
0x1c0037c17  jnz     loc_1C0080432
0x1c0037c1d  mov     eax, [rbx+128h]
0x1c0037c23  test    al, 4
0x1c0037c25  jnz     loc_1C0037B6D
0x1c0037c2b  jmp     loc_1C0080432
0x1c0037c30  mov     ecx, [rsp+98h+arg_0]
0x1c0037c37  cmp     ecx, cs:dword_1C013685C
0x1c0037c3d  jb      loc_1C0037B04
0x1c0037c43  mov     dl, [rbx+30h]; NewIrql
0x1c0037c46  mov     rcx, r12; SpinLock
0x1c0037c49  call    cs:__imp_KeReleaseSpinLock
0x1c0037c50  nop     dword ptr [rax+rax+00h]
0x1c0037c55  mov     edx, [rsi+8]
0x1c0037c58  mov     r8d, 3
0x1c0037c5e  xor     r9d, r9d
0x1c0037c61  lea     ecx, [rdx+100h]
0x1c0037c67  not     rcx
0x1c0037c6a  mov     [rsp+98h+var_60], rcx
0x1c0037c6f  mov     [rsi+10h], rcx
0x1c0037c73  mov     rcx, [rsi]
0x1c0037c76  mov     rax, cs:qword_1C0136CC8
0x1c0037c7d  mov     dword ptr [rsp+98h+var_68], edx
0x1c0037c81  xor     edx, edx
0x1c0037c83  mov     [rsp+98h+var_70], rcx
0x1c0037c88  mov     rcx, rbp
0x1c0037c8b  mov     word ptr [rsp+98h+var_78], r8w
0x1c0037c91  xor     r8d, r8d
0x1c0037c94  call    cs:__guard_dispatch_icall_fptr
0x1c0037c9a  mov     rdi, rax
0x1c0037c9d  test    rax, rax
0x1c0037ca0  jz      loc_1C0037D7F
0x1c0037ca6  and     qword ptr [rdi+28h], 0
0x1c0037cab  lea     rax, ?LogWriteDoubleBufferWriteCompletion@@YAJPEAX0KJ0@Z; LogWriteDoubleBufferWriteCompletion(void *,void *,ulong,long,void *)
0x1c0037cb2  and     qword ptr [rdi+30h], 0
0x1c0037cb7  and     qword ptr [rdi+38h], 0
0x1c0037cbc  mov     [rdi+20h], rax
0x1c0037cc0  xor     r15d, r15d
0x1c0037cc3  mov     rax, cs:qword_1C0136CF8
0x1c0037cca  mov     dl, 1
0x1c0037ccc  mov     rcx, rbp
0x1c0037ccf  call    cs:__guard_dispatch_icall_fptr
0x1c0037cd5  dec     eax
0x1c0037cd7  cmp     r15d, eax
0x1c0037cda  jnb     loc_1C0037D7F
0x1c0037ce0  mov     rax, cs:qword_1C0136CF0
0x1c0037ce7  mov     edx, r15d
0x1c0037cea  mov     rcx, rbp
0x1c0037ced  call    cs:__guard_dispatch_icall_fptr
0x1c0037cf3  cmp     dword ptr [rsi+18h], 0
0x1c0037cf7  mov     r14, rax
0x1c0037cfa  jz      short loc_1C0037D75
0x1c0037cfc  mov     rax, [rsi+10h]
0x1c0037d00  mov     ecx, [rsi+0Ch]
0x1c0037d03  add     rax, rcx
0x1c0037d06  cmp     [r14+10h], rax
0x1c0037d0a  jnz     short loc_1C0037D7F
0x1c0037d0c  mov     eax, [rsi+8]
0x1c0037d0f  mov     edx, [r14+8]
0x1c0037d13  sub     eax, ecx
0x1c0037d15  cmp     edx, eax
0x1c0037d17  ja      short loc_1C0037D7F
0x1c0037d19  add     rcx, [rsi]; Destination
0x1c0037d1c  mov     r8d, edx; Length
0x1c0037d1f  mov     rdx, [r14]; Source
0x1c0037d22  call    cs:__imp_RtlCopyMemoryNonTemporal
0x1c0037d29  nop     dword ptr [rax+rax+00h]
0x1c0037d2e  mov     eax, [r14+8]
0x1c0037d32  mov     r9d, 2
0x1c0037d38  add     [rsi+0Ch], eax
0x1c0037d3b  xor     r8d, r8d
0x1c0037d3e  inc     dword ptr [rsi+18h]
0x1c0037d41  mov     rdx, r14
0x1c0037d44  mov     rcx, [r14+10h]
0x1c0037d48  mov     rax, cs:qword_1C0136CD0
0x1c0037d4f  mov     [rsp+98h+var_70], rcx
0x1c0037d54  mov     ecx, [r14+8]
0x1c0037d58  mov     dword ptr [rsp+98h+var_78], ecx
0x1c0037d5c  mov     rcx, rbp
0x1c0037d5f  call    cs:__guard_dispatch_icall_fptr
0x1c0037d65  inc     r15d
0x1c0037d68  jmp     loc_1C0037CC3
0x1c0037d6d  dec     r13d
0x1c0037d70  jmp     loc_1C003794C
  ... truncated ...
```

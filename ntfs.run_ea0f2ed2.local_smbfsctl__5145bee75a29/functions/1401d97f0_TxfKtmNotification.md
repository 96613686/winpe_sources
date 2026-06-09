# TxfKtmNotification

- ea: `0x1401d97f0`
- end: `0x1401da216`
- name: `TxfKtmNotification`
- size: `2598`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT EnlistmentObject, PVOID RMContext, PVOID TransactionContext, ULONG TransactionNotification, PLARGE_INTEGER TmVirtualClock, ULONG ArgumentLength, PVOID Argument)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140007ea0`
- `0x140010c54`
- `0x14004088c`
- `0x140052074`
- `0x140053c98`
- `0x140053f38`
- `0x1400bbf04`
- `0x140188028`
- `0x140188ce4`
- `0x1401d60b8`
- `0x1401d97f0`
- `0x1401da21c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401d9cee`
- `ntoskrnl!KeSetEvent` at `0x1401d9cee`
- `ntoskrnl!ZwClose` at `0x1401d9945`
- `ntoskrnl!ZwClose` at `0x1401da161`
- `ntoskrnl!ZwClose` at `0x1402b082a`
- `ntoskrnl!ZwClose` at `0x1401d9945`
- `ntoskrnl!ZwClose` at `0x1401da161`
- `ntoskrnl!ZwClose` at `0x1402b082a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d9c69`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d9c69`
- `ntoskrnl!KeReleaseMutex` at `0x1401d9e40`
- `ntoskrnl!KeReleaseMutex` at `0x1401d9e40`
- `ntoskrnl!TmRollbackEnlistment` at `0x1401da0ac`
- `ntoskrnl!TmRollbackEnlistment` at `0x1401da0ac`
- `ntoskrnl!SeAuditTransactionStateChange` at `0x1401d9f92`
- `ntoskrnl!SeAuditTransactionStateChange` at `0x1401d9f92`
- `ntoskrnl!TmEnlistmentObjectType` at `0x1401d9c56`
- `ntoskrnl!TmDereferenceEnlistmentKey` at `0x1401d9910`
- `ntoskrnl!TmDereferenceEnlistmentKey` at `0x1401d9a1b`
- `ntoskrnl!TmDereferenceEnlistmentKey` at `0x1401d9910`
- `ntoskrnl!TmDereferenceEnlistmentKey` at `0x1401d9a1b`
- `ntoskrnl!ZwOpenEnlistment` at `0x1401d9c17`
- `ntoskrnl!ZwOpenEnlistment` at `0x1401d9c17`
- `ntoskrnl!ZwRecoverEnlistment` at `0x1401d9ca1`
- `ntoskrnl!ZwRecoverEnlistment` at `0x1401d9ca1`
- `ntoskrnl!TmReferenceEnlistmentKey` at `0x1401d9875`
- `ntoskrnl!TmReferenceEnlistmentKey` at `0x1401d9875`
- `ntoskrnl!TmCommitComplete` at `0x1401d9d46`
- `ntoskrnl!TmCommitComplete` at `0x1401d9fe8`
- `ntoskrnl!TmCommitComplete` at `0x1401d9d46`
- `ntoskrnl!TmCommitComplete` at `0x1401d9fe8`
- `ntoskrnl!TmRollbackComplete` at `0x1401d9d33`
- `ntoskrnl!TmRollbackComplete` at `0x1401d9f48`
- `ntoskrnl!TmRollbackComplete` at `0x1401d9fbb`
- `ntoskrnl!TmRollbackComplete` at `0x1401d9d33`
- `ntoskrnl!TmRollbackComplete` at `0x1401d9f48`
- `ntoskrnl!TmRollbackComplete` at `0x1401d9fbb`
- `ntoskrnl!TmPrepareComplete` at `0x1401d9d59`
- `ntoskrnl!TmPrepareComplete` at `0x1401da12c`
- `ntoskrnl!TmPrepareComplete` at `0x1401d9d59`
- `ntoskrnl!TmPrepareComplete` at `0x1401da12c`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x1401d9980`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x1401d9980`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d9e10`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d9e10`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9a36`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9a7d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9b8a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9d88`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9efa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9a36`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9a7d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9b8a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9d88`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9efa`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9ab2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9bb0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9de6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9ecd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9f37`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9faa`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9fcc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401da106`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9ab2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9bb0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9de6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9ecd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9f37`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9faa`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9fcc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401da106`

## pseudocode

```c
__int64 __fastcall TxfKtmNotification(
        PKENLISTMENT EnlistmentObject,
        PVOID RMContext,
        signed __int32 *TransactionContext,
        ULONG TransactionNotification,
        PLARGE_INTEGER TmVirtualClock,
        ULONG ArgumentLength,
        GUID *Argument)
{
  char v10; // r12
  unsigned int OnlyEnlistment; // ebx
  signed __int32 *v12; // rcx
  PLARGE_INTEGER v13; // rbx
  void *v14; // rcx
  int v15; // eax
  bool v16; // zf
  __int64 v17; // r8
  char v18; // r15
  int v19; // r8d
  PVOID v20; // rdx
  int v21; // edi
  _QWORD *v22; // rcx
  GUID *v23; // rsi
  NTSTATUS v24; // eax
  char *v25; // rax
  __int64 v26; // r9
  __int64 v27; // r8
  void **p_EnlistmentHandle; // rcx
  PVOID v29; // rcx
  void *v30; // rax
  NTSTATUS v31; // eax
  char v32; // bl
  LONGLONG v33; // rax
  int v34; // eax
  struct _ERESOURCE *v35; // rcx
  GUID *v36; // rcx
  ULONG v37; // r8d
  NTSTATUS v38; // eax
  __int64 v39; // rcx
  volatile signed __int64 *v40; // rcx
  _QWORD *v41; // rdx
  const char *v42; // rax
  unsigned __int8 LastReference[4]; // [rsp+54h] [rbp-74h] BYREF
  PVOID EnlistmentKey; // [rsp+58h] [rbp-70h] BYREF
  char v46; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v47[7]; // [rsp+61h] [rbp-67h] BYREF
  void *EnlistmentHandle; // [rsp+68h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-58h] BYREF
  signed __int32 *v50; // [rsp+E0h] [rbp+18h] BYREF

  v50 = TransactionContext;
  EnlistmentKey = 0;
  v10 = 0;
  LastReference[0] = 0;
  memset(&ObjectAttributes, 0, 44);
  v46 = 0;
  EnlistmentHandle = 0;
  if ( (*((_DWORD *)RMContext + 34) & 0x8000) != 0 )
    return 259;
  if ( TransactionNotification == 256 )
  {
    v23 = Argument;
    v24 = TxfTransMgrSearchAddTrans(RMContext, &Argument[1], 0, 1, 0, &EnlistmentKey);
    OnlyEnlistment = v24;
    if ( v24 == -1072103327 )
    {
      v25 = 0;
      EnlistmentKey = 0;
    }
    else
    {
      if ( v24 < 0 )
      {
        v26 = 3217422;
        goto LABEL_40;
      }
      ExAcquireResourceExclusiveLite((PERESOURCE)(*((_QWORD *)EnlistmentKey + 3) + 80LL), 1u);
      ++*((_DWORD *)EnlistmentKey + 1);
      LastReference[0] = 1;
      ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)EnlistmentKey + 3) + 80LL));
      v25 = (char *)EnlistmentKey;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    p_EnlistmentHandle = (void **)(v25 + 248);
    if ( !v25 )
      p_EnlistmentHandle = &EnlistmentHandle;
    v24 = ZwOpenEnlistment(p_EnlistmentHandle, 0xF001Fu, *((HANDLE *)RMContext + 82), v23, &ObjectAttributes);
    OnlyEnlistment = v24;
    if ( v24 < 0 )
    {
      v26 = 3217458;
      goto LABEL_40;
    }
    v29 = EnlistmentKey;
    if ( !EnlistmentKey )
      goto LABEL_52;
    v24 = ObReferenceObjectByHandle(
            *((HANDLE *)EnlistmentKey + 31),
            0,
            (POBJECT_TYPE)TmEnlistmentObjectType,
            0,
            (PVOID *)EnlistmentKey + 30,
            0);
    OnlyEnlistment = v24;
    if ( v24 >= 0 )
    {
      v29 = EnlistmentKey;
      if ( EnlistmentKey )
      {
        v30 = (void *)*((_QWORD *)EnlistmentKey + 31);
LABEL_53:
        OnlyEnlistment = ZwRecoverEnlistment(v30, v29);
        if ( (OnlyEnlistment & 0x80000000) == 0 )
        {
LABEL_58:
          OnlyEnlistment = 0;
          goto LABEL_113;
        }
        if ( EnlistmentKey && *((_QWORD *)EnlistmentKey + 30) )
          TxfDereferenceTransaction(&EnlistmentKey, 0);
        v26 = 3217512;
        v27 = OnlyEnlistment;
LABEL_42:
        TxfHardErrorFcn(0, RMContext, v27, v26);
        goto LABEL_113;
      }
LABEL_52:
      v30 = EnlistmentHandle;
      goto LABEL_53;
    }
    v26 = 3217479;
LABEL_40:
    v27 = (unsigned int)v24;
    goto LABEL_42;
  }
  if ( TransactionNotification == 0x2000 )
  {
    _InterlockedOr((volatile signed __int32 *)RMContext + 34, 0x100u);
    KeSetEvent((PRKEVENT)(*((_QWORD *)RMContext + 3) + 448LL), 0, 0);
    goto LABEL_58;
  }
  OnlyEnlistment = TmReferenceEnlistmentKey(EnlistmentObject, (PVOID *)&v50);
  v12 = v50;
  if ( v50 )
  {
    EnlistmentKey = v50;
    if ( _bittest(v50 + 4, 0x11u) )
    {
      v32 = 1;
      LOBYTE(Argument) = 1;
      v47[0] = 0;
      ExAcquireResourceExclusiveLite((PERESOURCE)(*((_QWORD *)v50 + 3) + 80LL), 1u);
      v12 = (signed __int32 *)EnlistmentKey;
      if ( _bittest((const signed __int32 *)EnlistmentKey + 4, 0x11u) )
      {
        TxfWaitForEnlistmentCompletion(
          0,
          (_DWORD)EnlistmentKey,
          (unsigned int)&Argument,
          *((_DWORD *)EnlistmentKey + 52) + 144,
          (__int64)v47);
        v12 = (signed __int32 *)EnlistmentKey;
        v32 = (char)Argument;
      }
      if ( v32 )
      {
        ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v12 + 3) + 80LL));
        v12 = (signed __int32 *)EnlistmentKey;
      }
    }
    v13 = TmVirtualClock;
    if ( TmVirtualClock )
    {
      KeWaitForSingleObject(*((PVOID *)RMContext + 68), Executive, 0, 0, 0);
      v33 = *((_QWORD *)RMContext + 67);
      if ( v13->QuadPart <= v33 )
        v13->QuadPart = v33;
      else
        *((union _LARGE_INTEGER *)RMContext + 67) = *v13;
      KeReleaseMutex(*((PRKMUTEX *)RMContext + 68), 0);
      v12 = (signed __int32 *)EnlistmentKey;
    }
    switch ( TransactionNotification )
    {
      case 2u:
        v15 = TxfTransMgrPrepareCommit(v12, 0, &v46);
        OnlyEnlistment = v15;
        v16 = v15 == 0;
        if ( v15 >= 0 )
        {
          if ( v46 )
          {
            OnlyEnlistment = TmReadOnlyEnlistment(EnlistmentObject, 0);
            v10 = 1;
            goto LABEL_13;
          }
          v16 = v15 == 0;
        }
        if ( !v16 )
        {
          if ( v15 < 0 )
          {
            OnlyEnlistment = -1072103421;
            if ( NtfsStatusDebugFlags )
            {
              v17 = 3217934;
              goto LABEL_20;
            }
          }
          goto LABEL_13;
        }
        v38 = TmPrepareComplete(EnlistmentObject, 0);
        break;
      case 4u:
        goto LABEL_21;
      case 8u:
        ExAcquireResourceExclusiveLite((PERESOURCE)(*((_QWORD *)v12 + 3) + 80LL), 1u);
        *((_DWORD *)EnlistmentKey + 109) |= 1u;
        v20 = EnlistmentKey;
        if ( *((PVOID *)EnlistmentKey + 52) == (char *)EnlistmentKey + 416 )
        {
          if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
          {
            McTemplateU0spjpj_EtwWriteTransfer(
              (_DWORD)RMContext + 672,
              (unsigned int)txftrans_c6564,
              (unsigned int)"TxfKtmNotification",
              (_DWORD)RMContext,
              (__int64)RMContext + 672,
              (char)EnlistmentKey,
              (__int64)EnlistmentKey + 256);
            v20 = EnlistmentKey;
          }
          ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v20 + 3) + 80LL));
          v21 = TxfTransMgrAbort(0, (_DWORD)EnlistmentKey);
          ExAcquireResourceExclusiveLite((PERESOURCE)(*((_QWORD *)EnlistmentKey + 3) + 80LL), 1u);
          OnlyEnlistment = 259;
          v20 = EnlistmentKey;
        }
        else
        {
          OnlyEnlistment = 259;
          v21 = 259;
        }
        if ( _bittest((const signed __int32 *)v20 + 4, 0x13u) && *((int *)v20 + 108) >= 0 )
        {
          *((_DWORD *)v20 + 108) = v21;
          v20 = EnlistmentKey;
        }
        v35 = (struct _ERESOURCE *)(*((_QWORD *)v20 + 3) + 80LL);
        if ( v21 >= 0 )
        {
          ExReleaseResourceLite(v35);
          OnlyEnlistment = TmRollbackComplete(EnlistmentObject, 0);
          v10 = 1;
          v36 = (GUID *)EnlistmentKey;
          if ( (*((_DWORD *)EnlistmentKey + 4) & 0x40000) == 0 )
            goto LABEL_13;
          v37 = 8;
LABEL_88:
          SeAuditTransactionStateChange(v36 + 16, (GUID *)(*(_QWORD *)&v36[13].Data1 + 672LL), v37);
          goto LABEL_13;
        }
        if ( !_bittest((const signed __int32 *)v20 + 4, 0x13u) )
        {
          ExReleaseResourceLite(v35);
          goto LABEL_13;
        }
        ExReleaseResourceLite(v35);
        v38 = TmRollbackComplete(EnlistmentObject, 0);
        break;
      case 0x200u:
LABEL_21:
        v18 = v12[4] & 1;
        v19 = TxfTransMgrPrepareCommit(v12, 1, &v46);
        if ( v19 < 0 )
        {
          if ( (*((_DWORD *)RMContext + 34) & 0x8000) == 0 )
          {
            v41 = EnlistmentKey;
            if ( !_bittest((const signed __int32 *)EnlistmentKey + 4, 0x13u) )
            {
              if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
              {
                v42 = " **PREPARED** ";
                if ( !v18 )
                  v42 = " ";
                McTemplateU0sdsjpjd_EtwWriteTransfer(
                  (_DWORD)EnlistmentKey + 256,
                  (unsigned int)" ",
                  v19,
                  TransactionNotification,
                  (__int64)v42,
                  (__int64)EnlistmentKey + 256,
                  (char)RMContext,
                  (__int64)RMContext + 672,
                  v19);
                v41 = EnlistmentKey;
              }
              if ( TransactionNotification == 512 )
              {
                TmRollbackEnlistment(EnlistmentObject, 0);
                OnlyEnlistment = 0;
                goto LABEL_13;
              }
              ExAcquireResourceExclusiveLite((PERESOURCE)(v41[3] + 80LL), 1u);
              *((_DWORD *)EnlistmentKey + 109) |= 1u;
              v22 = EnlistmentKey;
              if ( *((PVOID *)EnlistmentKey + 52) == (char *)EnlistmentKey + 416 )
              {
                if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
                {
                  McTemplateU0spjpj_EtwWriteTransfer(
                    (_DWORD)EnlistmentKey,
                    (unsigned int)txftrans_c6516,
                    (unsigned int)"TxfKtmNotification",
                    (_DWORD)RMContext,
                    (__int64)RMContext + 672,
                    (char)EnlistmentKey,
                    (__int64)EnlistmentKey + 256);
                  v22 = EnlistmentKey;
                }
                ExReleaseResourceLite((PERESOURCE)(v22[3] + 80LL));
                TxfTransMgrAbort(0, (_DWORD)EnlistmentKey);
              }
              else
              {
                ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)EnlistmentKey + 3) + 80LL));
              }
              OnlyEnlistment = -1072103421;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_13;
              v17 = 3217799;
              goto LABEL_20;
            }
          }
          goto LABEL_23;
        }
        OnlyEnlistment = TmCommitComplete(EnlistmentObject, 0);
        v10 = 1;
        v39 = *((_QWORD *)EnlistmentKey + 26);
        if ( v18 )
          v40 = (volatile signed __int64 *)(v39 + 272);
        else
          v40 = (volatile signed __int64 *)(v39 + 264);
        _InterlockedIncrement64(v40);
        v36 = (GUID *)EnlistmentKey;
        if ( (*((_DWORD *)EnlistmentKey + 4) & 0x40000) != 0 )
        {
          v37 = 4;
          goto LABEL_88;
        }
LABEL_13:
        TmDereferenceEnlistmentKey(EnlistmentObject, LastReference);
        v50 = 0;
        if ( v10 )
        {
          v14 = (void *)_InterlockedExchange64((volatile __int64 *)EnlistmentKey + 31, 0);
          if ( v14 )
            ZwClose(v14);
        }
        goto LABEL_113;
      case 0x4000u:
        v34 = TxfTransMgrRebuildIsolation(v12, v12);
        OnlyEnlistment = v34;
        if ( v34 >= 0 )
          goto LABEL_13;
        TxfHardErrorFcn(0, RMContext, (unsigned int)v34, 3217959);
LABEL_23:
        OnlyEnlistment = 259;
        goto LABEL_13;
      default:
        OnlyEnlistment = -1073741811;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_13;
        v17 = 3217968;
LABEL_20:
        NtfsStatusTraceAndDebugInternal(0, OnlyEnlistment, v17);
        goto LABEL_13;
    }
    OnlyEnlistment = v38;
    goto LABEL_13;
  }
  if ( TransactionNotification == 2 )
  {
    v31 = TmPrepareComplete(EnlistmentObject, 0);
    goto LABEL_68;
  }
  if ( TransactionNotification == 4 )
    goto LABEL_66;
  if ( TransactionNotification != 8 )
  {
    if ( TransactionNotification != 512 )
    {
      if ( TransactionNotification != 0x4000 )
      {
        OnlyEnlistment = -1073741811;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 3217572);
      }
      goto LABEL_26;
    }
LABEL_66:
    v31 = TmCommitComplete(EnlistmentObject, 0);
    goto LABEL_68;
  }
  v31 = TmRollbackComplete(EnlistmentObject, 0);
LABEL_68:
  OnlyEnlistment = v31;
LABEL_26:
  TmDereferenceEnlistmentKey(EnlistmentObject, 0);
LABEL_113:
  if ( LastReference[0] )
    TxfDereferenceTransaction(&EnlistmentKey, 0);
  if ( EnlistmentHandle )
    ZwClose(EnlistmentHandle);
  return OnlyEnlistment;
}

```

## disassembly

```asm
0x1401d97f0  mov     r11, rsp
0x1401d97f3  mov     [r11+8], rbx
0x1401d97f7  mov     [r11+20h], rsi
0x1401d97fb  mov     [r11+18h], r8
0x1401d97ff  mov     [r11+10h], rdx
0x1401d9803  push    rdi
0x1401d9804  push    r12
0x1401d9806  push    r13
0x1401d9808  push    r14
0x1401d980a  push    r15
0x1401d980c  sub     rsp, 0A0h
0x1401d9813  mov     esi, r9d
0x1401d9816  mov     rdi, rdx
0x1401d9819  mov     r14, rcx
0x1401d981c  xor     r13d, r13d
0x1401d981f  mov     [r11-70h], r13
0x1401d9823  mov     r12b, r13b
0x1401d9826  mov     [r11-74h], r13b
0x1401d982a  xor     eax, eax
0x1401d982c  xorps   xmm0, xmm0
0x1401d982f  movups  xmmword ptr [rsp+0C8h+var_58.Length], xmm0
0x1401d9834  movups  xmmword ptr [r11-48h], xmm0
0x1401d9839  movups  xmmword ptr [r11-3Ch], xmm0
0x1401d983e  mov     [r11-68h], r13b
0x1401d9842  mov     [r11-60h], r13
0x1401d9846  test    dword ptr [rdx+88h], 8000h
0x1401d9850  jnz     loc_1401DA16F
0x1401d9856  mov     eax, 100h
0x1401d985b  cmp     r9d, eax
0x1401d985e  jz      loc_1401D9AFA
0x1401d9864  cmp     r9d, 2000h
0x1401d986b  jz      loc_1401D9CD7
0x1401d9871  lea     rdx, [r11+18h]; Key
0x1401d9875  call    cs:__imp_TmReferenceEnlistmentKey
0x1401d987c  nop     dword ptr [rax+rax+00h]
0x1401d9881  mov     ebx, eax
0x1401d9883  mov     [rsp+0C8h+var_78], eax
0x1401d9887  mov     rcx, [rsp+0C8h+arg_10]
0x1401d988f  test    rcx, rcx
0x1401d9892  jz      loc_1401D9D06
0x1401d9898  mov     [rsp+0C8h+EnlistmentKey], rcx
0x1401d989d  bt      dword ptr [rcx+10h], 11h
0x1401d98a2  jb      loc_1401D9D70
0x1401d98a8  mov     [rsp+0C8h+var_78], r13d
0x1401d98ad  mov     rbx, [rsp+0C8h+TmVirtualClock]
0x1401d98b5  test    rbx, rbx
0x1401d98b8  jnz     loc_1401D9DFC
0x1401d98be  cmp     esi, 2
0x1401d98c1  jz      loc_1401D9956
0x1401d98c7  cmp     esi, 4
0x1401d98ca  jz      loc_1401D99AE
0x1401d98d0  cmp     esi, 8
0x1401d98d3  jz      loc_1401D9A2C
0x1401d98d9  cmp     esi, 200h
0x1401d98df  jz      loc_1401D99AE
0x1401d98e5  cmp     esi, 4000h
0x1401d98eb  jz      loc_1401D9E56
0x1401d98f1  mov     al, cs:NtfsStatusDebugFlags
0x1401d98f7  mov     ebx, 0C000000Dh
0x1401d98fc  test    al, al
0x1401d98fe  jnz     loc_1401D999A
0x1401d9904  mov     [rsp+0C8h+var_78], ebx
0x1401d9908  lea     rdx, [rsp+0C8h+LastReference]; LastReference
0x1401d990d  mov     rcx, r14; Enlistment
0x1401d9910  call    cs:__imp_TmDereferenceEnlistmentKey
0x1401d9917  nop     dword ptr [rax+rax+00h]
0x1401d991c  mov     [rsp+0C8h+arg_10], r13
0x1401d9924  test    r12b, r12b
0x1401d9927  jz      loc_1401DA150
0x1401d992d  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9932  mov     rcx, r13
0x1401d9935  xchg    rcx, [rax+0F8h]; Handle
0x1401d993c  test    rcx, rcx
0x1401d993f  jz      loc_1401DA150
0x1401d9945  call    cs:__imp_ZwClose
0x1401d994c  nop     dword ptr [rax+rax+00h]
0x1401d9951  jmp     loc_1401DA150
0x1401d9956  lea     r8, [rsp+0C8h+var_68]
0x1401d995b  xor     edx, edx
0x1401d995d  call    TxfTransMgrPrepareCommit
0x1401d9962  mov     ebx, eax
0x1401d9964  mov     [rsp+0C8h+var_78], eax
0x1401d9968  test    eax, eax
0x1401d996a  js      loc_1401DA125
0x1401d9970  cmp     [rsp+0C8h+var_68], r13b
0x1401d9975  jz      loc_1401DA123
0x1401d997b  xor     edx, edx; TmVirtualClock
0x1401d997d  mov     rcx, r14; Enlistment
0x1401d9980  call    cs:__imp_TmReadOnlyEnlistment
0x1401d9987  nop     dword ptr [rax+rax+00h]
0x1401d998c  mov     ebx, eax
0x1401d998e  mov     [rsp+0C8h+var_78], eax
0x1401d9992  mov     r12b, 1
0x1401d9995  jmp     loc_1401D9908
0x1401d999a  mov     r8d, 311A30h
0x1401d99a0  mov     edx, ebx
0x1401d99a2  xor     ecx, ecx
0x1401d99a4  call    NtfsStatusTraceAndDebugInternal
0x1401d99a9  jmp     loc_1401D9904
0x1401d99ae  mov     r15b, [rcx+10h]
0x1401d99b2  and     r15b, 1
0x1401d99b6  lea     r8, [rsp+0C8h+var_68]
0x1401d99bb  mov     edx, 1
0x1401d99c0  call    TxfTransMgrPrepareCommit
0x1401d99c5  mov     r8d, eax
0x1401d99c8  mov     [rsp+0C8h+var_78], eax
0x1401d99cc  test    eax, eax
0x1401d99ce  jns     loc_1401D9FE3
0x1401d99d4  test    dword ptr [rdi+88h], 8000h
0x1401d99de  jz      loc_1401DA039
0x1401d99e4  mov     al, cs:NtfsStatusDebugFlags
0x1401d99ea  mov     ebx, 103h
0x1401d99ef  jmp     loc_1401D9904
0x1401d99f4  mov     al, cs:NtfsStatusDebugFlags
0x1401d99fa  mov     ebx, 0C000000Dh
0x1401d99ff  test    al, al
0x1401d9a01  jz      short loc_1401D9A12
0x1401d9a03  mov     r8d, 3118A4h
0x1401d9a09  mov     edx, ebx
0x1401d9a0b  xor     ecx, ecx
0x1401d9a0d  call    NtfsStatusTraceAndDebugInternal
0x1401d9a12  mov     [rsp+0C8h+var_78], ebx
0x1401d9a16  xor     edx, edx; LastReference
0x1401d9a18  mov     rcx, r14; Enlistment
0x1401d9a1b  call    cs:__imp_TmDereferenceEnlistmentKey
0x1401d9a22  nop     dword ptr [rax+rax+00h]
0x1401d9a27  jmp     loc_1401DA150
0x1401d9a2c  mov     rcx, [rcx+18h]
0x1401d9a30  add     rcx, 50h ; 'P'; Resource
0x1401d9a34  mov     dl, 1; Wait
0x1401d9a36  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d9a3d  nop     dword ptr [rax+rax+00h]
0x1401d9a42  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9a47  or      dword ptr [rax+1B4h], 1
0x1401d9a4e  mov     rdx, [rsp+0C8h+EnlistmentKey]
0x1401d9a53  lea     rax, [rdx+1A0h]
0x1401d9a5a  cmp     [rax], rax
0x1401d9a5d  jz      loc_1401D9E84
0x1401d9a63  mov     ebx, 103h
0x1401d9a68  mov     edi, ebx
0x1401d9a6a  mov     [rsp+0C8h+var_78], ebx
0x1401d9a6e  jmp     loc_1401D9F10
0x1401d9a73  mov     rcx, [rdx+18h]
0x1401d9a77  add     rcx, 50h ; 'P'; Resource
0x1401d9a7b  mov     dl, 1; Wait
0x1401d9a7d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d9a84  nop     dword ptr [rax+rax+00h]
0x1401d9a89  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9a8e  or      dword ptr [rax+1B4h], 1
0x1401d9a95  mov     rcx, [rsp+0C8h+EnlistmentKey]
0x1401d9a9a  lea     rax, [rcx+1A0h]
0x1401d9aa1  cmp     [rax], rax
0x1401d9aa4  jz      loc_1401DA0C4
0x1401d9aaa  mov     rcx, [rcx+18h]
0x1401d9aae  add     rcx, 50h ; 'P'; Resource
0x1401d9ab2  call    cs:__imp_ExReleaseResourceLite
0x1401d9ab9  nop     dword ptr [rax+rax+00h]
0x1401d9abe  mov     al, cs:NtfsStatusDebugFlags
0x1401d9ac4  mov     ebx, 0C0190003h
0x1401d9ac9  test    al, al
0x1401d9acb  jz      loc_1401D9904
0x1401d9ad1  mov     r8d, 311987h
0x1401d9ad7  jmp     loc_1401D99A0
0x1401d9adc  mov     al, cs:NtfsStatusDebugFlags
0x1401d9ae2  mov     ebx, 0C0190003h
0x1401d9ae7  test    al, al
0x1401d9ae9  jz      loc_1401D9904
0x1401d9aef  mov     r8d, 311A0Eh
0x1401d9af5  jmp     loc_1401D99A0
0x1401d9afa  mov     rsi, [rsp+0C8h+Argument]
0x1401d9b02  lea     rdx, [rsi+10h]
0x1401d9b06  lea     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9b0b  mov     [rsp+0C8h+HandleInformation], rax
0x1401d9b10  mov     [rsp+0C8h+ObjectAttributes], r13
0x1401d9b15  mov     r9d, 1
0x1401d9b1b  xor     r8d, r8d
0x1401d9b1e  mov     rcx, rdi
0x1401d9b21  call    TxfTransMgrSearchAddTrans
0x1401d9b26  mov     ebx, eax
0x1401d9b28  mov     [rsp+0C8h+var_78], eax
0x1401d9b2c  cmp     eax, 0C0190061h
0x1401d9b31  jnz     short loc_1401D9B40
0x1401d9b33  mov     rax, r13
0x1401d9b36  mov     [rsp+0C8h+EnlistmentKey], rax
0x1401d9b3b  jmp     loc_1401D9BC1
0x1401d9b40  test    eax, eax
0x1401d9b42  jns     short loc_1401D9B7B
0x1401d9b44  mov     r9d, 31180Eh
0x1401d9b4a  jmp     short loc_1401D9B52
0x1401d9b4c  mov     r9d, 311847h
0x1401d9b52  mov     r8d, eax
0x1401d9b55  jmp     short loc_1401D9B6C
0x1401d9b57  xor     edx, edx
0x1401d9b59  lea     rcx, [rsp+0C8h+EnlistmentKey]
0x1401d9b5e  call    TxfDereferenceTransaction
0x1401d9b63  mov     r9d, 311868h
0x1401d9b69  mov     r8d, ebx
0x1401d9b6c  mov     rdx, rdi
0x1401d9b6f  xor     ecx, ecx
0x1401d9b71  call    TxfHardErrorFcn
0x1401d9b76  jmp     loc_1401DA150
0x1401d9b7b  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9b80  mov     rcx, [rax+18h]
0x1401d9b84  add     rcx, 50h ; 'P'; Resource
0x1401d9b88  mov     dl, 1; Wait
0x1401d9b8a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d9b91  nop     dword ptr [rax+rax+00h]
0x1401d9b96  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9b9b  inc     dword ptr [rax+4]
0x1401d9b9e  mov     [rsp+0C8h+LastReference], 1
0x1401d9ba3  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9ba8  mov     rcx, [rax+18h]
0x1401d9bac  add     rcx, 50h ; 'P'; Resource
0x1401d9bb0  call    cs:__imp_ExReleaseResourceLite
0x1401d9bb7  nop     dword ptr [rax+rax+00h]
0x1401d9bbc  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9bc1  mov     [rsp+0C8h+var_58.Length], 30h ; '0'
0x1401d9bc9  mov     [rsp+0C8h+var_58.RootDirectory], r13
0x1401d9bce  mov     [rsp+0C8h+var_58.Attributes], 240h
0x1401d9bd9  mov     [rsp+0C8h+var_58.ObjectName], r13
0x1401d9be1  xorps   xmm0, xmm0
0x1401d9be4  movdqu  xmmword ptr [rsp+0C8h+var_58.SecurityDescriptor], xmm0
0x1401d9bed  test    rax, rax
0x1401d9bf0  lea     rcx, [rax+0F8h]
0x1401d9bf7  jnz     short loc_1401D9BFE
0x1401d9bf9  lea     rcx, [rsp+0C8h+EnlistmentHandle]; EnlistmentHandle
0x1401d9bfe  lea     rax, [rsp+0C8h+var_58]
0x1401d9c03  mov     [rsp+0C8h+ObjectAttributes], rax; ObjectAttributes
0x1401d9c08  mov     r9, rsi; EnlistmentGuid
0x1401d9c0b  mov     r8, [rdi+290h]; RmHandle
0x1401d9c12  mov     edx, 0F001Fh; DesiredAccess
0x1401d9c17  call    cs:__imp_ZwOpenEnlistment
0x1401d9c1e  nop     dword ptr [rax+rax+00h]
0x1401d9c23  mov     ebx, eax
0x1401d9c25  mov     [rsp+0C8h+var_78], eax
0x1401d9c29  test    eax, eax
0x1401d9c2b  jns     short loc_1401D9C38
0x1401d9c2d  mov     r9d, 311832h
0x1401d9c33  jmp     loc_1401D9B52
0x1401d9c38  mov     rcx, [rsp+0C8h+EnlistmentKey]
0x1401d9c3d  test    rcx, rcx
0x1401d9c40  jz      short loc_1401D9C96
0x1401d9c42  lea     rax, [rcx+0F0h]
0x1401d9c49  mov     [rsp+0C8h+HandleInformation], r13; HandleInformation
0x1401d9c4e  mov     [rsp+0C8h+ObjectAttributes], rax; Object
0x1401d9c53  xor     r9d, r9d; AccessMode
0x1401d9c56  mov     r8, cs:TmEnlistmentObjectType
0x1401d9c5d  mov     r8, [r8]; ObjectType
0x1401d9c60  xor     edx, edx; DesiredAccess
0x1401d9c62  mov     rcx, [rcx+0F8h]; Handle
0x1401d9c69  call    cs:__imp_ObReferenceObjectByHandle
0x1401d9c70  nop     dword ptr [rax+rax+00h]
0x1401d9c75  mov     ebx, eax
0x1401d9c77  mov     [rsp+0C8h+var_78], eax
0x1401d9c7b  test    eax, eax
0x1401d9c7d  js      loc_1401D9B4C
0x1401d9c83  mov     rcx, [rsp+0C8h+EnlistmentKey]
0x1401d9c88  test    rcx, rcx
0x1401d9c8b  jz      short loc_1401D9C96
0x1401d9c8d  mov     rax, [rcx+0F8h]
0x1401d9c94  jmp     short loc_1401D9C9B
0x1401d9c96  mov     rax, [rsp+0C8h+EnlistmentHandle]
0x1401d9c9b  mov     rdx, rcx; EnlistmentKey
0x1401d9c9e  mov     rcx, rax; EnlistmentHandle
0x1401d9ca1  call    cs:__imp_ZwRecoverEnlistment
0x1401d9ca8  nop     dword ptr [rax+rax+00h]
0x1401d9cad  mov     ebx, eax
0x1401d9caf  mov     [rsp+0C8h+var_78], eax
0x1401d9cb3  test    eax, eax
0x1401d9cb5  jns     short loc_1401D9CFA
0x1401d9cb7  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9cbc  test    rax, rax
0x1401d9cbf  jz      loc_1401D9B63
0x1401d9cc5  cmp     [rax+0F0h], r13
0x1401d9ccc  jz      loc_1401D9B63
0x1401d9cd2  jmp     loc_1401D9B57
0x1401d9cd7  lock or [rdx+88h], eax
0x1401d9cde  mov     rcx, [rdx+18h]
0x1401d9ce2  add     rcx, 1C0h; Event
0x1401d9ce9  xor     r8d, r8d; Wait
0x1401d9cec  xor     edx, edx; Increment
0x1401d9cee  call    cs:__imp_KeSetEvent
0x1401d9cf5  nop     dword ptr [rax+rax+00h]
0x1401d9cfa  mov     ebx, r13d
0x1401d9cfd  mov     [rsp+0C8h+var_78], ebx
0x1401d9d01  jmp     loc_1401DA150
0x1401d9d06  cmp     esi, 2
0x1401d9d09  jz      short loc_1401D9D54
0x1401d9d0b  cmp     esi, 4
0x1401d9d0e  jz      short loc_1401D9D41
0x1401d9d10  cmp     esi, 8
0x1401d9d13  jz      short loc_1401D9D2E
0x1401d9d15  cmp     esi, 200h
0x1401d9d1b  jz      short loc_1401D9D41
0x1401d9d1d  cmp     esi, 4000h
0x1401d9d23  jz      loc_1401D9A16
0x1401d9d29  jmp     loc_1401D99F4
0x1401d9d2e  xor     edx, edx; TmVirtualClock
0x1401d9d30  mov     rcx, r14; Enlistment
0x1401d9d33  call    cs:__imp_TmRollbackComplete
  ... truncated ...
```

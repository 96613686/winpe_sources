# TxfKtmNotification

- ea: `0x1401d9840`
- end: `0x1401da266`
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
- `0x1400520e4`
- `0x140053d08`
- `0x140053fa8`
- `0x1400bbf04`
- `0x140188078`
- `0x140188d34`
- `0x1401d6108`
- `0x1401d9840`
- `0x1401da26c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401d9d3e`
- `ntoskrnl!KeSetEvent` at `0x1401d9d3e`
- `ntoskrnl!ZwClose` at `0x1401d9995`
- `ntoskrnl!ZwClose` at `0x1401da1b1`
- `ntoskrnl!ZwClose` at `0x1402b087a`
- `ntoskrnl!ZwClose` at `0x1401d9995`
- `ntoskrnl!ZwClose` at `0x1401da1b1`
- `ntoskrnl!ZwClose` at `0x1402b087a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d9cb9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d9cb9`
- `ntoskrnl!KeReleaseMutex` at `0x1401d9e90`
- `ntoskrnl!KeReleaseMutex` at `0x1401d9e90`
- `ntoskrnl!TmRollbackEnlistment` at `0x1401da0fc`
- `ntoskrnl!TmRollbackEnlistment` at `0x1401da0fc`
- `ntoskrnl!SeAuditTransactionStateChange` at `0x1401d9fe2`
- `ntoskrnl!SeAuditTransactionStateChange` at `0x1401d9fe2`
- `ntoskrnl!TmEnlistmentObjectType` at `0x1401d9ca6`
- `ntoskrnl!TmDereferenceEnlistmentKey` at `0x1401d9960`
- `ntoskrnl!TmDereferenceEnlistmentKey` at `0x1401d9a6b`
- `ntoskrnl!TmDereferenceEnlistmentKey` at `0x1401d9960`
- `ntoskrnl!TmDereferenceEnlistmentKey` at `0x1401d9a6b`
- `ntoskrnl!ZwOpenEnlistment` at `0x1401d9c67`
- `ntoskrnl!ZwOpenEnlistment` at `0x1401d9c67`
- `ntoskrnl!ZwRecoverEnlistment` at `0x1401d9cf1`
- `ntoskrnl!ZwRecoverEnlistment` at `0x1401d9cf1`
- `ntoskrnl!TmReferenceEnlistmentKey` at `0x1401d98c5`
- `ntoskrnl!TmReferenceEnlistmentKey` at `0x1401d98c5`
- `ntoskrnl!TmCommitComplete` at `0x1401d9d96`
- `ntoskrnl!TmCommitComplete` at `0x1401da038`
- `ntoskrnl!TmCommitComplete` at `0x1401d9d96`
- `ntoskrnl!TmCommitComplete` at `0x1401da038`
- `ntoskrnl!TmRollbackComplete` at `0x1401d9d83`
- `ntoskrnl!TmRollbackComplete` at `0x1401d9f98`
- `ntoskrnl!TmRollbackComplete` at `0x1401da00b`
- `ntoskrnl!TmRollbackComplete` at `0x1401d9d83`
- `ntoskrnl!TmRollbackComplete` at `0x1401d9f98`
- `ntoskrnl!TmRollbackComplete` at `0x1401da00b`
- `ntoskrnl!TmPrepareComplete` at `0x1401d9da9`
- `ntoskrnl!TmPrepareComplete` at `0x1401da17c`
- `ntoskrnl!TmPrepareComplete` at `0x1401d9da9`
- `ntoskrnl!TmPrepareComplete` at `0x1401da17c`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x1401d99d0`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x1401d99d0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d9e60`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d9e60`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9a86`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9acd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9bda`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9dd8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9f4a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9a86`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9acd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9bda`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9dd8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d9f4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9b02`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9c00`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9e36`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9f1d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9f87`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9ffa`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401da01c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401da156`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9b02`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9c00`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9e36`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9f1d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9f87`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d9ffa`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401da01c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401da156`

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
0x1401d9840  mov     r11, rsp
0x1401d9843  mov     [r11+8], rbx
0x1401d9847  mov     [r11+20h], rsi
0x1401d984b  mov     [r11+18h], r8
0x1401d984f  mov     [r11+10h], rdx
0x1401d9853  push    rdi
0x1401d9854  push    r12
0x1401d9856  push    r13
0x1401d9858  push    r14
0x1401d985a  push    r15
0x1401d985c  sub     rsp, 0A0h
0x1401d9863  mov     esi, r9d
0x1401d9866  mov     rdi, rdx
0x1401d9869  mov     r14, rcx
0x1401d986c  xor     r13d, r13d
0x1401d986f  mov     [r11-70h], r13
0x1401d9873  mov     r12b, r13b
0x1401d9876  mov     [r11-74h], r13b
0x1401d987a  xor     eax, eax
0x1401d987c  xorps   xmm0, xmm0
0x1401d987f  movups  xmmword ptr [rsp+0C8h+var_58.Length], xmm0
0x1401d9884  movups  xmmword ptr [r11-48h], xmm0
0x1401d9889  movups  xmmword ptr [r11-3Ch], xmm0
0x1401d988e  mov     [r11-68h], r13b
0x1401d9892  mov     [r11-60h], r13
0x1401d9896  test    dword ptr [rdx+88h], 8000h
0x1401d98a0  jnz     loc_1401DA1BF
0x1401d98a6  mov     eax, 100h
0x1401d98ab  cmp     r9d, eax
0x1401d98ae  jz      loc_1401D9B4A
0x1401d98b4  cmp     r9d, 2000h
0x1401d98bb  jz      loc_1401D9D27
0x1401d98c1  lea     rdx, [r11+18h]; Key
0x1401d98c5  call    cs:__imp_TmReferenceEnlistmentKey
0x1401d98cc  nop     dword ptr [rax+rax+00h]
0x1401d98d1  mov     ebx, eax
0x1401d98d3  mov     [rsp+0C8h+var_78], eax
0x1401d98d7  mov     rcx, [rsp+0C8h+arg_10]
0x1401d98df  test    rcx, rcx
0x1401d98e2  jz      loc_1401D9D56
0x1401d98e8  mov     [rsp+0C8h+EnlistmentKey], rcx
0x1401d98ed  bt      dword ptr [rcx+10h], 11h
0x1401d98f2  jb      loc_1401D9DC0
0x1401d98f8  mov     [rsp+0C8h+var_78], r13d
0x1401d98fd  mov     rbx, [rsp+0C8h+TmVirtualClock]
0x1401d9905  test    rbx, rbx
0x1401d9908  jnz     loc_1401D9E4C
0x1401d990e  cmp     esi, 2
0x1401d9911  jz      loc_1401D99A6
0x1401d9917  cmp     esi, 4
0x1401d991a  jz      loc_1401D99FE
0x1401d9920  cmp     esi, 8
0x1401d9923  jz      loc_1401D9A7C
0x1401d9929  cmp     esi, 200h
0x1401d992f  jz      loc_1401D99FE
0x1401d9935  cmp     esi, 4000h
0x1401d993b  jz      loc_1401D9EA6
0x1401d9941  mov     al, cs:NtfsStatusDebugFlags
0x1401d9947  mov     ebx, 0C000000Dh
0x1401d994c  test    al, al
0x1401d994e  jnz     loc_1401D99EA
0x1401d9954  mov     [rsp+0C8h+var_78], ebx
0x1401d9958  lea     rdx, [rsp+0C8h+LastReference]; LastReference
0x1401d995d  mov     rcx, r14; Enlistment
0x1401d9960  call    cs:__imp_TmDereferenceEnlistmentKey
0x1401d9967  nop     dword ptr [rax+rax+00h]
0x1401d996c  mov     [rsp+0C8h+arg_10], r13
0x1401d9974  test    r12b, r12b
0x1401d9977  jz      loc_1401DA1A0
0x1401d997d  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9982  mov     rcx, r13
0x1401d9985  xchg    rcx, [rax+0F8h]; Handle
0x1401d998c  test    rcx, rcx
0x1401d998f  jz      loc_1401DA1A0
0x1401d9995  call    cs:__imp_ZwClose
0x1401d999c  nop     dword ptr [rax+rax+00h]
0x1401d99a1  jmp     loc_1401DA1A0
0x1401d99a6  lea     r8, [rsp+0C8h+var_68]
0x1401d99ab  xor     edx, edx
0x1401d99ad  call    TxfTransMgrPrepareCommit
0x1401d99b2  mov     ebx, eax
0x1401d99b4  mov     [rsp+0C8h+var_78], eax
0x1401d99b8  test    eax, eax
0x1401d99ba  js      loc_1401DA175
0x1401d99c0  cmp     [rsp+0C8h+var_68], r13b
0x1401d99c5  jz      loc_1401DA173
0x1401d99cb  xor     edx, edx; TmVirtualClock
0x1401d99cd  mov     rcx, r14; Enlistment
0x1401d99d0  call    cs:__imp_TmReadOnlyEnlistment
0x1401d99d7  nop     dword ptr [rax+rax+00h]
0x1401d99dc  mov     ebx, eax
0x1401d99de  mov     [rsp+0C8h+var_78], eax
0x1401d99e2  mov     r12b, 1
0x1401d99e5  jmp     loc_1401D9958
0x1401d99ea  mov     r8d, 311A30h
0x1401d99f0  mov     edx, ebx
0x1401d99f2  xor     ecx, ecx
0x1401d99f4  call    NtfsStatusTraceAndDebugInternal
0x1401d99f9  jmp     loc_1401D9954
0x1401d99fe  mov     r15b, [rcx+10h]
0x1401d9a02  and     r15b, 1
0x1401d9a06  lea     r8, [rsp+0C8h+var_68]
0x1401d9a0b  mov     edx, 1
0x1401d9a10  call    TxfTransMgrPrepareCommit
0x1401d9a15  mov     r8d, eax
0x1401d9a18  mov     [rsp+0C8h+var_78], eax
0x1401d9a1c  test    eax, eax
0x1401d9a1e  jns     loc_1401DA033
0x1401d9a24  test    dword ptr [rdi+88h], 8000h
0x1401d9a2e  jz      loc_1401DA089
0x1401d9a34  mov     al, cs:NtfsStatusDebugFlags
0x1401d9a3a  mov     ebx, 103h
0x1401d9a3f  jmp     loc_1401D9954
0x1401d9a44  mov     al, cs:NtfsStatusDebugFlags
0x1401d9a4a  mov     ebx, 0C000000Dh
0x1401d9a4f  test    al, al
0x1401d9a51  jz      short loc_1401D9A62
0x1401d9a53  mov     r8d, 3118A4h
0x1401d9a59  mov     edx, ebx
0x1401d9a5b  xor     ecx, ecx
0x1401d9a5d  call    NtfsStatusTraceAndDebugInternal
0x1401d9a62  mov     [rsp+0C8h+var_78], ebx
0x1401d9a66  xor     edx, edx; LastReference
0x1401d9a68  mov     rcx, r14; Enlistment
0x1401d9a6b  call    cs:__imp_TmDereferenceEnlistmentKey
0x1401d9a72  nop     dword ptr [rax+rax+00h]
0x1401d9a77  jmp     loc_1401DA1A0
0x1401d9a7c  mov     rcx, [rcx+18h]
0x1401d9a80  add     rcx, 50h ; 'P'; Resource
0x1401d9a84  mov     dl, 1; Wait
0x1401d9a86  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d9a8d  nop     dword ptr [rax+rax+00h]
0x1401d9a92  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9a97  or      dword ptr [rax+1B4h], 1
0x1401d9a9e  mov     rdx, [rsp+0C8h+EnlistmentKey]
0x1401d9aa3  lea     rax, [rdx+1A0h]
0x1401d9aaa  cmp     [rax], rax
0x1401d9aad  jz      loc_1401D9ED4
0x1401d9ab3  mov     ebx, 103h
0x1401d9ab8  mov     edi, ebx
0x1401d9aba  mov     [rsp+0C8h+var_78], ebx
0x1401d9abe  jmp     loc_1401D9F60
0x1401d9ac3  mov     rcx, [rdx+18h]
0x1401d9ac7  add     rcx, 50h ; 'P'; Resource
0x1401d9acb  mov     dl, 1; Wait
0x1401d9acd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d9ad4  nop     dword ptr [rax+rax+00h]
0x1401d9ad9  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9ade  or      dword ptr [rax+1B4h], 1
0x1401d9ae5  mov     rcx, [rsp+0C8h+EnlistmentKey]
0x1401d9aea  lea     rax, [rcx+1A0h]
0x1401d9af1  cmp     [rax], rax
0x1401d9af4  jz      loc_1401DA114
0x1401d9afa  mov     rcx, [rcx+18h]
0x1401d9afe  add     rcx, 50h ; 'P'; Resource
0x1401d9b02  call    cs:__imp_ExReleaseResourceLite
0x1401d9b09  nop     dword ptr [rax+rax+00h]
0x1401d9b0e  mov     al, cs:NtfsStatusDebugFlags
0x1401d9b14  mov     ebx, 0C0190003h
0x1401d9b19  test    al, al
0x1401d9b1b  jz      loc_1401D9954
0x1401d9b21  mov     r8d, 311987h
0x1401d9b27  jmp     loc_1401D99F0
0x1401d9b2c  mov     al, cs:NtfsStatusDebugFlags
0x1401d9b32  mov     ebx, 0C0190003h
0x1401d9b37  test    al, al
0x1401d9b39  jz      loc_1401D9954
0x1401d9b3f  mov     r8d, 311A0Eh
0x1401d9b45  jmp     loc_1401D99F0
0x1401d9b4a  mov     rsi, [rsp+0C8h+Argument]
0x1401d9b52  lea     rdx, [rsi+10h]
0x1401d9b56  lea     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9b5b  mov     [rsp+0C8h+HandleInformation], rax
0x1401d9b60  mov     [rsp+0C8h+ObjectAttributes], r13
0x1401d9b65  mov     r9d, 1
0x1401d9b6b  xor     r8d, r8d
0x1401d9b6e  mov     rcx, rdi
0x1401d9b71  call    TxfTransMgrSearchAddTrans
0x1401d9b76  mov     ebx, eax
0x1401d9b78  mov     [rsp+0C8h+var_78], eax
0x1401d9b7c  cmp     eax, 0C0190061h
0x1401d9b81  jnz     short loc_1401D9B90
0x1401d9b83  mov     rax, r13
0x1401d9b86  mov     [rsp+0C8h+EnlistmentKey], rax
0x1401d9b8b  jmp     loc_1401D9C11
0x1401d9b90  test    eax, eax
0x1401d9b92  jns     short loc_1401D9BCB
0x1401d9b94  mov     r9d, 31180Eh
0x1401d9b9a  jmp     short loc_1401D9BA2
0x1401d9b9c  mov     r9d, 311847h
0x1401d9ba2  mov     r8d, eax
0x1401d9ba5  jmp     short loc_1401D9BBC
0x1401d9ba7  xor     edx, edx
0x1401d9ba9  lea     rcx, [rsp+0C8h+EnlistmentKey]
0x1401d9bae  call    TxfDereferenceTransaction
0x1401d9bb3  mov     r9d, 311868h
0x1401d9bb9  mov     r8d, ebx
0x1401d9bbc  mov     rdx, rdi
0x1401d9bbf  xor     ecx, ecx
0x1401d9bc1  call    TxfHardErrorFcn
0x1401d9bc6  jmp     loc_1401DA1A0
0x1401d9bcb  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9bd0  mov     rcx, [rax+18h]
0x1401d9bd4  add     rcx, 50h ; 'P'; Resource
0x1401d9bd8  mov     dl, 1; Wait
0x1401d9bda  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d9be1  nop     dword ptr [rax+rax+00h]
0x1401d9be6  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9beb  inc     dword ptr [rax+4]
0x1401d9bee  mov     [rsp+0C8h+LastReference], 1
0x1401d9bf3  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9bf8  mov     rcx, [rax+18h]
0x1401d9bfc  add     rcx, 50h ; 'P'; Resource
0x1401d9c00  call    cs:__imp_ExReleaseResourceLite
0x1401d9c07  nop     dword ptr [rax+rax+00h]
0x1401d9c0c  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9c11  mov     [rsp+0C8h+var_58.Length], 30h ; '0'
0x1401d9c19  mov     [rsp+0C8h+var_58.RootDirectory], r13
0x1401d9c1e  mov     [rsp+0C8h+var_58.Attributes], 240h
0x1401d9c29  mov     [rsp+0C8h+var_58.ObjectName], r13
0x1401d9c31  xorps   xmm0, xmm0
0x1401d9c34  movdqu  xmmword ptr [rsp+0C8h+var_58.SecurityDescriptor], xmm0
0x1401d9c3d  test    rax, rax
0x1401d9c40  lea     rcx, [rax+0F8h]
0x1401d9c47  jnz     short loc_1401D9C4E
0x1401d9c49  lea     rcx, [rsp+0C8h+EnlistmentHandle]; EnlistmentHandle
0x1401d9c4e  lea     rax, [rsp+0C8h+var_58]
0x1401d9c53  mov     [rsp+0C8h+ObjectAttributes], rax; ObjectAttributes
0x1401d9c58  mov     r9, rsi; EnlistmentGuid
0x1401d9c5b  mov     r8, [rdi+290h]; RmHandle
0x1401d9c62  mov     edx, 0F001Fh; DesiredAccess
0x1401d9c67  call    cs:__imp_ZwOpenEnlistment
0x1401d9c6e  nop     dword ptr [rax+rax+00h]
0x1401d9c73  mov     ebx, eax
0x1401d9c75  mov     [rsp+0C8h+var_78], eax
0x1401d9c79  test    eax, eax
0x1401d9c7b  jns     short loc_1401D9C88
0x1401d9c7d  mov     r9d, 311832h
0x1401d9c83  jmp     loc_1401D9BA2
0x1401d9c88  mov     rcx, [rsp+0C8h+EnlistmentKey]
0x1401d9c8d  test    rcx, rcx
0x1401d9c90  jz      short loc_1401D9CE6
0x1401d9c92  lea     rax, [rcx+0F0h]
0x1401d9c99  mov     [rsp+0C8h+HandleInformation], r13; HandleInformation
0x1401d9c9e  mov     [rsp+0C8h+ObjectAttributes], rax; Object
0x1401d9ca3  xor     r9d, r9d; AccessMode
0x1401d9ca6  mov     r8, cs:TmEnlistmentObjectType
0x1401d9cad  mov     r8, [r8]; ObjectType
0x1401d9cb0  xor     edx, edx; DesiredAccess
0x1401d9cb2  mov     rcx, [rcx+0F8h]; Handle
0x1401d9cb9  call    cs:__imp_ObReferenceObjectByHandle
0x1401d9cc0  nop     dword ptr [rax+rax+00h]
0x1401d9cc5  mov     ebx, eax
0x1401d9cc7  mov     [rsp+0C8h+var_78], eax
0x1401d9ccb  test    eax, eax
0x1401d9ccd  js      loc_1401D9B9C
0x1401d9cd3  mov     rcx, [rsp+0C8h+EnlistmentKey]
0x1401d9cd8  test    rcx, rcx
0x1401d9cdb  jz      short loc_1401D9CE6
0x1401d9cdd  mov     rax, [rcx+0F8h]
0x1401d9ce4  jmp     short loc_1401D9CEB
0x1401d9ce6  mov     rax, [rsp+0C8h+EnlistmentHandle]
0x1401d9ceb  mov     rdx, rcx; EnlistmentKey
0x1401d9cee  mov     rcx, rax; EnlistmentHandle
0x1401d9cf1  call    cs:__imp_ZwRecoverEnlistment
0x1401d9cf8  nop     dword ptr [rax+rax+00h]
0x1401d9cfd  mov     ebx, eax
0x1401d9cff  mov     [rsp+0C8h+var_78], eax
0x1401d9d03  test    eax, eax
0x1401d9d05  jns     short loc_1401D9D4A
0x1401d9d07  mov     rax, [rsp+0C8h+EnlistmentKey]
0x1401d9d0c  test    rax, rax
0x1401d9d0f  jz      loc_1401D9BB3
0x1401d9d15  cmp     [rax+0F0h], r13
0x1401d9d1c  jz      loc_1401D9BB3
0x1401d9d22  jmp     loc_1401D9BA7
0x1401d9d27  lock or [rdx+88h], eax
0x1401d9d2e  mov     rcx, [rdx+18h]
0x1401d9d32  add     rcx, 1C0h; Event
0x1401d9d39  xor     r8d, r8d; Wait
0x1401d9d3c  xor     edx, edx; Increment
0x1401d9d3e  call    cs:__imp_KeSetEvent
0x1401d9d45  nop     dword ptr [rax+rax+00h]
0x1401d9d4a  mov     ebx, r13d
0x1401d9d4d  mov     [rsp+0C8h+var_78], ebx
0x1401d9d51  jmp     loc_1401DA1A0
0x1401d9d56  cmp     esi, 2
0x1401d9d59  jz      short loc_1401D9DA4
0x1401d9d5b  cmp     esi, 4
0x1401d9d5e  jz      short loc_1401D9D91
0x1401d9d60  cmp     esi, 8
0x1401d9d63  jz      short loc_1401D9D7E
0x1401d9d65  cmp     esi, 200h
0x1401d9d6b  jz      short loc_1401D9D91
0x1401d9d6d  cmp     esi, 4000h
0x1401d9d73  jz      loc_1401D9A66
0x1401d9d79  jmp     loc_1401D9A44
0x1401d9d7e  xor     edx, edx; TmVirtualClock
0x1401d9d80  mov     rcx, r14; Enlistment
0x1401d9d83  call    cs:__imp_TmRollbackComplete
  ... truncated ...
```

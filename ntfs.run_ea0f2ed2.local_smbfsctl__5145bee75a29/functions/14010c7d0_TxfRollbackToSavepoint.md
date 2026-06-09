# TxfRollbackToSavepoint

- ea: `0x14010c7d0`
- end: `0x14010cec0`
- name: `TxfRollbackToSavepoint`
- size: `1776`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400fddfc`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x140008740`
- `0x140010be0`
- `0x140012ab0`
- `0x140012b50`
- `0x140016ea0`
- `0x140017030`
- `0x140038908`
- `0x140059250`
- `0x1400596c0`
- `0x1400b62e4`
- `0x14010c7d0`
- `0x140140f5c`
- `0x140188ce4`
- `0x14018dc4c`
- `0x1401d8340`
- `0x1401d973c`
- `0x1401da930`
- `0x1401dc54c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14010cd47`
- `ntoskrnl!KeSetEvent` at `0x1402c5e90`
- `ntoskrnl!KeSetEvent` at `0x14010cd47`
- `ntoskrnl!KeSetEvent` at `0x1402c5e90`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14010cdeb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c5f29`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14010cdeb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c5f29`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c89e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c89e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010caaa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010caaa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010cac8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010cac8`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010cb30`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010cb30`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010cb4f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010cb4f`
- `ntoskrnl!ExRaiseStatus` at `0x14010cc5c`
- `ntoskrnl!ExRaiseStatus` at `0x14010cc5c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14010cd85`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1402c5ecb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14010cd85`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1402c5ecb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010ca4b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010cc7a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010cda5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1402c5ee3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010ca4b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010cc7a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010cda5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1402c5ee3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x14010cd02`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1402c5e40`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x14010cd02`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1402c5e40`

## string_xrefs

- `0x14010ca82`: `TxfRollbackToSavepoint`

## pseudocode

```c
__int64 __fastcall TxfRollbackToSavepoint(__int64 a1, CLFS_CONTAINER_ID a2)
{
  NTSTATUS Undo; // ebx
  char v5; // r12
  char v6; // r14
  __int64 v7; // rsi
  CLFS_LSN *v8; // r15
  __int64 v9; // rax
  __int64 v10; // r8
  _QWORD *v11; // rax
  char v12; // dl
  CLFS_LSN *v13; // r14
  _QWORD *i; // rdx
  int v15; // ecx
  unsigned int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rax
  NTSTATUS v19; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rsi
  __int64 v24; // rax
  void *v25; // r14
  const CLFS_LSN *v26; // r15
  const CLFS_LSN ***v27; // r13
  bool v28; // zf
  ULONGLONG ullOffset; // rcx
  const CLFS_LSN **v30; // rax
  void *v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  char v35; // [rsp+40h] [rbp-338h]
  char v36; // [rsp+41h] [rbp-337h]
  CLFS_LSN plsn1; // [rsp+48h] [rbp-330h] BYREF
  _QWORD v38[2]; // [rsp+50h] [rbp-328h] BYREF
  CLFS_LSN plsn2; // [rsp+60h] [rbp-318h] BYREF
  __int64 v40; // [rsp+68h] [rbp-310h]
  int *v41; // [rsp+70h] [rbp-308h] BYREF
  CLFS_LSN v42; // [rsp+78h] [rbp-300h] BYREF
  _QWORD *v43; // [rsp+80h] [rbp-2F8h]
  _OWORD v44[2]; // [rsp+88h] [rbp-2F0h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-2D0h]
  int v46[164]; // [rsp+B0h] [rbp-2C8h] BYREF

  v40 = a1;
  Undo = 0;
  v36 = 0;
  v5 = 0;
  v6 = 0;
  v35 = 0;
  plsn1.ullOffset = 0;
  plsn2.ullOffset = 0;
  v7 = *(_QWORD *)(a1 + 208);
  v38[0] = v7;
  v8 = 0;
  v43 = 0;
  v42.ullOffset = 0;
  memset(v46, 0, sizeof(v46));
  v38[1] = v46;
  memset(v44, 0, sizeof(v44));
  v45 = 0;
  while ( _InterlockedIncrement((volatile signed __int32 *)(v7 + 232)) > 10 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v7 + 232));
    KeWaitForSingleObject((PVOID)(*(_QWORD *)(v7 + 24) + 72LL), Executive, 0, 0, 0);
  }
  v41 = v46;
  memset(v46, 0, sizeof(v46));
  if ( !(unsigned int)NtfsInitializeIrpContextInternal(0, 1, 0, (__int64 *)&v41) )
    *((_WORD *)v41 + 1) = 656;
  v9 = NtfsInitializeTopLevelIrp(v44, 3, *(_QWORD *)(v7 + 16));
  NtfsUpdateIrpContextWithTopLevel(v46, v9);
  v46[3] |= 0x10001u;
  NtfsSetIrpContextVcb(v46, *(_QWORD *)(v7 + 16));
  v46[109] |= 0x80048u;
  TxfTransFreeze(a1, 0);
  if ( (*(_DWORD *)(a1 + 16) & 0x80u) != 0 )
  {
    Undo = -1073741431;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_62;
    v10 = 3216656;
    goto LABEL_9;
  }
  if ( a2 <= *(_DWORD *)(a1 + 352) && a2 )
  {
    if ( *(_DWORD *)(a1 + 448) )
    {
      Undo = -1072103352;
      if ( NtfsStatusDebugFlags )
      {
        v10 = 3216678;
LABEL_9:
        NtfsStatusTraceAndDebugInternal(0, (unsigned int)Undo, v10);
      }
    }
    else
    {
      v11 = *(_QWORD **)(a1 + 320);
      v12 = 0;
      while ( v11 != (_QWORD *)(a1 + 320) )
      {
        v8 = (CLFS_LSN *)(v11 - 4);
        v43 = v11 - 4;
        if ( *((_DWORD *)v11 - 7) <= a2 )
        {
          v12 = 1;
          plsn2 = v8[1];
          if ( v8->offset.cidContainer < a2 )
          {
            v5 = 1;
            v8[3].offset.idxRecord |= 3u;
          }
          break;
        }
        v11 = (_QWORD *)*v11;
      }
      if ( v12 )
      {
        _InterlockedOr((volatile signed __int32 *)(a1 + 16), 0x400u);
        v13 = (CLFS_LSN *)(a1 + 48);
        if ( ClfsLsnGreater((const CLFS_LSN *)(a1 + 48), &plsn2) )
        {
          ExAcquireFastMutex(*(PFAST_MUTEX *)(v7 + 8912));
          v42 = *(CLFS_LSN *)(v7 + 8920);
          ExReleaseFastMutex(*(PFAST_MUTEX *)(v7 + 8912));
          v19 = TxfActOnAllStreamsForTransaction((unsigned int)v46, 2, &v42);
          Undo = v19;
          v36 = 1;
          if ( v19 )
          {
            if ( v19 == -30 )
            {
              v20 = TxfSearchAddTxfFcbCleanupList(v46[36], 0, 5, 0, 1);
              *(_DWORD *)(v20 + 16) |= 0x200u;
              *(_DWORD *)(*(_QWORD *)&v46[36] + 436LL) |= 0x20u;
              v21 = *(_QWORD *)(a1 + 208);
              *(_QWORD *)(v20 + 32) = v21;
              _InterlockedIncrement((volatile signed __int32 *)(v21 + 64));
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v20 + 32) + 48LL));
              Undo = -1073741608;
            }
            if ( NtfsStatusDebugFlags
              && Undo
              && Undo != 294
              && (unsigned int)(Undo - 298) > 1
              && (unsigned int)Undo < 0xFFFFFFED
              && Undo != -1073741608
              && Undo != -1073741802
              && Undo != -1073741807
              && (unsigned int)(Undo + 2147483643) > 1
              && Undo != 259 )
            {
              NtfsStatusTraceAndDebugInternal(v46, (unsigned int)Undo, 3216818);
            }
            ExRaiseStatus(Undo);
          }
          plsn1 = *v13;
          do
          {
            if ( !ClfsLsnGreater(&plsn1, &plsn2) )
              break;
            v35 = 1;
            Undo = TxfTransDoNextUndo((int)v46, a1);
          }
          while ( Undo >= 0 );
        }
        else
        {
          plsn1 = *v13;
          ProcessSavepointListForCurrentLogRec(a1);
        }
        if ( Undo < 0 )
          TxfSetupForDeferredAbortPriv(
            a1,
            Undo,
            (unsigned int)"TxfRollbackToSavepoint",
            (unsigned int)"txftrans.c",
            5599);
        if ( v5 )
          v8[1] = *(CLFS_LSN *)(a1 + 40);
        ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(a1 + 24) + 80LL), 1u);
        *(_DWORD *)(a1 + 352) = a2 - 1;
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 24) + 80LL));
        for ( i = *(_QWORD **)(a1 + 192); i != (_QWORD *)(a1 + 192); i = (_QWORD *)*i )
        {
          v15 = *((_DWORD *)i - 17);
          if ( (v15 & 0x60000) != 0 )
          {
            v16 = v15 & 0xFFFDFFFF;
            *((_DWORD *)i - 17) = v16;
            if ( (v16 & 0x40000) != 0 )
            {
              v17 = *(i - 3);
              if ( v17 )
              {
                v18 = *(_QWORD *)(v17 + 8);
                if ( v18 )
                {
                  if ( (*(_DWORD *)(v18 + 176) & 0x400) == 0 )
                    *((_DWORD *)i - 17) = v16 & 0xFFFBFFFF;
                }
              }
            }
          }
        }
        v6 = v35;
      }
      else
      {
        Undo = -1073741811;
        if ( NtfsStatusDebugFlags )
        {
          v10 = 3216724;
          goto LABEL_9;
        }
      }
    }
  }
  else
  {
    Undo = -1073741811;
    if ( NtfsStatusDebugFlags )
    {
      v10 = 3216668;
      goto LABEL_9;
    }
  }
LABEL_62:
  if ( *(_QWORD *)(a1 + 224) )
  {
    NtfsPurgeFileRecordCache(v46);
    v46[1] |= 0x200u;
    ClfsTerminateReadLog(*(PVOID *)(a1 + 224));
    v46[1] &= ~0x200u;
    *(_QWORD *)(a1 + 224) = 0;
    _InterlockedDecrement((volatile signed __int32 *)(v7 + 528));
  }
  if ( v5 )
    v8[3].offset.idxRecord &= ~1u;
  _InterlockedDecrement((volatile signed __int32 *)(v7 + 232));
  KeSetEvent((PRKEVENT)(*(_QWORD *)(v7 + 24) + 72LL), 0, 0);
  if ( v6 )
  {
    v23 = *(_QWORD *)(a1 + 184);
LABEL_68:
    v24 = a1 + 176;
    while ( v23 != v24 )
    {
      v25 = (void *)v23;
      v26 = (const CLFS_LSN *)v23;
      v27 = (const CLFS_LSN ***)(v23 + 8);
      v23 = *(_QWORD *)(v23 + 8);
      v28 = ClfsLsnNull(v26 + 2) == 0;
      v24 = a1 + 176;
      if ( v28 )
      {
        if ( !ClfsLsnGreater(v26 + 2, &plsn1) )
          break;
        ullOffset = v26->ullOffset;
        if ( *(const CLFS_LSN **)(v26->ullOffset + 8) != v26 || (v30 = *v27, **v27 != v26) )
          __fastfail(3u);
        *v30 = (const CLFS_LSN *)ullOffset;
        *(_QWORD *)(ullOffset + 8) = v30;
        v31 = (void *)v26[4].ullOffset;
        if ( v31 )
          TxfDereferenceTxfFcb(v31);
        ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, v25);
        goto LABEL_68;
      }
    }
    TxfCloseHandlesForTransaction(v46, a1, 0);
  }
  if ( v36 )
    Undo = TxfActOnAllStreamsForTransaction((unsigned int)v46, 4, 0);
  v38[0] = a1;
  LOBYTE(v22) = 1;
  TxfDereferenceTransaction(v38, v22);
  NtfsCleanupIrpContext((__int64)v46, 0, v32);
  v46[3] &= ~0x10000u;
  LOBYTE(v33) = 1;
  NtfsExtendedCompleteRequestInternal(v46, 0, 0, v33, 1);
  return (unsigned int)Undo;
}

```

## disassembly

```asm
0x14010c7d0  mov     [rsp+arg_8], rbx
0x14010c7d5  mov     [rsp+arg_10], rsi
0x14010c7da  push    rdi
0x14010c7db  push    r12
0x14010c7dd  push    r13
0x14010c7df  push    r14
0x14010c7e1  push    r15
0x14010c7e3  sub     rsp, 340h
0x14010c7ea  mov     rax, cs:__security_cookie
0x14010c7f1  xor     rax, rsp
0x14010c7f4  mov     [rsp+368h+var_38], rax
0x14010c7fc  mov     r13d, edx
0x14010c7ff  mov     rdi, rcx
0x14010c802  mov     [rsp+368h+var_310], rcx
0x14010c807  xor     eax, eax
0x14010c809  mov     ebx, eax
0x14010c80b  mov     [rsp+368h+var_335], al
0x14010c80f  mov     [rsp+368h+var_337], al
0x14010c813  mov     r12b, al
0x14010c816  mov     [rsp+368h+var_336], al
0x14010c81a  mov     r14b, al
0x14010c81d  mov     [rsp+368h+var_338], al
0x14010c821  mov     qword ptr [rsp+368h+plsn1], rax
0x14010c826  mov     qword ptr [rsp+368h+plsn2], rax
0x14010c82b  mov     rsi, [rcx+0D0h]
0x14010c832  mov     [rsp+368h+var_328], rsi
0x14010c837  mov     r15d, eax
0x14010c83a  mov     [rsp+368h+var_2F8], rax
0x14010c83f  mov     [rsp+368h+var_300], rax
0x14010c844  xor     edx, edx; Val
0x14010c846  mov     r8d, 290h; Size
0x14010c84c  lea     rcx, [rsp+368h+var_2C8]; void *
0x14010c854  call    memset
0x14010c859  lea     rax, [rsp+368h+var_2C8]
0x14010c861  mov     [rsp+368h+var_320], rax
0x14010c866  xorps   xmm0, xmm0
0x14010c869  xor     eax, eax
0x14010c86b  movups  [rsp+368h+var_2F0], xmm0
0x14010c870  movups  [rsp+368h+var_2E0], xmm0
0x14010c878  mov     [rsp+368h+var_2D0], rax
0x14010c880  jmp     short loc_14010C8AA
0x14010c882  lock dec dword ptr [rsi+0E8h]
0x14010c889  mov     rcx, [rsi+18h]
0x14010c88d  add     rcx, 48h ; 'H'; Object
0x14010c891  mov     [rsp+368h+Timeout], rbx; Timeout
0x14010c896  xor     r9d, r9d; Alertable
0x14010c899  xor     r8d, r8d; WaitMode
0x14010c89c  xor     edx, edx; WaitReason
0x14010c89e  call    cs:__imp_KeWaitForSingleObject
0x14010c8a5  nop     dword ptr [rax+rax+00h]
0x14010c8aa  mov     eax, 1
0x14010c8af  lock xadd [rsi+0E8h], eax
0x14010c8b7  inc     eax
0x14010c8b9  cmp     eax, 0Ah
0x14010c8bc  jg      short loc_14010C882
0x14010c8be  lea     rax, [rsp+368h+var_2C8]
0x14010c8c6  mov     [rsp+368h+var_308], rax
0x14010c8cb  xor     edx, edx; Val
0x14010c8cd  mov     r8d, 290h; Size
0x14010c8d3  lea     rcx, [rsp+368h+var_2C8]; void *
0x14010c8db  call    memset
0x14010c8e0  lea     r9, [rsp+368h+var_308]
0x14010c8e5  xor     r8d, r8d
0x14010c8e8  mov     dl, 1
0x14010c8ea  xor     ecx, ecx; Irp
0x14010c8ec  call    NtfsInitializeIrpContextInternal
0x14010c8f1  test    eax, eax
0x14010c8f3  jnz     short loc_14010C903
0x14010c8f5  mov     rax, [rsp+368h+var_308]
0x14010c8fa  mov     ecx, 290h
0x14010c8ff  mov     [rax+2], cx
0x14010c903  mov     r8, [rsi+10h]
0x14010c907  mov     edx, 3
0x14010c90c  lea     rcx, [rsp+368h+var_2F0]
0x14010c911  call    NtfsInitializeTopLevelIrp
0x14010c916  mov     rdx, rax
0x14010c919  lea     rcx, [rsp+368h+var_2C8]
0x14010c921  call    NtfsUpdateIrpContextWithTopLevel
0x14010c926  or      [rsp+368h+var_2BC], 10001h
0x14010c931  mov     rdx, [rsi+10h]
0x14010c935  lea     rcx, [rsp+368h+var_2C8]
0x14010c93d  call    NtfsSetIrpContextVcb
0x14010c942  mov     eax, [rsp+368h+var_114]
0x14010c949  or      eax, 80008h
0x14010c94e  mov     [rsp+368h+var_114], eax
0x14010c955  or      eax, 40h
0x14010c958  mov     [rsp+368h+var_114], eax
0x14010c95f  xor     edx, edx
0x14010c961  mov     rcx, rdi
0x14010c964  call    TxfTransFreeze
0x14010c969  mov     [rsp+368h+var_335], 1
0x14010c96e  mov     eax, [rdi+10h]
0x14010c971  test    al, al
0x14010c973  jns     short loc_14010C99C
0x14010c975  mov     al, cs:NtfsStatusDebugFlags
0x14010c97b  mov     ebx, 0C0000189h
0x14010c980  test    al, al
0x14010c982  jz      short loc_14010C993
0x14010c984  mov     r8d, 311510h
0x14010c98a  mov     edx, ebx
0x14010c98c  xor     ecx, ecx
0x14010c98e  call    NtfsStatusTraceAndDebugInternal
0x14010c993  mov     [rsp+368h+var_334], ebx
0x14010c997  jmp     loc_14010CCDB
0x14010c99c  cmp     r13d, [rdi+160h]
0x14010c9a3  ja      loc_14010CCB8
0x14010c9a9  cmp     r13d, 1
0x14010c9ad  jb      loc_14010CCB8
0x14010c9b3  cmp     dword ptr [rdi+1C0h], 0
0x14010c9ba  jz      short loc_14010C9D3
0x14010c9bc  mov     al, cs:NtfsStatusDebugFlags
0x14010c9c2  mov     ebx, 0C0190048h
0x14010c9c7  test    al, al
0x14010c9c9  jz      short loc_14010C993
0x14010c9cb  mov     r8d, 311526h
0x14010c9d1  jmp     short loc_14010C98A
0x14010c9d3  lea     rcx, [rdi+140h]
0x14010c9da  mov     rax, [rcx]
0x14010c9dd  xor     dl, dl
0x14010c9df  cmp     rax, rcx
0x14010c9e2  jz      short loc_14010CA10
0x14010c9e4  lea     r15, [rax-20h]
0x14010c9e8  mov     [rsp+368h+var_2F8], r15
0x14010c9ed  cmp     [r15+4], r13d
0x14010c9f1  ja      short loc_14010CA32
0x14010c9f3  mov     dl, 1
0x14010c9f5  mov     rax, [r15+8]
0x14010c9f9  mov     qword ptr [rsp+368h+plsn2], rax
0x14010c9fe  cmp     [r15+4], r13d
0x14010ca02  jnb     short loc_14010CA10
0x14010ca04  mov     r12b, dl
0x14010ca07  mov     [rsp+368h+var_336], dl
0x14010ca0b  or      dword ptr [r15+18h], 3
0x14010ca10  test    dl, dl
0x14010ca12  jnz     short loc_14010CA37
0x14010ca14  mov     al, cs:NtfsStatusDebugFlags
0x14010ca1a  mov     ebx, 0C000000Dh
0x14010ca1f  test    al, al
0x14010ca21  jz      loc_14010C993
0x14010ca27  mov     r8d, 311554h
0x14010ca2d  jmp     loc_14010C98A
0x14010ca32  mov     rax, [rax]
0x14010ca35  jmp     short loc_14010C9DF
0x14010ca37  lock or dword ptr [rdi+10h], 400h
0x14010ca3f  lea     r14, [rdi+30h]
0x14010ca43  lea     rdx, [rsp+368h+plsn2]; plsn2
0x14010ca48  mov     rcx, r14; plsn1
0x14010ca4b  call    cs:__imp_ClfsLsnGreater
0x14010ca52  nop     dword ptr [rax+rax+00h]
0x14010ca57  test    al, al
0x14010ca59  jnz     loc_14010CB29
0x14010ca5f  mov     rax, [r14]
0x14010ca62  mov     qword ptr [rsp+368h+plsn1], rax
0x14010ca67  mov     rcx, rdi
0x14010ca6a  call    ProcessSavepointListForCurrentLogRec
0x14010ca6f  test    ebx, ebx
0x14010ca71  jns     short loc_14010CA93
0x14010ca73  mov     dword ptr [rsp+368h+Timeout], 15DFh
0x14010ca7b  lea     r9, aTxftransC; "txftrans.c"
0x14010ca82  lea     r8, aTxfrollbacktos; "TxfRollbackToSavepoint"
0x14010ca89  mov     edx, ebx
0x14010ca8b  mov     rcx, rdi
0x14010ca8e  call    TxfSetupForDeferredAbortPriv
0x14010ca93  test    r12b, r12b
0x14010ca96  jz      short loc_14010CAA0
0x14010ca98  mov     rax, [rdi+28h]
0x14010ca9c  mov     [r15+8], rax
0x14010caa0  mov     rcx, [rdi+18h]
0x14010caa4  add     rcx, 50h ; 'P'; Resource
0x14010caa8  mov     dl, 1; Wait
0x14010caaa  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14010cab1  nop     dword ptr [rax+rax+00h]
0x14010cab6  lea     eax, [r13-1]
0x14010caba  mov     [rdi+160h], eax
0x14010cac0  mov     rcx, [rdi+18h]
0x14010cac4  add     rcx, 50h ; 'P'; Resource
0x14010cac8  call    cs:__imp_ExReleaseResourceLite
0x14010cacf  nop     dword ptr [rax+rax+00h]
0x14010cad4  lea     r8, [rdi+0C0h]
0x14010cadb  mov     rdx, [r8]
0x14010cade  cmp     rdx, r8
0x14010cae1  jz      loc_14010CCD6
0x14010cae7  mov     ecx, [rdx-44h]
0x14010caea  test    ecx, 60000h
0x14010caf0  jz      short loc_14010CB24
0x14010caf2  btr     ecx, 11h
0x14010caf6  mov     [rdx-44h], ecx
0x14010caf9  bt      ecx, 12h
0x14010cafd  jnb     short loc_14010CB24
0x14010caff  mov     rax, [rdx-18h]
0x14010cb03  test    rax, rax
0x14010cb06  jz      short loc_14010CB24
0x14010cb08  mov     rax, [rax+8]
0x14010cb0c  test    rax, rax
0x14010cb0f  jz      short loc_14010CB24
0x14010cb11  test    dword ptr [rax+0B0h], 400h
0x14010cb1b  jnz     short loc_14010CB24
0x14010cb1d  btr     ecx, 12h
0x14010cb21  mov     [rdx-44h], ecx
0x14010cb24  mov     rdx, [rdx]
0x14010cb27  jmp     short loc_14010CADE
0x14010cb29  mov     rcx, [rsi+22D0h]; FastMutex
0x14010cb30  call    cs:__imp_ExAcquireFastMutex
0x14010cb37  nop     dword ptr [rax+rax+00h]
0x14010cb3c  mov     rax, [rsi+22D8h]
0x14010cb43  mov     [rsp+368h+var_300], rax
0x14010cb48  mov     rcx, [rsi+22D0h]; FastMutex
0x14010cb4f  call    cs:__imp_ExReleaseFastMutex
0x14010cb56  nop     dword ptr [rax+rax+00h]
0x14010cb5b  lea     rax, [rsp+368h+var_300]
0x14010cb60  mov     [rsp+368h+var_340], rax
0x14010cb65  mov     dword ptr [rsp+368h+Timeout], 2
0x14010cb6d  mov     r9d, 4
0x14010cb73  lea     r8d, [r9+0Ch]
0x14010cb77  mov     rdx, rdi
0x14010cb7a  lea     rcx, [rsp+368h+var_2C8]
0x14010cb82  call    TxfActOnAllStreamsForTransaction
0x14010cb87  mov     ebx, eax
0x14010cb89  mov     [rsp+368h+var_334], eax
0x14010cb8d  mov     [rsp+368h+var_337], 1
0x14010cb92  test    eax, eax
0x14010cb94  jz      loc_14010CC68
0x14010cb9a  cmp     eax, 0FFFFFFE2h
0x14010cb9d  jnz     short loc_14010CBF4
0x14010cb9f  mov     byte ptr [rsp+368h+Timeout], 1
0x14010cba4  xor     r9d, r9d
0x14010cba7  xor     edx, edx
0x14010cba9  lea     r8d, [rax+23h]
0x14010cbad  mov     rcx, [rsp+368h+var_238]
0x14010cbb5  call    TxfSearchAddTxfFcbCleanupList
0x14010cbba  bts     dword ptr [rax+10h], 9
0x14010cbbf  mov     rcx, [rsp+368h+var_238]
0x14010cbc7  or      dword ptr [rcx+1B4h], 20h
0x14010cbce  mov     rcx, [rdi+0D0h]
0x14010cbd5  mov     [rax+20h], rcx
0x14010cbd9  lock inc dword ptr [rcx+40h]
0x14010cbdd  mov     rax, [rax+20h]
0x14010cbe1  lock inc dword ptr [rax+30h]
0x14010cbe5  mov     al, cs:NtfsStatusDebugFlags
0x14010cbeb  mov     ebx, 0C00000D8h
0x14010cbf0  mov     [rsp+368h+var_334], ebx
0x14010cbf4  mov     al, cs:NtfsStatusDebugFlags
0x14010cbfa  test    al, al
0x14010cbfc  jz      short loc_14010CC5A
0x14010cbfe  test    ebx, ebx
0x14010cc00  jz      short loc_14010CC5A
0x14010cc02  cmp     ebx, 126h
0x14010cc08  jz      short loc_14010CC5A
0x14010cc0a  lea     eax, [rbx-12Ah]
0x14010cc10  cmp     eax, 1
0x14010cc13  jbe     short loc_14010CC5A
0x14010cc15  cmp     ebx, 0FFFFFFEDh
0x14010cc18  jnb     short loc_14010CC5A
0x14010cc1a  cmp     ebx, 0C00000D8h
0x14010cc20  jz      short loc_14010CC5A
0x14010cc22  cmp     ebx, 0C0000016h
0x14010cc28  jz      short loc_14010CC5A
0x14010cc2a  cmp     ebx, 0C0000011h
0x14010cc30  jz      short loc_14010CC5A
0x14010cc32  lea     eax, [rbx+7FFFFFFBh]
0x14010cc38  cmp     eax, 1
0x14010cc3b  jbe     short loc_14010CC5A
0x14010cc3d  cmp     ebx, 103h
0x14010cc43  jz      short loc_14010CC5A
0x14010cc45  mov     r8d, 3115B2h
0x14010cc4b  mov     edx, ebx
0x14010cc4d  lea     rcx, [rsp+368h+var_2C8]
0x14010cc55  call    NtfsStatusTraceAndDebugInternal
0x14010cc5a  mov     ecx, ebx; Status
0x14010cc5c  call    cs:__imp_ExRaiseStatus
0x14010cc68  mov     rax, [r14]
0x14010cc6b  mov     qword ptr [rsp+368h+plsn1], rax
0x14010cc70  lea     rdx, [rsp+368h+plsn2]; plsn2
0x14010cc75  lea     rcx, [rsp+368h+plsn1]; plsn1
0x14010cc7a  call    cs:__imp_ClfsLsnGreater
0x14010cc81  nop     dword ptr [rax+rax+00h]
0x14010cc86  test    al, al
0x14010cc88  jz      loc_14010CA6F
0x14010cc8e  mov     [rsp+368h+var_338], 1
0x14010cc93  lea     r8, [rsp+368h+plsn1]
0x14010cc98  mov     rdx, rdi; int
0x14010cc9b  lea     rcx, [rsp+368h+var_2C8]; int
0x14010cca3  call    TxfTransDoNextUndo
0x14010cca8  mov     ebx, eax
0x14010ccaa  mov     [rsp+368h+var_334], eax
0x14010ccae  test    eax, eax
0x14010ccb0  js      loc_14010CA6F
0x14010ccb6  jmp     short loc_14010CC70
0x14010ccb8  mov     al, cs:NtfsStatusDebugFlags
0x14010ccbe  mov     ebx, 0C000000Dh
0x14010ccc3  test    al, al
0x14010ccc5  jz      loc_14010C993
0x14010cccb  mov     r8d, 31151Ch
0x14010ccd1  jmp     loc_14010C98A
0x14010ccd6  mov     r14b, [rsp+368h+var_338]
0x14010ccdb  cmp     qword ptr [rdi+0E0h], 0
0x14010cce3  jz      short loc_14010CD29
0x14010cce5  lea     rcx, [rsp+368h+var_2C8]
0x14010cced  call    NtfsPurgeFileRecordCache
0x14010ccf2  bts     [rsp+368h+var_2C4], 9
  ... truncated ...
```

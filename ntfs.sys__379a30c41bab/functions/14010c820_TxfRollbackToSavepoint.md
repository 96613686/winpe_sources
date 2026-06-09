# TxfRollbackToSavepoint

- ea: `0x14010c820`
- end: `0x14010cf10`
- name: `TxfRollbackToSavepoint`
- size: `1776`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400fde4c`

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
- `0x1400592c0`
- `0x140059740`
- `0x1400b62e4`
- `0x14010c820`
- `0x140140fac`
- `0x140188d34`
- `0x14018dc9c`
- `0x1401d8390`
- `0x1401d978c`
- `0x1401da980`
- `0x1401dc59c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14010cd97`
- `ntoskrnl!KeSetEvent` at `0x1402c5ee0`
- `ntoskrnl!KeSetEvent` at `0x14010cd97`
- `ntoskrnl!KeSetEvent` at `0x1402c5ee0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14010ce3b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c5f79`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14010ce3b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c5f79`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c8ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010c8ee`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010cafa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010cafa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010cb18`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010cb18`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010cb80`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010cb80`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010cb9f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010cb9f`
- `ntoskrnl!ExRaiseStatus` at `0x14010ccac`
- `ntoskrnl!ExRaiseStatus` at `0x14010ccac`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14010cdd5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1402c5f1b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14010cdd5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1402c5f1b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010ca9b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010ccca`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010cdf5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1402c5f33`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010ca9b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010ccca`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14010cdf5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1402c5f33`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x14010cd52`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1402c5e90`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x14010cd52`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1402c5e90`

## string_xrefs

- `0x14010cad2`: `TxfRollbackToSavepoint`

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
0x14010c820  mov     [rsp+arg_8], rbx
0x14010c825  mov     [rsp+arg_10], rsi
0x14010c82a  push    rdi
0x14010c82b  push    r12
0x14010c82d  push    r13
0x14010c82f  push    r14
0x14010c831  push    r15
0x14010c833  sub     rsp, 340h
0x14010c83a  mov     rax, cs:__security_cookie
0x14010c841  xor     rax, rsp
0x14010c844  mov     [rsp+368h+var_38], rax
0x14010c84c  mov     r13d, edx
0x14010c84f  mov     rdi, rcx
0x14010c852  mov     [rsp+368h+var_310], rcx
0x14010c857  xor     eax, eax
0x14010c859  mov     ebx, eax
0x14010c85b  mov     [rsp+368h+var_335], al
0x14010c85f  mov     [rsp+368h+var_337], al
0x14010c863  mov     r12b, al
0x14010c866  mov     [rsp+368h+var_336], al
0x14010c86a  mov     r14b, al
0x14010c86d  mov     [rsp+368h+var_338], al
0x14010c871  mov     qword ptr [rsp+368h+plsn1], rax
0x14010c876  mov     qword ptr [rsp+368h+plsn2], rax
0x14010c87b  mov     rsi, [rcx+0D0h]
0x14010c882  mov     [rsp+368h+var_328], rsi
0x14010c887  mov     r15d, eax
0x14010c88a  mov     [rsp+368h+var_2F8], rax
0x14010c88f  mov     [rsp+368h+var_300], rax
0x14010c894  xor     edx, edx; Val
0x14010c896  mov     r8d, 290h; Size
0x14010c89c  lea     rcx, [rsp+368h+var_2C8]; void *
0x14010c8a4  call    memset
0x14010c8a9  lea     rax, [rsp+368h+var_2C8]
0x14010c8b1  mov     [rsp+368h+var_320], rax
0x14010c8b6  xorps   xmm0, xmm0
0x14010c8b9  xor     eax, eax
0x14010c8bb  movups  [rsp+368h+var_2F0], xmm0
0x14010c8c0  movups  [rsp+368h+var_2E0], xmm0
0x14010c8c8  mov     [rsp+368h+var_2D0], rax
0x14010c8d0  jmp     short loc_14010C8FA
0x14010c8d2  lock dec dword ptr [rsi+0E8h]
0x14010c8d9  mov     rcx, [rsi+18h]
0x14010c8dd  add     rcx, 48h ; 'H'; Object
0x14010c8e1  mov     [rsp+368h+Timeout], rbx; Timeout
0x14010c8e6  xor     r9d, r9d; Alertable
0x14010c8e9  xor     r8d, r8d; WaitMode
0x14010c8ec  xor     edx, edx; WaitReason
0x14010c8ee  call    cs:__imp_KeWaitForSingleObject
0x14010c8f5  nop     dword ptr [rax+rax+00h]
0x14010c8fa  mov     eax, 1
0x14010c8ff  lock xadd [rsi+0E8h], eax
0x14010c907  inc     eax
0x14010c909  cmp     eax, 0Ah
0x14010c90c  jg      short loc_14010C8D2
0x14010c90e  lea     rax, [rsp+368h+var_2C8]
0x14010c916  mov     [rsp+368h+var_308], rax
0x14010c91b  xor     edx, edx; Val
0x14010c91d  mov     r8d, 290h; Size
0x14010c923  lea     rcx, [rsp+368h+var_2C8]; void *
0x14010c92b  call    memset
0x14010c930  lea     r9, [rsp+368h+var_308]
0x14010c935  xor     r8d, r8d
0x14010c938  mov     dl, 1
0x14010c93a  xor     ecx, ecx; Irp
0x14010c93c  call    NtfsInitializeIrpContextInternal
0x14010c941  test    eax, eax
0x14010c943  jnz     short loc_14010C953
0x14010c945  mov     rax, [rsp+368h+var_308]
0x14010c94a  mov     ecx, 290h
0x14010c94f  mov     [rax+2], cx
0x14010c953  mov     r8, [rsi+10h]
0x14010c957  mov     edx, 3
0x14010c95c  lea     rcx, [rsp+368h+var_2F0]
0x14010c961  call    NtfsInitializeTopLevelIrp
0x14010c966  mov     rdx, rax
0x14010c969  lea     rcx, [rsp+368h+var_2C8]
0x14010c971  call    NtfsUpdateIrpContextWithTopLevel
0x14010c976  or      [rsp+368h+var_2BC], 10001h
0x14010c981  mov     rdx, [rsi+10h]
0x14010c985  lea     rcx, [rsp+368h+var_2C8]
0x14010c98d  call    NtfsSetIrpContextVcb
0x14010c992  mov     eax, [rsp+368h+var_114]
0x14010c999  or      eax, 80008h
0x14010c99e  mov     [rsp+368h+var_114], eax
0x14010c9a5  or      eax, 40h
0x14010c9a8  mov     [rsp+368h+var_114], eax
0x14010c9af  xor     edx, edx
0x14010c9b1  mov     rcx, rdi
0x14010c9b4  call    TxfTransFreeze
0x14010c9b9  mov     [rsp+368h+var_335], 1
0x14010c9be  mov     eax, [rdi+10h]
0x14010c9c1  test    al, al
0x14010c9c3  jns     short loc_14010C9EC
0x14010c9c5  mov     al, cs:NtfsStatusDebugFlags
0x14010c9cb  mov     ebx, 0C0000189h
0x14010c9d0  test    al, al
0x14010c9d2  jz      short loc_14010C9E3
0x14010c9d4  mov     r8d, 311510h
0x14010c9da  mov     edx, ebx
0x14010c9dc  xor     ecx, ecx
0x14010c9de  call    NtfsStatusTraceAndDebugInternal
0x14010c9e3  mov     [rsp+368h+var_334], ebx
0x14010c9e7  jmp     loc_14010CD2B
0x14010c9ec  cmp     r13d, [rdi+160h]
0x14010c9f3  ja      loc_14010CD08
0x14010c9f9  cmp     r13d, 1
0x14010c9fd  jb      loc_14010CD08
0x14010ca03  cmp     dword ptr [rdi+1C0h], 0
0x14010ca0a  jz      short loc_14010CA23
0x14010ca0c  mov     al, cs:NtfsStatusDebugFlags
0x14010ca12  mov     ebx, 0C0190048h
0x14010ca17  test    al, al
0x14010ca19  jz      short loc_14010C9E3
0x14010ca1b  mov     r8d, 311526h
0x14010ca21  jmp     short loc_14010C9DA
0x14010ca23  lea     rcx, [rdi+140h]
0x14010ca2a  mov     rax, [rcx]
0x14010ca2d  xor     dl, dl
0x14010ca2f  cmp     rax, rcx
0x14010ca32  jz      short loc_14010CA60
0x14010ca34  lea     r15, [rax-20h]
0x14010ca38  mov     [rsp+368h+var_2F8], r15
0x14010ca3d  cmp     [r15+4], r13d
0x14010ca41  ja      short loc_14010CA82
0x14010ca43  mov     dl, 1
0x14010ca45  mov     rax, [r15+8]
0x14010ca49  mov     qword ptr [rsp+368h+plsn2], rax
0x14010ca4e  cmp     [r15+4], r13d
0x14010ca52  jnb     short loc_14010CA60
0x14010ca54  mov     r12b, dl
0x14010ca57  mov     [rsp+368h+var_336], dl
0x14010ca5b  or      dword ptr [r15+18h], 3
0x14010ca60  test    dl, dl
0x14010ca62  jnz     short loc_14010CA87
0x14010ca64  mov     al, cs:NtfsStatusDebugFlags
0x14010ca6a  mov     ebx, 0C000000Dh
0x14010ca6f  test    al, al
0x14010ca71  jz      loc_14010C9E3
0x14010ca77  mov     r8d, 311554h
0x14010ca7d  jmp     loc_14010C9DA
0x14010ca82  mov     rax, [rax]
0x14010ca85  jmp     short loc_14010CA2F
0x14010ca87  lock or dword ptr [rdi+10h], 400h
0x14010ca8f  lea     r14, [rdi+30h]
0x14010ca93  lea     rdx, [rsp+368h+plsn2]; plsn2
0x14010ca98  mov     rcx, r14; plsn1
0x14010ca9b  call    cs:__imp_ClfsLsnGreater
0x14010caa2  nop     dword ptr [rax+rax+00h]
0x14010caa7  test    al, al
0x14010caa9  jnz     loc_14010CB79
0x14010caaf  mov     rax, [r14]
0x14010cab2  mov     qword ptr [rsp+368h+plsn1], rax
0x14010cab7  mov     rcx, rdi
0x14010caba  call    ProcessSavepointListForCurrentLogRec
0x14010cabf  test    ebx, ebx
0x14010cac1  jns     short loc_14010CAE3
0x14010cac3  mov     dword ptr [rsp+368h+Timeout], 15DFh
0x14010cacb  lea     r9, aTxftransC; "txftrans.c"
0x14010cad2  lea     r8, aTxfrollbacktos; "TxfRollbackToSavepoint"
0x14010cad9  mov     edx, ebx
0x14010cadb  mov     rcx, rdi
0x14010cade  call    TxfSetupForDeferredAbortPriv
0x14010cae3  test    r12b, r12b
0x14010cae6  jz      short loc_14010CAF0
0x14010cae8  mov     rax, [rdi+28h]
0x14010caec  mov     [r15+8], rax
0x14010caf0  mov     rcx, [rdi+18h]
0x14010caf4  add     rcx, 50h ; 'P'; Resource
0x14010caf8  mov     dl, 1; Wait
0x14010cafa  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14010cb01  nop     dword ptr [rax+rax+00h]
0x14010cb06  lea     eax, [r13-1]
0x14010cb0a  mov     [rdi+160h], eax
0x14010cb10  mov     rcx, [rdi+18h]
0x14010cb14  add     rcx, 50h ; 'P'; Resource
0x14010cb18  call    cs:__imp_ExReleaseResourceLite
0x14010cb1f  nop     dword ptr [rax+rax+00h]
0x14010cb24  lea     r8, [rdi+0C0h]
0x14010cb2b  mov     rdx, [r8]
0x14010cb2e  cmp     rdx, r8
0x14010cb31  jz      loc_14010CD26
0x14010cb37  mov     ecx, [rdx-44h]
0x14010cb3a  test    ecx, 60000h
0x14010cb40  jz      short loc_14010CB74
0x14010cb42  btr     ecx, 11h
0x14010cb46  mov     [rdx-44h], ecx
0x14010cb49  bt      ecx, 12h
0x14010cb4d  jnb     short loc_14010CB74
0x14010cb4f  mov     rax, [rdx-18h]
0x14010cb53  test    rax, rax
0x14010cb56  jz      short loc_14010CB74
0x14010cb58  mov     rax, [rax+8]
0x14010cb5c  test    rax, rax
0x14010cb5f  jz      short loc_14010CB74
0x14010cb61  test    dword ptr [rax+0B0h], 400h
0x14010cb6b  jnz     short loc_14010CB74
0x14010cb6d  btr     ecx, 12h
0x14010cb71  mov     [rdx-44h], ecx
0x14010cb74  mov     rdx, [rdx]
0x14010cb77  jmp     short loc_14010CB2E
0x14010cb79  mov     rcx, [rsi+22D0h]; FastMutex
0x14010cb80  call    cs:__imp_ExAcquireFastMutex
0x14010cb87  nop     dword ptr [rax+rax+00h]
0x14010cb8c  mov     rax, [rsi+22D8h]
0x14010cb93  mov     [rsp+368h+var_300], rax
0x14010cb98  mov     rcx, [rsi+22D0h]; FastMutex
0x14010cb9f  call    cs:__imp_ExReleaseFastMutex
0x14010cba6  nop     dword ptr [rax+rax+00h]
0x14010cbab  lea     rax, [rsp+368h+var_300]
0x14010cbb0  mov     [rsp+368h+var_340], rax
0x14010cbb5  mov     dword ptr [rsp+368h+Timeout], 2
0x14010cbbd  mov     r9d, 4
0x14010cbc3  lea     r8d, [r9+0Ch]
0x14010cbc7  mov     rdx, rdi
0x14010cbca  lea     rcx, [rsp+368h+var_2C8]
0x14010cbd2  call    TxfActOnAllStreamsForTransaction
0x14010cbd7  mov     ebx, eax
0x14010cbd9  mov     [rsp+368h+var_334], eax
0x14010cbdd  mov     [rsp+368h+var_337], 1
0x14010cbe2  test    eax, eax
0x14010cbe4  jz      loc_14010CCB8
0x14010cbea  cmp     eax, 0FFFFFFE2h
0x14010cbed  jnz     short loc_14010CC44
0x14010cbef  mov     byte ptr [rsp+368h+Timeout], 1
0x14010cbf4  xor     r9d, r9d
0x14010cbf7  xor     edx, edx
0x14010cbf9  lea     r8d, [rax+23h]
0x14010cbfd  mov     rcx, [rsp+368h+var_238]
0x14010cc05  call    TxfSearchAddTxfFcbCleanupList
0x14010cc0a  bts     dword ptr [rax+10h], 9
0x14010cc0f  mov     rcx, [rsp+368h+var_238]
0x14010cc17  or      dword ptr [rcx+1B4h], 20h
0x14010cc1e  mov     rcx, [rdi+0D0h]
0x14010cc25  mov     [rax+20h], rcx
0x14010cc29  lock inc dword ptr [rcx+40h]
0x14010cc2d  mov     rax, [rax+20h]
0x14010cc31  lock inc dword ptr [rax+30h]
0x14010cc35  mov     al, cs:NtfsStatusDebugFlags
0x14010cc3b  mov     ebx, 0C00000D8h
0x14010cc40  mov     [rsp+368h+var_334], ebx
0x14010cc44  mov     al, cs:NtfsStatusDebugFlags
0x14010cc4a  test    al, al
0x14010cc4c  jz      short loc_14010CCAA
0x14010cc4e  test    ebx, ebx
0x14010cc50  jz      short loc_14010CCAA
0x14010cc52  cmp     ebx, 126h
0x14010cc58  jz      short loc_14010CCAA
0x14010cc5a  lea     eax, [rbx-12Ah]
0x14010cc60  cmp     eax, 1
0x14010cc63  jbe     short loc_14010CCAA
0x14010cc65  cmp     ebx, 0FFFFFFEDh
0x14010cc68  jnb     short loc_14010CCAA
0x14010cc6a  cmp     ebx, 0C00000D8h
0x14010cc70  jz      short loc_14010CCAA
0x14010cc72  cmp     ebx, 0C0000016h
0x14010cc78  jz      short loc_14010CCAA
0x14010cc7a  cmp     ebx, 0C0000011h
0x14010cc80  jz      short loc_14010CCAA
0x14010cc82  lea     eax, [rbx+7FFFFFFBh]
0x14010cc88  cmp     eax, 1
0x14010cc8b  jbe     short loc_14010CCAA
0x14010cc8d  cmp     ebx, 103h
0x14010cc93  jz      short loc_14010CCAA
0x14010cc95  mov     r8d, 3115B2h
0x14010cc9b  mov     edx, ebx
0x14010cc9d  lea     rcx, [rsp+368h+var_2C8]
0x14010cca5  call    NtfsStatusTraceAndDebugInternal
0x14010ccaa  mov     ecx, ebx; Status
0x14010ccac  call    cs:__imp_ExRaiseStatus
0x14010ccb8  mov     rax, [r14]
0x14010ccbb  mov     qword ptr [rsp+368h+plsn1], rax
0x14010ccc0  lea     rdx, [rsp+368h+plsn2]; plsn2
0x14010ccc5  lea     rcx, [rsp+368h+plsn1]; plsn1
0x14010ccca  call    cs:__imp_ClfsLsnGreater
0x14010ccd1  nop     dword ptr [rax+rax+00h]
0x14010ccd6  test    al, al
0x14010ccd8  jz      loc_14010CABF
0x14010ccde  mov     [rsp+368h+var_338], 1
0x14010cce3  lea     r8, [rsp+368h+plsn1]
0x14010cce8  mov     rdx, rdi; int
0x14010cceb  lea     rcx, [rsp+368h+var_2C8]; int
0x14010ccf3  call    TxfTransDoNextUndo
0x14010ccf8  mov     ebx, eax
0x14010ccfa  mov     [rsp+368h+var_334], eax
0x14010ccfe  test    eax, eax
0x14010cd00  js      loc_14010CABF
0x14010cd06  jmp     short loc_14010CCC0
0x14010cd08  mov     al, cs:NtfsStatusDebugFlags
0x14010cd0e  mov     ebx, 0C000000Dh
0x14010cd13  test    al, al
0x14010cd15  jz      loc_14010C9E3
0x14010cd1b  mov     r8d, 31151Ch
0x14010cd21  jmp     loc_14010C9DA
0x14010cd26  mov     r14b, [rsp+368h+var_338]
0x14010cd2b  cmp     qword ptr [rdi+0E0h], 0
0x14010cd33  jz      short loc_14010CD79
0x14010cd35  lea     rcx, [rsp+368h+var_2C8]
0x14010cd3d  call    NtfsPurgeFileRecordCache
0x14010cd42  bts     [rsp+368h+var_2C4], 9
  ... truncated ...
```

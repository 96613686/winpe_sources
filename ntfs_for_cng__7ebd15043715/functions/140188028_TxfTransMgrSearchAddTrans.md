# TxfTransMgrSearchAddTrans

- ea: `0x140188028`
- end: `0x140188b6a`
- name: `TxfTransMgrSearchAddTrans`
- size: `2882`
- prototype: `__int64 __fastcall(__int64, _OWORD *, struct _KTRANSACTION *, char, __int64, __int64 *)`
- caller_count: `14`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140017480`
- `0x1400ffd34`
- `0x140130b40`
- `0x14017db20`
- `0x140185c00`
- `0x1401879b0`
- `0x140187da0`
- `0x1401891f4`
- `0x14018a06c`
- `0x140193f30`
- `0x1401d5ad0`
- `0x1401d6948`
- `0x1401d97f0`
- `0x14020a62c`

## callees

- `0x140007ea0`
- `0x140033030`
- `0x14004088c`
- `0x140188028`
- `0x140188ce4`
- `0x14018dc4c`
- `0x140196e30`
- `0x1401da930`
- `0x1401db344`
- `0x14026f3d0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140188abf`
- `ntoskrnl!KeSetEvent` at `0x140188abf`
- `ntoskrnl!TmIsTransactionActive` at `0x1401881b8`
- `ntoskrnl!TmIsTransactionActive` at `0x140188a24`
- `ntoskrnl!TmIsTransactionActive` at `0x1401881b8`
- `ntoskrnl!TmIsTransactionActive` at `0x140188a24`
- `ntoskrnl!ObfReferenceObject` at `0x14018833e`
- `ntoskrnl!ObfReferenceObject` at `0x14018866b`
- `ntoskrnl!ObfReferenceObject` at `0x14018833e`
- `ntoskrnl!ObfReferenceObject` at `0x14018866b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14018883e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14018883e`
- `ntoskrnl!TmGetTransactionId` at `0x140188657`
- `ntoskrnl!TmGetTransactionId` at `0x140188657`
- `ntoskrnl!TmCreateEnlistment` at `0x140188438`
- `ntoskrnl!TmCreateEnlistment` at `0x140188438`
- `ntoskrnl!TmEnlistmentObjectType` at `0x14018882e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018821b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140188380`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140188454`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140188b43`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018821b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140188380`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140188454`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140188b43`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188281`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188399`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401883bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401884b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018888a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188af6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188b5c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aace2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aad04`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188281`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188399`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401883bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401884b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018888a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188af6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188b5c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aace2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aad04`
- `ntoskrnl!RtlCompareMemory` at `0x140188511`
- `ntoskrnl!RtlCompareMemory` at `0x140188511`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401880aa`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401880aa`
- `ntoskrnl!ExRaiseStatus` at `0x140188359`
- `ntoskrnl!ExRaiseStatus` at `0x140188359`

## pseudocode

```c
__int64 __fastcall TxfTransMgrSearchAddTrans(
        __int64 a1,
        _OWORD *a2,
        struct _KTRANSACTION *a3,
        char a4,
        __int64 a5,
        __int64 *a6)
{
  const void *v8; // r9
  signed int TransactionRequest; // esi
  __int64 EnlistmentKey; // rdi
  __int64 v12; // r12
  struct _ERESOURCE *v13; // rcx
  char v14; // r12
  __int64 v15; // r14
  int v16; // r14d
  char v17; // dl
  __int64 v18; // rdx
  __int64 v19; // rdi
  __int64 v20; // rdx
  struct _KEVENT *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  unsigned int v25; // r8d
  __int64 v27; // [rsp+58h] [rbp-80h] BYREF
  _QWORD v28[2]; // [rsp+60h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-68h] BYREF
  char v30; // [rsp+E0h] [rbp+8h] BYREF
  _OWORD *v31; // [rsp+E8h] [rbp+10h]
  char v32; // [rsp+F8h] [rbp+20h] BYREF

  v31 = a2;
  v8 = a2;
  TransactionRequest = 0;
  EnlistmentKey = 0;
  v27 = 0;
  v30 = 0;
  v32 = 0;
  memset(&ObjectAttributes, 0, 44);
  v12 = a1 + 144;
  v28[1] = a1 + 144;
  *a6 = 0;
  do
  {
    if ( !v30 )
    {
      v13 = *(struct _ERESOURCE **)(v12 + 16);
      if ( (a4 & 2) != 0 )
        ExAcquireResourceExclusiveLite(v13, 1u);
      else
        ExAcquireResourceSharedLite(v13, 1u);
      v30 = 1;
      v8 = v31;
    }
    if ( (a4 & 0xC) != 0
      || _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 1
      || _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 2 )
    {
      if ( (*(_DWORD *)(a1 + 136) & 0x1000) != 0
        && _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 2
        && (a4 & 4) == 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC01A002C, 0x310964u);
        TransactionRequest = -1072037844;
        goto LABEL_137;
      }
      if ( (*(_DWORD *)(a1 + 136) & 0xA00000) != 0
        && _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 2
        && (a4 & 4) == 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x310974u);
        TransactionRequest = -1073741670;
        goto LABEL_137;
      }
      v14 = 0;
      if ( a3 || v8 || (a4 & 8) == 0 )
      {
        EnlistmentKey = *(_QWORD *)(a1 + 152);
        v27 = EnlistmentKey;
        while ( 1 )
        {
          v15 = EnlistmentKey;
          if ( !EnlistmentKey )
            break;
          if ( ((*(_DWORD *)(EnlistmentKey + 16) & 0x2000) == 0 || (a4 & 0x40) != 0)
            && (a3 && *(struct _KTRANSACTION **)(EnlistmentKey + 232) == a3
             || v8 && RtlCompareMemory(v8, (const void *)(EnlistmentKey + 256), 0x10u) == 16) )
          {
            goto LABEL_30;
          }
          EnlistmentKey = *(_QWORD *)(EnlistmentKey + 104);
          v27 = *(_QWORD *)(v15 + 104);
          v8 = v31;
        }
      }
      else if ( *(_QWORD *)(a1 + 696) )
      {
        EnlistmentKey = *(_QWORD *)(a1 + 696);
        v27 = EnlistmentKey;
        v14 = 1;
      }
      if ( v14 )
      {
LABEL_30:
        ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(EnlistmentKey + 24) + 80LL), 1u);
        v32 = 1;
        if ( (*(_DWORD *)(EnlistmentKey + 16) & 0x20000) != 0 )
        {
          v12 = a1 + 144;
          TransactionRequest = TxfWaitForEnlistmentCompletion(a5, EnlistmentKey, &v32, a1 + 144, &v30);
          EnlistmentKey = 0;
          v27 = 0;
          if ( TransactionRequest >= 0 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC000022D, 0x3109ECu);
            TransactionRequest = -1073741267;
          }
          goto LABEL_137;
        }
        v16 = a4 & 1;
        v17 = (a4 & 1) != 0 || (a4 & 4) != 0;
        TransactionRequest = TxfGetTransactionRequest(EnlistmentKey, v17, (a4 & 0x10) != 0);
        if ( TransactionRequest >= 0 )
          *a6 = EnlistmentKey;
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(EnlistmentKey + 24) + 80LL));
        v32 = 0;
      }
      else
      {
        if ( (a4 & 2) == 0 )
        {
          if ( !a3 || TmIsTransactionActive(a3) )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC0190061, 0x310A20u);
            TransactionRequest = -1072103327;
            goto LABEL_27;
          }
          if ( !NtfsStatusDebugFlags )
            goto LABEL_26;
          v25 = 3213852;
          goto LABEL_89;
        }
        if ( (a4 & 8) == 0 && (a4 & 1) == 0 && !TmIsTransactionActive(a3) )
        {
          if ( !NtfsStatusDebugFlags )
          {
LABEL_26:
            TransactionRequest = -1072103421;
LABEL_27:
            v12 = a1 + 144;
            goto LABEL_137;
          }
          v25 = 3213886;
LABEL_89:
          NtfsStatusTraceAndDebugInternal(0, 0xC0190003, v25);
          goto LABEL_26;
        }
        v16 = a4 & 1;
        if ( (a4 & 1) == 0 )
        {
          if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) != 2 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC0190005, 0x310A4Bu);
            TransactionRequest = -1072103419;
            v12 = a1 + 144;
            goto LABEL_137;
          }
          v16 = 0;
        }
      }
      if ( (a4 & 0x20) != 0 && (!EnlistmentKey || !*(_QWORD *)(EnlistmentKey + 240)) && a3 && a5 )
      {
        v19 = TxfSearchAddTxfFcbCleanupList(*(_QWORD *)(a5 + 144), 0, 5, 0, 1);
        *(_DWORD *)(v19 + 16) |= 0x10000u;
        if ( *a6 )
        {
          *a6 = 0;
          if ( (a4 & 0x10) != 0 )
          {
            LOBYTE(v18) = 1;
            TxfDereferenceTransaction(&v27, v18);
          }
        }
        *(_QWORD *)(v19 + 24) = 0;
        *(_QWORD *)(v19 + 32) = a1;
        _InterlockedAdd((volatile signed __int32 *)(a1 + 64), 1u);
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v19 + 32) + 48LL), 1u);
        ObfReferenceObject(a3);
        *(_QWORD *)(v19 + 40) = a3;
        ExRaiseStatus(-1073741608);
      }
      if ( EnlistmentKey )
      {
        v12 = a1 + 144;
      }
      else
      {
        EnlistmentKey = TxfTransAllocate();
        v27 = EnlistmentKey;
        *a6 = EnlistmentKey;
        if ( v16 )
          _InterlockedOr((volatile signed __int32 *)(EnlistmentKey + 16), 0x62u);
        if ( v31 )
          *(_OWORD *)(EnlistmentKey + 256) = *v31;
        else
          TmGetTransactionId(a3, (PUOW)(EnlistmentKey + 256));
        if ( a3 )
        {
          ObfReferenceObject(a3);
          *(_QWORD *)(EnlistmentKey + 232) = a3;
        }
        _InterlockedOr((volatile signed __int32 *)(EnlistmentKey + 16), 0x2000000u);
        if ( a1 != *(_QWORD *)(*(_QWORD *)(a1 + 16) + 6248LL) && (*(_DWORD *)(a1 + 128) & 0x10) != 0 )
          _InterlockedOr((volatile signed __int32 *)(EnlistmentKey + 16), 0x1000000u);
        v12 = a1 + 144;
        *(_QWORD *)(EnlistmentKey + 304) = _InterlockedIncrement64((volatile signed __int64 *)(a1 + 224));
        _InterlockedAdd((volatile signed __int32 *)(a1 + 64), 1u);
        _InterlockedAdd((volatile signed __int32 *)(a1 + 40), 1u);
        v23 = *(_QWORD *)(EnlistmentKey + 208);
        if ( v23 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v23 + 40));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(EnlistmentKey + 208) + 64LL), 0xFFFFFFFF) == 1 )
            TxfDeleteTxfRmcb(*(PVOID *)(EnlistmentKey + 208));
        }
        *(_QWORD *)(EnlistmentKey + 208) = a1;
        *(_WORD *)(EnlistmentKey + 8) = 1;
        *(_DWORD *)(EnlistmentKey + 4) = 1;
        if ( v16 )
          *(_DWORD *)(EnlistmentKey + 4) = 2;
        *(_QWORD *)(EnlistmentKey + 40) = CLFS_LSN_NULL_EXT;
        *(_QWORD *)(EnlistmentKey + 48) = CLFS_LSN_NULL_EXT;
        *(_QWORD *)(EnlistmentKey + 32) = CLFS_LSN_NULL_EXT;
        *(_QWORD *)(EnlistmentKey + 64) = CLFS_LSN_NULL_EXT;
        *(_QWORD *)(EnlistmentKey + 296) = CLFS_LSN_NULL_EXT;
        *(_QWORD *)(EnlistmentKey + 384) = CLFS_LSN_NULL_EXT;
        *(_QWORD *)(EnlistmentKey + 72) = CLFS_LSN_NULL_EXT;
        *(_QWORD *)(EnlistmentKey + 184) = EnlistmentKey + 176;
        *(_QWORD *)(EnlistmentKey + 176) = EnlistmentKey + 176;
        *(_QWORD *)(EnlistmentKey + 328) = EnlistmentKey + 320;
        *(_QWORD *)(EnlistmentKey + 320) = EnlistmentKey + 320;
        if ( (*(_DWORD *)(a1 + 136) & 0x400000) != 0 )
        {
          TxfTransFreeze(EnlistmentKey, 68);
          _InterlockedOr((volatile signed __int32 *)(EnlistmentKey + 16), 0x10000000u);
        }
        v24 = *(_QWORD *)(a1 + 152);
        if ( v24 )
        {
          *(_QWORD *)(EnlistmentKey + 104) = v24;
          *(_QWORD *)(*(_QWORD *)(a1 + 152) + 112LL) = EnlistmentKey;
        }
        *(_QWORD *)(a1 + 152) = EnlistmentKey;
      }
      if ( (a4 & 0x20) != 0 && !*(_QWORD *)(EnlistmentKey + 240) )
      {
        ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(EnlistmentKey + 24) + 80LL), 1u);
        v32 = 1;
        ExReleaseResourceLite(*(PERESOURCE *)(v12 + 16));
        v30 = 0;
        _InterlockedOr((volatile signed __int32 *)(EnlistmentKey + 16), 0x20000u);
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(EnlistmentKey + 24) + 80LL));
        v32 = 0;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 512;
        ObjectAttributes.ObjectName = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        TransactionRequest = TmCreateEnlistment(
                               (PHANDLE)(EnlistmentKey + 248),
                               0,
                               0xF001Fu,
                               &ObjectAttributes,
                               *(PRKRESOURCEMANAGER *)(a1 + 648),
                               a3,
                               0,
                               0x20Eu,
                               (PVOID)EnlistmentKey);
        ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(EnlistmentKey + 24) + 80LL), 1u);
        v32 = 1;
        _InterlockedAnd((volatile signed __int32 *)(EnlistmentKey + 16), 0xFFFDFFFF);
        v21 = *(struct _KEVENT **)(EnlistmentKey + 392);
        if ( v21 )
          KeSetEvent(v21, 0, 0);
        if ( TransactionRequest >= 0 )
        {
          TransactionRequest = ObReferenceObjectByHandle(
                                 *(HANDLE *)(EnlistmentKey + 248),
                                 0,
                                 (POBJECT_TYPE)TmEnlistmentObjectType,
                                 0,
                                 (PVOID *)(EnlistmentKey + 240),
                                 0);
          if ( NtfsStatusDebugFlags
            && TransactionRequest
            && TransactionRequest != 294
            && (unsigned int)(TransactionRequest - 298) > 1
            && (unsigned int)TransactionRequest < 0xFFFFFFED
            && TransactionRequest != -1073741608
            && TransactionRequest != -1073741802
            && TransactionRequest != -1073741807
            && (unsigned int)(TransactionRequest + 2147483643) > 1
            && TransactionRequest != 259 )
          {
            NtfsStatusTraceAndDebugInternal(0, TransactionRequest, 0x310BBDu);
          }
          ++*(_DWORD *)(EnlistmentKey + 4);
          if ( (*(_DWORD *)(EnlistmentKey + 16) & 0x200) != 0 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0x1Du, 0x310BD0u);
            TransactionRequest = 29;
          }
          *(_QWORD *)(EnlistmentKey + 376) = MEMORY[0xFFFFF78000000014];
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(EnlistmentKey + 24) + 80LL));
          v32 = 0;
        }
        else
        {
          if ( NtfsStatusDebugFlags
            && (unsigned int)TransactionRequest < 0xFFFFFFED
            && TransactionRequest != -1073741802
            && TransactionRequest != -1073741807
            && (unsigned int)(TransactionRequest + 2147483643) > 1
            && TransactionRequest != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(0, TransactionRequest, 0x310B8Eu);
          }
          _InterlockedOr((volatile signed __int32 *)(EnlistmentKey + 16), 2u);
          if ( (*(_DWORD *)(EnlistmentKey + 16) & 0x200) != 0 )
          {
            v28[0] = EnlistmentKey;
            LOBYTE(v20) = 1;
            TxfDereferenceTransaction(v28, v20);
          }
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(EnlistmentKey + 24) + 80LL));
          v32 = 0;
          TxfRemoveTransactionFromList(EnlistmentKey);
          *a6 = 0;
          LOBYTE(v22) = 1;
          TxfDereferenceTransaction(&v27, v22);
          EnlistmentKey = v27;
        }
        goto LABEL_27;
      }
    }
    else
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0190005, 0x310957u);
      TransactionRequest = -1072103419;
    }
LABEL_137:
    if ( v30 )
    {
      ExReleaseResourceLite(*(PERESOURCE *)(v12 + 16));
      v30 = 0;
    }
    if ( v32 )
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(EnlistmentKey + 24) + 80LL));
    v8 = v31;
  }
  while ( TransactionRequest == -1073741267 );
  return (unsigned int)TransactionRequest;
}

```

## disassembly

```asm
0x140188028  mov     r11, rsp
0x14018802b  mov     [r11+10h], rdx
0x14018802f  push    rbx
0x140188030  push    rsi
0x140188031  push    rdi
0x140188032  push    r12
0x140188034  push    r13
0x140188036  push    r14
0x140188038  push    r15
0x14018803a  sub     rsp, 0A0h
0x140188041  mov     ebx, r9d
0x140188044  mov     r13, r8
0x140188047  mov     r9, rdx
0x14018804a  mov     r15, rcx
0x14018804d  xor     esi, esi
0x14018804f  xor     edi, edi
0x140188051  mov     [r11-80h], rdi
0x140188055  mov     [r11+8], sil
0x140188059  mov     [r11+20h], sil
0x14018805d  xor     eax, eax
0x14018805f  xorps   xmm0, xmm0
0x140188062  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.Length], xmm0
0x140188067  movups  xmmword ptr [r11-58h], xmm0
0x14018806c  movups  xmmword ptr [r11-4Ch], xmm0
0x140188071  lea     r12, [rcx+90h]
0x140188078  mov     [rsp+0D8h+var_70], r12
0x14018807d  mov     rax, [rsp+0D8h+arg_28]
0x140188085  mov     [rax], rsi
0x140188088  lea     ecx, [rsi+4]
0x14018808b  lea     r14d, [rsi+1]
0x14018808f  cmp     [rsp+0D8h+arg_0], 0
0x140188097  jnz     short loc_1401880CB
0x140188099  mov     rcx, [r12+10h]; Resource
0x14018809e  mov     dl, r14b; Wait
0x1401880a1  test    bl, 2
0x1401880a4  jnz     loc_140188B43
0x1401880aa  call    cs:__imp_ExAcquireResourceSharedLite
0x1401880b1  nop     dword ptr [rax+rax+00h]
0x1401880b6  mov     [rsp+0D8h+arg_0], r14b
0x1401880be  mov     r9, [rsp+0D8h+arg_8]
0x1401880c6  mov     ecx, 4
0x1401880cb  test    bl, 0Ch
0x1401880ce  jnz     short loc_1401880F4
0x1401880d0  mov     eax, ecx
0x1401880d2  lock cmpxchg [r15+84h], ecx
0x1401880db  cmp     eax, r14d
0x1401880de  jz      short loc_1401880F4
0x1401880e0  mov     eax, ecx
0x1401880e2  lock cmpxchg [r15+84h], ecx
0x1401880eb  cmp     eax, 2
0x1401880ee  jnz     loc_140188914
0x1401880f4  test    dword ptr [r15+88h], 1000h
0x1401880ff  jnz     loc_1401889E3
0x140188105  test    dword ptr [r15+88h], 0A00000h
0x140188110  jz      short loc_14018813E
0x140188112  mov     eax, ecx
0x140188114  lock cmpxchg [r15+84h], ecx
0x14018811d  cmp     eax, 2
0x140188120  jnz     short loc_14018813E
0x140188122  test    cl, bl
0x140188124  jnz     short loc_14018813E
0x140188126  mov     al, cs:NtfsStatusDebugFlags
0x14018812c  test    al, al
0x14018812e  jnz     loc_140188940
0x140188134  mov     esi, 0C000009Ah
0x140188139  jmp     loc_140188923
0x14018813e  xor     r12b, r12b
0x140188141  mov     [rsp+0D8h+var_88], r12b
0x140188146  test    r13, r13
0x140188149  jz      loc_14018852C
0x14018814f  mov     rdi, [r15+98h]
0x140188156  mov     [rsp+0D8h+var_80], rdi
0x14018815b  mov     r14, rdi
0x14018815e  mov     rdx, rdi
0x140188161  test    rdx, rdx
0x140188164  jz      short loc_14018818D
0x140188166  test    dword ptr [rdi+10h], 2000h
0x14018816d  setnz   cl
0x140188170  test    bl, 40h
0x140188173  setz    al
0x140188176  test    al, cl
0x140188178  jz      short loc_1401881EF
0x14018817a  mov     rdi, [r14+68h]
0x14018817e  mov     [rsp+0D8h+var_80], rdi
0x140188183  mov     r9, [rsp+0D8h+arg_8]
0x14018818b  jmp     short loc_14018815B
0x14018818d  mov     r14d, 1
0x140188193  test    r12b, r12b
0x140188196  jnz     short loc_140188210
0x140188198  test    bl, 2
0x14018819b  jz      loc_140188A18
0x1401881a1  test    bl, 8
0x1401881a4  setz    cl
0x1401881a7  test    r14b, bl
0x1401881aa  setz    al
0x1401881ad  test    al, cl
0x1401881af  jz      loc_1401885CD
0x1401881b5  mov     rcx, r13; Transaction
0x1401881b8  call    cs:__imp_TmIsTransactionActive
0x1401881bf  nop     dword ptr [rax+rax+00h]
0x1401881c4  test    al, al
0x1401881c6  jnz     loc_1401885CD
0x1401881cc  mov     al, cs:NtfsStatusDebugFlags
0x1401881d2  test    al, al
0x1401881d4  jnz     loc_1401887A0
0x1401881da  mov     esi, 0C0190003h
0x1401881df  mov     [rsp+0D8h+var_84], esi
0x1401881e3  lea     r12, [r15+90h]
0x1401881ea  jmp     loc_140188AE7
0x1401881ef  test    r13, r13
0x1401881f2  jz      loc_1401884F8
0x1401881f8  cmp     [r14+0E8h], r13
0x1401881ff  jnz     loc_1401884F8
0x140188205  mov     r14d, 1
0x14018820b  mov     [rsp+0D8h+var_88], r14b
0x140188210  mov     rcx, [rdi+18h]
0x140188214  add     rcx, 50h ; 'P'; Resource
0x140188218  mov     dl, r14b; Wait
0x14018821b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140188222  nop     dword ptr [rax+rax+00h]
0x140188227  mov     [rsp+0D8h+arg_18], r14b
0x14018822f  test    dword ptr [rdi+10h], 20000h
0x140188236  jnz     loc_140188563
0x14018823c  mov     eax, ebx
0x14018823e  and     eax, 10h
0x140188241  mov     r14d, ebx
0x140188244  mov     r12d, 1
0x14018824a  and     r14d, r12d
0x14018824d  jz      loc_140188A04
0x140188253  mov     dl, r12b
0x140188256  test    eax, eax
0x140188258  setnz   r8b
0x14018825c  mov     rcx, rdi
0x14018825f  call    TxfGetTransactionRequest
0x140188264  mov     esi, eax
0x140188266  mov     [rsp+0D8h+var_84], eax
0x14018826a  test    eax, eax
0x14018826c  js      short loc_140188279
0x14018826e  mov     rax, [rsp+0D8h+arg_28]
0x140188276  mov     [rax], rdi
0x140188279  mov     rcx, [rdi+18h]
0x14018827d  add     rcx, 50h ; 'P'; Resource
0x140188281  call    cs:__imp_ExReleaseResourceLite
0x140188288  nop     dword ptr [rax+rax+00h]
0x14018828d  mov     [rsp+0D8h+arg_18], 0
0x140188295  test    bl, 20h
0x140188298  jnz     short loc_1401882BE
0x14018829a  test    rdi, rdi
0x14018829d  jz      loc_14018861B
0x1401882a3  lea     r12, [r15+90h]
0x1401882aa  test    bl, 20h
0x1401882ad  jnz     loc_140188365
0x1401882b3  mov     r14d, 1
0x1401882b9  jmp     loc_140188AE7
0x1401882be  test    rdi, rdi
0x1401882c1  jz      short loc_1401882CD
0x1401882c3  cmp     qword ptr [rdi+0F0h], 0
0x1401882cb  jnz     short loc_14018829A
0x1401882cd  test    r13, r13
0x1401882d0  jz      short loc_14018829A
0x1401882d2  mov     rax, [rsp+0D8h+arg_20]
0x1401882da  test    rax, rax
0x1401882dd  jz      short loc_14018829A
0x1401882df  mov     byte ptr [rsp+0D8h+ResourceManager], r12b
0x1401882e4  xor     r9d, r9d
0x1401882e7  xor     edx, edx
0x1401882e9  lea     r8d, [r9+5]
0x1401882ed  mov     rcx, [rax+90h]
0x1401882f4  call    TxfSearchAddTxfFcbCleanupList
0x1401882f9  mov     rdi, rax
0x1401882fc  bts     dword ptr [rax+10h], 10h
0x140188301  mov     rax, [rsp+0D8h+arg_28]
0x140188309  xor     esi, esi
0x14018830b  cmp     [rax], rsi
0x14018830e  jz      short loc_140188325
0x140188310  mov     [rax], rsi
0x140188313  test    bl, 10h
0x140188316  jz      short loc_140188325
0x140188318  mov     dl, r12b
0x14018831b  lea     rcx, [rsp+0D8h+var_80]
0x140188320  call    TxfDereferenceTransaction
0x140188325  mov     [rdi+18h], rsi
0x140188329  mov     [rdi+20h], r15
0x14018832d  lock add [r15+40h], r12d
0x140188332  mov     rax, [rdi+20h]
0x140188336  lock add [rax+30h], r12d
0x14018833b  mov     rcx, r13; Object
0x14018833e  call    cs:__imp_ObfReferenceObject
0x140188345  nop     dword ptr [rax+rax+00h]
0x14018834a  mov     [rdi+28h], r13
0x14018834e  mov     al, cs:NtfsStatusDebugFlags
0x140188354  mov     ecx, 0C00000D8h; Status
0x140188359  call    cs:__imp_ExRaiseStatus
0x140188365  lea     r14, [rdi+0F0h]
0x14018836c  cmp     qword ptr [r14], 0
0x140188370  jnz     loc_1401882B3
0x140188376  mov     rcx, [rdi+18h]
0x14018837a  add     rcx, 50h ; 'P'; Resource
0x14018837e  mov     dl, 1; Wait
0x140188380  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140188387  nop     dword ptr [rax+rax+00h]
0x14018838c  mov     [rsp+0D8h+arg_18], 1
0x140188394  mov     rcx, [r12+10h]; Resource
0x140188399  call    cs:__imp_ExReleaseResourceLite
0x1401883a0  nop     dword ptr [rax+rax+00h]
0x1401883a5  xor     esi, esi
0x1401883a7  mov     [rsp+0D8h+arg_0], sil
0x1401883af  lock or dword ptr [rdi+10h], 20000h
0x1401883b7  mov     rcx, [rdi+18h]
0x1401883bb  add     rcx, 50h ; 'P'; Resource
0x1401883bf  call    cs:__imp_ExReleaseResourceLite
0x1401883c6  nop     dword ptr [rax+rax+00h]
0x1401883cb  mov     [rsp+0D8h+arg_18], sil
0x1401883d3  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x1401883db  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], rsi
0x1401883e0  mov     [rsp+0D8h+ObjectAttributes.Attributes], 200h
0x1401883eb  mov     [rsp+0D8h+ObjectAttributes.ObjectName], rsi
0x1401883f3  xorps   xmm0, xmm0
0x1401883f6  movdqu  xmmword ptr [rsp+0D8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401883ff  lea     r12, [rdi+0F8h]
0x140188406  mov     [rsp+0D8h+EnlistmentKey], rdi; EnlistmentKey
0x14018840b  mov     [rsp+0D8h+NotificationMask], 20Eh; NotificationMask
0x140188413  mov     [rsp+0D8h+CreateOptions], esi; CreateOptions
0x140188417  mov     [rsp+0D8h+Transaction], r13; Transaction
0x14018841c  mov     rax, [r15+288h]
0x140188423  mov     [rsp+0D8h+ResourceManager], rax; ResourceManager
0x140188428  lea     r9, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x14018842d  xor     edx, edx; PreviousMode
0x14018842f  mov     r8d, 0F001Fh; DesiredAccess
0x140188435  mov     rcx, r12; EnlistmentHandle
0x140188438  call    cs:__imp_TmCreateEnlistment
0x14018843f  nop     dword ptr [rax+rax+00h]
0x140188444  mov     esi, eax
0x140188446  mov     [rsp+0D8h+var_84], eax
0x14018844a  mov     rcx, [rdi+18h]
0x14018844e  add     rcx, 50h ; 'P'; Resource
0x140188452  mov     dl, 1; Wait
0x140188454  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14018845b  nop     dword ptr [rax+rax+00h]
0x140188460  mov     [rsp+0D8h+arg_18], 1
0x140188468  lock and dword ptr [rdi+10h], 0FFFDFFFFh
0x140188470  mov     rcx, [rdi+188h]; Event
0x140188477  test    rcx, rcx
0x14018847a  jnz     loc_140188ABA
0x140188480  test    esi, esi
0x140188482  jns     loc_14018881D
0x140188488  mov     al, cs:NtfsStatusDebugFlags
0x14018848e  test    al, al
0x140188490  jnz     loc_1401887B7
0x140188496  mov     r14d, 1
0x14018849c  lock or dword ptr [rdi+10h], 2
0x1401884a1  test    dword ptr [rdi+10h], 200h
0x1401884a8  jnz     loc_140188AD0
0x1401884ae  mov     rcx, [rdi+18h]
0x1401884b2  add     rcx, 50h ; 'P'; Resource
0x1401884b6  call    cs:__imp_ExReleaseResourceLite
0x1401884bd  nop     dword ptr [rax+rax+00h]
0x1401884c2  mov     [rsp+0D8h+arg_18], 0
0x1401884ca  mov     rcx, rdi
0x1401884cd  call    TxfRemoveTransactionFromList
0x1401884d2  mov     rax, [rsp+0D8h+arg_28]
0x1401884da  mov     qword ptr [rax], 0
0x1401884e1  mov     dl, r14b
0x1401884e4  lea     rcx, [rsp+0D8h+var_80]
0x1401884e9  call    TxfDereferenceTransaction
0x1401884ee  mov     rdi, [rsp+0D8h+var_80]
0x1401884f3  jmp     loc_1401881E3
0x1401884f8  test    r9, r9
0x1401884fb  jz      loc_14018817A
0x140188501  add     rdx, 100h; Source2
0x140188508  mov     r8d, 10h; Length
0x14018850e  mov     rcx, r9; Source1
0x140188511  call    cs:__imp_RtlCompareMemory
0x140188518  nop     dword ptr [rax+rax+00h]
0x14018851d  cmp     rax, 10h
0x140188521  jnz     loc_14018817A
0x140188527  jmp     loc_140188205
0x14018852c  test    r9, r9
0x14018852f  jnz     loc_14018814F
0x140188535  test    bl, 8
0x140188538  jz      loc_14018814F
0x14018853e  mov     rax, [r15+2B8h]
0x140188545  test    rax, rax
0x140188548  jz      loc_140188193
0x14018854e  mov     rdi, rax
0x140188551  mov     [rsp+0D8h+var_80], rax
0x140188556  mov     r12b, r14b
0x140188559  mov     [rsp+0D8h+var_88], r14b
0x14018855e  jmp     loc_140188193
0x140188563  lea     rax, [rsp+0D8h+arg_0]
0x14018856b  mov     [rsp+0D8h+ResourceManager], rax
0x140188570  lea     r12, [r15+90h]
0x140188577  mov     r9, r12
0x14018857a  lea     r8, [rsp+0D8h+arg_18]
0x140188582  mov     rdx, rdi
0x140188585  mov     rcx, [rsp+0D8h+arg_20]
0x14018858d  call    TxfWaitForEnlistmentCompletion
0x140188592  mov     esi, eax
0x140188594  mov     [rsp+0D8h+var_84], eax
0x140188598  xor     edi, edi
  ... truncated ...
```

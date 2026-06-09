# UlpEnumerateCouplings

- ea: `0x140071790`
- end: `0x140071f6f`
- name: `UlpEnumerateCouplings`
- size: `2015`
- prototype: ``
- caller_count: `4`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140060e24`
- `0x140062c5c`
- `0x140071698`
- `0x1400ce13c`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140049d28`
- `0x14005dff0`
- `0x14005e050`
- `0x1400705f0`
- `0x140071790`
- `0x14009622c`
- `0x1400a033c`
- `0x14013dc78`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3974`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140071c3a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140071c3a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140071d64`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140071d64`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140071a91`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140071a91`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140071cc0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140071cc0`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140071d18`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140071d18`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140071f26`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140071f26`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140071c62`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140071c62`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140071c9e`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140071c9e`
- `ntoskrnl!KeSetEvent` at `0x140071d82`
- `ntoskrnl!KeSetEvent` at `0x140071d82`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140071ce9`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140071ce9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140071bfe`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140071bfe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007184e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400718b8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400719be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400719e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007184e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400718b8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400719be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400719e3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400717f5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140071889`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400717f5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140071889`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140071842`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400718ac`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140071842`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400718ac`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400719b2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400719d7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400719b2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400719d7`
- `ntoskrnl!IoGetCurrentProcess` at `0x140071b2c`
- `ntoskrnl!IoGetCurrentProcess` at `0x140071b2c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007192b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071948`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007192b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071948`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400717e4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071878`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071912`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071937`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400717e4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071878`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071912`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071937`

## pseudocode

```c
void __fastcall UlpEnumerateCouplings(
        __int64 a1,
        __int64 a2,
        void (__fastcall *a3)(char *, _QWORD, __int64),
        __int64 a4,
        __int64 a5)
{
  char *v8; // rbx
  char *i; // rsi
  volatile signed __int32 *v10; // rdx
  signed __int32 v11; // eax
  signed __int32 v12; // ecx
  int v13; // eax
  __int64 v14; // rsi
  __int64 v15; // rdx
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // r8
  _QWORD *v20; // rdx
  volatile signed __int32 *v21; // rdx
  volatile signed __int32 *v22; // rdx
  int v23; // eax
  __int64 v24; // rsi
  int v25; // edi
  bool v26; // zf
  unsigned __int64 v27; // rdi
  int v28; // eax
  __int64 v29; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v31; // r9
  void *CurrentServerSilo; // rbp
  __int64 v33; // rcx
  __int64 v34; // rdi
  USHORT CurrentNodeNumber; // ax
  char v36; // si
  __int64 v37; // rax
  __int64 v38; // r14
  ULONG v39; // esi
  ULONG_PTR v40; // rdx
  int v41; // ecx
  __int64 v42; // rsi
  int v43; // eax
  __int64 v44; // [rsp+40h] [rbp-D8h] BYREF
  __int128 v45; // [rsp+48h] [rbp-D0h]
  _DWORD v46[24]; // [rsp+60h] [rbp-B8h] BYREF

  *(_QWORD *)&v45 = a4;
  v44 = a5;
  v8 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qPqqq(a5, a2, a3, a1, a2, a3, a4, a5, v44);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  for ( i = *(char **)(a1 + 8); i != (char *)(a1 + 8); i = *(char **)i )
  {
    v10 = (volatile signed __int32 *)&i[-a2 + 20];
    while ( 1 )
    {
      v11 = *v10;
      if ( !*v10 )
        break;
      v12 = v11 + 1;
      if ( UxDebugCheckRefcount && v12 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v10, 0x21u, v12);
      if ( v11 == _InterlockedCompareExchange(v10, v12, v11) )
      {
        ExReleasePushLockSharedEx(a1, 0);
        KeLeaveCriticalRegion();
        if ( v8 )
        {
          v43 = _InterlockedDecrement((volatile signed __int32 *)v8 + 5);
          if ( UxDebugCheckRefcount && v43 <= -1 )
            UlBugCheckEx(3u, (ULONG_PTR)(v8 + 20), 0x21u, v43);
          if ( !v43 )
            UlpFreeCoupling(v8, 0);
        }
        a3(&i[-a2], v45, v44);
        KeEnterCriticalRegion();
        ExAcquirePushLockSharedEx(a1, 0);
        v8 = &i[-a2];
        break;
      }
    }
  }
  ExReleasePushLockSharedEx(a1, 0);
  KeLeaveCriticalRegion();
  if ( !v8 )
    goto LABEL_34;
  v13 = _InterlockedDecrement((volatile signed __int32 *)v8 + 5);
  if ( UxDebugCheckRefcount && v13 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v8 + 20), 0x21u, v13);
  if ( v13 )
    goto LABEL_34;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v8, 0);
  v14 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 8) + 264LL) + 8LL * *(unsigned __int16 *)(*((_QWORD *)v8 + 7) + 56LL));
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*((_QWORD *)v8 + 7) + 944LL, 0);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v14, 0);
  v15 = *((_QWORD *)v8 + 3);
  v16 = v8 + 24;
  if ( *(char **)(v15 + 8) != v8 + 24 )
    goto LABEL_51;
  v17 = (_QWORD *)*((_QWORD *)v8 + 4);
  if ( (_QWORD *)*v17 != v16
    || (*v17 = v15,
        *(_QWORD *)(v15 + 8) = v17,
        *v16 = 0,
        *((_QWORD *)v8 + 4) = 0,
        v18 = v8 + 40,
        v19 = *((_QWORD *)v8 + 5),
        *(char **)(v19 + 8) != v8 + 40)
    || (v20 = (_QWORD *)*((_QWORD *)v8 + 6), (_QWORD *)*v20 != v18) )
  {
LABEL_51:
    __fastfail(3u);
  }
  *v20 = v19;
  *(_QWORD *)(v19 + 8) = v20;
  *v18 = 0;
  *((_QWORD *)v8 + 6) = 0;
  ExReleasePushLockExclusiveEx(v14, 0);
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*((_QWORD *)v8 + 7) + 944LL, 0);
  KeLeaveCriticalRegion();
  v21 = (volatile signed __int32 *)*((_QWORD *)v8 + 11);
  if ( v21 )
  {
    v28 = _InterlockedDecrement(v21);
    if ( UxDebugCheckRefcount && v28 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v21, 0xEu, v28);
    if ( !v28 )
      UlConsumerCleanupCompletion(*((_QWORD *)v8 + 11));
    *((_QWORD *)v8 + 11) = 0;
  }
  v22 = (volatile signed __int32 *)*((_QWORD *)v8 + 8);
  v23 = _InterlockedDecrement(v22);
  if ( UxDebugCheckRefcount && v23 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v22, 0xEu, v23);
  if ( !v23 )
    UlFreeRequestQueue(*((PVOID *)v8 + 8));
  v24 = *((_QWORD *)v8 + 7);
  *((_QWORD *)v8 + 8) = 0;
  v25 = _InterlockedDecrement((volatile signed __int32 *)(v24 + 40));
  if ( UxDebugCheckRefcount && v25 <= -1 )
    UlBugCheckEx(3u, v24 + 40, 0xEu, v25);
  if ( v25 )
    goto LABEL_26;
  v29 = v24 + 64;
  CurrentProcess = IoGetCurrentProcess();
  CurrentServerSilo = *(void **)(v24 + 1088);
  v33 = *(_QWORD *)(v24 + 64);
  if ( UxSystemProcess == CurrentProcess )
  {
    if ( v33 || *(_QWORD *)(v24 + 80) || *(_QWORD *)(v24 + 96) )
      UlBugCheckEx(1u, v24 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( !KeGetCurrentIrql() )
    {
      v36 = 0;
      v45 = 0;
      if ( CurrentServerSilo == (void *)-1LL )
      {
        v38 = *((_QWORD *)&v45 + 1);
      }
      else
      {
        v37 = PsAttachSiloToCurrentThread(CurrentServerSilo);
        v38 = v37;
        v36 = 1;
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
        {
          WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v37, CurrentServerSilo);
          UlFreeHttpConnection(v29);
LABEL_61:
          if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v38);
          PsDetachSiloFromCurrentThread(v38);
          goto LABEL_26;
        }
      }
      UlFreeHttpConnection(v29);
      if ( !v36 )
        goto LABEL_26;
      goto LABEL_61;
    }
    v39 = 0;
    if ( (unsigned int)dword_1401A3F48 > 1 )
    {
      v39 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
      if ( byte_1401A3F60 )
        v39 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
    }
    if ( CurrentServerSilo == (void *)-1LL )
      CurrentServerSilo = (void *)PsGetCurrentServerSilo();
    *(_QWORD *)(v29 + 32) = CurrentServerSilo;
    v44 = 0;
    if ( CurrentServerSilo )
      ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
    PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v44);
    v40 = v44 + 24;
    v41 = _InterlockedIncrement((volatile signed __int32 *)(v44 + 24));
    if ( UxDebugCheckRefcount && v41 <= -1 )
      UlBugCheckEx(3u, v40, 0xDu, v41);
    *(_BYTE *)(v29 + 24) = 1;
    v42 = *(_QWORD *)(qword_1401A3F50 + 8LL * v39);
    *(_QWORD *)(v29 + 16) = UlFreeHttpConnection;
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v42 + 16), (PSLIST_ENTRY)v29) )
    {
      KeSetEvent((PRKEVENT)(v42 + 32), 0, 0);
      UlpActivateThreadPoolQueue((PVOID)v42);
    }
  }
  else
  {
    if ( v33 || *(_QWORD *)(v24 + 80) || *(_QWORD *)(v24 + 96) )
      UlBugCheckEx(1u, v24 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
    LOBYTE(v31) = 1;
    UlThreadPoolEnqueueWorkItem(0, v24 + 64, UlFreeHttpConnection, v31, CurrentServerSilo, -1);
  }
LABEL_26:
  v26 = UxDebugDisableLookaside == 0;
  *((_QWORD *)v8 + 7) = 0;
  *((_DWORD *)v8 + 4) = 1969441909;
  if ( v26 )
  {
    if ( UxCompactMode )
    {
      v34 = qword_1401A0910;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v34, v8, CurrentNodeNumber);
    }
    else
    {
      v27 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v8 + 1) << 7);
      if ( !*(_BYTE *)(v27 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0910, v27 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v27 + 64), v8);
    }
  }
  else
  {
    memset(v46, 0, sizeof(v46));
    v46[10] = dword_1401A0928;
    ((void (__fastcall *)(char *, _DWORD *))off_1401A0938)(v8, v46);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
LABEL_34:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 33, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  }
}

```

## disassembly

```asm
0x140071790  push    rbx
0x140071792  push    rbp
0x140071793  push    rsi
0x140071794  push    rdi
0x140071795  push    r12
0x140071797  push    r13
0x140071799  push    r14
0x14007179b  push    r15
0x14007179d  sub     rsp, 0D8h
0x1400717a4  mov     rax, cs:__security_cookie
0x1400717ab  xor     rax, rsp
0x1400717ae  mov     [rsp+118h+var_58], rax
0x1400717b6  mov     rbp, rcx
0x1400717b9  mov     qword ptr [rsp+118h+var_D0], r9
0x1400717be  mov     rcx, [rsp+118h+arg_20]
0x1400717c6  xor     r14d, r14d
0x1400717c9  mov     [rsp+118h+var_D8], rcx
0x1400717ce  mov     r13, r8
0x1400717d1  mov     r12, rdx
0x1400717d4  mov     ebx, r14d
0x1400717d7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400717de  jnz     loc_140071DEA
0x1400717e4  call    cs:__imp_KeEnterCriticalRegion
0x1400717eb  nop     dword ptr [rax+rax+00h]
0x1400717f0  xor     edx, edx
0x1400717f2  mov     rcx, rbp
0x1400717f5  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400717fc  nop     dword ptr [rax+rax+00h]
0x140071801  mov     rsi, [rbp+8]
0x140071805  lea     r15, [rbp+8]
0x140071809  mov     edi, 0FFFFFFFFh
0x14007180e  cmp     rsi, r15
0x140071811  jz      loc_1400718A7
0x140071817  mov     r14, rsi
0x14007181a  sub     r14, r12
0x14007181d  lea     rdx, [r14+14h]; BugCheckParameter2
0x140071821  mov     eax, [rdx]
0x140071823  test    eax, eax
0x140071825  jz      short loc_140071898
0x140071827  cmp     cs:UxDebugCheckRefcount, 0
0x14007182e  lea     ecx, [rax+1]
0x140071831  jnz     loc_140071C1E
0x140071837  lock cmpxchg [rdx], ecx
0x14007183b  jnz     short loc_140071821
0x14007183d  xor     edx, edx
0x14007183f  mov     rcx, rbp
0x140071842  call    cs:__imp_ExReleasePushLockSharedEx
0x140071849  nop     dword ptr [rax+rax+00h]
0x14007184e  call    cs:__imp_KeLeaveCriticalRegion
0x140071855  nop     dword ptr [rax+rax+00h]
0x14007185a  test    rbx, rbx
0x14007185d  jnz     loc_140071E8D
0x140071863  mov     r8, [rsp+118h+var_D8]
0x140071868  mov     rcx, r14
0x14007186b  mov     rdx, qword ptr [rsp+118h+var_D0]
0x140071870  mov     rax, r13
0x140071873  call    _guard_dispatch_icall
0x140071878  call    cs:__imp_KeEnterCriticalRegion
0x14007187f  nop     dword ptr [rax+rax+00h]
0x140071884  xor     edx, edx
0x140071886  mov     rcx, rbp
0x140071889  call    cs:__imp_ExAcquirePushLockSharedEx
0x140071890  nop     dword ptr [rax+rax+00h]
0x140071895  mov     rbx, r14
0x140071898  mov     rsi, [rsi]
0x14007189b  cmp     rsi, r15
0x14007189e  jnz     loc_140071817
0x1400718a4  xor     r14d, r14d
0x1400718a7  xor     edx, edx
0x1400718a9  mov     rcx, rbp
0x1400718ac  call    cs:__imp_ExReleasePushLockSharedEx
0x1400718b3  nop     dword ptr [rax+rax+00h]
0x1400718b8  call    cs:__imp_KeLeaveCriticalRegion
0x1400718bf  nop     dword ptr [rax+rax+00h]
0x1400718c4  test    rbx, rbx
0x1400718c7  jz      loc_140071AE1
0x1400718cd  lea     rdx, [rbx+14h]; BugCheckParameter2
0x1400718d1  mov     eax, edi
0x1400718d3  lock xadd [rdx], eax
0x1400718d7  dec     eax
0x1400718d9  cmp     cs:UxDebugCheckRefcount, 0
0x1400718e0  jnz     loc_140071B7F
0x1400718e6  test    eax, eax
0x1400718e8  jnz     loc_140071AE1
0x1400718ee  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400718f5  jnz     loc_140071E0B
0x1400718fb  mov     rax, [rbx+38h]
0x1400718ff  movzx   edx, word ptr [rax+38h]
0x140071903  mov     rax, [rbx+40h]
0x140071907  mov     rcx, [rax+108h]
0x14007190e  mov     rsi, [rcx+rdx*8]
0x140071912  call    cs:__imp_KeEnterCriticalRegion
0x140071919  nop     dword ptr [rax+rax+00h]
0x14007191e  mov     rcx, [rbx+38h]
0x140071922  xor     edx, edx
0x140071924  add     rcx, 3B0h
0x14007192b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140071932  nop     dword ptr [rax+rax+00h]
0x140071937  call    cs:__imp_KeEnterCriticalRegion
0x14007193e  nop     dword ptr [rax+rax+00h]
0x140071943  xor     edx, edx
0x140071945  mov     rcx, rsi
0x140071948  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14007194f  nop     dword ptr [rax+rax+00h]
0x140071954  mov     rdx, [rbx+18h]
0x140071958  lea     rax, [rbx+18h]
0x14007195c  cmp     [rdx+8], rax
0x140071960  jnz     loc_140071BD4
0x140071966  mov     rcx, [rax+8]
0x14007196a  cmp     [rcx], rax
0x14007196d  jnz     loc_140071BD4
0x140071973  mov     [rcx], rdx
0x140071976  mov     [rdx+8], rcx
0x14007197a  mov     [rax], r14
0x14007197d  mov     [rax+8], r14
0x140071981  lea     rax, [rbx+28h]
0x140071985  mov     r8, [rax]
0x140071988  cmp     [r8+8], rax
0x14007198c  jnz     loc_140071BD4
0x140071992  mov     rdx, [rax+8]
0x140071996  cmp     [rdx], rax
0x140071999  jnz     loc_140071BD4
0x14007199f  mov     [rdx], r8
0x1400719a2  mov     rcx, rsi
0x1400719a5  mov     [r8+8], rdx
0x1400719a9  xor     edx, edx
0x1400719ab  mov     [rax], r14
0x1400719ae  mov     [rax+8], r14
0x1400719b2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400719b9  nop     dword ptr [rax+rax+00h]
0x1400719be  call    cs:__imp_KeLeaveCriticalRegion
0x1400719c5  nop     dword ptr [rax+rax+00h]
0x1400719ca  mov     rcx, [rbx+38h]
0x1400719ce  xor     edx, edx
0x1400719d0  add     rcx, 3B0h
0x1400719d7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400719de  nop     dword ptr [rax+rax+00h]
0x1400719e3  call    cs:__imp_KeLeaveCriticalRegion
0x1400719ea  nop     dword ptr [rax+rax+00h]
0x1400719ef  mov     rdx, [rbx+58h]; BugCheckParameter2
0x1400719f3  test    rdx, rdx
0x1400719f6  jnz     loc_140071B02
0x1400719fc  mov     rdx, [rbx+40h]; BugCheckParameter2
0x140071a00  mov     eax, edi
0x140071a02  lock xadd [rdx], eax
0x140071a06  dec     eax
0x140071a08  cmp     cs:UxDebugCheckRefcount, 0
0x140071a0f  jnz     loc_140071B9B
0x140071a15  test    eax, eax
0x140071a17  jz      loc_140071EDF
0x140071a1d  mov     rsi, [rbx+38h]
0x140071a21  mov     [rbx+40h], r14
0x140071a25  lea     rdx, [rsi+28h]; BugCheckParameter2
0x140071a29  lock xadd [rdx], edi
0x140071a2d  dec     edi
0x140071a2f  cmp     cs:UxDebugCheckRefcount, 0
0x140071a36  jnz     loc_140071BB7
0x140071a3c  test    edi, edi
0x140071a3e  jz      loc_140071B28
0x140071a44  cmp     cs:UxDebugDisableLookaside, 0
0x140071a4b  mov     [rbx+38h], r14
0x140071a4f  mov     dword ptr [rbx+10h], 75634C75h
0x140071a56  jnz     loc_140071F37
0x140071a5c  cmp     cs:UxCompactMode, 0
0x140071a63  jnz     loc_140071BF7
0x140071a69  mov     edi, [rbx]
0x140071a6b  mov     rcx, cs:qword_1401A0910
0x140071a72  inc     edi
0x140071a74  shl     rdi, 7
0x140071a78  add     rdi, rcx
0x140071a7b  movzx   eax, byte ptr [rdi+0B0h]
0x140071a82  test    al, al
0x140071a84  jz      loc_140071E7F
0x140071a8a  mov     rdx, rbx; Entry
0x140071a8d  lea     rcx, [rdi+40h]; Lookaside
0x140071a91  call    cs:__imp_ExFreeToLookasideListEx
0x140071a98  nop     dword ptr [rax+rax+00h]
0x140071a9d  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140071aa4  jnz     short loc_140071ACB
0x140071aa6  mov     rcx, [rsp+118h+var_58]
0x140071aae  xor     rcx, rsp; StackCookie
0x140071ab1  call    __security_check_cookie
0x140071ab6  add     rsp, 0D8h
0x140071abd  pop     r15
0x140071abf  pop     r14
0x140071ac1  pop     r13
0x140071ac3  pop     r12
0x140071ac5  pop     rdi
0x140071ac6  pop     rsi
0x140071ac7  pop     rbp
0x140071ac8  pop     rbx
0x140071ac9  retn
0x140071acb  mov     edx, 18h
0x140071ad0  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140071ad7  mov     ecx, 408h
0x140071adc  call    WPP_SF_
0x140071ae1  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140071ae8  jz      short loc_140071AA6
0x140071aea  mov     edx, 21h ; '!'
0x140071aef  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140071af6  mov     ecx, 408h
0x140071afb  call    WPP_SF_
0x140071b00  jmp     short loc_140071AA6
0x140071b02  mov     eax, edi
0x140071b04  lock xadd [rdx], eax
0x140071b08  dec     eax
0x140071b0a  cmp     cs:UxDebugCheckRefcount, 0
0x140071b11  jnz     loc_140071BDB
0x140071b17  test    eax, eax
0x140071b19  jz      loc_140071ED1
0x140071b1f  mov     [rbx+58h], r14
0x140071b23  jmp     loc_1400719FC
0x140071b28  lea     rdi, [rsi+40h]
0x140071b2c  call    cs:__imp_IoGetCurrentProcess
0x140071b33  nop     dword ptr [rax+rax+00h]
0x140071b38  cmp     cs:UxSystemProcess, rax
0x140071b3f  mov     rbp, [rsi+440h]
0x140071b46  mov     rcx, [rdi]
0x140071b49  jnz     loc_140071DBE
0x140071b4f  test    rcx, rcx
0x140071b52  jnz     short loc_140071B64
0x140071b54  cmp     [rdi+10h], rcx
0x140071b58  jnz     short loc_140071B64
0x140071b5a  cmp     [rdi+20h], rcx
0x140071b5e  jz      loc_140071C3A
0x140071b64  mov     r9d, 0E1h; BugCheckParameter4
0x140071b6a  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140071b71  mov     rdx, rdi; BugCheckParameter2
0x140071b74  mov     ecx, 1; BugCheckParameter1
0x140071b79  call    UlBugCheckEx
0x140071b7f  cmp     eax, edi
0x140071b81  jg      loc_1400718E6
0x140071b87  movsxd  r9, eax; BugCheckParameter4
0x140071b8a  mov     ecx, 3; BugCheckParameter1
0x140071b8f  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140071b95  call    UlBugCheckEx
0x140071b9b  cmp     eax, edi
0x140071b9d  jg      loc_140071A15
0x140071ba3  movsxd  r9, eax; BugCheckParameter4
0x140071ba6  mov     ecx, 3; BugCheckParameter1
0x140071bab  mov     r8d, 0Eh; BugCheckParameter3
0x140071bb1  call    UlBugCheckEx
0x140071bb7  cmp     edi, 0FFFFFFFFh
0x140071bba  jg      loc_140071A3C
0x140071bc0  movsxd  r9, edi; BugCheckParameter4
0x140071bc3  mov     ecx, 3; BugCheckParameter1
0x140071bc8  mov     r8d, 0Eh; BugCheckParameter3
0x140071bce  call    UlBugCheckEx
0x140071bd4  mov     ecx, 3
0x140071bd9  int     29h; Win8: RtlFailFast(ecx)
0x140071bdb  cmp     eax, edi
0x140071bdd  jg      loc_140071B17
0x140071be3  movsxd  r9, eax; BugCheckParameter4
0x140071be6  mov     ecx, 3; BugCheckParameter1
0x140071beb  mov     r8d, 0Eh; BugCheckParameter3
0x140071bf1  call    UlBugCheckEx
0x140071bf7  mov     rdi, cs:qword_1401A0910
0x140071bfe  call    cs:__imp_KeGetCurrentNodeNumber
0x140071c05  nop     dword ptr [rax+rax+00h]
0x140071c0a  movzx   r8d, ax
0x140071c0e  mov     rdx, rbx
0x140071c11  mov     rcx, rdi
0x140071c14  call    PplFreeToLookasideListProcessor
0x140071c19  jmp     loc_140071A9D
0x140071c1e  cmp     ecx, edi
0x140071c20  jg      loc_140071837
0x140071c26  movsxd  r9, ecx; BugCheckParameter4
0x140071c29  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140071c2f  mov     ecx, 3; BugCheckParameter1
0x140071c34  call    UlBugCheckEx
0x140071c3a  call    cs:__imp_KeGetCurrentIrql
0x140071c41  nop     dword ptr [rax+rax+00h]
0x140071c46  test    al, al
0x140071c48  jnz     short loc_140071CB2
0x140071c4a  xor     sil, sil
0x140071c4d  xorps   xmm0, xmm0
0x140071c50  movups  [rsp+118h+var_D0], xmm0
0x140071c55  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x140071c59  jz      loc_140071DB4
0x140071c5f  mov     rcx, rbp
0x140071c62  call    cs:__imp_PsAttachSiloToCurrentThread
0x140071c69  nop     dword ptr [rax+rax+00h]
0x140071c6e  mov     r14, rax
0x140071c71  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140071c78  mov     sil, 1
0x140071c7b  jnz     loc_140071E54
0x140071c81  mov     rcx, rdi
0x140071c84  call    UlFreeHttpConnection
0x140071c89  test    sil, sil
0x140071c8c  jz      short loc_140071CAA
0x140071c8e  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140071c95  jnz     loc_140071EED
0x140071c9b  mov     rcx, r14
0x140071c9e  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140071ca5  nop     dword ptr [rax+rax+00h]
0x140071caa  xor     r14d, r14d
0x140071cad  jmp     loc_140071A44
0x140071cb2  cmp     cs:dword_1401A3F48, 1
0x140071cb9  mov     esi, r14d
0x140071cbc  jbe     short loc_140071CE3
  ... truncated ...
```

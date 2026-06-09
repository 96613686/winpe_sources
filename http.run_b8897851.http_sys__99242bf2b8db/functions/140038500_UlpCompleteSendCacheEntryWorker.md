# UlpCompleteSendCacheEntryWorker

- ea: `0x140038500`
- end: `0x140038d62`
- name: `UlpCompleteSendCacheEntryWorker`
- size: `2146`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000a350`
- `0x14000a520`
- `0x14000c390`
- `0x140022610`
- `0x140038500`
- `0x140038d68`
- `0x140038ea0`
- `0x140038f90`
- `0x140039360`
- `0x140049d28`
- `0x14005dff0`
- `0x1400b1bac`
- `0x1400ca804`
- `0x1400ca8c4`
- `0x1400e35f8`
- `0x1400e8ecc`
- `0x14011bc94`
- `0x14013dc78`
- `0x14014b000`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4b0c`
- `0x1401d9e44`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140038789`
- `ntoskrnl!KeGetCurrentIrql` at `0x140038789`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400388e8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400388e8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400386c1`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400386c1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140038845`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140038845`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003889b`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003889b`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140038cf3`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140038cf3`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400387b4`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400387b4`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400387f0`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400387f0`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140038962`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140038962`
- `ntoskrnl!KeSetEvent` at `0x140038906`
- `ntoskrnl!KeSetEvent` at `0x140038906`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14003886e`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14003886e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140038a1b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140038a1b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140038945`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140038945`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c7c`

## string_xrefs

- `0x140175601`: `SendCacheEntryFailed`

## pseudocode

```c
void __fastcall UlpCompleteSendCacheEntryWorker(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  __int64 v4; // r12
  int v5; // edi
  void *v6; // r14
  unsigned int v7; // r15d
  __int64 HkeContextFromRequest; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rdi
  void *v14; // rcx
  bool v15; // zf
  unsigned __int64 v16; // rdi
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // rdi
  void *CurrentServerSilo; // rbx
  char v21; // si
  __int64 v22; // rax
  __int64 v23; // r14
  ULONG v24; // esi
  ULONG_PTR v25; // rdx
  int v26; // eax
  __int64 v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // rcx
  ULONG_PTR v30; // rdx
  __int64 v31; // rdi
  USHORT CurrentNodeNumber; // ax
  char v33; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int8 v34; // [rsp+41h] [rbp-88h] BYREF
  _BYTE v35[6]; // [rsp+42h] [rbp-87h] BYREF
  __int128 v36; // [rsp+48h] [rbp-81h] BYREF
  __int64 v37; // [rsp+58h] [rbp-71h]
  __int128 v38; // [rsp+60h] [rbp-69h] BYREF
  _DWORD v39[24]; // [rsp+70h] [rbp-59h] BYREF

  v34 = 0;
  v33 = 0;
  v35[0] = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 196, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, a1);
  v2 = *(_QWORD *)(a1 + 96);
  v3 = a1 - 32;
  v4 = *(_QWORD *)(v2 + 24);
  v5 = *(_DWORD *)(v3 + 160);
  v6 = *(void **)(v3 + 80);
  v33 = 0;
  v34 = 0;
  if ( v5 < 0 )
  {
    v28 = *(_QWORD *)(v2 + 24);
    if ( v28 )
    {
      v29 = *(_QWORD *)(v28 + 1096);
      if ( (*(_BYTE *)(v29 + 1760) & 0x20) != 0
        && (!*(_QWORD *)(v29 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v2, v28, 0)) )
      {
        McTemplateK0xsq_EtwWriteTransfer(
          *(_QWORD *)(*(_QWORD *)(v2 + 24) + 1096LL) + 1688,
          v28,
          v2 + 72,
          *(_QWORD *)(v2 + 56),
          (__int64)"SendCacheEntryFailed",
          v5);
      }
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_dq(1040, 197, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, (unsigned int)v5, *(_QWORD *)(v2 + 56));
    UlCloseConnection(v4);
  }
  UlSetSendCompleteState(v2, 1, 0, (unsigned int)&v33, (__int64)&v34, (__int64)v35, *(_QWORD *)(v3 + 168), (__int64)v6);
  if ( *(_BYTE *)(*(_QWORD *)(v3 + 80) + 576LL) )
    UlLogHttpCacheResponse(v3, 0);
  if ( v35[0] && (*(_DWORD *)(v2 + 2216) & 7) != 0 )
  {
    v36 = 0;
    v37 = 0;
    v7 = 0;
    v38 = 0;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qq(1033, 220, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, v2, *(_QWORD *)(v2 + 64));
    HkeContextFromRequest = UlGetHkeContextFromRequest(v2, 0);
    v9 = HkeContextFromRequest;
    if ( HkeContextFromRequest )
    {
      if ( !*(_DWORD *)(HkeContextFromRequest + 136) && *(_DWORD *)(HkeContextFromRequest + 256) == 1 )
      {
        *(_QWORD *)&v36 = 0;
        v37 = 0;
        DWORD2(v36) = 0;
        v7 = UlHkeIndicatePublishEntityRequest(HkeContextFromRequest, &v36, 1, &v38);
      }
      UlHkeCancelCalloutContext(v9, 0);
      UlHkeDereferenceCalloutContext(v9, 10);
    }
    v10 = UlGetHkeContextFromRequest(v2, 1);
    v11 = v10;
    if ( v10 )
    {
      UlHkeCancelCalloutContext(v10, 0);
      UlHkeDereferenceCalloutContext(v11, 10);
    }
    v12 = UlGetHkeContextFromRequest(v2, 2);
    v13 = v12;
    if ( v12 )
    {
      UlHkeCancelCalloutContext(v12, 0);
      UlHkeDereferenceCalloutContext(v13, 10);
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1033, 221, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, v7);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 203, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, v3);
  v14 = *(void **)(v3 + 144);
  if ( v14 )
  {
    UlCleanupRangeCacheTracker(v14);
    *(_QWORD *)(v3 + 144) = 0;
  }
  if ( *(_BYTE *)(v3 + 20) )
  {
    v15 = UxDebugDisableLookaside == 0;
    *(_DWORD *)(v3 + 16) = 1094929525;
    if ( v15 )
    {
      if ( UxCompactMode )
      {
        v31 = qword_1401A01F0;
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        PplFreeToLookasideListProcessor(v31, v3, CurrentNodeNumber);
      }
      else
      {
        v16 = qword_1401A01F0 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v3 + 1) << 7);
        if ( !*(_BYTE *)(v16 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A01F0, v16 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v16 + 64), (PVOID)v3);
      }
    }
    else
    {
      memset(v39, 0, sizeof(v39));
      v39[10] = dword_1401A0208;
      ((void (__fastcall *)(__int64, _DWORD *))off_1401A0218)(v3, v39);
    }
  }
  else
  {
    *(_DWORD *)(v3 + 16) = 1633897589;
    ExFreePoolWithTag((PVOID)v3, 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1033, 204, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids);
  *(_QWORD *)(v2 + 1696) = 0;
  UlCheckinUriCacheEntry(v6);
  if ( v33 )
    UlResumeParsing(v4, v34);
  v18 = _InterlockedDecrement((volatile signed __int32 *)(v2 + 48));
  if ( UxDebugCheckRefcount && v18 <= -1 )
    UlBugCheckEx(3u, v2 + 48, 0x22u, v18);
  if ( !v18 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_qq(1032, 40, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v2, *(_QWORD *)(v2 + 64));
    if ( (*(_DWORD *)(v2 + 2264) & 1) != 0 || *(_QWORD *)(v2 + 2288) || *(_QWORD *)(v2 + 2312) )
    {
      v30 = v2 + 1248;
      if ( *(_QWORD *)(v2 + 1248) || *(_QWORD *)(v2 + 1264) || *(_QWORD *)(v2 + 1280) )
        UlBugCheckEx(1u, v30, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x645u);
      LOBYTE(v17) = 1;
      UlThreadPoolEnqueueWorkItem(0, v30, UlpFreeHttpRequest, v17, *(_QWORD *)(*(_QWORD *)(v2 + 24) + 1088LL), -1);
      goto LABEL_49;
    }
    v19 = v2 + 1248;
    if ( *(_QWORD *)(v2 + 1248) || *(_QWORD *)(v2 + 1264) || *(_QWORD *)(v2 + 1280) )
      UlBugCheckEx(1u, v2 + 1248, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x64Du);
    CurrentServerSilo = *(void **)(*(_QWORD *)(v2 + 24) + 1088LL);
    if ( KeGetCurrentIrql() )
    {
      v24 = 0;
      if ( (unsigned int)dword_1401A3F48 > 1 )
      {
        v24 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F60 )
          v24 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v19 + 32) = CurrentServerSilo;
      *(_QWORD *)&v38 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v38);
      v25 = v38 + 24;
      v26 = _InterlockedIncrement((volatile signed __int32 *)(v38 + 24));
      if ( UxDebugCheckRefcount && v26 <= -1 )
        UlBugCheckEx(3u, v25, 0xDu, v26);
      *(_BYTE *)(v19 + 24) = 1;
      v27 = *(_QWORD *)(qword_1401A3F50 + 8LL * v24);
      *(_QWORD *)(v19 + 16) = UlpFreeHttpRequest;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v27 + 16), (PSLIST_ENTRY)v19) )
      {
        KeSetEvent((PRKEVENT)(v27 + 32), 0, 0);
        if ( *(_BYTE *)(*(_QWORD *)v27 + 33LL) )
        {
          if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v27 + 68), 1, 0) )
          {
            if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
              WPP_SF_Dd(
                1304,
                18,
                WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids,
                *(unsigned int *)(v27 + 8),
                **(_DWORD **)v27);
            _InterlockedIncrement((volatile signed __int32 *)(v27 + 64));
            ExAcquireRundownProtection(&UlThreadPoolIoWorkItemsRundown);
            IoQueueWorkItemEx(*(PIO_WORKITEM *)(v27 + 56), UlpThreadPoolStarter, DelayedWorkQueue, (PVOID)v27);
          }
        }
      }
      goto LABEL_49;
    }
    v21 = 0;
    v38 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v23 = *((_QWORD *)&v38 + 1);
    }
    else
    {
      v22 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v23 = v22;
      v21 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v22, CurrentServerSilo);
        UlpFreeHttpRequest(v19);
        goto LABEL_46;
      }
    }
    UlpFreeHttpRequest(v19);
    if ( !v21 )
    {
LABEL_49:
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_(1032, 41, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
      goto LABEL_51;
    }
LABEL_46:
    if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v23);
    PsDetachSiloFromCurrentThread(v23);
    goto LABEL_49;
  }
LABEL_51:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1033, 198, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids);
}

```

## disassembly

```asm
0x140038500  push    rbp
0x140038502  push    rbx
0x140038503  push    rsi
0x140038504  push    rdi
0x140038505  push    r12
0x140038507  push    r13
0x140038509  push    r14
0x14003850b  push    r15
0x14003850d  lea     rbp, [rsp-1Fh]
0x140038512  sub     rsp, 0E8h
0x140038519  mov     rax, cs:__security_cookie
0x140038520  xor     rax, rsp
0x140038523  mov     [rbp+57h+var_50], rax
0x140038527  mov     rsi, rcx
0x14003852a  mov     [rsp+120h+var_DF], 0
0x14003852f  mov     [rsp+120h+var_E0], 0
0x140038534  mov     [rsp+120h+var_DE], 0
0x140038539  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140038540  jnz     loc_140038A72
0x140038546  mov     rbx, [rsi+60h]
0x14003854a  add     rsi, 0FFFFFFFFFFFFFFE0h
0x14003854e  mov     r12, [rbx+18h]
0x140038552  mov     edi, [rsi+0A0h]
0x140038558  mov     r14, [rsi+50h]
0x14003855c  mov     [rsp+120h+var_E0], 0
0x140038561  mov     [rsp+120h+var_DF], 0
0x140038566  test    edi, edi
0x140038568  js      loc_140038973
0x14003856e  mov     rax, [rsi+0A8h]
0x140038575  lea     r9, [rsp+120h+var_E0]
0x14003857a  mov     [rsp+120h+var_E8], r14
0x14003857f  xor     r8d, r8d
0x140038582  mov     [rsp+120h+var_F0], rax
0x140038587  mov     dl, 1
0x140038589  lea     rax, [rsp+120h+var_DE]
0x14003858e  mov     rcx, rbx
0x140038591  mov     [rsp+120h+var_F8], rax
0x140038596  lea     rax, [rsp+120h+var_DF]
0x14003859b  mov     [rsp+120h+var_100], rax
0x1400385a0  call    UlSetSendCompleteState
0x1400385a5  mov     rax, [rsi+50h]
0x1400385a9  cmp     byte ptr [rax+240h], 0
0x1400385b0  jnz     loc_140038B3D
0x1400385b6  xor     r13d, r13d
0x1400385b9  mov     r15d, 1
0x1400385bf  cmp     [rsp+120h+var_DE], r13b
0x1400385c4  jz      loc_140038651
0x1400385ca  mov     eax, [rbx+8A8h]
0x1400385d0  test    al, 7
0x1400385d2  jz      short loc_140038651
0x1400385d4  xorps   xmm0, xmm0
0x1400385d7  xor     eax, eax
0x1400385d9  movups  [rsp+120h+var_D8], xmm0
0x1400385de  mov     [rbp+57h+var_C8], rax
0x1400385e2  mov     r15d, r13d
0x1400385e5  movups  [rbp+57h+var_C0], xmm0
0x1400385e9  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400385f0  jnz     loc_140038B4C
0x1400385f6  xor     edx, edx
0x1400385f8  mov     rcx, rbx
0x1400385fb  call    UlGetHkeContextFromRequest
0x140038600  mov     rdi, rax
0x140038603  test    rax, rax
0x140038606  jnz     loc_140038B73
0x14003860c  mov     edx, 1
0x140038611  mov     rcx, rbx
0x140038614  call    UlGetHkeContextFromRequest
0x140038619  mov     rdi, rax
0x14003861c  test    rax, rax
0x14003861f  jnz     loc_140038BB9
0x140038625  mov     edx, 2
0x14003862a  mov     rcx, rbx
0x14003862d  call    UlGetHkeContextFromRequest
0x140038632  mov     rdi, rax
0x140038635  test    rax, rax
0x140038638  jnz     loc_140038BD5
0x14003863e  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140038645  jnz     loc_140038BF1
0x14003864b  mov     r15d, 1
0x140038651  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140038658  jnz     loc_140038C0F
0x14003865e  mov     rcx, [rsi+90h]; P
0x140038665  test    rcx, rcx
0x140038668  jnz     loc_140038C2D
0x14003866e  cmp     [rsi+14h], r13b
0x140038672  jz      loc_140038C70
0x140038678  cmp     cs:UxDebugDisableLookaside, r13b
0x14003867f  mov     dword ptr [rsi+10h], 41434C75h
0x140038686  jnz     loc_140038C3E
0x14003868c  cmp     cs:UxCompactMode, r13b
0x140038693  jnz     loc_140038A14
0x140038699  mov     edi, [rsi]
0x14003869b  mov     rcx, cs:qword_1401A01F0
0x1400386a2  inc     edi
0x1400386a4  shl     rdi, 7
0x1400386a8  add     rdi, rcx
0x1400386ab  movzx   eax, byte ptr [rdi+0B0h]
0x1400386b2  test    al, al
0x1400386b4  jz      loc_140038AB7
0x1400386ba  mov     rdx, rsi; Entry
0x1400386bd  lea     rcx, [rdi+40h]; Lookaside
0x1400386c1  call    cs:__imp_ExFreeToLookasideListEx
0x1400386c8  nop     dword ptr [rax+rax+00h]
0x1400386cd  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400386d4  jnz     loc_140038C8D
0x1400386da  mov     rcx, r14; P
0x1400386dd  mov     [rbx+6A0h], r13
0x1400386e4  call    UlCheckinUriCacheEntry
0x1400386e9  cmp     [rsp+120h+var_E0], r13b
0x1400386ee  jnz     loc_140038CA8
0x1400386f4  lea     rdx, [rbx+30h]; BugCheckParameter2
0x1400386f8  mov     eax, 0FFFFFFFFh
0x1400386fd  lock xadd [rdx], eax
0x140038701  dec     eax
0x140038703  cmp     cs:UxDebugCheckRefcount, r13b
0x14003870a  jnz     loc_1400389AC
0x140038710  test    eax, eax
0x140038712  jnz     loc_140038809
0x140038718  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003871f  jnz     loc_140038AC5
0x140038725  mov     eax, [rbx+8D8h]
0x14003872b  test    al, 1
0x14003872d  jnz     loc_1400389E6
0x140038733  cmp     [rbx+8F0h], r13
0x14003873a  jnz     loc_1400389E6
0x140038740  cmp     [rbx+908h], r13
0x140038747  jnz     loc_1400389E6
0x14003874d  lea     rdi, [rbx+4E0h]
0x140038754  cmp     [rdi], r13
0x140038757  jnz     short loc_140038765
0x140038759  cmp     [rdi+10h], r13
0x14003875d  jnz     short loc_140038765
0x14003875f  cmp     [rdi+20h], r13
0x140038763  jz      short loc_14003877E
0x140038765  mov     r9d, 64Dh; BugCheckParameter4
0x14003876b  lea     r8, aMinioHttpSysHt; "minio\\http\\sys\\httpconn.c"
0x140038772  mov     rdx, rdi; BugCheckParameter2
0x140038775  mov     rcx, r15; BugCheckParameter1
0x140038778  call    UlBugCheckEx
0x14003877e  mov     rax, [rbx+18h]
0x140038782  mov     rbx, [rax+440h]
0x140038789  call    cs:__imp_KeGetCurrentIrql
0x140038790  nop     dword ptr [rax+rax+00h]
0x140038795  test    al, al
0x140038797  jnz     loc_140038837
0x14003879d  xor     sil, sil
0x1400387a0  xorps   xmm0, xmm0
0x1400387a3  movups  [rbp+57h+var_C0], xmm0
0x1400387a7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400387ab  jz      loc_140038A3B
0x1400387b1  mov     rcx, rbx
0x1400387b4  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400387bb  nop     dword ptr [rax+rax+00h]
0x1400387c0  mov     r14, rax
0x1400387c3  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400387ca  mov     sil, 1
0x1400387cd  jnz     loc_140038AEC
0x1400387d3  mov     rcx, rdi
0x1400387d6  call    UlpFreeHttpRequest
0x1400387db  test    sil, sil
0x1400387de  jz      short loc_1400387FC
0x1400387e0  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400387e7  jnz     loc_140038CBA
0x1400387ed  mov     rcx, r14
0x1400387f0  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1400387f7  nop     dword ptr [rax+rax+00h]
0x1400387fc  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140038803  jnz     loc_140038D2C
0x140038809  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140038810  jnz     loc_140038D47
0x140038816  mov     rcx, [rbp+57h+var_50]
0x14003881a  xor     rcx, rsp; StackCookie
0x14003881d  call    __security_check_cookie
0x140038822  add     rsp, 0E8h
0x140038829  pop     r15
0x14003882b  pop     r14
0x14003882d  pop     r13
0x14003882f  pop     r12
0x140038831  pop     rdi
0x140038832  pop     rsi
0x140038833  pop     rbx
0x140038834  pop     rbp
0x140038835  retn
0x140038837  cmp     cs:dword_1401A3F48, 1
0x14003883e  mov     esi, r13d
0x140038841  jbe     short loc_140038868
0x140038843  xor     ecx, ecx; ProcNumber
0x140038845  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14003884c  nop     dword ptr [rax+rax+00h]
0x140038851  xor     edx, edx
0x140038853  div     cs:UxNumberOfProcessors
0x140038859  cmp     cs:byte_1401A3F60, r13b
0x140038860  mov     esi, edx
0x140038862  jnz     loc_140038CD8
0x140038868  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14003886c  jnz     short loc_14003887D
0x14003886e  call    cs:__imp_PsGetCurrentServerSilo
0x140038875  nop     dword ptr [rax+rax+00h]
0x14003887a  mov     rbx, rax
0x14003887d  mov     [rdi+20h], rbx
0x140038881  mov     qword ptr [rbp+57h+var_C0], r13
0x140038885  test    rbx, rbx
0x140038888  jnz     loc_140038CEB
0x14003888e  mov     edx, cs:UxPodMonitorSlot
0x140038894  lea     r8, [rbp+57h+var_C0]
0x140038898  mov     rcx, rbx
0x14003889b  call    cs:__imp_PsGetPermanentSiloContext
0x1400388a2  nop     dword ptr [rax+rax+00h]
0x1400388a7  mov     rdx, qword ptr [rbp+57h+var_C0]
0x1400388ab  mov     eax, r15d
0x1400388ae  add     rdx, 18h; BugCheckParameter2
0x1400388b2  lock xadd [rdx], eax
0x1400388b6  inc     eax
0x1400388b8  cmp     cs:UxDebugCheckRefcount, r13b
0x1400388bf  jnz     loc_1400389C9
0x1400388c5  mov     byte ptr [rdi+18h], 1
0x1400388c9  lea     r8, UlpFreeHttpRequest
0x1400388d0  mov     rax, cs:qword_1401A3F50
0x1400388d7  mov     rdx, rdi; ListEntry
0x1400388da  mov     ecx, esi
0x1400388dc  mov     rbx, [rax+rcx*8]
0x1400388e0  mov     [rdi+10h], r8
0x1400388e4  lea     rcx, [rbx+10h]; ListHead
0x1400388e8  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400388ef  nop     dword ptr [rax+rax+00h]
0x1400388f4  test    rax, rax
0x1400388f7  jnz     loc_1400387FC
0x1400388fd  lea     rcx, [rbx+20h]; Event
0x140038901  xor     r8d, r8d; Wait
0x140038904  xor     edx, edx; Increment
0x140038906  call    cs:__imp_KeSetEvent
0x14003890d  nop     dword ptr [rax+rax+00h]
0x140038912  mov     rax, [rbx]
0x140038915  cmp     [rax+21h], r13b
0x140038919  jz      loc_1400387FC
0x14003891f  xor     eax, eax
0x140038921  lock cmpxchg [rbx+44h], r15d
0x140038927  jnz     loc_1400387FC
0x14003892d  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 1
0x140038934  jnz     loc_140038D04
0x14003893a  lock inc dword ptr [rbx+40h]
0x14003893e  lea     rcx, UlThreadPoolIoWorkItemsRundown; RunRef
0x140038945  call    cs:__imp_ExAcquireRundownProtection
0x14003894c  nop     dword ptr [rax+rax+00h]
0x140038951  mov     rcx, [rbx+38h]; IoWorkItem
0x140038955  lea     rdx, UlpThreadPoolStarter; WorkerRoutine
0x14003895c  mov     r9, rbx; Context
0x14003895f  mov     r8d, r15d; QueueType
0x140038962  call    cs:__imp_IoQueueWorkItemEx
0x140038969  nop     dword ptr [rax+rax+00h]
0x14003896e  jmp     loc_1400387FC
0x140038973  mov     rdx, [rbx+18h]
0x140038977  test    rdx, rdx
0x14003897a  jz      short loc_140038990
0x14003897c  mov     rcx, [rdx+448h]
0x140038983  test    byte ptr [rcx+6E0h], 20h
0x14003898a  jnz     loc_140038B17
0x140038990  test    byte ptr cs:xmmword_1401A2CA0+2, 1
0x140038997  jnz     loc_140038A90
0x14003899d  mov     dl, 1
0x14003899f  mov     rcx, r12
0x1400389a2  call    UlCloseConnection
0x1400389a7  jmp     loc_14003856E
0x1400389ac  cmp     eax, 0FFFFFFFFh
0x1400389af  jg      loc_140038710
0x1400389b5  movsxd  r9, eax; BugCheckParameter4
0x1400389b8  mov     ecx, 3; BugCheckParameter1
0x1400389bd  mov     r8d, 22h ; '"'; BugCheckParameter3
0x1400389c3  call    UlBugCheckEx
0x1400389c9  cmp     eax, 0FFFFFFFFh
0x1400389cc  jg      loc_1400388C5
0x1400389d2  movsxd  r9, eax; BugCheckParameter4
0x1400389d5  mov     ecx, 3; BugCheckParameter1
0x1400389da  mov     r8d, 0Dh; BugCheckParameter3
0x1400389e0  call    UlBugCheckEx
0x1400389e6  lea     rdx, [rbx+4E0h]; BugCheckParameter2
0x1400389ed  cmp     [rdx], r13
0x1400389f0  jnz     short loc_1400389FE
0x1400389f2  cmp     [rdx+10h], r13
0x1400389f6  jnz     short loc_1400389FE
0x1400389f8  cmp     [rdx+20h], r13
0x1400389fc  jz      short loc_140038A44
0x1400389fe  mov     r9d, 645h; BugCheckParameter4
0x140038a04  lea     r8, aMinioHttpSysHt; "minio\\http\\sys\\httpconn.c"
0x140038a0b  mov     rcx, r15; BugCheckParameter1
0x140038a0e  call    UlBugCheckEx
0x140038a14  mov     rdi, cs:qword_1401A01F0
0x140038a1b  call    cs:__imp_KeGetCurrentNodeNumber
0x140038a22  nop     dword ptr [rax+rax+00h]
0x140038a27  movzx   r8d, ax
0x140038a2b  mov     rdx, rsi
0x140038a2e  mov     rcx, rdi
0x140038a31  call    PplFreeToLookasideListProcessor
0x140038a36  jmp     loc_1400386CD
0x140038a3b  mov     r14, qword ptr [rbp+57h+var_C0+8]
0x140038a3f  jmp     loc_1400387D3
0x140038a44  mov     rax, [rbx+18h]
0x140038a48  lea     r8, UlpFreeHttpRequest
0x140038a4f  mov     dword ptr [rsp+120h+var_F8], 0FFFFFFFFh
0x140038a57  mov     r9b, 1
  ... truncated ...
```

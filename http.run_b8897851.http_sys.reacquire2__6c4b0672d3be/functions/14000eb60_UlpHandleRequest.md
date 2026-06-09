# UlpHandleRequest

- ea: `0x14000eb60`
- end: `0x14000f475`
- name: `UlpHandleRequest`
- size: `2325`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x14000eb60`
- `0x14000f480`
- `0x140013430`
- `0x140022610`
- `0x14006caf0`
- `0x1400a84fc`
- `0x1400eaaac`
- `0x14013dc78`
- `0x140155660`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4444`
- `0x1401ca158`
- `0x1401cd764`
- `0x1401d9c5c`
- `0x1401d9e44`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000ef4c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ef4c`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000ebaa`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000ebaa`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000f079`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000f079`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000efd2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000efd2`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000f02c`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000f02c`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14000f43c`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14000f43c`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000ef73`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000ef73`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000efb4`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000efb4`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000f0f3`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000f0f3`
- `ntoskrnl!KeSetEvent` at `0x14000f097`
- `ntoskrnl!KeSetEvent` at `0x14000f097`
- `ntoskrnl!IofCompleteRequest` at `0x14000ee0c`
- `ntoskrnl!IofCompleteRequest` at `0x14000ee0c`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000effb`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000effb`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000f0d6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000f0d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ed53`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ed53`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ed47`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ed47`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000ee9d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000ee9d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ec09`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ec09`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ebf1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ebf1`

## pseudocode

```c
_QWORD *__fastcall UlpHandleRequest(__int64 a1)
{
  int Request; // r15d
  __int64 v3; // rdi
  PSLIST_ENTRY v4; // rax
  _QWORD *v5; // rdx
  _QWORD *p_Next; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // r8
  _QWORD *v12; // r12
  _QWORD *v13; // rbx
  __int64 v14; // r13
  _QWORD *v15; // r12
  _QWORD *v16; // rsi
  __int64 v17; // rax
  int v18; // r14d
  _QWORD *v19; // rcx
  _QWORD *result; // rax
  __int64 v21; // rax
  _QWORD *i; // rcx
  ULONG_PTR v23; // rbx
  struct _KPROCESS *CurrentProcess; // rax
  void *CurrentServerSilo; // rdi
  __int64 v26; // rcx
  char v27; // si
  __int64 v28; // rax
  __int64 v29; // r14
  ULONG v30; // esi
  ULONG_PTR v31; // rdx
  int v32; // eax
  __int64 v33; // rdi
  char v34; // bl
  __int64 v35; // rax
  __int64 v36; // rcx
  _QWORD v37[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v38[2]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v39; // [rsp+60h] [rbp-10h]
  _QWORD *v40; // [rsp+A0h] [rbp+30h] BYREF

  Request = 0;
  v37[1] = 0;
  v37[0] = 0;
  v38[0] = v38;
  v38[1] = v38;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 33, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1);
  v3 = a1 - 160;
  v4 = ExpInterlockedFlushSList((PSLIST_HEADER)(v3 + 320));
  v5 = 0;
  p_Next = &v4->Next;
  v37[0] = 0;
  if ( v4 )
  {
    do
    {
      v7 = (_QWORD *)*p_Next;
      *p_Next = v5;
      v5 = p_Next;
      v37[0] = p_Next;
      p_Next = v7;
    }
    while ( v7 );
  }
  KeEnterCriticalRegion();
  v8 = v3 + 576;
  ExAcquirePushLockExclusiveEx(v3 + 576, 0);
  if ( (*(_DWORD *)(v3 + 632) & 2) != 0 || *(_BYTE *)(v3 + 524) )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_q(1032, 277, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, v37);
    for ( i = (_QWORD *)v37[0]; v37[0]; i = (_QWORD *)v37[0] )
    {
      v37[0] = *i;
      *i = 0;
      i[1] = 0;
      UlReleaseRequestBuffer(v3, i - 6);
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 278, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
    if ( (BYTE9(xmmword_1401A2C90) & 0x40) != 0 )
      WPP_SF_qqdd(
        782,
        34,
        WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids,
        v3,
        *(_QWORD *)(v3 + 568),
        (*(_DWORD *)(v3 + 632) >> 1) & 1,
        *(unsigned __int8 *)(v3 + 524));
  }
  else
  {
    v12 = (_QWORD *)(v3 + 568);
    v40 = (_QWORD *)(v3 + 568);
    while ( 1 )
    {
      v13 = (_QWORD *)v37[0];
      if ( !v37[0] )
        break;
      v14 = v37[0] - 48LL;
      v37[0] = *(_QWORD *)v37[0];
      v13[1] = 0;
      *v13 = 0;
      if ( (BYTE9(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_qqP(1294, 35, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, v3, *v12, v13 - 6);
      v15 = 0;
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_qqP(1032, 164, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, v3, *(_QWORD *)(v3 + 48), v13 - 6);
      v16 = *(_QWORD **)(v3 + 592);
      if ( v16 != (_QWORD *)(v3 + 584) )
      {
        v10 = *(_QWORD *)(v14 + 144);
        do
        {
          v15 = v16 - 6;
          if ( v16[12] < v10 )
            break;
          v16 = (_QWORD *)v16[1];
        }
        while ( v16 != (_QWORD *)(v3 + 584) );
      }
      if ( (BYTE9(xmmword_1401A2CA0) & 1) != 0 )
      {
        v35 = -1;
        if ( v15 )
          v35 = v15[18];
        WPP_SF_qqIqI(v10, v9, v11, v3, v13 - 6, *(_QWORD *)(v14 + 144), v15, v35);
      }
      v17 = *v16;
      if ( *(_QWORD **)(*v16 + 8LL) != v16 )
LABEL_54:
        __fastfail(3u);
      v12 = v40;
      *v13 = v17;
      v13[1] = v16;
      *(_QWORD *)(v17 + 8) = v13;
      v40 = v12;
      *v16 = v13;
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_(1032, 166, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
      v11 = *v12;
      if ( !*v12 || !*(_BYTE *)(v11 + 2440) )
      {
        if ( (BYTE9(xmmword_1401A2CA0) & 0x40) != 0 )
          WPP_SF_qqD(1294, 36, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, v3, v11, v37[0] != 0);
        if ( v37[0] )
          LOBYTE(v9) = 1;
        else
          v9 = 0;
        Request = UlpParseNextRequest(v3, v9, v38);
      }
      if ( Request < 0 )
      {
        UlpFreeReceiveBufferList(v3, v37);
        break;
      }
    }
    v8 = v3 + 576;
  }
  if ( (BYTE9(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_dqq(
      1294,
      37,
      WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids,
      (unsigned int)Request,
      v3,
      *(_QWORD *)(v3 + 568));
  if ( Request < 0 && *(_QWORD *)(v3 + 568) )
  {
    if ( (BYTE9(xmmword_1401A2C90) & 0x40) != 0 )
      WPP_SF_dqq(
        782,
        38,
        WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids,
        (unsigned int)Request,
        v3,
        *(_QWORD *)(v3 + 568));
    v36 = *(_QWORD *)(v3 + 568);
    if ( !*(_DWORD *)(v36 + 1868) )
      UlSetErrorCode(v36, 1, 0);
    v34 = byte_1401A3780;
    if ( SBYTE2(xmmword_1401A2CA0) < 0 )
      WPP_SF_d(1047, 10, WPP_b6616b8acc683c557a6f97eb9025b7cb_Traceguids, (unsigned __int8)byte_1401A3780);
    if ( v34 )
      UxPktMonTraceDropHttpReceiveWithError(*(_QWORD *)(v3 + 568), 3758116868LL, (unsigned int)Request);
    UlSendErrorResponse(v3);
  }
  ExReleasePushLockExclusiveEx(v8, 0);
  KeLeaveCriticalRegion();
  v18 = _InterlockedDecrement((volatile signed __int32 *)(v3 + 40));
  if ( UxDebugCheckRefcount && v18 <= -1 )
    UlBugCheckEx(3u, v3 + 40, 0xDu, v18);
  if ( !v18 )
  {
    v23 = v3 + 64;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(void **)(v3 + 1088);
    v26 = *(_QWORD *)v23;
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v26 || *(_QWORD *)(v23 + 16) || *(_QWORD *)(v23 + 32) )
        UlBugCheckEx(1u, v23, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      UlThreadPoolEnqueueWorkItem(0, v23, UlFreeHttpConnection, 1, CurrentServerSilo, -1);
      goto LABEL_32;
    }
    if ( v26 || *(_QWORD *)(v23 + 16) || *(_QWORD *)(v23 + 32) )
      UlBugCheckEx(1u, v23, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
    {
      v30 = 0;
      if ( (unsigned int)dword_1401A3F48 > 1 )
      {
        v30 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F60 )
          v30 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v23 + 32) = CurrentServerSilo;
      v40 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v40);
      v31 = (ULONG_PTR)(v40 + 3);
      v32 = _InterlockedIncrement((volatile signed __int32 *)v40 + 6);
      if ( UxDebugCheckRefcount && v32 <= -1 )
        UlBugCheckEx(3u, v31, 0xDu, v32);
      *(_BYTE *)(v23 + 24) = 1;
      v33 = *(_QWORD *)(qword_1401A3F50 + 8LL * v30);
      *(_QWORD *)(v23 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v33 + 16), (PSLIST_ENTRY)v23) )
      {
        KeSetEvent((PRKEVENT)(v33 + 32), 0, 0);
        if ( *(_BYTE *)(*(_QWORD *)v33 + 33LL) )
        {
          if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v33 + 68), 1, 0) )
          {
            if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
              WPP_SF_Dd(
                1304,
                18,
                WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids,
                *(unsigned int *)(v33 + 8),
                **(_DWORD **)v33);
            _InterlockedIncrement((volatile signed __int32 *)(v33 + 64));
            ExAcquireRundownProtection(&UlThreadPoolIoWorkItemsRundown);
            IoQueueWorkItemEx(*(PIO_WORKITEM *)(v33 + 56), UlpThreadPoolStarter, DelayedWorkQueue, (PVOID)v33);
          }
        }
      }
      goto LABEL_32;
    }
    v27 = 0;
    v39 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v29 = *((_QWORD *)&v39 + 1);
    }
    else
    {
      v28 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v29 = v28;
      v27 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v28, CurrentServerSilo);
        UlFreeHttpConnection(v23);
        goto LABEL_66;
      }
    }
    UlFreeHttpConnection(v23);
    if ( !v27 )
      goto LABEL_32;
LABEL_66:
    if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v29);
    PsDetachSiloFromCurrentThread(v29);
  }
LABEL_32:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 289, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, v38);
  while ( 1 )
  {
    v19 = (_QWORD *)v38[0];
    result = v38;
    if ( (_QWORD *)v38[0] == v38 )
      break;
    if ( *(_QWORD **)(v38[0] + 8LL) != v38 )
      goto LABEL_54;
    v21 = *(_QWORD *)v38[0];
    if ( *(_QWORD *)(*(_QWORD *)v38[0] + 8LL) != v38[0] )
      goto LABEL_54;
    v38[0] = *(_QWORD *)v38[0];
    *(_QWORD *)(v21 + 8) = v38;
    *v19 = 0;
    v19[1] = 0;
    IofCompleteRequest((PIRP)(v19 - 21), 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    result = (_QWORD *)WPP_SF_(1032, 290, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      return (_QWORD *)WPP_SF_(1032, 39, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000eb60  push    rbp
0x14000eb62  push    rsi
0x14000eb63  push    rdi
0x14000eb64  push    r14
0x14000eb66  push    r15
0x14000eb68  mov     rbp, rsp
0x14000eb6b  sub     rsp, 70h
0x14000eb6f  xor     r15d, r15d
0x14000eb72  mov     rdi, rcx
0x14000eb75  xor     eax, eax
0x14000eb77  mov     [rbp+var_28], rax
0x14000eb7b  mov     [rbp+var_30], rax
0x14000eb7f  lea     rax, [rbp+var_20]
0x14000eb83  mov     [rbp+var_20], rax
0x14000eb87  lea     rax, [rbp+var_20]
0x14000eb8b  mov     [rbp+var_18], rax
0x14000eb8f  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000eb96  jnz     loc_14000F2C5
0x14000eb9c  add     rdi, 0FFFFFFFFFFFFFF60h
0x14000eba3  lea     rcx, [rdi+140h]; ListHead
0x14000ebaa  call    cs:__imp_ExpInterlockedFlushSList
0x14000ebb1  nop     dword ptr [rax+rax+00h]
0x14000ebb6  xor     edx, edx
0x14000ebb8  mov     rcx, rax
0x14000ebbb  mov     [rbp+var_30], rdx
0x14000ebbf  test    rax, rax
0x14000ebc2  jz      short loc_14000EBD9
0x14000ebc4  mov     rax, [rcx]
0x14000ebc7  mov     [rcx], rdx
0x14000ebca  mov     rdx, rcx
0x14000ebcd  mov     [rbp+var_30], rcx
0x14000ebd1  mov     rcx, rax
0x14000ebd4  test    rax, rax
0x14000ebd7  jnz     short loc_14000EBC4
0x14000ebd9  mov     [rsp+70h+arg_8], rbx
0x14000ebe1  mov     [rsp+70h+arg_10], r12
0x14000ebe9  mov     [rsp+70h+arg_18], r13
0x14000ebf1  call    cs:__imp_KeEnterCriticalRegion
0x14000ebf8  nop     dword ptr [rax+rax+00h]
0x14000ebfd  lea     rsi, [rdi+240h]
0x14000ec04  xor     edx, edx
0x14000ec06  mov     rcx, rsi
0x14000ec09  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000ec10  nop     dword ptr [rax+rax+00h]
0x14000ec15  mov     eax, [rdi+278h]
0x14000ec1b  mov     r14, 0FFFFFFFFFFFFFFFFh
0x14000ec22  test    al, 2
0x14000ec24  jnz     loc_14000EE1D
0x14000ec2a  cmp     [rdi+20Ch], r15b
0x14000ec31  jnz     loc_14000EE1D
0x14000ec37  lea     r12, [rdi+238h]
0x14000ec3e  mov     [rbp+arg_0], r12
0x14000ec42  mov     rbx, [rbp+var_30]
0x14000ec46  test    rbx, rbx
0x14000ec49  jz      loc_14000ED1F
0x14000ec4f  mov     rax, [rbx]
0x14000ec52  lea     r13, [rbx-30h]
0x14000ec56  xor     esi, esi
0x14000ec58  mov     [rbp+var_30], rax
0x14000ec5c  mov     [r13+38h], rsi
0x14000ec60  mov     [rbx], rsi
0x14000ec63  test    byte ptr cs:xmmword_1401A2CA0+9, 40h
0x14000ec6a  jnz     loc_14000F1FC
0x14000ec70  mov     r12, rsi
0x14000ec73  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000ec7a  jnz     loc_14000F158
0x14000ec80  mov     rsi, [rdi+250h]
0x14000ec87  lea     rax, [rdi+248h]
0x14000ec8e  cmp     rsi, rax
0x14000ec91  jnz     loc_14000EF22
0x14000ec97  test    byte ptr cs:xmmword_1401A2CA0+9, 1
0x14000ec9e  jnz     loc_14000F2E3
0x14000eca4  mov     rax, [rsi]
0x14000eca7  cmp     [rax+8], rsi
0x14000ecab  jnz     loc_14000EF08
0x14000ecb1  mov     r12, [rbp+arg_0]
0x14000ecb5  mov     [rbx], rax
0x14000ecb8  mov     [rbx+8], rsi
0x14000ecbc  mov     [rax+8], rbx
0x14000ecc0  mov     [rbp+arg_0], r12
0x14000ecc4  mov     [rsi], rbx
0x14000ecc7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000ecce  jnz     loc_14000F1A3
0x14000ecd4  mov     r8, [r12]
0x14000ecd8  test    r8, r8
0x14000ecdb  jnz     loc_14000EF0F
0x14000ece1  test    byte ptr cs:xmmword_1401A2CA0+9, 40h
0x14000ece8  jnz     loc_14000F2FC
0x14000ecee  cmp     [rbp+var_30], 0
0x14000ecf3  jnz     loc_14000EF45
0x14000ecf9  xor     edx, edx
0x14000ecfb  lea     r8, [rbp+var_20]
0x14000ecff  mov     rcx, rdi
0x14000ed02  call    UlpParseNextRequest
0x14000ed07  mov     r15d, eax
0x14000ed0a  test    r15d, r15d
0x14000ed0d  jns     loc_14000EC42
0x14000ed13  lea     rdx, [rbp+var_30]
0x14000ed17  mov     rcx, rdi
0x14000ed1a  call    UlpFreeReceiveBufferList
0x14000ed1f  lea     rsi, [rdi+240h]
0x14000ed26  test    byte ptr cs:xmmword_1401A2CA0+9, 40h
0x14000ed2d  jnz     loc_14000F38E
0x14000ed33  mov     r12d, 1
0x14000ed39  test    r15d, r15d
0x14000ed3c  js      loc_14000F3BD
0x14000ed42  xor     edx, edx
0x14000ed44  mov     rcx, rsi
0x14000ed47  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ed4e  nop     dword ptr [rax+rax+00h]
0x14000ed53  call    cs:__imp_KeLeaveCriticalRegion
0x14000ed5a  nop     dword ptr [rax+rax+00h]
0x14000ed5f  lea     rdx, [rdi+28h]; BugCheckParameter2
0x14000ed63  lock xadd [rdx], r14d
0x14000ed68  dec     r14d
0x14000ed6b  cmp     cs:UxDebugCheckRefcount, 0
0x14000ed72  jnz     loc_14000EEEA
0x14000ed78  test    r14d, r14d
0x14000ed7b  jz      loc_14000EE99
0x14000ed81  test    byte ptr cs:xmmword_1401A2CA0+1, r12b
0x14000ed88  jnz     loc_14000F184
0x14000ed8e  mov     rcx, [rbp+var_20]
0x14000ed92  lea     rax, [rbp+var_20]
0x14000ed96  cmp     rcx, rax
0x14000ed99  jnz     short loc_14000EDCD
0x14000ed9b  test    byte ptr cs:xmmword_1401A2CA0+1, r12b
0x14000eda2  jnz     loc_14000F1BE
0x14000eda8  mov     r13, [rsp+70h+arg_18]
0x14000edb0  mov     r12, [rsp+70h+arg_10]
0x14000edb8  mov     rbx, [rsp+70h+arg_8]
0x14000edc0  add     rsp, 70h
0x14000edc4  pop     r15
0x14000edc6  pop     r14
0x14000edc8  pop     rdi
0x14000edc9  pop     rsi
0x14000edca  pop     rbp
0x14000edcb  retn
0x14000edcd  lea     rax, [rbp+var_20]
0x14000edd1  cmp     [rcx+8], rax
0x14000edd5  jnz     loc_14000EF08
0x14000eddb  mov     rax, [rcx]
0x14000edde  cmp     [rax+8], rcx
0x14000ede2  jnz     loc_14000EF08
0x14000ede8  mov     [rbp+var_20], rax
0x14000edec  lea     rdx, [rbp+var_20]
0x14000edf0  mov     [rax+8], rdx
0x14000edf4  xor     edx, edx; PriorityBoost
0x14000edf6  mov     qword ptr [rcx], 0
0x14000edfd  mov     qword ptr [rcx+8], 0
0x14000ee05  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14000ee0c  call    cs:__imp_IofCompleteRequest
0x14000ee13  nop     dword ptr [rax+rax+00h]
0x14000ee18  jmp     loc_14000ED8E
0x14000ee1d  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000ee24  jnz     loc_14000F32C
0x14000ee2a  mov     rcx, [rbp+var_30]
0x14000ee2e  test    rcx, rcx
0x14000ee31  jnz     loc_14000F34B
0x14000ee37  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000ee3e  jnz     loc_14000F373
0x14000ee44  test    byte ptr cs:xmmword_1401A2C90+9, 40h
0x14000ee4b  jz      loc_14000ED26
0x14000ee51  mov     r8d, [rdi+278h]
0x14000ee58  mov     edx, 22h ; '"'
0x14000ee5d  movzx   eax, byte ptr [rdi+20Ch]
0x14000ee64  mov     ecx, 30Eh
0x14000ee69  mov     dword ptr [rsp+70h+var_40], eax
0x14000ee6d  mov     r9, rdi
0x14000ee70  mov     rax, [rdi+238h]
0x14000ee77  shr     r8d, 1
0x14000ee7a  and     r8d, 1
0x14000ee7e  mov     dword ptr [rsp+70h+var_48], r8d
0x14000ee83  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x14000ee8a  mov     [rsp+70h+var_50], rax
0x14000ee8f  call    WPP_SF_qqdd
0x14000ee94  jmp     loc_14000ED26
0x14000ee99  lea     rbx, [rdi+40h]
0x14000ee9d  call    cs:__imp_IoGetCurrentProcess
0x14000eea4  nop     dword ptr [rax+rax+00h]
0x14000eea9  cmp     cs:UxSystemProcess, rax
0x14000eeb0  mov     rdi, [rdi+440h]
0x14000eeb7  mov     rcx, [rbx]
0x14000eeba  jnz     loc_14000F12A
0x14000eec0  test    rcx, rcx
0x14000eec3  jnz     short loc_14000EED1
0x14000eec5  cmp     [rbx+10h], rcx
0x14000eec9  jnz     short loc_14000EED1
0x14000eecb  cmp     [rbx+20h], rcx
0x14000eecf  jz      short loc_14000EF4C
0x14000eed1  mov     r9d, 0E1h; BugCheckParameter4
0x14000eed7  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14000eede  mov     rdx, rbx; BugCheckParameter2
0x14000eee1  mov     rcx, r12; BugCheckParameter1
0x14000eee4  call    UlBugCheckEx
0x14000eeea  cmp     r14d, 0FFFFFFFFh
0x14000eeee  jg      loc_14000ED78
0x14000eef4  movsxd  r9, r14d; BugCheckParameter4
0x14000eef7  mov     ecx, 3; BugCheckParameter1
0x14000eefc  mov     r8d, 0Dh; BugCheckParameter3
0x14000ef02  call    UlBugCheckEx
0x14000ef08  mov     ecx, 3
0x14000ef0d  int     29h; Win8: RtlFailFast(ecx)
0x14000ef0f  cmp     byte ptr [r8+988h], 0
0x14000ef17  jnz     loc_14000ED0A
0x14000ef1d  jmp     loc_14000ECE1
0x14000ef22  mov     rcx, [r13+90h]
0x14000ef29  cmp     [rsi+60h], rcx
0x14000ef2d  lea     r12, [rsi-30h]
0x14000ef31  jb      loc_14000EC97
0x14000ef37  mov     rsi, [rsi+8]
0x14000ef3b  cmp     rsi, rax
0x14000ef3e  jnz     short loc_14000EF29
0x14000ef40  jmp     loc_14000EC97
0x14000ef45  mov     dl, 1
0x14000ef47  jmp     loc_14000ECFB
0x14000ef4c  call    cs:__imp_KeGetCurrentIrql
0x14000ef53  nop     dword ptr [rax+rax+00h]
0x14000ef58  test    al, al
0x14000ef5a  jnz     short loc_14000EFC5
0x14000ef5c  xor     sil, sil
0x14000ef5f  xorps   xmm0, xmm0
0x14000ef62  movups  [rbp+var_10], xmm0
0x14000ef66  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000ef6a  jz      loc_14000F121
0x14000ef70  mov     rcx, rdi
0x14000ef73  call    cs:__imp_PsAttachSiloToCurrentThread
0x14000ef7a  nop     dword ptr [rax+rax+00h]
0x14000ef7f  mov     r14, rax
0x14000ef82  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14000ef89  movzx   esi, r12b
0x14000ef8d  jnz     loc_14000F24F
0x14000ef93  mov     rcx, rbx
0x14000ef96  call    UlFreeHttpConnection
0x14000ef9b  test    sil, sil
0x14000ef9e  jz      loc_14000ED81
0x14000efa4  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14000efab  jnz     loc_14000F403
0x14000efb1  mov     rcx, r14
0x14000efb4  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14000efbb  nop     dword ptr [rax+rax+00h]
0x14000efc0  jmp     loc_14000ED81
0x14000efc5  xor     esi, esi
0x14000efc7  cmp     cs:dword_1401A3F48, r12d
0x14000efce  jbe     short loc_14000EFF5
0x14000efd0  xor     ecx, ecx; ProcNumber
0x14000efd2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000efd9  nop     dword ptr [rax+rax+00h]
0x14000efde  xor     edx, edx
0x14000efe0  div     cs:UxNumberOfProcessors
0x14000efe6  cmp     cs:byte_1401A3F60, 0
0x14000efed  mov     esi, edx
0x14000efef  jnz     loc_14000F421
0x14000eff5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000eff9  jnz     short loc_14000F00A
0x14000effb  call    cs:__imp_PsGetCurrentServerSilo
0x14000f002  nop     dword ptr [rax+rax+00h]
0x14000f007  mov     rdi, rax
0x14000f00a  mov     [rbx+20h], rdi
0x14000f00e  mov     [rbp+arg_0], 0
0x14000f016  test    rdi, rdi
0x14000f019  jnz     loc_14000F434
0x14000f01f  mov     edx, cs:UxPodMonitorSlot
0x14000f025  lea     r8, [rbp+arg_0]
0x14000f029  mov     rcx, rdi
0x14000f02c  call    cs:__imp_PsGetPermanentSiloContext
0x14000f033  nop     dword ptr [rax+rax+00h]
0x14000f038  mov     rdx, [rbp+arg_0]
0x14000f03c  mov     eax, r12d
0x14000f03f  add     rdx, 18h; BugCheckParameter2
0x14000f043  lock xadd [rdx], eax
0x14000f047  inc     eax
0x14000f049  cmp     cs:UxDebugCheckRefcount, 0
0x14000f050  jnz     loc_14000F104
0x14000f056  mov     [rbx+18h], r12b
0x14000f05a  mov     rdx, rbx; ListEntry
0x14000f05d  mov     rax, cs:qword_1401A3F50
0x14000f064  mov     ecx, esi
0x14000f066  mov     rdi, [rax+rcx*8]
0x14000f06a  lea     rax, UlFreeHttpConnection
0x14000f071  mov     [rbx+10h], rax
0x14000f075  lea     rcx, [rdi+10h]; ListHead
0x14000f079  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000f080  nop     dword ptr [rax+rax+00h]
0x14000f085  test    rax, rax
0x14000f088  jnz     loc_14000ED81
0x14000f08e  lea     rcx, [rdi+20h]; Event
0x14000f092  xor     r8d, r8d; Wait
0x14000f095  xor     edx, edx; Increment
0x14000f097  call    cs:__imp_KeSetEvent
0x14000f09e  nop     dword ptr [rax+rax+00h]
0x14000f0a3  mov     rax, [rdi]
0x14000f0a6  cmp     byte ptr [rax+21h], 0
0x14000f0aa  jz      loc_14000ED81
0x14000f0b0  xor     eax, eax
0x14000f0b2  lock cmpxchg [rdi+44h], r12d
0x14000f0b8  jnz     loc_14000ED81
0x14000f0be  test    byte ptr cs:xmmword_1401A2CA0+0Bh, r12b
0x14000f0c5  jnz     loc_14000F44D
0x14000f0cb  lock inc dword ptr [rdi+40h]
0x14000f0cf  lea     rcx, UlThreadPoolIoWorkItemsRundown; RunRef
  ... truncated ...
```

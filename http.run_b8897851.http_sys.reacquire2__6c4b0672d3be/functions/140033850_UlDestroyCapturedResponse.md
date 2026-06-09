# UlDestroyCapturedResponse

- ea: `0x140033850`
- end: `0x14003426e`
- name: `UlDestroyCapturedResponse`
- size: `2590`
- prototype: ``
- caller_count: `16`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001d270`
- `0x140033330`
- `0x1400354c0`
- `0x1400474f0`
- `0x1400548f4`
- `0x1400ba79c`
- `0x1400c9fd0`
- `0x1400ca304`
- `0x1400eacc0`
- `0x1400eb5a0`
- `0x1400ece74`
- `0x1400f1ad8`
- `0x1400f3fdc`
- `0x140128f38`
- `0x14012ae10`
- `0x14012c51c`

## callees

- `0x14000a350`
- `0x14000c390`
- `0x140022610`
- `0x140033850`
- `0x140038ea0`
- `0x140049d28`
- `0x14005dff0`
- `0x14006e50c`
- `0x1400879b0`
- `0x1400aedc0`
- `0x1400c7aa8`
- `0x1400ca8c4`
- `0x14013dc78`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9e44`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140033b74`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033b74`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140033dec`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140033dec`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400339db`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033a4a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033ab9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033c4c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400339db`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033a4a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033ab9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033c4c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033d42`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033d42`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140033d9a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140033d9a`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400341e5`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400341e5`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140033ba0`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140033ba0`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140033bdc`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140033bdc`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140033e67`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140033e67`
- `ntoskrnl!KeSetEvent` at `0x140033e0a`
- `ntoskrnl!KeSetEvent` at `0x140033e0a`
- `ntoskrnl!IoFreeMdl` at `0x1400338fa`
- `ntoskrnl!IoFreeMdl` at `0x1400338fa`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140033d6b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140033d6b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140033f13`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140033f13`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140033e4a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140033e4a`
- `ntoskrnl!ObfDereferenceObject` at `0x140033d18`
- `ntoskrnl!ObfDereferenceObject` at `0x140033d18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033cb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033cc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033cde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f77`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003411b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034135`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003414f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034169`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003417e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003419b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033cb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033cc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033cde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f77`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003411b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034135`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003414f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034169`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003417e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003419b`

## pseudocode

```c
void __fastcall UlDestroyCapturedResponse(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  volatile signed __int32 *v5; // rcx
  __int64 v6; // rbx
  unsigned int i; // ebp
  __int64 v8; // rdi
  int v9; // eax
  struct _MDL *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rdi
  unsigned __int64 v14; // rsi
  void *v15; // rdi
  unsigned __int64 v16; // rsi
  void *v17; // rdi
  unsigned __int64 v18; // rsi
  __int64 v19; // rax
  volatile signed __int32 *v20; // rdx
  int v21; // r14d
  __int64 v22; // rsi
  __int64 v23; // rdi
  void *CurrentServerSilo; // rsi
  char v25; // bp
  __int64 v26; // rax
  __int64 v27; // r14
  bool v28; // zf
  unsigned __int64 v29; // rdi
  void *v30; // rcx
  ULONG v31; // ebp
  ULONG_PTR v32; // rdx
  int v33; // eax
  __int64 v34; // r14
  __int64 v35; // rcx
  ULONG_PTR v36; // rdx
  __int64 v37; // rdi
  USHORT CurrentNodeNumber; // ax
  int v39; // eax
  __int128 v40; // [rsp+30h] [rbp-98h] BYREF
  _DWORD v41[24]; // [rsp+40h] [rbp-88h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 99, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, a1);
  v5 = *(volatile signed __int32 **)(a1 - 472);
  v6 = a1 - 608;
  if ( v5 )
  {
    v39 = _InterlockedDecrement(v5 + 1);
    if ( UxDebugCheckRefcount && v39 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v5 + 1), 0x23u, v39);
    if ( !v39 )
      UcFreeStream((PVOID)v5);
    *(_QWORD *)(v6 + 136) = 0;
  }
  for ( i = 0; i < *(_DWORD *)(v6 + 880); ++i )
  {
    v8 = *(_QWORD *)(v6 + 888) + 80LL * i;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_q(1033, 97, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, *(_QWORD *)(v6 + 888) + 80LL * i);
    if ( v8 )
    {
      v9 = *(_DWORD *)v8;
      if ( *(_DWORD *)v8 == 3 )
      {
        v10 = *(struct _MDL **)(v8 + 8);
        if ( v10 )
        {
          IoFreeMdl(v10);
          *(_QWORD *)(v8 + 8) = 0;
        }
        v11 = *(void **)(v8 + 16);
        if ( v11 )
        {
          UlCheckinUriCacheEntry(v11);
          *(_QWORD *)(v8 + 16) = 0;
        }
      }
      else if ( v9 == 2 )
      {
        if ( *(_QWORD *)(v8 + 40) )
        {
          if ( SBYTE8(xmmword_1401A2CA0) < 0 )
            WPP_SF_q(1287, 13, WPP_356047d6fb313977e1ed462fdcc3e5cd_Traceguids, v8 + 24);
          v30 = *(void **)(v8 + 40);
          if ( v30 )
          {
            ObfDereferenceObject(v30);
            *(_QWORD *)(v8 + 40) = 0;
          }
          *(_DWORD *)(v8 + 24) = 1701603686;
        }
      }
      else if ( v9 == 4 )
      {
        v35 = *(_QWORD *)(v8 + 24);
        if ( v35 )
        {
          UlHkeDereferenceCalloutContext(v35, 52);
          *(_QWORD *)(v8 + 24) = 0;
        }
      }
    }
    *(_DWORD *)v8 = 0;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1033, 98, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids);
  }
  if ( *(_QWORD *)(v6 + 544) )
    UlHkeBuilderCleanup();
  if ( *(_BYTE *)(v6 + 52) )
    ExFreePoolWithTag(*(PVOID *)(v6 + 192), 0);
  if ( *(_BYTE *)(v6 + 53) )
    ExFreePoolWithTag(*(PVOID *)(v6 + 208), 0);
  if ( *(_BYTE *)(v6 + 54) )
    ExFreePoolWithTag(*(PVOID *)(v6 + 696), 0);
  if ( *(_BYTE *)(v6 + 55) )
  {
    ExFreePoolWithTag(*(PVOID *)(v6 + 736), 0);
    ExFreePoolWithTag(*(PVOID *)(v6 + 672), 0);
  }
  if ( *(_QWORD *)(v6 + 512) )
    UlDestroyLogDataBuffer();
  v12 = *(void **)(v6 + 256);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  v13 = *(void **)(v6 + 336);
  if ( v13 )
  {
    if ( *(_BYTE *)(v6 + 344) )
    {
      if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A0490, *(_QWORD *)(v6 + 336));
      }
      else
      {
        v14 = qword_1401A0490 + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v6 + 348) + 1) << 7);
        if ( !*(_BYTE *)(v14 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0490, v14 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v14 + 64), v13);
      }
    }
    else
    {
      ExFreePoolWithTag(*(PVOID *)(v6 + 336), 0);
    }
  }
  *(_OWORD *)(v6 + 328) = 0;
  *(_QWORD *)(v6 + 344) = 0;
  v15 = *(void **)(v6 + 296);
  if ( v15 )
  {
    if ( *(_BYTE *)(v6 + 304) )
    {
      if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A0490, *(_QWORD *)(v6 + 296));
      }
      else
      {
        v16 = qword_1401A0490 + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v6 + 308) + 1) << 7);
        if ( !*(_BYTE *)(v16 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0490, v16 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v16 + 64), v15);
      }
    }
    else
    {
      ExFreePoolWithTag(*(PVOID *)(v6 + 296), 0);
    }
  }
  *(_OWORD *)(v6 + 288) = 0;
  *(_QWORD *)(v6 + 304) = 0;
  v17 = *(void **)(v6 + 376);
  if ( v17 )
  {
    if ( *(_BYTE *)(v6 + 384) )
    {
      if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A0490, *(_QWORD *)(v6 + 376));
      }
      else
      {
        v18 = qword_1401A0490 + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v6 + 388) + 1) << 7);
        if ( !*(_BYTE *)(v18 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0490, v18 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v18 + 64), v17);
      }
    }
    else
    {
      ExFreePoolWithTag(*(PVOID *)(v6 + 376), 0);
    }
  }
  v19 = 0;
  *(_OWORD *)(v6 + 368) = 0;
  *(_QWORD *)(v6 + 384) = 0;
  v20 = (volatile signed __int32 *)(*(_QWORD *)(v6 + 24) + 48LL);
  v21 = _InterlockedDecrement(v20);
  if ( UxDebugCheckRefcount && v21 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v20, 0x17u, v21);
  if ( !v21 )
  {
    v22 = *(_QWORD *)(v6 + 24);
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    {
      if ( v22 )
        v19 = *(_QWORD *)(v22 + 64);
      WPP_SF_qq(1032, 40, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v22, v19);
    }
    if ( (*(_DWORD *)(v22 + 2264) & 1) != 0 || *(_QWORD *)(v22 + 2288) || *(_QWORD *)(v22 + 2312) )
    {
      v36 = v22 + 1248;
      if ( *(_QWORD *)(v22 + 1248) || *(_QWORD *)(v22 + 1264) || *(_QWORD *)(v22 + 1280) )
        UlBugCheckEx(1u, v36, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x645u);
      LOBYTE(a4) = 1;
      UlThreadPoolEnqueueWorkItem(0, v36, UlpFreeHttpRequest, a4, *(_QWORD *)(*(_QWORD *)(v22 + 24) + 1088LL), -1);
      goto LABEL_65;
    }
    v23 = v22 + 1248;
    if ( *(_QWORD *)(v22 + 1248) || *(_QWORD *)(v22 + 1264) || *(_QWORD *)(v22 + 1280) )
      UlBugCheckEx(1u, v22 + 1248, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x64Du);
    CurrentServerSilo = *(void **)(*(_QWORD *)(v22 + 24) + 1088LL);
    if ( KeGetCurrentIrql() )
    {
      v31 = 0;
      if ( (unsigned int)dword_1401A3F48 > 1 )
      {
        v31 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F60 )
          v31 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v23 + 32) = CurrentServerSilo;
      *(_QWORD *)&v40 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v40);
      v32 = v40 + 24;
      v33 = _InterlockedIncrement((volatile signed __int32 *)(v40 + 24));
      if ( UxDebugCheckRefcount && v33 <= -1 )
        UlBugCheckEx(3u, v32, 0xDu, v33);
      *(_BYTE *)(v23 + 24) = 1;
      v34 = *(_QWORD *)(qword_1401A3F50 + 8LL * v31);
      *(_QWORD *)(v23 + 16) = UlpFreeHttpRequest;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v34 + 16), (PSLIST_ENTRY)v23) )
      {
        KeSetEvent((PRKEVENT)(v34 + 32), 0, 0);
        if ( *(_BYTE *)(*(_QWORD *)v34 + 33LL) )
        {
          if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v34 + 68), 1, 0) )
          {
            if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
              WPP_SF_Dd(
                1304,
                18,
                WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids,
                *(unsigned int *)(v34 + 8),
                **(_DWORD **)v34);
            _InterlockedIncrement((volatile signed __int32 *)(v34 + 64));
            ExAcquireRundownProtection(&UlThreadPoolIoWorkItemsRundown);
            IoQueueWorkItemEx(*(PIO_WORKITEM *)(v34 + 56), UlpThreadPoolStarter, DelayedWorkQueue, (PVOID)v34);
          }
        }
      }
      goto LABEL_65;
    }
    v25 = 0;
    v40 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v27 = *((_QWORD *)&v40 + 1);
    }
    else
    {
      v26 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v27 = v26;
      v25 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v26, CurrentServerSilo);
        UlpFreeHttpRequest(v23);
        goto LABEL_62;
      }
    }
    UlpFreeHttpRequest(v23);
    if ( !v25 )
    {
LABEL_65:
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_(1032, 41, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
      goto LABEL_67;
    }
LABEL_62:
    if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v27);
    PsDetachSiloFromCurrentThread(v27);
    goto LABEL_65;
  }
LABEL_67:
  *(_QWORD *)(v6 + 24) = 0;
  if ( *(_BYTE *)(v6 + 44) )
  {
    v28 = UxDebugDisableLookaside == 0;
    *(_DWORD *)(v6 + 16) = 1380535413;
    if ( v28 )
    {
      if ( UxCompactMode )
      {
        v37 = qword_1401A0250;
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        PplFreeToLookasideListProcessor(v37, v6, CurrentNodeNumber);
      }
      else
      {
        v29 = qword_1401A0250 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v6 + 1) << 7);
        if ( !*(_BYTE *)(v29 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0250, v29 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v29 + 64), (PVOID)v6);
      }
    }
    else
    {
      memset(v41, 0, sizeof(v41));
      v41[10] = dword_1401A0268;
      ((void (__fastcall *)(__int64, _DWORD *))off_1401A0278)(v6, v41);
    }
  }
  else
  {
    *(_DWORD *)(v6 + 16) = 1919503477;
    ExFreePoolWithTag((PVOID)v6, 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1033, 100, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids);
}

```

## disassembly

```asm
0x140033850  push    rbx
0x140033852  push    r14
0x140033854  push    r15
0x140033856  sub     rsp, 0B0h
0x14003385d  mov     rax, cs:__security_cookie
0x140033864  xor     rax, rsp
0x140033867  mov     [rsp+0C8h+var_28], rax
0x14003386f  mov     rbx, rcx
0x140033872  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140033879  jnz     loc_14003407D
0x14003387f  mov     rcx, [rbx-1D8h]; P
0x140033886  add     rbx, 0FFFFFFFFFFFFFDA0h
0x14003388d  xor     r15d, r15d
0x140033890  mov     r14d, 0FFFFFFFFh
0x140033896  test    rcx, rcx
0x140033899  jnz     loc_14003403E
0x14003389f  mov     [rsp+0C8h+arg_8], rbp
0x1400338a7  mov     ebp, r15d
0x1400338aa  mov     [rsp+0C8h+arg_10], rsi
0x1400338b2  mov     [rsp+0C8h+arg_18], rdi
0x1400338ba  cmp     [rbx+370h], r15d
0x1400338c1  jbe     short loc_140033931
0x1400338c3  mov     eax, ebp
0x1400338c5  lea     rdi, [rax+rax*4]
0x1400338c9  shl     rdi, 4
0x1400338cd  add     rdi, [rbx+378h]
0x1400338d4  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400338db  jnz     loc_1400340A2
0x1400338e1  test    rdi, rdi
0x1400338e4  jz      short loc_140033917
0x1400338e6  mov     eax, [rdi]
0x1400338e8  cmp     eax, 3
0x1400338eb  jnz     loc_140033CEF
0x1400338f1  mov     rcx, [rdi+8]; Mdl
0x1400338f5  test    rcx, rcx
0x1400338f8  jz      short loc_14003390A
0x1400338fa  call    cs:__imp_IoFreeMdl
0x140033901  nop     dword ptr [rax+rax+00h]
0x140033906  mov     [rdi+8], r15
0x14003390a  mov     rcx, [rdi+10h]; P
0x14003390e  test    rcx, rcx
0x140033911  jnz     loc_1400340C0
0x140033917  mov     [rdi], r15d
0x14003391a  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140033921  jnz     loc_1400340ED
0x140033927  inc     ebp
0x140033929  cmp     ebp, [rbx+370h]
0x14003392f  jb      short loc_1400338C3
0x140033931  mov     rcx, [rbx+220h]
0x140033938  test    rcx, rcx
0x14003393b  jnz     loc_140034108
0x140033941  cmp     [rbx+34h], r15b
0x140033945  jnz     loc_140034112
0x14003394b  cmp     [rbx+35h], r15b
0x14003394f  jnz     loc_14003412C
0x140033955  cmp     [rbx+36h], r15b
0x140033959  jnz     loc_140034146
0x14003395f  cmp     [rbx+37h], r15b
0x140033963  jnz     loc_140034160
0x140033969  mov     rcx, [rbx+200h]
0x140033970  test    rcx, rcx
0x140033973  jnz     loc_14003418F
0x140033979  mov     rcx, [rbx+100h]; P
0x140033980  test    rcx, rcx
0x140033983  jnz     loc_140034199
0x140033989  mov     rdi, [rbx+150h]
0x140033990  test    rdi, rdi
0x140033993  jz      short loc_1400339E7
0x140033995  cmp     [rbx+158h], r15b
0x14003399c  jz      loc_140033CAD
0x1400339a2  cmp     cs:UxCompactMode, r15b
0x1400339a9  mov     rcx, cs:qword_1401A0490
0x1400339b0  jnz     loc_140033F88
0x1400339b6  mov     esi, [rbx+15Ch]
0x1400339bc  inc     esi
0x1400339be  shl     rsi, 7
0x1400339c2  add     rsi, rcx
0x1400339c5  movzx   eax, byte ptr [rsi+0B0h]
0x1400339cc  test    al, al
0x1400339ce  jz      loc_140033FDB
0x1400339d4  mov     rdx, rdi; Entry
0x1400339d7  lea     rcx, [rsi+40h]; Lookaside
0x1400339db  call    cs:__imp_ExFreeToLookasideListEx
0x1400339e2  nop     dword ptr [rax+rax+00h]
0x1400339e7  xor     eax, eax
0x1400339e9  xorps   xmm0, xmm0
0x1400339ec  movups  xmmword ptr [rbx+148h], xmm0
0x1400339f3  mov     [rbx+158h], rax
0x1400339fa  mov     rdi, [rbx+128h]
0x140033a01  test    rdi, rdi
0x140033a04  jz      short loc_140033A56
0x140033a06  cmp     [rbx+130h], al
0x140033a0c  jz      loc_140033CC3
0x140033a12  cmp     cs:UxCompactMode, al
0x140033a18  mov     rcx, cs:qword_1401A0490
0x140033a1f  jnz     loc_140033F95
0x140033a25  mov     esi, [rbx+134h]
0x140033a2b  inc     esi
0x140033a2d  shl     rsi, 7
0x140033a31  add     rsi, rcx
0x140033a34  movzx   eax, byte ptr [rsi+0B0h]
0x140033a3b  test    al, al
0x140033a3d  jz      loc_140033FE9
0x140033a43  mov     rdx, rdi; Entry
0x140033a46  lea     rcx, [rsi+40h]; Lookaside
0x140033a4a  call    cs:__imp_ExFreeToLookasideListEx
0x140033a51  nop     dword ptr [rax+rax+00h]
0x140033a56  xor     eax, eax
0x140033a58  xorps   xmm0, xmm0
0x140033a5b  movups  xmmword ptr [rbx+120h], xmm0
0x140033a62  mov     [rbx+130h], rax
0x140033a69  mov     rdi, [rbx+178h]
0x140033a70  test    rdi, rdi
0x140033a73  jz      short loc_140033AC5
0x140033a75  cmp     [rbx+180h], al
0x140033a7b  jz      loc_140033CD9
0x140033a81  cmp     cs:UxCompactMode, al
0x140033a87  mov     rcx, cs:qword_1401A0490
0x140033a8e  jnz     loc_140033FA2
0x140033a94  mov     esi, [rbx+184h]
0x140033a9a  inc     esi
0x140033a9c  shl     rsi, 7
0x140033aa0  add     rsi, rcx
0x140033aa3  movzx   eax, byte ptr [rsi+0B0h]
0x140033aaa  test    al, al
0x140033aac  jz      loc_140033FF7
0x140033ab2  mov     rdx, rdi; Entry
0x140033ab5  lea     rcx, [rsi+40h]; Lookaside
0x140033ab9  call    cs:__imp_ExFreeToLookasideListEx
0x140033ac0  nop     dword ptr [rax+rax+00h]
0x140033ac5  xor     eax, eax
0x140033ac7  xorps   xmm0, xmm0
0x140033aca  movups  xmmword ptr [rbx+170h], xmm0
0x140033ad1  mov     [rbx+180h], rax
0x140033ad8  mov     rdx, [rbx+18h]
0x140033adc  add     rdx, 30h ; '0'; BugCheckParameter2
0x140033ae0  lock xadd [rdx], r14d
0x140033ae5  dec     r14d
0x140033ae8  cmp     cs:UxDebugCheckRefcount, al
0x140033aee  jnz     loc_140033E78
0x140033af4  test    r14d, r14d
0x140033af7  jnz     loc_140033BF5
0x140033afd  mov     rsi, [rbx+18h]
0x140033b01  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140033b08  jnz     loc_140033FAF
0x140033b0e  mov     eax, [rsi+8D8h]
0x140033b14  test    al, 1
0x140033b16  jnz     loc_140033EDC
0x140033b1c  cmp     [rsi+8F0h], r15
0x140033b23  jnz     loc_140033EDC
0x140033b29  cmp     [rsi+908h], r15
0x140033b30  jnz     loc_140033EDC
0x140033b36  lea     rdi, [rsi+4E0h]
0x140033b3d  cmp     [rdi], r15
0x140033b40  jnz     short loc_140033B4E
0x140033b42  cmp     [rdi+10h], r15
0x140033b46  jnz     short loc_140033B4E
0x140033b48  cmp     [rdi+20h], r15
0x140033b4c  jz      short loc_140033B69
0x140033b4e  mov     r9d, 64Dh; BugCheckParameter4
0x140033b54  lea     r8, aMinioHttpSysHt; "minio\\http\\sys\\httpconn.c"
0x140033b5b  mov     rdx, rdi; BugCheckParameter2
0x140033b5e  mov     ecx, 1; BugCheckParameter1
0x140033b63  call    UlBugCheckEx
0x140033b69  mov     rax, [rsi+18h]
0x140033b6d  mov     rsi, [rax+440h]
0x140033b74  call    cs:__imp_KeGetCurrentIrql
0x140033b7b  nop     dword ptr [rax+rax+00h]
0x140033b80  test    al, al
0x140033b82  jnz     loc_140033D34
0x140033b88  xor     bpl, bpl
0x140033b8b  xorps   xmm0, xmm0
0x140033b8e  movups  [rsp+0C8h+var_98], xmm0
0x140033b93  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140033b97  jz      loc_140033F33
0x140033b9d  mov     rcx, rsi
0x140033ba0  call    cs:__imp_PsAttachSiloToCurrentThread
0x140033ba7  nop     dword ptr [rax+rax+00h]
0x140033bac  mov     r14, rax
0x140033baf  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140033bb6  mov     bpl, 1
0x140033bb9  jnz     loc_140034005
0x140033bbf  mov     rcx, rdi
0x140033bc2  call    UlpFreeHttpRequest
0x140033bc7  test    bpl, bpl
0x140033bca  jz      short loc_140033BE8
0x140033bcc  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140033bd3  jnz     loc_1400341AC
0x140033bd9  mov     rcx, r14
0x140033bdc  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140033be3  nop     dword ptr [rax+rax+00h]
0x140033be8  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140033bef  jnz     loc_14003421E
0x140033bf5  mov     [rbx+18h], r15
0x140033bf9  cmp     [rbx+2Ch], r15b
0x140033bfd  jz      loc_140033F6B
0x140033c03  cmp     cs:UxDebugDisableLookaside, r15b
0x140033c0a  mov     dword ptr [rbx+10h], 52494C75h
0x140033c11  jnz     loc_140034239
0x140033c17  cmp     cs:UxCompactMode, r15b
0x140033c1e  jnz     loc_140033F0C
0x140033c24  mov     edi, [rbx]
0x140033c26  mov     rcx, cs:qword_1401A0250
0x140033c2d  inc     edi
0x140033c2f  shl     rdi, 7
0x140033c33  add     rdi, rcx
0x140033c36  movzx   eax, byte ptr [rdi+0B0h]
0x140033c3d  test    al, al
0x140033c3f  jz      loc_140034030
0x140033c45  mov     rdx, rbx; Entry
0x140033c48  lea     rcx, [rdi+40h]; Lookaside
0x140033c4c  call    cs:__imp_ExFreeToLookasideListEx
0x140033c53  nop     dword ptr [rax+rax+00h]
0x140033c58  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140033c5f  jz      short loc_140033C77
0x140033c61  mov     edx, 64h ; 'd'
0x140033c66  lea     r8, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids
0x140033c6d  mov     ecx, 409h
0x140033c72  call    WPP_SF_
0x140033c77  mov     rsi, [rsp+0C8h+arg_10]
0x140033c7f  mov     rbp, [rsp+0C8h+arg_8]
0x140033c87  mov     rdi, [rsp+0C8h+arg_18]
0x140033c8f  mov     rcx, [rsp+0C8h+var_28]
0x140033c97  xor     rcx, rsp; StackCookie
0x140033c9a  call    __security_check_cookie
0x140033c9f  add     rsp, 0B0h
0x140033ca6  pop     r15
0x140033ca8  pop     r14
0x140033caa  pop     rbx
0x140033cab  retn
0x140033cad  xor     edx, edx; Tag
0x140033caf  mov     rcx, rdi; P
0x140033cb2  call    cs:__imp_ExFreePoolWithTag
0x140033cb9  nop     dword ptr [rax+rax+00h]
0x140033cbe  jmp     loc_1400339E7
0x140033cc3  xor     edx, edx; Tag
0x140033cc5  mov     rcx, rdi; P
0x140033cc8  call    cs:__imp_ExFreePoolWithTag
0x140033ccf  nop     dword ptr [rax+rax+00h]
0x140033cd4  jmp     loc_140033A56
0x140033cd9  xor     edx, edx; Tag
0x140033cdb  mov     rcx, rdi; P
0x140033cde  call    cs:__imp_ExFreePoolWithTag
0x140033ce5  nop     dword ptr [rax+rax+00h]
0x140033cea  jmp     loc_140033AC5
0x140033cef  cmp     eax, 2
0x140033cf2  jnz     loc_140033EB3
0x140033cf8  cmp     [rdi+28h], r15
0x140033cfc  jz      loc_140033917
0x140033d02  cmp     byte ptr cs:xmmword_1401A2CA0+8, r15b
0x140033d09  jl      loc_1400340CE
0x140033d0f  mov     rcx, [rdi+28h]; Object
0x140033d13  test    rcx, rcx
0x140033d16  jz      short loc_140033D28
0x140033d18  call    cs:__imp_ObfDereferenceObject
0x140033d1f  nop     dword ptr [rax+rax+00h]
0x140033d24  mov     [rdi+28h], r15
0x140033d28  mov     dword ptr [rdi+18h], 656C6966h
0x140033d2f  jmp     loc_140033917
0x140033d34  cmp     cs:dword_1401A3F48, 1
0x140033d3b  mov     ebp, r15d
0x140033d3e  jbe     short loc_140033D65
0x140033d40  xor     ecx, ecx; ProcNumber
0x140033d42  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140033d49  nop     dword ptr [rax+rax+00h]
0x140033d4e  xor     edx, edx
0x140033d50  div     cs:UxNumberOfProcessors
0x140033d56  cmp     cs:byte_1401A3F60, r15b
0x140033d5d  mov     ebp, edx
0x140033d5f  jnz     loc_1400341CA
0x140033d65  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140033d69  jnz     short loc_140033D7A
0x140033d6b  call    cs:__imp_PsGetCurrentServerSilo
0x140033d72  nop     dword ptr [rax+rax+00h]
0x140033d77  mov     rsi, rax
0x140033d7a  mov     [rdi+20h], rsi
0x140033d7e  mov     qword ptr [rsp+0C8h+var_98], r15
0x140033d83  test    rsi, rsi
0x140033d86  jnz     loc_1400341DD
0x140033d8c  mov     edx, cs:UxPodMonitorSlot
0x140033d92  lea     r8, [rsp+0C8h+var_98]
0x140033d97  mov     rcx, rsi
0x140033d9a  call    cs:__imp_PsGetPermanentSiloContext
0x140033da1  nop     dword ptr [rax+rax+00h]
0x140033da6  mov     rdx, qword ptr [rsp+0C8h+var_98]
0x140033dab  mov     esi, 1
0x140033db0  add     rdx, 18h; BugCheckParameter2
0x140033db4  mov     eax, esi
0x140033db6  lock xadd [rdx], eax
0x140033dba  inc     eax
0x140033dbc  cmp     cs:UxDebugCheckRefcount, r15b
0x140033dc3  jnz     loc_140033E96
0x140033dc9  mov     [rdi+18h], sil
0x140033dcd  lea     r8, UlpFreeHttpRequest
0x140033dd4  mov     rax, cs:qword_1401A3F50
0x140033ddb  mov     rdx, rdi; ListEntry
0x140033dde  mov     ecx, ebp
0x140033de0  mov     r14, [rax+rcx*8]
0x140033de4  mov     [rdi+10h], r8
0x140033de8  lea     rcx, [r14+10h]; ListHead
  ... truncated ...
```

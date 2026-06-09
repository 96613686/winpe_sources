# UlFreeBuildTracker

- ea: `0x140033310`
- end: `0x140033822`
- name: `UlFreeBuildTracker`
- size: `1298`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `6`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140032fb0`
- `0x1400833a0`
- `0x140096790`
- `0x1400bc890`
- `0x1400c9b50`
- `0x1400d1f64`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140033310`
- `0x140033830`
- `0x140035a50`
- `0x14005e030`
- `0x1400a031c`
- `0x14013dd68`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400333f6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033699`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400333f6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033699`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140033590`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140033590`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400334e6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400334e6`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003353f`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003353f`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400337e8`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400337e8`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140033427`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400336bf`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140033427`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400336bf`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140033463`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140033463`
- `ntoskrnl!IoFreeIrp` at `0x140033336`
- `ntoskrnl!IoFreeIrp` at `0x140033336`
- `ntoskrnl!KeSetEvent` at `0x1400335ae`
- `ntoskrnl!KeSetEvent` at `0x1400335ae`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140033510`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140033510`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400334a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400334a7`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400335cb`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400335cb`

## pseudocode

```c
void __fastcall UlFreeBuildTracker(_QWORD *P)
{
  IRP *v2; // rcx
  __int64 v3; // rsi
  int v4; // eax
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rsi
  void *CurrentServerSilo; // rbp
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  char v12; // r14
  __int64 v13; // rax
  __int64 v14; // r15
  volatile signed __int32 *v15; // rdx
  int v16; // edi
  ULONG v17; // r14d
  ULONG_PTR v18; // rdx
  int v19; // ecx
  __int64 v20; // rbp
  __int64 *v21; // r14
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v23; // r9
  __int64 v24; // rsi
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int128 v30; // [rsp+30h] [rbp-38h] BYREF
  __int64 v31; // [rsp+70h] [rbp+8h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 95, WPP_173ede4a325638307373c19033e5a27a_Traceguids, P);
  v2 = (IRP *)P[6];
  if ( v2 )
  {
    IoFreeIrp(v2);
    P[6] = 0;
  }
  v3 = P[4];
  if ( v3 )
  {
    v4 = _InterlockedDecrement((volatile signed __int32 *)(v3 + 40));
    if ( UxDebugCheckRefcount && v4 <= -1 )
      UlBugCheckEx(3u, v3 + 40, 0x14u, v4);
    if ( v4 )
      goto LABEL_8;
    v21 = (__int64 *)(v3 + 64);
    CurrentProcess = IoGetCurrentProcess();
    v24 = *(_QWORD *)(v3 + 1088);
    v25 = *v21;
    if ( UxSystemProcess == CurrentProcess )
    {
      if ( v25 || v21[2] || v21[4] )
        UlBugCheckEx(1u, (ULONG_PTR)v21, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
      if ( !KeGetCurrentIrql() )
      {
        v30 = 0;
        if ( v24 != -1 )
        {
          LOBYTE(v30) = 1;
          v26 = PsAttachSiloToCurrentThread(v24);
          *((_QWORD *)&v30 + 1) = v26;
          if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v26, v24);
        }
        UlFreeHttpConnection(v21);
        UxPodDetachThread(&v30);
        goto LABEL_8;
      }
    }
    else if ( v25 || v21[2] || v21[4] )
    {
      UlBugCheckEx(1u, (ULONG_PTR)v21, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
    }
    LOBYTE(v23) = 1;
    UlThreadPoolEnqueueWorkItem(0, v21, UlFreeHttpConnection, v23, v24, -1);
LABEL_8:
    P[4] = 0;
  }
  v5 = P[5];
  if ( v5 )
  {
    v6 = _InterlockedDecrement((volatile signed __int32 *)(v5 + 20));
    if ( UxDebugCheckRefcount && v6 <= -1 )
      UlBugCheckEx(3u, v5 + 20, 0x14u, v6);
    if ( v6 )
      goto LABEL_23;
    v7 = v5 + 608;
    if ( *(_QWORD *)(v5 + 608) || *(_QWORD *)(v5 + 624) || *(_QWORD *)(v5 + 640) )
      UlBugCheckEx(1u, v5 + 608, (ULONG_PTR)"minio\\http\\sys\\sendresponse.h", 0x453u);
    CurrentServerSilo = *(void **)(*(_QWORD *)(*(_QWORD *)(v5 + 24) + 24LL) + 1088LL);
    if ( KeGetCurrentIrql() )
    {
      v17 = 0;
      if ( (unsigned int)dword_1401A3F48 > 1 )
      {
        v17 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F60 )
          v17 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v7 + 32) = CurrentServerSilo;
      v31 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v31);
      v18 = v31 + 24;
      v19 = _InterlockedIncrement((volatile signed __int32 *)(v31 + 24));
      if ( UxDebugCheckRefcount && v19 <= -1 )
        UlBugCheckEx(3u, v18, 0xDu, v19);
      *(_BYTE *)(v7 + 24) = 1;
      v20 = *(_QWORD *)(qword_1401A3F50 + 8LL * v17);
      *(_QWORD *)(v7 + 16) = UlDestroyCapturedResponse;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v20 + 16), (PSLIST_ENTRY)v7) )
      {
        KeSetEvent((PRKEVENT)(v20 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v20);
      }
      goto LABEL_23;
    }
    v12 = 0;
    v30 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v14 = *((_QWORD *)&v30 + 1);
    }
    else
    {
      v13 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v14 = v13;
      v12 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v13, CurrentServerSilo);
        UlDestroyCapturedResponse(v7, v27, v28, v29);
        goto LABEL_20;
      }
    }
    UlDestroyCapturedResponse(v7, v9, v10, v11);
    if ( !v12 )
    {
LABEL_23:
      P[5] = 0;
      goto LABEL_24;
    }
LABEL_20:
    if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v14);
    PsDetachSiloFromCurrentThread(v14);
    goto LABEL_23;
  }
LABEL_24:
  v15 = (volatile signed __int32 *)P[3];
  v16 = _InterlockedDecrement(v15);
  if ( UxDebugCheckRefcount && v16 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v15, 0x14u, v16);
  if ( !v16 )
    UlConsumerCleanupCompletion(P[3]);
  P[3] = 0;
  *((_DWORD *)P + 4) = 1801604213;
  ExFreePoolWithTag(P, 0);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1033, 96, WPP_173ede4a325638307373c19033e5a27a_Traceguids);
}

```

## disassembly

```asm
0x140033310  push    rbx
0x140033312  push    rsi
0x140033313  push    rdi
0x140033314  push    r12
0x140033316  sub     rsp, 48h
0x14003331a  mov     rbx, rcx
0x14003331d  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140033324  jnz     loc_140033790
0x14003332a  mov     rcx, [rbx+30h]; Irp
0x14003332e  xor     r12d, r12d
0x140033331  test    rcx, rcx
0x140033334  jz      short loc_140033346
0x140033336  call    cs:__imp_IoFreeIrp
0x14003333d  nop     dword ptr [rax+rax+00h]
0x140033342  mov     [rbx+30h], r12
0x140033346  mov     rsi, [rbx+20h]
0x14003334a  mov     edi, 0FFFFFFFFh
0x14003334f  mov     [rsp+68h+arg_10], r14
0x140033357  test    rsi, rsi
0x14003335a  jz      short loc_140033381
0x14003335c  lea     rdx, [rsi+28h]; BugCheckParameter2
0x140033360  mov     eax, edi
0x140033362  lock xadd [rdx], eax
0x140033366  dec     eax
0x140033368  cmp     cs:UxDebugCheckRefcount, r12b
0x14003336f  jnz     loc_140033657
0x140033375  test    eax, eax
0x140033377  jz      loc_1400335C7
0x14003337d  mov     [rbx+20h], r12
0x140033381  mov     rcx, [rbx+28h]
0x140033385  mov     [rsp+68h+arg_8], rbp
0x14003338a  test    rcx, rcx
0x14003338d  jz      loc_140033478
0x140033393  lea     rdx, [rcx+14h]; BugCheckParameter2
0x140033397  mov     eax, edi
0x140033399  lock xadd [rdx], eax
0x14003339d  dec     eax
0x14003339f  cmp     cs:UxDebugCheckRefcount, r12b
0x1400333a6  jnz     loc_14003363B
0x1400333ac  test    eax, eax
0x1400333ae  jnz     loc_140033474
0x1400333b4  lea     rsi, [rcx+260h]
0x1400333bb  cmp     [rsi], r12
0x1400333be  jnz     short loc_1400333CC
0x1400333c0  cmp     [rsi+10h], r12
0x1400333c4  jnz     short loc_1400333CC
0x1400333c6  cmp     [rsi+20h], r12
0x1400333ca  jz      short loc_1400333E7
0x1400333cc  mov     r9d, 453h; BugCheckParameter4
0x1400333d2  lea     r8, aMinioHttpSysSe_0; "minio\\http\\sys\\sendresponse.h"
0x1400333d9  mov     rdx, rsi; BugCheckParameter2
0x1400333dc  mov     ecx, 1; BugCheckParameter1
0x1400333e1  call    UlBugCheckEx
0x1400333e7  mov     rax, [rcx+18h]
0x1400333eb  mov     rcx, [rax+18h]
0x1400333ef  mov     rbp, [rcx+440h]
0x1400333f6  call    cs:__imp_KeGetCurrentIrql
0x1400333fd  nop     dword ptr [rax+rax+00h]
0x140033402  test    al, al
0x140033404  jnz     loc_1400334D8
0x14003340a  xor     r14b, r14b
0x14003340d  mov     [rsp+68h+var_28], r15
0x140033412  xorps   xmm0, xmm0
0x140033415  movups  [rsp+68h+var_38], xmm0
0x14003341a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14003341e  jz      loc_14003368F
0x140033424  mov     rcx, rbp
0x140033427  call    cs:__imp_PsAttachSiloToCurrentThread
0x14003342e  nop     dword ptr [rax+rax+00h]
0x140033433  mov     r15, rax
0x140033436  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14003343d  mov     r14b, 1
0x140033440  jnz     loc_140033765
0x140033446  mov     rcx, rsi
0x140033449  call    UlDestroyCapturedResponse
0x14003344e  test    r14b, r14b
0x140033451  jz      short loc_14003346F
0x140033453  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14003345a  jnz     loc_1400337AE
0x140033460  mov     rcx, r15
0x140033463  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14003346a  nop     dword ptr [rax+rax+00h]
0x14003346f  mov     r15, [rsp+68h+var_28]
0x140033474  mov     [rbx+28h], r12
0x140033478  mov     rdx, [rbx+18h]; BugCheckParameter2
0x14003347c  lock xadd [rdx], edi
0x140033480  dec     edi
0x140033482  cmp     cs:UxDebugCheckRefcount, r12b
0x140033489  jnz     loc_14003361E
0x14003348f  test    edi, edi
0x140033491  jz      loc_1400337F9
0x140033497  xor     edx, edx; Tag
0x140033499  mov     [rbx+18h], r12
0x14003349d  mov     rcx, rbx; P
0x1400334a0  mov     dword ptr [rbx+10h], 6B624C75h
0x1400334a7  call    cs:__imp_ExFreePoolWithTag
0x1400334ae  nop     dword ptr [rax+rax+00h]
0x1400334b3  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400334ba  jnz     loc_140033807
0x1400334c0  mov     rbp, [rsp+68h+arg_8]
0x1400334c5  mov     r14, [rsp+68h+arg_10]
0x1400334cd  add     rsp, 48h
0x1400334d1  pop     r12
0x1400334d3  pop     rdi
0x1400334d4  pop     rsi
0x1400334d5  pop     rbx
0x1400334d6  retn
0x1400334d8  cmp     cs:dword_1401A3F48, 1
0x1400334df  mov     r14d, r12d
0x1400334e2  jbe     short loc_14003350A
0x1400334e4  xor     ecx, ecx; ProcNumber
0x1400334e6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400334ed  nop     dword ptr [rax+rax+00h]
0x1400334f2  xor     edx, edx
0x1400334f4  div     cs:UxNumberOfProcessors
0x1400334fa  cmp     cs:byte_1401A3F60, r12b
0x140033501  mov     r14d, edx
0x140033504  jnz     loc_1400337CC
0x14003350a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14003350e  jnz     short loc_14003351F
0x140033510  call    cs:__imp_PsGetCurrentServerSilo
0x140033517  nop     dword ptr [rax+rax+00h]
0x14003351c  mov     rbp, rax
0x14003351f  mov     [rsi+20h], rbp
0x140033523  mov     [rsp+68h+arg_0], r12
0x140033528  test    rbp, rbp
0x14003352b  jnz     loc_1400337E0
0x140033531  mov     edx, cs:UxPodMonitorSlot
0x140033537  lea     r8, [rsp+68h+arg_0]
0x14003353c  mov     rcx, rbp
0x14003353f  call    cs:__imp_PsGetPermanentSiloContext
0x140033546  nop     dword ptr [rax+rax+00h]
0x14003354b  mov     rdx, [rsp+68h+arg_0]
0x140033550  mov     ecx, 1
0x140033555  add     rdx, 18h; BugCheckParameter2
0x140033559  lock xadd [rdx], ecx
0x14003355d  inc     ecx
0x14003355f  cmp     cs:UxDebugCheckRefcount, r12b
0x140033566  jnz     loc_140033673
0x14003356c  mov     byte ptr [rsi+18h], 1
0x140033570  mov     rdx, rsi; ListEntry
0x140033573  mov     rax, cs:qword_1401A3F50
0x14003357a  mov     ecx, r14d
0x14003357d  mov     rbp, [rax+rcx*8]
0x140033581  lea     rax, UlDestroyCapturedResponse
0x140033588  mov     [rsi+10h], rax
0x14003358c  lea     rcx, [rbp+10h]; ListHead
0x140033590  call    cs:__imp_ExpInterlockedPushEntrySList
0x140033597  nop     dword ptr [rax+rax+00h]
0x14003359c  test    rax, rax
0x14003359f  jnz     loc_140033474
0x1400335a5  lea     rcx, [rbp+20h]; Event
0x1400335a9  xor     r8d, r8d; Wait
0x1400335ac  xor     edx, edx; Increment
0x1400335ae  call    cs:__imp_KeSetEvent
0x1400335b5  nop     dword ptr [rax+rax+00h]
0x1400335ba  mov     rcx, rbp; Context
0x1400335bd  call    UlpActivateThreadPoolQueue
0x1400335c2  jmp     loc_140033474
0x1400335c7  lea     r14, [rsi+40h]
0x1400335cb  call    cs:__imp_IoGetCurrentProcess
0x1400335d2  nop     dword ptr [rax+rax+00h]
0x1400335d7  cmp     cs:UxSystemProcess, rax
0x1400335de  mov     rsi, [rsi+440h]
0x1400335e5  mov     rcx, [r14]
0x1400335e8  jnz     loc_140033716
0x1400335ee  test    rcx, rcx
0x1400335f1  jnz     short loc_140033603
0x1400335f3  cmp     [r14+10h], r12
0x1400335f7  jnz     short loc_140033603
0x1400335f9  cmp     [r14+20h], r12
0x1400335fd  jz      loc_140033699
0x140033603  mov     r9d, 0E1h; BugCheckParameter4
0x140033609  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140033610  mov     rdx, r14; BugCheckParameter2
0x140033613  mov     ecx, 1; BugCheckParameter1
0x140033618  call    UlBugCheckEx
0x14003361e  cmp     edi, 0FFFFFFFFh
0x140033621  jg      loc_14003348F
0x140033627  movsxd  r9, edi; BugCheckParameter4
0x14003362a  mov     ecx, 3; BugCheckParameter1
0x14003362f  mov     r8d, 14h; BugCheckParameter3
0x140033635  call    UlBugCheckEx
0x14003363b  cmp     eax, edi
0x14003363d  jg      loc_1400333AC
0x140033643  movsxd  r9, eax; BugCheckParameter4
0x140033646  mov     ecx, 3; BugCheckParameter1
0x14003364b  mov     r8d, 14h; BugCheckParameter3
0x140033651  call    UlBugCheckEx
0x140033657  cmp     eax, edi
0x140033659  jg      loc_140033375
0x14003365f  movsxd  r9, eax; BugCheckParameter4
0x140033662  mov     ecx, 3; BugCheckParameter1
0x140033667  mov     r8d, 14h; BugCheckParameter3
0x14003366d  call    UlBugCheckEx
0x140033673  cmp     ecx, edi
0x140033675  jg      loc_14003356C
0x14003367b  movsxd  r9, ecx; BugCheckParameter4
0x14003367e  mov     r8d, 0Dh; BugCheckParameter3
0x140033684  mov     ecx, 3; BugCheckParameter1
0x140033689  call    UlBugCheckEx
0x14003368f  mov     r15, qword ptr [rsp+68h+var_38+8]
0x140033694  jmp     loc_140033446
0x140033699  call    cs:__imp_KeGetCurrentIrql
0x1400336a0  nop     dword ptr [rax+rax+00h]
0x1400336a5  test    al, al
0x1400336a7  jnz     short loc_1400336F0
0x1400336a9  xorps   xmm0, xmm0
0x1400336ac  movups  [rsp+68h+var_38], xmm0
0x1400336b1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400336b5  jz      short loc_1400336D9
0x1400336b7  mov     rcx, rsi
0x1400336ba  mov     byte ptr [rsp+68h+var_38], 1
0x1400336bf  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400336c6  nop     dword ptr [rax+rax+00h]
0x1400336cb  mov     qword ptr [rsp+68h+var_38+8], rax
0x1400336d0  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400336d7  jnz     short loc_140033742
0x1400336d9  mov     rcx, r14
0x1400336dc  call    UlFreeHttpConnection
0x1400336e1  lea     rcx, [rsp+68h+var_38]
0x1400336e6  call    UxPodDetachThread
0x1400336eb  jmp     loc_14003337D
0x1400336f0  mov     [rsp+68h+var_40], 0FFFFFFFFh
0x1400336f8  lea     r8, UlFreeHttpConnection
0x1400336ff  mov     r9b, 1
0x140033702  mov     [rsp+68h+var_48], rsi
0x140033707  mov     rdx, r14
0x14003370a  xor     ecx, ecx
0x14003370c  call    UlThreadPoolEnqueueWorkItem
0x140033711  jmp     loc_14003337D
0x140033716  test    rcx, rcx
0x140033719  jnz     short loc_140033727
0x14003371b  cmp     [r14+10h], r12
0x14003371f  jnz     short loc_140033727
0x140033721  cmp     [r14+20h], r12
0x140033725  jz      short loc_1400336F0
0x140033727  mov     r9d, 0DBh; BugCheckParameter4
0x14003372d  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140033734  mov     rdx, r14; BugCheckParameter2
0x140033737  mov     ecx, 1; BugCheckParameter1
0x14003373c  call    UlBugCheckEx
0x140033742  mov     edx, 19h
0x140033747  mov     [rsp+68h+var_48], rsi
0x14003374c  mov     ecx, 51Ch
0x140033751  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140033758  mov     r9, rax
0x14003375b  call    WPP_SF_qq
0x140033760  jmp     loc_1400336D9
0x140033765  mov     edx, 19h
0x14003376a  mov     [rsp+68h+var_48], rbp
0x14003376f  mov     ecx, 51Ch
0x140033774  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x14003377b  mov     r9, rax
0x14003377e  call    WPP_SF_qq
0x140033783  mov     rcx, rsi
0x140033786  call    UlDestroyCapturedResponse
0x14003378b  jmp     loc_140033453
0x140033790  mov     edx, 5Fh ; '_'
0x140033795  lea     r8, WPP_173ede4a325638307373c19033e5a27a_Traceguids
0x14003379c  mov     ecx, 409h
0x1400337a1  mov     r9, rbx
0x1400337a4  call    WPP_SF_q
0x1400337a9  jmp     loc_14003332A
0x1400337ae  mov     edx, 1Ah
0x1400337b3  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x1400337ba  mov     ecx, 51Ch
0x1400337bf  mov     r9, r15
0x1400337c2  call    WPP_SF_q
0x1400337c7  jmp     loc_140033460
0x1400337cc  lea     rcx, UlThreadPoolArena
0x1400337d3  call    UlpAssignThreadPoolWork
0x1400337d8  mov     r14d, eax
0x1400337db  jmp     loc_14003350A
0x1400337e0  mov     edx, 49576C55h; Tag
0x1400337e5  mov     rcx, rbp; Object
0x1400337e8  call    cs:__imp_ObfReferenceObjectWithTag
0x1400337ef  nop     dword ptr [rax+rax+00h]
0x1400337f4  jmp     loc_140033531
0x1400337f9  mov     rcx, [rbx+18h]
0x1400337fd  call    UlConsumerCleanupCompletion
0x140033802  jmp     loc_140033497
0x140033807  mov     edx, 60h ; '`'
0x14003380c  lea     r8, WPP_173ede4a325638307373c19033e5a27a_Traceguids
0x140033813  mov     ecx, 409h
0x140033818  call    WPP_SF_
0x14003381d  jmp     loc_1400334C0
```

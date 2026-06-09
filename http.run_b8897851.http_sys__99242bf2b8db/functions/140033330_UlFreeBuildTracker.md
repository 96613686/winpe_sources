# UlFreeBuildTracker

- ea: `0x140033330`
- end: `0x140033842`
- name: `UlFreeBuildTracker`
- size: `1298`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `6`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140032fd0`
- `0x1400833c0`
- `0x1400967b0`
- `0x1400bc970`
- `0x1400c9c30`
- `0x1400d2044`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140033330`
- `0x140033850`
- `0x140035a70`
- `0x14005e050`
- `0x1400a033c`
- `0x14013dc78`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140033416`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400336b9`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033416`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400336b9`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400335b0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400335b0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033506`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033506`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003355f`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003355f`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140033808`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140033808`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140033447`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400336df`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140033447`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400336df`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140033483`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140033483`
- `ntoskrnl!IoFreeIrp` at `0x140033356`
- `ntoskrnl!IoFreeIrp` at `0x140033356`
- `ntoskrnl!KeSetEvent` at `0x1400335ce`
- `ntoskrnl!KeSetEvent` at `0x1400335ce`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140033530`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140033530`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400334c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400334c7`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400335eb`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400335eb`

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
    WPP_SF_q(1033, 95, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, P);
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
    WPP_SF_(1033, 96, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids);
}

```

## disassembly

```asm
0x140033330  push    rbx
0x140033332  push    rsi
0x140033333  push    rdi
0x140033334  push    r12
0x140033336  sub     rsp, 48h
0x14003333a  mov     rbx, rcx
0x14003333d  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140033344  jnz     loc_1400337B0
0x14003334a  mov     rcx, [rbx+30h]; Irp
0x14003334e  xor     r12d, r12d
0x140033351  test    rcx, rcx
0x140033354  jz      short loc_140033366
0x140033356  call    cs:__imp_IoFreeIrp
0x14003335d  nop     dword ptr [rax+rax+00h]
0x140033362  mov     [rbx+30h], r12
0x140033366  mov     rsi, [rbx+20h]
0x14003336a  mov     edi, 0FFFFFFFFh
0x14003336f  mov     [rsp+68h+arg_10], r14
0x140033377  test    rsi, rsi
0x14003337a  jz      short loc_1400333A1
0x14003337c  lea     rdx, [rsi+28h]; BugCheckParameter2
0x140033380  mov     eax, edi
0x140033382  lock xadd [rdx], eax
0x140033386  dec     eax
0x140033388  cmp     cs:UxDebugCheckRefcount, r12b
0x14003338f  jnz     loc_140033677
0x140033395  test    eax, eax
0x140033397  jz      loc_1400335E7
0x14003339d  mov     [rbx+20h], r12
0x1400333a1  mov     rcx, [rbx+28h]
0x1400333a5  mov     [rsp+68h+arg_8], rbp
0x1400333aa  test    rcx, rcx
0x1400333ad  jz      loc_140033498
0x1400333b3  lea     rdx, [rcx+14h]; BugCheckParameter2
0x1400333b7  mov     eax, edi
0x1400333b9  lock xadd [rdx], eax
0x1400333bd  dec     eax
0x1400333bf  cmp     cs:UxDebugCheckRefcount, r12b
0x1400333c6  jnz     loc_14003365B
0x1400333cc  test    eax, eax
0x1400333ce  jnz     loc_140033494
0x1400333d4  lea     rsi, [rcx+260h]
0x1400333db  cmp     [rsi], r12
0x1400333de  jnz     short loc_1400333EC
0x1400333e0  cmp     [rsi+10h], r12
0x1400333e4  jnz     short loc_1400333EC
0x1400333e6  cmp     [rsi+20h], r12
0x1400333ea  jz      short loc_140033407
0x1400333ec  mov     r9d, 453h; BugCheckParameter4
0x1400333f2  lea     r8, aMinioHttpSysSe_0; "minio\\http\\sys\\sendresponse.h"
0x1400333f9  mov     rdx, rsi; BugCheckParameter2
0x1400333fc  mov     ecx, 1; BugCheckParameter1
0x140033401  call    UlBugCheckEx
0x140033407  mov     rax, [rcx+18h]
0x14003340b  mov     rcx, [rax+18h]
0x14003340f  mov     rbp, [rcx+440h]
0x140033416  call    cs:__imp_KeGetCurrentIrql
0x14003341d  nop     dword ptr [rax+rax+00h]
0x140033422  test    al, al
0x140033424  jnz     loc_1400334F8
0x14003342a  xor     r14b, r14b
0x14003342d  mov     [rsp+68h+var_28], r15
0x140033432  xorps   xmm0, xmm0
0x140033435  movups  [rsp+68h+var_38], xmm0
0x14003343a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14003343e  jz      loc_1400336AF
0x140033444  mov     rcx, rbp
0x140033447  call    cs:__imp_PsAttachSiloToCurrentThread
0x14003344e  nop     dword ptr [rax+rax+00h]
0x140033453  mov     r15, rax
0x140033456  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14003345d  mov     r14b, 1
0x140033460  jnz     loc_140033785
0x140033466  mov     rcx, rsi
0x140033469  call    UlDestroyCapturedResponse
0x14003346e  test    r14b, r14b
0x140033471  jz      short loc_14003348F
0x140033473  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14003347a  jnz     loc_1400337CE
0x140033480  mov     rcx, r15
0x140033483  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14003348a  nop     dword ptr [rax+rax+00h]
0x14003348f  mov     r15, [rsp+68h+var_28]
0x140033494  mov     [rbx+28h], r12
0x140033498  mov     rdx, [rbx+18h]; BugCheckParameter2
0x14003349c  lock xadd [rdx], edi
0x1400334a0  dec     edi
0x1400334a2  cmp     cs:UxDebugCheckRefcount, r12b
0x1400334a9  jnz     loc_14003363E
0x1400334af  test    edi, edi
0x1400334b1  jz      loc_140033819
0x1400334b7  xor     edx, edx; Tag
0x1400334b9  mov     [rbx+18h], r12
0x1400334bd  mov     rcx, rbx; P
0x1400334c0  mov     dword ptr [rbx+10h], 6B624C75h
0x1400334c7  call    cs:__imp_ExFreePoolWithTag
0x1400334ce  nop     dword ptr [rax+rax+00h]
0x1400334d3  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400334da  jnz     loc_140033827
0x1400334e0  mov     rbp, [rsp+68h+arg_8]
0x1400334e5  mov     r14, [rsp+68h+arg_10]
0x1400334ed  add     rsp, 48h
0x1400334f1  pop     r12
0x1400334f3  pop     rdi
0x1400334f4  pop     rsi
0x1400334f5  pop     rbx
0x1400334f6  retn
0x1400334f8  cmp     cs:dword_1401A3F48, 1
0x1400334ff  mov     r14d, r12d
0x140033502  jbe     short loc_14003352A
0x140033504  xor     ecx, ecx; ProcNumber
0x140033506  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14003350d  nop     dword ptr [rax+rax+00h]
0x140033512  xor     edx, edx
0x140033514  div     cs:UxNumberOfProcessors
0x14003351a  cmp     cs:byte_1401A3F60, r12b
0x140033521  mov     r14d, edx
0x140033524  jnz     loc_1400337EC
0x14003352a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14003352e  jnz     short loc_14003353F
0x140033530  call    cs:__imp_PsGetCurrentServerSilo
0x140033537  nop     dword ptr [rax+rax+00h]
0x14003353c  mov     rbp, rax
0x14003353f  mov     [rsi+20h], rbp
0x140033543  mov     [rsp+68h+arg_0], r12
0x140033548  test    rbp, rbp
0x14003354b  jnz     loc_140033800
0x140033551  mov     edx, cs:UxPodMonitorSlot
0x140033557  lea     r8, [rsp+68h+arg_0]
0x14003355c  mov     rcx, rbp
0x14003355f  call    cs:__imp_PsGetPermanentSiloContext
0x140033566  nop     dword ptr [rax+rax+00h]
0x14003356b  mov     rdx, [rsp+68h+arg_0]
0x140033570  mov     ecx, 1
0x140033575  add     rdx, 18h; BugCheckParameter2
0x140033579  lock xadd [rdx], ecx
0x14003357d  inc     ecx
0x14003357f  cmp     cs:UxDebugCheckRefcount, r12b
0x140033586  jnz     loc_140033693
0x14003358c  mov     byte ptr [rsi+18h], 1
0x140033590  mov     rdx, rsi; ListEntry
0x140033593  mov     rax, cs:qword_1401A3F50
0x14003359a  mov     ecx, r14d
0x14003359d  mov     rbp, [rax+rcx*8]
0x1400335a1  lea     rax, UlDestroyCapturedResponse
0x1400335a8  mov     [rsi+10h], rax
0x1400335ac  lea     rcx, [rbp+10h]; ListHead
0x1400335b0  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400335b7  nop     dword ptr [rax+rax+00h]
0x1400335bc  test    rax, rax
0x1400335bf  jnz     loc_140033494
0x1400335c5  lea     rcx, [rbp+20h]; Event
0x1400335c9  xor     r8d, r8d; Wait
0x1400335cc  xor     edx, edx; Increment
0x1400335ce  call    cs:__imp_KeSetEvent
0x1400335d5  nop     dword ptr [rax+rax+00h]
0x1400335da  mov     rcx, rbp; Context
0x1400335dd  call    UlpActivateThreadPoolQueue
0x1400335e2  jmp     loc_140033494
0x1400335e7  lea     r14, [rsi+40h]
0x1400335eb  call    cs:__imp_IoGetCurrentProcess
0x1400335f2  nop     dword ptr [rax+rax+00h]
0x1400335f7  cmp     cs:UxSystemProcess, rax
0x1400335fe  mov     rsi, [rsi+440h]
0x140033605  mov     rcx, [r14]
0x140033608  jnz     loc_140033736
0x14003360e  test    rcx, rcx
0x140033611  jnz     short loc_140033623
0x140033613  cmp     [r14+10h], r12
0x140033617  jnz     short loc_140033623
0x140033619  cmp     [r14+20h], r12
0x14003361d  jz      loc_1400336B9
0x140033623  mov     r9d, 0E1h; BugCheckParameter4
0x140033629  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140033630  mov     rdx, r14; BugCheckParameter2
0x140033633  mov     ecx, 1; BugCheckParameter1
0x140033638  call    UlBugCheckEx
0x14003363e  cmp     edi, 0FFFFFFFFh
0x140033641  jg      loc_1400334AF
0x140033647  movsxd  r9, edi; BugCheckParameter4
0x14003364a  mov     ecx, 3; BugCheckParameter1
0x14003364f  mov     r8d, 14h; BugCheckParameter3
0x140033655  call    UlBugCheckEx
0x14003365b  cmp     eax, edi
0x14003365d  jg      loc_1400333CC
0x140033663  movsxd  r9, eax; BugCheckParameter4
0x140033666  mov     ecx, 3; BugCheckParameter1
0x14003366b  mov     r8d, 14h; BugCheckParameter3
0x140033671  call    UlBugCheckEx
0x140033677  cmp     eax, edi
0x140033679  jg      loc_140033395
0x14003367f  movsxd  r9, eax; BugCheckParameter4
0x140033682  mov     ecx, 3; BugCheckParameter1
0x140033687  mov     r8d, 14h; BugCheckParameter3
0x14003368d  call    UlBugCheckEx
0x140033693  cmp     ecx, edi
0x140033695  jg      loc_14003358C
0x14003369b  movsxd  r9, ecx; BugCheckParameter4
0x14003369e  mov     r8d, 0Dh; BugCheckParameter3
0x1400336a4  mov     ecx, 3; BugCheckParameter1
0x1400336a9  call    UlBugCheckEx
0x1400336af  mov     r15, qword ptr [rsp+68h+var_38+8]
0x1400336b4  jmp     loc_140033466
0x1400336b9  call    cs:__imp_KeGetCurrentIrql
0x1400336c0  nop     dword ptr [rax+rax+00h]
0x1400336c5  test    al, al
0x1400336c7  jnz     short loc_140033710
0x1400336c9  xorps   xmm0, xmm0
0x1400336cc  movups  [rsp+68h+var_38], xmm0
0x1400336d1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400336d5  jz      short loc_1400336F9
0x1400336d7  mov     rcx, rsi
0x1400336da  mov     byte ptr [rsp+68h+var_38], 1
0x1400336df  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400336e6  nop     dword ptr [rax+rax+00h]
0x1400336eb  mov     qword ptr [rsp+68h+var_38+8], rax
0x1400336f0  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400336f7  jnz     short loc_140033762
0x1400336f9  mov     rcx, r14
0x1400336fc  call    UlFreeHttpConnection
0x140033701  lea     rcx, [rsp+68h+var_38]
0x140033706  call    UxPodDetachThread
0x14003370b  jmp     loc_14003339D
0x140033710  mov     [rsp+68h+var_40], 0FFFFFFFFh
0x140033718  lea     r8, UlFreeHttpConnection
0x14003371f  mov     r9b, 1
0x140033722  mov     [rsp+68h+var_48], rsi
0x140033727  mov     rdx, r14
0x14003372a  xor     ecx, ecx
0x14003372c  call    UlThreadPoolEnqueueWorkItem
0x140033731  jmp     loc_14003339D
0x140033736  test    rcx, rcx
0x140033739  jnz     short loc_140033747
0x14003373b  cmp     [r14+10h], r12
0x14003373f  jnz     short loc_140033747
0x140033741  cmp     [r14+20h], r12
0x140033745  jz      short loc_140033710
0x140033747  mov     r9d, 0DBh; BugCheckParameter4
0x14003374d  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140033754  mov     rdx, r14; BugCheckParameter2
0x140033757  mov     ecx, 1; BugCheckParameter1
0x14003375c  call    UlBugCheckEx
0x140033762  mov     edx, 19h
0x140033767  mov     [rsp+68h+var_48], rsi
0x14003376c  mov     ecx, 51Ch
0x140033771  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140033778  mov     r9, rax
0x14003377b  call    WPP_SF_qq
0x140033780  jmp     loc_1400336F9
0x140033785  mov     edx, 19h
0x14003378a  mov     [rsp+68h+var_48], rbp
0x14003378f  mov     ecx, 51Ch
0x140033794  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x14003379b  mov     r9, rax
0x14003379e  call    WPP_SF_qq
0x1400337a3  mov     rcx, rsi
0x1400337a6  call    UlDestroyCapturedResponse
0x1400337ab  jmp     loc_140033473
0x1400337b0  mov     edx, 5Fh ; '_'
0x1400337b5  lea     r8, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids
0x1400337bc  mov     ecx, 409h
0x1400337c1  mov     r9, rbx
0x1400337c4  call    WPP_SF_q
0x1400337c9  jmp     loc_14003334A
0x1400337ce  mov     edx, 1Ah
0x1400337d3  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x1400337da  mov     ecx, 51Ch
0x1400337df  mov     r9, r15
0x1400337e2  call    WPP_SF_q
0x1400337e7  jmp     loc_140033480
0x1400337ec  lea     rcx, UlThreadPoolArena
0x1400337f3  call    UlpAssignThreadPoolWork
0x1400337f8  mov     r14d, eax
0x1400337fb  jmp     loc_14003352A
0x140033800  mov     edx, 49576C55h; Tag
0x140033805  mov     rcx, rbp; Object
0x140033808  call    cs:__imp_ObfReferenceObjectWithTag
0x14003380f  nop     dword ptr [rax+rax+00h]
0x140033814  jmp     loc_140033551
0x140033819  mov     rcx, [rbx+18h]
0x14003381d  call    UlConsumerCleanupCompletion
0x140033822  jmp     loc_1400334B7
0x140033827  mov     edx, 60h ; '`'
0x14003382c  lea     r8, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids
0x140033833  mov     ecx, 409h
0x140033838  call    WPP_SF_
0x14003383d  jmp     loc_1400334E0
```

# UlRemoveSendIrpCancelRoutine

- ea: `0x1400356b0`
- end: `0x140035a5c`
- name: `UlRemoveSendIrpCancelRoutine`
- size: `940`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400354c0`
- `0x14003721c`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x1400356b0`
- `0x14005e050`
- `0x14013dc78`
- `0x1401c3008`
- `0x1401c3f78`
- `0x1401d9c5c`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140035793`
- `ntoskrnl!KeGetCurrentIrql` at `0x140035793`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400358bd`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400358bd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140035819`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140035819`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140035871`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140035871`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140035a4b`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140035a4b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400357bb`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400357bb`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400357fb`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400357fb`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140035912`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140035912`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140035923`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140035923`
- `ntoskrnl!KeSetEvent` at `0x1400358db`
- `ntoskrnl!KeSetEvent` at `0x1400358db`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140035842`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140035842`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003572b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003572b`

## pseudocode

```c
__int64 __fastcall UlRemoveSendIrpCancelRoutine(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned __int8 v5; // bl
  __int64 v7; // rbx
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v9; // r9
  void *CurrentServerSilo; // rsi
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  char v15; // di
  __int64 v16; // rax
  __int64 v17; // rbp
  ULONG v18; // edi
  ULONG_PTR v19; // rdx
  int v20; // ecx
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  KIRQL Irql; // [rsp+68h] [rbp+10h] BYREF
  __int64 v27; // [rsp+70h] [rbp+18h] BYREF

  Irql = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
  {
    if ( a1 )
      v22 = *(_QWORD *)(a1 + 48);
    else
      v22 = 0;
    WPP_SF_qqP(1033, 77, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, a1, v22, a2);
  }
  if ( _InterlockedExchange64((volatile __int64 *)(a2 + 104), 0) )
  {
    *(_QWORD *)(a2 + 120) = 0;
    v4 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 40));
    if ( UxDebugCheckRefcount && v4 <= -1 )
      UlBugCheckEx(3u, a1 + 40, 0x25u, v4);
    if ( v4 )
      goto LABEL_5;
    v7 = a1 + 64;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(void **)(a1 + 1088);
    v11 = *(_QWORD *)(a1 + 64);
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v11 || *(_QWORD *)(a1 + 80) || *(_QWORD *)(a1 + 96) )
        UlBugCheckEx(1u, a1 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      LOBYTE(v9) = 1;
      UlThreadPoolEnqueueWorkItem(0, a1 + 64, UlFreeHttpConnection, v9, CurrentServerSilo, -1);
      goto LABEL_5;
    }
    if ( v11 || *(_QWORD *)(a1 + 80) || *(_QWORD *)(a1 + 96) )
      UlBugCheckEx(1u, a1 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
    {
      v18 = 0;
      if ( (unsigned int)dword_1401A3F48 > 1 )
      {
        v18 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F60 )
          v18 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v7 + 32) = CurrentServerSilo;
      v27 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v27);
      v19 = v27 + 24;
      v20 = _InterlockedIncrement((volatile signed __int32 *)(v27 + 24));
      if ( UxDebugCheckRefcount && v20 <= -1 )
        UlBugCheckEx(3u, v19, 0xDu, v20);
      *(_BYTE *)(v7 + 24) = 1;
      v21 = *(_QWORD *)(qword_1401A3F50 + 8LL * v18);
      *(_QWORD *)(v7 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v21 + 16), (PSLIST_ENTRY)v7) )
      {
        KeSetEvent((PRKEVENT)(v21 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v21);
      }
      goto LABEL_5;
    }
    v15 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v17 = 0;
    }
    else
    {
      v16 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v17 = v16;
      v15 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v16, CurrentServerSilo);
        UlFreeHttpConnection(v7, v23, v24, v25);
        goto LABEL_20;
      }
    }
    UlFreeHttpConnection(v7, v12, v13, v14);
    if ( !v15 )
    {
LABEL_5:
      v5 = 1;
      goto LABEL_6;
    }
LABEL_20:
    if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v17);
    PsDetachSiloFromCurrentThread(v17);
    goto LABEL_5;
  }
  IoAcquireCancelSpinLock(&Irql);
  IoReleaseCancelSpinLock(Irql);
  v5 = 0;
LABEL_6:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1033, 78, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1400356b0  push    rbx
0x1400356b2  push    rbp
0x1400356b3  push    rdi
0x1400356b4  sub     rsp, 40h
0x1400356b8  mov     rbx, rdx
0x1400356bb  mov     [rsp+58h+Irql], 0
0x1400356c0  mov     rdi, rcx
0x1400356c3  xor     ebp, ebp
0x1400356c5  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400356cc  jnz     loc_14003596C
0x1400356d2  mov     rax, rbp
0x1400356d5  mov     [rsp+58h+arg_0], rsi
0x1400356da  xchg    rax, [rbx+68h]
0x1400356de  test    rax, rax
0x1400356e1  jz      loc_14003590D
0x1400356e7  mov     [rbx+78h], rbp
0x1400356eb  lea     rdx, [rdi+28h]; BugCheckParameter2
0x1400356ef  mov     eax, 0FFFFFFFFh
0x1400356f4  lock xadd [rdx], eax
0x1400356f8  dec     eax
0x1400356fa  cmp     cs:UxDebugCheckRefcount, bpl
0x140035701  jnz     short loc_14003577A
0x140035703  test    eax, eax
0x140035705  jz      short loc_140035727
0x140035707  mov     bl, 1
0x140035709  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140035710  jnz     loc_14003599D
0x140035716  mov     rsi, [rsp+58h+arg_0]
0x14003571b  movzx   eax, bl
0x14003571e  add     rsp, 40h
0x140035722  pop     rdi
0x140035723  pop     rbp
0x140035724  pop     rbx
0x140035725  retn
0x140035727  lea     rbx, [rdi+40h]
0x14003572b  call    cs:__imp_IoGetCurrentProcess
0x140035732  nop     dword ptr [rax+rax+00h]
0x140035737  cmp     cs:UxSystemProcess, rax
0x14003573e  mov     rsi, [rdi+440h]
0x140035745  mov     rcx, [rbx]
0x140035748  jnz     loc_140035940
0x14003574e  test    rcx, rcx
0x140035751  jnz     short loc_14003575F
0x140035753  cmp     [rbx+10h], rbp
0x140035757  jnz     short loc_14003575F
0x140035759  cmp     [rbx+20h], rbp
0x14003575d  jz      short loc_140035793
0x14003575f  mov     r9d, 0E1h; BugCheckParameter4
0x140035765  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14003576c  mov     rdx, rbx; BugCheckParameter2
0x14003576f  mov     ecx, 1; BugCheckParameter1
0x140035774  call    UlBugCheckEx
0x14003577a  cmp     eax, 0FFFFFFFFh
0x14003577d  jg      short loc_140035703
0x14003577f  movsxd  r9, eax; BugCheckParameter4
0x140035782  mov     ecx, 3; BugCheckParameter1
0x140035787  mov     r8d, 25h ; '%'; BugCheckParameter3
0x14003578d  call    UlBugCheckEx
0x140035793  call    cs:__imp_KeGetCurrentIrql
0x14003579a  nop     dword ptr [rax+rax+00h]
0x14003579f  test    al, al
0x1400357a1  jnz     short loc_14003580C
0x1400357a3  xor     dil, dil
0x1400357a6  xorps   xmm0, xmm0
0x1400357a9  movups  [rsp+58h+var_28], xmm0
0x1400357ae  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400357b2  jz      loc_140035936
0x1400357b8  mov     rcx, rsi
0x1400357bb  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400357c2  nop     dword ptr [rax+rax+00h]
0x1400357c7  mov     rbp, rax
0x1400357ca  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400357d1  mov     dil, 1
0x1400357d4  jnz     loc_1400359E7
0x1400357da  mov     rcx, rbx
0x1400357dd  call    UlFreeHttpConnection
0x1400357e2  test    dil, dil
0x1400357e5  jz      loc_140035707
0x1400357eb  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400357f2  jnz     loc_140035A12
0x1400357f8  mov     rcx, rbp
0x1400357fb  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140035802  nop     dword ptr [rax+rax+00h]
0x140035807  jmp     loc_140035707
0x14003580c  cmp     cs:dword_1401A3F48, 1
0x140035813  mov     edi, ebp
0x140035815  jbe     short loc_14003583C
0x140035817  xor     ecx, ecx; ProcNumber
0x140035819  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140035820  nop     dword ptr [rax+rax+00h]
0x140035825  xor     edx, edx
0x140035827  div     cs:UxNumberOfProcessors
0x14003582d  cmp     cs:byte_1401A3F60, bpl
0x140035834  mov     edi, edx
0x140035836  jnz     loc_140035A30
0x14003583c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140035840  jnz     short loc_140035851
0x140035842  call    cs:__imp_PsGetCurrentServerSilo
0x140035849  nop     dword ptr [rax+rax+00h]
0x14003584e  mov     rsi, rax
0x140035851  mov     [rbx+20h], rsi
0x140035855  mov     [rsp+58h+arg_10], rbp
0x14003585a  test    rsi, rsi
0x14003585d  jnz     loc_140035A43
0x140035863  mov     edx, cs:UxPodMonitorSlot
0x140035869  lea     r8, [rsp+58h+arg_10]
0x14003586e  mov     rcx, rsi
0x140035871  call    cs:__imp_PsGetPermanentSiloContext
0x140035878  nop     dword ptr [rax+rax+00h]
0x14003587d  mov     rdx, [rsp+58h+arg_10]
0x140035882  mov     ecx, 1
0x140035887  add     rdx, 18h; BugCheckParameter2
0x14003588b  lock xadd [rdx], ecx
0x14003588f  inc     ecx
0x140035891  cmp     cs:UxDebugCheckRefcount, bpl
0x140035898  jnz     short loc_1400358F4
0x14003589a  mov     byte ptr [rbx+18h], 1
0x14003589e  mov     rdx, rbx; ListEntry
0x1400358a1  mov     rax, cs:qword_1401A3F50
0x1400358a8  mov     ecx, edi
0x1400358aa  mov     rdi, [rax+rcx*8]
0x1400358ae  lea     rax, UlFreeHttpConnection
0x1400358b5  mov     [rbx+10h], rax
0x1400358b9  lea     rcx, [rdi+10h]; ListHead
0x1400358bd  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400358c4  nop     dword ptr [rax+rax+00h]
0x1400358c9  test    rax, rax
0x1400358cc  jnz     loc_140035707
0x1400358d2  lea     rcx, [rdi+20h]; Event
0x1400358d6  xor     r8d, r8d; Wait
0x1400358d9  xor     edx, edx; Increment
0x1400358db  call    cs:__imp_KeSetEvent
0x1400358e2  nop     dword ptr [rax+rax+00h]
0x1400358e7  mov     rcx, rdi; Context
0x1400358ea  call    UlpActivateThreadPoolQueue
0x1400358ef  jmp     loc_140035707
0x1400358f4  cmp     ecx, 0FFFFFFFFh
0x1400358f7  jg      short loc_14003589A
0x1400358f9  movsxd  r9, ecx; BugCheckParameter4
0x1400358fc  mov     r8d, 0Dh; BugCheckParameter3
0x140035902  mov     ecx, 3; BugCheckParameter1
0x140035907  call    UlBugCheckEx
0x14003590d  lea     rcx, [rsp+58h+Irql]; Irql
0x140035912  call    cs:__imp_IoAcquireCancelSpinLock
0x140035919  nop     dword ptr [rax+rax+00h]
0x14003591e  movzx   ecx, [rsp+58h+Irql]; Irql
0x140035923  call    cs:__imp_IoReleaseCancelSpinLock
0x14003592a  nop     dword ptr [rax+rax+00h]
0x14003592f  xor     bl, bl
0x140035931  jmp     loc_140035709
0x140035936  mov     rbp, qword ptr [rsp+58h+var_28+8]
0x14003593b  jmp     loc_1400357DA
0x140035940  test    rcx, rcx
0x140035943  jnz     short loc_140035951
0x140035945  cmp     [rbx+10h], rbp
0x140035949  jnz     short loc_140035951
0x14003594b  cmp     [rbx+20h], rbp
0x14003594f  jz      short loc_1400359C1
0x140035951  mov     r9d, 0DBh; BugCheckParameter4
0x140035957  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14003595e  mov     rdx, rbx; BugCheckParameter2
0x140035961  mov     ecx, 1; BugCheckParameter1
0x140035966  call    UlBugCheckEx
0x14003596c  test    rdi, rdi
0x14003596f  jz      short loc_1400359BC
0x140035971  mov     rax, [rcx+30h]
0x140035975  mov     edx, 4Dh ; 'M'
0x14003597a  mov     [rsp+58h+var_30], rbx
0x14003597f  mov     ecx, 409h
0x140035984  mov     [rsp+58h+var_38], rax
0x140035989  mov     r9, rdi
0x14003598c  lea     r8, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids
0x140035993  call    WPP_SF_qqP
0x140035998  jmp     loc_1400356D2
0x14003599d  movzx   r9d, bl
0x1400359a1  lea     r8, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids
0x1400359a8  mov     edx, 4Eh ; 'N'
0x1400359ad  mov     ecx, 409h
0x1400359b2  call    WPP_SF_d
0x1400359b7  jmp     loc_140035716
0x1400359bc  mov     rax, rbp
0x1400359bf  jmp     short loc_140035975
0x1400359c1  mov     dword ptr [rsp+58h+var_30], 0FFFFFFFFh
0x1400359c9  lea     r8, UlFreeHttpConnection
0x1400359d0  mov     r9b, 1
0x1400359d3  mov     [rsp+58h+var_38], rsi
0x1400359d8  mov     rdx, rbx
0x1400359db  xor     ecx, ecx
0x1400359dd  call    UlThreadPoolEnqueueWorkItem
0x1400359e2  jmp     loc_140035707
0x1400359e7  mov     edx, 19h
0x1400359ec  mov     [rsp+58h+var_38], rsi
0x1400359f1  mov     ecx, 51Ch
0x1400359f6  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x1400359fd  mov     r9, rax
0x140035a00  call    WPP_SF_qq
0x140035a05  mov     rcx, rbx
0x140035a08  call    UlFreeHttpConnection
0x140035a0d  jmp     loc_1400357EB
0x140035a12  mov     edx, 1Ah
0x140035a17  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140035a1e  mov     ecx, 51Ch
0x140035a23  mov     r9, rbp
0x140035a26  call    WPP_SF_q
0x140035a2b  jmp     loc_1400357F8
0x140035a30  lea     rcx, UlThreadPoolArena
0x140035a37  call    UlpAssignThreadPoolWork
0x140035a3c  mov     edi, eax
0x140035a3e  jmp     loc_14003583C
0x140035a43  mov     edx, 49576C55h; Tag
0x140035a48  mov     rcx, rsi; Object
0x140035a4b  call    cs:__imp_ObfReferenceObjectWithTag
0x140035a52  nop     dword ptr [rax+rax+00h]
0x140035a57  jmp     loc_140035863
```

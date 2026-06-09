# UlpConnectionDisconnectWorker

- ea: `0x140037b00`
- end: `0x140038109`
- name: `UlpConnectionDisconnectWorker`
- size: `1545`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140013430`
- `0x140022610`
- `0x140037080`
- `0x140037b00`
- `0x140039360`
- `0x140051454`
- `0x14005e050`
- `0x14006eb10`
- `0x1400eaaac`
- `0x14013dc78`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401cc858`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140037d74`
- `ntoskrnl!KeGetCurrentIrql` at `0x140037d74`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140037e69`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140037e69`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140037df7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140037df7`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140037d9b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140037d9b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140037dd9`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140037dd9`
- `ntoskrnl!KeSetEvent` at `0x140037e87`
- `ntoskrnl!KeSetEvent` at `0x140037e87`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140037e20`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140037e20`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140037c54`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140037c54`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140037c48`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140037c48`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037cf9`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037cf9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140037b49`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140037b49`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140037b34`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140037b34`

## pseudocode

```c
void __fastcall UlpConnectionDisconnectWorker(__int64 a1)
{
  int v2; // ebp
  __int64 v3; // rdx
  __int64 v4; // r8
  _DWORD *v5; // rdi
  __int64 v6; // rcx
  _QWORD *v7; // r14
  _QWORD *v8; // r15
  __int64 v9; // rbp
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v15; // r9
  __int64 CurrentServerSilo; // rsi
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  char v21; // bl
  __int64 v22; // rax
  __int64 v23; // rbp
  ULONG v24; // ebx
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rax
  __int64 v31; // rax

  v2 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 198, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1);
  if ( (BYTE9(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1288, 199, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1, a1 - 112);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 464, 0);
  v5 = (_DWORD *)(a1 + 520);
  if ( (*(_DWORD *)(a1 + 236) & 0x400) != 0 )
    *v5 &= ~0x40u;
  *v5 |= 0x10u;
  if ( (*(_BYTE *)v5 & 0x60) == 0x60 )
    UlCompleteWaitForDisconnects(a1 - 112, 0, v4);
  v6 = *(_QWORD *)(a1 + 456);
  if ( v6 )
    v2 = *(_DWORD *)(v6 + 496);
  v7 = (_QWORD *)(a1 + 264);
  v8 = (_QWORD *)(a1 + 256);
  if ( (BYTE9(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_IIIqL(v6, v3, v4, *(_QWORD *)(a1 + 248), *v8, *v7, v6, v2);
  if ( (*v5 & 2) == 0 && *v8 == *v7 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    {
      if ( a1 == 112 )
        v30 = 0;
      else
        v30 = *(_QWORD *)(a1 - 64);
      WPP_SF_qq(1032, 205, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1 - 112, v30);
    }
    v9 = *(_QWORD *)(a1 + 456);
    v10 = a1;
    if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
    {
      if ( a1 == 112 )
        v26 = 0;
      else
        v26 = *(_QWORD *)(a1 - 64);
      WPP_SF_qq(1038, 46, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1 - 112, v26);
    }
    if ( (*v5 & 0x100) != 0 && v9 && *(_DWORD *)(v9 + 496) == 8 )
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_qq(1038, 47, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1 - 112, v9);
      v31 = *(_QWORD *)(v9 + 2144);
      *(_QWORD *)(v9 + 2128) = v31;
      *(_QWORD *)(v9 + 2152) = v31 - *(_QWORD *)(v9 + 2160);
      *(_QWORD *)(v9 + 2136) = 0;
      *(_DWORD *)(v9 + 496) = 10;
      UlDeliverEntityBody(v9, v10);
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
      WPP_SF_(1038, 48, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
    v11 = *(_QWORD *)(a1 + 456);
    if ( !v11 || *(_BYTE *)(v11 + 2205) )
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_q(1032, 206, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1 - 112);
      UlCloseConnection(a1 - 112);
    }
    else if ( *(int *)(v11 + 496) < 10 )
    {
      if ( (BYTE9(xmmword_1401A2C90) & 1) != 0 )
        WPP_SF_q(776, 207, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1 - 112);
      UlSetErrorCode(*(_QWORD *)(a1 + 456), 1, 0);
      UlSendErrorResponse(a1 - 112);
    }
    else
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 1) == 0 )
        goto LABEL_26;
      WPP_SF_q(1032, 208, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1 - 112);
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 209, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
  }
LABEL_26:
  ExReleasePushLockExclusiveEx(a1 + 464, 0);
  KeLeaveCriticalRegion();
  v12 = _InterlockedDecrement((volatile signed __int32 *)(a1 - 72));
  if ( UxDebugCheckRefcount && v12 <= -1 )
    UlBugCheckEx(3u, a1 - 72, 0xDu, v12);
  if ( !v12 )
  {
    v13 = a1 - 48;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(_QWORD *)(a1 + 976);
    v17 = *(_QWORD *)(a1 - 48);
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v17 || *(_QWORD *)(v13 + 16) || *(_QWORD *)(v13 + 32) )
        UlBugCheckEx(1u, a1 - 48, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      LOBYTE(v15) = 1;
      UlThreadPoolEnqueueWorkItem(0, a1 - 48, UlFreeHttpConnection, v15, CurrentServerSilo, -1);
      goto LABEL_28;
    }
    if ( v17 || *(_QWORD *)(v13 + 16) || *(_QWORD *)(v13 + 32) )
      UlBugCheckEx(1u, a1 - 48, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
    {
      v24 = 0;
      if ( (unsigned int)dword_1401A3F48 > 1 )
      {
        v24 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F60 )
          v24 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == -1 )
        CurrentServerSilo = PsGetCurrentServerSilo();
      *(_QWORD *)(v13 + 32) = CurrentServerSilo;
      UxPodReferenceSilo(CurrentServerSilo, 1230466133, 13);
      *(_BYTE *)(v13 + 24) = 1;
      v25 = *(_QWORD *)(qword_1401A3F50 + 8LL * v24);
      *(_QWORD *)(v13 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v25 + 16), (PSLIST_ENTRY)v13) )
      {
        KeSetEvent((PRKEVENT)(v25 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v25);
      }
      goto LABEL_28;
    }
    v21 = 0;
    if ( CurrentServerSilo == -1 )
    {
      v23 = 0;
    }
    else
    {
      v22 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v23 = v22;
      v21 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v22, CurrentServerSilo);
        UlFreeHttpConnection(v13, v27, v28, v29);
LABEL_45:
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v23);
        PsDetachSiloFromCurrentThread(v23);
        goto LABEL_28;
      }
    }
    UlFreeHttpConnection(v13, v18, v19, v20);
    if ( !v21 )
      goto LABEL_28;
    goto LABEL_45;
  }
LABEL_28:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 201, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
}

```

## disassembly

```asm
0x140037b00  mov     [rsp+arg_18], rbx
0x140037b05  push    rbp
0x140037b06  push    rsi
0x140037b07  push    rdi
0x140037b08  sub     rsp, 50h
0x140037b0c  mov     [rsp+68h+arg_0], r12
0x140037b11  mov     rbx, rcx
0x140037b14  xor     ebp, ebp
0x140037b16  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037b1d  jnz     loc_140037EDA
0x140037b23  lea     r12, [rbx-70h]
0x140037b27  test    byte ptr cs:xmmword_1401A2CA0+9, 1
0x140037b2e  jnz     loc_140037FC4
0x140037b34  call    cs:__imp_KeEnterCriticalRegion
0x140037b3b  nop     dword ptr [rax+rax+00h]
0x140037b40  xor     edx, edx
0x140037b42  lea     rcx, [rbx+1D0h]
0x140037b49  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140037b50  nop     dword ptr [rax+rax+00h]
0x140037b55  test    dword ptr [rbx+0ECh], 400h
0x140037b5f  lea     rdi, [rbx+208h]
0x140037b66  jz      short loc_140037B6B
0x140037b68  and     dword ptr [rdi], 0FFFFFFBFh
0x140037b6b  or      dword ptr [rdi], 10h
0x140037b6e  mov     eax, [rdi]
0x140037b70  and     eax, 60h
0x140037b73  cmp     al, 60h ; '`'
0x140037b75  jz      loc_140037D65
0x140037b7b  mov     rcx, [rbx+1C8h]
0x140037b82  test    rcx, rcx
0x140037b85  jz      short loc_140037B8D
0x140037b87  mov     ebp, [rcx+1F0h]
0x140037b8d  test    byte ptr cs:xmmword_1401A2CA0+9, 1
0x140037b94  mov     [rsp+68h+arg_8], r14
0x140037b99  lea     r14, [rbx+108h]
0x140037ba0  mov     [rsp+68h+arg_10], r15
0x140037ba8  lea     r15, [rbx+100h]
0x140037baf  jnz     loc_140037FE7
0x140037bb5  mov     eax, [rdi]
0x140037bb7  test    al, 2
0x140037bb9  jnz     loc_140037C3F
0x140037bbf  mov     rax, [r14]
0x140037bc2  cmp     [r15], rax
0x140037bc5  jnz     short loc_140037C3F
0x140037bc7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037bce  jnz     loc_140037F94
0x140037bd4  mov     rbp, [rbx+1C8h]
0x140037bdb  mov     rcx, 0FFFFFFFFFFFFFFC0h
0x140037be2  mov     rdx, rbx
0x140037be5  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x140037bec  jnz     loc_140037F13
0x140037bf2  test    dword ptr [rdi], 100h
0x140037bf8  jnz     loc_140038011
0x140037bfe  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x140037c05  jnz     loc_140038058
0x140037c0b  mov     rax, [rbx+1C8h]
0x140037c12  test    rax, rax
0x140037c15  jnz     loc_140037CB0
0x140037c1b  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037c22  jnz     loc_14003809F
0x140037c28  xor     edx, edx
0x140037c2a  mov     rcx, r12
0x140037c2d  call    UlCloseConnection
0x140037c32  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037c39  jnz     loc_140037EF8
0x140037c3f  xor     edx, edx
0x140037c41  lea     rcx, [rbx+1D0h]
0x140037c48  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140037c4f  nop     dword ptr [rax+rax+00h]
0x140037c54  call    cs:__imp_KeLeaveCriticalRegion
0x140037c5b  nop     dword ptr [rax+rax+00h]
0x140037c60  lea     rdx, [rbx-48h]; BugCheckParameter2
0x140037c64  mov     eax, 0FFFFFFFFh
0x140037c69  lock xadd [rdx], eax
0x140037c6d  mov     r15, [rsp+68h+arg_10]
0x140037c75  dec     eax
0x140037c77  cmp     cs:UxDebugCheckRefcount, 0
0x140037c7e  mov     r14, [rsp+68h+arg_8]
0x140037c83  mov     r12, [rsp+68h+arg_0]
0x140037c88  jnz     loc_140037D48
0x140037c8e  test    eax, eax
0x140037c90  jz      short loc_140037CF5
0x140037c92  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037c99  jnz     loc_1400380EE
0x140037c9f  mov     rbx, [rsp+68h+arg_18]
0x140037ca7  add     rsp, 50h
0x140037cab  pop     rdi
0x140037cac  pop     rsi
0x140037cad  pop     rbp
0x140037cae  retn
0x140037cb0  cmp     byte ptr [rax+89Dh], 0
0x140037cb7  jnz     loc_140037C1B
0x140037cbd  cmp     dword ptr [rax+1F0h], 0Ah
0x140037cc4  jl      loc_140038073
0x140037cca  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037cd1  jz      loc_140037C3F
0x140037cd7  mov     edx, 0D0h
0x140037cdc  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x140037ce3  mov     ecx, 408h
0x140037ce8  mov     r9, r12
0x140037ceb  call    WPP_SF_q
0x140037cf0  jmp     loc_140037C32
0x140037cf5  lea     rdi, [rbx-30h]
0x140037cf9  call    cs:__imp_IoGetCurrentProcess
0x140037d00  nop     dword ptr [rax+rax+00h]
0x140037d05  cmp     cs:UxSystemProcess, rax
0x140037d0c  mov     rsi, [rbx+3D0h]
0x140037d13  mov     rcx, [rdi]
0x140037d16  jnz     loc_140037EAA
0x140037d1c  test    rcx, rcx
0x140037d1f  jnz     short loc_140037D2D
0x140037d21  cmp     [rdi+10h], rcx
0x140037d25  jnz     short loc_140037D2D
0x140037d27  cmp     [rdi+20h], rcx
0x140037d2b  jz      short loc_140037D74
0x140037d2d  mov     r9d, 0E1h; BugCheckParameter4
0x140037d33  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140037d3a  mov     rdx, rdi; BugCheckParameter2
0x140037d3d  mov     ecx, 1; BugCheckParameter1
0x140037d42  call    UlBugCheckEx
0x140037d48  cmp     eax, 0FFFFFFFFh
0x140037d4b  jg      loc_140037C8E
0x140037d51  movsxd  r9, eax; BugCheckParameter4
0x140037d54  mov     ecx, 3; BugCheckParameter1
0x140037d59  mov     r8d, 0Dh; BugCheckParameter3
0x140037d5f  call    UlBugCheckEx
0x140037d65  xor     edx, edx
0x140037d67  mov     rcx, r12
0x140037d6a  call    UlCompleteWaitForDisconnects
0x140037d6f  jmp     loc_140037B7B
0x140037d74  call    cs:__imp_KeGetCurrentIrql
0x140037d7b  nop     dword ptr [rax+rax+00h]
0x140037d80  test    al, al
0x140037d82  jnz     short loc_140037DEA
0x140037d84  xor     bl, bl
0x140037d86  xorps   xmm0, xmm0
0x140037d89  movups  [rsp+68h+var_28], xmm0
0x140037d8e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140037d92  jz      loc_140037EA0
0x140037d98  mov     rcx, rsi
0x140037d9b  call    cs:__imp_PsAttachSiloToCurrentThread
0x140037da2  nop     dword ptr [rax+rax+00h]
0x140037da7  mov     rbp, rax
0x140037daa  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140037db1  mov     bl, 1
0x140037db3  jnz     loc_140037F69
0x140037db9  mov     rcx, rdi
0x140037dbc  call    UlFreeHttpConnection
0x140037dc1  test    bl, bl
0x140037dc3  jz      loc_140037C92
0x140037dc9  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140037dd0  jnz     loc_1400380BD
0x140037dd6  mov     rcx, rbp
0x140037dd9  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140037de0  nop     dword ptr [rax+rax+00h]
0x140037de5  jmp     loc_140037C92
0x140037dea  xor     ebx, ebx
0x140037dec  cmp     cs:dword_1401A3F48, 1
0x140037df3  jbe     short loc_140037E1A
0x140037df5  xor     ecx, ecx; ProcNumber
0x140037df7  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140037dfe  nop     dword ptr [rax+rax+00h]
0x140037e03  xor     edx, edx
0x140037e05  div     cs:UxNumberOfProcessors
0x140037e0b  cmp     cs:byte_1401A3F60, 0
0x140037e12  mov     ebx, edx
0x140037e14  jnz     loc_1400380DB
0x140037e1a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140037e1e  jnz     short loc_140037E2F
0x140037e20  call    cs:__imp_PsGetCurrentServerSilo
0x140037e27  nop     dword ptr [rax+rax+00h]
0x140037e2c  mov     rsi, rax
0x140037e2f  mov     edx, 49576C55h
0x140037e34  mov     [rdi+20h], rsi
0x140037e38  mov     r8d, 0Dh
0x140037e3e  mov     rcx, rsi
0x140037e41  call    UxPodReferenceSilo
0x140037e46  mov     byte ptr [rdi+18h], 1
0x140037e4a  mov     rdx, rdi; ListEntry
0x140037e4d  mov     rax, cs:qword_1401A3F50
0x140037e54  mov     ecx, ebx
0x140037e56  mov     rbx, [rax+rcx*8]
0x140037e5a  lea     rax, UlFreeHttpConnection
0x140037e61  mov     [rdi+10h], rax
0x140037e65  lea     rcx, [rbx+10h]; ListHead
0x140037e69  call    cs:__imp_ExpInterlockedPushEntrySList
0x140037e70  nop     dword ptr [rax+rax+00h]
0x140037e75  test    rax, rax
0x140037e78  jnz     loc_140037C92
0x140037e7e  lea     rcx, [rbx+20h]; Event
0x140037e82  xor     r8d, r8d; Wait
0x140037e85  xor     edx, edx; Increment
0x140037e87  call    cs:__imp_KeSetEvent
0x140037e8e  nop     dword ptr [rax+rax+00h]
0x140037e93  mov     rcx, rbx; Context
0x140037e96  call    UlpActivateThreadPoolQueue
0x140037e9b  jmp     loc_140037C92
0x140037ea0  mov     rbp, qword ptr [rsp+68h+var_28+8]
0x140037ea5  jmp     loc_140037DB9
0x140037eaa  test    rcx, rcx
0x140037ead  jnz     short loc_140037EBF
0x140037eaf  cmp     [rdi+10h], rcx
0x140037eb3  jnz     short loc_140037EBF
0x140037eb5  cmp     [rdi+20h], rcx
0x140037eb9  jz      loc_140037F43
0x140037ebf  mov     r9d, 0DBh; BugCheckParameter4
0x140037ec5  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140037ecc  mov     rdx, rdi; BugCheckParameter2
0x140037ecf  mov     ecx, 1; BugCheckParameter1
0x140037ed4  call    UlBugCheckEx
0x140037eda  mov     edx, 0C6h
0x140037edf  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x140037ee6  mov     ecx, 408h
0x140037eeb  mov     r9, rbx
0x140037eee  call    WPP_SF_q
0x140037ef3  jmp     loc_140037B23
0x140037ef8  mov     edx, 0D1h
0x140037efd  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x140037f04  mov     ecx, 408h
0x140037f09  call    WPP_SF_
0x140037f0e  jmp     loc_140037C3F
0x140037f13  test    r12, r12
0x140037f16  jz      short loc_140037F3F
0x140037f18  mov     rax, [rdx+rcx]
0x140037f1c  mov     edx, 2Eh ; '.'
0x140037f21  mov     [rsp+68h+var_48], rax
0x140037f26  mov     ecx, 40Eh
0x140037f2b  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x140037f32  mov     r9, r12
0x140037f35  call    WPP_SF_qq
0x140037f3a  jmp     loc_140037BF2
0x140037f3f  xor     eax, eax
0x140037f41  jmp     short loc_140037F1C
0x140037f43  mov     dword ptr [rsp+68h+var_40], 0FFFFFFFFh
0x140037f4b  lea     r8, UlFreeHttpConnection
0x140037f52  mov     r9b, 1
0x140037f55  mov     [rsp+68h+var_48], rsi
0x140037f5a  mov     rdx, rdi
0x140037f5d  xor     ecx, ecx
0x140037f5f  call    UlThreadPoolEnqueueWorkItem
0x140037f64  jmp     loc_140037C92
0x140037f69  mov     edx, 19h
0x140037f6e  mov     [rsp+68h+var_48], rsi
0x140037f73  mov     ecx, 51Ch
0x140037f78  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140037f7f  mov     r9, rax
0x140037f82  call    WPP_SF_qq
0x140037f87  mov     rcx, rdi
0x140037f8a  call    UlFreeHttpConnection
0x140037f8f  jmp     loc_140037DC9
0x140037f94  test    r12, r12
0x140037f97  jz      short loc_140037FC0
0x140037f99  mov     rax, [rbx-40h]
0x140037f9d  mov     edx, 0CDh
0x140037fa2  mov     [rsp+68h+var_48], rax
0x140037fa7  mov     ecx, 408h
0x140037fac  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x140037fb3  mov     r9, r12
0x140037fb6  call    WPP_SF_qq
0x140037fbb  jmp     loc_140037BD4
0x140037fc0  xor     eax, eax
0x140037fc2  jmp     short loc_140037F9D
0x140037fc4  mov     edx, 0C7h
0x140037fc9  mov     [rsp+68h+var_48], r12
0x140037fce  mov     ecx, 508h
0x140037fd3  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x140037fda  mov     r9, rbx
0x140037fdd  call    WPP_SF_qq
0x140037fe2  jmp     loc_140037B34
0x140037fe7  mov     rax, [r14]
0x140037fea  mov     r9, [rbx+0F8h]
0x140037ff1  mov     [rsp+68h+var_30], ebp
0x140037ff5  mov     [rsp+68h+var_38], rcx
0x140037ffa  mov     [rsp+68h+var_40], rax
0x140037fff  mov     rax, [r15]
0x140038002  mov     [rsp+68h+var_48], rax
0x140038007  call    WPP_SF_IIIqL
0x14003800c  jmp     loc_140037BB5
0x140038011  test    rbp, rbp
0x140038014  jz      loc_140037BFE
0x14003801a  cmp     dword ptr [rbp+1F0h], 8
0x140038021  jnz     loc_140037BFE
0x140038027  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14003802e  jz      loc_140175588
0x140038034  mov     edx, 2Fh ; '/'
0x140038039  mov     [rsp+68h+var_48], rbp
0x14003803e  mov     ecx, 40Eh
0x140038043  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x14003804a  mov     r9, r12
0x14003804d  call    WPP_SF_qq
0x140038052  nop
0x140038053  jmp     loc_140175588
0x140038058  mov     edx, 30h ; '0'
0x14003805d  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x140038064  mov     ecx, 40Eh
0x140038069  call    WPP_SF_
0x14003806e  jmp     loc_140037C0B
0x140038073  test    byte ptr cs:xmmword_1401A2C90+9, 1
0x14003807a  jz      loc_1401755C7
0x140038080  mov     edx, 0CFh
  ... truncated ...
```

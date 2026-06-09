# UlpConnectionDisconnectWorker

- ea: `0x140037ae0`
- end: `0x1400380e9`
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
- `0x140037060`
- `0x140037ae0`
- `0x140039340`
- `0x140051434`
- `0x14005e030`
- `0x14006eaf0`
- `0x1400eaaec`
- `0x14013dd68`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401cc858`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140037d54`
- `ntoskrnl!KeGetCurrentIrql` at `0x140037d54`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140037e49`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140037e49`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140037dd7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140037dd7`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140037d7b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140037d7b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140037db9`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140037db9`
- `ntoskrnl!KeSetEvent` at `0x140037e67`
- `ntoskrnl!KeSetEvent` at `0x140037e67`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140037e00`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140037e00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140037c34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140037c34`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140037c28`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140037c28`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037cd9`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037cd9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140037b29`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140037b29`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140037b14`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140037b14`

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
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v14; // r9
  __int64 CurrentServerSilo; // rsi
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  char v20; // bl
  __int64 v21; // rax
  __int64 v22; // rbp
  ULONG v23; // ebx
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // [rsp+28h] [rbp-40h]

  v2 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 198, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1);
  if ( (BYTE9(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1288, 199, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1, a1 - 112);
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
        v29 = 0;
      else
        v29 = *(_QWORD *)(a1 - 64);
      WPP_SF_qq(1032, 205, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1 - 112, v29);
    }
    v9 = *(_QWORD *)(a1 + 456);
    if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
    {
      if ( a1 == 112 )
        v25 = 0;
      else
        v25 = *(_QWORD *)(a1 - 64);
      WPP_SF_qq(1038, 46, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1 - 112, v25);
    }
    if ( (*v5 & 0x100) != 0 && v9 && *(_DWORD *)(v9 + 496) == 8 )
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_qq(1038, 47, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1 - 112, v9);
      v30 = *(_QWORD *)(v9 + 2144);
      *(_QWORD *)(v9 + 2128) = v30;
      *(_QWORD *)(v9 + 2152) = v30 - *(_QWORD *)(v9 + 2160);
      *(_QWORD *)(v9 + 2136) = 0;
      *(_DWORD *)(v9 + 496) = 10;
      UlDeliverEntityBody(v9);
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
      WPP_SF_(1038, 48, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids);
    v10 = *(_QWORD *)(a1 + 456);
    if ( !v10 || *(_BYTE *)(v10 + 2205) )
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_q(1032, 206, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1 - 112);
      UlCloseConnection(a1 - 112);
    }
    else if ( *(int *)(v10 + 496) < 10 )
    {
      if ( (BYTE9(xmmword_1401A2C90) & 1) != 0 )
        WPP_SF_q(776, 207, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1 - 112);
      UlSetErrorCode(*(_QWORD *)(a1 + 456), 1, 0);
      UlSendErrorResponse(a1 - 112);
    }
    else
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 1) == 0 )
        goto LABEL_26;
      WPP_SF_q(1032, 208, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1 - 112);
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 209, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids);
  }
LABEL_26:
  ExReleasePushLockExclusiveEx(a1 + 464, 0);
  KeLeaveCriticalRegion();
  v11 = _InterlockedDecrement((volatile signed __int32 *)(a1 - 72));
  if ( UxDebugCheckRefcount && v11 <= -1 )
    UlBugCheckEx(3u, a1 - 72, 0xDu, v11);
  if ( !v11 )
  {
    v12 = a1 - 48;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(_QWORD *)(a1 + 976);
    v16 = *(_QWORD *)(a1 - 48);
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v16 || *(_QWORD *)(v12 + 16) || *(_QWORD *)(v12 + 32) )
        UlBugCheckEx(1u, a1 - 48, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      LODWORD(v31) = -1;
      LOBYTE(v14) = 1;
      UlThreadPoolEnqueueWorkItem(0, a1 - 48, UlFreeHttpConnection, v14, CurrentServerSilo, v31);
      goto LABEL_28;
    }
    if ( v16 || *(_QWORD *)(v12 + 16) || *(_QWORD *)(v12 + 32) )
      UlBugCheckEx(1u, a1 - 48, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
    {
      v23 = 0;
      if ( (unsigned int)dword_1401A3F08 > 1 )
      {
        v23 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F20 )
          v23 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == -1 )
        CurrentServerSilo = PsGetCurrentServerSilo();
      *(_QWORD *)(v12 + 32) = CurrentServerSilo;
      UxPodReferenceSilo(CurrentServerSilo, 1230466133, 13);
      *(_BYTE *)(v12 + 24) = 1;
      v24 = *(_QWORD *)(qword_1401A3F10 + 8LL * v23);
      *(_QWORD *)(v12 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v24 + 16), (PSLIST_ENTRY)v12) )
      {
        KeSetEvent((PRKEVENT)(v24 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v24);
      }
      goto LABEL_28;
    }
    v20 = 0;
    if ( CurrentServerSilo == -1 )
    {
      v22 = 0;
    }
    else
    {
      v21 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v22 = v21;
      v20 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v21, CurrentServerSilo);
        UlFreeHttpConnection(v12, v26, v27, v28);
LABEL_45:
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v22);
        PsDetachSiloFromCurrentThread(v22);
        goto LABEL_28;
      }
    }
    UlFreeHttpConnection(v12, v17, v18, v19);
    if ( !v20 )
      goto LABEL_28;
    goto LABEL_45;
  }
LABEL_28:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 201, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids);
}

```

## disassembly

```asm
0x140037ae0  mov     [rsp+arg_18], rbx
0x140037ae5  push    rbp
0x140037ae6  push    rsi
0x140037ae7  push    rdi
0x140037ae8  sub     rsp, 50h
0x140037aec  mov     [rsp+68h+arg_0], r12
0x140037af1  mov     rbx, rcx
0x140037af4  xor     ebp, ebp
0x140037af6  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037afd  jnz     loc_140037EBA
0x140037b03  lea     r12, [rbx-70h]
0x140037b07  test    byte ptr cs:xmmword_1401A2CA0+9, 1
0x140037b0e  jnz     loc_140037FA4
0x140037b14  call    cs:__imp_KeEnterCriticalRegion
0x140037b1b  nop     dword ptr [rax+rax+00h]
0x140037b20  xor     edx, edx
0x140037b22  lea     rcx, [rbx+1D0h]
0x140037b29  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140037b30  nop     dword ptr [rax+rax+00h]
0x140037b35  test    dword ptr [rbx+0ECh], 400h
0x140037b3f  lea     rdi, [rbx+208h]
0x140037b46  jz      short loc_140037B4B
0x140037b48  and     dword ptr [rdi], 0FFFFFFBFh
0x140037b4b  or      dword ptr [rdi], 10h
0x140037b4e  mov     eax, [rdi]
0x140037b50  and     eax, 60h
0x140037b53  cmp     al, 60h ; '`'
0x140037b55  jz      loc_140037D45
0x140037b5b  mov     rcx, [rbx+1C8h]
0x140037b62  test    rcx, rcx
0x140037b65  jz      short loc_140037B6D
0x140037b67  mov     ebp, [rcx+1F0h]
0x140037b6d  test    byte ptr cs:xmmword_1401A2CA0+9, 1
0x140037b74  mov     [rsp+68h+arg_8], r14
0x140037b79  lea     r14, [rbx+108h]
0x140037b80  mov     [rsp+68h+arg_10], r15
0x140037b88  lea     r15, [rbx+100h]
0x140037b8f  jnz     loc_140037FC7
0x140037b95  mov     eax, [rdi]
0x140037b97  test    al, 2
0x140037b99  jnz     loc_140037C1F
0x140037b9f  mov     rax, [r14]
0x140037ba2  cmp     [r15], rax
0x140037ba5  jnz     short loc_140037C1F
0x140037ba7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037bae  jnz     loc_140037F74
0x140037bb4  mov     rbp, [rbx+1C8h]
0x140037bbb  mov     rcx, 0FFFFFFFFFFFFFFC0h
0x140037bc2  mov     rdx, rbx
0x140037bc5  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x140037bcc  jnz     loc_140037EF3
0x140037bd2  test    dword ptr [rdi], 100h
0x140037bd8  jnz     loc_140037FF1
0x140037bde  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x140037be5  jnz     loc_140038038
0x140037beb  mov     rax, [rbx+1C8h]
0x140037bf2  test    rax, rax
0x140037bf5  jnz     loc_140037C90
0x140037bfb  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037c02  jnz     loc_14003807F
0x140037c08  xor     edx, edx
0x140037c0a  mov     rcx, r12
0x140037c0d  call    UlCloseConnection
0x140037c12  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037c19  jnz     loc_140037ED8
0x140037c1f  xor     edx, edx
0x140037c21  lea     rcx, [rbx+1D0h]
0x140037c28  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140037c2f  nop     dword ptr [rax+rax+00h]
0x140037c34  call    cs:__imp_KeLeaveCriticalRegion
0x140037c3b  nop     dword ptr [rax+rax+00h]
0x140037c40  lea     rdx, [rbx-48h]; BugCheckParameter2
0x140037c44  mov     eax, 0FFFFFFFFh
0x140037c49  lock xadd [rdx], eax
0x140037c4d  mov     r15, [rsp+68h+arg_10]
0x140037c55  dec     eax
0x140037c57  cmp     cs:UxDebugCheckRefcount, 0
0x140037c5e  mov     r14, [rsp+68h+arg_8]
0x140037c63  mov     r12, [rsp+68h+arg_0]
0x140037c68  jnz     loc_140037D28
0x140037c6e  test    eax, eax
0x140037c70  jz      short loc_140037CD5
0x140037c72  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037c79  jnz     loc_1400380CE
0x140037c7f  mov     rbx, [rsp+68h+arg_18]
0x140037c87  add     rsp, 50h
0x140037c8b  pop     rdi
0x140037c8c  pop     rsi
0x140037c8d  pop     rbp
0x140037c8e  retn
0x140037c90  cmp     byte ptr [rax+89Dh], 0
0x140037c97  jnz     loc_140037BFB
0x140037c9d  cmp     dword ptr [rax+1F0h], 0Ah
0x140037ca4  jl      loc_140038053
0x140037caa  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140037cb1  jz      loc_140037C1F
0x140037cb7  mov     edx, 0D0h
0x140037cbc  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x140037cc3  mov     ecx, 408h
0x140037cc8  mov     r9, r12
0x140037ccb  call    WPP_SF_q
0x140037cd0  jmp     loc_140037C12
0x140037cd5  lea     rdi, [rbx-30h]
0x140037cd9  call    cs:__imp_IoGetCurrentProcess
0x140037ce0  nop     dword ptr [rax+rax+00h]
0x140037ce5  cmp     cs:UxSystemProcess, rax
0x140037cec  mov     rsi, [rbx+3D0h]
0x140037cf3  mov     rcx, [rdi]
0x140037cf6  jnz     loc_140037E8A
0x140037cfc  test    rcx, rcx
0x140037cff  jnz     short loc_140037D0D
0x140037d01  cmp     [rdi+10h], rcx
0x140037d05  jnz     short loc_140037D0D
0x140037d07  cmp     [rdi+20h], rcx
0x140037d0b  jz      short loc_140037D54
0x140037d0d  mov     r9d, 0E1h; BugCheckParameter4
0x140037d13  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140037d1a  mov     rdx, rdi; BugCheckParameter2
0x140037d1d  mov     ecx, 1; BugCheckParameter1
0x140037d22  call    UlBugCheckEx
0x140037d28  cmp     eax, 0FFFFFFFFh
0x140037d2b  jg      loc_140037C6E
0x140037d31  movsxd  r9, eax; BugCheckParameter4
0x140037d34  mov     ecx, 3; BugCheckParameter1
0x140037d39  mov     r8d, 0Dh; BugCheckParameter3
0x140037d3f  call    UlBugCheckEx
0x140037d45  xor     edx, edx
0x140037d47  mov     rcx, r12
0x140037d4a  call    UlCompleteWaitForDisconnects
0x140037d4f  jmp     loc_140037B5B
0x140037d54  call    cs:__imp_KeGetCurrentIrql
0x140037d5b  nop     dword ptr [rax+rax+00h]
0x140037d60  test    al, al
0x140037d62  jnz     short loc_140037DCA
0x140037d64  xor     bl, bl
0x140037d66  xorps   xmm0, xmm0
0x140037d69  movups  [rsp+68h+var_28], xmm0
0x140037d6e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140037d72  jz      loc_140037E80
0x140037d78  mov     rcx, rsi
0x140037d7b  call    cs:__imp_PsAttachSiloToCurrentThread
0x140037d82  nop     dword ptr [rax+rax+00h]
0x140037d87  mov     rbp, rax
0x140037d8a  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140037d91  mov     bl, 1
0x140037d93  jnz     loc_140037F49
0x140037d99  mov     rcx, rdi
0x140037d9c  call    UlFreeHttpConnection
0x140037da1  test    bl, bl
0x140037da3  jz      loc_140037C72
0x140037da9  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140037db0  jnz     loc_14003809D
0x140037db6  mov     rcx, rbp
0x140037db9  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140037dc0  nop     dword ptr [rax+rax+00h]
0x140037dc5  jmp     loc_140037C72
0x140037dca  xor     ebx, ebx
0x140037dcc  cmp     cs:dword_1401A3F08, 1
0x140037dd3  jbe     short loc_140037DFA
0x140037dd5  xor     ecx, ecx; ProcNumber
0x140037dd7  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140037dde  nop     dword ptr [rax+rax+00h]
0x140037de3  xor     edx, edx
0x140037de5  div     cs:UxNumberOfProcessors
0x140037deb  cmp     cs:byte_1401A3F20, 0
0x140037df2  mov     ebx, edx
0x140037df4  jnz     loc_1400380BB
0x140037dfa  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140037dfe  jnz     short loc_140037E0F
0x140037e00  call    cs:__imp_PsGetCurrentServerSilo
0x140037e07  nop     dword ptr [rax+rax+00h]
0x140037e0c  mov     rsi, rax
0x140037e0f  mov     edx, 49576C55h
0x140037e14  mov     [rdi+20h], rsi
0x140037e18  mov     r8d, 0Dh
0x140037e1e  mov     rcx, rsi
0x140037e21  call    UxPodReferenceSilo
0x140037e26  mov     byte ptr [rdi+18h], 1
0x140037e2a  mov     rdx, rdi; ListEntry
0x140037e2d  mov     rax, cs:qword_1401A3F10
0x140037e34  mov     ecx, ebx
0x140037e36  mov     rbx, [rax+rcx*8]
0x140037e3a  lea     rax, UlFreeHttpConnection
0x140037e41  mov     [rdi+10h], rax
0x140037e45  lea     rcx, [rbx+10h]; ListHead
0x140037e49  call    cs:__imp_ExpInterlockedPushEntrySList
0x140037e50  nop     dword ptr [rax+rax+00h]
0x140037e55  test    rax, rax
0x140037e58  jnz     loc_140037C72
0x140037e5e  lea     rcx, [rbx+20h]; Event
0x140037e62  xor     r8d, r8d; Wait
0x140037e65  xor     edx, edx; Increment
0x140037e67  call    cs:__imp_KeSetEvent
0x140037e6e  nop     dword ptr [rax+rax+00h]
0x140037e73  mov     rcx, rbx; Context
0x140037e76  call    UlpActivateThreadPoolQueue
0x140037e7b  jmp     loc_140037C72
0x140037e80  mov     rbp, qword ptr [rsp+68h+var_28+8]
0x140037e85  jmp     loc_140037D99
0x140037e8a  test    rcx, rcx
0x140037e8d  jnz     short loc_140037E9F
0x140037e8f  cmp     [rdi+10h], rcx
0x140037e93  jnz     short loc_140037E9F
0x140037e95  cmp     [rdi+20h], rcx
0x140037e99  jz      loc_140037F23
0x140037e9f  mov     r9d, 0DBh; BugCheckParameter4
0x140037ea5  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140037eac  mov     rdx, rdi; BugCheckParameter2
0x140037eaf  mov     ecx, 1; BugCheckParameter1
0x140037eb4  call    UlBugCheckEx
0x140037eba  mov     edx, 0C6h
0x140037ebf  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x140037ec6  mov     ecx, 408h
0x140037ecb  mov     r9, rbx
0x140037ece  call    WPP_SF_q
0x140037ed3  jmp     loc_140037B03
0x140037ed8  mov     edx, 0D1h
0x140037edd  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x140037ee4  mov     ecx, 408h
0x140037ee9  call    WPP_SF_
0x140037eee  jmp     loc_140037C1F
0x140037ef3  test    r12, r12
0x140037ef6  jz      short loc_140037F1F
0x140037ef8  mov     rax, [rdx+rcx]
0x140037efc  mov     edx, 2Eh ; '.'
0x140037f01  mov     [rsp+68h+var_48], rax
0x140037f06  mov     ecx, 40Eh
0x140037f0b  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x140037f12  mov     r9, r12
0x140037f15  call    WPP_SF_qq
0x140037f1a  jmp     loc_140037BD2
0x140037f1f  xor     eax, eax
0x140037f21  jmp     short loc_140037EFC
0x140037f23  mov     dword ptr [rsp+68h+var_40], 0FFFFFFFFh
0x140037f2b  lea     r8, UlFreeHttpConnection
0x140037f32  mov     r9b, 1
0x140037f35  mov     [rsp+68h+var_48], rsi
0x140037f3a  mov     rdx, rdi
0x140037f3d  xor     ecx, ecx
0x140037f3f  call    UlThreadPoolEnqueueWorkItem
0x140037f44  jmp     loc_140037C72
0x140037f49  mov     edx, 19h
0x140037f4e  mov     [rsp+68h+var_48], rsi
0x140037f53  mov     ecx, 51Ch
0x140037f58  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140037f5f  mov     r9, rax
0x140037f62  call    WPP_SF_qq
0x140037f67  mov     rcx, rdi
0x140037f6a  call    UlFreeHttpConnection
0x140037f6f  jmp     loc_140037DA9
0x140037f74  test    r12, r12
0x140037f77  jz      short loc_140037FA0
0x140037f79  mov     rax, [rbx-40h]
0x140037f7d  mov     edx, 0CDh
0x140037f82  mov     [rsp+68h+var_48], rax
0x140037f87  mov     ecx, 408h
0x140037f8c  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x140037f93  mov     r9, r12
0x140037f96  call    WPP_SF_qq
0x140037f9b  jmp     loc_140037BB4
0x140037fa0  xor     eax, eax
0x140037fa2  jmp     short loc_140037F7D
0x140037fa4  mov     edx, 0C7h
0x140037fa9  mov     [rsp+68h+var_48], r12
0x140037fae  mov     ecx, 508h
0x140037fb3  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x140037fba  mov     r9, rbx
0x140037fbd  call    WPP_SF_qq
0x140037fc2  jmp     loc_140037B14
0x140037fc7  mov     rax, [r14]
0x140037fca  mov     r9, [rbx+0F8h]
0x140037fd1  mov     [rsp+68h+var_30], ebp
0x140037fd5  mov     [rsp+68h+var_38], rcx
0x140037fda  mov     [rsp+68h+var_40], rax
0x140037fdf  mov     rax, [r15]
0x140037fe2  mov     [rsp+68h+var_48], rax
0x140037fe7  call    WPP_SF_IIIqL
0x140037fec  jmp     loc_140037B95
0x140037ff1  test    rbp, rbp
0x140037ff4  jz      loc_140037BDE
0x140037ffa  cmp     dword ptr [rbp+1F0h], 8
0x140038001  jnz     loc_140037BDE
0x140038007  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14003800e  jz      loc_140175688
0x140038014  mov     edx, 2Fh ; '/'
0x140038019  mov     [rsp+68h+var_48], rbp
0x14003801e  mov     ecx, 40Eh
0x140038023  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x14003802a  mov     r9, r12
0x14003802d  call    WPP_SF_qq
0x140038032  nop
0x140038033  jmp     loc_140175688
0x140038038  mov     edx, 30h ; '0'
0x14003803d  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x140038044  mov     ecx, 40Eh
0x140038049  call    WPP_SF_
0x14003804e  jmp     loc_140037BEB
0x140038053  test    byte ptr cs:xmmword_1401A2C90+9, 1
0x14003805a  jz      loc_1401756C7
0x140038060  mov     edx, 0CFh
  ... truncated ...
```

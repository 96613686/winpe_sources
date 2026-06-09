# UxpTpRestartFastTransmit

- ea: `0x1400558a0`
- end: `0x140055c22`
- name: `UxpTpRestartFastTransmit`
- size: `898`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140053730`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x1400558a0`
- `0x140055c28`
- `0x14005e050`
- `0x14013dc78`
- `0x1401677e0`
- `0x1401c3008`
- `0x1401c3f78`
- `0x1401c4a18`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400559a5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400559a5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140055ada`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140055ada`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140055a31`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140055a31`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140055a8d`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140055a8d`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140055bea`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140055bea`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400559d2`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400559d2`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140055a0e`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140055a0e`
- `ntoskrnl!KeSetEvent` at `0x140055af8`
- `ntoskrnl!KeSetEvent` at `0x140055af8`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140055a5a`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140055a5a`
- `ntoskrnl!IoGetCurrentProcess` at `0x140055939`
- `ntoskrnl!IoGetCurrentProcess` at `0x140055939`

## pseudocode

```c
__int64 (__fastcall *__fastcall UxpTpRestartFastTransmit(__int64 a1, int a2, __int64 a3))(_QWORD, _QWORD, __int64)
{
  __int64 v6; // rsi
  int v7; // eax
  __int64 (__fastcall *result)(_QWORD, _QWORD, __int64); // rax
  __int64 v9; // r14
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v11; // r9
  void *CurrentServerSilo; // r15
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  char v17; // si
  __int64 v18; // rax
  __int64 v19; // r12
  ULONG v20; // esi
  ULONG_PTR v21; // rdx
  int v22; // ecx
  __int64 v23; // rsi
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // [rsp+70h] [rbp+8h] BYREF

  if ( a2 >= 0 )
    UxpTpDequeueTransmitPacket(*(PKSPIN_LOCK *)a1, *(_DWORD *)(a1 + 8), 0, 1u);
  v6 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
  v7 = _InterlockedDecrement((volatile signed __int32 *)(v6 + 40));
  if ( UxDebugCheckRefcount && v7 <= -1 )
    UlBugCheckEx(3u, v6 + 40, 0x2Au, v7);
  if ( !v7 )
  {
    v9 = v6 + 64;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(void **)(v6 + 1088);
    v13 = *(_QWORD *)(v6 + 64);
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v13 || *(_QWORD *)(v6 + 80) || *(_QWORD *)(v6 + 96) )
        UlBugCheckEx(1u, v6 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      LOBYTE(v11) = 1;
      UlThreadPoolEnqueueWorkItem(0, v6 + 64, UlFreeHttpConnection, v11, CurrentServerSilo, -1);
      goto LABEL_5;
    }
    if ( v13 || *(_QWORD *)(v6 + 80) || *(_QWORD *)(v6 + 96) )
      UlBugCheckEx(1u, v6 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
    {
      v20 = 0;
      if ( (unsigned int)dword_1401A3F48 > 1 )
      {
        v20 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F60 )
          v20 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v9 + 32) = CurrentServerSilo;
      v27 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v27);
      v21 = v27 + 24;
      v22 = _InterlockedIncrement((volatile signed __int32 *)(v27 + 24));
      if ( UxDebugCheckRefcount && v22 <= -1 )
        UlBugCheckEx(3u, v21, 0xDu, v22);
      *(_BYTE *)(v9 + 24) = 1;
      v23 = *(_QWORD *)(qword_1401A3F50 + 8LL * v20);
      *(_QWORD *)(v9 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v23 + 16), (PSLIST_ENTRY)v9) )
      {
        KeSetEvent((PRKEVENT)(v23 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v23);
      }
      goto LABEL_5;
    }
    v17 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v19 = 0;
    }
    else
    {
      v18 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v19 = v18;
      v17 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v18, CurrentServerSilo);
        UlFreeHttpConnection(v9, v24, v25, v26);
LABEL_21:
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v19);
        PsDetachSiloFromCurrentThread(v19);
        goto LABEL_5;
      }
    }
    UlFreeHttpConnection(v9, v14, v15, v16);
    if ( !v17 )
      goto LABEL_5;
    goto LABEL_21;
  }
LABEL_5:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qdP(1032, 57, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids, a1, a2, a3);
  result = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 16);
  if ( result )
    return (__int64 (__fastcall *)(_QWORD, _QWORD, __int64))result(*(_QWORD *)(a1 + 24), (unsigned int)a2, a3);
  return result;
}

```

## disassembly

```asm
0x1400558a0  push    rbx
0x1400558a2  push    rbp
0x1400558a3  push    rsi
0x1400558a4  push    rdi
0x1400558a5  sub     rsp, 48h
0x1400558a9  mov     rbp, r8
0x1400558ac  mov     edi, edx
0x1400558ae  mov     rbx, rcx
0x1400558b1  test    edx, edx
0x1400558b3  js      short loc_1400558C6
0x1400558b5  mov     edx, [rcx+8]
0x1400558b8  mov     r9b, 1
0x1400558bb  mov     rcx, [rcx]; SpinLock
0x1400558be  xor     r8d, r8d
0x1400558c1  call    UxpTpDequeueTransmitPacket
0x1400558c6  mov     rax, [rbx]
0x1400558c9  mov     rsi, [rax+8]
0x1400558cd  mov     eax, 0FFFFFFFFh
0x1400558d2  lea     rdx, [rsi+28h]; BugCheckParameter2
0x1400558d6  lock xadd [rdx], eax
0x1400558da  dec     eax
0x1400558dc  cmp     cs:UxDebugCheckRefcount, 0
0x1400558e3  jnz     loc_140055988
0x1400558e9  mov     [rsp+68h+arg_10], r14
0x1400558f1  mov     [rsp+68h+var_28], r15
0x1400558f6  test    eax, eax
0x1400558f8  jz      short loc_140055935
0x1400558fa  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140055901  jnz     loc_140055BFB
0x140055907  mov     rax, [rbx+10h]
0x14005590b  test    rax, rax
0x14005590e  jz      short loc_14005591E
0x140055910  mov     rcx, [rbx+18h]
0x140055914  mov     r8, rbp
0x140055917  mov     edx, edi
0x140055919  call    _guard_dispatch_icall
0x14005591e  mov     r14, [rsp+68h+arg_10]
0x140055926  mov     r15, [rsp+68h+var_28]
0x14005592b  add     rsp, 48h
0x14005592f  pop     rdi
0x140055930  pop     rsi
0x140055931  pop     rbp
0x140055932  pop     rbx
0x140055933  retn
0x140055935  lea     r14, [rsi+40h]
0x140055939  call    cs:__imp_IoGetCurrentProcess
0x140055940  nop     dword ptr [rax+rax+00h]
0x140055945  cmp     cs:UxSystemProcess, rax
0x14005594c  mov     r15, [rsi+440h]
0x140055953  mov     rcx, [r14]
0x140055956  jnz     loc_140055B34
0x14005595c  test    rcx, rcx
0x14005595f  jnz     short loc_14005596D
0x140055961  cmp     [r14+10h], rcx
0x140055965  jnz     short loc_14005596D
0x140055967  cmp     [r14+20h], rcx
0x14005596b  jz      short loc_1400559A5
0x14005596d  mov     r9d, 0E1h; BugCheckParameter4
0x140055973  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14005597a  mov     rdx, r14; BugCheckParameter2
0x14005597d  mov     ecx, 1; BugCheckParameter1
0x140055982  call    UlBugCheckEx
0x140055988  cmp     eax, 0FFFFFFFFh
0x14005598b  jg      loc_1400558E9
0x140055991  movsxd  r9, eax; BugCheckParameter4
0x140055994  mov     ecx, 3; BugCheckParameter1
0x140055999  mov     r8d, 2Ah ; '*'; BugCheckParameter3
0x14005599f  call    UlBugCheckEx
0x1400559a5  call    cs:__imp_KeGetCurrentIrql
0x1400559ac  nop     dword ptr [rax+rax+00h]
0x1400559b1  test    al, al
0x1400559b3  jnz     short loc_140055A24
0x1400559b5  xor     sil, sil
0x1400559b8  mov     [rsp+68h+arg_8], r12
0x1400559bd  xorps   xmm0, xmm0
0x1400559c0  movups  [rsp+68h+var_38], xmm0
0x1400559c5  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1400559c9  jz      loc_140055B2A
0x1400559cf  mov     rcx, r15
0x1400559d2  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400559d9  nop     dword ptr [rax+rax+00h]
0x1400559de  mov     r12, rax
0x1400559e1  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400559e8  mov     sil, 1
0x1400559eb  jnz     loc_140055B86
0x1400559f1  mov     rcx, r14
0x1400559f4  call    UlFreeHttpConnection
0x1400559f9  test    sil, sil
0x1400559fc  jz      short loc_140055A1A
0x1400559fe  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140055a05  jnz     loc_140055BB1
0x140055a0b  mov     rcx, r12
0x140055a0e  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140055a15  nop     dword ptr [rax+rax+00h]
0x140055a1a  mov     r12, [rsp+68h+arg_8]
0x140055a1f  jmp     loc_1400558FA
0x140055a24  xor     esi, esi
0x140055a26  cmp     cs:dword_1401A3F48, 1
0x140055a2d  jbe     short loc_140055A54
0x140055a2f  xor     ecx, ecx; ProcNumber
0x140055a31  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140055a38  nop     dword ptr [rax+rax+00h]
0x140055a3d  xor     edx, edx
0x140055a3f  div     cs:UxNumberOfProcessors
0x140055a45  cmp     cs:byte_1401A3F60, 0
0x140055a4c  mov     esi, edx
0x140055a4e  jnz     loc_140055BCF
0x140055a54  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140055a58  jnz     short loc_140055A69
0x140055a5a  call    cs:__imp_PsGetCurrentServerSilo
0x140055a61  nop     dword ptr [rax+rax+00h]
0x140055a66  mov     r15, rax
0x140055a69  mov     [r14+20h], r15
0x140055a6d  mov     [rsp+68h+arg_0], 0
0x140055a76  test    r15, r15
0x140055a79  jnz     loc_140055BE2
0x140055a7f  mov     edx, cs:UxPodMonitorSlot
0x140055a85  lea     r8, [rsp+68h+arg_0]
0x140055a8a  mov     rcx, r15
0x140055a8d  call    cs:__imp_PsGetPermanentSiloContext
0x140055a94  nop     dword ptr [rax+rax+00h]
0x140055a99  mov     rdx, [rsp+68h+arg_0]
0x140055a9e  mov     ecx, 1
0x140055aa3  add     rdx, 18h; BugCheckParameter2
0x140055aa7  lock xadd [rdx], ecx
0x140055aab  inc     ecx
0x140055aad  cmp     cs:UxDebugCheckRefcount, 0
0x140055ab4  jnz     short loc_140055B11
0x140055ab6  mov     byte ptr [r14+18h], 1
0x140055abb  mov     rdx, r14; ListEntry
0x140055abe  mov     rax, cs:qword_1401A3F50
0x140055ac5  mov     ecx, esi
0x140055ac7  mov     rsi, [rax+rcx*8]
0x140055acb  lea     rax, UlFreeHttpConnection
0x140055ad2  mov     [r14+10h], rax
0x140055ad6  lea     rcx, [rsi+10h]; ListHead
0x140055ada  call    cs:__imp_ExpInterlockedPushEntrySList
0x140055ae1  nop     dword ptr [rax+rax+00h]
0x140055ae6  test    rax, rax
0x140055ae9  jnz     loc_1400558FA
0x140055aef  lea     rcx, [rsi+20h]; Event
0x140055af3  xor     r8d, r8d; Wait
0x140055af6  xor     edx, edx; Increment
0x140055af8  call    cs:__imp_KeSetEvent
0x140055aff  nop     dword ptr [rax+rax+00h]
0x140055b04  mov     rcx, rsi; Context
0x140055b07  call    UlpActivateThreadPoolQueue
0x140055b0c  jmp     loc_1400558FA
0x140055b11  cmp     ecx, 0FFFFFFFFh
0x140055b14  jg      short loc_140055AB6
0x140055b16  movsxd  r9, ecx; BugCheckParameter4
0x140055b19  mov     r8d, 0Dh; BugCheckParameter3
0x140055b1f  mov     ecx, 3; BugCheckParameter1
0x140055b24  call    UlBugCheckEx
0x140055b2a  mov     r12, qword ptr [rsp+68h+var_38+8]
0x140055b2f  jmp     loc_1400559F1
0x140055b34  test    rcx, rcx
0x140055b37  jnz     short loc_140055B45
0x140055b39  cmp     [r14+10h], rcx
0x140055b3d  jnz     short loc_140055B45
0x140055b3f  cmp     [r14+20h], rcx
0x140055b43  jz      short loc_140055B60
0x140055b45  mov     r9d, 0DBh; BugCheckParameter4
0x140055b4b  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140055b52  mov     rdx, r14; BugCheckParameter2
0x140055b55  mov     ecx, 1; BugCheckParameter1
0x140055b5a  call    UlBugCheckEx
0x140055b60  mov     dword ptr [rsp+68h+var_40], 0FFFFFFFFh
0x140055b68  lea     r8, UlFreeHttpConnection
0x140055b6f  mov     r9b, 1
0x140055b72  mov     [rsp+68h+var_48], r15
0x140055b77  mov     rdx, r14
0x140055b7a  xor     ecx, ecx
0x140055b7c  call    UlThreadPoolEnqueueWorkItem
0x140055b81  jmp     loc_1400558FA
0x140055b86  mov     edx, 19h
0x140055b8b  mov     [rsp+68h+var_48], r15
0x140055b90  mov     ecx, 51Ch
0x140055b95  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140055b9c  mov     r9, rax
0x140055b9f  call    WPP_SF_qq
0x140055ba4  mov     rcx, r14
0x140055ba7  call    UlFreeHttpConnection
0x140055bac  jmp     loc_1400559FE
0x140055bb1  mov     edx, 1Ah
0x140055bb6  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140055bbd  mov     ecx, 51Ch
0x140055bc2  mov     r9, r12
0x140055bc5  call    WPP_SF_q
0x140055bca  jmp     loc_140055A0B
0x140055bcf  lea     rcx, UlThreadPoolArena
0x140055bd6  call    UlpAssignThreadPoolWork
0x140055bdb  mov     esi, eax
0x140055bdd  jmp     loc_140055A54
0x140055be2  mov     edx, 49576C55h; Tag
0x140055be7  mov     rcx, r15; Object
0x140055bea  call    cs:__imp_ObfReferenceObjectWithTag
0x140055bf1  nop     dword ptr [rax+rax+00h]
0x140055bf6  jmp     loc_140055A7F
0x140055bfb  mov     edx, 39h ; '9'
0x140055c00  mov     [rsp+68h+var_40], rbp
0x140055c05  mov     ecx, 408h
0x140055c0a  mov     dword ptr [rsp+68h+var_48], edi
0x140055c0e  mov     r9, rbx
0x140055c11  lea     r8, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids
0x140055c18  call    WPP_SF_qdP
0x140055c1d  jmp     loc_140055907
```

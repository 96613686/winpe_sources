# UlConnectionCleanupWorker

- ea: `0x1400568e0`
- end: `0x140056f88`
- name: `UlConnectionCleanupWorker`
- size: `1704`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140055320`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140035a70`
- `0x1400568e0`
- `0x140056f90`
- `0x140058870`
- `0x14005e0f0`
- `0x140061ea0`
- `0x140062bf0`
- `0x14006eb10`
- `0x140070c18`
- `0x1400a026c`
- `0x1400a398c`
- `0x1400b111c`
- `0x1401677e0`
- `0x1401c3008`
- `0x1401c37f8`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140056af1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056ba6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056c5f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056af1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056ba6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056c5f`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140056bce`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140056c82`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140056bce`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140056c82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400569ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400569ea`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400569de`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400569de`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056ab6`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056b27`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056b76`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056ab6`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056b27`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056b76`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005697c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005697c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140056967`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140056967`

## pseudocode

```c
__int64 __fastcall UlConnectionCleanupWorker(__int64 *BugCheckParameter2)
{
  __int64 *v2; // rbx
  volatile signed __int32 *v3; // rdi
  int v4; // eax
  char v5; // r15
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r13
  __int64 result; // rax
  __int64 *v10; // rbx
  int v11; // esi
  int v12; // eax
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v14; // r9
  __int64 v15; // r13
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  struct _KPROCESS *v20; // rax
  __int64 v21; // r9
  __int64 v22; // r12
  __int64 v23; // rcx
  struct _KPROCESS *v24; // rax
  __int64 v25; // r9
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // r15d
  __int64 v39; // r9
  _QWORD *v40; // r15
  __int128 v41; // [rsp+50h] [rbp+7h] BYREF
  char v42; // [rsp+B0h] [rbp+67h] BYREF
  unsigned __int8 v43; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 v44; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v45; // [rsp+C8h] [rbp+7Fh] BYREF

  v42 = 0;
  v44 = 0;
  v45 = 0;
  v43 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 24, WPP_682cf469470432b235cb9a4961616e40_Traceguids, BugCheckParameter2);
  v2 = BugCheckParameter2 - 8;
  if ( (BYTE9(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1288, 25, WPP_682cf469470432b235cb9a4961616e40_Traceguids, BugCheckParameter2 - 8);
  UlCleanupBundle(v2 + 81);
  v3 = (volatile signed __int32 *)(v2 + 5);
  v4 = _InterlockedIncrement((volatile signed __int32 *)v2 + 10);
  if ( UxDebugCheckRefcount && v4 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v2 + 5), 0x21u, v4);
  v5 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v2 + 72, 0);
  v8 = v2[71];
  if ( v8 )
  {
    UlQueryRequestQueueRequestState(v2[71], &v42, &v43);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v8 + 2228), 1, 0) && *(_QWORD *)(v8 + 1376) && v42 )
    {
      v5 = 1;
      if ( (int)UlpZombifyHttpConnection(BugCheckParameter2 - 8) >= 0 )
        goto LABEL_7;
      UlErrorLog((_DWORD)BugCheckParameter2 - 64, v8, (unsigned int)"Connection_Dropped_List_Full", 28, 0, 1, 0);
LABEL_93:
      UlUnlinkHttpRequest(v8, v35, v36, v37);
      v5 = 0;
      v2[71] = 0;
      *((_DWORD *)v2 + 158) |= 2u;
      goto LABEL_8;
    }
    if ( (*((_DWORD *)v2 + 86) & 0x80u) != 0 )
    {
      UlpErrorLogConnectionReset(BugCheckParameter2 - 8, v8, v43);
      goto LABEL_93;
    }
    if ( *(_DWORD *)(v8 + 1868) || *(_DWORD *)(v8 + 2116) == 1 )
      goto LABEL_93;
    v40 = v2 + 62;
    if ( UxKirHttpBugFix25Q1 )
    {
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v2 + 62, 12, &v44, &v45, 0, 0);
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, __int64 *, _QWORD, _QWORD))(v2[63] + 136))(
              *v40,
              12,
              &v44,
              &v45,
              0,
              0);
      v38 = v34;
      if ( (BYTE3(xmmword_1401A2CA0) & 2) == 0 )
        goto LABEL_73;
    }
    else
    {
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v2 + 62, 12, &v44, 0, 0, 0);
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, _QWORD, _QWORD, _QWORD))(v2[63] + 136))(
              *v40,
              12,
              &v44,
              0,
              0,
              0);
      v38 = v34;
      if ( (BYTE3(xmmword_1401A2CA0) & 2) == 0 )
        goto LABEL_73;
    }
    WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v34);
LABEL_73:
    if ( v38 >= 0 )
    {
      v36 = v44;
      if ( v44 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *(_BYTE *)(v44 + v39) );
        UlErrorLog((_DWORD)BugCheckParameter2 - 64, v8, v44, v39, v45, 1, 0);
      }
    }
    goto LABEL_93;
  }
LABEL_7:
  *((_DWORD *)v2 + 158) |= 2u;
  if ( v5 )
    goto LABEL_9;
LABEL_8:
  if ( v2[6] )
  {
    UxFreeOpaqueId();
    v2[6] = 0;
    v12 = _InterlockedDecrement(v3);
    if ( UxDebugCheckRefcount && v12 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v2 + 5), 0x10u, v12);
    if ( !v12 )
    {
      CurrentProcess = IoGetCurrentProcess();
      v15 = v2[136];
      v16 = *BugCheckParameter2;
      if ( UxSystemProcess == CurrentProcess )
      {
        v41 = 0;
        if ( v16 || BugCheckParameter2[2] || BugCheckParameter2[4] )
          goto LABEL_33;
        if ( !KeGetCurrentIrql() )
        {
          UxPodAttachThread(v15, &v41);
          UlFreeHttpConnection((__int64)BugCheckParameter2, v17, v18, v19);
          UxPodDetachThread(&v41);
          goto LABEL_9;
        }
      }
      else if ( v16 || BugCheckParameter2[2] || BugCheckParameter2[4] )
      {
        goto LABEL_61;
      }
      LOBYTE(v14) = 1;
      UlThreadPoolEnqueueWorkItem(0, BugCheckParameter2, UlFreeHttpConnection, v14, v15, -1);
    }
  }
LABEL_9:
  *((_DWORD *)v2 + 158) |= 8u;
  if ( (v2[79] & 0x20) != 0 )
  {
    LOBYTE(v6) = 1;
    UlCompleteWaitForDisconnects((__int64)(BugCheckParameter2 - 8), v6, v7);
  }
  UlCleanupConnectionCouplings((__int64)(BugCheckParameter2 - 8));
  ExReleasePushLockExclusiveEx(v2 + 72, 0);
  KeLeaveCriticalRegion();
  result = (unsigned int)_InterlockedDecrement(v3);
  if ( UxDebugCheckRefcount && (int)result <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v2 + 5), 0x21u, (int)result);
  v10 = v2 + 136;
  if ( !(_DWORD)result )
  {
    v20 = IoGetCurrentProcess();
    v22 = *v10;
    v23 = *BugCheckParameter2;
    if ( UxSystemProcess == v20 )
    {
      if ( v23 || BugCheckParameter2[2] || BugCheckParameter2[4] )
        goto LABEL_33;
      if ( !KeGetCurrentIrql() )
      {
        v41 = 0;
        if ( v22 != -1 )
        {
          LOBYTE(v41) = 1;
          v33 = PsAttachSiloToCurrentThread(v22);
          *((_QWORD *)&v41 + 1) = v33;
          if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v33, v22);
        }
        UlFreeHttpConnection((__int64)BugCheckParameter2, v31, v32, v21);
        result = UxPodDetachThread(&v41);
        goto LABEL_13;
      }
    }
    else if ( v23 || BugCheckParameter2[2] || BugCheckParameter2[4] )
    {
      goto LABEL_61;
    }
    LOBYTE(v21) = 1;
    result = UlThreadPoolEnqueueWorkItem(0, BugCheckParameter2, UlFreeHttpConnection, v21, v22, -1);
  }
LABEL_13:
  if ( !v5 )
  {
    v11 = _InterlockedDecrement(v3);
    if ( UxDebugCheckRefcount && v11 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v3, 0xDu, v11);
    if ( !v11 )
    {
      v24 = IoGetCurrentProcess();
      v26 = *v10;
      v27 = *BugCheckParameter2;
      if ( UxSystemProcess == v24 )
      {
        if ( !v27 && !BugCheckParameter2[2] && !BugCheckParameter2[4] )
        {
          if ( !KeGetCurrentIrql() )
          {
            v41 = 0;
            if ( v26 != -1 )
            {
              LOBYTE(v41) = 1;
              v30 = PsAttachSiloToCurrentThread(v26);
              *((_QWORD *)&v41 + 1) = v30;
              if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
                WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v30, v26);
            }
            UlFreeHttpConnection((__int64)BugCheckParameter2, v28, v29, v25);
            result = UxPodDetachThread(&v41);
            goto LABEL_16;
          }
LABEL_55:
          LOBYTE(v25) = 1;
          result = UlThreadPoolEnqueueWorkItem(0, BugCheckParameter2, UlFreeHttpConnection, v25, v26, -1);
          goto LABEL_16;
        }
LABEL_33:
        UlBugCheckEx(1u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
      }
      if ( !v27 && !BugCheckParameter2[2] && !BugCheckParameter2[4] )
        goto LABEL_55;
LABEL_61:
      UlBugCheckEx(1u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
    }
  }
LABEL_16:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    return WPP_SF_(1032, 26, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1400568e0  push    rbp
0x1400568e2  push    rbx
0x1400568e3  push    rdi
0x1400568e4  push    r14
0x1400568e6  lea     rbp, [rsp-3Fh]
0x1400568eb  sub     rsp, 88h
0x1400568f2  xor     eax, eax
0x1400568f4  mov     [rbp+57h+arg_0], 0
0x1400568f8  mov     [rbp+57h+arg_10], rax
0x1400568fc  mov     r14, rcx
0x1400568ff  mov     [rbp+57h+arg_18], rax
0x140056903  mov     [rbp+57h+arg_8], 0
0x140056907  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005690e  jnz     loc_140056F22
0x140056914  lea     rbx, [r14-40h]
0x140056918  test    byte ptr cs:xmmword_1401A2CA0+9, 1
0x14005691f  jnz     loc_140056F40
0x140056925  lea     rcx, [rbx+288h]
0x14005692c  call    UlCleanupBundle
0x140056931  mov     eax, 1
0x140056936  lea     rdi, [rbx+28h]
0x14005693a  lock xadd [rdi], eax
0x14005693e  inc     eax
0x140056940  cmp     cs:UxDebugCheckRefcount, 0
0x140056947  jnz     loc_140056A6C
0x14005694d  mov     [rsp+0A0h+var_20], rsi
0x140056955  mov     [rsp+0A0h+var_28], r12
0x14005695a  mov     [rsp+0A0h+var_30], r13
0x14005695f  mov     [rsp+0A0h+var_38], r15
0x140056964  xor     r15b, r15b
0x140056967  call    cs:__imp_KeEnterCriticalRegion
0x14005696e  nop     dword ptr [rax+rax+00h]
0x140056973  xor     edx, edx
0x140056975  lea     rcx, [rbx+240h]
0x14005697c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140056983  nop     dword ptr [rax+rax+00h]
0x140056988  mov     r13, [rbx+238h]
0x14005698f  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140056996  test    r13, r13
0x140056999  jnz     loc_140176F98
0x14005699f  or      dword ptr [rbx+278h], 2
0x1400569a6  test    r15b, r15b
0x1400569a9  jnz     short loc_1400569B8
0x1400569ab  mov     rcx, [rbx+30h]
0x1400569af  test    rcx, rcx
0x1400569b2  jnz     loc_140056A8C
0x1400569b8  or      dword ptr [rbx+278h], 8
0x1400569bf  mov     eax, [rbx+278h]
0x1400569c5  test    al, 20h
0x1400569c7  jnz     loc_140056F5E
0x1400569cd  mov     rcx, rbx
0x1400569d0  call    UlCleanupConnectionCouplings
0x1400569d5  xor     edx, edx
0x1400569d7  lea     rcx, [rbx+240h]
0x1400569de  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400569e5  nop     dword ptr [rax+rax+00h]
0x1400569ea  call    cs:__imp_KeLeaveCriticalRegion
0x1400569f1  nop     dword ptr [rax+rax+00h]
0x1400569f6  mov     eax, esi
0x1400569f8  lock xadd [rdi], eax
0x1400569fc  dec     eax
0x1400569fe  cmp     cs:UxDebugCheckRefcount, 0
0x140056a05  jnz     loc_140056C01
0x140056a0b  add     rbx, 440h
0x140056a12  test    eax, eax
0x140056a14  jz      loc_140056B27
0x140056a1a  test    r15b, r15b
0x140056a1d  jnz     short loc_140056A3A
0x140056a1f  lock xadd [rdi], esi
0x140056a23  dec     esi
0x140056a25  cmp     cs:UxDebugCheckRefcount, r15b
0x140056a2c  jnz     loc_140056C20
0x140056a32  test    esi, esi
0x140056a34  jz      loc_140056B76
0x140056a3a  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140056a41  jnz     loc_140056F6D
0x140056a47  mov     r13, [rsp+0A0h+var_30]
0x140056a4c  mov     r12, [rsp+0A0h+var_28]
0x140056a51  mov     rsi, [rsp+0A0h+var_20]
0x140056a59  mov     r15, [rsp+0A0h+var_38]
0x140056a5e  add     rsp, 88h
0x140056a65  pop     r14
0x140056a67  pop     rdi
0x140056a68  pop     rbx
0x140056a69  pop     rbp
0x140056a6a  retn
0x140056a6c  cmp     eax, 0FFFFFFFFh
0x140056a6f  jg      loc_14005694D
0x140056a75  movsxd  r9, eax; BugCheckParameter4
0x140056a78  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140056a7e  mov     rdx, rdi; BugCheckParameter2
0x140056a81  mov     ecx, 3; BugCheckParameter1
0x140056a86  call    UlBugCheckEx
0x140056a8c  call    UxFreeOpaqueId
0x140056a91  mov     eax, esi
0x140056a93  mov     qword ptr [rbx+30h], 0
0x140056a9b  lock xadd [rdi], eax
0x140056a9f  dec     eax
0x140056aa1  cmp     cs:UxDebugCheckRefcount, 0
0x140056aa8  jnz     loc_140056C40
0x140056aae  test    eax, eax
0x140056ab0  jnz     loc_1400569B8
0x140056ab6  call    cs:__imp_IoGetCurrentProcess
0x140056abd  nop     dword ptr [rax+rax+00h]
0x140056ac2  cmp     cs:UxSystemProcess, rax
0x140056ac9  mov     r13, [rbx+440h]
0x140056ad0  mov     rcx, [r14]
0x140056ad3  jnz     loc_140056D75
0x140056ad9  xorps   xmm0, xmm0
0x140056adc  movups  [rbp+57h+var_50], xmm0
0x140056ae0  test    rcx, rcx
0x140056ae3  jnz     short loc_140056B5B
0x140056ae5  cmp     [r14+10h], rcx
0x140056ae9  jnz     short loc_140056B5B
0x140056aeb  cmp     [r14+20h], rcx
0x140056aef  jnz     short loc_140056B5B
0x140056af1  call    cs:__imp_KeGetCurrentIrql
0x140056af8  nop     dword ptr [rax+rax+00h]
0x140056afd  test    al, al
0x140056aff  jnz     loc_140056D08
0x140056b05  lea     rdx, [rbp+57h+var_50]
0x140056b09  mov     rcx, r13
0x140056b0c  call    UxPodAttachThread
0x140056b11  mov     rcx, r14
0x140056b14  call    UlFreeHttpConnection
0x140056b19  lea     rcx, [rbp+57h+var_50]
0x140056b1d  call    UxPodDetachThread
0x140056b22  jmp     loc_1400569B8
0x140056b27  call    cs:__imp_IoGetCurrentProcess
0x140056b2e  nop     dword ptr [rax+rax+00h]
0x140056b33  cmp     cs:UxSystemProcess, rax
0x140056b3a  mov     r12, [rbx]
0x140056b3d  mov     rcx, [r14]
0x140056b40  jnz     loc_140056D2E
0x140056b46  test    rcx, rcx
0x140056b49  jnz     short loc_140056B5B
0x140056b4b  cmp     [r14+10h], rcx
0x140056b4f  jnz     short loc_140056B5B
0x140056b51  cmp     [r14+20h], rcx
0x140056b55  jz      loc_140056C5F
0x140056b5b  mov     r9d, 0E1h; BugCheckParameter4
0x140056b61  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140056b68  mov     rdx, r14; BugCheckParameter2
0x140056b6b  mov     ecx, 1; BugCheckParameter1
0x140056b70  call    UlBugCheckEx
0x140056b76  call    cs:__imp_IoGetCurrentProcess
0x140056b7d  nop     dword ptr [rax+rax+00h]
0x140056b82  cmp     cs:UxSystemProcess, rax
0x140056b89  mov     rbx, [rbx]
0x140056b8c  mov     rcx, [r14]
0x140056b8f  jnz     loc_140056D5E
0x140056b95  test    rcx, rcx
0x140056b98  jnz     short loc_140056B5B
0x140056b9a  cmp     [r14+10h], rcx
0x140056b9e  jnz     short loc_140056B5B
0x140056ba0  cmp     [r14+20h], rcx
0x140056ba4  jnz     short loc_140056B5B
0x140056ba6  call    cs:__imp_KeGetCurrentIrql
0x140056bad  nop     dword ptr [rax+rax+00h]
0x140056bb2  test    al, al
0x140056bb4  jnz     loc_140056CDB
0x140056bba  xorps   xmm0, xmm0
0x140056bbd  movups  [rbp+57h+var_50], xmm0
0x140056bc1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140056bc5  jz      short loc_140056BEB
0x140056bc7  mov     rcx, rbx
0x140056bca  mov     byte ptr [rbp+57h+var_50], 1
0x140056bce  call    cs:__imp_PsAttachSiloToCurrentThread
0x140056bd5  nop     dword ptr [rax+rax+00h]
0x140056bda  mov     qword ptr [rbp+57h+var_50+8], rax
0x140056bde  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140056be5  jnz     loc_140056DA8
0x140056beb  mov     rcx, r14
0x140056bee  call    UlFreeHttpConnection
0x140056bf3  lea     rcx, [rbp+57h+var_50]
0x140056bf7  call    UxPodDetachThread
0x140056bfc  jmp     loc_140056A3A
0x140056c01  cmp     eax, esi
0x140056c03  jg      loc_140056A0B
0x140056c09  movsxd  r9, eax; BugCheckParameter4
0x140056c0c  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140056c12  mov     rdx, rdi; BugCheckParameter2
0x140056c15  mov     ecx, 3; BugCheckParameter1
0x140056c1a  call    UlBugCheckEx
0x140056c20  cmp     esi, 0FFFFFFFFh
0x140056c23  jg      loc_140056A32
0x140056c29  movsxd  r9, esi; BugCheckParameter4
0x140056c2c  mov     r8d, 0Dh; BugCheckParameter3
0x140056c32  mov     rdx, rdi; BugCheckParameter2
0x140056c35  mov     ecx, 3; BugCheckParameter1
0x140056c3a  call    UlBugCheckEx
0x140056c40  cmp     eax, esi
0x140056c42  jg      loc_140056AAE
0x140056c48  movsxd  r9, eax; BugCheckParameter4
0x140056c4b  mov     r8d, 10h; BugCheckParameter3
0x140056c51  mov     rdx, rdi; BugCheckParameter2
0x140056c54  mov     ecx, 3; BugCheckParameter1
0x140056c59  call    UlBugCheckEx
0x140056c5f  call    cs:__imp_KeGetCurrentIrql
0x140056c66  nop     dword ptr [rax+rax+00h]
0x140056c6b  test    al, al
0x140056c6d  jnz     short loc_140056CB5
0x140056c6f  xorps   xmm0, xmm0
0x140056c72  movups  [rbp+57h+var_50], xmm0
0x140056c76  cmp     r12, rsi
0x140056c79  jz      short loc_140056C9F
0x140056c7b  mov     rcx, r12
0x140056c7e  mov     byte ptr [rbp+57h+var_50], 1
0x140056c82  call    cs:__imp_PsAttachSiloToCurrentThread
0x140056c89  nop     dword ptr [rax+rax+00h]
0x140056c8e  mov     qword ptr [rbp+57h+var_50+8], rax
0x140056c92  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140056c99  jnz     loc_140056D85
0x140056c9f  mov     rcx, r14
0x140056ca2  call    UlFreeHttpConnection
0x140056ca7  lea     rcx, [rbp+57h+var_50]
0x140056cab  call    UxPodDetachThread
0x140056cb0  jmp     loc_140056A1A
0x140056cb5  mov     dword ptr [rsp+0A0h+var_78], 0FFFFFFFFh
0x140056cbd  lea     r8, UlFreeHttpConnection
0x140056cc4  mov     r9b, 1
0x140056cc7  mov     [rsp+0A0h+var_80], r12
0x140056ccc  mov     rdx, r14
0x140056ccf  xor     ecx, ecx
0x140056cd1  call    UlThreadPoolEnqueueWorkItem
0x140056cd6  jmp     loc_140056A1A
0x140056cdb  mov     dword ptr [rsp+0A0h+var_78], 0FFFFFFFFh
0x140056ce3  lea     r8, UlFreeHttpConnection
0x140056cea  mov     r9b, 1
0x140056ced  mov     [rsp+0A0h+var_80], rbx
0x140056cf2  mov     rdx, r14
0x140056cf5  xor     ecx, ecx
0x140056cf7  call    UlThreadPoolEnqueueWorkItem
0x140056cfc  jmp     loc_140056A3A
0x140056d01  cmp     qword ptr [r14+20h], 0
0x140056d06  jnz     short loc_140056D43
0x140056d08  mov     dword ptr [rsp+0A0h+var_78], 0FFFFFFFFh
0x140056d10  lea     r8, UlFreeHttpConnection
0x140056d17  mov     r9b, 1
0x140056d1a  mov     [rsp+0A0h+var_80], r13
0x140056d1f  mov     rdx, r14
0x140056d22  xor     ecx, ecx
0x140056d24  call    UlThreadPoolEnqueueWorkItem
0x140056d29  jmp     loc_1400569B8
0x140056d2e  test    rcx, rcx
0x140056d31  jnz     short loc_140056D43
0x140056d33  cmp     [r14+10h], rcx
0x140056d37  jnz     short loc_140056D43
0x140056d39  cmp     [r14+20h], rcx
0x140056d3d  jz      loc_140056CB5
0x140056d43  mov     r9d, 0DBh; BugCheckParameter4
0x140056d49  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140056d50  mov     rdx, r14; BugCheckParameter2
0x140056d53  mov     ecx, 1; BugCheckParameter1
0x140056d58  call    UlBugCheckEx
0x140056d5e  test    rcx, rcx
0x140056d61  jnz     short loc_140056D43
0x140056d63  cmp     [r14+10h], rcx
0x140056d67  jnz     short loc_140056D43
0x140056d69  cmp     [r14+20h], rcx
0x140056d6d  jz      loc_140056CDB
0x140056d73  jmp     short loc_140056D43
0x140056d75  test    rcx, rcx
0x140056d78  jnz     short loc_140056D43
0x140056d7a  cmp     [r14+10h], rcx
0x140056d7e  jnz     short loc_140056D43
0x140056d80  jmp     loc_140056D01
0x140056d85  mov     edx, 19h
0x140056d8a  mov     [rsp+0A0h+var_80], r12
0x140056d8f  mov     ecx, 51Ch
0x140056d94  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140056d9b  mov     r9, rax
0x140056d9e  call    WPP_SF_qq
0x140056da3  jmp     loc_140056C9F
0x140056da8  mov     edx, 19h
0x140056dad  mov     [rsp+0A0h+var_80], rbx
0x140056db2  mov     ecx, 51Ch
0x140056db7  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140056dbe  mov     r9, rax
0x140056dc1  call    WPP_SF_qq
0x140056dc6  jmp     loc_140056BEB
0x140056dcb  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x140056dd2  jz      short loc_140056E19
0x140056dd4  mov     [rsp+0A0h+var_60], 0
0x140056ddd  lea     rax, [rbp+57h+arg_18]
0x140056de1  mov     [rsp+0A0h+var_68], 0
0x140056dea  lea     r8, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids
0x140056df1  mov     [rsp+0A0h+var_70], rax
0x140056df6  mov     edx, 0Ah
0x140056dfb  lea     rax, [rbp+57h+arg_10]
0x140056dff  mov     ecx, 419h
0x140056e04  mov     [rsp+0A0h+var_78], rax
0x140056e09  mov     r9, r15
0x140056e0c  mov     dword ptr [rsp+0A0h+var_80], 0Ch
0x140056e14  call    WPP_SF_qLqqqq
0x140056e19  mov     rax, [r15+8]
0x140056e1d  lea     r9, [rbp+57h+arg_18]
0x140056e21  mov     rcx, [r15]
0x140056e24  lea     r8, [rbp+57h+arg_10]
0x140056e28  mov     [rsp+0A0h+var_78], 0
  ... truncated ...
```

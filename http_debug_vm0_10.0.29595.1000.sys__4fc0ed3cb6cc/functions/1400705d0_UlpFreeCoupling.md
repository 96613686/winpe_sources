# UlpFreeCoupling

- ea: `0x1400705d0`
- end: `0x140070bf2`
- name: `UlpFreeCoupling`
- size: `1570`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `15`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a520`
- `0x14003deb0`
- `0x140056f70`
- `0x14005e0d0`
- `0x14005f3a0`
- `0x14006ce20`
- `0x14006eaf0`
- `0x14006f200`
- `0x140071234`
- `0x140071770`
- `0x140071f60`
- `0x1400cbc50`
- `0x1400cc97c`
- `0x1400ce370`
- `0x1400cefa0`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140049d08`
- `0x14005dfd0`
- `0x14005e030`
- `0x1400705d0`
- `0x14009620c`
- `0x1400a031c`
- `0x14013dd68`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400708fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400708fe`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140070a35`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140070a35`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400707b8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400707b8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070991`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070991`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x1400709e9`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x1400709e9`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140070bac`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140070bac`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14007092e`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14007092e`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14007096a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14007096a`
- `ntoskrnl!KeSetEvent` at `0x140070a53`
- `ntoskrnl!KeSetEvent` at `0x140070a53`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400709ba`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400709ba`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400708de`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400708de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400706d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400706f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400706d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400706f5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400706c4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400706e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400706c4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400706e9`
- `ntoskrnl!IoGetCurrentProcess` at `0x140070828`
- `ntoskrnl!IoGetCurrentProcess` at `0x140070828`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007063d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007065a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007063d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007065a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070624`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070649`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070624`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070649`

## pseudocode

```c
void __fastcall UlpFreeCoupling(char *Entry, unsigned __int8 a2)
{
  __int64 v4; // rdi
  __int64 v5; // rdx
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  volatile signed __int32 *v11; // rdx
  volatile signed __int32 *v12; // rdx
  int v13; // eax
  __int64 v14; // rsi
  int v15; // edi
  bool v16; // zf
  unsigned __int64 v17; // rdi
  int v18; // eax
  ULONG_PTR v19; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v21; // r9
  void *CurrentServerSilo; // rsi
  __int64 v23; // rcx
  __int64 v24; // rdi
  USHORT CurrentNodeNumber; // ax
  char v26; // bp
  __int64 v27; // rax
  __int64 v28; // r14
  ULONG v29; // ebp
  ULONG_PTR v30; // rdx
  int v31; // ecx
  __int64 v32; // rsi
  __int128 v33; // [rsp+30h] [rbp-98h] BYREF
  _DWORD v34[24]; // [rsp+40h] [rbp-88h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, Entry, a2);
  if ( !a2 )
  {
    v4 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)Entry + 8) + 264LL)
                   + 8LL * *(unsigned __int16 *)(*((_QWORD *)Entry + 7) + 56LL));
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(*((_QWORD *)Entry + 7) + 944LL, 0);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v4, 0);
    v5 = *((_QWORD *)Entry + 3);
    v6 = Entry + 24;
    if ( *(char **)(v5 + 8) != Entry + 24 )
      goto LABEL_36;
    v7 = (_QWORD *)*((_QWORD *)Entry + 4);
    if ( (_QWORD *)*v7 != v6
      || (*v7 = v5,
          *(_QWORD *)(v5 + 8) = v7,
          *v6 = 0,
          *((_QWORD *)Entry + 4) = 0,
          v8 = Entry + 40,
          v9 = *((_QWORD *)Entry + 5),
          *(char **)(v9 + 8) != Entry + 40)
      || (v10 = (_QWORD *)*((_QWORD *)Entry + 6), (_QWORD *)*v10 != v8) )
    {
LABEL_36:
      __fastfail(3u);
    }
    *v10 = v9;
    *(_QWORD *)(v9 + 8) = v10;
    *v8 = 0;
    *((_QWORD *)Entry + 6) = 0;
    ExReleasePushLockExclusiveEx(v4, 0);
    KeLeaveCriticalRegion();
    ExReleasePushLockExclusiveEx(*((_QWORD *)Entry + 7) + 944LL, 0);
    KeLeaveCriticalRegion();
  }
  v11 = (volatile signed __int32 *)*((_QWORD *)Entry + 11);
  if ( v11 )
  {
    v18 = _InterlockedDecrement(v11);
    if ( UxDebugCheckRefcount && v18 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v11, 0xEu, v18);
    if ( !v18 )
      UlConsumerCleanupCompletion(*((_QWORD *)Entry + 11));
    *((_QWORD *)Entry + 11) = 0;
  }
  v12 = (volatile signed __int32 *)*((_QWORD *)Entry + 8);
  v13 = _InterlockedDecrement(v12);
  if ( UxDebugCheckRefcount && v13 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v12, 0xEu, v13);
  if ( !v13 )
    UlFreeRequestQueue(*((PVOID *)Entry + 8));
  v14 = *((_QWORD *)Entry + 7);
  *((_QWORD *)Entry + 8) = 0;
  v15 = _InterlockedDecrement((volatile signed __int32 *)(v14 + 40));
  if ( UxDebugCheckRefcount && v15 <= -1 )
    UlBugCheckEx(3u, v14 + 40, 0xEu, v15);
  if ( !v15 )
  {
    v19 = v14 + 64;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(void **)(v14 + 1088);
    v23 = *(_QWORD *)v19;
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v23 || *(_QWORD *)(v19 + 16) || *(_QWORD *)(v19 + 32) )
        UlBugCheckEx(1u, v19, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      LOBYTE(v21) = 1;
      UlThreadPoolEnqueueWorkItem(0, v19, UlFreeHttpConnection, v21, CurrentServerSilo, -1);
      goto LABEL_15;
    }
    if ( v23 || *(_QWORD *)(v19 + 16) || *(_QWORD *)(v19 + 32) )
      UlBugCheckEx(1u, v19, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
    {
      v29 = 0;
      if ( (unsigned int)dword_1401A3F48 > 1 )
      {
        v29 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F60 )
          v29 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v19 + 32) = CurrentServerSilo;
      *(_QWORD *)&v33 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v33);
      v30 = v33 + 24;
      v31 = _InterlockedIncrement((volatile signed __int32 *)(v33 + 24));
      if ( UxDebugCheckRefcount && v31 <= -1 )
        UlBugCheckEx(3u, v30, 0xDu, v31);
      *(_BYTE *)(v19 + 24) = 1;
      v32 = *(_QWORD *)(qword_1401A3F50 + 8LL * v29);
      *(_QWORD *)(v19 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v32 + 16), (PSLIST_ENTRY)v19) )
      {
        KeSetEvent((PRKEVENT)(v32 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v32);
      }
      goto LABEL_15;
    }
    v26 = 0;
    v33 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v28 = *((_QWORD *)&v33 + 1);
    }
    else
    {
      v27 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v28 = v27;
      v26 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v27, CurrentServerSilo);
        UlFreeHttpConnection(v19);
LABEL_44:
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v28);
        PsDetachSiloFromCurrentThread(v28);
        goto LABEL_15;
      }
    }
    UlFreeHttpConnection(v19);
    if ( !v26 )
      goto LABEL_15;
    goto LABEL_44;
  }
LABEL_15:
  v16 = UxDebugDisableLookaside == 0;
  *((_QWORD *)Entry + 7) = 0;
  *((_DWORD *)Entry + 4) = 1969441909;
  if ( v16 )
  {
    if ( UxCompactMode )
    {
      v24 = qword_1401A0910;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v24, Entry, CurrentNodeNumber);
    }
    else
    {
      v17 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*(_DWORD *)Entry + 1) << 7);
      if ( !*(_BYTE *)(v17 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0910, v17 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v17 + 64), Entry);
    }
  }
  else
  {
    memset(v34, 0, sizeof(v34));
    v34[10] = dword_1401A0928;
    ((void (__fastcall *)(char *, _DWORD *))off_1401A0938)(Entry, v34);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
}

```

## disassembly

```asm
0x1400705d0  push    rbx
0x1400705d2  push    rdi
0x1400705d3  push    r15
0x1400705d5  sub     rsp, 0B0h
0x1400705dc  mov     rax, cs:__security_cookie
0x1400705e3  xor     rax, rsp
0x1400705e6  mov     [rsp+0C8h+var_28], rax
0x1400705ee  movzx   edi, dl
0x1400705f1  mov     rbx, rcx
0x1400705f4  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400705fb  jnz     loc_140070ABB
0x140070601  xor     r15d, r15d
0x140070604  test    dil, dil
0x140070607  jnz     loc_140070701
0x14007060d  mov     rax, [rbx+38h]
0x140070611  movzx   edx, word ptr [rax+38h]
0x140070615  mov     rax, [rbx+40h]
0x140070619  mov     rcx, [rax+108h]
0x140070620  mov     rdi, [rcx+rdx*8]
0x140070624  call    cs:__imp_KeEnterCriticalRegion
0x14007062b  nop     dword ptr [rax+rax+00h]
0x140070630  mov     rcx, [rbx+38h]
0x140070634  xor     edx, edx
0x140070636  add     rcx, 3B0h
0x14007063d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140070644  nop     dword ptr [rax+rax+00h]
0x140070649  call    cs:__imp_KeEnterCriticalRegion
0x140070650  nop     dword ptr [rax+rax+00h]
0x140070655  xor     edx, edx
0x140070657  mov     rcx, rdi
0x14007065a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140070661  nop     dword ptr [rax+rax+00h]
0x140070666  mov     rdx, [rbx+18h]
0x14007066a  lea     rax, [rbx+18h]
0x14007066e  cmp     [rdx+8], rax
0x140070672  jnz     loc_1400708B4
0x140070678  mov     rcx, [rax+8]
0x14007067c  cmp     [rcx], rax
0x14007067f  jnz     loc_1400708B4
0x140070685  mov     [rcx], rdx
0x140070688  mov     [rdx+8], rcx
0x14007068c  mov     [rax], r15
0x14007068f  mov     [rax+8], r15
0x140070693  lea     rax, [rbx+28h]
0x140070697  mov     rdx, [rax]
0x14007069a  cmp     [rdx+8], rax
0x14007069e  jnz     loc_1400708B4
0x1400706a4  mov     rcx, [rax+8]
0x1400706a8  cmp     [rcx], rax
0x1400706ab  jnz     loc_1400708B4
0x1400706b1  mov     [rcx], rdx
0x1400706b4  mov     [rdx+8], rcx
0x1400706b8  xor     edx, edx
0x1400706ba  mov     rcx, rdi
0x1400706bd  mov     [rax], r15
0x1400706c0  mov     [rax+8], r15
0x1400706c4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400706cb  nop     dword ptr [rax+rax+00h]
0x1400706d0  call    cs:__imp_KeLeaveCriticalRegion
0x1400706d7  nop     dword ptr [rax+rax+00h]
0x1400706dc  mov     rcx, [rbx+38h]
0x1400706e0  xor     edx, edx
0x1400706e2  add     rcx, 3B0h
0x1400706e9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400706f0  nop     dword ptr [rax+rax+00h]
0x1400706f5  call    cs:__imp_KeLeaveCriticalRegion
0x1400706fc  nop     dword ptr [rax+rax+00h]
0x140070701  mov     rdx, [rbx+58h]; BugCheckParameter2
0x140070705  mov     edi, 0FFFFFFFFh
0x14007070a  test    rdx, rdx
0x14007070d  jnz     loc_1400707FE
0x140070713  mov     rdx, [rbx+40h]; BugCheckParameter2
0x140070717  mov     eax, edi
0x140070719  lock xadd [rdx], eax
0x14007071d  dec     eax
0x14007071f  cmp     cs:UxDebugCheckRefcount, r15b
0x140070726  jnz     loc_14007087B
0x14007072c  mov     [rsp+0C8h+arg_10], rsi
0x140070734  test    eax, eax
0x140070736  jz      loc_140070B65
0x14007073c  mov     rsi, [rbx+38h]
0x140070740  mov     [rbx+40h], r15
0x140070744  lea     rdx, [rsi+28h]; BugCheckParameter2
0x140070748  lock xadd [rdx], edi
0x14007074c  dec     edi
0x14007074e  cmp     cs:UxDebugCheckRefcount, r15b
0x140070755  jnz     loc_140070897
0x14007075b  mov     [rsp+0C8h+arg_8], rbp
0x140070763  test    edi, edi
0x140070765  jz      loc_140070824
0x14007076b  cmp     cs:UxDebugDisableLookaside, r15b
0x140070772  mov     [rbx+38h], r15
0x140070776  mov     dword ptr [rbx+10h], 75634C75h
0x14007077d  jnz     loc_140070BBD
0x140070783  cmp     cs:UxCompactMode, r15b
0x14007078a  jnz     loc_1400708D7
0x140070790  mov     edi, [rbx]
0x140070792  mov     rcx, cs:qword_1401A0910
0x140070799  inc     edi
0x14007079b  shl     rdi, 7
0x14007079f  add     rdi, rcx
0x1400707a2  movzx   eax, byte ptr [rdi+0B0h]
0x1400707a9  test    al, al
0x1400707ab  jz      loc_140070B49
0x1400707b1  mov     rdx, rbx; Entry
0x1400707b4  lea     rcx, [rdi+40h]; Lookaside
0x1400707b8  call    cs:__imp_ExFreeToLookasideListEx
0x1400707bf  nop     dword ptr [rax+rax+00h]
0x1400707c4  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400707cb  jnz     loc_140070ADD
0x1400707d1  mov     rbp, [rsp+0C8h+arg_8]
0x1400707d9  mov     rsi, [rsp+0C8h+arg_10]
0x1400707e1  mov     rcx, [rsp+0C8h+var_28]
0x1400707e9  xor     rcx, rsp; StackCookie
0x1400707ec  call    __security_check_cookie
0x1400707f1  add     rsp, 0B0h
0x1400707f8  pop     r15
0x1400707fa  pop     rdi
0x1400707fb  pop     rbx
0x1400707fc  retn
0x1400707fe  mov     eax, edi
0x140070800  lock xadd [rdx], eax
0x140070804  dec     eax
0x140070806  cmp     cs:UxDebugCheckRefcount, r15b
0x14007080d  jnz     loc_1400708BB
0x140070813  test    eax, eax
0x140070815  jz      loc_140070B57
0x14007081b  mov     [rbx+58h], r15
0x14007081f  jmp     loc_140070713
0x140070824  lea     rdi, [rsi+40h]
0x140070828  call    cs:__imp_IoGetCurrentProcess
0x14007082f  nop     dword ptr [rax+rax+00h]
0x140070834  cmp     cs:UxSystemProcess, rax
0x14007083b  mov     rsi, [rsi+440h]
0x140070842  mov     rcx, [rdi]
0x140070845  jnz     loc_140070A8F
0x14007084b  test    rcx, rcx
0x14007084e  jnz     short loc_140070860
0x140070850  cmp     [rdi+10h], r15
0x140070854  jnz     short loc_140070860
0x140070856  cmp     [rdi+20h], r15
0x14007085a  jz      loc_1400708FE
0x140070860  mov     r9d, 0E1h; BugCheckParameter4
0x140070866  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14007086d  mov     rdx, rdi; BugCheckParameter2
0x140070870  mov     ecx, 1; BugCheckParameter1
0x140070875  call    UlBugCheckEx
0x14007087b  cmp     eax, edi
0x14007087d  jg      loc_14007072C
0x140070883  movsxd  r9, eax; BugCheckParameter4
0x140070886  mov     ecx, 3; BugCheckParameter1
0x14007088b  mov     r8d, 0Eh; BugCheckParameter3
0x140070891  call    UlBugCheckEx
0x140070897  cmp     edi, 0FFFFFFFFh
0x14007089a  jg      loc_14007075B
0x1400708a0  movsxd  r9, edi; BugCheckParameter4
0x1400708a3  mov     ecx, 3; BugCheckParameter1
0x1400708a8  mov     r8d, 0Eh; BugCheckParameter3
0x1400708ae  call    UlBugCheckEx
0x1400708b4  mov     ecx, 3
0x1400708b9  int     29h; Win8: RtlFailFast(ecx)
0x1400708bb  cmp     eax, edi
0x1400708bd  jg      loc_140070813
0x1400708c3  movsxd  r9, eax; BugCheckParameter4
0x1400708c6  mov     ecx, 3; BugCheckParameter1
0x1400708cb  mov     r8d, 0Eh; BugCheckParameter3
0x1400708d1  call    UlBugCheckEx
0x1400708d7  mov     rdi, cs:qword_1401A0910
0x1400708de  call    cs:__imp_KeGetCurrentNodeNumber
0x1400708e5  nop     dword ptr [rax+rax+00h]
0x1400708ea  movzx   r8d, ax
0x1400708ee  mov     rdx, rbx
0x1400708f1  mov     rcx, rdi
0x1400708f4  call    PplFreeToLookasideListProcessor
0x1400708f9  jmp     loc_1400707C4
0x1400708fe  call    cs:__imp_KeGetCurrentIrql
0x140070905  nop     dword ptr [rax+rax+00h]
0x14007090a  test    al, al
0x14007090c  jnz     short loc_140070983
0x14007090e  xor     bpl, bpl
0x140070911  mov     [rsp+0C8h+arg_18], r14
0x140070919  xorps   xmm0, xmm0
0x14007091c  movups  [rsp+0C8h+var_98], xmm0
0x140070921  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140070925  jz      loc_140070A85
0x14007092b  mov     rcx, rsi
0x14007092e  call    cs:__imp_PsAttachSiloToCurrentThread
0x140070935  nop     dword ptr [rax+rax+00h]
0x14007093a  mov     r14, rax
0x14007093d  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140070944  mov     bpl, 1
0x140070947  jnz     loc_140070B1E
0x14007094d  mov     rcx, rdi
0x140070950  call    UlFreeHttpConnection
0x140070955  test    bpl, bpl
0x140070958  jz      short loc_140070976
0x14007095a  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140070961  jnz     loc_140070B73
0x140070967  mov     rcx, r14
0x14007096a  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140070971  nop     dword ptr [rax+rax+00h]
0x140070976  mov     r14, [rsp+0C8h+arg_18]
0x14007097e  jmp     loc_14007076B
0x140070983  cmp     cs:dword_1401A3F48, 1
0x14007098a  mov     ebp, r15d
0x14007098d  jbe     short loc_1400709B4
0x14007098f  xor     ecx, ecx; ProcNumber
0x140070991  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140070998  nop     dword ptr [rax+rax+00h]
0x14007099d  xor     edx, edx
0x14007099f  div     cs:UxNumberOfProcessors
0x1400709a5  cmp     cs:byte_1401A3F60, r15b
0x1400709ac  mov     ebp, edx
0x1400709ae  jnz     loc_140070B91
0x1400709b4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400709b8  jnz     short loc_1400709C9
0x1400709ba  call    cs:__imp_PsGetCurrentServerSilo
0x1400709c1  nop     dword ptr [rax+rax+00h]
0x1400709c6  mov     rsi, rax
0x1400709c9  mov     [rdi+20h], rsi
0x1400709cd  mov     qword ptr [rsp+0C8h+var_98], r15
0x1400709d2  test    rsi, rsi
0x1400709d5  jnz     loc_140070BA4
0x1400709db  mov     edx, cs:UxPodMonitorSlot
0x1400709e1  lea     r8, [rsp+0C8h+var_98]
0x1400709e6  mov     rcx, rsi
0x1400709e9  call    cs:__imp_PsGetPermanentSiloContext
0x1400709f0  nop     dword ptr [rax+rax+00h]
0x1400709f5  mov     rdx, qword ptr [rsp+0C8h+var_98]
0x1400709fa  mov     ecx, 1
0x1400709ff  add     rdx, 18h; BugCheckParameter2
0x140070a03  lock xadd [rdx], ecx
0x140070a07  inc     ecx
0x140070a09  cmp     cs:UxDebugCheckRefcount, r15b
0x140070a10  jnz     short loc_140070A6C
0x140070a12  mov     byte ptr [rdi+18h], 1
0x140070a16  mov     rdx, rdi; ListEntry
0x140070a19  mov     rax, cs:qword_1401A3F50
0x140070a20  mov     ecx, ebp
0x140070a22  mov     rsi, [rax+rcx*8]
0x140070a26  lea     rax, UlFreeHttpConnection
0x140070a2d  mov     [rdi+10h], rax
0x140070a31  lea     rcx, [rsi+10h]; ListHead
0x140070a35  call    cs:__imp_ExpInterlockedPushEntrySList
0x140070a3c  nop     dword ptr [rax+rax+00h]
0x140070a41  test    rax, rax
0x140070a44  jnz     loc_14007076B
0x140070a4a  lea     rcx, [rsi+20h]; Event
0x140070a4e  xor     r8d, r8d; Wait
0x140070a51  xor     edx, edx; Increment
0x140070a53  call    cs:__imp_KeSetEvent
0x140070a5a  nop     dword ptr [rax+rax+00h]
0x140070a5f  mov     rcx, rsi; Context
0x140070a62  call    UlpActivateThreadPoolQueue
0x140070a67  jmp     loc_14007076B
0x140070a6c  cmp     ecx, 0FFFFFFFFh
0x140070a6f  jg      short loc_140070A12
0x140070a71  movsxd  r9, ecx; BugCheckParameter4
0x140070a74  mov     r8d, 0Dh; BugCheckParameter3
0x140070a7a  mov     ecx, 3; BugCheckParameter1
0x140070a7f  call    UlBugCheckEx
0x140070a85  mov     r14, qword ptr [rsp+0C8h+var_98+8]
0x140070a8a  jmp     loc_14007094D
0x140070a8f  test    rcx, rcx
0x140070a92  jnz     short loc_140070AA0
0x140070a94  cmp     [rdi+10h], r15
0x140070a98  jnz     short loc_140070AA0
0x140070a9a  cmp     [rdi+20h], r15
0x140070a9e  jz      short loc_140070AF8
0x140070aa0  mov     r9d, 0DBh; BugCheckParameter4
0x140070aa6  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140070aad  mov     rdx, rdi; BugCheckParameter2
0x140070ab0  mov     ecx, 1; BugCheckParameter1
0x140070ab5  call    UlBugCheckEx
0x140070abb  mov     edx, 17h
0x140070ac0  mov     dword ptr [rsp+0C8h+var_A8], edi
0x140070ac4  mov     ecx, 408h
0x140070ac9  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140070ad0  mov     r9, rbx
0x140070ad3  call    WPP_SF_qD
0x140070ad8  jmp     loc_140070601
0x140070add  mov     edx, 18h
0x140070ae2  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140070ae9  mov     ecx, 408h
0x140070aee  call    WPP_SF_
0x140070af3  jmp     loc_1400707D1
0x140070af8  mov     [rsp+0C8h+var_A0], 0FFFFFFFFh
0x140070b00  lea     r8, UlFreeHttpConnection
0x140070b07  mov     r9b, 1
0x140070b0a  mov     [rsp+0C8h+var_A8], rsi
0x140070b0f  mov     rdx, rdi
0x140070b12  xor     ecx, ecx
0x140070b14  call    UlThreadPoolEnqueueWorkItem
0x140070b19  jmp     loc_14007076B
0x140070b1e  mov     edx, 19h
0x140070b23  mov     [rsp+0C8h+var_A8], rsi
0x140070b28  mov     ecx, 51Ch
0x140070b2d  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140070b34  mov     r9, rax
0x140070b37  call    WPP_SF_qq
  ... truncated ...
```

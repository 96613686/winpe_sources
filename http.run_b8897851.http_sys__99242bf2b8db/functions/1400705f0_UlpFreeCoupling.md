# UlpFreeCoupling

- ea: `0x1400705f0`
- end: `0x140070c12`
- name: `UlpFreeCoupling`
- size: `1570`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `15`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a520`
- `0x14003ded0`
- `0x140056f90`
- `0x14005e0f0`
- `0x14005f3c0`
- `0x14006ce40`
- `0x14006eb10`
- `0x14006f220`
- `0x140071254`
- `0x140071790`
- `0x140071f80`
- `0x1400cbd30`
- `0x1400cca5c`
- `0x1400ce450`
- `0x1400cf080`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140049d28`
- `0x14005dff0`
- `0x14005e050`
- `0x1400705f0`
- `0x14009622c`
- `0x1400a033c`
- `0x14013dc78`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14007091e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14007091e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140070a55`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140070a55`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400707d8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400707d8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400709b1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400709b1`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140070a09`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140070a09`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140070bcc`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140070bcc`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14007094e`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14007094e`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14007098a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14007098a`
- `ntoskrnl!KeSetEvent` at `0x140070a73`
- `ntoskrnl!KeSetEvent` at `0x140070a73`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400709da`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400709da`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400708fe`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400708fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400706f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070715`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400706f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070715`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400706e4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140070709`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400706e4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140070709`
- `ntoskrnl!IoGetCurrentProcess` at `0x140070848`
- `ntoskrnl!IoGetCurrentProcess` at `0x140070848`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007065d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007067a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007065d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007067a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070644`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070669`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070644`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070669`

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
0x1400705f0  push    rbx
0x1400705f2  push    rdi
0x1400705f3  push    r15
0x1400705f5  sub     rsp, 0B0h
0x1400705fc  mov     rax, cs:__security_cookie
0x140070603  xor     rax, rsp
0x140070606  mov     [rsp+0C8h+var_28], rax
0x14007060e  movzx   edi, dl
0x140070611  mov     rbx, rcx
0x140070614  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14007061b  jnz     loc_140070ADB
0x140070621  xor     r15d, r15d
0x140070624  test    dil, dil
0x140070627  jnz     loc_140070721
0x14007062d  mov     rax, [rbx+38h]
0x140070631  movzx   edx, word ptr [rax+38h]
0x140070635  mov     rax, [rbx+40h]
0x140070639  mov     rcx, [rax+108h]
0x140070640  mov     rdi, [rcx+rdx*8]
0x140070644  call    cs:__imp_KeEnterCriticalRegion
0x14007064b  nop     dword ptr [rax+rax+00h]
0x140070650  mov     rcx, [rbx+38h]
0x140070654  xor     edx, edx
0x140070656  add     rcx, 3B0h
0x14007065d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140070664  nop     dword ptr [rax+rax+00h]
0x140070669  call    cs:__imp_KeEnterCriticalRegion
0x140070670  nop     dword ptr [rax+rax+00h]
0x140070675  xor     edx, edx
0x140070677  mov     rcx, rdi
0x14007067a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140070681  nop     dword ptr [rax+rax+00h]
0x140070686  mov     rdx, [rbx+18h]
0x14007068a  lea     rax, [rbx+18h]
0x14007068e  cmp     [rdx+8], rax
0x140070692  jnz     loc_1400708D4
0x140070698  mov     rcx, [rax+8]
0x14007069c  cmp     [rcx], rax
0x14007069f  jnz     loc_1400708D4
0x1400706a5  mov     [rcx], rdx
0x1400706a8  mov     [rdx+8], rcx
0x1400706ac  mov     [rax], r15
0x1400706af  mov     [rax+8], r15
0x1400706b3  lea     rax, [rbx+28h]
0x1400706b7  mov     rdx, [rax]
0x1400706ba  cmp     [rdx+8], rax
0x1400706be  jnz     loc_1400708D4
0x1400706c4  mov     rcx, [rax+8]
0x1400706c8  cmp     [rcx], rax
0x1400706cb  jnz     loc_1400708D4
0x1400706d1  mov     [rcx], rdx
0x1400706d4  mov     [rdx+8], rcx
0x1400706d8  xor     edx, edx
0x1400706da  mov     rcx, rdi
0x1400706dd  mov     [rax], r15
0x1400706e0  mov     [rax+8], r15
0x1400706e4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400706eb  nop     dword ptr [rax+rax+00h]
0x1400706f0  call    cs:__imp_KeLeaveCriticalRegion
0x1400706f7  nop     dword ptr [rax+rax+00h]
0x1400706fc  mov     rcx, [rbx+38h]
0x140070700  xor     edx, edx
0x140070702  add     rcx, 3B0h
0x140070709  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140070710  nop     dword ptr [rax+rax+00h]
0x140070715  call    cs:__imp_KeLeaveCriticalRegion
0x14007071c  nop     dword ptr [rax+rax+00h]
0x140070721  mov     rdx, [rbx+58h]; BugCheckParameter2
0x140070725  mov     edi, 0FFFFFFFFh
0x14007072a  test    rdx, rdx
0x14007072d  jnz     loc_14007081E
0x140070733  mov     rdx, [rbx+40h]; BugCheckParameter2
0x140070737  mov     eax, edi
0x140070739  lock xadd [rdx], eax
0x14007073d  dec     eax
0x14007073f  cmp     cs:UxDebugCheckRefcount, r15b
0x140070746  jnz     loc_14007089B
0x14007074c  mov     [rsp+0C8h+arg_10], rsi
0x140070754  test    eax, eax
0x140070756  jz      loc_140070B85
0x14007075c  mov     rsi, [rbx+38h]
0x140070760  mov     [rbx+40h], r15
0x140070764  lea     rdx, [rsi+28h]; BugCheckParameter2
0x140070768  lock xadd [rdx], edi
0x14007076c  dec     edi
0x14007076e  cmp     cs:UxDebugCheckRefcount, r15b
0x140070775  jnz     loc_1400708B7
0x14007077b  mov     [rsp+0C8h+arg_8], rbp
0x140070783  test    edi, edi
0x140070785  jz      loc_140070844
0x14007078b  cmp     cs:UxDebugDisableLookaside, r15b
0x140070792  mov     [rbx+38h], r15
0x140070796  mov     dword ptr [rbx+10h], 75634C75h
0x14007079d  jnz     loc_140070BDD
0x1400707a3  cmp     cs:UxCompactMode, r15b
0x1400707aa  jnz     loc_1400708F7
0x1400707b0  mov     edi, [rbx]
0x1400707b2  mov     rcx, cs:qword_1401A0910
0x1400707b9  inc     edi
0x1400707bb  shl     rdi, 7
0x1400707bf  add     rdi, rcx
0x1400707c2  movzx   eax, byte ptr [rdi+0B0h]
0x1400707c9  test    al, al
0x1400707cb  jz      loc_140070B69
0x1400707d1  mov     rdx, rbx; Entry
0x1400707d4  lea     rcx, [rdi+40h]; Lookaside
0x1400707d8  call    cs:__imp_ExFreeToLookasideListEx
0x1400707df  nop     dword ptr [rax+rax+00h]
0x1400707e4  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400707eb  jnz     loc_140070AFD
0x1400707f1  mov     rbp, [rsp+0C8h+arg_8]
0x1400707f9  mov     rsi, [rsp+0C8h+arg_10]
0x140070801  mov     rcx, [rsp+0C8h+var_28]
0x140070809  xor     rcx, rsp; StackCookie
0x14007080c  call    __security_check_cookie
0x140070811  add     rsp, 0B0h
0x140070818  pop     r15
0x14007081a  pop     rdi
0x14007081b  pop     rbx
0x14007081c  retn
0x14007081e  mov     eax, edi
0x140070820  lock xadd [rdx], eax
0x140070824  dec     eax
0x140070826  cmp     cs:UxDebugCheckRefcount, r15b
0x14007082d  jnz     loc_1400708DB
0x140070833  test    eax, eax
0x140070835  jz      loc_140070B77
0x14007083b  mov     [rbx+58h], r15
0x14007083f  jmp     loc_140070733
0x140070844  lea     rdi, [rsi+40h]
0x140070848  call    cs:__imp_IoGetCurrentProcess
0x14007084f  nop     dword ptr [rax+rax+00h]
0x140070854  cmp     cs:UxSystemProcess, rax
0x14007085b  mov     rsi, [rsi+440h]
0x140070862  mov     rcx, [rdi]
0x140070865  jnz     loc_140070AAF
0x14007086b  test    rcx, rcx
0x14007086e  jnz     short loc_140070880
0x140070870  cmp     [rdi+10h], r15
0x140070874  jnz     short loc_140070880
0x140070876  cmp     [rdi+20h], r15
0x14007087a  jz      loc_14007091E
0x140070880  mov     r9d, 0E1h; BugCheckParameter4
0x140070886  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14007088d  mov     rdx, rdi; BugCheckParameter2
0x140070890  mov     ecx, 1; BugCheckParameter1
0x140070895  call    UlBugCheckEx
0x14007089b  cmp     eax, edi
0x14007089d  jg      loc_14007074C
0x1400708a3  movsxd  r9, eax; BugCheckParameter4
0x1400708a6  mov     ecx, 3; BugCheckParameter1
0x1400708ab  mov     r8d, 0Eh; BugCheckParameter3
0x1400708b1  call    UlBugCheckEx
0x1400708b7  cmp     edi, 0FFFFFFFFh
0x1400708ba  jg      loc_14007077B
0x1400708c0  movsxd  r9, edi; BugCheckParameter4
0x1400708c3  mov     ecx, 3; BugCheckParameter1
0x1400708c8  mov     r8d, 0Eh; BugCheckParameter3
0x1400708ce  call    UlBugCheckEx
0x1400708d4  mov     ecx, 3
0x1400708d9  int     29h; Win8: RtlFailFast(ecx)
0x1400708db  cmp     eax, edi
0x1400708dd  jg      loc_140070833
0x1400708e3  movsxd  r9, eax; BugCheckParameter4
0x1400708e6  mov     ecx, 3; BugCheckParameter1
0x1400708eb  mov     r8d, 0Eh; BugCheckParameter3
0x1400708f1  call    UlBugCheckEx
0x1400708f7  mov     rdi, cs:qword_1401A0910
0x1400708fe  call    cs:__imp_KeGetCurrentNodeNumber
0x140070905  nop     dword ptr [rax+rax+00h]
0x14007090a  movzx   r8d, ax
0x14007090e  mov     rdx, rbx
0x140070911  mov     rcx, rdi
0x140070914  call    PplFreeToLookasideListProcessor
0x140070919  jmp     loc_1400707E4
0x14007091e  call    cs:__imp_KeGetCurrentIrql
0x140070925  nop     dword ptr [rax+rax+00h]
0x14007092a  test    al, al
0x14007092c  jnz     short loc_1400709A3
0x14007092e  xor     bpl, bpl
0x140070931  mov     [rsp+0C8h+arg_18], r14
0x140070939  xorps   xmm0, xmm0
0x14007093c  movups  [rsp+0C8h+var_98], xmm0
0x140070941  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140070945  jz      loc_140070AA5
0x14007094b  mov     rcx, rsi
0x14007094e  call    cs:__imp_PsAttachSiloToCurrentThread
0x140070955  nop     dword ptr [rax+rax+00h]
0x14007095a  mov     r14, rax
0x14007095d  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140070964  mov     bpl, 1
0x140070967  jnz     loc_140070B3E
0x14007096d  mov     rcx, rdi
0x140070970  call    UlFreeHttpConnection
0x140070975  test    bpl, bpl
0x140070978  jz      short loc_140070996
0x14007097a  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140070981  jnz     loc_140070B93
0x140070987  mov     rcx, r14
0x14007098a  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140070991  nop     dword ptr [rax+rax+00h]
0x140070996  mov     r14, [rsp+0C8h+arg_18]
0x14007099e  jmp     loc_14007078B
0x1400709a3  cmp     cs:dword_1401A3F48, 1
0x1400709aa  mov     ebp, r15d
0x1400709ad  jbe     short loc_1400709D4
0x1400709af  xor     ecx, ecx; ProcNumber
0x1400709b1  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400709b8  nop     dword ptr [rax+rax+00h]
0x1400709bd  xor     edx, edx
0x1400709bf  div     cs:UxNumberOfProcessors
0x1400709c5  cmp     cs:byte_1401A3F60, r15b
0x1400709cc  mov     ebp, edx
0x1400709ce  jnz     loc_140070BB1
0x1400709d4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400709d8  jnz     short loc_1400709E9
0x1400709da  call    cs:__imp_PsGetCurrentServerSilo
0x1400709e1  nop     dword ptr [rax+rax+00h]
0x1400709e6  mov     rsi, rax
0x1400709e9  mov     [rdi+20h], rsi
0x1400709ed  mov     qword ptr [rsp+0C8h+var_98], r15
0x1400709f2  test    rsi, rsi
0x1400709f5  jnz     loc_140070BC4
0x1400709fb  mov     edx, cs:UxPodMonitorSlot
0x140070a01  lea     r8, [rsp+0C8h+var_98]
0x140070a06  mov     rcx, rsi
0x140070a09  call    cs:__imp_PsGetPermanentSiloContext
0x140070a10  nop     dword ptr [rax+rax+00h]
0x140070a15  mov     rdx, qword ptr [rsp+0C8h+var_98]
0x140070a1a  mov     ecx, 1
0x140070a1f  add     rdx, 18h; BugCheckParameter2
0x140070a23  lock xadd [rdx], ecx
0x140070a27  inc     ecx
0x140070a29  cmp     cs:UxDebugCheckRefcount, r15b
0x140070a30  jnz     short loc_140070A8C
0x140070a32  mov     byte ptr [rdi+18h], 1
0x140070a36  mov     rdx, rdi; ListEntry
0x140070a39  mov     rax, cs:qword_1401A3F50
0x140070a40  mov     ecx, ebp
0x140070a42  mov     rsi, [rax+rcx*8]
0x140070a46  lea     rax, UlFreeHttpConnection
0x140070a4d  mov     [rdi+10h], rax
0x140070a51  lea     rcx, [rsi+10h]; ListHead
0x140070a55  call    cs:__imp_ExpInterlockedPushEntrySList
0x140070a5c  nop     dword ptr [rax+rax+00h]
0x140070a61  test    rax, rax
0x140070a64  jnz     loc_14007078B
0x140070a6a  lea     rcx, [rsi+20h]; Event
0x140070a6e  xor     r8d, r8d; Wait
0x140070a71  xor     edx, edx; Increment
0x140070a73  call    cs:__imp_KeSetEvent
0x140070a7a  nop     dword ptr [rax+rax+00h]
0x140070a7f  mov     rcx, rsi; Context
0x140070a82  call    UlpActivateThreadPoolQueue
0x140070a87  jmp     loc_14007078B
0x140070a8c  cmp     ecx, 0FFFFFFFFh
0x140070a8f  jg      short loc_140070A32
0x140070a91  movsxd  r9, ecx; BugCheckParameter4
0x140070a94  mov     r8d, 0Dh; BugCheckParameter3
0x140070a9a  mov     ecx, 3; BugCheckParameter1
0x140070a9f  call    UlBugCheckEx
0x140070aa5  mov     r14, qword ptr [rsp+0C8h+var_98+8]
0x140070aaa  jmp     loc_14007096D
0x140070aaf  test    rcx, rcx
0x140070ab2  jnz     short loc_140070AC0
0x140070ab4  cmp     [rdi+10h], r15
0x140070ab8  jnz     short loc_140070AC0
0x140070aba  cmp     [rdi+20h], r15
0x140070abe  jz      short loc_140070B18
0x140070ac0  mov     r9d, 0DBh; BugCheckParameter4
0x140070ac6  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140070acd  mov     rdx, rdi; BugCheckParameter2
0x140070ad0  mov     ecx, 1; BugCheckParameter1
0x140070ad5  call    UlBugCheckEx
0x140070adb  mov     edx, 17h
0x140070ae0  mov     dword ptr [rsp+0C8h+var_A8], edi
0x140070ae4  mov     ecx, 408h
0x140070ae9  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140070af0  mov     r9, rbx
0x140070af3  call    WPP_SF_qD
0x140070af8  jmp     loc_140070621
0x140070afd  mov     edx, 18h
0x140070b02  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140070b09  mov     ecx, 408h
0x140070b0e  call    WPP_SF_
0x140070b13  jmp     loc_1400707F1
0x140070b18  mov     [rsp+0C8h+var_A0], 0FFFFFFFFh
0x140070b20  lea     r8, UlFreeHttpConnection
0x140070b27  mov     r9b, 1
0x140070b2a  mov     [rsp+0C8h+var_A8], rsi
0x140070b2f  mov     rdx, rdi
0x140070b32  xor     ecx, ecx
0x140070b34  call    UlThreadPoolEnqueueWorkItem
0x140070b39  jmp     loc_14007078B
0x140070b3e  mov     edx, 19h
0x140070b43  mov     [rsp+0C8h+var_A8], rsi
0x140070b48  mov     ecx, 51Ch
0x140070b4d  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140070b54  mov     r9, rax
0x140070b57  call    WPP_SF_qq
  ... truncated ...
```

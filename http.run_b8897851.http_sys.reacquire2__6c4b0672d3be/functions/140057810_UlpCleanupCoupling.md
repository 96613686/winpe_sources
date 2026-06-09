# UlpCleanupCoupling

- ea: `0x140057810`
- end: `0x140057f59`
- name: `UlpCleanupCoupling`
- size: `1865`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140056f90`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140049d28`
- `0x140057810`
- `0x14005dff0`
- `0x14005e050`
- `0x14009622c`
- `0x1400a033c`
- `0x14013dc78`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9c5c`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140057c1a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140057c1a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140057d51`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140057d51`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140057a79`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140057a79`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140057cad`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140057cad`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140057d05`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140057d05`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140057f13`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140057f13`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140057c4a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140057c4a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140057c86`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140057c86`
- `ntoskrnl!KeSetEvent` at `0x140057d6f`
- `ntoskrnl!KeSetEvent` at `0x140057d6f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140057cd6`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140057cd6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140057bfa`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140057bfa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057894`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400579a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400579cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057ad1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057894`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400579a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400579cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057ad1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140057888`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005799a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400579bf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140057ac5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140057888`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005799a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400579bf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140057ac5`
- `ntoskrnl!IoGetCurrentProcess` at `0x140057b28`
- `ntoskrnl!IoGetCurrentProcess` at `0x140057b28`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057869`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057913`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057930`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057869`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057913`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057930`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140057857`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400578fa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005791f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140057857`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400578fa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005791f`

## pseudocode

```c
void __fastcall UlpCleanupCoupling(char *Entry, __int64 a2, __int64 a3)
{
  char *v4; // rcx
  int v5; // eax
  __int64 v6; // rsi
  __int64 v7; // rdx
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // r8
  _QWORD *v12; // rdx
  volatile signed __int32 *v13; // rdx
  volatile signed __int32 *v14; // rdx
  int v15; // eax
  __int64 v16; // rsi
  int v17; // edi
  bool v18; // zf
  unsigned __int64 v19; // rdi
  int v20; // eax
  ULONG_PTR v21; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v23; // r9
  void *CurrentServerSilo; // rsi
  __int64 v25; // rcx
  __int64 v26; // rdi
  USHORT CurrentNodeNumber; // ax
  char v28; // bp
  __int64 v29; // rax
  __int64 v30; // r14
  ULONG v31; // ebp
  ULONG_PTR v32; // rdx
  int v33; // ecx
  __int64 v34; // rsi
  __int128 v35; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD v36[24]; // [rsp+40h] [rbp-98h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qqP(1032, 29, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, Entry, a2, a3);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(Entry + 72, 0);
  v4 = Entry + 72;
  if ( Entry[80] )
  {
    ExReleasePushLockExclusiveEx(v4, 0);
    KeLeaveCriticalRegion();
    goto LABEL_28;
  }
  Entry[80] = 1;
  ExReleasePushLockExclusiveEx(v4, 0);
  KeLeaveCriticalRegion();
  if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_q(1046, 30, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, Entry);
  v5 = _InterlockedDecrement((volatile signed __int32 *)Entry + 5);
  if ( UxDebugCheckRefcount && v5 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(Entry + 20), 1u, v5);
  if ( v5 )
    goto LABEL_28;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, Entry, 0);
  v6 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)Entry + 8) + 264LL)
                 + 8LL * *(unsigned __int16 *)(*((_QWORD *)Entry + 7) + 56LL));
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*((_QWORD *)Entry + 7) + 944LL, 0);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v6, 0);
  v7 = *((_QWORD *)Entry + 3);
  v8 = Entry + 24;
  if ( *(char **)(v7 + 8) != Entry + 24 )
    goto LABEL_45;
  v9 = (_QWORD *)*((_QWORD *)Entry + 4);
  if ( (_QWORD *)*v9 != v8
    || (*v9 = v7,
        *(_QWORD *)(v7 + 8) = v9,
        *v8 = 0,
        *((_QWORD *)Entry + 4) = 0,
        v10 = Entry + 40,
        v11 = *((_QWORD *)Entry + 5),
        *(char **)(v11 + 8) != Entry + 40)
    || (v12 = (_QWORD *)*((_QWORD *)Entry + 6), (_QWORD *)*v12 != v10) )
  {
LABEL_45:
    __fastfail(3u);
  }
  *v12 = v11;
  *(_QWORD *)(v11 + 8) = v12;
  *v10 = 0;
  *((_QWORD *)Entry + 6) = 0;
  ExReleasePushLockExclusiveEx(v6, 0);
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*((_QWORD *)Entry + 7) + 944LL, 0);
  KeLeaveCriticalRegion();
  v13 = (volatile signed __int32 *)*((_QWORD *)Entry + 11);
  if ( v13 )
  {
    v20 = _InterlockedDecrement(v13);
    if ( UxDebugCheckRefcount && v20 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v13, 0xEu, v20);
    if ( !v20 )
      UlConsumerCleanupCompletion(*((_QWORD *)Entry + 11));
    *((_QWORD *)Entry + 11) = 0;
  }
  v14 = (volatile signed __int32 *)*((_QWORD *)Entry + 8);
  v15 = _InterlockedDecrement(v14);
  if ( UxDebugCheckRefcount && v15 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v14, 0xEu, v15);
  if ( !v15 )
    UlFreeRequestQueue(*((PVOID *)Entry + 8));
  v16 = *((_QWORD *)Entry + 7);
  *((_QWORD *)Entry + 8) = 0;
  v17 = _InterlockedDecrement((volatile signed __int32 *)(v16 + 40));
  if ( UxDebugCheckRefcount && v17 <= -1 )
    UlBugCheckEx(3u, v16 + 40, 0xEu, v17);
  if ( !v17 )
  {
    v21 = v16 + 64;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(void **)(v16 + 1088);
    v25 = *(_QWORD *)v21;
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v25 || *(_QWORD *)(v21 + 16) || *(_QWORD *)(v21 + 32) )
        UlBugCheckEx(1u, v21, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      LOBYTE(v23) = 1;
      UlThreadPoolEnqueueWorkItem(0, v21, UlFreeHttpConnection, v23, CurrentServerSilo, -1);
      goto LABEL_20;
    }
    if ( v25 || *(_QWORD *)(v21 + 16) || *(_QWORD *)(v21 + 32) )
      UlBugCheckEx(1u, v21, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
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
      *(_QWORD *)(v21 + 32) = CurrentServerSilo;
      *(_QWORD *)&v35 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v35);
      v32 = v35 + 24;
      v33 = _InterlockedIncrement((volatile signed __int32 *)(v35 + 24));
      if ( UxDebugCheckRefcount && v33 <= -1 )
        UlBugCheckEx(3u, v32, 0xDu, v33);
      *(_BYTE *)(v21 + 24) = 1;
      v34 = *(_QWORD *)(qword_1401A3F50 + 8LL * v31);
      *(_QWORD *)(v21 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v34 + 16), (PSLIST_ENTRY)v21) )
      {
        KeSetEvent((PRKEVENT)(v34 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v34);
      }
      goto LABEL_20;
    }
    v28 = 0;
    v35 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v30 = *((_QWORD *)&v35 + 1);
    }
    else
    {
      v29 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v30 = v29;
      v28 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v29, CurrentServerSilo);
        UlFreeHttpConnection(v21);
LABEL_53:
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v30);
        PsDetachSiloFromCurrentThread(v30);
        goto LABEL_20;
      }
    }
    UlFreeHttpConnection(v21);
    if ( !v28 )
      goto LABEL_20;
    goto LABEL_53;
  }
LABEL_20:
  v18 = UxDebugDisableLookaside == 0;
  *((_QWORD *)Entry + 7) = 0;
  *((_DWORD *)Entry + 4) = 1969441909;
  if ( v18 )
  {
    if ( UxCompactMode )
    {
      v26 = qword_1401A0910;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v26, Entry, CurrentNodeNumber);
    }
    else
    {
      v19 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*(_DWORD *)Entry + 1) << 7);
      if ( !*(_BYTE *)(v19 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0910, v19 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v19 + 64), Entry);
    }
  }
  else
  {
    memset(v36, 0, sizeof(v36));
    v36[10] = dword_1401A0928;
    ((void (__fastcall *)(char *, _DWORD *))off_1401A0938)(Entry, v36);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
LABEL_28:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 31, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  }
}

```

## disassembly

```asm
0x140057810  push    rbx
0x140057812  push    rdi
0x140057813  sub     rsp, 0C8h
0x14005781a  mov     rax, cs:__security_cookie
0x140057821  xor     rax, rsp
0x140057824  mov     [rsp+0D8h+var_38], rax
0x14005782c  mov     r9, rdx
0x14005782f  mov     rbx, rcx
0x140057832  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140057839  jnz     loc_140057E19
0x14005783f  mov     [rsp+0D8h+arg_18], rbp
0x140057847  mov     [rsp+0D8h+var_18], rsi
0x14005784f  mov     [rsp+0D8h+var_28], r15
0x140057857  call    cs:__imp_KeEnterCriticalRegion
0x14005785e  nop     dword ptr [rax+rax+00h]
0x140057863  xor     edx, edx
0x140057865  lea     rcx, [rbx+48h]
0x140057869  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140057870  nop     dword ptr [rax+rax+00h]
0x140057875  xor     edx, edx
0x140057877  lea     rcx, [rbx+48h]
0x14005787b  cmp     [rbx+50h], dl
0x14005787e  jnz     loc_140057AC5
0x140057884  mov     byte ptr [rbx+50h], 1
0x140057888  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005788f  nop     dword ptr [rax+rax+00h]
0x140057894  call    cs:__imp_KeLeaveCriticalRegion
0x14005789b  nop     dword ptr [rax+rax+00h]
0x1400578a0  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x1400578a7  jnz     loc_140057EA0
0x1400578ad  mov     edi, 0FFFFFFFFh
0x1400578b2  lea     rdx, [rbx+14h]; BugCheckParameter2
0x1400578b6  mov     eax, edi
0x1400578b8  lock xadd [rdx], eax
0x1400578bc  dec     eax
0x1400578be  cmp     cs:UxDebugCheckRefcount, 0
0x1400578c5  jnz     loc_140057B7B
0x1400578cb  test    eax, eax
0x1400578cd  jnz     loc_140057ADD
0x1400578d3  xor     r15d, r15d
0x1400578d6  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400578dd  jnz     loc_140057DDB
0x1400578e3  mov     rax, [rbx+38h]
0x1400578e7  movzx   edx, word ptr [rax+38h]
0x1400578eb  mov     rax, [rbx+40h]
0x1400578ef  mov     rcx, [rax+108h]
0x1400578f6  mov     rsi, [rcx+rdx*8]
0x1400578fa  call    cs:__imp_KeEnterCriticalRegion
0x140057901  nop     dword ptr [rax+rax+00h]
0x140057906  mov     rcx, [rbx+38h]
0x14005790a  xor     edx, edx
0x14005790c  add     rcx, 3B0h
0x140057913  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005791a  nop     dword ptr [rax+rax+00h]
0x14005791f  call    cs:__imp_KeEnterCriticalRegion
0x140057926  nop     dword ptr [rax+rax+00h]
0x14005792b  xor     edx, edx
0x14005792d  mov     rcx, rsi
0x140057930  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140057937  nop     dword ptr [rax+rax+00h]
0x14005793c  mov     rdx, [rbx+18h]
0x140057940  lea     rax, [rbx+18h]
0x140057944  cmp     [rdx+8], rax
0x140057948  jnz     loc_140057BD0
0x14005794e  mov     rcx, [rax+8]
0x140057952  cmp     [rcx], rax
0x140057955  jnz     loc_140057BD0
0x14005795b  mov     [rcx], rdx
0x14005795e  mov     [rdx+8], rcx
0x140057962  mov     [rax], r15
0x140057965  mov     [rax+8], r15
0x140057969  lea     rax, [rbx+28h]
0x14005796d  mov     r8, [rax]
0x140057970  cmp     [r8+8], rax
0x140057974  jnz     loc_140057BD0
0x14005797a  mov     rdx, [rax+8]
0x14005797e  cmp     [rdx], rax
0x140057981  jnz     loc_140057BD0
0x140057987  mov     [rdx], r8
0x14005798a  mov     rcx, rsi
0x14005798d  mov     [r8+8], rdx
0x140057991  xor     edx, edx
0x140057993  mov     [rax], r15
0x140057996  mov     [rax+8], r15
0x14005799a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400579a1  nop     dword ptr [rax+rax+00h]
0x1400579a6  call    cs:__imp_KeLeaveCriticalRegion
0x1400579ad  nop     dword ptr [rax+rax+00h]
0x1400579b2  mov     rcx, [rbx+38h]
0x1400579b6  xor     edx, edx
0x1400579b8  add     rcx, 3B0h
0x1400579bf  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400579c6  nop     dword ptr [rax+rax+00h]
0x1400579cb  call    cs:__imp_KeLeaveCriticalRegion
0x1400579d2  nop     dword ptr [rax+rax+00h]
0x1400579d7  mov     rdx, [rbx+58h]; BugCheckParameter2
0x1400579db  test    rdx, rdx
0x1400579de  jnz     loc_140057AFE
0x1400579e4  mov     rdx, [rbx+40h]; BugCheckParameter2
0x1400579e8  mov     eax, edi
0x1400579ea  lock xadd [rdx], eax
0x1400579ee  dec     eax
0x1400579f0  cmp     cs:UxDebugCheckRefcount, r15b
0x1400579f7  jnz     loc_140057B97
0x1400579fd  test    eax, eax
0x1400579ff  jz      loc_140057ECC
0x140057a05  mov     rsi, [rbx+38h]
0x140057a09  mov     [rbx+40h], r15
0x140057a0d  lea     rdx, [rsi+28h]; BugCheckParameter2
0x140057a11  lock xadd [rdx], edi
0x140057a15  dec     edi
0x140057a17  cmp     cs:UxDebugCheckRefcount, r15b
0x140057a1e  jnz     loc_140057BB3
0x140057a24  test    edi, edi
0x140057a26  jz      loc_140057B24
0x140057a2c  cmp     cs:UxDebugDisableLookaside, r15b
0x140057a33  mov     [rbx+38h], r15
0x140057a37  mov     dword ptr [rbx+10h], 75634C75h
0x140057a3e  jnz     loc_140057F24
0x140057a44  cmp     cs:UxCompactMode, r15b
0x140057a4b  jnz     loc_140057BF3
0x140057a51  mov     edi, [rbx]
0x140057a53  mov     rcx, cs:qword_1401A0910
0x140057a5a  inc     edi
0x140057a5c  shl     rdi, 7
0x140057a60  add     rdi, rcx
0x140057a63  movzx   eax, byte ptr [rdi+0B0h]
0x140057a6a  test    al, al
0x140057a6c  jz      loc_140057E92
0x140057a72  mov     rdx, rbx; Entry
0x140057a75  lea     rcx, [rdi+40h]; Lookaside
0x140057a79  call    cs:__imp_ExFreeToLookasideListEx
0x140057a80  nop     dword ptr [rax+rax+00h]
0x140057a85  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140057a8c  jnz     loc_140057DFE
0x140057a92  mov     r15, [rsp+0D8h+var_28]
0x140057a9a  mov     rsi, [rsp+0D8h+var_18]
0x140057aa2  mov     rbp, [rsp+0D8h+arg_18]
0x140057aaa  mov     rcx, [rsp+0D8h+var_38]
0x140057ab2  xor     rcx, rsp; StackCookie
0x140057ab5  call    __security_check_cookie
0x140057aba  add     rsp, 0C8h
0x140057ac1  pop     rdi
0x140057ac2  pop     rbx
0x140057ac3  retn
0x140057ac5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140057acc  nop     dword ptr [rax+rax+00h]
0x140057ad1  call    cs:__imp_KeLeaveCriticalRegion
0x140057ad8  nop     dword ptr [rax+rax+00h]
0x140057add  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140057ae4  jz      short loc_140057A92
0x140057ae6  mov     edx, 1Fh
0x140057aeb  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140057af2  mov     ecx, 408h
0x140057af7  call    WPP_SF_
0x140057afc  jmp     short loc_140057A92
0x140057afe  mov     eax, edi
0x140057b00  lock xadd [rdx], eax
0x140057b04  dec     eax
0x140057b06  cmp     cs:UxDebugCheckRefcount, r15b
0x140057b0d  jnz     loc_140057BD7
0x140057b13  test    eax, eax
0x140057b15  jz      loc_140057EBE
0x140057b1b  mov     [rbx+58h], r15
0x140057b1f  jmp     loc_1400579E4
0x140057b24  lea     rdi, [rsi+40h]
0x140057b28  call    cs:__imp_IoGetCurrentProcess
0x140057b2f  nop     dword ptr [rax+rax+00h]
0x140057b34  cmp     cs:UxSystemProcess, rax
0x140057b3b  mov     rsi, [rsi+440h]
0x140057b42  mov     rcx, [rdi]
0x140057b45  jnz     loc_140057DAB
0x140057b4b  test    rcx, rcx
0x140057b4e  jnz     short loc_140057B60
0x140057b50  cmp     [rdi+10h], r15
0x140057b54  jnz     short loc_140057B60
0x140057b56  cmp     [rdi+20h], r15
0x140057b5a  jz      loc_140057C1A
0x140057b60  mov     r9d, 0E1h; BugCheckParameter4
0x140057b66  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140057b6d  mov     rdx, rdi; BugCheckParameter2
0x140057b70  mov     ecx, 1; BugCheckParameter1
0x140057b75  call    UlBugCheckEx
0x140057b7b  cmp     eax, edi
0x140057b7d  jg      loc_1400578CB
0x140057b83  movsxd  r9, eax; BugCheckParameter4
0x140057b86  mov     ecx, 3; BugCheckParameter1
0x140057b8b  mov     r8d, 1; BugCheckParameter3
0x140057b91  call    UlBugCheckEx
0x140057b97  cmp     eax, edi
0x140057b99  jg      loc_1400579FD
0x140057b9f  movsxd  r9, eax; BugCheckParameter4
0x140057ba2  mov     ecx, 3; BugCheckParameter1
0x140057ba7  mov     r8d, 0Eh; BugCheckParameter3
0x140057bad  call    UlBugCheckEx
0x140057bb3  cmp     edi, 0FFFFFFFFh
0x140057bb6  jg      loc_140057A24
0x140057bbc  movsxd  r9, edi; BugCheckParameter4
0x140057bbf  mov     ecx, 3; BugCheckParameter1
0x140057bc4  mov     r8d, 0Eh; BugCheckParameter3
0x140057bca  call    UlBugCheckEx
0x140057bd0  mov     ecx, 3
0x140057bd5  int     29h; Win8: RtlFailFast(ecx)
0x140057bd7  cmp     eax, edi
0x140057bd9  jg      loc_140057B13
0x140057bdf  movsxd  r9, eax; BugCheckParameter4
0x140057be2  mov     ecx, 3; BugCheckParameter1
0x140057be7  mov     r8d, 0Eh; BugCheckParameter3
0x140057bed  call    UlBugCheckEx
0x140057bf3  mov     rdi, cs:qword_1401A0910
0x140057bfa  call    cs:__imp_KeGetCurrentNodeNumber
0x140057c01  nop     dword ptr [rax+rax+00h]
0x140057c06  movzx   r8d, ax
0x140057c0a  mov     rdx, rbx
0x140057c0d  mov     rcx, rdi
0x140057c10  call    PplFreeToLookasideListProcessor
0x140057c15  jmp     loc_140057A85
0x140057c1a  call    cs:__imp_KeGetCurrentIrql
0x140057c21  nop     dword ptr [rax+rax+00h]
0x140057c26  test    al, al
0x140057c28  jnz     short loc_140057C9F
0x140057c2a  xor     bpl, bpl
0x140057c2d  mov     [rsp+0D8h+var_20], r14
0x140057c35  xorps   xmm0, xmm0
0x140057c38  movups  [rsp+0D8h+var_A8], xmm0
0x140057c3d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140057c41  jz      loc_140057DA1
0x140057c47  mov     rcx, rsi
0x140057c4a  call    cs:__imp_PsAttachSiloToCurrentThread
0x140057c51  nop     dword ptr [rax+rax+00h]
0x140057c56  mov     r14, rax
0x140057c59  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140057c60  mov     bpl, 1
0x140057c63  jnz     loc_140057E67
0x140057c69  mov     rcx, rdi
0x140057c6c  call    UlFreeHttpConnection
0x140057c71  test    bpl, bpl
0x140057c74  jz      short loc_140057C92
0x140057c76  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140057c7d  jnz     loc_140057EDA
0x140057c83  mov     rcx, r14
0x140057c86  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140057c8d  nop     dword ptr [rax+rax+00h]
0x140057c92  mov     r14, [rsp+0D8h+var_20]
0x140057c9a  jmp     loc_140057A2C
0x140057c9f  cmp     cs:dword_1401A3F48, 1
0x140057ca6  mov     ebp, r15d
0x140057ca9  jbe     short loc_140057CD0
0x140057cab  xor     ecx, ecx; ProcNumber
0x140057cad  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140057cb4  nop     dword ptr [rax+rax+00h]
0x140057cb9  xor     edx, edx
0x140057cbb  div     cs:UxNumberOfProcessors
0x140057cc1  cmp     cs:byte_1401A3F60, r15b
0x140057cc8  mov     ebp, edx
0x140057cca  jnz     loc_140057EF8
0x140057cd0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140057cd4  jnz     short loc_140057CE5
0x140057cd6  call    cs:__imp_PsGetCurrentServerSilo
0x140057cdd  nop     dword ptr [rax+rax+00h]
0x140057ce2  mov     rsi, rax
0x140057ce5  mov     [rdi+20h], rsi
0x140057ce9  mov     qword ptr [rsp+0D8h+var_A8], r15
0x140057cee  test    rsi, rsi
0x140057cf1  jnz     loc_140057F0B
0x140057cf7  mov     edx, cs:UxPodMonitorSlot
0x140057cfd  lea     r8, [rsp+0D8h+var_A8]
0x140057d02  mov     rcx, rsi
0x140057d05  call    cs:__imp_PsGetPermanentSiloContext
0x140057d0c  nop     dword ptr [rax+rax+00h]
0x140057d11  mov     rdx, qword ptr [rsp+0D8h+var_A8]
0x140057d16  mov     ecx, 1
0x140057d1b  add     rdx, 18h; BugCheckParameter2
0x140057d1f  lock xadd [rdx], ecx
0x140057d23  inc     ecx
0x140057d25  cmp     cs:UxDebugCheckRefcount, r15b
0x140057d2c  jnz     short loc_140057D88
0x140057d2e  mov     byte ptr [rdi+18h], 1
0x140057d32  mov     rdx, rdi; ListEntry
0x140057d35  mov     rax, cs:qword_1401A3F50
0x140057d3c  mov     ecx, ebp
0x140057d3e  mov     rsi, [rax+rcx*8]
0x140057d42  lea     rax, UlFreeHttpConnection
0x140057d49  mov     [rdi+10h], rax
0x140057d4d  lea     rcx, [rsi+10h]; ListHead
0x140057d51  call    cs:__imp_ExpInterlockedPushEntrySList
0x140057d58  nop     dword ptr [rax+rax+00h]
0x140057d5d  test    rax, rax
0x140057d60  jnz     loc_140057A2C
0x140057d66  lea     rcx, [rsi+20h]; Event
0x140057d6a  xor     r8d, r8d; Wait
0x140057d6d  xor     edx, edx; Increment
0x140057d6f  call    cs:__imp_KeSetEvent
0x140057d76  nop     dword ptr [rax+rax+00h]
0x140057d7b  mov     rcx, rsi; Context
0x140057d7e  call    UlpActivateThreadPoolQueue
0x140057d83  jmp     loc_140057A2C
0x140057d88  cmp     ecx, 0FFFFFFFFh
0x140057d8b  jg      short loc_140057D2E
0x140057d8d  movsxd  r9, ecx; BugCheckParameter4
  ... truncated ...
```

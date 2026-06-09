# UxTlDestroyConnection

- ea: `0x14005d930`
- end: `0x14005dfe1`
- name: `UxTlDestroyConnection`
- size: `1713`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `13`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005c7b0`
- `0x14005cda0`
- `0x14005ce20`
- `0x14005d250`
- `0x14005d310`
- `0x14005d510`
- `0x14005d530`
- `0x14005d710`
- `0x1400649b0`
- `0x1400bb7e0`
- `0x14013fb30`
- `0x14013fb88`
- `0x140154cd8`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140049d28`
- `0x14005d930`
- `0x14005dff0`
- `0x1400cb148`
- `0x14013dc78`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f78`
- `0x1401d9e44`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005da2e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005da2e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005dccd`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005dccd`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005ddbe`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005ddbe`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005ddff`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005ddff`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005dafd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005db97`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005dafd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005db97`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005dc22`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005dc22`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005dc7b`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005dc7b`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005dfa8`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005dfa8`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005da5a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005da5a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005dbd7`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005dbd7`
- `ntoskrnl!IoFreeIrp` at `0x14005da8f`
- `ntoskrnl!IoFreeIrp` at `0x14005da8f`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14005dd45`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14005dd45`
- `ntoskrnl!KeSetEvent` at `0x14005dceb`
- `ntoskrnl!KeSetEvent` at `0x14005ddec`
- `ntoskrnl!KeSetEvent` at `0x14005dceb`
- `ntoskrnl!KeSetEvent` at `0x14005ddec`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005dc4c`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005dc4c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005db80`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005dd97`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005db80`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005dd97`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14005dd28`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14005dd28`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005db3e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005db3e`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005d9d8`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005d9d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005db1e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005db1e`

## pseudocode

```c
__int64 __fastcall UxTlDestroyConnection(char *Entry)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  void (__fastcall *v4)(__int64); // rax
  __int64 v5; // r8
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v8; // r9
  __int64 v9; // rbp
  __int64 v10; // rcx
  void *CurrentServerSilo; // rbp
  char v12; // r15
  __int64 v13; // rax
  __int64 v14; // r12
  __int64 v15; // rbp
  IRP *v16; // rcx
  _DWORD *v17; // r14
  unsigned __int64 v18; // rdi
  __int64 v19; // rdi
  KIRQL v20; // al
  bool v21; // zf
  KIRQL v22; // si
  __int64 v23; // rax
  __int64 v24; // rdi
  USHORT v25; // ax
  __int64 v26; // r9
  int v27; // esi
  ULONG v28; // r14d
  ULONG_PTR v29; // rdx
  int v30; // eax
  __int64 v31; // rsi
  __int64 v32; // rdi
  USHORT CurrentNodeNumber; // ax
  ULONG_PTR v34; // rdx
  int v35; // eax
  ULONG_PTR v36; // rdx
  __int128 v37; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD v38[24]; // [rsp+40h] [rbp-98h] BYREF

  v2 = *((_QWORD *)Entry + 10);
  if ( v2 )
  {
    v3 = *((_QWORD *)Entry + 12);
    v4 = *(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL);
    *((_QWORD *)Entry + 10) = 0;
    v5 = *(_QWORD *)(v3 + 184);
    *(_QWORD *)(v5 - 16) = &UxpWskRestartCloseConnection;
    *(_QWORD *)(v5 - 8) = Entry;
    *(_BYTE *)(v5 - 69) = -32;
    v4(v2);
    return 259;
  }
  else
  {
    CurrentProcess = IoGetCurrentProcess();
    v9 = *((_QWORD *)Entry + 26);
    v10 = *((_QWORD *)Entry + 54);
    if ( UxSystemProcess == CurrentProcess )
    {
      if ( v10 || *((_QWORD *)Entry + 56) || *((_QWORD *)Entry + 58) )
        UlBugCheckEx(1u, (ULONG_PTR)(Entry + 432), (ULONG_PTR)"minio\\http\\sys\\wskp.c", 0x117Eu);
      CurrentServerSilo = *(void **)(v9 + 192);
      if ( KeGetCurrentIrql() )
      {
        v28 = 0;
        if ( (unsigned int)dword_1401A3F48 > 1 )
        {
          v28 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
          if ( byte_1401A3F60 )
            v28 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
        }
        if ( CurrentServerSilo == (void *)-1LL )
          CurrentServerSilo = (void *)PsGetCurrentServerSilo();
        *((_QWORD *)Entry + 58) = CurrentServerSilo;
        *(_QWORD *)&v37 = 0;
        if ( CurrentServerSilo )
          ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
        PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v37);
        v29 = v37 + 24;
        v30 = _InterlockedIncrement((volatile signed __int32 *)(v37 + 24));
        if ( UxDebugCheckRefcount && v30 <= -1 )
          UlBugCheckEx(3u, v29, 0xDu, v30);
        Entry[456] = 1;
        v31 = *(_QWORD *)(qword_1401A3F50 + 8LL * v28);
        *((_QWORD *)Entry + 56) = UxTlDestroyConnectionWorker;
        if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v31 + 16), (PSLIST_ENTRY)Entry + 27) )
        {
          KeSetEvent((PRKEVENT)(v31 + 32), 0, 0);
          if ( *(_BYTE *)(*(_QWORD *)v31 + 33LL) )
          {
            if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v31 + 68), 1, 0) )
            {
              if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
                WPP_SF_Dd(
                  1304,
                  18,
                  WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids,
                  *(unsigned int *)(v31 + 8),
                  **(_DWORD **)v31);
              _InterlockedIncrement((volatile signed __int32 *)(v31 + 64));
              ExAcquireRundownProtection(&UlThreadPoolIoWorkItemsRundown);
              IoQueueWorkItemEx(*(PIO_WORKITEM *)(v31 + 56), UlpThreadPoolStarter, DelayedWorkQueue, (PVOID)v31);
            }
          }
        }
      }
      else
      {
        v37 = 0;
        if ( CurrentServerSilo == (void *)-1LL )
        {
          v14 = *((_QWORD *)&v37 + 1);
          v12 = v37;
        }
        else
        {
          v12 = 1;
          v13 = PsAttachSiloToCurrentThread(CurrentServerSilo);
          v14 = v13;
          if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v13, CurrentServerSilo);
        }
        v15 = *((_QWORD *)Entry + 26);
        *((_QWORD *)Entry + 26) = 0;
        v16 = (IRP *)*((_QWORD *)Entry + 12);
        if ( v16 )
        {
          IoFreeIrp(v16);
          *((_QWORD *)Entry + 12) = 0;
        }
        v17 = (_DWORD *)*((_QWORD *)Entry + 13);
        if ( v17 )
        {
          memset(v38, 0, sizeof(v38));
          if ( UxDebugDisableLookaside )
          {
            v38[10] = dword_1401A0388;
            ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A0398)(v17, v38);
          }
          else if ( UxCompactMode )
          {
            v32 = qword_1401A0370;
            CurrentNodeNumber = KeGetCurrentNodeNumber();
            PplFreeToLookasideListProcessor(v32, v17, CurrentNodeNumber);
          }
          else
          {
            v18 = qword_1401A0370 + ((unsigned __int64)(unsigned int)(*v17 + 1) << 7);
            if ( !*(_BYTE *)(v18 + 176) )
              PplpLazyInitializeLookasideList(qword_1401A0370, v18 + 64);
            ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v18 + 64), v17);
          }
          *((_QWORD *)Entry + 13) = 0;
        }
        v19 = *((_QWORD *)Entry + 60);
        *((_QWORD *)Entry + 60) = 0;
        v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v19);
        v21 = (*(_DWORD *)(v19 + 12))-- == 1;
        v22 = v20;
        if ( v21 )
        {
          KeAcquireSpinLockAtDpcLevel(&UlPartitionsSpinLock);
          if ( !--UlPartitionsActiveCount )
            KeSetEvent(&UlScavengerRefreshEvent, 0, 0);
          KeReleaseSpinLockFromDpcLevel(&UlPartitionsSpinLock);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)v19, v22);
        v23 = *((_QWORD *)Entry + 65);
        if ( v23 )
        {
          v34 = v23 + 16;
          v35 = _InterlockedDecrement((volatile signed __int32 *)(v23 + 16));
          if ( UxDebugCheckRefcount && v35 <= -1 )
            UlBugCheckEx(3u, v34, 0xAu, v35);
          if ( !v35 )
            UlAiFreeAddressInformation(*((PVOID *)Entry + 65));
        }
        *((_DWORD *)Entry + 14) = 7;
        *((_DWORD *)Entry + 8) = 1129598069;
        if ( v15 )
        {
          v24 = *(_QWORD *)(*(_QWORD *)(v15 + 200) + 8680LL);
          v25 = KeGetCurrentNodeNumber();
          ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v24 + 8LL * v25 + 8), Entry);
          v27 = _InterlockedDecrement((volatile signed __int32 *)(v15 + 8));
          if ( UxDebugCheckRefcount && v27 <= -1 )
            UlBugCheckEx(3u, v15 + 8, 0xFu, v27);
          if ( !v27 )
          {
            v36 = v15 + 48;
            if ( *(_QWORD *)(v15 + 48) || *(_QWORD *)(v15 + 64) || *(_QWORD *)(v15 + 80) )
              UlBugCheckEx(1u, v36, (ULONG_PTR)"minio\\http\\sys\\tl.h", 0x400u);
            LOBYTE(v26) = 1;
            UlThreadPoolEnqueueWorkItem(0, v36, UxTlDestroyListenEndpoint, v26, *(_QWORD *)(v15 + 192), -1);
          }
        }
        if ( v12 )
        {
          if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v14);
          PsDetachSiloFromCurrentThread(v14);
        }
      }
    }
    else
    {
      if ( v10 || *((_QWORD *)Entry + 56) || *((_QWORD *)Entry + 58) )
        UlBugCheckEx(1u, (ULONG_PTR)(Entry + 432), (ULONG_PTR)"minio\\http\\sys\\wskp.c", 0x1178u);
      LOBYTE(v8) = 1;
      UlThreadPoolEnqueueWorkItem(0, Entry + 432, UxTlDestroyConnectionWorker, v8, *(_QWORD *)(v9 + 192), -1);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14005d930  push    rbx
0x14005d932  push    rsi
0x14005d933  sub     rsp, 0C8h
0x14005d93a  mov     rax, cs:__security_cookie
0x14005d941  xor     rax, rsp
0x14005d944  mov     [rsp+0D8h+var_38], rax
0x14005d94c  mov     rbx, rcx
0x14005d94f  mov     rcx, [rcx+50h]
0x14005d953  test    rcx, rcx
0x14005d956  jz      short loc_14005D9A9
0x14005d958  mov     rax, [rcx]
0x14005d95b  lea     r9, UxpWskRestartCloseConnection
0x14005d962  mov     rdx, [rbx+60h]
0x14005d966  xor     esi, esi
0x14005d968  mov     rax, [rax+8]
0x14005d96c  mov     [rbx+50h], rsi
0x14005d970  mov     r8, [rdx+0B8h]
0x14005d977  mov     [r8-10h], r9
0x14005d97b  mov     [r8-8], rbx
0x14005d97f  mov     byte ptr [r8-45h], 0E0h
0x14005d984  call    _guard_dispatch_icall
0x14005d989  mov     eax, 103h
0x14005d98e  mov     rcx, [rsp+0D8h+var_38]
0x14005d996  xor     rcx, rsp; StackCookie
0x14005d999  call    __security_check_cookie
0x14005d99e  add     rsp, 0C8h
0x14005d9a5  pop     rsi
0x14005d9a6  pop     rbx
0x14005d9a7  retn
0x14005d9a9  mov     [rsp+0D8h+arg_8], rbp
0x14005d9b1  mov     [rsp+0D8h+arg_10], rdi
0x14005d9b9  lea     rdi, [rbx+1B0h]
0x14005d9c0  mov     [rsp+0D8h+var_18], r12
0x14005d9c8  mov     [rsp+0D8h+var_20], r14
0x14005d9d0  mov     [rsp+0D8h+var_28], r15
0x14005d9d8  call    cs:__imp_IoGetCurrentProcess
0x14005d9df  nop     dword ptr [rax+rax+00h]
0x14005d9e4  cmp     cs:UxSystemProcess, rax
0x14005d9eb  mov     rbp, [rbx+0D0h]
0x14005d9f2  mov     rcx, [rdi]
0x14005d9f5  jnz     loc_14005DE4E
0x14005d9fb  test    rcx, rcx
0x14005d9fe  jnz     short loc_14005DA0C
0x14005da00  cmp     [rdi+10h], rcx
0x14005da04  jnz     short loc_14005DA0C
0x14005da06  cmp     [rdi+20h], rcx
0x14005da0a  jz      short loc_14005DA27
0x14005da0c  mov     r9d, 117Eh; BugCheckParameter4
0x14005da12  lea     r8, aMinioHttpSysWs; "minio\\http\\sys\\wskp.c"
0x14005da19  mov     rdx, rdi; BugCheckParameter2
0x14005da1c  mov     ecx, 1; BugCheckParameter1
0x14005da21  call    UlBugCheckEx
0x14005da27  mov     rbp, [rbp+0C0h]
0x14005da2e  call    cs:__imp_KeGetCurrentIrql
0x14005da35  nop     dword ptr [rax+rax+00h]
0x14005da3a  test    al, al
0x14005da3c  jnz     loc_14005DC12
0x14005da42  xorps   xmm0, xmm0
0x14005da45  movups  [rsp+0D8h+var_A8], xmm0
0x14005da4a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14005da4e  jz      loc_14005DE10
0x14005da54  mov     rcx, rbp
0x14005da57  mov     r15b, 1
0x14005da5a  call    cs:__imp_PsAttachSiloToCurrentThread
0x14005da61  nop     dword ptr [rax+rax+00h]
0x14005da66  mov     r12, rax
0x14005da69  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14005da70  jnz     loc_14005DEBF
0x14005da76  mov     rbp, [rbx+0D0h]
0x14005da7d  xor     esi, esi
0x14005da7f  mov     [rbx+0D0h], rsi
0x14005da86  mov     rcx, [rbx+60h]; Irp
0x14005da8a  test    rcx, rcx
0x14005da8d  jz      short loc_14005DA9F
0x14005da8f  call    cs:__imp_IoFreeIrp
0x14005da96  nop     dword ptr [rax+rax+00h]
0x14005da9b  mov     [rbx+60h], rsi
0x14005da9f  mov     r14, [rbx+68h]
0x14005daa3  test    r14, r14
0x14005daa6  jz      short loc_14005DB0D
0x14005daa8  xor     edx, edx; Val
0x14005daaa  lea     rcx, [rsp+0D8h+var_98]; void *
0x14005daaf  mov     r8d, 60h ; '`'; Size
0x14005dab5  call    memset
0x14005daba  cmp     cs:UxDebugDisableLookaside, sil
0x14005dac1  jnz     loc_14005DF4B
0x14005dac7  cmp     cs:UxCompactMode, sil
0x14005dace  jnz     loc_14005DD90
0x14005dad4  mov     edi, [r14]
0x14005dad7  mov     rcx, cs:qword_1401A0370
0x14005dade  inc     edi
0x14005dae0  shl     rdi, 7
0x14005dae4  add     rdi, rcx
0x14005dae7  movzx   eax, byte ptr [rdi+0B0h]
0x14005daee  test    al, al
0x14005daf0  jz      loc_14005DEE2
0x14005daf6  mov     rdx, r14; Entry
0x14005daf9  lea     rcx, [rdi+40h]; Lookaside
0x14005dafd  call    cs:__imp_ExFreeToLookasideListEx
0x14005db04  nop     dword ptr [rax+rax+00h]
0x14005db09  mov     [rbx+68h], rsi
0x14005db0d  mov     rdi, [rbx+1E0h]
0x14005db14  mov     rcx, rdi; SpinLock
0x14005db17  mov     [rbx+1E0h], rsi
0x14005db1e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005db25  nop     dword ptr [rax+rax+00h]
0x14005db2a  add     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x14005db2e  movzx   esi, al
0x14005db31  jz      loc_14005DDB7
0x14005db37  movzx   edx, sil; NewIrql
0x14005db3b  mov     rcx, rdi; SpinLock
0x14005db3e  call    cs:__imp_KeReleaseSpinLock
0x14005db45  nop     dword ptr [rax+rax+00h]
0x14005db4a  mov     rax, [rbx+208h]
0x14005db51  mov     esi, 0FFFFFFFFh
0x14005db56  test    rax, rax
0x14005db59  jnz     loc_14005DE20
0x14005db5f  mov     dword ptr [rbx+38h], 7
0x14005db66  mov     dword ptr [rbx+20h], 43544C75h
0x14005db6d  test    rbp, rbp
0x14005db70  jz      short loc_14005DBC2
0x14005db72  mov     rax, [rbp+0C8h]
0x14005db79  mov     rdi, [rax+21E8h]
0x14005db80  call    cs:__imp_KeGetCurrentNodeNumber
0x14005db87  nop     dword ptr [rax+rax+00h]
0x14005db8c  movzx   ecx, ax
0x14005db8f  mov     rdx, rbx; Entry
0x14005db92  mov     rcx, [rdi+rcx*8+8]; Lookaside
0x14005db97  call    cs:__imp_ExFreeToLookasideListEx
0x14005db9e  nop     dword ptr [rax+rax+00h]
0x14005dba3  lea     rdx, [rbp+8]; BugCheckParameter2
0x14005dba7  lock xadd [rdx], esi
0x14005dbab  dec     esi
0x14005dbad  cmp     cs:UxDebugCheckRefcount, 0
0x14005dbb4  jnz     loc_14005DD56
0x14005dbba  test    esi, esi
0x14005dbbc  jz      loc_14005DEF0
0x14005dbc2  test    r15b, r15b
0x14005dbc5  jz      short loc_14005DBE3
0x14005dbc7  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14005dbce  jnz     loc_14005DF6E
0x14005dbd4  mov     rcx, r12
0x14005dbd7  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14005dbde  nop     dword ptr [rax+rax+00h]
0x14005dbe3  mov     r14, [rsp+0D8h+var_20]
0x14005dbeb  xor     eax, eax
0x14005dbed  mov     r12, [rsp+0D8h+var_18]
0x14005dbf5  mov     rdi, [rsp+0D8h+arg_10]
0x14005dbfd  mov     rbp, [rsp+0D8h+arg_8]
0x14005dc05  mov     r15, [rsp+0D8h+var_28]
0x14005dc0d  jmp     loc_14005D98E
0x14005dc12  xor     esi, esi
0x14005dc14  cmp     cs:dword_1401A3F48, 1
0x14005dc1b  mov     r14d, esi
0x14005dc1e  jbe     short loc_14005DC46
0x14005dc20  xor     ecx, ecx; ProcNumber
0x14005dc22  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14005dc29  nop     dword ptr [rax+rax+00h]
0x14005dc2e  xor     edx, edx
0x14005dc30  div     cs:UxNumberOfProcessors
0x14005dc36  cmp     cs:byte_1401A3F60, sil
0x14005dc3d  mov     r14d, edx
0x14005dc40  jnz     loc_14005DF8C
0x14005dc46  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14005dc4a  jnz     short loc_14005DC5B
0x14005dc4c  call    cs:__imp_PsGetCurrentServerSilo
0x14005dc53  nop     dword ptr [rax+rax+00h]
0x14005dc58  mov     rbp, rax
0x14005dc5b  mov     [rdi+20h], rbp
0x14005dc5f  mov     qword ptr [rsp+0D8h+var_A8], rsi
0x14005dc64  test    rbp, rbp
0x14005dc67  jnz     loc_14005DFA0
0x14005dc6d  mov     edx, cs:UxPodMonitorSlot
0x14005dc73  lea     r8, [rsp+0D8h+var_A8]
0x14005dc78  mov     rcx, rbp
0x14005dc7b  call    cs:__imp_PsGetPermanentSiloContext
0x14005dc82  nop     dword ptr [rax+rax+00h]
0x14005dc87  mov     rdx, qword ptr [rsp+0D8h+var_A8]
0x14005dc8c  mov     ebx, 1
0x14005dc91  add     rdx, 18h; BugCheckParameter2
0x14005dc95  mov     eax, ebx
0x14005dc97  lock xadd [rdx], eax
0x14005dc9b  inc     eax
0x14005dc9d  cmp     cs:UxDebugCheckRefcount, sil
0x14005dca4  jnz     loc_14005DD73
0x14005dcaa  mov     [rdi+18h], bl
0x14005dcad  mov     rdx, rdi; ListEntry
0x14005dcb0  mov     rax, cs:qword_1401A3F50
0x14005dcb7  mov     ecx, r14d
0x14005dcba  mov     rsi, [rax+rcx*8]
0x14005dcbe  lea     rax, UxTlDestroyConnectionWorker
0x14005dcc5  mov     [rdi+10h], rax
0x14005dcc9  lea     rcx, [rsi+10h]; ListHead
0x14005dccd  call    cs:__imp_ExpInterlockedPushEntrySList
0x14005dcd4  nop     dword ptr [rax+rax+00h]
0x14005dcd9  test    rax, rax
0x14005dcdc  jnz     loc_14005DBE3
0x14005dce2  lea     rcx, [rsi+20h]; Event
0x14005dce6  xor     r8d, r8d; Wait
0x14005dce9  xor     edx, edx; Increment
0x14005dceb  call    cs:__imp_KeSetEvent
0x14005dcf2  nop     dword ptr [rax+rax+00h]
0x14005dcf7  mov     rax, [rsi]
0x14005dcfa  cmp     byte ptr [rax+21h], 0
0x14005dcfe  jz      loc_14005DBE3
0x14005dd04  xor     eax, eax
0x14005dd06  lock cmpxchg [rsi+44h], ebx
0x14005dd0b  jnz     loc_14005DBE3
0x14005dd11  test    byte ptr cs:xmmword_1401A2CA0+0Bh, bl
0x14005dd17  jnz     loc_14005DFB9
0x14005dd1d  lock inc dword ptr [rsi+40h]
0x14005dd21  lea     rcx, UlThreadPoolIoWorkItemsRundown; RunRef
0x14005dd28  call    cs:__imp_ExAcquireRundownProtection
0x14005dd2f  nop     dword ptr [rax+rax+00h]
0x14005dd34  mov     rcx, [rsi+38h]; IoWorkItem
0x14005dd38  lea     rdx, UlpThreadPoolStarter; WorkerRoutine
0x14005dd3f  mov     r9, rsi; Context
0x14005dd42  mov     r8d, ebx; QueueType
0x14005dd45  call    cs:__imp_IoQueueWorkItemEx
0x14005dd4c  nop     dword ptr [rax+rax+00h]
0x14005dd51  jmp     loc_14005DBE3
0x14005dd56  cmp     esi, 0FFFFFFFFh
0x14005dd59  jg      loc_14005DBBA
0x14005dd5f  movsxd  r9, esi; BugCheckParameter4
0x14005dd62  mov     ecx, 3; BugCheckParameter1
0x14005dd67  mov     r8d, 0Fh; BugCheckParameter3
0x14005dd6d  call    UlBugCheckEx
0x14005dd73  cmp     eax, 0FFFFFFFFh
0x14005dd76  jg      loc_14005DCAA
0x14005dd7c  movsxd  r9, eax; BugCheckParameter4
0x14005dd7f  mov     ecx, 3; BugCheckParameter1
0x14005dd84  mov     r8d, 0Dh; BugCheckParameter3
0x14005dd8a  call    UlBugCheckEx
0x14005dd90  mov     rdi, cs:qword_1401A0370
0x14005dd97  call    cs:__imp_KeGetCurrentNodeNumber
0x14005dd9e  nop     dword ptr [rax+rax+00h]
0x14005dda3  movzx   r8d, ax
0x14005dda7  mov     rdx, r14
0x14005ddaa  mov     rcx, rdi
0x14005ddad  call    PplFreeToLookasideListProcessor
0x14005ddb2  jmp     loc_14005DB09
0x14005ddb7  lea     rcx, UlPartitionsSpinLock; SpinLock
0x14005ddbe  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14005ddc5  nop     dword ptr [rax+rax+00h]
0x14005ddca  mov     edx, cs:UlPartitionsActiveCount
0x14005ddd0  dec     edx
0x14005ddd2  mov     cs:UlPartitionsActiveCount, edx
0x14005ddd8  mov     edx, cs:UlPartitionsActiveCount; Increment
0x14005ddde  test    edx, edx
0x14005dde0  jnz     short loc_14005DDF8
0x14005dde2  xor     r8d, r8d; Wait
0x14005dde5  lea     rcx, UlScavengerRefreshEvent; Event
0x14005ddec  call    cs:__imp_KeSetEvent
0x14005ddf3  nop     dword ptr [rax+rax+00h]
0x14005ddf8  lea     rcx, UlPartitionsSpinLock; SpinLock
0x14005ddff  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14005de06  nop     dword ptr [rax+rax+00h]
0x14005de0b  jmp     loc_14005DB37
0x14005de10  mov     r12, qword ptr [rsp+0D8h+var_A8+8]
0x14005de15  movzx   r15d, byte ptr [rsp+0D8h+var_A8]
0x14005de1b  jmp     loc_14005DA76
0x14005de20  lea     rdx, [rax+10h]; BugCheckParameter2
0x14005de24  mov     eax, esi
0x14005de26  lock xadd [rdx], eax
0x14005de2a  dec     eax
0x14005de2c  cmp     cs:UxDebugCheckRefcount, 0
0x14005de33  jnz     short loc_14005DE7A
0x14005de35  test    eax, eax
0x14005de37  jnz     loc_14005DB5F
0x14005de3d  mov     rcx, [rbx+208h]; P
0x14005de44  call    UlAiFreeAddressInformation
0x14005de49  jmp     loc_14005DB5F
0x14005de4e  test    rcx, rcx
0x14005de51  jnz     short loc_14005DE5F
0x14005de53  cmp     [rdi+10h], rcx
0x14005de57  jnz     short loc_14005DE5F
0x14005de59  cmp     [rdi+20h], rcx
0x14005de5d  jz      short loc_14005DE92
0x14005de5f  mov     r9d, 1178h; BugCheckParameter4
0x14005de65  lea     r8, aMinioHttpSysWs; "minio\\http\\sys\\wskp.c"
0x14005de6c  mov     rdx, rdi; BugCheckParameter2
0x14005de6f  mov     ecx, 1; BugCheckParameter1
0x14005de74  call    UlBugCheckEx
0x14005de7a  cmp     eax, esi
0x14005de7c  jg      short loc_14005DE35
0x14005de7e  movsxd  r9, eax; BugCheckParameter4
0x14005de81  mov     ecx, 3; BugCheckParameter1
0x14005de86  mov     r8d, 0Ah; BugCheckParameter3
0x14005de8c  call    UlBugCheckEx
0x14005de92  mov     rax, [rbp+0C0h]
0x14005de99  lea     r8, UxTlDestroyConnectionWorker
0x14005dea0  mov     [rsp+0D8h+var_B0], 0FFFFFFFFh
0x14005dea8  mov     r9b, 1
0x14005deab  mov     rdx, rdi
0x14005deae  mov     [rsp+0D8h+var_B8], rax
0x14005deb3  xor     ecx, ecx
0x14005deb5  call    UlThreadPoolEnqueueWorkItem
0x14005deba  jmp     loc_14005DBE3
0x14005debf  mov     edx, 19h
0x14005dec4  mov     [rsp+0D8h+var_B8], rbp
  ... truncated ...
```

# UxTlDestroyConnection

- ea: `0x14005d910`
- end: `0x14005dfc1`
- name: `UxTlDestroyConnection`
- size: `1713`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `13`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005c790`
- `0x14005cd80`
- `0x14005ce00`
- `0x14005d230`
- `0x14005d2f0`
- `0x14005d4f0`
- `0x14005d510`
- `0x14005d6f0`
- `0x140064990`
- `0x1400bb700`
- `0x14013fc20`
- `0x14013fc78`
- `0x140154de8`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140049d08`
- `0x14005d910`
- `0x14005dfd0`
- `0x1400cb068`
- `0x14013dd68`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f78`
- `0x1401d9e44`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005da0e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005da0e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005dcad`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005dcad`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005dd9e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005dd9e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005dddf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005dddf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005dadd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005db77`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005dadd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005db77`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005dc02`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005dc02`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005dc5b`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005dc5b`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005df88`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005df88`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005da3a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005da3a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005dbb7`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005dbb7`
- `ntoskrnl!IoFreeIrp` at `0x14005da6f`
- `ntoskrnl!IoFreeIrp` at `0x14005da6f`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14005dd25`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14005dd25`
- `ntoskrnl!KeSetEvent` at `0x14005dccb`
- `ntoskrnl!KeSetEvent` at `0x14005ddcc`
- `ntoskrnl!KeSetEvent` at `0x14005dccb`
- `ntoskrnl!KeSetEvent` at `0x14005ddcc`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005dc2c`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005dc2c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005db60`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005dd77`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005db60`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005dd77`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14005dd08`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14005dd08`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005db1e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005db1e`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005d9b8`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005d9b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005dafe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005dafe`

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
0x14005d910  push    rbx
0x14005d912  push    rsi
0x14005d913  sub     rsp, 0C8h
0x14005d91a  mov     rax, cs:__security_cookie
0x14005d921  xor     rax, rsp
0x14005d924  mov     [rsp+0D8h+var_38], rax
0x14005d92c  mov     rbx, rcx
0x14005d92f  mov     rcx, [rcx+50h]
0x14005d933  test    rcx, rcx
0x14005d936  jz      short loc_14005D989
0x14005d938  mov     rax, [rcx]
0x14005d93b  lea     r9, UxpWskRestartCloseConnection
0x14005d942  mov     rdx, [rbx+60h]
0x14005d946  xor     esi, esi
0x14005d948  mov     rax, [rax+8]
0x14005d94c  mov     [rbx+50h], rsi
0x14005d950  mov     r8, [rdx+0B8h]
0x14005d957  mov     [r8-10h], r9
0x14005d95b  mov     [r8-8], rbx
0x14005d95f  mov     byte ptr [r8-45h], 0E0h
0x14005d964  call    _guard_dispatch_icall
0x14005d969  mov     eax, 103h
0x14005d96e  mov     rcx, [rsp+0D8h+var_38]
0x14005d976  xor     rcx, rsp; StackCookie
0x14005d979  call    __security_check_cookie
0x14005d97e  add     rsp, 0C8h
0x14005d985  pop     rsi
0x14005d986  pop     rbx
0x14005d987  retn
0x14005d989  mov     [rsp+0D8h+arg_8], rbp
0x14005d991  mov     [rsp+0D8h+arg_10], rdi
0x14005d999  lea     rdi, [rbx+1B0h]
0x14005d9a0  mov     [rsp+0D8h+var_18], r12
0x14005d9a8  mov     [rsp+0D8h+var_20], r14
0x14005d9b0  mov     [rsp+0D8h+var_28], r15
0x14005d9b8  call    cs:__imp_IoGetCurrentProcess
0x14005d9bf  nop     dword ptr [rax+rax+00h]
0x14005d9c4  cmp     cs:UxSystemProcess, rax
0x14005d9cb  mov     rbp, [rbx+0D0h]
0x14005d9d2  mov     rcx, [rdi]
0x14005d9d5  jnz     loc_14005DE2E
0x14005d9db  test    rcx, rcx
0x14005d9de  jnz     short loc_14005D9EC
0x14005d9e0  cmp     [rdi+10h], rcx
0x14005d9e4  jnz     short loc_14005D9EC
0x14005d9e6  cmp     [rdi+20h], rcx
0x14005d9ea  jz      short loc_14005DA07
0x14005d9ec  mov     r9d, 117Eh; BugCheckParameter4
0x14005d9f2  lea     r8, aMinioHttpSysWs; "minio\\http\\sys\\wskp.c"
0x14005d9f9  mov     rdx, rdi; BugCheckParameter2
0x14005d9fc  mov     ecx, 1; BugCheckParameter1
0x14005da01  call    UlBugCheckEx
0x14005da07  mov     rbp, [rbp+0C0h]
0x14005da0e  call    cs:__imp_KeGetCurrentIrql
0x14005da15  nop     dword ptr [rax+rax+00h]
0x14005da1a  test    al, al
0x14005da1c  jnz     loc_14005DBF2
0x14005da22  xorps   xmm0, xmm0
0x14005da25  movups  [rsp+0D8h+var_A8], xmm0
0x14005da2a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14005da2e  jz      loc_14005DDF0
0x14005da34  mov     rcx, rbp
0x14005da37  mov     r15b, 1
0x14005da3a  call    cs:__imp_PsAttachSiloToCurrentThread
0x14005da41  nop     dword ptr [rax+rax+00h]
0x14005da46  mov     r12, rax
0x14005da49  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14005da50  jnz     loc_14005DE9F
0x14005da56  mov     rbp, [rbx+0D0h]
0x14005da5d  xor     esi, esi
0x14005da5f  mov     [rbx+0D0h], rsi
0x14005da66  mov     rcx, [rbx+60h]; Irp
0x14005da6a  test    rcx, rcx
0x14005da6d  jz      short loc_14005DA7F
0x14005da6f  call    cs:__imp_IoFreeIrp
0x14005da76  nop     dword ptr [rax+rax+00h]
0x14005da7b  mov     [rbx+60h], rsi
0x14005da7f  mov     r14, [rbx+68h]
0x14005da83  test    r14, r14
0x14005da86  jz      short loc_14005DAED
0x14005da88  xor     edx, edx; Val
0x14005da8a  lea     rcx, [rsp+0D8h+var_98]; void *
0x14005da8f  mov     r8d, 60h ; '`'; Size
0x14005da95  call    memset
0x14005da9a  cmp     cs:UxDebugDisableLookaside, sil
0x14005daa1  jnz     loc_14005DF2B
0x14005daa7  cmp     cs:UxCompactMode, sil
0x14005daae  jnz     loc_14005DD70
0x14005dab4  mov     edi, [r14]
0x14005dab7  mov     rcx, cs:qword_1401A0370
0x14005dabe  inc     edi
0x14005dac0  shl     rdi, 7
0x14005dac4  add     rdi, rcx
0x14005dac7  movzx   eax, byte ptr [rdi+0B0h]
0x14005dace  test    al, al
0x14005dad0  jz      loc_14005DEC2
0x14005dad6  mov     rdx, r14; Entry
0x14005dad9  lea     rcx, [rdi+40h]; Lookaside
0x14005dadd  call    cs:__imp_ExFreeToLookasideListEx
0x14005dae4  nop     dword ptr [rax+rax+00h]
0x14005dae9  mov     [rbx+68h], rsi
0x14005daed  mov     rdi, [rbx+1E0h]
0x14005daf4  mov     rcx, rdi; SpinLock
0x14005daf7  mov     [rbx+1E0h], rsi
0x14005dafe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005db05  nop     dword ptr [rax+rax+00h]
0x14005db0a  add     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x14005db0e  movzx   esi, al
0x14005db11  jz      loc_14005DD97
0x14005db17  movzx   edx, sil; NewIrql
0x14005db1b  mov     rcx, rdi; SpinLock
0x14005db1e  call    cs:__imp_KeReleaseSpinLock
0x14005db25  nop     dword ptr [rax+rax+00h]
0x14005db2a  mov     rax, [rbx+208h]
0x14005db31  mov     esi, 0FFFFFFFFh
0x14005db36  test    rax, rax
0x14005db39  jnz     loc_14005DE00
0x14005db3f  mov     dword ptr [rbx+38h], 7
0x14005db46  mov     dword ptr [rbx+20h], 43544C75h
0x14005db4d  test    rbp, rbp
0x14005db50  jz      short loc_14005DBA2
0x14005db52  mov     rax, [rbp+0C8h]
0x14005db59  mov     rdi, [rax+21E8h]
0x14005db60  call    cs:__imp_KeGetCurrentNodeNumber
0x14005db67  nop     dword ptr [rax+rax+00h]
0x14005db6c  movzx   ecx, ax
0x14005db6f  mov     rdx, rbx; Entry
0x14005db72  mov     rcx, [rdi+rcx*8+8]; Lookaside
0x14005db77  call    cs:__imp_ExFreeToLookasideListEx
0x14005db7e  nop     dword ptr [rax+rax+00h]
0x14005db83  lea     rdx, [rbp+8]; BugCheckParameter2
0x14005db87  lock xadd [rdx], esi
0x14005db8b  dec     esi
0x14005db8d  cmp     cs:UxDebugCheckRefcount, 0
0x14005db94  jnz     loc_14005DD36
0x14005db9a  test    esi, esi
0x14005db9c  jz      loc_14005DED0
0x14005dba2  test    r15b, r15b
0x14005dba5  jz      short loc_14005DBC3
0x14005dba7  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14005dbae  jnz     loc_14005DF4E
0x14005dbb4  mov     rcx, r12
0x14005dbb7  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14005dbbe  nop     dword ptr [rax+rax+00h]
0x14005dbc3  mov     r14, [rsp+0D8h+var_20]
0x14005dbcb  xor     eax, eax
0x14005dbcd  mov     r12, [rsp+0D8h+var_18]
0x14005dbd5  mov     rdi, [rsp+0D8h+arg_10]
0x14005dbdd  mov     rbp, [rsp+0D8h+arg_8]
0x14005dbe5  mov     r15, [rsp+0D8h+var_28]
0x14005dbed  jmp     loc_14005D96E
0x14005dbf2  xor     esi, esi
0x14005dbf4  cmp     cs:dword_1401A3F48, 1
0x14005dbfb  mov     r14d, esi
0x14005dbfe  jbe     short loc_14005DC26
0x14005dc00  xor     ecx, ecx; ProcNumber
0x14005dc02  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14005dc09  nop     dword ptr [rax+rax+00h]
0x14005dc0e  xor     edx, edx
0x14005dc10  div     cs:UxNumberOfProcessors
0x14005dc16  cmp     cs:byte_1401A3F60, sil
0x14005dc1d  mov     r14d, edx
0x14005dc20  jnz     loc_14005DF6C
0x14005dc26  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14005dc2a  jnz     short loc_14005DC3B
0x14005dc2c  call    cs:__imp_PsGetCurrentServerSilo
0x14005dc33  nop     dword ptr [rax+rax+00h]
0x14005dc38  mov     rbp, rax
0x14005dc3b  mov     [rdi+20h], rbp
0x14005dc3f  mov     qword ptr [rsp+0D8h+var_A8], rsi
0x14005dc44  test    rbp, rbp
0x14005dc47  jnz     loc_14005DF80
0x14005dc4d  mov     edx, cs:UxPodMonitorSlot
0x14005dc53  lea     r8, [rsp+0D8h+var_A8]
0x14005dc58  mov     rcx, rbp
0x14005dc5b  call    cs:__imp_PsGetPermanentSiloContext
0x14005dc62  nop     dword ptr [rax+rax+00h]
0x14005dc67  mov     rdx, qword ptr [rsp+0D8h+var_A8]
0x14005dc6c  mov     ebx, 1
0x14005dc71  add     rdx, 18h; BugCheckParameter2
0x14005dc75  mov     eax, ebx
0x14005dc77  lock xadd [rdx], eax
0x14005dc7b  inc     eax
0x14005dc7d  cmp     cs:UxDebugCheckRefcount, sil
0x14005dc84  jnz     loc_14005DD53
0x14005dc8a  mov     [rdi+18h], bl
0x14005dc8d  mov     rdx, rdi; ListEntry
0x14005dc90  mov     rax, cs:qword_1401A3F50
0x14005dc97  mov     ecx, r14d
0x14005dc9a  mov     rsi, [rax+rcx*8]
0x14005dc9e  lea     rax, UxTlDestroyConnectionWorker
0x14005dca5  mov     [rdi+10h], rax
0x14005dca9  lea     rcx, [rsi+10h]; ListHead
0x14005dcad  call    cs:__imp_ExpInterlockedPushEntrySList
0x14005dcb4  nop     dword ptr [rax+rax+00h]
0x14005dcb9  test    rax, rax
0x14005dcbc  jnz     loc_14005DBC3
0x14005dcc2  lea     rcx, [rsi+20h]; Event
0x14005dcc6  xor     r8d, r8d; Wait
0x14005dcc9  xor     edx, edx; Increment
0x14005dccb  call    cs:__imp_KeSetEvent
0x14005dcd2  nop     dword ptr [rax+rax+00h]
0x14005dcd7  mov     rax, [rsi]
0x14005dcda  cmp     byte ptr [rax+21h], 0
0x14005dcde  jz      loc_14005DBC3
0x14005dce4  xor     eax, eax
0x14005dce6  lock cmpxchg [rsi+44h], ebx
0x14005dceb  jnz     loc_14005DBC3
0x14005dcf1  test    byte ptr cs:xmmword_1401A2CA0+0Bh, bl
0x14005dcf7  jnz     loc_14005DF99
0x14005dcfd  lock inc dword ptr [rsi+40h]
0x14005dd01  lea     rcx, UlThreadPoolIoWorkItemsRundown; RunRef
0x14005dd08  call    cs:__imp_ExAcquireRundownProtection
0x14005dd0f  nop     dword ptr [rax+rax+00h]
0x14005dd14  mov     rcx, [rsi+38h]; IoWorkItem
0x14005dd18  lea     rdx, UlpThreadPoolStarter; WorkerRoutine
0x14005dd1f  mov     r9, rsi; Context
0x14005dd22  mov     r8d, ebx; QueueType
0x14005dd25  call    cs:__imp_IoQueueWorkItemEx
0x14005dd2c  nop     dword ptr [rax+rax+00h]
0x14005dd31  jmp     loc_14005DBC3
0x14005dd36  cmp     esi, 0FFFFFFFFh
0x14005dd39  jg      loc_14005DB9A
0x14005dd3f  movsxd  r9, esi; BugCheckParameter4
0x14005dd42  mov     ecx, 3; BugCheckParameter1
0x14005dd47  mov     r8d, 0Fh; BugCheckParameter3
0x14005dd4d  call    UlBugCheckEx
0x14005dd53  cmp     eax, 0FFFFFFFFh
0x14005dd56  jg      loc_14005DC8A
0x14005dd5c  movsxd  r9, eax; BugCheckParameter4
0x14005dd5f  mov     ecx, 3; BugCheckParameter1
0x14005dd64  mov     r8d, 0Dh; BugCheckParameter3
0x14005dd6a  call    UlBugCheckEx
0x14005dd70  mov     rdi, cs:qword_1401A0370
0x14005dd77  call    cs:__imp_KeGetCurrentNodeNumber
0x14005dd7e  nop     dword ptr [rax+rax+00h]
0x14005dd83  movzx   r8d, ax
0x14005dd87  mov     rdx, r14
0x14005dd8a  mov     rcx, rdi
0x14005dd8d  call    PplFreeToLookasideListProcessor
0x14005dd92  jmp     loc_14005DAE9
0x14005dd97  lea     rcx, UlPartitionsSpinLock; SpinLock
0x14005dd9e  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14005dda5  nop     dword ptr [rax+rax+00h]
0x14005ddaa  mov     edx, cs:UlPartitionsActiveCount
0x14005ddb0  dec     edx
0x14005ddb2  mov     cs:UlPartitionsActiveCount, edx
0x14005ddb8  mov     edx, cs:UlPartitionsActiveCount; Increment
0x14005ddbe  test    edx, edx
0x14005ddc0  jnz     short loc_14005DDD8
0x14005ddc2  xor     r8d, r8d; Wait
0x14005ddc5  lea     rcx, UlScavengerRefreshEvent; Event
0x14005ddcc  call    cs:__imp_KeSetEvent
0x14005ddd3  nop     dword ptr [rax+rax+00h]
0x14005ddd8  lea     rcx, UlPartitionsSpinLock; SpinLock
0x14005dddf  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14005dde6  nop     dword ptr [rax+rax+00h]
0x14005ddeb  jmp     loc_14005DB17
0x14005ddf0  mov     r12, qword ptr [rsp+0D8h+var_A8+8]
0x14005ddf5  movzx   r15d, byte ptr [rsp+0D8h+var_A8]
0x14005ddfb  jmp     loc_14005DA56
0x14005de00  lea     rdx, [rax+10h]; BugCheckParameter2
0x14005de04  mov     eax, esi
0x14005de06  lock xadd [rdx], eax
0x14005de0a  dec     eax
0x14005de0c  cmp     cs:UxDebugCheckRefcount, 0
0x14005de13  jnz     short loc_14005DE5A
0x14005de15  test    eax, eax
0x14005de17  jnz     loc_14005DB3F
0x14005de1d  mov     rcx, [rbx+208h]; P
0x14005de24  call    UlAiFreeAddressInformation
0x14005de29  jmp     loc_14005DB3F
0x14005de2e  test    rcx, rcx
0x14005de31  jnz     short loc_14005DE3F
0x14005de33  cmp     [rdi+10h], rcx
0x14005de37  jnz     short loc_14005DE3F
0x14005de39  cmp     [rdi+20h], rcx
0x14005de3d  jz      short loc_14005DE72
0x14005de3f  mov     r9d, 1178h; BugCheckParameter4
0x14005de45  lea     r8, aMinioHttpSysWs; "minio\\http\\sys\\wskp.c"
0x14005de4c  mov     rdx, rdi; BugCheckParameter2
0x14005de4f  mov     ecx, 1; BugCheckParameter1
0x14005de54  call    UlBugCheckEx
0x14005de5a  cmp     eax, esi
0x14005de5c  jg      short loc_14005DE15
0x14005de5e  movsxd  r9, eax; BugCheckParameter4
0x14005de61  mov     ecx, 3; BugCheckParameter1
0x14005de66  mov     r8d, 0Ah; BugCheckParameter3
0x14005de6c  call    UlBugCheckEx
0x14005de72  mov     rax, [rbp+0C0h]
0x14005de79  lea     r8, UxTlDestroyConnectionWorker
0x14005de80  mov     [rsp+0D8h+var_B0], 0FFFFFFFFh
0x14005de88  mov     r9b, 1
0x14005de8b  mov     rdx, rdi
0x14005de8e  mov     [rsp+0D8h+var_B8], rax
0x14005de93  xor     ecx, ecx
0x14005de95  call    UlThreadPoolEnqueueWorkItem
0x14005de9a  jmp     loc_14005DBC3
0x14005de9f  mov     edx, 19h
0x14005dea4  mov     [rsp+0D8h+var_B8], rbp
  ... truncated ...
```

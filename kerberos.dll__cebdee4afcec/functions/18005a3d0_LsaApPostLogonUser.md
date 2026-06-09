# LsaApPostLogonUser

- ea: `0x18005a3d0`
- end: `0x18005a6f7`
- name: `LsaApPostLogonUser`
- size: `807`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180009afc`
- `0x18000a650`
- `0x18005a3d0`
- `0x18008b70c`
- `0x18008f410`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005a5b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005a5b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005a59d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005a59d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005a5dc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005a5dc`
- `ntdll!RtlEnterCriticalSection` at `0x18005a4ef`
- `ntdll!RtlEnterCriticalSection` at `0x18005a633`
- `ntdll!RtlEnterCriticalSection` at `0x18005a4ef`
- `ntdll!RtlEnterCriticalSection` at `0x18005a633`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a559`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a696`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a559`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a696`

## string_xrefs

- `0x18005a3dd`: `LsaApPostLogonUser: LogonId %#x:%x, LinkedLogonId %#x:%x\n`
- `0x18005a573`: `Found an ongoing DMSA migration, linked DMSA:  %!KERBNAME!\n`
- `0x18005a643`: `LsaApPostLogonUser: linked logon session %#x:%x is OK to clean up credentials, flags %#x\n`

## pseudocode

```c
__int64 __fastcall LsaApPostLogonUser(__int64 a1)
{
  unsigned int v2; // ebp
  int v3; // eax
  int v4; // eax
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  struct _RTL_CRITICAL_SECTION *LogonSession; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  int LockSemaphore; // eax
  DWORD v10; // ebx
  struct _RTL_CRITICAL_SECTION *v11; // rax
  int LockSemaphore_high; // eax
  DWORD Period; // [rsp+28h] [rbp-60h]
  DWORD Perioda; // [rsp+28h] [rbp-60h]
  ULONG Flags; // [rsp+30h] [rbp-58h]
  ULONG Flagsa; // [rsp+30h] [rbp-58h]
  int v17; // [rsp+38h] [rbp-50h]
  __int128 v18; // [rsp+40h] [rbp-48h] BYREF
  __int64 v19; // [rsp+50h] [rbp-38h]

  v19 = 0;
  v17 = *(_DWORD *)(a1 + 12);
  Flags = *(_DWORD *)(a1 + 16);
  v2 = 0;
  Period = *(_DWORD *)(a1 + 4);
  v3 = *(_DWORD *)(a1 + 8);
  v18 = 0;
  KerbTracerT::Log(
    10,
    "LsaApPostLogonUser",
    12506,
    "LsaApPostLogonUser: LogonId %#x:%x, LinkedLogonId %#x:%x\n",
    v3,
    Period,
    Flags,
    v17);
  v4 = *(_DWORD *)(a1 + 4);
  if ( v4 == 999 || v4 == 996 )
  {
    if ( !*(_DWORD *)(a1 + 8) )
      return 0;
LABEL_7:
    if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v18) )
    {
      KerbTracerT::Log(1, "LsaApPostLogonUser", 12525, "LsaApPostLogonUser: GetCallInfo failed: %#x\n", -1073741595);
      return 3221225701LL;
    }
    v6 = 0;
    LogonSession = (struct _RTL_CRITICAL_SECTION *)KerbLocateLogonSession((const struct _LUID *)(a1 + 4), 0);
    v8 = LogonSession;
    if ( !LogonSession )
      goto LABEL_27;
    RtlEnterCriticalSection(LogonSession + 2);
    LockSemaphore = (int)v8[22].LockSemaphore;
    *(PRTL_CRITICAL_SECTION_DEBUG *)((char *)&v8[23].DebugInfo + 4) = *(PRTL_CRITICAL_SECTION_DEBUG *)(a1 + 12);
    *(_QWORD *)&v8[18].LockCount = 0;
    if ( (LockSemaphore & 0x200000) == 0 )
    {
      LODWORD(v8[22].LockSemaphore) = LockSemaphore | 0x400000;
      KerbTracerT::Log(
        10,
        "LsaApPostLogonUser",
        12544,
        "LsaApPostLogonUser: logon session %#x:%x is OK to clean up credentials, flags %#x\n",
        HIDWORD(v8[1].LockSemaphore),
        LODWORD(v8[1].LockSemaphore),
        LockSemaphore | 0x400000);
      KerbCleanupLogonSessionCredentials((struct _KERB_LOGON_SESSION *)v8);
    }
    RtlLeaveCriticalSection(v8 + 2);
    if ( SLOBYTE(v8[13].LockCount) >= 0
      || (KerbTracerT::Log(
            3,
            "LsaApPostLogonUser",
            12556,
            "Found an ongoing DMSA migration, linked DMSA:  %!KERBNAME!\n",
            *(_QWORD *)&v8[19].LockCount),
          AcquireSRWLockShared(&KerbDmsaPolicy::Lock),
          v10 = 3600000 * KerbDmsaPolicy::PermissionWriteTimer,
          ReleaseSRWLockShared(&KerbDmsaPolicy::Lock),
          CreateTimerQueueTimer(
            (PHANDLE)&v8[19].SpinCount,
            0,
            (WAITORTIMERCALLBACK)AddMachineToDmsaPrincipalsAllowedCallback,
            &v8[1].LockSemaphore,
            0,
            v10,
            0)) )
    {
LABEL_27:
      if ( *(_QWORD *)(a1 + 12) )
      {
        v11 = (struct _RTL_CRITICAL_SECTION *)KerbLocateLogonSession((const struct _LUID *)(a1 + 12), 0);
        v6 = v11;
        if ( v11 )
        {
          RtlEnterCriticalSection(v11 + 2);
          LODWORD(v6[22].LockSemaphore) &= ~0x200000u;
          LODWORD(v6[22].LockSemaphore) |= 0x400000u;
          LockSemaphore_high = HIDWORD(v6[1].LockSemaphore);
          Flagsa = (ULONG)v6[22].LockSemaphore;
          Perioda = (DWORD)v6[1].LockSemaphore;
          *(_QWORD *)&v6[18].LockCount = 0;
          KerbTracerT::Log(
            10,
            "LsaApPostLogonUser",
            12586,
            "LsaApPostLogonUser: linked logon session %#x:%x is OK to clean up credentials, flags %#x\n",
            LockSemaphore_high,
            Perioda,
            Flagsa);
          KerbCleanupLogonSessionCredentials((struct _KERB_LOGON_SESSION *)v6);
          RtlLeaveCriticalSection(v6 + 2);
        }
      }
      if ( !v8 )
        goto LABEL_21;
    }
    else
    {
      KerbTracerT::Log(1, "LsaApPostLogonUser", 12566, "Failed to schedule a timer to add permissions for for DMSA\n");
      v2 = -1073741595;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
      KerbFreeLogonSession(v8);
LABEL_21:
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
        KerbFreeLogonSession(v6);
    }
    return v2;
  }
  if ( v4 != 997 || *(_DWORD *)(a1 + 8) )
    goto LABEL_7;
  return v2;
}

```

## disassembly

```asm
0x18005a3d0  push    rbx
0x18005a3d2  push    rbp
0x18005a3d3  push    r13
0x18005a3d5  push    r14
0x18005a3d7  sub     rsp, 68h
0x18005a3db  xor     eax, eax
0x18005a3dd  lea     r9, aLsaappostlogon_2; "LsaApPostLogonUser: LogonId %#x:%x, Lin"...
0x18005a3e4  mov     [rsp+88h+var_38], rax
0x18005a3e9  lea     rdx, aLsaappostlogon_0; "LsaApPostLogonUser"
0x18005a3f0  mov     eax, [rcx+0Ch]
0x18005a3f3  mov     r14, rcx
0x18005a3f6  mov     [rsp+88h+var_50], eax
0x18005a3fa  xorps   xmm0, xmm0
0x18005a3fd  mov     eax, [rcx+10h]
0x18005a400  mov     r8d, 30DAh
0x18005a406  mov     [rsp+88h+Flags], eax
0x18005a40a  xor     ebp, ebp
0x18005a40c  mov     eax, [rcx+4]
0x18005a40f  mov     [rsp+88h+Period], eax
0x18005a413  mov     eax, [rcx+8]
0x18005a416  mov     ecx, 0Ah
0x18005a41b  movups  [rsp+88h+var_48], xmm0
0x18005a420  mov     [rsp+88h+DueTime], eax
0x18005a424  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005a429  mov     eax, [r14+4]
0x18005a42d  cmp     eax, 3E7h
0x18005a432  jnz     short loc_18005A447
0x18005a434  cmp     [r14+8], ebp
0x18005a438  jnz     short loc_18005A45F
0x18005a43a  mov     eax, ebp
0x18005a43c  add     rsp, 68h
0x18005a440  pop     r14
0x18005a442  pop     r13
0x18005a444  pop     rbp
0x18005a445  pop     rbx
0x18005a446  retn
0x18005a447  cmp     eax, 3E4h
0x18005a44c  jz      short loc_18005A434
0x18005a44e  cmp     eax, 3E5h
0x18005a453  jnz     short loc_18005A45F
0x18005a455  cmp     [r14+8], ebp
0x18005a459  jz      loc_18005A6EA
0x18005a45f  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18005a466  lea     rcx, [rsp+88h+var_48]
0x18005a46b  mov     rax, [rax+0C0h]
0x18005a472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a477  test    al, al
0x18005a479  jnz     short loc_18005A4AF
0x18005a47b  mov     ebp, 0C00000E5h
0x18005a480  lea     r9, aLsaappostlogon_1; "LsaApPostLogonUser: GetCallInfo failed:"...
0x18005a487  mov     r8d, 30EDh
0x18005a48d  mov     [rsp+88h+DueTime], ebp
0x18005a491  lea     rdx, aLsaappostlogon_0; "LsaApPostLogonUser"
0x18005a498  mov     ecx, 1
0x18005a49d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005a4a2  mov     eax, ebp
0x18005a4a4  add     rsp, 68h
0x18005a4a8  pop     r14
0x18005a4aa  pop     r13
0x18005a4ac  pop     rbp
0x18005a4ad  pop     rbx
0x18005a4ae  retn
0x18005a4af  mov     [rsp+88h+arg_8], rsi
0x18005a4b7  lea     rcx, [r14+4]; struct _LUID *
0x18005a4bb  mov     [rsp+88h+arg_10], rdi
0x18005a4c3  xor     edx, edx; unsigned __int8
0x18005a4c5  mov     [rsp+88h+arg_18], r12
0x18005a4cd  xor     edi, edi
0x18005a4cf  mov     [rsp+88h+var_28], r15
0x18005a4d4  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x18005a4d9  mov     rsi, rax
0x18005a4dc  mov     r15d, 0FFFFFFFFh
0x18005a4e2  test    rax, rax
0x18005a4e5  jz      loc_18005A60E
0x18005a4eb  lea     rcx, [rax+50h]; CriticalSection
0x18005a4ef  call    cs:__imp_RtlEnterCriticalSection
0x18005a4f5  mov     rcx, [r14+0Ch]
0x18005a4f9  mov     eax, [rsi+388h]
0x18005a4ff  mov     [rsi+39Ch], rcx
0x18005a506  mov     [rsi+2D8h], rdi
0x18005a50d  bt      eax, 15h
0x18005a511  jb      short loc_18005A555
0x18005a513  bts     eax, 16h
0x18005a517  lea     r9, aLsaappostlogon; "LsaApPostLogonUser: logon session %#x:%"...
0x18005a51e  mov     [rsp+88h+Flags], eax
0x18005a522  lea     rdx, aLsaappostlogon_0; "LsaApPostLogonUser"
0x18005a529  mov     [rsi+388h], eax
0x18005a52f  mov     r8d, 3100h
0x18005a535  mov     eax, [rsi+40h]
0x18005a538  mov     ecx, 0Ah
0x18005a53d  mov     [rsp+88h+Period], eax
0x18005a541  mov     eax, [rsi+44h]
0x18005a544  mov     [rsp+88h+DueTime], eax
0x18005a548  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005a54d  mov     rcx, rsi; struct _KERB_LOGON_SESSION *
0x18005a550  call    ?KerbCleanupLogonSessionCredentials@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbCleanupLogonSessionCredentials(_KERB_LOGON_SESSION *)
0x18005a555  lea     rcx, [rsi+50h]; CriticalSection
0x18005a559  call    cs:__imp_RtlLeaveCriticalSection
0x18005a55f  test    byte ptr [rsi+210h], 80h
0x18005a566  jz      loc_18005A60E
0x18005a56c  mov     rax, [rsi+300h]
0x18005a573  lea     r9, aFoundAnOngoing; "Found an ongoing DMSA migration, linked"...
0x18005a57a  mov     r8d, 310Ch
0x18005a580  mov     qword ptr [rsp+88h+DueTime], rax
0x18005a585  lea     rdx, aLsaappostlogon_0; "LsaApPostLogonUser"
0x18005a58c  mov     ecx, 3
0x18005a591  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005a596  lea     rcx, ?Lock@KerbDmsaPolicy@@0Vsrwlock@wil@@A; SRWLock
0x18005a59d  call    cs:__imp_AcquireSRWLockShared
0x18005a5a3  imul    ebx, cs:?PermissionWriteTimer@KerbDmsaPolicy@@0KA, 36EE80h; ulong KerbDmsaPolicy::PermissionWriteTimer
0x18005a5ad  lea     rcx, ?Lock@KerbDmsaPolicy@@0Vsrwlock@wil@@A; SRWLock
0x18005a5b4  call    cs:__imp_ReleaseSRWLockShared
0x18005a5ba  xor     eax, eax
0x18005a5bc  lea     rcx, [rsi+318h]; phNewTimer
0x18005a5c3  mov     [rsp+88h+Flags], eax; Flags
0x18005a5c7  lea     r9, [rsi+40h]; Parameter
0x18005a5cb  mov     [rsp+88h+Period], ebx; Period
0x18005a5cf  lea     r8, ?AddMachineToDmsaPrincipalsAllowedCallback@@YAXPEAXE@Z; Callback
0x18005a5d6  xor     edx, edx; TimerQueue
0x18005a5d8  mov     [rsp+88h+DueTime], eax; DueTime
0x18005a5dc  call    cs:__imp_CreateTimerQueueTimer
0x18005a5e2  test    eax, eax
0x18005a5e4  jnz     short loc_18005A60E
0x18005a5e6  lea     r9, aFailedToSchedu; "Failed to schedule a timer to add permi"...
0x18005a5ed  mov     r8d, 3116h
0x18005a5f3  lea     rdx, aLsaappostlogon_0; "LsaApPostLogonUser"
0x18005a5fa  mov     ecx, 1
0x18005a5ff  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005a604  mov     ebp, 0C00000E5h
0x18005a609  jmp     loc_18005A6A1
0x18005a60e  mov     eax, [r14+10h]
0x18005a612  or      eax, [r14+0Ch]
0x18005a616  jz      loc_18005A69C
0x18005a61c  xor     edx, edx; unsigned __int8
0x18005a61e  lea     rcx, [r14+0Ch]; struct _LUID *
0x18005a622  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x18005a627  mov     rdi, rax
0x18005a62a  test    rax, rax
0x18005a62d  jz      short loc_18005A69C
0x18005a62f  lea     rcx, [rax+50h]; CriticalSection
0x18005a633  call    cs:__imp_RtlEnterCriticalSection
0x18005a639  and     dword ptr [rdi+388h], 0FFDFFFFFh
0x18005a643  lea     r9, aLsaappostlogon_3; "LsaApPostLogonUser: linked logon sessio"...
0x18005a64a  or      dword ptr [rdi+388h], 400000h
0x18005a654  mov     r8d, 312Ah
0x18005a65a  mov     edx, [rdi+388h]
0x18005a660  mov     ecx, 0Ah
0x18005a665  mov     eax, [rdi+44h]
0x18005a668  mov     [rsp+88h+Flags], edx
0x18005a66c  mov     edx, [rdi+40h]
0x18005a66f  mov     [rsp+88h+Period], edx
0x18005a673  lea     rdx, aLsaappostlogon_0; "LsaApPostLogonUser"
0x18005a67a  mov     [rdi+2D8h], rbp
0x18005a681  mov     [rsp+88h+DueTime], eax
0x18005a685  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005a68a  mov     rcx, rdi; struct _KERB_LOGON_SESSION *
0x18005a68d  call    ?KerbCleanupLogonSessionCredentials@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbCleanupLogonSessionCredentials(_KERB_LOGON_SESSION *)
0x18005a692  lea     rcx, [rdi+50h]; CriticalSection
0x18005a696  call    cs:__imp_RtlLeaveCriticalSection
0x18005a69c  test    rsi, rsi
0x18005a69f  jz      short loc_18005A6B5
0x18005a6a1  mov     eax, r15d
0x18005a6a4  lock xadd [rsi], eax
0x18005a6a8  cmp     eax, 1
0x18005a6ab  jnz     short loc_18005A6B5
0x18005a6ad  mov     rcx, rsi; hMem
0x18005a6b0  call    ?KerbFreeLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbFreeLogonSession(_KERB_LOGON_SESSION *)
0x18005a6b5  mov     r12, [rsp+88h+arg_18]
0x18005a6bd  mov     rsi, [rsp+88h+arg_8]
0x18005a6c5  test    rdi, rdi
0x18005a6c8  jz      short loc_18005A6DD
0x18005a6ca  lock xadd [rdi], r15d
0x18005a6cf  cmp     r15d, 1
0x18005a6d3  jnz     short loc_18005A6DD
0x18005a6d5  mov     rcx, rdi; hMem
0x18005a6d8  call    ?KerbFreeLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbFreeLogonSession(_KERB_LOGON_SESSION *)
0x18005a6dd  mov     rdi, [rsp+88h+arg_10]
0x18005a6e5  mov     r15, [rsp+88h+var_28]
0x18005a6ea  mov     eax, ebp
0x18005a6ec  add     rsp, 68h
0x18005a6f0  pop     r14
0x18005a6f2  pop     r13
0x18005a6f4  pop     rbp
0x18005a6f5  pop     rbx
0x18005a6f6  retn
```

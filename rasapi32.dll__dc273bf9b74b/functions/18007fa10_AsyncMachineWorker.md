# AsyncMachineWorker

- ea: `0x18007fa10`
- end: `0x18007fd46`
- name: `AsyncMachineWorker`
- size: `822`
- prototype: `void __fastcall __noreturn(char *Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003ea48`
- `0x18004e580`
- `0x18004e984`
- `0x18007fa10`
- `0x18007fd4c`
- `0x18007fe30`
- `0x18007fedc`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007fd27`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007fd27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fc1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fc29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fc90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fc9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fd1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fd30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fc1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fc29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fc90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fc9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fd1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fd30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fbc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fbcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fbd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fc7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fcd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fce6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fbc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fbcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fbd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fc7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fcd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fce6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18007fb1b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18007fb1b`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007fa9b`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007fa9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007faa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fb25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007faa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fb25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007fcf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007fcf8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18007fd3f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18007fd3f`

## pseudocode

```c
void __fastcall __noreturn AsyncMachineWorker(char *Parameter)
{
  int v2; // edi
  DWORD LastError; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  __int64 v7; // r9
  int v8; // [rsp+60h] [rbp+40h] BYREF
  __int64 v9; // [rsp+68h] [rbp+48h] BYREF
  void *DuplicateTokenHandle; // [rsp+70h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a844d46fc5703f471860e34880cece0e_Traceguids);
  }
  v2 = 0;
  v9 = 0;
  v8 = 0;
  DuplicateTokenHandle = 0;
  if ( (unsigned __int64)(Parameter - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( DuplicateToken(Parameter, SecurityImpersonation, &DuplicateTokenHandle) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_a844d46fc5703f471860e34880cece0e_Traceguids);
      }
      if ( ImpersonateLoggedOnUser(DuplicateTokenHandle) )
        goto LABEL_23;
      LastError = GetLastError();
      if ( LastError )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_49;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v5 = 21;
          goto LABEL_12;
        }
      }
      else
      {
LABEL_43:
        v4 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_43;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_49;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 19;
LABEL_12:
        WPP_SF_d(v4[2], v5, WPP_a844d46fc5703f471860e34880cece0e_Traceguids, LastError);
        goto LABEL_43;
      }
    }
LABEL_44:
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x800) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      WPP_SF_(v4[2], 25, WPP_a844d46fc5703f471860e34880cece0e_Traceguids);
    if ( v2 )
    {
LABEL_50:
      CleanupAsyncWorkItems();
      CloseHandle(hAsyncThread);
      hAsyncThread = 0;
      CleanUpContextQueue();
      CleanUpDMEvent();
      LeaveCriticalSection(&csAsyncLock);
      SetEvent(HEventNotHangingUp);
      LeaveCriticalSection(&csStopLock);
      FreeLibraryAndExitThread(g_hModule, 0);
    }
LABEL_49:
    EnterCriticalSection(&csStopLock);
    EnterCriticalSection(&csAsyncLock);
    goto LABEL_50;
  }
  while ( 1 )
  {
LABEL_23:
    while ( 1 )
    {
      v8 = 0;
      v6 = WaitForDialMachineEvent(&v9, &v8);
      if ( !v6 )
        break;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_a844d46fc5703f471860e34880cece0e_Traceguids, v6);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v8 != 5 )
        goto LABEL_44;
      EnterCriticalSection(&csStopLock);
      EnterCriticalSection(&csAsyncLock);
      EnterCriticalSection(&RasconncbListLock);
      v7 = *((unsigned int *)PdtllistRasconncb + 4);
      if ( !(_DWORD)v7 )
      {
        LeaveCriticalSection(&RasconncbListLock);
        v2 = 1;
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_a844d46fc5703f471860e34880cece0e_Traceguids, v7);
      }
      LeaveCriticalSection(&RasconncbListLock);
      LeaveCriticalSection(&csAsyncLock);
LABEL_41:
      LeaveCriticalSection(&csStopLock);
    }
    if ( (*(unsigned int (__fastcall **)(__int64, bool))(v9 + 16))(v9, v8 == 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_a844d46fc5703f471860e34880cece0e_Traceguids);
      }
      EnterCriticalSection(&csStopLock);
      (*(void (**)(void))(v9 + 24))();
      goto LABEL_41;
    }
  }
}

```

## disassembly

```asm
0x18007fa10  push    rbp
0x18007fa12  push    rbx
0x18007fa13  push    rdi
0x18007fa14  push    r12
0x18007fa16  push    r13
0x18007fa18  push    r14
0x18007fa1a  push    r15
0x18007fa1c  mov     rbp, rsp
0x18007fa1f  sub     rsp, 20h
0x18007fa23  mov     rbx, rcx
0x18007fa26  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fa2d  lea     r15, WPP_GLOBAL_Control
0x18007fa34  lea     r12, WPP_a844d46fc5703f471860e34880cece0e_Traceguids
0x18007fa3b  mov     r14d, 800h
0x18007fa41  cmp     rcx, r15
0x18007fa44  jz      short loc_18007FA63
0x18007fa46  test    [rcx+1Ch], r14d
0x18007fa4a  jz      short loc_18007FA63
0x18007fa4c  cmp     byte ptr [rcx+19h], 6
0x18007fa50  jb      short loc_18007FA63
0x18007fa52  mov     rcx, [rcx+10h]
0x18007fa56  mov     edx, 12h
0x18007fa5b  mov     r8, r12
0x18007fa5e  call    WPP_SF_
0x18007fa63  xor     edi, edi
0x18007fa65  mov     [rbp+arg_8], 0
0x18007fa6d  lea     rax, [rbx-1]
0x18007fa71  mov     [rbp+arg_0], 0
0x18007fa78  mov     [rbp+DuplicateTokenHandle], 0
0x18007fa80  lea     r13, csStopLock
0x18007fa87  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007fa8b  ja      loc_18007FB61
0x18007fa91  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18007fa95  mov     rcx, rbx; ExistingTokenHandle
0x18007fa98  lea     edx, [rdi+2]; ImpersonationLevel
0x18007fa9b  call    cs:__imp_DuplicateToken
0x18007faa1  test    eax, eax
0x18007faa3  jnz     short loc_18007FAEE
0x18007faa5  call    cs:__imp_GetLastError
0x18007faab  test    eax, eax
0x18007faad  jz      loc_18007FCA9
0x18007fab3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007faba  cmp     rcx, r15
0x18007fabd  jz      loc_18007FCD6
0x18007fac3  test    [rcx+1Ch], r14d
0x18007fac7  jz      loc_18007FCB0
0x18007facd  cmp     byte ptr [rcx+19h], 2
0x18007fad1  jb      loc_18007FCB0
0x18007fad7  lea     edx, [rdi+13h]
0x18007fada  mov     rcx, [rcx+10h]
0x18007fade  mov     r9d, eax
0x18007fae1  mov     r8, r12
0x18007fae4  call    WPP_SF_d
0x18007fae9  jmp     loc_18007FCA9
0x18007faee  mov     rcx, cs:WPP_GLOBAL_Control
0x18007faf5  cmp     rcx, r15
0x18007faf8  jz      short loc_18007FB17
0x18007fafa  test    [rcx+1Ch], r14d
0x18007fafe  jz      short loc_18007FB17
0x18007fb00  cmp     byte ptr [rcx+19h], 5
0x18007fb04  jb      short loc_18007FB17
0x18007fb06  mov     rcx, [rcx+10h]
0x18007fb0a  mov     edx, 14h
0x18007fb0f  mov     r8, r12
0x18007fb12  call    WPP_SF_
0x18007fb17  mov     rcx, [rbp+DuplicateTokenHandle]; hToken
0x18007fb1b  call    cs:__imp_ImpersonateLoggedOnUser
0x18007fb21  test    eax, eax
0x18007fb23  jnz     short loc_18007FB61
0x18007fb25  call    cs:__imp_GetLastError
0x18007fb2b  test    eax, eax
0x18007fb2d  jz      loc_18007FCA9
0x18007fb33  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fb3a  cmp     rcx, r15
0x18007fb3d  jz      loc_18007FCD6
0x18007fb43  test    [rcx+1Ch], r14d
0x18007fb47  jz      loc_18007FCB0
0x18007fb4d  cmp     byte ptr [rcx+19h], 2
0x18007fb51  jb      loc_18007FCB0
0x18007fb57  mov     edx, 15h
0x18007fb5c  jmp     loc_18007FADA
0x18007fb61  lea     rbx, RasconncbListLock
0x18007fb68  lea     rdx, [rbp+arg_0]
0x18007fb6c  mov     [rbp+arg_0], edi
0x18007fb6f  lea     rcx, [rbp+arg_8]
0x18007fb73  call    WaitForDialMachineEvent
0x18007fb78  test    eax, eax
0x18007fb7a  jz      loc_18007FC31
0x18007fb80  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fb87  cmp     rcx, r15
0x18007fb8a  jz      short loc_18007FBB3
0x18007fb8c  test    [rcx+1Ch], r14d
0x18007fb90  jz      short loc_18007FBB3
0x18007fb92  cmp     byte ptr [rcx+19h], 2
0x18007fb96  jb      short loc_18007FBB3
0x18007fb98  mov     rcx, [rcx+10h]
0x18007fb9c  mov     edx, 16h
0x18007fba1  mov     r9d, eax
0x18007fba4  mov     r8, r12
0x18007fba7  call    WPP_SF_d
0x18007fbac  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fbb3  cmp     [rbp+arg_0], 5
0x18007fbb7  jnz     loc_18007FCB0
0x18007fbbd  mov     rcx, r13; lpCriticalSection
0x18007fbc0  call    cs:__imp_EnterCriticalSection
0x18007fbc6  lea     rcx, csAsyncLock; lpCriticalSection
0x18007fbcd  call    cs:__imp_EnterCriticalSection
0x18007fbd3  mov     rcx, rbx; lpCriticalSection
0x18007fbd6  call    cs:__imp_EnterCriticalSection
0x18007fbdc  mov     rax, cs:PdtllistRasconncb
0x18007fbe3  mov     r9d, [rax+10h]
0x18007fbe7  test    r9d, r9d
0x18007fbea  jz      loc_18007FC9B
0x18007fbf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fbf7  cmp     rcx, r15
0x18007fbfa  jz      short loc_18007FC19
0x18007fbfc  test    [rcx+1Ch], r14d
0x18007fc00  jz      short loc_18007FC19
0x18007fc02  cmp     byte ptr [rcx+19h], 5
0x18007fc06  jb      short loc_18007FC19
0x18007fc08  mov     rcx, [rcx+10h]
0x18007fc0c  mov     edx, 17h
0x18007fc11  mov     r8, r12
0x18007fc14  call    WPP_SF_d
0x18007fc19  mov     rcx, rbx; lpCriticalSection
0x18007fc1c  call    cs:__imp_LeaveCriticalSection
0x18007fc22  lea     rcx, csAsyncLock; lpCriticalSection
0x18007fc29  call    cs:__imp_LeaveCriticalSection
0x18007fc2f  jmp     short loc_18007FC8D
0x18007fc31  mov     rcx, [rbp+arg_8]
0x18007fc35  xor     edx, edx
0x18007fc37  cmp     [rbp+arg_0], edx
0x18007fc3a  setz    dl
0x18007fc3d  mov     rax, [rcx+10h]
0x18007fc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc46  test    eax, eax
0x18007fc48  jz      loc_18007FB68
0x18007fc4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fc55  cmp     rcx, r15
0x18007fc58  jz      short loc_18007FC77
0x18007fc5a  test    [rcx+1Ch], r14d
0x18007fc5e  jz      short loc_18007FC77
0x18007fc60  cmp     byte ptr [rcx+19h], 5
0x18007fc64  jb      short loc_18007FC77
0x18007fc66  mov     rcx, [rcx+10h]
0x18007fc6a  mov     edx, 18h
0x18007fc6f  mov     r8, r12
0x18007fc72  call    WPP_SF_
0x18007fc77  mov     rcx, r13; lpCriticalSection
0x18007fc7a  call    cs:__imp_EnterCriticalSection
0x18007fc80  mov     rcx, [rbp+arg_8]
0x18007fc84  mov     rax, [rcx+18h]
0x18007fc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc8d  mov     rcx, r13; lpCriticalSection
0x18007fc90  call    cs:__imp_LeaveCriticalSection
0x18007fc96  jmp     loc_18007FB68
0x18007fc9b  mov     rcx, rbx; lpCriticalSection
0x18007fc9e  call    cs:__imp_LeaveCriticalSection
0x18007fca4  mov     edi, 1
0x18007fca9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fcb0  cmp     rcx, r15
0x18007fcb3  jz      short loc_18007FCD2
0x18007fcb5  test    [rcx+1Ch], r14d
0x18007fcb9  jz      short loc_18007FCD2
0x18007fcbb  cmp     byte ptr [rcx+19h], 5
0x18007fcbf  jb      short loc_18007FCD2
0x18007fcc1  mov     rcx, [rcx+10h]
0x18007fcc5  mov     edx, 19h
0x18007fcca  mov     r8, r12
0x18007fccd  call    WPP_SF_
0x18007fcd2  test    edi, edi
0x18007fcd4  jnz     short loc_18007FCEC
0x18007fcd6  mov     rcx, r13; lpCriticalSection
0x18007fcd9  call    cs:__imp_EnterCriticalSection
0x18007fcdf  lea     rcx, csAsyncLock; lpCriticalSection
0x18007fce6  call    cs:__imp_EnterCriticalSection
0x18007fcec  call    CleanupAsyncWorkItems
0x18007fcf1  mov     rcx, cs:hAsyncThread; hObject
0x18007fcf8  call    cs:__imp_CloseHandle
0x18007fcfe  mov     cs:hAsyncThread, 0
0x18007fd09  call    CleanUpContextQueue
0x18007fd0e  call    CleanUpDMEvent
0x18007fd13  lea     rcx, csAsyncLock; lpCriticalSection
0x18007fd1a  call    cs:__imp_LeaveCriticalSection
0x18007fd20  mov     rcx, cs:HEventNotHangingUp; hEvent
0x18007fd27  call    cs:__imp_SetEvent
0x18007fd2d  mov     rcx, r13; lpCriticalSection
0x18007fd30  call    cs:__imp_LeaveCriticalSection
0x18007fd36  mov     rcx, cs:g_hModule; hLibModule
0x18007fd3d  xor     edx, edx; dwExitCode
0x18007fd3f  call    cs:__imp_FreeLibraryAndExitThread
```

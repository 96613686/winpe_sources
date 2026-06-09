# PopSwitchUpdateUserShutdownScenarioState

- ea: `0x14078f364`
- end: `0x14078f4c2`
- name: `PopSwitchUpdateUserShutdownScenarioState`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140732ea0`
- `0x140adf630`

## callees

- `0x140433300`
- `0x1404333a0`
- `0x1404681d4`
- `0x1404682ac`
- `0x140498150`
- `0x1406e8590`
- `0x14078f364`
- `0x140aae530`
- `0x140ba3b70`
- `0x140ba3bb4`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14078f411`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14078f471`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14078f411`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x14078f471`

## pseudocode

```c
__int64 __fastcall PopSwitchUpdateUserShutdownScenarioState(int a1)
{
  int v2; // edi
  char v3; // bl
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8

  PopAcquirePolicyLock();
  if ( PopUserShutdownScenarioTargetState != a1 )
  {
    PopUserShutdownScenarioTargetState = a1;
    PopUserShutdownScenarioUserInitiated = 1;
    if ( (PopUserShutdownScenarioCurrentState & 0xFFFFFFFD) != 0 && PopUserShutdownScenarioCurrentState != a1 )
    {
      do
      {
        v2 = a1;
        v3 = PopUserShutdownScenarioUserInitiated;
        PopUserShutdownScenarioCurrentState = v2 - 1;
        PopReleasePolicyLock();
        if ( v2 == 1 )
        {
          PopQueueWorkItem(&PopClearUserShutdownMarkerWorkItem, 1);
          *(_DWORD *)&stru_140E4D568.SavedApcStateFill[36] = 0;
          if ( *(_QWORD *)&stru_140E4D568.ReservedPreviousReadyTimeValue )
          {
            LOBYTE(v8) = v3;
            guard_dispatch_icall_no_overrides(v8, v7, v9);
          }
          if ( PopUserShutdownTaskClient )
          {
            PdcTaskClientRequest(PopUserShutdownTaskClient, 0);
            if ( PopUserShutdownWinlogonBlockerHandle )
              SleepstudyHelperBlockerActiveDereference(PopUserShutdownWinlogonBlockerHandle);
          }
          PpmEndHighPerfRequest(3);
        }
        else if ( v2 == 3 )
        {
          PopTransitionCheckpoint(7);
          PopQueueWorkItem(&PopSetUserShutdownMarkerWorkItem, 1);
          *(_DWORD *)&stru_140E4D568.SavedApcStateFill[36] = 1;
          if ( stru_140E4D568.AbWaitObject )
            guard_dispatch_icall_no_overrides(v5, v4, v6);
          if ( PopUserShutdownTaskClient )
          {
            LOBYTE(v4) = 1;
            PdcTaskClientRequest(PopUserShutdownTaskClient, v4);
            if ( PopUserShutdownWinlogonBlockerHandle )
              SleepstudyHelperBlockerActiveReference(PopUserShutdownWinlogonBlockerHandle);
          }
          PpmBeginHighPerfRequest();
        }
        PopAcquirePolicyLock();
        a1 = PopUserShutdownScenarioTargetState;
        PopUserShutdownScenarioCurrentState = v2;
      }
      while ( v2 != PopUserShutdownScenarioTargetState );
    }
  }
  return PopReleasePolicyLock();
}

```

## disassembly

```asm
0x14078f364  mov     [rsp+arg_0], rbx
0x14078f369  push    rdi
0x14078f36a  sub     rsp, 20h
0x14078f36e  mov     ebx, ecx
0x14078f370  call    PopAcquirePolicyLock
0x14078f375  cmp     cs:PopUserShutdownScenarioTargetState, ebx
0x14078f37b  jz      loc_14078F4B1
0x14078f381  mov     eax, cs:PopUserShutdownScenarioCurrentState
0x14078f387  mov     cs:PopUserShutdownScenarioTargetState, ebx
0x14078f38d  mov     cs:PopUserShutdownScenarioUserInitiated, 1
0x14078f394  test    eax, 0FFFFFFFDh
0x14078f399  jz      loc_14078F4B1
0x14078f39f  cmp     eax, ebx
0x14078f3a1  jz      loc_14078F4B1
0x14078f3a7  mov     edi, ebx
0x14078f3a9  mov     bl, cs:PopUserShutdownScenarioUserInitiated
0x14078f3af  lea     eax, [rdi-1]
0x14078f3b2  mov     cs:PopUserShutdownScenarioCurrentState, eax
0x14078f3b8  call    PopReleasePolicyLock
0x14078f3bd  mov     ecx, edi
0x14078f3bf  sub     ecx, 1
0x14078f3c2  jz      short loc_14078F435
0x14078f3c4  cmp     ecx, 2
0x14078f3c7  jnz     loc_14078F498
0x14078f3cd  xor     edx, edx
0x14078f3cf  lea     ecx, [rdx+7]
0x14078f3d2  call    PopTransitionCheckpoint
0x14078f3d7  mov     edx, 1
0x14078f3dc  lea     rcx, PopSetUserShutdownMarkerWorkItem
0x14078f3e3  call    PopQueueWorkItem
0x14078f3e8  mov     rax, cs:stru_140E4D568.AbWaitObject
0x14078f3ef  mov     dword ptr cs:stru_140E4D568.___u57+24h, 1
0x14078f3f9  test    rax, rax
0x14078f3fc  jz      short loc_14078F403
0x14078f3fe  call    _guard_dispatch_icall_no_overrides
0x14078f403  mov     rcx, cs:PopUserShutdownTaskClient
0x14078f40a  test    rcx, rcx
0x14078f40d  jz      short loc_14078F42E
0x14078f40f  mov     dl, 1
0x14078f411  call    cs:__imp_PdcTaskClientRequest
0x14078f418  nop     dword ptr [rax+rax+00h]
0x14078f41d  mov     rcx, cs:PopUserShutdownWinlogonBlockerHandle; SpinLock
0x14078f424  test    rcx, rcx
0x14078f427  jz      short loc_14078F42E
0x14078f429  call    SleepstudyHelperBlockerActiveReference
0x14078f42e  call    PpmBeginHighPerfRequest
0x14078f433  jmp     short loc_14078F498
0x14078f435  mov     edx, 1
0x14078f43a  lea     rcx, PopClearUserShutdownMarkerWorkItem
0x14078f441  call    PopQueueWorkItem
0x14078f446  mov     rax, qword ptr cs:stru_140E4D568.ReservedPreviousReadyTimeValue
0x14078f44d  mov     dword ptr cs:stru_140E4D568.___u57+24h, 0
0x14078f457  test    rax, rax
0x14078f45a  jz      short loc_14078F463
0x14078f45c  mov     cl, bl
0x14078f45e  call    _guard_dispatch_icall_no_overrides
0x14078f463  mov     rcx, cs:PopUserShutdownTaskClient
0x14078f46a  test    rcx, rcx
0x14078f46d  jz      short loc_14078F48E
0x14078f46f  xor     edx, edx
0x14078f471  call    cs:__imp_PdcTaskClientRequest
0x14078f478  nop     dword ptr [rax+rax+00h]
0x14078f47d  mov     rcx, cs:PopUserShutdownWinlogonBlockerHandle; SpinLock
0x14078f484  test    rcx, rcx
0x14078f487  jz      short loc_14078F48E
0x14078f489  call    SleepstudyHelperBlockerActiveDereference
0x14078f48e  mov     ecx, 3
0x14078f493  call    PpmEndHighPerfRequest
0x14078f498  call    PopAcquirePolicyLock
0x14078f49d  mov     ebx, cs:PopUserShutdownScenarioTargetState
0x14078f4a3  mov     cs:PopUserShutdownScenarioCurrentState, edi
0x14078f4a9  cmp     edi, ebx
0x14078f4ab  jnz     loc_14078F3A7
0x14078f4b1  call    PopReleasePolicyLock
0x14078f4b6  mov     rbx, [rsp+28h+arg_0]
0x14078f4bb  add     rsp, 20h
0x14078f4bf  pop     rdi
0x14078f4c0  retn
```

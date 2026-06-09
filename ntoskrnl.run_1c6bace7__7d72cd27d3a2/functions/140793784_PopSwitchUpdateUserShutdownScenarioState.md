# PopSwitchUpdateUserShutdownScenarioState

- ea: `0x140793784`
- end: `0x1407938e2`
- name: `PopSwitchUpdateUserShutdownScenarioState`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140737660`
- `0x140ae5300`

## callees

- `0x140446890`
- `0x140446930`
- `0x140477040`
- `0x140477118`
- `0x1404a5ee0`
- `0x1406eb0e0`
- `0x140793784`
- `0x140ab4140`
- `0x140ba6ae0`
- `0x140ba6b24`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x140793831`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x140793891`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x140793831`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRequest` at `0x140793891`

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
          PopQueueWorkItem(PopClearUserShutdownMarkerWorkItem, 1);
          PopBsdShutdownInProgress = 0;
          if ( (_QWORD)xmmword_140E4D8D0 )
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
          PopQueueWorkItem(PopSetUserShutdownMarkerWorkItem, 1);
          PopBsdShutdownInProgress = 1;
          if ( *((_QWORD *)&PoPdcCallbacks + 1) )
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
0x140793784  mov     [rsp+arg_0], rbx
0x140793789  push    rdi
0x14079378a  sub     rsp, 20h
0x14079378e  mov     ebx, ecx
0x140793790  call    PopAcquirePolicyLock
0x140793795  cmp     cs:PopUserShutdownScenarioTargetState, ebx
0x14079379b  jz      loc_1407938D1
0x1407937a1  mov     eax, cs:PopUserShutdownScenarioCurrentState
0x1407937a7  mov     cs:PopUserShutdownScenarioTargetState, ebx
0x1407937ad  mov     cs:PopUserShutdownScenarioUserInitiated, 1
0x1407937b4  test    eax, 0FFFFFFFDh
0x1407937b9  jz      loc_1407938D1
0x1407937bf  cmp     eax, ebx
0x1407937c1  jz      loc_1407938D1
0x1407937c7  mov     edi, ebx
0x1407937c9  mov     bl, cs:PopUserShutdownScenarioUserInitiated
0x1407937cf  lea     eax, [rdi-1]
0x1407937d2  mov     cs:PopUserShutdownScenarioCurrentState, eax
0x1407937d8  call    PopReleasePolicyLock
0x1407937dd  mov     ecx, edi
0x1407937df  sub     ecx, 1
0x1407937e2  jz      short loc_140793855
0x1407937e4  cmp     ecx, 2
0x1407937e7  jnz     loc_1407938B8
0x1407937ed  xor     edx, edx
0x1407937ef  lea     ecx, [rdx+7]
0x1407937f2  call    PopTransitionCheckpoint
0x1407937f7  mov     edx, 1
0x1407937fc  lea     rcx, PopSetUserShutdownMarkerWorkItem
0x140793803  call    PopQueueWorkItem
0x140793808  mov     rax, qword ptr cs:PoPdcCallbacks+8
0x14079380f  mov     cs:PopBsdShutdownInProgress, 1
0x140793819  test    rax, rax
0x14079381c  jz      short loc_140793823
0x14079381e  call    _guard_dispatch_icall_no_overrides
0x140793823  mov     rcx, cs:PopUserShutdownTaskClient
0x14079382a  test    rcx, rcx
0x14079382d  jz      short loc_14079384E
0x14079382f  mov     dl, 1
0x140793831  call    cs:__imp_PdcTaskClientRequest
0x140793838  nop     dword ptr [rax+rax+00h]
0x14079383d  mov     rcx, cs:PopUserShutdownWinlogonBlockerHandle; SpinLock
0x140793844  test    rcx, rcx
0x140793847  jz      short loc_14079384E
0x140793849  call    SleepstudyHelperBlockerActiveReference
0x14079384e  call    PpmBeginHighPerfRequest
0x140793853  jmp     short loc_1407938B8
0x140793855  mov     edx, 1
0x14079385a  lea     rcx, PopClearUserShutdownMarkerWorkItem
0x140793861  call    PopQueueWorkItem
0x140793866  mov     rax, qword ptr cs:xmmword_140E4D8D0
0x14079386d  mov     cs:PopBsdShutdownInProgress, 0
0x140793877  test    rax, rax
0x14079387a  jz      short loc_140793883
0x14079387c  mov     cl, bl
0x14079387e  call    _guard_dispatch_icall_no_overrides
0x140793883  mov     rcx, cs:PopUserShutdownTaskClient
0x14079388a  test    rcx, rcx
0x14079388d  jz      short loc_1407938AE
0x14079388f  xor     edx, edx
0x140793891  call    cs:__imp_PdcTaskClientRequest
0x140793898  nop     dword ptr [rax+rax+00h]
0x14079389d  mov     rcx, cs:PopUserShutdownWinlogonBlockerHandle; SpinLock
0x1407938a4  test    rcx, rcx
0x1407938a7  jz      short loc_1407938AE
0x1407938a9  call    SleepstudyHelperBlockerActiveDereference
0x1407938ae  mov     ecx, 3
0x1407938b3  call    PpmEndHighPerfRequest
0x1407938b8  call    PopAcquirePolicyLock
0x1407938bd  mov     ebx, cs:PopUserShutdownScenarioTargetState
0x1407938c3  mov     cs:PopUserShutdownScenarioCurrentState, edi
0x1407938c9  cmp     edi, ebx
0x1407938cb  jnz     loc_1407937C7
0x1407938d1  call    PopReleasePolicyLock
0x1407938d6  mov     rbx, [rsp+28h+arg_0]
0x1407938db  add     rsp, 20h
0x1407938df  pop     rdi
0x1407938e0  retn
```

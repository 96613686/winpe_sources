# FwEdpMonShutdown

- ea: `0x1800b343c`
- end: `0x1800b35d7`
- name: `FwEdpMonShutdown`
- size: `411`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058e04`
- `0x1800bf5b0`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x18006a8a8`
- `0x1800b343c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800b3488`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800b34e5`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800b3530`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800b3488`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800b34e5`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800b3530`
- `ntdll!RtlNtStatusToDosError` at `0x1800b3496`
- `ntdll!RtlNtStatusToDosError` at `0x1800b34f3`
- `ntdll!RtlNtStatusToDosError` at `0x1800b353e`
- `ntdll!RtlNtStatusToDosError` at `0x1800b3496`
- `ntdll!RtlNtStatusToDosError` at `0x1800b34f3`
- `ntdll!RtlNtStatusToDosError` at `0x1800b353e`
- `fwbase!FwCriticalSectionDestroy` at `0x1800b3592`
- `fwbase!FwCriticalSectionDestroy` at `0x1800b3592`

## pseudocode

```c
ULONG FwEdpMonShutdown()
{
  NTSTATUS v0; // eax
  ULONG result; // eax
  __int64 v2; // rcx
  __int64 v3; // rdx
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_8df00e504a1239db98983c5e6d66f62b_Traceguids);
  FwCancelLock();
  if ( qword_180132888 )
  {
    v0 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    result = RtlNtStatusToDosError(v0);
    if ( result )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return result;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_22;
      v3 = 17;
      goto LABEL_9;
    }
  }
  if ( qword_180132880 )
  {
    v4 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    result = RtlNtStatusToDosError(v4);
    if ( result )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return result;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_22;
      v3 = 18;
      goto LABEL_9;
    }
  }
  if ( !qword_180132878
    || (v5 = RtlUnsubscribeWnfNotificationWaitForCompletion(), (result = RtlNtStatusToDosError(v5)) == 0) )
  {
    qword_180132888 = 0;
    qword_180132880 = 0;
    qword_180132878 = 0;
    result = FwCriticalSectionDestroy(qword_180132890);
    dword_180132868 = 0;
    goto LABEL_21;
  }
  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return result;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v3 = 19;
LABEL_9:
    result = WPP_SF_d(*(_QWORD *)(v2 + 16), v3, WPP_8df00e504a1239db98983c5e6d66f62b_Traceguids, result);
LABEL_21:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_22:
  if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 8) != 0 )
    return WPP_SF_(*(_QWORD *)(v2 + 16), 20, WPP_8df00e504a1239db98983c5e6d66f62b_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800b343c  mov     [rsp+arg_0], rsi
0x1800b3441  push    rdi
0x1800b3442  sub     rsp, 20h
0x1800b3446  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b344d  lea     rdi, WPP_GLOBAL_Control
0x1800b3454  lea     rsi, WPP_8df00e504a1239db98983c5e6d66f62b_Traceguids
0x1800b345b  cmp     rcx, rdi
0x1800b345e  jz      short loc_1800B3477
0x1800b3460  test    byte ptr [rcx+1Ch], 8
0x1800b3464  jz      short loc_1800B3477
0x1800b3466  mov     rcx, [rcx+10h]
0x1800b346a  mov     edx, 10h
0x1800b346f  mov     r8, rsi
0x1800b3472  call    WPP_SF_
0x1800b3477  call    FwCancelLock
0x1800b347c  mov     rcx, cs:qword_180132888
0x1800b3483  test    rcx, rcx
0x1800b3486  jz      short loc_1800B34D9
0x1800b3488  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800b348f  nop     dword ptr [rax+rax+00h]
0x1800b3494  mov     ecx, eax; Status
0x1800b3496  call    cs:__imp_RtlNtStatusToDosError
0x1800b349d  nop     dword ptr [rax+rax+00h]
0x1800b34a2  test    eax, eax
0x1800b34a4  jz      short loc_1800B34D9
0x1800b34a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b34ad  cmp     rcx, rdi
0x1800b34b0  jz      loc_1800B35CB
0x1800b34b6  test    byte ptr [rcx+1Ch], 1
0x1800b34ba  jz      loc_1800B35AF
0x1800b34c0  mov     edx, 11h
0x1800b34c5  mov     rcx, [rcx+10h]
0x1800b34c9  mov     r9d, eax
0x1800b34cc  mov     r8, rsi
0x1800b34cf  call    WPP_SF_d
0x1800b34d4  jmp     loc_1800B35A8
0x1800b34d9  mov     rcx, cs:qword_180132880
0x1800b34e0  test    rcx, rcx
0x1800b34e3  jz      short loc_1800B3524
0x1800b34e5  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800b34ec  nop     dword ptr [rax+rax+00h]
0x1800b34f1  mov     ecx, eax; Status
0x1800b34f3  call    cs:__imp_RtlNtStatusToDosError
0x1800b34fa  nop     dword ptr [rax+rax+00h]
0x1800b34ff  test    eax, eax
0x1800b3501  jz      short loc_1800B3524
0x1800b3503  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b350a  cmp     rcx, rdi
0x1800b350d  jz      loc_1800B35CB
0x1800b3513  test    byte ptr [rcx+1Ch], 1
0x1800b3517  jz      loc_1800B35AF
0x1800b351d  mov     edx, 12h
0x1800b3522  jmp     short loc_1800B34C5
0x1800b3524  mov     rcx, cs:qword_180132878
0x1800b352b  test    rcx, rcx
0x1800b352e  jz      short loc_1800B356A
0x1800b3530  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800b3537  nop     dword ptr [rax+rax+00h]
0x1800b353c  mov     ecx, eax; Status
0x1800b353e  call    cs:__imp_RtlNtStatusToDosError
0x1800b3545  nop     dword ptr [rax+rax+00h]
0x1800b354a  test    eax, eax
0x1800b354c  jz      short loc_1800B356A
0x1800b354e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3555  cmp     rcx, rdi
0x1800b3558  jz      short loc_1800B35CB
0x1800b355a  test    byte ptr [rcx+1Ch], 1
0x1800b355e  jz      short loc_1800B35AF
0x1800b3560  mov     edx, 13h
0x1800b3565  jmp     loc_1800B34C5
0x1800b356a  lea     rcx, qword_180132890
0x1800b3571  mov     cs:qword_180132888, 0
0x1800b357c  mov     cs:qword_180132880, 0
0x1800b3587  mov     cs:qword_180132878, 0
0x1800b3592  call    cs:__imp_FwCriticalSectionDestroy
0x1800b3599  nop     dword ptr [rax+rax+00h]
0x1800b359e  mov     cs:dword_180132868, 0
0x1800b35a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b35af  cmp     rcx, rdi
0x1800b35b2  jz      short loc_1800B35CB
0x1800b35b4  test    byte ptr [rcx+1Ch], 8
0x1800b35b8  jz      short loc_1800B35CB
0x1800b35ba  mov     rcx, [rcx+10h]
0x1800b35be  mov     edx, 14h
0x1800b35c3  mov     r8, rsi
0x1800b35c6  call    WPP_SF_
0x1800b35cb  mov     rsi, [rsp+28h+arg_0]
0x1800b35d0  add     rsp, 20h
0x1800b35d4  pop     rdi
0x1800b35d5  retn
```

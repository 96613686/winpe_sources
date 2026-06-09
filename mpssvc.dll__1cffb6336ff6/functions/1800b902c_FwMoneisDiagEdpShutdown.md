# FwMoneisDiagEdpShutdown

- ea: `0x1800b902c`
- end: `0x1800b9136`
- name: `FwMoneisDiagEdpShutdown`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b9700`

## callees

- `0x180005aa0`
- `0x1800093b0`
- `0x180071624`
- `0x1800b902c`
- `0x1800b9d6c`
- `0x1800b9fb0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b90ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b90ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b90ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b90ad`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x1800b904d`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x1800b906c`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x1800b904d`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x1800b906c`
- `fwbase!FwCriticalSectionDestroy` at `0x1800b912f`
- `fwbase!FwFree` at `0x1800b9079`
- `fwbase!FwFree` at `0x1800b9099`
- `fwbase!FwFree` at `0x1800b9079`
- `fwbase!FwFree` at `0x1800b9099`

## pseudocode

```c
__int64 FwMoneisDiagEdpShutdown()
{
  __int64 v0; // rdx
  __int64 v1; // r8
  __int64 v2; // r9
  __int64 v3; // rcx
  __int64 v4; // rax

  if ( qword_18012C778 && (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
    PolicyManager_FreeStringValue(qword_18012C778);
  if ( qword_18012C790 && (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
    PolicyManager_FreeStringValue(qword_18012C790);
  FwFree(qword_18012C7C0);
  FwMoneisEdpUpdateNrptCloudResources(0);
  FwMoneisFreeEdpNrptRuleList(qword_18012C7D0);
  FwFree(qword_18012C7A8);
  if ( pwk )
  {
    WaitForThreadpoolWorkCallbacks(pwk, 0);
    CloseThreadpoolWork(pwk);
    pwk = 0;
  }
  while ( 1 )
  {
    v3 = qword_18012C720;
    if ( (__int64 *)qword_18012C720 == &qword_18012C720 )
      break;
    if ( *(__int64 **)(qword_18012C720 + 8) != &qword_18012C720
      || (v4 = *(_QWORD *)qword_18012C720, *(_QWORD *)(*(_QWORD *)qword_18012C720 + 8LL) != qword_18012C720) )
    {
      __fastfail(3u);
    }
    qword_18012C720 = *(_QWORD *)qword_18012C720;
    *(_QWORD *)(v4 + 8) = &qword_18012C720;
    FwMoneisDiagCleanupOpList(v3 - 40, 1, 1);
  }
  if ( (__int64 *)qword_18012C730 != &qword_18012C730 )
    MicrosoftTelemetryAssertTriggeredNoArgs(qword_18012C720, v0, v1, v2);
  return FwCriticalSectionDestroy(qword_18012C740);
}

```

## disassembly

```asm
0x1800b902c  push    rbx
0x1800b902e  sub     rsp, 20h
0x1800b9032  xor     ebx, ebx
0x1800b9034  cmp     cs:qword_18012C778, rbx
0x1800b903b  jz      short loc_1800B9053
0x1800b903d  call    IsPolicyManager_GetPolicyIntPresent
0x1800b9042  test    al, al
0x1800b9044  jz      short loc_1800B9053
0x1800b9046  mov     rcx, cs:qword_18012C778
0x1800b904d  call    cs:__imp_PolicyManager_FreeStringValue
0x1800b9053  cmp     cs:qword_18012C790, rbx
0x1800b905a  jz      short loc_1800B9072
0x1800b905c  call    IsPolicyManager_GetPolicyIntPresent
0x1800b9061  test    al, al
0x1800b9063  jz      short loc_1800B9072
0x1800b9065  mov     rcx, cs:qword_18012C790
0x1800b906c  call    cs:__imp_PolicyManager_FreeStringValue
0x1800b9072  mov     rcx, cs:qword_18012C7C0
0x1800b9079  call    cs:__imp_FwFree
0x1800b907f  xor     ecx, ecx
0x1800b9081  call    FwMoneisEdpUpdateNrptCloudResources
0x1800b9086  mov     rcx, cs:qword_18012C7D0
0x1800b908d  call    FwMoneisFreeEdpNrptRuleList
0x1800b9092  mov     rcx, cs:qword_18012C7A8
0x1800b9099  call    cs:__imp_FwFree
0x1800b909f  mov     rcx, cs:pwk; pwk
0x1800b90a6  test    rcx, rcx
0x1800b90a9  jz      short loc_1800B90C7
0x1800b90ab  xor     edx, edx; fCancelPendingCallbacks
0x1800b90ad  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800b90b3  mov     rcx, cs:pwk; pwk
0x1800b90ba  call    cs:__imp_CloseThreadpoolWork
0x1800b90c0  mov     cs:pwk, rbx
0x1800b90c7  lea     rbx, qword_18012C720
0x1800b90ce  mov     rcx, cs:qword_18012C720
0x1800b90d5  cmp     rcx, rbx
0x1800b90d8  jz      short loc_1800B910E
0x1800b90da  cmp     [rcx+8], rbx
0x1800b90de  jnz     short loc_1800B9107
0x1800b90e0  mov     rax, [rcx]
0x1800b90e3  cmp     [rax+8], rcx
0x1800b90e7  jnz     short loc_1800B9107
0x1800b90e9  mov     edx, 1
0x1800b90ee  mov     cs:qword_18012C720, rax
0x1800b90f5  mov     r8d, edx
0x1800b90f8  mov     [rax+8], rbx
0x1800b90fc  add     rcx, 0FFFFFFFFFFFFFFD8h
0x1800b9100  call    FwMoneisDiagCleanupOpList
0x1800b9105  jmp     short loc_1800B90CE
0x1800b9107  mov     ecx, 3
0x1800b910c  int     29h; Win8: RtlFailFast(ecx)
0x1800b910e  lea     rax, qword_18012C730
0x1800b9115  cmp     cs:qword_18012C730, rax
0x1800b911c  jz      short loc_1800B9123
0x1800b911e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b9123  lea     rcx, qword_18012C740
0x1800b912a  add     rsp, 20h
0x1800b912e  pop     rbx
0x1800b912f  jmp     cs:__imp_FwCriticalSectionDestroy
```

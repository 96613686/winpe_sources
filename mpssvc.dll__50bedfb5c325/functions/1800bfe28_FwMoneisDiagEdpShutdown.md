# FwMoneisDiagEdpShutdown

- ea: `0x1800bfe28`
- end: `0x1800bff5b`
- name: `FwMoneisDiagEdpShutdown`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c0564`

## callees

- `0x1800089bc`
- `0x18002adc4`
- `0x180074ad4`
- `0x1800bfe28`
- `0x1800c0c64`
- `0x1800c0ecc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800bfec1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800bfec1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bfed4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bfed4`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x1800bfe49`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x1800bfe6e`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x1800bfe49`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x1800bfe6e`
- `fwbase!FwCriticalSectionDestroy` at `0x1800bff4f`
- `fwbase!FwFree` at `0x1800bfe81`
- `fwbase!FwFree` at `0x1800bfea7`
- `fwbase!FwFree` at `0x1800bfe81`
- `fwbase!FwFree` at `0x1800bfea7`

## pseudocode

```c
__int64 FwMoneisDiagEdpShutdown()
{
  __int64 v0; // rcx
  __int64 v1; // rax

  if ( qword_180132948 && (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
    PolicyManager_FreeStringValue(qword_180132948);
  if ( qword_180132960 && (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
    PolicyManager_FreeStringValue(qword_180132960);
  FwFree(qword_180132990);
  FwMoneisEdpUpdateNrptCloudResources(0);
  FwMoneisFreeEdpNrptRuleList(qword_1801329A0);
  FwFree(qword_180132978);
  if ( pwk )
  {
    WaitForThreadpoolWorkCallbacks(pwk, 0);
    CloseThreadpoolWork(pwk);
    pwk = 0;
  }
  while ( 1 )
  {
    v0 = qword_1801328F0;
    if ( (__int64 *)qword_1801328F0 == &qword_1801328F0 )
      break;
    if ( *(__int64 **)(qword_1801328F0 + 8) != &qword_1801328F0
      || (v1 = *(_QWORD *)qword_1801328F0, *(_QWORD *)(*(_QWORD *)qword_1801328F0 + 8LL) != qword_1801328F0) )
    {
      __fastfail(3u);
    }
    qword_1801328F0 = *(_QWORD *)qword_1801328F0;
    *(_QWORD *)(v1 + 8) = &qword_1801328F0;
    FwMoneisDiagCleanupOpList(v0 - 40, 1, 1);
  }
  if ( (__int64 *)qword_180132900 != &qword_180132900 )
    MicrosoftTelemetryAssertTriggeredNoArgs(qword_1801328F0);
  return FwCriticalSectionDestroy(qword_180132910);
}

```

## disassembly

```asm
0x1800bfe28  push    rbx
0x1800bfe2a  sub     rsp, 20h
0x1800bfe2e  xor     ebx, ebx
0x1800bfe30  cmp     cs:qword_180132948, rbx
0x1800bfe37  jz      short loc_1800BFE55
0x1800bfe39  call    IsPolicyManager_GetPolicyIntPresent
0x1800bfe3e  test    al, al
0x1800bfe40  jz      short loc_1800BFE55
0x1800bfe42  mov     rcx, cs:qword_180132948
0x1800bfe49  call    cs:__imp_PolicyManager_FreeStringValue
0x1800bfe50  nop     dword ptr [rax+rax+00h]
0x1800bfe55  cmp     cs:qword_180132960, rbx
0x1800bfe5c  jz      short loc_1800BFE7A
0x1800bfe5e  call    IsPolicyManager_GetPolicyIntPresent
0x1800bfe63  test    al, al
0x1800bfe65  jz      short loc_1800BFE7A
0x1800bfe67  mov     rcx, cs:qword_180132960
0x1800bfe6e  call    cs:__imp_PolicyManager_FreeStringValue
0x1800bfe75  nop     dword ptr [rax+rax+00h]
0x1800bfe7a  mov     rcx, cs:qword_180132990
0x1800bfe81  call    cs:__imp_FwFree
0x1800bfe88  nop     dword ptr [rax+rax+00h]
0x1800bfe8d  xor     ecx, ecx
0x1800bfe8f  call    FwMoneisEdpUpdateNrptCloudResources
0x1800bfe94  mov     rcx, cs:qword_1801329A0
0x1800bfe9b  call    FwMoneisFreeEdpNrptRuleList
0x1800bfea0  mov     rcx, cs:qword_180132978
0x1800bfea7  call    cs:__imp_FwFree
0x1800bfeae  nop     dword ptr [rax+rax+00h]
0x1800bfeb3  mov     rcx, cs:pwk; pwk
0x1800bfeba  test    rcx, rcx
0x1800bfebd  jz      short loc_1800BFEE7
0x1800bfebf  xor     edx, edx; fCancelPendingCallbacks
0x1800bfec1  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800bfec8  nop     dword ptr [rax+rax+00h]
0x1800bfecd  mov     rcx, cs:pwk; pwk
0x1800bfed4  call    cs:__imp_CloseThreadpoolWork
0x1800bfedb  nop     dword ptr [rax+rax+00h]
0x1800bfee0  mov     cs:pwk, rbx
0x1800bfee7  lea     rbx, qword_1801328F0
0x1800bfeee  mov     rcx, cs:qword_1801328F0
0x1800bfef5  cmp     rcx, rbx
0x1800bfef8  jz      short loc_1800BFF2E
0x1800bfefa  cmp     [rcx+8], rbx
0x1800bfefe  jnz     short loc_1800BFF27
0x1800bff00  mov     rax, [rcx]
0x1800bff03  cmp     [rax+8], rcx
0x1800bff07  jnz     short loc_1800BFF27
0x1800bff09  mov     edx, 1
0x1800bff0e  mov     cs:qword_1801328F0, rax
0x1800bff15  mov     r8d, edx
0x1800bff18  mov     [rax+8], rbx
0x1800bff1c  add     rcx, 0FFFFFFFFFFFFFFD8h
0x1800bff20  call    FwMoneisDiagCleanupOpList
0x1800bff25  jmp     short loc_1800BFEEE
0x1800bff27  mov     ecx, 3
0x1800bff2c  int     29h; Win8: RtlFailFast(ecx)
0x1800bff2e  lea     rax, qword_180132900
0x1800bff35  cmp     cs:qword_180132900, rax
0x1800bff3c  jz      short loc_1800BFF43
0x1800bff3e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "IsListEmpty(&(gFwMoneisDiag.OpGetEdpIdNoProxyCheckList))")
0x1800bff43  lea     rcx, qword_180132910
0x1800bff4a  add     rsp, 20h
0x1800bff4e  pop     rbx
0x1800bff4f  jmp     cs:__imp_FwCriticalSectionDestroy
```

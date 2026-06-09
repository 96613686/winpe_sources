# CiAsyncRefreshPoliciesOnNightsWatchModeChange

- ea: `0x1800724e4`
- end: `0x18007258a`
- name: `CiAsyncRefreshPoliciesOnNightsWatchModeChange`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007281c`

## callees

- `0x1800724e4`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x180072570`
- `ntoskrnl!ExQueueWorkItem` at `0x180072570`
- `ntoskrnl!RtlWriteRegistryValue` at `0x18007251f`
- `ntoskrnl!RtlWriteRegistryValue` at `0x18007251f`

## string_xrefs

- `0x180072511`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

## pseudocode

```c
NTSTATUS __fastcall CiAsyncRefreshPoliciesOnNightsWatchModeChange(int a1, unsigned __int8 a2)
{
  unsigned __int64 v2; // rdi
  NTSTATUS result; // eax
  NTSTATUS v4; // ebx
  int ValueData; // [rsp+40h] [rbp+8h] BYREF

  ValueData = a1;
  v2 = a2;
  g_NightsWatchDesktopMinValueSeenDuringThisBootSession = a1;
  result = RtlWriteRegistryValue(
             0,
             L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
             L"VerifiedAndReputablePolicyState",
             4u,
             &ValueData,
             4u);
  v4 = result;
  if ( result >= 0 )
  {
    if ( _InterlockedCompareExchange(&g_CiPolicyRefreshScheduled, 1, 0) )
    {
      return -1073741739;
    }
    else
    {
      CiAsyncPolicyRefreshWorkItem.Parameter = (PVOID)v2;
      CiAsyncPolicyRefreshWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)CiAsyncPolicyRefreshRoutine;
      CiAsyncPolicyRefreshWorkItem.List.Flink = 0;
      ExQueueWorkItem(&CiAsyncPolicyRefreshWorkItem, DelayedWorkQueue);
      return v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800724e4  mov     rax, rsp
0x1800724e7  mov     [rax+10h], rbx
0x1800724eb  mov     [rax+8], ecx
0x1800724ee  push    rdi
0x1800724ef  sub     rsp, 30h
0x1800724f3  mov     r9d, 4; ValueType
0x1800724f9  movzx   edi, dl
0x1800724fc  mov     [rax-10h], r9d
0x180072500  lea     rax, [rax+8]
0x180072504  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, ecx
0x18007250a  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x180072511  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180072518  mov     [rsp+38h+ValueData], rax; ValueData
0x18007251d  xor     ecx, ecx; RelativeTo
0x18007251f  call    cs:__imp_RtlWriteRegistryValue
0x180072526  nop     dword ptr [rax+rax+00h]
0x18007252b  mov     ebx, eax
0x18007252d  test    eax, eax
0x18007252f  js      short loc_18007257E
0x180072531  mov     edx, 1; QueueType
0x180072536  xor     eax, eax
0x180072538  lock cmpxchg cs:g_CiPolicyRefreshScheduled, edx
0x180072540  jz      short loc_180072549
0x180072542  mov     eax, 0C0000055h
0x180072547  jmp     short loc_18007257E
0x180072549  lea     rax, CiAsyncPolicyRefreshRoutine
0x180072550  mov     cs:CiAsyncPolicyRefreshWorkItem.Parameter, rdi
0x180072557  lea     rcx, CiAsyncPolicyRefreshWorkItem; WorkItem
0x18007255e  mov     cs:CiAsyncPolicyRefreshWorkItem.WorkerRoutine, rax
0x180072565  mov     cs:CiAsyncPolicyRefreshWorkItem.List.Flink, 0
0x180072570  call    cs:__imp_ExQueueWorkItem
0x180072577  nop     dword ptr [rax+rax+00h]
0x18007257c  mov     eax, ebx
0x18007257e  mov     rbx, [rsp+38h+arg_8]
0x180072583  add     rsp, 30h
0x180072587  pop     rdi
0x180072588  retn
```

# CiAsyncRefreshPoliciesOnNightsWatchModeChange

- ea: `0x180073794`
- end: `0x18007383a`
- name: `CiAsyncRefreshPoliciesOnNightsWatchModeChange`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073acc`

## callees

- `0x180073794`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x180073820`
- `ntoskrnl!ExQueueWorkItem` at `0x180073820`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800737cf`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800737cf`

## string_xrefs

- `0x1800737c1`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x180073794  mov     rax, rsp
0x180073797  mov     [rax+10h], rbx
0x18007379b  mov     [rax+8], ecx
0x18007379e  push    rdi
0x18007379f  sub     rsp, 30h
0x1800737a3  mov     r9d, 4; ValueType
0x1800737a9  movzx   edi, dl
0x1800737ac  mov     [rax-10h], r9d
0x1800737b0  lea     rax, [rax+8]
0x1800737b4  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, ecx
0x1800737ba  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x1800737c1  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800737c8  mov     [rsp+38h+ValueData], rax; ValueData
0x1800737cd  xor     ecx, ecx; RelativeTo
0x1800737cf  call    cs:__imp_RtlWriteRegistryValue
0x1800737d6  nop     dword ptr [rax+rax+00h]
0x1800737db  mov     ebx, eax
0x1800737dd  test    eax, eax
0x1800737df  js      short loc_18007382E
0x1800737e1  mov     edx, 1; QueueType
0x1800737e6  xor     eax, eax
0x1800737e8  lock cmpxchg cs:g_CiPolicyRefreshScheduled, edx
0x1800737f0  jz      short loc_1800737F9
0x1800737f2  mov     eax, 0C0000055h
0x1800737f7  jmp     short loc_18007382E
0x1800737f9  lea     rax, CiAsyncPolicyRefreshRoutine
0x180073800  mov     cs:CiAsyncPolicyRefreshWorkItem.Parameter, rdi
0x180073807  lea     rcx, CiAsyncPolicyRefreshWorkItem; WorkItem
0x18007380e  mov     cs:CiAsyncPolicyRefreshWorkItem.WorkerRoutine, rax
0x180073815  mov     cs:CiAsyncPolicyRefreshWorkItem.List.Flink, 0
0x180073820  call    cs:__imp_ExQueueWorkItem
0x180073827  nop     dword ptr [rax+rax+00h]
0x18007382c  mov     eax, ebx
0x18007382e  mov     rbx, [rsp+38h+arg_8]
0x180073833  add     rsp, 30h
0x180073837  pop     rdi
0x180073838  retn
```

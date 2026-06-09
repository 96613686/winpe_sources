# CiAsyncRefreshPoliciesOnNightsWatchModeChange

- ea: `0x180073a74`
- end: `0x180073b1a`
- name: `CiAsyncRefreshPoliciesOnNightsWatchModeChange`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073dac`

## callees

- `0x180073a74`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x180073b00`
- `ntoskrnl!ExQueueWorkItem` at `0x180073b00`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180073aaf`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180073aaf`

## string_xrefs

- `0x180073aa1`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x180073a74  mov     rax, rsp
0x180073a77  mov     [rax+10h], rbx
0x180073a7b  mov     [rax+8], ecx
0x180073a7e  push    rdi
0x180073a7f  sub     rsp, 30h
0x180073a83  mov     r9d, 4; ValueType
0x180073a89  movzx   edi, dl
0x180073a8c  mov     [rax-10h], r9d
0x180073a90  lea     rax, [rax+8]
0x180073a94  mov     cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession, ecx
0x180073a9a  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x180073aa1  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180073aa8  mov     [rsp+38h+ValueData], rax; ValueData
0x180073aad  xor     ecx, ecx; RelativeTo
0x180073aaf  call    cs:__imp_RtlWriteRegistryValue
0x180073ab6  nop     dword ptr [rax+rax+00h]
0x180073abb  mov     ebx, eax
0x180073abd  test    eax, eax
0x180073abf  js      short loc_180073B0E
0x180073ac1  mov     edx, 1; QueueType
0x180073ac6  xor     eax, eax
0x180073ac8  lock cmpxchg cs:g_CiPolicyRefreshScheduled, edx
0x180073ad0  jz      short loc_180073AD9
0x180073ad2  mov     eax, 0C0000055h
0x180073ad7  jmp     short loc_180073B0E
0x180073ad9  lea     rax, CiAsyncPolicyRefreshRoutine
0x180073ae0  mov     cs:CiAsyncPolicyRefreshWorkItem.Parameter, rdi
0x180073ae7  lea     rcx, CiAsyncPolicyRefreshWorkItem; WorkItem
0x180073aee  mov     cs:CiAsyncPolicyRefreshWorkItem.WorkerRoutine, rax
0x180073af5  mov     cs:CiAsyncPolicyRefreshWorkItem.List.Flink, 0
0x180073b00  call    cs:__imp_ExQueueWorkItem
0x180073b07  nop     dword ptr [rax+rax+00h]
0x180073b0c  mov     eax, ebx
0x180073b0e  mov     rbx, [rsp+38h+arg_8]
0x180073b13  add     rsp, 30h
0x180073b17  pop     rdi
0x180073b18  retn
```

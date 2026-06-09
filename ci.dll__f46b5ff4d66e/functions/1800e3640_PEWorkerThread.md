# PEWorkerThread

- ea: `0x1800e3640`
- end: `0x1800e3749`
- name: `PEWorkerThread`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007e398`

## callees

- `0x1800e3640`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1800e36f8`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1800e36f8`
- `ntoskrnl!NtSetInformationThread` at `0x1800e36ad`
- `ntoskrnl!NtSetInformationThread` at `0x1800e3730`
- `ntoskrnl!NtSetInformationThread` at `0x1800e36ad`
- `ntoskrnl!NtSetInformationThread` at `0x1800e3730`
- `ntoskrnl!NtQueryInformationThread` at `0x1800e367e`
- `ntoskrnl!NtQueryInformationThread` at `0x1800e367e`
- `ntoskrnl!KeSetPriorityThread` at `0x1800e36d8`
- `ntoskrnl!KeSetPriorityThread` at `0x1800e36d8`
- `ntoskrnl!PsTerminateSystemThread` at `0x1800e370b`
- `ntoskrnl!PsTerminateSystemThread` at `0x1800e370b`

## pseudocode

```c
NTSTATUS __fastcall PEWorkerThread(char a1)
{
  int v2; // ebx
  NTSTATUS result; // eax
  unsigned int v4; // [rsp+40h] [rbp+8h] BYREF
  int ThreadInformation; // [rsp+48h] [rbp+10h] BYREF

  ThreadInformation = 0;
  v4 = 8;
  if ( NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, &v4, 4u, 0) >= 0 )
  {
    ThreadInformation = 1;
    if ( v4 <= 1 || NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, &ThreadInformation, 4u) < 0 )
      v4 = 8;
  }
  v2 = a1 & 1;
  if ( v2 )
    KeSetPriorityThread(KeGetCurrentThread(), 16);
  result = RtlRunOnceExecuteOnce(&g_PERunOnce, (PRTL_RUN_ONCE_INIT_FN)I_PEVerifyBootDrivers, 0, 0);
  if ( v2 )
    result = PsTerminateSystemThread(0);
  if ( v4 != 8 )
    return NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, &v4, 4u);
  return result;
}

```

## disassembly

```asm
0x1800e3640  mov     rax, rsp
0x1800e3643  mov     [rax+18h], rbx
0x1800e3647  push    r14
0x1800e3649  sub     rsp, 30h
0x1800e364d  mov     r9d, 4; ThreadInformationLength
0x1800e3653  mov     dword ptr [rax+10h], 0
0x1800e365a  mov     rbx, rcx
0x1800e365d  mov     dword ptr [rax+8], 8
0x1800e3664  mov     r14, 0FFFFFFFFFFFFFFFEh
0x1800e366b  mov     qword ptr [rax-18h], 0
0x1800e3673  lea     r8, [rax+8]; ThreadInformation
0x1800e3677  mov     rcx, r14; ThreadHandle
0x1800e367a  lea     edx, [r9+14h]; ThreadInformationClass
0x1800e367e  call    cs:__imp_NtQueryInformationThread
0x1800e3685  nop     dword ptr [rax+rax+00h]
0x1800e368a  test    eax, eax
0x1800e368c  js      short loc_1800E36C5
0x1800e368e  cmp     [rsp+38h+arg_0], 1
0x1800e3693  mov     [rsp+38h+ThreadInformation], 1
0x1800e369b  jbe     short loc_1800E36BD
0x1800e369d  lea     r9d, [r14+6]; ThreadInformationLength
0x1800e36a1  mov     rcx, r14; ThreadHandle
0x1800e36a4  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1800e36a9  lea     edx, [r14+1Ah]; ThreadInformationClass
0x1800e36ad  call    cs:__imp_NtSetInformationThread
0x1800e36b4  nop     dword ptr [rax+rax+00h]
0x1800e36b9  test    eax, eax
0x1800e36bb  jns     short loc_1800E36C5
0x1800e36bd  mov     [rsp+38h+arg_0], 8
0x1800e36c5  and     ebx, 1
0x1800e36c8  jz      short loc_1800E36E4
0x1800e36ca  mov     rcx, gs:188h; Thread
0x1800e36d3  mov     edx, 10h; Priority
0x1800e36d8  call    cs:__imp_KeSetPriorityThread
0x1800e36df  nop     dword ptr [rax+rax+00h]
0x1800e36e4  xor     r9d, r9d; Context
0x1800e36e7  lea     rdx, I_PEVerifyBootDrivers; InitFn
0x1800e36ee  xor     r8d, r8d; Parameter
0x1800e36f1  lea     rcx, g_PERunOnce; RunOnce
0x1800e36f8  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800e36ff  nop     dword ptr [rax+rax+00h]
0x1800e3704  test    rbx, rbx
0x1800e3707  jz      short loc_1800E3717
0x1800e3709  xor     ecx, ecx; ExitStatus
0x1800e370b  call    cs:__imp_PsTerminateSystemThread
0x1800e3712  nop     dword ptr [rax+rax+00h]
0x1800e3717  cmp     [rsp+38h+arg_0], 8
0x1800e371c  jz      short loc_1800E373C
0x1800e371e  mov     r9d, 4; ThreadInformationLength
0x1800e3724  lea     r8, [rsp+38h+arg_0]; ThreadInformation
0x1800e3729  mov     rcx, r14; ThreadHandle
0x1800e372c  lea     edx, [r9+14h]; ThreadInformationClass
0x1800e3730  call    cs:__imp_NtSetInformationThread
0x1800e3737  nop     dword ptr [rax+rax+00h]
0x1800e373c  mov     rbx, [rsp+38h+arg_10]
0x1800e3741  add     rsp, 30h
0x1800e3745  pop     r14
0x1800e3747  retn
```

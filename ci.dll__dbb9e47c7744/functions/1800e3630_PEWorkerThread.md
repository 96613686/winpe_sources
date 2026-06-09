# PEWorkerThread

- ea: `0x1800e3630`
- end: `0x1800e3739`
- name: `PEWorkerThread`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007f9c4`

## callees

- `0x1800e3630`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1800e36e8`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1800e36e8`
- `ntoskrnl!NtSetInformationThread` at `0x1800e369d`
- `ntoskrnl!NtSetInformationThread` at `0x1800e3720`
- `ntoskrnl!NtSetInformationThread` at `0x1800e369d`
- `ntoskrnl!NtSetInformationThread` at `0x1800e3720`
- `ntoskrnl!NtQueryInformationThread` at `0x1800e366e`
- `ntoskrnl!NtQueryInformationThread` at `0x1800e366e`
- `ntoskrnl!KeSetPriorityThread` at `0x1800e36c8`
- `ntoskrnl!KeSetPriorityThread` at `0x1800e36c8`
- `ntoskrnl!PsTerminateSystemThread` at `0x1800e36fb`
- `ntoskrnl!PsTerminateSystemThread` at `0x1800e36fb`

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
0x1800e3630  mov     rax, rsp
0x1800e3633  mov     [rax+18h], rbx
0x1800e3637  push    r14
0x1800e3639  sub     rsp, 30h
0x1800e363d  mov     r9d, 4; ThreadInformationLength
0x1800e3643  mov     dword ptr [rax+10h], 0
0x1800e364a  mov     rbx, rcx
0x1800e364d  mov     dword ptr [rax+8], 8
0x1800e3654  mov     r14, 0FFFFFFFFFFFFFFFEh
0x1800e365b  mov     qword ptr [rax-18h], 0
0x1800e3663  lea     r8, [rax+8]; ThreadInformation
0x1800e3667  mov     rcx, r14; ThreadHandle
0x1800e366a  lea     edx, [r9+14h]; ThreadInformationClass
0x1800e366e  call    cs:__imp_NtQueryInformationThread
0x1800e3675  nop     dword ptr [rax+rax+00h]
0x1800e367a  test    eax, eax
0x1800e367c  js      short loc_1800E36B5
0x1800e367e  cmp     [rsp+38h+arg_0], 1
0x1800e3683  mov     [rsp+38h+ThreadInformation], 1
0x1800e368b  jbe     short loc_1800E36AD
0x1800e368d  lea     r9d, [r14+6]; ThreadInformationLength
0x1800e3691  mov     rcx, r14; ThreadHandle
0x1800e3694  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1800e3699  lea     edx, [r14+1Ah]; ThreadInformationClass
0x1800e369d  call    cs:__imp_NtSetInformationThread
0x1800e36a4  nop     dword ptr [rax+rax+00h]
0x1800e36a9  test    eax, eax
0x1800e36ab  jns     short loc_1800E36B5
0x1800e36ad  mov     [rsp+38h+arg_0], 8
0x1800e36b5  and     ebx, 1
0x1800e36b8  jz      short loc_1800E36D4
0x1800e36ba  mov     rcx, gs:188h; Thread
0x1800e36c3  mov     edx, 10h; Priority
0x1800e36c8  call    cs:__imp_KeSetPriorityThread
0x1800e36cf  nop     dword ptr [rax+rax+00h]
0x1800e36d4  xor     r9d, r9d; Context
0x1800e36d7  lea     rdx, I_PEVerifyBootDrivers; InitFn
0x1800e36de  xor     r8d, r8d; Parameter
0x1800e36e1  lea     rcx, g_PERunOnce; RunOnce
0x1800e36e8  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800e36ef  nop     dword ptr [rax+rax+00h]
0x1800e36f4  test    rbx, rbx
0x1800e36f7  jz      short loc_1800E3707
0x1800e36f9  xor     ecx, ecx; ExitStatus
0x1800e36fb  call    cs:__imp_PsTerminateSystemThread
0x1800e3702  nop     dword ptr [rax+rax+00h]
0x1800e3707  cmp     [rsp+38h+arg_0], 8
0x1800e370c  jz      short loc_1800E372C
0x1800e370e  mov     r9d, 4; ThreadInformationLength
0x1800e3714  lea     r8, [rsp+38h+arg_0]; ThreadInformation
0x1800e3719  mov     rcx, r14; ThreadHandle
0x1800e371c  lea     edx, [r9+14h]; ThreadInformationClass
0x1800e3720  call    cs:__imp_NtSetInformationThread
0x1800e3727  nop     dword ptr [rax+rax+00h]
0x1800e372c  mov     rbx, [rsp+38h+arg_10]
0x1800e3731  add     rsp, 30h
0x1800e3735  pop     r14
0x1800e3737  retn
```

# PEWorkerThread

- ea: `0x1800e3bb0`
- end: `0x1800e3cb9`
- name: `PEWorkerThread`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800803d8`

## callees

- `0x1800e3bb0`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1800e3c68`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1800e3c68`
- `ntoskrnl!NtSetInformationThread` at `0x1800e3c1d`
- `ntoskrnl!NtSetInformationThread` at `0x1800e3ca0`
- `ntoskrnl!NtSetInformationThread` at `0x1800e3c1d`
- `ntoskrnl!NtSetInformationThread` at `0x1800e3ca0`
- `ntoskrnl!NtQueryInformationThread` at `0x1800e3bee`
- `ntoskrnl!NtQueryInformationThread` at `0x1800e3bee`
- `ntoskrnl!KeSetPriorityThread` at `0x1800e3c48`
- `ntoskrnl!KeSetPriorityThread` at `0x1800e3c48`
- `ntoskrnl!PsTerminateSystemThread` at `0x1800e3c7b`
- `ntoskrnl!PsTerminateSystemThread` at `0x1800e3c7b`

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
0x1800e3bb0  mov     rax, rsp
0x1800e3bb3  mov     [rax+18h], rbx
0x1800e3bb7  push    r14
0x1800e3bb9  sub     rsp, 30h
0x1800e3bbd  mov     r9d, 4; ThreadInformationLength
0x1800e3bc3  mov     dword ptr [rax+10h], 0
0x1800e3bca  mov     rbx, rcx
0x1800e3bcd  mov     dword ptr [rax+8], 8
0x1800e3bd4  mov     r14, 0FFFFFFFFFFFFFFFEh
0x1800e3bdb  mov     qword ptr [rax-18h], 0
0x1800e3be3  lea     r8, [rax+8]; ThreadInformation
0x1800e3be7  mov     rcx, r14; ThreadHandle
0x1800e3bea  lea     edx, [r9+14h]; ThreadInformationClass
0x1800e3bee  call    cs:__imp_NtQueryInformationThread
0x1800e3bf5  nop     dword ptr [rax+rax+00h]
0x1800e3bfa  test    eax, eax
0x1800e3bfc  js      short loc_1800E3C35
0x1800e3bfe  cmp     [rsp+38h+arg_0], 1
0x1800e3c03  mov     [rsp+38h+ThreadInformation], 1
0x1800e3c0b  jbe     short loc_1800E3C2D
0x1800e3c0d  lea     r9d, [r14+6]; ThreadInformationLength
0x1800e3c11  mov     rcx, r14; ThreadHandle
0x1800e3c14  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1800e3c19  lea     edx, [r14+1Ah]; ThreadInformationClass
0x1800e3c1d  call    cs:__imp_NtSetInformationThread
0x1800e3c24  nop     dword ptr [rax+rax+00h]
0x1800e3c29  test    eax, eax
0x1800e3c2b  jns     short loc_1800E3C35
0x1800e3c2d  mov     [rsp+38h+arg_0], 8
0x1800e3c35  and     ebx, 1
0x1800e3c38  jz      short loc_1800E3C54
0x1800e3c3a  mov     rcx, gs:188h; Thread
0x1800e3c43  mov     edx, 10h; Priority
0x1800e3c48  call    cs:__imp_KeSetPriorityThread
0x1800e3c4f  nop     dword ptr [rax+rax+00h]
0x1800e3c54  xor     r9d, r9d; Context
0x1800e3c57  lea     rdx, I_PEVerifyBootDrivers; InitFn
0x1800e3c5e  xor     r8d, r8d; Parameter
0x1800e3c61  lea     rcx, g_PERunOnce; RunOnce
0x1800e3c68  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800e3c6f  nop     dword ptr [rax+rax+00h]
0x1800e3c74  test    rbx, rbx
0x1800e3c77  jz      short loc_1800E3C87
0x1800e3c79  xor     ecx, ecx; ExitStatus
0x1800e3c7b  call    cs:__imp_PsTerminateSystemThread
0x1800e3c82  nop     dword ptr [rax+rax+00h]
0x1800e3c87  cmp     [rsp+38h+arg_0], 8
0x1800e3c8c  jz      short loc_1800E3CAC
0x1800e3c8e  mov     r9d, 4; ThreadInformationLength
0x1800e3c94  lea     r8, [rsp+38h+arg_0]; ThreadInformation
0x1800e3c99  mov     rcx, r14; ThreadHandle
0x1800e3c9c  lea     edx, [r9+14h]; ThreadInformationClass
0x1800e3ca0  call    cs:__imp_NtSetInformationThread
0x1800e3ca7  nop     dword ptr [rax+rax+00h]
0x1800e3cac  mov     rbx, [rsp+38h+arg_10]
0x1800e3cb1  add     rsp, 30h
0x1800e3cb5  pop     r14
0x1800e3cb7  retn
```

# SecTimerThreadRoutine

- ea: `0x14003aec0`
- end: `0x14003afd5`
- name: `SecTimerThreadRoutine`
- size: `277`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140011650`
- `0x14003a890`
- `0x14003aec0`
- `0x14003b3ec`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x14003af17`
- `ntoskrnl!PsTerminateSystemThread` at `0x14003afb0`
- `ntoskrnl!PsTerminateSystemThread` at `0x14003af17`
- `ntoskrnl!PsTerminateSystemThread` at `0x14003afb0`
- `ntoskrnl!KeSetPriorityThread` at `0x14003aeea`
- `ntoskrnl!KeSetPriorityThread` at `0x14003aeea`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003af7a`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003af7a`
- `ntoskrnl!ExAllocateTimer` at `0x14003aefe`
- `ntoskrnl!ExAllocateTimer` at `0x14003aefe`
- `ntoskrnl!ExDeleteTimer` at `0x14003afa2`
- `ntoskrnl!ExDeleteTimer` at `0x14003afa2`
- `ntoskrnl!ExSetTimer` at `0x14003af42`
- `ntoskrnl!ExSetTimer` at `0x14003af42`

## pseudocode

```c
void __fastcall SecTimerThreadRoutine(char *StartContext)
{
  void *Timer; // rbx
  __int64 v3; // rax
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  PVOID Object[2]; // [rsp+40h] [rbp-28h] BYREF

  KeSetPriorityThread(KeGetCurrentThread(), 7);
  Timer = (void *)ExAllocateTimer(0, 0, 8);
  if ( !Timer )
    PsTerminateSystemThread(-1073741801);
  Object[1] = Timer;
  Object[0] = StartContext + 16;
  while ( 1 )
  {
    v3 = SecGetStatisticsCallBackPeriodInNanoSeconds();
    ExSetTimer(Timer, v3, 0, 0);
    v4 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
    if ( !v4 )
      break;
    if ( v4 == 1 )
      SecLogStatistics();
  }
  LOBYTE(v6) = 1;
  LOBYTE(v5) = 1;
  ExDeleteTimer(Timer, v5, v6, 0);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x14003aec0  mov     [rsp+arg_0], rbx
0x14003aec5  push    rdi
0x14003aec6  sub     rsp, 60h
0x14003aeca  mov     rax, cs:__security_cookie
0x14003aed1  xor     rax, rsp
0x14003aed4  mov     [rsp+68h+var_18], rax
0x14003aed9  mov     rdi, rcx
0x14003aedc  mov     edx, 7; Priority
0x14003aee1  mov     rcx, gs:188h; Thread
0x14003aeea  call    cs:__imp_KeSetPriorityThread
0x14003aef1  nop     dword ptr [rax+rax+00h]
0x14003aef6  xor     edx, edx
0x14003aef8  xor     ecx, ecx
0x14003aefa  lea     r8d, [rdx+8]
0x14003aefe  call    cs:__imp_ExAllocateTimer
0x14003af05  nop     dword ptr [rax+rax+00h]
0x14003af0a  mov     rbx, rax
0x14003af0d  test    rax, rax
0x14003af10  jnz     short loc_14003AF23
0x14003af12  mov     ecx, 0C0000017h; ExitStatus
0x14003af17  call    cs:__imp_PsTerminateSystemThread
0x14003af1e  nop     dword ptr [rax+rax+00h]
0x14003af23  lea     rcx, [rdi+10h]
0x14003af27  mov     [rsp+68h+var_20], rbx
0x14003af2c  mov     [rsp+68h+Object], rcx
0x14003af31  call    SecGetStatisticsCallBackPeriodInNanoSeconds
0x14003af36  mov     rdx, rax
0x14003af39  xor     r9d, r9d
0x14003af3c  xor     r8d, r8d
0x14003af3f  mov     rcx, rbx
0x14003af42  call    cs:__imp_ExSetTimer
0x14003af49  nop     dword ptr [rax+rax+00h]
0x14003af4e  xor     r9d, r9d; WaitReason
0x14003af51  mov     [rsp+68h+WaitBlockArray], 0; WaitBlockArray
0x14003af5a  mov     [rsp+68h+Timeout], 0; Timeout
0x14003af63  lea     rdx, [rsp+68h+Object]; Object
0x14003af68  mov     [rsp+68h+Alertable], 0; Alertable
0x14003af6d  mov     [rsp+68h+WaitMode], 0; WaitMode
0x14003af72  lea     r8d, [r9+1]; WaitType
0x14003af76  lea     ecx, [r9+2]; Count
0x14003af7a  call    cs:__imp_KeWaitForMultipleObjects
0x14003af81  nop     dword ptr [rax+rax+00h]
0x14003af86  test    eax, eax
0x14003af88  jz      short loc_14003AF96
0x14003af8a  cmp     eax, 1
0x14003af8d  jnz     short loc_14003AF31
0x14003af8f  call    SecLogStatistics
0x14003af94  jmp     short loc_14003AF31
0x14003af96  mov     r8b, 1
0x14003af99  xor     r9d, r9d
0x14003af9c  mov     dl, r8b
0x14003af9f  mov     rcx, rbx
0x14003afa2  call    cs:__imp_ExDeleteTimer
0x14003afa9  nop     dword ptr [rax+rax+00h]
0x14003afae  xor     ecx, ecx; ExitStatus
0x14003afb0  call    cs:__imp_PsTerminateSystemThread
0x14003afb7  nop     dword ptr [rax+rax+00h]
0x14003afbc  mov     rcx, [rsp+68h+var_18]
0x14003afc1  xor     rcx, rsp; StackCookie
0x14003afc4  call    __security_check_cookie
0x14003afc9  mov     rbx, [rsp+68h+arg_0]
0x14003afce  add     rsp, 60h
0x14003afd2  pop     rdi
0x14003afd3  retn
```

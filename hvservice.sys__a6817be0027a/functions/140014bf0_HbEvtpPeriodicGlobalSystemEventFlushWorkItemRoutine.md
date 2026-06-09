# HbEvtpPeriodicGlobalSystemEventFlushWorkItemRoutine

- ea: `0x140014bf0`
- end: `0x140014cb8`
- name: `HbEvtpPeriodicGlobalSystemEventFlushWorkItemRoutine`
- size: `200`
- prototype: `void __fastcall(_QWORD *IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140001230`
- `0x140014bf0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140014ca0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140014ca0`
- `ntoskrnl!IoFreeWorkItem` at `0x140014c87`
- `ntoskrnl!IoFreeWorkItem` at `0x140014c87`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140014c11`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140014c11`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140014c78`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140014c78`
- `winhvr!WinHvFlushEventLogBuffer` at `0x140014c54`
- `winhvr!WinHvFlushEventLogBuffer` at `0x140014c54`

## pseudocode

```c
void __fastcall HbEvtpPeriodicGlobalSystemEventFlushWorkItemRoutine(
        _QWORD *IoObject,
        PVOID Context,
        PIO_WORKITEM IoWorkItem)
{
  struct _IO_REMOVE_LOCK *v3; // rsi
  unsigned int v5; // ebx
  __int64 *i; // rdi
  __int64 *v7; // [rsp+30h] [rbp+8h] BYREF

  v3 = (struct _IO_REMOVE_LOCK *)IoObject[8];
  v7 = 0;
  if ( ExAcquireRundownProtection(&stru_1400092E8) )
  {
    if ( (int)HbEvtpGetLogConfiguration(0, &v7) >= 0 )
    {
      v5 = 0;
      for ( i = v7; v5 < *((_DWORD *)i + 2); ++v5 )
        WinHvFlushEventLogBuffer(0, v5);
    }
    ExReleaseRundownProtection(&stru_1400092E8);
  }
  IoFreeWorkItem(IoWorkItem);
  IoReleaseRemoveLockEx(v3 + 2, v3, 0x20u);
}

```

## disassembly

```asm
0x140014bf0  mov     [rsp+arg_18], rbp
0x140014bf5  push    rsi
0x140014bf6  sub     rsp, 20h
0x140014bfa  mov     rsi, [rcx+40h]
0x140014bfe  mov     rbp, r8
0x140014c01  lea     rcx, stru_1400092E8; RunRef
0x140014c08  mov     [rsp+28h+arg_0], 0
0x140014c11  call    cs:__imp_ExAcquireRundownProtection
0x140014c18  nop     dword ptr [rax+rax+00h]
0x140014c1d  test    al, al
0x140014c1f  jz      short loc_140014C84
0x140014c21  lea     rdx, [rsp+28h+arg_0]
0x140014c26  xor     ecx, ecx
0x140014c28  call    HbEvtpGetLogConfiguration
0x140014c2d  test    eax, eax
0x140014c2f  js      short loc_140014C71
0x140014c31  mov     [rsp+28h+arg_8], rbx
0x140014c36  xor     ebx, ebx
0x140014c38  mov     [rsp+28h+arg_10], rdi
0x140014c3d  mov     rdi, [rsp+28h+arg_0]
0x140014c42  cmp     [rdi+8], ebx
0x140014c45  jbe     short loc_140014C67
0x140014c47  nop     word ptr [rax+rax+00000000h]
0x140014c50  mov     edx, ebx
0x140014c52  xor     ecx, ecx
0x140014c54  call    cs:__imp_WinHvFlushEventLogBuffer
0x140014c5b  nop     dword ptr [rax+rax+00h]
0x140014c60  inc     ebx
0x140014c62  cmp     ebx, [rdi+8]
0x140014c65  jb      short loc_140014C50
0x140014c67  mov     rbx, [rsp+28h+arg_8]
0x140014c6c  mov     rdi, [rsp+28h+arg_10]
0x140014c71  lea     rcx, stru_1400092E8; RunRef
0x140014c78  call    cs:__imp_ExReleaseRundownProtection
0x140014c7f  nop     dword ptr [rax+rax+00h]
0x140014c84  mov     rcx, rbp; IoWorkItem
0x140014c87  call    cs:__imp_IoFreeWorkItem
0x140014c8e  nop     dword ptr [rax+rax+00h]
0x140014c93  lea     rcx, [rsi+40h]; RemoveLock
0x140014c97  mov     r8d, 20h ; ' '; RemlockSize
0x140014c9d  mov     rdx, rsi; Tag
0x140014ca0  call    cs:__imp_IoReleaseRemoveLockEx
0x140014ca7  nop     dword ptr [rax+rax+00h]
0x140014cac  mov     rbp, [rsp+28h+arg_18]
0x140014cb1  add     rsp, 20h
0x140014cb5  pop     rsi
0x140014cb6  retn
```

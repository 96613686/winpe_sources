# SecPsCalloutWorker

- ea: `0x14002f5e0`
- end: `0x14002f6c9`
- name: `SecPsCalloutWorker`
- size: `233`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140007350`
- `0x14002f5e0`
- `0x140031b38`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14002f61c`
- `ntoskrnl!KeClearEvent` at `0x14002f61c`
- `ntoskrnl!KeReadStateEvent` at `0x14002f68c`
- `ntoskrnl!KeReadStateEvent` at `0x14002f68c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14002f62e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14002f62e`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14002f665`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14002f665`
- `ntoskrnl!PsTerminateSystemThread` at `0x14002f6b6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002f60c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002f60c`

## pseudocode

```c
void __fastcall SecPsCalloutWorker(char *StartContext)
{
  __int64 *v2; // rbx
  __int64 v3; // rax

  do
  {
    KeWaitForSingleObject(StartContext + 104, Executive, 0, 0, 0);
    KeClearEvent((PRKEVENT)(StartContext + 104));
    while ( *(char **)StartContext != StartContext )
    {
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(StartContext + 16));
      v2 = *(__int64 **)StartContext;
      if ( *(char **)(*(_QWORD *)StartContext + 8LL) != StartContext || (v3 = *v2, *(__int64 **)(*v2 + 8) != v2) )
        __fastfail(3u);
      *(_QWORD *)StartContext = v3;
      *(_QWORD *)(v3 + 8) = StartContext;
      --*((_DWORD *)StartContext + 32);
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(StartContext + 16));
      SecHandleWorkItem((__int64)(v2 - 1));
      SecReleaseWorkPacket(v2 - 1);
    }
  }
  while ( !KeReadStateEvent((PRKEVENT)StartContext + 3) );
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x14002f5e0  mov     [rsp+arg_0], rbx
0x14002f5e5  mov     [rsp+arg_8], rbp
0x14002f5ea  mov     [rsp+arg_10], rsi
0x14002f5ef  push    rdi
0x14002f5f0  sub     rsp, 30h
0x14002f5f4  mov     rdi, rcx
0x14002f5f7  xor     r9d, r9d; Alertable
0x14002f5fa  mov     [rsp+38h+Timeout], 0; Timeout
0x14002f603  xor     r8d, r8d; WaitMode
0x14002f606  lea     rcx, [rdi+68h]; Object
0x14002f60a  xor     edx, edx; WaitReason
0x14002f60c  call    cs:__imp_KeWaitForSingleObject
0x14002f613  nop     dword ptr [rax+rax+00h]
0x14002f618  lea     rcx, [rdi+68h]; Event
0x14002f61c  call    cs:__imp_KeClearEvent
0x14002f623  nop     dword ptr [rax+rax+00h]
0x14002f628  jmp     short loc_14002F683
0x14002f62a  lea     rcx, [rdi+10h]; Mutex
0x14002f62e  call    cs:__imp_KeAcquireGuardedMutex
0x14002f635  nop     dword ptr [rax+rax+00h]
0x14002f63a  mov     rbx, [rdi]
0x14002f63d  cmp     [rbx+8], rdi
0x14002f641  jnz     short loc_14002F6C2
0x14002f643  mov     rax, [rbx]
0x14002f646  cmp     [rax+8], rbx
0x14002f64a  jnz     short loc_14002F6C2
0x14002f64c  mov     [rdi], rax
0x14002f64f  lea     rcx, [rdi+10h]; Mutex
0x14002f653  mov     [rax+8], rdi
0x14002f657  mov     eax, [rdi+80h]
0x14002f65d  dec     eax
0x14002f65f  mov     [rdi+80h], eax
0x14002f665  call    cs:__imp_KeReleaseGuardedMutex
0x14002f66c  nop     dword ptr [rax+rax+00h]
0x14002f671  lea     rcx, [rbx-8]
0x14002f675  call    SecHandleWorkItem
0x14002f67a  lea     rcx, [rbx-8]
0x14002f67e  call    SecReleaseWorkPacket
0x14002f683  cmp     [rdi], rdi
0x14002f686  jnz     short loc_14002F62A
0x14002f688  lea     rcx, [rdi+48h]; Event
0x14002f68c  call    cs:__imp_KeReadStateEvent
0x14002f693  nop     dword ptr [rax+rax+00h]
0x14002f698  test    eax, eax
0x14002f69a  jz      loc_14002F5F7
0x14002f6a0  xor     ecx, ecx
0x14002f6a2  mov     rbx, [rsp+38h+arg_0]
0x14002f6a7  mov     rbp, [rsp+38h+arg_8]
0x14002f6ac  mov     rsi, [rsp+38h+arg_10]
0x14002f6b1  add     rsp, 30h
0x14002f6b5  pop     rdi
0x14002f6b6  jmp     cs:__imp_PsTerminateSystemThread
0x14002f6c2  mov     ecx, 3
0x14002f6c7  int     29h; Win8: RtlFailFast(ecx)
```

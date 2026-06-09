# lldpDetachPortFromBinding

- ea: `0x140010998`
- end: `0x140010a45`
- name: `lldpDetachPortFromBinding`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010560`
- `0x140012640`

## callees

- `0x1400041fc`
- `0x140004320`
- `0x140010998`
- `0x140010a50`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400109e8`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400109e8`

## pseudocode

```c
__int64 __fastcall lldpDetachPortFromBinding(__int64 a1)
{
  struct _KTHREAD *CurrentThread; // rsi
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) )
    lldpDeliverSpecialUnbindNotifications();
  CurrentThread = KeGetCurrentThread();
  Interval.QuadPart = -10000;
  while ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 16), (signed __int64)CurrentThread, 0) )
  {
    KeDelayExecutionThread(0, 0, &Interval);
    if ( Interval.QuadPart > -10000000 )
      Interval.QuadPart *= 2LL;
  }
  *(_QWORD *)(a1 + 24) = 0;
  lldpReleaseInterLock(a1 + 8);
  lldpCleanupPacket(a1 + 184);
  return lldpCleanupPacket(a1 + 152);
}

```

## disassembly

```asm
0x140010998  mov     [rsp+arg_10], rbx
0x14001099d  mov     [rsp+arg_18], rsi
0x1400109a2  push    rdi
0x1400109a3  sub     rsp, 20h
0x1400109a7  mov     rax, [rcx+18h]
0x1400109ab  mov     rbx, rcx
0x1400109ae  cmp     qword ptr [rax+10h], 0
0x1400109b3  jz      short loc_1400109BA
0x1400109b5  call    lldpDeliverSpecialUnbindNotifications
0x1400109ba  mov     qword ptr [rsp+28h+Interval], 0
0x1400109c3  mov     rsi, gs:188h
0x1400109cc  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFFD8F0h
0x1400109d5  xor     eax, eax
0x1400109d7  lock cmpxchg [rbx+10h], rsi
0x1400109dd  jz      short loc_140010A0B
0x1400109df  lea     r8, [rsp+28h+Interval]; Interval
0x1400109e4  xor     edx, edx; Alertable
0x1400109e6  xor     ecx, ecx; WaitMode
0x1400109e8  call    cs:__imp_KeDelayExecutionThread
0x1400109ef  nop     dword ptr [rax+rax+00h]
0x1400109f4  mov     rax, qword ptr [rsp+28h+Interval]
0x1400109f9  cmp     rax, 0FFFFFFFFFF676980h
0x1400109ff  jle     short loc_1400109D5
0x140010a01  add     rax, rax
0x140010a04  mov     qword ptr [rsp+28h+Interval], rax
0x140010a09  jmp     short loc_1400109D5
0x140010a0b  lea     rcx, [rbx+8]
0x140010a0f  mov     qword ptr [rbx+18h], 0
0x140010a17  call    lldpReleaseInterLock
0x140010a1c  lea     rcx, [rbx+0B8h]
0x140010a23  call    lldpCleanupPacket
0x140010a28  lea     rcx, [rbx+98h]
0x140010a2f  call    lldpCleanupPacket
0x140010a34  mov     rbx, [rsp+28h+arg_10]
0x140010a39  mov     rsi, [rsp+28h+arg_18]
0x140010a3e  add     rsp, 20h
0x140010a42  pop     rdi
0x140010a43  retn
```

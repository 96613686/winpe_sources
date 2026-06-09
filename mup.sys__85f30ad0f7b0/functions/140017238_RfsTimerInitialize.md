# RfsTimerInitialize

- ea: `0x140017238`
- end: `0x1400172b0`
- name: `RfsTimerInitialize`
- size: `120`
- prototype: `__int64 __fastcall(PVOID DeferredContext)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140010f18`
- `0x140012560`
- `0x140014e38`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x140017272`
- `ntoskrnl!KeInitializeDpc` at `0x140017272`
- `ntoskrnl!KeInitializeTimerEx` at `0x140017258`
- `ntoskrnl!KeInitializeTimerEx` at `0x140017258`

## pseudocode

```c
__int64 (__fastcall *__fastcall RfsTimerInitialize(char *DeferredContext, __int64 a2, __int64 a3, __int64 a4))()
{
  __int64 (__fastcall *result)(); // rax

  *((_DWORD *)DeferredContext + 16) = 32;
  *((_QWORD *)DeferredContext + 21) = a3;
  *((_QWORD *)DeferredContext + 22) = a4;
  KeInitializeTimerEx((PKTIMER)DeferredContext, NotificationTimer);
  KeInitializeDpc((PRKDPC)(DeferredContext + 72), RfsTimerpExpirationDpc, DeferredContext);
  result = RfsTimerpExpirationWorker;
  *((_QWORD *)DeferredContext + 20) = DeferredContext;
  *((_QWORD *)DeferredContext + 19) = RfsTimerpExpirationWorker;
  *((_QWORD *)DeferredContext + 17) = 0;
  *((_QWORD *)DeferredContext + 23) = 0;
  return result;
}

```

## disassembly

```asm
0x140017238  push    rbx
0x14001723a  sub     rsp, 20h
0x14001723e  xor     edx, edx; Type
0x140017240  mov     dword ptr [rcx+40h], 20h ; ' '
0x140017247  mov     rbx, rcx
0x14001724a  mov     [rcx+0A8h], r8
0x140017251  mov     [rcx+0B0h], r9
0x140017258  call    cs:__imp_KeInitializeTimerEx
0x14001725f  nop     dword ptr [rax+rax+00h]
0x140017264  lea     rcx, [rbx+48h]; Dpc
0x140017268  mov     r8, rbx; DeferredContext
0x14001726b  lea     rdx, RfsTimerpExpirationDpc; DeferredRoutine
0x140017272  call    cs:__imp_KeInitializeDpc
0x140017279  nop     dword ptr [rax+rax+00h]
0x14001727e  lea     rax, RfsTimerpExpirationWorker
0x140017285  mov     [rbx+0A0h], rbx
0x14001728c  mov     [rbx+98h], rax
0x140017293  mov     qword ptr [rbx+88h], 0
0x14001729e  mov     qword ptr [rbx+0B8h], 0
0x1400172a9  add     rsp, 20h
0x1400172ad  pop     rbx
0x1400172ae  retn
```

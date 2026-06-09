# RsrcKillCompletion

- ea: `0x14002fee0`
- end: `0x14003000a`
- name: `RsrcKillCompletion`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140013184`
- `0x14001e8f4`
- `0x14002fee0`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x14002ffb7`
- `ntoskrnl!KeInitializeDpc` at `0x14002ffb7`
- `ntoskrnl!KeInsertQueueDpc` at `0x14002ffcb`
- `ntoskrnl!KeInsertQueueDpc` at `0x14002ffcb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ff47`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ff47`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ffe1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ffe1`

## pseudocode

```c
__int64 __fastcall RsrcKillCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  KIRQL v7; // al
  _QWORD *v8; // r8
  KIRQL v9; // si
  struct _KDPC *v10; // rbx
  __int64 v11; // rax

  DisconnectHndlrNotOs(0, a3, 0, 0, 0, 0, 2, *(_BYTE *)(a3 + 125));
  NbtDereferenceLowerConnection(a3, v5, v6, 108, (__int64)"minio\\netbt\\sys\\nt\\tdihndlr.c");
  v7 = KeAcquireSpinLockRaiseToDpc(&Lock);
  v8 = DeferredContext;
  Irp = a2;
  v9 = v7;
  if ( DeferredContext != &DeferredContext )
  {
    v10 = (struct _KDPC *)Dpc;
    if ( Dpc )
    {
      Dpc = 0;
      if ( *((PVOID **)DeferredContext + 1) != &DeferredContext
        || (v11 = *(_QWORD *)DeferredContext, *(PVOID *)(*(_QWORD *)DeferredContext + 8LL) != DeferredContext) )
      {
        __fastfail(3u);
      }
      DeferredContext = *(PVOID *)DeferredContext;
      *(_QWORD *)(v11 + 8) = &DeferredContext;
      v8[1] = 24841;
      *v8 = 24841;
      KeInitializeDpc(v10, DpcNextOutOfRsrcKill, v8);
      KeInsertQueueDpc(v10, 0, 0);
    }
  }
  KeReleaseSpinLock(&Lock, v9);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14002fee0  mov     [rsp+arg_0], rbx
0x14002fee5  mov     [rsp+arg_8], rsi
0x14002feea  push    rdi
0x14002feeb  sub     rsp, 40h
0x14002feef  mov     al, [r8+7Dh]
0x14002fef3  mov     rbx, r8
0x14002fef6  mov     [rsp+48h+Irql], al; Irql
0x14002fefa  mov     rdi, rdx
0x14002fefd  mov     [rsp+48h+var_18], 2; int
0x14002ff05  xor     r9d, r9d; int
0x14002ff08  mov     [rsp+48h+var_20], 0; __int64
0x14002ff11  xor     r8d, r8d; int
0x14002ff14  mov     rdx, rbx; int
0x14002ff17  mov     [rsp+48h+var_28], 0; int
0x14002ff1f  xor     ecx, ecx; int
0x14002ff21  call    DisconnectHndlrNotOs
0x14002ff26  lea     rax, aMinioNetbtSysN_2; "minio\\netbt\\sys\\nt\\tdihndlr.c"
0x14002ff2d  mov     r9d, 106Ch
0x14002ff33  mov     rcx, rbx
0x14002ff36  mov     qword ptr [rsp+48h+var_28], rax
0x14002ff3b  call    NbtDereferenceLowerConnection
0x14002ff40  lea     rcx, Lock; SpinLock
0x14002ff47  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ff4e  nop     dword ptr [rax+rax+00h]
0x14002ff53  mov     r8, cs:DeferredContext; DeferredContext
0x14002ff5a  lea     rcx, DeferredContext
0x14002ff61  mov     cs:Irp, rdi
0x14002ff68  mov     sil, al
0x14002ff6b  cmp     r8, rcx
0x14002ff6e  jz      short loc_14002FFD7
0x14002ff70  mov     rbx, cs:Dpc
0x14002ff77  test    rbx, rbx
0x14002ff7a  jz      short loc_14002FFD7
0x14002ff7c  mov     cs:Dpc, 0
0x14002ff87  cmp     [r8+8], rcx
0x14002ff8b  jnz     short loc_140030003
0x14002ff8d  mov     rax, [r8]
0x14002ff90  cmp     [rax+8], r8
0x14002ff94  jnz     short loc_140030003
0x14002ff96  mov     cs:DeferredContext, rax
0x14002ff9d  lea     rdx, DpcNextOutOfRsrcKill; DeferredRoutine
0x14002ffa4  mov     [rax+8], rcx
0x14002ffa8  mov     eax, 6109h
0x14002ffad  mov     rcx, rbx; Dpc
0x14002ffb0  mov     [r8+8], rax
0x14002ffb4  mov     [r8], rax
0x14002ffb7  call    cs:__imp_KeInitializeDpc
0x14002ffbe  nop     dword ptr [rax+rax+00h]
0x14002ffc3  xor     r8d, r8d; SystemArgument2
0x14002ffc6  xor     edx, edx; SystemArgument1
0x14002ffc8  mov     rcx, rbx; Dpc
0x14002ffcb  call    cs:__imp_KeInsertQueueDpc
0x14002ffd2  nop     dword ptr [rax+rax+00h]
0x14002ffd7  mov     dl, sil; NewIrql
0x14002ffda  lea     rcx, Lock; SpinLock
0x14002ffe1  call    cs:__imp_KeReleaseSpinLock
0x14002ffe8  nop     dword ptr [rax+rax+00h]
0x14002ffed  mov     rbx, [rsp+48h+arg_0]
0x14002fff2  mov     eax, 0C0000016h
0x14002fff7  mov     rsi, [rsp+48h+arg_8]
0x14002fffc  add     rsp, 40h
0x140030000  pop     rdi
0x140030001  retn
0x140030003  mov     ecx, 3
0x140030008  int     29h; Win8: RtlFailFast(ecx)
```

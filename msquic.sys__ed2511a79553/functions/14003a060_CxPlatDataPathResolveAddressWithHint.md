# CxPlatDataPathResolveAddressWithHint

- ea: `0x14003a060`
- end: `0x14003a189`
- name: `CxPlatDataPathResolveAddressWithHint`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140039e18`

## callees

- `0x14003a060`
- `0x14003c980`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14003a0a0`
- `ntoskrnl!KeInitializeEvent` at `0x14003a0a0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a144`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a144`
- `ntoskrnl!IoFreeIrp` at `0x14003a15c`
- `ntoskrnl!IoFreeIrp` at `0x14003a15c`
- `ntoskrnl!IoAllocateIrp` at `0x14003a0b0`
- `ntoskrnl!IoAllocateIrp` at `0x14003a0b0`

## pseudocode

```c
__int64 __fastcall CxPlatDataPathResolveAddressWithHint(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PIRP Irp; // rax
  IRP *v9; // rdi
  unsigned int Status; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v12; // eax
  struct _KEVENT Object; // [rsp+60h] [rbp-28h] BYREF

  memset(&Object, 0, sizeof(Object));
  KeInitializeEvent(&Object, SynchronizationEvent, 0);
  Irp = IoAllocateIrp(1, 0);
  v9 = Irp;
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CxPlatDataPathIoCompletion;
    CurrentStackLocation[-1].Context = &Object;
    CurrentStackLocation[-1].Control = -32;
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, __int64, __int64, _QWORD, _QWORD, IRP *))(*(_QWORD *)(a1 + 104) + 32LL))(
            *(_QWORD *)(a1 + 96),
            a2,
            0,
            0,
            0,
            a3,
            a4,
            0,
            0,
            v9);
    Status = v12;
    if ( v12 == 259 )
    {
      KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
    }
    else if ( v12 < 0 )
    {
LABEL_7:
      IoFreeIrp(v9);
      return Status;
    }
    Status = v9->IoStatus.Status;
    goto LABEL_7;
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x14003a060  mov     r11, rsp
0x14003a063  mov     [r11+8], rbx
0x14003a067  mov     [r11+10h], rbp
0x14003a06b  mov     [r11+18h], rsi
0x14003a06f  mov     [r11+20h], rdi
0x14003a073  push    r14
0x14003a075  sub     rsp, 80h
0x14003a07c  xor     eax, eax
0x14003a07e  xorps   xmm0, xmm0
0x14003a081  mov     rbp, r8
0x14003a084  mov     r14, rdx
0x14003a087  mov     rbx, rcx
0x14003a08a  xor     r8d, r8d; State
0x14003a08d  movups  xmmword ptr [rsp+88h+Object.Header], xmm0
0x14003a092  lea     edx, [rax+1]; Type
0x14003a095  mov     [r11-18h], rax
0x14003a099  lea     rcx, [r11-28h]; Event
0x14003a09d  mov     rsi, r9
0x14003a0a0  call    cs:__imp_KeInitializeEvent
0x14003a0a7  nop     dword ptr [rax+rax+00h]
0x14003a0ac  xor     edx, edx; ChargeQuota
0x14003a0ae  mov     cl, 1; StackSize
0x14003a0b0  call    cs:__imp_IoAllocateIrp
0x14003a0b7  nop     dword ptr [rax+rax+00h]
0x14003a0bc  mov     rdi, rax
0x14003a0bf  test    rax, rax
0x14003a0c2  jnz     short loc_14003A0CE
0x14003a0c4  mov     ebx, 0C0000017h
0x14003a0c9  jmp     loc_14003A168
0x14003a0ce  mov     rax, [rax+0B8h]
0x14003a0d5  lea     rcx, CxPlatDataPathIoCompletion
0x14003a0dc  mov     [rsp+88h+var_40], rdi
0x14003a0e1  xor     r9d, r9d
0x14003a0e4  and     [rsp+88h+var_48], 0
0x14003a0ea  xor     r8d, r8d
0x14003a0ed  and     [rsp+88h+var_50], 0
0x14003a0f3  mov     rdx, r14
0x14003a0f6  mov     [rax-10h], rcx
0x14003a0fa  lea     rcx, [rsp+88h+Object]
0x14003a0ff  mov     [rax-8], rcx
0x14003a103  mov     byte ptr [rax-45h], 0E0h
0x14003a107  mov     rax, [rbx+68h]
0x14003a10b  mov     rcx, [rbx+60h]
0x14003a10f  mov     [rsp+88h+var_58], rsi
0x14003a114  mov     [rsp+88h+var_60], rbp
0x14003a119  mov     rax, [rax+20h]
0x14003a11d  and     [rsp+88h+var_68], 0
0x14003a123  call    _guard_dispatch_icall
0x14003a128  mov     ebx, eax
0x14003a12a  cmp     eax, 103h
0x14003a12f  jnz     short loc_14003A152
0x14003a131  and     [rsp+88h+var_68], 0
0x14003a137  lea     rcx, [rsp+88h+Object]; Object
0x14003a13c  xor     r9d, r9d; Alertable
0x14003a13f  xor     r8d, r8d; WaitMode
0x14003a142  xor     edx, edx; WaitReason
0x14003a144  call    cs:__imp_KeWaitForSingleObject
0x14003a14b  nop     dword ptr [rax+rax+00h]
0x14003a150  jmp     short loc_14003A156
0x14003a152  test    eax, eax
0x14003a154  js      short loc_14003A159
0x14003a156  mov     ebx, [rdi+30h]
0x14003a159  mov     rcx, rdi; Irp
0x14003a15c  call    cs:__imp_IoFreeIrp
0x14003a163  nop     dword ptr [rax+rax+00h]
0x14003a168  lea     r11, [rsp+88h+var_8]
0x14003a170  mov     eax, ebx
0x14003a172  mov     rbx, [r11+10h]
0x14003a176  mov     rbp, [r11+18h]
0x14003a17a  mov     rsi, [r11+20h]
0x14003a17e  mov     rdi, [r11+28h]
0x14003a182  mov     rsp, r11
0x14003a185  pop     r14
0x14003a187  retn
```

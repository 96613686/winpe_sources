# ReturnIrp

- ea: `0x1400148a0`
- end: `0x140014906`
- name: `ReturnIrp`
- size: `102`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400062b0`
- `0x1400281b0`
- `0x140047d90`
- `0x14004b7a0`
- `0x14004ce30`
- `0x14004d120`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400148ee`
- `ntoskrnl!IofCompleteRequest` at `0x1400148ee`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400148d0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400148d0`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400148b9`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400148b9`

## pseudocode

```c
void __fastcall ReturnIrp(PIRP Irp, NTSTATUS a2)
{
  CCHAR v4; // dl
  KIRQL Irql; // [rsp+38h] [rbp+10h] BYREF

  Irql = 0;
  IoAcquireCancelSpinLock(&Irql);
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0);
  IoReleaseCancelSpinLock(Irql);
  Irp->IoStatus.Status = a2;
  v4 = 2;
  if ( a2 )
    v4 = 0;
  IofCompleteRequest(Irp, v4);
}

```

## disassembly

```asm
0x1400148a0  mov     [rsp+arg_0], rbx
0x1400148a5  push    rdi
0x1400148a6  sub     rsp, 20h
0x1400148aa  mov     rdi, rcx
0x1400148ad  mov     [rsp+28h+Irql], 0
0x1400148b2  lea     rcx, [rsp+28h+Irql]; Irql
0x1400148b7  mov     ebx, edx
0x1400148b9  call    cs:__imp_IoAcquireCancelSpinLock
0x1400148c0  nop     dword ptr [rax+rax+00h]
0x1400148c5  xor     eax, eax
0x1400148c7  xchg    rax, [rdi+68h]
0x1400148cb  movzx   ecx, [rsp+28h+Irql]; Irql
0x1400148d0  call    cs:__imp_IoReleaseCancelSpinLock
0x1400148d7  nop     dword ptr [rax+rax+00h]
0x1400148dc  xor     eax, eax
0x1400148de  mov     [rdi+30h], ebx
0x1400148e1  test    ebx, ebx
0x1400148e3  mov     edx, 2
0x1400148e8  mov     rcx, rdi; Irp
0x1400148eb  cmovnz  edx, eax; PriorityBoost
0x1400148ee  call    cs:__imp_IofCompleteRequest
0x1400148f5  nop     dword ptr [rax+rax+00h]
0x1400148fa  mov     rbx, [rsp+28h+arg_0]
0x1400148ff  add     rsp, 20h
0x140014903  pop     rdi
0x140014904  retn
```

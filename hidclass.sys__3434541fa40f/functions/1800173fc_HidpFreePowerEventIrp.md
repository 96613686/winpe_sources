# HidpFreePowerEventIrp

- ea: `0x1800173fc`
- end: `0x1800174b1`
- name: `HidpFreePowerEventIrp`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003e5b0`

## callees

- `0x1800173fc`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x180017434`
- `ntoskrnl!MmBadPointer` at `0x180017446`
- `ntoskrnl!IofCompleteRequest` at `0x180017494`
- `ntoskrnl!IofCompleteRequest` at `0x180017494`
- `ntoskrnl!KeReleaseSpinLock` at `0x180017465`
- `ntoskrnl!KeReleaseSpinLock` at `0x180017465`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001741a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001741a`

## pseudocode

```c
void __fastcall HidpFreePowerEventIrp(__int64 a1)
{
  KSPIN_LOCK *v1; // rsi
  IRP *v3; // rbx
  KIRQL v4; // al
  unsigned __int64 v5; // r8
  _IRP *MasterIrp; // rax

  v1 = (KSPIN_LOCK *)(a1 + 328);
  v3 = 0;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 328));
  v5 = *(_QWORD *)(a1 + 320);
  if ( v5 && (PVOID)v5 != MmBadPointer )
  {
    v3 = (IRP *)(v5 & -(__int64)(_InterlockedExchange64((volatile __int64 *)(v5 + 104), 0) != 0));
    *(_QWORD *)(a1 + 320) = MmBadPointer;
  }
  KeReleaseSpinLock(v1, v4);
  if ( v3 )
  {
    MasterIrp = v3->AssociatedIrp.MasterIrp;
    v3->IoStatus.Status = -1073741667;
    *(_DWORD *)&MasterIrp->Type = 0;
    v3->IoStatus.Information = 0;
    IofCompleteRequest(v3, 0);
  }
}

```

## disassembly

```asm
0x1800173fc  mov     [rsp+arg_0], rbx
0x180017401  mov     [rsp+arg_8], rsi
0x180017406  push    rdi
0x180017407  sub     rsp, 20h
0x18001740b  lea     rsi, [rcx+148h]
0x180017412  mov     rdi, rcx
0x180017415  mov     rcx, rsi; SpinLock
0x180017418  xor     ebx, ebx
0x18001741a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180017421  nop     dword ptr [rax+rax+00h]
0x180017426  mov     r8, [rdi+140h]
0x18001742d  mov     cl, al
0x18001742f  test    r8, r8
0x180017432  jz      short loc_180017460
0x180017434  mov     rdx, cs:MmBadPointer
0x18001743b  cmp     r8, [rdx]
0x18001743e  jz      short loc_180017460
0x180017440  xor     edx, edx
0x180017442  xchg    rdx, [r8+68h]
0x180017446  mov     rax, cs:MmBadPointer
0x18001744d  neg     rdx
0x180017450  sbb     rbx, rbx
0x180017453  and     rbx, r8
0x180017456  mov     rdx, [rax]
0x180017459  mov     [rdi+140h], rdx
0x180017460  mov     dl, cl; NewIrql
0x180017462  mov     rcx, rsi; SpinLock
0x180017465  call    cs:__imp_KeReleaseSpinLock
0x18001746c  nop     dword ptr [rax+rax+00h]
0x180017471  test    rbx, rbx
0x180017474  jz      short loc_1800174A0
0x180017476  mov     rax, [rbx+18h]
0x18001747a  xor     edx, edx; PriorityBoost
0x18001747c  mov     dword ptr [rbx+30h], 0C000009Dh
0x180017483  mov     rcx, rbx; Irp
0x180017486  mov     dword ptr [rax], 0
0x18001748c  mov     qword ptr [rbx+38h], 0
0x180017494  call    cs:__imp_IofCompleteRequest
0x18001749b  nop     dword ptr [rax+rax+00h]
0x1800174a0  mov     rbx, [rsp+28h+arg_0]
0x1800174a5  mov     rsi, [rsp+28h+arg_8]
0x1800174aa  add     rsp, 20h
0x1800174ae  pop     rdi
0x1800174af  retn
```

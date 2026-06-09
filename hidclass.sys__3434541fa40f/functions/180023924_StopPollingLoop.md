# StopPollingLoop

- ea: `0x180023924`
- end: `0x180023a39`
- name: `StopPollingLoop`
- size: `277`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006ac8`
- `0x18001a1cc`

## callees

- `0x18000cd00`
- `0x180023924`

## import_xrefs

- `ntoskrnl!KeInitializeTimer` at `0x180023967`
- `ntoskrnl!KeInitializeTimer` at `0x180023967`
- `ntoskrnl!KeCancelTimer` at `0x180023957`
- `ntoskrnl!KeCancelTimer` at `0x180023957`
- `ntoskrnl!IofCompleteRequest` at `0x180023a16`
- `ntoskrnl!IofCompleteRequest` at `0x180023a16`
- `ntoskrnl!KeReleaseSpinLock` at `0x180023979`
- `ntoskrnl!KeReleaseSpinLock` at `0x180023979`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180023944`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180023944`

## pseudocode

```c
void __fastcall StopPollingLoop(__int64 a1, char a2)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v5; // di
  __int64 **v6; // rcx
  __int64 ***v7; // rax
  __int64 Irp; // rax
  __int64 *v9; // rcx
  __int64 *v10; // rax
  IRP *v11; // rcx
  __int64 *v12; // [rsp+20h] [rbp-18h] BYREF
  __int64 **v13; // [rsp+28h] [rbp-10h]

  v2 = (KSPIN_LOCK *)(a1 + 232);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 232));
  KeCancelTimer((PKTIMER)(a1 + 88));
  KeInitializeTimer((PKTIMER)(a1 + 88));
  KeReleaseSpinLock(v2, v5);
  if ( a2 )
  {
    v13 = &v12;
    v12 = (__int64 *)&v12;
    while ( 1 )
    {
      Irp = DequeuePolledReadIrp(a1);
      if ( !Irp )
        break;
      v6 = v13;
      if ( *v13 != (__int64 *)&v12 )
LABEL_10:
        __fastfail(3u);
      v7 = (__int64 ***)(Irp + 168);
      *v7 = &v12;
      v7[1] = v6;
      *v6 = (__int64 *)v7;
      v13 = (__int64 **)v7;
    }
    while ( 1 )
    {
      v9 = v12;
      if ( v12 == (__int64 *)&v12 )
        break;
      if ( (__int64 **)v12[1] != &v12 )
        goto LABEL_10;
      v10 = (__int64 *)*v12;
      if ( *(__int64 **)(*v12 + 8) != v12 )
        goto LABEL_10;
      v12 = (__int64 *)*v12;
      v10[1] = (__int64)&v12;
      v11 = (IRP *)(v9 - 21);
      v11->IoStatus.Status = -1073741667;
      v11->IoStatus.Information = 0;
      IofCompleteRequest(v11, 0);
    }
  }
}

```

## disassembly

```asm
0x180023924  push    rbp
0x180023926  push    rbx
0x180023927  push    rsi
0x180023928  push    rdi
0x180023929  push    r14
0x18002392b  push    r15
0x18002392d  mov     rbp, rsp
0x180023930  sub     rsp, 38h
0x180023934  lea     rsi, [rcx+0E8h]
0x18002393b  mov     r15, rcx
0x18002393e  mov     rcx, rsi; SpinLock
0x180023941  mov     r14b, dl
0x180023944  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18002394b  nop     dword ptr [rax+rax+00h]
0x180023950  lea     rcx, [r15+58h]; PKTIMER
0x180023954  mov     dil, al
0x180023957  call    cs:__imp_KeCancelTimer
0x18002395e  nop     dword ptr [rax+rax+00h]
0x180023963  lea     rcx, [r15+58h]; Timer
0x180023967  call    cs:__imp_KeInitializeTimer
0x18002396e  nop     dword ptr [rax+rax+00h]
0x180023973  mov     dl, dil; NewIrql
0x180023976  mov     rcx, rsi; SpinLock
0x180023979  call    cs:__imp_KeReleaseSpinLock
0x180023980  nop     dword ptr [rax+rax+00h]
0x180023985  test    r14b, r14b
0x180023988  jz      loc_180023A2B
0x18002398e  lea     rax, [rbp+var_18]
0x180023992  mov     [rbp+var_10], rax
0x180023996  lea     rax, [rbp+var_18]
0x18002399a  mov     [rbp+var_18], rax
0x18002399e  jmp     short loc_1800239C5
0x1800239a0  mov     rcx, [rbp+var_10]
0x1800239a4  lea     rdx, [rbp+var_18]
0x1800239a8  cmp     [rcx], rdx
0x1800239ab  jnz     short loc_180023A24
0x1800239ad  add     rax, 0A8h
0x1800239b3  lea     rdx, [rbp+var_18]
0x1800239b7  mov     [rax], rdx
0x1800239ba  mov     [rax+8], rcx
0x1800239be  mov     [rcx], rax
0x1800239c1  mov     [rbp+var_10], rax
0x1800239c5  mov     rcx, r15
0x1800239c8  call    DequeuePolledReadIrp
0x1800239cd  test    rax, rax
0x1800239d0  jnz     short loc_1800239A0
0x1800239d2  mov     rcx, [rbp+var_18]
0x1800239d6  lea     rax, [rbp+var_18]
0x1800239da  cmp     rcx, rax
0x1800239dd  jz      short loc_180023A2B
0x1800239df  lea     rax, [rbp+var_18]
0x1800239e3  cmp     [rcx+8], rax
0x1800239e7  jnz     short loc_180023A24
0x1800239e9  mov     rax, [rcx]
0x1800239ec  cmp     [rax+8], rcx
0x1800239f0  jnz     short loc_180023A24
0x1800239f2  mov     [rbp+var_18], rax
0x1800239f6  lea     rdx, [rbp+var_18]
0x1800239fa  mov     [rax+8], rdx
0x1800239fe  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x180023a05  xor     edx, edx; PriorityBoost
0x180023a07  mov     dword ptr [rcx+30h], 0C000009Dh
0x180023a0e  mov     qword ptr [rcx+38h], 0
0x180023a16  call    cs:__imp_IofCompleteRequest
0x180023a1d  nop     dword ptr [rax+rax+00h]
0x180023a22  jmp     short loc_1800239D2
0x180023a24  mov     ecx, 3
0x180023a29  int     29h; Win8: RtlFailFast(ecx)
0x180023a2b  add     rsp, 38h
0x180023a2f  pop     r15
0x180023a31  pop     r14
0x180023a33  pop     rdi
0x180023a34  pop     rsi
0x180023a35  pop     rbx
0x180023a36  pop     rbp
0x180023a37  retn
```

# PxCmNotifyCloseAfComplete

- ea: `0x140002100`
- end: `0x1400021ee`
- name: `PxCmNotifyCloseAfComplete`
- size: `238`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400011b0`

## callees

- `0x140001bc8`
- `0x140002100`
- `0x1400078f0`
- `0x140007940`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002159`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002190`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002159`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002190`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002180`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400021b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002180`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400021b5`
- `NDIS!NdisSetEvent` at `0x1400021d1`
- `NDIS!NdisSetEvent` at `0x1400021d1`

## pseudocode

```c
void __fastcall PxCmNotifyCloseAfComplete(char *P)
{
  __int64 v2; // rdi
  KIRQL v3; // al
  bool v4; // zf
  KIRQL v5; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids, 0);
  v2 = *((_QWORD *)P + 17);
  if ( v2 )
  {
    v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 184));
    v4 = (*(_DWORD *)(v2 + 20))-- == 1;
    *(_BYTE *)(v2 + 192) = v3;
    if ( v4 )
      DoDerefClAfWork(v2);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 184), v3);
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 11);
    v4 = (*((_DWORD *)P + 5))-- == 1;
    P[96] = v5;
    if ( v4 )
      DoDerefCmAfWork(P);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)P + 11, v5);
  }
  else
  {
    *((_DWORD *)P + 32) = 0;
    NdisSetEvent((PNDIS_EVENT)(P + 104));
  }
}

```

## disassembly

```asm
0x140002100  mov     [rsp+arg_8], rbx
0x140002105  mov     [rsp+arg_10], rsi
0x14000210a  push    rdi
0x14000210b  sub     rsp, 20h
0x14000210f  mov     rbx, rcx
0x140002112  mov     rcx, cs:WPP_GLOBAL_Control
0x140002119  lea     rax, WPP_GLOBAL_Control
0x140002120  cmp     rcx, rax
0x140002123  jz      short loc_140002143
0x140002125  cmp     byte ptr [rcx+29h], 5
0x140002129  jb      short loc_140002143
0x14000212b  mov     rcx, [rcx+18h]
0x14000212f  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x140002136  mov     edx, 1Bh
0x14000213b  xor     r9d, r9d
0x14000213e  call    WPP_SF_q
0x140002143  mov     rdi, [rbx+88h]
0x14000214a  test    rdi, rdi
0x14000214d  jz      short loc_1400021C3
0x14000214f  lea     rsi, [rdi+0B8h]
0x140002156  mov     rcx, rsi; SpinLock
0x140002159  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002160  nop     dword ptr [rax+rax+00h]
0x140002165  add     dword ptr [rdi+14h], 0FFFFFFFFh
0x140002169  mov     [rdi+0C0h], al
0x14000216f  jnz     short loc_14000217B
0x140002171  mov     rcx, rdi
0x140002174  call    DoDerefClAfWork
0x140002179  jmp     short loc_14000218C
0x14000217b  mov     dl, al; NewIrql
0x14000217d  mov     rcx, rsi; SpinLock
0x140002180  call    cs:__imp_KeReleaseSpinLock
0x140002187  nop     dword ptr [rax+rax+00h]
0x14000218c  lea     rcx, [rbx+58h]; SpinLock
0x140002190  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002197  nop     dword ptr [rax+rax+00h]
0x14000219c  add     dword ptr [rbx+14h], 0FFFFFFFFh
0x1400021a0  mov     [rbx+60h], al
0x1400021a3  jnz     short loc_1400021AF
0x1400021a5  mov     rcx, rbx; P
0x1400021a8  call    DoDerefCmAfWork
0x1400021ad  jmp     short loc_1400021DD
0x1400021af  mov     dl, al; NewIrql
0x1400021b1  lea     rcx, [rbx+58h]; SpinLock
0x1400021b5  call    cs:__imp_KeReleaseSpinLock
0x1400021bc  nop     dword ptr [rax+rax+00h]
0x1400021c1  jmp     short loc_1400021DD
0x1400021c3  lea     rcx, [rbx+68h]; Event
0x1400021c7  mov     dword ptr [rbx+80h], 0
0x1400021d1  call    cs:__imp_NdisSetEvent
0x1400021d8  nop     dword ptr [rax+rax+00h]
0x1400021dd  mov     rbx, [rsp+28h+arg_8]
0x1400021e2  mov     rsi, [rsp+28h+arg_10]
0x1400021e7  add     rsp, 20h
0x1400021eb  pop     rdi
0x1400021ec  retn
```

# PayloadAckTimerEvent

- ea: `0x140015190`
- end: `0x1400152a8`
- name: `PayloadAckTimerEvent`
- size: `280`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1400013f0`
- `0x140015190`
- `0x14001b830`
- `0x14001c050`
- `0x14001c390`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140015208`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015270`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015208`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015270`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015286`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015286`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015248`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015248`

## pseudocode

```c
__int64 __fastcall PayloadAckTimerEvent(PVOID Entry, __int64 a2, int a3)
{
  __int64 v3; // r15
  KSPIN_LOCK *v6; // rdi
  char v7; // si
  __int64 v8; // r14
  KIRQL v9; // al
  bool v10; // zf
  KIRQL v11; // al
  __int64 v13; // [rsp+28h] [rbp-60h]
  __int64 v14; // [rsp+30h] [rbp-58h]

  v3 = *(_QWORD *)(a2 + 24);
  if ( !a3 )
  {
    v6 = (KSPIN_LOCK *)(a2 + 40);
    if ( (unsigned __int8)ReferenceCall(a2) )
    {
      v7 = 0;
      v8 = 0;
      v9 = KeAcquireSpinLockRaiseToDpc(v6);
      *(_BYTE *)(a2 + 48) = v9;
      if ( Entry == *(PVOID *)(a2 + 272) )
      {
        v10 = (*(_DWORD *)(a2 + 60) & 0x2000000) == 0;
        *(_QWORD *)(a2 + 272) = 0;
        if ( !v10 )
        {
          v7 = 1;
          v8 = *(_QWORD *)(a2 + 32);
          ++*(_DWORD *)(a2 + 400);
        }
      }
      KeReleaseSpinLock(v6, v9);
      if ( v7 )
        ScheduleTunnelWork(v8, a2, (__int64)SendPayloadAck, 0, 0, v13, v14, 0);
      else
        DereferenceCall(a2);
    }
    else
    {
      v11 = KeAcquireSpinLockRaiseToDpc(v6);
      *(_BYTE *)(a2 + 48) = v11;
      if ( Entry == *(PVOID *)(a2 + 272) )
        *(_QWORD *)(a2 + 272) = 0;
      KeReleaseSpinLock(v6, v11);
    }
  }
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 576), Entry);
  return DereferenceVc(a2);
}

```

## disassembly

```asm
0x140015190  push    rbx
0x140015192  push    rbp
0x140015193  push    rsi
0x140015194  push    rdi
0x140015195  push    r14
0x140015197  push    r15
0x140015199  sub     rsp, 58h
0x14001519d  mov     r15, [rdx+18h]
0x1400151a1  mov     rbx, rdx
0x1400151a4  mov     rbp, rcx
0x1400151a7  test    r8d, r8d
0x1400151aa  jnz     loc_14001527C
0x1400151b0  mov     rcx, rdx
0x1400151b3  lea     rdi, [rdx+28h]
0x1400151b7  call    ReferenceCall
0x1400151bc  mov     rcx, rdi; SpinLock
0x1400151bf  test    al, al
0x1400151c1  jz      loc_140015248
0x1400151c7  xor     sil, sil
0x1400151ca  xor     r14d, r14d
0x1400151cd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400151d4  nop     dword ptr [rax+rax+00h]
0x1400151d9  mov     [rbx+30h], al
0x1400151dc  cmp     rbp, [rbx+110h]
0x1400151e3  jnz     short loc_140015203
0x1400151e5  test    dword ptr [rbx+3Ch], 2000000h
0x1400151ec  mov     [rbx+110h], r14
0x1400151f3  jz      short loc_140015203
0x1400151f5  lea     esi, [r14+1]
0x1400151f9  mov     r14, [rbx+20h]
0x1400151fd  add     [rbx+190h], esi
0x140015203  mov     dl, al; NewIrql
0x140015205  mov     rcx, rdi; SpinLock
0x140015208  call    cs:__imp_KeReleaseSpinLock
0x14001520f  nop     dword ptr [rax+rax+00h]
0x140015214  test    sil, sil
0x140015217  jz      short loc_14001523E
0x140015219  mov     [rsp+88h+var_50], 0
0x14001521e  lea     r8, SendPayloadAck
0x140015225  xor     r9d, r9d
0x140015228  mov     [rsp+88h+var_68], 0
0x140015231  mov     rdx, rbx
0x140015234  mov     rcx, r14
0x140015237  call    ScheduleTunnelWork
0x14001523c  jmp     short loc_14001527C
0x14001523e  mov     rcx, rbx
0x140015241  call    DereferenceCall
0x140015246  jmp     short loc_14001527C
0x140015248  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001524f  nop     dword ptr [rax+rax+00h]
0x140015254  mov     [rbx+30h], al
0x140015257  cmp     rbp, [rbx+110h]
0x14001525e  jnz     short loc_14001526B
0x140015260  mov     qword ptr [rbx+110h], 0
0x14001526b  mov     dl, al; NewIrql
0x14001526d  mov     rcx, rdi; SpinLock
0x140015270  call    cs:__imp_KeReleaseSpinLock
0x140015277  nop     dword ptr [rax+rax+00h]
0x14001527c  lea     rcx, [r15+240h]; Lookaside
0x140015283  mov     rdx, rbp; Entry
0x140015286  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001528d  nop     dword ptr [rax+rax+00h]
0x140015292  mov     rcx, rbx
0x140015295  call    DereferenceVc
0x14001529a  add     rsp, 58h
0x14001529e  pop     r15
0x1400152a0  pop     r14
0x1400152a2  pop     rdi
0x1400152a3  pop     rsi
0x1400152a4  pop     rbp
0x1400152a5  pop     rbx
0x1400152a6  retn
```

# ReceivePayloadPassive

- ea: `0x14001af80`
- end: `0x14001b1cc`
- name: `ReceivePayloadPassive`
- size: `588`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1400012e0`
- `0x140001870`
- `0x1400031ec`
- `0x14001af80`
- `0x14001b830`
- `0x14001b8a0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001b01a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b050`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b0ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b12b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b1b3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b01a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b050`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b0ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b12b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b1b3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b0a3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b0a3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001afbe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b02a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b0b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001afbe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b02a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b0b6`
- `NDIS!NdisFreeNetBufferList` at `0x14001b173`
- `NDIS!NdisFreeNetBufferList` at `0x14001b173`
- `NDIS!NdisFreeIoWorkItem` at `0x14001afab`
- `NDIS!NdisFreeIoWorkItem` at `0x14001afab`

## pseudocode

```c
__int64 __fastcall ReceivePayloadPassive(__int64 a1, void *a2)
{
  __int64 v2; // r12
  int v4; // ebp
  __int64 v5; // r13
  void **v6; // r14
  void *v7; // rbx
  void **v8; // rax
  KIRQL v9; // al
  bool v10; // zf
  KSPIN_LOCK *v11; // rcx
  char v12; // di
  KIRQL v13; // dl

  v2 = *(_QWORD *)(a1 + 32);
  v4 = 50;
  v5 = *(_QWORD *)(v2 + 24);
  NdisFreeIoWorkItem(a2);
  v6 = (void **)(a1 + 440);
  *(_BYTE *)(a1 + 472) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 464));
  do
  {
    v7 = *v6;
    if ( *v6 == v6 )
      break;
    if ( *((void ***)v7 + 1) != v6 || (v8 = *(void ***)v7, *(void **)(*(_QWORD *)v7 + 8LL) != v7) )
      __fastfail(3u);
    *v6 = v8;
    v8[1] = v6;
    --v4;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 464), *(_BYTE *)(a1 + 472));
    v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
    v10 = (*(_DWORD *)(a1 + 60) & 0x200) == 0;
    v11 = (KSPIN_LOCK *)(a1 + 72);
    *(_BYTE *)(a1 + 80) = v9;
    if ( v10 )
    {
      KeReleaseSpinLock(v11, v9);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids, a1);
      }
LABEL_14:
      NdisFreeNetBufferList(*((PNET_BUFFER_LIST *)v7 + 9));
      goto LABEL_7;
    }
    ++*(_DWORD *)(a1 + 64);
    KeReleaseSpinLock(v11, v9);
    v12 = ReceivePayload(
            v5,
            v2,
            a1,
            *((struct _NET_BUFFER_LIST **)v7 + 9),
            *((_DWORD *)v7 + 16),
            *((_DWORD *)v7 + 17),
            (__int64)v7 + 16);
    DereferenceCall(a1);
    if ( v12 )
      goto LABEL_14;
LABEL_7:
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v5 + 1216), v7);
    *(_BYTE *)(a1 + 472) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 464));
  }
  while ( v4 );
  if ( *v6 == v6 || (unsigned int)ScheduleWork(v5, &ReceivePayloadPassive, a1) )
  {
    v13 = *(_BYTE *)(a1 + 472);
    *(_BYTE *)(a1 + 456) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 464), v13);
    DereferenceAdapter(v5);
    return DereferenceCall(a1);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 464), *(_BYTE *)(a1 + 472));
    return DereferenceAdapter(v5);
  }
}

```

## disassembly

```asm
0x14001af80  mov     [rsp+arg_8], rbx
0x14001af85  mov     [rsp+arg_10], rbp
0x14001af8a  push    rsi
0x14001af8b  push    r12
0x14001af8d  push    r13
0x14001af8f  push    r14
0x14001af91  push    r15
0x14001af93  sub     rsp, 40h
0x14001af97  mov     r12, [rcx+20h]
0x14001af9b  mov     rsi, rcx
0x14001af9e  mov     rcx, rdx; NdisIoWorkItemHandle
0x14001afa1  mov     ebp, 32h ; '2'
0x14001afa6  mov     r13, [r12+18h]
0x14001afab  call    cs:__imp_NdisFreeIoWorkItem
0x14001afb2  nop     dword ptr [rax+rax+00h]
0x14001afb7  lea     rcx, [rsi+1D0h]; SpinLock
0x14001afbe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001afc5  nop     dword ptr [rax+rax+00h]
0x14001afca  lea     r14, [rsi+1B8h]
0x14001afd1  mov     [rsp+68h+arg_0], rdi
0x14001afd6  mov     [rsi+1D8h], al
0x14001afdc  nop     dword ptr [rax+00h]
0x14001afe0  mov     rbx, [r14]
0x14001afe3  cmp     rbx, r14
0x14001afe6  jz      loc_14001B0D0
0x14001afec  cmp     [rbx+8], r14
0x14001aff0  jnz     loc_14001B184
0x14001aff6  mov     rax, [rbx]
0x14001aff9  cmp     [rax+8], rbx
0x14001affd  jnz     loc_14001B184
0x14001b003  mov     [r14], rax
0x14001b006  lea     rcx, [rsi+1D0h]; SpinLock
0x14001b00d  mov     [rax+8], r14
0x14001b011  dec     ebp
0x14001b013  movzx   edx, byte ptr [rsi+1D8h]; NewIrql
0x14001b01a  call    cs:__imp_KeReleaseSpinLock
0x14001b021  nop     dword ptr [rax+rax+00h]
0x14001b026  lea     rcx, [rsi+48h]; SpinLock
0x14001b02a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b031  nop     dword ptr [rax+rax+00h]
0x14001b036  test    dword ptr [rsi+3Ch], 200h
0x14001b03d  lea     rcx, [rsi+48h]; SpinLock
0x14001b041  mov     [rsi+50h], al
0x14001b044  movzx   edx, al; NewIrql
0x14001b047  jz      loc_14001B12B
0x14001b04d  inc     dword ptr [rsi+40h]
0x14001b050  call    cs:__imp_KeReleaseSpinLock
0x14001b057  nop     dword ptr [rax+rax+00h]
0x14001b05c  mov     r9, [rbx+48h]
0x14001b060  lea     rax, [rbx+10h]
0x14001b064  mov     [rsp+68h+var_38], rax
0x14001b069  mov     r8, rsi
0x14001b06c  mov     eax, [rbx+44h]
0x14001b06f  mov     rdx, r12
0x14001b072  mov     [rsp+68h+var_40], eax
0x14001b076  mov     rcx, r13
0x14001b079  mov     eax, [rbx+40h]
0x14001b07c  mov     [rsp+68h+var_48], eax
0x14001b080  call    ReceivePayload
0x14001b085  mov     rcx, rsi
0x14001b088  movzx   edi, al
0x14001b08b  call    DereferenceCall
0x14001b090  test    dil, dil
0x14001b093  jnz     loc_14001B16F
0x14001b099  lea     rcx, [r13+4C0h]; Lookaside
0x14001b0a0  mov     rdx, rbx; Entry
0x14001b0a3  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001b0aa  nop     dword ptr [rax+rax+00h]
0x14001b0af  lea     rcx, [rsi+1D0h]; SpinLock
0x14001b0b6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b0bd  nop     dword ptr [rax+rax+00h]
0x14001b0c2  mov     [rsi+1D8h], al
0x14001b0c8  test    ebp, ebp
0x14001b0ca  jnz     loc_14001AFE0
0x14001b0d0  cmp     [r14], r14
0x14001b0d3  jnz     loc_14001B18B
0x14001b0d9  movzx   edx, byte ptr [rsi+1D8h]; NewIrql
0x14001b0e0  lea     rcx, [rsi+1D0h]; SpinLock
0x14001b0e7  mov     byte ptr [rsi+1C8h], 0
0x14001b0ee  call    cs:__imp_KeReleaseSpinLock
0x14001b0f5  nop     dword ptr [rax+rax+00h]
0x14001b0fa  mov     rcx, r13
0x14001b0fd  call    DereferenceAdapter
0x14001b102  mov     rcx, rsi
0x14001b105  call    DereferenceCall
0x14001b10a  mov     rdi, [rsp+68h+arg_0]
0x14001b10f  mov     rbx, [rsp+68h+arg_8]
0x14001b114  mov     rbp, [rsp+68h+arg_10]
0x14001b11c  add     rsp, 40h
0x14001b120  pop     r15
0x14001b122  pop     r14
0x14001b124  pop     r13
0x14001b126  pop     r12
0x14001b128  pop     rsi
0x14001b129  retn
0x14001b12b  call    cs:__imp_KeReleaseSpinLock
0x14001b132  nop     dword ptr [rax+rax+00h]
0x14001b137  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b13e  lea     rax, WPP_GLOBAL_Control
0x14001b145  cmp     rcx, rax
0x14001b148  jz      short loc_14001B16F
0x14001b14a  mov     eax, [rcx+2Ch]
0x14001b14d  test    al, 20h
0x14001b14f  jz      short loc_14001B16F
0x14001b151  cmp     byte ptr [rcx+29h], 1
0x14001b155  jb      short loc_14001B16F
0x14001b157  mov     rcx, [rcx+18h]
0x14001b15b  lea     r8, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids
0x14001b162  mov     edx, 15h
0x14001b167  mov     r9, rsi
0x14001b16a  call    WPP_SF_q
0x14001b16f  mov     rcx, [rbx+48h]; NetBufferList
0x14001b173  call    cs:__imp_NdisFreeNetBufferList
0x14001b17a  nop     dword ptr [rax+rax+00h]
0x14001b17f  jmp     loc_14001B099
0x14001b184  mov     ecx, 3
0x14001b189  int     29h; Win8: RtlFailFast(ecx)
0x14001b18b  mov     r8, rsi
0x14001b18e  lea     rdx, ReceivePayloadPassive
0x14001b195  mov     rcx, r13
0x14001b198  call    ScheduleWork
0x14001b19d  test    eax, eax
0x14001b19f  jnz     loc_14001B0D9
0x14001b1a5  movzx   edx, byte ptr [rsi+1D8h]; NewIrql
0x14001b1ac  lea     rcx, [rsi+1D0h]; SpinLock
0x14001b1b3  call    cs:__imp_KeReleaseSpinLock
0x14001b1ba  nop     dword ptr [rax+rax+00h]
0x14001b1bf  mov     rcx, r13
0x14001b1c2  call    DereferenceAdapter
0x14001b1c7  jmp     loc_14001B10A
```

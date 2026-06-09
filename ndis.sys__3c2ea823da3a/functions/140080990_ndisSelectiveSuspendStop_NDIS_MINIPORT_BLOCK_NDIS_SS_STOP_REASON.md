# ndisSelectiveSuspendStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)

- ea: `0x140080990`
- end: `0x140080d12`
- name: `?ndisSelectiveSuspendStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z`
- size: `898`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: ``

## callers

- `0x140041c50`
- `0x14007f7c0`
- `0x1400ae010`
- `0x14015dd60`
- `0x14016b6b0`
- `0x1401747a8`

## callees

- `0x140011570`
- `0x140012580`
- `0x14001d350`
- `0x14003a010`
- `0x14004d890`
- `0x140070bb0`
- `0x140080990`
- `0x1401564e0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140080c38`
- `ntoskrnl!KeWaitForSingleObject` at `0x140080c38`
- `ntoskrnl!KeReadStateEvent` at `0x140080b9f`
- `ntoskrnl!KeReadStateEvent` at `0x140080b9f`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140080caf`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140080caf`
- `ntoskrnl!KeClearEvent` at `0x140080a32`
- `ntoskrnl!KeClearEvent` at `0x140080a32`
- `ntoskrnl!KeCancelTimer` at `0x140080c62`
- `ntoskrnl!KeCancelTimer` at `0x140080c62`
- `ntoskrnl!KeReleaseSpinLock` at `0x140080bba`
- `ntoskrnl!KeReleaseSpinLock` at `0x140080c96`
- `ntoskrnl!KeReleaseSpinLock` at `0x140080cf6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140080bba`
- `ntoskrnl!KeReleaseSpinLock` at `0x140080c96`
- `ntoskrnl!KeReleaseSpinLock` at `0x140080cf6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400809b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140080cda`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400809b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140080cda`

## pseudocode

```c
void __fastcall ndisSelectiveSuspendStop(struct _NDIS_MINIPORT_BLOCK *a1, unsigned int a2)
{
  struct _NDIS_SELECTIVE_SUSPEND *SelectiveSuspend; // rbx
  char v5; // bp
  int v6; // r15d
  KIRQL v7; // r14
  int v8; // edx
  unsigned __int8 IsPowerReferencedForSelectiveSuspend; // r12
  unsigned int v10; // eax
  __int64 v11; // rax
  unsigned __int8 v12; // dl
  int v13; // eax
  char v14; // bp
  KIRQL v15; // dl
  KIRQL v16; // al

  SelectiveSuspend = a1->SelectiveSuspend;
  v5 = 0;
  v6 = a1->Flags & 0x80;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SelectiveSuspend);
  IsPowerReferencedForSelectiveSuspend = ndisIsPowerReferencedForSelectiveSuspend(SelectiveSuspend, v6 != 0);
  if ( v6
    && !*((_DWORD *)SelectiveSuspend + 128)
    && !*((_DWORD *)SelectiveSuspend + 129)
    && !*((_DWORD *)SelectiveSuspend + 132)
    && !*((_DWORD *)SelectiveSuspend + 133)
    && !*((_DWORD *)SelectiveSuspend + 130)
    && !*((_DWORD *)SelectiveSuspend + 131)
    && !*((_DWORD *)SelectiveSuspend + 144)
    && !*((_DWORD *)SelectiveSuspend + 127) )
  {
    v5 = 1;
    KeClearEvent((PRKEVENT)((char *)SelectiveSuspend + 272));
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v8,
      15,
      34,
      (struct _GUID *)&WPP_63e371e5a248373aa5c809d99c379eef_Traceguids,
      (char)a1,
      a2);
  }
  switch ( a2 )
  {
    case 1u:
      *((_DWORD *)SelectiveSuspend + 127) |= 1u;
      goto LABEL_25;
    case 2u:
      *((_DWORD *)SelectiveSuspend + 127) |= 2u;
      goto LABEL_25;
    case 3u:
      *((_DWORD *)SelectiveSuspend + 127) |= 4u;
      *((_DWORD *)SelectiveSuspend + 126) |= 0x400u;
      goto LABEL_25;
    case 4u:
      *((_DWORD *)SelectiveSuspend + 127) |= 8u;
      goto LABEL_25;
    case 5u:
      *((_DWORD *)SelectiveSuspend + 127) |= 0x10u;
      goto LABEL_25;
    case 6u:
      *((_DWORD *)SelectiveSuspend + 127) |= 0x20u;
      goto LABEL_25;
    case 7u:
      *((_DWORD *)SelectiveSuspend + 127) |= 0x40u;
      goto LABEL_25;
    case 8u:
      ++*((_DWORD *)SelectiveSuspend + 134);
      *((_DWORD *)SelectiveSuspend + 127) |= 0x80u;
      goto LABEL_25;
    case 0xBu:
      *((_DWORD *)SelectiveSuspend + 127) |= 0x400u;
      goto LABEL_25;
    case 0xDu:
      ++*((_DWORD *)SelectiveSuspend + 135);
      *((_DWORD *)SelectiveSuspend + 127) |= 0x1000u;
      goto LABEL_25;
    default:
      if ( !a2 )
        goto LABEL_37;
LABEL_25:
      if ( IsPowerReferencedForSelectiveSuspend )
      {
        *((_DWORD *)SelectiveSuspend + 159) = a2;
        *((_DWORD *)SelectiveSuspend + 160) = 0;
      }
      else
      {
        *((_DWORD *)SelectiveSuspend + 157) = a2;
        *((_DWORD *)SelectiveSuspend + 158) = 0;
      }
      if ( a2 == 7 )
        goto LABEL_37;
      if ( a2 <= 0xF )
      {
        v10 = a2;
      }
      else
      {
        if ( a2 - 33 > 0x20 )
          goto LABEL_37;
        v10 = a2 - 17;
      }
      if ( v10 <= 0x30 )
      {
        v11 = 16 * ((int)v10 + 46LL);
        *(_DWORD *)((char *)SelectiveSuspend + v11 + 4) = a2;
        if ( IsPowerReferencedForSelectiveSuspend )
          ++*(_WORD *)((char *)SelectiveSuspend + v11 + 2);
        else
          ++*(_WORD *)((char *)SelectiveSuspend + v11);
      }
LABEL_37:
      if ( !v6 )
      {
        v13 = *((_DWORD *)SelectiveSuspend + 126);
        if ( (v13 & 1) != 0 )
        {
          KeCancelTimer((PKTIMER)((char *)SelectiveSuspend + 16));
          *((_DWORD *)SelectiveSuspend + 126) &= ~1u;
          v14 = 1;
          v13 = *((_DWORD *)SelectiveSuspend + 126);
        }
        else
        {
          v14 = 0;
        }
        if ( (v13 & 0x200) == 0 )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)SelectiveSuspend, v7);
          ndisCancelWaitWake(a1);
          if ( v14 )
          {
            KeFlushQueuedDpcs();
            ndisWaitForKernelObject((char *)SelectiveSuspend + 152);
          }
          ndisCancelIdleRequestSync(a1, a2, 0, 1u);
          v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SelectiveSuspend);
          *((_DWORD *)SelectiveSuspend + 126) |= 0x200u;
          v15 = v16;
          goto LABEL_55;
        }
LABEL_51:
        v15 = v7;
LABEL_55:
        KeReleaseSpinLock((PKSPIN_LOCK)SelectiveSuspend, v15);
        return;
      }
      if ( !v5 && KeReadStateEvent((PRKEVENT)((char *)SelectiveSuspend + 272)) )
        goto LABEL_51;
      KeReleaseSpinLock((PKSPIN_LOCK)SelectiveSuspend, v7);
      if ( a2 == 6 )
      {
LABEL_43:
        ndisWdfAcquirePowerReferenceHelper(a1, 0, 0);
        ndisWdfSelectiveSuspendResumeOperations(a1, v12, 1u);
        return;
      }
      if ( a2 == 5 )
      {
        if ( !v5 )
          return;
        goto LABEL_43;
      }
      if ( v5 )
        ndisWdfAcquirePowerReferenceHelper(a1, 1u, 0);
      else
        KeWaitForSingleObject((char *)SelectiveSuspend + 272, Executive, 0, 0, 0);
      return;
  }
}

```

## disassembly

```asm
0x140080990  push    rbx
0x140080992  push    rbp
0x140080993  push    rsi
0x140080994  push    rdi
0x140080995  push    r12
0x140080997  push    r14
0x140080999  push    r15
0x14008099b  sub     rsp, 40h
0x14008099f  mov     rbx, [rcx+1160h]
0x1400809a6  mov     rsi, rcx
0x1400809a9  mov     r15d, [rcx+78h]
0x1400809ad  mov     edi, edx
0x1400809af  mov     rcx, rbx; SpinLock
0x1400809b2  xor     bpl, bpl
0x1400809b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400809bc  nop     dword ptr [rax+rax+00h]
0x1400809c1  and     r15d, 80h
0x1400809c8  mov     rcx, rbx; struct _NDIS_SELECTIVE_SUSPEND *
0x1400809cb  movzx   r14d, al
0x1400809cf  setnz   dl; unsigned __int8
0x1400809d2  call    ?ndisIsPowerReferencedForSelectiveSuspend@@YAEPEAU_NDIS_SELECTIVE_SUSPEND@@E@Z; ndisIsPowerReferencedForSelectiveSuspend(_NDIS_SELECTIVE_SUSPEND *,uchar)
0x1400809d7  movzx   r12d, al
0x1400809db  test    r15d, r15d
0x1400809de  jz      short loc_140080A3E
0x1400809e0  cmp     dword ptr [rbx+200h], 0
0x1400809e7  jnz     short loc_140080A3E
0x1400809e9  cmp     dword ptr [rbx+204h], 0
0x1400809f0  jnz     short loc_140080A3E
0x1400809f2  cmp     dword ptr [rbx+210h], 0
0x1400809f9  jnz     short loc_140080A3E
0x1400809fb  cmp     dword ptr [rbx+214h], 0
0x140080a02  jnz     short loc_140080A3E
0x140080a04  cmp     dword ptr [rbx+208h], 0
0x140080a0b  jnz     short loc_140080A3E
0x140080a0d  cmp     dword ptr [rbx+20Ch], 0
0x140080a14  jnz     short loc_140080A3E
0x140080a16  cmp     dword ptr [rbx+240h], 0
0x140080a1d  jnz     short loc_140080A3E
0x140080a1f  cmp     dword ptr [rbx+1FCh], 0
0x140080a26  jnz     short loc_140080A3E
0x140080a28  lea     rcx, [rbx+110h]; Event
0x140080a2f  mov     bpl, 1
0x140080a32  call    cs:__imp_KeClearEvent
0x140080a39  nop     dword ptr [rax+rax+00h]
0x140080a3e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140080a45  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140080a4c  jz      short loc_140080A81
0x140080a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140080a55  lea     rax, WPP_63e371e5a248373aa5c809d99c379eef_Traceguids
0x140080a5c  mov     dword ptr [rsp+78h+var_48], edi; char
0x140080a60  mov     r9d, 22h ; '"'; int
0x140080a66  mov     qword ptr [rsp+78h+var_50], rsi; char
0x140080a6b  mov     r8d, 0Fh; int
0x140080a71  mov     dl, 4; int
0x140080a73  mov     [rsp+78h+Timeout], rax; struct _GUID *
0x140080a78  mov     rcx, [rcx+40h]; int
0x140080a7c  call    WPP_RECORDER_SF_qL
0x140080a81  lea     eax, [rdi-1]; switch 13 cases
0x140080a84  cmp     eax, 0Ch
0x140080a87  ja      def_140080AA0; jumptable 0000000140080AA0 default case, cases 9,10,12
0x140080a8d  lea     rdx, cs:140000000h
0x140080a94  cdqe
0x140080a96  mov     ecx, ds:(jpt_140080AA0 - 140000000h)[rdx+rax*4]
0x140080a9d  add     rcx, rdx
0x140080aa0  jmp     rcx; switch jump
0x140080aa6  or      dword ptr [rbx+1FCh], 1; jumptable 0000000140080AA0 case 1
0x140080aad  jmp     short loc_140080B23
0x140080aaf  or      dword ptr [rbx+1FCh], 2; jumptable 0000000140080AA0 case 2
0x140080ab6  jmp     short loc_140080B23
0x140080ab8  or      dword ptr [rbx+1FCh], 4; jumptable 0000000140080AA0 case 3
0x140080abf  or      dword ptr [rbx+1F8h], 400h
0x140080ac9  jmp     short loc_140080B23
0x140080acb  or      dword ptr [rbx+1FCh], 8; jumptable 0000000140080AA0 case 4
0x140080ad2  jmp     short loc_140080B23
0x140080ad4  or      dword ptr [rbx+1FCh], 10h; jumptable 0000000140080AA0 case 5
0x140080adb  jmp     short loc_140080B23
0x140080add  or      dword ptr [rbx+1FCh], 20h; jumptable 0000000140080AA0 case 6
0x140080ae4  jmp     short loc_140080B23
0x140080ae6  or      dword ptr [rbx+1FCh], 40h; jumptable 0000000140080AA0 case 7
0x140080aed  jmp     short loc_140080B23
0x140080aef  inc     dword ptr [rbx+218h]; jumptable 0000000140080AA0 case 8
0x140080af5  or      dword ptr [rbx+1FCh], 80h
0x140080aff  jmp     short loc_140080B23
0x140080b01  or      dword ptr [rbx+1FCh], 400h; jumptable 0000000140080AA0 case 11
0x140080b0b  jmp     short loc_140080B23
0x140080b0d  inc     dword ptr [rbx+21Ch]; jumptable 0000000140080AA0 case 13
0x140080b13  or      dword ptr [rbx+1FCh], 1000h
0x140080b1d  jmp     short loc_140080B23
0x140080b1f  test    edi, edi; jumptable 0000000140080AA0 default case, cases 9,10,12
0x140080b21  jz      short loc_140080B8A
0x140080b23  test    r12b, r12b
0x140080b26  jnz     short loc_140080B3A
0x140080b28  mov     [rbx+274h], edi
0x140080b2e  mov     dword ptr [rbx+278h], 0
0x140080b38  jmp     short loc_140080B4A
0x140080b3a  mov     [rbx+27Ch], edi
0x140080b40  mov     dword ptr [rbx+280h], 0
0x140080b4a  cmp     edi, 7
0x140080b4d  jz      short loc_140080B8A
0x140080b4f  cmp     edi, 0Fh
0x140080b52  jbe     short loc_140080B61
0x140080b54  lea     eax, [rdi-21h]
0x140080b57  cmp     eax, 20h ; ' '
0x140080b5a  ja      short loc_140080B8A
0x140080b5c  lea     eax, [rdi-11h]
0x140080b5f  jmp     short loc_140080B63
0x140080b61  mov     eax, edi
0x140080b63  test    eax, eax
0x140080b65  js      short loc_140080B8A
0x140080b67  cmp     eax, 31h ; '1'
0x140080b6a  jnb     short loc_140080B8A
0x140080b6c  cdqe
0x140080b6e  add     rax, 2Eh ; '.'
0x140080b72  shl     rax, 4
0x140080b76  mov     [rax+rbx+4], edi
0x140080b7a  test    r12b, r12b
0x140080b7d  jnz     short loc_140080B85
0x140080b7f  inc     word ptr [rax+rbx]
0x140080b83  jmp     short loc_140080B8A
0x140080b85  inc     word ptr [rax+rbx+2]
0x140080b8a  test    r15d, r15d
0x140080b8d  jz      loc_140080C54
0x140080b93  test    bpl, bpl
0x140080b96  jnz     short loc_140080BB3
0x140080b98  lea     rcx, [rbx+110h]; Event
0x140080b9f  call    cs:__imp_KeReadStateEvent
0x140080ba6  nop     dword ptr [rax+rax+00h]
0x140080bab  test    eax, eax
0x140080bad  jnz     loc_140080C89
0x140080bb3  movzx   edx, r14b; NewIrql
0x140080bb7  mov     rcx, rbx; SpinLock
0x140080bba  call    cs:__imp_KeReleaseSpinLock
0x140080bc1  nop     dword ptr [rax+rax+00h]
0x140080bc6  cmp     edi, 6
0x140080bc9  jz      short loc_140080BD9
0x140080bcb  cmp     edi, 5
0x140080bce  jnz     short loc_140080C01
0x140080bd0  test    bpl, bpl
0x140080bd3  jz      loc_140080D02
0x140080bd9  xor     r8d, r8d; unsigned __int8
0x140080bdc  xor     edx, edx; unsigned __int8
0x140080bde  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140080be1  call    ?ndisWdfAcquirePowerReferenceHelper@@YAXPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisWdfAcquirePowerReferenceHelper(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x140080be6  mov     r8b, 1; unsigned __int8
0x140080be9  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140080bec  call    ?ndisWdfSelectiveSuspendResumeOperations@@YAXPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisWdfSelectiveSuspendResumeOperations(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x140080bf1  add     rsp, 40h
0x140080bf5  pop     r15
0x140080bf7  pop     r14
0x140080bf9  pop     r12
0x140080bfb  pop     rdi
0x140080bfc  pop     rsi
0x140080bfd  pop     rbp
0x140080bfe  pop     rbx
0x140080bff  retn
0x140080c01  xor     r8d, r8d; unsigned __int8
0x140080c04  test    bpl, bpl
0x140080c07  jz      short loc_140080C23
0x140080c09  mov     dl, 1; unsigned __int8
0x140080c0b  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140080c0e  call    ?ndisWdfAcquirePowerReferenceHelper@@YAXPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisWdfAcquirePowerReferenceHelper(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x140080c13  add     rsp, 40h
0x140080c17  pop     r15
0x140080c19  pop     r14
0x140080c1b  pop     r12
0x140080c1d  pop     rdi
0x140080c1e  pop     rsi
0x140080c1f  pop     rbp
0x140080c20  pop     rbx
0x140080c21  retn
0x140080c23  lea     rcx, [rbx+110h]; Object
0x140080c2a  mov     [rsp+78h+Timeout], 0; Timeout
0x140080c33  xor     r9d, r9d; Alertable
0x140080c36  xor     edx, edx; WaitReason
0x140080c38  call    cs:__imp_KeWaitForSingleObject
0x140080c3f  nop     dword ptr [rax+rax+00h]
0x140080c44  add     rsp, 40h
0x140080c48  pop     r15
0x140080c4a  pop     r14
0x140080c4c  pop     r12
0x140080c4e  pop     rdi
0x140080c4f  pop     rsi
0x140080c50  pop     rbp
0x140080c51  pop     rbx
0x140080c52  retn
0x140080c54  mov     eax, [rbx+1F8h]
0x140080c5a  test    al, 1
0x140080c5c  jz      short loc_140080C80
0x140080c5e  lea     rcx, [rbx+10h]; PKTIMER
0x140080c62  call    cs:__imp_KeCancelTimer
0x140080c69  nop     dword ptr [rax+rax+00h]
0x140080c6e  and     dword ptr [rbx+1F8h], 0FFFFFFFEh
0x140080c75  mov     bpl, 1
0x140080c78  mov     eax, [rbx+1F8h]
0x140080c7e  jmp     short loc_140080C83
0x140080c80  xor     bpl, bpl
0x140080c83  bt      eax, 9
0x140080c87  jnb     short loc_140080C8F
0x140080c89  movzx   edx, r14b
0x140080c8d  jmp     short loc_140080CF3
0x140080c8f  movzx   edx, r14b; NewIrql
0x140080c93  mov     rcx, rbx; SpinLock
0x140080c96  call    cs:__imp_KeReleaseSpinLock
0x140080c9d  nop     dword ptr [rax+rax+00h]
0x140080ca2  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140080ca5  call    ?ndisCancelWaitWake@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisCancelWaitWake(_NDIS_MINIPORT_BLOCK *)
0x140080caa  test    bpl, bpl
0x140080cad  jz      short loc_140080CC7
0x140080caf  call    cs:__imp_KeFlushQueuedDpcs
0x140080cb6  nop     dword ptr [rax+rax+00h]
0x140080cbb  lea     rcx, [rbx+98h]; void *
0x140080cc2  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x140080cc7  mov     r9b, 1; unsigned __int8
0x140080cca  xor     r8d, r8d; unsigned int
0x140080ccd  mov     edx, edi; char
0x140080ccf  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140080cd2  call    ?ndisCancelIdleRequestSync@@YAXPEAU_NDIS_MINIPORT_BLOCK@@KKE@Z; ndisCancelIdleRequestSync(_NDIS_MINIPORT_BLOCK *,ulong,ulong,uchar)
0x140080cd7  mov     rcx, rbx; SpinLock
0x140080cda  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140080ce1  nop     dword ptr [rax+rax+00h]
0x140080ce6  or      dword ptr [rbx+1F8h], 200h
0x140080cf0  movzx   edx, al; NewIrql
0x140080cf3  mov     rcx, rbx; SpinLock
0x140080cf6  call    cs:__imp_KeReleaseSpinLock
0x140080cfd  nop     dword ptr [rax+rax+00h]
0x140080d02  add     rsp, 40h
0x140080d06  pop     r15
0x140080d08  pop     r14
0x140080d0a  pop     r12
0x140080d0c  pop     rdi
0x140080d0d  pop     rsi
0x140080d0e  pop     rbp
0x140080d0f  pop     rbx
0x140080d10  retn
```

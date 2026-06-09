# ndisSelectiveSuspendStopWdf(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)

- ea: `0x1400c26f4`
- end: `0x1400c2930`
- name: `?ndisSelectiveSuspendStopWdf@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z`
- size: `572`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x140041c50`
- `0x14007f7c0`
- `0x1400ae010`
- `0x14015dd60`
- `0x14016b6b0`
- `0x1401747a8`

## callees

- `0x140012180`
- `0x140012580`
- `0x14001d350`
- `0x14004d890`
- `0x1400c26f4`
- `0x1400c2e64`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400c2922`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c2922`
- `ntoskrnl!KeReadStateEvent` at `0x1400c2899`
- `ntoskrnl!KeReadStateEvent` at `0x1400c2899`
- `ntoskrnl!KeClearEvent` at `0x1400c2784`
- `ntoskrnl!KeClearEvent` at `0x1400c2784`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c28af`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c28c3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c28af`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c28c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c2713`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c2713`

## pseudocode

```c
void __fastcall ndisSelectiveSuspendStopWdf(struct _NDIS_MINIPORT_BLOCK *a1, int a2)
{
  struct _NDIS_SELECTIVE_SUSPEND *SelectiveSuspend; // rbx
  char v5; // si
  KIRQL v6; // r14
  __int64 v7; // rdx
  bool v8; // r15

  SelectiveSuspend = a1->SelectiveSuspend;
  v5 = 0;
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SelectiveSuspend);
  v8 = ndisIsPowerReferencedForSelectiveSuspend(SelectiveSuspend, 1u) == 0;
  if ( !*((_DWORD *)SelectiveSuspend + 128)
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
    LOBYTE(v7) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v7,
      15,
      35,
      (struct _GUID *)&WPP_63e371e5a248373aa5c809d99c379eef_Traceguids,
      (char)a1,
      a2);
  }
  if ( a2 > 6 )
  {
    switch ( a2 )
    {
      case 7:
        *((_DWORD *)SelectiveSuspend + 127) |= 0x40u;
        break;
      case 8:
        ++*((_DWORD *)SelectiveSuspend + 134);
        *((_DWORD *)SelectiveSuspend + 127) |= 0x80u;
        break;
      case 11:
        *((_DWORD *)SelectiveSuspend + 127) |= 0x400u;
        break;
      case 13:
        ++*((_DWORD *)SelectiveSuspend + 135);
        *((_DWORD *)SelectiveSuspend + 127) |= 0x1000u;
        break;
    }
  }
  else
  {
    switch ( a2 )
    {
      case 6:
        *((_DWORD *)SelectiveSuspend + 127) |= 0x20u;
        break;
      case 1:
        *((_DWORD *)SelectiveSuspend + 127) |= 1u;
        break;
      case 2:
        *((_DWORD *)SelectiveSuspend + 127) |= 2u;
        break;
      case 3:
        *((_DWORD *)SelectiveSuspend + 127) |= 4u;
        *((_DWORD *)SelectiveSuspend + 126) |= 0x400u;
        break;
      case 4:
        *((_DWORD *)SelectiveSuspend + 127) |= 8u;
        break;
      case 5:
        *((_DWORD *)SelectiveSuspend + 127) |= 0x10u;
        break;
    }
  }
  LOBYTE(v7) = v8;
  ndisSelectiveSuspendSetResumeBusyReason(SelectiveSuspend, v7, (unsigned int)a2, 0);
  if ( !v5 && KeReadStateEvent((PRKEVENT)((char *)SelectiveSuspend + 272)) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SelectiveSuspend, v6);
    return;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SelectiveSuspend, v6);
  if ( a2 == 6 )
  {
LABEL_39:
    ndisWdfAcquireAsyncPowerRefAndResume(a1);
    return;
  }
  if ( ((a2 - 3) & 0xFFFFFFFD) == 0 )
  {
    if ( !v5 )
      return;
    goto LABEL_39;
  }
  if ( v5 )
    ndisWdfAcquirePowerReferenceHelper(a1, 1u, 0);
  else
    KeWaitForSingleObject((char *)SelectiveSuspend + 272, Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x1400c26f4  push    rbx
0x1400c26f6  push    rbp
0x1400c26f7  push    rsi
0x1400c26f8  push    rdi
0x1400c26f9  push    r14
0x1400c26fb  push    r15
0x1400c26fd  sub     rsp, 48h
0x1400c2701  mov     rbx, [rcx+1160h]
0x1400c2708  mov     rbp, rcx
0x1400c270b  mov     rcx, rbx; SpinLock
0x1400c270e  mov     edi, edx
0x1400c2710  xor     sil, sil
0x1400c2713  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400c271a  nop     dword ptr [rax+rax+00h]
0x1400c271f  mov     dl, 1; unsigned __int8
0x1400c2721  mov     rcx, rbx; struct _NDIS_SELECTIVE_SUSPEND *
0x1400c2724  mov     r14b, al
0x1400c2727  call    ?ndisIsPowerReferencedForSelectiveSuspend@@YAEPEAU_NDIS_SELECTIVE_SUSPEND@@E@Z; ndisIsPowerReferencedForSelectiveSuspend(_NDIS_SELECTIVE_SUSPEND *,uchar)
0x1400c272c  test    al, al
0x1400c272e  setz    r15b
0x1400c2732  cmp     dword ptr [rbx+200h], 0
0x1400c2739  jnz     short loc_1400C2790
0x1400c273b  cmp     dword ptr [rbx+204h], 0
0x1400c2742  jnz     short loc_1400C2790
0x1400c2744  cmp     dword ptr [rbx+210h], 0
0x1400c274b  jnz     short loc_1400C2790
0x1400c274d  cmp     dword ptr [rbx+214h], 0
0x1400c2754  jnz     short loc_1400C2790
0x1400c2756  cmp     dword ptr [rbx+208h], 0
0x1400c275d  jnz     short loc_1400C2790
0x1400c275f  cmp     dword ptr [rbx+20Ch], 0
0x1400c2766  jnz     short loc_1400C2790
0x1400c2768  cmp     dword ptr [rbx+240h], 0
0x1400c276f  jnz     short loc_1400C2790
0x1400c2771  cmp     dword ptr [rbx+1FCh], 0
0x1400c2778  jnz     short loc_1400C2790
0x1400c277a  lea     rcx, [rbx+110h]; Event
0x1400c2781  mov     sil, 1
0x1400c2784  call    cs:__imp_KeClearEvent
0x1400c278b  nop     dword ptr [rax+rax+00h]
0x1400c2790  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c2797  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c279e  jz      short loc_1400C27D1
0x1400c27a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c27a7  lea     rax, WPP_63e371e5a248373aa5c809d99c379eef_Traceguids
0x1400c27ae  mov     r9d, 23h ; '#'; int
0x1400c27b4  mov     dword ptr [rsp+78h+var_48], edi; char
0x1400c27b8  mov     qword ptr [rsp+78h+var_50], rbp; char
0x1400c27bd  mov     dl, 4; int
0x1400c27bf  mov     [rsp+78h+Timeout], rax; struct _GUID *
0x1400c27c4  mov     rcx, [rcx+40h]; int
0x1400c27c8  lea     r8d, [r9-14h]; int
0x1400c27cc  call    WPP_RECORDER_SF_qL
0x1400c27d1  cmp     edi, 6
0x1400c27d4  jg      short loc_1400C2835
0x1400c27d6  jz      short loc_1400C282C
0x1400c27d8  mov     ecx, edi
0x1400c27da  sub     ecx, 1
0x1400c27dd  jz      short loc_1400C2823
0x1400c27df  sub     ecx, 1
0x1400c27e2  jz      short loc_1400C281A
0x1400c27e4  sub     ecx, 1
0x1400c27e7  jz      short loc_1400C2809
0x1400c27e9  sub     ecx, 1
0x1400c27ec  jz      short loc_1400C2800
0x1400c27ee  cmp     ecx, 1
0x1400c27f1  jnz     loc_1400C287C
0x1400c27f7  or      dword ptr [rbx+1FCh], 10h
0x1400c27fe  jmp     short loc_1400C287C
0x1400c2800  or      dword ptr [rbx+1FCh], 8
0x1400c2807  jmp     short loc_1400C287C
0x1400c2809  or      dword ptr [rbx+1FCh], 4
0x1400c2810  bts     dword ptr [rbx+1F8h], 0Ah
0x1400c2818  jmp     short loc_1400C287C
0x1400c281a  or      dword ptr [rbx+1FCh], 2
0x1400c2821  jmp     short loc_1400C287C
0x1400c2823  or      dword ptr [rbx+1FCh], 1
0x1400c282a  jmp     short loc_1400C287C
0x1400c282c  or      dword ptr [rbx+1FCh], 20h
0x1400c2833  jmp     short loc_1400C287C
0x1400c2835  mov     ecx, edi
0x1400c2837  sub     ecx, 7
0x1400c283a  jz      short loc_1400C2875
0x1400c283c  sub     ecx, 1
0x1400c283f  jz      short loc_1400C2865
0x1400c2841  sub     ecx, 3
0x1400c2844  jz      short loc_1400C285B
0x1400c2846  cmp     ecx, 2
0x1400c2849  jnz     short loc_1400C287C
0x1400c284b  inc     dword ptr [rbx+21Ch]
0x1400c2851  bts     dword ptr [rbx+1FCh], 0Ch
0x1400c2859  jmp     short loc_1400C287C
0x1400c285b  bts     dword ptr [rbx+1FCh], 0Ah
0x1400c2863  jmp     short loc_1400C287C
0x1400c2865  inc     dword ptr [rbx+218h]
0x1400c286b  bts     dword ptr [rbx+1FCh], 7
0x1400c2873  jmp     short loc_1400C287C
0x1400c2875  or      dword ptr [rbx+1FCh], 40h
0x1400c287c  xor     r9d, r9d
0x1400c287f  mov     r8d, edi
0x1400c2882  mov     dl, r15b
0x1400c2885  mov     rcx, rbx
0x1400c2888  call    ndisSelectiveSuspendSetResumeBusyReason
0x1400c288d  test    sil, sil
0x1400c2890  jnz     short loc_1400C28BD
0x1400c2892  lea     rcx, [rbx+110h]; Event
0x1400c2899  call    cs:__imp_KeReadStateEvent
0x1400c28a0  nop     dword ptr [rax+rax+00h]
0x1400c28a5  test    eax, eax
0x1400c28a7  jz      short loc_1400C28BD
0x1400c28a9  mov     dl, r14b; NewIrql
0x1400c28ac  mov     rcx, rbx; SpinLock
0x1400c28af  call    cs:__imp_KeReleaseSpinLock
0x1400c28b6  nop     dword ptr [rax+rax+00h]
0x1400c28bb  jmp     short loc_1400C28EB
0x1400c28bd  mov     dl, r14b; NewIrql
0x1400c28c0  mov     rcx, rbx; SpinLock
0x1400c28c3  call    cs:__imp_KeReleaseSpinLock
0x1400c28ca  nop     dword ptr [rax+rax+00h]
0x1400c28cf  cmp     edi, 6
0x1400c28d2  jz      short loc_1400C28E3
0x1400c28d4  lea     eax, [rdi-3]
0x1400c28d7  test    eax, 0FFFFFFFDh
0x1400c28dc  jnz     short loc_1400C28F9
0x1400c28de  test    sil, sil
0x1400c28e1  jz      short loc_1400C28EB
0x1400c28e3  mov     rcx, rbp; struct _NDIS_MINIPORT_BLOCK *
0x1400c28e6  call    ?ndisWdfAcquireAsyncPowerRefAndResume@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisWdfAcquireAsyncPowerRefAndResume(_NDIS_MINIPORT_BLOCK *)
0x1400c28eb  add     rsp, 48h
0x1400c28ef  pop     r15
0x1400c28f1  pop     r14
0x1400c28f3  pop     rdi
0x1400c28f4  pop     rsi
0x1400c28f5  pop     rbp
0x1400c28f6  pop     rbx
0x1400c28f7  retn
0x1400c28f9  xor     r8d, r8d; unsigned __int8
0x1400c28fc  test    sil, sil
0x1400c28ff  jz      short loc_1400C290D
0x1400c2901  mov     dl, 1; unsigned __int8
0x1400c2903  mov     rcx, rbp; struct _NDIS_MINIPORT_BLOCK *
0x1400c2906  call    ?ndisWdfAcquirePowerReferenceHelper@@YAXPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisWdfAcquirePowerReferenceHelper(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x1400c290b  jmp     short loc_1400C28EB
0x1400c290d  lea     rcx, [rbx+110h]; Object
0x1400c2914  mov     [rsp+78h+Timeout], 0; Timeout
0x1400c291d  xor     r9d, r9d; Alertable
0x1400c2920  xor     edx, edx; WaitReason
0x1400c2922  call    cs:__imp_KeWaitForSingleObject
0x1400c2929  nop     dword ptr [rax+rax+00h]
0x1400c292e  jmp     short loc_1400C28EB
```

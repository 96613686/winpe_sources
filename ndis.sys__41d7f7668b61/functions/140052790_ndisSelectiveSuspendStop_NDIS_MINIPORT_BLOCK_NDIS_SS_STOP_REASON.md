# ndisSelectiveSuspendStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)

- ea: `0x140052790`
- end: `0x140052aab`
- name: `?ndisSelectiveSuspendStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z`
- size: `795`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: ``

## callers

- `0x1400440c0`
- `0x140052740`
- `0x1400b3450`
- `0x140164d00`
- `0x14016e890`
- `0x14017a7a8`

## callees

- `0x1400114b0`
- `0x1400335f0`
- `0x14003cac0`
- `0x14003cec0`
- `0x140044e80`
- `0x1400456c0`
- `0x140052790`
- `0x140052ac0`
- `0x140088a2c`
- `0x1400a34f0`
- `0x14015d480`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400529c5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400529c5`
- `ntoskrnl!KeReadStateEvent` at `0x140052948`
- `ntoskrnl!KeReadStateEvent` at `0x140052948`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140052a48`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140052a48`
- `ntoskrnl!KeClearEvent` at `0x140052836`
- `ntoskrnl!KeClearEvent` at `0x140052836`
- `ntoskrnl!KeCancelTimer` at `0x1400529fb`
- `ntoskrnl!KeCancelTimer` at `0x1400529fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052963`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052a2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052a8f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052963`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052a2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052a8f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400527be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140052a73`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400527be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140052a73`

## pseudocode

```c
void __fastcall ndisSelectiveSuspendStop(struct _NDIS_MINIPORT_BLOCK *a1, unsigned int a2)
{
  struct _NDIS_SELECTIVE_SUSPEND *SelectiveSuspend; // rbx
  char v5; // r14
  unsigned __int8 v6; // si
  KIRQL v7; // bp
  int v8; // edx
  bool v9; // r15
  unsigned __int8 v10; // dl
  int v11; // eax
  char v12; // si
  KIRQL v13; // dl
  KIRQL v14; // al

  SelectiveSuspend = a1->SelectiveSuspend;
  v5 = 0;
  v6 = MINIPORT_TEST_FLAG(a1, 0x80u);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SelectiveSuspend);
  v9 = ndisIsPowerReferencedForSelectiveSuspend(SelectiveSuspend, v6) == 0;
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
      (struct _GUID *)&WPP_b81154d141493d7d4341dde393003738_Traceguids,
      (char)a1,
      a2);
  }
  switch ( a2 )
  {
    case 1u:
      *((_DWORD *)SelectiveSuspend + 127) |= 1u;
      break;
    case 2u:
      *((_DWORD *)SelectiveSuspend + 127) |= 2u;
      break;
    case 3u:
      *((_DWORD *)SelectiveSuspend + 127) |= 4u;
      *((_DWORD *)SelectiveSuspend + 126) |= 0x400u;
      break;
    case 4u:
      *((_DWORD *)SelectiveSuspend + 127) |= 8u;
      break;
    case 5u:
      *((_DWORD *)SelectiveSuspend + 127) |= 0x10u;
      break;
    case 6u:
      *((_DWORD *)SelectiveSuspend + 127) |= 0x20u;
      break;
    case 7u:
      *((_DWORD *)SelectiveSuspend + 127) |= 0x40u;
      break;
    case 8u:
      ++*((_DWORD *)SelectiveSuspend + 134);
      *((_DWORD *)SelectiveSuspend + 127) |= 0x80u;
      break;
    case 0xBu:
      *((_DWORD *)SelectiveSuspend + 127) |= 0x400u;
      break;
    case 0xDu:
      ++*((_DWORD *)SelectiveSuspend + 135);
      *((_DWORD *)SelectiveSuspend + 127) |= 0x1000u;
      break;
    default:
      break;
  }
  ndisSelectiveSuspendSetResumeBusyReason(SelectiveSuspend, v9, a2, 0);
  if ( !v6 )
  {
    v11 = *((_DWORD *)SelectiveSuspend + 126);
    if ( (v11 & 1) != 0 )
    {
      KeCancelTimer((PKTIMER)((char *)SelectiveSuspend + 16));
      *((_DWORD *)SelectiveSuspend + 126) &= ~1u;
      v12 = 1;
      v11 = *((_DWORD *)SelectiveSuspend + 126);
    }
    else
    {
      v12 = 0;
    }
    if ( (v11 & 0x200) == 0 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)SelectiveSuspend, v7);
      ndisCancelWaitWake(a1);
      if ( v12 )
      {
        KeFlushQueuedDpcs();
        ndisWaitForKernelObject((char *)SelectiveSuspend + 152);
      }
      ndisCancelIdleRequestSync(a1, a2, 0, 1u);
      v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SelectiveSuspend);
      *((_DWORD *)SelectiveSuspend + 126) |= 0x200u;
      v13 = v14;
      goto LABEL_44;
    }
LABEL_40:
    v13 = v7;
LABEL_44:
    KeReleaseSpinLock((PKSPIN_LOCK)SelectiveSuspend, v13);
    return;
  }
  if ( !v5 && KeReadStateEvent((PRKEVENT)((char *)SelectiveSuspend + 272)) )
    goto LABEL_40;
  KeReleaseSpinLock((PKSPIN_LOCK)SelectiveSuspend, v7);
  if ( a2 == 6 )
  {
LABEL_31:
    ndisWdfAcquirePowerReferenceHelper(a1, 0, 0);
    ndisWdfSelectiveSuspendResumeOperations(a1, v10, 1u);
    return;
  }
  if ( (unsigned int)Feature_SSDeadlock_Fix__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( a2 == 5 )
    {
      if ( !v5 )
        return;
      goto LABEL_31;
    }
    if ( !v5 )
      goto LABEL_33;
  }
  else if ( !v5 )
  {
LABEL_33:
    KeWaitForSingleObject((char *)SelectiveSuspend + 272, Executive, 0, 0, 0);
    return;
  }
  ndisWdfAcquirePowerReferenceHelper(a1, 1u, 0);
}

```

## disassembly

```asm
0x140052790  push    rbx
0x140052792  push    rbp
0x140052793  push    rsi
0x140052794  push    rdi
0x140052795  push    r13
0x140052797  push    r14
0x140052799  push    r15
0x14005279b  sub     rsp, 40h
0x14005279f  mov     rbx, [rcx+1160h]
0x1400527a6  mov     edi, edx
0x1400527a8  mov     edx, 80h; unsigned int
0x1400527ad  mov     r13, rcx
0x1400527b0  xor     r14b, r14b
0x1400527b3  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400527b8  mov     rcx, rbx; SpinLock
0x1400527bb  movzx   esi, al
0x1400527be  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400527c5  nop     dword ptr [rax+rax+00h]
0x1400527ca  movzx   edx, sil; unsigned __int8
0x1400527ce  mov     rcx, rbx; struct _NDIS_SELECTIVE_SUSPEND *
0x1400527d1  movzx   ebp, al
0x1400527d4  call    ?ndisIsPowerReferencedForSelectiveSuspend@@YAEPEAU_NDIS_SELECTIVE_SUSPEND@@E@Z; ndisIsPowerReferencedForSelectiveSuspend(_NDIS_SELECTIVE_SUSPEND *,uchar)
0x1400527d9  test    al, al
0x1400527db  setz    r15b
0x1400527df  test    sil, sil
0x1400527e2  jz      short loc_140052842
0x1400527e4  cmp     dword ptr [rbx+200h], 0
0x1400527eb  jnz     short loc_140052842
0x1400527ed  cmp     dword ptr [rbx+204h], 0
0x1400527f4  jnz     short loc_140052842
0x1400527f6  cmp     dword ptr [rbx+210h], 0
0x1400527fd  jnz     short loc_140052842
0x1400527ff  cmp     dword ptr [rbx+214h], 0
0x140052806  jnz     short loc_140052842
0x140052808  cmp     dword ptr [rbx+208h], 0
0x14005280f  jnz     short loc_140052842
0x140052811  cmp     dword ptr [rbx+20Ch], 0
0x140052818  jnz     short loc_140052842
0x14005281a  cmp     dword ptr [rbx+240h], 0
0x140052821  jnz     short loc_140052842
0x140052823  cmp     dword ptr [rbx+1FCh], 0
0x14005282a  jnz     short loc_140052842
0x14005282c  lea     rcx, [rbx+110h]; Event
0x140052833  mov     r14b, 1
0x140052836  call    cs:__imp_KeClearEvent
0x14005283d  nop     dword ptr [rax+rax+00h]
0x140052842  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140052849  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140052850  jz      short loc_140052885
0x140052852  mov     rcx, cs:WPP_GLOBAL_Control
0x140052859  lea     rax, WPP_b81154d141493d7d4341dde393003738_Traceguids
0x140052860  mov     dword ptr [rsp+78h+var_48], edi; char
0x140052864  mov     r9d, 22h ; '"'; int
0x14005286a  mov     qword ptr [rsp+78h+var_50], r13; char
0x14005286f  mov     r8d, 0Fh; int
0x140052875  mov     dl, 4; int
0x140052877  mov     [rsp+78h+Timeout], rax; struct _GUID *
0x14005287c  mov     rcx, [rcx+40h]; int
0x140052880  call    WPP_RECORDER_SF_qL
0x140052885  lea     eax, [rdi-1]; switch 13 cases
0x140052888  cmp     eax, 0Ch
0x14005288b  ja      def_1400528A4; jumptable 00000001400528A4 default case, cases 9,10,12
0x140052891  lea     rdx, cs:140000000h
0x140052898  cdqe
0x14005289a  mov     ecx, ds:(jpt_1400528A4 - 140000000h)[rdx+rax*4]
0x1400528a1  add     rcx, rdx
0x1400528a4  jmp     rcx; switch jump
0x1400528aa  or      dword ptr [rbx+1FCh], 1; jumptable 00000001400528A4 case 1
0x1400528b1  jmp     short def_1400528A4; jumptable 00000001400528A4 default case, cases 9,10,12
0x1400528b3  or      dword ptr [rbx+1FCh], 2; jumptable 00000001400528A4 case 2
0x1400528ba  jmp     short def_1400528A4; jumptable 00000001400528A4 default case, cases 9,10,12
0x1400528bc  or      dword ptr [rbx+1FCh], 4; jumptable 00000001400528A4 case 3
0x1400528c3  or      dword ptr [rbx+1F8h], 400h
0x1400528cd  jmp     short def_1400528A4; jumptable 00000001400528A4 default case, cases 9,10,12
0x1400528cf  or      dword ptr [rbx+1FCh], 8; jumptable 00000001400528A4 case 4
0x1400528d6  jmp     short def_1400528A4; jumptable 00000001400528A4 default case, cases 9,10,12
0x1400528d8  or      dword ptr [rbx+1FCh], 10h; jumptable 00000001400528A4 case 5
0x1400528df  jmp     short def_1400528A4; jumptable 00000001400528A4 default case, cases 9,10,12
0x1400528e1  or      dword ptr [rbx+1FCh], 20h; jumptable 00000001400528A4 case 6
0x1400528e8  jmp     short def_1400528A4; jumptable 00000001400528A4 default case, cases 9,10,12
0x1400528ea  or      dword ptr [rbx+1FCh], 40h; jumptable 00000001400528A4 case 7
0x1400528f1  jmp     short def_1400528A4; jumptable 00000001400528A4 default case, cases 9,10,12
0x1400528f3  inc     dword ptr [rbx+218h]; jumptable 00000001400528A4 case 8
0x1400528f9  or      dword ptr [rbx+1FCh], 80h
0x140052903  jmp     short def_1400528A4; jumptable 00000001400528A4 default case, cases 9,10,12
0x140052905  or      dword ptr [rbx+1FCh], 400h; jumptable 00000001400528A4 case 11
0x14005290f  jmp     short def_1400528A4; jumptable 00000001400528A4 default case, cases 9,10,12
0x140052911  inc     dword ptr [rbx+21Ch]; jumptable 00000001400528A4 case 13
0x140052917  or      dword ptr [rbx+1FCh], 1000h
0x140052921  xor     r9d, r9d; jumptable 00000001400528A4 default case, cases 9,10,12
0x140052924  mov     r8d, edi
0x140052927  movzx   edx, r15b
0x14005292b  mov     rcx, rbx
0x14005292e  call    ndisSelectiveSuspendSetResumeBusyReason
0x140052933  test    sil, sil
0x140052936  jz      loc_1400529ED
0x14005293c  test    r14b, r14b
0x14005293f  jnz     short loc_14005295C
0x140052941  lea     rcx, [rbx+110h]; Event
0x140052948  call    cs:__imp_KeReadStateEvent
0x14005294f  nop     dword ptr [rax+rax+00h]
0x140052954  test    eax, eax
0x140052956  jnz     loc_140052A22
0x14005295c  movzx   edx, bpl; NewIrql
0x140052960  mov     rcx, rbx; SpinLock
0x140052963  call    cs:__imp_KeReleaseSpinLock
0x14005296a  nop     dword ptr [rax+rax+00h]
0x14005296f  cmp     edi, 6
0x140052972  jz      short loc_14005298B
0x140052974  call    Feature_SSDeadlock_Fix__private_IsEnabledDeviceUsageNoInline
0x140052979  test    eax, eax
0x14005297b  jz      short loc_1400529D6
0x14005297d  cmp     edi, 5
0x140052980  jnz     short loc_1400529A8
0x140052982  test    r14b, r14b
0x140052985  jz      loc_140052A9B
0x14005298b  xor     r8d, r8d; unsigned __int8
0x14005298e  xor     edx, edx; unsigned __int8
0x140052990  mov     rcx, r13; struct _NDIS_MINIPORT_BLOCK *
0x140052993  call    ?ndisWdfAcquirePowerReferenceHelper@@YAXPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisWdfAcquirePowerReferenceHelper(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x140052998  mov     r8b, 1; unsigned __int8
0x14005299b  mov     rcx, r13; struct _NDIS_MINIPORT_BLOCK *
0x14005299e  call    ?ndisWdfSelectiveSuspendResumeOperations@@YAXPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisWdfSelectiveSuspendResumeOperations(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x1400529a3  jmp     loc_140052A9B
0x1400529a8  test    r14b, r14b
0x1400529ab  jnz     short loc_1400529DB
0x1400529ad  lea     rcx, [rbx+110h]; Object
0x1400529b4  mov     [rsp+78h+Timeout], 0; Timeout
0x1400529bd  xor     r9d, r9d; Alertable
0x1400529c0  xor     r8d, r8d; WaitMode
0x1400529c3  xor     edx, edx; WaitReason
0x1400529c5  call    cs:__imp_KeWaitForSingleObject
0x1400529cc  nop     dword ptr [rax+rax+00h]
0x1400529d1  jmp     loc_140052A9B
0x1400529d6  test    r14b, r14b
0x1400529d9  jz      short loc_1400529AD
0x1400529db  xor     r8d, r8d; unsigned __int8
0x1400529de  mov     dl, 1; unsigned __int8
0x1400529e0  mov     rcx, r13; struct _NDIS_MINIPORT_BLOCK *
0x1400529e3  call    ?ndisWdfAcquirePowerReferenceHelper@@YAXPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisWdfAcquirePowerReferenceHelper(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x1400529e8  jmp     loc_140052A9B
0x1400529ed  mov     eax, [rbx+1F8h]
0x1400529f3  test    al, 1
0x1400529f5  jz      short loc_140052A19
0x1400529f7  lea     rcx, [rbx+10h]; PKTIMER
0x1400529fb  call    cs:__imp_KeCancelTimer
0x140052a02  nop     dword ptr [rax+rax+00h]
0x140052a07  and     dword ptr [rbx+1F8h], 0FFFFFFFEh
0x140052a0e  mov     sil, 1
0x140052a11  mov     eax, [rbx+1F8h]
0x140052a17  jmp     short loc_140052A1C
0x140052a19  xor     sil, sil
0x140052a1c  bt      eax, 9
0x140052a20  jnb     short loc_140052A28
0x140052a22  movzx   edx, bpl
0x140052a26  jmp     short loc_140052A8C
0x140052a28  movzx   edx, bpl; NewIrql
0x140052a2c  mov     rcx, rbx; SpinLock
0x140052a2f  call    cs:__imp_KeReleaseSpinLock
0x140052a36  nop     dword ptr [rax+rax+00h]
0x140052a3b  mov     rcx, r13; struct _NDIS_MINIPORT_BLOCK *
0x140052a3e  call    ?ndisCancelWaitWake@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisCancelWaitWake(_NDIS_MINIPORT_BLOCK *)
0x140052a43  test    sil, sil
0x140052a46  jz      short loc_140052A60
0x140052a48  call    cs:__imp_KeFlushQueuedDpcs
0x140052a4f  nop     dword ptr [rax+rax+00h]
0x140052a54  lea     rcx, [rbx+98h]; void *
0x140052a5b  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x140052a60  mov     r9b, 1; unsigned __int8
0x140052a63  xor     r8d, r8d; unsigned int
0x140052a66  mov     edx, edi; char
0x140052a68  mov     rcx, r13; struct _NDIS_MINIPORT_BLOCK *
0x140052a6b  call    ?ndisCancelIdleRequestSync@@YAXPEAU_NDIS_MINIPORT_BLOCK@@KKE@Z; ndisCancelIdleRequestSync(_NDIS_MINIPORT_BLOCK *,ulong,ulong,uchar)
0x140052a70  mov     rcx, rbx; SpinLock
0x140052a73  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140052a7a  nop     dword ptr [rax+rax+00h]
0x140052a7f  or      dword ptr [rbx+1F8h], 200h
0x140052a89  movzx   edx, al; NewIrql
0x140052a8c  mov     rcx, rbx; SpinLock
0x140052a8f  call    cs:__imp_KeReleaseSpinLock
0x140052a96  nop     dword ptr [rax+rax+00h]
0x140052a9b  add     rsp, 40h
0x140052a9f  pop     r15
0x140052aa1  pop     r14
0x140052aa3  pop     r13
0x140052aa5  pop     rdi
0x140052aa6  pop     rsi
0x140052aa7  pop     rbp
0x140052aa8  pop     rbx
0x140052aa9  retn
```

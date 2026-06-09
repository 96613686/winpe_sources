# FveConvUpdatePriority

- ea: `0x1400a6414`
- end: `0x1400a684b`
- name: `FveConvUpdatePriority`
- size: `1079`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140024040`
- `0x14005a47c`
- `0x14005a640`
- `0x1400a54ec`

## callees

- `0x14000a150`
- `0x14000aef4`
- `0x14000bc1c`
- `0x1400a6414`
- `0x1400dc534`

## import_xrefs

- `ntoskrnl!IoBoostThreadIo` at `0x1400a67be`
- `ntoskrnl!IoBoostThreadIo` at `0x1400a6814`
- `ntoskrnl!IoBoostThreadIo` at `0x1400a67be`
- `ntoskrnl!IoBoostThreadIo` at `0x1400a6814`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a6761`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a6761`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400a664c`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400a6673`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400a664c`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400a6673`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a645b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a645b`

## pseudocode

```c
__int64 __fastcall FveConvUpdatePriority(__int64 a1, int a2, int a3, unsigned __int8 a4, char a5, char a6)
{
  __int64 v6; // r15
  unsigned int v7; // r14d
  int v8; // ebp
  int v9; // esi
  KSPIN_LOCK *v11; // r13
  __int64 v12; // r9
  int v13; // edi
  __int64 v14; // r9
  int v15; // r8d
  unsigned int v16; // eax
  int v17; // r8d
  int v18; // edx
  char v19; // bp
  __int64 v20; // r8
  __int64 v21; // r9
  KIRQL NewIrql; // [rsp+98h] [rbp+20h]

  v6 = *(_QWORD *)(a1 + 576);
  v7 = 2;
  v8 = a4;
  v9 = a2;
  if ( a3 <= 2 )
    v7 = a3;
  if ( a4 && a2 < 18 )
    v9 = 18;
  v11 = (KSPIN_LOCK *)(a1 + 536);
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 536));
  if ( a6 )
  {
    v12 = *(unsigned int *)(a1 + 548);
    if ( v9 == (_DWORD)v12 )
      goto LABEL_17;
    goto LABEL_10;
  }
  if ( v9 > *(_DWORD *)(a1 + 548) )
  {
    v12 = *(unsigned int *)(a1 + 548);
LABEL_10:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids, v12, v9);
    }
    *(_DWORD *)(a1 + 548) = v9;
    if ( !a6 )
      goto LABEL_15;
LABEL_17:
    v14 = *(unsigned int *)(a1 + 556);
    if ( v7 == (_DWORD)v14 )
      goto LABEL_24;
    goto LABEL_18;
  }
LABEL_15:
  v13 = 0;
  if ( (signed int)v7 <= *(_DWORD *)(a1 + 556) )
  {
LABEL_25:
    if ( !(_BYTE)v8 || *(_BYTE *)(a1 + 565) )
      goto LABEL_33;
    goto LABEL_27;
  }
  v14 = *(unsigned int *)(a1 + 556);
LABEL_18:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids, v14, v7);
  }
  *(_DWORD *)(a1 + 556) = v7;
  if ( !a6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 560));
    v13 = 1;
    goto LABEL_25;
  }
LABEL_24:
  v13 = -*(_DWORD *)(a1 + 560);
  *(_DWORD *)(a1 + 560) = 0;
LABEL_27:
  if ( (_BYTE)v8 != *(_BYTE *)(a1 + 565) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids,
        *(unsigned __int8 *)(a1 + 565),
        v8);
    }
    *(_BYTE *)(a1 + 565) = v8;
  }
LABEL_33:
  if ( a5 )
  {
    v15 = *(_DWORD *)(a1 + 548);
    if ( *(_DWORD *)(a1 + 544) != v15 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids,
          *(unsigned int *)(a1 + 544),
          v15);
      }
      *(_DWORD *)(a1 + 544) = *(_DWORD *)(a1 + 548);
      if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v16 = KeSetActualBasePriorityThread(v6, *(unsigned int *)(a1 + 544));
        if ( (signed int)v16 > *(_DWORD *)(a1 + 544) )
        {
          *(_DWORD *)(a1 + 544) = v16;
          *(_DWORD *)(a1 + 548) = v16;
          KeSetActualBasePriorityThread(v6, v16);
        }
      }
    }
    v17 = *(_DWORD *)(a1 + 556);
    if ( *(_DWORD *)(a1 + 552) != v17 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids,
          *(unsigned int *)(a1 + 552),
          v17);
      }
      *(_DWORD *)(a1 + 552) = *(_DWORD *)(a1 + 556);
    }
    v18 = *(unsigned __int8 *)(a1 + 565);
    if ( *(_BYTE *)(a1 + 564) != (_BYTE)v18 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids,
          *(unsigned __int8 *)(a1 + 564),
          v18);
      }
      *(_BYTE *)(a1 + 564) = *(_BYTE *)(a1 + 565);
    }
  }
  v19 = *(_BYTE *)(a1 + 564);
  KeReleaseSpinLock(v11, NewIrql);
  if ( v13 <= 0 )
  {
    for ( ; v13 < 0; ++v13 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids,
          *(_QWORD *)(a1 + 568));
      }
      LOBYTE(v20) = 1;
      IoBoostThreadIo(*(_QWORD *)(a1 + 568), 1, v20);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_Lq(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids,
        v7,
        *(_QWORD *)(a1 + 568));
    }
    IoBoostThreadIo(*(_QWORD *)(a1 + 568), v7, 0);
  }
  LOBYTE(v21) = a6;
  LOBYTE(v20) = v19;
  return FveTransformUpdatePriority(*(_QWORD *)(a1 + 304), (unsigned int)v9, v20, v21);
}

```

## disassembly

```asm
0x1400a6414  push    rbx
0x1400a6416  push    rbp
0x1400a6417  push    rsi
0x1400a6418  push    rdi
0x1400a6419  push    r12
0x1400a641b  push    r13
0x1400a641d  push    r14
0x1400a641f  push    r15
0x1400a6421  sub     rsp, 38h
0x1400a6425  mov     r15, [rcx+240h]
0x1400a642c  mov     r14d, 2
0x1400a6432  cmp     r8d, r14d
0x1400a6435  movzx   ebp, r9b
0x1400a6439  mov     esi, edx
0x1400a643b  mov     rbx, rcx
0x1400a643e  cmovle  r14d, r8d
0x1400a6442  test    r9b, r9b
0x1400a6445  jz      short loc_1400A6451
0x1400a6447  mov     eax, 12h
0x1400a644c  cmp     edx, eax
0x1400a644e  cmovl   esi, eax
0x1400a6451  lea     r13, [rcx+218h]
0x1400a6458  mov     rcx, r13; SpinLock
0x1400a645b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400a6462  nop     dword ptr [rax+rax+00h]
0x1400a6467  mov     r12b, [rsp+78h+arg_28]
0x1400a646f  lea     r10, WPP_GLOBAL_Control
0x1400a6476  mov     [rsp+78h+NewIrql], al
0x1400a647d  test    r12b, r12b
0x1400a6480  jnz     short loc_1400A6493
0x1400a6482  cmp     esi, [rbx+224h]
0x1400a6488  jle     short loc_1400A64E3
0x1400a648a  mov     r9d, [rbx+224h]
0x1400a6491  jmp     short loc_1400A649F
0x1400a6493  mov     r9d, [rbx+224h]
0x1400a649a  cmp     esi, r9d
0x1400a649d  jz      short loc_1400A64FB
0x1400a649f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a64a6  cmp     rcx, r10
0x1400a64a9  jz      short loc_1400A64D8
0x1400a64ab  mov     eax, [rcx+2Ch]
0x1400a64ae  test    al, 2
0x1400a64b0  jz      short loc_1400A64D8
0x1400a64b2  cmp     byte ptr [rcx+29h], 5
0x1400a64b6  jb      short loc_1400A64D8
0x1400a64b8  mov     rcx, [rcx+18h]
0x1400a64bc  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a64c3  mov     edx, 0Ah
0x1400a64c8  mov     dword ptr [rsp+78h+var_58], esi
0x1400a64cc  call    WPP_SF_Dd
0x1400a64d1  lea     r10, WPP_GLOBAL_Control
0x1400a64d8  mov     [rbx+224h], esi
0x1400a64de  test    r12b, r12b
0x1400a64e1  jnz     short loc_1400A64FB
0x1400a64e3  xor     edi, edi
0x1400a64e5  cmp     r14d, [rbx+22Ch]
0x1400a64ec  jle     loc_1400A6572
0x1400a64f2  mov     r9d, [rbx+22Ch]
0x1400a64f9  jmp     short loc_1400A6507
0x1400a64fb  mov     r9d, [rbx+22Ch]
0x1400a6502  cmp     r14d, r9d
0x1400a6505  jz      short loc_1400A655B
0x1400a6507  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a650e  cmp     rcx, r10
0x1400a6511  jz      short loc_1400A6541
0x1400a6513  mov     eax, [rcx+2Ch]
0x1400a6516  test    al, 2
0x1400a6518  jz      short loc_1400A6541
0x1400a651a  cmp     byte ptr [rcx+29h], 5
0x1400a651e  jb      short loc_1400A6541
0x1400a6520  mov     rcx, [rcx+18h]
0x1400a6524  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a652b  mov     edx, 0Bh
0x1400a6530  mov     dword ptr [rsp+78h+var_58], r14d
0x1400a6535  call    WPP_SF_Dd
0x1400a653a  lea     r10, WPP_GLOBAL_Control
0x1400a6541  mov     [rbx+22Ch], r14d
0x1400a6548  test    r12b, r12b
0x1400a654b  jnz     short loc_1400A655B
0x1400a654d  lock inc dword ptr [rbx+230h]
0x1400a6554  mov     edi, 1
0x1400a6559  jmp     short loc_1400A6572
0x1400a655b  mov     edi, [rbx+230h]
0x1400a6561  neg     edi
0x1400a6563  mov     dword ptr [rbx+230h], 0
0x1400a656d  test    r12b, r12b
0x1400a6570  jnz     short loc_1400A6580
0x1400a6572  test    bpl, bpl
0x1400a6575  jz      short loc_1400A65CF
0x1400a6577  cmp     byte ptr [rbx+235h], 0
0x1400a657e  jnz     short loc_1400A65CF
0x1400a6580  movzx   edx, byte ptr [rbx+235h]
0x1400a6587  cmp     bpl, dl
0x1400a658a  jz      short loc_1400A65CF
0x1400a658c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6593  cmp     rcx, r10
0x1400a6596  jz      short loc_1400A65C8
0x1400a6598  mov     eax, [rcx+2Ch]
0x1400a659b  test    al, 2
0x1400a659d  jz      short loc_1400A65C8
0x1400a659f  cmp     byte ptr [rcx+29h], 5
0x1400a65a3  jb      short loc_1400A65C8
0x1400a65a5  mov     rcx, [rcx+18h]
0x1400a65a9  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a65b0  mov     r9d, edx
0x1400a65b3  mov     dword ptr [rsp+78h+var_58], ebp
0x1400a65b7  mov     edx, 0Ch
0x1400a65bc  call    WPP_SF_Dd
0x1400a65c1  lea     r10, WPP_GLOBAL_Control
0x1400a65c8  mov     [rbx+235h], bpl
0x1400a65cf  cmp     [rsp+78h+arg_20], 0
0x1400a65d7  jz      loc_1400A6749
0x1400a65dd  mov     eax, [rbx+220h]
0x1400a65e3  mov     r8d, [rbx+224h]
0x1400a65ea  cmp     eax, r8d
0x1400a65ed  jz      loc_1400A667F
0x1400a65f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a65fa  cmp     rcx, r10
0x1400a65fd  jz      short loc_1400A662D
0x1400a65ff  mov     eax, [rcx+2Ch]
0x1400a6602  test    al, 2
0x1400a6604  jz      short loc_1400A662D
0x1400a6606  cmp     byte ptr [rcx+29h], 5
0x1400a660a  jb      short loc_1400A662D
0x1400a660c  mov     rcx, [rcx+18h]
0x1400a6610  mov     edx, 0Dh
0x1400a6615  mov     r9d, [rbx+220h]
0x1400a661c  mov     dword ptr [rsp+78h+var_58], r8d
0x1400a6621  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a6628  call    WPP_SF_Dd
0x1400a662d  mov     eax, [rbx+224h]
0x1400a6633  mov     [rbx+220h], eax
0x1400a6639  lea     rax, [r15-1]
0x1400a663d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400a6641  ja      short loc_1400A667F
0x1400a6643  mov     edx, [rbx+220h]
0x1400a6649  mov     rcx, r15
0x1400a664c  call    cs:__imp_KeSetActualBasePriorityThread
0x1400a6653  nop     dword ptr [rax+rax+00h]
0x1400a6658  mov     edx, [rbx+220h]
0x1400a665e  cmp     eax, edx
0x1400a6660  jle     short loc_1400A667F
0x1400a6662  mov     edx, eax
0x1400a6664  mov     [rbx+220h], eax
0x1400a666a  mov     rcx, r15
0x1400a666d  mov     [rbx+224h], eax
0x1400a6673  call    cs:__imp_KeSetActualBasePriorityThread
0x1400a667a  nop     dword ptr [rax+rax+00h]
0x1400a667f  mov     eax, [rbx+228h]
0x1400a6685  mov     r8d, [rbx+22Ch]
0x1400a668c  cmp     eax, r8d
0x1400a668f  jz      short loc_1400A66E0
0x1400a6691  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6698  lea     r15, WPP_GLOBAL_Control
0x1400a669f  cmp     rcx, r15
0x1400a66a2  jz      short loc_1400A66D2
0x1400a66a4  mov     eax, [rcx+2Ch]
0x1400a66a7  test    al, 2
0x1400a66a9  jz      short loc_1400A66D2
0x1400a66ab  cmp     byte ptr [rcx+29h], 5
0x1400a66af  jb      short loc_1400A66D2
0x1400a66b1  mov     rcx, [rcx+18h]
0x1400a66b5  mov     edx, 0Eh
0x1400a66ba  mov     r9d, [rbx+228h]
0x1400a66c1  mov     dword ptr [rsp+78h+var_58], r8d
0x1400a66c6  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a66cd  call    WPP_SF_Dd
0x1400a66d2  mov     eax, [rbx+22Ch]
0x1400a66d8  mov     [rbx+228h], eax
0x1400a66de  jmp     short loc_1400A66E7
0x1400a66e0  lea     r15, WPP_GLOBAL_Control
0x1400a66e7  mov     al, [rbx+234h]
0x1400a66ed  movzx   edx, byte ptr [rbx+235h]
0x1400a66f4  cmp     al, dl
0x1400a66f6  jz      short loc_1400A6750
0x1400a66f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a66ff  cmp     rcx, r15
0x1400a6702  jz      short loc_1400A673B
0x1400a6704  mov     eax, [rcx+2Ch]
0x1400a6707  test    al, 2
0x1400a6709  jz      short loc_1400A673B
0x1400a670b  cmp     byte ptr [rcx+29h], 5
0x1400a670f  jb      short loc_1400A673B
0x1400a6711  movzx   r9d, byte ptr [rbx+234h]
0x1400a6719  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a6720  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6727  mov     eax, edx
0x1400a6729  mov     edx, 0Fh
0x1400a672e  mov     dword ptr [rsp+78h+var_58], eax
0x1400a6732  mov     rcx, [rcx+18h]
0x1400a6736  call    WPP_SF_Dd
0x1400a673b  mov     al, [rbx+235h]
0x1400a6741  mov     [rbx+234h], al
0x1400a6747  jmp     short loc_1400A6750
0x1400a6749  lea     r15, WPP_GLOBAL_Control
0x1400a6750  mov     dl, [rsp+78h+NewIrql]; NewIrql
0x1400a6757  mov     rcx, r13; SpinLock
0x1400a675a  mov     bpl, [rbx+234h]
0x1400a6761  call    cs:__imp_KeReleaseSpinLock
0x1400a6768  nop     dword ptr [rax+rax+00h]
0x1400a676d  test    edi, edi
0x1400a676f  jle     short loc_1400A67CC
0x1400a6771  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6778  cmp     rcx, r15
0x1400a677b  jz      short loc_1400A67AE
0x1400a677d  mov     eax, [rcx+2Ch]
0x1400a6780  test    al, 2
0x1400a6782  jz      short loc_1400A67AE
0x1400a6784  cmp     byte ptr [rcx+29h], 5
0x1400a6788  jb      short loc_1400A67AE
0x1400a678a  mov     rax, [rbx+238h]
0x1400a6791  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a6798  mov     rcx, [rcx+18h]
0x1400a679c  mov     edx, 10h
0x1400a67a1  mov     r9d, r14d
0x1400a67a4  mov     [rsp+78h+var_58], rax
0x1400a67a9  call    WPP_SF_Lq
0x1400a67ae  mov     rcx, [rbx+238h]
0x1400a67b5  xor     r9d, r9d
0x1400a67b8  xor     r8d, r8d
0x1400a67bb  mov     edx, r14d
0x1400a67be  call    cs:__imp_IoBoostThreadIo
0x1400a67c5  nop     dword ptr [rax+rax+00h]
0x1400a67ca  jmp     short loc_1400A6825
0x1400a67cc  jns     short loc_1400A6825
0x1400a67ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a67d5  cmp     rcx, r15
0x1400a67d8  jz      short loc_1400A6803
0x1400a67da  mov     eax, [rcx+2Ch]
0x1400a67dd  test    al, 2
0x1400a67df  jz      short loc_1400A6803
0x1400a67e1  cmp     byte ptr [rcx+29h], 5
0x1400a67e5  jb      short loc_1400A6803
0x1400a67e7  mov     r9, [rbx+238h]
0x1400a67ee  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a67f5  mov     rcx, [rcx+18h]
0x1400a67f9  mov     edx, 11h
0x1400a67fe  call    WPP_SF_q
0x1400a6803  mov     rcx, [rbx+238h]
0x1400a680a  xor     r9d, r9d
0x1400a680d  mov     r8b, 1
0x1400a6810  lea     edx, [r9+1]
0x1400a6814  call    cs:__imp_IoBoostThreadIo
0x1400a681b  nop     dword ptr [rax+rax+00h]
0x1400a6820  add     edi, 1
0x1400a6823  js      short loc_1400A67CE
0x1400a6825  mov     rcx, [rbx+130h]
0x1400a682c  mov     r9b, r12b
0x1400a682f  mov     r8b, bpl
0x1400a6832  mov     edx, esi
0x1400a6834  call    FveTransformUpdatePriority
0x1400a6839  add     rsp, 38h
0x1400a683d  pop     r15
0x1400a683f  pop     r14
0x1400a6841  pop     r13
0x1400a6843  pop     r12
0x1400a6845  pop     rdi
0x1400a6846  pop     rsi
0x1400a6847  pop     rbp
0x1400a6848  pop     rbx
0x1400a6849  retn
```

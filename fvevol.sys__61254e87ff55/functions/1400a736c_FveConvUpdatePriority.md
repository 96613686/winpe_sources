# FveConvUpdatePriority

- ea: `0x1400a736c`
- end: `0x1400a77a3`
- name: `FveConvUpdatePriority`
- size: `1079`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140025040`
- `0x14005c4d4`
- `0x14005c698`
- `0x1400a6444`

## callees

- `0x14000a210`
- `0x14000afb4`
- `0x14000bda8`
- `0x1400a736c`
- `0x1400df3c4`

## import_xrefs

- `ntoskrnl!IoBoostThreadIo` at `0x1400a7716`
- `ntoskrnl!IoBoostThreadIo` at `0x1400a776c`
- `ntoskrnl!IoBoostThreadIo` at `0x1400a7716`
- `ntoskrnl!IoBoostThreadIo` at `0x1400a776c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a76b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a76b9`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400a75a4`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400a75cb`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400a75a4`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400a75cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a73b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a73b3`

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
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_8d48425948c73b66a608165fe5646329_Traceguids, v12, v9);
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
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_8d48425948c73b66a608165fe5646329_Traceguids, v14, v7);
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
        WPP_8d48425948c73b66a608165fe5646329_Traceguids,
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
          WPP_8d48425948c73b66a608165fe5646329_Traceguids,
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
          WPP_8d48425948c73b66a608165fe5646329_Traceguids,
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
          WPP_8d48425948c73b66a608165fe5646329_Traceguids,
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
          WPP_8d48425948c73b66a608165fe5646329_Traceguids,
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
        WPP_8d48425948c73b66a608165fe5646329_Traceguids,
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
0x1400a736c  push    rbx
0x1400a736e  push    rbp
0x1400a736f  push    rsi
0x1400a7370  push    rdi
0x1400a7371  push    r12
0x1400a7373  push    r13
0x1400a7375  push    r14
0x1400a7377  push    r15
0x1400a7379  sub     rsp, 38h
0x1400a737d  mov     r15, [rcx+240h]
0x1400a7384  mov     r14d, 2
0x1400a738a  cmp     r8d, r14d
0x1400a738d  movzx   ebp, r9b
0x1400a7391  mov     esi, edx
0x1400a7393  mov     rbx, rcx
0x1400a7396  cmovle  r14d, r8d
0x1400a739a  test    r9b, r9b
0x1400a739d  jz      short loc_1400A73A9
0x1400a739f  mov     eax, 12h
0x1400a73a4  cmp     edx, eax
0x1400a73a6  cmovl   esi, eax
0x1400a73a9  lea     r13, [rcx+218h]
0x1400a73b0  mov     rcx, r13; SpinLock
0x1400a73b3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400a73ba  nop     dword ptr [rax+rax+00h]
0x1400a73bf  mov     r12b, [rsp+78h+arg_28]
0x1400a73c7  lea     r10, WPP_GLOBAL_Control
0x1400a73ce  mov     [rsp+78h+NewIrql], al
0x1400a73d5  test    r12b, r12b
0x1400a73d8  jnz     short loc_1400A73EB
0x1400a73da  cmp     esi, [rbx+224h]
0x1400a73e0  jle     short loc_1400A743B
0x1400a73e2  mov     r9d, [rbx+224h]
0x1400a73e9  jmp     short loc_1400A73F7
0x1400a73eb  mov     r9d, [rbx+224h]
0x1400a73f2  cmp     esi, r9d
0x1400a73f5  jz      short loc_1400A7453
0x1400a73f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a73fe  cmp     rcx, r10
0x1400a7401  jz      short loc_1400A7430
0x1400a7403  mov     eax, [rcx+2Ch]
0x1400a7406  test    al, 2
0x1400a7408  jz      short loc_1400A7430
0x1400a740a  cmp     byte ptr [rcx+29h], 5
0x1400a740e  jb      short loc_1400A7430
0x1400a7410  mov     rcx, [rcx+18h]
0x1400a7414  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a741b  mov     edx, 0Ah
0x1400a7420  mov     dword ptr [rsp+78h+var_58], esi
0x1400a7424  call    WPP_SF_Dd
0x1400a7429  lea     r10, WPP_GLOBAL_Control
0x1400a7430  mov     [rbx+224h], esi
0x1400a7436  test    r12b, r12b
0x1400a7439  jnz     short loc_1400A7453
0x1400a743b  xor     edi, edi
0x1400a743d  cmp     r14d, [rbx+22Ch]
0x1400a7444  jle     loc_1400A74CA
0x1400a744a  mov     r9d, [rbx+22Ch]
0x1400a7451  jmp     short loc_1400A745F
0x1400a7453  mov     r9d, [rbx+22Ch]
0x1400a745a  cmp     r14d, r9d
0x1400a745d  jz      short loc_1400A74B3
0x1400a745f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7466  cmp     rcx, r10
0x1400a7469  jz      short loc_1400A7499
0x1400a746b  mov     eax, [rcx+2Ch]
0x1400a746e  test    al, 2
0x1400a7470  jz      short loc_1400A7499
0x1400a7472  cmp     byte ptr [rcx+29h], 5
0x1400a7476  jb      short loc_1400A7499
0x1400a7478  mov     rcx, [rcx+18h]
0x1400a747c  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a7483  mov     edx, 0Bh
0x1400a7488  mov     dword ptr [rsp+78h+var_58], r14d
0x1400a748d  call    WPP_SF_Dd
0x1400a7492  lea     r10, WPP_GLOBAL_Control
0x1400a7499  mov     [rbx+22Ch], r14d
0x1400a74a0  test    r12b, r12b
0x1400a74a3  jnz     short loc_1400A74B3
0x1400a74a5  lock inc dword ptr [rbx+230h]
0x1400a74ac  mov     edi, 1
0x1400a74b1  jmp     short loc_1400A74CA
0x1400a74b3  mov     edi, [rbx+230h]
0x1400a74b9  neg     edi
0x1400a74bb  mov     dword ptr [rbx+230h], 0
0x1400a74c5  test    r12b, r12b
0x1400a74c8  jnz     short loc_1400A74D8
0x1400a74ca  test    bpl, bpl
0x1400a74cd  jz      short loc_1400A7527
0x1400a74cf  cmp     byte ptr [rbx+235h], 0
0x1400a74d6  jnz     short loc_1400A7527
0x1400a74d8  movzx   edx, byte ptr [rbx+235h]
0x1400a74df  cmp     bpl, dl
0x1400a74e2  jz      short loc_1400A7527
0x1400a74e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a74eb  cmp     rcx, r10
0x1400a74ee  jz      short loc_1400A7520
0x1400a74f0  mov     eax, [rcx+2Ch]
0x1400a74f3  test    al, 2
0x1400a74f5  jz      short loc_1400A7520
0x1400a74f7  cmp     byte ptr [rcx+29h], 5
0x1400a74fb  jb      short loc_1400A7520
0x1400a74fd  mov     rcx, [rcx+18h]
0x1400a7501  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a7508  mov     r9d, edx
0x1400a750b  mov     dword ptr [rsp+78h+var_58], ebp
0x1400a750f  mov     edx, 0Ch
0x1400a7514  call    WPP_SF_Dd
0x1400a7519  lea     r10, WPP_GLOBAL_Control
0x1400a7520  mov     [rbx+235h], bpl
0x1400a7527  cmp     [rsp+78h+arg_20], 0
0x1400a752f  jz      loc_1400A76A1
0x1400a7535  mov     eax, [rbx+220h]
0x1400a753b  mov     r8d, [rbx+224h]
0x1400a7542  cmp     eax, r8d
0x1400a7545  jz      loc_1400A75D7
0x1400a754b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7552  cmp     rcx, r10
0x1400a7555  jz      short loc_1400A7585
0x1400a7557  mov     eax, [rcx+2Ch]
0x1400a755a  test    al, 2
0x1400a755c  jz      short loc_1400A7585
0x1400a755e  cmp     byte ptr [rcx+29h], 5
0x1400a7562  jb      short loc_1400A7585
0x1400a7564  mov     rcx, [rcx+18h]
0x1400a7568  mov     edx, 0Dh
0x1400a756d  mov     r9d, [rbx+220h]
0x1400a7574  mov     dword ptr [rsp+78h+var_58], r8d
0x1400a7579  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a7580  call    WPP_SF_Dd
0x1400a7585  mov     eax, [rbx+224h]
0x1400a758b  mov     [rbx+220h], eax
0x1400a7591  lea     rax, [r15-1]
0x1400a7595  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400a7599  ja      short loc_1400A75D7
0x1400a759b  mov     edx, [rbx+220h]
0x1400a75a1  mov     rcx, r15
0x1400a75a4  call    cs:__imp_KeSetActualBasePriorityThread
0x1400a75ab  nop     dword ptr [rax+rax+00h]
0x1400a75b0  mov     edx, [rbx+220h]
0x1400a75b6  cmp     eax, edx
0x1400a75b8  jle     short loc_1400A75D7
0x1400a75ba  mov     edx, eax
0x1400a75bc  mov     [rbx+220h], eax
0x1400a75c2  mov     rcx, r15
0x1400a75c5  mov     [rbx+224h], eax
0x1400a75cb  call    cs:__imp_KeSetActualBasePriorityThread
0x1400a75d2  nop     dword ptr [rax+rax+00h]
0x1400a75d7  mov     eax, [rbx+228h]
0x1400a75dd  mov     r8d, [rbx+22Ch]
0x1400a75e4  cmp     eax, r8d
0x1400a75e7  jz      short loc_1400A7638
0x1400a75e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a75f0  lea     r15, WPP_GLOBAL_Control
0x1400a75f7  cmp     rcx, r15
0x1400a75fa  jz      short loc_1400A762A
0x1400a75fc  mov     eax, [rcx+2Ch]
0x1400a75ff  test    al, 2
0x1400a7601  jz      short loc_1400A762A
0x1400a7603  cmp     byte ptr [rcx+29h], 5
0x1400a7607  jb      short loc_1400A762A
0x1400a7609  mov     rcx, [rcx+18h]
0x1400a760d  mov     edx, 0Eh
0x1400a7612  mov     r9d, [rbx+228h]
0x1400a7619  mov     dword ptr [rsp+78h+var_58], r8d
0x1400a761e  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a7625  call    WPP_SF_Dd
0x1400a762a  mov     eax, [rbx+22Ch]
0x1400a7630  mov     [rbx+228h], eax
0x1400a7636  jmp     short loc_1400A763F
0x1400a7638  lea     r15, WPP_GLOBAL_Control
0x1400a763f  mov     al, [rbx+234h]
0x1400a7645  movzx   edx, byte ptr [rbx+235h]
0x1400a764c  cmp     al, dl
0x1400a764e  jz      short loc_1400A76A8
0x1400a7650  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7657  cmp     rcx, r15
0x1400a765a  jz      short loc_1400A7693
0x1400a765c  mov     eax, [rcx+2Ch]
0x1400a765f  test    al, 2
0x1400a7661  jz      short loc_1400A7693
0x1400a7663  cmp     byte ptr [rcx+29h], 5
0x1400a7667  jb      short loc_1400A7693
0x1400a7669  movzx   r9d, byte ptr [rbx+234h]
0x1400a7671  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a7678  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a767f  mov     eax, edx
0x1400a7681  mov     edx, 0Fh
0x1400a7686  mov     dword ptr [rsp+78h+var_58], eax
0x1400a768a  mov     rcx, [rcx+18h]
0x1400a768e  call    WPP_SF_Dd
0x1400a7693  mov     al, [rbx+235h]
0x1400a7699  mov     [rbx+234h], al
0x1400a769f  jmp     short loc_1400A76A8
0x1400a76a1  lea     r15, WPP_GLOBAL_Control
0x1400a76a8  mov     dl, [rsp+78h+NewIrql]; NewIrql
0x1400a76af  mov     rcx, r13; SpinLock
0x1400a76b2  mov     bpl, [rbx+234h]
0x1400a76b9  call    cs:__imp_KeReleaseSpinLock
0x1400a76c0  nop     dword ptr [rax+rax+00h]
0x1400a76c5  test    edi, edi
0x1400a76c7  jle     short loc_1400A7724
0x1400a76c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a76d0  cmp     rcx, r15
0x1400a76d3  jz      short loc_1400A7706
0x1400a76d5  mov     eax, [rcx+2Ch]
0x1400a76d8  test    al, 2
0x1400a76da  jz      short loc_1400A7706
0x1400a76dc  cmp     byte ptr [rcx+29h], 5
0x1400a76e0  jb      short loc_1400A7706
0x1400a76e2  mov     rax, [rbx+238h]
0x1400a76e9  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a76f0  mov     rcx, [rcx+18h]
0x1400a76f4  mov     edx, 10h
0x1400a76f9  mov     r9d, r14d
0x1400a76fc  mov     [rsp+78h+var_58], rax
0x1400a7701  call    WPP_SF_Lq
0x1400a7706  mov     rcx, [rbx+238h]
0x1400a770d  xor     r9d, r9d
0x1400a7710  xor     r8d, r8d
0x1400a7713  mov     edx, r14d
0x1400a7716  call    cs:__imp_IoBoostThreadIo
0x1400a771d  nop     dword ptr [rax+rax+00h]
0x1400a7722  jmp     short loc_1400A777D
0x1400a7724  jns     short loc_1400A777D
0x1400a7726  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a772d  cmp     rcx, r15
0x1400a7730  jz      short loc_1400A775B
0x1400a7732  mov     eax, [rcx+2Ch]
0x1400a7735  test    al, 2
0x1400a7737  jz      short loc_1400A775B
0x1400a7739  cmp     byte ptr [rcx+29h], 5
0x1400a773d  jb      short loc_1400A775B
0x1400a773f  mov     r9, [rbx+238h]
0x1400a7746  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a774d  mov     rcx, [rcx+18h]
0x1400a7751  mov     edx, 11h
0x1400a7756  call    WPP_SF_q
0x1400a775b  mov     rcx, [rbx+238h]
0x1400a7762  xor     r9d, r9d
0x1400a7765  mov     r8b, 1
0x1400a7768  lea     edx, [r9+1]
0x1400a776c  call    cs:__imp_IoBoostThreadIo
0x1400a7773  nop     dword ptr [rax+rax+00h]
0x1400a7778  add     edi, 1
0x1400a777b  js      short loc_1400A7726
0x1400a777d  mov     rcx, [rbx+130h]
0x1400a7784  mov     r9b, r12b
0x1400a7787  mov     r8b, bpl
0x1400a778a  mov     edx, esi
0x1400a778c  call    FveTransformUpdatePriority
0x1400a7791  add     rsp, 38h
0x1400a7795  pop     r15
0x1400a7797  pop     r14
0x1400a7799  pop     r13
0x1400a779b  pop     r12
0x1400a779d  pop     rdi
0x1400a779e  pop     rsi
0x1400a779f  pop     rbp
0x1400a77a0  pop     rbx
0x1400a77a1  retn
```

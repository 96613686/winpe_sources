# UxSslAllocateTransportDataIndication

- ea: `0x140077310`
- end: `0x140077758`
- name: `UxSslAllocateTransportDataIndication`
- size: `1096`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140065220`
- `0x140076760`
- `0x1400778f0`
- `0x1400a89d0`

## callees

- `0x140049d08`
- `0x1400513f0`
- `0x140077310`
- `0x1401678f0`
- `0x1401c49c4`
- `0x1401c4b0c`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14007739b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400774ba`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14007739b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400774ba`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007762b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007765c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007767a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400776c9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007762b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007765c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007767a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400776c9`
- `ntoskrnl!ExAllocatePool3` at `0x140178a07`
- `ntoskrnl!ExAllocatePool3` at `0x140178a07`
- `ntoskrnl!KeInitializeSpinLock` at `0x140077410`
- `ntoskrnl!KeInitializeSpinLock` at `0x140077410`

## pseudocode

```c
__int64 __fastcall UxSslAllocateTransportDataIndication(unsigned int a1, _QWORD *a2)
{
  __int64 v3; // rdi
  int v4; // r14d
  int v5; // ebp
  unsigned __int64 v6; // rbx
  char *v7; // rax
  char *v8; // rbx
  unsigned int v9; // ebp
  int v11; // ebp
  unsigned __int64 v12; // rbx
  char *v13; // rax
  unsigned int LockArray_high; // ebp
  __int64 v15; // rcx
  __int64 CurrentNodeNumber; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  USHORT v20; // ax
  __int64 v21; // rbx
  __int64 v22; // rbx
  USHORT v23; // ax
  unsigned int v24; // ebp
  __int64 v25; // rbx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 Pool3; // rax

  v3 = a1;
  v4 = 2;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_dq(1041, 14, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, a2);
  *a2 = 0;
  if ( (unsigned int)v3 > 0x905 )
  {
    if ( (unsigned int)v3 <= 0x2105 )
    {
      LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
      if ( UxDebugDisableLookaside )
      {
        v17 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0660)(
                (unsigned int)dword_1401A0648,
                qword_1401A0650,
                (unsigned int)dword_1401A0658,
                0);
      }
      else
      {
        if ( UxCompactMode )
        {
          v21 = qword_1401A0640;
          CurrentNodeNumber = KeGetCurrentNodeNumber();
          v15 = v21;
        }
        else
        {
          v15 = qword_1401A0640;
          CurrentNodeNumber = LockArray_high;
        }
        v17 = PplAllocateFromLookasideListProcessor(v15, CurrentNodeNumber);
      }
      v8 = (char *)v17;
      if ( v17 )
      {
        *(_QWORD *)(v17 + 4) = 0;
        *(_DWORD *)(v17 + 12) = 0;
        *(_QWORD *)(v17 + 24) = 0;
        *(_OWORD *)(v17 + 96) = 0;
        *(_OWORD *)(v17 + 112) = 0;
        *(_DWORD *)v17 = LockArray_high;
        v9 = 0;
        v4 = 1;
        goto LABEL_11;
      }
    }
    else if ( (unsigned int)v3 > 0x4105 )
    {
      if ( UxSslLargeBufferEnabled && (unsigned int)v3 <= 0x820A )
      {
        v24 = HIDWORD(KeGetPcr()[1].LockArray);
        if ( UxDebugDisableLookaside )
        {
          v18 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A06C0)(
                  (unsigned int)dword_1401A06A8,
                  qword_1401A06B0,
                  (unsigned int)dword_1401A06B8,
                  0);
        }
        else
        {
          if ( UxCompactMode )
          {
            v25 = qword_1401A06A0;
            v26 = KeGetCurrentNodeNumber();
            v27 = v25;
          }
          else
          {
            v27 = qword_1401A06A0;
            v26 = v24;
          }
          v18 = PplAllocateFromLookasideListProcessor(v27, v26);
        }
        v8 = (char *)v18;
        if ( v18 )
        {
          *(_QWORD *)(v18 + 4) = 0;
          *(_DWORD *)(v18 + 12) = 0;
          *(_QWORD *)(v18 + 24) = 0;
          *(_OWORD *)(v18 + 96) = 0;
          *(_OWORD *)(v18 + 112) = 0;
          *(_DWORD *)v18 = v24;
          v9 = 0;
          v4 = 3;
          goto LABEL_11;
        }
      }
      else
      {
        Pool3 = ExAllocatePool3(66, v3 + 128, 1280538709, UxLowPriorityPool, 1);
        v8 = (char *)Pool3;
        if ( Pool3 )
        {
          v9 = 0;
          *(_OWORD *)Pool3 = 0;
          v4 = 4;
          *(_QWORD *)(Pool3 + 24) = 0;
          *(_OWORD *)(Pool3 + 96) = 0;
          *(_OWORD *)(Pool3 + 112) = 0;
          goto LABEL_11;
        }
      }
    }
    else
    {
      v11 = HIDWORD(KeGetPcr()[1].LockArray);
      if ( UxDebugDisableLookaside )
      {
        v13 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0690)(
                        (unsigned int)dword_1401A0678,
                        qword_1401A0680,
                        (unsigned int)dword_1401A0688,
                        0);
      }
      else if ( UxCompactMode )
      {
        v22 = qword_1401A0670;
        v23 = KeGetCurrentNodeNumber();
        v13 = (char *)PplAllocateFromLookasideListProcessor(v22, v23);
      }
      else
      {
        v12 = qword_1401A0670 + ((unsigned __int64)(unsigned int)(v11 + 1) << 7);
        if ( !*(_BYTE *)(v12 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0670, v12 + 64);
        v13 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v12 + 64));
      }
      v8 = v13;
      if ( v13 )
      {
        *(_QWORD *)(v13 + 4) = 0;
        *((_DWORD *)v13 + 3) = 0;
        *((_QWORD *)v13 + 3) = 0;
        *((_OWORD *)v13 + 6) = 0;
        *((_OWORD *)v13 + 7) = 0;
        *(_DWORD *)v13 = v11;
        v9 = 0;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v5 = HIDWORD(KeGetPcr()[1].LockArray);
    if ( UxDebugDisableLookaside )
    {
      v7 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0630)(
                     (unsigned int)dword_1401A0618,
                     qword_1401A0620,
                     (unsigned int)dword_1401A0628,
                     0);
    }
    else if ( UxCompactMode )
    {
      v19 = qword_1401A0610;
      v20 = KeGetCurrentNodeNumber();
      v7 = (char *)PplAllocateFromLookasideListProcessor(v19, v20);
    }
    else
    {
      v6 = qword_1401A0610 + ((unsigned __int64)(unsigned int)(v5 + 1) << 7);
      if ( !*(_BYTE *)(v6 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0610, v6 + 64);
      v7 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v6 + 64));
    }
    v8 = v7;
    if ( v7 )
    {
      *(_QWORD *)(v7 + 4) = 0;
      *((_DWORD *)v7 + 3) = 0;
      *((_QWORD *)v7 + 3) = 0;
      *((_OWORD *)v7 + 6) = 0;
      *((_OWORD *)v7 + 7) = 0;
      *(_DWORD *)v7 = v5;
      v9 = 0;
      v4 = 0;
LABEL_11:
      *((_DWORD *)v8 + 5) = 1;
      *((_DWORD *)v8 + 4) = 1280538709;
      *((_QWORD *)v8 + 5) = v8 + 32;
      *((_QWORD *)v8 + 4) = v8 + 32;
      *((_QWORD *)v8 + 7) = v8 + 48;
      *((_QWORD *)v8 + 6) = v8 + 48;
      *((_QWORD *)v8 + 9) = v8 + 64;
      *((_QWORD *)v8 + 8) = v8 + 64;
      *((_QWORD *)v8 + 11) = v8 + 80;
      *((_QWORD *)v8 + 10) = v8 + 80;
      KeInitializeSpinLock((PKSPIN_LOCK)v8 + 3);
      *((_DWORD *)v8 + 30) = v4;
      *((_QWORD *)v8 + 12) = v8 + 128;
      *((_DWORD *)v8 + 27) = v3;
      *a2 = v8;
      goto LABEL_12;
    }
  }
  v9 = -1073741670;
LABEL_12:
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_LqL(1041, 15, WPP_6033a49e77e7395416619077875677ff_Traceguids, v9, *a2, v4);
  return v9;
}

```

## disassembly

```asm
0x140077310  mov     [rsp+arg_18], rsi
0x140077315  push    r14
0x140077317  sub     rsp, 30h
0x14007731b  mov     [rsp+38h+arg_10], rdi
0x140077320  mov     rsi, rdx
0x140077323  mov     edi, ecx
0x140077325  mov     r14d, 2
0x14007732b  test    byte ptr cs:xmmword_1401A2CA0+2, r14b
0x140077332  jnz     loc_1400776F0
0x140077338  mov     [rsp+38h+arg_0], rbx
0x14007733d  mov     [rsp+38h+arg_8], rbp
0x140077342  mov     qword ptr [rsi], 0
0x140077349  cmp     edi, 905h
0x14007734f  ja      loc_14007745C
0x140077355  mov     ebp, gs:1A4h
0x14007735d  cmp     cs:UxDebugDisableLookaside, 0
0x140077364  jnz     loc_1400774F3
0x14007736a  cmp     cs:UxCompactMode, 0
0x140077371  jnz     loc_140077624
0x140077377  mov     rcx, cs:qword_1401A0610
0x14007737e  lea     ebx, [rbp+1]
0x140077381  shl     rbx, 7
0x140077385  add     rbx, rcx
0x140077388  movzx   eax, byte ptr [rbx+0B0h]
0x14007738f  test    al, al
0x140077391  jz      loc_140077647
0x140077397  lea     rcx, [rbx+40h]; Lookaside
0x14007739b  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400773a2  nop     dword ptr [rax+rax+00h]
0x1400773a7  mov     rbx, rax
0x1400773aa  test    rax, rax
0x1400773ad  jz      loc_1400775EF
0x1400773b3  xor     eax, eax
0x1400773b5  xorps   xmm0, xmm0
0x1400773b8  mov     [rbx+4], rax
0x1400773bc  mov     [rbx+0Ch], eax
0x1400773bf  mov     [rbx+18h], rax
0x1400773c3  movups  xmmword ptr [rbx+60h], xmm0
0x1400773c7  movups  xmmword ptr [rbx+70h], xmm0
0x1400773cb  mov     [rbx], ebp
0x1400773cd  xor     ebp, ebp
0x1400773cf  xor     r14d, r14d
0x1400773d2  mov     dword ptr [rbx+14h], 1
0x1400773d9  lea     rax, [rbx+20h]
0x1400773dd  mov     dword ptr [rbx+10h], 4C537855h
0x1400773e4  lea     rcx, [rbx+18h]; SpinLock
0x1400773e8  mov     [rax+8], rax
0x1400773ec  mov     [rax], rax
0x1400773ef  lea     rax, [rbx+30h]
0x1400773f3  mov     [rax+8], rax
0x1400773f7  mov     [rax], rax
0x1400773fa  lea     rax, [rbx+40h]
0x1400773fe  mov     [rax+8], rax
0x140077402  mov     [rax], rax
0x140077405  lea     rax, [rbx+50h]
0x140077409  mov     [rax+8], rax
0x14007740d  mov     [rax], rax
0x140077410  call    cs:__imp_KeInitializeSpinLock
0x140077417  nop     dword ptr [rax+rax+00h]
0x14007741c  lea     rax, [rbx+80h]
0x140077423  mov     [rbx+78h], r14d
0x140077427  mov     [rbx+60h], rax
0x14007742b  mov     [rbx+6Ch], edi
0x14007742e  mov     [rsi], rbx
0x140077431  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140077438  mov     rdi, [rsp+38h+arg_10]
0x14007743d  mov     rbx, [rsp+38h+arg_0]
0x140077442  jnz     loc_1400775F9
0x140077448  mov     rsi, [rsp+38h+arg_18]
0x14007744d  mov     eax, ebp
0x14007744f  mov     rbp, [rsp+38h+arg_8]
0x140077454  add     rsp, 30h
0x140077458  pop     r14
0x14007745a  retn
0x14007745c  cmp     edi, 2105h
0x140077462  jbe     loc_140077540
0x140077468  cmp     edi, 4105h
0x14007746e  ja      loc_140077713
0x140077474  mov     ebp, gs:1A4h
0x14007747c  cmp     cs:UxDebugDisableLookaside, 0
0x140077483  jnz     loc_14007751B
0x140077489  cmp     cs:UxCompactMode, 0
0x140077490  jnz     loc_140077673
0x140077496  mov     rcx, cs:qword_1401A0670
0x14007749d  lea     ebx, [rbp+1]
0x1400774a0  shl     rbx, 7
0x1400774a4  add     rbx, rcx
0x1400774a7  movzx   eax, byte ptr [rbx+0B0h]
0x1400774ae  test    al, al
0x1400774b0  jz      loc_140077696
0x1400774b6  lea     rcx, [rbx+40h]; Lookaside
0x1400774ba  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400774c1  nop     dword ptr [rax+rax+00h]
0x1400774c6  mov     rbx, rax
0x1400774c9  test    rax, rax
0x1400774cc  jz      loc_1400775EF
0x1400774d2  xor     eax, eax
0x1400774d4  xorps   xmm0, xmm0
0x1400774d7  mov     [rbx+4], rax
0x1400774db  mov     [rbx+0Ch], eax
0x1400774de  mov     [rbx+18h], rax
0x1400774e2  movups  xmmword ptr [rbx+60h], xmm0
0x1400774e6  movups  xmmword ptr [rbx+70h], xmm0
0x1400774ea  mov     [rbx], ebp
0x1400774ec  xor     ebp, ebp
0x1400774ee  jmp     loc_1400773D2
0x1400774f3  mov     rax, cs:off_1401A0630
0x1400774fa  xor     r9d, r9d
0x1400774fd  mov     r8d, cs:dword_1401A0628
0x140077504  mov     rdx, cs:qword_1401A0620
0x14007750b  mov     ecx, cs:dword_1401A0618
0x140077511  call    _guard_dispatch_icall
0x140077516  jmp     loc_1400773A7
0x14007751b  mov     rax, cs:off_1401A0690
0x140077522  xor     r9d, r9d
0x140077525  mov     r8d, cs:dword_1401A0688
0x14007752c  mov     rdx, cs:qword_1401A0680
0x140077533  mov     ecx, cs:dword_1401A0678
0x140077539  call    _guard_dispatch_icall
0x14007753e  jmp     short loc_1400774C6
0x140077540  mov     ebp, gs:1A4h
0x140077548  cmp     cs:UxDebugDisableLookaside, 0
0x14007754f  jnz     short loc_14007759B
0x140077551  cmp     cs:UxCompactMode, 0
0x140077558  jnz     loc_140077655
0x14007755e  mov     rcx, cs:qword_1401A0640
0x140077565  mov     edx, ebp
0x140077567  call    PplAllocateFromLookasideListProcessor
0x14007756c  mov     rbx, rax
0x14007756f  test    rax, rax
0x140077572  jz      short loc_1400775EF
0x140077574  xor     eax, eax
0x140077576  xorps   xmm0, xmm0
0x140077579  mov     [rbx+4], rax
0x14007757d  mov     [rbx+0Ch], eax
0x140077580  mov     [rbx+18h], rax
0x140077584  movups  xmmword ptr [rbx+60h], xmm0
0x140077588  movups  xmmword ptr [rbx+70h], xmm0
0x14007758c  mov     [rbx], ebp
0x14007758e  xor     ebp, ebp
0x140077590  mov     r14d, 1
0x140077596  jmp     loc_1400773D2
0x14007759b  mov     rax, cs:off_1401A0660
0x1400775a2  xor     r9d, r9d
0x1400775a5  mov     r8d, cs:dword_1401A0658
0x1400775ac  mov     rdx, cs:qword_1401A0650
0x1400775b3  mov     ecx, cs:dword_1401A0648
0x1400775b9  call    _guard_dispatch_icall
0x1400775be  jmp     short loc_14007756C
0x1400775c0  mov     rax, cs:off_1401A06C0
0x1400775c7  xor     r9d, r9d
0x1400775ca  mov     r8d, cs:dword_1401A06B8
0x1400775d1  mov     rdx, cs:qword_1401A06B0
0x1400775d8  mov     ecx, cs:dword_1401A06A8
0x1400775de  call    _guard_dispatch_icall
0x1400775e3  mov     rbx, rax
0x1400775e6  test    rax, rax
0x1400775e9  jnz     loc_140077731
0x1400775ef  mov     ebp, 0C000009Ah
0x1400775f4  jmp     loc_140077431
0x1400775f9  mov     r9, [rsi]
0x1400775fc  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x140077603  mov     [rsp+38h+var_10], r14d
0x140077608  mov     edx, 0Fh
0x14007760d  mov     [rsp+38h+var_18], r9
0x140077612  mov     ecx, 411h
0x140077617  mov     r9d, ebp
0x14007761a  call    WPP_SF_LqL
0x14007761f  jmp     loc_140077448
0x140077624  mov     rbx, cs:qword_1401A0610
0x14007762b  call    cs:__imp_KeGetCurrentNodeNumber
0x140077632  nop     dword ptr [rax+rax+00h]
0x140077637  movzx   edx, ax
0x14007763a  mov     rcx, rbx
0x14007763d  call    PplAllocateFromLookasideListProcessor
0x140077642  jmp     loc_1400773A7
0x140077647  lea     rdx, [rbx+40h]
0x14007764b  call    PplpLazyInitializeLookasideList
0x140077650  jmp     loc_140077397
0x140077655  mov     rbx, cs:qword_1401A0640
0x14007765c  call    cs:__imp_KeGetCurrentNodeNumber
0x140077663  nop     dword ptr [rax+rax+00h]
0x140077668  movzx   edx, ax
0x14007766b  mov     rcx, rbx
0x14007766e  jmp     loc_140077567
0x140077673  mov     rbx, cs:qword_1401A0670
0x14007767a  call    cs:__imp_KeGetCurrentNodeNumber
0x140077681  nop     dword ptr [rax+rax+00h]
0x140077686  movzx   edx, ax
0x140077689  mov     rcx, rbx
0x14007768c  call    PplAllocateFromLookasideListProcessor
0x140077691  jmp     loc_1400774C6
0x140077696  lea     rdx, [rbx+40h]
0x14007769a  call    PplpLazyInitializeLookasideList
0x14007769f  jmp     loc_1400774B6
0x1400776a4  mov     ebp, gs:1A4h
0x1400776ac  cmp     cs:UxDebugDisableLookaside, 0
0x1400776b3  jnz     loc_1400775C0
0x1400776b9  cmp     cs:UxCompactMode, 0
0x1400776c0  jz      short loc_1400776E5
0x1400776c2  mov     rbx, cs:qword_1401A06A0
0x1400776c9  call    cs:__imp_KeGetCurrentNodeNumber
0x1400776d0  nop     dword ptr [rax+rax+00h]
0x1400776d5  movzx   edx, ax
0x1400776d8  mov     rcx, rbx
0x1400776db  call    PplAllocateFromLookasideListProcessor
0x1400776e0  jmp     loc_1400775E3
0x1400776e5  mov     rcx, cs:qword_1401A06A0
0x1400776ec  mov     edx, ebp
0x1400776ee  jmp     short loc_1400776DB
0x1400776f0  mov     edx, 0Eh
0x1400776f5  mov     [rsp+38h+var_18], rsi
0x1400776fa  mov     ecx, 411h
0x1400776ff  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x140077706  mov     r9d, edi
0x140077709  call    WPP_SF_dq
0x14007770e  jmp     loc_140077338
0x140077713  cmp     cs:UxSslLargeBufferEnabled, 0
0x14007771a  jz      loc_1401789E6
0x140077720  cmp     edi, 820Ah
0x140077726  ja      loc_1401789E6
0x14007772c  jmp     loc_1400776A4
0x140077731  xor     eax, eax
0x140077733  xorps   xmm0, xmm0
0x140077736  mov     [rbx+4], rax
0x14007773a  mov     [rbx+0Ch], eax
0x14007773d  mov     [rbx+18h], rax
0x140077741  movups  xmmword ptr [rbx+60h], xmm0
0x140077745  movups  xmmword ptr [rbx+70h], xmm0
0x140077749  mov     [rbx], ebp
0x14007774b  xor     ebp, ebp
0x14007774d  mov     r14d, 3
0x140077753  jmp     loc_1400773D2
0x1401789e6  lea     rdx, [rdi+80h]
0x1401789ed  mov     dword ptr [rsp+38h+var_18], 1
0x1401789f5  lea     r9, UxLowPriorityPool
0x1401789fc  mov     ecx, 42h ; 'B'
0x140178a01  mov     r8d, 4C537855h
0x140178a07  call    cs:__imp_ExAllocatePool3
0x140178a0e  nop     dword ptr [rax+rax+00h]
0x140178a13  mov     rbx, rax
0x140178a16  test    rax, rax
0x140178a19  jz      loc_1400775EF
0x140178a1f  xorps   xmm0, xmm0
0x140178a22  xor     ebp, ebp
0x140178a24  movaps  xmmword ptr [rax], xmm0
0x140178a27  mov     r14d, 4
0x140178a2d  xor     eax, eax
0x140178a2f  mov     [rbx+18h], rax
0x140178a33  movups  xmmword ptr [rbx+60h], xmm0
0x140178a37  movups  xmmword ptr [rbx+70h], xmm0
0x140178a3b  jmp     loc_1400773D2
```

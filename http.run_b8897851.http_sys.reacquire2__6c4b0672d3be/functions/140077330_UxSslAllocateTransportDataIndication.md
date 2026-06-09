# UxSslAllocateTransportDataIndication

- ea: `0x140077330`
- end: `0x140077778`
- name: `UxSslAllocateTransportDataIndication`
- size: `1096`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140065240`
- `0x140076780`
- `0x140077910`
- `0x1400a89f0`

## callees

- `0x140049d28`
- `0x140051410`
- `0x140077330`
- `0x1401677e0`
- `0x1401c49c4`
- `0x1401c4b0c`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400773bb`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400774da`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400773bb`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400774da`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007764b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007767c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007769a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400776e9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007764b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007767c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007769a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400776e9`
- `ntoskrnl!ExAllocatePool3` at `0x140178907`
- `ntoskrnl!ExAllocatePool3` at `0x140178907`
- `ntoskrnl!KeInitializeSpinLock` at `0x140077430`
- `ntoskrnl!KeInitializeSpinLock` at `0x140077430`

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
0x140077330  mov     [rsp+arg_18], rsi
0x140077335  push    r14
0x140077337  sub     rsp, 30h
0x14007733b  mov     [rsp+38h+arg_10], rdi
0x140077340  mov     rsi, rdx
0x140077343  mov     edi, ecx
0x140077345  mov     r14d, 2
0x14007734b  test    byte ptr cs:xmmword_1401A2CA0+2, r14b
0x140077352  jnz     loc_140077710
0x140077358  mov     [rsp+38h+arg_0], rbx
0x14007735d  mov     [rsp+38h+arg_8], rbp
0x140077362  mov     qword ptr [rsi], 0
0x140077369  cmp     edi, 905h
0x14007736f  ja      loc_14007747C
0x140077375  mov     ebp, gs:1A4h
0x14007737d  cmp     cs:UxDebugDisableLookaside, 0
0x140077384  jnz     loc_140077513
0x14007738a  cmp     cs:UxCompactMode, 0
0x140077391  jnz     loc_140077644
0x140077397  mov     rcx, cs:qword_1401A0610
0x14007739e  lea     ebx, [rbp+1]
0x1400773a1  shl     rbx, 7
0x1400773a5  add     rbx, rcx
0x1400773a8  movzx   eax, byte ptr [rbx+0B0h]
0x1400773af  test    al, al
0x1400773b1  jz      loc_140077667
0x1400773b7  lea     rcx, [rbx+40h]; Lookaside
0x1400773bb  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400773c2  nop     dword ptr [rax+rax+00h]
0x1400773c7  mov     rbx, rax
0x1400773ca  test    rax, rax
0x1400773cd  jz      loc_14007760F
0x1400773d3  xor     eax, eax
0x1400773d5  xorps   xmm0, xmm0
0x1400773d8  mov     [rbx+4], rax
0x1400773dc  mov     [rbx+0Ch], eax
0x1400773df  mov     [rbx+18h], rax
0x1400773e3  movups  xmmword ptr [rbx+60h], xmm0
0x1400773e7  movups  xmmword ptr [rbx+70h], xmm0
0x1400773eb  mov     [rbx], ebp
0x1400773ed  xor     ebp, ebp
0x1400773ef  xor     r14d, r14d
0x1400773f2  mov     dword ptr [rbx+14h], 1
0x1400773f9  lea     rax, [rbx+20h]
0x1400773fd  mov     dword ptr [rbx+10h], 4C537855h
0x140077404  lea     rcx, [rbx+18h]; SpinLock
0x140077408  mov     [rax+8], rax
0x14007740c  mov     [rax], rax
0x14007740f  lea     rax, [rbx+30h]
0x140077413  mov     [rax+8], rax
0x140077417  mov     [rax], rax
0x14007741a  lea     rax, [rbx+40h]
0x14007741e  mov     [rax+8], rax
0x140077422  mov     [rax], rax
0x140077425  lea     rax, [rbx+50h]
0x140077429  mov     [rax+8], rax
0x14007742d  mov     [rax], rax
0x140077430  call    cs:__imp_KeInitializeSpinLock
0x140077437  nop     dword ptr [rax+rax+00h]
0x14007743c  lea     rax, [rbx+80h]
0x140077443  mov     [rbx+78h], r14d
0x140077447  mov     [rbx+60h], rax
0x14007744b  mov     [rbx+6Ch], edi
0x14007744e  mov     [rsi], rbx
0x140077451  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140077458  mov     rdi, [rsp+38h+arg_10]
0x14007745d  mov     rbx, [rsp+38h+arg_0]
0x140077462  jnz     loc_140077619
0x140077468  mov     rsi, [rsp+38h+arg_18]
0x14007746d  mov     eax, ebp
0x14007746f  mov     rbp, [rsp+38h+arg_8]
0x140077474  add     rsp, 30h
0x140077478  pop     r14
0x14007747a  retn
0x14007747c  cmp     edi, 2105h
0x140077482  jbe     loc_140077560
0x140077488  cmp     edi, 4105h
0x14007748e  ja      loc_140077733
0x140077494  mov     ebp, gs:1A4h
0x14007749c  cmp     cs:UxDebugDisableLookaside, 0
0x1400774a3  jnz     loc_14007753B
0x1400774a9  cmp     cs:UxCompactMode, 0
0x1400774b0  jnz     loc_140077693
0x1400774b6  mov     rcx, cs:qword_1401A0670
0x1400774bd  lea     ebx, [rbp+1]
0x1400774c0  shl     rbx, 7
0x1400774c4  add     rbx, rcx
0x1400774c7  movzx   eax, byte ptr [rbx+0B0h]
0x1400774ce  test    al, al
0x1400774d0  jz      loc_1400776B6
0x1400774d6  lea     rcx, [rbx+40h]; Lookaside
0x1400774da  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400774e1  nop     dword ptr [rax+rax+00h]
0x1400774e6  mov     rbx, rax
0x1400774e9  test    rax, rax
0x1400774ec  jz      loc_14007760F
0x1400774f2  xor     eax, eax
0x1400774f4  xorps   xmm0, xmm0
0x1400774f7  mov     [rbx+4], rax
0x1400774fb  mov     [rbx+0Ch], eax
0x1400774fe  mov     [rbx+18h], rax
0x140077502  movups  xmmword ptr [rbx+60h], xmm0
0x140077506  movups  xmmword ptr [rbx+70h], xmm0
0x14007750a  mov     [rbx], ebp
0x14007750c  xor     ebp, ebp
0x14007750e  jmp     loc_1400773F2
0x140077513  mov     rax, cs:off_1401A0630
0x14007751a  xor     r9d, r9d
0x14007751d  mov     r8d, cs:dword_1401A0628
0x140077524  mov     rdx, cs:qword_1401A0620
0x14007752b  mov     ecx, cs:dword_1401A0618
0x140077531  call    _guard_dispatch_icall
0x140077536  jmp     loc_1400773C7
0x14007753b  mov     rax, cs:off_1401A0690
0x140077542  xor     r9d, r9d
0x140077545  mov     r8d, cs:dword_1401A0688
0x14007754c  mov     rdx, cs:qword_1401A0680
0x140077553  mov     ecx, cs:dword_1401A0678
0x140077559  call    _guard_dispatch_icall
0x14007755e  jmp     short loc_1400774E6
0x140077560  mov     ebp, gs:1A4h
0x140077568  cmp     cs:UxDebugDisableLookaside, 0
0x14007756f  jnz     short loc_1400775BB
0x140077571  cmp     cs:UxCompactMode, 0
0x140077578  jnz     loc_140077675
0x14007757e  mov     rcx, cs:qword_1401A0640
0x140077585  mov     edx, ebp
0x140077587  call    PplAllocateFromLookasideListProcessor
0x14007758c  mov     rbx, rax
0x14007758f  test    rax, rax
0x140077592  jz      short loc_14007760F
0x140077594  xor     eax, eax
0x140077596  xorps   xmm0, xmm0
0x140077599  mov     [rbx+4], rax
0x14007759d  mov     [rbx+0Ch], eax
0x1400775a0  mov     [rbx+18h], rax
0x1400775a4  movups  xmmword ptr [rbx+60h], xmm0
0x1400775a8  movups  xmmword ptr [rbx+70h], xmm0
0x1400775ac  mov     [rbx], ebp
0x1400775ae  xor     ebp, ebp
0x1400775b0  mov     r14d, 1
0x1400775b6  jmp     loc_1400773F2
0x1400775bb  mov     rax, cs:off_1401A0660
0x1400775c2  xor     r9d, r9d
0x1400775c5  mov     r8d, cs:dword_1401A0658
0x1400775cc  mov     rdx, cs:qword_1401A0650
0x1400775d3  mov     ecx, cs:dword_1401A0648
0x1400775d9  call    _guard_dispatch_icall
0x1400775de  jmp     short loc_14007758C
0x1400775e0  mov     rax, cs:off_1401A06C0
0x1400775e7  xor     r9d, r9d
0x1400775ea  mov     r8d, cs:dword_1401A06B8
0x1400775f1  mov     rdx, cs:qword_1401A06B0
0x1400775f8  mov     ecx, cs:dword_1401A06A8
0x1400775fe  call    _guard_dispatch_icall
0x140077603  mov     rbx, rax
0x140077606  test    rax, rax
0x140077609  jnz     loc_140077751
0x14007760f  mov     ebp, 0C000009Ah
0x140077614  jmp     loc_140077451
0x140077619  mov     r9, [rsi]
0x14007761c  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x140077623  mov     [rsp+38h+var_10], r14d
0x140077628  mov     edx, 0Fh
0x14007762d  mov     [rsp+38h+var_18], r9
0x140077632  mov     ecx, 411h
0x140077637  mov     r9d, ebp
0x14007763a  call    WPP_SF_LqL
0x14007763f  jmp     loc_140077468
0x140077644  mov     rbx, cs:qword_1401A0610
0x14007764b  call    cs:__imp_KeGetCurrentNodeNumber
0x140077652  nop     dword ptr [rax+rax+00h]
0x140077657  movzx   edx, ax
0x14007765a  mov     rcx, rbx
0x14007765d  call    PplAllocateFromLookasideListProcessor
0x140077662  jmp     loc_1400773C7
0x140077667  lea     rdx, [rbx+40h]
0x14007766b  call    PplpLazyInitializeLookasideList
0x140077670  jmp     loc_1400773B7
0x140077675  mov     rbx, cs:qword_1401A0640
0x14007767c  call    cs:__imp_KeGetCurrentNodeNumber
0x140077683  nop     dword ptr [rax+rax+00h]
0x140077688  movzx   edx, ax
0x14007768b  mov     rcx, rbx
0x14007768e  jmp     loc_140077587
0x140077693  mov     rbx, cs:qword_1401A0670
0x14007769a  call    cs:__imp_KeGetCurrentNodeNumber
0x1400776a1  nop     dword ptr [rax+rax+00h]
0x1400776a6  movzx   edx, ax
0x1400776a9  mov     rcx, rbx
0x1400776ac  call    PplAllocateFromLookasideListProcessor
0x1400776b1  jmp     loc_1400774E6
0x1400776b6  lea     rdx, [rbx+40h]
0x1400776ba  call    PplpLazyInitializeLookasideList
0x1400776bf  jmp     loc_1400774D6
0x1400776c4  mov     ebp, gs:1A4h
0x1400776cc  cmp     cs:UxDebugDisableLookaside, 0
0x1400776d3  jnz     loc_1400775E0
0x1400776d9  cmp     cs:UxCompactMode, 0
0x1400776e0  jz      short loc_140077705
0x1400776e2  mov     rbx, cs:qword_1401A06A0
0x1400776e9  call    cs:__imp_KeGetCurrentNodeNumber
0x1400776f0  nop     dword ptr [rax+rax+00h]
0x1400776f5  movzx   edx, ax
0x1400776f8  mov     rcx, rbx
0x1400776fb  call    PplAllocateFromLookasideListProcessor
0x140077700  jmp     loc_140077603
0x140077705  mov     rcx, cs:qword_1401A06A0
0x14007770c  mov     edx, ebp
0x14007770e  jmp     short loc_1400776FB
0x140077710  mov     edx, 0Eh
0x140077715  mov     [rsp+38h+var_18], rsi
0x14007771a  mov     ecx, 411h
0x14007771f  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x140077726  mov     r9d, edi
0x140077729  call    WPP_SF_dq
0x14007772e  jmp     loc_140077358
0x140077733  cmp     cs:UxSslLargeBufferEnabled, 0
0x14007773a  jz      loc_1401788E6
0x140077740  cmp     edi, 820Ah
0x140077746  ja      loc_1401788E6
0x14007774c  jmp     loc_1400776C4
0x140077751  xor     eax, eax
0x140077753  xorps   xmm0, xmm0
0x140077756  mov     [rbx+4], rax
0x14007775a  mov     [rbx+0Ch], eax
0x14007775d  mov     [rbx+18h], rax
0x140077761  movups  xmmword ptr [rbx+60h], xmm0
0x140077765  movups  xmmword ptr [rbx+70h], xmm0
0x140077769  mov     [rbx], ebp
0x14007776b  xor     ebp, ebp
0x14007776d  mov     r14d, 3
0x140077773  jmp     loc_1400773F2
0x1401788e6  lea     rdx, [rdi+80h]
0x1401788ed  mov     dword ptr [rsp+38h+var_18], 1
0x1401788f5  lea     r9, UxLowPriorityPool
0x1401788fc  mov     ecx, 42h ; 'B'
0x140178901  mov     r8d, 4C537855h
0x140178907  call    cs:__imp_ExAllocatePool3
0x14017890e  nop     dword ptr [rax+rax+00h]
0x140178913  mov     rbx, rax
0x140178916  test    rax, rax
0x140178919  jz      loc_14007760F
0x14017891f  xorps   xmm0, xmm0
0x140178922  xor     ebp, ebp
0x140178924  movaps  xmmword ptr [rax], xmm0
0x140178927  mov     r14d, 4
0x14017892d  xor     eax, eax
0x14017892f  mov     [rbx+18h], rax
0x140178933  movups  xmmword ptr [rbx+60h], xmm0
0x140178937  movups  xmmword ptr [rbx+70h], xmm0
0x14017893b  jmp     loc_1400773F2
```

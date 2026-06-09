# UlpOpenCoupling

- ea: `0x14003ded0`
- end: `0x14003e658`
- name: `UlpOpenCoupling`
- size: `1928`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003cde0`
- `0x140071254`

## callees

- `0x14000a350`
- `0x14003ded0`
- `0x140049d28`
- `0x140051410`
- `0x1400705f0`
- `0x140087a70`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c5c10`
- `0x1401d9f54`
- `0x1401da2b4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003e083`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003e083`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003dfd9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003e400`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003e4b8`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003dfd9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003e400`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003e4b8`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x14003e155`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x14003e609`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x14003e155`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x14003e609`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003e4e2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003e4e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003dfe5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e2c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e334`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e3ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e40c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e4c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003dfe5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e2c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e334`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e3ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e40c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e4c4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14003df30`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14003df30`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14003e328`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14003e328`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003e2b6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003e3de`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003e2b6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003e3de`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003e1ab`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003e351`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003e1ab`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003e351`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003e124`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003e124`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003df18`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003e19a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003e340`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003df18`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003e19a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003e340`

## pseudocode

```c
__int64 __fastcall UlpOpenCoupling(__int64 a1, ULONG_PTR a2, char **a3)
{
  volatile signed __int32 *v3; // r15
  __int64 v6; // r12
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  int Coupling; // esi
  _QWORD *v11; // r8
  _QWORD *v12; // r14
  _QWORD *v13; // rdi
  volatile signed __int32 *v14; // rdx
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  char *v17; // r9
  volatile signed __int32 LockArray_high; // esi
  unsigned __int64 v20; // rdi
  volatile signed __int32 *v21; // rax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rbx
  __int64 v26; // rcx
  _QWORD *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  char *v30; // rdx
  int v31; // eax
  __int64 v32; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v34; // rax
  _QWORD *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  char v38; // [rsp+80h] [rbp+8h] BYREF
  char **v39; // [rsp+90h] [rbp+18h]
  PVOID Entry; // [rsp+98h] [rbp+20h] BYREF

  v39 = a3;
  v3 = 0;
  Entry = 0;
  v38 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a1 )
      v28 = *(_QWORD *)(a1 + 48);
    else
      v28 = 0;
    WPP_SF_qqqi(1032, 27, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, v28, a2, a3);
  }
  KeEnterCriticalRegion();
  v6 = a1 + 944;
  ExAcquirePushLockSharedEx(a1 + 944, 0);
  if ( *(_BYTE *)(a1 + 968) )
    goto LABEL_62;
  Coupling = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qiqqq(v8, v7, v9, a1, *(_QWORD *)(a1 + 48), a2, &v38, &Entry);
  v11 = 0;
  v12 = (_QWORD *)(a1 + 952);
  v13 = *(_QWORD **)(a1 + 952);
  Entry = 0;
  while ( v13 != v12 )
  {
    if ( v13[5] == a2 )
    {
      v14 = (volatile signed __int32 *)v13 - 1;
      do
      {
        v15 = *v14;
        if ( !*v14 )
        {
          v11 = Entry;
          Coupling = -1073741436;
          goto LABEL_14;
        }
        v16 = v15 + 1;
        if ( UxDebugCheckRefcount && v16 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)v14, 0xAu, v16);
      }
      while ( v15 != _InterlockedCompareExchange(v14, v16, v15) );
      if ( v13 != (_QWORD *)*v12 && (v38 || (unsigned __int8)ExTryConvertPushLockSharedToExclusiveEx(a1 + 944, 0)) )
      {
        v38 = 1;
        v34 = *v13;
        if ( *(_QWORD **)(*v13 + 8LL) == v13 )
        {
          v35 = (_QWORD *)v13[1];
          if ( (_QWORD *)*v35 == v13 )
          {
            *v35 = v34;
            *(_QWORD *)(v34 + 8) = v35;
            *v13 = 0;
            v13[1] = 0;
            v36 = *v12;
            if ( *(_QWORD **)(*v12 + 8LL) == v12 )
            {
              *v13 = v36;
              v13[1] = v12;
              *(_QWORD *)(v36 + 8) = v13;
              *v12 = v13;
              goto LABEL_13;
            }
          }
        }
LABEL_37:
        __fastfail(3u);
      }
LABEL_13:
      v11 = v13 - 3;
      Entry = v13 - 3;
      break;
    }
    v13 = (_QWORD *)*v13;
  }
LABEL_14:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_qD(1032, 26, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v11, Coupling);
    v11 = Entry;
  }
  if ( Coupling >= 0 && !v11 )
  {
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    if ( UxDebugDisableLookaside )
    {
      v21 = (volatile signed __int32 *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0930)(
                                         (unsigned int)dword_1401A0918,
                                         qword_1401A0920,
                                         (unsigned int)dword_1401A0928,
                                         0);
    }
    else if ( UxCompactMode )
    {
      v32 = qword_1401A0910;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      v21 = (volatile signed __int32 *)PplAllocateFromLookasideListProcessor(v32, CurrentNodeNumber);
    }
    else
    {
      v20 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
      if ( !*(_BYTE *)(v20 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0910, v20 + 64);
      v21 = (volatile signed __int32 *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v20 + 64));
    }
    v3 = v21;
    if ( v21 )
    {
      memset((void *)v21, 0, 0xA0u);
      *v3 = LockArray_high;
      *((_DWORD *)v3 + 4) = 1430482005;
      *((_DWORD *)v3 + 5) = 1;
      *((_BYTE *)v3 + 81) = 1;
      *((_QWORD *)v3 + 7) = a1;
      *((_QWORD *)v3 + 8) = a2;
      v22 = _InterlockedIncrement((volatile signed __int32 *)a2);
      if ( UxDebugCheckRefcount && v22 <= -1 )
        UlBugCheckEx(3u, a2, 0xEu, v22);
      v23 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
      if ( UxDebugCheckRefcount && v23 <= -1 )
        UlBugCheckEx(3u, a1 + 40, 0xEu, v23);
      Coupling = 0;
      *((_QWORD *)v3 + 9) = 0;
      *((_QWORD *)v3 + 13) = v3 + 24;
      *((_QWORD *)v3 + 12) = v3 + 24;
      *((_QWORD *)v3 + 15) = v3 + 28;
      *((_QWORD *)v3 + 14) = v3 + 28;
      KeInitializeSpinLock((PKSPIN_LOCK)v3 + 16);
      *((_QWORD *)v3 + 18) = v3 + 34;
      *((_QWORD *)v3 + 17) = v3 + 34;
      *((_DWORD *)v3 + 38) = 0;
      *((_DWORD *)v3 + 39) = -1;
      if ( (unsigned __int8)ExTryConvertPushLockSharedToExclusiveEx(a1 + 944, 0) )
      {
LABEL_33:
        v38 = 1;
        v24 = _InterlockedIncrement(v3 + 5);
        if ( UxDebugCheckRefcount && v24 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)(v3 + 5), 0xAu, v24);
        v25 = *(_QWORD *)(*(_QWORD *)(a2 + 264) + 8LL * *(unsigned __int16 *)(a1 + 56));
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v25, 0);
        if ( !*(_BYTE *)(v25 + 24) )
        {
          v26 = *v12;
          if ( *(_QWORD **)(*v12 + 8LL) != v12 )
            goto LABEL_37;
          *((_QWORD *)v3 + 3) = v26;
          *((_QWORD *)v3 + 4) = v12;
          *(_QWORD *)(v26 + 8) = v3 + 6;
          *v12 = v3 + 6;
          v27 = *(_QWORD **)(v25 + 16);
          if ( *v27 != v25 + 8 )
            goto LABEL_37;
          *((_QWORD *)v3 + 5) = v25 + 8;
          *((_QWORD *)v3 + 6) = v27;
          *v27 = v3 + 10;
          *(_QWORD *)(v25 + 16) = v3 + 10;
          ExReleasePushLockExclusiveEx(v25, 0);
          KeLeaveCriticalRegion();
          Entry = (PVOID)v3;
          v3 = 0;
          goto LABEL_18;
        }
        v29 = _InterlockedDecrement(v3 + 5);
        if ( UxDebugCheckRefcount && v29 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)(v3 + 5), 0xAu, v29);
        if ( !v29 )
          UlpFreeCoupling((char *)v3, 0);
        ExReleasePushLockExclusiveEx(v25, 0);
        KeLeaveCriticalRegion();
LABEL_62:
        Coupling = -1073741436;
        ExReleasePushLockEx(v6, 0);
        KeLeaveCriticalRegion();
        goto LABEL_63;
      }
      ExReleasePushLockSharedEx(a1 + 944, 0);
      KeLeaveCriticalRegion();
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(a1 + 944, 0);
      v38 = 1;
      if ( !*(_BYTE *)(a1 + 968) )
      {
        Coupling = UlpFindCoupling(a1, a2, &v38, &Entry);
        if ( Coupling < 0 || Entry )
          goto LABEL_18;
        goto LABEL_33;
      }
      Coupling = -1073741436;
    }
    else
    {
      Coupling = -1073741670;
    }
    ExReleasePushLockEx(a1 + 944, 0);
    KeLeaveCriticalRegion();
    goto LABEL_63;
  }
LABEL_18:
  ExReleasePushLockEx(v6, 0);
  KeLeaveCriticalRegion();
  if ( Coupling >= 0 )
  {
    v17 = (char *)Entry;
    goto LABEL_20;
  }
LABEL_63:
  v17 = (char *)Entry;
  if ( Entry )
  {
    v30 = (char *)Entry + 20;
    v31 = _InterlockedDecrement((volatile signed __int32 *)Entry + 5);
    if ( UxDebugCheckRefcount && v31 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v30, 0xAu, v31);
    if ( !v31 )
      UlpFreeCoupling(v17, 0);
    v17 = 0;
    Entry = 0;
  }
LABEL_20:
  if ( v3 )
  {
    v37 = _InterlockedDecrement(v3 + 5);
    if ( UxDebugCheckRefcount && v37 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v3 + 5), 1u, v37);
    UlpFreeCoupling((char *)v3, 1u);
    v17 = (char *)Entry;
  }
  *v39 = v17;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 28, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v17, Coupling);
  return (unsigned int)Coupling;
}

```

## disassembly

```asm
0x14003ded0  mov     rax, rsp
0x14003ded3  mov     [rax+18h], r8
0x14003ded7  push    rbx
0x14003ded8  push    rbp
0x14003ded9  push    rdi
0x14003deda  push    r12
0x14003dedc  push    r13
0x14003dede  push    r14
0x14003dee0  push    r15
0x14003dee2  sub     rsp, 40h
0x14003dee6  xor     r15d, r15d
0x14003dee9  mov     qword ptr [rax+20h], 0
0x14003def1  mov     [rax+8], r15b
0x14003def5  mov     r13, rdx
0x14003def8  mov     rbx, rcx
0x14003defb  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003df02  jnz     loc_14003E1F5
0x14003df08  mov     edi, 30h ; '0'
0x14003df0d  mov     [rsp+78h+arg_8], rsi
0x14003df15  mov     rbp, rbx
0x14003df18  call    cs:__imp_KeEnterCriticalRegion
0x14003df1f  nop     dword ptr [rax+rax+00h]
0x14003df24  lea     r12, [rbx+3B0h]
0x14003df2b  xor     edx, edx
0x14003df2d  mov     rcx, r12
0x14003df30  call    cs:__imp_ExAcquirePushLockSharedEx
0x14003df37  nop     dword ptr [rax+rax+00h]
0x14003df3c  mov     r14d, 0FFFFFFFFh
0x14003df42  cmp     [rbx+3C8h], r15b
0x14003df49  jnz     loc_14003E3F6
0x14003df4f  xor     esi, esi
0x14003df51  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003df58  jnz     loc_14003E5C1
0x14003df5e  xor     r8d, r8d
0x14003df61  lea     r14, [rbx+3B8h]
0x14003df68  mov     rdi, [r14]
0x14003df6b  mov     [rsp+78h+Entry], r8
0x14003df73  cmp     rdi, r14
0x14003df76  jz      short loc_14003DFBE
0x14003df78  cmp     [rdi+28h], r13
0x14003df7c  lea     rbp, [rdi-18h]
0x14003df80  jnz     loc_14003E3AB
0x14003df86  lea     rdx, [rbp+14h]; BugCheckParameter2
0x14003df8a  mov     eax, [rdx]
0x14003df8c  test    eax, eax
0x14003df8e  jz      loc_14003E22B
0x14003df94  cmp     cs:UxDebugCheckRefcount, sil
0x14003df9b  lea     ecx, [rax+1]
0x14003df9e  jnz     loc_14003E306
0x14003dfa4  lock cmpxchg [rdx], ecx
0x14003dfa8  jnz     short loc_14003DF8A
0x14003dfaa  cmp     rdi, [r14]
0x14003dfad  jnz     loc_14003E5F6
0x14003dfb3  mov     r8, rbp
0x14003dfb6  mov     [rsp+78h+Entry], rbp
0x14003dfbe  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003dfc5  jnz     loc_14003E622
0x14003dfcb  test    esi, esi
0x14003dfcd  js      short loc_14003DFD4
0x14003dfcf  test    r8, r8
0x14003dfd2  jz      short loc_14003E03D
0x14003dfd4  xor     edx, edx
0x14003dfd6  mov     rcx, r12
0x14003dfd9  call    cs:__imp_ExReleasePushLockEx
0x14003dfe0  nop     dword ptr [rax+rax+00h]
0x14003dfe5  call    cs:__imp_KeLeaveCriticalRegion
0x14003dfec  nop     dword ptr [rax+rax+00h]
0x14003dff1  test    esi, esi
0x14003dff3  js      loc_14003E4D0
0x14003dff9  mov     r9, [rsp+78h+Entry]
0x14003e001  test    r15, r15
0x14003e004  jnz     loc_14003E579
0x14003e00a  mov     rax, [rsp+78h+arg_10]
0x14003e012  mov     [rax], r9
0x14003e015  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003e01c  jnz     loc_14003E470
0x14003e022  mov     eax, esi
0x14003e024  mov     rsi, [rsp+78h+arg_8]
0x14003e02c  add     rsp, 40h
0x14003e030  pop     r15
0x14003e032  pop     r14
0x14003e034  pop     r13
0x14003e036  pop     r12
0x14003e038  pop     rdi
0x14003e039  pop     rbp
0x14003e03a  pop     rbx
0x14003e03b  retn
0x14003e03d  mov     esi, gs:1A4h
0x14003e045  cmp     cs:UxDebugDisableLookaside, r15b
0x14003e04c  jnz     loc_14003E2DE
0x14003e052  cmp     cs:UxCompactMode, r15b
0x14003e059  jnz     loc_14003E4DB
0x14003e05f  mov     rcx, cs:qword_1401A0910
0x14003e066  lea     edi, [rsi+1]
0x14003e069  shl     rdi, 7
0x14003e06d  add     rdi, rcx
0x14003e070  movzx   eax, byte ptr [rdi+0B0h]
0x14003e077  test    al, al
0x14003e079  jz      loc_14003E4FE
0x14003e07f  lea     rcx, [rdi+40h]; Lookaside
0x14003e083  call    cs:__imp_ExAllocateFromLookasideListEx
0x14003e08a  nop     dword ptr [rax+rax+00h]
0x14003e08f  xor     edx, edx; Val
0x14003e091  mov     r15, rax
0x14003e094  test    rax, rax
0x14003e097  jz      loc_14003E4B0
0x14003e09d  mov     r8d, 0A0h; Size
0x14003e0a3  mov     rcx, rax; void *
0x14003e0a6  call    memset
0x14003e0ab  mov     [r15], esi
0x14003e0ae  mov     eax, 1
0x14003e0b3  mov     dword ptr [r15+10h], 55436C55h
0x14003e0bb  mov     dword ptr [r15+14h], 1
0x14003e0c3  mov     byte ptr [r15+51h], 1
0x14003e0c8  mov     [r15+38h], rbx
0x14003e0cc  mov     [r15+40h], r13
0x14003e0d0  lock xadd [r13+0], eax
0x14003e0d6  inc     eax
0x14003e0d8  cmp     cs:UxDebugCheckRefcount, 0
0x14003e0df  jnz     loc_14003E241
0x14003e0e5  lea     rdx, [rbx+28h]; BugCheckParameter2
0x14003e0e9  mov     eax, 1
0x14003e0ee  lock xadd [rdx], eax
0x14003e0f2  inc     eax
0x14003e0f4  cmp     cs:UxDebugCheckRefcount, 0
0x14003e0fb  jnz     loc_14003E261
0x14003e101  lea     rax, [r15+60h]
0x14003e105  xor     esi, esi
0x14003e107  mov     [r15+48h], rsi
0x14003e10b  lea     rcx, [r15+80h]; SpinLock
0x14003e112  mov     [rax+8], rax
0x14003e116  mov     [rax], rax
0x14003e119  lea     rax, [r15+70h]
0x14003e11d  mov     [rax+8], rax
0x14003e121  mov     [rax], rax
0x14003e124  call    cs:__imp_KeInitializeSpinLock
0x14003e12b  nop     dword ptr [rax+rax+00h]
0x14003e130  lea     rax, [r15+88h]
0x14003e137  xor     edx, edx
0x14003e139  mov     [rax+8], rax
0x14003e13d  mov     rcx, r12
0x14003e140  mov     [rax], rax
0x14003e143  mov     [r15+98h], esi
0x14003e14a  mov     dword ptr [r15+9Ch], 0FFFFFFFFh
0x14003e155  call    cs:__imp_ExTryConvertPushLockSharedToExclusiveEx
0x14003e15c  nop     dword ptr [rax+rax+00h]
0x14003e161  test    al, al
0x14003e163  jz      loc_14003E323
0x14003e169  mov     [rsp+78h+arg_0], 1
0x14003e171  mov     eax, 1
0x14003e176  lock xadd [r15+14h], eax
0x14003e17c  inc     eax
0x14003e17e  cmp     cs:UxDebugCheckRefcount, 0
0x14003e185  jnz     loc_14003E27E
0x14003e18b  movzx   ecx, word ptr [rbx+38h]
0x14003e18f  mov     rax, [r13+108h]
0x14003e196  mov     rbx, [rax+rcx*8]
0x14003e19a  call    cs:__imp_KeEnterCriticalRegion
0x14003e1a1  nop     dword ptr [rax+rax+00h]
0x14003e1a6  xor     edx, edx
0x14003e1a8  mov     rcx, rbx
0x14003e1ab  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003e1b2  nop     dword ptr [rax+rax+00h]
0x14003e1b7  cmp     byte ptr [rbx+18h], 0
0x14003e1bb  jnz     loc_14003E3B3
0x14003e1c1  mov     rcx, [r14]
0x14003e1c4  cmp     [rcx+8], r14
0x14003e1c8  jnz     short loc_14003E1EE
0x14003e1ca  mov     [r15+18h], rcx
0x14003e1ce  lea     rax, [r15+18h]
0x14003e1d2  mov     [rax+8], r14
0x14003e1d6  mov     [rcx+8], rax
0x14003e1da  lea     rcx, [rbx+8]
0x14003e1de  mov     [r14], rax
0x14003e1e1  mov     rdx, [rcx+8]
0x14003e1e5  cmp     [rdx], rcx
0x14003e1e8  jz      loc_14003E29F
0x14003e1ee  mov     ecx, 3
0x14003e1f3  int     29h; Win8: RtlFailFast(ecx)
0x14003e1f5  test    rbx, rbx
0x14003e1f8  jz      short loc_14003E23D
0x14003e1fa  mov     rax, [rcx+30h]
0x14003e1fe  mov     [rsp+78h+var_48], r8
0x14003e203  mov     edx, 1Bh
0x14003e208  mov     [rsp+78h+var_50], r13
0x14003e20d  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x14003e214  mov     ecx, 408h
0x14003e219  mov     [rsp+78h+var_58], rax
0x14003e21e  mov     r9, rbx
0x14003e221  call    WPP_SF_qqqi
0x14003e226  jmp     loc_14003DF08
0x14003e22b  mov     r8, [rsp+78h+Entry]
0x14003e233  mov     esi, 0C0000184h
0x14003e238  jmp     loc_14003DFBE
0x14003e23d  xor     eax, eax
0x14003e23f  jmp     short loc_14003E1FE
0x14003e241  cmp     eax, 0FFFFFFFFh
0x14003e244  jg      loc_14003E0E5
0x14003e24a  movsxd  r9, eax; BugCheckParameter4
0x14003e24d  mov     r8d, 0Eh; BugCheckParameter3
0x14003e253  mov     rdx, r13; BugCheckParameter2
0x14003e256  mov     ecx, 3; BugCheckParameter1
0x14003e25b  call    UlBugCheckEx
0x14003e261  cmp     eax, 0FFFFFFFFh
0x14003e264  jg      loc_14003E101
0x14003e26a  movsxd  r9, eax; BugCheckParameter4
0x14003e26d  mov     ecx, 3; BugCheckParameter1
0x14003e272  mov     r8d, 0Eh; BugCheckParameter3
0x14003e278  call    UlBugCheckEx
0x14003e27e  cmp     eax, 0FFFFFFFFh
0x14003e281  jg      loc_14003E18B
0x14003e287  movsxd  r9, eax; BugCheckParameter4
0x14003e28a  lea     rdx, [r15+14h]; BugCheckParameter2
0x14003e28e  mov     r8d, 0Ah; BugCheckParameter3
0x14003e294  mov     ecx, 3; BugCheckParameter1
0x14003e299  call    UlBugCheckEx
0x14003e29f  lea     rax, [r15+28h]
0x14003e2a3  mov     [rax], rcx
0x14003e2a6  mov     [rax+8], rdx
0x14003e2aa  mov     [rdx], rax
0x14003e2ad  xor     edx, edx
0x14003e2af  mov     [rcx+8], rax
0x14003e2b3  mov     rcx, rbx
0x14003e2b6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003e2bd  nop     dword ptr [rax+rax+00h]
0x14003e2c2  call    cs:__imp_KeLeaveCriticalRegion
0x14003e2c9  nop     dword ptr [rax+rax+00h]
0x14003e2ce  mov     [rsp+78h+Entry], r15
0x14003e2d6  xor     r15d, r15d
0x14003e2d9  jmp     loc_14003DFD4
0x14003e2de  mov     rax, cs:off_1401A0930
0x14003e2e5  xor     r9d, r9d
0x14003e2e8  mov     r8d, cs:dword_1401A0928
0x14003e2ef  mov     rdx, cs:qword_1401A0920
0x14003e2f6  mov     ecx, cs:dword_1401A0918
0x14003e2fc  call    _guard_dispatch_icall
0x14003e301  jmp     loc_14003E08F
0x14003e306  cmp     ecx, 0FFFFFFFFh
0x14003e309  jg      loc_14003DFA4
0x14003e30f  movsxd  r9, ecx; BugCheckParameter4
0x14003e312  mov     r8d, 0Ah; BugCheckParameter3
0x14003e318  mov     ecx, 3; BugCheckParameter1
0x14003e31d  call    UlBugCheckEx
0x14003e323  xor     edx, edx
0x14003e325  mov     rcx, r12
0x14003e328  call    cs:__imp_ExReleasePushLockSharedEx
0x14003e32f  nop     dword ptr [rax+rax+00h]
0x14003e334  call    cs:__imp_KeLeaveCriticalRegion
0x14003e33b  nop     dword ptr [rax+rax+00h]
0x14003e340  call    cs:__imp_KeEnterCriticalRegion
0x14003e347  nop     dword ptr [rax+rax+00h]
0x14003e34c  xor     edx, edx
0x14003e34e  mov     rcx, r12
0x14003e351  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003e358  nop     dword ptr [rax+rax+00h]
0x14003e35d  mov     [rsp+78h+arg_0], 1
0x14003e365  cmp     [rbx+3C8h], sil
0x14003e36c  jnz     loc_14003E64C
0x14003e372  lea     r9, [rsp+78h+Entry]
0x14003e37a  mov     rdx, r13
0x14003e37d  lea     r8, [rsp+78h+arg_0]
0x14003e385  mov     rcx, rbx
0x14003e388  call    UlpFindCoupling
0x14003e38d  mov     esi, eax
0x14003e38f  test    eax, eax
0x14003e391  js      loc_14003DFD4
0x14003e397  cmp     [rsp+78h+Entry], 0
0x14003e3a0  jz      loc_14003E169
0x14003e3a6  jmp     loc_14003DFD4
0x14003e3ab  mov     rdi, [rdi]
0x14003e3ae  jmp     loc_14003DF73
0x14003e3b3  mov     r14d, 0FFFFFFFFh
0x14003e3b9  mov     eax, r14d
0x14003e3bc  lock xadd [r15+14h], eax
0x14003e3c2  dec     eax
0x14003e3c4  cmp     cs:UxDebugCheckRefcount, 0
0x14003e3cb  jnz     loc_14003E48F
0x14003e3d1  test    eax, eax
0x14003e3d3  jz      loc_14003E461
0x14003e3d9  xor     edx, edx
0x14003e3db  mov     rcx, rbx
0x14003e3de  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003e3e5  nop     dword ptr [rax+rax+00h]
0x14003e3ea  call    cs:__imp_KeLeaveCriticalRegion
0x14003e3f1  nop     dword ptr [rax+rax+00h]
0x14003e3f6  xor     edx, edx
0x14003e3f8  mov     rcx, r12
0x14003e3fb  mov     esi, 0C0000184h
0x14003e400  call    cs:__imp_ExReleasePushLockEx
0x14003e407  nop     dword ptr [rax+rax+00h]
0x14003e40c  call    cs:__imp_KeLeaveCriticalRegion
0x14003e413  nop     dword ptr [rax+rax+00h]
0x14003e418  mov     r9, [rsp+78h+Entry]
0x14003e420  test    r9, r9
0x14003e423  jz      loc_14003E001
0x14003e429  lea     rdx, [r9+14h]; BugCheckParameter2
0x14003e42d  mov     eax, r14d
0x14003e430  lock xadd [rdx], eax
0x14003e434  dec     eax
0x14003e436  cmp     cs:UxDebugCheckRefcount, 0
  ... truncated ...
```

# UxpSslCopyTransportIndicationsToHandshakeBuffer

- ea: `0x140076780`
- end: `0x140077324`
- name: `UxpSslCopyTransportIndicationsToHandshakeBuffer`
- size: `2980`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14013c8d8`

## callees

- `0x14000a350`
- `0x140049d28`
- `0x14005dff0`
- `0x14006e50c`
- `0x140076780`
- `0x140077330`
- `0x140167700`
- `0x1401677e0`
- `0x140167840`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140076919`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140076919`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140076a96`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140076a96`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007705e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077138`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077215`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400772d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007705e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077138`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077215`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400772d4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007682e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007682e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140076814`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140076814`

## pseudocode

```c
__int64 __fastcall UxpSslCopyTransportIndicationsToHandshakeBuffer(__int64 a1, _QWORD **a2)
{
  __int64 v3; // r13
  int v4; // r15d
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  unsigned int *v7; // r14
  KIRQL v8; // al
  unsigned int v9; // edi
  unsigned int *v10; // r13
  unsigned int v11; // r12d
  __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  unsigned int v17; // ecx
  unsigned int *v18; // rbx
  _QWORD *v19; // rax
  __int64 v21; // rbx
  USHORT CurrentNodeNumber; // ax
  _QWORD *v23; // rcx
  unsigned int *v24; // rbx
  volatile signed __int32 *v25; // rdx
  int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  _DWORD *v32; // rbx
  unsigned int v33; // edi
  int v34; // eax
  unsigned int v35; // eax
  char *v36; // rdx
  int v37; // eax
  unsigned int v38; // eax
  PVOID v39; // rax
  PVOID P; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v41; // [rsp+38h] [rbp-61h]
  __int64 v42; // [rsp+40h] [rbp-59h]
  _DWORD v43[24]; // [rsp+50h] [rbp-49h] BYREF

  v42 = a1;
  v3 = a1;
  v4 = 0;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qq(1041, 61, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, a2);
  while ( 1 )
  {
    v5 = *a2;
    if ( *a2 == a2 )
      break;
    if ( (_QWORD **)v5[1] != a2 || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
LABEL_32:
      __fastfail(3u);
    *a2 = v6;
    v7 = (unsigned int *)(v5 - 8);
    v6[1] = a2;
    v5[1] = v5;
    *v5 = v5;
    v8 = KeAcquireSpinLockRaiseToDpc(v5 - 5);
    v41 = v7[26];
    v9 = v41;
    KeReleaseSpinLock((PKSPIN_LOCK)v7 + 3, v8);
    v10 = *(unsigned int **)(v3 + 1536);
    v11 = v9 - v7[28];
    if ( v10[27] >= v11 )
      goto LABEL_7;
    P = 0;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qD(1041, 47, WPP_6033a49e77e7395416619077875677ff_Traceguids, v10, v11);
    if ( v10 )
    {
      v17 = v11 + v10[26];
    }
    else
    {
      v17 = v11;
      if ( v11 < 0x4105 )
        v17 = 16645;
    }
    v4 = UxSslAllocateTransportDataIndication(v17, &P);
    if ( v4 < 0 )
    {
      v18 = (unsigned int *)P;
      if ( !P )
        goto LABEL_24;
      v36 = (char *)P + 20;
      v37 = _InterlockedDecrement((volatile signed __int32 *)P + 5);
      if ( UxDebugCheckRefcount && v37 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v36, 1u, v37);
      if ( v37 )
        goto LABEL_78;
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_q(1041, 10, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids, v18);
      v38 = v18[30];
      v18[4] = 1819498613;
      if ( v38 )
      {
        switch ( v38 )
        {
          case 1u:
            memset(v43, 0, sizeof(v43));
            if ( UxDebugDisableLookaside )
            {
              v43[10] = dword_1401A0658;
              ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0668)(v18, v43);
              goto LABEL_84;
            }
            v31 = qword_1401A0640;
            break;
          case 2u:
            memset(v43, 0, sizeof(v43));
            if ( UxDebugDisableLookaside )
            {
              v43[10] = dword_1401A0688;
              ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0698)(v18, v43);
              goto LABEL_84;
            }
            v31 = qword_1401A0670;
            break;
          case 3u:
            memset(v43, 0, sizeof(v43));
            if ( UxDebugDisableLookaside )
            {
              v43[10] = dword_1401A06B8;
              ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A06C8)(v18, v43);
              goto LABEL_84;
            }
            v31 = qword_1401A06A0;
            break;
          default:
            ExFreePoolWithTag(v18, 0);
            goto LABEL_84;
        }
      }
      else
      {
        memset(v43, 0, sizeof(v43));
        if ( UxDebugDisableLookaside )
        {
          v43[10] = dword_1401A0628;
          ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0638)(v18, v43);
          goto LABEL_84;
        }
        v31 = qword_1401A0610;
      }
      if ( UxCompactMode )
        PnlFreeToLookasideList(v31, v18);
      else
        PplFreeToLookasideListProcessor(v31, v18, *v18);
LABEL_84:
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 11, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids);
      goto LABEL_78;
    }
    if ( v10 )
    {
      v32 = P;
      v33 = v10[26];
      memmove((void *)(*((_QWORD *)P + 12) + *((unsigned int *)P + 26)), *((const void **)v10 + 12), v33);
      v32[26] += v33;
      v32[27] -= v33;
      *((_DWORD *)P + 28) = v10[28];
      v34 = _InterlockedDecrement((volatile signed __int32 *)v10 + 5);
      if ( UxDebugCheckRefcount && v34 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v10 + 5), 1u, v34);
      if ( v34 )
        goto LABEL_77;
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_q(1041, 10, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids, v10);
      v35 = v10[30];
      v10[4] = 1819498613;
      if ( v35 )
      {
        switch ( v35 )
        {
          case 1u:
            memset(v43, 0, sizeof(v43));
            if ( UxDebugDisableLookaside )
            {
              v43[10] = dword_1401A0658;
              ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0668)(v10, v43);
              goto LABEL_75;
            }
            v30 = qword_1401A0640;
            break;
          case 2u:
            memset(v43, 0, sizeof(v43));
            if ( UxDebugDisableLookaside )
            {
              v43[10] = dword_1401A0688;
              ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0698)(v10, v43);
              goto LABEL_75;
            }
            v30 = qword_1401A0670;
            break;
          case 3u:
            memset(v43, 0, sizeof(v43));
            if ( UxDebugDisableLookaside )
            {
              v43[10] = dword_1401A06B8;
              ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A06C8)(v10, v43);
              goto LABEL_75;
            }
            v30 = qword_1401A06A0;
            break;
          default:
            ExFreePoolWithTag(v10, 0);
            goto LABEL_75;
        }
      }
      else
      {
        memset(v43, 0, sizeof(v43));
        if ( UxDebugDisableLookaside )
        {
          v43[10] = dword_1401A0628;
          ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0638)(v10, v43);
          goto LABEL_75;
        }
        v30 = qword_1401A0610;
      }
      if ( UxCompactMode )
        PnlFreeToLookasideList(v30, v10);
      else
        PplFreeToLookasideListProcessor(v30, v10, *v10);
LABEL_75:
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 11, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids);
LABEL_77:
      v9 = v41;
      *(_QWORD *)(v42 + 1536) = P;
LABEL_78:
      P = 0;
      goto LABEL_24;
    }
    v39 = P;
    P = 0;
    *(_QWORD *)(v42 + 1536) = v39;
LABEL_24:
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1041, 48, WPP_6033a49e77e7395416619077875677ff_Traceguids, (unsigned int)v4);
    if ( v4 < 0 )
      break;
LABEL_7:
    v3 = v42;
    v12 = *(_QWORD *)(v42 + 1536);
    memmove(
      (void *)(*(_QWORD *)(v12 + 96) + *(unsigned int *)(v12 + 104)),
      (const void *)(*((_QWORD *)v7 + 12) + v7[28]),
      v11);
    *(_DWORD *)(v12 + 104) += v11;
    *(_DWORD *)(v12 + 108) -= v11;
    v7[28] = v9;
    v13 = _InterlockedDecrement((volatile signed __int32 *)v7 + 5);
    if ( UxDebugCheckRefcount && v13 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v7 + 5), 0x1Du, v13);
    if ( !v13 )
    {
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_q(1041, 10, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids, v7);
      v14 = v7[30];
      v7[4] = 1819498613;
      switch ( v14 )
      {
        case 0u:
          memset(v43, 0, sizeof(v43));
          if ( UxDebugDisableLookaside )
          {
            v43[10] = dword_1401A0628;
            ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0638)(v7, v43);
            goto LABEL_16;
          }
          if ( UxCompactMode )
          {
            v21 = qword_1401A0610;
            CurrentNodeNumber = KeGetCurrentNodeNumber();
            PplFreeToLookasideListProcessor(v21, v7, CurrentNodeNumber);
            goto LABEL_16;
          }
          v15 = qword_1401A0610;
          v16 = qword_1401A0610 + ((unsigned __int64)(*v7 + 1) << 7);
          if ( *(_BYTE *)(v16 + 176) )
            goto LABEL_15;
LABEL_38:
          PplpLazyInitializeLookasideList(v15, v16 + 64);
LABEL_15:
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v16 + 64), v7);
          goto LABEL_16;
        case 1u:
          memset(v43, 0, sizeof(v43));
          if ( UxDebugDisableLookaside )
          {
            v43[10] = dword_1401A0658;
            ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0668)(v7, v43);
            goto LABEL_16;
          }
          v29 = qword_1401A0640;
          break;
        case 2u:
          memset(v43, 0, sizeof(v43));
          if ( UxDebugDisableLookaside )
          {
            v43[10] = dword_1401A0688;
            ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0698)(v7, v43);
            goto LABEL_16;
          }
          v15 = qword_1401A0670;
          if ( UxCompactMode )
          {
            PnlFreeToLookasideList(qword_1401A0670, v7);
            goto LABEL_16;
          }
          v16 = qword_1401A0670 + ((unsigned __int64)(*v7 + 1) << 7);
          if ( *(_BYTE *)(v16 + 176) )
            goto LABEL_15;
          goto LABEL_38;
        case 3u:
          memset(v43, 0, sizeof(v43));
          if ( UxDebugDisableLookaside )
          {
            v43[10] = dword_1401A06B8;
            ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A06C8)(v7, v43);
            goto LABEL_16;
          }
          v29 = qword_1401A06A0;
          break;
        default:
          ExFreePoolWithTag(v7, 0);
          goto LABEL_16;
      }
      if ( UxCompactMode )
        PnlFreeToLookasideList(v29, v7);
      else
        PplFreeToLookasideListProcessor(v29, v7, *v7);
LABEL_16:
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 11, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids);
    }
  }
  while ( 1 )
  {
    v19 = *a2;
    if ( *a2 == a2 )
      break;
    if ( (_QWORD **)v19[1] != a2 )
      goto LABEL_32;
    v23 = (_QWORD *)*v19;
    if ( *(_QWORD **)(*v19 + 8LL) != v19 )
      goto LABEL_32;
    *a2 = v23;
    v24 = (unsigned int *)(v19 - 8);
    v23[1] = a2;
    v25 = (volatile signed __int32 *)v19 - 11;
    v19[1] = v19;
    *v19 = v19;
    v26 = _InterlockedDecrement(v25);
    if ( UxDebugCheckRefcount && v26 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v25, 0x1Du, v26);
    if ( !v26 )
    {
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_q(1041, 10, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids, v24);
      v27 = v24[30];
      v24[4] = 1819498613;
      if ( v27 )
      {
        switch ( v27 )
        {
          case 1u:
            memset(v43, 0, sizeof(v43));
            if ( !UxDebugDisableLookaside )
            {
              v28 = qword_1401A0640;
              goto LABEL_52;
            }
            v43[10] = dword_1401A0658;
            ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0668)(v24, v43);
            break;
          case 2u:
            memset(v43, 0, sizeof(v43));
            if ( !UxDebugDisableLookaside )
            {
              v28 = qword_1401A0670;
              goto LABEL_52;
            }
            v43[10] = dword_1401A0688;
            ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0698)(v24, v43);
            break;
          case 3u:
            memset(v43, 0, sizeof(v43));
            if ( !UxDebugDisableLookaside )
            {
              v28 = qword_1401A06A0;
LABEL_52:
              if ( UxCompactMode )
                PnlFreeToLookasideList(v28, v24);
              else
                PplFreeToLookasideListProcessor(v28, v24, *v24);
              break;
            }
            v43[10] = dword_1401A06B8;
            ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A06C8)(v24, v43);
            break;
          default:
            ExFreePoolWithTag(v24, 0);
            break;
        }
      }
      else
      {
        memset(v43, 0, sizeof(v43));
        if ( !UxDebugDisableLookaside )
        {
          v28 = qword_1401A0610;
          goto LABEL_52;
        }
        v43[10] = dword_1401A0628;
        ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0638)(v24, v43);
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 11, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids);
    }
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 62, WPP_6033a49e77e7395416619077875677ff_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140076780  push    rbp
0x140076782  push    rsi
0x140076783  push    r13
0x140076785  push    r15
0x140076787  lea     rbp, [rsp-3Fh]
0x14007678c  sub     rsp, 0D8h
0x140076793  mov     rax, cs:__security_cookie
0x14007679a  xor     rax, rsp
0x14007679d  mov     [rbp+57h+var_40], rax
0x1400767a1  mov     rsi, rdx
0x1400767a4  mov     [rbp+57h+var_B0], rcx
0x1400767a8  mov     r13, rcx
0x1400767ab  xor     r15d, r15d
0x1400767ae  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400767b5  jnz     loc_140076F57
0x1400767bb  mov     [rsp+0F0h+arg_10], rbx
0x1400767c3  mov     [rsp+0F0h+var_20], rdi
0x1400767cb  mov     [rsp+0F0h+var_28], r12
0x1400767d3  mov     [rsp+0F0h+var_30], r14
0x1400767db  mov     rax, [rsi]
0x1400767de  cmp     rax, rsi
0x1400767e1  jz      loc_1400769A7
0x1400767e7  cmp     [rax+8], rsi
0x1400767eb  jnz     loc_140076A04
0x1400767f1  mov     rcx, [rax]
0x1400767f4  cmp     [rcx+8], rax
0x1400767f8  jnz     loc_140076A04
0x1400767fe  mov     [rsi], rcx
0x140076801  lea     r14, [rax-40h]
0x140076805  mov     [rcx+8], rsi
0x140076809  lea     rcx, [r14+18h]; SpinLock
0x14007680d  mov     [rax+8], rax
0x140076811  mov     [rax], rax
0x140076814  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14007681b  nop     dword ptr [rax+rax+00h]
0x140076820  mov     edi, [r14+68h]
0x140076824  lea     rcx, [r14+18h]; SpinLock
0x140076828  movzx   edx, al; NewIrql
0x14007682b  mov     [rbp+57h+var_B8], edi
0x14007682e  call    cs:__imp_KeReleaseSpinLock
0x140076835  nop     dword ptr [rax+rax+00h]
0x14007683a  mov     r13, [r13+600h]
0x140076841  mov     r12d, edi
0x140076844  sub     r12d, [r14+70h]
0x140076848  cmp     [r13+6Ch], r12d
0x14007684c  jb      loc_14007694D
0x140076852  mov     edx, [r14+70h]
0x140076856  mov     r13, [rbp+57h+var_B0]
0x14007685a  add     rdx, [r14+60h]; Src
0x14007685e  mov     r8d, r12d; Size
0x140076861  mov     rbx, [r13+600h]
0x140076868  mov     ecx, [rbx+68h]
0x14007686b  add     rcx, [rbx+60h]; void *
0x14007686f  call    memmove
0x140076874  add     [rbx+68h], r12d
0x140076878  lea     rdx, [r14+14h]; BugCheckParameter2
0x14007687c  sub     [rbx+6Ch], r12d
0x140076880  mov     eax, 0FFFFFFFFh
0x140076885  mov     [r14+70h], edi
0x140076889  lock xadd [rdx], eax
0x14007688d  dec     eax
0x14007688f  cmp     cs:UxDebugCheckRefcount, 0
0x140076896  jnz     loc_140076A72
0x14007689c  test    eax, eax
0x14007689e  jnz     loc_1400767DB
0x1400768a4  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400768ab  jnz     loc_140077188
0x1400768b1  mov     eax, [r14+78h]
0x1400768b5  xor     edx, edx; Val
0x1400768b7  mov     dword ptr [r14+10h], 6C735875h
0x1400768bf  test    eax, eax
0x1400768c1  jnz     loc_140076A0B
0x1400768c7  mov     r8d, 60h ; '`'; Size
0x1400768cd  lea     rcx, [rbp+57h+var_A0]; void *
0x1400768d1  call    memset
0x1400768d6  cmp     cs:UxDebugDisableLookaside, 0
0x1400768dd  jnz     loc_1400771A6
0x1400768e3  cmp     cs:UxCompactMode, 0
0x1400768ea  jnz     loc_140076A8F
0x1400768f0  mov     ebx, [r14]
0x1400768f3  mov     rcx, cs:qword_1401A0610
0x1400768fa  inc     ebx
0x1400768fc  shl     rbx, 7
0x140076900  add     rbx, rcx
0x140076903  movzx   eax, byte ptr [rbx+0B0h]
0x14007690a  test    al, al
0x14007690c  jz      loc_140076A64
0x140076912  mov     rdx, r14; Entry
0x140076915  lea     rcx, [rbx+40h]; Lookaside
0x140076919  call    cs:__imp_ExFreeToLookasideListEx
0x140076920  nop     dword ptr [rax+rax+00h]
0x140076925  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007692c  jz      loc_1400767DB
0x140076932  mov     edx, 0Bh
0x140076937  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x14007693e  mov     ecx, 411h
0x140076943  call    WPP_SF_
0x140076948  jmp     loc_1400767DB
0x14007694d  xor     ebx, ebx
0x14007694f  mov     [rbp+57h+P], rbx
0x140076953  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007695a  jnz     loc_140076F7A
0x140076960  test    r13, r13
0x140076963  jz      loc_140076F9D
0x140076969  mov     ecx, [r13+68h]
0x14007696d  add     ecx, r12d
0x140076970  lea     rdx, [rbp+57h+P]
0x140076974  call    UxSslAllocateTransportDataIndication
0x140076979  mov     r15d, eax
0x14007697c  test    eax, eax
0x14007697e  jns     loc_140076FB0
0x140076984  mov     rbx, [rbp+57h+P]
0x140076988  test    rbx, rbx
0x14007698b  jnz     loc_140076E27
0x140076991  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140076998  jnz     loc_14007716A
0x14007699e  test    r15d, r15d
0x1400769a1  jns     loc_140076852
0x1400769a7  mov     rax, [rsi]
0x1400769aa  cmp     rax, rsi
0x1400769ad  jnz     short loc_1400769FA
0x1400769af  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400769b6  jnz     loc_140077306
0x1400769bc  mov     r14, [rsp+0F0h+var_30]
0x1400769c4  mov     eax, r15d
0x1400769c7  mov     r12, [rsp+0F0h+var_28]
0x1400769cf  mov     rdi, [rsp+0F0h+var_20]
0x1400769d7  mov     rbx, [rsp+0F0h+arg_10]
0x1400769df  mov     rcx, [rbp+57h+var_40]
0x1400769e3  xor     rcx, rsp; StackCookie
0x1400769e6  call    __security_check_cookie
0x1400769eb  add     rsp, 0D8h
0x1400769f2  pop     r15
0x1400769f4  pop     r13
0x1400769f6  pop     rsi
0x1400769f7  pop     rbp
0x1400769f8  retn
0x1400769fa  cmp     [rax+8], rsi
0x1400769fe  jz      loc_140076AC3
0x140076a04  mov     ecx, 3
0x140076a09  int     29h; Win8: RtlFailFast(ecx)
0x140076a0b  cmp     eax, 1
0x140076a0e  jz      loc_140076B96
0x140076a14  cmp     eax, 2
0x140076a17  jnz     loc_140077209
0x140076a1d  mov     r8d, 60h ; '`'; Size
0x140076a23  lea     rcx, [rbp+57h+var_A0]; void *
0x140076a27  call    memset
0x140076a2c  cmp     cs:UxDebugDisableLookaside, 0
0x140076a33  jnz     loc_1400771E8
0x140076a39  cmp     cs:UxCompactMode, 0
0x140076a40  mov     rcx, cs:qword_1401A0670
0x140076a47  jnz     short loc_140076AB6
0x140076a49  mov     ebx, [r14]
0x140076a4c  inc     ebx
0x140076a4e  shl     rbx, 7
0x140076a52  add     rbx, rcx
0x140076a55  movzx   eax, byte ptr [rbx+0B0h]
0x140076a5c  test    al, al
0x140076a5e  jnz     loc_140076912
0x140076a64  lea     rdx, [rbx+40h]
0x140076a68  call    PplpLazyInitializeLookasideList
0x140076a6d  jmp     loc_140076912
0x140076a72  cmp     eax, 0FFFFFFFFh
0x140076a75  jg      loc_14007689C
0x140076a7b  movsxd  r9, eax; BugCheckParameter4
0x140076a7e  mov     ecx, 3; BugCheckParameter1
0x140076a83  mov     r8d, 1Dh; BugCheckParameter3
0x140076a89  call    UlBugCheckEx
0x140076a8f  mov     rbx, cs:qword_1401A0610
0x140076a96  call    cs:__imp_KeGetCurrentNodeNumber
0x140076a9d  nop     dword ptr [rax+rax+00h]
0x140076aa2  movzx   r8d, ax
0x140076aa6  mov     rdx, r14
0x140076aa9  mov     rcx, rbx
0x140076aac  call    PplFreeToLookasideListProcessor
0x140076ab1  jmp     loc_140076925
0x140076ab6  mov     rdx, r14
0x140076ab9  call    PnlFreeToLookasideList
0x140076abe  jmp     loc_140076925
0x140076ac3  mov     rcx, [rax]
0x140076ac6  cmp     [rcx+8], rax
0x140076aca  jnz     loc_140076A04
0x140076ad0  mov     [rsi], rcx
0x140076ad3  lea     rbx, [rax-40h]
0x140076ad7  mov     [rcx+8], rsi
0x140076adb  lea     rdx, [rbx+14h]; BugCheckParameter2
0x140076adf  mov     [rax+8], rax
0x140076ae3  mov     [rax], rax
0x140076ae6  mov     eax, 0FFFFFFFFh
0x140076aeb  lock xadd [rdx], eax
0x140076aef  dec     eax
0x140076af1  cmp     cs:UxDebugCheckRefcount, 0
0x140076af8  jnz     loc_140076C01
0x140076afe  test    eax, eax
0x140076b00  jnz     loc_1400769A7
0x140076b06  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140076b0d  jnz     loc_140077247
0x140076b13  mov     eax, [rbx+78h]
0x140076b16  xor     edx, edx; Val
0x140076b18  mov     dword ptr [rbx+10h], 6C735875h
0x140076b1f  test    eax, eax
0x140076b21  jz      loc_140076C1E
0x140076b27  cmp     eax, 1
0x140076b2a  jnz     loc_140076C46
0x140076b30  mov     r8d, 60h ; '`'; Size
0x140076b36  lea     rcx, [rbp+57h+var_A0]; void *
0x140076b3a  call    memset
0x140076b3f  cmp     cs:UxDebugDisableLookaside, 0
0x140076b46  jnz     loc_140077286
0x140076b4c  mov     rcx, cs:qword_1401A0640
0x140076b53  cmp     cs:UxCompactMode, 0
0x140076b5a  mov     rdx, rbx
0x140076b5d  jz      short loc_140076B8C
0x140076b5f  call    PnlFreeToLookasideList
0x140076b64  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140076b6b  jz      loc_1400769A7
0x140076b71  mov     edx, 0Bh
0x140076b76  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x140076b7d  mov     ecx, 411h
0x140076b82  call    WPP_SF_
0x140076b87  jmp     loc_1400769A7
0x140076b8c  mov     r8d, [rbx]
0x140076b8f  call    PplFreeToLookasideListProcessor
0x140076b94  jmp     short loc_140076B64
0x140076b96  mov     r8d, 60h ; '`'; Size
0x140076b9c  lea     rcx, [rbp+57h+var_A0]; void *
0x140076ba0  call    memset
0x140076ba5  cmp     cs:UxDebugDisableLookaside, 0
0x140076bac  jnz     loc_1400771C7
0x140076bb2  mov     rcx, cs:qword_1401A0640
0x140076bb9  jmp     short loc_140076BDE
0x140076bbb  mov     r8d, 60h ; '`'; Size
0x140076bc1  lea     rcx, [rbp+57h+var_A0]; void *
0x140076bc5  call    memset
0x140076bca  cmp     cs:UxDebugDisableLookaside, 0
0x140076bd1  jnz     loc_140077226
0x140076bd7  mov     rcx, cs:qword_1401A06A0
0x140076bde  cmp     cs:UxCompactMode, 0
0x140076be5  mov     rdx, r14
0x140076be8  jz      short loc_140076BF4
0x140076bea  call    PnlFreeToLookasideList
0x140076bef  jmp     loc_140076925
0x140076bf4  mov     r8d, [r14]
0x140076bf7  call    PplFreeToLookasideListProcessor
0x140076bfc  jmp     loc_140076925
0x140076c01  cmp     eax, 0FFFFFFFFh
0x140076c04  jg      loc_140076AFE
0x140076c0a  movsxd  r9, eax; BugCheckParameter4
0x140076c0d  mov     ecx, 3; BugCheckParameter1
0x140076c12  mov     r8d, 1Dh; BugCheckParameter3
0x140076c18  call    UlBugCheckEx
0x140076c1e  mov     r8d, 60h ; '`'; Size
0x140076c24  lea     rcx, [rbp+57h+var_A0]; void *
0x140076c28  call    memset
0x140076c2d  cmp     cs:UxDebugDisableLookaside, 0
0x140076c34  jnz     loc_140077265
0x140076c3a  mov     rcx, cs:qword_1401A0610
0x140076c41  jmp     loc_140076B53
0x140076c46  cmp     eax, 2
0x140076c49  jnz     loc_1400772C8
0x140076c4f  mov     r8d, 60h ; '`'; Size
0x140076c55  lea     rcx, [rbp+57h+var_A0]; void *
0x140076c59  call    memset
0x140076c5e  cmp     cs:UxDebugDisableLookaside, 0
0x140076c65  jnz     loc_1400772A7
0x140076c6b  mov     rcx, cs:qword_1401A0670
0x140076c72  jmp     loc_140076B53
0x140076c77  mov     r8d, 60h ; '`'; Size
0x140076c7d  lea     rcx, [rbp+57h+var_A0]; void *
0x140076c81  call    memset
0x140076c86  cmp     cs:UxDebugDisableLookaside, 0
0x140076c8d  jnz     loc_140077010
0x140076c93  mov     rcx, cs:qword_1401A0640
0x140076c9a  cmp     cs:UxCompactMode, 0
0x140076ca1  mov     rdx, r13
0x140076ca4  jz      short loc_140076CD7
0x140076ca6  call    PnlFreeToLookasideList
0x140076cab  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140076cb2  jnz     loc_140077090
0x140076cb8  mov     rcx, [rbp+57h+var_B0]
0x140076cbc  mov     rax, [rbp+57h+P]
0x140076cc0  mov     edi, [rbp+57h+var_B8]
0x140076cc3  mov     [rcx+600h], rax
0x140076cca  mov     [rbp+57h+P], 0
0x140076cd2  jmp     loc_140076991
0x140076cd7  mov     r8d, [r13+0]
0x140076cdb  call    PplFreeToLookasideListProcessor
0x140076ce0  jmp     short loc_140076CAB
0x140076ce2  mov     r8d, 60h ; '`'; Size
0x140076ce8  lea     rcx, [rbp+57h+var_A0]; void *
0x140076cec  call    memset
0x140076cf1  cmp     cs:UxDebugDisableLookaside, 0
0x140076cf8  jnz     loc_1400770EA
0x140076cfe  mov     rcx, cs:qword_1401A0640
0x140076d05  cmp     cs:UxCompactMode, 0
0x140076d0c  mov     rdx, rbx
0x140076d0f  jz      short loc_140076D37
0x140076d11  call    PnlFreeToLookasideList
0x140076d16  test    byte ptr cs:xmmword_1401A2CA0+2, 2
  ... truncated ...
```

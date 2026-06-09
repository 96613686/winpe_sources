# UxpSslCopyTransportIndicationsToHandshakeBuffer

- ea: `0x140076760`
- end: `0x140077304`
- name: `UxpSslCopyTransportIndicationsToHandshakeBuffer`
- size: `2980`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14013c9c8`

## callees

- `0x14000a350`
- `0x140049d08`
- `0x14005dfd0`
- `0x14006e4ec`
- `0x140076760`
- `0x140077310`
- `0x140167810`
- `0x1401678f0`
- `0x140167940`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400768f9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400768f9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140076a76`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140076a76`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007703e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077118`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400771f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400772b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007703e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077118`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400771f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400772b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007680e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007680e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400767f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400767f4`

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
0x140076760  push    rbp
0x140076762  push    rsi
0x140076763  push    r13
0x140076765  push    r15
0x140076767  lea     rbp, [rsp-3Fh]
0x14007676c  sub     rsp, 0D8h
0x140076773  mov     rax, cs:__security_cookie
0x14007677a  xor     rax, rsp
0x14007677d  mov     [rbp+57h+var_40], rax
0x140076781  mov     rsi, rdx
0x140076784  mov     [rbp+57h+var_B0], rcx
0x140076788  mov     r13, rcx
0x14007678b  xor     r15d, r15d
0x14007678e  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140076795  jnz     loc_140076F37
0x14007679b  mov     [rsp+0F0h+arg_10], rbx
0x1400767a3  mov     [rsp+0F0h+var_20], rdi
0x1400767ab  mov     [rsp+0F0h+var_28], r12
0x1400767b3  mov     [rsp+0F0h+var_30], r14
0x1400767bb  mov     rax, [rsi]
0x1400767be  cmp     rax, rsi
0x1400767c1  jz      loc_140076987
0x1400767c7  cmp     [rax+8], rsi
0x1400767cb  jnz     loc_1400769E4
0x1400767d1  mov     rcx, [rax]
0x1400767d4  cmp     [rcx+8], rax
0x1400767d8  jnz     loc_1400769E4
0x1400767de  mov     [rsi], rcx
0x1400767e1  lea     r14, [rax-40h]
0x1400767e5  mov     [rcx+8], rsi
0x1400767e9  lea     rcx, [r14+18h]; SpinLock
0x1400767ed  mov     [rax+8], rax
0x1400767f1  mov     [rax], rax
0x1400767f4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400767fb  nop     dword ptr [rax+rax+00h]
0x140076800  mov     edi, [r14+68h]
0x140076804  lea     rcx, [r14+18h]; SpinLock
0x140076808  movzx   edx, al; NewIrql
0x14007680b  mov     [rbp+57h+var_B8], edi
0x14007680e  call    cs:__imp_KeReleaseSpinLock
0x140076815  nop     dword ptr [rax+rax+00h]
0x14007681a  mov     r13, [r13+600h]
0x140076821  mov     r12d, edi
0x140076824  sub     r12d, [r14+70h]
0x140076828  cmp     [r13+6Ch], r12d
0x14007682c  jb      loc_14007692D
0x140076832  mov     edx, [r14+70h]
0x140076836  mov     r13, [rbp+57h+var_B0]
0x14007683a  add     rdx, [r14+60h]; Src
0x14007683e  mov     r8d, r12d; Size
0x140076841  mov     rbx, [r13+600h]
0x140076848  mov     ecx, [rbx+68h]
0x14007684b  add     rcx, [rbx+60h]; void *
0x14007684f  call    memmove
0x140076854  add     [rbx+68h], r12d
0x140076858  lea     rdx, [r14+14h]; BugCheckParameter2
0x14007685c  sub     [rbx+6Ch], r12d
0x140076860  mov     eax, 0FFFFFFFFh
0x140076865  mov     [r14+70h], edi
0x140076869  lock xadd [rdx], eax
0x14007686d  dec     eax
0x14007686f  cmp     cs:UxDebugCheckRefcount, 0
0x140076876  jnz     loc_140076A52
0x14007687c  test    eax, eax
0x14007687e  jnz     loc_1400767BB
0x140076884  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007688b  jnz     loc_140077168
0x140076891  mov     eax, [r14+78h]
0x140076895  xor     edx, edx; Val
0x140076897  mov     dword ptr [r14+10h], 6C735875h
0x14007689f  test    eax, eax
0x1400768a1  jnz     loc_1400769EB
0x1400768a7  mov     r8d, 60h ; '`'; Size
0x1400768ad  lea     rcx, [rbp+57h+var_A0]; void *
0x1400768b1  call    memset
0x1400768b6  cmp     cs:UxDebugDisableLookaside, 0
0x1400768bd  jnz     loc_140077186
0x1400768c3  cmp     cs:UxCompactMode, 0
0x1400768ca  jnz     loc_140076A6F
0x1400768d0  mov     ebx, [r14]
0x1400768d3  mov     rcx, cs:qword_1401A0610
0x1400768da  inc     ebx
0x1400768dc  shl     rbx, 7
0x1400768e0  add     rbx, rcx
0x1400768e3  movzx   eax, byte ptr [rbx+0B0h]
0x1400768ea  test    al, al
0x1400768ec  jz      loc_140076A44
0x1400768f2  mov     rdx, r14; Entry
0x1400768f5  lea     rcx, [rbx+40h]; Lookaside
0x1400768f9  call    cs:__imp_ExFreeToLookasideListEx
0x140076900  nop     dword ptr [rax+rax+00h]
0x140076905  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007690c  jz      loc_1400767BB
0x140076912  mov     edx, 0Bh
0x140076917  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x14007691e  mov     ecx, 411h
0x140076923  call    WPP_SF_
0x140076928  jmp     loc_1400767BB
0x14007692d  xor     ebx, ebx
0x14007692f  mov     [rbp+57h+P], rbx
0x140076933  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007693a  jnz     loc_140076F5A
0x140076940  test    r13, r13
0x140076943  jz      loc_140076F7D
0x140076949  mov     ecx, [r13+68h]
0x14007694d  add     ecx, r12d
0x140076950  lea     rdx, [rbp+57h+P]
0x140076954  call    UxSslAllocateTransportDataIndication
0x140076959  mov     r15d, eax
0x14007695c  test    eax, eax
0x14007695e  jns     loc_140076F90
0x140076964  mov     rbx, [rbp+57h+P]
0x140076968  test    rbx, rbx
0x14007696b  jnz     loc_140076E07
0x140076971  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140076978  jnz     loc_14007714A
0x14007697e  test    r15d, r15d
0x140076981  jns     loc_140076832
0x140076987  mov     rax, [rsi]
0x14007698a  cmp     rax, rsi
0x14007698d  jnz     short loc_1400769DA
0x14007698f  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140076996  jnz     loc_1400772E6
0x14007699c  mov     r14, [rsp+0F0h+var_30]
0x1400769a4  mov     eax, r15d
0x1400769a7  mov     r12, [rsp+0F0h+var_28]
0x1400769af  mov     rdi, [rsp+0F0h+var_20]
0x1400769b7  mov     rbx, [rsp+0F0h+arg_10]
0x1400769bf  mov     rcx, [rbp+57h+var_40]
0x1400769c3  xor     rcx, rsp; StackCookie
0x1400769c6  call    __security_check_cookie
0x1400769cb  add     rsp, 0D8h
0x1400769d2  pop     r15
0x1400769d4  pop     r13
0x1400769d6  pop     rsi
0x1400769d7  pop     rbp
0x1400769d8  retn
0x1400769da  cmp     [rax+8], rsi
0x1400769de  jz      loc_140076AA3
0x1400769e4  mov     ecx, 3
0x1400769e9  int     29h; Win8: RtlFailFast(ecx)
0x1400769eb  cmp     eax, 1
0x1400769ee  jz      loc_140076B76
0x1400769f4  cmp     eax, 2
0x1400769f7  jnz     loc_1400771E9
0x1400769fd  mov     r8d, 60h ; '`'; Size
0x140076a03  lea     rcx, [rbp+57h+var_A0]; void *
0x140076a07  call    memset
0x140076a0c  cmp     cs:UxDebugDisableLookaside, 0
0x140076a13  jnz     loc_1400771C8
0x140076a19  cmp     cs:UxCompactMode, 0
0x140076a20  mov     rcx, cs:qword_1401A0670
0x140076a27  jnz     short loc_140076A96
0x140076a29  mov     ebx, [r14]
0x140076a2c  inc     ebx
0x140076a2e  shl     rbx, 7
0x140076a32  add     rbx, rcx
0x140076a35  movzx   eax, byte ptr [rbx+0B0h]
0x140076a3c  test    al, al
0x140076a3e  jnz     loc_1400768F2
0x140076a44  lea     rdx, [rbx+40h]
0x140076a48  call    PplpLazyInitializeLookasideList
0x140076a4d  jmp     loc_1400768F2
0x140076a52  cmp     eax, 0FFFFFFFFh
0x140076a55  jg      loc_14007687C
0x140076a5b  movsxd  r9, eax; BugCheckParameter4
0x140076a5e  mov     ecx, 3; BugCheckParameter1
0x140076a63  mov     r8d, 1Dh; BugCheckParameter3
0x140076a69  call    UlBugCheckEx
0x140076a6f  mov     rbx, cs:qword_1401A0610
0x140076a76  call    cs:__imp_KeGetCurrentNodeNumber
0x140076a7d  nop     dword ptr [rax+rax+00h]
0x140076a82  movzx   r8d, ax
0x140076a86  mov     rdx, r14
0x140076a89  mov     rcx, rbx
0x140076a8c  call    PplFreeToLookasideListProcessor
0x140076a91  jmp     loc_140076905
0x140076a96  mov     rdx, r14
0x140076a99  call    PnlFreeToLookasideList
0x140076a9e  jmp     loc_140076905
0x140076aa3  mov     rcx, [rax]
0x140076aa6  cmp     [rcx+8], rax
0x140076aaa  jnz     loc_1400769E4
0x140076ab0  mov     [rsi], rcx
0x140076ab3  lea     rbx, [rax-40h]
0x140076ab7  mov     [rcx+8], rsi
0x140076abb  lea     rdx, [rbx+14h]; BugCheckParameter2
0x140076abf  mov     [rax+8], rax
0x140076ac3  mov     [rax], rax
0x140076ac6  mov     eax, 0FFFFFFFFh
0x140076acb  lock xadd [rdx], eax
0x140076acf  dec     eax
0x140076ad1  cmp     cs:UxDebugCheckRefcount, 0
0x140076ad8  jnz     loc_140076BE1
0x140076ade  test    eax, eax
0x140076ae0  jnz     loc_140076987
0x140076ae6  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140076aed  jnz     loc_140077227
0x140076af3  mov     eax, [rbx+78h]
0x140076af6  xor     edx, edx; Val
0x140076af8  mov     dword ptr [rbx+10h], 6C735875h
0x140076aff  test    eax, eax
0x140076b01  jz      loc_140076BFE
0x140076b07  cmp     eax, 1
0x140076b0a  jnz     loc_140076C26
0x140076b10  mov     r8d, 60h ; '`'; Size
0x140076b16  lea     rcx, [rbp+57h+var_A0]; void *
0x140076b1a  call    memset
0x140076b1f  cmp     cs:UxDebugDisableLookaside, 0
0x140076b26  jnz     loc_140077266
0x140076b2c  mov     rcx, cs:qword_1401A0640
0x140076b33  cmp     cs:UxCompactMode, 0
0x140076b3a  mov     rdx, rbx
0x140076b3d  jz      short loc_140076B6C
0x140076b3f  call    PnlFreeToLookasideList
0x140076b44  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140076b4b  jz      loc_140076987
0x140076b51  mov     edx, 0Bh
0x140076b56  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x140076b5d  mov     ecx, 411h
0x140076b62  call    WPP_SF_
0x140076b67  jmp     loc_140076987
0x140076b6c  mov     r8d, [rbx]
0x140076b6f  call    PplFreeToLookasideListProcessor
0x140076b74  jmp     short loc_140076B44
0x140076b76  mov     r8d, 60h ; '`'; Size
0x140076b7c  lea     rcx, [rbp+57h+var_A0]; void *
0x140076b80  call    memset
0x140076b85  cmp     cs:UxDebugDisableLookaside, 0
0x140076b8c  jnz     loc_1400771A7
0x140076b92  mov     rcx, cs:qword_1401A0640
0x140076b99  jmp     short loc_140076BBE
0x140076b9b  mov     r8d, 60h ; '`'; Size
0x140076ba1  lea     rcx, [rbp+57h+var_A0]; void *
0x140076ba5  call    memset
0x140076baa  cmp     cs:UxDebugDisableLookaside, 0
0x140076bb1  jnz     loc_140077206
0x140076bb7  mov     rcx, cs:qword_1401A06A0
0x140076bbe  cmp     cs:UxCompactMode, 0
0x140076bc5  mov     rdx, r14
0x140076bc8  jz      short loc_140076BD4
0x140076bca  call    PnlFreeToLookasideList
0x140076bcf  jmp     loc_140076905
0x140076bd4  mov     r8d, [r14]
0x140076bd7  call    PplFreeToLookasideListProcessor
0x140076bdc  jmp     loc_140076905
0x140076be1  cmp     eax, 0FFFFFFFFh
0x140076be4  jg      loc_140076ADE
0x140076bea  movsxd  r9, eax; BugCheckParameter4
0x140076bed  mov     ecx, 3; BugCheckParameter1
0x140076bf2  mov     r8d, 1Dh; BugCheckParameter3
0x140076bf8  call    UlBugCheckEx
0x140076bfe  mov     r8d, 60h ; '`'; Size
0x140076c04  lea     rcx, [rbp+57h+var_A0]; void *
0x140076c08  call    memset
0x140076c0d  cmp     cs:UxDebugDisableLookaside, 0
0x140076c14  jnz     loc_140077245
0x140076c1a  mov     rcx, cs:qword_1401A0610
0x140076c21  jmp     loc_140076B33
0x140076c26  cmp     eax, 2
0x140076c29  jnz     loc_1400772A8
0x140076c2f  mov     r8d, 60h ; '`'; Size
0x140076c35  lea     rcx, [rbp+57h+var_A0]; void *
0x140076c39  call    memset
0x140076c3e  cmp     cs:UxDebugDisableLookaside, 0
0x140076c45  jnz     loc_140077287
0x140076c4b  mov     rcx, cs:qword_1401A0670
0x140076c52  jmp     loc_140076B33
0x140076c57  mov     r8d, 60h ; '`'; Size
0x140076c5d  lea     rcx, [rbp+57h+var_A0]; void *
0x140076c61  call    memset
0x140076c66  cmp     cs:UxDebugDisableLookaside, 0
0x140076c6d  jnz     loc_140076FF0
0x140076c73  mov     rcx, cs:qword_1401A0640
0x140076c7a  cmp     cs:UxCompactMode, 0
0x140076c81  mov     rdx, r13
0x140076c84  jz      short loc_140076CB7
0x140076c86  call    PnlFreeToLookasideList
0x140076c8b  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140076c92  jnz     loc_140077070
0x140076c98  mov     rcx, [rbp+57h+var_B0]
0x140076c9c  mov     rax, [rbp+57h+P]
0x140076ca0  mov     edi, [rbp+57h+var_B8]
0x140076ca3  mov     [rcx+600h], rax
0x140076caa  mov     [rbp+57h+P], 0
0x140076cb2  jmp     loc_140076971
0x140076cb7  mov     r8d, [r13+0]
0x140076cbb  call    PplFreeToLookasideListProcessor
0x140076cc0  jmp     short loc_140076C8B
0x140076cc2  mov     r8d, 60h ; '`'; Size
0x140076cc8  lea     rcx, [rbp+57h+var_A0]; void *
0x140076ccc  call    memset
0x140076cd1  cmp     cs:UxDebugDisableLookaside, 0
0x140076cd8  jnz     loc_1400770CA
0x140076cde  mov     rcx, cs:qword_1401A0640
0x140076ce5  cmp     cs:UxCompactMode, 0
0x140076cec  mov     rdx, rbx
0x140076cef  jz      short loc_140076D17
0x140076cf1  call    PnlFreeToLookasideList
0x140076cf6  test    byte ptr cs:xmmword_1401A2CA0+2, 2
  ... truncated ...
```

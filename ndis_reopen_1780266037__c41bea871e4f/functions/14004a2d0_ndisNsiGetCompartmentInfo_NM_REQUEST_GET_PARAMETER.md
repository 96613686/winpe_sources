# ndisNsiGetCompartmentInfo(_NM_REQUEST_GET_PARAMETER *)

- ea: `0x14004a2d0`
- end: `0x14004aa27`
- name: `?ndisNsiGetCompartmentInfo@@YAJPEAU_NM_REQUEST_GET_PARAMETER@@@Z`
- size: `1879`
- prototype: `__int64 __fastcall(struct _NM_REQUEST_GET_PARAMETER *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400110b0`
- `0x1400114b0`
- `0x14004a2d0`
- `0x1400eb4c0`
- `0x1400ebce0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004a397`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004a401`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004a397`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004a401`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004a619`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004a619`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004a2ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004a2ff`
- `ntoskrnl!ObfDereferenceObject` at `0x14004a9a6`
- `ntoskrnl!ObfDereferenceObject` at `0x14004a9a6`
- `ntoskrnl!KeSetEvent` at `0x14004a5c4`
- `ntoskrnl!KeSetEvent` at `0x14004a5c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004a4c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004a5db`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004a773`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004a7d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004a8fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004a4c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004a5db`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004a773`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004a7d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004a8fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004a46d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004a4d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004a594`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004a8cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004a46d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004a4d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004a594`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004a8cb`
- `ntoskrnl!SeQueryInformationToken` at `0x14004a6a2`
- `ntoskrnl!SeQueryInformationToken` at `0x14004a6db`
- `ntoskrnl!SeQueryInformationToken` at `0x14004a6a2`
- `ntoskrnl!SeQueryInformationToken` at `0x14004a6db`
- `ntoskrnl!PsGetThreadProperty` at `0x14004a36c`
- `ntoskrnl!PsGetThreadProperty` at `0x14004a36c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004a92c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004a93d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004a92c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004a93d`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004a3ba`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004a424`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004a3ba`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004a424`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004a3d5`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004a43f`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004a3d5`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004a43f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004a6b3`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004a6ec`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004a6b3`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004a6ec`

## pseudocode

```c
__int64 __fastcall ndisNsiGetCompartmentInfo(struct _NM_REQUEST_GET_PARAMETER *a1)
{
  int v2; // edx
  struct _KTHREAD *CurrentThread; // rsi
  unsigned int v4; // r12d
  unsigned __int8 v5; // r13
  unsigned int *ThreadProperty; // rax
  PACCESS_TOKEN v7; // rax
  void *v8; // r14
  unsigned int CurrentProcessSessionId; // eax
  unsigned int v10; // edi
  struct _KTHREAD *v11; // rsi
  PACCESS_TOKEN v12; // rax
  void *v13; // r14
  unsigned int ThreadSessionId; // eax
  unsigned int v15; // r14d
  KIRQL v16; // al
  struct _NDIS_IF_COMPARTMENT_BLOCK *v17; // rcx
  KIRQL v18; // r8
  struct _NDIS_IF_COMPARTMENT_BLOCK *i; // rax
  KIRQL v20; // al
  int v21; // edx
  KIRQL v22; // r15
  int v23; // edx
  unsigned int v24; // esi
  KIRQL v25; // dl
  int v26; // r12d
  unsigned int v27; // r14d
  char *v28; // rsi
  unsigned int v29; // r14d
  KIRQL v30; // r14
  struct _KEVENT *v31; // rcx
  unsigned int v33; // eax
  int v34; // r15d
  NTSTATUS v35; // edi
  NTSTATUS v36; // edi
  struct _NDIS_IF_COMPARTMENT_BLOCK *v37; // rax
  struct _NDIS_IF_COMPARTMENT_BLOCK *v38; // rdi
  struct _NDIS_IF_COMPARTMENT_BLOCK *v39; // rax
  _DWORD *v40; // rcx
  int v41; // eax
  int v42; // esi
  KIRQL v43; // r8
  __int128 Buf1; // [rsp+40h] [rbp-9h] BYREF
  __int64 v45; // [rsp+50h] [rbp+7h]
  unsigned __int8 EffectiveOnly; // [rsp+B0h] [rbp+67h] BYREF
  unsigned int CopyOnOpen; // [rsp+B8h] [rbp+6Fh] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+C0h] [rbp+77h] BYREF
  PVOID TokenInformation; // [rsp+C8h] [rbp+7Fh] BYREF

  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      22,
      43,
      (struct _GUID *)&WPP_7b6e8809435e3846b6104774dae7899f_Traceguids,
      (char)a1);
  KeEnterCriticalRegion();
  if ( *((_DWORD *)a1 + 6) == 4 )
  {
    if ( *((_DWORD *)a1 + 12) )
    {
      if ( *((_QWORD *)a1 + 5) )
      {
        CurrentThread = KeGetCurrentThread();
        v4 = **((_DWORD **)a1 + 2);
        v5 = 0;
        v45 = 0;
        Buf1 = 0;
        ThreadProperty = (unsigned int *)PsGetThreadProperty(CurrentThread, 0x6D43644Eu, 0);
        if ( ThreadProperty )
        {
          v15 = *ThreadProperty;
          ObfDereferenceObject(ThreadProperty);
          if ( v15 )
            goto LABEL_18;
        }
        LOBYTE(CopyOnOpen) = 0;
        EffectiveOnly = 0;
        ImpersonationLevel = SecurityAnonymous;
        TokenInformation = 0;
        if ( KeGetCurrentIrql() >= 2u )
        {
          CurrentProcessSessionId = PsGetCurrentProcessSessionId();
        }
        else
        {
          v7 = PsReferenceImpersonationToken(CurrentThread, (PBOOLEAN)&CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
          v8 = v7;
          if ( v7 )
          {
            v35 = SeQueryInformationToken(v7, TokenSessionId, &TokenInformation);
            PsDereferenceImpersonationToken(v8);
            if ( v35 >= 0 )
            {
              v10 = (unsigned int)TokenInformation;
LABEL_11:
              if ( v10 != -1 )
                goto LABEL_16;
              v11 = KeGetCurrentThread();
              LOBYTE(CopyOnOpen) = 0;
              EffectiveOnly = 0;
              ImpersonationLevel = SecurityAnonymous;
              TokenInformation = 0;
              if ( KeGetCurrentIrql() >= 2u )
              {
                ThreadSessionId = PsGetCurrentProcessSessionId();
              }
              else
              {
                v12 = PsReferenceImpersonationToken(v11, (PBOOLEAN)&CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
                v13 = v12;
                if ( v12 )
                {
                  v36 = SeQueryInformationToken(v12, TokenSessionId, &TokenInformation);
                  PsDereferenceImpersonationToken(v13);
                  if ( v36 >= 0 )
                  {
                    v10 = (unsigned int)TokenInformation;
LABEL_16:
                    if ( v10 < dword_140122898 )
                    {
                      v42 = 0;
                      v43 = KeAcquireSpinLockRaiseToDpc(&qword_1401228E0);
                      if ( v10 < dword_140122898 )
                        v42 = *((_DWORD *)qword_1401228E8 + 6 * v10);
                      KeReleaseSpinLock(&qword_1401228E0, v43);
                      if ( !v42 )
                        v42 = 1;
                      v15 = v42;
                    }
                    else
                    {
                      v15 = 1;
                    }
LABEL_18:
                    v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
                    v17 = 0;
                    v18 = v16;
                    for ( i = qword_1401229D8;
                          i != (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_1401229D8;
                          i = *(struct _NDIS_IF_COMPARTMENT_BLOCK **)i )
                    {
                      if ( *((_DWORD *)i + 4) == v15 )
                      {
                        v17 = i;
                        break;
                      }
                      if ( *((_DWORD *)i + 4) > v15 )
                        break;
                    }
                    *((_QWORD *)&Buf1 + 1) = *(_QWORD *)((char *)v17 + 1684);
                    v45 = *(_QWORD *)((char *)v17 + 1692);
                    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v18);
                    v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
                    v21 = *((_DWORD *)a1 + 14);
                    v22 = v20;
                    if ( v21 )
                    {
                      v23 = v21 - 1;
                      if ( !v23 )
                      {
                        v4 = 0;
                        goto LABEL_75;
                      }
                      if ( v23 != 1 )
                      {
                        v24 = -1073741808;
                        v25 = v20;
LABEL_47:
                        KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v25);
                        goto LABEL_48;
                      }
LABEL_75:
                      while ( 1 )
                      {
                        v39 = qword_1401229D8;
                        v38 = 0;
                        while ( v39 != (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_1401229D8 )
                        {
                          if ( *((_DWORD *)v39 + 4) > v4 )
                          {
                            v38 = v39;
                            break;
                          }
                          v39 = *(struct _NDIS_IF_COMPARTMENT_BLOCK **)v39;
                        }
                        if ( !v38 )
                          goto LABEL_73;
                        v4 = *((_DWORD *)v38 + 4);
                        if ( v15 == v4
                          || !memcmp((char *)&Buf1 + 8, (char *)v38 + 1684, 0x10u)
                          || (*((_DWORD *)v38 + 420) & 2) == 0 && v15 == 1 )
                        {
                          goto LABEL_82;
                        }
                      }
                    }
                    v37 = qword_1401229D8;
                    v38 = 0;
                    while ( v37 != (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_1401229D8 )
                    {
                      if ( *((_DWORD *)v37 + 4) == v4 )
                      {
                        v38 = v37;
                        break;
                      }
                      if ( *((_DWORD *)v37 + 4) > v4 )
                        break;
                      v37 = *(struct _NDIS_IF_COMPARTMENT_BLOCK **)v37;
                    }
                    if ( !v38 )
                    {
LABEL_73:
                      KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v22);
                      v24 = -1073741772;
                      if ( *((_DWORD *)a1 + 14) )
                        v24 = -2147483622;
                      goto LABEL_42;
                    }
                    if ( v15 != *((_DWORD *)v38 + 4)
                      && memcmp((char *)&Buf1 + 8, (char *)v38 + 1684, 0x10u)
                      && ((*((_DWORD *)v38 + 420) & 2) != 0 || v15 != 1) )
                    {
                      v38 = 0;
                      goto LABEL_73;
                    }
LABEL_82:
                    v24 = 0;
                    CopyOnOpen = 0;
                    _InterlockedIncrement((volatile signed __int32 *)v38 + 11);
                    v40 = (_DWORD *)*((_QWORD *)a1 + 2);
                    v41 = *((_DWORD *)v38 + 4);
                    EffectiveOnly = 1;
                    *v40 = v41;
                    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v22);
                    if ( *((_DWORD *)a1 + 8) )
                    {
                      v24 = -1073741808;
                      goto LABEL_41;
                    }
                    if ( !*((_QWORD *)a1 + 5) )
                    {
                      *((_DWORD *)a1 + 12) = 0;
LABEL_41:
                      v5 = EffectiveOnly;
LABEL_42:
                      if ( !v5 )
                        goto LABEL_48;
                      v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v38 + 11, 0xFFFFFFFF) == 1 )
                      {
                        v31 = (struct _KEVENT *)*((_QWORD *)v38 + 214);
                        if ( v31 )
                          KeSetEvent(v31, 0, 0);
                      }
                      v25 = v30;
                      goto LABEL_47;
                    }
                    v26 = *((_DWORD *)a1 + 12);
                    v27 = *((_DWORD *)a1 + 13);
                    if ( v26 <= 0 )
                    {
LABEL_39:
                      v29 = v27 - *((_DWORD *)a1 + 13);
                      *((_DWORD *)a1 + 12) = v29;
                      if ( !v29 )
                        v24 = -1073741811;
                      goto LABEL_41;
                    }
                    v28 = (char *)*((_QWORD *)a1 + 5);
                    while ( 1 )
                    {
                      if ( v5 )
                      {
LABEL_38:
                        v24 = CopyOnOpen;
                        goto LABEL_39;
                      }
                      if ( v27 > 0x234 )
                        break;
                      if ( v27 == 564 )
                      {
                        v33 = 516;
                        v34 = 1080;
                      }
                      else if ( v27 )
                      {
                        switch ( v27 )
                        {
                          case 8u:
                            v33 = 8;
                            v34 = 16;
                            break;
                          case 0x10u:
                            v34 = 32;
LABEL_86:
                            v33 = 16;
                            break;
                          case 0x20u:
                            v34 = 48;
                            v33 = 16;
                            break;
                          case 0x30u:
                            v33 = 516;
                            v34 = 564;
                            break;
                          default:
                            goto LABEL_36;
                        }
                      }
                      else
                      {
                        v33 = 4;
                        v34 = 8;
                      }
LABEL_55:
                      if ( v26 >= v33 )
                      {
                        memmove(v28, (char *)v38 + v27 + 64, v33);
                        v28 += v34 - v27;
                        v26 += v27 - v34;
                        v27 = v34;
                        goto LABEL_37;
                      }
LABEL_36:
                      v5 = 1;
LABEL_37:
                      if ( v26 <= 0 )
                        goto LABEL_38;
                    }
                    if ( v27 != 1080 )
                    {
                      switch ( v27 )
                      {
                        case 0x448u:
                          v33 = 516;
                          v34 = 1616;
                          break;
                        case 0x650u:
                          v33 = 4;
                          v34 = 1620;
                          break;
                        case 0x654u:
                          v34 = 1636;
                          v5 = 1;
                          v33 = 16;
                          break;
                        default:
                          goto LABEL_36;
                      }
                      goto LABEL_55;
                    }
                    v34 = 1096;
                    goto LABEL_86;
                  }
                }
                ThreadSessionId = PsGetThreadSessionId(v11);
              }
              v10 = ThreadSessionId;
              goto LABEL_16;
            }
          }
          CurrentProcessSessionId = PsGetThreadSessionId(CurrentThread);
        }
        v10 = CurrentProcessSessionId;
        goto LABEL_11;
      }
      v24 = -1073741808;
    }
    else
    {
      v24 = -1073741808;
    }
  }
  else
  {
    v24 = -1073741808;
  }
LABEL_48:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v2,
      22,
      44,
      (struct _GUID *)&WPP_7b6e8809435e3846b6104774dae7899f_Traceguids,
      (char)a1,
      v24);
  }
  KeLeaveCriticalRegion();
  return v24;
}

```

## disassembly

```asm
0x14004a2d0  push    rbp
0x14004a2d2  push    rbx
0x14004a2d3  push    rsi
0x14004a2d4  push    rdi
0x14004a2d5  lea     rbp, [rsp-3Fh]
0x14004a2da  sub     rsp, 88h
0x14004a2e1  mov     rbx, rcx
0x14004a2e4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004a2eb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004a2f2  lea     rdi, WPP_7b6e8809435e3846b6104774dae7899f_Traceguids
0x14004a2f9  jnz     loc_14004A9DC
0x14004a2ff  call    cs:__imp_KeEnterCriticalRegion
0x14004a306  nop     dword ptr [rax+rax+00h]
0x14004a30b  cmp     dword ptr [rbx+18h], 4
0x14004a30f  jnz     loc_14004AA09
0x14004a315  cmp     dword ptr [rbx+30h], 0
0x14004a319  jz      loc_14004AA13
0x14004a31f  cmp     qword ptr [rbx+28h], 0
0x14004a324  jz      loc_14004AA1D
0x14004a32a  mov     rax, [rbx+10h]
0x14004a32e  xorps   xmm0, xmm0
0x14004a331  mov     rsi, gs:188h
0x14004a33a  xor     r8d, r8d; Flags
0x14004a33d  mov     [rsp+0A0h+var_20], r12
0x14004a345  mov     edx, 6D43644Eh; Key
0x14004a34a  mov     [rsp+0A0h+var_28], r13
0x14004a34f  mov     rcx, rsi; Thread
0x14004a352  mov     r12d, [rax]
0x14004a355  xor     r13b, r13b
0x14004a358  xor     eax, eax
0x14004a35a  mov     [rsp+0A0h+var_30], r14
0x14004a35f  mov     [rbp+57h+var_50], rax
0x14004a363  mov     [rsp+0A0h+var_38], r15
0x14004a368  movups  [rbp+57h+Buf1], xmm0
0x14004a36c  call    cs:__imp_PsGetThreadProperty
0x14004a373  nop     dword ptr [rax+rax+00h]
0x14004a378  xor     r15d, r15d
0x14004a37b  mov     rcx, rax; Object
0x14004a37e  test    rax, rax
0x14004a381  jnz     loc_14004A999
0x14004a387  mov     byte ptr [rbp+57h+CopyOnOpen], r13b
0x14004a38b  mov     [rbp+57h+EffectiveOnly], r13b
0x14004a38f  mov     [rbp+57h+ImpersonationLevel], r15d
0x14004a393  mov     [rbp+57h+TokenInformation], r15
0x14004a397  call    cs:__imp_KeGetCurrentIrql
0x14004a39e  nop     dword ptr [rax+rax+00h]
0x14004a3a3  cmp     al, 2
0x14004a3a5  jnb     loc_14004A92C
0x14004a3ab  lea     r9, [rbp+57h+ImpersonationLevel]; ImpersonationLevel
0x14004a3af  mov     rcx, rsi; Thread
0x14004a3b2  lea     r8, [rbp+57h+EffectiveOnly]; EffectiveOnly
0x14004a3b6  lea     rdx, [rbp+57h+CopyOnOpen]; CopyOnOpen
0x14004a3ba  call    cs:__imp_PsReferenceImpersonationToken
0x14004a3c1  nop     dword ptr [rax+rax+00h]
0x14004a3c6  mov     r14, rax
0x14004a3c9  test    rax, rax
0x14004a3cc  jnz     loc_14004A696
0x14004a3d2  mov     rcx, rsi
0x14004a3d5  call    cs:__imp_PsGetThreadSessionId
0x14004a3dc  nop     dword ptr [rax+rax+00h]
0x14004a3e1  mov     edi, eax
0x14004a3e3  cmp     edi, 0FFFFFFFFh
0x14004a3e6  jnz     short loc_14004A44D
0x14004a3e8  mov     rsi, gs:188h
0x14004a3f1  mov     byte ptr [rbp+57h+CopyOnOpen], r13b
0x14004a3f5  mov     [rbp+57h+EffectiveOnly], r13b
0x14004a3f9  mov     [rbp+57h+ImpersonationLevel], r15d
0x14004a3fd  mov     [rbp+57h+TokenInformation], r15
0x14004a401  call    cs:__imp_KeGetCurrentIrql
0x14004a408  nop     dword ptr [rax+rax+00h]
0x14004a40d  cmp     al, 2
0x14004a40f  jnb     loc_14004A93D
0x14004a415  lea     r9, [rbp+57h+ImpersonationLevel]; ImpersonationLevel
0x14004a419  mov     rcx, rsi; Thread
0x14004a41c  lea     r8, [rbp+57h+EffectiveOnly]; EffectiveOnly
0x14004a420  lea     rdx, [rbp+57h+CopyOnOpen]; CopyOnOpen
0x14004a424  call    cs:__imp_PsReferenceImpersonationToken
0x14004a42b  nop     dword ptr [rax+rax+00h]
0x14004a430  mov     r14, rax
0x14004a433  test    rax, rax
0x14004a436  jnz     loc_14004A6CF
0x14004a43c  mov     rcx, rsi
0x14004a43f  call    cs:__imp_PsGetThreadSessionId
0x14004a446  nop     dword ptr [rax+rax+00h]
0x14004a44b  mov     edi, eax
0x14004a44d  cmp     edi, cs:dword_140122898
0x14004a453  jb      loc_14004A8C1
0x14004a459  mov     r14d, 1
0x14004a45f  mov     dword ptr [rbp+57h+Buf1+4], r14d
0x14004a463  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004a46a  mov     edi, r14d
0x14004a46d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004a474  nop     dword ptr [rax+rax+00h]
0x14004a479  mov     rcx, r15
0x14004a47c  lea     rsi, qword_1401229D8
0x14004a483  movzx   r8d, al
0x14004a487  mov     rax, cs:qword_1401229D8
0x14004a48e  cmp     rax, rsi
0x14004a491  jz      short loc_14004A49F
0x14004a493  cmp     [rax+10h], edi
0x14004a496  jnz     loc_14004A708
0x14004a49c  mov     rcx, rax
0x14004a49f  mov     rax, [rcx+694h]
0x14004a4a6  movzx   edx, r8b; NewIrql
0x14004a4aa  mov     qword ptr [rbp+57h+Buf1+8], rax
0x14004a4ae  mov     rax, [rcx+69Ch]
0x14004a4b5  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004a4bc  mov     [rbp+57h+var_50], rax
0x14004a4c0  call    cs:__imp_KeReleaseSpinLock
0x14004a4c7  nop     dword ptr [rax+rax+00h]
0x14004a4cc  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004a4d3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004a4da  nop     dword ptr [rax+rax+00h]
0x14004a4df  mov     edx, [rbx+38h]
0x14004a4e2  movzx   r15d, al
0x14004a4e6  test    edx, edx
0x14004a4e8  jz      loc_14004A716
0x14004a4ee  sub     edx, 1
0x14004a4f1  jz      loc_14004A784
0x14004a4f7  cmp     edx, 1
0x14004a4fa  jz      loc_14004A787
0x14004a500  mov     esi, 0C0000010h
0x14004a505  movzx   edx, al
0x14004a508  jmp     loc_14004A5D4
0x14004a50d  mov     r12d, [rbx+30h]
0x14004a511  mov     r14d, [rbx+34h]
0x14004a515  test    r12d, r12d
0x14004a518  jle     short loc_14004A574
0x14004a51a  mov     rsi, rax
0x14004a51d  nop     dword ptr [rax]
0x14004a520  test    r13b, r13b
0x14004a523  jnz     short loc_14004A571
0x14004a525  cmp     r14d, 234h
0x14004a52c  ja      loc_14004A634
0x14004a532  jz      loc_14004A84E
0x14004a538  test    r14d, r14d
0x14004a53b  jz      loc_14004A83E
0x14004a541  cmp     r14d, 8
0x14004a545  jz      loc_14004A82E
0x14004a54b  cmp     r14d, 10h
0x14004a54f  jz      loc_14004A805
0x14004a555  cmp     r14d, 20h ; ' '
0x14004a559  jz      loc_14004A8B1
0x14004a55f  cmp     r14d, 30h ; '0'
0x14004a563  jz      loc_14004A989
0x14004a569  mov     r13b, 1
0x14004a56c  test    r12d, r12d
0x14004a56f  jg      short loc_14004A520
0x14004a571  mov     esi, [rbp+57h+CopyOnOpen]
0x14004a574  sub     r14d, [rbx+34h]
0x14004a578  mov     [rbx+30h], r14d
0x14004a57c  jnz     short loc_14004A583
0x14004a57e  mov     esi, 0C000000Dh
0x14004a583  movzx   r13d, [rbp+57h+EffectiveOnly]
0x14004a588  test    r13b, r13b
0x14004a58b  jz      short loc_14004A5E7
0x14004a58d  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004a594  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004a59b  nop     dword ptr [rax+rax+00h]
0x14004a5a0  movzx   r14d, al
0x14004a5a4  mov     eax, 0FFFFFFFFh
0x14004a5a9  lock xadd [rdi+2Ch], eax
0x14004a5ae  cmp     eax, 1
0x14004a5b1  jnz     short loc_14004A5D0
0x14004a5b3  mov     rcx, [rdi+6B0h]; Event
0x14004a5ba  test    rcx, rcx
0x14004a5bd  jz      short loc_14004A5D0
0x14004a5bf  xor     r8d, r8d; Wait
0x14004a5c2  xor     edx, edx; Increment
0x14004a5c4  call    cs:__imp_KeSetEvent
0x14004a5cb  nop     dword ptr [rax+rax+00h]
0x14004a5d0  movzx   edx, r14b; NewIrql
0x14004a5d4  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004a5db  call    cs:__imp_KeReleaseSpinLock
0x14004a5e2  nop     dword ptr [rax+rax+00h]
0x14004a5e7  mov     r14, [rsp+0A0h+var_30]
0x14004a5ec  lea     rdi, WPP_7b6e8809435e3846b6104774dae7899f_Traceguids
0x14004a5f3  mov     r13, [rsp+0A0h+var_28]
0x14004a5f8  mov     r12, [rsp+0A0h+var_20]
0x14004a600  mov     r15, [rsp+0A0h+var_38]
0x14004a605  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004a60c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004a613  jnz     loc_14004A880
0x14004a619  call    cs:__imp_KeLeaveCriticalRegion
0x14004a620  nop     dword ptr [rax+rax+00h]
0x14004a625  mov     eax, esi
0x14004a627  add     rsp, 88h
0x14004a62e  pop     rdi
0x14004a62f  pop     rsi
0x14004a630  pop     rbx
0x14004a631  pop     rbp
0x14004a632  retn
0x14004a634  mov     eax, r14d
0x14004a637  sub     eax, 438h
0x14004a63c  jz      loc_14004A86E
0x14004a642  sub     eax, 10h
0x14004a645  jz      loc_14004A85E
0x14004a64b  sub     eax, 208h
0x14004a650  jnz     loc_14004A9C0
0x14004a656  mov     eax, 4
0x14004a65b  mov     r15d, 654h
0x14004a661  cmp     r12d, eax
0x14004a664  jb      loc_14004A569
0x14004a66a  mov     edx, r14d
0x14004a66d  mov     rcx, rsi; void *
0x14004a670  add     rdx, 40h ; '@'
0x14004a674  mov     r8d, eax; Size
0x14004a677  add     rdx, rdi; Src
0x14004a67a  call    memmove
0x14004a67f  mov     eax, r15d
0x14004a682  sub     eax, r14d
0x14004a685  sub     r14d, r15d
0x14004a688  add     rsi, rax
0x14004a68b  add     r12d, r14d
0x14004a68e  mov     r14d, r15d
0x14004a691  jmp     loc_14004A56C
0x14004a696  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14004a69a  mov     edx, 0Ch; TokenInformationClass
0x14004a69f  mov     rcx, r14; Token
0x14004a6a2  call    cs:__imp_SeQueryInformationToken
0x14004a6a9  nop     dword ptr [rax+rax+00h]
0x14004a6ae  mov     rcx, r14; ImpersonationToken
0x14004a6b1  mov     edi, eax
0x14004a6b3  call    cs:__imp_PsDereferenceImpersonationToken
0x14004a6ba  nop     dword ptr [rax+rax+00h]
0x14004a6bf  test    edi, edi
0x14004a6c1  js      loc_14004A3D2
0x14004a6c7  mov     edi, dword ptr [rbp+57h+TokenInformation]
0x14004a6ca  jmp     loc_14004A3E3
0x14004a6cf  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14004a6d3  mov     edx, 0Ch; TokenInformationClass
0x14004a6d8  mov     rcx, r14; Token
0x14004a6db  call    cs:__imp_SeQueryInformationToken
0x14004a6e2  nop     dword ptr [rax+rax+00h]
0x14004a6e7  mov     rcx, r14; ImpersonationToken
0x14004a6ea  mov     edi, eax
0x14004a6ec  call    cs:__imp_PsDereferenceImpersonationToken
0x14004a6f3  nop     dword ptr [rax+rax+00h]
0x14004a6f8  test    edi, edi
0x14004a6fa  js      loc_14004A43C
0x14004a700  mov     edi, dword ptr [rbp+57h+TokenInformation]
0x14004a703  jmp     loc_14004A44D
0x14004a708  ja      loc_14004A49F
0x14004a70e  mov     rax, [rax]
0x14004a711  jmp     loc_14004A48E
0x14004a716  mov     rax, cs:qword_1401229D8
0x14004a71d  xor     edi, edi
0x14004a71f  cmp     rax, rsi
0x14004a722  jz      short loc_14004A731
0x14004a724  cmp     [rax+10h], r12d
0x14004a728  jnz     loc_14004A91E
0x14004a72e  mov     rdi, rax
0x14004a731  test    rdi, rdi
0x14004a734  jz      short loc_14004A768
0x14004a736  cmp     r14d, [rdi+10h]
0x14004a73a  jz      short loc_14004A7B5
0x14004a73c  lea     rdx, [rdi+694h]; Buf2
0x14004a743  mov     r8d, 10h; Size
0x14004a749  lea     rcx, [rbp+57h+Buf1+8]; Buf1
0x14004a74d  call    memcmp
0x14004a752  test    eax, eax
0x14004a754  jz      short loc_14004A7B5
0x14004a756  mov     eax, [rdi+690h]
0x14004a75c  test    al, 2
0x14004a75e  jnz     short loc_14004A766
0x14004a760  cmp     r14d, 1
0x14004a764  jz      short loc_14004A7B5
0x14004a766  xor     edi, edi
0x14004a768  movzx   edx, r15b; NewIrql
0x14004a76c  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004a773  call    cs:__imp_KeReleaseSpinLock
0x14004a77a  nop     dword ptr [rax+rax+00h]
0x14004a77f  jmp     loc_14004A818
0x14004a784  xor     r12d, r12d
0x14004a787  mov     rax, cs:qword_1401229D8
0x14004a78e  xor     edi, edi
0x14004a790  cmp     rax, rsi
0x14004a793  jz      short loc_14004A7A3
0x14004a795  cmp     [rax+10h], r12d
0x14004a799  ja      short loc_14004A7A0
0x14004a79b  mov     rax, [rax]
0x14004a79e  jmp     short loc_14004A790
0x14004a7a0  mov     rdi, rax
0x14004a7a3  test    rdi, rdi
0x14004a7a6  jz      short loc_14004A768
0x14004a7a8  mov     r12d, [rdi+10h]
0x14004a7ac  cmp     r14d, r12d
0x14004a7af  jnz     loc_14004A94E
0x14004a7b5  xor     esi, esi
0x14004a7b7  mov     [rbp+57h+CopyOnOpen], esi
0x14004a7ba  lock inc dword ptr [rdi+2Ch]
0x14004a7be  mov     rcx, [rbx+10h]
0x14004a7c2  movzx   edx, r15b; NewIrql
0x14004a7c6  mov     eax, [rdi+10h]
0x14004a7c9  mov     [rbp+57h+EffectiveOnly], 1
0x14004a7cd  mov     [rcx], eax
0x14004a7cf  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004a7d6  call    cs:__imp_KeReleaseSpinLock
0x14004a7dd  nop     dword ptr [rax+rax+00h]
0x14004a7e2  test    rdi, rdi
  ... truncated ...
```

# ndisNsiGetCompartmentInfo(_NM_REQUEST_GET_PARAMETER *)

- ea: `0x1400457d0`
- end: `0x140045f27`
- name: `?ndisNsiGetCompartmentInfo@@YAJPEAU_NM_REQUEST_GET_PARAMETER@@@Z`
- size: `1879`
- prototype: `__int64 __fastcall(struct _NM_REQUEST_GET_PARAMETER *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14001cf50`
- `0x14001d350`
- `0x1400457d0`
- `0x1400e62c0`
- `0x1400e6ae0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140045897`
- `ntoskrnl!KeGetCurrentIrql` at `0x140045901`
- `ntoskrnl!KeGetCurrentIrql` at `0x140045897`
- `ntoskrnl!KeGetCurrentIrql` at `0x140045901`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140045b19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140045b19`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400457ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400457ff`
- `ntoskrnl!ObfDereferenceObject` at `0x140045ea6`
- `ntoskrnl!ObfDereferenceObject` at `0x140045ea6`
- `ntoskrnl!KeSetEvent` at `0x140045ac4`
- `ntoskrnl!KeSetEvent` at `0x140045ac4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400459c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045adb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045c73`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045cd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045dfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400459c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045adb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045c73`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045cd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045dfe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004596d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400459d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140045a94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140045dcb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004596d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400459d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140045a94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140045dcb`
- `ntoskrnl!SeQueryInformationToken` at `0x140045ba2`
- `ntoskrnl!SeQueryInformationToken` at `0x140045bdb`
- `ntoskrnl!SeQueryInformationToken` at `0x140045ba2`
- `ntoskrnl!SeQueryInformationToken` at `0x140045bdb`
- `ntoskrnl!PsGetThreadProperty` at `0x14004586c`
- `ntoskrnl!PsGetThreadProperty` at `0x14004586c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140045e2c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140045e3d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140045e2c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140045e3d`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400458ba`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140045924`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400458ba`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140045924`
- `ntoskrnl!PsGetThreadSessionId` at `0x1400458d5`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004593f`
- `ntoskrnl!PsGetThreadSessionId` at `0x1400458d5`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004593f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140045bb3`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140045bec`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140045bb3`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140045bec`

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
                    if ( v10 < dword_14011C898 )
                    {
                      v42 = 0;
                      v43 = KeAcquireSpinLockRaiseToDpc(&qword_14011C8E0);
                      if ( v10 < dword_14011C898 )
                        v42 = *((_DWORD *)qword_14011C8E8 + 6 * v10);
                      KeReleaseSpinLock(&qword_14011C8E0, v43);
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
                    for ( i = qword_14011C9D8;
                          i != (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_14011C9D8;
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
                        v39 = qword_14011C9D8;
                        v38 = 0;
                        while ( v39 != (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_14011C9D8 )
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
                    v37 = qword_14011C9D8;
                    v38 = 0;
                    while ( v37 != (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_14011C9D8 )
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
0x1400457d0  push    rbp
0x1400457d2  push    rbx
0x1400457d3  push    rsi
0x1400457d4  push    rdi
0x1400457d5  lea     rbp, [rsp-3Fh]
0x1400457da  sub     rsp, 88h
0x1400457e1  mov     rbx, rcx
0x1400457e4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400457eb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400457f2  lea     rdi, WPP_7b6e8809435e3846b6104774dae7899f_Traceguids
0x1400457f9  jnz     loc_140045EDC
0x1400457ff  call    cs:__imp_KeEnterCriticalRegion
0x140045806  nop     dword ptr [rax+rax+00h]
0x14004580b  cmp     dword ptr [rbx+18h], 4
0x14004580f  jnz     loc_140045F09
0x140045815  cmp     dword ptr [rbx+30h], 0
0x140045819  jz      loc_140045F13
0x14004581f  cmp     qword ptr [rbx+28h], 0
0x140045824  jz      loc_140045F1D
0x14004582a  mov     rax, [rbx+10h]
0x14004582e  xorps   xmm0, xmm0
0x140045831  mov     rsi, gs:188h
0x14004583a  xor     r8d, r8d; Flags
0x14004583d  mov     [rsp+0A0h+var_20], r12
0x140045845  mov     edx, 6D43644Eh; Key
0x14004584a  mov     [rsp+0A0h+var_28], r13
0x14004584f  mov     rcx, rsi; Thread
0x140045852  mov     r12d, [rax]
0x140045855  xor     r13b, r13b
0x140045858  xor     eax, eax
0x14004585a  mov     [rsp+0A0h+var_30], r14
0x14004585f  mov     [rbp+57h+var_50], rax
0x140045863  mov     [rsp+0A0h+var_38], r15
0x140045868  movups  [rbp+57h+Buf1], xmm0
0x14004586c  call    cs:__imp_PsGetThreadProperty
0x140045873  nop     dword ptr [rax+rax+00h]
0x140045878  xor     r15d, r15d
0x14004587b  mov     rcx, rax; Object
0x14004587e  test    rax, rax
0x140045881  jnz     loc_140045E99
0x140045887  mov     byte ptr [rbp+57h+CopyOnOpen], r13b
0x14004588b  mov     [rbp+57h+EffectiveOnly], r13b
0x14004588f  mov     [rbp+57h+ImpersonationLevel], r15d
0x140045893  mov     [rbp+57h+TokenInformation], r15
0x140045897  call    cs:__imp_KeGetCurrentIrql
0x14004589e  nop     dword ptr [rax+rax+00h]
0x1400458a3  cmp     al, 2
0x1400458a5  jnb     loc_140045E2C
0x1400458ab  lea     r9, [rbp+57h+ImpersonationLevel]; ImpersonationLevel
0x1400458af  mov     rcx, rsi; Thread
0x1400458b2  lea     r8, [rbp+57h+EffectiveOnly]; EffectiveOnly
0x1400458b6  lea     rdx, [rbp+57h+CopyOnOpen]; CopyOnOpen
0x1400458ba  call    cs:__imp_PsReferenceImpersonationToken
0x1400458c1  nop     dword ptr [rax+rax+00h]
0x1400458c6  mov     r14, rax
0x1400458c9  test    rax, rax
0x1400458cc  jnz     loc_140045B96
0x1400458d2  mov     rcx, rsi
0x1400458d5  call    cs:__imp_PsGetThreadSessionId
0x1400458dc  nop     dword ptr [rax+rax+00h]
0x1400458e1  mov     edi, eax
0x1400458e3  cmp     edi, 0FFFFFFFFh
0x1400458e6  jnz     short loc_14004594D
0x1400458e8  mov     rsi, gs:188h
0x1400458f1  mov     byte ptr [rbp+57h+CopyOnOpen], r13b
0x1400458f5  mov     [rbp+57h+EffectiveOnly], r13b
0x1400458f9  mov     [rbp+57h+ImpersonationLevel], r15d
0x1400458fd  mov     [rbp+57h+TokenInformation], r15
0x140045901  call    cs:__imp_KeGetCurrentIrql
0x140045908  nop     dword ptr [rax+rax+00h]
0x14004590d  cmp     al, 2
0x14004590f  jnb     loc_140045E3D
0x140045915  lea     r9, [rbp+57h+ImpersonationLevel]; ImpersonationLevel
0x140045919  mov     rcx, rsi; Thread
0x14004591c  lea     r8, [rbp+57h+EffectiveOnly]; EffectiveOnly
0x140045920  lea     rdx, [rbp+57h+CopyOnOpen]; CopyOnOpen
0x140045924  call    cs:__imp_PsReferenceImpersonationToken
0x14004592b  nop     dword ptr [rax+rax+00h]
0x140045930  mov     r14, rax
0x140045933  test    rax, rax
0x140045936  jnz     loc_140045BCF
0x14004593c  mov     rcx, rsi
0x14004593f  call    cs:__imp_PsGetThreadSessionId
0x140045946  nop     dword ptr [rax+rax+00h]
0x14004594b  mov     edi, eax
0x14004594d  cmp     edi, cs:dword_14011C898
0x140045953  jb      loc_140045DC1
0x140045959  mov     r14d, 1
0x14004595f  mov     dword ptr [rbp+57h+Buf1+4], r14d
0x140045963  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004596a  mov     edi, r14d
0x14004596d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140045974  nop     dword ptr [rax+rax+00h]
0x140045979  mov     rcx, r15
0x14004597c  lea     rsi, qword_14011C9D8
0x140045983  movzx   r8d, al
0x140045987  mov     rax, cs:qword_14011C9D8
0x14004598e  cmp     rax, rsi
0x140045991  jz      short loc_14004599F
0x140045993  cmp     [rax+10h], edi
0x140045996  jnz     loc_140045C08
0x14004599c  mov     rcx, rax
0x14004599f  mov     rax, [rcx+694h]
0x1400459a6  movzx   edx, r8b; NewIrql
0x1400459aa  mov     qword ptr [rbp+57h+Buf1+8], rax
0x1400459ae  mov     rax, [rcx+69Ch]
0x1400459b5  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400459bc  mov     [rbp+57h+var_50], rax
0x1400459c0  call    cs:__imp_KeReleaseSpinLock
0x1400459c7  nop     dword ptr [rax+rax+00h]
0x1400459cc  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400459d3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400459da  nop     dword ptr [rax+rax+00h]
0x1400459df  mov     edx, [rbx+38h]
0x1400459e2  movzx   r15d, al
0x1400459e6  test    edx, edx
0x1400459e8  jz      loc_140045C16
0x1400459ee  sub     edx, 1
0x1400459f1  jz      loc_140045C84
0x1400459f7  cmp     edx, 1
0x1400459fa  jz      loc_140045C87
0x140045a00  mov     esi, 0C0000010h
0x140045a05  movzx   edx, al
0x140045a08  jmp     loc_140045AD4
0x140045a0d  mov     r12d, [rbx+30h]
0x140045a11  mov     r14d, [rbx+34h]
0x140045a15  test    r12d, r12d
0x140045a18  jle     short loc_140045A74
0x140045a1a  mov     rsi, rax
0x140045a1d  nop     dword ptr [rax]
0x140045a20  test    r13b, r13b
0x140045a23  jnz     short loc_140045A71
0x140045a25  cmp     r14d, 234h
0x140045a2c  ja      loc_140045B34
0x140045a32  jz      loc_140045D4E
0x140045a38  test    r14d, r14d
0x140045a3b  jz      loc_140045D3E
0x140045a41  cmp     r14d, 8
0x140045a45  jz      loc_140045D2E
0x140045a4b  cmp     r14d, 10h
0x140045a4f  jz      loc_140045D05
0x140045a55  cmp     r14d, 20h ; ' '
0x140045a59  jz      loc_140045DB1
0x140045a5f  cmp     r14d, 30h ; '0'
0x140045a63  jz      loc_140045E89
0x140045a69  mov     r13b, 1
0x140045a6c  test    r12d, r12d
0x140045a6f  jg      short loc_140045A20
0x140045a71  mov     esi, [rbp+57h+CopyOnOpen]
0x140045a74  sub     r14d, [rbx+34h]
0x140045a78  mov     [rbx+30h], r14d
0x140045a7c  jnz     short loc_140045A83
0x140045a7e  mov     esi, 0C000000Dh
0x140045a83  movzx   r13d, [rbp+57h+EffectiveOnly]
0x140045a88  test    r13b, r13b
0x140045a8b  jz      short loc_140045AE7
0x140045a8d  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140045a94  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140045a9b  nop     dword ptr [rax+rax+00h]
0x140045aa0  movzx   r14d, al
0x140045aa4  mov     eax, 0FFFFFFFFh
0x140045aa9  lock xadd [rdi+2Ch], eax
0x140045aae  cmp     eax, 1
0x140045ab1  jnz     short loc_140045AD0
0x140045ab3  mov     rcx, [rdi+6B0h]; Event
0x140045aba  test    rcx, rcx
0x140045abd  jz      short loc_140045AD0
0x140045abf  xor     r8d, r8d; Wait
0x140045ac2  xor     edx, edx; Increment
0x140045ac4  call    cs:__imp_KeSetEvent
0x140045acb  nop     dword ptr [rax+rax+00h]
0x140045ad0  movzx   edx, r14b; NewIrql
0x140045ad4  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140045adb  call    cs:__imp_KeReleaseSpinLock
0x140045ae2  nop     dword ptr [rax+rax+00h]
0x140045ae7  mov     r14, [rsp+0A0h+var_30]
0x140045aec  lea     rdi, WPP_7b6e8809435e3846b6104774dae7899f_Traceguids
0x140045af3  mov     r13, [rsp+0A0h+var_28]
0x140045af8  mov     r12, [rsp+0A0h+var_20]
0x140045b00  mov     r15, [rsp+0A0h+var_38]
0x140045b05  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140045b0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140045b13  jnz     loc_140045D80
0x140045b19  call    cs:__imp_KeLeaveCriticalRegion
0x140045b20  nop     dword ptr [rax+rax+00h]
0x140045b25  mov     eax, esi
0x140045b27  add     rsp, 88h
0x140045b2e  pop     rdi
0x140045b2f  pop     rsi
0x140045b30  pop     rbx
0x140045b31  pop     rbp
0x140045b32  retn
0x140045b34  mov     eax, r14d
0x140045b37  sub     eax, 438h
0x140045b3c  jz      loc_140045D6E
0x140045b42  sub     eax, 10h
0x140045b45  jz      loc_140045D5E
0x140045b4b  sub     eax, 208h
0x140045b50  jnz     loc_140045EC0
0x140045b56  mov     eax, 4
0x140045b5b  mov     r15d, 654h
0x140045b61  cmp     r12d, eax
0x140045b64  jb      loc_140045A69
0x140045b6a  mov     edx, r14d
0x140045b6d  mov     rcx, rsi; void *
0x140045b70  add     rdx, 40h ; '@'
0x140045b74  mov     r8d, eax; Size
0x140045b77  add     rdx, rdi; Src
0x140045b7a  call    memmove
0x140045b7f  mov     eax, r15d
0x140045b82  sub     eax, r14d
0x140045b85  sub     r14d, r15d
0x140045b88  add     rsi, rax
0x140045b8b  add     r12d, r14d
0x140045b8e  mov     r14d, r15d
0x140045b91  jmp     loc_140045A6C
0x140045b96  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140045b9a  mov     edx, 0Ch; TokenInformationClass
0x140045b9f  mov     rcx, r14; Token
0x140045ba2  call    cs:__imp_SeQueryInformationToken
0x140045ba9  nop     dword ptr [rax+rax+00h]
0x140045bae  mov     rcx, r14; ImpersonationToken
0x140045bb1  mov     edi, eax
0x140045bb3  call    cs:__imp_PsDereferenceImpersonationToken
0x140045bba  nop     dword ptr [rax+rax+00h]
0x140045bbf  test    edi, edi
0x140045bc1  js      loc_1400458D2
0x140045bc7  mov     edi, dword ptr [rbp+57h+TokenInformation]
0x140045bca  jmp     loc_1400458E3
0x140045bcf  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140045bd3  mov     edx, 0Ch; TokenInformationClass
0x140045bd8  mov     rcx, r14; Token
0x140045bdb  call    cs:__imp_SeQueryInformationToken
0x140045be2  nop     dword ptr [rax+rax+00h]
0x140045be7  mov     rcx, r14; ImpersonationToken
0x140045bea  mov     edi, eax
0x140045bec  call    cs:__imp_PsDereferenceImpersonationToken
0x140045bf3  nop     dword ptr [rax+rax+00h]
0x140045bf8  test    edi, edi
0x140045bfa  js      loc_14004593C
0x140045c00  mov     edi, dword ptr [rbp+57h+TokenInformation]
0x140045c03  jmp     loc_14004594D
0x140045c08  ja      loc_14004599F
0x140045c0e  mov     rax, [rax]
0x140045c11  jmp     loc_14004598E
0x140045c16  mov     rax, cs:qword_14011C9D8
0x140045c1d  xor     edi, edi
0x140045c1f  cmp     rax, rsi
0x140045c22  jz      short loc_140045C31
0x140045c24  cmp     [rax+10h], r12d
0x140045c28  jnz     loc_140045E1E
0x140045c2e  mov     rdi, rax
0x140045c31  test    rdi, rdi
0x140045c34  jz      short loc_140045C68
0x140045c36  cmp     r14d, [rdi+10h]
0x140045c3a  jz      short loc_140045CB5
0x140045c3c  lea     rdx, [rdi+694h]; Buf2
0x140045c43  mov     r8d, 10h; Size
0x140045c49  lea     rcx, [rbp+57h+Buf1+8]; Buf1
0x140045c4d  call    memcmp
0x140045c52  test    eax, eax
0x140045c54  jz      short loc_140045CB5
0x140045c56  mov     eax, [rdi+690h]
0x140045c5c  test    al, 2
0x140045c5e  jnz     short loc_140045C66
0x140045c60  cmp     r14d, 1
0x140045c64  jz      short loc_140045CB5
0x140045c66  xor     edi, edi
0x140045c68  movzx   edx, r15b; NewIrql
0x140045c6c  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140045c73  call    cs:__imp_KeReleaseSpinLock
0x140045c7a  nop     dword ptr [rax+rax+00h]
0x140045c7f  jmp     loc_140045D18
0x140045c84  xor     r12d, r12d
0x140045c87  mov     rax, cs:qword_14011C9D8
0x140045c8e  xor     edi, edi
0x140045c90  cmp     rax, rsi
0x140045c93  jz      short loc_140045CA3
0x140045c95  cmp     [rax+10h], r12d
0x140045c99  ja      short loc_140045CA0
0x140045c9b  mov     rax, [rax]
0x140045c9e  jmp     short loc_140045C90
0x140045ca0  mov     rdi, rax
0x140045ca3  test    rdi, rdi
0x140045ca6  jz      short loc_140045C68
0x140045ca8  mov     r12d, [rdi+10h]
0x140045cac  cmp     r14d, r12d
0x140045caf  jnz     loc_140045E4E
0x140045cb5  xor     esi, esi
0x140045cb7  mov     [rbp+57h+CopyOnOpen], esi
0x140045cba  lock inc dword ptr [rdi+2Ch]
0x140045cbe  mov     rcx, [rbx+10h]
0x140045cc2  movzx   edx, r15b; NewIrql
0x140045cc6  mov     eax, [rdi+10h]
0x140045cc9  mov     [rbp+57h+EffectiveOnly], 1
0x140045ccd  mov     [rcx], eax
0x140045ccf  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140045cd6  call    cs:__imp_KeReleaseSpinLock
0x140045cdd  nop     dword ptr [rax+rax+00h]
0x140045ce2  test    rdi, rdi
  ... truncated ...
```

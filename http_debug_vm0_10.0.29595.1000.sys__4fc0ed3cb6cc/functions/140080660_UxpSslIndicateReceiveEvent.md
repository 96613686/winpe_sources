# UxpSslIndicateReceiveEvent

- ea: `0x140080660`
- end: `0x140080f83`
- name: `UxpSslIndicateReceiveEvent`
- size: `2339`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007f470`
- `0x14007fb50`

## callees

- `0x14000a350`
- `0x140049d08`
- `0x1400513f0`
- `0x14005dfd0`
- `0x14006e4ec`
- `0x14006f4a0`
- `0x14006f9e0`
- `0x140080660`
- `0x1400a9b00`
- `0x1400ee29c`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`
- `0x1401da2b4`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14008078c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14008078c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140080922`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140080a6e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140080922`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140080a6e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080b44`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080bed`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080b44`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080bed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008070b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008070b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080e7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080e7f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400806ff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400806ff`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080983`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080cd5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080f54`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080983`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080cd5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080f54`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008096e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140080cc0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140080f3f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008096e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140080cc0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140080f3f`

## pseudocode

```c
__int64 __fastcall UxpSslIndicateReceiveEvent(__int64 a1)
{
  _QWORD *v2; // rsi
  __int64 v3; // rax
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx
  unsigned int v6; // r15d
  __int64 v7; // rcx
  unsigned int v8; // ecx
  int LockArray_high; // r15d
  unsigned __int64 v10; // rdi
  _OWORD *v11; // rax
  _OWORD *v12; // r8
  int v13; // eax
  unsigned int v14; // eax
  int v15; // edx
  bool v16; // r13
  int v17; // edi
  int v18; // eax
  volatile signed __int32 *v19; // rsi
  int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // r8
  unsigned __int64 v23; // rdi
  char v24; // di
  unsigned __int64 v26; // rdi
  __int64 v27; // rdi
  USHORT v28; // ax
  __int64 v29; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v31; // rcx
  int v32; // r13d
  _QWORD *v33; // rax
  __int64 v34; // rcx
  unsigned int v35; // [rsp+40h] [rbp-49h] BYREF
  _OWORD *v36; // [rsp+48h] [rbp-41h] BYREF
  _DWORD v37[24]; // [rsp+50h] [rbp-39h] BYREF

  v35 = 0;
  v36 = 0;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 199, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1);
  v2 = *(_QWORD **)(a1 + 1480);
  v3 = *v2;
  if ( *(_QWORD **)(*v2 + 8LL) != v2 )
    goto LABEL_75;
  v4 = (_QWORD *)v2[1];
  if ( (_QWORD *)*v4 != v2 )
    goto LABEL_75;
  *v4 = v3;
  v5 = v2 - 3;
  *(_QWORD *)(v3 + 8) = v4;
  v2[1] = v2;
  *v2 = v2;
  v6 = 0;
  *(_BYTE *)(a1 + 1362) = 0;
  ExReleasePushLockExclusiveEx(a1 + 208, 0);
  KeLeaveCriticalRegion();
  v7 = *(_QWORD *)(a1 + 1696);
  if ( (*(_BYTE *)(v7 + 1762) & 8) != 0
    && (!*(_QWORD *)(v7 + 1776)
     || (unsigned __int8)UlEtwEvaluateFilter(
                           v7,
                           a1 + 88,
                           a1 + 116,
                           0,
                           *(_QWORD *)(a1 + 1656),
                           *(unsigned __int16 *)(a1 + 1648),
                           0,
                           0,
                           v35)) )
  {
    McTemplateK0qp_EtwWriteTransfer(
      *(_QWORD *)(a1 + 1696) + 1688LL,
      HTTP_EVENT_SSL_DELIVER_STREAM_DATA,
      a1 + 72,
      *((unsigned int *)v5 + 14),
      a1);
  }
  v8 = *((_DWORD *)v5 + 14);
  v35 = v8;
  if ( *((_DWORD *)v5 + 14) )
  {
    v36 = 0;
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    if ( UxDebugDisableLookaside )
    {
      v11 = (_OWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0720)(
                        (unsigned int)dword_1401A0708,
                        qword_1401A0710,
                        (unsigned int)dword_1401A0718,
                        0);
    }
    else if ( UxCompactMode )
    {
      v29 = qword_1401A0700;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      v11 = (_OWORD *)PplAllocateFromLookasideListProcessor(v29, CurrentNodeNumber);
    }
    else
    {
      v10 = qword_1401A0700 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
      if ( !*(_BYTE *)(v10 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0700, v10 + 64);
      v11 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v10 + 64));
    }
    v12 = v11;
    if ( !v11 )
    {
      v24 = 0;
      v6 = -1073741670;
      goto LABEL_48;
    }
    *v11 = 0;
    v11[1] = 0;
    v11[2] = 0;
    *(_DWORD *)v11 = LockArray_high;
    *((_DWORD *)v11 + 4) = 1229089877;
    *((_QWORD *)v11 + 3) = v5[6];
    v13 = _InterlockedIncrement((volatile signed __int32 *)v5 + 5);
    if ( UxDebugCheckRefcount && v13 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v5 + 20, 0x46u, v13);
    *((_QWORD *)v12 + 4) = v5;
    v36 = v12;
    if ( (BYTE10(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qqqi(1297, 200, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, v2 - 3, v5[5], v12);
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, _OWORD **, _QWORD, unsigned int *))(*(_QWORD *)(a1 + 32) + 48LL))(
            *(_QWORD *)(a1 + 24),
            0x4000,
            &v36,
            *((unsigned int *)v5 + 14),
            &v35);
    v8 = v35;
    v6 = v14;
  }
  v15 = *((_DWORD *)v5 + 14);
  v16 = v8 == v15;
  if ( v8 )
  {
    v5[6] += v8;
    v15 -= v8;
    *((_DWORD *)v5 + 14) = v15;
  }
  if ( !v15 )
  {
    v17 = *((_DWORD *)v5 + 15);
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qD(1041, 16, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, *((_DWORD *)v5 + 15));
    *(_DWORD *)(a1 + 1352) += v17;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 17, WPP_6033a49e77e7395416619077875677ff_Traceguids);
    v18 = _InterlockedDecrement((volatile signed __int32 *)v5 + 5);
    if ( UxDebugCheckRefcount && v18 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v5 + 20, 1u, v18);
    if ( v18 )
      goto LABEL_45;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qq(1041, 193, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, v2 - 3);
    v19 = (volatile signed __int32 *)v5[5];
    if ( !v19 )
    {
LABEL_41:
      *((_DWORD *)v5 + 4) = 1685280885;
      if ( v5 == (_QWORD *)(a1 + 1840) )
      {
        *(_QWORD *)(a1 + 1496) = v5;
      }
      else if ( UxDebugDisableLookaside )
      {
        memset(v37, 0, sizeof(v37));
        v37[10] = dword_1401A06E8;
        ((void (__fastcall *)(_QWORD *, _DWORD *))off_1401A06F8)(v5, v37);
      }
      else if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A06D0, v5);
      }
      else
      {
        v26 = qword_1401A06D0 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v5 + 1) << 7);
        if ( !*(_BYTE *)(v26 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A06D0, v26 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v26 + 64), v5);
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 194, WPP_6033a49e77e7395416619077875677ff_Traceguids);
LABEL_45:
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(a1 + 208, 0);
      goto LABEL_46;
    }
    v20 = _InterlockedDecrement(v19 + 5);
    if ( UxDebugCheckRefcount && v20 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v19 + 5), 0x46u, v20);
    if ( v20 )
    {
LABEL_40:
      v5[5] = 0;
      goto LABEL_41;
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_q(1041, 10, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids, v19);
    v21 = *((_DWORD *)v19 + 30);
    *((_DWORD *)v19 + 4) = 1819498613;
    switch ( v21 )
    {
      case 0u:
        if ( UxDebugDisableLookaside )
        {
          memset(v37, 0, sizeof(v37));
          v37[10] = dword_1401A0628;
          ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0638)(v19, v37);
        }
        else
        {
          if ( !UxCompactMode )
          {
            v22 = qword_1401A0610;
            v23 = qword_1401A0610 + ((unsigned __int64)(unsigned int)(*v19 + 1) << 7);
            if ( *(_BYTE *)(v23 + 176) )
            {
LABEL_37:
              ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v23 + 64), (PVOID)v19);
              goto LABEL_38;
            }
LABEL_68:
            PplpLazyInitializeLookasideList(v22, v23 + 64);
            goto LABEL_37;
          }
          v27 = qword_1401A0610;
          v28 = KeGetCurrentNodeNumber();
          PplFreeToLookasideListProcessor(v27, v19, v28);
        }
        goto LABEL_38;
      case 1u:
        if ( UxDebugDisableLookaside )
        {
          memset(v37, 0, sizeof(v37));
          v37[10] = dword_1401A0658;
          ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0668)(v19, v37);
          goto LABEL_38;
        }
        v31 = qword_1401A0640;
        break;
      case 2u:
        if ( UxDebugDisableLookaside )
        {
          memset(v37, 0, sizeof(v37));
          v37[10] = dword_1401A0688;
          ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0698)(v19, v37);
        }
        else
        {
          if ( !UxCompactMode )
          {
            v22 = qword_1401A0670;
            v23 = qword_1401A0670 + ((unsigned __int64)(unsigned int)(*v19 + 1) << 7);
            if ( *(_BYTE *)(v23 + 176) )
              goto LABEL_37;
            goto LABEL_68;
          }
          PnlFreeToLookasideList(qword_1401A0670, v19);
        }
LABEL_38:
        if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
          WPP_SF_(1041, 11, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids);
        goto LABEL_40;
      case 3u:
        if ( UxDebugDisableLookaside )
        {
          memset(v37, 0, sizeof(v37));
          v37[10] = dword_1401A06B8;
          ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A06C8)(v19, v37);
          goto LABEL_38;
        }
        v31 = qword_1401A06A0;
        break;
      default:
        ExFreePoolWithTag((PVOID)v19, 0);
        goto LABEL_38;
    }
    if ( UxCompactMode )
      PnlFreeToLookasideList(v31, v19);
    else
      PplFreeToLookasideListProcessor(v31, v19, *(unsigned int *)v19);
    goto LABEL_38;
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 208, 0);
  v33 = (_QWORD *)(a1 + 1480);
  v34 = *(_QWORD *)(a1 + 1480);
  if ( *(_QWORD *)(v34 + 8) != a1 + 1480 )
LABEL_75:
    __fastfail(3u);
  *v2 = v34;
  v2[1] = v33;
  *(_QWORD *)(v34 + 8) = v2;
  *v33 = v2;
LABEL_46:
  v5 = 0;
  v24 = 1;
  if ( v16 )
    *(_BYTE *)(a1 + 1362) = 1;
LABEL_48:
  if ( v36 )
  {
    UxSslFreeBufferIndication(a1);
    v36 = 0;
  }
  if ( v5 )
  {
    v32 = _InterlockedDecrement((volatile signed __int32 *)v5 + 5);
    if ( UxDebugCheckRefcount && v32 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v5 + 20, 1u, v32);
    if ( !v32 )
      UxpSslFreeDataIndication(a1, v5);
  }
  if ( !v24 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 208, 0);
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 201, WPP_6033a49e77e7395416619077875677ff_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x140080660  push    rbp
0x140080662  push    rsi
0x140080663  push    rdi
0x140080664  push    r14
0x140080666  lea     rbp, [rsp-3Fh]
0x14008066b  sub     rsp, 0C8h
0x140080672  mov     rax, cs:__security_cookie
0x140080679  xor     rax, rsp
0x14008067c  mov     [rbp+57h+var_30], rax
0x140080680  xor     edi, edi
0x140080682  mov     r14, rcx
0x140080685  mov     [rbp+57h+var_A0], edi
0x140080688  mov     [rbp+57h+var_98], rdi
0x14008068c  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140080693  jnz     loc_140080D08
0x140080699  mov     rsi, [r14+5C8h]
0x1400806a0  mov     [rsp+0E0h+arg_8], rbx
0x1400806a8  mov     [rsp+0E0h+arg_10], r12
0x1400806b0  mov     [rsp+0E0h+arg_18], r13
0x1400806b8  mov     rax, [rsi]
0x1400806bb  mov     [rsp+0E0h+var_20], r15
0x1400806c3  cmp     [rax+8], rsi
0x1400806c7  jnz     loc_140080B64
0x1400806cd  mov     rcx, [rsi+8]
0x1400806d1  cmp     [rcx], rsi
0x1400806d4  jnz     loc_140080B64
0x1400806da  mov     [rcx], rax
0x1400806dd  lea     rbx, [rsi-18h]
0x1400806e1  mov     [rax+8], rcx
0x1400806e5  xor     edx, edx
0x1400806e7  mov     [rsi+8], rsi
0x1400806eb  lea     rcx, [r14+0D0h]
0x1400806f2  mov     [rsi], rsi
0x1400806f5  mov     r15d, edi
0x1400806f8  mov     [r14+552h], dil
0x1400806ff  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140080706  nop     dword ptr [rax+rax+00h]
0x14008070b  call    cs:__imp_KeLeaveCriticalRegion
0x140080712  nop     dword ptr [rax+rax+00h]
0x140080717  mov     rcx, [r14+6A0h]
0x14008071e  test    byte ptr [rcx+6E2h], 8
0x140080725  jnz     loc_140080D26
0x14008072b  mov     ecx, [rbx+38h]
0x14008072e  mov     r13d, 0FFFFFFFFh
0x140080734  mov     [rbp+57h+var_A0], ecx
0x140080737  cmp     [rbx+38h], edi
0x14008073a  jz      loc_140080822
0x140080740  mov     [rbp+57h+var_98], rdi
0x140080744  mov     r15d, gs:1A4h
0x14008074d  cmp     cs:UxDebugDisableLookaside, dil
0x140080754  jnz     loc_140080B15
0x14008075a  cmp     cs:UxCompactMode, dil
0x140080761  jnz     loc_140080BE6
0x140080767  mov     r8, cs:qword_1401A0700
0x14008076e  lea     edi, [r15+1]
0x140080772  shl     rdi, 7
0x140080776  add     rdi, r8
0x140080779  movzx   eax, byte ptr [rdi+0B0h]
0x140080780  test    al, al
0x140080782  jz      loc_140080C09
0x140080788  lea     rcx, [rdi+40h]; Lookaside
0x14008078c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140080793  nop     dword ptr [rax+rax+00h]
0x140080798  mov     r8, rax
0x14008079b  test    rax, rax
0x14008079e  jz      loc_140080B93
0x1400807a4  xorps   xmm0, xmm0
0x1400807a7  movaps  xmmword ptr [rax], xmm0
0x1400807aa  movaps  xmmword ptr [rax+10h], xmm0
0x1400807ae  movaps  xmmword ptr [rax+20h], xmm0
0x1400807b2  mov     [rax], r15d
0x1400807b5  mov     dword ptr [rax+10h], 49426C55h
0x1400807bc  lea     rdx, [rbx+14h]; BugCheckParameter2
0x1400807c0  mov     rax, [rbx+30h]
0x1400807c4  mov     [r8+18h], rax
0x1400807c8  mov     eax, 1
0x1400807cd  lock xadd [rdx], eax
0x1400807d1  inc     eax
0x1400807d3  cmp     cs:UxDebugCheckRefcount, 0
0x1400807da  jnz     loc_140080A0F
0x1400807e0  mov     [r8+20h], rbx
0x1400807e4  mov     [rbp+57h+var_98], r8
0x1400807e8  test    byte ptr cs:xmmword_1401A2CA0+0Ah, 2
0x1400807ef  jnz     loc_140080D71
0x1400807f5  mov     rax, [r14+20h]
0x1400807f9  lea     rcx, [rbp+57h+var_A0]
0x1400807fd  mov     r9d, [rbx+38h]
0x140080801  lea     r8, [rbp+57h+var_98]
0x140080805  mov     [rsp+0E0h+var_C0], rcx
0x14008080a  mov     edx, 4000h
0x14008080f  mov     rcx, [r14+18h]
0x140080813  mov     rax, [rax+30h]
0x140080817  call    _guard_dispatch_icall
0x14008081c  mov     ecx, [rbp+57h+var_A0]
0x14008081f  mov     r15d, eax
0x140080822  mov     edx, [rbx+38h]
0x140080825  cmp     ecx, edx
0x140080827  setz    r13b
0x14008082b  test    ecx, ecx
0x14008082d  jz      short loc_14008083A
0x14008082f  mov     eax, ecx
0x140080831  add     [rbx+30h], rax
0x140080835  sub     edx, ecx
0x140080837  mov     [rbx+38h], edx
0x14008083a  test    edx, edx
0x14008083c  jnz     loc_140080CC0
0x140080842  mov     edi, [rbx+3Ch]
0x140080845  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14008084c  jnz     loc_140080BA1
0x140080852  add     [r14+548h], edi
0x140080859  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140080860  jnz     loc_140080DA2
0x140080866  mov     edi, 0FFFFFFFFh
0x14008086b  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14008086f  mov     eax, edi
0x140080871  lock xadd [rdx], eax
0x140080875  dec     eax
0x140080877  cmp     cs:UxDebugCheckRefcount, 0
0x14008087e  jnz     loc_140080ADD
0x140080884  test    eax, eax
0x140080886  jnz     loc_14008096E
0x14008088c  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140080893  jnz     loc_140080BC3
0x140080899  mov     rsi, [rbx+28h]
0x14008089d  test    rsi, rsi
0x1400808a0  jz      loc_140080943
0x1400808a6  lea     rdx, [rsi+14h]; BugCheckParameter2
0x1400808aa  mov     eax, edi
0x1400808ac  lock xadd [rdx], eax
0x1400808b0  dec     eax
0x1400808b2  cmp     cs:UxDebugCheckRefcount, 0
0x1400808b9  jnz     loc_140080AF9
0x1400808bf  test    eax, eax
0x1400808c1  jnz     short loc_14008093B
0x1400808c3  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400808ca  jnz     loc_140080DBD
0x1400808d0  mov     eax, [rsi+78h]
0x1400808d3  mov     dword ptr [rsi+10h], 6C735875h
0x1400808da  test    eax, eax
0x1400808dc  jnz     loc_140080A7F
0x1400808e2  cmp     cs:UxDebugDisableLookaside, al
0x1400808e8  jnz     loc_140080DDB
0x1400808ee  cmp     cs:UxCompactMode, al
0x1400808f4  jnz     loc_140080B3D
0x1400808fa  mov     edi, [rsi]
0x1400808fc  mov     r8, cs:qword_1401A0610
0x140080903  inc     edi
0x140080905  shl     rdi, 7
0x140080909  add     rdi, r8
0x14008090c  movzx   eax, byte ptr [rdi+0B0h]
0x140080913  test    al, al
0x140080915  jz      loc_140080ACC
0x14008091b  mov     rdx, rsi; Entry
0x14008091e  lea     rcx, [rdi+40h]; Lookaside
0x140080922  call    cs:__imp_ExFreeToLookasideListEx
0x140080929  nop     dword ptr [rax+rax+00h]
0x14008092e  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140080935  jnz     loc_140080EC2
0x14008093b  mov     qword ptr [rbx+28h], 0
0x140080943  lea     rax, [r14+730h]
0x14008094a  mov     dword ptr [rbx+10h], 64735875h
0x140080951  cmp     rbx, rax
0x140080954  jnz     loc_140080A2C
0x14008095a  mov     [r14+5D8h], rbx
0x140080961  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140080968  jnz     loc_140080F0F
0x14008096e  call    cs:__imp_KeEnterCriticalRegion
0x140080975  nop     dword ptr [rax+rax+00h]
0x14008097a  xor     edx, edx
0x14008097c  lea     rcx, [r14+0D0h]
0x140080983  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14008098a  nop     dword ptr [rax+rax+00h]
0x14008098f  xor     ebx, ebx
0x140080991  mov     dil, 1
0x140080994  test    r13b, r13b
0x140080997  mov     r13d, 0FFFFFFFFh
0x14008099d  jz      short loc_1400809A6
0x14008099f  mov     [r14+552h], dil
0x1400809a6  mov     rdx, [rbp+57h+var_98]
0x1400809aa  test    rdx, rdx
0x1400809ad  jnz     loc_140080F2A
0x1400809b3  test    rbx, rbx
0x1400809b6  jnz     loc_140080C78
0x1400809bc  test    dil, dil
0x1400809bf  jz      loc_140080F3F
0x1400809c5  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400809cc  jnz     loc_140080F65
0x1400809d2  mov     r13, [rsp+0E0h+arg_18]
0x1400809da  mov     eax, r15d
0x1400809dd  mov     r15, [rsp+0E0h+var_20]
0x1400809e5  mov     r12, [rsp+0E0h+arg_10]
0x1400809ed  mov     rbx, [rsp+0E0h+arg_8]
0x1400809f5  mov     rcx, [rbp+57h+var_30]
0x1400809f9  xor     rcx, rsp; StackCookie
0x1400809fc  call    __security_check_cookie
0x140080a01  add     rsp, 0C8h
0x140080a08  pop     r14
0x140080a0a  pop     rdi
0x140080a0b  pop     rsi
0x140080a0c  pop     rbp
0x140080a0d  retn
0x140080a0f  cmp     eax, r13d
0x140080a12  jg      loc_1400807E0
0x140080a18  movsxd  r9, eax; BugCheckParameter4
0x140080a1b  mov     ecx, 3; BugCheckParameter1
0x140080a20  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x140080a26  call    UlBugCheckEx
0x140080a2c  cmp     cs:UxDebugDisableLookaside, 0
0x140080a33  jnz     loc_140080EDD
0x140080a39  cmp     cs:UxCompactMode, 0
0x140080a40  jnz     loc_140080B6B
0x140080a46  mov     edi, [rbx]
0x140080a48  mov     r8, cs:qword_1401A06D0
0x140080a4f  inc     edi
0x140080a51  shl     rdi, 7
0x140080a55  add     rdi, r8
0x140080a58  movzx   eax, byte ptr [rdi+0B0h]
0x140080a5f  test    al, al
0x140080a61  jz      loc_140080C67
0x140080a67  mov     rdx, rbx; Entry
0x140080a6a  lea     rcx, [rdi+40h]; Lookaside
0x140080a6e  call    cs:__imp_ExFreeToLookasideListEx
0x140080a75  nop     dword ptr [rax+rax+00h]
0x140080a7a  jmp     loc_140080961
0x140080a7f  cmp     eax, 1
0x140080a82  jz      loc_140080C1A
0x140080a88  cmp     eax, 2
0x140080a8b  jnz     loc_140080E71
0x140080a91  cmp     cs:UxDebugDisableLookaside, 0
0x140080a98  jnz     loc_140080E3F
0x140080a9e  cmp     cs:UxCompactMode, 0
0x140080aa5  jnz     loc_140080B7F
0x140080aab  mov     edi, [rsi]
0x140080aad  mov     r8, cs:qword_1401A0670
0x140080ab4  inc     edi
0x140080ab6  shl     rdi, 7
0x140080aba  add     rdi, r8
0x140080abd  movzx   eax, byte ptr [rdi+0B0h]
0x140080ac4  test    al, al
0x140080ac6  jnz     loc_14008091B
0x140080acc  lea     rdx, [rdi+40h]
0x140080ad0  mov     rcx, r8
0x140080ad3  call    PplpLazyInitializeLookasideList
0x140080ad8  jmp     loc_14008091B
0x140080add  cmp     eax, edi
0x140080adf  jg      loc_140080884
0x140080ae5  movsxd  r9, eax; BugCheckParameter4
0x140080ae8  mov     ecx, 3; BugCheckParameter1
0x140080aed  mov     r8d, 1; BugCheckParameter3
0x140080af3  call    UlBugCheckEx
0x140080af9  cmp     eax, edi
0x140080afb  jg      loc_1400808BF
0x140080b01  movsxd  r9, eax; BugCheckParameter4
0x140080b04  mov     ecx, 3; BugCheckParameter1
0x140080b09  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x140080b0f  call    UlBugCheckEx
0x140080b15  mov     rax, cs:off_1401A0720
0x140080b1c  xor     r9d, r9d
0x140080b1f  mov     r8d, cs:dword_1401A0718
0x140080b26  mov     rdx, cs:qword_1401A0710
0x140080b2d  mov     ecx, cs:dword_1401A0708
0x140080b33  call    _guard_dispatch_icall
0x140080b38  jmp     loc_140080798
0x140080b3d  mov     rdi, cs:qword_1401A0610
0x140080b44  call    cs:__imp_KeGetCurrentNodeNumber
0x140080b4b  nop     dword ptr [rax+rax+00h]
0x140080b50  movzx   r8d, ax
0x140080b54  mov     rdx, rsi
0x140080b57  mov     rcx, rdi
0x140080b5a  call    PplFreeToLookasideListProcessor
0x140080b5f  jmp     loc_14008092E
0x140080b64  mov     ecx, 3
0x140080b69  int     29h; Win8: RtlFailFast(ecx)
0x140080b6b  mov     rcx, cs:qword_1401A06D0
0x140080b72  mov     rdx, rbx
0x140080b75  call    PnlFreeToLookasideList
0x140080b7a  jmp     loc_140080961
0x140080b7f  mov     rcx, cs:qword_1401A0670
0x140080b86  mov     rdx, rsi
0x140080b89  call    PnlFreeToLookasideList
0x140080b8e  jmp     loc_14008092E
0x140080b93  xor     dil, dil
0x140080b96  mov     r15d, 0C000009Ah
0x140080b9c  jmp     loc_1400809A6
0x140080ba1  mov     edx, 10h
0x140080ba6  mov     dword ptr [rsp+0E0h+var_C0], edi
0x140080baa  mov     ecx, 411h
0x140080baf  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x140080bb6  mov     r9, r14
0x140080bb9  call    WPP_SF_qD
0x140080bbe  jmp     loc_140080852
0x140080bc3  mov     edx, 0C1h
0x140080bc8  mov     [rsp+0E0h+var_C0], rbx
0x140080bcd  mov     ecx, 411h
0x140080bd2  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x140080bd9  mov     r9, r14
0x140080bdc  call    WPP_SF_qq
0x140080be1  jmp     loc_140080899
0x140080be6  mov     rdi, cs:qword_1401A0700
0x140080bed  call    cs:__imp_KeGetCurrentNodeNumber
  ... truncated ...
```

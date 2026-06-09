# UxpSslIndicateReceiveEvent

- ea: `0x140080680`
- end: `0x140080fa3`
- name: `UxpSslIndicateReceiveEvent`
- size: `2339`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007f490`
- `0x14007fb70`

## callees

- `0x14000a350`
- `0x140049d28`
- `0x140051410`
- `0x14005dff0`
- `0x14006e50c`
- `0x14006f4c0`
- `0x14006fa00`
- `0x140080680`
- `0x1400a9b20`
- `0x1400ee26c`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`
- `0x1401da2b4`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400807ac`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400807ac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140080942`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140080a8e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140080942`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140080a8e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080b64`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080c0d`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080b64`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080c0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008072b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008072b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080e9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080e9f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14008071f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14008071f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400809a3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080cf5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080f74`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400809a3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080cf5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140080f74`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008098e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140080ce0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140080f5f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008098e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140080ce0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140080f5f`

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
0x140080680  push    rbp
0x140080682  push    rsi
0x140080683  push    rdi
0x140080684  push    r14
0x140080686  lea     rbp, [rsp-3Fh]
0x14008068b  sub     rsp, 0C8h
0x140080692  mov     rax, cs:__security_cookie
0x140080699  xor     rax, rsp
0x14008069c  mov     [rbp+57h+var_30], rax
0x1400806a0  xor     edi, edi
0x1400806a2  mov     r14, rcx
0x1400806a5  mov     [rbp+57h+var_A0], edi
0x1400806a8  mov     [rbp+57h+var_98], rdi
0x1400806ac  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400806b3  jnz     loc_140080D28
0x1400806b9  mov     rsi, [r14+5C8h]
0x1400806c0  mov     [rsp+0E0h+arg_8], rbx
0x1400806c8  mov     [rsp+0E0h+arg_10], r12
0x1400806d0  mov     [rsp+0E0h+arg_18], r13
0x1400806d8  mov     rax, [rsi]
0x1400806db  mov     [rsp+0E0h+var_20], r15
0x1400806e3  cmp     [rax+8], rsi
0x1400806e7  jnz     loc_140080B84
0x1400806ed  mov     rcx, [rsi+8]
0x1400806f1  cmp     [rcx], rsi
0x1400806f4  jnz     loc_140080B84
0x1400806fa  mov     [rcx], rax
0x1400806fd  lea     rbx, [rsi-18h]
0x140080701  mov     [rax+8], rcx
0x140080705  xor     edx, edx
0x140080707  mov     [rsi+8], rsi
0x14008070b  lea     rcx, [r14+0D0h]
0x140080712  mov     [rsi], rsi
0x140080715  mov     r15d, edi
0x140080718  mov     [r14+552h], dil
0x14008071f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140080726  nop     dword ptr [rax+rax+00h]
0x14008072b  call    cs:__imp_KeLeaveCriticalRegion
0x140080732  nop     dword ptr [rax+rax+00h]
0x140080737  mov     rcx, [r14+6A0h]
0x14008073e  test    byte ptr [rcx+6E2h], 8
0x140080745  jnz     loc_140080D46
0x14008074b  mov     ecx, [rbx+38h]
0x14008074e  mov     r13d, 0FFFFFFFFh
0x140080754  mov     [rbp+57h+var_A0], ecx
0x140080757  cmp     [rbx+38h], edi
0x14008075a  jz      loc_140080842
0x140080760  mov     [rbp+57h+var_98], rdi
0x140080764  mov     r15d, gs:1A4h
0x14008076d  cmp     cs:UxDebugDisableLookaside, dil
0x140080774  jnz     loc_140080B35
0x14008077a  cmp     cs:UxCompactMode, dil
0x140080781  jnz     loc_140080C06
0x140080787  mov     r8, cs:qword_1401A0700
0x14008078e  lea     edi, [r15+1]
0x140080792  shl     rdi, 7
0x140080796  add     rdi, r8
0x140080799  movzx   eax, byte ptr [rdi+0B0h]
0x1400807a0  test    al, al
0x1400807a2  jz      loc_140080C29
0x1400807a8  lea     rcx, [rdi+40h]; Lookaside
0x1400807ac  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400807b3  nop     dword ptr [rax+rax+00h]
0x1400807b8  mov     r8, rax
0x1400807bb  test    rax, rax
0x1400807be  jz      loc_140080BB3
0x1400807c4  xorps   xmm0, xmm0
0x1400807c7  movaps  xmmword ptr [rax], xmm0
0x1400807ca  movaps  xmmword ptr [rax+10h], xmm0
0x1400807ce  movaps  xmmword ptr [rax+20h], xmm0
0x1400807d2  mov     [rax], r15d
0x1400807d5  mov     dword ptr [rax+10h], 49426C55h
0x1400807dc  lea     rdx, [rbx+14h]; BugCheckParameter2
0x1400807e0  mov     rax, [rbx+30h]
0x1400807e4  mov     [r8+18h], rax
0x1400807e8  mov     eax, 1
0x1400807ed  lock xadd [rdx], eax
0x1400807f1  inc     eax
0x1400807f3  cmp     cs:UxDebugCheckRefcount, 0
0x1400807fa  jnz     loc_140080A2F
0x140080800  mov     [r8+20h], rbx
0x140080804  mov     [rbp+57h+var_98], r8
0x140080808  test    byte ptr cs:xmmword_1401A2CA0+0Ah, 2
0x14008080f  jnz     loc_140080D91
0x140080815  mov     rax, [r14+20h]
0x140080819  lea     rcx, [rbp+57h+var_A0]
0x14008081d  mov     r9d, [rbx+38h]
0x140080821  lea     r8, [rbp+57h+var_98]
0x140080825  mov     [rsp+0E0h+var_C0], rcx
0x14008082a  mov     edx, 4000h
0x14008082f  mov     rcx, [r14+18h]
0x140080833  mov     rax, [rax+30h]
0x140080837  call    _guard_dispatch_icall
0x14008083c  mov     ecx, [rbp+57h+var_A0]
0x14008083f  mov     r15d, eax
0x140080842  mov     edx, [rbx+38h]
0x140080845  cmp     ecx, edx
0x140080847  setz    r13b
0x14008084b  test    ecx, ecx
0x14008084d  jz      short loc_14008085A
0x14008084f  mov     eax, ecx
0x140080851  add     [rbx+30h], rax
0x140080855  sub     edx, ecx
0x140080857  mov     [rbx+38h], edx
0x14008085a  test    edx, edx
0x14008085c  jnz     loc_140080CE0
0x140080862  mov     edi, [rbx+3Ch]
0x140080865  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14008086c  jnz     loc_140080BC1
0x140080872  add     [r14+548h], edi
0x140080879  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140080880  jnz     loc_140080DC2
0x140080886  mov     edi, 0FFFFFFFFh
0x14008088b  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14008088f  mov     eax, edi
0x140080891  lock xadd [rdx], eax
0x140080895  dec     eax
0x140080897  cmp     cs:UxDebugCheckRefcount, 0
0x14008089e  jnz     loc_140080AFD
0x1400808a4  test    eax, eax
0x1400808a6  jnz     loc_14008098E
0x1400808ac  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400808b3  jnz     loc_140080BE3
0x1400808b9  mov     rsi, [rbx+28h]
0x1400808bd  test    rsi, rsi
0x1400808c0  jz      loc_140080963
0x1400808c6  lea     rdx, [rsi+14h]; BugCheckParameter2
0x1400808ca  mov     eax, edi
0x1400808cc  lock xadd [rdx], eax
0x1400808d0  dec     eax
0x1400808d2  cmp     cs:UxDebugCheckRefcount, 0
0x1400808d9  jnz     loc_140080B19
0x1400808df  test    eax, eax
0x1400808e1  jnz     short loc_14008095B
0x1400808e3  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400808ea  jnz     loc_140080DDD
0x1400808f0  mov     eax, [rsi+78h]
0x1400808f3  mov     dword ptr [rsi+10h], 6C735875h
0x1400808fa  test    eax, eax
0x1400808fc  jnz     loc_140080A9F
0x140080902  cmp     cs:UxDebugDisableLookaside, al
0x140080908  jnz     loc_140080DFB
0x14008090e  cmp     cs:UxCompactMode, al
0x140080914  jnz     loc_140080B5D
0x14008091a  mov     edi, [rsi]
0x14008091c  mov     r8, cs:qword_1401A0610
0x140080923  inc     edi
0x140080925  shl     rdi, 7
0x140080929  add     rdi, r8
0x14008092c  movzx   eax, byte ptr [rdi+0B0h]
0x140080933  test    al, al
0x140080935  jz      loc_140080AEC
0x14008093b  mov     rdx, rsi; Entry
0x14008093e  lea     rcx, [rdi+40h]; Lookaside
0x140080942  call    cs:__imp_ExFreeToLookasideListEx
0x140080949  nop     dword ptr [rax+rax+00h]
0x14008094e  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140080955  jnz     loc_140080EE2
0x14008095b  mov     qword ptr [rbx+28h], 0
0x140080963  lea     rax, [r14+730h]
0x14008096a  mov     dword ptr [rbx+10h], 64735875h
0x140080971  cmp     rbx, rax
0x140080974  jnz     loc_140080A4C
0x14008097a  mov     [r14+5D8h], rbx
0x140080981  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140080988  jnz     loc_140080F2F
0x14008098e  call    cs:__imp_KeEnterCriticalRegion
0x140080995  nop     dword ptr [rax+rax+00h]
0x14008099a  xor     edx, edx
0x14008099c  lea     rcx, [r14+0D0h]
0x1400809a3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400809aa  nop     dword ptr [rax+rax+00h]
0x1400809af  xor     ebx, ebx
0x1400809b1  mov     dil, 1
0x1400809b4  test    r13b, r13b
0x1400809b7  mov     r13d, 0FFFFFFFFh
0x1400809bd  jz      short loc_1400809C6
0x1400809bf  mov     [r14+552h], dil
0x1400809c6  mov     rdx, [rbp+57h+var_98]
0x1400809ca  test    rdx, rdx
0x1400809cd  jnz     loc_140080F4A
0x1400809d3  test    rbx, rbx
0x1400809d6  jnz     loc_140080C98
0x1400809dc  test    dil, dil
0x1400809df  jz      loc_140080F5F
0x1400809e5  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400809ec  jnz     loc_140080F85
0x1400809f2  mov     r13, [rsp+0E0h+arg_18]
0x1400809fa  mov     eax, r15d
0x1400809fd  mov     r15, [rsp+0E0h+var_20]
0x140080a05  mov     r12, [rsp+0E0h+arg_10]
0x140080a0d  mov     rbx, [rsp+0E0h+arg_8]
0x140080a15  mov     rcx, [rbp+57h+var_30]
0x140080a19  xor     rcx, rsp; StackCookie
0x140080a1c  call    __security_check_cookie
0x140080a21  add     rsp, 0C8h
0x140080a28  pop     r14
0x140080a2a  pop     rdi
0x140080a2b  pop     rsi
0x140080a2c  pop     rbp
0x140080a2d  retn
0x140080a2f  cmp     eax, r13d
0x140080a32  jg      loc_140080800
0x140080a38  movsxd  r9, eax; BugCheckParameter4
0x140080a3b  mov     ecx, 3; BugCheckParameter1
0x140080a40  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x140080a46  call    UlBugCheckEx
0x140080a4c  cmp     cs:UxDebugDisableLookaside, 0
0x140080a53  jnz     loc_140080EFD
0x140080a59  cmp     cs:UxCompactMode, 0
0x140080a60  jnz     loc_140080B8B
0x140080a66  mov     edi, [rbx]
0x140080a68  mov     r8, cs:qword_1401A06D0
0x140080a6f  inc     edi
0x140080a71  shl     rdi, 7
0x140080a75  add     rdi, r8
0x140080a78  movzx   eax, byte ptr [rdi+0B0h]
0x140080a7f  test    al, al
0x140080a81  jz      loc_140080C87
0x140080a87  mov     rdx, rbx; Entry
0x140080a8a  lea     rcx, [rdi+40h]; Lookaside
0x140080a8e  call    cs:__imp_ExFreeToLookasideListEx
0x140080a95  nop     dword ptr [rax+rax+00h]
0x140080a9a  jmp     loc_140080981
0x140080a9f  cmp     eax, 1
0x140080aa2  jz      loc_140080C3A
0x140080aa8  cmp     eax, 2
0x140080aab  jnz     loc_140080E91
0x140080ab1  cmp     cs:UxDebugDisableLookaside, 0
0x140080ab8  jnz     loc_140080E5F
0x140080abe  cmp     cs:UxCompactMode, 0
0x140080ac5  jnz     loc_140080B9F
0x140080acb  mov     edi, [rsi]
0x140080acd  mov     r8, cs:qword_1401A0670
0x140080ad4  inc     edi
0x140080ad6  shl     rdi, 7
0x140080ada  add     rdi, r8
0x140080add  movzx   eax, byte ptr [rdi+0B0h]
0x140080ae4  test    al, al
0x140080ae6  jnz     loc_14008093B
0x140080aec  lea     rdx, [rdi+40h]
0x140080af0  mov     rcx, r8
0x140080af3  call    PplpLazyInitializeLookasideList
0x140080af8  jmp     loc_14008093B
0x140080afd  cmp     eax, edi
0x140080aff  jg      loc_1400808A4
0x140080b05  movsxd  r9, eax; BugCheckParameter4
0x140080b08  mov     ecx, 3; BugCheckParameter1
0x140080b0d  mov     r8d, 1; BugCheckParameter3
0x140080b13  call    UlBugCheckEx
0x140080b19  cmp     eax, edi
0x140080b1b  jg      loc_1400808DF
0x140080b21  movsxd  r9, eax; BugCheckParameter4
0x140080b24  mov     ecx, 3; BugCheckParameter1
0x140080b29  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x140080b2f  call    UlBugCheckEx
0x140080b35  mov     rax, cs:off_1401A0720
0x140080b3c  xor     r9d, r9d
0x140080b3f  mov     r8d, cs:dword_1401A0718
0x140080b46  mov     rdx, cs:qword_1401A0710
0x140080b4d  mov     ecx, cs:dword_1401A0708
0x140080b53  call    _guard_dispatch_icall
0x140080b58  jmp     loc_1400807B8
0x140080b5d  mov     rdi, cs:qword_1401A0610
0x140080b64  call    cs:__imp_KeGetCurrentNodeNumber
0x140080b6b  nop     dword ptr [rax+rax+00h]
0x140080b70  movzx   r8d, ax
0x140080b74  mov     rdx, rsi
0x140080b77  mov     rcx, rdi
0x140080b7a  call    PplFreeToLookasideListProcessor
0x140080b7f  jmp     loc_14008094E
0x140080b84  mov     ecx, 3
0x140080b89  int     29h; Win8: RtlFailFast(ecx)
0x140080b8b  mov     rcx, cs:qword_1401A06D0
0x140080b92  mov     rdx, rbx
0x140080b95  call    PnlFreeToLookasideList
0x140080b9a  jmp     loc_140080981
0x140080b9f  mov     rcx, cs:qword_1401A0670
0x140080ba6  mov     rdx, rsi
0x140080ba9  call    PnlFreeToLookasideList
0x140080bae  jmp     loc_14008094E
0x140080bb3  xor     dil, dil
0x140080bb6  mov     r15d, 0C000009Ah
0x140080bbc  jmp     loc_1400809C6
0x140080bc1  mov     edx, 10h
0x140080bc6  mov     dword ptr [rsp+0E0h+var_C0], edi
0x140080bca  mov     ecx, 411h
0x140080bcf  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x140080bd6  mov     r9, r14
0x140080bd9  call    WPP_SF_qD
0x140080bde  jmp     loc_140080872
0x140080be3  mov     edx, 0C1h
0x140080be8  mov     [rsp+0E0h+var_C0], rbx
0x140080bed  mov     ecx, 411h
0x140080bf2  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x140080bf9  mov     r9, r14
0x140080bfc  call    WPP_SF_qq
0x140080c01  jmp     loc_1400808B9
0x140080c06  mov     rdi, cs:qword_1401A0700
0x140080c0d  call    cs:__imp_KeGetCurrentNodeNumber
  ... truncated ...
```

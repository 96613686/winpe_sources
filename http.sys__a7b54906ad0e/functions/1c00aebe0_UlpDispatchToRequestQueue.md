# UlpDispatchToRequestQueue

- ea: `0x1c00aebe0`
- end: `0x1c00af020`
- name: `UlpDispatchToRequestQueue`
- size: `1088`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c00084d0`
- `0x1c00ad390`
- `0x1c0100e20`

## callees

- `0x1c0008090`
- `0x1c0015480`
- `0x1c001604c`
- `0x1c001a4b0`
- `0x1c001a5f0`
- `0x1c0029618`
- `0x1c002a13c`
- `0x1c002e650`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c008f3a8`
- `0x1c008f680`
- `0x1c008f7c0`
- `0x1c008f890`
- `0x1c008fc24`
- `0x1c0090f34`
- `0x1c0091028`
- `0x1c00a8718`
- `0x1c00aebe0`
- `0x1c00af030`
- `0x1c00b0480`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1c00e4b0f`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e4b0f`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00aee8a`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00af003`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00aee8a`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00af003`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00aec94`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00aec94`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00aee4b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00aee6c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00aefc5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00aefe6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00aee4b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00aee6c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00aefc5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00aefe6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00aecd4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00aecf6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00aecd4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00aecf6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00aee57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00aee78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00aee96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00aefd1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00aeff2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00af00f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00aee57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00aee78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00aee96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00aefd1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00aeff2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00af00f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00aec7f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00aecbf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00aece0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00aec7f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00aecbf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00aece0`
- `HAL!KeQueryPerformanceCounter` at `0x1c00aef9f`
- `HAL!KeQueryPerformanceCounter` at `0x1c00aef9f`

## pseudocode

```c
__int64 __fastcall UlpDispatchToRequestQueue(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        _BYTE *a4,
        struct _LIST_ENTRY *a5)
{
  __int64 v9; // rdx
  int v10; // esi
  __int64 v11; // rdi
  __int64 v12; // rcx
  _BYTE *v13; // rax
  volatile signed __int32 *v14; // rax
  __int64 v15; // rdi
  __int64 v16; // r8
  int v17; // eax
  int v18; // edx
  PIRP v19; // rdi
  __int64 FsContext; // rdi
  __int64 v21; // r15
  _QWORD *v22; // rdx
  _QWORD *v23; // rcx
  int v24; // eax
  PVOID v25; // rcx
  __int64 v26; // rax
  IRP *v27; // rdi
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v30; // rcx
  unsigned int v31; // eax
  PFILE_OBJECT FileObject; // rdx
  PVOID v33; // r15
  __int64 v34; // rcx
  __int64 v35; // r9
  const wchar_t *v36; // rax
  const wchar_t *v37; // rcx
  char v38; // [rsp+50h] [rbp-31h]
  PVOID P; // [rsp+58h] [rbp-29h] BYREF
  __int64 v40; // [rsp+60h] [rbp-21h]
  PIRP v41; // [rsp+68h] [rbp-19h] BYREF
  struct _LIST_ENTRY *v42; // [rsp+70h] [rbp-11h]
  _QWORD v43[3]; // [rsp+78h] [rbp-9h] BYREF
  char v44; // [rsp+90h] [rbp+Fh]
  int v45; // [rsp+91h] [rbp+10h]
  __int16 v46; // [rsp+95h] [rbp+14h]
  char v47; // [rsp+97h] [rbp+16h]

  v41 = 0;
  v42 = a5;
  P = 0;
  v38 = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
  {
    if ( a2 )
      v30 = *(_QWORD *)(a2 + 64);
    else
      v30 = 0;
    WPP_SF_qqilqq(v30, a5, a1, a2, v30, a3, a4, a5);
  }
  *a4 = 0;
  *(_BYTE *)(a2 + 1836) = 1;
  if ( !a3 && !*(_BYTE *)(a2 + 1835) )
  {
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 96));
    *(_BYTE *)(a2 + 1835) = 1;
  }
  v10 = UlpOpenCoupling(*(_QWORD *)(a2 + 24), a1, &P);
  if ( v10 >= 0 )
  {
    KeEnterCriticalRegion();
    v40 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 280), 0);
    v11 = v40;
    if ( a3 )
    {
      if ( !*(_QWORD *)(a1 + 296) )
      {
        v10 = 0;
        goto LABEL_55;
      }
    }
    else
    {
      v12 = *(unsigned int *)(a1 + 224);
      if ( (_DWORD)v12 )
      {
        v31 = UlpRequestQueueStateToErrorCode(v12);
        UlSetErrorCode(a2, v31, a1);
        v10 = -1073741769;
        goto LABEL_55;
      }
    }
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a2 + 1688, 0);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx((char *)P + 56, 0);
    if ( !*((_BYTE *)P + 64) )
    {
      if ( a3 )
      {
        if ( *(_BYTE *)(a2 + 1837) )
        {
          v10 = 0;
LABEL_54:
          ExReleasePushLockExclusiveEx((char *)P + 56, 0);
          KeLeaveCriticalRegion();
          ExReleasePushLockExclusiveEx(a2 + 1688, 0);
          KeLeaveCriticalRegion();
LABEL_55:
          ExReleaseCacheAwarePushLockSharedEx(v11, 0);
          KeLeaveCriticalRegion();
          goto LABEL_33;
        }
        *(_DWORD *)(a2 + 1724) = 1;
        UlpToggleRequestQueueTimer(a2, 0);
      }
      else
      {
        v13 = P;
        *(_DWORD *)(a2 + 1724) = 2;
        if ( v13[65] || !*(_DWORD *)(a1 + 272) )
        {
          v13[65] = 0;
          v38 = 1;
        }
      }
      if ( !*(_QWORD *)(a2 + 1696) )
      {
        v14 = (volatile signed __int32 *)P;
        *(_QWORD *)(a2 + 1696) = P;
        _InterlockedIncrement(v14);
      }
      if ( a3 )
      {
        v16 = *(_QWORD *)(a1 + 296);
        v15 = 3000;
      }
      else
      {
        v15 = 3048;
        v16 = *((_QWORD *)P + 9);
      }
      v17 = UlpSubmitRequest(a1, a2, v16, &v41);
      v10 = v17;
      switch ( v17 )
      {
        case 0:
          *a4 = 1;
          _InterlockedIncrement((volatile signed __int32 *)(a2 + 48));
          v19 = v41;
          if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
            WPP_SF_q(126, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v41);
          FsContext = (__int64)v19->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
          if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
            WPP_SF_q(127, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, FsContext);
          v21 = *(_QWORD *)(a2 + 1696);
          if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
            WPP_SF_qqqL(176, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a2, *(_QWORD *)(a2 + 64), FsContext, 0);
          if ( *(_BYTE *)(v21 + 64) && (*(_DWORD *)&WPP_MAIN_CB.StackSize & 0x200000) != 0 )
            WPP_SF_qLLqqZq(
              *(_QWORD *)(FsContext + 8),
              v18,
              a2,
              *(_DWORD *)(a2 + 1720),
              *(_DWORD *)(a2 + 1724),
              FsContext,
              *(_QWORD *)(FsContext + 8),
              *(_QWORD *)(FsContext + 8) + 152LL,
              v21);
          *(_DWORD *)(a2 + 1720) = 2;
          v22 = *(_QWORD **)(v21 + 88);
          v23 = (_QWORD *)(a2 + 1704);
          if ( *v22 != v21 + 80 )
            __fastfail(3u);
          *v23 = v21 + 80;
          *(_QWORD *)(a2 + 1712) = v22;
          *v22 = v23;
          *(_QWORD *)(v21 + 88) = v23;
          v24 = *(_DWORD *)(FsContext + 40);
          if ( v24 == 1 )
          {
            if ( *(_QWORD *)(v21 + 72) )
            {
LABEL_30:
              *(_QWORD *)(a2 + 1728) = FsContext;
              _InterlockedIncrement((volatile signed __int32 *)FsContext);
              if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
                WPP_SF_D(179, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
              ExReleasePushLockExclusiveEx((char *)P + 56, 0);
              KeLeaveCriticalRegion();
              ExReleasePushLockExclusiveEx(a2 + 1688, 0);
              KeLeaveCriticalRegion();
              ExReleaseCacheAwarePushLockSharedEx(v40, 0);
              KeLeaveCriticalRegion();
              UlCopyRequestToIrp(a2, v41, FsContext, v42, 1);
              v41 = 0;
              goto LABEL_33;
            }
            *(_QWORD *)(v21 + 72) = FsContext;
            _InterlockedIncrement((volatile signed __int32 *)FsContext);
            v24 = *(_DWORD *)(FsContext + 40);
          }
          if ( v24 == 4 )
            *(_BYTE *)(a2 + 1837) = 1;
          goto LABEL_30;
        case -1073741110:
          UlSetErrorCode(a2, 23, a1);
          break;
        case 259:
          *a4 = 1;
          _InterlockedIncrement((volatile signed __int32 *)(a2 + 48));
          *(_DWORD *)(a2 + 1720) = 1;
          UlStartRequestQueueTimer(a2);
          PerformanceCounter = KeQueryPerformanceCounter(0);
          if ( !*(_QWORD *)(v15 + a2) )
            *(LARGE_INTEGER *)(v15 + a2) = PerformanceCounter;
          v11 = v40;
          v10 = 0;
          goto LABEL_54;
      }
      v11 = v40;
    }
    v10 = -1073741436;
    goto LABEL_54;
  }
LABEL_33:
  v25 = P;
  if ( P )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P, 0xFFFFFFFF) == 1 )
      UlpFreeCoupling(v25);
    P = 0;
  }
  if ( v38 )
  {
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_q(152, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1);
    v26 = UlSiqDequeueIrp((PKSPIN_LOCK)(a1 + 64));
    v27 = (IRP *)v26;
    if ( v26 )
    {
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_q(126, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v26);
      FileObject = v27->Tail.Overlay.CurrentStackLocation->FileObject;
      v33 = FileObject->FsContext;
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_q(127, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v33);
      v27->IoStatus.Status = 0;
      v27->IoStatus.Information = 0;
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x200000) != 0 )
        WPP_SF_qqqZ(153, (_DWORD)FileObject, (_DWORD)v27, (_DWORD)v33, a1, a1 + 152);
      IofCompleteRequest(v27, 2);
    }
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_(154, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  }
  if ( v10 < 0 )
  {
    if ( !a3 )
      _InterlockedIncrement64((volatile signed __int64 *)(a1 + 104));
    v34 = *(_QWORD *)(*(_QWORD *)(a2 + 24) + 960LL);
    if ( *(_BYTE *)(v34 + 1568) )
    {
      v35 = *(_QWORD *)(a2 + 56);
      v43[0] = a2 + 72;
      v36 = *(const wchar_t **)(a1 + 160);
      v43[2] = v34;
      v37 = L"<<unnamed>>";
      v45 = 0;
      if ( v36 )
        v37 = v36;
      v46 = 0;
      v47 = 0;
      v43[1] = 0;
      v44 = 0;
      McTemplateK0xsz_UlEtwWriteEventWrapper(
        (_DWORD)v37,
        (unsigned int)HTTP_EVENT_REQUEST_REJECTED,
        (unsigned int)v43,
        v35,
        (__int64)"RequestQueueLimitReached",
        (__int64)v37);
    }
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x200000) != 0 )
      WPP_SF_Zi(185, v9, a1 + 152, *(_QWORD *)(a2 + 56));
  }
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_DD(186, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, (unsigned __int8)*a4, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1c00aebe0  push    rbp
0x1c00aebe2  push    rbx
0x1c00aebe3  push    rsi
0x1c00aebe4  push    r12
0x1c00aebe6  push    r13
0x1c00aebe8  push    r14
0x1c00aebea  push    r15
0x1c00aebec  lea     rbp, [rsp-1Fh]
0x1c00aebf1  sub     rsp, 0A0h
0x1c00aebf8  mov     rax, cs:__security_cookie
0x1c00aebff  xor     rax, rsp
0x1c00aec02  mov     [rbp+4Fh+var_38], rax
0x1c00aec06  xor     r15d, r15d
0x1c00aec09  movzx   r12d, r8b
0x1c00aec0d  mov     rbx, rdx
0x1c00aec10  mov     [rbp+4Fh+var_68], r15
0x1c00aec14  mov     rdx, [rbp+4Fh+arg_20]
0x1c00aec18  mov     r13, r9
0x1c00aec1b  mov     [rbp+4Fh+var_60], rdx
0x1c00aec1f  mov     r14, rcx
0x1c00aec22  mov     [rbp+4Fh+P], r15
0x1c00aec26  mov     [rbp+4Fh+var_80], r15b
0x1c00aec2a  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00aec30  test    al, al
0x1c00aec32  js      loc_1C00E48C6
0x1c00aec38  mov     [r13+0], r15b
0x1c00aec3c  mov     byte ptr [rbx+72Ch], 1
0x1c00aec43  test    r12b, r12b
0x1c00aec46  jnz     short loc_1C00AEC5D
0x1c00aec48  cmp     [rbx+72Bh], r15b
0x1c00aec4f  jnz     short loc_1C00AEC5D
0x1c00aec51  lock inc qword ptr [r14+60h]
0x1c00aec56  mov     byte ptr [rbx+72Bh], 1
0x1c00aec5d  mov     rcx, [rbx+18h]
0x1c00aec61  lea     r8, [rbp+4Fh+P]
0x1c00aec65  mov     rdx, r14
0x1c00aec68  mov     [rsp+0D0h+arg_10], rdi
0x1c00aec70  call    UlpOpenCoupling
0x1c00aec75  mov     esi, eax
0x1c00aec77  test    eax, eax
0x1c00aec79  js      loc_1C00AEEC1
0x1c00aec7f  call    cs:__imp_KeEnterCriticalRegion
0x1c00aec86  nop     dword ptr [rax+rax+00h]
0x1c00aec8b  mov     rcx, [r14+118h]
0x1c00aec92  xor     edx, edx
0x1c00aec94  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c00aec9b  nop     dword ptr [rax+rax+00h]
0x1c00aeca0  mov     [rbp+4Fh+var_70], rax
0x1c00aeca4  mov     rdi, rax
0x1c00aeca7  test    r12b, r12b
0x1c00aecaa  jnz     loc_1C00E4915
0x1c00aecb0  mov     ecx, [r14+0E0h]
0x1c00aecb7  test    ecx, ecx
0x1c00aecb9  jnz     loc_1C00E48F9
0x1c00aecbf  call    cs:__imp_KeEnterCriticalRegion
0x1c00aecc6  nop     dword ptr [rax+rax+00h]
0x1c00aeccb  xor     edx, edx
0x1c00aeccd  lea     rcx, [rbx+698h]
0x1c00aecd4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00aecdb  nop     dword ptr [rax+rax+00h]
0x1c00aece0  call    cs:__imp_KeEnterCriticalRegion
0x1c00aece7  nop     dword ptr [rax+rax+00h]
0x1c00aecec  mov     rcx, [rbp+4Fh+P]
0x1c00aecf0  xor     edx, edx
0x1c00aecf2  add     rcx, 38h ; '8'
0x1c00aecf6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00aecfd  nop     dword ptr [rax+rax+00h]
0x1c00aed02  mov     rax, [rbp+4Fh+P]
0x1c00aed06  cmp     [rax+40h], r15b
0x1c00aed0a  jnz     loc_1C00E4982
0x1c00aed10  test    r12b, r12b
0x1c00aed13  jnz     loc_1C00E492A
0x1c00aed19  mov     rax, [rbp+4Fh+P]
0x1c00aed1d  mov     dword ptr [rbx+6BCh], 2
0x1c00aed27  cmp     [rax+41h], r15b
0x1c00aed2b  jz      loc_1C00AEF5A
0x1c00aed31  mov     [rax+41h], r15b
0x1c00aed35  mov     [rbp+4Fh+var_80], 1
0x1c00aed39  cmp     [rbx+6A0h], r15
0x1c00aed40  jnz     short loc_1C00AED50
0x1c00aed42  mov     rax, [rbp+4Fh+P]
0x1c00aed46  mov     [rbx+6A0h], rax
0x1c00aed4d  lock inc dword ptr [rax]
0x1c00aed50  test    r12b, r12b
0x1c00aed53  jnz     loc_1C00E495D
0x1c00aed59  mov     rax, [rbp+4Fh+P]
0x1c00aed5d  mov     edi, 0BE8h
0x1c00aed62  mov     r8, [rax+48h]
0x1c00aed66  lea     r9, [rbp+4Fh+var_68]
0x1c00aed6a  mov     rdx, rbx
0x1c00aed6d  mov     rcx, r14
0x1c00aed70  call    UlpSubmitRequest
0x1c00aed75  mov     esi, eax
0x1c00aed77  test    eax, eax
0x1c00aed79  jnz     loc_1C00AEF6C
0x1c00aed7f  mov     byte ptr [r13+0], 1
0x1c00aed84  lock inc dword ptr [rbx+30h]
0x1c00aed88  mov     rdi, [rbp+4Fh+var_68]
0x1c00aed8c  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00aed92  test    al, al
0x1c00aed94  js      loc_1C00E498C
0x1c00aed9a  mov     rax, [rdi+0B8h]
0x1c00aeda1  mov     rcx, [rax+30h]
0x1c00aeda5  mov     rdi, [rcx+18h]
0x1c00aeda9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00aedaf  test    al, al
0x1c00aedb1  js      loc_1C00E49A6
0x1c00aedb7  mov     r15, [rbx+6A0h]
0x1c00aedbe  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00aedc4  test    al, al
0x1c00aedc6  js      loc_1C00E49C0
0x1c00aedcc  cmp     byte ptr [r15+40h], 0
0x1c00aedd1  jnz     loc_1C00E49EB
0x1c00aedd7  lea     rax, [r15+50h]
0x1c00aeddb  mov     dword ptr [rbx+6B8h], 2
0x1c00aede5  mov     rdx, [rax+8]
0x1c00aede9  lea     rcx, [rbx+6A8h]
0x1c00aedf0  cmp     [rdx], rax
0x1c00aedf3  jnz     loc_1C00E4A39
0x1c00aedf9  mov     [rcx], rax
0x1c00aedfc  mov     [rcx+8], rdx
0x1c00aee00  mov     [rdx], rcx
0x1c00aee03  mov     [rax+8], rcx
0x1c00aee07  mov     eax, [rdi+28h]
0x1c00aee0a  cmp     eax, 1
0x1c00aee0d  jnz     short loc_1C00AEE20
0x1c00aee0f  cmp     qword ptr [r15+48h], 0
0x1c00aee14  jnz     short loc_1C00AEE29
0x1c00aee16  mov     [r15+48h], rdi
0x1c00aee1a  lock inc dword ptr [rdi]
0x1c00aee1d  mov     eax, [rdi+28h]
0x1c00aee20  cmp     eax, 4
0x1c00aee23  jz      loc_1C00E4A40
0x1c00aee29  mov     [rbx+6C0h], rdi
0x1c00aee30  lock inc dword ptr [rdi]
0x1c00aee33  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00aee39  test    al, al
0x1c00aee3b  js      loc_1C00E4A4C
0x1c00aee41  mov     rcx, [rbp+4Fh+P]
0x1c00aee45  xor     edx, edx
0x1c00aee47  add     rcx, 38h ; '8'
0x1c00aee4b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00aee52  nop     dword ptr [rax+rax+00h]
0x1c00aee57  call    cs:__imp_KeLeaveCriticalRegion
0x1c00aee5e  nop     dword ptr [rax+rax+00h]
0x1c00aee63  xor     edx, edx
0x1c00aee65  lea     rcx, [rbx+698h]
0x1c00aee6c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00aee73  nop     dword ptr [rax+rax+00h]
0x1c00aee78  call    cs:__imp_KeLeaveCriticalRegion
0x1c00aee7f  nop     dword ptr [rax+rax+00h]
0x1c00aee84  mov     rcx, [rbp+4Fh+var_70]
0x1c00aee88  xor     edx, edx
0x1c00aee8a  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00aee91  nop     dword ptr [rax+rax+00h]
0x1c00aee96  call    cs:__imp_KeLeaveCriticalRegion
0x1c00aee9d  nop     dword ptr [rax+rax+00h]
0x1c00aeea2  mov     r9, [rbp+4Fh+var_60]
0x1c00aeea6  mov     r8, rdi
0x1c00aeea9  mov     rdx, [rbp+4Fh+var_68]
0x1c00aeead  mov     rcx, rbx
0x1c00aeeb0  mov     byte ptr [rsp+0D0h+var_B0], 1
0x1c00aeeb5  call    UlCopyRequestToIrp
0x1c00aeeba  xor     r15d, r15d
0x1c00aeebd  mov     [rbp+4Fh+var_68], r15
0x1c00aeec1  mov     rcx, [rbp+4Fh+P]; P
0x1c00aeec5  test    rcx, rcx
0x1c00aeec8  jz      short loc_1C00AEEE3
0x1c00aeeca  mov     eax, 0FFFFFFFFh
0x1c00aeecf  lock xadd [rcx], eax
0x1c00aeed3  cmp     eax, 1
0x1c00aeed6  jnz     short loc_1C00AEEDF
0x1c00aeed8  xor     edx, edx
0x1c00aeeda  call    UlpFreeCoupling
0x1c00aeedf  mov     [rbp+4Fh+P], r15
0x1c00aeee3  cmp     [rbp+4Fh+var_80], 0
0x1c00aeee7  jz      short loc_1C00AEF1A
0x1c00aeee9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00aeeef  test    al, al
0x1c00aeef1  js      loc_1C00E4A69
0x1c00aeef7  lea     rcx, [r14+40h]; SpinLock
0x1c00aeefb  call    UlSiqDequeueIrp
0x1c00aef00  mov     rdi, rax
0x1c00aef03  test    rax, rax
0x1c00aef06  jnz     loc_1C00E4A83
0x1c00aef0c  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00aef12  test    al, al
0x1c00aef14  js      loc_1C00E4B23
0x1c00aef1a  test    esi, esi
0x1c00aef1c  js      loc_1C00E4B3A
0x1c00aef22  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00aef28  test    al, al
0x1c00aef2a  js      loc_1C00E4BDE
0x1c00aef30  mov     rdi, [rsp+0D0h+arg_10]
0x1c00aef38  mov     eax, esi
0x1c00aef3a  mov     rcx, [rbp+4Fh+var_38]
0x1c00aef3e  xor     rcx, rsp; StackCookie
0x1c00aef41  call    __security_check_cookie
0x1c00aef46  add     rsp, 0A0h
0x1c00aef4d  pop     r15
0x1c00aef4f  pop     r14
0x1c00aef51  pop     r13
0x1c00aef53  pop     r12
0x1c00aef55  pop     rsi
0x1c00aef56  pop     rbx
0x1c00aef57  pop     rbp
0x1c00aef58  retn
0x1c00aef5a  cmp     [r14+110h], r15d
0x1c00aef61  jnz     loc_1C00AED39
0x1c00aef67  jmp     loc_1C00AED31
0x1c00aef6c  cmp     eax, 0C00002CAh
0x1c00aef71  jz      loc_1C00E496E
0x1c00aef77  cmp     eax, 103h
0x1c00aef7c  jnz     loc_1C00E497E
0x1c00aef82  mov     byte ptr [r13+0], 1
0x1c00aef87  lock inc dword ptr [rbx+30h]
0x1c00aef8b  mov     rcx, rbx
0x1c00aef8e  mov     dword ptr [rbx+6B8h], 1
0x1c00aef98  call    UlStartRequestQueueTimer
0x1c00aef9d  xor     ecx, ecx; PerformanceFrequency
0x1c00aef9f  call    cs:__imp_KeQueryPerformanceCounter
0x1c00aefa6  nop     dword ptr [rax+rax+00h]
0x1c00aefab  cmp     [rdi+rbx], r15
0x1c00aefaf  jnz     short loc_1C00AEFB5
0x1c00aefb1  mov     [rdi+rbx], rax
0x1c00aefb5  mov     rdi, [rbp+4Fh+var_70]
0x1c00aefb9  xor     esi, esi
0x1c00aefbb  mov     rcx, [rbp+4Fh+P]
0x1c00aefbf  xor     edx, edx
0x1c00aefc1  add     rcx, 38h ; '8'
0x1c00aefc5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00aefcc  nop     dword ptr [rax+rax+00h]
0x1c00aefd1  call    cs:__imp_KeLeaveCriticalRegion
0x1c00aefd8  nop     dword ptr [rax+rax+00h]
0x1c00aefdd  xor     edx, edx
0x1c00aefdf  lea     rcx, [rbx+698h]
0x1c00aefe6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00aefed  nop     dword ptr [rax+rax+00h]
0x1c00aeff2  call    cs:__imp_KeLeaveCriticalRegion
0x1c00aeff9  nop     dword ptr [rax+rax+00h]
0x1c00aeffe  xor     edx, edx
0x1c00af000  mov     rcx, rdi
0x1c00af003  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00af00a  nop     dword ptr [rax+rax+00h]
0x1c00af00f  call    cs:__imp_KeLeaveCriticalRegion
0x1c00af016  nop     dword ptr [rax+rax+00h]
0x1c00af01b  jmp     loc_1C00AEEC1
0x1c00e48c6  test    rbx, rbx
0x1c00e48c9  jz      short loc_1C00E48D1
0x1c00e48cb  mov     rcx, [rbx+40h]
0x1c00e48cf  jmp     short loc_1C00E48D4
0x1c00e48d1  mov     rcx, r15
0x1c00e48d4  mov     [rsp+0D0h+var_98], rdx
0x1c00e48d9  mov     r9, rbx
0x1c00e48dc  mov     [rsp+0D0h+var_A0], r13
0x1c00e48e1  mov     r8, r14
0x1c00e48e4  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x1c00e48e9  mov     [rsp+0D0h+var_B0], rcx
0x1c00e48ee  call    WPP_SF_qqilqq
0x1c00e48f3  nop
0x1c00e48f4  jmp     loc_1C00AEC38
0x1c00e48f9  call    UlpRequestQueueStateToErrorCode
0x1c00e48fe  mov     r8, r14
0x1c00e4901  mov     edx, eax
0x1c00e4903  mov     rcx, rbx
0x1c00e4906  call    UlSetErrorCode
0x1c00e490b  mov     esi, 0C0000037h
0x1c00e4910  jmp     loc_1C00AEFFE
0x1c00e4915  cmp     [r14+128h], r15
0x1c00e491c  jnz     loc_1C00AECBF
0x1c00e4922  mov     esi, r15d
0x1c00e4925  jmp     loc_1C00AEFFE
0x1c00e492a  cmp     [rbx+72Dh], r15b
0x1c00e4931  jz      short loc_1C00E493A
0x1c00e4933  xor     esi, esi
0x1c00e4935  jmp     loc_1C00AEFBB
0x1c00e493a  test    r12b, r12b
0x1c00e493d  jz      loc_1C00AED19
0x1c00e4943  xor     edx, edx
0x1c00e4945  mov     dword ptr [rbx+6BCh], 1
0x1c00e494f  mov     rcx, rbx
0x1c00e4952  call    UlpToggleRequestQueueTimer
0x1c00e4957  nop
0x1c00e4958  jmp     loc_1C00AED39
0x1c00e495d  mov     r8, [r14+128h]
0x1c00e4964  mov     edi, 0BB8h
0x1c00e4969  jmp     loc_1C00AED66
0x1c00e496e  mov     r8, r14
0x1c00e4971  mov     edx, 17h
0x1c00e4976  mov     rcx, rbx
0x1c00e4979  call    UlSetErrorCode
0x1c00e497e  mov     rdi, [rbp+4Fh+var_70]
0x1c00e4982  mov     esi, 0C0000184h
0x1c00e4987  jmp     loc_1C00AEFBB
0x1c00e498c  mov     ecx, 7Eh ; '~'
0x1c00e4991  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00e4998  mov     r8, rdi
0x1c00e499b  call    WPP_SF_q
0x1c00e49a0  nop
0x1c00e49a1  jmp     loc_1C00AED9A
  ... truncated ...
```

# MouHid_ReadComplete

- ea: `0x140002ff0`
- end: `0x140003834`
- name: `MouHid_ReadComplete`
- size: `2116`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x140001464`
- `0x140002ff0`
- `0x14000383c`
- `0x140003b4c`
- `0x140003cf8`
- `0x140004e10`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400030cc`
- `ntoskrnl!KeSetEvent` at `0x1400030cc`
- `ntoskrnl!KeLowerIrql` at `0x1400036c3`
- `ntoskrnl!KeLowerIrql` at `0x14000378e`
- `ntoskrnl!KeLowerIrql` at `0x1400036c3`
- `ntoskrnl!KeLowerIrql` at `0x14000378e`
- `ntoskrnl!KfRaiseIrql` at `0x14000368e`
- `ntoskrnl!KfRaiseIrql` at `0x140003759`
- `ntoskrnl!KfRaiseIrql` at `0x14000368e`
- `ntoskrnl!KfRaiseIrql` at `0x140003759`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003552`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000370c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003552`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000370c`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400037a9`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400037a9`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400037db`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400037db`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400030e7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400030e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003595`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000374b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003595`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000374b`
- `HIDPARSE!HidP_GetUsages` at `0x1400031d3`
- `HIDPARSE!HidP_GetUsages` at `0x1400031d3`
- `HIDPARSE!HidP_GetUsageValue` at `0x140003344`
- `HIDPARSE!HidP_GetUsageValue` at `0x140003425`
- `HIDPARSE!HidP_GetUsageValue` at `0x140003513`
- `HIDPARSE!HidP_GetUsageValue` at `0x140003645`
- `HIDPARSE!HidP_GetUsageValue` at `0x140003344`
- `HIDPARSE!HidP_GetUsageValue` at `0x140003425`
- `HIDPARSE!HidP_GetUsageValue` at `0x140003513`
- `HIDPARSE!HidP_GetUsageValue` at `0x140003645`
- `HIDPARSE!HidP_UsageListDifference` at `0x140003205`
- `HIDPARSE!HidP_UsageListDifference` at `0x140003205`
- `HIDPARSE!HidP_GetScaledUsageValue` at `0x1400032e1`
- `HIDPARSE!HidP_GetScaledUsageValue` at `0x1400033c4`
- `HIDPARSE!HidP_GetScaledUsageValue` at `0x1400034b5`
- `HIDPARSE!HidP_GetScaledUsageValue` at `0x1400035e7`
- `HIDPARSE!HidP_GetScaledUsageValue` at `0x1400032e1`
- `HIDPARSE!HidP_GetScaledUsageValue` at `0x1400033c4`
- `HIDPARSE!HidP_GetScaledUsageValue` at `0x1400034b5`
- `HIDPARSE!HidP_GetScaledUsageValue` at `0x1400035e7`

## pseudocode

```c
__int64 __fastcall MouHid_ReadComplete(char a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v5; // r14
  char v6; // r15
  int v7; // edx
  __int64 v8; // rsi
  ULONG *v10; // r13
  ULONG *v11; // r12
  unsigned int v12; // ecx
  unsigned __int16 *v13; // rdx
  unsigned int v14; // r8d
  __int64 v15; // rax
  unsigned __int16 *v16; // rdx
  unsigned int v17; // r8d
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  NTSTATUS ScaledUsageValue; // eax
  KIRQL v23; // r8
  ULONG v24; // eax
  int v25; // eax
  NTSTATUS v26; // eax
  KIRQL v27; // bl
  __int16 v28; // cx
  KIRQL v29; // r8
  ULONG v30; // eax
  KIRQL v31; // bl
  _OWORD *ErrorLogEntry; // rax
  int UsageLength; // [rsp+20h] [rbp-38h]
  ULONG v34; // [rsp+40h] [rbp-18h] BYREF
  _DWORD v35[5]; // [rsp+44h] [rbp-14h] BYREF
  char v37; // [rsp+A8h] [rbp+50h]
  bool v38; // [rsp+B0h] [rbp+58h]
  ULONG UsageValue; // [rsp+B8h] [rbp+60h] BYREF

  UsageValue = 0;
  v5 = a2;
  v35[0] = 0;
  v6 = a1;
  v34 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      2,
      10,
      (__int64)WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids);
  }
  v7 = *(_DWORD *)(v5 + 48);
  v8 = *(_QWORD *)(a3 + 216);
  v38 = _InterlockedCompareExchange((volatile signed __int32 *)(a3 + 28), 3, 1) != 1;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a3 + 24), 0, 0) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qql(WPP_GLOBAL_Control->DeviceExtension, v7, a3, a4, UsageLength, v6, v5, *(_DWORD *)(a3 + 24));
    goto LABEL_7;
  }
  if ( v7 == -1073741738 || v7 == -1073741727 || v7 == -1073741667 || v7 == -1073741536 )
  {
LABEL_7:
    if ( v38 )
    {
      KeSetEvent((PRKEVENT)(a3 + 144), 0, 0);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a3 + 240), *(PVOID *)(a3 + 112), 0x20u);
    }
    goto LABEL_9;
  }
  if ( !v7 )
  {
    *(_DWORD *)(a3 + 356) = 0;
    v10 = (ULONG *)(a3 + 364);
    *(_DWORD *)(a3 + 364) = 0;
    v11 = (ULONG *)(a3 + 368);
    *(_DWORD *)(a3 + 368) = 0;
    v34 = *(unsigned __int16 *)(v8 + 28);
    v37 = 0;
    if ( HidP_GetUsages(
           HidP_Input,
           9u,
           0,
           *(PUSAGE *)(v8 + 112),
           &v34,
           *(PHIDP_PREPARSED_DATA *)(v8 + 32),
           *(PCHAR *)(v8 + 104),
           *(unsigned __int16 *)(v8 + 44)) >= 0
      && HidP_UsageListDifference(
           *(PUSAGE *)(v8 + 120),
           *(PUSAGE *)(v8 + 112),
           *(PUSAGE *)(v8 + 128),
           *(PUSAGE *)(v8 + 136),
           *(unsigned __int16 *)(v8 + 28)) >= 0 )
    {
      LOWORD(v12) = *(_WORD *)(v8 + 28);
      if ( (_WORD)v12 )
      {
        v13 = *(unsigned __int16 **)(v8 + 136);
        v14 = 0;
        do
        {
          v15 = *v13;
          if ( !(_WORD)v15 )
            break;
          if ( (unsigned int)v15 <= 5 )
            *(_WORD *)(a3 + 356) |= HidP_TranslateUsageToDownFlag[v15];
          v12 = *(unsigned __int16 *)(v8 + 28);
          ++v14;
          ++v13;
        }
        while ( v14 < v12 );
        v16 = *(unsigned __int16 **)(v8 + 128);
        v17 = 0;
        if ( (_WORD)v12 )
        {
          do
          {
            v18 = *v16;
            if ( !(_WORD)v18 )
              break;
            if ( (unsigned int)v18 <= 5 )
              *(_WORD *)(a3 + 356) |= HidP_TranslateUsageToUpFlag[v18];
            ++v17;
            ++v16;
          }
          while ( v17 < *(unsigned __int16 *)(v8 + 28) );
        }
      }
      v19 = *(_QWORD *)(v8 + 120);
      *(_QWORD *)(v8 + 120) = *(_QWORD *)(v8 + 112);
      *(_QWORD *)(v8 + 112) = v19;
    }
    if ( (*(_DWORD *)(a3 + 120) & 2) == 0
      && HidP_GetScaledUsageValue(
           HidP_Input,
           1u,
           0,
           0x30u,
           (PLONG)(a3 + 364),
           *(PHIDP_PREPARSED_DATA *)(v8 + 32),
           *(PCHAR *)(v8 + 104),
           *(unsigned __int16 *)(v8 + 44)) == -1072627706 )
    {
      *(_DWORD *)(a3 + 120) |= 2u;
      v37 = 1;
      *(_DWORD *)(v8 + 8) = (1 << (*(_WORD *)v8 - 1)) - 1;
    }
    if ( (*(_DWORD *)(a3 + 120) & 2) != 0 )
    {
      UsageValue = 0;
      if ( HidP_GetUsageValue(
             HidP_Input,
             1u,
             0,
             0x30u,
             &UsageValue,
             *(PHIDP_PREPARSED_DATA *)(v8 + 32),
             *(PCHAR *)(v8 + 104),
             *(unsigned __int16 *)(v8 + 44)) >= 0 )
        *v10 = UsageValue | ((UsageValue & (*(_DWORD *)(v8 + 8) + 1)) != 0 ? ~*(_DWORD *)(v8 + 8) : 0);
    }
    if ( *(_BYTE *)(v8 + 16) )
    {
      v20 = *(int *)(v8 + 8);
      if ( (_DWORD)v20 )
        *v10 = 0xFFFFLL * (int)*v10 / v20;
    }
    if ( (*(_DWORD *)(a3 + 120) & 4) == 0
      && HidP_GetScaledUsageValue(
           HidP_Input,
           1u,
           0,
           0x31u,
           (PLONG)(a3 + 368),
           *(PHIDP_PREPARSED_DATA *)(v8 + 32),
           *(PCHAR *)(v8 + 104),
           *(unsigned __int16 *)(v8 + 44)) == -1072627706 )
    {
      *(_DWORD *)(a3 + 120) |= 4u;
      v37 = 1;
      *(_DWORD *)(v8 + 12) = (1 << (*(_WORD *)(v8 + 2) - 1)) - 1;
    }
    if ( (*(_DWORD *)(a3 + 120) & 4) != 0 )
    {
      UsageValue = 0;
      if ( HidP_GetUsageValue(
             HidP_Input,
             1u,
             0,
             0x31u,
             &UsageValue,
             *(PHIDP_PREPARSED_DATA *)(v8 + 32),
             *(PCHAR *)(v8 + 104),
             *(unsigned __int16 *)(v8 + 44)) >= 0 )
        *v11 = UsageValue | ((UsageValue & (*(_DWORD *)(v8 + 12) + 1)) != 0 ? ~*(_DWORD *)(v8 + 12) : 0);
    }
    if ( *(_BYTE *)(v8 + 16) )
      *v11 = 0xFFFFLL * (int)*v11 / *(int *)(v8 + 12);
    if ( !*(_BYTE *)(v8 + 17) )
    {
      v21 = *(_DWORD *)(a3 + 120);
      UsageValue = 0;
      if ( (v21 & 8) == 0 )
      {
        ScaledUsageValue = HidP_GetScaledUsageValue(
                             HidP_Input,
                             *(_WORD *)(v8 + 18),
                             0,
                             *(_WORD *)(v8 + 20),
                             (PLONG)&UsageValue,
                             *(PHIDP_PREPARSED_DATA *)(v8 + 32),
                             *(PCHAR *)(v8 + 104),
                             *(unsigned __int16 *)(v8 + 44));
        if ( ScaledUsageValue == -1072627708 )
        {
          *(_BYTE *)(v8 + 17) = 1;
        }
        else if ( ScaledUsageValue == -1072627706 )
        {
          *(_DWORD *)(a3 + 120) |= 8u;
          v37 = 1;
        }
      }
      if ( (*(_DWORD *)(a3 + 120) & 8) != 0
        && HidP_GetUsageValue(
             HidP_Input,
             *(_WORD *)(v8 + 18),
             0,
             *(_WORD *)(v8 + 20),
             &UsageValue,
             *(PHIDP_PREPARSED_DATA *)(v8 + 32),
             *(PCHAR *)(v8 + 104),
             *(unsigned __int16 *)(v8 + 44)) >= 0 )
      {
        UsageValue |= (UsageValue & (1 << (*(_WORD *)(v8 + 4) - 1))) != 0 ? -1 << (*(_WORD *)(v8 + 4) - 1) : 0;
      }
      if ( UsageValue )
      {
        v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 64));
        v24 = (int)(*(_DWORD *)(a3 + 76) * UsageValue) / *(_DWORD *)(a3 + 100);
        UsageValue = v24;
        if ( *(_BYTE *)(a3 + 48) )
          LOWORD(v24) = -(__int16)v24;
        *(_WORD *)(a3 + 358) = v24;
        *(_WORD *)(a3 + 356) |= 0x400u;
        KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 64), v23);
      }
      else
      {
        *(_WORD *)(a3 + 358) = 0;
      }
    }
    if ( *(_BYTE *)(v8 + 22) )
      goto LABEL_83;
    v25 = *(_DWORD *)(a3 + 120);
    UsageValue = 0;
    if ( (v25 & 0x10) == 0 )
    {
      v26 = HidP_GetScaledUsageValue(
              HidP_Input,
              *(_WORD *)(v8 + 24),
              0,
              *(_WORD *)(v8 + 26),
              (PLONG)&UsageValue,
              *(PHIDP_PREPARSED_DATA *)(v8 + 32),
              *(PCHAR *)(v8 + 104),
              *(unsigned __int16 *)(v8 + 44));
      if ( v26 == -1072627708 )
      {
        *(_BYTE *)(v8 + 22) = 1;
      }
      else if ( v26 == -1072627706 )
      {
        *(_DWORD *)(a3 + 120) |= 0x10u;
        v37 = 1;
      }
    }
    if ( (*(_DWORD *)(a3 + 120) & 0x10) != 0
      && HidP_GetUsageValue(
           HidP_Input,
           *(_WORD *)(v8 + 24),
           0,
           *(_WORD *)(v8 + 26),
           &UsageValue,
           *(PHIDP_PREPARSED_DATA *)(v8 + 32),
           *(PCHAR *)(v8 + 104),
           *(unsigned __int16 *)(v8 + 44)) >= 0 )
    {
      UsageValue |= (UsageValue & (1 << (*(_WORD *)(v8 + 6) - 1))) != 0 ? -1 << (*(_WORD *)(v8 + 6) - 1) : 0;
    }
    if ( _bittest16((const signed __int16 *)(a3 + 356), 0xAu) )
    {
      if ( !UsageValue )
      {
LABEL_83:
        v31 = KfRaiseIrql(2u);
        (*(void (__fastcall **)(_QWORD, __int64, __int64, _DWORD *))(a3 + 232))(
          *(_QWORD *)(a3 + 224),
          a3 + 352,
          a3 + 376,
          v35);
        KeLowerIrql(v31);
        if ( v37 )
        {
          ErrorLogEntry = IoAllocateErrorLogEntry(*(PVOID *)(*(_QWORD *)a3 + 8LL), 0x30u);
          if ( ErrorLogEntry )
          {
            *ErrorLogEntry = 0;
            ErrorLogEntry[1] = 0;
            ErrorLogEntry[2] = 0;
            *((_DWORD *)ErrorLogEntry + 3) = -2147155967;
            *((_DWORD *)ErrorLogEntry + 5) = -2147155967;
            *((_WORD *)ErrorLogEntry + 2) = 0;
            IoWriteErrorLogEntry(ErrorLogEntry);
          }
        }
        v6 = a1;
        goto LABEL_87;
      }
      v27 = KfRaiseIrql(2u);
      (*(void (__fastcall **)(_QWORD, __int64, __int64, _DWORD *))(a3 + 232))(
        *(_QWORD *)(a3 + 224),
        a3 + 352,
        a3 + 376,
        v35);
      KeLowerIrql(v27);
      *(_WORD *)(a3 + 356) = 2048;
      if ( *(_BYTE *)(a3 + 49) )
        v28 = -(__int16)UsageValue;
      else
        v28 = UsageValue;
      *(_WORD *)(a3 + 358) = v28;
      if ( !*(_BYTE *)(v8 + 16) )
      {
        *v10 = 0;
        *v11 = 0;
      }
    }
    if ( UsageValue )
    {
      v29 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 64));
      v30 = (int)(*(_DWORD *)(a3 + 84) * UsageValue) / *(_DWORD *)(a3 + 104);
      UsageValue = v30;
      if ( *(_BYTE *)(a3 + 49) )
        LOWORD(v30) = -(__int16)v30;
      *(_WORD *)(a3 + 356) |= 0x800u;
      *(_WORD *)(a3 + 358) = v30;
      KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 64), v29);
    }
    goto LABEL_83;
  }
LABEL_87:
  if ( v38 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_q(WPP_GLOBAL_Control->DeviceExtension, v7, a3, 12, UsageLength, v6);
    MouHid_StartRead(a3);
  }
LABEL_9:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      2,
      13,
      (__int64)WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140002ff0  mov     [rsp-40h+arg_0], rcx
0x140002ff5  push    rbp
0x140002ff6  push    rbx
0x140002ff7  push    rsi
0x140002ff8  push    rdi
0x140002ff9  push    r12
0x140002ffb  push    r13
0x140002ffd  push    r14
0x140002fff  push    r15
0x140003001  mov     rbp, rsp
0x140003004  sub     rsp, 58h
0x140003008  xor     r12d, r12d
0x14000300b  mov     rdi, r8
0x14000300e  mov     [rbp+UsageValue], r12d
0x140003012  mov     r14, rdx
0x140003015  mov     [rbp+var_14], r12d
0x140003019  mov     r15, rcx
0x14000301c  mov     [rbp+var_18], r12d
0x140003020  lea     r13, WPP_RECORDER_INITIALIZED
0x140003027  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000302e  lea     rax, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003035  jz      short loc_14000305F
0x140003037  mov     rcx, cs:WPP_GLOBAL_Control
0x14000303e  cmp     [rcx+48h], r12w
0x140003043  jz      short loc_14000305F
0x140003045  mov     rcx, [rcx+40h]
0x140003049  lea     r9d, [r12+0Ah]
0x14000304e  lea     r8d, [r12+2]
0x140003053  mov     [rsp+58h+UsageLength], rax
0x140003058  mov     dl, 5
0x14000305a  call    WPP_RECORDER_SF_
0x14000305f  mov     edx, [r14+30h]
0x140003063  mov     ecx, 3
0x140003068  mov     rsi, [rdi+0D8h]
0x14000306f  lea     ebx, [rcx-2]
0x140003072  mov     eax, ebx
0x140003074  lock cmpxchg [rdi+1Ch], ecx
0x140003079  setnz   [rbp+arg_10]
0x14000307d  mov     ecx, r12d; ReportType
0x140003080  xor     eax, eax
0x140003082  lock cmpxchg [rdi+18h], ecx
0x140003087  jnz     loc_140003142
0x14000308d  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140003094  jz      short loc_1400030B7
0x140003096  mov     rcx, cs:WPP_GLOBAL_Control
0x14000309d  mov     eax, [rdi+18h]
0x1400030a0  mov     [rsp+58h+ReportLength], eax
0x1400030a4  mov     [rsp+58h+Report], r14
0x1400030a9  mov     rcx, [rcx+40h]
0x1400030ad  mov     [rsp+58h+PreparsedData], r15
0x1400030b2  call    WPP_RECORDER_SF_qql
0x1400030b7  xor     r14d, r14d
0x1400030ba  cmp     [rbp+arg_10], r14b
0x1400030be  jz      short loc_1400030F3
0x1400030c0  lea     rcx, [rdi+90h]; Event
0x1400030c7  xor     r8d, r8d; Wait
0x1400030ca  xor     edx, edx; Increment
0x1400030cc  call    cs:__imp_KeSetEvent
0x1400030d3  nop     dword ptr [rax+rax+00h]
0x1400030d8  mov     rdx, [rdi+70h]; Tag
0x1400030dc  lea     rcx, [rdi+0F0h]; RemoveLock
0x1400030e3  lea     r8d, [r14+20h]; RemlockSize
0x1400030e7  call    cs:__imp_IoReleaseRemoveLockEx
0x1400030ee  nop     dword ptr [rax+rax+00h]
0x1400030f3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400030fa  jz      short loc_14000312B
0x1400030fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140003103  cmp     [rcx+48h], r14w
0x140003108  jz      short loc_14000312B
0x14000310a  mov     rcx, [rcx+40h]
0x14000310e  lea     rax, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003115  mov     r9d, 0Dh
0x14000311b  mov     [rsp+58h+UsageLength], rax
0x140003120  mov     dl, 5
0x140003122  lea     r8d, [r9-0Bh]
0x140003126  call    WPP_RECORDER_SF_
0x14000312b  mov     eax, 0C0000016h
0x140003130  add     rsp, 58h
0x140003134  pop     r15
0x140003136  pop     r14
0x140003138  pop     r13
0x14000313a  pop     r12
0x14000313c  pop     rdi
0x14000313d  pop     rsi
0x14000313e  pop     rbx
0x14000313f  pop     rbp
0x140003140  retn
0x140003142  cmp     edx, 0C0000056h
0x140003148  jz      loc_1400030B7
0x14000314e  cmp     edx, 0C0000061h
0x140003154  jz      loc_1400030B7
0x14000315a  cmp     edx, 0C000009Dh
0x140003160  jz      loc_1400030B7
0x140003166  cmp     edx, 0C0000120h
0x14000316c  jz      loc_1400030B7
0x140003172  xor     r14d, r14d
0x140003175  test    edx, edx
0x140003177  jnz     loc_1400037F2
0x14000317d  mov     [rdi+164h], r14d
0x140003184  lea     r13, [rdi+16Ch]
0x14000318b  mov     [r13+0], r14d
0x14000318f  lea     r12, [rdi+170h]
0x140003196  mov     [r12], r14d
0x14000319a  lea     edx, [r14+9]; UsagePage
0x14000319e  movzx   eax, word ptr [rsi+1Ch]
0x1400031a2  xor     r8d, r8d; LinkCollection
0x1400031a5  mov     [rbp+var_18], eax
0x1400031a8  movzx   eax, word ptr [rsi+2Ch]
0x1400031ac  mov     r9, [rsi+70h]; UsageList
0x1400031b0  mov     [rsp+58h+ReportLength], eax; ReportLength
0x1400031b4  mov     rax, [rsi+68h]
0x1400031b8  mov     [rsp+58h+Report], rax; Report
0x1400031bd  mov     rax, [rsi+20h]
0x1400031c1  mov     [rsp+58h+PreparsedData], rax; PreparsedData
0x1400031c6  lea     rax, [rbp+var_18]
0x1400031ca  mov     [rsp+58h+UsageLength], rax; UsageLength
0x1400031cf  mov     [rbp+arg_8], r14b
0x1400031d3  call    cs:__imp_HidP_GetUsages
0x1400031da  nop     dword ptr [rax+rax+00h]
0x1400031df  test    eax, eax
0x1400031e1  js      loc_1400032AE
0x1400031e7  movzx   eax, word ptr [rsi+1Ch]
0x1400031eb  mov     r9, [rsi+88h]; MakeUsageList
0x1400031f2  mov     r8, [rsi+80h]; BreakUsageList
0x1400031f9  mov     rdx, [rsi+70h]; CurrentUsageList
0x1400031fd  mov     rcx, [rsi+78h]; PreviousUsageList
0x140003201  mov     dword ptr [rsp+58h+UsageLength], eax; UsageListLength
0x140003205  call    cs:__imp_HidP_UsageListDifference
0x14000320c  nop     dword ptr [rax+rax+00h]
0x140003211  test    eax, eax
0x140003213  js      loc_1400032AE
0x140003219  movzx   ecx, word ptr [rsi+1Ch]
0x14000321d  cmp     r14w, cx
0x140003221  jnb     short loc_14000329E
0x140003223  mov     rdx, [rsi+88h]
0x14000322a  lea     r9, cs:140000000h
0x140003231  mov     r8d, r14d
0x140003234  movzx   eax, word ptr [rdx]
0x140003237  test    ax, ax
0x14000323a  jz      short loc_140003261
0x14000323c  cmp     eax, 5
0x14000323f  ja      short loc_140003251
0x140003241  movzx   eax, ds:rva HidP_TranslateUsageToDownFlag[r9+rax*2]
0x14000324a  or      [rdi+164h], ax
0x140003251  movzx   ecx, word ptr [rsi+1Ch]
0x140003255  add     r8d, ebx
0x140003258  add     rdx, 2
0x14000325c  cmp     r8d, ecx
0x14000325f  jb      short loc_140003234
0x140003261  mov     rdx, [rsi+80h]
0x140003268  mov     r8d, r14d
0x14000326b  cmp     r14w, cx
0x14000326f  jnb     short loc_14000329E
0x140003271  movzx   eax, word ptr [rdx]
0x140003274  test    ax, ax
0x140003277  jz      short loc_14000329E
0x140003279  cmp     eax, 5
0x14000327c  ja      short loc_14000328E
0x14000327e  movzx   eax, ds:rva HidP_TranslateUsageToUpFlag[r9+rax*2]
0x140003287  or      [rdi+164h], ax
0x14000328e  movzx   eax, word ptr [rsi+1Ch]
0x140003292  add     r8d, ebx
0x140003295  add     rdx, 2
0x140003299  cmp     r8d, eax
0x14000329c  jb      short loc_140003271
0x14000329e  mov     rcx, [rsi+78h]
0x1400032a2  mov     rax, [rsi+70h]
0x1400032a6  mov     [rsi+78h], rax
0x1400032aa  mov     [rsi+70h], rcx
0x1400032ae  mov     eax, [rdi+78h]
0x1400032b1  test    al, 2
0x1400032b3  jnz     short loc_140003309
0x1400032b5  movzx   eax, word ptr [rsi+2Ch]
0x1400032b9  mov     r9d, 30h ; '0'; Usage
0x1400032bf  mov     [rsp+58h+ReportLength], eax; ReportLength
0x1400032c3  xor     r8d, r8d; LinkCollection
0x1400032c6  mov     rax, [rsi+68h]
0x1400032ca  mov     edx, ebx; UsagePage
0x1400032cc  mov     [rsp+58h+Report], rax; Report
0x1400032d1  xor     ecx, ecx; ReportType
0x1400032d3  mov     rax, [rsi+20h]
0x1400032d7  mov     [rsp+58h+PreparsedData], rax; PreparsedData
0x1400032dc  mov     [rsp+58h+UsageLength], r13; UsageValue
0x1400032e1  call    cs:__imp_HidP_GetScaledUsageValue
0x1400032e8  nop     dword ptr [rax+rax+00h]
0x1400032ed  cmp     eax, 0C0110006h
0x1400032f2  jnz     short loc_140003309
0x1400032f4  or      dword ptr [rdi+78h], 2
0x1400032f8  mov     eax, ebx
0x1400032fa  movzx   ecx, word ptr [rsi]
0x1400032fd  sub     ecx, ebx
0x1400032ff  mov     [rbp+arg_8], bl
0x140003302  shl     eax, cl
0x140003304  sub     eax, ebx
0x140003306  mov     [rsi+8], eax
0x140003309  mov     eax, [rdi+78h]
0x14000330c  test    al, 2
0x14000330e  jz      short loc_14000336C
0x140003310  mov     [rbp+UsageValue], r14d
0x140003314  mov     r9d, 30h ; '0'; Usage
0x14000331a  movzx   eax, word ptr [rsi+2Ch]
0x14000331e  xor     r8d, r8d; LinkCollection
0x140003321  mov     [rsp+58h+ReportLength], eax; ReportLength
0x140003325  mov     edx, ebx; UsagePage
0x140003327  mov     rax, [rsi+68h]
0x14000332b  xor     ecx, ecx; ReportType
0x14000332d  mov     [rsp+58h+Report], rax; Report
0x140003332  mov     rax, [rsi+20h]
0x140003336  mov     [rsp+58h+PreparsedData], rax; PreparsedData
0x14000333b  lea     rax, [rbp+UsageValue]
0x14000333f  mov     [rsp+58h+UsageLength], rax; UsageValue
0x140003344  call    cs:__imp_HidP_GetUsageValue
0x14000334b  nop     dword ptr [rax+rax+00h]
0x140003350  test    eax, eax
0x140003352  js      short loc_14000336C
0x140003354  mov     ecx, [rsi+8]
0x140003357  lea     eax, [rcx+1]
0x14000335a  not     ecx
0x14000335c  and     eax, [rbp+UsageValue]
0x14000335f  neg     eax
0x140003361  sbb     eax, eax
0x140003363  and     eax, ecx
0x140003365  or      eax, [rbp+UsageValue]
0x140003368  mov     [r13+0], eax
0x14000336c  cmp     [rsi+10h], r14b
0x140003370  jz      short loc_14000338E
0x140003372  movsxd  rcx, dword ptr [rsi+8]
0x140003376  test    ecx, ecx
0x140003378  jz      short loc_14000338E
0x14000337a  movsxd  rax, dword ptr [r13+0]
0x14000337e  imul    rax, 0FFFFh
0x140003385  cqo
0x140003387  idiv    rcx
0x14000338a  mov     [r13+0], eax
0x14000338e  mov     eax, [rdi+78h]
0x140003391  mov     r15d, 31h ; '1'
0x140003397  test    al, 4
0x140003399  jnz     short loc_1400033ED
0x14000339b  movzx   eax, word ptr [rsi+2Ch]
0x14000339f  mov     r9d, r15d; Usage
0x1400033a2  mov     [rsp+58h+ReportLength], eax; ReportLength
0x1400033a6  xor     r8d, r8d; LinkCollection
0x1400033a9  mov     rax, [rsi+68h]
0x1400033ad  mov     edx, ebx; UsagePage
0x1400033af  mov     [rsp+58h+Report], rax; Report
0x1400033b4  xor     ecx, ecx; ReportType
0x1400033b6  mov     rax, [rsi+20h]
0x1400033ba  mov     [rsp+58h+PreparsedData], rax; PreparsedData
0x1400033bf  mov     [rsp+58h+UsageLength], r12; UsageValue
0x1400033c4  call    cs:__imp_HidP_GetScaledUsageValue
0x1400033cb  nop     dword ptr [rax+rax+00h]
0x1400033d0  cmp     eax, 0C0110006h
0x1400033d5  jnz     short loc_1400033ED
0x1400033d7  or      dword ptr [rdi+78h], 4
0x1400033db  mov     eax, ebx
0x1400033dd  movzx   ecx, word ptr [rsi+2]
0x1400033e1  sub     ecx, ebx
0x1400033e3  mov     [rbp+arg_8], bl
0x1400033e6  shl     eax, cl
0x1400033e8  sub     eax, ebx
0x1400033ea  mov     [rsi+0Ch], eax
0x1400033ed  mov     eax, [rdi+78h]
0x1400033f0  test    al, 4
0x1400033f2  jz      short loc_14000344D
0x1400033f4  mov     [rbp+UsageValue], r14d
0x1400033f8  mov     r9d, r15d; Usage
0x1400033fb  movzx   eax, word ptr [rsi+2Ch]
0x1400033ff  xor     r8d, r8d; LinkCollection
0x140003402  mov     [rsp+58h+ReportLength], eax; ReportLength
0x140003406  mov     edx, ebx; UsagePage
0x140003408  mov     rax, [rsi+68h]
0x14000340c  xor     ecx, ecx; ReportType
0x14000340e  mov     [rsp+58h+Report], rax; Report
0x140003413  mov     rax, [rsi+20h]
0x140003417  mov     [rsp+58h+PreparsedData], rax; PreparsedData
0x14000341c  lea     rax, [rbp+UsageValue]
0x140003420  mov     [rsp+58h+UsageLength], rax; UsageValue
0x140003425  call    cs:__imp_HidP_GetUsageValue
0x14000342c  nop     dword ptr [rax+rax+00h]
0x140003431  test    eax, eax
0x140003433  js      short loc_14000344D
0x140003435  mov     ecx, [rsi+0Ch]
0x140003438  lea     eax, [rcx+1]
0x14000343b  not     ecx
0x14000343d  and     eax, [rbp+UsageValue]
0x140003440  neg     eax
0x140003442  sbb     eax, eax
0x140003444  and     eax, ecx
0x140003446  or      eax, [rbp+UsageValue]
0x140003449  mov     [r12], eax
0x14000344d  cmp     [rsi+10h], r14b
0x140003451  jz      short loc_14000346B
0x140003453  movsxd  rax, dword ptr [r12]
0x140003457  movsxd  rcx, dword ptr [rsi+0Ch]
0x14000345b  imul    rax, 0FFFFh
0x140003462  cqo
0x140003464  idiv    rcx
0x140003467  mov     [r12], eax
0x14000346b  or      r15d, 0FFFFFFFFh
0x14000346f  cmp     [rsi+11h], r14b
  ... truncated ...
```

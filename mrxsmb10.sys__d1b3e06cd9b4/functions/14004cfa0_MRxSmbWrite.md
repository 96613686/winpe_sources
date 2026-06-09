# MRxSmbWrite

- ea: `0x14004cfa0`
- end: `0x14004d7df`
- name: `MRxSmbWrite`
- size: `2111`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e01c`
- `0x14000ebd8`
- `0x14001086c`
- `0x1400159f4`
- `0x140015a50`
- `0x140046120`
- `0x14004cfa0`
- `0x14004d7f0`
- `0x14004dd50`
- `0x14004e4f0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14004d76d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004d76d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d4ef`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d504`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d650`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d6ae`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d4ef`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d504`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d650`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004d6ae`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004d373`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004d5a6`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004d373`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004d5a6`
- `ntoskrnl!KeInitializeEvent` at `0x14004d1fc`
- `ntoskrnl!KeInitializeEvent` at `0x14004d1fc`
- `ntoskrnl!ExAllocatePool2` at `0x14004d1ba`
- `ntoskrnl!ExAllocatePool2` at `0x14004d1ba`
- `rdbss!RxIndicateChangeOfOplockStateForTarget` at `0x14004d0cd`
- `rdbss!RxIndicateChangeOfOplockStateForTarget` at `0x14004d0cd`
- `rdbss!RxLowIoGetBufferAddress` at `0x14004d180`
- `rdbss!RxLowIoGetBufferAddress` at `0x14004d217`
- `rdbss!RxLowIoGetBufferAddress` at `0x14004d259`
- `rdbss!RxLowIoGetBufferAddress` at `0x14004d180`
- `rdbss!RxLowIoGetBufferAddress` at `0x14004d217`
- `rdbss!RxLowIoGetBufferAddress` at `0x14004d259`

## pseudocode

```c
__int64 __fastcall MRxSmbWrite(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // r12
  bool v5; // di
  __int64 v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // rbp
  unsigned int v10; // ebx
  __int64 v11; // rbp
  int v12; // r13d
  unsigned int v13; // r15d
  __int64 Pool2; // rax
  __int64 v15; // r14
  char v16; // di
  __int64 v17; // rcx
  __int64 BufferAddress; // rax
  unsigned int OrdinaryExchange; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // ebx
  union _LARGE_INTEGER *v23; // rbp
  __int128 *v24; // rcx
  __int64 v25; // rdx
  union _LARGE_INTEGER *v26; // rax
  __int128 v27; // xmm0
  union _LARGE_INTEGER v28; // r8
  int v29; // eax
  unsigned int v30; // edi
  char v31; // bl
  __int64 v32; // r9
  LONGLONG v33; // rdx
  __int64 i; // r9
  int v35; // edx
  LONG v36; // eax
  __int64 v37; // rdx
  int v38; // esi
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // r8
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-78h]
  PVOID pContext; // [rsp+30h] [rbp-68h] BYREF
  struct _KEVENT Event; // [rsp+38h] [rbp-60h] BYREF
  char v46; // [rsp+A8h] [rbp+10h]
  bool v47; // [rsp+B0h] [rbp+18h]
  __int64 v48; // [rsp+B8h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 64);
  v3 = *(_QWORD *)(a1 + 56);
  v48 = v2;
  v47 = (*(_DWORD *)(a1 + 120) & 0x1000) != 0;
  pContext = 0;
  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids);
    v2 = v48;
  }
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 120LL) + 77LL) == 1
    && *(_DWORD *)(*(_QWORD *)(a1 + 48) + 8LL) > 0xFFFFu )
  {
    return 3221225990LL;
  }
  v5 = 0;
  v46 = 1;
  if ( *(_WORD *)v3 == 0xEC22 )
    *(_DWORD *)(*(_QWORD *)(v3 + 136) + 4LL) |= 2u;
  v6 = *(_QWORD *)(v2 + 32);
  if ( v6 )
    v7 = *(_QWORD *)(v6 + 48);
  else
    v7 = 0;
  v8 = *(_QWORD *)(v6 + 40);
  v9 = *(_QWORD *)(v8 + 40);
  if ( *(_BYTE *)(v7 + 10) == 3 && (*(_DWORD *)(a1 + 536) & 1) == 0 )
  {
    RxIndicateChangeOfOplockStateForTarget(*(_QWORD *)(*(_QWORD *)(v8 + 32) + 32LL), *(_QWORD *)(v2 + 32), 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids, v6);
    v2 = v48;
  }
  if ( *(_BYTE *)(*(_QWORD *)(v3 + 120) + 77LL) == 1 )
  {
    v46 = 0;
    v5 = *(_DWORD *)(*(_QWORD *)(v2 + 80) + 4LL) != 0;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(v9 + 88) + 420LL) & 0x40000000) == 0 )
    v46 = 0;
  v10 = *(_DWORD *)(*(_QWORD *)(v9 + 104) + 116LL);
  if ( v5 )
    v10 -= 2;
  v11 = a1;
  v12 = *(_DWORD *)(a1 + 568) / v10;
  if ( *(_DWORD *)(a1 + 568) % v10 || !*(_DWORD *)(a1 + 568) )
    ++v12;
  if ( !RxLowIoGetBufferAddress((PRX_CONTEXT)a1) && *(_DWORD *)(a1 + 568) )
  {
    v13 = -1073741670;
    goto LABEL_103;
  }
  v13 = 0;
  Pool2 = ExAllocatePool2(64, (unsigned int)(4 * v12 + 384), 2001890643);
  v15 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 8) = a1;
    v16 = 1;
    *(_DWORD *)(Pool2 + 336) = v10;
    *(_DWORD *)(Pool2 + 328) = v12;
    if ( (*(_DWORD *)(a1 + 120) & 0x1000) == 0 )
    {
      KeInitializeEvent(&Event, SynchronizationEvent, 0);
      *(_QWORD *)(v15 + 352) = &Event;
    }
    *(_QWORD *)v15 = RxLowIoGetBufferAddress((PRX_CONTEXT)a1);
    v17 = *(_QWORD *)(a1 + 560);
    *(_QWORD *)(v15 + 32) = v17;
    *(_DWORD *)(v15 + 16) = *(_DWORD *)(a1 + 568);
    if ( v17 == -1 )
    {
      *(_BYTE *)(v15 + 46) = 1;
      *(_QWORD *)(v15 + 32) = *(_QWORD *)(v7 + 88);
    }
    if ( *(_QWORD *)(a1 + 544) )
      BufferAddress = (__int64)RxLowIoGetBufferAddress((PRX_CONTEXT)a1);
    else
      BufferAddress = 1;
    *(_QWORD *)v15 = BufferAddress;
    v13 = 259;
    *(_DWORD *)(v15 + 344) = 1;
    *(_DWORD *)(v15 + 28) = 0;
    *(_WORD *)(v15 + 44) = 0;
    *(_DWORD *)(v15 + 376) = 0;
    while ( 1 )
    {
      OrdinaryExchange = _SmbPseCreateOrdinaryExchange(
                           v11,
                           *(_QWORD *)(*(_QWORD *)(v48 + 32) + 40LL),
                           15,
                           (__int64)SmbPseExchangeStart_Write,
                           (__int64)Timeout,
                           (__int64 *)&pContext);
      v22 = OrdinaryExchange;
      if ( OrdinaryExchange )
      {
        if ( v16 )
          *(_DWORD *)(v15 + 360) = OrdinaryExchange;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids);
          goto LABEL_98;
        }
LABEL_101:
        MRxSmbDereferenceGlobalReadWrite((PVOID)v15, v20, v21);
        if ( !v47 )
        {
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          v13 = *(_DWORD *)(v11 + 176);
        }
        break;
      }
      v23 = (union _LARGE_INTEGER *)pContext;
      v24 = (__int128 *)v15;
      v25 = 3;
      *((_QWORD *)pContext + 53) = SmbPseExchangeStart_Write;
      v26 = v23 + 59;
      v23[107].QuadPart = v15;
      do
      {
        v26 += 16;
        v27 = *v24;
        v24 += 8;
        *(_OWORD *)&v26[-16].LowPart = v27;
        *(_OWORD *)&v26[-14].LowPart = *(v24 - 7);
        *(_OWORD *)&v26[-12].LowPart = *(v24 - 6);
        *(_OWORD *)&v26[-10].LowPart = *(v24 - 5);
        *(_OWORD *)&v26[-8].LowPart = *(v24 - 4);
        *(_OWORD *)&v26[-6].LowPart = *(v24 - 3);
        *(_OWORD *)&v26[-4].LowPart = *(v24 - 2);
        *(_OWORD *)&v26[-2].LowPart = *(v24 - 1);
        --v25;
      }
      while ( v25 );
      if ( *(_BYTE *)(*(_QWORD *)(v3 + 120) + 77LL) == 1 && *(_DWORD *)(*(_QWORD *)(v48 + 80) + 4LL) )
        BYTE2(v23[48].u.LowPart) |= 0x80u;
      ExAcquireFastMutex(&MRxSmbReadWriteMutex);
      v28 = v23[107];
      v29 = *(_DWORD *)(v28.QuadPart + 360);
      if ( v29 )
      {
        v30 = *(_DWORD *)(v28.QuadPart + 332);
        v31 = 0;
        if ( v29 != -1063771909 )
          goto LABEL_64;
        v32 = 0;
        *(_QWORD *)(a1 + 184) = 0;
        *(_DWORD *)(v28.QuadPart + 360) = 0;
        for ( v23[6].LowPart = 0; (unsigned int)v32 < *(_DWORD *)(v28.QuadPart + 328); v32 = (unsigned int)(v32 + 1) )
        {
          v33 = v28.QuadPart + 4 * v32;
          if ( *(_DWORD *)(v33 + 380) == 1 )
          {
            *(_DWORD *)(v33 + 380) = 3;
          }
          else if ( *(_DWORD *)(v33 + 380) == 2 )
          {
            *(_DWORD *)(v33 + 380) = 0;
          }
        }
      }
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= *(_DWORD *)(v28.QuadPart + 328) )
        {
          ExReleaseFastMutex(&MRxSmbReadWriteMutex);
          goto LABEL_92;
        }
        if ( !*(_DWORD *)(v28.QuadPart + 4 * i + 380) )
          break;
      }
      *(_DWORD *)(v28.QuadPart + 4 * i + 380) = 1;
      v23[63].QuadPart = *(_QWORD *)(v28.QuadPart + 32)
                       + (unsigned int)i * (unsigned __int64)*(unsigned int *)(v28.QuadPart + 336);
      if ( (_DWORD)i != *(_DWORD *)(v28.QuadPart + 328) - 1
        || (v35 = *(_DWORD *)(v28.QuadPart + 16) % *(_DWORD *)(v28.QuadPart + 336)) == 0 )
      {
        v35 = *(_DWORD *)(v28.QuadPart + 336);
        if ( !*(_DWORD *)(v28.QuadPart + 16) )
          v35 = 0;
      }
      v23[61].LowPart = v35;
      v36 = *(_DWORD *)(v28.QuadPart + 336) * i;
      v23[101].HighPart = i;
      v23[62].HighPart = v36;
      v30 = _InterlockedIncrement((volatile signed __int32 *)(v28.QuadPart + 332));
      v31 = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        Timeout = v23;
        WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids);
        ExReleaseFastMutex(&MRxSmbReadWriteMutex);
        goto LABEL_65;
      }
LABEL_64:
      ExReleaseFastMutex(&MRxSmbReadWriteMutex);
      if ( !v31 )
      {
LABEL_92:
        SmbPseFinalizeOrdinaryExchange((unsigned __int8 *)v23);
        v11 = a1;
        v22 = 259;
LABEL_98:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids, v22, v12);
        }
        goto LABEL_101;
      }
LABEL_65:
      v38 = v12;
      v39 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(v15 + 344));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          LODWORD(Timeout) = v39;
          WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 14, v39, v15, Timeout);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          LODWORD(Timeout) = v12;
          WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, v37, v39, v23);
        }
      }
      --v12;
      v22 = SmbCeInitiateExchange(v23);
      if ( v22 != 259 )
      {
        ExAcquireFastMutex(&MRxSmbReadWriteMutex);
        if ( v22 )
        {
          v12 = v38;
          *(_DWORD *)(v15 + 4LL * (unsigned int)v23[101].HighPart + 380) = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              16,
              WPP_ce2c64477360322a8496f3fa453cac86_Traceguids,
              (unsigned int)v23[101].HighPart);
          }
        }
        if ( !HIBYTE(v23[64].QuadPart) )
        {
          MRxSmbDereferenceGlobalReadWrite((PVOID)v15, v40, v41);
          v30 = _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 332), 0xFFFFFFFF);
        }
        --v30;
        if ( v22 == -1073741631 )
        {
          if ( v30 )
          {
            v22 = 0;
LABEL_84:
            ExReleaseFastMutex(&MRxSmbReadWriteMutex);
            SmbPseFinalizeOrdinaryExchange((unsigned __int8 *)v23);
            goto LABEL_85;
          }
        }
        else if ( !v22 )
        {
          goto LABEL_84;
        }
        if ( !*(_DWORD *)(v15 + 360) )
          *(_DWORD *)(v15 + 360) = v22;
        goto LABEL_84;
      }
LABEL_85:
      v11 = a1;
      if ( v30 < MaxNumOfExchangesForPipelineReadWrite )
      {
        v16 = 0;
        if ( v22 == -1069481983 || v46 && v12 && v22 == 259 )
          continue;
      }
      goto LABEL_98;
    }
  }
LABEL_103:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x14004cfa0  mov     [rsp+RxContext], rcx
0x14004cfa5  push    r12
0x14004cfa7  push    r14
0x14004cfa9  push    r15
0x14004cfab  sub     rsp, 80h
0x14004cfb2  test    dword ptr [rcx+78h], 1000h
0x14004cfb9  mov     r14, rcx
0x14004cfbc  mov     rdx, [rcx+40h]
0x14004cfc0  mov     r12, [rcx+38h]
0x14004cfc4  mov     [rsp+98h+arg_18], rdx
0x14004cfcc  jz      short loc_14004CFD8
0x14004cfce  mov     [rsp+98h+arg_10], 1
0x14004cfd6  jmp     short loc_14004CFE0
0x14004cfd8  mov     [rsp+98h+arg_10], 0
0x14004cfe0  xorps   xmm0, xmm0
0x14004cfe3  mov     [rsp+98h+pContext], 0
0x14004cfec  xor     eax, eax
0x14004cfee  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x14004cff3  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x14004cff8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004cfff  lea     r15, WPP_GLOBAL_Control
0x14004d006  cmp     rcx, r15
0x14004d009  jz      short loc_14004D031
0x14004d00b  test    dword ptr [rcx+2Ch], 400h
0x14004d012  jz      short loc_14004D031
0x14004d014  mov     rcx, [rcx+18h]
0x14004d018  lea     r8, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids
0x14004d01f  mov     edx, 0Bh
0x14004d024  call    WPP_SF_
0x14004d029  mov     rdx, [rsp+98h+arg_18]
0x14004d031  mov     rax, [r14+38h]
0x14004d035  mov     rcx, [rax+78h]
0x14004d039  cmp     byte ptr [rcx+4Dh], 1
0x14004d03d  jnz     short loc_14004D056
0x14004d03f  mov     rax, [r14+30h]
0x14004d043  cmp     dword ptr [rax+8], 0FFFFh
0x14004d04a  jbe     short loc_14004D056
0x14004d04c  mov     eax, 0C0000206h
0x14004d051  jmp     loc_14004D7D0
0x14004d056  mov     [rsp+98h+var_20], rbx
0x14004d05b  mov     eax, 0EC22h
0x14004d060  mov     [rsp+98h+var_28], rbp
0x14004d065  mov     [rsp+98h+var_30], rsi
0x14004d06a  mov     [rsp+98h+var_38], rdi
0x14004d06f  xor     dil, dil
0x14004d072  mov     [rsp+98h+var_40], r13
0x14004d077  mov     [rsp+98h+arg_8], 1
0x14004d07f  cmp     [r12], ax
0x14004d084  jnz     short loc_14004D092
0x14004d086  mov     rax, [r12+88h]
0x14004d08e  or      dword ptr [rax+4], 2
0x14004d092  mov     rbx, [rdx+20h]
0x14004d096  test    rbx, rbx
0x14004d099  jnz     short loc_14004D09F
0x14004d09b  xor     esi, esi
0x14004d09d  jmp     short loc_14004D0A3
0x14004d09f  mov     rsi, [rbx+30h]
0x14004d0a3  cmp     byte ptr [rsi+0Ah], 3
0x14004d0a7  mov     rcx, [rbx+28h]
0x14004d0ab  mov     rbp, [rcx+28h]
0x14004d0af  jnz     short loc_14004D10E
0x14004d0b1  mov     eax, [r14+218h]
0x14004d0b8  test    al, 1
0x14004d0ba  jnz     short loc_14004D10E
0x14004d0bc  mov     rcx, [rcx+20h]
0x14004d0c0  xor     r9d, r9d
0x14004d0c3  xor     r8d, r8d
0x14004d0c6  mov     rdx, rbx
0x14004d0c9  mov     rcx, [rcx+20h]
0x14004d0cd  call    cs:__imp_RxIndicateChangeOfOplockStateForTarget
0x14004d0d4  nop     dword ptr [rax+rax+00h]
0x14004d0d9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d0e0  cmp     rcx, r15
0x14004d0e3  jz      short loc_14004D106
0x14004d0e5  test    dword ptr [rcx+2Ch], 200h
0x14004d0ec  jz      short loc_14004D106
0x14004d0ee  mov     rcx, [rcx+18h]
0x14004d0f2  lea     r8, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids
0x14004d0f9  mov     edx, 0Ch
0x14004d0fe  mov     r9, rbx
0x14004d101  call    WPP_SF_q
0x14004d106  mov     rdx, [rsp+98h+arg_18]
0x14004d10e  mov     rax, [r12+78h]
0x14004d113  mov     ecx, 1
0x14004d118  cmp     [rax+4Dh], cl
0x14004d11b  jnz     short loc_14004D134
0x14004d11d  mov     rax, [rdx+50h]
0x14004d121  mov     [rsp+98h+arg_8], dil
0x14004d129  movzx   edi, dil
0x14004d12d  cmp     dword ptr [rax+4], 0
0x14004d131  cmovnz  edi, ecx
0x14004d134  mov     rax, [rbp+58h]
0x14004d138  test    dword ptr [rax+1A4h], 40000000h
0x14004d142  jnz     short loc_14004D14C
0x14004d144  mov     [rsp+98h+arg_8], 0
0x14004d14c  mov     rax, [rbp+68h]
0x14004d150  mov     ebx, [rax+74h]
0x14004d153  test    dil, dil
0x14004d156  jz      short loc_14004D15B
0x14004d158  add     ebx, 0FFFFFFFEh
0x14004d15b  mov     rbp, [rsp+98h+RxContext]
0x14004d163  xor     edx, edx
0x14004d165  mov     ecx, [rbp+238h]
0x14004d16b  mov     eax, ecx
0x14004d16d  div     ebx
0x14004d16f  mov     r13d, eax
0x14004d172  test    edx, edx
0x14004d174  jnz     short loc_14004D17A
0x14004d176  test    ecx, ecx
0x14004d178  jnz     short loc_14004D17D
0x14004d17a  inc     r13d
0x14004d17d  mov     rcx, rbp; RxContext
0x14004d180  call    cs:__imp_RxLowIoGetBufferAddress
0x14004d187  nop     dword ptr [rax+rax+00h]
0x14004d18c  test    rax, rax
0x14004d18f  jnz     short loc_14004D1A4
0x14004d191  cmp     [rbp+238h], eax
0x14004d197  jz      short loc_14004D1A4
0x14004d199  mov     r15d, 0C000009Ah
0x14004d19f  jmp     loc_14004D780
0x14004d1a4  lea     edx, ds:180h[r13*4]
0x14004d1ac  mov     ecx, 40h ; '@'
0x14004d1b1  mov     r8d, 77526D53h
0x14004d1b7  xor     r15d, r15d
0x14004d1ba  call    cs:__imp_ExAllocatePool2
0x14004d1c1  nop     dword ptr [rax+rax+00h]
0x14004d1c6  mov     r14, rax
0x14004d1c9  test    rax, rax
0x14004d1cc  jz      loc_14004D780
0x14004d1d2  mov     [rax+8], rbp
0x14004d1d6  mov     dil, 1
0x14004d1d9  mov     [rax+150h], ebx
0x14004d1df  mov     [rax+148h], r13d
0x14004d1e6  test    dword ptr [rbp+78h], 1000h
0x14004d1ed  jnz     short loc_14004D214
0x14004d1ef  xor     r8d, r8d; State
0x14004d1f2  lea     rcx, [rsp+98h+Event]; Event
0x14004d1f7  mov     edx, 1; Type
0x14004d1fc  call    cs:__imp_KeInitializeEvent
0x14004d203  nop     dword ptr [rax+rax+00h]
0x14004d208  lea     rax, [rsp+98h+Event]
0x14004d20d  mov     [r14+160h], rax
0x14004d214  mov     rcx, rbp; RxContext
0x14004d217  call    cs:__imp_RxLowIoGetBufferAddress
0x14004d21e  nop     dword ptr [rax+rax+00h]
0x14004d223  mov     [r14], rax
0x14004d226  mov     rcx, [rbp+230h]
0x14004d22d  mov     [r14+20h], rcx
0x14004d231  mov     eax, [rbp+238h]
0x14004d237  mov     [r14+10h], eax
0x14004d23b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14004d23f  jnz     short loc_14004D24D
0x14004d241  mov     [r14+2Eh], dil
0x14004d245  mov     rax, [rsi+58h]
0x14004d249  mov     [r14+20h], rax
0x14004d24d  cmp     [rbp+220h], r15
0x14004d254  jz      short loc_14004D267
0x14004d256  mov     rcx, rbp; RxContext
0x14004d259  call    cs:__imp_RxLowIoGetBufferAddress
0x14004d260  nop     dword ptr [rax+rax+00h]
0x14004d265  jmp     short loc_14004D26C
0x14004d267  mov     eax, 1
0x14004d26c  mov     [r14], rax
0x14004d26f  mov     r15d, 103h
0x14004d275  xor     eax, eax
0x14004d277  mov     dword ptr [r14+158h], 1
0x14004d282  mov     [r14+1Ch], eax
0x14004d286  mov     [r14+2Ch], ax
0x14004d28b  mov     [r14+178h], eax
0x14004d292  lea     rcx, SmbPseExchangeStart_Write
0x14004d299  nop     dword ptr [rax+00000000h]
0x14004d2a0  mov     rsi, [rsp+98h+arg_18]
0x14004d2a8  lea     rax, [rsp+98h+pContext]
0x14004d2ad  mov     r9, rcx
0x14004d2b0  mov     [rsp+98h+var_70], rax
0x14004d2b5  mov     r8d, 0Fh
0x14004d2bb  mov     rcx, rbp
0x14004d2be  mov     rdx, [rsi+20h]
0x14004d2c2  mov     rdx, [rdx+28h]
0x14004d2c6  call    __SmbPseCreateOrdinaryExchange
0x14004d2cb  mov     ebx, eax
0x14004d2cd  test    eax, eax
0x14004d2cf  jnz     loc_14004D6CF
0x14004d2d5  mov     rbp, [rsp+98h+pContext]
0x14004d2da  lea     rax, SmbPseExchangeStart_Write
0x14004d2e1  mov     rcx, r14
0x14004d2e4  mov     edx, 3
0x14004d2e9  mov     [rbp+1A8h], rax
0x14004d2f0  lea     rax, [rbp+1D8h]
0x14004d2f7  mov     [rbp+358h], r14
0x14004d2fe  lea     rax, [rax+80h]
0x14004d305  movups  xmm0, xmmword ptr [rcx]
0x14004d308  lea     rcx, [rcx+80h]
0x14004d30f  movups  xmmword ptr [rax-80h], xmm0
0x14004d313  movups  xmm1, xmmword ptr [rcx-70h]
0x14004d317  movups  xmmword ptr [rax-70h], xmm1
0x14004d31b  movups  xmm0, xmmword ptr [rcx-60h]
0x14004d31f  movups  xmmword ptr [rax-60h], xmm0
0x14004d323  movups  xmm1, xmmword ptr [rcx-50h]
0x14004d327  movups  xmmword ptr [rax-50h], xmm1
0x14004d32b  movups  xmm0, xmmword ptr [rcx-40h]
0x14004d32f  movups  xmmword ptr [rax-40h], xmm0
0x14004d333  movups  xmm1, xmmword ptr [rcx-30h]
0x14004d337  movups  xmmword ptr [rax-30h], xmm1
0x14004d33b  movups  xmm0, xmmword ptr [rcx-20h]
0x14004d33f  movups  xmmword ptr [rax-20h], xmm0
0x14004d343  movups  xmm1, xmmword ptr [rcx-10h]
0x14004d347  movups  xmmword ptr [rax-10h], xmm1
0x14004d34b  sub     rdx, 1
0x14004d34f  jnz     short loc_14004D2FE
0x14004d351  mov     rax, [r12+78h]
0x14004d356  cmp     byte ptr [rax+4Dh], 1
0x14004d35a  jnz     short loc_14004D36C
0x14004d35c  mov     rax, [rsi+50h]
0x14004d360  cmp     [rax+4], edx
0x14004d363  jz      short loc_14004D36C
0x14004d365  or      byte ptr [rbp+182h], 80h
0x14004d36c  lea     rcx, MRxSmbReadWriteMutex; FastMutex
0x14004d373  call    cs:__imp_ExAcquireFastMutex
0x14004d37a  nop     dword ptr [rax+rax+00h]
0x14004d37f  mov     r8, [rbp+358h]
0x14004d386  mov     eax, [r8+168h]
0x14004d38d  test    eax, eax
0x14004d38f  jz      short loc_14004D40C
0x14004d391  mov     edi, [r8+14Ch]
0x14004d398  xor     bl, bl
0x14004d39a  cmp     eax, 0C09820FBh
0x14004d39f  jnz     loc_14004D4FD
0x14004d3a5  mov     rax, [rsp+98h+RxContext]
0x14004d3ad  xor     r9d, r9d
0x14004d3b0  mov     qword ptr [rax+0B8h], 0
0x14004d3bb  mov     dword ptr [r8+168h], 0
0x14004d3c6  mov     dword ptr [rbp+30h], 0
0x14004d3cd  cmp     [r8+148h], r9d
0x14004d3d4  jbe     short loc_14004D40C
0x14004d3d6  lea     rdx, [r8+r9*4]
0x14004d3da  mov     ecx, [rdx+17Ch]
0x14004d3e0  sub     ecx, 1
0x14004d3e3  jz      short loc_14004D3F6
0x14004d3e5  cmp     ecx, 1
0x14004d3e8  jnz     short loc_14004D400
0x14004d3ea  mov     dword ptr [rdx+17Ch], 0
0x14004d3f4  jmp     short loc_14004D400
0x14004d3f6  mov     dword ptr [rdx+17Ch], 3
0x14004d400  inc     r9d
0x14004d403  cmp     r9d, [r8+148h]
0x14004d40a  jb      short loc_14004D3D6
0x14004d40c  mov     eax, [r8+148h]
0x14004d413  xor     r9d, r9d
0x14004d416  cmp     r9d, eax
0x14004d419  jnb     loc_14004D6A7
0x14004d41f  cmp     dword ptr [r8+r9*4+17Ch], 0
0x14004d428  mov     ecx, r9d
0x14004d42b  jz      short loc_14004D432
0x14004d42d  inc     r9d
0x14004d430  jmp     short loc_14004D416
0x14004d432  mov     r10d, 1
0x14004d438  mov     [r8+r9*4+17Ch], r10d
0x14004d440  mov     eax, [r8+150h]
0x14004d447  imul    rax, rcx
0x14004d44b  add     rax, [r8+20h]
0x14004d44f  mov     [rbp+1F8h], rax
0x14004d456  mov     eax, [r8+148h]
0x14004d45d  mov     ecx, [r8+150h]
0x14004d464  dec     eax
0x14004d466  cmp     r9d, eax
0x14004d469  jnz     short loc_14004D477
0x14004d46b  mov     eax, [r8+10h]
0x14004d46f  xor     edx, edx
0x14004d471  div     ecx
0x14004d473  test    edx, edx
0x14004d475  jnz     short loc_14004D482
0x14004d477  cmp     dword ptr [r8+10h], 0
0x14004d47c  mov     edx, ecx
0x14004d47e  jnz     short loc_14004D482
0x14004d480  xor     edx, edx
0x14004d482  mov     [rbp+1E8h], edx
0x14004d488  mov     eax, r9d
0x14004d48b  imul    eax, [r8+150h]
0x14004d493  mov     edi, r10d
0x14004d496  mov     [rbp+32Ch], r9d
0x14004d49d  mov     [rbp+1F4h], eax
0x14004d4a3  lock xadd [r8+14Ch], edi
0x14004d4ac  inc     edi
0x14004d4ae  movzx   ebx, r10b
0x14004d4b2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d4b9  lea     rax, WPP_GLOBAL_Control
0x14004d4c0  cmp     rcx, rax
0x14004d4c3  jz      short loc_14004D4FD
0x14004d4c5  test    dword ptr [rcx+2Ch], 200h
0x14004d4cc  jz      short loc_14004D4FD
0x14004d4ce  mov     rcx, [rcx+18h]
0x14004d4d2  lea     r8, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids
0x14004d4d9  mov     edx, 23h ; '#'
0x14004d4de  mov     [rsp+98h+Timeout], rbp
0x14004d4e3  call    WPP_SF_dq
0x14004d4e8  lea     rcx, MRxSmbReadWriteMutex; FastMutex
0x14004d4ef  call    cs:__imp_ExReleaseFastMutex
0x14004d4f6  nop     dword ptr [rax+rax+00h]
0x14004d4fb  jmp     short loc_14004D518
  ... truncated ...
```

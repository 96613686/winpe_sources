# PxCoBindAdapterEx

- ea: `0x140002670`
- end: `0x140002fc0`
- name: `PxCoBindAdapterEx`
- size: `2384`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x140001b84`
- `0x140001bc8`
- `0x140002670`
- `0x140004554`
- `0x140004690`
- `0x140007b44`
- `0x140007fc0`
- `0x1400080a0`
- `0x1400081c0`
- `0x1400084c0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000271e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000286e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002c64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000271e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000286e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002c64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f49`
- `ntoskrnl!KeInitializeSpinLock` at `0x140002827`
- `ntoskrnl!KeInitializeSpinLock` at `0x140002827`
- `ntoskrnl!RtlGUIDFromString` at `0x14000292d`
- `ntoskrnl!RtlGUIDFromString` at `0x14000292d`
- `ntoskrnl!ExAllocatePool2` at `0x1400027f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400027f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002915`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002915`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000278a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400028ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002ca0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f80`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000278a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400028ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002ca0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f80`
- `NDIS!NdisInitializeEvent` at `0x140002a0b`
- `NDIS!NdisInitializeEvent` at `0x140002a22`
- `NDIS!NdisInitializeEvent` at `0x140002a36`
- `NDIS!NdisInitializeEvent` at `0x140002b72`
- `NDIS!NdisInitializeEvent` at `0x140002d9c`
- `NDIS!NdisInitializeEvent` at `0x140002f09`
- `NDIS!NdisInitializeEvent` at `0x140002a0b`
- `NDIS!NdisInitializeEvent` at `0x140002a22`
- `NDIS!NdisInitializeEvent` at `0x140002a36`
- `NDIS!NdisInitializeEvent` at `0x140002b72`
- `NDIS!NdisInitializeEvent` at `0x140002d9c`
- `NDIS!NdisInitializeEvent` at `0x140002f09`
- `NDIS!NdisWaitEvent` at `0x140002704`
- `NDIS!NdisWaitEvent` at `0x140002ae2`
- `NDIS!NdisWaitEvent` at `0x140002bf1`
- `NDIS!NdisWaitEvent` at `0x140002e02`
- `NDIS!NdisWaitEvent` at `0x140002f32`
- `NDIS!NdisWaitEvent` at `0x140002704`
- `NDIS!NdisWaitEvent` at `0x140002ae2`
- `NDIS!NdisWaitEvent` at `0x140002bf1`
- `NDIS!NdisWaitEvent` at `0x140002e02`
- `NDIS!NdisWaitEvent` at `0x140002f32`
- `NDIS!NdisSetEvent` at `0x140002ece`
- `NDIS!NdisSetEvent` at `0x140002ece`
- `NDIS!NdisOpenAdapterEx` at `0x140002ac8`
- `NDIS!NdisOpenAdapterEx` at `0x140002bd7`
- `NDIS!NdisOpenAdapterEx` at `0x140002ac8`
- `NDIS!NdisOpenAdapterEx` at `0x140002bd7`
- `NDIS!NdisOidRequest` at `0x140002de6`
- `NDIS!NdisOidRequest` at `0x140002de6`
- `NDIS!NdisCloseAdapterEx` at `0x140002f1a`
- `NDIS!NdisCloseAdapterEx` at `0x140002f1a`

## pseudocode

```c
__int64 __fastcall PxCoBindAdapterEx(__int64 a1, void *a2, __int64 a3)
{
  UNICODE_STRING *v3; // r13
  char v4; // r14
  KIRQL v5; // r15
  _QWORD *v6; // rdi
  _QWORD *v7; // rbx
  size_t Length; // rsi
  __int64 v9; // r8
  unsigned int v10; // ebx
  unsigned int MaximumLength; // eax
  __int64 Pool2; // rax
  __int64 v13; // r12
  KSPIN_LOCK *v14; // r15
  PKDEFERRED_ROUTINE DeferredRoutine; // rcx
  KIRQL v16; // al
  PKDEFERRED_ROUTINE v17; // rdx
  PKDEFERRED_ROUTINE *v18; // rcx
  __int64 v19; // rcx
  wchar_t *Buffer; // rdx
  bool v21; // zf
  unsigned int v22; // ecx
  __m128i v23; // xmm0
  __int64 v24; // rax
  void **v25; // rsi
  int v26; // edi
  KIRQL v27; // al
  KIRQL v28; // al
  unsigned int v29; // ebx
  int v30; // eax
  void *v31; // rcx
  NDIS_STATUS v32; // eax
  __int64 v33; // rsi
  __int64 v34; // r8
  _WORD *v35; // rbx
  int v36; // edi
  int v37; // edi
  KIRQL v38; // al
  KSPIN_LOCK *v39; // rcx
  NDIS_HANDLE BindContext; // [rsp+70h] [rbp-90h] BYREF
  int v42; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v43; // [rsp+7Ch] [rbp-84h] BYREF
  _NDIS_OPEN_PARAMETERS OpenParameters; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  void *Src[16]; // [rsp+D0h] [rbp-30h]
  _BYTE OidRequest[280]; // [rsp+150h] [rbp+50h] BYREF
  _DWORD v48[20]; // [rsp+270h] [rbp+170h] BYREF

  v3 = *(UNICODE_STRING **)(a3 + 16);
  BindContext = a2;
  memset(&OpenParameters, 0, sizeof(OpenParameters));
  v43 = 0;
  v42 = -2130671474;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 18, a3, v3->Buffer);
  NdisWaitEvent((PNDIS_EVENT)((char *)WPP_MAIN_CB.Dpc.DeferredRoutine + 64), 0);
  v4 = 0;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WPP_MAIN_CB.Dpc.DeferredRoutine + 11);
  v6 = (_QWORD *)((char *)WPP_MAIN_CB.Dpc.DeferredRoutine + 32);
  *((_BYTE *)WPP_MAIN_CB.Dpc.DeferredRoutine + 96) = v5;
  v7 = (_QWORD *)*v6;
  if ( (_QWORD *)*v6 != v6 )
  {
    Length = v3->Length;
    while ( (_WORD)Length != *((_WORD *)v7 + 88) || memcmp(v3->Buffer, (const void *)v7[23], Length) )
    {
      v7 = (_QWORD *)*v7;
      if ( v7 == v6 )
        goto LABEL_11;
    }
    v4 = 1;
  }
LABEL_11:
  KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.Dpc.DeferredRoutine + 11, v5);
  if ( v4 )
  {
    v10 = 65539;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 19, v9, v3->Buffer);
    return v10;
  }
  MaximumLength = v3->MaximumLength;
  if ( MaximumLength + 640 < MaximumLength )
    return (unsigned int)-1073741670;
  Pool2 = ExAllocatePool2(64, MaximumLength + 640, 3364944);
  v13 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v14 = (KSPIN_LOCK *)(Pool2 + 624);
  *(_DWORD *)(Pool2 + 20) = 2;
  *(_DWORD *)(Pool2 + 16) = 538996035;
  KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 624));
  DeferredRoutine = WPP_MAIN_CB.Dpc.DeferredRoutine;
  *(_QWORD *)(v13 + 88) = v13 + 80;
  *(_QWORD *)(v13 + 80) = v13 + 80;
  *(_QWORD *)(v13 + 104) = v13 + 96;
  *(_QWORD *)(v13 + 96) = v13 + 96;
  *(_QWORD *)(v13 + 48) = v13 + 40;
  *(_QWORD *)(v13 + 40) = v13 + 40;
  *(_QWORD *)(v13 + 64) = v13 + 56;
  *(_QWORD *)(v13 + 56) = v13 + 56;
  v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)DeferredRoutine + 11);
  v17 = WPP_MAIN_CB.Dpc.DeferredRoutine;
  *((_BYTE *)WPP_MAIN_CB.Dpc.DeferredRoutine + 96) = v16;
  v18 = (PKDEFERRED_ROUTINE *)*((_QWORD *)v17 + 5);
  if ( *v18 != (PKDEFERRED_ROUTINE)((char *)v17 + 32) )
    __fastfail(3u);
  *(_QWORD *)(v13 + 8) = v18;
  *(_QWORD *)v13 = (char *)v17 + 32;
  *v18 = (PKDEFERRED_ROUTINE)v13;
  *((_QWORD *)v17 + 5) = v13;
  KeReleaseSpinLock((PKSPIN_LOCK)v17 + 11, *((_BYTE *)v17 + 96));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_a6cada0c64e03ec47d691a112a859896_Traceguids, v13);
  v19 = v3->Length >> 1;
  if ( (_DWORD)v19 )
  {
    Buffer = v3->Buffer;
    while ( Buffer[v19] != 123 )
    {
      v21 = (_DWORD)v19 == 1;
      v19 = (unsigned int)(v19 - 1);
      if ( v21 )
        goto LABEL_30;
    }
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, &Buffer[v19]);
    RtlGUIDFromString(&DestinationString, (GUID *)(v13 + 152));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_DDDDDDDDDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        (unsigned int)WPP_55e376f2a9f936ee4a212904c2347983_Traceguids,
        *(_DWORD *)(v13 + 152),
        *(_WORD *)(v13 + 156),
        *(_WORD *)(v13 + 158),
        *(_BYTE *)(v13 + 160),
        *(_BYTE *)(v13 + 161),
        *(_BYTE *)(v13 + 162),
        *(_BYTE *)(v13 + 163),
        *(_BYTE *)(v13 + 164),
        *(_BYTE *)(v13 + 165),
        *(_BYTE *)(v13 + 166),
        *(_BYTE *)(v13 + 167));
      v14 = (KSPIN_LOCK *)(v13 + 624);
    }
  }
LABEL_30:
  NdisInitializeEvent((PNDIS_EVENT)(v13 + 552));
  NdisInitializeEvent((PNDIS_EVENT)(v13 + 520));
  NdisInitializeEvent((PNDIS_EVENT)(v13 + 584));
  v22 = 0;
  *(_DWORD *)(v13 + 616) = 0;
  do
  {
    v23 = _mm_cvtsi32_si128(v22);
    v24 = v22;
    v22 += 4;
    *(__m128i *)&v48[v24] = _mm_add_epi32(_mm_shuffle_epi32(v23, 0), (__m128i)_xmm);
  }
  while ( v22 < 0x14 );
  v25 = (void **)(v13 + 32);
  OpenParameters.MediumArray = (PNDIS_MEDIUM)v48;
  OpenParameters.Header = (NDIS_OBJECT_HEADER)3670407;
  OpenParameters.SelectedMediumIndex = &v43;
  OpenParameters.AdapterName = v3;
  OpenParameters.FrameTypeArray = (PNET_FRAME_TYPE)&v42;
  OpenParameters.MediumArraySize = 20;
  OpenParameters.FrameTypeArraySize = 2;
  v10 = NdisOpenAdapterEx(
          *((NDIS_HANDLE *)WPP_MAIN_CB.Dpc.DeferredRoutine + 3),
          (NDIS_HANDLE)v13,
          &OpenParameters,
          BindContext,
          (PNDIS_HANDLE)(v13 + 32));
  if ( v10 == 259 )
  {
    NdisWaitEvent((PNDIS_EVENT)(v13 + 520), 0);
    v10 = *(_DWORD *)(v13 + 544);
  }
  if ( v10 )
  {
    v26 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids, v10);
    *v25 = 0;
    *(_DWORD *)(v13 + 168) = -1;
LABEL_45:
    *(_DWORD *)(v13 + 20) = 1;
    goto LABEL_63;
  }
  v27 = KeAcquireSpinLockRaiseToDpc(v14);
  ++*(_DWORD *)(v13 + 24);
  *(_BYTE *)(v13 + 632) = v27;
  KeReleaseSpinLock(v14, v27);
  NdisInitializeEvent((PNDIS_EVENT)(v13 + 520));
  OpenParameters.MediumArray = (PNDIS_MEDIUM)v48;
  OpenParameters.Header = (NDIS_OBJECT_HEADER)3670407;
  OpenParameters.SelectedMediumIndex = &v43;
  OpenParameters.AdapterName = v3;
  OpenParameters.FrameTypeArray = (PNET_FRAME_TYPE)&v42;
  OpenParameters.MediumArraySize = 20;
  OpenParameters.FrameTypeArraySize = 2;
  v10 = NdisOpenAdapterEx(
          *((NDIS_HANDLE *)WPP_MAIN_CB.Dpc.DeferredRoutine + 3),
          (NDIS_HANDLE)(v13 + 16),
          &OpenParameters,
          BindContext,
          (PNDIS_HANDLE)(v13 + 72));
  if ( v10 == 259 )
  {
    NdisWaitEvent((PNDIS_EVENT)(v13 + 520), 0);
    v10 = *(_DWORD *)(v13 + 544);
  }
  if ( v10 )
  {
    v26 = 2;
    *(_QWORD *)(v13 + 72) = 0;
    *(_DWORD *)(v13 + 168) = -1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids, v10);
    goto LABEL_45;
  }
  v28 = KeAcquireSpinLockRaiseToDpc(v14);
  ++*(_DWORD *)(v13 + 24);
  v26 = 3;
  *(_BYTE *)(v13 + 632) = v28;
  *(_DWORD *)(v13 + 20) = 3;
  *(_DWORD *)(v13 + 168) = v48[v43];
  KeReleaseSpinLock(v14, v28);
  v29 = 0;
  LODWORD(BindContext) = 0;
  memset(OidRequest, 0, sizeof(OidRequest));
  Src[0] = L"GENERIC";
  Src[1] = L"X25";
  Src[2] = L"ISDN";
  Src[3] = L"SERIAL";
  Src[4] = L"FRAMERELAY";
  Src[5] = L"ATM";
  Src[6] = L"SONET";
  Src[7] = L"SW56";
  Src[8] = L"PPTP VPN";
  Src[9] = L"L2TP VPN";
  Src[10] = L"IRDA";
  Src[11] = L"PARALLEL";
  Src[12] = L"PPPOE";
  Src[13] = L"SSTP";
  Src[14] = L"AGILE VPN";
  Src[15] = L"GRE";
  v30 = *(_DWORD *)(v13 + 168);
  if ( v30 == 3 )
  {
LABEL_49:
    NdisInitializeEvent((PNDIS_EVENT)&OidRequest[248]);
    memset(OidRequest, 0, 0xF0u);
    v31 = *v25;
    *(_QWORD *)&OidRequest[40] = &BindContext;
    *(_QWORD *)OidRequest = 15729046;
    *(_QWORD *)&OidRequest[8] = 0;
    *(_DWORD *)&OidRequest[32] = 67174661;
    *(_DWORD *)&OidRequest[48] = 4;
    v32 = NdisOidRequest(v31, (PNDIS_OID_REQUEST)OidRequest);
    if ( v32 == 259 )
    {
      NdisWaitEvent((PNDIS_EVENT)&OidRequest[248], 0);
      v32 = *(_DWORD *)&OidRequest[272];
    }
    if ( v32 )
    {
      v29 = 0;
      LODWORD(BindContext) = 0;
    }
    else
    {
      v29 = (unsigned int)BindContext;
    }
    if ( v29 < 0x10 )
      goto LABEL_58;
    v29 = 0;
    goto LABEL_57;
  }
  if ( v30 != 8 )
  {
    if ( v30 != 12 )
      goto LABEL_58;
    goto LABEL_49;
  }
  v29 = 5;
LABEL_57:
  LODWORD(BindContext) = v29;
LABEL_58:
  v33 = -1;
  *(_DWORD *)(v13 + 172) = v29;
  v34 = -1;
  v35 = Src[v29];
  do
    ++v34;
  while ( v35[v34] );
  memmove((void *)(v13 + 196), v35, 2 * v34);
  do
    ++v33;
  while ( v35[v33] );
  v10 = 0;
  *(_DWORD *)(v13 + 192) = 2 * v33;
  *(_WORD *)(v13 + 178) = v3->MaximumLength;
  *(_WORD *)(v13 + 176) = v3->Length;
  *(_QWORD *)(v13 + 184) = v13 + 640;
  memmove((void *)(v13 + 640), v3->Buffer, v3->Length);
LABEL_63:
  *(_DWORD *)(v13 + 576) = 0;
  NdisSetEvent((PNDIS_EVENT)(v13 + 552));
  if ( v10 )
  {
    v36 = v26 - 1;
    if ( v36 )
    {
      v37 = v36 - 1;
      if ( v37 )
      {
        if ( v37 != 1 )
          return v10;
        --*(_DWORD *)(v13 + 24);
      }
      NdisInitializeEvent((PNDIS_EVENT)(v13 + 456));
      if ( NdisCloseAdapterEx(*(NDIS_HANDLE *)(v13 + 32)) == 259 )
        NdisWaitEvent((PNDIS_EVENT)(v13 + 456), 0);
      v38 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 624));
      v21 = (*(_DWORD *)(v13 + 24))-- == 1;
      v39 = (KSPIN_LOCK *)(v13 + 624);
      *(_BYTE *)(v13 + 632) = v38;
      if ( !v21 )
      {
        KeReleaseSpinLock(v39, v38);
        return v10;
      }
      KeReleaseSpinLock(v39, v38);
    }
    PxFreeAdapter((PVOID)v13);
  }
  return v10;
}

```

## disassembly

```asm
0x140002670  mov     [rsp-8+arg_0], rbx
0x140002675  push    rbp
0x140002676  push    rsi
0x140002677  push    rdi
0x140002678  push    r12
0x14000267a  push    r13
0x14000267c  push    r14
0x14000267e  push    r15
0x140002680  lea     rbp, [rsp-1D0h]
0x140002688  sub     rsp, 2D0h
0x14000268f  mov     rax, cs:__security_cookie
0x140002696  xor     rax, rsp
0x140002699  mov     [rbp+200h+var_40], rax
0x1400026a0  mov     r13, [r8+10h]
0x1400026a4  xorps   xmm0, xmm0
0x1400026a7  xor     eax, eax
0x1400026a9  mov     [rsp+300h+BindContext], rdx
0x1400026ae  movups  xmmword ptr [rbp+200h+OpenParameters.Header.Type], xmm0
0x1400026b2  mov     qword ptr [rbp+200h+OpenParameters.FrameTypeArraySize], rax
0x1400026b6  movups  xmmword ptr [rbp+200h+OpenParameters.MediumArray], xmm0
0x1400026ba  mov     [rsp+300h+var_284], 0
0x1400026c2  movups  xmmword ptr [rbp+200h+OpenParameters.SelectedMediumIndex], xmm0
0x1400026c6  mov     [rsp+300h+var_288], 8100888Eh
0x1400026ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026d5  lea     rsi, WPP_GLOBAL_Control
0x1400026dc  cmp     rcx, rsi
0x1400026df  jz      short loc_1400026F7
0x1400026e1  cmp     byte ptr [rcx+29h], 5
0x1400026e5  jb      short loc_1400026F7
0x1400026e7  mov     r9, [r13+8]
0x1400026eb  lea     edx, [rax+12h]
0x1400026ee  mov     rcx, [rcx+18h]
0x1400026f2  call    WPP_SF_S
0x1400026f7  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x1400026fe  xor     edx, edx; MsToWait
0x140002700  add     rcx, 40h ; '@'; Event
0x140002704  call    cs:__imp_NdisWaitEvent
0x14000270b  nop     dword ptr [rax+rax+00h]
0x140002710  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140002717  xor     r14b, r14b
0x14000271a  add     rcx, 58h ; 'X'; SpinLock
0x14000271e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002725  nop     dword ptr [rax+rax+00h]
0x14000272a  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140002731  mov     r15b, al
0x140002734  lea     rdi, [rcx+20h]
0x140002738  mov     [rcx+60h], al
0x14000273b  mov     rbx, [rdi]
0x14000273e  cmp     rbx, rdi
0x140002741  jz      short loc_14000277C
0x140002743  movzx   esi, word ptr [r13+0]
0x140002748  cmp     si, [rbx+0B0h]
0x14000274f  jnz     short loc_140002768
0x140002751  mov     rdx, [rbx+0B8h]; Buf2
0x140002758  mov     r8, rsi; Size
0x14000275b  mov     rcx, [r13+8]; Buf1
0x14000275f  call    memcmp
0x140002764  test    eax, eax
0x140002766  jz      short loc_140002772
0x140002768  mov     rbx, [rbx]
0x14000276b  cmp     rbx, rdi
0x14000276e  jnz     short loc_140002748
0x140002770  jmp     short loc_140002775
0x140002772  mov     r14b, 1
0x140002775  lea     rsi, WPP_GLOBAL_Control
0x14000277c  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140002783  mov     dl, r15b; NewIrql
0x140002786  add     rcx, 58h ; 'X'; SpinLock
0x14000278a  call    cs:__imp_KeReleaseSpinLock
0x140002791  nop     dword ptr [rax+rax+00h]
0x140002796  test    r14b, r14b
0x140002799  jz      short loc_1400027D4
0x14000279b  mov     ebx, 10003h
0x1400027a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400027a7  cmp     rcx, rsi
0x1400027aa  jz      loc_140002F93
0x1400027b0  mov     edi, 3
0x1400027b5  cmp     [rcx+29h], dil
0x1400027b9  jb      loc_140002F93
0x1400027bf  mov     r9, [r13+8]
0x1400027c3  lea     edx, [rdi+10h]
0x1400027c6  mov     rcx, [rcx+18h]
0x1400027ca  call    WPP_SF_S
0x1400027cf  jmp     loc_140002F93
0x1400027d4  movzx   eax, word ptr [r13+2]
0x1400027d9  lea     ecx, [rax+280h]
0x1400027df  cmp     ecx, eax
0x1400027e1  jb      loc_140002F8E
0x1400027e7  mov     edx, ecx
0x1400027e9  mov     r8d, 335850h
0x1400027ef  mov     ecx, 40h ; '@'
0x1400027f4  call    cs:__imp_ExAllocatePool2
0x1400027fb  nop     dword ptr [rax+rax+00h]
0x140002800  xor     r14d, r14d
0x140002803  mov     r12, rax
0x140002806  test    rax, rax
0x140002809  jz      loc_140002F8E
0x14000280f  lea     r15, [rax+270h]
0x140002816  mov     dword ptr [rax+14h], 2
0x14000281d  mov     rcx, r15; SpinLock
0x140002820  mov     dword ptr [rax+10h], 20206D43h
0x140002827  call    cs:__imp_KeInitializeSpinLock
0x14000282e  nop     dword ptr [rax+rax+00h]
0x140002833  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14000283a  lea     rax, [r12+50h]
0x14000283f  mov     [rax+8], rax
0x140002843  add     rcx, 58h ; 'X'; SpinLock
0x140002847  mov     [rax], rax
0x14000284a  lea     rax, [r12+60h]
0x14000284f  mov     [rax+8], rax
0x140002853  mov     [rax], rax
0x140002856  lea     rax, [r12+28h]
0x14000285b  mov     [rax+8], rax
0x14000285f  mov     [rax], rax
0x140002862  lea     rax, [r12+38h]
0x140002867  mov     [rax+8], rax
0x14000286b  mov     [rax], rax
0x14000286e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002875  nop     dword ptr [rax+rax+00h]
0x14000287a  mov     rdx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140002881  mov     [rdx+60h], al
0x140002884  lea     rax, [rdx+20h]
0x140002888  mov     rcx, [rax+8]
0x14000288c  cmp     [rcx], rax
0x14000288f  jz      short loc_140002897
0x140002891  lea     ecx, [r14+3]
0x140002895  int     29h; Win8: RtlFailFast(ecx)
0x140002897  mov     [r12+8], rcx
0x14000289c  mov     [r12], rax
0x1400028a0  mov     [rcx], r12
0x1400028a3  lea     rcx, [rdx+58h]; SpinLock
0x1400028a7  mov     [rax+8], r12
0x1400028ab  mov     dl, [rdx+60h]; NewIrql
0x1400028ae  call    cs:__imp_KeReleaseSpinLock
0x1400028b5  nop     dword ptr [rax+rax+00h]
0x1400028ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028c1  cmp     rcx, rsi
0x1400028c4  jz      short loc_1400028E4
0x1400028c6  cmp     byte ptr [rcx+29h], 5
0x1400028ca  jb      short loc_1400028E4
0x1400028cc  mov     rcx, [rcx+18h]
0x1400028d0  lea     r8, WPP_a6cada0c64e03ec47d691a112a859896_Traceguids
0x1400028d7  mov     edx, 0Ah
0x1400028dc  mov     r9, r12
0x1400028df  call    WPP_SF_q
0x1400028e4  movzx   ecx, word ptr [r13+0]
0x1400028e9  shr     ecx, 1
0x1400028eb  jz      loc_140002A03
0x1400028f1  mov     rdx, [r13+8]
0x1400028f5  cmp     word ptr [rdx+rcx*2], 7Bh ; '{'
0x1400028fa  jz      short loc_140002906
0x1400028fc  add     ecx, 0FFFFFFFFh
0x1400028ff  jnz     short loc_1400028F5
0x140002901  jmp     loc_140002A03
0x140002906  xorps   xmm0, xmm0
0x140002909  lea     rdx, [rdx+rcx*2]; SourceString
0x14000290d  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x140002911  movups  xmmword ptr [rbp+200h+DestinationString.Length], xmm0
0x140002915  call    cs:__imp_RtlInitUnicodeString
0x14000291c  nop     dword ptr [rax+rax+00h]
0x140002921  lea     rdx, [r12+98h]; Guid
0x140002929  lea     rcx, [rbp+200h+DestinationString]; GuidString
0x14000292d  call    cs:__imp_RtlGUIDFromString
0x140002934  nop     dword ptr [rax+rax+00h]
0x140002939  mov     rcx, cs:WPP_GLOBAL_Control
0x140002940  cmp     rcx, rsi
0x140002943  jz      loc_140002A03
0x140002949  cmp     byte ptr [rcx+29h], 4
0x14000294d  jb      loc_140002A03
0x140002953  movzx   r8d, byte ptr [r12+0A6h]
0x14000295c  mov     edx, 14h
0x140002961  movzx   r9d, byte ptr [r12+0A5h]
0x14000296a  movzx   eax, byte ptr [r12+0A7h]
0x140002973  movzx   r10d, byte ptr [r12+0A4h]
0x14000297c  movzx   r11d, byte ptr [r12+0A3h]
0x140002985  movzx   ebx, byte ptr [r12+0A2h]
0x14000298e  movzx   edi, byte ptr [r12+0A1h]
0x140002997  movzx   esi, byte ptr [r12+0A0h]
0x1400029a0  movzx   r14d, word ptr [r12+9Eh]
0x1400029a9  movzx   r15d, word ptr [r12+9Ch]
0x1400029b2  mov     rcx, [rcx+18h]
0x1400029b6  mov     [rsp+300h+var_298], eax
0x1400029ba  mov     [rsp+300h+var_2A0], r8d
0x1400029bf  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x1400029c6  mov     [rsp+300h+var_2A8], r9d
0x1400029cb  mov     r9d, [r12+98h]
0x1400029d3  mov     [rsp+300h+var_2B0], r10d
0x1400029d8  mov     [rsp+300h+var_2B8], r11d
0x1400029dd  mov     [rsp+300h+var_2C0], ebx
0x1400029e1  mov     [rsp+300h+var_2C8], edi
0x1400029e5  mov     [rsp+300h+var_2D0], esi
0x1400029e9  mov     [rsp+300h+var_2D8], r14d
0x1400029ee  mov     dword ptr [rsp+300h+NdisBindingHandle], r15d
0x1400029f3  call    WPP_SF_DDDDDDDDDDD
0x1400029f8  xor     r14d, r14d
0x1400029fb  lea     r15, [r12+270h]
0x140002a03  lea     rcx, [r12+228h]; Event
0x140002a0b  call    cs:__imp_NdisInitializeEvent
0x140002a12  nop     dword ptr [rax+rax+00h]
0x140002a17  lea     rdi, [r12+208h]
0x140002a1f  mov     rcx, rdi; Event
0x140002a22  call    cs:__imp_NdisInitializeEvent
0x140002a29  nop     dword ptr [rax+rax+00h]
0x140002a2e  lea     rcx, [r12+248h]; Event
0x140002a36  call    cs:__imp_NdisInitializeEvent
0x140002a3d  nop     dword ptr [rax+rax+00h]
0x140002a42  mov     ecx, r14d
0x140002a45  mov     [r12+268h], r14d
0x140002a4d  movd    xmm0, ecx
0x140002a51  mov     eax, ecx
0x140002a53  add     ecx, 4
0x140002a56  pshufd  xmm0, xmm0, 0
0x140002a5b  paddd   xmm0, cs:__xmm@00000003000000020000000100000000
0x140002a63  movdqu  xmmword ptr [rbp+rax*4+200h+var_90], xmm0
0x140002a6c  cmp     ecx, 14h
0x140002a6f  jb      short loc_140002A4D
0x140002a71  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140002a78  lea     rax, [rbp+200h+var_90]
0x140002a7f  mov     r9, [rsp+300h+BindContext]; BindContext
0x140002a84  lea     rsi, [r12+20h]
0x140002a89  mov     [rbp+200h+OpenParameters.MediumArray], rax
0x140002a8d  lea     r8, [rbp+200h+OpenParameters]; OpenParameters
0x140002a91  lea     rax, [rsp+300h+var_284]
0x140002a96  mov     dword ptr [rbp+200h+OpenParameters.Header.Type], 380187h
0x140002a9d  mov     [rbp+200h+OpenParameters.SelectedMediumIndex], rax
0x140002aa1  mov     rdx, r12; ProtocolBindingContext
0x140002aa4  lea     rax, [rsp+300h+var_288]
0x140002aa9  mov     [rbp+200h+OpenParameters.AdapterName], r13
0x140002aad  mov     [rbp+200h+OpenParameters.FrameTypeArray], rax
0x140002ab1  mov     [rbp+200h+OpenParameters.MediumArraySize], 14h
0x140002ab8  mov     [rbp+200h+OpenParameters.FrameTypeArraySize], 2
0x140002abf  mov     rcx, [rcx+18h]; NdisProtocolHandle
0x140002ac3  mov     [rsp+300h+NdisBindingHandle], rsi; NdisBindingHandle
0x140002ac8  call    cs:__imp_NdisOpenAdapterEx
0x140002acf  nop     dword ptr [rax+rax+00h]
0x140002ad4  mov     ebx, eax
0x140002ad6  cmp     eax, 103h
0x140002adb  jnz     short loc_140002AF6
0x140002add  xor     edx, edx; MsToWait
0x140002adf  mov     rcx, rdi; Event
0x140002ae2  call    cs:__imp_NdisWaitEvent
0x140002ae9  nop     dword ptr [rax+rax+00h]
0x140002aee  mov     ebx, [r12+220h]
0x140002af6  test    ebx, ebx
0x140002af8  jz      short loc_140002B42
0x140002afa  mov     edi, 1
0x140002aff  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b06  lea     rax, WPP_GLOBAL_Control
0x140002b0d  cmp     rcx, rax
0x140002b10  jz      short loc_140002B2E
0x140002b12  cmp     byte ptr [rcx+29h], 2
0x140002b16  jb      short loc_140002B2E
0x140002b18  mov     rcx, [rcx+18h]
0x140002b1c  lea     edx, [rdi+14h]
0x140002b1f  mov     r9d, ebx
0x140002b22  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x140002b29  call    WPP_SF_d
0x140002b2e  mov     [rsi], r14
0x140002b31  mov     dword ptr [r12+0A8h], 0FFFFFFFFh
0x140002b3d  jmp     loc_140002C53
0x140002b42  mov     rcx, r15; SpinLock
0x140002b45  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002b4c  nop     dword ptr [rax+rax+00h]
0x140002b51  inc     dword ptr [r12+18h]
0x140002b56  mov     rcx, r15; SpinLock
0x140002b59  mov     dl, al; NewIrql
0x140002b5b  mov     [r12+278h], al
0x140002b63  call    cs:__imp_KeReleaseSpinLock
0x140002b6a  nop     dword ptr [rax+rax+00h]
0x140002b6f  mov     rcx, rdi; Event
0x140002b72  call    cs:__imp_NdisInitializeEvent
0x140002b79  nop     dword ptr [rax+rax+00h]
0x140002b7e  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140002b85  lea     rax, [rbp+200h+var_90]
0x140002b8c  mov     r9, [rsp+300h+BindContext]; BindContext
0x140002b91  lea     r14, [r12+48h]
0x140002b96  mov     [rbp+200h+OpenParameters.MediumArray], rax
0x140002b9a  lea     r8, [rbp+200h+OpenParameters]; OpenParameters
0x140002b9e  lea     rax, [rsp+300h+var_284]
0x140002ba3  mov     dword ptr [rbp+200h+OpenParameters.Header.Type], 380187h
0x140002baa  mov     [rbp+200h+OpenParameters.SelectedMediumIndex], rax
0x140002bae  lea     rdx, [r12+10h]; ProtocolBindingContext
0x140002bb3  lea     rax, [rsp+300h+var_288]
0x140002bb8  mov     [rbp+200h+OpenParameters.AdapterName], r13
0x140002bbc  mov     [rbp+200h+OpenParameters.FrameTypeArray], rax
0x140002bc0  mov     [rbp+200h+OpenParameters.MediumArraySize], 14h
0x140002bc7  mov     [rbp+200h+OpenParameters.FrameTypeArraySize], 2
0x140002bce  mov     rcx, [rcx+18h]; NdisProtocolHandle
0x140002bd2  mov     [rsp+300h+NdisBindingHandle], r14; NdisBindingHandle
0x140002bd7  call    cs:__imp_NdisOpenAdapterEx
0x140002bde  nop     dword ptr [rax+rax+00h]
0x140002be3  mov     ebx, eax
0x140002be5  cmp     eax, 103h
0x140002bea  jnz     short loc_140002C05
0x140002bec  xor     edx, edx; MsToWait
0x140002bee  mov     rcx, rdi; Event
0x140002bf1  call    cs:__imp_NdisWaitEvent
0x140002bf8  nop     dword ptr [rax+rax+00h]
0x140002bfd  mov     ebx, [r12+220h]
0x140002c05  test    ebx, ebx
  ... truncated ...
```

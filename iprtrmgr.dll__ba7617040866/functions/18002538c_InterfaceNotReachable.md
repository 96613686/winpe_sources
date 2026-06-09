# InterfaceNotReachable

- ea: `0x18002538c`
- end: `0x18002589a`
- name: `InterfaceNotReachable`
- size: `1294`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003da00`

## callees

- `0x180001f30`
- `0x18000ac60`
- `0x180011790`
- `0x1800118a4`
- `0x1800163dc`
- `0x18001a82c`
- `0x18001c74c`
- `0x18002538c`
- `0x18003fb20`
- `0x180044d2c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002546f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002546f`
- `ntdll!RtlReleaseResource` at `0x1800254a2`
- `ntdll!RtlReleaseResource` at `0x180025786`
- `ntdll!RtlReleaseResource` at `0x1800257f1`
- `ntdll!RtlReleaseResource` at `0x1800254a2`
- `ntdll!RtlReleaseResource` at `0x180025786`
- `ntdll!RtlReleaseResource` at `0x1800257f1`
- `KERNEL32!LeaveCriticalSection` at `0x180025414`
- `KERNEL32!LeaveCriticalSection` at `0x1800254ba`
- `KERNEL32!LeaveCriticalSection` at `0x18002579e`
- `KERNEL32!LeaveCriticalSection` at `0x18002581f`
- `KERNEL32!LeaveCriticalSection` at `0x180025414`
- `KERNEL32!LeaveCriticalSection` at `0x1800254ba`
- `KERNEL32!LeaveCriticalSection` at `0x18002579e`
- `KERNEL32!LeaveCriticalSection` at `0x18002581f`
- `KERNEL32!EnterCriticalSection` at `0x1800253f8`
- `KERNEL32!EnterCriticalSection` at `0x1800254ab`
- `KERNEL32!EnterCriticalSection` at `0x18002578f`
- `KERNEL32!EnterCriticalSection` at `0x1800253f8`
- `KERNEL32!EnterCriticalSection` at `0x1800254ab`
- `KERNEL32!EnterCriticalSection` at `0x18002578f`

## string_xrefs

- `0x180025718`: `InterfaceNotReachable: %ws is already connected`

## pseudocode

```c
__int64 __fastcall InterfaceNotReachable(unsigned int a1, unsigned int a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  char v7; // al
  __int128 *v8; // r9
  unsigned int v9; // eax
  __int128 *v10; // r9
  unsigned int v11; // ebx
  int v12; // ecx
  unsigned int v13; // eax
  __int128 *v14; // r9
  unsigned int v15; // eax
  __int128 *v16; // r9
  __int128 *v17; // r9
  __int128 v18; // [rsp+38h] [rbp-860h] BYREF
  int v19; // [rsp+48h] [rbp-850h] BYREF
  __int128 v20; // [rsp+4Ch] [rbp-84Ch]
  __int128 v21; // [rsp+5Ch] [rbp-83Ch]
  int v22; // [rsp+6Ch] [rbp-82Ch]
  int v23; // [rsp+70h] [rbp-828h] BYREF
  _BYTE v24[2044]; // [rsp+74h] [rbp-824h] BYREF

  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v19 = 0;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  v18 = 0;
  EnterCriticalSection(&RouterStateLock);
  if ( (_DWORD)RouterState )
  {
    LeaveCriticalSection(&RouterStateLock);
    v11 = 900;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"error %d on RM API", 900);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v23);
    }
    return v11;
  }
  ++HIDWORD(RouterState);
  LeaveCriticalSection(&RouterStateLock);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"Entered: %ws", L"InterfaceNotReachable");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v23);
  }
  RtlAcquireResourceExclusive(&Resource, 1u);
  v4 = InterfaceLookupByICBSeqNumber(a1);
  v5 = v4;
  if ( !v4 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"InterfaceNotReachable : No interface with ICB number %d", a1);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v23);
    }
    goto LABEL_50;
  }
  if ( !*(_DWORD *)(v4 + 144) )
  {
    *(_DWORD *)(v4 + 168) = 1;
    RtlReleaseResource(&Resource);
LABEL_8:
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    return 0;
  }
  v7 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v23) = 0;
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v23, L"InterfaceNotReachable: %ws is not reachable for reason %d", *(_QWORD *)(v5 + 72), a2);
    v7 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v8 = &v18;
      if ( v5 != -688 )
        LODWORD(v8) = v5 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v23,
        (_DWORD)v8,
        *(_QWORD *)(v5 + 72),
        (__int64)&v19);
      v7 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( *(_DWORD *)(v5 + 144) != 3 )
  {
    v12 = *(_DWORD *)(v5 + 168);
    if ( v12 == 3 )
    {
      v13 = NotifyWanarpOfFailure(v5);
      if ( v13 != 259 )
      {
        if ( v13 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v23) = 0;
            LOWORD(v19) = 0;
            FormatRRASErrorString(&v23, L"InterfaceNotReachable: IOCTL_WANARP_CONNECT_FAILED failed. Status %x", v13);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v14 = &v18;
              if ( v5 != -688 )
                LODWORD(v14) = v5 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v23,
                (_DWORD)v14,
                *(_QWORD *)(v5 + 72),
                (__int64)&v19);
            }
          }
        }
      }
      v15 = ClearWfpFiltersForInterfaceFromWanarp(v5);
      if ( v15 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v23) = 0;
          LOWORD(v19) = 0;
          FormatRRASErrorString(
            &v23,
            L"InterfaceNotReachable: ClearWfpFiltersForInterfaceFromWanarp failed with error: %d",
            v15);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v16 = &v18;
            if ( v5 != -688 )
              LODWORD(v16) = v5 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v23,
              (_DWORD)v16,
              *(_QWORD *)(v5 + 72),
              (__int64)&v19);
          }
        }
      }
      UpdateOrClearDodRoutesForInterface(v5, 0);
      DeAllocateBindings(v5);
      *(_DWORD *)(v5 + 180) = 0;
    }
    else if ( v12 == 4 )
    {
      if ( v7 < 0 )
      {
        LOWORD(v23) = 0;
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v23, L"InterfaceNotReachable: %ws is already connected", *(_QWORD *)(v5 + 72));
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v17 = &v18;
          if ( v5 != -688 )
            LODWORD(v17) = v5 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v23,
            (_DWORD)v17,
            *(_QWORD *)(v5 + 72),
            (__int64)&v19);
        }
      }
      v11 = 1609;
      goto LABEL_46;
    }
    WanInterfaceInactiveToDown(v5, 0);
LABEL_50:
    RtlReleaseResource(&Resource);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: InterfaceNotReachable");
    goto LABEL_8;
  }
  if ( a2 != 5 )
  {
    v9 = LanEtcInterfaceUpToDown(v5);
    if ( v9 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v23) = 0;
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v23, L"InterfaceNotReachable: Failed to status for %d to down", v9);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v10 = &v18;
          if ( v5 != -688 )
            LODWORD(v10) = v5 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v23,
            (_DWORD)v10,
            *(_QWORD *)(v5 + 72),
            (__int64)&v19);
        }
      }
    }
  }
  v11 = 0;
LABEL_46:
  RtlReleaseResource(&Resource);
  EnterCriticalSection(&RouterStateLock);
  --HIDWORD(RouterState);
  LeaveCriticalSection(&RouterStateLock);
  return v11;
}

```

## disassembly

```asm
0x18002538c  mov     [rsp+arg_10], rbx
0x180025391  mov     [rsp+arg_18], rsi
0x180025396  push    rdi
0x180025397  push    r12
0x180025399  push    r14
0x18002539b  sub     rsp, 880h
0x1800253a2  mov     rax, cs:__security_cookie
0x1800253a9  xor     rax, rsp
0x1800253ac  mov     [rsp+898h+var_28], rax
0x1800253b4  mov     r14d, edx
0x1800253b7  mov     rsi, rcx
0x1800253ba  xor     eax, eax
0x1800253bc  lea     rcx, [rsp+898h+var_824]; void *
0x1800253c1  xor     edx, edx; Val
0x1800253c3  mov     [rsp+898h+var_828], eax
0x1800253c7  mov     r8d, 7FCh; Size
0x1800253cd  call    memset_0
0x1800253d2  xorps   xmm0, xmm0
0x1800253d5  lea     r12, RouterStateLock
0x1800253dc  xor     eax, eax
0x1800253de  mov     rcx, r12; lpCriticalSection
0x1800253e1  mov     [rsp+898h+var_850], eax
0x1800253e5  movups  [rsp+898h+var_84C], xmm0
0x1800253ea  mov     [rsp+898h+var_82C], eax
0x1800253ee  movups  [rsp+898h+var_83C], xmm0
0x1800253f3  movups  [rsp+898h+var_860], xmm0
0x1800253f8  call    cs:__imp_EnterCriticalSection
0x1800253fe  cmp     dword ptr cs:RouterState, 0
0x180025405  mov     rcx, r12; lpCriticalSection
0x180025408  jnz     loc_18002581F
0x18002540e  inc     dword ptr cs:RouterState+4
0x180025414  call    cs:__imp_LeaveCriticalSection
0x18002541a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180025421  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180025428  jge     short loc_180025466
0x18002542a  xor     eax, eax
0x18002542c  lea     r8, aInterfacenotre_1; "InterfaceNotReachable"
0x180025433  lea     rdx, aEnteredWs; "Entered: %ws"
0x18002543a  mov     word ptr [rsp+898h+var_828], ax
0x18002543f  lea     rcx, [rsp+898h+var_828]
0x180025444  call    FormatRRASErrorString
0x180025449  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180025450  jge     short loc_180025466
0x180025452  lea     r8, [rsp+898h+var_828]
0x180025457  mov     rcx, rdi
0x18002545a  lea     rdx, RasRtrmgrTraceInfo
0x180025461  call    McTemplateU0z_EventWriteTransfer
0x180025466  mov     dl, 1; Wait
0x180025468  lea     rcx, Resource; Resource
0x18002546f  call    cs:__imp_RtlAcquireResourceExclusive
0x180025475  mov     ecx, esi
0x180025477  call    InterfaceLookupByICBSeqNumber
0x18002547c  mov     rbx, rax
0x18002547f  test    rax, rax
0x180025482  jz      loc_1800257A9
0x180025488  cmp     dword ptr [rax+90h], 0
0x18002548f  jnz     short loc_1800254C7
0x180025491  lea     rcx, Resource; Resource
0x180025498  mov     dword ptr [rax+0A8h], 1
0x1800254a2  call    cs:__imp_RtlReleaseResource
0x1800254a8  mov     rcx, r12; lpCriticalSection
0x1800254ab  call    cs:__imp_EnterCriticalSection
0x1800254b1  dec     dword ptr cs:RouterState+4
0x1800254b7  mov     rcx, r12; lpCriticalSection
0x1800254ba  call    cs:__imp_LeaveCriticalSection
0x1800254c0  xor     eax, eax
0x1800254c2  jmp     loc_180025871
0x1800254c7  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800254ce  test    al, al
0x1800254d0  jns     short loc_180025542
0x1800254d2  xor     eax, eax
0x1800254d4  lea     rdx, aInterfacenotre_4; "InterfaceNotReachable: %ws is not reach"...
0x1800254db  mov     word ptr [rsp+898h+var_828], ax
0x1800254e0  lea     rcx, [rsp+898h+var_828]
0x1800254e5  mov     word ptr [rsp+898h+var_850], ax
0x1800254ea  mov     r9d, r14d
0x1800254ed  mov     r8, [rbx+48h]
0x1800254f1  call    FormatRRASErrorString
0x1800254f6  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800254fd  test    al, al
0x1800254ff  jns     short loc_180025542
0x180025501  lea     rax, [rbx+2B0h]
0x180025508  mov     rcx, rdi
0x18002550b  test    rax, rax
0x18002550e  lea     r9, [rsp+898h+var_860]
0x180025513  lea     r8, [rsp+898h+var_828]
0x180025518  cmovnz  r9, rax
0x18002551c  lea     rdx, RasRtrmgrParamTraceInfo
0x180025523  lea     rax, [rsp+898h+var_850]
0x180025528  mov     [rsp+898h+var_870], rax
0x18002552d  mov     rax, [rbx+48h]
0x180025531  mov     [rsp+898h+var_878], rax
0x180025536  call    McTemplateU0zjzz_EventWriteTransfer
0x18002553b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180025542  cmp     dword ptr [rbx+90h], 3
0x180025549  jnz     loc_1800255D7
0x18002554f  cmp     r14d, 5
0x180025553  jz      short loc_1800255D0
0x180025555  mov     rcx, rbx
0x180025558  call    LanEtcInterfaceUpToDown
0x18002555d  test    eax, eax
0x18002555f  jz      short loc_1800255D0
0x180025561  mov     sil, 40h ; '@'
0x180025564  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18002556b  jz      short loc_1800255D0
0x18002556d  xor     ecx, ecx
0x18002556f  lea     rdx, aInterfacenotre_3; "InterfaceNotReachable: Failed to status"...
0x180025576  mov     word ptr [rsp+898h+var_828], cx
0x18002557b  mov     r8d, eax
0x18002557e  mov     word ptr [rsp+898h+var_850], cx
0x180025583  lea     rcx, [rsp+898h+var_828]
0x180025588  call    FormatRRASErrorString
0x18002558d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180025594  jz      short loc_1800255D0
0x180025596  lea     rax, [rbx+2B0h]
0x18002559d  mov     rcx, rdi
0x1800255a0  test    rax, rax
0x1800255a3  lea     r9, [rsp+898h+var_860]
0x1800255a8  lea     r8, [rsp+898h+var_828]
0x1800255ad  cmovnz  r9, rax
0x1800255b1  lea     rdx, RasRtrMgrParamTraceError
0x1800255b8  lea     rax, [rsp+898h+var_850]
0x1800255bd  mov     [rsp+898h+var_870], rax
0x1800255c2  mov     rax, [rbx+48h]
0x1800255c6  mov     [rsp+898h+var_878], rax
0x1800255cb  call    McTemplateU0zjzz_EventWriteTransfer
0x1800255d0  xor     ebx, ebx
0x1800255d2  jmp     loc_18002577F
0x1800255d7  mov     ecx, [rbx+0A8h]
0x1800255dd  cmp     ecx, 3
0x1800255e0  jnz     loc_18002570D
0x1800255e6  mov     rcx, rbx
0x1800255e9  call    NotifyWanarpOfFailure
0x1800255ee  mov     r8d, eax
0x1800255f1  mov     sil, 40h ; '@'
0x1800255f4  cmp     eax, 103h
0x1800255f9  jz      short loc_18002566A
0x1800255fb  test    eax, eax
0x1800255fd  jz      short loc_18002566A
0x1800255ff  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180025606  jz      short loc_18002566A
0x180025608  xor     ecx, ecx
0x18002560a  lea     rdx, aInterfacenotre_2; "InterfaceNotReachable: IOCTL_WANARP_CON"...
0x180025611  mov     word ptr [rsp+898h+var_828], cx
0x180025616  xor     eax, eax
0x180025618  lea     rcx, [rsp+898h+var_828]
0x18002561d  mov     word ptr [rsp+898h+var_850], ax
0x180025622  call    FormatRRASErrorString
0x180025627  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18002562e  jz      short loc_18002566A
0x180025630  lea     rax, [rbx+2B0h]
0x180025637  mov     rcx, rdi
0x18002563a  test    rax, rax
0x18002563d  lea     r9, [rsp+898h+var_860]
0x180025642  lea     r8, [rsp+898h+var_828]
0x180025647  cmovnz  r9, rax
0x18002564b  lea     rdx, RasRtrMgrParamTraceError
0x180025652  lea     rax, [rsp+898h+var_850]
0x180025657  mov     [rsp+898h+var_870], rax
0x18002565c  mov     rax, [rbx+48h]
0x180025660  mov     [rsp+898h+var_878], rax
0x180025665  call    McTemplateU0zjzz_EventWriteTransfer
0x18002566a  mov     rcx, rbx
0x18002566d  call    ClearWfpFiltersForInterfaceFromWanarp
0x180025672  test    eax, eax
0x180025674  jz      short loc_1800256E2
0x180025676  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18002567d  jz      short loc_1800256E2
0x18002567f  xor     ecx, ecx
0x180025681  lea     rdx, aInterfacenotre_5; "InterfaceNotReachable: ClearWfpFiltersF"...
0x180025688  mov     word ptr [rsp+898h+var_828], cx
0x18002568d  mov     r8d, eax
0x180025690  mov     word ptr [rsp+898h+var_850], cx
0x180025695  lea     rcx, [rsp+898h+var_828]
0x18002569a  call    FormatRRASErrorString
0x18002569f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x1800256a6  jz      short loc_1800256E2
0x1800256a8  lea     rax, [rbx+2B0h]
0x1800256af  mov     rcx, rdi
0x1800256b2  test    rax, rax
0x1800256b5  lea     r9, [rsp+898h+var_860]
0x1800256ba  lea     r8, [rsp+898h+var_828]
0x1800256bf  cmovnz  r9, rax
0x1800256c3  lea     rdx, RasRtrMgrParamTraceError
0x1800256ca  lea     rax, [rsp+898h+var_850]
0x1800256cf  mov     [rsp+898h+var_870], rax
0x1800256d4  mov     rax, [rbx+48h]
0x1800256d8  mov     [rsp+898h+var_878], rax
0x1800256dd  call    McTemplateU0zjzz_EventWriteTransfer
0x1800256e2  xor     edx, edx
0x1800256e4  mov     rcx, rbx
0x1800256e7  call    UpdateOrClearDodRoutesForInterface
0x1800256ec  mov     rcx, rbx
0x1800256ef  call    DeAllocateBindings
0x1800256f4  mov     dword ptr [rbx+0B4h], 0
0x1800256fe  xor     edx, edx
0x180025700  mov     rcx, rbx
0x180025703  call    WanInterfaceInactiveToDown
0x180025708  jmp     loc_1800257EA
0x18002570d  cmp     ecx, 4
0x180025710  jnz     short loc_1800256FE
0x180025712  test    al, al
0x180025714  jns     short loc_18002577A
0x180025716  xor     eax, eax
0x180025718  lea     rdx, aInterfacenotre_0; "InterfaceNotReachable: %ws is already c"...
0x18002571f  mov     word ptr [rsp+898h+var_828], ax
0x180025724  lea     rcx, [rsp+898h+var_828]
0x180025729  mov     word ptr [rsp+898h+var_850], ax
0x18002572e  mov     r8, [rbx+48h]
0x180025732  call    FormatRRASErrorString
0x180025737  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18002573e  jge     short loc_18002577A
0x180025740  lea     rax, [rbx+2B0h]
0x180025747  mov     rcx, rdi
0x18002574a  test    rax, rax
0x18002574d  lea     r9, [rsp+898h+var_860]
0x180025752  lea     r8, [rsp+898h+var_828]
0x180025757  cmovnz  r9, rax
0x18002575b  lea     rdx, RasRtrmgrParamTraceInfo
0x180025762  lea     rax, [rsp+898h+var_850]
0x180025767  mov     [rsp+898h+var_870], rax
0x18002576c  mov     rax, [rbx+48h]
0x180025770  mov     [rsp+898h+var_878], rax
0x180025775  call    McTemplateU0zjzz_EventWriteTransfer
0x18002577a  mov     ebx, 649h
0x18002577f  lea     rcx, Resource; Resource
0x180025786  call    cs:__imp_RtlReleaseResource
0x18002578c  mov     rcx, r12; lpCriticalSection
0x18002578f  call    cs:__imp_EnterCriticalSection
0x180025795  dec     dword ptr cs:RouterState+4
0x18002579b  mov     rcx, r12; lpCriticalSection
0x18002579e  call    cs:__imp_LeaveCriticalSection
0x1800257a4  jmp     loc_18002586F
0x1800257a9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800257b0  jge     short loc_1800257EA
0x1800257b2  xor     eax, eax
0x1800257b4  lea     rdx, aInterfacenotre; "InterfaceNotReachable : No interface wi"...
0x1800257bb  mov     r8d, esi
0x1800257be  mov     word ptr [rsp+898h+var_828], ax
0x1800257c3  lea     rcx, [rsp+898h+var_828]
0x1800257c8  call    FormatRRASErrorString
0x1800257cd  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800257d4  jge     short loc_1800257EA
0x1800257d6  lea     r8, [rsp+898h+var_828]
0x1800257db  mov     rcx, rdi
0x1800257de  lea     rdx, RasRtrmgrTraceInfo
0x1800257e5  call    McTemplateU0z_EventWriteTransfer
0x1800257ea  lea     rcx, Resource; Resource
0x1800257f1  call    cs:__imp_RtlReleaseResource
0x1800257f7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800257fe  jz      loc_1800254A8
0x180025804  lea     r8, aLeavingInterfa; "Leaving: InterfaceNotReachable"
0x18002580b  mov     rcx, rdi
0x18002580e  lea     rdx, RasRtrmgrTraceInfo
0x180025815  call    McTemplateU0z_EventWriteTransfer
0x18002581a  jmp     loc_1800254A8
0x18002581f  call    cs:__imp_LeaveCriticalSection
0x180025825  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18002582c  mov     ebx, 384h
0x180025831  jge     short loc_18002586F
0x180025833  xor     eax, eax
0x180025835  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x18002583c  mov     r8d, ebx
0x18002583f  mov     word ptr [rsp+898h+var_828], ax
0x180025844  lea     rcx, [rsp+898h+var_828]
0x180025849  call    FormatRRASErrorString
0x18002584e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180025855  jge     short loc_18002586F
0x180025857  lea     r8, [rsp+898h+var_828]
0x18002585c  lea     rdx, RasRtrmgrTraceInfo
0x180025863  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002586a  call    McTemplateU0z_EventWriteTransfer
0x18002586f  mov     eax, ebx
0x180025871  mov     rcx, [rsp+898h+var_28]
0x180025879  xor     rcx, rsp; StackCookie
0x18002587c  call    __security_check_cookie
0x180025881  lea     r11, [rsp+898h+var_18]
0x180025889  mov     rbx, [r11+30h]
0x18002588d  mov     rsi, [r11+38h]
0x180025891  mov     rsp, r11
0x180025894  pop     r14
0x180025896  pop     r12
0x180025898  pop     rdi
0x180025899  retn
```

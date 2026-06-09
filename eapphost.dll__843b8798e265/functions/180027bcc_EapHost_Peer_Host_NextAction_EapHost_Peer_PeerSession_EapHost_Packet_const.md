# EapHost::Peer::Host::NextAction(EapHost::Peer::PeerSession &,EapHost::Packet const &)

- ea: `0x180027bcc`
- end: `0x180028c14`
- name: `?NextAction@Host@Peer@EapHost@@AEAA?AW4RequestActionType@RequestActionValue@23@AEAVPeerSession@23@AEBVPacket@3@@Z`
- size: `4168`
- prototype: `enum EapHost::Peer::RequestActionValue::RequestActionType __high(struct EapHost::Peer::PeerSession *, const struct EapHost::Packet *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028f50`

## callees

- `0x180002af0`
- `0x180004b4c`
- `0x180004fb8`
- `0x180007564`
- `0x18000a21c`
- `0x18000a24c`
- `0x18000a4d4`
- `0x18000a528`
- `0x180011a04`
- `0x180011cb8`
- `0x1800120c4`
- `0x180015530`
- `0x18001df04`
- `0x18001df74`
- `0x18001e04c`
- `0x180023c40`
- `0x180027908`
- `0x180027948`
- `0x180027bcc`
- `0x18002f8a0`
- `0x180030b08`
- `0x180030e4c`
- `0x180030f54`
- `0x1800343a8`
- `0x18003512c`
- `0x180039010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180027cb6`
- `ntdll!EtwEventEnabled` at `0x180027d4f`
- `ntdll!EtwEventEnabled` at `0x180027dff`
- `ntdll!EtwEventEnabled` at `0x180027ea1`
- `ntdll!EtwEventEnabled` at `0x180027ffd`
- `ntdll!EtwEventEnabled` at `0x1800280c0`
- `ntdll!EtwEventEnabled` at `0x180028206`
- `ntdll!EtwEventEnabled` at `0x1800282e5`
- `ntdll!EtwEventEnabled` at `0x180028381`
- `ntdll!EtwEventEnabled` at `0x180028418`
- `ntdll!EtwEventEnabled` at `0x180028501`
- `ntdll!EtwEventEnabled` at `0x1800285c1`
- `ntdll!EtwEventEnabled` at `0x1800288a7`
- `ntdll!EtwEventEnabled` at `0x180028a07`
- `ntdll!EtwEventEnabled` at `0x180028ac8`
- `ntdll!EtwEventEnabled` at `0x180028b45`
- `ntdll!EtwEventEnabled` at `0x180027cb6`
- `ntdll!EtwEventEnabled` at `0x180027d4f`
- `ntdll!EtwEventEnabled` at `0x180027dff`
- `ntdll!EtwEventEnabled` at `0x180027ea1`
- `ntdll!EtwEventEnabled` at `0x180027ffd`
- `ntdll!EtwEventEnabled` at `0x1800280c0`
- `ntdll!EtwEventEnabled` at `0x180028206`
- `ntdll!EtwEventEnabled` at `0x1800282e5`
- `ntdll!EtwEventEnabled` at `0x180028381`
- `ntdll!EtwEventEnabled` at `0x180028418`
- `ntdll!EtwEventEnabled` at `0x180028501`
- `ntdll!EtwEventEnabled` at `0x1800285c1`
- `ntdll!EtwEventEnabled` at `0x1800288a7`
- `ntdll!EtwEventEnabled` at `0x180028a07`
- `ntdll!EtwEventEnabled` at `0x180028ac8`
- `ntdll!EtwEventEnabled` at `0x180028b45`

## string_xrefs

- `0x180028303`: `Session(%d) IsIdentityRequest received in unexpected state (%d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall EapHost::Peer::Host::NextAction(volatile signed __int32 *a1, __int64 a2, unsigned __int8 *a3)
{
  char v5; // r14
  unsigned int v6; // esi
  __int64 v7; // r9
  unsigned __int8 v8; // bl
  int v9; // r8d
  const char *v10; // r13
  const char *v11; // rax
  __int64 *Type; // rax
  __int64 v13; // rbx
  _QWORD *v14; // rax
  bool v15; // bl
  __int64 v16; // rsi
  const struct EapHost::EapType *v17; // rdx
  char v18; // al
  int v19; // r12d
  int v20; // r8d
  int v21; // r15d
  int v22; // ecx
  int v23; // r9d
  int v24; // eax
  __int64 v25; // r9
  int v26; // eax
  EapHost::Packet *v27; // rcx
  unsigned int v28; // eax
  int v29; // eax
  _OWORD *v30; // r15
  const struct ConstBuffer *v31; // rax
  __int64 v32; // r11
  __int64 v33; // rbx
  const struct _EAP_TYPE *v34; // rsi
  int v35; // r11d
  ReferenceCounted *v36; // rbx
  ReferenceCounted *v37; // rcx
  volatile signed __int32 *v38; // rbx
  char v39; // bl
  __int64 v40; // r15
  const struct EapHost::EapType *v41; // rdx
  char v42; // al
  int v43; // r8d
  int v44; // r10d
  int v45; // r12d
  int v46; // r9d
  int v47; // eax
  __int64 v48; // r9
  int v49; // eax
  int v50; // eax
  int v51; // r8d
  const char *v52; // r13
  const char *v53; // rax
  char v55[8]; // [rsp+50h] [rbp-B0h] BYREF
  char v56[8]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+64h] [rbp-9Ch]
  __int64 v59; // [rsp+70h] [rbp-90h] BYREF
  void *v60; // [rsp+78h] [rbp-88h] BYREF
  ReferenceCounted *v61; // [rsp+80h] [rbp-80h] BYREF
  void *v62; // [rsp+88h] [rbp-78h] BYREF
  __int64 v63; // [rsp+90h] [rbp-70h]
  volatile signed __int32 *v64; // [rsp+98h] [rbp-68h]
  void *v65[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v66; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-40h]
  int v68; // [rsp+C8h] [rbp-38h]
  char v69[32]; // [rsp+D0h] [rbp-30h] BYREF
  char v70[2048]; // [rsp+F0h] [rbp-10h] BYREF

  v64 = a1;
  v5 = 0;
  LODWORD(v60) = 0;
  v6 = 8;
  v7 = *(_QWORD *)(a2 + 304);
  if ( v7 && *(_BYTE *)(v7 + 1) == a3[1] )
  {
    v8 = *a3;
    if ( *a3 == 1
      && _byteswap_ushort(*(_WORD *)(v7 + 2)) == _byteswap_ushort(*((_WORD *)a3 + 1))
      && !memcmp_0(
            (const void *)v7,
            a3,
            (unsigned __int16)(*(unsigned __int8 *)(v7 + 2) << 8) | (unsigned __int64)*(unsigned __int8 *)(v7 + 3)) )
    {
      if ( EapHost::Packet::IsIdentityRequest((EapHost::Packet *)a3) && *(_DWORD *)(a2 + 268) == 1 )
      {
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
          && (int)StringCchPrintfA(v70, 0x800u, " Session(%d), discard dup identity request", *(_DWORD *)(a2 + 56)) >= 0
          && Microsoft_Windows_EapHostEnableBits < 0 )
        {
          McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
            *(unsigned int *)(a2 + 56));
        }
      }
      else
      {
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
          && (int)StringCchPrintfA(v70, 0x800u, " Session(%d), Retransmit", *(_DWORD *)(a2 + 56)) >= 0
          && Microsoft_Windows_EapHostEnableBits < 0 )
        {
          McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
            *(unsigned int *)(a2 + 56));
        }
        return 3;
      }
      return v6;
    }
    if ( *(_DWORD *)(a2 + 268) == 3 && *(_BYTE *)(a2 + 132) == 17 )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v70, 0x800u, " Session(%d), Leap, continueMethod", *(_DWORD *)(a2 + 56)) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a2 + 56));
      }
      return 6;
    }
    if ( (unsigned __int8)(v8 - 3) <= 1u )
    {
      v10 = "success";
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
      {
        v11 = "success";
        if ( *a3 != 3 )
          v11 = "failure";
        if ( (int)StringCchPrintfA(v70, 0x800u, " Session(%d), %s.", *(_DWORD *)(a2 + 56), v11) >= 0
          && Microsoft_Windows_EapHostEnableBits < 0 )
        {
          McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
        }
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *a3 != 3 )
          v10 = "failure";
        WPP_SF_ds(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, v9, *(_DWORD *)(a2 + 56), (__int64)v10);
      }
      return 7;
    }
    v15 = 0;
    if ( EapHost::Packet::IsTypeRequest((EapHost::Packet *)a3) )
    {
      Type = (__int64 *)EapHost::Packet::GetType(*(_QWORD *)(a2 + 304), &v59);
      LODWORD(v60) = 1;
      v13 = *Type;
      v14 = (_QWORD *)EapHost::Packet::GetType(a3, &v61);
      v5 = 3;
      if ( !(unsigned __int8)operator==(*v14, v13) && *(_DWORD *)(a2 + 268) == 2 )
        v15 = 1;
    }
    if ( (v5 & 2) != 0 )
    {
      v5 &= ~2u;
      std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(&v61);
    }
    if ( (v5 & 1) != 0 )
      std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(&v59);
    if ( v15 )
    {
      EapHost::EapType::EapType((EapHost::EapType *)v56, (const struct _EAP_TYPE *)(a2 + 132));
      EapHost::Packet::GetType(a3, &v59);
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(
                  v70,
                  0x800u,
                  " Session(%d), Continue Method, 1st authentication packet has same ID (%d) as that of earlier packet.",
                  *(_DWORD *)(a2 + 56),
                  a3[1]) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a2 + 56),
          a3[1]);
      }
      v16 = v59;
      if ( (unsigned __int8)operator==(v56, v59)
        || EapHost::EapType::IsCompatibleExpandedTypeOf((EapHost::EapType *)v56, v17) )
      {
        v6 = 6;
      }
      else
      {
        v18 = EtwEventEnabled(eaphost_Context, DebugInfoEvent);
        v19 = HIDWORD(v58);
        v20 = v58;
        v21 = v57;
        if ( v18 )
        {
          if ( v57 == 0xFE )
          {
            v22 = HIDWORD(v58);
          }
          else
          {
            v22 = 0;
            v20 = 0;
          }
          if ( *(_BYTE *)(v16 + 8) == 0xFE )
          {
            v23 = *(_DWORD *)(v16 + 12);
            v24 = *(_DWORD *)(v16 + 16);
          }
          else
          {
            v23 = 0;
            v24 = 0;
          }
          if ( (int)StringCchPrintfA(
                      v70,
                      0x800u,
                      "Nak: Type mismatch Requested(VenId(%d), VenType(%d), Type(%d)),Available(VenId(%d), VenType(%d), T"
                      "ype(%d)), state(%d)",
                      v23,
                      v24,
                      *(unsigned __int8 *)(v16 + 8),
                      v20,
                      v22,
                      v57,
                      *(_DWORD *)(a2 + 268)) >= 0
            && Microsoft_Windows_EapHostEnableBits < 0 )
          {
            McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
          }
          v20 = v58;
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          if ( (_BYTE)v21 != 0xFE )
          {
            v19 = 0;
            v20 = 0;
          }
          if ( *(_BYTE *)(v16 + 8) == 0xFE )
          {
            v25 = *(unsigned int *)(v16 + 12);
            v26 = *(_DWORD *)(v16 + 16);
          }
          else
          {
            v25 = 0;
            v26 = 0;
          }
          WPP_SF_ddddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
            v25,
            v26,
            *(unsigned __int8 *)(v16 + 8),
            v20,
            v19,
            v21,
            *(_DWORD *)(a2 + 268));
        }
        v6 = 5;
      }
      std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(&v59);
    }
    else
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(
                  v70,
                  0x800u,
                  "Session(%d) Unexpected duplicate packet type (%d) when in state (%d)",
                  *(_DWORD *)(a2 + 56),
                  *a3,
                  *(_DWORD *)(a2 + 268)) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_ddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          65,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a2 + 56),
          *a3,
          *(_DWORD *)(a2 + 268));
      }
    }
  }
  else if ( EapHost::Packet::IsIdentityRequest((EapHost::Packet *)a3) )
  {
    v28 = *(_DWORD *)(a2 + 268);
    if ( v28 <= 1 )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v70, 0x800u, " Session(%d), IdentityRequest", *(_DWORD *)(a2 + 56)) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a2 + 56));
      }
      return 1;
    }
    else if ( v28 - 2 <= 1 )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(
                  v70,
                  0x800u,
                  " Session(%d), 2nd IdentityRequest(%d); ReAuth",
                  *(_DWORD *)(a2 + 56),
                  a3[1]) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a2 + 56),
          a3[1]);
      }
      return 2;
    }
    else
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(
                  v70,
                  0x800u,
                  "Session(%d) IsIdentityRequest received in unexpected state (%d)",
                  *(_DWORD *)(a2 + 56),
                  *(_DWORD *)(a2 + 268)) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a2 + 56),
          *(_DWORD *)(a2 + 268));
      }
    }
  }
  else if ( *a3 == 1
         && ((v57 = 0, v58 = 0, EapHost::Packet::GetType(v27, (struct EapHost::EapType *)v56), v57 == 2)
          || v57 == 0xFE && v58 == 0x200000000LL)
         && *(_BYTE *)(a2 + 277) )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v70, 0x800u, " Session(%d), NotificationRequest", *(_DWORD *)(a2 + 56)) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
        *(unsigned int *)(a2 + 56));
    }
    return 4;
  }
  else if ( !EapHost::Packet::IsTypeRequest((EapHost::Packet *)a3)
         || (v29 = *(_DWORD *)(a2 + 268), (v29 & 0xFFFFFFFC) != 0)
         || v29 == 1 )
  {
    if ( (unsigned __int8)(*a3 - 3) > 1u )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(
                  v70,
                  0x800u,
                  "Session(%d) Unexpected packet type (%d) when in state (%d)",
                  *(_DWORD *)(a2 + 56),
                  *a3,
                  *(_DWORD *)(a2 + 268)) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_ddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a2 + 56),
          *a3,
          *(_DWORD *)(a2 + 268));
      }
    }
    else
    {
      v52 = "success";
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
      {
        v53 = "success";
        if ( *a3 != 3 )
          v53 = "failure";
        if ( (int)StringCchPrintfA(v70, 0x800u, " Session(%d), %s, lastId != reqId", *(_DWORD *)(a2 + 56), v53) >= 0
          && Microsoft_Windows_EapHostEnableBits < 0 )
        {
          McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
        }
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *a3 != 3 )
          v52 = "failure";
        WPP_SF_ds(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, v51, *(_DWORD *)(a2 + 56), (__int64)v52);
      }
      if ( *(_DWORD *)(a2 + 268) )
        return 7;
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
        && (int)StringCchPrintfA(v70, 0x800u, "Received Success/Failure before Identity request, discarding") >= 0
        && (byte_18004F981 & 8) != 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v70);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids);
      }
    }
  }
  else
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v70, 0x800u, " Session(%d), TypeRequest", *(_DWORD *)(a2 + 56)) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
        *(unsigned int *)(a2 + 56));
    }
    EapHost::EapType::EapType((EapHost::EapType *)v56, (const struct _EAP_TYPE *)(a2 + 132));
    EapHost::Packet::GetType(a3, &v59);
    v30 = (_OWORD *)(a2 + 132);
    if ( *(_BYTE *)(a2 + 132) )
    {
      v40 = v59;
      if ( (unsigned __int8)operator==(v56, v59)
        || EapHost::EapType::IsCompatibleExpandedTypeOf((EapHost::EapType *)v56, v41) )
      {
        v6 = 6;
      }
      else
      {
        v42 = EtwEventEnabled(eaphost_Context, DebugInfoEvent);
        v43 = HIDWORD(v58);
        v44 = v58;
        v45 = v57;
        if ( v42 )
        {
          if ( v57 != 0xFE )
          {
            v43 = 0;
            v44 = 0;
          }
          if ( *(_BYTE *)(v40 + 8) == 0xFE )
          {
            v46 = *(_DWORD *)(v40 + 12);
            v47 = *(_DWORD *)(v40 + 16);
          }
          else
          {
            v46 = 0;
            v47 = 0;
          }
          if ( (int)StringCchPrintfA(
                      v70,
                      0x800u,
                      "Nak: Type mismatch Requested(VenId(%d), VenType(%d), Type(%d)),Available(VenId(%d), VenType(%d), T"
                      "ype(%d)), state(%d)",
                      v46,
                      v47,
                      *(unsigned __int8 *)(v40 + 8),
                      v44,
                      v43,
                      v57,
                      *(_DWORD *)(a2 + 268)) >= 0
            && Microsoft_Windows_EapHostEnableBits < 0 )
          {
            McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v70);
          }
          v43 = HIDWORD(v58);
          v44 = v58;
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          if ( (_BYTE)v45 != 0xFE )
          {
            v43 = 0;
            v44 = 0;
          }
          if ( *(_BYTE *)(v40 + 8) == 0xFE )
          {
            v48 = *(unsigned int *)(v40 + 12);
            v49 = *(_DWORD *)(v40 + 16);
          }
          else
          {
            v48 = 0;
            v49 = 0;
          }
          WPP_SF_ddddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            55,
            WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
            v48,
            v49,
            *(unsigned __int8 *)(v40 + 8),
            v44,
            v43,
            v45,
            *(_DWORD *)(a2 + 268));
        }
        v50 = 8;
        if ( *(_DWORD *)(a2 + 268) != 3 )
          v50 = 5;
        v6 = v50;
      }
    }
    else
    {
      v65[0] = 0;
      v65[1] = 0;
      v66 = 0;
      v67 = 0;
      TempBuffer<0>::Assign(v65, *(_QWORD *)(a2 + 232));
      v31 = (const struct ConstBuffer *)TempBuffer<0>::TempBuffer<0>(&v62, v65);
      EapLm::Peer::GenericIdentityMarshaller::Unmarshal(v31, (struct EapHost::Peer::_EapHostGenericCredentials *)&v66);
      HeapAllocator::Free(v62);
      v32 = 0;
      v33 = v67;
      while ( (unsigned int)v32 < (unsigned int)v66 )
      {
        v34 = (const struct _EAP_TYPE *)(v33 + 48 * v32);
        EapHost::EapType::EapType((EapHost::EapType *)v69, v34);
        if ( (unsigned __int8)operator==(v69, v59) )
        {
          *v30 = *(_OWORD *)&v34->type;
          TempBuffer<0>::Assign(a2 + 208, v34[1].dwVendorId);
          TempBuffer<0>::Assign(a2 + 224, v34[2].dwVendorType);
          EapHost::EapType::EapType((EapHost::EapType *)&v66, (const struct _EAP_TYPE *)(a2 + 132));
          *(_QWORD *)&v66 = &EapHost::EapMethodType::`vftable';
          v68 = *(_DWORD *)(a2 + 144);
          EapLm::Peer::EapLibraryManagerRuntime::GetEapMethodRuntime(*((EapLm::BaseEapLibraryManager **)v64 + 19));
          v36 = v61;
          v37 = *(ReferenceCounted **)(a2 + 288);
          if ( v61 != v37 )
          {
            if ( v37 )
              ReferenceCounted::Release(v37);
            *(_QWORD *)(a2 + 288) = v36;
            if ( v36 )
              _InterlockedAdd((volatile signed __int32 *)v36 + 2, 1u);
          }
          if ( !v34[2].dwVendorType )
          {
            v62 = 0;
            v63 = 0;
            v60 = 0;
            v55[0] = 0;
            v38 = *(volatile signed __int32 **)(a2 + 288);
            v64 = v38;
            if ( v38 )
              _InterlockedAdd(v38 + 2, 1u);
            (*(void (__fastcall **)(volatile signed __int32 *, _QWORD, __int64, __int64, __int64, void **, void **, char *))(*(_QWORD *)v38 + 32LL))(
              v38,
              *(unsigned int *)(a2 + 128),
              a2 + 192,
              a2 + 208,
              a2 + 224,
              &v62,
              &v60,
              v55);
            if ( v38 )
              ReferenceCounted::Release((ReferenceCounted *)v38);
            if ( !v55[0] )
              TempBuffer<0>::Assign(a2 + 224, v63);
            HeapAllocator::Free(v60);
            v60 = 0;
            HeapAllocator::Free(v62);
          }
          if ( v61 )
            ReferenceCounted::Release(v61);
          break;
        }
        v32 = (unsigned int)(v35 + 1);
      }
      v39 = *(_BYTE *)v30;
      HeapAllocator::Free(v65[0]);
      v6 = (v39 != 0) + 5;
    }
    std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(&v59);
  }
  return v6;
}

```

## disassembly

```asm
0x180027bcc  mov     [rsp-8+arg_18], rbx
0x180027bd1  push    rbp
0x180027bd2  push    rsi
0x180027bd3  push    rdi
0x180027bd4  push    r12
0x180027bd6  push    r13
0x180027bd8  push    r14
0x180027bda  push    r15
0x180027bdc  lea     rbp, [rsp-800h]
0x180027be4  sub     rsp, 900h
0x180027beb  mov     rax, cs:__security_cookie
0x180027bf2  xor     rax, rsp
0x180027bf5  mov     [rbp+830h+var_40], rax
0x180027bfc  mov     r15, r8
0x180027bff  mov     rdi, rdx
0x180027c02  mov     [rbp+830h+var_898], rcx
0x180027c06  xor     r14d, r14d
0x180027c09  mov     dword ptr [rsp+930h+var_8B8], r14d
0x180027c0e  lea     esi, [r14+8]
0x180027c12  mov     r9, [rdx+130h]
0x180027c19  test    r9, r9
0x180027c1c  jz      loc_1800282A3
0x180027c22  mov     al, [r8+1]
0x180027c26  cmp     [r9+1], al
0x180027c2a  jnz     loc_1800282A3
0x180027c30  mov     bl, [r8]
0x180027c33  lea     r12d, [r14+1]
0x180027c37  cmp     bl, r12b
0x180027c3a  jnz     loc_180027DD4
0x180027c40  movzx   edx, byte ptr [r9+2]
0x180027c45  shl     dx, 8
0x180027c49  movzx   r8d, byte ptr [r9+3]
0x180027c4e  movzx   ecx, byte ptr [r15+2]
0x180027c53  shl     cx, 8
0x180027c57  movzx   eax, byte ptr [r15+3]
0x180027c5c  or      cx, ax
0x180027c5f  movzx   eax, r8w
0x180027c63  or      ax, dx
0x180027c66  cmp     ax, cx
0x180027c69  jnz     loc_180027DD4
0x180027c6f  movzx   eax, dx
0x180027c72  or      r8, rax; Size
0x180027c75  mov     rdx, r15; Buf2
0x180027c78  mov     rcx, r9; Buf1
0x180027c7b  call    memcmp_0
0x180027c80  test    eax, eax
0x180027c82  jnz     loc_180027DD4
0x180027c88  mov     rcx, r15; this
0x180027c8b  call    ?IsIdentityRequest@Packet@EapHost@@QEBA_NXZ; EapHost::Packet::IsIdentityRequest(void)
0x180027c90  test    al, al
0x180027c92  jz      loc_180027D3E
0x180027c98  cmp     [rdi+10Ch], r12d
0x180027c9f  jnz     loc_180027D3E
0x180027ca5  lea     rbx, DebugInfoEvent
0x180027cac  mov     rdx, rbx
0x180027caf  mov     rcx, cs:eaphost_Context
0x180027cb6  call    cs:__imp_EtwEventEnabled
0x180027cbd  nop     dword ptr [rax+rax+00h]
0x180027cc2  test    al, al
0x180027cc4  jz      short loc_180027CFF
0x180027cc6  mov     r9d, [rdi+38h]
0x180027cca  lea     r8, aSessionDDiscar_0; " Session(%d), discard dup identity requ"...
0x180027cd1  mov     edx, 800h; unsigned __int64
0x180027cd6  lea     rcx, [rbp+830h+var_840]; char *
0x180027cda  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180027cdf  test    eax, eax
0x180027ce1  js      short loc_180027CFF
0x180027ce3  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x180027cea  jz      short loc_180027CFF
0x180027cec  lea     r8, [rbp+830h+var_840]
0x180027cf0  mov     rdx, rbx
0x180027cf3  lea     rcx, eaphost_Context
0x180027cfa  call    McTemplateU0s_EtwEventWriteTransfer
0x180027cff  lea     r14, WPP_GLOBAL_Control
0x180027d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d0d  cmp     rcx, r14
0x180027d10  jz      loc_180028BE7
0x180027d16  test    byte ptr [rcx+1Ch], 4
0x180027d1a  jz      loc_180028BE7
0x180027d20  mov     edx, 3Bh ; ';'
0x180027d25  mov     r9d, [rdi+38h]
0x180027d29  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180027d30  mov     rcx, [rcx+10h]
0x180027d34  call    WPP_SF_d
0x180027d39  jmp     loc_180028BE7
0x180027d3e  lea     rbx, DebugInfoEvent
0x180027d45  mov     rdx, rbx
0x180027d48  mov     rcx, cs:eaphost_Context
0x180027d4f  call    cs:__imp_EtwEventEnabled
0x180027d56  nop     dword ptr [rax+rax+00h]
0x180027d5b  test    al, al
0x180027d5d  jz      short loc_180027D98
0x180027d5f  mov     r9d, [rdi+38h]
0x180027d63  lea     r8, aSessionDRetran; " Session(%d), Retransmit"
0x180027d6a  mov     edx, 800h; unsigned __int64
0x180027d6f  lea     rcx, [rbp+830h+var_840]; char *
0x180027d73  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180027d78  test    eax, eax
0x180027d7a  js      short loc_180027D98
0x180027d7c  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x180027d83  jz      short loc_180027D98
0x180027d85  lea     r8, [rbp+830h+var_840]
0x180027d89  mov     rdx, rbx
0x180027d8c  lea     rcx, eaphost_Context
0x180027d93  call    McTemplateU0s_EtwEventWriteTransfer
0x180027d98  lea     r14, WPP_GLOBAL_Control
0x180027d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027da6  cmp     rcx, r14
0x180027da9  jz      short loc_180027DCA
0x180027dab  test    byte ptr [rcx+1Ch], 4
0x180027daf  jz      short loc_180027DCA
0x180027db1  mov     edx, 3Ch ; '<'
0x180027db6  mov     r9d, [rdi+38h]
0x180027dba  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180027dc1  mov     rcx, [rcx+10h]
0x180027dc5  call    WPP_SF_d
0x180027dca  mov     esi, 3
0x180027dcf  jmp     loc_180028BE7
0x180027dd4  cmp     dword ptr [rdi+10Ch], 3
0x180027ddb  jnz     loc_180027E84
0x180027de1  cmp     byte ptr [rdi+84h], 11h
0x180027de8  jnz     loc_180027E84
0x180027dee  lea     rbx, DebugInfoEvent
0x180027df5  mov     rdx, rbx
0x180027df8  mov     rcx, cs:eaphost_Context
0x180027dff  call    cs:__imp_EtwEventEnabled
0x180027e06  nop     dword ptr [rax+rax+00h]
0x180027e0b  test    al, al
0x180027e0d  jz      short loc_180027E48
0x180027e0f  mov     r9d, [rdi+38h]
0x180027e13  lea     r8, aSessionDLeapCo; " Session(%d), Leap, continueMethod"
0x180027e1a  mov     edx, 800h; unsigned __int64
0x180027e1f  lea     rcx, [rbp+830h+var_840]; char *
0x180027e23  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180027e28  test    eax, eax
0x180027e2a  js      short loc_180027E48
0x180027e2c  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x180027e33  jz      short loc_180027E48
0x180027e35  lea     r8, [rbp+830h+var_840]
0x180027e39  mov     rdx, rbx
0x180027e3c  lea     rcx, eaphost_Context
0x180027e43  call    McTemplateU0s_EtwEventWriteTransfer
0x180027e48  lea     r14, WPP_GLOBAL_Control
0x180027e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e56  cmp     rcx, r14
0x180027e59  jz      short loc_180027E7A
0x180027e5b  test    byte ptr [rcx+1Ch], 4
0x180027e5f  jz      short loc_180027E7A
0x180027e61  mov     edx, 3Dh ; '='
0x180027e66  mov     r9d, [rdi+38h]
0x180027e6a  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180027e71  mov     rcx, [rcx+10h]
0x180027e75  call    WPP_SF_d
0x180027e7a  mov     esi, 6
0x180027e7f  jmp     loc_180028BE7
0x180027e84  sub     bl, 3
0x180027e87  cmp     bl, r12b
0x180027e8a  ja      loc_180027F4A
0x180027e90  lea     rbx, DebugInfoEvent
0x180027e97  mov     rdx, rbx
0x180027e9a  mov     rcx, cs:eaphost_Context
0x180027ea1  call    cs:__imp_EtwEventEnabled
0x180027ea8  nop     dword ptr [rax+rax+00h]
0x180027ead  lea     r13, aSuccess; "success"
0x180027eb4  lea     rsi, aFailure; "failure"
0x180027ebb  test    al, al
0x180027ebd  jz      short loc_180027F08
0x180027ebf  mov     rax, r13
0x180027ec2  cmp     byte ptr [r15], 3
0x180027ec6  cmovnz  rax, rsi
0x180027eca  mov     [rsp+930h+var_910], rax
0x180027ecf  mov     r9d, [rdi+38h]
0x180027ed3  lea     r8, aSessionDS; " Session(%d), %s."
0x180027eda  mov     edx, 800h; unsigned __int64
0x180027edf  lea     rcx, [rbp+830h+var_840]; char *
0x180027ee3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180027ee8  test    eax, eax
0x180027eea  js      short loc_180027F08
0x180027eec  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x180027ef3  jz      short loc_180027F08
0x180027ef5  lea     r8, [rbp+830h+var_840]
0x180027ef9  mov     rdx, rbx
0x180027efc  lea     rcx, eaphost_Context
0x180027f03  call    McTemplateU0s_EtwEventWriteTransfer
0x180027f08  lea     r14, WPP_GLOBAL_Control
0x180027f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f16  cmp     rcx, r14
0x180027f19  jz      short loc_180027F40
0x180027f1b  test    byte ptr [rcx+1Ch], 4
0x180027f1f  jz      short loc_180027F40
0x180027f21  cmp     byte ptr [r15], 3
0x180027f25  cmovnz  r13, rsi
0x180027f29  mov     edx, 3Eh ; '>'
0x180027f2e  mov     [rsp+930h+var_910], r13
0x180027f33  mov     r9d, [rdi+38h]
0x180027f37  mov     rcx, [rcx+10h]
0x180027f3b  call    WPP_SF_ds
0x180027f40  mov     esi, 7
0x180027f45  jmp     loc_180028BE7
0x180027f4a  mov     rcx, r15; this
0x180027f4d  call    ?IsTypeRequest@Packet@EapHost@@QEBA_NXZ; EapHost::Packet::IsTypeRequest(void)
0x180027f52  test    al, al
0x180027f54  jz      short loc_180027F9F
0x180027f56  lea     rdx, [rsp+930h+var_8C0]
0x180027f5b  mov     rcx, [rdi+130h]
0x180027f62  call    ?GetType@Packet@EapHost@@QEBA?AV?$unique_ptr@VEapType@EapHost@@U?$default_delete@VEapType@EapHost@@@std@@@std@@XZ; EapHost::Packet::GetType(void)
0x180027f67  nop
0x180027f68  mov     dword ptr [rsp+930h+var_8B8], r12d
0x180027f6d  mov     rbx, [rax]
0x180027f70  lea     rdx, [rbp+830h+var_8B0]
0x180027f74  mov     rcx, r15
0x180027f77  call    ?GetType@Packet@EapHost@@QEBA?AV?$unique_ptr@VEapType@EapHost@@U?$default_delete@VEapType@EapHost@@@std@@@std@@XZ; EapHost::Packet::GetType(void)
0x180027f7c  mov     r14d, 3
0x180027f82  mov     rdx, rbx
0x180027f85  mov     rcx, [rax]
0x180027f88  call    ??8@YA_NAEBVEapType@EapHost@@0@Z; operator==(EapHost::EapType const &,EapHost::EapType const &)
0x180027f8d  test    al, al
0x180027f8f  jnz     short loc_180027F9F
0x180027f91  cmp     dword ptr [rdi+10Ch], 2
0x180027f98  jnz     short loc_180027F9F
0x180027f9a  mov     bl, r12b
0x180027f9d  jmp     short loc_180027FA1
0x180027f9f  xor     bl, bl
0x180027fa1  test    r14b, 2
0x180027fa5  jz      short loc_180027FB5
0x180027fa7  and     r14d, 0FFFFFFFDh
0x180027fab  lea     rcx, [rbp+830h+var_8B0]
0x180027faf  call    ??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(void)
0x180027fb4  nop
0x180027fb5  test    r12b, r14b
0x180027fb8  jz      short loc_180027FC4
0x180027fba  lea     rcx, [rsp+930h+var_8C0]
0x180027fbf  call    ??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(void)
0x180027fc4  test    bl, bl
0x180027fc6  jz      loc_1800281F5
0x180027fcc  lea     rdx, [rdi+84h]; struct _EAP_TYPE *
0x180027fd3  lea     rcx, [rsp+930h+var_8D8]; this
0x180027fd8  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x180027fdd  nop
0x180027fde  lea     rdx, [rsp+930h+var_8C0]
0x180027fe3  mov     rcx, r15
0x180027fe6  call    ?GetType@Packet@EapHost@@QEBA?AV?$unique_ptr@VEapType@EapHost@@U?$default_delete@VEapType@EapHost@@@std@@@std@@XZ; EapHost::Packet::GetType(void)
0x180027feb  nop
0x180027fec  lea     rbx, DebugInfoEvent
0x180027ff3  mov     rdx, rbx
0x180027ff6  mov     rcx, cs:eaphost_Context
0x180027ffd  call    cs:__imp_EtwEventEnabled
0x180028004  nop     dword ptr [rax+rax+00h]
0x180028009  test    al, al
0x18002800b  jz      short loc_18002804F
0x18002800d  movzx   eax, byte ptr [r15+1]
0x180028012  mov     dword ptr [rsp+930h+var_910], eax
0x180028016  mov     r9d, [rdi+38h]
0x18002801a  lea     r8, aSessionDContin; " Session(%d), Continue Method, 1st auth"...
0x180028021  mov     edx, 800h; unsigned __int64
0x180028026  lea     rcx, [rbp+830h+var_840]; char *
0x18002802a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002802f  test    eax, eax
0x180028031  js      short loc_18002804F
0x180028033  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x18002803a  jz      short loc_18002804F
0x18002803c  lea     r8, [rbp+830h+var_840]
0x180028040  mov     rdx, rbx
0x180028043  lea     rcx, eaphost_Context
0x18002804a  call    McTemplateU0s_EtwEventWriteTransfer
0x18002804f  lea     r14, WPP_GLOBAL_Control
0x180028056  mov     rcx, cs:WPP_GLOBAL_Control
0x18002805d  cmp     rcx, r14
0x180028060  jz      short loc_18002808A
0x180028062  test    byte ptr [rcx+1Ch], 4
0x180028066  jz      short loc_18002808A
0x180028068  movzx   eax, byte ptr [r15+1]
0x18002806d  mov     edx, 3Fh ; '?'
0x180028072  mov     dword ptr [rsp+930h+var_910], eax
0x180028076  mov     r9d, [rdi+38h]
0x18002807a  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180028081  mov     rcx, [rcx+10h]
0x180028085  call    WPP_SF_dd
0x18002808a  mov     rsi, [rsp+930h+var_8C0]
0x18002808f  mov     rdx, rsi
0x180028092  lea     rcx, [rsp+930h+var_8D8]
0x180028097  call    ??8@YA_NAEBVEapType@EapHost@@0@Z; operator==(EapHost::EapType const &,EapHost::EapType const &)
0x18002809c  test    al, al
0x18002809e  jnz     loc_1800281E0
0x1800280a4  lea     rcx, [rsp+930h+var_8D8]; this
0x1800280a9  call    ?IsCompatibleExpandedTypeOf@EapType@EapHost@@QEAA_NAEBV12@@Z; EapHost::EapType::IsCompatibleExpandedTypeOf(EapHost::EapType const &)
0x1800280ae  test    al, al
0x1800280b0  jnz     loc_1800281E0
0x1800280b6  mov     rdx, rbx
0x1800280b9  mov     rcx, cs:eaphost_Context
0x1800280c0  call    cs:__imp_EtwEventEnabled
0x1800280c7  nop     dword ptr [rax+rax+00h]
0x1800280cc  mov     r13b, 0FEh
0x1800280cf  mov     r12d, dword ptr [rsp+930h+var_8CC+4]
0x1800280d4  mov     r8d, dword ptr [rsp+930h+var_8CC]
0x1800280d9  movzx   r15d, [rsp+930h+var_8D0]
0x1800280df  test    al, al
0x1800280e1  jz      loc_18002816A
0x1800280e7  mov     r10d, [rdi+10Ch]
0x1800280ee  cmp     r15b, r13b
  ... truncated ...
```

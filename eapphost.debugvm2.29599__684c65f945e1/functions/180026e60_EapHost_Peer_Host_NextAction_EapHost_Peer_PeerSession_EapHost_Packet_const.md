# EapHost::Peer::Host::NextAction(EapHost::Peer::PeerSession &,EapHost::Packet const &)

- ea: `0x180026e60`
- end: `0x180027e47`
- name: `?NextAction@Host@Peer@EapHost@@AEAA?AW4RequestActionType@RequestActionValue@23@AEAVPeerSession@23@AEBVPacket@3@@Z`
- size: `4071`
- prototype: `enum EapHost::Peer::RequestActionValue::RequestActionType __high(struct EapHost::Peer::PeerSession *, const struct EapHost::Packet *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028168`

## callees

- `0x180002a90`
- `0x1800049d8`
- `0x180004e7c`
- `0x1800072cc`
- `0x180009dc4`
- `0x180009dec`
- `0x18000a050`
- `0x18000a09c`
- `0x1800112d4`
- `0x180011578`
- `0x180011958`
- `0x180014cfc`
- `0x18001d428`
- `0x18001d498`
- `0x18001d56c`
- `0x180022fd8`
- `0x180026ba4`
- `0x180026be4`
- `0x180026e60`
- `0x18002e7c0`
- `0x18002f93c`
- `0x18002fc40`
- `0x18002fd44`
- `0x180033008`
- `0x180033d6c`
- `0x180038010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180026f4a`
- `ntdll!EtwEventEnabled` at `0x180026fdd`
- `ntdll!EtwEventEnabled` at `0x180027087`
- `ntdll!EtwEventEnabled` at `0x180027123`
- `ntdll!EtwEventEnabled` at `0x180027279`
- `ntdll!EtwEventEnabled` at `0x180027336`
- `ntdll!EtwEventEnabled` at `0x180027476`
- `ntdll!EtwEventEnabled` at `0x18002754f`
- `ntdll!EtwEventEnabled` at `0x1800275e5`
- `ntdll!EtwEventEnabled` at `0x180027676`
- `ntdll!EtwEventEnabled` at `0x180027759`
- `ntdll!EtwEventEnabled` at `0x180027813`
- `ntdll!EtwEventEnabled` at `0x180027af3`
- `ntdll!EtwEventEnabled` at `0x180027c4d`
- `ntdll!EtwEventEnabled` at `0x180027d08`
- `ntdll!EtwEventEnabled` at `0x180027d7f`
- `ntdll!EtwEventEnabled` at `0x180026f4a`
- `ntdll!EtwEventEnabled` at `0x180026fdd`
- `ntdll!EtwEventEnabled` at `0x180027087`
- `ntdll!EtwEventEnabled` at `0x180027123`
- `ntdll!EtwEventEnabled` at `0x180027279`
- `ntdll!EtwEventEnabled` at `0x180027336`
- `ntdll!EtwEventEnabled` at `0x180027476`
- `ntdll!EtwEventEnabled` at `0x18002754f`
- `ntdll!EtwEventEnabled` at `0x1800275e5`
- `ntdll!EtwEventEnabled` at `0x180027676`
- `ntdll!EtwEventEnabled` at `0x180027759`
- `ntdll!EtwEventEnabled` at `0x180027813`
- `ntdll!EtwEventEnabled` at `0x180027af3`
- `ntdll!EtwEventEnabled` at `0x180027c4d`
- `ntdll!EtwEventEnabled` at `0x180027d08`
- `ntdll!EtwEventEnabled` at `0x180027d7f`

## string_xrefs

- `0x180027567`: `Session(%d) IsIdentityRequest received in unexpected state (%d)`

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
        && (byte_18004E841 & 8) != 0 )
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
0x180026e60  mov     [rsp-8+arg_18], rbx
0x180026e65  push    rbp
0x180026e66  push    rsi
0x180026e67  push    rdi
0x180026e68  push    r12
0x180026e6a  push    r13
0x180026e6c  push    r14
0x180026e6e  push    r15
0x180026e70  lea     rbp, [rsp-800h]
0x180026e78  sub     rsp, 900h
0x180026e7f  mov     rax, cs:__security_cookie
0x180026e86  xor     rax, rsp
0x180026e89  mov     [rbp+830h+var_40], rax
0x180026e90  mov     r15, r8
0x180026e93  mov     rdi, rdx
0x180026e96  mov     [rbp+830h+var_898], rcx
0x180026e9a  xor     r14d, r14d
0x180026e9d  mov     dword ptr [rsp+930h+var_8B8], r14d
0x180026ea2  lea     esi, [r14+8]
0x180026ea6  mov     r9, [rdx+130h]
0x180026ead  test    r9, r9
0x180026eb0  jz      loc_18002750D
0x180026eb6  mov     al, [r8+1]
0x180026eba  cmp     [r9+1], al
0x180026ebe  jnz     loc_18002750D
0x180026ec4  mov     bl, [r8]
0x180026ec7  lea     r12d, [r14+1]
0x180026ecb  cmp     bl, r12b
0x180026ece  jnz     loc_18002705C
0x180026ed4  movzx   edx, byte ptr [r9+2]
0x180026ed9  shl     dx, 8
0x180026edd  movzx   r8d, byte ptr [r9+3]
0x180026ee2  movzx   ecx, byte ptr [r15+2]
0x180026ee7  shl     cx, 8
0x180026eeb  movzx   eax, byte ptr [r15+3]
0x180026ef0  or      cx, ax
0x180026ef3  movzx   eax, r8w
0x180026ef7  or      ax, dx
0x180026efa  cmp     ax, cx
0x180026efd  jnz     loc_18002705C
0x180026f03  movzx   eax, dx
0x180026f06  or      r8, rax; Size
0x180026f09  mov     rdx, r15; Buf2
0x180026f0c  mov     rcx, r9; Buf1
0x180026f0f  call    memcmp_0
0x180026f14  test    eax, eax
0x180026f16  jnz     loc_18002705C
0x180026f1c  mov     rcx, r15; this
0x180026f1f  call    ?IsIdentityRequest@Packet@EapHost@@QEBA_NXZ; EapHost::Packet::IsIdentityRequest(void)
0x180026f24  test    al, al
0x180026f26  jz      loc_180026FCC
0x180026f2c  cmp     [rdi+10Ch], r12d
0x180026f33  jnz     loc_180026FCC
0x180026f39  lea     rbx, DebugInfoEvent
0x180026f40  mov     rdx, rbx
0x180026f43  mov     rcx, cs:eaphost_Context
0x180026f4a  call    cs:__imp_EtwEventEnabled
0x180026f50  test    al, al
0x180026f52  jz      short loc_180026F8D
0x180026f54  mov     r9d, [rdi+38h]
0x180026f58  lea     r8, aSessionDDiscar_0; " Session(%d), discard dup identity requ"...
0x180026f5f  mov     edx, 800h; unsigned __int64
0x180026f64  lea     rcx, [rbp+830h+var_840]; char *
0x180026f68  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180026f6d  test    eax, eax
0x180026f6f  js      short loc_180026F8D
0x180026f71  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x180026f78  jz      short loc_180026F8D
0x180026f7a  lea     r8, [rbp+830h+var_840]
0x180026f7e  mov     rdx, rbx
0x180026f81  lea     rcx, eaphost_Context
0x180026f88  call    McTemplateU0s_EtwEventWriteTransfer
0x180026f8d  lea     r14, WPP_GLOBAL_Control
0x180026f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f9b  cmp     rcx, r14
0x180026f9e  jz      loc_180027E1B
0x180026fa4  test    byte ptr [rcx+1Ch], 4
0x180026fa8  jz      loc_180027E1B
0x180026fae  mov     edx, 3Bh ; ';'
0x180026fb3  mov     r9d, [rdi+38h]
0x180026fb7  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180026fbe  mov     rcx, [rcx+10h]
0x180026fc2  call    WPP_SF_d
0x180026fc7  jmp     loc_180027E1B
0x180026fcc  lea     rbx, DebugInfoEvent
0x180026fd3  mov     rdx, rbx
0x180026fd6  mov     rcx, cs:eaphost_Context
0x180026fdd  call    cs:__imp_EtwEventEnabled
0x180026fe3  test    al, al
0x180026fe5  jz      short loc_180027020
0x180026fe7  mov     r9d, [rdi+38h]
0x180026feb  lea     r8, aSessionDRetran; " Session(%d), Retransmit"
0x180026ff2  mov     edx, 800h; unsigned __int64
0x180026ff7  lea     rcx, [rbp+830h+var_840]; char *
0x180026ffb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180027000  test    eax, eax
0x180027002  js      short loc_180027020
0x180027004  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x18002700b  jz      short loc_180027020
0x18002700d  lea     r8, [rbp+830h+var_840]
0x180027011  mov     rdx, rbx
0x180027014  lea     rcx, eaphost_Context
0x18002701b  call    McTemplateU0s_EtwEventWriteTransfer
0x180027020  lea     r14, WPP_GLOBAL_Control
0x180027027  mov     rcx, cs:WPP_GLOBAL_Control
0x18002702e  cmp     rcx, r14
0x180027031  jz      short loc_180027052
0x180027033  test    byte ptr [rcx+1Ch], 4
0x180027037  jz      short loc_180027052
0x180027039  mov     edx, 3Ch ; '<'
0x18002703e  mov     r9d, [rdi+38h]
0x180027042  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180027049  mov     rcx, [rcx+10h]
0x18002704d  call    WPP_SF_d
0x180027052  mov     esi, 3
0x180027057  jmp     loc_180027E1B
0x18002705c  cmp     dword ptr [rdi+10Ch], 3
0x180027063  jnz     loc_180027106
0x180027069  cmp     byte ptr [rdi+84h], 11h
0x180027070  jnz     loc_180027106
0x180027076  lea     rbx, DebugInfoEvent
0x18002707d  mov     rdx, rbx
0x180027080  mov     rcx, cs:eaphost_Context
0x180027087  call    cs:__imp_EtwEventEnabled
0x18002708d  test    al, al
0x18002708f  jz      short loc_1800270CA
0x180027091  mov     r9d, [rdi+38h]
0x180027095  lea     r8, aSessionDLeapCo; " Session(%d), Leap, continueMethod"
0x18002709c  mov     edx, 800h; unsigned __int64
0x1800270a1  lea     rcx, [rbp+830h+var_840]; char *
0x1800270a5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800270aa  test    eax, eax
0x1800270ac  js      short loc_1800270CA
0x1800270ae  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x1800270b5  jz      short loc_1800270CA
0x1800270b7  lea     r8, [rbp+830h+var_840]
0x1800270bb  mov     rdx, rbx
0x1800270be  lea     rcx, eaphost_Context
0x1800270c5  call    McTemplateU0s_EtwEventWriteTransfer
0x1800270ca  lea     r14, WPP_GLOBAL_Control
0x1800270d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270d8  cmp     rcx, r14
0x1800270db  jz      short loc_1800270FC
0x1800270dd  test    byte ptr [rcx+1Ch], 4
0x1800270e1  jz      short loc_1800270FC
0x1800270e3  mov     edx, 3Dh ; '='
0x1800270e8  mov     r9d, [rdi+38h]
0x1800270ec  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800270f3  mov     rcx, [rcx+10h]
0x1800270f7  call    WPP_SF_d
0x1800270fc  mov     esi, 6
0x180027101  jmp     loc_180027E1B
0x180027106  sub     bl, 3
0x180027109  cmp     bl, r12b
0x18002710c  ja      loc_1800271C6
0x180027112  lea     rbx, DebugInfoEvent
0x180027119  mov     rdx, rbx
0x18002711c  mov     rcx, cs:eaphost_Context
0x180027123  call    cs:__imp_EtwEventEnabled
0x180027129  lea     r13, aSuccess; "success"
0x180027130  lea     rsi, aFailure; "failure"
0x180027137  test    al, al
0x180027139  jz      short loc_180027184
0x18002713b  mov     rax, r13
0x18002713e  cmp     byte ptr [r15], 3
0x180027142  cmovnz  rax, rsi
0x180027146  mov     [rsp+930h+var_910], rax
0x18002714b  mov     r9d, [rdi+38h]
0x18002714f  lea     r8, aSessionDS; " Session(%d), %s."
0x180027156  mov     edx, 800h; unsigned __int64
0x18002715b  lea     rcx, [rbp+830h+var_840]; char *
0x18002715f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180027164  test    eax, eax
0x180027166  js      short loc_180027184
0x180027168  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x18002716f  jz      short loc_180027184
0x180027171  lea     r8, [rbp+830h+var_840]
0x180027175  mov     rdx, rbx
0x180027178  lea     rcx, eaphost_Context
0x18002717f  call    McTemplateU0s_EtwEventWriteTransfer
0x180027184  lea     r14, WPP_GLOBAL_Control
0x18002718b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027192  cmp     rcx, r14
0x180027195  jz      short loc_1800271BC
0x180027197  test    byte ptr [rcx+1Ch], 4
0x18002719b  jz      short loc_1800271BC
0x18002719d  cmp     byte ptr [r15], 3
0x1800271a1  cmovnz  r13, rsi
0x1800271a5  mov     edx, 3Eh ; '>'
0x1800271aa  mov     [rsp+930h+var_910], r13
0x1800271af  mov     r9d, [rdi+38h]
0x1800271b3  mov     rcx, [rcx+10h]
0x1800271b7  call    WPP_SF_ds
0x1800271bc  mov     esi, 7
0x1800271c1  jmp     loc_180027E1B
0x1800271c6  mov     rcx, r15; this
0x1800271c9  call    ?IsTypeRequest@Packet@EapHost@@QEBA_NXZ; EapHost::Packet::IsTypeRequest(void)
0x1800271ce  test    al, al
0x1800271d0  jz      short loc_18002721B
0x1800271d2  lea     rdx, [rsp+930h+var_8C0]
0x1800271d7  mov     rcx, [rdi+130h]
0x1800271de  call    ?GetType@Packet@EapHost@@QEBA?AV?$unique_ptr@VEapType@EapHost@@U?$default_delete@VEapType@EapHost@@@std@@@std@@XZ; EapHost::Packet::GetType(void)
0x1800271e3  nop
0x1800271e4  mov     dword ptr [rsp+930h+var_8B8], r12d
0x1800271e9  mov     rbx, [rax]
0x1800271ec  lea     rdx, [rbp+830h+var_8B0]
0x1800271f0  mov     rcx, r15
0x1800271f3  call    ?GetType@Packet@EapHost@@QEBA?AV?$unique_ptr@VEapType@EapHost@@U?$default_delete@VEapType@EapHost@@@std@@@std@@XZ; EapHost::Packet::GetType(void)
0x1800271f8  mov     r14d, 3
0x1800271fe  mov     rdx, rbx
0x180027201  mov     rcx, [rax]
0x180027204  call    ??8@YA_NAEBVEapType@EapHost@@0@Z; operator==(EapHost::EapType const &,EapHost::EapType const &)
0x180027209  test    al, al
0x18002720b  jnz     short loc_18002721B
0x18002720d  cmp     dword ptr [rdi+10Ch], 2
0x180027214  jnz     short loc_18002721B
0x180027216  mov     bl, r12b
0x180027219  jmp     short loc_18002721D
0x18002721b  xor     bl, bl
0x18002721d  test    r14b, 2
0x180027221  jz      short loc_180027231
0x180027223  and     r14d, 0FFFFFFFDh
0x180027227  lea     rcx, [rbp+830h+var_8B0]
0x18002722b  call    ??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(void)
0x180027230  nop
0x180027231  test    r12b, r14b
0x180027234  jz      short loc_180027240
0x180027236  lea     rcx, [rsp+930h+var_8C0]
0x18002723b  call    ??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(void)
0x180027240  test    bl, bl
0x180027242  jz      loc_180027465
0x180027248  lea     rdx, [rdi+84h]; struct _EAP_TYPE *
0x18002724f  lea     rcx, [rsp+930h+var_8D8]; this
0x180027254  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x180027259  nop
0x18002725a  lea     rdx, [rsp+930h+var_8C0]
0x18002725f  mov     rcx, r15
0x180027262  call    ?GetType@Packet@EapHost@@QEBA?AV?$unique_ptr@VEapType@EapHost@@U?$default_delete@VEapType@EapHost@@@std@@@std@@XZ; EapHost::Packet::GetType(void)
0x180027267  nop
0x180027268  lea     rbx, DebugInfoEvent
0x18002726f  mov     rdx, rbx
0x180027272  mov     rcx, cs:eaphost_Context
0x180027279  call    cs:__imp_EtwEventEnabled
0x18002727f  test    al, al
0x180027281  jz      short loc_1800272C5
0x180027283  movzx   eax, byte ptr [r15+1]
0x180027288  mov     dword ptr [rsp+930h+var_910], eax
0x18002728c  mov     r9d, [rdi+38h]
0x180027290  lea     r8, aSessionDContin; " Session(%d), Continue Method, 1st auth"...
0x180027297  mov     edx, 800h; unsigned __int64
0x18002729c  lea     rcx, [rbp+830h+var_840]; char *
0x1800272a0  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800272a5  test    eax, eax
0x1800272a7  js      short loc_1800272C5
0x1800272a9  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x1800272b0  jz      short loc_1800272C5
0x1800272b2  lea     r8, [rbp+830h+var_840]
0x1800272b6  mov     rdx, rbx
0x1800272b9  lea     rcx, eaphost_Context
0x1800272c0  call    McTemplateU0s_EtwEventWriteTransfer
0x1800272c5  lea     r14, WPP_GLOBAL_Control
0x1800272cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272d3  cmp     rcx, r14
0x1800272d6  jz      short loc_180027300
0x1800272d8  test    byte ptr [rcx+1Ch], 4
0x1800272dc  jz      short loc_180027300
0x1800272de  movzx   eax, byte ptr [r15+1]
0x1800272e3  mov     edx, 3Fh ; '?'
0x1800272e8  mov     dword ptr [rsp+930h+var_910], eax
0x1800272ec  mov     r9d, [rdi+38h]
0x1800272f0  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800272f7  mov     rcx, [rcx+10h]
0x1800272fb  call    WPP_SF_dd
0x180027300  mov     rsi, [rsp+930h+var_8C0]
0x180027305  mov     rdx, rsi
0x180027308  lea     rcx, [rsp+930h+var_8D8]
0x18002730d  call    ??8@YA_NAEBVEapType@EapHost@@0@Z; operator==(EapHost::EapType const &,EapHost::EapType const &)
0x180027312  test    al, al
0x180027314  jnz     loc_180027450
0x18002731a  lea     rcx, [rsp+930h+var_8D8]; this
0x18002731f  call    ?IsCompatibleExpandedTypeOf@EapType@EapHost@@QEAA_NAEBV12@@Z; EapHost::EapType::IsCompatibleExpandedTypeOf(EapHost::EapType const &)
0x180027324  test    al, al
0x180027326  jnz     loc_180027450
0x18002732c  mov     rdx, rbx
0x18002732f  mov     rcx, cs:eaphost_Context
0x180027336  call    cs:__imp_EtwEventEnabled
0x18002733c  mov     r13b, 0FEh
0x18002733f  mov     r12d, dword ptr [rsp+930h+var_8CC+4]
0x180027344  mov     r8d, dword ptr [rsp+930h+var_8CC]
0x180027349  movzx   r15d, [rsp+930h+var_8D0]
0x18002734f  test    al, al
0x180027351  jz      loc_1800273DA
0x180027357  mov     r10d, [rdi+10Ch]
0x18002735e  cmp     r15b, r13b
0x180027361  jnz     short loc_180027368
0x180027363  mov     ecx, r12d
0x180027366  jmp     short loc_18002736D
0x180027368  xor     ecx, ecx
0x18002736a  xor     r8d, r8d
0x18002736d  movzx   edx, byte ptr [rsi+8]
  ... truncated ...
```

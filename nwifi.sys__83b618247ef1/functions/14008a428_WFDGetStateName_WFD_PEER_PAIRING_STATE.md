# WFDGetStateName(WFD_PEER_PAIRING_STATE)

- ea: `0x14008a428`
- end: `0x14008a5cd`
- name: `?WFDGetStateName@@YAPEADW4WFD_PEER_PAIRING_STATE@@@Z`
- size: `421`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14008a970`
- `0x14008ab4c`
- `0x14008acd8`

## callees

- `0x14008a428`

## string_xrefs

- `0x14008a49a`: `WFD_PEER_STATE_InviteWaitForOIDRequestComplete`
- `0x14008a491`: `WFD_PEER_STATE_InviteWaitForRequestSendComplete`
- `0x14008a488`: `WFD_PEER_STATE_InviteRequestSendComplete`
- `0x14008a4fb`: `WFD_PEER_STATE_ProvDiscWaitForOIDRequestComplete`
- `0x14008a4f2`: `WFD_PEER_STATE_ProvDiscWaitForRequestSendComplete`
- `0x14008a4e9`: `WFD_PEER_STATE_ProvDiscRequestSendComplete`
- `0x14008a4ce`: `WFD_PEER_STATE_GONRequestWaitForOIDRequestComplete`
- `0x14008a504`: `WFD_PEER_STATE_GONRequestWaitForRequestSendComplete`
- `0x14008a55f`: `WFD_PEER_STATE_GONRequestSendComplete`
- `0x14008a556`: `WFD_PEER_STATE_GONWaitForIncomingResponse`
- `0x14008a54d`: `WFD_PEER_STATE_GONIncomingResponseReceived`
- `0x14008a544`: `WFD_PEER_STATE_GONWaitForIncomingRequest`
- `0x14008a53b`: `WFD_PEER_STATE_GONIncomingRequestReceived`
- `0x14008a532`: `WFD_PEER_STATE_GONResponseWaitForOIDRequestComplete`
- `0x14008a568`: `WFD_PEER_STATE_GONResponseWaitForRequestSendComplete`
- `0x14008a5c5`: `WFD_PEER_STATE_GONResponseSendComplete`
- `0x14008a5bc`: `WFD_PEER_STATE_GONWaitForIncomingConfirm`
- `0x14008a5b3`: `WFD_PEER_STATE_GONIncomingConfirmReceived`
- `0x14008a5aa`: `WFD_PEER_STATE_GONConfirmWaitForOIDRequestComplete`
- `0x14008a5a1`: `WFD_PEER_STATE_GONConfirmWaitForRequestSendComplete`
- `0x14008a598`: `WFD_PEER_STATE_GONConfirmSendComplete`

## pseudocode

```c
const char *__fastcall WFDGetStateName(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx

  if ( a1 <= 18 )
  {
    if ( a1 == 18 )
      return "WFD_PEER_STATE_GONRequestWaitForRequestSendComplete";
    if ( a1 > 7 )
    {
      v7 = a1 - 9;
      if ( !v7 )
        return "WFD_PEER_STATE_ProvDiscWaitForOIDRequestComplete";
      v8 = v7 - 1;
      if ( !v8 )
        return "WFD_PEER_STATE_ProvDiscWaitForRequestSendComplete";
      v9 = v8 - 1;
      if ( !v9 )
        return "WFD_PEER_STATE_ProvDiscRequestSendComplete";
      v10 = v9 - 1;
      if ( !v10 )
        return "WFD_PEER_STATE_ProvDiscWaitForResponse";
      v11 = v10 - 1;
      if ( !v11 )
        return "WFD_PEER_STATE_ProvDiscResponseReceived";
      if ( v11 == 4 )
        return "WFD_PEER_STATE_GONRequestWaitForOIDRequestComplete";
    }
    else
    {
      if ( a1 == 7 )
        return "WFD_PEER_STATE_InviteReinviteRequestReceived";
      if ( !a1 )
        return "WFD_PEER_STATE_InviteWaitForOIDRequestComplete";
      v1 = a1 - 1;
      if ( !v1 )
        return "WFD_PEER_STATE_InviteWaitForRequestSendComplete";
      v2 = v1 - 1;
      if ( !v2 )
        return "WFD_PEER_STATE_InviteRequestSendComplete";
      v3 = v2 - 1;
      if ( !v3 )
        return "WFD_PEER_STATE_InviteWaitForResponse";
      v4 = v3 - 1;
      if ( !v4 )
        return "WFD_PEER_STATE_InviteReinviteRequestCrossed";
      v5 = v4 - 1;
      if ( !v5 )
        return "WFD_PEER_STATE_InviteResponseReceived";
      if ( v5 == 1 )
        return "WFD_PEER_STATE_InviteWaitForReinviteRequest";
    }
    return "UNKNOWN_STATE";
  }
  if ( a1 <= 25 )
  {
    if ( a1 == 25 )
      return "WFD_PEER_STATE_GONResponseWaitForRequestSendComplete";
    v12 = a1 - 19;
    if ( !v12 )
      return "WFD_PEER_STATE_GONRequestSendComplete";
    v13 = v12 - 1;
    if ( !v13 )
      return "WFD_PEER_STATE_GONWaitForIncomingResponse";
    v14 = v13 - 1;
    if ( !v14 )
      return "WFD_PEER_STATE_GONIncomingResponseReceived";
    v15 = v14 - 1;
    if ( !v15 )
      return "WFD_PEER_STATE_GONWaitForIncomingRequest";
    v16 = v15 - 1;
    if ( !v16 )
      return "WFD_PEER_STATE_GONIncomingRequestReceived";
    if ( v16 == 1 )
      return "WFD_PEER_STATE_GONResponseWaitForOIDRequestComplete";
    return "UNKNOWN_STATE";
  }
  v17 = a1 - 26;
  if ( !v17 )
    return "WFD_PEER_STATE_GONResponseSendComplete";
  v18 = v17 - 1;
  if ( !v18 )
    return "WFD_PEER_STATE_GONWaitForIncomingConfirm";
  v19 = v18 - 1;
  if ( !v19 )
    return "WFD_PEER_STATE_GONIncomingConfirmReceived";
  v20 = v19 - 1;
  if ( !v20 )
    return "WFD_PEER_STATE_GONConfirmWaitForOIDRequestComplete";
  v21 = v20 - 1;
  if ( !v21 )
    return "WFD_PEER_STATE_GONConfirmWaitForRequestSendComplete";
  if ( v21 != 1 )
    return "UNKNOWN_STATE";
  return "WFD_PEER_STATE_GONConfirmSendComplete";
}

```

## disassembly

```asm
0x14008a428  cmp     ecx, 12h
0x14008a42b  jg      loc_14008A50D
0x14008a431  jz      loc_14008A504
0x14008a437  cmp     ecx, 7
0x14008a43a  jg      short loc_14008A4AC
0x14008a43c  jz      short loc_14008A4A3
0x14008a43e  test    ecx, ecx
0x14008a440  jz      short loc_14008A49A
0x14008a442  sub     ecx, 1
0x14008a445  jz      short loc_14008A491
0x14008a447  sub     ecx, 1
0x14008a44a  jz      short loc_14008A488
0x14008a44c  sub     ecx, 1
0x14008a44f  jz      short loc_14008A47F
0x14008a451  sub     ecx, 1
0x14008a454  jz      short loc_14008A476
0x14008a456  sub     ecx, 1
0x14008a459  jz      short loc_14008A46D
0x14008a45b  cmp     ecx, 1
0x14008a45e  jnz     loc_14008A58F
0x14008a464  lea     rax, aWfdPeerStateIn_1; "WFD_PEER_STATE_InviteWaitForReinviteReq"...
0x14008a46b  retn
0x14008a46d  lea     rax, aWfdPeerStateIn_3; "WFD_PEER_STATE_InviteResponseReceived"
0x14008a474  retn
0x14008a476  lea     rax, aWfdPeerStateIn_4; "WFD_PEER_STATE_InviteReinviteRequestCro"...
0x14008a47d  retn
0x14008a47f  lea     rax, aWfdPeerStateIn_5; "WFD_PEER_STATE_InviteWaitForResponse"
0x14008a486  retn
0x14008a488  lea     rax, aWfdPeerStateIn; "WFD_PEER_STATE_InviteRequestSendComplet"...
0x14008a48f  retn
0x14008a491  lea     rax, aWfdPeerStateIn_2; "WFD_PEER_STATE_InviteWaitForRequestSend"...
0x14008a498  retn
0x14008a49a  lea     rax, aWfdPeerStateIn_6; "WFD_PEER_STATE_InviteWaitForOIDRequestC"...
0x14008a4a1  retn
0x14008a4a3  lea     rax, aWfdPeerStateIn_0; "WFD_PEER_STATE_InviteReinviteRequestRec"...
0x14008a4aa  retn
0x14008a4ac  sub     ecx, 9
0x14008a4af  jz      short loc_14008A4FB
0x14008a4b1  sub     ecx, 1
0x14008a4b4  jz      short loc_14008A4F2
0x14008a4b6  sub     ecx, 1
0x14008a4b9  jz      short loc_14008A4E9
0x14008a4bb  sub     ecx, 1
0x14008a4be  jz      short loc_14008A4E0
0x14008a4c0  sub     ecx, 1
0x14008a4c3  jz      short loc_14008A4D7
0x14008a4c5  cmp     ecx, 4
0x14008a4c8  jnz     loc_14008A58F
0x14008a4ce  lea     rax, aWfdPeerStateGo; "WFD_PEER_STATE_GONRequestWaitForOIDRequ"...
0x14008a4d5  retn
0x14008a4d7  lea     rax, aWfdPeerStatePr_2; "WFD_PEER_STATE_ProvDiscResponseReceived"
0x14008a4de  retn
0x14008a4e0  lea     rax, aWfdPeerStatePr_3; "WFD_PEER_STATE_ProvDiscWaitForResponse"
0x14008a4e7  retn
0x14008a4e9  lea     rax, aWfdPeerStatePr_1; "WFD_PEER_STATE_ProvDiscRequestSendCompl"...
0x14008a4f0  retn
0x14008a4f2  lea     rax, aWfdPeerStatePr; "WFD_PEER_STATE_ProvDiscWaitForRequestSe"...
0x14008a4f9  retn
0x14008a4fb  lea     rax, aWfdPeerStatePr_0; "WFD_PEER_STATE_ProvDiscWaitForOIDReques"...
0x14008a502  retn
0x14008a504  lea     rax, aWfdPeerStateGo_10; "WFD_PEER_STATE_GONRequestWaitForRequest"...
0x14008a50b  retn
0x14008a50d  cmp     ecx, 19h
0x14008a510  jg      short loc_14008A571
0x14008a512  jz      short loc_14008A568
0x14008a514  sub     ecx, 13h
0x14008a517  jz      short loc_14008A55F
0x14008a519  sub     ecx, 1
0x14008a51c  jz      short loc_14008A556
0x14008a51e  sub     ecx, 1
0x14008a521  jz      short loc_14008A54D
0x14008a523  sub     ecx, 1
0x14008a526  jz      short loc_14008A544
0x14008a528  sub     ecx, 1
0x14008a52b  jz      short loc_14008A53B
0x14008a52d  cmp     ecx, 1
0x14008a530  jnz     short loc_14008A58F
0x14008a532  lea     rax, aWfdPeerStateGo_9; "WFD_PEER_STATE_GONResponseWaitForOIDReq"...
0x14008a539  retn
0x14008a53b  lea     rax, aWfdPeerStateGo_0; "WFD_PEER_STATE_GONIncomingRequestReceiv"...
0x14008a542  retn
0x14008a544  lea     rax, aWfdPeerStateGo_11; "WFD_PEER_STATE_GONWaitForIncomingReques"...
0x14008a54b  retn
0x14008a54d  lea     rax, aWfdPeerStateGo_6; "WFD_PEER_STATE_GONIncomingResponseRecei"...
0x14008a554  retn
0x14008a556  lea     rax, aWfdPeerStateGo_5; "WFD_PEER_STATE_GONWaitForIncomingRespon"...
0x14008a55d  retn
0x14008a55f  lea     rax, aWfdPeerStateGo_4; "WFD_PEER_STATE_GONRequestSendComplete"
0x14008a566  retn
0x14008a568  lea     rax, aWfdPeerStateGo_2; "WFD_PEER_STATE_GONResponseWaitForReques"...
0x14008a56f  retn
0x14008a571  sub     ecx, 1Ah
0x14008a574  jz      short loc_14008A5C5
0x14008a576  sub     ecx, 1
0x14008a579  jz      short loc_14008A5BC
0x14008a57b  sub     ecx, 1
0x14008a57e  jz      short loc_14008A5B3
0x14008a580  sub     ecx, 1
0x14008a583  jz      short loc_14008A5AA
0x14008a585  sub     ecx, 1
0x14008a588  jz      short loc_14008A5A1
0x14008a58a  cmp     ecx, 1
0x14008a58d  jz      short loc_14008A598
0x14008a58f  lea     rax, aUnknownState; "UNKNOWN_STATE"
0x14008a596  retn
0x14008a598  lea     rax, aWfdPeerStateGo_13; "WFD_PEER_STATE_GONConfirmSendComplete"
0x14008a59f  retn
0x14008a5a1  lea     rax, aWfdPeerStateGo_1; "WFD_PEER_STATE_GONConfirmWaitForRequest"...
0x14008a5a8  retn
0x14008a5aa  lea     rax, aWfdPeerStateGo_3; "WFD_PEER_STATE_GONConfirmWaitForOIDRequ"...
0x14008a5b1  retn
0x14008a5b3  lea     rax, aWfdPeerStateGo_12; "WFD_PEER_STATE_GONIncomingConfirmReceiv"...
0x14008a5ba  retn
0x14008a5bc  lea     rax, aWfdPeerStateGo_7; "WFD_PEER_STATE_GONWaitForIncomingConfir"...
0x14008a5c3  retn
0x14008a5c5  lea     rax, aWfdPeerStateGo_8; "WFD_PEER_STATE_GONResponseSendComplete"
0x14008a5cc  retn
```

# WFDGetStateName(WFD_PEER_PAIRING_STATE)

- ea: `0x14008bc58`
- end: `0x14008bdfd`
- name: `?WFDGetStateName@@YAPEADW4WFD_PEER_PAIRING_STATE@@@Z`
- size: `421`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14008c1a0`
- `0x14008c37c`
- `0x14008c508`

## callees

- `0x14008bc58`

## string_xrefs

- `0x14008bcca`: `WFD_PEER_STATE_InviteWaitForOIDRequestComplete`
- `0x14008bcc1`: `WFD_PEER_STATE_InviteWaitForRequestSendComplete`
- `0x14008bcb8`: `WFD_PEER_STATE_InviteRequestSendComplete`
- `0x14008bd2b`: `WFD_PEER_STATE_ProvDiscWaitForOIDRequestComplete`
- `0x14008bd22`: `WFD_PEER_STATE_ProvDiscWaitForRequestSendComplete`
- `0x14008bd19`: `WFD_PEER_STATE_ProvDiscRequestSendComplete`
- `0x14008bcfe`: `WFD_PEER_STATE_GONRequestWaitForOIDRequestComplete`
- `0x14008bd34`: `WFD_PEER_STATE_GONRequestWaitForRequestSendComplete`
- `0x14008bd8f`: `WFD_PEER_STATE_GONRequestSendComplete`
- `0x14008bd86`: `WFD_PEER_STATE_GONWaitForIncomingResponse`
- `0x14008bd7d`: `WFD_PEER_STATE_GONIncomingResponseReceived`
- `0x14008bd74`: `WFD_PEER_STATE_GONWaitForIncomingRequest`
- `0x14008bd6b`: `WFD_PEER_STATE_GONIncomingRequestReceived`
- `0x14008bd62`: `WFD_PEER_STATE_GONResponseWaitForOIDRequestComplete`
- `0x14008bd98`: `WFD_PEER_STATE_GONResponseWaitForRequestSendComplete`
- `0x14008bdf5`: `WFD_PEER_STATE_GONResponseSendComplete`
- `0x14008bdec`: `WFD_PEER_STATE_GONWaitForIncomingConfirm`
- `0x14008bde3`: `WFD_PEER_STATE_GONIncomingConfirmReceived`
- `0x14008bdda`: `WFD_PEER_STATE_GONConfirmWaitForOIDRequestComplete`
- `0x14008bdd1`: `WFD_PEER_STATE_GONConfirmWaitForRequestSendComplete`
- `0x14008bdc8`: `WFD_PEER_STATE_GONConfirmSendComplete`

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
0x14008bc58  cmp     ecx, 12h
0x14008bc5b  jg      loc_14008BD3D
0x14008bc61  jz      loc_14008BD34
0x14008bc67  cmp     ecx, 7
0x14008bc6a  jg      short loc_14008BCDC
0x14008bc6c  jz      short loc_14008BCD3
0x14008bc6e  test    ecx, ecx
0x14008bc70  jz      short loc_14008BCCA
0x14008bc72  sub     ecx, 1
0x14008bc75  jz      short loc_14008BCC1
0x14008bc77  sub     ecx, 1
0x14008bc7a  jz      short loc_14008BCB8
0x14008bc7c  sub     ecx, 1
0x14008bc7f  jz      short loc_14008BCAF
0x14008bc81  sub     ecx, 1
0x14008bc84  jz      short loc_14008BCA6
0x14008bc86  sub     ecx, 1
0x14008bc89  jz      short loc_14008BC9D
0x14008bc8b  cmp     ecx, 1
0x14008bc8e  jnz     loc_14008BDBF
0x14008bc94  lea     rax, aWfdPeerStateIn_1; "WFD_PEER_STATE_InviteWaitForReinviteReq"...
0x14008bc9b  retn
0x14008bc9d  lea     rax, aWfdPeerStateIn_3; "WFD_PEER_STATE_InviteResponseReceived"
0x14008bca4  retn
0x14008bca6  lea     rax, aWfdPeerStateIn_4; "WFD_PEER_STATE_InviteReinviteRequestCro"...
0x14008bcad  retn
0x14008bcaf  lea     rax, aWfdPeerStateIn_5; "WFD_PEER_STATE_InviteWaitForResponse"
0x14008bcb6  retn
0x14008bcb8  lea     rax, aWfdPeerStateIn; "WFD_PEER_STATE_InviteRequestSendComplet"...
0x14008bcbf  retn
0x14008bcc1  lea     rax, aWfdPeerStateIn_2; "WFD_PEER_STATE_InviteWaitForRequestSend"...
0x14008bcc8  retn
0x14008bcca  lea     rax, aWfdPeerStateIn_6; "WFD_PEER_STATE_InviteWaitForOIDRequestC"...
0x14008bcd1  retn
0x14008bcd3  lea     rax, aWfdPeerStateIn_0; "WFD_PEER_STATE_InviteReinviteRequestRec"...
0x14008bcda  retn
0x14008bcdc  sub     ecx, 9
0x14008bcdf  jz      short loc_14008BD2B
0x14008bce1  sub     ecx, 1
0x14008bce4  jz      short loc_14008BD22
0x14008bce6  sub     ecx, 1
0x14008bce9  jz      short loc_14008BD19
0x14008bceb  sub     ecx, 1
0x14008bcee  jz      short loc_14008BD10
0x14008bcf0  sub     ecx, 1
0x14008bcf3  jz      short loc_14008BD07
0x14008bcf5  cmp     ecx, 4
0x14008bcf8  jnz     loc_14008BDBF
0x14008bcfe  lea     rax, aWfdPeerStateGo; "WFD_PEER_STATE_GONRequestWaitForOIDRequ"...
0x14008bd05  retn
0x14008bd07  lea     rax, aWfdPeerStatePr_2; "WFD_PEER_STATE_ProvDiscResponseReceived"
0x14008bd0e  retn
0x14008bd10  lea     rax, aWfdPeerStatePr_3; "WFD_PEER_STATE_ProvDiscWaitForResponse"
0x14008bd17  retn
0x14008bd19  lea     rax, aWfdPeerStatePr_1; "WFD_PEER_STATE_ProvDiscRequestSendCompl"...
0x14008bd20  retn
0x14008bd22  lea     rax, aWfdPeerStatePr; "WFD_PEER_STATE_ProvDiscWaitForRequestSe"...
0x14008bd29  retn
0x14008bd2b  lea     rax, aWfdPeerStatePr_0; "WFD_PEER_STATE_ProvDiscWaitForOIDReques"...
0x14008bd32  retn
0x14008bd34  lea     rax, aWfdPeerStateGo_10; "WFD_PEER_STATE_GONRequestWaitForRequest"...
0x14008bd3b  retn
0x14008bd3d  cmp     ecx, 19h
0x14008bd40  jg      short loc_14008BDA1
0x14008bd42  jz      short loc_14008BD98
0x14008bd44  sub     ecx, 13h
0x14008bd47  jz      short loc_14008BD8F
0x14008bd49  sub     ecx, 1
0x14008bd4c  jz      short loc_14008BD86
0x14008bd4e  sub     ecx, 1
0x14008bd51  jz      short loc_14008BD7D
0x14008bd53  sub     ecx, 1
0x14008bd56  jz      short loc_14008BD74
0x14008bd58  sub     ecx, 1
0x14008bd5b  jz      short loc_14008BD6B
0x14008bd5d  cmp     ecx, 1
0x14008bd60  jnz     short loc_14008BDBF
0x14008bd62  lea     rax, aWfdPeerStateGo_9; "WFD_PEER_STATE_GONResponseWaitForOIDReq"...
0x14008bd69  retn
0x14008bd6b  lea     rax, aWfdPeerStateGo_0; "WFD_PEER_STATE_GONIncomingRequestReceiv"...
0x14008bd72  retn
0x14008bd74  lea     rax, aWfdPeerStateGo_11; "WFD_PEER_STATE_GONWaitForIncomingReques"...
0x14008bd7b  retn
0x14008bd7d  lea     rax, aWfdPeerStateGo_6; "WFD_PEER_STATE_GONIncomingResponseRecei"...
0x14008bd84  retn
0x14008bd86  lea     rax, aWfdPeerStateGo_5; "WFD_PEER_STATE_GONWaitForIncomingRespon"...
0x14008bd8d  retn
0x14008bd8f  lea     rax, aWfdPeerStateGo_4; "WFD_PEER_STATE_GONRequestSendComplete"
0x14008bd96  retn
0x14008bd98  lea     rax, aWfdPeerStateGo_2; "WFD_PEER_STATE_GONResponseWaitForReques"...
0x14008bd9f  retn
0x14008bda1  sub     ecx, 1Ah
0x14008bda4  jz      short loc_14008BDF5
0x14008bda6  sub     ecx, 1
0x14008bda9  jz      short loc_14008BDEC
0x14008bdab  sub     ecx, 1
0x14008bdae  jz      short loc_14008BDE3
0x14008bdb0  sub     ecx, 1
0x14008bdb3  jz      short loc_14008BDDA
0x14008bdb5  sub     ecx, 1
0x14008bdb8  jz      short loc_14008BDD1
0x14008bdba  cmp     ecx, 1
0x14008bdbd  jz      short loc_14008BDC8
0x14008bdbf  lea     rax, aUnknownState; "UNKNOWN_STATE"
0x14008bdc6  retn
0x14008bdc8  lea     rax, aWfdPeerStateGo_13; "WFD_PEER_STATE_GONConfirmSendComplete"
0x14008bdcf  retn
0x14008bdd1  lea     rax, aWfdPeerStateGo_1; "WFD_PEER_STATE_GONConfirmWaitForRequest"...
0x14008bdd8  retn
0x14008bdda  lea     rax, aWfdPeerStateGo_3; "WFD_PEER_STATE_GONConfirmWaitForOIDRequ"...
0x14008bde1  retn
0x14008bde3  lea     rax, aWfdPeerStateGo_12; "WFD_PEER_STATE_GONIncomingConfirmReceiv"...
0x14008bdea  retn
0x14008bdec  lea     rax, aWfdPeerStateGo_7; "WFD_PEER_STATE_GONWaitForIncomingConfir"...
0x14008bdf3  retn
0x14008bdf5  lea     rax, aWfdPeerStateGo_8; "WFD_PEER_STATE_GONResponseSendComplete"
0x14008bdfc  retn
```

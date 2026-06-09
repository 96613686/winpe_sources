# EapHost::Peer::Host::Send(EapHost::Peer::PeerSession &)

- ea: `0x18002a2fc`
- end: `0x18002a7e9`
- name: `?Send@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z`
- size: `1261`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a7f0`

## callees

- `0x180002af0`
- `0x1800039e8`
- `0x180004b4c`
- `0x180005000`
- `0x18000a24c`
- `0x18000a4d4`
- `0x180011cb8`
- `0x1800120c4`
- `0x18001dc08`
- `0x18001dd20`
- `0x1800277a8`
- `0x180027a98`
- `0x180028c1c`
- `0x18002a2fc`
- `0x18002a8fc`
- `0x18002aa10`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18002a397`
- `ntdll!EtwEventEnabled` at `0x18002a45d`
- `ntdll!EtwEventEnabled` at `0x18002a501`
- `ntdll!EtwEventEnabled` at `0x18002a639`
- `ntdll!EtwEventEnabled` at `0x18002a6cc`
- `ntdll!EtwEventEnabled` at `0x18002a397`
- `ntdll!EtwEventEnabled` at `0x18002a45d`
- `ntdll!EtwEventEnabled` at `0x18002a501`
- `ntdll!EtwEventEnabled` at `0x18002a639`
- `ntdll!EtwEventEnabled` at `0x18002a6cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall EapHost::Peer::Host::Send(__int64 a1, _QWORD *a2, __int64 a3)
{
  int v5; // r8d
  EapHost::Peer::Host *v6; // rcx
  HKEY v7; // rax
  EapHost::Peer::Host *v8; // rcx
  EapHost::Peer::Host *v9; // rcx
  __int64 v10; // rax
  int *v11; // rdx
  EapHost::Peer::Host *v12; // rcx
  int *v13; // rdx
  EapHost::Peer::Host *v14; // rcx
  int v16[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v17; // [rsp+40h] [rbp-C0h]
  _BYTE v18[24]; // [rsp+48h] [rbp-B8h] BYREF
  char v19[2048]; // [rsp+60h] [rbp-A0h] BYREF

  v17 = a2;
  *a2 = 0;
  v16[2] = 1;
  v5 = *(_DWORD *)(a3 + 264);
  switch ( v5 )
  {
    case 0:
      break;
    case 1:
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v19, 0x800u, " Session(%d), Nak", *(_DWORD *)(a3 + 56)) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v19);
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a3 + 56));
      }
      v13 = (int *)EapHost::Peer::Host::Nak(v14, v16, a3);
      goto LABEL_54;
    case 2:
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a3 + 56));
      }
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v19, 0x800u, " Session(%d), ExpandedNak", *(_DWORD *)(a3 + 56)) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v19);
      }
      EapHost::EapType::EapType((EapHost::EapType *)v18, (const struct _EAP_TYPE *)(a3 + 132));
      EapHost::Packet::CreateExpandedNakResponse((int)v16);
      v13 = v16;
LABEL_54:
      std::unique_ptr<EapHost::Packet>::operator=<std::default_delete<EapHost::Packet>,0>(a2, v13);
      std::unique_ptr<EapHost::Packet>::~unique_ptr<EapHost::Packet>(v16);
      *(_DWORD *)(a3 + 260) = 0;
      *(_BYTE *)(a3 + 278) = 1;
      goto LABEL_58;
    case 3:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a3 + 56));
      }
      v10 = EapHost::Peer::Host::SendFromMethod(v12, v16, a3);
      goto LABEL_24;
    case 4:
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v19, 0x800u, " Session(%d), RetransmitResponse", *(_DWORD *)(a3 + 56)) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v19);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a3 + 56));
      }
      EapHost::Packet::Clone(*(void **)(a3 + 296));
      v11 = v16;
      goto LABEL_33;
    case 5:
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v19, 0x800u, " Session(%d), NotificationResponse", *(_DWORD *)(a3 + 56)) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v19);
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a3 + 56));
      }
      v10 = EapHost::Peer::Host::NotificationResponse(v9, v16, a3);
LABEL_24:
      v11 = (int *)v10;
LABEL_33:
      std::unique_ptr<EapHost::Packet>::operator=<std::default_delete<EapHost::Packet>,0>(a2, v11);
      std::unique_ptr<EapHost::Packet>::~unique_ptr<EapHost::Packet>(v16);
      *(_DWORD *)(a3 + 260) = 0;
      goto LABEL_58;
    case 6:
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v19, 0x800u, " Session(%d), IdentityResponse", *(_DWORD *)(a3 + 56)) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v19);
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
          *(unsigned int *)(a3 + 56));
      }
      v7 = EapHost::Peer::Host::IdentityResponse((__int64)v6, (HKEY)v16, a3);
      std::unique_ptr<EapHost::Packet>::operator=<std::default_delete<EapHost::Packet>,0>(a2, v7);
      std::unique_ptr<EapHost::Packet>::~unique_ptr<EapHost::Packet>(v16);
      *(_DWORD *)(a3 + 260) = 0;
      *(_DWORD *)(a3 + 268) = 2;
      goto LABEL_58;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
      *(unsigned int *)(a3 + 56),
      v5);
  }
LABEL_58:
  EapHost::Peer::Host::SendPacketEapAuthenticationTipTest(v8, (const struct EapHost::Peer::PeerSession *)a3);
  *(_DWORD *)(a3 + 264) = 0;
  return a2;
}

```

## disassembly

```asm
0x18002a2fc  mov     [rsp-8+arg_0], rbx
0x18002a301  push    rbp
0x18002a302  push    rsi
0x18002a303  push    rdi
0x18002a304  lea     rbp, [rsp-770h]
0x18002a30c  sub     rsp, 870h
0x18002a313  mov     rax, cs:__security_cookie
0x18002a31a  xor     rax, rsp
0x18002a31d  mov     [rbp+780h+var_20], rax
0x18002a324  mov     rbx, r8
0x18002a327  mov     rdi, rdx
0x18002a32a  mov     [rsp+880h+var_840], rdx
0x18002a32f  xor     esi, esi
0x18002a331  mov     [rsp+880h+var_848], esi
0x18002a335  mov     [rdx], rsi
0x18002a338  mov     [rsp+880h+var_848], 1
0x18002a340  mov     r8d, [r8+108h]
0x18002a347  mov     ecx, r8d
0x18002a34a  test    r8d, r8d
0x18002a34d  jz      loc_18002A77E
0x18002a353  sub     ecx, 1
0x18002a356  jz      loc_18002A6BE
0x18002a35c  sub     ecx, 1
0x18002a35f  jz      loc_18002A5F9
0x18002a365  sub     ecx, 1
0x18002a368  jz      loc_18002A5B5
0x18002a36e  sub     ecx, 1
0x18002a371  jz      loc_18002A4F3
0x18002a377  sub     ecx, 1
0x18002a37a  jz      loc_18002A44F
0x18002a380  cmp     ecx, 1
0x18002a383  jnz     loc_18002A77E
0x18002a389  lea     rdx, DebugInfoEvent
0x18002a390  mov     rcx, cs:eaphost_Context
0x18002a397  call    cs:__imp_EtwEventEnabled
0x18002a39e  nop     dword ptr [rax+rax+00h]
0x18002a3a3  test    al, al
0x18002a3a5  jz      short loc_18002A3E6
0x18002a3a7  mov     r9d, [rbx+38h]
0x18002a3ab  lea     r8, aSessionDIdenti; " Session(%d), IdentityResponse"
0x18002a3b2  mov     edx, 800h; unsigned __int64
0x18002a3b7  lea     rcx, [rsp+880h+var_820]; char *
0x18002a3bc  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002a3c1  test    eax, eax
0x18002a3c3  js      short loc_18002A3E6
0x18002a3c5  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x18002a3cc  jge     short loc_18002A3E6
0x18002a3ce  lea     r8, [rsp+880h+var_820]
0x18002a3d3  lea     rdx, DebugInfoEvent
0x18002a3da  lea     rcx, eaphost_Context
0x18002a3e1  call    McTemplateU0s_EtwEventWriteTransfer
0x18002a3e6  lea     rax, WPP_GLOBAL_Control
0x18002a3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3f4  cmp     rcx, rax
0x18002a3f7  jz      short loc_18002A418
0x18002a3f9  test    byte ptr [rcx+1Ch], 4
0x18002a3fd  jz      short loc_18002A418
0x18002a3ff  mov     edx, 44h ; 'D'
0x18002a404  mov     r9d, [rbx+38h]
0x18002a408  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002a40f  mov     rcx, [rcx+10h]
0x18002a413  call    WPP_SF_d
0x18002a418  mov     r8, rbx
0x18002a41b  lea     rdx, [rsp+880h+var_850]
0x18002a420  call    ?IdentityResponse@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z; EapHost::Peer::Host::IdentityResponse(EapHost::Peer::PeerSession &)
0x18002a425  mov     rdx, rax
0x18002a428  mov     rcx, rdi
0x18002a42b  call    ??$?4U?$default_delete@VPacket@EapHost@@@std@@$0A@@?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapHost::Packet>::operator=<std::default_delete<EapHost::Packet>,0>(std::unique_ptr<EapHost::Packet> &&)
0x18002a430  lea     rcx, [rsp+880h+var_850]
0x18002a435  call    ??1?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::Packet>::~unique_ptr<EapHost::Packet>(void)
0x18002a43a  mov     [rbx+104h], esi
0x18002a440  mov     dword ptr [rbx+10Ch], 2
0x18002a44a  jmp     loc_18002A7B5
0x18002a44f  lea     rdx, DebugInfoEvent
0x18002a456  mov     rcx, cs:eaphost_Context
0x18002a45d  call    cs:__imp_EtwEventEnabled
0x18002a464  nop     dword ptr [rax+rax+00h]
0x18002a469  test    al, al
0x18002a46b  jz      short loc_18002A4AC
0x18002a46d  mov     r9d, [rbx+38h]
0x18002a471  lea     r8, aSessionDNotifi; " Session(%d), NotificationResponse"
0x18002a478  mov     edx, 800h; unsigned __int64
0x18002a47d  lea     rcx, [rsp+880h+var_820]; char *
0x18002a482  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002a487  test    eax, eax
0x18002a489  js      short loc_18002A4AC
0x18002a48b  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x18002a492  jge     short loc_18002A4AC
0x18002a494  lea     r8, [rsp+880h+var_820]
0x18002a499  lea     rdx, DebugInfoEvent
0x18002a4a0  lea     rcx, eaphost_Context
0x18002a4a7  call    McTemplateU0s_EtwEventWriteTransfer
0x18002a4ac  lea     rax, WPP_GLOBAL_Control
0x18002a4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4ba  cmp     rcx, rax
0x18002a4bd  jz      short loc_18002A4DE
0x18002a4bf  test    byte ptr [rcx+1Ch], 4
0x18002a4c3  jz      short loc_18002A4DE
0x18002a4c5  mov     edx, 43h ; 'C'
0x18002a4ca  mov     r9d, [rbx+38h]
0x18002a4ce  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002a4d5  mov     rcx, [rcx+10h]
0x18002a4d9  call    WPP_SF_d
0x18002a4de  mov     r8, rbx
0x18002a4e1  lea     rdx, [rsp+880h+var_850]
0x18002a4e6  call    ?NotificationResponse@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z; EapHost::Peer::Host::NotificationResponse(EapHost::Peer::PeerSession &)
0x18002a4eb  mov     rdx, rax
0x18002a4ee  jmp     loc_18002A598
0x18002a4f3  lea     rdx, DebugInfoEvent
0x18002a4fa  mov     rcx, cs:eaphost_Context
0x18002a501  call    cs:__imp_EtwEventEnabled
0x18002a508  nop     dword ptr [rax+rax+00h]
0x18002a50d  test    al, al
0x18002a50f  jz      short loc_18002A550
0x18002a511  mov     r9d, [rbx+38h]
0x18002a515  lea     r8, aSessionDRetran_0; " Session(%d), RetransmitResponse"
0x18002a51c  mov     edx, 800h; unsigned __int64
0x18002a521  lea     rcx, [rsp+880h+var_820]; char *
0x18002a526  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002a52b  test    eax, eax
0x18002a52d  js      short loc_18002A550
0x18002a52f  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x18002a536  jge     short loc_18002A550
0x18002a538  lea     r8, [rsp+880h+var_820]
0x18002a53d  lea     rdx, DebugInfoEvent
0x18002a544  lea     rcx, eaphost_Context
0x18002a54b  call    McTemplateU0s_EtwEventWriteTransfer
0x18002a550  lea     rax, WPP_GLOBAL_Control
0x18002a557  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a55e  cmp     rcx, rax
0x18002a561  jz      short loc_18002A582
0x18002a563  test    byte ptr [rcx+1Ch], 4
0x18002a567  jz      short loc_18002A582
0x18002a569  mov     edx, 42h ; 'B'
0x18002a56e  mov     r9d, [rbx+38h]
0x18002a572  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002a579  mov     rcx, [rcx+10h]
0x18002a57d  call    WPP_SF_d
0x18002a582  lea     rdx, [rsp+880h+var_850]
0x18002a587  mov     rcx, [rbx+128h]; Src
0x18002a58e  call    ?Clone@Packet@EapHost@@QEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@XZ; EapHost::Packet::Clone(void)
0x18002a593  lea     rdx, [rsp+880h+var_850]
0x18002a598  mov     rcx, rdi
0x18002a59b  call    ??$?4U?$default_delete@VPacket@EapHost@@@std@@$0A@@?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapHost::Packet>::operator=<std::default_delete<EapHost::Packet>,0>(std::unique_ptr<EapHost::Packet> &&)
0x18002a5a0  lea     rcx, [rsp+880h+var_850]
0x18002a5a5  call    ??1?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::Packet>::~unique_ptr<EapHost::Packet>(void)
0x18002a5aa  mov     [rbx+104h], esi
0x18002a5b0  jmp     loc_18002A7B5
0x18002a5b5  lea     rax, WPP_GLOBAL_Control
0x18002a5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5c3  cmp     rcx, rax
0x18002a5c6  jz      short loc_18002A5E7
0x18002a5c8  test    byte ptr [rcx+1Ch], 4
0x18002a5cc  jz      short loc_18002A5E7
0x18002a5ce  mov     edx, 47h ; 'G'
0x18002a5d3  mov     r9d, [rbx+38h]
0x18002a5d7  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002a5de  mov     rcx, [rcx+10h]
0x18002a5e2  call    WPP_SF_d
0x18002a5e7  mov     r8, rbx
0x18002a5ea  lea     rdx, [rsp+880h+var_850]
0x18002a5ef  call    ?SendFromMethod@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z; EapHost::Peer::Host::SendFromMethod(EapHost::Peer::PeerSession &)
0x18002a5f4  jmp     loc_18002A4EB
0x18002a5f9  lea     rax, WPP_GLOBAL_Control
0x18002a600  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a607  cmp     rcx, rax
0x18002a60a  jz      short loc_18002A62B
0x18002a60c  test    byte ptr [rcx+1Ch], 4
0x18002a610  jz      short loc_18002A62B
0x18002a612  mov     edx, 46h ; 'F'
0x18002a617  mov     r9d, [rbx+38h]
0x18002a61b  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002a622  mov     rcx, [rcx+10h]
0x18002a626  call    WPP_SF_d
0x18002a62b  lea     rdx, DebugInfoEvent
0x18002a632  mov     rcx, cs:eaphost_Context
0x18002a639  call    cs:__imp_EtwEventEnabled
0x18002a640  nop     dword ptr [rax+rax+00h]
0x18002a645  test    al, al
0x18002a647  jz      short loc_18002A688
0x18002a649  mov     r9d, [rbx+38h]
0x18002a64d  lea     r8, aSessionDExpand; " Session(%d), ExpandedNak"
0x18002a654  mov     edx, 800h; unsigned __int64
0x18002a659  lea     rcx, [rsp+880h+var_820]; char *
0x18002a65e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002a663  test    eax, eax
0x18002a665  js      short loc_18002A688
0x18002a667  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x18002a66e  jge     short loc_18002A688
0x18002a670  lea     r8, [rsp+880h+var_820]
0x18002a675  lea     rdx, DebugInfoEvent
0x18002a67c  lea     rcx, eaphost_Context
0x18002a683  call    McTemplateU0s_EtwEventWriteTransfer
0x18002a688  lea     rdx, [rbx+84h]; struct _EAP_TYPE *
0x18002a68f  lea     rcx, [rsp+880h+var_838]; this
0x18002a694  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x18002a699  nop
0x18002a69a  mov     rdx, [rbx+130h]
0x18002a6a1  lea     r8, [rsp+880h+var_838]
0x18002a6a6  mov     dl, [rdx+1]
0x18002a6a9  lea     rcx, [rsp+880h+var_850]; int
0x18002a6ae  call    ?CreateExpandedNakResponse@Packet@EapHost@@SA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@EAEAVEapType@2@@Z; EapHost::Packet::CreateExpandedNakResponse(uchar,EapHost::EapType &)
0x18002a6b3  nop
0x18002a6b4  lea     rdx, [rsp+880h+var_850]
0x18002a6b9  jmp     loc_18002A75D
0x18002a6be  lea     rdx, DebugInfoEvent
0x18002a6c5  mov     rcx, cs:eaphost_Context
0x18002a6cc  call    cs:__imp_EtwEventEnabled
0x18002a6d3  nop     dword ptr [rax+rax+00h]
0x18002a6d8  test    al, al
0x18002a6da  jz      short loc_18002A71B
0x18002a6dc  mov     r9d, [rbx+38h]
0x18002a6e0  lea     r8, aSessionDNak; " Session(%d), Nak"
0x18002a6e7  mov     edx, 800h; unsigned __int64
0x18002a6ec  lea     rcx, [rsp+880h+var_820]; char *
0x18002a6f1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002a6f6  test    eax, eax
0x18002a6f8  js      short loc_18002A71B
0x18002a6fa  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x18002a701  jge     short loc_18002A71B
0x18002a703  lea     r8, [rsp+880h+var_820]
0x18002a708  lea     rdx, DebugInfoEvent
0x18002a70f  lea     rcx, eaphost_Context
0x18002a716  call    McTemplateU0s_EtwEventWriteTransfer
0x18002a71b  lea     rax, WPP_GLOBAL_Control
0x18002a722  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a729  cmp     rcx, rax
0x18002a72c  jz      short loc_18002A74D
0x18002a72e  test    byte ptr [rcx+1Ch], 4
0x18002a732  jz      short loc_18002A74D
0x18002a734  mov     edx, 45h ; 'E'
0x18002a739  mov     r9d, [rbx+38h]
0x18002a73d  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002a744  mov     rcx, [rcx+10h]
0x18002a748  call    WPP_SF_d
0x18002a74d  mov     r8, rbx
0x18002a750  lea     rdx, [rsp+880h+var_850]
0x18002a755  call    ?Nak@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z; EapHost::Peer::Host::Nak(EapHost::Peer::PeerSession &)
0x18002a75a  mov     rdx, rax
0x18002a75d  mov     rcx, rdi
0x18002a760  call    ??$?4U?$default_delete@VPacket@EapHost@@@std@@$0A@@?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapHost::Packet>::operator=<std::default_delete<EapHost::Packet>,0>(std::unique_ptr<EapHost::Packet> &&)
0x18002a765  lea     rcx, [rsp+880h+var_850]
0x18002a76a  call    ??1?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::Packet>::~unique_ptr<EapHost::Packet>(void)
0x18002a76f  mov     [rbx+104h], esi
0x18002a775  mov     byte ptr [rbx+116h], 1
0x18002a77c  jmp     short loc_18002A7B5
0x18002a77e  lea     rax, WPP_GLOBAL_Control
0x18002a785  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a78c  cmp     rcx, rax
0x18002a78f  jz      short loc_18002A7B5
0x18002a791  test    byte ptr [rcx+1Ch], 4
0x18002a795  jz      short loc_18002A7B5
0x18002a797  mov     edx, 48h ; 'H'
0x18002a79c  mov     [rsp+880h+var_860], r8d
0x18002a7a1  mov     r9d, [rbx+38h]
0x18002a7a5  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002a7ac  mov     rcx, [rcx+10h]
0x18002a7b0  call    WPP_SF_dd
0x18002a7b5  mov     rdx, rbx; struct EapHost::Peer::PeerSession *
0x18002a7b8  call    ?SendPacketEapAuthenticationTipTest@Host@Peer@EapHost@@AEBAXAEBVPeerSession@23@@Z; EapHost::Peer::Host::SendPacketEapAuthenticationTipTest(EapHost::Peer::PeerSession const &)
0x18002a7bd  mov     [rbx+108h], esi
0x18002a7c3  mov     rax, rdi
0x18002a7c6  mov     rcx, [rbp+780h+var_20]
0x18002a7cd  xor     rcx, rsp; StackCookie
0x18002a7d0  call    __security_check_cookie
0x18002a7d5  mov     rbx, [rsp+880h+arg_0]
0x18002a7dd  add     rsp, 870h
0x18002a7e4  pop     rdi
0x18002a7e5  pop     rsi
0x18002a7e6  pop     rbp
0x18002a7e7  retn
```

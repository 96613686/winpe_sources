# EapHost::Peer::Host::Send(EapHost::Peer::PeerSession &)

- ea: `0x1800294c8`
- end: `0x180029997`
- name: `?Send@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z`
- size: `1231`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800299a0`

## callees

- `0x180002a90`
- `0x180003948`
- `0x1800049d8`
- `0x180004ec0`
- `0x180009dec`
- `0x18000a050`
- `0x180011578`
- `0x180011958`
- `0x18001d138`
- `0x18001d248`
- `0x180026a4c`
- `0x180026d2c`
- `0x180027e50`
- `0x1800294c8`
- `0x180029aac`
- `0x180029bc0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180029563`
- `ntdll!EtwEventEnabled` at `0x180029623`
- `ntdll!EtwEventEnabled` at `0x1800296c1`
- `ntdll!EtwEventEnabled` at `0x1800297f3`
- `ntdll!EtwEventEnabled` at `0x180029880`
- `ntdll!EtwEventEnabled` at `0x180029563`
- `ntdll!EtwEventEnabled` at `0x180029623`
- `ntdll!EtwEventEnabled` at `0x1800296c1`
- `ntdll!EtwEventEnabled` at `0x1800297f3`
- `ntdll!EtwEventEnabled` at `0x180029880`

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
0x1800294c8  mov     [rsp-8+arg_0], rbx
0x1800294cd  push    rbp
0x1800294ce  push    rsi
0x1800294cf  push    rdi
0x1800294d0  lea     rbp, [rsp-770h]
0x1800294d8  sub     rsp, 870h
0x1800294df  mov     rax, cs:__security_cookie
0x1800294e6  xor     rax, rsp
0x1800294e9  mov     [rbp+780h+var_20], rax
0x1800294f0  mov     rbx, r8
0x1800294f3  mov     rdi, rdx
0x1800294f6  mov     [rsp+880h+var_840], rdx
0x1800294fb  xor     esi, esi
0x1800294fd  mov     [rsp+880h+var_848], esi
0x180029501  mov     [rdx], rsi
0x180029504  mov     [rsp+880h+var_848], 1
0x18002950c  mov     r8d, [r8+108h]
0x180029513  mov     ecx, r8d
0x180029516  test    r8d, r8d
0x180029519  jz      loc_18002992C
0x18002951f  sub     ecx, 1
0x180029522  jz      loc_180029872
0x180029528  sub     ecx, 1
0x18002952b  jz      loc_1800297B3
0x180029531  sub     ecx, 1
0x180029534  jz      loc_18002976F
0x18002953a  sub     ecx, 1
0x18002953d  jz      loc_1800296B3
0x180029543  sub     ecx, 1
0x180029546  jz      loc_180029615
0x18002954c  cmp     ecx, 1
0x18002954f  jnz     loc_18002992C
0x180029555  lea     rdx, DebugInfoEvent
0x18002955c  mov     rcx, cs:eaphost_Context
0x180029563  call    cs:__imp_EtwEventEnabled
0x180029569  test    al, al
0x18002956b  jz      short loc_1800295AC
0x18002956d  mov     r9d, [rbx+38h]
0x180029571  lea     r8, aSessionDIdenti; " Session(%d), IdentityResponse"
0x180029578  mov     edx, 800h; unsigned __int64
0x18002957d  lea     rcx, [rsp+880h+var_820]; char *
0x180029582  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180029587  test    eax, eax
0x180029589  js      short loc_1800295AC
0x18002958b  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x180029592  jge     short loc_1800295AC
0x180029594  lea     r8, [rsp+880h+var_820]
0x180029599  lea     rdx, DebugInfoEvent
0x1800295a0  lea     rcx, eaphost_Context
0x1800295a7  call    McTemplateU0s_EtwEventWriteTransfer
0x1800295ac  lea     rax, WPP_GLOBAL_Control
0x1800295b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800295ba  cmp     rcx, rax
0x1800295bd  jz      short loc_1800295DE
0x1800295bf  test    byte ptr [rcx+1Ch], 4
0x1800295c3  jz      short loc_1800295DE
0x1800295c5  mov     edx, 44h ; 'D'
0x1800295ca  mov     r9d, [rbx+38h]
0x1800295ce  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800295d5  mov     rcx, [rcx+10h]
0x1800295d9  call    WPP_SF_d
0x1800295de  mov     r8, rbx
0x1800295e1  lea     rdx, [rsp+880h+var_850]
0x1800295e6  call    ?IdentityResponse@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z; EapHost::Peer::Host::IdentityResponse(EapHost::Peer::PeerSession &)
0x1800295eb  mov     rdx, rax
0x1800295ee  mov     rcx, rdi
0x1800295f1  call    ??$?4U?$default_delete@VPacket@EapHost@@@std@@$0A@@?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapHost::Packet>::operator=<std::default_delete<EapHost::Packet>,0>(std::unique_ptr<EapHost::Packet> &&)
0x1800295f6  lea     rcx, [rsp+880h+var_850]
0x1800295fb  call    ??1?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::Packet>::~unique_ptr<EapHost::Packet>(void)
0x180029600  mov     [rbx+104h], esi
0x180029606  mov     dword ptr [rbx+10Ch], 2
0x180029610  jmp     loc_180029963
0x180029615  lea     rdx, DebugInfoEvent
0x18002961c  mov     rcx, cs:eaphost_Context
0x180029623  call    cs:__imp_EtwEventEnabled
0x180029629  test    al, al
0x18002962b  jz      short loc_18002966C
0x18002962d  mov     r9d, [rbx+38h]
0x180029631  lea     r8, aSessionDNotifi; " Session(%d), NotificationResponse"
0x180029638  mov     edx, 800h; unsigned __int64
0x18002963d  lea     rcx, [rsp+880h+var_820]; char *
0x180029642  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180029647  test    eax, eax
0x180029649  js      short loc_18002966C
0x18002964b  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x180029652  jge     short loc_18002966C
0x180029654  lea     r8, [rsp+880h+var_820]
0x180029659  lea     rdx, DebugInfoEvent
0x180029660  lea     rcx, eaphost_Context
0x180029667  call    McTemplateU0s_EtwEventWriteTransfer
0x18002966c  lea     rax, WPP_GLOBAL_Control
0x180029673  mov     rcx, cs:WPP_GLOBAL_Control
0x18002967a  cmp     rcx, rax
0x18002967d  jz      short loc_18002969E
0x18002967f  test    byte ptr [rcx+1Ch], 4
0x180029683  jz      short loc_18002969E
0x180029685  mov     edx, 43h ; 'C'
0x18002968a  mov     r9d, [rbx+38h]
0x18002968e  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180029695  mov     rcx, [rcx+10h]
0x180029699  call    WPP_SF_d
0x18002969e  mov     r8, rbx
0x1800296a1  lea     rdx, [rsp+880h+var_850]
0x1800296a6  call    ?NotificationResponse@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z; EapHost::Peer::Host::NotificationResponse(EapHost::Peer::PeerSession &)
0x1800296ab  mov     rdx, rax
0x1800296ae  jmp     loc_180029752
0x1800296b3  lea     rdx, DebugInfoEvent
0x1800296ba  mov     rcx, cs:eaphost_Context
0x1800296c1  call    cs:__imp_EtwEventEnabled
0x1800296c7  test    al, al
0x1800296c9  jz      short loc_18002970A
0x1800296cb  mov     r9d, [rbx+38h]
0x1800296cf  lea     r8, aSessionDRetran_0; " Session(%d), RetransmitResponse"
0x1800296d6  mov     edx, 800h; unsigned __int64
0x1800296db  lea     rcx, [rsp+880h+var_820]; char *
0x1800296e0  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800296e5  test    eax, eax
0x1800296e7  js      short loc_18002970A
0x1800296e9  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x1800296f0  jge     short loc_18002970A
0x1800296f2  lea     r8, [rsp+880h+var_820]
0x1800296f7  lea     rdx, DebugInfoEvent
0x1800296fe  lea     rcx, eaphost_Context
0x180029705  call    McTemplateU0s_EtwEventWriteTransfer
0x18002970a  lea     rax, WPP_GLOBAL_Control
0x180029711  mov     rcx, cs:WPP_GLOBAL_Control
0x180029718  cmp     rcx, rax
0x18002971b  jz      short loc_18002973C
0x18002971d  test    byte ptr [rcx+1Ch], 4
0x180029721  jz      short loc_18002973C
0x180029723  mov     edx, 42h ; 'B'
0x180029728  mov     r9d, [rbx+38h]
0x18002972c  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180029733  mov     rcx, [rcx+10h]
0x180029737  call    WPP_SF_d
0x18002973c  lea     rdx, [rsp+880h+var_850]
0x180029741  mov     rcx, [rbx+128h]; Src
0x180029748  call    ?Clone@Packet@EapHost@@QEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@XZ; EapHost::Packet::Clone(void)
0x18002974d  lea     rdx, [rsp+880h+var_850]
0x180029752  mov     rcx, rdi
0x180029755  call    ??$?4U?$default_delete@VPacket@EapHost@@@std@@$0A@@?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapHost::Packet>::operator=<std::default_delete<EapHost::Packet>,0>(std::unique_ptr<EapHost::Packet> &&)
0x18002975a  lea     rcx, [rsp+880h+var_850]
0x18002975f  call    ??1?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::Packet>::~unique_ptr<EapHost::Packet>(void)
0x180029764  mov     [rbx+104h], esi
0x18002976a  jmp     loc_180029963
0x18002976f  lea     rax, WPP_GLOBAL_Control
0x180029776  mov     rcx, cs:WPP_GLOBAL_Control
0x18002977d  cmp     rcx, rax
0x180029780  jz      short loc_1800297A1
0x180029782  test    byte ptr [rcx+1Ch], 4
0x180029786  jz      short loc_1800297A1
0x180029788  mov     edx, 47h ; 'G'
0x18002978d  mov     r9d, [rbx+38h]
0x180029791  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180029798  mov     rcx, [rcx+10h]
0x18002979c  call    WPP_SF_d
0x1800297a1  mov     r8, rbx
0x1800297a4  lea     rdx, [rsp+880h+var_850]
0x1800297a9  call    ?SendFromMethod@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z; EapHost::Peer::Host::SendFromMethod(EapHost::Peer::PeerSession &)
0x1800297ae  jmp     loc_1800296AB
0x1800297b3  lea     rax, WPP_GLOBAL_Control
0x1800297ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297c1  cmp     rcx, rax
0x1800297c4  jz      short loc_1800297E5
0x1800297c6  test    byte ptr [rcx+1Ch], 4
0x1800297ca  jz      short loc_1800297E5
0x1800297cc  mov     edx, 46h ; 'F'
0x1800297d1  mov     r9d, [rbx+38h]
0x1800297d5  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800297dc  mov     rcx, [rcx+10h]
0x1800297e0  call    WPP_SF_d
0x1800297e5  lea     rdx, DebugInfoEvent
0x1800297ec  mov     rcx, cs:eaphost_Context
0x1800297f3  call    cs:__imp_EtwEventEnabled
0x1800297f9  test    al, al
0x1800297fb  jz      short loc_18002983C
0x1800297fd  mov     r9d, [rbx+38h]
0x180029801  lea     r8, aSessionDExpand; " Session(%d), ExpandedNak"
0x180029808  mov     edx, 800h; unsigned __int64
0x18002980d  lea     rcx, [rsp+880h+var_820]; char *
0x180029812  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180029817  test    eax, eax
0x180029819  js      short loc_18002983C
0x18002981b  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x180029822  jge     short loc_18002983C
0x180029824  lea     r8, [rsp+880h+var_820]
0x180029829  lea     rdx, DebugInfoEvent
0x180029830  lea     rcx, eaphost_Context
0x180029837  call    McTemplateU0s_EtwEventWriteTransfer
0x18002983c  lea     rdx, [rbx+84h]; struct _EAP_TYPE *
0x180029843  lea     rcx, [rsp+880h+var_838]; this
0x180029848  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x18002984d  nop
0x18002984e  mov     rdx, [rbx+130h]
0x180029855  lea     r8, [rsp+880h+var_838]
0x18002985a  mov     dl, [rdx+1]
0x18002985d  lea     rcx, [rsp+880h+var_850]; int
0x180029862  call    ?CreateExpandedNakResponse@Packet@EapHost@@SA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@EAEAVEapType@2@@Z; EapHost::Packet::CreateExpandedNakResponse(uchar,EapHost::EapType &)
0x180029867  nop
0x180029868  lea     rdx, [rsp+880h+var_850]
0x18002986d  jmp     loc_18002990B
0x180029872  lea     rdx, DebugInfoEvent
0x180029879  mov     rcx, cs:eaphost_Context
0x180029880  call    cs:__imp_EtwEventEnabled
0x180029886  test    al, al
0x180029888  jz      short loc_1800298C9
0x18002988a  mov     r9d, [rbx+38h]
0x18002988e  lea     r8, aSessionDNak; " Session(%d), Nak"
0x180029895  mov     edx, 800h; unsigned __int64
0x18002989a  lea     rcx, [rsp+880h+var_820]; char *
0x18002989f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800298a4  test    eax, eax
0x1800298a6  js      short loc_1800298C9
0x1800298a8  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x1800298af  jge     short loc_1800298C9
0x1800298b1  lea     r8, [rsp+880h+var_820]
0x1800298b6  lea     rdx, DebugInfoEvent
0x1800298bd  lea     rcx, eaphost_Context
0x1800298c4  call    McTemplateU0s_EtwEventWriteTransfer
0x1800298c9  lea     rax, WPP_GLOBAL_Control
0x1800298d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800298d7  cmp     rcx, rax
0x1800298da  jz      short loc_1800298FB
0x1800298dc  test    byte ptr [rcx+1Ch], 4
0x1800298e0  jz      short loc_1800298FB
0x1800298e2  mov     edx, 45h ; 'E'
0x1800298e7  mov     r9d, [rbx+38h]
0x1800298eb  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800298f2  mov     rcx, [rcx+10h]
0x1800298f6  call    WPP_SF_d
0x1800298fb  mov     r8, rbx
0x1800298fe  lea     rdx, [rsp+880h+var_850]
0x180029903  call    ?Nak@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z; EapHost::Peer::Host::Nak(EapHost::Peer::PeerSession &)
0x180029908  mov     rdx, rax
0x18002990b  mov     rcx, rdi
0x18002990e  call    ??$?4U?$default_delete@VPacket@EapHost@@@std@@$0A@@?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapHost::Packet>::operator=<std::default_delete<EapHost::Packet>,0>(std::unique_ptr<EapHost::Packet> &&)
0x180029913  lea     rcx, [rsp+880h+var_850]
0x180029918  call    ??1?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::Packet>::~unique_ptr<EapHost::Packet>(void)
0x18002991d  mov     [rbx+104h], esi
0x180029923  mov     byte ptr [rbx+116h], 1
0x18002992a  jmp     short loc_180029963
0x18002992c  lea     rax, WPP_GLOBAL_Control
0x180029933  mov     rcx, cs:WPP_GLOBAL_Control
0x18002993a  cmp     rcx, rax
0x18002993d  jz      short loc_180029963
0x18002993f  test    byte ptr [rcx+1Ch], 4
0x180029943  jz      short loc_180029963
0x180029945  mov     edx, 48h ; 'H'
0x18002994a  mov     [rsp+880h+var_860], r8d
0x18002994f  mov     r9d, [rbx+38h]
0x180029953  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002995a  mov     rcx, [rcx+10h]
0x18002995e  call    WPP_SF_dd
0x180029963  mov     rdx, rbx; struct EapHost::Peer::PeerSession *
0x180029966  call    ?SendPacketEapAuthenticationTipTest@Host@Peer@EapHost@@AEBAXAEBVPeerSession@23@@Z; EapHost::Peer::Host::SendPacketEapAuthenticationTipTest(EapHost::Peer::PeerSession const &)
0x18002996b  mov     [rbx+108h], esi
0x180029971  mov     rax, rdi
0x180029974  mov     rcx, [rbp+780h+var_20]
0x18002997b  xor     rcx, rsp; StackCookie
0x18002997e  call    __security_check_cookie
0x180029983  mov     rbx, [rsp+880h+arg_0]
0x18002998b  add     rsp, 870h
0x180029992  pop     rdi
0x180029993  pop     rsi
0x180029994  pop     rbp
0x180029995  retn
```

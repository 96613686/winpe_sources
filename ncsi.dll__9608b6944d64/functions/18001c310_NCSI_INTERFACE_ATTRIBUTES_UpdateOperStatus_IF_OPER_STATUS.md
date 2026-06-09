# NCSI_INTERFACE_ATTRIBUTES::UpdateOperStatus(IF_OPER_STATUS)

- ea: `0x18001c310`
- end: `0x18001c5b5`
- name: `?UpdateOperStatus@NCSI_INTERFACE_ATTRIBUTES@@QEAA_NW4IF_OPER_STATUS@@@Z`
- size: `677`
- prototype: `bool __fastcall(NCSI_INTERFACE_ATTRIBUTES *__hidden this, enum IF_OPER_STATUS)`
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a950`
- `0x18001c1c4`
- `0x1800451a0`

## callees

- `0x180004450`
- `0x1800098e8`
- `0x18000e59c`
- `0x1800182b4`
- `0x18001a564`
- `0x18001a5dc`
- `0x18001c310`
- `0x180027070`
- `0x18002f990`
- `0x1800301e8`
- `0x1800310d8`
- `0x18004147c`
- `0x180042950`
- `0x180042b90`
- `0x180059b68`
- `0x180062a0c`
- `0x180062b28`
- `0x180062b60`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c38a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c38a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c51f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c51f`

## pseudocode

```c
char __fastcall NCSI_INTERFACE_ATTRIBUTES::UpdateOperStatus(NCSI_INTERFACE_ATTRIBUTES *this, enum IF_OPER_STATUS a2)
{
  int v2; // eax
  ULONGLONG TickCount64; // rax
  __int128 v6; // xmm0
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int128 v13; // [rsp+40h] [rbp-28h]
  __int128 v14; // [rsp+40h] [rbp-28h]
  __int64 v15; // [rsp+90h] [rbp+28h] BYREF
  int v16; // [rsp+98h] [rbp+30h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+38h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+40h] BYREF

  v2 = *((_DWORD *)this + 2918);
  if ( v2 != a2 && (v2 == 1 || a2 == IfOperStatusUp) )
  {
    *((_DWORD *)this + 2918) = a2;
    if ( a2 == IfOperStatusUp )
    {
      if ( !*((_DWORD *)this + 6) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      ++*((_QWORD *)this + 1460);
      NCSI_INTERFACE_ATTRIBUTES::ResetInternetProbeState(this);
      *((_DWORD *)this + 6) = 0;
      if ( *((_BYTE *)this + 11745) )
      {
        if ( (unsigned __int8)InterfaceStatsDwordValue<bool>::GetValue((char *)this + 11744) )
        {
          TickCount64 = GetTickCount64();
          *((_BYTE *)this + 12088) = 0;
          *((_QWORD *)this + 1465) = TickCount64;
          InterfaceStats::ResetStatistics((NCSI_INTERFACE_ATTRIBUTES *)((char *)this + 11720));
        }
      }
      *((_DWORD *)this + 2937) = 1;
      *((_BYTE *)this + 11752) = 1;
      *((_DWORD *)this + 2939) = GetZeroSpecialTickCount();
      *((_BYTE *)this + 11760) = 1;
      *((_BYTE *)this + 12885) = 0;
    }
    else
    {
      if ( *((_DWORD *)this + 6) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      *((_DWORD *)this + 2937) = a2;
      *((_BYTE *)this + 11752) = 1;
      if ( *((_QWORD *)this + 1465) )
      {
        InterfaceStats::CheckpointStatistics((NCSI_INTERFACE_ATTRIBUTES *)((char *)this + 11720));
        *((_QWORD *)this + 1465) = 0;
      }
      *((_DWORD *)this + 1132) = -1;
      *((_BYTE *)this + 11812) = 0;
      *((_DWORD *)this + 2118) = -1;
      *((_BYTE *)this + 11884) = 0;
      *((_DWORD *)this + 1133) = -1;
      *((_BYTE *)this + 11824) = 0;
      *((_DWORD *)this + 2119) = -1;
      *((_BYTE *)this + 11896) = 0;
      NCSI_INTERFACE_ATTRIBUTES::ResetInternetProbeState(this);
      v13 = 0;
      HIDWORD(v13) = 0;
      v6 = v13;
      v14 = 0;
      *(_OWORD *)((char *)this + 4500) = v6;
      HIDWORD(v14) = 0;
      *((_OWORD *)this + 282) = 0;
      *(_OWORD *)((char *)this + 8444) = v14;
      *(_OWORD *)((char *)this + 8456) = 0;
      NCSI_INTERFACE_ATTRIBUTES::ResetNextHopToProxy(this);
      NCSI_INTERFACE_ATTRIBUTES::ClearHotspotMode(v7, 0);
      NCSI_INTERFACE_ATTRIBUTES::ClearHotspotMode(this, 1);
      *((_BYTE *)this + 4499) = 0;
      *((_BYTE *)this + 8443) = 0;
      NCSI_INTERFACE_ATTRIBUTES::SetIpAddressExistence(this, 0, 0);
      NCSI_INTERFACE_ATTRIBUTES::SetIpAddressExistence(this, 1, 0);
      NCSI_INTERFACE_ATTRIBUTES::SetGlobalIpAddressExistence(this, 0, 0);
      NCSI_INTERFACE_ATTRIBUTES::SetGlobalIpAddressExistence(this, 1, 0);
      NCSI_INTERFACE_ATTRIBUTES::SetNoDefaultGateway(this, 0);
      NCSI_INTERFACE_ATTRIBUTES::SetNoDefaultGateway(v8, 1);
      NCSI_INTERFACE_ATTRIBUTES::ResetCapabilityForFamily(v9, 0);
      NCSI_INTERFACE_ATTRIBUTES::ResetCapabilityForFamily(this, 1);
      Nsi::UpdateInterfaceCorporateLocation(this, 0);
      NCSI_INTERFACE_ATTRIBUTES::SetCorporateConnectivity(this, 0);
      NCSI_INTERFACE_ATTRIBUTES::ResetCorporateLocationDetection(this);
      *((_DWORD *)this + 6) = 1;
      *((_DWORD *)this + 2922) = GetTickCount();
      if ( (unsigned int)dword_18009A048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A048, 0x200000000000LL) )
      {
        v16 = *((unsigned __int16 *)this + 3);
        v17 = *(_QWORD *)this;
        v15 = 2048;
        v18 = (__int64)this + 8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (__int64)&v18,
          (int)&word_180087696,
          v10,
          v11,
          &v18,
          (__int64)&v17,
          (__int64)&v16,
          (__int64)&v15);
      }
    }
    return 1;
  }
  else
  {
    *((_DWORD *)this + 2918) = a2;
    return 0;
  }
}

```

## disassembly

```asm
0x18001c310  push    rbp
0x18001c312  push    rbx
0x18001c313  push    rsi
0x18001c314  push    r14
0x18001c316  mov     rbp, rsp
0x18001c319  sub     rsp, 68h
0x18001c31d  mov     eax, [rcx+2D98h]
0x18001c323  mov     esi, edx
0x18001c325  mov     rbx, rcx
0x18001c328  cmp     eax, edx
0x18001c32a  jz      loc_18001C5A3
0x18001c330  mov     r14d, 1
0x18001c336  cmp     eax, r14d
0x18001c339  jz      short loc_18001C344
0x18001c33b  cmp     edx, r14d
0x18001c33e  jnz     loc_18001C5A3
0x18001c344  mov     [rcx+2D98h], esi
0x18001c34a  cmp     esi, r14d
0x18001c34d  jnz     short loc_18001C3CE
0x18001c34f  cmp     dword ptr [rcx+18h], 0
0x18001c353  jnz     short loc_18001C35A
0x18001c355  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c35a  add     [rbx+2DA0h], r14
0x18001c361  mov     rcx, rbx; this
0x18001c364  call    ?ResetInternetProbeState@NCSI_INTERFACE_ATTRIBUTES@@QEAAXXZ; NCSI_INTERFACE_ATTRIBUTES::ResetInternetProbeState(void)
0x18001c369  lea     rsi, [rbx+2DC8h]
0x18001c370  mov     dword ptr [rbx+18h], 0
0x18001c377  cmp     byte ptr [rsi+19h], 0
0x18001c37b  jz      short loc_18001C3A2
0x18001c37d  lea     rcx, [rsi+18h]
0x18001c381  call    ?GetValue@?$InterfaceStatsDwordValue@_N@@QEBA_NXZ; InterfaceStatsDwordValue<bool>::GetValue(void)
0x18001c386  test    al, al
0x18001c388  jz      short loc_18001C3A2
0x18001c38a  call    cs:__imp_GetTickCount64
0x18001c390  mov     rcx, rsi; this
0x18001c393  mov     byte ptr [rsi+170h], 0
0x18001c39a  mov     [rsi], rax
0x18001c39d  call    ?ResetStatistics@InterfaceStats@@AEAAXXZ; InterfaceStats::ResetStatistics(void)
0x18001c3a2  mov     [rbx+2DE4h], r14d
0x18001c3a9  mov     [rbx+2DE8h], r14b
0x18001c3b0  call    ?GetZeroSpecialTickCount@@YAKXZ; GetZeroSpecialTickCount(void)
0x18001c3b5  mov     [rbx+2DECh], eax
0x18001c3bb  mov     [rbx+2DF0h], r14b
0x18001c3c2  mov     byte ptr [rbx+3255h], 0
0x18001c3c9  jmp     loc_18001C59E
0x18001c3ce  cmp     dword ptr [rcx+18h], 0
0x18001c3d2  jz      short loc_18001C3D9
0x18001c3d4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c3d9  mov     [rbx+2DE4h], esi
0x18001c3df  lea     rsi, [rbx+2DC8h]
0x18001c3e6  mov     [rbx+2DE8h], r14b
0x18001c3ed  cmp     qword ptr [rsi], 0
0x18001c3f1  jz      short loc_18001C402
0x18001c3f3  mov     rcx, rsi; this
0x18001c3f6  call    ?CheckpointStatistics@InterfaceStats@@AEAAXXZ; InterfaceStats::CheckpointStatistics(void)
0x18001c3fb  mov     qword ptr [rsi], 0
0x18001c402  or      eax, 0FFFFFFFFh
0x18001c405  mov     rcx, rbx; this
0x18001c408  mov     [rbx+11B0h], eax
0x18001c40e  mov     byte ptr [rbx+2E24h], 0
0x18001c415  mov     [rbx+2118h], eax
0x18001c41b  mov     byte ptr [rbx+2E6Ch], 0
0x18001c422  mov     [rbx+11B4h], eax
0x18001c428  mov     byte ptr [rbx+2E30h], 0
0x18001c42f  mov     [rbx+211Ch], eax
0x18001c435  mov     byte ptr [rbx+2E78h], 0
0x18001c43c  call    ?ResetInternetProbeState@NCSI_INTERFACE_ATTRIBUTES@@QEAAXXZ; NCSI_INTERFACE_ATTRIBUTES::ResetInternetProbeState(void)
0x18001c441  xorps   xmm1, xmm1
0x18001c444  xorps   xmm2, xmm2
0x18001c447  movups  [rbp+var_28], xmm1
0x18001c44b  xor     eax, eax
0x18001c44d  mov     rcx, rbx; this
0x18001c450  movups  [rbp+var_28+0Ch], xmm1
0x18001c454  movups  xmm0, [rbp+var_28]
0x18001c458  movups  [rbp+var_28], xmm2
0x18001c45c  movups  xmmword ptr [rbx+1194h], xmm0
0x18001c463  movups  [rbp+var_28+0Ch], xmm2
0x18001c467  movups  xmm0, [rbp+var_28]
0x18001c46b  movups  xmmword ptr [rbx+11A0h], xmm1
0x18001c472  movups  xmmword ptr [rbx+20FCh], xmm0
0x18001c479  movups  xmmword ptr [rbx+2108h], xmm2
0x18001c480  call    ?ResetNextHopToProxy@NCSI_INTERFACE_ATTRIBUTES@@QEAAXXZ; NCSI_INTERFACE_ATTRIBUTES::ResetNextHopToProxy(void)
0x18001c485  xor     edx, edx
0x18001c487  call    ?ClearHotspotMode@NCSI_INTERFACE_ATTRIBUTES@@QEAAXW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::ClearHotspotMode(_NLA_CONNECTIVITY_FAMILY)
0x18001c48c  mov     edx, r14d
0x18001c48f  mov     rcx, rbx
0x18001c492  call    ?ClearHotspotMode@NCSI_INTERFACE_ATTRIBUTES@@QEAAXW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::ClearHotspotMode(_NLA_CONNECTIVITY_FAMILY)
0x18001c497  xor     r8d, r8d
0x18001c49a  mov     byte ptr [rbx+1193h], 0
0x18001c4a1  xor     edx, edx
0x18001c4a3  mov     byte ptr [rbx+20FBh], 0
0x18001c4aa  mov     rcx, rbx
0x18001c4ad  call    ?SetIpAddressExistence@NCSI_INTERFACE_ATTRIBUTES@@QEAA_NW4_NLA_CONNECTIVITY_FAMILY@@_N@Z; NCSI_INTERFACE_ATTRIBUTES::SetIpAddressExistence(_NLA_CONNECTIVITY_FAMILY,bool)
0x18001c4b2  xor     r8d, r8d
0x18001c4b5  mov     edx, r14d
0x18001c4b8  mov     rcx, rbx
0x18001c4bb  call    ?SetIpAddressExistence@NCSI_INTERFACE_ATTRIBUTES@@QEAA_NW4_NLA_CONNECTIVITY_FAMILY@@_N@Z; NCSI_INTERFACE_ATTRIBUTES::SetIpAddressExistence(_NLA_CONNECTIVITY_FAMILY,bool)
0x18001c4c0  xor     r8d, r8d
0x18001c4c3  xor     edx, edx
0x18001c4c5  mov     rcx, rbx
0x18001c4c8  call    ?SetGlobalIpAddressExistence@NCSI_INTERFACE_ATTRIBUTES@@QEAA_NW4_NLA_CONNECTIVITY_FAMILY@@_N@Z; NCSI_INTERFACE_ATTRIBUTES::SetGlobalIpAddressExistence(_NLA_CONNECTIVITY_FAMILY,bool)
0x18001c4cd  xor     r8d, r8d
0x18001c4d0  mov     edx, r14d
0x18001c4d3  mov     rcx, rbx
0x18001c4d6  call    ?SetGlobalIpAddressExistence@NCSI_INTERFACE_ATTRIBUTES@@QEAA_NW4_NLA_CONNECTIVITY_FAMILY@@_N@Z; NCSI_INTERFACE_ATTRIBUTES::SetGlobalIpAddressExistence(_NLA_CONNECTIVITY_FAMILY,bool)
0x18001c4db  xor     edx, edx
0x18001c4dd  mov     rcx, rbx
0x18001c4e0  call    ?SetNoDefaultGateway@NCSI_INTERFACE_ATTRIBUTES@@QEAAXW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::SetNoDefaultGateway(_NLA_CONNECTIVITY_FAMILY)
0x18001c4e5  mov     edx, r14d
0x18001c4e8  call    ?SetNoDefaultGateway@NCSI_INTERFACE_ATTRIBUTES@@QEAAXW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::SetNoDefaultGateway(_NLA_CONNECTIVITY_FAMILY)
0x18001c4ed  xor     edx, edx
0x18001c4ef  call    ?ResetCapabilityForFamily@NCSI_INTERFACE_ATTRIBUTES@@QEAAXW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::ResetCapabilityForFamily(_NLA_CONNECTIVITY_FAMILY)
0x18001c4f4  mov     edx, r14d
0x18001c4f7  mov     rcx, rbx
0x18001c4fa  call    ?ResetCapabilityForFamily@NCSI_INTERFACE_ATTRIBUTES@@QEAAXW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::ResetCapabilityForFamily(_NLA_CONNECTIVITY_FAMILY)
0x18001c4ff  xor     edx, edx; union _NET_LUID_LH *
0x18001c501  mov     rcx, rbx; this
0x18001c504  call    ?UpdateInterfaceCorporateLocation@Nsi@@YA_NAEBT_NET_LUID_LH@@_N@Z; Nsi::UpdateInterfaceCorporateLocation(_NET_LUID_LH const &,bool)
0x18001c509  xor     edx, edx; bool
0x18001c50b  mov     rcx, rbx; this
0x18001c50e  call    ?SetCorporateConnectivity@NCSI_INTERFACE_ATTRIBUTES@@QEAA_N_N@Z; NCSI_INTERFACE_ATTRIBUTES::SetCorporateConnectivity(bool)
0x18001c513  mov     rcx, rbx; this
0x18001c516  call    ?ResetCorporateLocationDetection@NCSI_INTERFACE_ATTRIBUTES@@QEAAXXZ; NCSI_INTERFACE_ATTRIBUTES::ResetCorporateLocationDetection(void)
0x18001c51b  mov     [rbx+18h], r14d
0x18001c51f  call    cs:__imp_GetTickCount
0x18001c525  mov     [rbx+2DA8h], eax
0x18001c52b  mov     eax, cs:dword_18009A048
0x18001c531  cmp     eax, 5
0x18001c534  jbe     short loc_18001C59E
0x18001c536  mov     rdx, 200000000000h
0x18001c540  lea     rcx, dword_18009A048
0x18001c547  call    _tlgKeywordOn
0x18001c54c  test    al, al
0x18001c54e  jz      short loc_18001C59E
0x18001c550  movzx   eax, word ptr [rbx+6]
0x18001c554  lea     rcx, [rbp+arg_0]
0x18001c558  mov     [rsp+68h+var_30], rcx
0x18001c55d  lea     rdx, word_180087696
0x18001c564  mov     [rbp+arg_8], eax
0x18001c567  lea     rcx, [rbp+arg_8]
0x18001c56b  mov     rax, [rbx]
0x18001c56e  mov     [rsp+68h+var_38], rcx
0x18001c573  lea     rcx, [rbp+arg_10]
0x18001c577  mov     [rsp+68h+var_40], rcx
0x18001c57c  lea     rcx, [rbp+arg_18]
0x18001c580  mov     [rbp+arg_10], rax
0x18001c584  lea     rax, [rbx+8]
0x18001c588  mov     [rsp+68h+var_48], rcx
0x18001c58d  mov     [rbp+arg_0], 800h
0x18001c595  mov     [rbp+arg_18], rax
0x18001c599  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001c59e  mov     al, r14b
0x18001c5a1  jmp     short loc_18001C5AB
0x18001c5a3  mov     [rcx+2D98h], esi
0x18001c5a9  xor     al, al
0x18001c5ab  add     rsp, 68h
0x18001c5af  pop     r14
0x18001c5b1  pop     rsi
0x18001c5b2  pop     rbx
0x18001c5b3  pop     rbp
0x18001c5b4  retn
```

# cdp::CommandServicePollResponse::CommandJsonPayload::CommandJsonPayload(cdp::Serializer<cdp::JsonData> const &)

- ea: `0x1801d29a4`
- end: `0x1801d2f68`
- name: `??$?0UJsonData@cdp@@@CommandJsonPayload@CommandServicePollResponse@cdp@@QEAA@AEBV?$Serializer@UJsonData@cdp@@@2@@Z`
- size: `1476`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802a3158`

## callees

- `0x180010ee0`
- `0x18001ee70`
- `0x180030190`
- `0x1800482a0`
- `0x18005ba50`
- `0x1800809b8`
- `0x1800c1fec`
- `0x1800dd0f4`
- `0x18011db1c`
- `0x1801d29a4`
- `0x1801f6fb0`
- `0x1802126a8`
- `0x18027eaa8`
- `0x18027eb54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1801d2e4c`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1801d2e4c`

## string_xrefs

- `0x1801d2f22`: `{"text":"Ignoring sequencing for Request ID '%s' because fastPathSessionId is empty"}`
- `0x1801d2c44`: `commandTypeId`
- `0x1801d2c8a`: `commandTypeId`
- `0x1801d2cac`: `commandTypeText`
- `0x1801d2cf5`: `commandTypeText`
- `0x1801d2eb6`: `fastPathSessionId`
- `0x1801d2e67`: `fastPathSequenceNumber`
- `0x1801d2aec`: `onecoreuap\windows\cdp\core\private\CommandServicePollResponse.h`
- `0x1801d2b52`: `onecoreuap\windows\cdp\core\private\CommandServicePollResponse.h`
- `0x1801d2bb8`: `onecoreuap\windows\cdp\core\private\CommandServicePollResponse.h`
- `0x1801d2c17`: `onecoreuap\windows\cdp\core\private\CommandServicePollResponse.h`
- `0x1801d2c78`: `onecoreuap\windows\cdp\core\private\CommandServicePollResponse.h`
- `0x1801d2ce3`: `onecoreuap\windows\cdp\core\private\CommandServicePollResponse.h`
- `0x1801d2d4e`: `onecoreuap\windows\cdp\core\private\CommandServicePollResponse.h`
- `0x1801d2db9`: `onecoreuap\windows\cdp\core\private\CommandServicePollResponse.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall cdp::CommandServicePollResponse::CommandJsonPayload::CommandJsonPayload(__int64 a1, __int64 a2)
{
  const char *v4; // r15
  _QWORD *v5; // rdi
  __int64 v6; // r14
  __int64 v7; // r13
  char v8; // bl
  __int64 v9; // r8
  __int64 v10; // rax
  char v11; // bl
  __int64 v12; // r8
  __int64 v13; // rax
  char v14; // bl
  __int64 v15; // rax
  char v16; // bl
  __int64 v17; // rax
  char v18; // bl
  __int64 v19; // r8
  __int64 v20; // rax
  char v21; // bl
  __int64 v22; // r8
  __int64 v23; // rax
  char v24; // bl
  __int64 v25; // r8
  __int64 v26; // rax
  char v27; // bl
  __int64 v28; // r8
  __int64 v29; // rax
  _BYTE *v30; // r14
  _QWORD *v31; // rbx
  char v32; // bl
  char v33; // bl
  const char *v35; // [rsp+20h] [rbp-59h] BYREF
  int v36; // [rsp+28h] [rbp-51h]
  __int64 v37; // [rsp+30h] [rbp-49h]
  _OWORD v38[2]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v39[56]; // [rsp+60h] [rbp-19h] BYREF

  v37 = a1;
  *(_QWORD *)a1 = &cdp::CommandServicePollResponse::CommandJsonPayload::`vftable';
  v4 = (const char *)(a1 + 8);
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 15;
  *(_BYTE *)(a1 + 8) = 0;
  v5 = (_QWORD *)(a1 + 40);
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 15;
  *(_BYTE *)(a1 + 40) = 0;
  v6 = a1 + 72;
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 15;
  *(_BYTE *)(a1 + 72) = 0;
  v7 = a1 + 104;
  *(_OWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 15;
  *(_BYTE *)(a1 + 104) = 0;
  *(_BYTE *)(a1 + 136) = 0;
  *(_OWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 15;
  *(_BYTE *)(a1 + 144) = 0;
  *(_OWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 15;
  *(_BYTE *)(a1 + 176) = 0;
  *(_OWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 15;
  *(_BYTE *)(a1 + 208) = 0;
  *(_OWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 15;
  *(_BYTE *)(a1 + 240) = 0;
  *(_BYTE *)(a1 + 272) = 0;
  *(_DWORD *)(a1 + 276) = 0;
  *(_OWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 296) = 0;
  *(_QWORD *)(a1 + 304) = 15;
  *(_BYTE *)(a1 + 280) = 0;
  std::string::string(v38, "requestId");
  v8 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, v4, v38, 0);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  if ( !v8 )
  {
    v35 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServicePollResponse.h";
    v36 = 41;
    v10 = ((__int64 (__fastcall *)(_BYTE *, const char **, __int64, const char *))cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>)(
            v39,
            &v35,
            v9,
            "requestId");
    cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v35, v10);
  }
  std::string::string(v38, "requestStatus");
  v11 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, v5, v38, 0);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  if ( !v11 )
  {
    v35 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServicePollResponse.h";
    v36 = 42;
    v13 = ((__int64 (__fastcall *)(_BYTE *, const char **, __int64, const char *))cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>)(
            v39,
            &v35,
            v12,
            "requestStatus");
    cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v35, v13);
  }
  std::string::string(v38, "sourceUserDeviceThumbprint");
  v14 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, v6, v38, 0);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  if ( !v14 )
  {
    v35 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServicePollResponse.h";
    v36 = 43;
    v15 = cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[27]>(v39, &v35);
    cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v35, v15);
  }
  std::string::string(v38, "destinationUserDeviceThumbprint");
  v16 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, v7, v38, 0);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  if ( !v16 )
  {
    v35 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServicePollResponse.h";
    v36 = 44;
    v17 = cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[32]>(v39, &v35);
    cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v35, v17);
  }
  std::string::string(v38, "commandTypeId");
  v18 = cdp::Serializer<cdp::JsonData>::GetValue<unsigned char,unsigned char>(a2, a1 + 136, v38);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  if ( !v18 )
  {
    v35 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServicePollResponse.h";
    v36 = 45;
    v20 = ((__int64 (__fastcall *)(_BYTE *, const char **, __int64, const char *))cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>)(
            v39,
            &v35,
            v19,
            "commandTypeId");
    cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v35, v20);
  }
  std::string::string(v38, "commandTypeText");
  v21 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, a1 + 144, v38, 0);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  if ( !v21 )
  {
    v35 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServicePollResponse.h";
    v36 = 46;
    v23 = ((__int64 (__fastcall *)(_BYTE *, const char **, __int64, const char *))cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>)(
            v39,
            &v35,
            v22,
            "commandTypeText");
    cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v35, v23);
  }
  std::string::string(v38, "correlationVector");
  v24 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, a1 + 208, v38, 0);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  if ( !v24 )
  {
    v35 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServicePollResponse.h";
    v36 = 47;
    v26 = ((__int64 (__fastcall *)(_BYTE *, const char **, __int64, const char *))cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>)(
            v39,
            &v35,
            v25,
            "correlationVector");
    cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v35, v26);
  }
  std::string::string(v38, "correlationId");
  v27 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, a1 + 240, v38, 0);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  if ( !v27 )
  {
    v35 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServicePollResponse.h";
    v36 = 48;
    v29 = ((__int64 (__fastcall *)(_BYTE *, const char **, __int64, const char *))cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>)(
            v39,
            &v35,
            v28,
            "correlationId");
    cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v35, v29);
  }
  std::string::string(v38, "error");
  cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, a1 + 176, v38, 0);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  if ( v5[3] <= 0xFu )
    v30 = v5;
  else
    v30 = (_BYTE *)*v5;
  v31 = *(_QWORD **)std::string::end(v5, &v35);
  if ( v5[3] > 0xFu )
    v5 = (_QWORD *)*v5;
  while ( v5 != v31 )
  {
    *v30++ = _o_tolower((unsigned int)*(char *)v5);
    v5 = (_QWORD *)((char *)v5 + 1);
  }
  LODWORD(v35) = 0;
  std::string::string(v38, "fastPathSequenceNumber");
  v32 = cdp::Serializer<cdp::JsonData>::GetValue<unsigned int,unsigned int>(a2, &v35, v38, 0);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  if ( v32 )
  {
    v38[0] = 0;
    v38[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v38[0]) = 0;
    std::string::string(v39, "fastPathSessionId");
    v33 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, v38, v39, 0);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v39);
    if ( v33 )
    {
      *(_BYTE *)(a1 + 272) = 1;
      *(_DWORD *)(a1 + 276) = (_DWORD)v35;
      std::string::operator=(a1 + 280, v38);
    }
    else
    {
      if ( *((_QWORD *)v4 + 3) > 0xFu )
        v4 = *(const char **)v4;
      v35 = v4;
      Log<unsigned __int64 &>(
        2,
        "{\"text\":\"Ignoring sequencing for Request ID '%s' because fastPathSessionId is empty\"}",
        (const char *)&v35);
    }
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v38);
  }
  return a1;
}

```

## disassembly

```asm
0x1801d29a4  mov     [rsp-8+arg_10], rbx
0x1801d29a9  push    rbp
0x1801d29aa  push    rsi
0x1801d29ab  push    rdi
0x1801d29ac  push    r12
0x1801d29ae  push    r13
0x1801d29b0  push    r14
0x1801d29b2  push    r15
0x1801d29b4  lea     rbp, [rsp-27h]
0x1801d29b9  sub     rsp, 0A0h
0x1801d29c0  mov     rax, cs:__security_cookie
0x1801d29c7  xor     rax, rsp
0x1801d29ca  mov     [rbp+57h+var_38], rax
0x1801d29ce  mov     rsi, rdx
0x1801d29d1  mov     r12, rcx
0x1801d29d4  mov     [rbp+57h+var_A0], rcx
0x1801d29d8  lea     rax, ??_7CommandJsonPayload@CommandServicePollResponse@cdp@@6B@; const cdp::CommandServicePollResponse::CommandJsonPayload::`vftable'
0x1801d29df  mov     [rcx], rax
0x1801d29e2  lea     r15, [rcx+8]
0x1801d29e6  xorps   xmm0, xmm0
0x1801d29e9  movups  xmmword ptr [r15], xmm0
0x1801d29ed  xor     ecx, ecx
0x1801d29ef  mov     [r15+10h], rcx
0x1801d29f3  lea     edx, [rcx+0Fh]
0x1801d29f6  mov     [r15+18h], rdx
0x1801d29fa  mov     [r15], cl
0x1801d29fd  lea     rdi, [r12+28h]
0x1801d2a02  movups  xmmword ptr [rdi], xmm0
0x1801d2a05  mov     [rdi+10h], rcx
0x1801d2a09  mov     [rdi+18h], rdx
0x1801d2a0d  mov     [rdi], cl
0x1801d2a0f  lea     r14, [r12+48h]
0x1801d2a14  movups  xmmword ptr [r14], xmm0
0x1801d2a18  mov     [r14+10h], rcx
0x1801d2a1c  mov     [r14+18h], rdx
0x1801d2a20  mov     [r14], cl
0x1801d2a23  lea     r13, [r12+68h]
0x1801d2a28  movups  xmmword ptr [r13+0], xmm0
0x1801d2a2d  mov     [r13+10h], rcx
0x1801d2a31  mov     [r13+18h], rdx
0x1801d2a35  mov     [r13+0], cl
0x1801d2a39  mov     [r12+88h], cl
0x1801d2a41  lea     rax, [r12+90h]
0x1801d2a49  movups  xmmword ptr [rax], xmm0
0x1801d2a4c  mov     [rax+10h], rcx
0x1801d2a50  mov     [rax+18h], rdx
0x1801d2a54  mov     [rax], cl
0x1801d2a56  lea     rax, [r12+0B0h]
0x1801d2a5e  movups  xmmword ptr [rax], xmm0
0x1801d2a61  mov     [rax+10h], rcx
0x1801d2a65  mov     [rax+18h], rdx
0x1801d2a69  mov     [rax], cl
0x1801d2a6b  lea     rax, [r12+0D0h]
0x1801d2a73  movups  xmmword ptr [rax], xmm0
0x1801d2a76  mov     [rax+10h], rcx
0x1801d2a7a  mov     [rax+18h], rdx
0x1801d2a7e  mov     [rax], cl
0x1801d2a80  lea     rax, [r12+0F0h]
0x1801d2a88  movups  xmmword ptr [rax], xmm0
0x1801d2a8b  mov     [rax+10h], rcx
0x1801d2a8f  mov     [rax+18h], rdx
0x1801d2a93  mov     [rax], cl
0x1801d2a95  mov     [r12+110h], cl
0x1801d2a9d  mov     [r12+114h], ecx
0x1801d2aa5  lea     rax, [r12+118h]
0x1801d2aad  movups  xmmword ptr [rax], xmm0
0x1801d2ab0  mov     [rax+10h], rcx
0x1801d2ab4  mov     [rax+18h], rdx
0x1801d2ab8  mov     [rax], cl
0x1801d2aba  lea     rdx, aRequestid; "requestId"
0x1801d2ac1  lea     rcx, [rbp+57h+var_90]
0x1801d2ac5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2aca  nop
0x1801d2acb  xor     r9d, r9d
0x1801d2ace  lea     r8, [rbp+57h+var_90]
0x1801d2ad2  mov     rdx, r15
0x1801d2ad5  mov     rcx, rsi
0x1801d2ad8  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801d2add  mov     bl, al
0x1801d2adf  lea     rcx, [rbp+57h+var_90]; void *
0x1801d2ae3  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d2ae8  test    bl, bl
0x1801d2aea  jnz     short loc_1801D2B20
0x1801d2aec  lea     rax, aOnecoreuapWind_63; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801d2af3  mov     [rbp+57h+var_B0], rax
0x1801d2af7  mov     [rbp+57h+var_A8], 29h ; ')'
0x1801d2afe  lea     r9, aRequestid; "requestId"
0x1801d2b05  lea     rdx, [rbp+57h+var_B0]
0x1801d2b09  lea     rcx, [rbp+57h+var_70]
0x1801d2b0d  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801d2b12  nop
0x1801d2b13  mov     rdx, rax
0x1801d2b16  lea     rcx, [rbp+57h+var_B0]
0x1801d2b1a  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801d2b20  lea     rdx, aRequeststatus; "requestStatus"
0x1801d2b27  lea     rcx, [rbp+57h+var_90]
0x1801d2b2b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2b30  nop
0x1801d2b31  xor     r9d, r9d
0x1801d2b34  lea     r8, [rbp+57h+var_90]
0x1801d2b38  mov     rdx, rdi
0x1801d2b3b  mov     rcx, rsi
0x1801d2b3e  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801d2b43  mov     bl, al
0x1801d2b45  lea     rcx, [rbp+57h+var_90]; void *
0x1801d2b49  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d2b4e  test    bl, bl
0x1801d2b50  jnz     short loc_1801D2B86
0x1801d2b52  lea     rax, aOnecoreuapWind_63; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801d2b59  mov     [rbp+57h+var_B0], rax
0x1801d2b5d  mov     [rbp+57h+var_A8], 2Ah ; '*'
0x1801d2b64  lea     r9, aRequeststatus; "requestStatus"
0x1801d2b6b  lea     rdx, [rbp+57h+var_B0]
0x1801d2b6f  lea     rcx, [rbp+57h+var_70]
0x1801d2b73  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801d2b78  nop
0x1801d2b79  mov     rdx, rax
0x1801d2b7c  lea     rcx, [rbp+57h+var_B0]
0x1801d2b80  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801d2b86  lea     rdx, aSourceuserdevi; "sourceUserDeviceThumbprint"
0x1801d2b8d  lea     rcx, [rbp+57h+var_90]
0x1801d2b91  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2b96  nop
0x1801d2b97  xor     r9d, r9d
0x1801d2b9a  lea     r8, [rbp+57h+var_90]
0x1801d2b9e  mov     rdx, r14
0x1801d2ba1  mov     rcx, rsi
0x1801d2ba4  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801d2ba9  mov     bl, al
0x1801d2bab  lea     rcx, [rbp+57h+var_90]; void *
0x1801d2baf  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d2bb4  test    bl, bl
0x1801d2bb6  jnz     short loc_1801D2BE5
0x1801d2bb8  lea     rax, aOnecoreuapWind_63; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801d2bbf  mov     [rbp+57h+var_B0], rax
0x1801d2bc3  mov     [rbp+57h+var_A8], 2Bh ; '+'
0x1801d2bca  lea     rdx, [rbp+57h+var_B0]
0x1801d2bce  lea     rcx, [rbp+57h+var_70]
0x1801d2bd2  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BL@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BL@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[27]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[27])
0x1801d2bd7  nop
0x1801d2bd8  mov     rdx, rax
0x1801d2bdb  lea     rcx, [rbp+57h+var_B0]
0x1801d2bdf  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801d2be5  lea     rdx, aDestinationuse; "destinationUserDeviceThumbprint"
0x1801d2bec  lea     rcx, [rbp+57h+var_90]
0x1801d2bf0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2bf5  nop
0x1801d2bf6  xor     r9d, r9d
0x1801d2bf9  lea     r8, [rbp+57h+var_90]
0x1801d2bfd  mov     rdx, r13
0x1801d2c00  mov     rcx, rsi
0x1801d2c03  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801d2c08  mov     bl, al
0x1801d2c0a  lea     rcx, [rbp+57h+var_90]; void *
0x1801d2c0e  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d2c13  test    bl, bl
0x1801d2c15  jnz     short loc_1801D2C44
0x1801d2c17  lea     rax, aOnecoreuapWind_63; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801d2c1e  mov     [rbp+57h+var_B0], rax
0x1801d2c22  mov     [rbp+57h+var_A8], 2Ch ; ','
0x1801d2c29  lea     rdx, [rbp+57h+var_B0]
0x1801d2c2d  lea     rcx, [rbp+57h+var_70]
0x1801d2c31  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0CA@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0CA@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[32]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[32])
0x1801d2c36  nop
0x1801d2c37  mov     rdx, rax
0x1801d2c3a  lea     rcx, [rbp+57h+var_B0]
0x1801d2c3e  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801d2c44  lea     rdx, aCommandtypeid; "commandTypeId"
0x1801d2c4b  lea     rcx, [rbp+57h+var_90]
0x1801d2c4f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2c54  nop
0x1801d2c55  lea     r8, [rbp+57h+var_90]
0x1801d2c59  lea     rdx, [r12+88h]
0x1801d2c61  mov     rcx, rsi
0x1801d2c64  call    ??$GetValue@EE@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAEAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<uchar,uchar>(uchar &,std::string const &,bool)
0x1801d2c69  mov     bl, al
0x1801d2c6b  lea     rcx, [rbp+57h+var_90]; void *
0x1801d2c6f  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d2c74  test    bl, bl
0x1801d2c76  jnz     short loc_1801D2CAC
0x1801d2c78  lea     rax, aOnecoreuapWind_63; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801d2c7f  mov     [rbp+57h+var_B0], rax
0x1801d2c83  mov     [rbp+57h+var_A8], 2Dh ; '-'
0x1801d2c8a  lea     r9, aCommandtypeid; "commandTypeId"
0x1801d2c91  lea     rdx, [rbp+57h+var_B0]
0x1801d2c95  lea     rcx, [rbp+57h+var_70]
0x1801d2c99  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801d2c9e  nop
0x1801d2c9f  mov     rdx, rax
0x1801d2ca2  lea     rcx, [rbp+57h+var_B0]
0x1801d2ca6  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801d2cac  lea     rdx, aCommandtypetex; "commandTypeText"
0x1801d2cb3  lea     rcx, [rbp+57h+var_90]
0x1801d2cb7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2cbc  nop
0x1801d2cbd  xor     r9d, r9d
0x1801d2cc0  lea     r8, [rbp+57h+var_90]
0x1801d2cc4  lea     rdx, [r12+90h]
0x1801d2ccc  mov     rcx, rsi
0x1801d2ccf  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801d2cd4  mov     bl, al
0x1801d2cd6  lea     rcx, [rbp+57h+var_90]; void *
0x1801d2cda  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d2cdf  test    bl, bl
0x1801d2ce1  jnz     short loc_1801D2D17
0x1801d2ce3  lea     rax, aOnecoreuapWind_63; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801d2cea  mov     [rbp+57h+var_B0], rax
0x1801d2cee  mov     [rbp+57h+var_A8], 2Eh ; '.'
0x1801d2cf5  lea     r9, aCommandtypetex; "commandTypeText"
0x1801d2cfc  lea     rdx, [rbp+57h+var_B0]
0x1801d2d00  lea     rcx, [rbp+57h+var_70]
0x1801d2d04  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801d2d09  nop
0x1801d2d0a  mov     rdx, rax
0x1801d2d0d  lea     rcx, [rbp+57h+var_B0]
0x1801d2d11  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801d2d17  lea     rdx, aCorrelationvec; "correlationVector"
0x1801d2d1e  lea     rcx, [rbp+57h+var_90]
0x1801d2d22  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2d27  nop
0x1801d2d28  xor     r9d, r9d
0x1801d2d2b  lea     r8, [rbp+57h+var_90]
0x1801d2d2f  lea     rdx, [r12+0D0h]
0x1801d2d37  mov     rcx, rsi
0x1801d2d3a  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801d2d3f  mov     bl, al
0x1801d2d41  lea     rcx, [rbp+57h+var_90]; void *
0x1801d2d45  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d2d4a  test    bl, bl
0x1801d2d4c  jnz     short loc_1801D2D82
0x1801d2d4e  lea     rax, aOnecoreuapWind_63; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801d2d55  mov     [rbp+57h+var_B0], rax
0x1801d2d59  mov     [rbp+57h+var_A8], 2Fh ; '/'
0x1801d2d60  lea     r9, aCorrelationvec; "correlationVector"
0x1801d2d67  lea     rdx, [rbp+57h+var_B0]
0x1801d2d6b  lea     rcx, [rbp+57h+var_70]
0x1801d2d6f  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801d2d74  nop
0x1801d2d75  mov     rdx, rax
0x1801d2d78  lea     rcx, [rbp+57h+var_B0]
0x1801d2d7c  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801d2d82  lea     rdx, aCorrelationid; "correlationId"
0x1801d2d89  lea     rcx, [rbp+57h+var_90]
0x1801d2d8d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2d92  nop
0x1801d2d93  xor     r9d, r9d
0x1801d2d96  lea     r8, [rbp+57h+var_90]
0x1801d2d9a  lea     rdx, [r12+0F0h]
0x1801d2da2  mov     rcx, rsi
0x1801d2da5  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801d2daa  mov     bl, al
0x1801d2dac  lea     rcx, [rbp+57h+var_90]; void *
0x1801d2db0  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d2db5  test    bl, bl
0x1801d2db7  jnz     short loc_1801D2DED
0x1801d2db9  lea     rax, aOnecoreuapWind_63; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801d2dc0  mov     [rbp+57h+var_B0], rax
0x1801d2dc4  mov     [rbp+57h+var_A8], 30h ; '0'
0x1801d2dcb  lea     r9, aCorrelationid; "correlationId"
0x1801d2dd2  lea     rdx, [rbp+57h+var_B0]
0x1801d2dd6  lea     rcx, [rbp+57h+var_70]
0x1801d2dda  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801d2ddf  nop
0x1801d2de0  mov     rdx, rax
0x1801d2de3  lea     rcx, [rbp+57h+var_B0]
0x1801d2de7  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801d2ded  lea     rdx, aError_0; "error"
0x1801d2df4  lea     rcx, [rbp+57h+var_90]
0x1801d2df8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2dfd  nop
0x1801d2dfe  xor     r9d, r9d
0x1801d2e01  lea     r8, [rbp+57h+var_90]
0x1801d2e05  lea     rdx, [r12+0B0h]
0x1801d2e0d  mov     rcx, rsi
0x1801d2e10  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801d2e15  nop
0x1801d2e16  lea     rcx, [rbp+57h+var_90]; void *
0x1801d2e1a  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d2e1f  cmp     qword ptr [rdi+18h], 0Fh
0x1801d2e24  jbe     short loc_1801D2E2B
0x1801d2e26  mov     r14, [rdi]
0x1801d2e29  jmp     short loc_1801D2E2E
0x1801d2e2b  mov     r14, rdi
0x1801d2e2e  lea     rdx, [rbp+57h+var_B0]
0x1801d2e32  mov     rcx, rdi
0x1801d2e35  call    ?end@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@2@XZ; std::string::end(void)
0x1801d2e3a  mov     rbx, [rax]
0x1801d2e3d  cmp     qword ptr [rdi+18h], 0Fh
0x1801d2e42  jbe     short loc_1801D2E5B
0x1801d2e44  mov     rdi, [rdi]
0x1801d2e47  jmp     short loc_1801D2E5B
0x1801d2e49  movsx   ecx, byte ptr [rdi]
0x1801d2e4c  call    cs:__imp__o_tolower
0x1801d2e52  mov     [r14], al
0x1801d2e55  inc     r14
0x1801d2e58  inc     rdi
0x1801d2e5b  cmp     rdi, rbx
0x1801d2e5e  jnz     short loc_1801D2E49
0x1801d2e60  mov     dword ptr [rbp+57h+var_B0], 0
0x1801d2e67  lea     rdx, aFastpathsequen_1; "fastPathSequenceNumber"
  ... truncated ...
```

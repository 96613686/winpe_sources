# cdp::CommandServiceCloudNotificationJsonPayload::CommandServiceCloudNotificationJsonPayload(cdp::Serializer<cdp::JsonData> const &)

- ea: `0x1801dde44`
- end: `0x1801de278`
- name: `??$?0UJsonData@cdp@@@CommandServiceCloudNotificationJsonPayload@cdp@@QEAA@AEBV?$Serializer@UJsonData@cdp@@@1@@Z`
- size: `1076`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180281738`

## callees

- `0x180010ee0`
- `0x180030190`
- `0x1800482a0`
- `0x180083c74`
- `0x1800c1fec`
- `0x1800d8524`
- `0x1800dd0f4`
- `0x18011db1c`
- `0x1801dde44`
- `0x1801f6fb0`
- `0x1802126a8`
- `0x18027e5f0`
- `0x18027e9fc`
- `0x180280acc`
- `0x180283518`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1801de23b`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1801de23b`

## string_xrefs

- `0x1801de1b1`: `commandTypeId`
- `0x1801de09d`: `fastPathDelivery`
- `0x1801de037`: `commandLocation`
- `0x1801de07b`: `commandLocation`
- `0x1801ddfc6`: `commands`
- `0x1801de008`: `commands`
- `0x1801ddf4f`: `commandsWithheld`
- `0x1801ddf94`: `commandsWithheld`
- `0x1801ddf17`: `onecoreuap\windows\cdp\core\private\CommandServiceCloudNotificationJsonPayload.h`
- `0x1801ddf82`: `onecoreuap\windows\cdp\core\private\CommandServiceCloudNotificationJsonPayload.h`
- `0x1801ddff6`: `onecoreuap\windows\cdp\core\private\CommandServiceCloudNotificationJsonPayload.h`
- `0x1801de069`: `onecoreuap\windows\cdp\core\private\CommandServiceCloudNotificationJsonPayload.h`
- `0x1801de117`: `onecoreuap\windows\cdp\core\private\CommandServiceCloudNotificationJsonPayload.h`
- `0x1801de17d`: `onecoreuap\windows\cdp\core\private\CommandServiceCloudNotificationJsonPayload.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall cdp::CommandServiceCloudNotificationJsonPayload::CommandServiceCloudNotificationJsonPayload(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r15
  _QWORD *v5; // rdi
  __int64 v6; // r12
  char v7; // bl
  __int64 v8; // rax
  char v9; // bl
  __int64 v10; // r8
  __int64 v11; // rax
  char v12; // bl
  __int64 v13; // r8
  __int64 v14; // rax
  char v15; // bl
  __int64 v16; // r8
  __int64 v17; // rax
  char v18; // bl
  __int64 v19; // r8
  __int64 v20; // rax
  char v21; // bl
  __int64 v22; // r8
  __int64 v23; // rax
  _BYTE *v24; // rsi
  _QWORD *v25; // rbx
  __int64 v27; // [rsp+20h] [rbp-89h] BYREF
  int v28; // [rsp+28h] [rbp-81h]
  _BYTE v29[56]; // [rsp+30h] [rbp-79h] BYREF
  const char *v30; // [rsp+68h] [rbp-41h] BYREF
  int v31; // [rsp+70h] [rbp-39h]
  __int128 v32; // [rsp+88h] [rbp-21h] BYREF
  __int64 v33; // [rsp+98h] [rbp-11h]

  v27 = a1;
  *(_BYTE *)(a1 + 1) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = a1 + 32;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 15;
  *(_BYTE *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 15;
  *(_BYTE *)(a1 + 64) = 0;
  v5 = (_QWORD *)(a1 + 96);
  *(_OWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 15;
  *(_BYTE *)(a1 + 96) = 0;
  *(_WORD *)(a1 + 128) = 0;
  v6 = a1 + 136;
  *(_OWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 15;
  *(_BYTE *)(a1 + 136) = 0;
  std::string::string(&v32, "notificationTypeId");
  v7 = cdp::Serializer<cdp::JsonData>::GetValue<enum cdp::CommandServiceCloudNotificationType,enum cdp::CommandServiceCloudNotificationType>(
         a2,
         a1,
         &v32);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v32);
  if ( !v7 )
  {
    v30 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServiceCloudNotificationJsonPayload.h";
    v31 = 30;
    v8 = cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[19]>(&v32, &v30);
    cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v30, v8);
  }
  if ( *(_BYTE *)a1 )
  {
    if ( *(_BYTE *)a1 == 1 )
    {
      std::string::string(&v32, "requestId");
      v18 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, v4, &v32, 0);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v32);
      if ( !v18 )
      {
        v30 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServiceCloudNotificationJsonPayload.h";
        v31 = 47;
        v20 = cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(
                v29,
                &v30,
                v19,
                "requestId",
                v27,
                v28);
        cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v30, v20);
      }
      std::string::string(&v32, "requestStatus");
      v21 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, v5, &v32, 0);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v32);
      if ( !v21 )
      {
        v30 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServiceCloudNotificationJsonPayload.h";
        v31 = 48;
        v23 = cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(
                v29,
                &v30,
                v22,
                "requestStatus",
                v27,
                v28);
        cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v30, v23);
      }
      std::string::string(&v32, "commandTypeId");
      cdp::Serializer<cdp::JsonData>::GetValue<unsigned char,unsigned char>(a2, a1 + 128, &v32);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v32);
      std::string::string(&v32, "correlationVector");
      cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, a1 + 64, &v32, 0);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v32);
      if ( v5[3] <= 0xFu )
        v24 = v5;
      else
        v24 = (_BYTE *)*v5;
      v25 = *(_QWORD **)std::string::end(v5, &v27);
      if ( v5[3] > 0xFu )
        v5 = (_QWORD *)*v5;
      while ( v5 != v25 )
      {
        *v24++ = _o_tolower((unsigned int)*(char *)v5);
        v5 = (_QWORD *)((char *)v5 + 1);
      }
    }
  }
  else
  {
    std::string::string(&v32, "commandsWithheld");
    v9 = cdp::Serializer<cdp::JsonData>::GetValue<bool,bool>(a2, a1 + 1, &v32, 0);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v32);
    if ( !v9 )
    {
      v30 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServiceCloudNotificationJsonPayload.h";
      v31 = 34;
      v11 = cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(
              &v32,
              &v30,
              v10,
              "commandsWithheld",
              v27,
              v28);
      cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v30, v11);
    }
    v32 = 0;
    v33 = 0;
    std::string::string(&v30, "commands");
    v12 = cdp::Serializer<cdp::JsonData>::GetValue<cdp::CommandServiceCloudNotificationJsonPayload::CommandArrayJsonPayload,cdp::CommandServiceCloudNotificationJsonPayload::CommandArrayJsonPayload>(
            a2,
            &v32,
            &v30);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v30);
    if ( !v12 )
    {
      v30 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServiceCloudNotificationJsonPayload.h";
      v31 = 37;
      v14 = cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(
              v29,
              &v30,
              v13,
              "commands",
              v27,
              v28);
      cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v30, v14);
    }
    std::vector<cdp::CommandServiceCloudNotificationJsonPayload::CommandJsonPayload>::operator=(a1 + 8, &v32);
    std::string::string(&v30, "commandLocation");
    v15 = cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(a2, v6, &v30, 0);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v30);
    if ( !v15 )
    {
      v30 = "onecoreuap\\windows\\cdp\\core\\private\\CommandServiceCloudNotificationJsonPayload.h";
      v31 = 41;
      v17 = cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(
              v29,
              &v30,
              v16,
              "commandLocation",
              v27,
              v28);
      cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v30, v17);
    }
    std::string::string(&v30, "fastPathDelivery");
    cdp::Serializer<cdp::JsonData>::GetValue<bool,bool>(a2, a1 + 129, &v30, 0);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v30);
    std::vector<cdp::CommandServiceCloudNotificationJsonPayload::CommandJsonPayload>::_Tidy(&v32);
  }
  return a1;
}

```

## disassembly

```asm
0x1801dde44  mov     [rsp-8+arg_10], rbx
0x1801dde49  push    rbp
0x1801dde4a  push    rsi
0x1801dde4b  push    rdi
0x1801dde4c  push    r12
0x1801dde4e  push    r13
0x1801dde50  push    r14
0x1801dde52  push    r15
0x1801dde54  lea     rbp, [rsp-27h]
0x1801dde59  sub     rsp, 0D0h
0x1801dde60  mov     rax, cs:__security_cookie
0x1801dde67  xor     rax, rsp
0x1801dde6a  mov     [rbp+57h+var_40], rax
0x1801dde6e  mov     rsi, rdx
0x1801dde71  mov     r14, rcx
0x1801dde74  mov     [rsp+100h+var_E0], rcx
0x1801dde79  xor     ecx, ecx
0x1801dde7b  mov     [r14+1], cl
0x1801dde7f  mov     [r14+8], rcx
0x1801dde83  mov     [r14+10h], rcx
0x1801dde87  mov     [r14+18h], rcx
0x1801dde8b  lea     r15, [r14+20h]
0x1801dde8f  xorps   xmm0, xmm0
0x1801dde92  movups  xmmword ptr [r15], xmm0
0x1801dde96  mov     [r15+10h], rcx
0x1801dde9a  lea     edx, [rcx+0Fh]
0x1801dde9d  mov     [r15+18h], rdx
0x1801ddea1  mov     [r15], cl
0x1801ddea4  movups  xmmword ptr [r14+40h], xmm0
0x1801ddea9  mov     [r14+50h], rcx
0x1801ddead  mov     [r14+58h], rdx
0x1801ddeb1  mov     [r14+40h], cl
0x1801ddeb5  lea     rdi, [r14+60h]
0x1801ddeb9  movups  xmmword ptr [rdi], xmm0
0x1801ddebc  mov     [rdi+10h], rcx
0x1801ddec0  mov     [rdi+18h], rdx
0x1801ddec4  mov     [rdi], cl
0x1801ddec6  mov     [r14+80h], cx
0x1801ddece  lea     r12, [r14+88h]
0x1801dded5  movups  xmmword ptr [r12], xmm0
0x1801ddeda  mov     [r12+10h], rcx
0x1801ddedf  mov     [r12+18h], rdx
0x1801ddee4  mov     [r12], cl
0x1801ddee8  lea     rdx, aNotificationty; "notificationTypeId"
0x1801ddeef  lea     rcx, [rbp+57h+var_78]
0x1801ddef3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801ddef8  nop
0x1801ddef9  lea     r8, [rbp+57h+var_78]
0x1801ddefd  mov     rdx, r14
0x1801ddf00  mov     rcx, rsi
0x1801ddf03  call    ??$GetValue@W4CommandServiceCloudNotificationType@cdp@@W412@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAW4CommandServiceCloudNotificationType@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<cdp::CommandServiceCloudNotificationType,cdp::CommandServiceCloudNotificationType>(cdp::CommandServiceCloudNotificationType &,std::string const &,bool)
0x1801ddf08  mov     bl, al
0x1801ddf0a  lea     rcx, [rbp+57h+var_78]; void *
0x1801ddf0e  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801ddf13  test    bl, bl
0x1801ddf15  jnz     short loc_1801DDF44
0x1801ddf17  lea     rax, aOnecoreuapWind_42; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801ddf1e  mov     [rbp+57h+var_98], rax
0x1801ddf22  mov     [rbp+57h+var_90], 1Eh
0x1801ddf29  lea     rdx, [rbp+57h+var_98]
0x1801ddf2d  lea     rcx, [rbp+57h+var_78]
0x1801ddf31  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BD@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BD@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[19]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[19])
0x1801ddf36  nop
0x1801ddf37  mov     rdx, rax
0x1801ddf3a  lea     rcx, [rbp+57h+var_98]
0x1801ddf3e  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801ddf44  mov     al, [r14]
0x1801ddf47  test    al, al
0x1801ddf49  jnz     loc_1801DE0DD
0x1801ddf4f  lea     rdx, aCommandswithhe; "commandsWithheld"
0x1801ddf56  lea     rcx, [rbp+57h+var_78]
0x1801ddf5a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801ddf5f  nop
0x1801ddf60  xor     r9d, r9d
0x1801ddf63  lea     r8, [rbp+57h+var_78]
0x1801ddf67  lea     rdx, [r14+1]
0x1801ddf6b  mov     rcx, rsi
0x1801ddf6e  call    ??$GetValue@_N_N@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<bool,bool>(bool &,std::string const &,bool)
0x1801ddf73  mov     bl, al
0x1801ddf75  lea     rcx, [rbp+57h+var_78]; void *
0x1801ddf79  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801ddf7e  test    bl, bl
0x1801ddf80  jnz     short loc_1801DDFB6
0x1801ddf82  lea     rax, aOnecoreuapWind_42; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801ddf89  mov     [rbp+57h+var_98], rax
0x1801ddf8d  mov     [rbp+57h+var_90], 22h ; '"'
0x1801ddf94  lea     r9, aCommandswithhe; "commandsWithheld"
0x1801ddf9b  lea     rdx, [rbp+57h+var_98]
0x1801ddf9f  lea     rcx, [rbp+57h+var_78]
0x1801ddfa3  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801ddfa8  nop
0x1801ddfa9  mov     rdx, rax
0x1801ddfac  lea     rcx, [rbp+57h+var_98]
0x1801ddfb0  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801ddfb6  xorps   xmm0, xmm0
0x1801ddfb9  movdqu  [rbp+57h+var_78], xmm0
0x1801ddfbe  mov     [rbp+57h+var_68], 0
0x1801ddfc6  lea     rdx, aCommands_0; "commands"
0x1801ddfcd  lea     rcx, [rbp+57h+var_98]
0x1801ddfd1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801ddfd6  nop
0x1801ddfd7  lea     r8, [rbp+57h+var_98]
0x1801ddfdb  lea     rdx, [rbp+57h+var_78]
0x1801ddfdf  mov     rcx, rsi
0x1801ddfe2  call    ??$GetValue@VCommandArrayJsonPayload@CommandServiceCloudNotificationJsonPayload@cdp@@V123@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAVCommandArrayJsonPayload@CommandServiceCloudNotificationJsonPayload@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<cdp::CommandServiceCloudNotificationJsonPayload::CommandArrayJsonPayload,cdp::CommandServiceCloudNotificationJsonPayload::CommandArrayJsonPayload>(cdp::CommandServiceCloudNotificationJsonPayload::CommandArrayJsonPayload &,std::string const &,bool)
0x1801ddfe7  mov     bl, al
0x1801ddfe9  lea     rcx, [rbp+57h+var_98]; void *
0x1801ddfed  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801ddff2  test    bl, bl
0x1801ddff4  jnz     short loc_1801DE02A
0x1801ddff6  lea     rax, aOnecoreuapWind_42; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801ddffd  mov     [rbp+57h+var_98], rax
0x1801de001  mov     [rbp+57h+var_90], 25h ; '%'
0x1801de008  lea     r9, aCommands_0; "commands"
0x1801de00f  lea     rdx, [rbp+57h+var_98]
0x1801de013  lea     rcx, [rbp+57h+var_D0]
0x1801de017  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801de01c  nop
0x1801de01d  mov     rdx, rax
0x1801de020  lea     rcx, [rbp+57h+var_98]
0x1801de024  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801de02a  lea     rdx, [rbp+57h+var_78]
0x1801de02e  lea     rcx, [r14+8]
0x1801de032  call    ??4?$vector@VCommandJsonPayload@CommandServiceCloudNotificationJsonPayload@cdp@@V?$allocator@VCommandJsonPayload@CommandServiceCloudNotificationJsonPayload@cdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<cdp::CommandServiceCloudNotificationJsonPayload::CommandJsonPayload>::operator=(std::vector<cdp::CommandServiceCloudNotificationJsonPayload::CommandJsonPayload> &&)
0x1801de037  lea     rdx, aCommandlocatio; "commandLocation"
0x1801de03e  lea     rcx, [rbp+57h+var_98]
0x1801de042  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801de047  nop
0x1801de048  xor     r9d, r9d
0x1801de04b  lea     r8, [rbp+57h+var_98]
0x1801de04f  mov     rdx, r12
0x1801de052  mov     rcx, rsi
0x1801de055  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801de05a  mov     bl, al
0x1801de05c  lea     rcx, [rbp+57h+var_98]; void *
0x1801de060  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801de065  test    bl, bl
0x1801de067  jnz     short loc_1801DE09D
0x1801de069  lea     rax, aOnecoreuapWind_42; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801de070  mov     [rbp+57h+var_98], rax
0x1801de074  mov     [rbp+57h+var_90], 29h ; ')'
0x1801de07b  lea     r9, aCommandlocatio; "commandLocation"
0x1801de082  lea     rdx, [rbp+57h+var_98]
0x1801de086  lea     rcx, [rbp+57h+var_D0]
0x1801de08a  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801de08f  nop
0x1801de090  mov     rdx, rax
0x1801de093  lea     rcx, [rbp+57h+var_98]
0x1801de097  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801de09d  lea     rdx, aFastpathdelive; "fastPathDelivery"
0x1801de0a4  lea     rcx, [rbp+57h+var_98]
0x1801de0a8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801de0ad  nop
0x1801de0ae  xor     r9d, r9d
0x1801de0b1  lea     r8, [rbp+57h+var_98]
0x1801de0b5  lea     rdx, [r14+81h]
0x1801de0bc  mov     rcx, rsi
0x1801de0bf  call    ??$GetValue@_N_N@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<bool,bool>(bool &,std::string const &,bool)
0x1801de0c4  nop
0x1801de0c5  lea     rcx, [rbp+57h+var_98]; void *
0x1801de0c9  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801de0ce  nop
0x1801de0cf  lea     rcx, [rbp+57h+var_78]
0x1801de0d3  call    ?_Tidy@?$vector@VCommandJsonPayload@CommandServiceCloudNotificationJsonPayload@cdp@@V?$allocator@VCommandJsonPayload@CommandServiceCloudNotificationJsonPayload@cdp@@@std@@@std@@AEAAXXZ; std::vector<cdp::CommandServiceCloudNotificationJsonPayload::CommandJsonPayload>::_Tidy(void)
0x1801de0d8  jmp     loc_1801DE24E
0x1801de0dd  cmp     al, 1
0x1801de0df  jnz     loc_1801DE24E
0x1801de0e5  lea     rdx, aRequestid; "requestId"
0x1801de0ec  lea     rcx, [rbp+57h+var_78]
0x1801de0f0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801de0f5  nop
0x1801de0f6  xor     r9d, r9d
0x1801de0f9  lea     r8, [rbp+57h+var_78]
0x1801de0fd  mov     rdx, r15
0x1801de100  mov     rcx, rsi
0x1801de103  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801de108  mov     bl, al
0x1801de10a  lea     rcx, [rbp+57h+var_78]; void *
0x1801de10e  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801de113  test    bl, bl
0x1801de115  jnz     short loc_1801DE14B
0x1801de117  lea     rax, aOnecoreuapWind_42; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801de11e  mov     [rbp+57h+var_98], rax
0x1801de122  mov     [rbp+57h+var_90], 2Fh ; '/'
0x1801de129  lea     r9, aRequestid; "requestId"
0x1801de130  lea     rdx, [rbp+57h+var_98]
0x1801de134  lea     rcx, [rbp+57h+var_D0]
0x1801de138  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801de13d  nop
0x1801de13e  mov     rdx, rax
0x1801de141  lea     rcx, [rbp+57h+var_98]
0x1801de145  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801de14b  lea     rdx, aRequeststatus; "requestStatus"
0x1801de152  lea     rcx, [rbp+57h+var_78]
0x1801de156  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801de15b  nop
0x1801de15c  xor     r9d, r9d
0x1801de15f  lea     r8, [rbp+57h+var_78]
0x1801de163  mov     rdx, rdi
0x1801de166  mov     rcx, rsi
0x1801de169  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801de16e  mov     bl, al
0x1801de170  lea     rcx, [rbp+57h+var_78]; void *
0x1801de174  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801de179  test    bl, bl
0x1801de17b  jnz     short loc_1801DE1B1
0x1801de17d  lea     rax, aOnecoreuapWind_42; "onecoreuap\\windows\\cdp\\core\\private"...
0x1801de184  mov     [rbp+57h+var_98], rax
0x1801de188  mov     [rbp+57h+var_90], 30h ; '0'
0x1801de18f  lea     r9, aRequeststatus; "requestStatus"
0x1801de196  lea     rdx, [rbp+57h+var_98]
0x1801de19a  lea     rcx, [rbp+57h+var_D0]
0x1801de19e  call    ??$MakeException@V?$HResultException@$0?HPPLPOPO@@cdp@@AEAY0BC@$$CBD@cdp@@YA?AV?$HResultException@$0?HPPLPOPO@@0@AEBUCDPSourceLocationInfo@0@PEBDAEAY0BC@$$CBD@Z; cdp::MakeException<cdp::HResultException<-2147221246>,char const (&)[18]>(cdp::CDPSourceLocationInfo const &,char const *,char const (&)[18])
0x1801de1a3  nop
0x1801de1a4  mov     rdx, rax
0x1801de1a7  lea     rcx, [rbp+57h+var_98]
0x1801de1ab  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221246>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221246> &&)
0x1801de1b1  lea     rdx, aCommandtypeid; "commandTypeId"
0x1801de1b8  lea     rcx, [rbp+57h+var_78]
0x1801de1bc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801de1c1  nop
0x1801de1c2  lea     r8, [rbp+57h+var_78]
0x1801de1c6  lea     rdx, [r14+80h]
0x1801de1cd  mov     rcx, rsi
0x1801de1d0  call    ??$GetValue@EE@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAEAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<uchar,uchar>(uchar &,std::string const &,bool)
0x1801de1d5  nop
0x1801de1d6  lea     rcx, [rbp+57h+var_78]; void *
0x1801de1da  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801de1df  lea     rdx, aCorrelationvec; "correlationVector"
0x1801de1e6  lea     rcx, [rbp+57h+var_78]
0x1801de1ea  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801de1ef  nop
0x1801de1f0  xor     r9d, r9d
0x1801de1f3  lea     r8, [rbp+57h+var_78]
0x1801de1f7  lea     rdx, [r14+40h]
0x1801de1fb  mov     rcx, rsi
0x1801de1fe  call    ??$GetValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@_N@Z; cdp::Serializer<cdp::JsonData>::GetValue<std::string,std::string>(std::string &,std::string const &,bool)
0x1801de203  nop
0x1801de204  lea     rcx, [rbp+57h+var_78]; void *
0x1801de208  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801de20d  cmp     qword ptr [rdi+18h], 0Fh
0x1801de212  jbe     short loc_1801DE219
0x1801de214  mov     rsi, [rdi]
0x1801de217  jmp     short loc_1801DE21C
0x1801de219  mov     rsi, rdi
0x1801de21c  lea     rdx, [rsp+100h+var_E0]
0x1801de221  mov     rcx, rdi
0x1801de224  call    ?end@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@2@XZ; std::string::end(void)
0x1801de229  mov     rbx, [rax]
0x1801de22c  cmp     qword ptr [rdi+18h], 0Fh
0x1801de231  jbe     short loc_1801DE249
0x1801de233  mov     rdi, [rdi]
0x1801de236  jmp     short loc_1801DE249
0x1801de238  movsx   ecx, byte ptr [rdi]
0x1801de23b  call    cs:__imp__o_tolower
0x1801de241  mov     [rsi], al
0x1801de243  inc     rsi
0x1801de246  inc     rdi
0x1801de249  cmp     rdi, rbx
0x1801de24c  jnz     short loc_1801DE238
0x1801de24e  mov     rax, r14
0x1801de251  mov     rcx, [rbp+57h+var_40]
0x1801de255  xor     rcx, rsp; StackCookie
0x1801de258  call    __security_check_cookie
0x1801de25d  mov     rbx, [rsp+100h+arg_10]
0x1801de265  add     rsp, 0D0h
0x1801de26c  pop     r15
0x1801de26e  pop     r14
0x1801de270  pop     r13
0x1801de272  pop     r12
0x1801de274  pop     rdi
0x1801de275  pop     rsi
0x1801de276  pop     rbp
0x1801de277  retn
```

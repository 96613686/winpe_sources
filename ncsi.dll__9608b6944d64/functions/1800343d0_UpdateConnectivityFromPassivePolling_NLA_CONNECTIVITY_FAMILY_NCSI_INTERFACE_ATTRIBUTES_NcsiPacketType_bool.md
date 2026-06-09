# UpdateConnectivityFromPassivePolling(_NLA_CONNECTIVITY_FAMILY,NCSI_INTERFACE_ATTRIBUTES *,NcsiPacketType,bool &)

- ea: `0x1800343d0`
- end: `0x1800347be`
- name: `?UpdateConnectivityFromPassivePolling@@YAXW4_NLA_CONNECTIVITY_FAMILY@@PEAVNCSI_INTERFACE_ATTRIBUTES@@W4NcsiPacketType@@AEA_N@Z`
- size: `1006`
- prototype: `void __high(enum _NLA_CONNECTIVITY_FAMILY, struct NCSI_INTERFACE_ATTRIBUTES *, enum NcsiPacketType, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x180010230`

## callees

- `0x18000d188`
- `0x18000d3d0`
- `0x18001f66c`
- `0x1800299cc`
- `0x180031510`
- `0x180032474`
- `0x1800343d0`
- `0x18003ee84`
- `0x180042a38`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180034779`
- `ntdll!EtwEventWriteTransfer` at `0x180034779`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800345d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800345f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800345d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800345f5`

## string_xrefs

- `0x18003446f`: `Abandoning UpdateConnectivityFromPassivePolling in standby`
- `0x18003447b`: `UpdateConnectivityFromPassivePolling - Exiting`
- `0x18003450d`: `UpdateConnectivityFromPassivePolling - Exiting`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UpdateConnectivityFromPassivePolling(unsigned int a1, _BYTE *a2, int a3, _BYTE *a4)
{
  int v7; // esi
  _BYTE *v8; // r15
  Ncsi::Power *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  char v16; // al
  const char *v17; // rdi
  const char *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  const char *v21; // [rsp+40h] [rbp-C0h] BYREF
  const char *v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  BOOL v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v27[4]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-50h] BYREF
  char *v29; // [rsp+C0h] [rbp-40h] BYREF
  int v30; // [rsp+C8h] [rbp-38h]
  int v31; // [rsp+CCh] [rbp-34h]
  __int16 *v32; // [rsp+D0h] [rbp-30h]
  int v33; // [rsp+D8h] [rbp-28h]
  int v34; // [rsp+DCh] [rbp-24h]
  __int64 *v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+E8h] [rbp-18h]
  const char *v37; // [rsp+F0h] [rbp-10h]
  int v38; // [rsp+F8h] [rbp-8h]
  int v39; // [rsp+FCh] [rbp-4h]
  const char **v40; // [rsp+100h] [rbp+0h]
  __int64 v41; // [rsp+108h] [rbp+8h]
  const char **v42; // [rsp+110h] [rbp+10h]
  __int64 v43; // [rsp+118h] [rbp+18h]
  BOOL *v44; // [rsp+120h] [rbp+20h]
  __int64 v45; // [rsp+128h] [rbp+28h]
  __int64 *v46; // [rsp+130h] [rbp+30h]
  __int64 v47; // [rsp+138h] [rbp+38h]
  const char *v48; // [rsp+140h] [rbp+40h]
  int v49; // [rsp+148h] [rbp+48h]
  int v50; // [rsp+14Ch] [rbp+4Ch]

  if ( a3 )
    v7 = (unsigned int)(a3 - 1) < 2;
  else
    v7 = 2;
  v8 = &a2[3944 * a1];
  if ( !*((_DWORD *)v8 + 1106) && NCSI_INTERFACE_ATTRIBUTES::CanPerformGatewayArpProbe((NCSI_INTERFACE_ATTRIBUTES *)a2) )
  {
    if ( Ncsi::Power::IsSystemInStandby(v9) )
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        v23 = *(_QWORD *)a2;
        v22 = "Abandoning UpdateConnectivityFromPassivePolling in standby";
        v21 = "UpdateConnectivityFromPassivePolling - Exiting";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v10,
          (unsigned __int8 *)&unk_180088AC8,
          v11,
          v12,
          (const unsigned __int16 **)&v21,
          (const unsigned __int16 **)&v22,
          (__int64)&v23);
      }
      return;
    }
    memset(v27, 0, sizeof(v27));
    Ncsi::Power::ReferenceAllNetworkInterfaces(v27, 9, 60000);
    if ( !Ncsi::Power::AutoPdcNetworkRef::ActivationAcquired((Ncsi::Power::AutoPdcNetworkRef *)v27) )
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        v23 = *(_QWORD *)a2;
        v22 = "Cannot acquire PDC ref";
        v21 = "UpdateConnectivityFromPassivePolling - Exiting";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v13,
          (unsigned __int8 *)byte_1800889ED,
          v14,
          v15,
          (const unsigned __int16 **)&v21,
          (const unsigned __int16 **)&v22,
          (__int64)&v23);
      }
      goto LABEL_13;
    }
    v28 = *(_OWORD *)(a2 + 8);
    if ( (unsigned int)NcsiPerformArpProbe(&v28, *(_QWORD *)a2, a1) )
    {
LABEL_13:
      Ncsi::Power::AutoPdcNetworkRef::~AutoPdcNetworkRef((Ncsi::Power::AutoPdcNetworkRef *)v27);
      return;
    }
    Ncsi::Power::AutoPdcNetworkRef::~AutoPdcNetworkRef((Ncsi::Power::AutoPdcNetworkRef *)v27);
  }
  if ( v7 == 2 )
  {
    if ( a1 )
    {
      if ( a1 != 1 )
      {
LABEL_21:
        v7 = 1;
        goto LABEL_22;
      }
      v16 = a2[8298];
    }
    else
    {
      v16 = a2[4353];
    }
    if ( !v16 )
      goto LABEL_21;
  }
LABEL_22:
  if ( (unsigned int)dword_18009A080 > 5 )
  {
    if ( v7 <= *((_DWORD *)v8 + 1106) )
    {
      v17 = "no change in state";
      if ( v7 != *((_DWORD *)v8 + 1106) )
        v17 = "reset connection age to zero.";
    }
    else
    {
      v17 = "change state, reset connection age to zero and signal listeners.";
    }
    v25 = (GetTickCount() - *((_DWORD *)v8 + 1081)) / 0x3E8;
    v24 = (GetTickCount() - *((_DWORD *)v8 + 1081)) / 0x3E8 > dword_18009B3B0;
    LODWORD(v21) = v7;
    LODWORD(v22) = *((_DWORD *)v8 + 1106);
    if ( a1 )
    {
      if ( a1 == 1 )
        v18 = "IPv6";
      else
        v18 = "UnknownConnectivityFamily";
    }
    else
    {
      v18 = "IPv4";
    }
    v26 = *(_QWORD *)a2;
    v19 = -1;
    v20 = -1;
    do
      ++v20;
    while ( v17[v20] );
    v48 = v17;
    v49 = v20 + 1;
    v50 = 0;
    v46 = &v25;
    v47 = 8;
    v44 = &v24;
    v45 = 4;
    v42 = &v21;
    v43 = 4;
    v40 = &v22;
    v41 = 4;
    do
      ++v19;
    while ( v18[v19] );
    v37 = v18;
    v38 = v19 + 1;
    v39 = 0;
    v35 = &v26;
    v36 = 8;
    v28 = 0x50B000000uLL;
    v29 = (char *)off_18009A088;
    v30 = *(unsigned __int16 *)off_18009A088;
    v31 = 2;
    v32 = word_180088A4A;
    v33 = 125;
    v34 = 1;
    LODWORD(v23) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_18009A0A0, &v28, 0, 0, 9, &v29);
  }
  *a4 = NCSI_INTERFACE_ATTRIBUTES::RaiseCapabilityForFamily(a2, a1, (unsigned int)v7, 13);
}

```

## disassembly

```asm
0x1800343d0  mov     [rsp-8+arg_10], rbx
0x1800343d5  push    rbp
0x1800343d6  push    rsi
0x1800343d7  push    rdi
0x1800343d8  push    r12
0x1800343da  push    r13
0x1800343dc  push    r14
0x1800343de  push    r15
0x1800343e0  lea     rbp, [rsp-60h]
0x1800343e5  sub     rsp, 160h
0x1800343ec  mov     rax, cs:__security_cookie
0x1800343f3  xor     rax, rsp
0x1800343f6  mov     [rbp+90h+var_40], rax
0x1800343fa  mov     r12, r9
0x1800343fd  mov     rbx, rdx
0x180034400  movsxd  r14, ecx
0x180034403  xor     r13d, r13d
0x180034406  test    r8d, r8d
0x180034409  jz      short loc_180034423
0x18003440b  sub     r8d, 1
0x18003440f  jz      short loc_18003441C
0x180034411  cmp     r8d, 1
0x180034415  jz      short loc_18003441C
0x180034417  mov     esi, r13d
0x18003441a  jmp     short loc_180034428
0x18003441c  mov     esi, 1
0x180034421  jmp     short loc_180034428
0x180034423  mov     esi, 2
0x180034428  imul    r15, r14, 0F68h
0x18003442f  add     r15, rbx
0x180034432  cmp     [r15+1148h], r13d
0x180034439  jnz     loc_180034579
0x18003443f  mov     rcx, rbx; this
0x180034442  call    ?CanPerformGatewayArpProbe@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NXZ; NCSI_INTERFACE_ATTRIBUTES::CanPerformGatewayArpProbe(void)
0x180034447  test    al, al
0x180034449  jz      loc_180034579
0x18003444f  call    ?IsSystemInStandby@Power@Ncsi@@YA_NXZ; Ncsi::Power::IsSystemInStandby(void)
0x180034454  test    al, al
0x180034456  jz      short loc_1800344B6
0x180034458  mov     eax, cs:dword_18009A080
0x18003445e  cmp     eax, 5
0x180034461  jbe     loc_180034797
0x180034467  mov     rax, [rbx]
0x18003446a  mov     [rsp+190h+var_140], rax
0x18003446f  lea     rax, aAbandoningUpda; "Abandoning UpdateConnectivityFromPassiv"...
0x180034476  mov     [rsp+190h+var_148], rax
0x18003447b  lea     rax, aUpdateconnecti_0; "UpdateConnectivityFromPassivePolling - "...
0x180034482  mov     [rsp+190h+var_150], rax
0x180034487  lea     rax, [rsp+190h+var_140]
0x18003448c  mov     [rsp+190h+var_160], rax
0x180034491  lea     rax, [rsp+190h+var_148]
0x180034496  mov     [rsp+190h+var_168], rax
0x18003449b  lea     rax, [rsp+190h+var_150]
0x1800344a0  mov     [rsp+190h+var_170], rax
0x1800344a5  lea     rdx, unk_180088AC8
0x1800344ac  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800344b1  jmp     loc_180034797
0x1800344b6  xorps   xmm0, xmm0
0x1800344b9  movups  [rsp+190h+var_120], xmm0
0x1800344be  movups  [rbp+90h+var_110], xmm0
0x1800344c2  movups  [rbp+90h+var_100], xmm0
0x1800344c6  movups  [rbp+90h+var_F0], xmm0
0x1800344ca  mov     edx, 9
0x1800344cf  mov     r8d, 0EA60h
0x1800344d5  lea     rcx, [rsp+190h+var_120]
0x1800344da  call    ?ReferenceAllNetworkInterfaces@Power@Ncsi@@YA?AVAutoPdcNetworkRef@12@W4NetworkRefReason@12@K@Z; Ncsi::Power::ReferenceAllNetworkInterfaces(Ncsi::Power::NetworkRefReason,ulong)
0x1800344df  nop
0x1800344e0  lea     rcx, [rsp+190h+var_120]; this
0x1800344e5  call    ?ActivationAcquired@AutoPdcNetworkRef@Power@Ncsi@@QEBA_NXZ; Ncsi::Power::AutoPdcNetworkRef::ActivationAcquired(void)
0x1800344ea  test    al, al
0x1800344ec  jnz     short loc_180034545
0x1800344ee  mov     eax, cs:dword_18009A080
0x1800344f4  cmp     eax, 5
0x1800344f7  jbe     short loc_180034560
0x1800344f9  mov     rax, [rbx]
0x1800344fc  mov     [rsp+190h+var_140], rax
0x180034501  lea     rax, aCannotAcquireP; "Cannot acquire PDC ref"
0x180034508  mov     [rsp+190h+var_148], rax
0x18003450d  lea     rax, aUpdateconnecti_0; "UpdateConnectivityFromPassivePolling - "...
0x180034514  mov     [rsp+190h+var_150], rax
0x180034519  lea     rax, [rsp+190h+var_140]
0x18003451e  mov     [rsp+190h+var_160], rax
0x180034523  lea     rax, [rsp+190h+var_148]
0x180034528  mov     [rsp+190h+var_168], rax
0x18003452d  lea     rax, [rsp+190h+var_150]
0x180034532  mov     [rsp+190h+var_170], rax
0x180034537  lea     rdx, byte_1800889ED
0x18003453e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180034543  jmp     short loc_180034560
0x180034545  movups  xmm0, xmmword ptr [rbx+8]
0x180034549  movaps  [rbp+90h+var_E0], xmm0
0x18003454d  mov     r8d, r14d
0x180034550  mov     rdx, [rbx]
0x180034553  lea     rcx, [rbp+90h+var_E0]
0x180034557  call    ?NcsiPerformArpProbe@@YAKU_GUID@@T_NET_LUID_LH@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; NcsiPerformArpProbe(_GUID,_NET_LUID_LH,_NLA_CONNECTIVITY_FAMILY)
0x18003455c  test    eax, eax
0x18003455e  jz      short loc_18003456F
0x180034560  lea     rcx, [rsp+190h+var_120]; this
0x180034565  call    ??1AutoPdcNetworkRef@Power@Ncsi@@QEAA@XZ; Ncsi::Power::AutoPdcNetworkRef::~AutoPdcNetworkRef(void)
0x18003456a  jmp     loc_180034797
0x18003456f  lea     rcx, [rsp+190h+var_120]; this
0x180034574  call    ??1AutoPdcNetworkRef@Power@Ncsi@@QEAA@XZ; Ncsi::Power::AutoPdcNetworkRef::~AutoPdcNetworkRef(void)
0x180034579  cmp     esi, 2
0x18003457c  jnz     short loc_1800345A2
0x18003457e  test    r14d, r14d
0x180034581  jnz     short loc_18003458C
0x180034583  movzx   eax, byte ptr [rbx+1101h]
0x18003458a  jmp     short loc_180034599
0x18003458c  cmp     r14d, 1
0x180034590  jnz     short loc_18003459D
0x180034592  movzx   eax, byte ptr [rbx+206Ah]
0x180034599  test    al, al
0x18003459b  jnz     short loc_1800345A2
0x18003459d  mov     esi, 1
0x1800345a2  mov     eax, cs:dword_18009A080
0x1800345a8  cmp     eax, 5
0x1800345ab  jbe     loc_18003477F
0x1800345b1  cmp     esi, [r15+1148h]
0x1800345b8  jle     short loc_1800345C3
0x1800345ba  lea     rdi, aChangeStateRes; "change state, reset connection age to z"...
0x1800345c1  jmp     short loc_1800345D5
0x1800345c3  lea     rdi, aNoChangeInStat; "no change in state"
0x1800345ca  lea     rcx, aResetConnectio; "reset connection age to zero."
0x1800345d1  cmovnz  rdi, rcx
0x1800345d5  call    cs:__imp_GetTickCount
0x1800345db  mov     ecx, eax
0x1800345dd  sub     ecx, [r15+10E4h]
0x1800345e4  mov     eax, 10624DD3h
0x1800345e9  mul     ecx
0x1800345eb  shr     edx, 6
0x1800345ee  mov     ecx, edx
0x1800345f0  mov     [rsp+190h+var_130], rcx
0x1800345f5  call    cs:__imp_GetTickCount
0x1800345fb  mov     ecx, eax
0x1800345fd  sub     ecx, [r15+10E4h]
0x180034604  mov     r8d, cs:dword_18009B3B0
0x18003460b  nop
0x18003460c  mov     eax, 10624DD3h
0x180034611  mul     ecx
0x180034613  shr     edx, 6
0x180034616  mov     eax, r13d
0x180034619  cmp     edx, r8d
0x18003461c  setnbe  al
0x18003461f  mov     [rsp+190h+var_138], eax
0x180034623  mov     dword ptr [rsp+190h+var_150], esi
0x180034627  mov     eax, [r15+1148h]
0x18003462e  mov     dword ptr [rsp+190h+var_148], eax
0x180034632  test    r14d, r14d
0x180034635  jz      short loc_18003464F
0x180034637  cmp     r14d, 1
0x18003463b  jz      short loc_180034646
0x18003463d  lea     rdx, aUnknownconnect; "UnknownConnectivityFamily"
0x180034644  jmp     short loc_180034656
0x180034646  lea     rdx, aIpv6; "IPv6"
0x18003464d  jmp     short loc_180034656
0x18003464f  lea     rdx, aIpv4; "IPv4"
0x180034656  mov     rax, [rbx]
0x180034659  mov     [rsp+190h+var_128], rax
0x18003465e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180034665  mov     rax, rcx
0x180034668  nop     dword ptr [rax+rax+00000000h]
0x180034670  inc     rax
0x180034673  cmp     byte ptr [rdi+rax], 0
0x180034677  jnz     short loc_180034670
0x180034679  mov     [rbp+90h+var_50], rdi
0x18003467d  inc     eax
0x18003467f  mov     [rbp+90h+var_48], eax
0x180034682  mov     [rbp+90h+var_44], r13d
0x180034686  lea     rax, [rsp+190h+var_130]
0x18003468b  mov     [rbp+90h+var_60], rax
0x18003468f  mov     [rbp+90h+var_58], 8
0x180034697  lea     rax, [rsp+190h+var_138]
0x18003469c  mov     [rbp+90h+var_70], rax
0x1800346a0  mov     [rbp+90h+var_68], 4
0x1800346a8  lea     rax, [rsp+190h+var_150]
0x1800346ad  mov     [rbp+90h+var_80], rax
0x1800346b1  mov     [rbp+90h+var_78], 4
0x1800346b9  lea     rax, [rsp+190h+var_148]
0x1800346be  mov     [rbp+90h+var_90], rax
0x1800346c2  mov     [rbp+90h+var_88], 4
0x1800346ca  nop     word ptr [rax+rax+00h]
0x1800346d0  lea     rcx, [rcx+1]
0x1800346d4  cmp     byte ptr [rdx+rcx], 0
0x1800346d8  jnz     short loc_1800346D0
0x1800346da  mov     [rbp+90h+var_A0], rdx
0x1800346de  lea     eax, [rcx+1]
0x1800346e1  mov     [rbp+90h+var_98], eax
0x1800346e4  mov     [rbp+90h+var_94], r13d
0x1800346e8  lea     rax, [rsp+190h+var_128]
0x1800346ed  mov     [rbp+90h+var_B0], rax
0x1800346f1  mov     [rbp+90h+var_A8], 8
0x1800346f9  mov     dword ptr [rbp+90h+var_E0], 0B000000h
0x180034700  movzx   eax, cs:word_180088A40
0x180034707  mov     dword ptr [rbp+90h+var_E0+4], eax
0x18003470a  mov     qword ptr [rbp+90h+var_E0+8], r13
0x18003470e  mov     rax, cs:off_18009A088
0x180034715  mov     [rbp+90h+var_D0], rax
0x180034719  movzx   eax, word ptr [rax]
0x18003471c  mov     [rbp+90h+var_C8], eax
0x18003471f  mov     [rbp+90h+var_C4], 2
0x180034726  lea     rax, word_180088A4A
0x18003472d  mov     [rbp+90h+var_C0], rax
0x180034731  mov     [rbp+90h+var_B8], 7Dh ; '}'
0x180034738  mov     [rbp+90h+var_B4], 1
0x18003473f  lea     rax, _TraceLoggingMetadataEnd
0x180034746  lea     rcx, _TraceLoggingMetadata
0x18003474d  sub     eax, ecx
0x18003474f  mov     dword ptr [rsp+190h+var_140], eax
0x180034753  mov     eax, dword ptr [rsp+190h+var_140]
0x180034757  lea     rax, [rbp+90h+var_D0]
0x18003475b  mov     [rsp+190h+var_168], rax
0x180034760  mov     dword ptr [rsp+190h+var_170], 9
0x180034768  xor     r9d, r9d
0x18003476b  xor     r8d, r8d
0x18003476e  lea     rdx, [rbp+90h+var_E0]
0x180034772  mov     rcx, cs:qword_18009A0A0
0x180034779  call    cs:__imp_EtwEventWriteTransfer
0x18003477f  mov     r9d, 0Dh
0x180034785  mov     r8d, esi
0x180034788  mov     edx, r14d
0x18003478b  mov     rcx, rbx
0x18003478e  call    ?RaiseCapabilityForFamily@NCSI_INTERFACE_ATTRIBUTES@@QEAA_NW4_NLA_CONNECTIVITY_FAMILY@@W4_CONNECTIVITY_CAPABILITY@@W4_NLA_CAPABILITY_CHANGE_REASON@@@Z; NCSI_INTERFACE_ATTRIBUTES::RaiseCapabilityForFamily(_NLA_CONNECTIVITY_FAMILY,_CONNECTIVITY_CAPABILITY,_NLA_CAPABILITY_CHANGE_REASON)
0x180034793  mov     [r12], al
0x180034797  mov     rcx, [rbp+90h+var_40]
0x18003479b  xor     rcx, rsp; StackCookie
0x18003479e  call    __security_check_cookie
0x1800347a3  mov     rbx, [rsp+190h+arg_10]
0x1800347ab  add     rsp, 160h
0x1800347b2  pop     r15
0x1800347b4  pop     r14
0x1800347b6  pop     r13
0x1800347b8  pop     r12
0x1800347ba  pop     rdi
0x1800347bb  pop     rsi
0x1800347bc  pop     rbp
0x1800347bd  retn
```

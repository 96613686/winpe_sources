# int_VpnProfilePlumbWfpFilter(void)

- ea: `0x1800ddb70`
- end: `0x1800de243`
- name: `?int_VpnProfilePlumbWfpFilter@@YAKXZ`
- size: `1747`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c5930`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x1800ab634`
- `0x1800ddb70`
- `0x1800de24c`
- `0x1800e3fac`
- `0x1800e4364`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddcd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dddda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddcd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dddda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800de1cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800de1e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800de1cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800de1e1`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800ddc6c`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800ddc6c`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800de099`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800de0ee`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800de099`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800de0ee`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800de12a`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800de169`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800de12a`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800de169`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800dddca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800dddca`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ddcc3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ddcc3`

## string_xrefs

- `0x1800ddd0e`: `DuplicateToken`
- `0x1800dde15`: `ConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
__int64 int_VpnProfilePlumbWfpFilter(void)
{
  NTSTATUS v0; // eax
  DWORD v1; // ebx
  DWORD LastError; // eax
  DWORD v3; // esi
  const char *v4; // rdx
  __int64 v5; // r8
  int v6; // eax
  struct _LIST_ENTRY *v7; // rcx
  DWORD v8; // eax
  DWORD v9; // esi
  struct _LIST_ENTRY *v10; // rcx
  __int64 v11; // rdx
  struct _LIST_ENTRY *v12; // rcx
  __int64 v13; // rdx
  ULONG SecurityDescriptorSize; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  NET_LUID InterfaceLuid; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+58h] [rbp-A8h] BYREF
  FWPM_CALLOUT0 callout; // [rsp+70h] [rbp-90h] BYREF
  FWPM_CALLOUT0 v22; // [rsp+D0h] [rbp-30h] BYREF
  FWPM_FILTER0 filter; // [rsp+130h] [rbp+30h] BYREF
  FWPM_FILTER0 v24; // [rsp+200h] [rbp+100h] BYREF
  GUID v25; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v26; // [rsp+2E0h] [rbp+1E0h]
  int v27; // [rsp+2E8h] [rbp+1E8h]
  int v28; // [rsp+2F0h] [rbp+1F0h]
  GUID v29; // [rsp+2F8h] [rbp+1F8h]
  int v30; // [rsp+308h] [rbp+208h]
  int v31; // [rsp+310h] [rbp+210h]
  int v32; // [rsp+318h] [rbp+218h]
  GUID v33; // [rsp+320h] [rbp+220h]
  int v34; // [rsp+330h] [rbp+230h]
  int v35; // [rsp+338h] [rbp+238h]
  NET_LUID *p_InterfaceLuid; // [rsp+340h] [rbp+240h]
  GUID v37; // [rsp+348h] [rbp+248h]
  int v38; // [rsp+358h] [rbp+258h]
  int v39; // [rsp+360h] [rbp+260h]
  __int128 *v40; // [rsp+368h] [rbp+268h]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 551, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  filter.filterKey.Data1 = 0;
  memset_0(&filter.filterKey.Data2, 0, 0xC4u);
  v24.filterKey.Data1 = 0;
  memset_0(&v24.filterKey.Data2, 0, 0xC4u);
  v25.Data1 = 0;
  memset_0(&v25.Data2, 0, 0x9Cu);
  StringSid = 0;
  InterfaceLuid.Value = 0;
  StringSecurityDescriptor = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  callout.calloutKey.Data1 = 0;
  memset_0(&callout.calloutKey.Data2, 0, 0x54u);
  v22.calloutKey.Data1 = 0;
  memset_0(&v22.calloutKey.Data2, 0, 0x54u);
  v20 = 0;
  v0 = ConvertInterfaceIndexToLuid(InterfaceIndex, &InterfaceLuid);
  if ( v0 < 0 )
  {
    v1 = 87;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control[1].Flink,
        552,
        &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
        (unsigned int)v0,
        87);
    }
    goto LABEL_53;
  }
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 553, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, LastError);
      }
      v1 = 0;
      v4 = "DuplicateToken";
      v5 = v3;
      goto LABEL_52;
    }
  }
  v6 = VpnStringBuild(&StringSecurityDescriptor, L"O:LSD:(A;;CC;;;", StringSid);
  v1 = v6;
  if ( v6 >= 0 )
  {
    v1 = 0;
    goto LABEL_25;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 554, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v6);
    v7 = WPP_GLOBAL_Control;
  }
  if ( (v1 & 0x1FFF0000) == 0x70000 )
    v1 = (unsigned __int16)v1;
  if ( !v1 )
  {
LABEL_25:
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            StringSecurityDescriptor,
            1u,
            &SecurityDescriptor,
            &SecurityDescriptorSize) )
    {
      v8 = GetLastError();
      v9 = v8;
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 556, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v8);
        }
        v5 = v9;
        v4 = "ConvertStringSecurityDescriptorToSecurityDescriptor";
        goto LABEL_52;
      }
    }
    v25 = FWPM_CONDITION_IP_PROTOCOL;
    v29 = FWPM_CONDITION_IP_PROTOCOL;
    p_InterfaceLuid = &InterfaceLuid;
    LODWORD(v20) = SecurityDescriptorSize;
    *((_QWORD *)&v20 + 1) = SecurityDescriptor;
    v40 = &v20;
    *(_DWORD *)&filter.filterKey.Data4[4] = -1917430209;
    filter.displayData.name = L"VPN IPv4 TCP Flow counting filter";
    filter.displayData.description = L"This filter keep track of VPN IPv4 TCP Flow, to determine when the connection is no longer in use";
    filter.filterCondition = (FWPM_FILTER_CONDITION0 *)&v25;
    v33 = FWPM_CONDITION_IP_LOCAL_INTERFACE;
    *(_DWORD *)&v24.filterKey.Data4[4] = 668242566;
    v24.displayData.name = L"VPN IPv6 TCP Flow counting filter";
    v37 = FWPM_CONDITION_ALE_USER_ID;
    *(_QWORD *)&filter.filterKey.Data2 = 0xE12DB8AD4AD526F3uLL;
    v24.displayData.description = L"This filter keep track of VPN IPv6 TCP Flow, to determine when the connection is no longer in use";
    *(_QWORD *)&v24.filterKey.Data2 = 0x21B475A5440E8E64LL;
    filter.action.type = 24580;
    v24.action.type = 24580;
    v24.filterCondition = (FWPM_FILTER_CONDITION0 *)&v25;
    v26 = 0;
    v27 = 1;
    v28 = 6;
    v30 = 0;
    v31 = 1;
    v32 = 17;
    v34 = 0;
    v35 = 4;
    v38 = 0;
    v39 = 14;
    filter.filterKey.Data1 = 2078314097;
    filter.flags = 0;
    filter.layerKey = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4;
    filter.weight.type = FWP_EMPTY;
    filter.subLayerKey = FWPM_SUBLAYER_INSPECTION;
    filter.numFilterConditions = 4;
    filter.action.filterType = stru_18010B540;
    v24.filterKey.Data1 = -1669476602;
    v24.flags = 0;
    v24.layerKey = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6;
    v24.weight.type = FWP_EMPTY;
    v24.subLayerKey = FWPM_SUBLAYER_INSPECTION;
    v24.numFilterConditions = 4;
    v24.action.filterType = stru_18010B560;
    callout.calloutKey = stru_18010B540;
    v22.calloutKey = stru_18010B560;
    callout.displayData.name = L"callout for vpn ale IPv4 flows";
    callout.applicableLayer = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4;
    v22.displayData.name = L"callout for vpn ale IPv6 flows";
    v22.applicableLayer = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6;
    v1 = FwpmCalloutAdd0(g_FwpEngineHandle, &callout, 0, 0);
    if ( v1 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_36;
      }
      v11 = 557;
LABEL_35:
      WPP_SF_d(v10[1].Flink, v11, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v1);
LABEL_36:
      v4 = "FwpmCalloutAdd0";
LABEL_51:
      v5 = v1;
LABEL_52:
      VpnReportError("int_VpnProfilePlumbWfpFilter", v4, v5);
      goto LABEL_53;
    }
    v1 = FwpmCalloutAdd0(g_FwpEngineHandle, &v22, 0, 0);
    if ( v1 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_36;
      }
      v11 = 558;
      goto LABEL_35;
    }
    v1 = FwpmFilterAdd0(g_FwpEngineHandle, &filter, 0, 0);
    if ( v1 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_50;
      }
      v13 = 559;
    }
    else
    {
      v1 = FwpmFilterAdd0(g_FwpEngineHandle, &v24, 0, 0);
      if ( !v1 )
        goto LABEL_53;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_50;
      }
      v13 = 560;
    }
    WPP_SF_d(v12[1].Flink, v13, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v1);
LABEL_50:
    v4 = "FwpmFilterAdd0";
    goto LABEL_51;
  }
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v7[1].Blink) & 1) != 0 )
    WPP_SF_d(v7[1].Flink, 555, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v1);
LABEL_53:
  MprCommonFree((LPVOID)StringSecurityDescriptor);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v1 )
  {
    int_VpnProfileUnPlumbWfpFilter();
    if ( (v1 & 0x80000000) != 0
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 561, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v1);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800ddb70  push    rbp
0x1800ddb72  push    rbx
0x1800ddb73  push    rsi
0x1800ddb74  push    r12
0x1800ddb76  push    r14
0x1800ddb78  push    r15
0x1800ddb7a  lea     rbp, [rsp-288h]
0x1800ddb82  sub     rsp, 388h
0x1800ddb89  mov     rax, cs:__security_cookie
0x1800ddb90  xor     rax, rsp
0x1800ddb93  mov     [rbp+2B0h+var_40], rax
0x1800ddb9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddba1  lea     r15, WPP_GLOBAL_Control
0x1800ddba8  lea     r12, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800ddbaf  cmp     rcx, r15
0x1800ddbb2  jz      short loc_1800DDBCB
0x1800ddbb4  test    byte ptr [rcx+1Ch], 8
0x1800ddbb8  jz      short loc_1800DDBCB
0x1800ddbba  mov     rcx, [rcx+10h]
0x1800ddbbe  mov     edx, 227h
0x1800ddbc3  mov     r8, r12
0x1800ddbc6  call    WPP_SF_
0x1800ddbcb  mov     ebx, 0C4h
0x1800ddbd0  lea     rcx, [rbp+2B0h+filter.filterKey.Data2]; void *
0x1800ddbd4  xor     r14d, r14d
0x1800ddbd7  mov     r8d, ebx; Size
0x1800ddbda  xor     edx, edx; Val
0x1800ddbdc  mov     [rbp+2B0h+filter.filterKey.Data1], r14d
0x1800ddbe0  call    memset_0
0x1800ddbe5  mov     r8d, ebx; Size
0x1800ddbe8  mov     [rbp+2B0h+var_1B0.filterKey.Data1], r14d
0x1800ddbef  xor     edx, edx; Val
0x1800ddbf1  lea     rcx, [rbp+2B0h+var_1B0.filterKey.Data2]; void *
0x1800ddbf8  call    memset_0
0x1800ddbfd  xor     edx, edx; Val
0x1800ddbff  mov     [rbp+2B0h+var_E0], r14d
0x1800ddc06  lea     r8d, [rbx-28h]; Size
0x1800ddc0a  lea     rcx, [rbp+2B0h+var_DC]; void *
0x1800ddc11  call    memset_0
0x1800ddc16  lea     ebx, [r14+54h]
0x1800ddc1a  mov     [rsp+3B0h+StringSid], r14
0x1800ddc1f  mov     r8d, ebx; Size
0x1800ddc22  mov     qword ptr [rsp+3B0h+InterfaceLuid], r14
0x1800ddc27  xor     edx, edx; Val
0x1800ddc29  mov     [rsp+3B0h+StringSecurityDescriptor], r14
0x1800ddc2e  lea     rcx, [rsp+3B0h+callout.calloutKey.Data2]; void *
0x1800ddc33  mov     [rsp+3B0h+SecurityDescriptor], r14
0x1800ddc38  mov     [rsp+3B0h+SecurityDescriptorSize], r14d
0x1800ddc3d  mov     [rsp+3B0h+callout.calloutKey.Data1], r14d
0x1800ddc42  call    memset_0
0x1800ddc47  mov     r8d, ebx; Size
0x1800ddc4a  mov     [rbp+2B0h+var_2E0.calloutKey.Data1], r14d
0x1800ddc4e  xor     edx, edx; Val
0x1800ddc50  lea     rcx, [rbp+2B0h+var_2E0.calloutKey.Data2]; void *
0x1800ddc54  call    memset_0
0x1800ddc59  mov     ecx, cs:InterfaceIndex; InterfaceIndex
0x1800ddc5f  lea     rdx, [rsp+3B0h+InterfaceLuid]; InterfaceLuid
0x1800ddc64  xorps   xmm0, xmm0
0x1800ddc67  movups  [rsp+3B0h+var_358], xmm0
0x1800ddc6c  call    cs:__imp_ConvertInterfaceIndexToLuid
0x1800ddc73  nop     dword ptr [rax+rax+00h]
0x1800ddc78  test    eax, eax
0x1800ddc7a  jns     short loc_1800DDCB7
0x1800ddc7c  lea     ebx, [r14+57h]
0x1800ddc80  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddc87  cmp     rcx, r15
0x1800ddc8a  jz      loc_1800DE1B7
0x1800ddc90  test    byte ptr [rcx+1Ch], 1
0x1800ddc94  jz      loc_1800DE1B7
0x1800ddc9a  mov     rcx, [rcx+10h]
0x1800ddc9e  mov     edx, 228h
0x1800ddca3  mov     r9d, eax
0x1800ddca6  mov     dword ptr [rsp+3B0h+var_390], ebx
0x1800ddcaa  mov     r8, r12
0x1800ddcad  call    WPP_SF_Dd
0x1800ddcb2  jmp     loc_1800DE1B7
0x1800ddcb7  mov     rcx, cs:Sid; Sid
0x1800ddcbe  lea     rdx, [rsp+3B0h+StringSid]; StringSid
0x1800ddcc3  call    cs:__imp_ConvertSidToStringSidW
0x1800ddcca  nop     dword ptr [rax+rax+00h]
0x1800ddccf  test    eax, eax
0x1800ddcd1  jnz     short loc_1800DDD1D
0x1800ddcd3  call    cs:__imp_GetLastError
0x1800ddcda  nop     dword ptr [rax+rax+00h]
0x1800ddcdf  mov     esi, eax
0x1800ddce1  test    eax, eax
0x1800ddce3  jz      short loc_1800DDD1D
0x1800ddce5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddcec  cmp     rcx, r15
0x1800ddcef  jz      short loc_1800DDD0B
0x1800ddcf1  test    byte ptr [rcx+1Ch], 1
0x1800ddcf5  jz      short loc_1800DDD0B
0x1800ddcf7  mov     rcx, [rcx+10h]
0x1800ddcfb  mov     edx, 229h
0x1800ddd00  mov     r9d, eax
0x1800ddd03  mov     r8, r12
0x1800ddd06  call    WPP_SF_d
0x1800ddd0b  mov     ebx, r14d
0x1800ddd0e  lea     rdx, aDuplicatetoken; "DuplicateToken"
0x1800ddd15  mov     r8d, esi
0x1800ddd18  jmp     loc_1800DE1AB
0x1800ddd1d  mov     r8, [rsp+3B0h+StringSid]
0x1800ddd22  lea     r9, aACcS11521; ")(A;;CC;;;S-1-15-2-1)"
0x1800ddd29  lea     rdx, aOLsdACc; "O:LSD:(A;;CC;;;"
0x1800ddd30  mov     [rsp+3B0h+var_390], r14
0x1800ddd35  lea     rcx, [rsp+3B0h+StringSecurityDescriptor]
0x1800ddd3a  call    VpnStringBuild
0x1800ddd3f  mov     ebx, eax
0x1800ddd41  test    eax, eax
0x1800ddd43  jns     short loc_1800DDDB3
0x1800ddd45  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddd4c  cmp     rcx, r15
0x1800ddd4f  jz      short loc_1800DDD72
0x1800ddd51  test    byte ptr [rcx+1Ch], 1
0x1800ddd55  jz      short loc_1800DDD72
0x1800ddd57  mov     rcx, [rcx+10h]
0x1800ddd5b  mov     edx, 22Ah
0x1800ddd60  mov     r9d, eax
0x1800ddd63  mov     r8, r12
0x1800ddd66  call    WPP_SF_d
0x1800ddd6b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddd72  mov     eax, ebx
0x1800ddd74  and     eax, 1FFF0000h
0x1800ddd79  cmp     eax, 70000h
0x1800ddd7e  jnz     short loc_1800DDD83
0x1800ddd80  movzx   ebx, bx
0x1800ddd83  test    ebx, ebx
0x1800ddd85  jz      short loc_1800DDDB6
0x1800ddd87  cmp     rcx, r15
0x1800ddd8a  jz      loc_1800DE1B7
0x1800ddd90  test    byte ptr [rcx+1Ch], 1
0x1800ddd94  jz      loc_1800DE1B7
0x1800ddd9a  mov     rcx, [rcx+10h]
0x1800ddd9e  mov     edx, 22Bh
0x1800ddda3  mov     r9d, ebx
0x1800ddda6  mov     r8, r12
0x1800ddda9  call    WPP_SF_d
0x1800dddae  jmp     loc_1800DE1B7
0x1800dddb3  mov     ebx, r14d
0x1800dddb6  mov     rcx, [rsp+3B0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800dddbb  lea     r9, [rsp+3B0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800dddc0  lea     r8, [rsp+3B0h+SecurityDescriptor]; SecurityDescriptor
0x1800dddc5  mov     edx, 1; StringSDRevision
0x1800dddca  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800dddd1  nop     dword ptr [rax+rax+00h]
0x1800dddd6  test    eax, eax
0x1800dddd8  jnz     short loc_1800DDE21
0x1800dddda  call    cs:__imp_GetLastError
0x1800ddde1  nop     dword ptr [rax+rax+00h]
0x1800ddde6  mov     esi, eax
0x1800ddde8  test    eax, eax
0x1800dddea  jz      short loc_1800DDE21
0x1800dddec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dddf3  cmp     rcx, r15
0x1800dddf6  jz      short loc_1800DDE12
0x1800dddf8  test    byte ptr [rcx+1Ch], 1
0x1800dddfc  jz      short loc_1800DDE12
0x1800dddfe  mov     rcx, [rcx+10h]
0x1800dde02  mov     edx, 22Ch
0x1800dde07  mov     r9d, eax
0x1800dde0a  mov     r8, r12
0x1800dde0d  call    WPP_SF_d
0x1800dde12  mov     r8d, esi
0x1800dde15  lea     rdx, aConvertstrings_1; "ConvertStringSecurityDescriptorToSecuri"...
0x1800dde1c  jmp     loc_1800DE1AB
0x1800dde21  mov     eax, dword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data4+4
0x1800dde27  mov     r9d, 4
0x1800dde2d  movsd   xmm0, qword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data2
0x1800dde35  mov     ecx, cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x1800dde3b  movups  xmm1, xmmword ptr cs:FWPM_SUBLAYER_INSPECTION.Data1
0x1800dde42  mov     r8d, cs:stru_18010B540.Data1
0x1800dde49  movups  xmm4, xmmword ptr cs:FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4.Data1
0x1800dde50  mov     edx, dword ptr cs:stru_18010B540.Data4+4
0x1800dde56  movups  xmm2, xmmword ptr cs:FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6.Data1
0x1800dde5d  mov     [rbp+2B0h+var_D4], eax
0x1800dde63  movsd   xmm3, qword ptr cs:stru_18010B540.Data2
0x1800dde6b  mov     [rbp+2B0h+var_AC], eax
0x1800dde71  lea     rax, [rsp+3B0h+InterfaceLuid]
0x1800dde76  mov     [rbp+2B0h+var_70], rax
0x1800dde7d  mov     eax, [rsp+3B0h+SecurityDescriptorSize]
0x1800dde81  mov     dword ptr [rsp+3B0h+var_358], eax
0x1800dde85  mov     rax, [rsp+3B0h+SecurityDescriptor]
0x1800dde8a  mov     qword ptr [rsp+3B0h+var_358+8], rax
0x1800dde8f  lea     rax, [rsp+3B0h+var_358]
0x1800dde94  mov     [rbp+2B0h+var_48], rax
0x1800dde9b  mov     eax, dword ptr cs:key.Data4+4
0x1800ddea1  mov     dword ptr [rbp+2B0h+filter.filterKey.Data4+4], eax
0x1800ddea4  lea     rax, aVpnIpv4TcpFlow; "VPN IPv4 TCP Flow counting filter"
0x1800ddeab  mov     [rbp+2B0h+filter.displayData.name], rax
0x1800ddeaf  lea     rax, aThisFilterKeep_0; "This filter keep track of VPN IPv4 TCP "...
0x1800ddeb6  mov     [rbp+2B0h+filter.displayData.description], rax
0x1800ddeba  lea     rax, [rbp+2B0h+var_E0]
0x1800ddec1  movsd   [rbp+2B0h+var_DC], xmm0
0x1800ddec9  movsd   [rbp+2B0h+var_B4], xmm0
0x1800dded1  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_INTERFACE.Data1
0x1800dded8  mov     [rbp+2B0h+filter.filterCondition], rax
0x1800ddedf  mov     eax, dword ptr cs:stru_1800FDFA8.Data4+4
0x1800ddee5  movdqu  [rbp+2B0h+var_90], xmm0
0x1800ddeed  mov     dword ptr [rbp+2B0h+var_1B0.filterKey.Data4+4], eax
0x1800ddef3  lea     rax, aVpnIpv6TcpFlow; "VPN IPv6 TCP Flow counting filter"
0x1800ddefa  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_ALE_USER_ID.Data1
0x1800ddf01  mov     [rbp+2B0h+var_1B0.displayData.name], rax
0x1800ddf08  lea     rax, aThisFilterKeep; "This filter keep track of VPN IPv6 TCP "...
0x1800ddf0f  mov     [rbp+2B0h+var_E0], ecx
0x1800ddf15  movdqu  [rbp+2B0h+var_68], xmm0
0x1800ddf1d  mov     [rbp+2B0h+var_B8], ecx
0x1800ddf23  mov     ecx, 6004h
0x1800ddf28  movsd   xmm0, qword ptr cs:key.Data2
0x1800ddf30  movsd   qword ptr [rbp+2B0h+filter.filterKey.Data2], xmm0
0x1800ddf35  movsd   xmm0, qword ptr cs:stru_1800FDFA8.Data2
0x1800ddf3d  mov     [rbp+2B0h+var_1B0.displayData.description], rax
0x1800ddf44  lea     rax, [rbp+2B0h+var_E0]
0x1800ddf4b  movsd   qword ptr [rbp+2B0h+var_1B0.filterKey.Data2], xmm0
0x1800ddf53  movsd   xmm0, qword ptr cs:stru_18010B560.Data2
0x1800ddf5b  mov     [rbp+2B0h+filter.action.type], ecx
0x1800ddf61  mov     [rbp+2B0h+var_1B0.action.type], ecx
0x1800ddf67  mov     ecx, cs:stru_18010B560.Data1
0x1800ddf6d  mov     [rbp+2B0h+var_1B0.filterCondition], rax
0x1800ddf74  mov     eax, dword ptr cs:stru_18010B560.Data4+4
0x1800ddf7a  mov     [rbp+2B0h+var_D0], r14d
0x1800ddf81  mov     [rbp+2B0h+var_C8], 1
0x1800ddf8b  mov     [rbp+2B0h+var_C0], 6
0x1800ddf95  mov     [rbp+2B0h+var_A8], r14d
0x1800ddf9c  mov     [rbp+2B0h+var_A0], 1
0x1800ddfa6  mov     [rbp+2B0h+var_98], 11h
0x1800ddfb0  mov     [rbp+2B0h+var_80], r14d
0x1800ddfb7  mov     [rbp+2B0h+var_78], r9d
0x1800ddfbe  mov     [rbp+2B0h+var_58], r14d
0x1800ddfc5  mov     [rbp+2B0h+var_50], 0Eh
0x1800ddfcf  mov     [rbp+2B0h+filter.filterKey.Data1], 7BE08E71h
0x1800ddfd6  mov     [rbp+2B0h+filter.flags], r14d
0x1800ddfda  movdqu  xmmword ptr [rbp+2B0h+filter.layerKey.Data1], xmm4
0x1800ddfdf  mov     [rbp+2B0h+filter.weight.type], r14d
0x1800ddfe6  movdqu  xmmword ptr [rbp+2B0h+filter.subLayerKey.Data1], xmm1
0x1800ddfee  mov     [rbp+2B0h+filter.numFilterConditions], r9d
0x1800ddff5  mov     dword ptr [rbp+2B0h+filter.action.4], r8d
0x1800ddffc  movsd   qword ptr [rbp+2B0h+filter.action.4+4], xmm3
0x1800de004  mov     dword ptr [rbp+2B0h+filter.action.4+0Ch], edx
0x1800de00a  mov     [rbp+2B0h+var_1B0.filterKey.Data1], 9C7DCF06h
0x1800de014  mov     [rbp+2B0h+var_1B0.flags], r14d
0x1800de01b  movdqu  xmmword ptr [rbp+2B0h+var_1B0.layerKey.Data1], xmm2
0x1800de023  mov     [rbp+2B0h+var_1B0.weight.type], r14d
0x1800de02a  movdqu  xmmword ptr [rbp+2B0h+var_1B0.subLayerKey.Data1], xmm1
0x1800de032  mov     [rbp+2B0h+var_1B0.numFilterConditions], r9d
0x1800de039  mov     dword ptr [rbp+2B0h+var_1B0.action.4], ecx
0x1800de03f  movsd   qword ptr [rbp+2B0h+var_1B0.action.4+4], xmm0
0x1800de047  mov     dword ptr [rsp+3B0h+callout.calloutKey.Data4+4], edx
0x1800de04b  xor     r9d, r9d; id
0x1800de04e  lea     rdx, aCalloutForVpnA; "callout for vpn ale IPv4 flows"
0x1800de055  mov     dword ptr [rbp+2B0h+var_1B0.action.4+0Ch], eax
0x1800de05b  mov     dword ptr [rbp+2B0h+var_2E0.calloutKey.Data4+4], eax
0x1800de05e  lea     rax, aCalloutForVpnA_0; "callout for vpn ale IPv6 flows"
0x1800de065  mov     [rbp+2B0h+callout.displayData.name], rdx
0x1800de069  lea     rdx, [rsp+3B0h+callout]; callout
0x1800de06e  mov     [rsp+3B0h+callout.calloutKey.Data1], r8d
0x1800de073  xor     r8d, r8d; sd
0x1800de076  mov     [rbp+2B0h+var_2E0.calloutKey.Data1], ecx
0x1800de079  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; engineHandle
0x1800de080  movsd   qword ptr [rsp+3B0h+callout.calloutKey.Data2], xmm3
0x1800de086  movdqu  xmmword ptr [rbp+2B0h+callout.applicableLayer.Data1], xmm4
0x1800de08b  mov     [rbp+2B0h+var_2E0.displayData.name], rax
0x1800de08f  movsd   qword ptr [rbp+2B0h+var_2E0.calloutKey.Data2], xmm0
0x1800de094  movdqu  xmmword ptr [rbp+2B0h+var_2E0.applicableLayer.Data1], xmm2
0x1800de099  call    cs:__imp_FwpmCalloutAdd0
0x1800de0a0  nop     dword ptr [rax+rax+00h]
0x1800de0a5  mov     ebx, eax
0x1800de0a7  test    eax, eax
0x1800de0a9  jz      short loc_1800DE0DD
0x1800de0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de0b2  cmp     rcx, r15
0x1800de0b5  jz      short loc_1800DE0D1
0x1800de0b7  test    byte ptr [rcx+1Ch], 1
0x1800de0bb  jz      short loc_1800DE0D1
0x1800de0bd  mov     edx, 22Dh
0x1800de0c2  mov     rcx, [rcx+10h]
0x1800de0c6  mov     r9d, ebx
0x1800de0c9  mov     r8, r12
0x1800de0cc  call    WPP_SF_d
0x1800de0d1  lea     rdx, aFwpmcalloutadd; "FwpmCalloutAdd0"
0x1800de0d8  jmp     loc_1800DE1A8
0x1800de0dd  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; engineHandle
0x1800de0e4  lea     rdx, [rbp+2B0h+var_2E0]; callout
0x1800de0e8  xor     r9d, r9d; id
0x1800de0eb  xor     r8d, r8d; sd
0x1800de0ee  call    cs:__imp_FwpmCalloutAdd0
0x1800de0f5  nop     dword ptr [rax+rax+00h]
0x1800de0fa  mov     ebx, eax
0x1800de0fc  test    eax, eax
0x1800de0fe  jz      short loc_1800DE119
0x1800de100  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de107  cmp     rcx, r15
0x1800de10a  jz      short loc_1800DE0D1
0x1800de10c  test    byte ptr [rcx+1Ch], 1
0x1800de110  jz      short loc_1800DE0D1
0x1800de112  mov     edx, 22Eh
0x1800de117  jmp     short loc_1800DE0C2
0x1800de119  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; engineHandle
0x1800de120  lea     rdx, [rbp+2B0h+filter]; filter
0x1800de124  xor     r9d, r9d; id
0x1800de127  xor     r8d, r8d; sd
  ... truncated ...
```

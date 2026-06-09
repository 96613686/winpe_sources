# FwEventHttpProxyChanged

- ea: `0x180067c5c`
- end: `0x180067fc0`
- name: `FwEventHttpProxyChanged`
- size: `868`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180044ca4`

## callees

- `0x18000af3c`
- `0x180029b48`
- `0x180049d98`
- `0x18004c870`
- `0x180067c5c`
- `0x180067fc8`
- `0x18006f520`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x180067d51`
- `fwbase!FwHResultToWindowsError` at `0x180067d9e`
- `fwbase!FwHResultToWindowsError` at `0x180067deb`
- `fwbase!FwHResultToWindowsError` at `0x180067e38`
- `fwbase!FwHResultToWindowsError` at `0x180067e84`
- `fwbase!FwHResultToWindowsError` at `0x180067d51`
- `fwbase!FwHResultToWindowsError` at `0x180067d9e`
- `fwbase!FwHResultToWindowsError` at `0x180067deb`
- `fwbase!FwHResultToWindowsError` at `0x180067e38`
- `fwbase!FwHResultToWindowsError` at `0x180067e84`
- `fwbase!FwFree` at `0x180067f4a`
- `fwbase!FwFree` at `0x180067f5e`
- `fwbase!FwFree` at `0x180067f72`
- `fwbase!FwFree` at `0x180067f86`
- `fwbase!FwFree` at `0x180067f99`
- `fwbase!FwFree` at `0x180067f4a`
- `fwbase!FwFree` at `0x180067f5e`
- `fwbase!FwFree` at `0x180067f72`
- `fwbase!FwFree` at `0x180067f86`
- `fwbase!FwFree` at `0x180067f99`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067d49`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067d96`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067de3`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067e30`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067e7c`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067d49`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067d96`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067de3`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067e30`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067e7c`

## pseudocode

```c
__int64 __fastcall FwEventHttpProxyChanged(int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, char a7)
{
  __int64 v7; // r12
  __int64 v8; // r13
  unsigned int IsEventEnbled; // ebx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int OpenPortorAuthAppAddrAsString; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v22; // [rsp+20h] [rbp-A1h] BYREF
  unsigned __int16 *v23; // [rsp+28h] [rbp-99h] BYREF
  unsigned __int16 *v24; // [rsp+30h] [rbp-91h] BYREF
  unsigned __int16 *v25; // [rsp+38h] [rbp-89h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-81h] BYREF
  unsigned __int16 *v27; // [rsp+48h] [rbp-79h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+50h] [rbp-71h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+60h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+70h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+80h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+90h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+A0h] [rbp-21h] BYREF
  char *v34; // [rsp+B0h] [rbp-11h]
  __int64 v35; // [rsp+B8h] [rbp-9h]
  int v36; // [rsp+110h] [rbp+4Fh] BYREF

  v36 = a1;
  v7 = a5;
  v8 = a6;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  IsEventEnbled = FwIsEventEnbled(&NetIsoHttpProxyChangedEvent, &v22);
  if ( IsEventEnbled )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v14 = 13;
LABEL_5:
      v15 = IsEventEnbled;
LABEL_6:
      WPP_SF_d(*(_QWORD *)(v13 + 16), v14, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids, v15);
    }
  }
  else if ( v22 )
  {
    OpenPortorAuthAppAddrAsString = GetOpenPortorAuthAppAddrAsString(a2, &v23, 1);
    IsEventEnbled = FwHResultToWindowsError(OpenPortorAuthAppAddrAsString);
    if ( IsEventEnbled )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v14 = 15;
        goto LABEL_5;
      }
    }
    else
    {
      v17 = GetOpenPortorAuthAppAddrAsString(a3, &v24, 1);
      IsEventEnbled = FwHResultToWindowsError(v17);
      if ( IsEventEnbled )
      {
        v13 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v14 = 16;
          goto LABEL_5;
        }
      }
      else
      {
        v18 = GetOpenPortorAuthAppAddrAsString(a4, &v25, 1);
        IsEventEnbled = FwHResultToWindowsError(v18);
        if ( IsEventEnbled )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v14 = 17;
            goto LABEL_5;
          }
        }
        else
        {
          v19 = GetOpenPortorAuthAppAddrAsString(v7, &v26, 1);
          IsEventEnbled = FwHResultToWindowsError(v19);
          if ( IsEventEnbled )
          {
            v13 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v14 = 18;
              goto LABEL_5;
            }
          }
          else
          {
            v20 = GetOpenPortorAuthAppAddrAsString(v8, &v27, 1);
            IsEventEnbled = FwHResultToWindowsError(v20);
            if ( !IsEventEnbled )
            {
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
              *(_QWORD *)&v28.Size = 4;
              v28.Ptr = (ULONGLONG)&v36;
              FwSerializeStringEventParam(&v29, v23);
              FwSerializeStringEventParam(&v30, v24);
              FwSerializeStringEventParam(&v31, v25);
              FwSerializeStringEventParam(&v32, v26);
              FwSerializeStringEventParam(&v33, v27);
              v35 = 4;
              v34 = &a7;
              IsEventEnbled = FwLogEvent(&NetIsoHttpProxyChangedEvent, 7u, &v28);
              goto LABEL_32;
            }
            v13 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v14 = 19;
              goto LABEL_5;
            }
          }
        }
      }
    }
  }
  else
  {
    IsEventEnbled = 0;
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v14 = 14;
      v15 = 0;
      goto LABEL_6;
    }
  }
LABEL_32:
  FwFree(v23);
  v23 = 0;
  FwFree(v24);
  v24 = 0;
  FwFree(v25);
  v25 = 0;
  FwFree(v26);
  v26 = 0;
  FwFree(v27);
  return IsEventEnbled;
}

```

## disassembly

```asm
0x180067c5c  mov     [rsp-8+arg_0], ecx
0x180067c60  push    rbp
0x180067c61  push    rbx
0x180067c62  push    rsi
0x180067c63  push    r12
0x180067c65  push    r13
0x180067c67  push    r14
0x180067c69  push    r15
0x180067c6b  lea     rbp, [rsp-0Fh]
0x180067c70  sub     rsp, 0D0h
0x180067c77  mov     rax, cs:__security_cookie
0x180067c7e  xor     rax, rsp
0x180067c81  mov     [rbp+3Fh+var_40], rax
0x180067c85  mov     r12, [rbp+3Fh+arg_20]
0x180067c89  lea     rcx, NetIsoHttpProxyChangedEvent
0x180067c90  mov     r13, [rbp+3Fh+arg_28]
0x180067c94  xor     eax, eax
0x180067c96  mov     rsi, rdx
0x180067c99  mov     [rsp+100h+var_E0], eax
0x180067c9d  lea     rdx, [rsp+100h+var_E0]
0x180067ca2  mov     [rsp+100h+var_D8], rax
0x180067ca7  mov     [rsp+100h+var_D0], rax
0x180067cac  mov     r15, r9
0x180067caf  mov     [rsp+100h+var_C8], rax
0x180067cb4  mov     r14, r8
0x180067cb7  mov     [rsp+100h+var_C0], rax
0x180067cbc  mov     [rbp+3Fh+var_B8], rax
0x180067cc0  call    FwIsEventEnbled
0x180067cc5  mov     ebx, eax
0x180067cc7  test    eax, eax
0x180067cc9  jz      short loc_180067D09
0x180067ccb  mov     rax, cs:WPP_GLOBAL_Control
0x180067cd2  lea     rcx, WPP_GLOBAL_Control
0x180067cd9  cmp     rax, rcx
0x180067cdc  jz      loc_180067F45
0x180067ce2  test    byte ptr [rax+1Ch], 1
0x180067ce6  jz      loc_180067F45
0x180067cec  mov     edx, 0Dh
0x180067cf1  mov     r9d, ebx
0x180067cf4  mov     rcx, [rax+10h]
0x180067cf8  lea     r8, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids
0x180067cff  call    WPP_SF_d
0x180067d04  jmp     loc_180067F45
0x180067d09  cmp     [rsp+100h+var_E0], 0
0x180067d0e  jnz     short loc_180067D3B
0x180067d10  xor     ebx, ebx
0x180067d12  mov     rax, cs:WPP_GLOBAL_Control
0x180067d19  lea     rcx, WPP_GLOBAL_Control
0x180067d20  cmp     rax, rcx
0x180067d23  jz      loc_180067F45
0x180067d29  test    byte ptr [rax+1Ch], 1
0x180067d2d  jz      loc_180067F45
0x180067d33  lea     edx, [rbx+0Eh]
0x180067d36  xor     r9d, r9d
0x180067d39  jmp     short loc_180067CF4
0x180067d3b  mov     r8d, 1
0x180067d41  lea     rdx, [rsp+100h+var_D8]
0x180067d46  mov     rcx, rsi
0x180067d49  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x180067d4f  mov     ecx, eax
0x180067d51  call    cs:__imp_FwHResultToWindowsError
0x180067d57  mov     ebx, eax
0x180067d59  test    eax, eax
0x180067d5b  jz      short loc_180067D88
0x180067d5d  mov     rax, cs:WPP_GLOBAL_Control
0x180067d64  lea     rcx, WPP_GLOBAL_Control
0x180067d6b  cmp     rax, rcx
0x180067d6e  jz      loc_180067F45
0x180067d74  test    byte ptr [rax+1Ch], 1
0x180067d78  jz      loc_180067F45
0x180067d7e  mov     edx, 0Fh
0x180067d83  jmp     loc_180067CF1
0x180067d88  mov     r8d, 1
0x180067d8e  lea     rdx, [rsp+100h+var_D0]
0x180067d93  mov     rcx, r14
0x180067d96  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x180067d9c  mov     ecx, eax
0x180067d9e  call    cs:__imp_FwHResultToWindowsError
0x180067da4  mov     ebx, eax
0x180067da6  test    eax, eax
0x180067da8  jz      short loc_180067DD5
0x180067daa  mov     rax, cs:WPP_GLOBAL_Control
0x180067db1  lea     rcx, WPP_GLOBAL_Control
0x180067db8  cmp     rax, rcx
0x180067dbb  jz      loc_180067F45
0x180067dc1  test    byte ptr [rax+1Ch], 1
0x180067dc5  jz      loc_180067F45
0x180067dcb  mov     edx, 10h
0x180067dd0  jmp     loc_180067CF1
0x180067dd5  mov     r8d, 1
0x180067ddb  lea     rdx, [rsp+100h+var_C8]
0x180067de0  mov     rcx, r15
0x180067de3  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x180067de9  mov     ecx, eax
0x180067deb  call    cs:__imp_FwHResultToWindowsError
0x180067df1  mov     ebx, eax
0x180067df3  test    eax, eax
0x180067df5  jz      short loc_180067E22
0x180067df7  mov     rax, cs:WPP_GLOBAL_Control
0x180067dfe  lea     rcx, WPP_GLOBAL_Control
0x180067e05  cmp     rax, rcx
0x180067e08  jz      loc_180067F45
0x180067e0e  test    byte ptr [rax+1Ch], 1
0x180067e12  jz      loc_180067F45
0x180067e18  mov     edx, 11h
0x180067e1d  jmp     loc_180067CF1
0x180067e22  mov     r8d, 1
0x180067e28  lea     rdx, [rsp+100h+var_C0]
0x180067e2d  mov     rcx, r12
0x180067e30  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x180067e36  mov     ecx, eax
0x180067e38  call    cs:__imp_FwHResultToWindowsError
0x180067e3e  mov     ebx, eax
0x180067e40  test    eax, eax
0x180067e42  jz      short loc_180067E6F
0x180067e44  mov     rax, cs:WPP_GLOBAL_Control
0x180067e4b  lea     rcx, WPP_GLOBAL_Control
0x180067e52  cmp     rax, rcx
0x180067e55  jz      loc_180067F45
0x180067e5b  test    byte ptr [rax+1Ch], 1
0x180067e5f  jz      loc_180067F45
0x180067e65  mov     edx, 12h
0x180067e6a  jmp     loc_180067CF1
0x180067e6f  mov     r8d, 1
0x180067e75  lea     rdx, [rbp+3Fh+var_B8]
0x180067e79  mov     rcx, r13
0x180067e7c  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x180067e82  mov     ecx, eax
0x180067e84  call    cs:__imp_FwHResultToWindowsError
0x180067e8a  mov     ebx, eax
0x180067e8c  test    eax, eax
0x180067e8e  jz      short loc_180067EBB
0x180067e90  mov     rax, cs:WPP_GLOBAL_Control
0x180067e97  lea     rcx, WPP_GLOBAL_Control
0x180067e9e  cmp     rax, rcx
0x180067ea1  jz      loc_180067F45
0x180067ea7  test    byte ptr [rax+1Ch], 1
0x180067eab  jz      loc_180067F45
0x180067eb1  mov     edx, 13h
0x180067eb6  jmp     loc_180067CF1
0x180067ebb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180067ec2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x180067ec7  mov     rdx, [rsp+100h+var_D8]; unsigned __int16 *
0x180067ecc  lea     rcx, [rbp+3Fh+var_A0]; struct _EVENT_DATA_DESCRIPTOR *
0x180067ed0  test    al, al
0x180067ed2  mov     qword ptr [rbp+3Fh+var_B0.Size], 4
0x180067eda  lea     rax, [rbp+3Fh+arg_0]
0x180067ede  mov     [rbp+3Fh+var_B0.Ptr], rax
0x180067ee2  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180067ee7  mov     rdx, [rsp+100h+var_D0]; unsigned __int16 *
0x180067eec  lea     rcx, [rbp+3Fh+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x180067ef0  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180067ef5  mov     rdx, [rsp+100h+var_C8]; unsigned __int16 *
0x180067efa  lea     rcx, [rbp+3Fh+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x180067efe  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180067f03  mov     rdx, [rsp+100h+var_C0]; unsigned __int16 *
0x180067f08  lea     rcx, [rbp+3Fh+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x180067f0c  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180067f11  mov     rdx, [rbp+3Fh+var_B8]; unsigned __int16 *
0x180067f15  lea     rcx, [rbp+3Fh+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x180067f19  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180067f1e  lea     rax, [rbp+3Fh+arg_30]
0x180067f22  mov     [rbp+3Fh+var_48], 4
0x180067f2a  lea     r8, [rbp+3Fh+var_B0]; struct _EVENT_DATA_DESCRIPTOR *
0x180067f2e  mov     [rbp+3Fh+var_50], rax
0x180067f32  mov     edx, 7; unsigned int
0x180067f37  lea     rcx, NetIsoHttpProxyChangedEvent; struct _EVENT_DESCRIPTOR *
0x180067f3e  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180067f43  mov     ebx, eax
0x180067f45  mov     rcx, [rsp+100h+var_D8]
0x180067f4a  call    cs:__imp_FwFree
0x180067f50  mov     rcx, [rsp+100h+var_D0]
0x180067f55  mov     [rsp+100h+var_D8], 0
0x180067f5e  call    cs:__imp_FwFree
0x180067f64  mov     rcx, [rsp+100h+var_C8]
0x180067f69  mov     [rsp+100h+var_D0], 0
0x180067f72  call    cs:__imp_FwFree
0x180067f78  mov     rcx, [rsp+100h+var_C0]
0x180067f7d  mov     [rsp+100h+var_C8], 0
0x180067f86  call    cs:__imp_FwFree
0x180067f8c  mov     rcx, [rbp+3Fh+var_B8]
0x180067f90  mov     [rsp+100h+var_C0], 0
0x180067f99  call    cs:__imp_FwFree
0x180067f9f  mov     eax, ebx
0x180067fa1  mov     rcx, [rbp+3Fh+var_40]
0x180067fa5  xor     rcx, rsp; StackCookie
0x180067fa8  call    __security_check_cookie
0x180067fad  add     rsp, 0D0h
0x180067fb4  pop     r15
0x180067fb6  pop     r14
0x180067fb8  pop     r13
0x180067fba  pop     r12
0x180067fbc  pop     rsi
0x180067fbd  pop     rbx
0x180067fbe  pop     rbp
0x180067fbf  retn
```

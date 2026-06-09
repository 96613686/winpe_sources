# FwEventCapabilityDefinitionChanged

- ea: `0x18000df3c`
- end: `0x18000e0b4`
- name: `FwEventCapabilityDefinitionChanged`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c260`

## callees

- `0x18000af3c`
- `0x18000df3c`
- `0x180029b48`
- `0x180067fc8`
- `0x18006f520`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000e08a`
- `ntdll!EtwEventWrite` at `0x18000e08a`
- `ntdll!EtwEventEnabled` at `0x18000df7d`
- `ntdll!EtwEventEnabled` at `0x18000e06a`
- `ntdll!EtwEventEnabled` at `0x18000df7d`
- `ntdll!EtwEventEnabled` at `0x18000e06a`
- `fwbase!FwHResultToWindowsError` at `0x18000dfda`
- `fwbase!FwHResultToWindowsError` at `0x18000dfda`
- `fwbase!FwFree` at `0x18000e096`
- `fwbase!FwFree` at `0x18000e096`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18000dfd2`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18000dfd2`

## pseudocode

```c
__int64 __fastcall FwEventCapabilityDefinitionChanged(int a1, int a2, int a3, __int64 a4)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int OpenPortorAuthAppAddrAsString; // eax
  unsigned __int16 *v11; // [rsp+28h] [rbp-19h] BYREF
  _QWORD v12[6]; // [rsp+38h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+68h] [rbp+27h] BYREF
  int v14; // [rsp+A8h] [rbp+67h] BYREF
  int v15; // [rsp+B0h] [rbp+6Fh] BYREF
  int v16; // [rsp+B8h] [rbp+77h] BYREF

  v16 = a3;
  v15 = a2;
  v14 = a1;
  v11 = 0;
  if ( (unsigned __int8)EtwEventEnabled(qword_180131410, NetIsoCapabilityDefinitionChangedEvent) )
  {
    OpenPortorAuthAppAddrAsString = GetOpenPortorAuthAppAddrAsString(a4, &v11, 1);
    v5 = FwHResultToWindowsError(OpenPortorAuthAppAddrAsString);
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 27;
        v8 = v5;
        goto LABEL_5;
      }
    }
    else
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
      v12[0] = &v14;
      v12[1] = 4;
      v12[2] = &v15;
      v12[4] = &v16;
      v12[3] = 4;
      v12[5] = 4;
      FwSerializeStringEventParam(&v13, v11);
      v5 = 0;
      if ( (unsigned __int8)EtwEventEnabled(qword_180131410, NetIsoCapabilityDefinitionChangedEvent) )
        v5 = EtwEventWrite(qword_180131410, NetIsoCapabilityDefinitionChangedEvent, 4, v12);
    }
  }
  else
  {
    v5 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 26;
      v8 = 0;
LABEL_5:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids, v8);
    }
  }
  FwFree(v11);
  return v5;
}

```

## disassembly

```asm
0x18000df3c  mov     rax, rsp
0x18000df3f  mov     [rax+18h], r8d
0x18000df43  mov     [rax+10h], edx
0x18000df46  mov     [rax+8], ecx
0x18000df49  push    rbp
0x18000df4a  push    rbx
0x18000df4b  lea     rbp, [rax-5Fh]
0x18000df4f  sub     rsp, 88h
0x18000df56  mov     rax, cs:__security_cookie
0x18000df5d  xor     rax, rsp
0x18000df60  mov     [rbp+57h+var_20], rax
0x18000df64  mov     rcx, cs:qword_180131410
0x18000df6b  lea     rdx, NetIsoCapabilityDefinitionChangedEvent
0x18000df72  mov     rbx, r9
0x18000df75  mov     [rbp+57h+var_70], 0
0x18000df7d  call    cs:__imp_EtwEventEnabled
0x18000df83  test    al, al
0x18000df85  jnz     short loc_18000DFC5
0x18000df87  xor     ebx, ebx
0x18000df89  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df90  lea     rax, WPP_GLOBAL_Control
0x18000df97  cmp     rcx, rax
0x18000df9a  jz      loc_18000E092
0x18000dfa0  test    byte ptr [rcx+1Ch], 1
0x18000dfa4  jz      loc_18000E092
0x18000dfaa  lea     edx, [rbx+1Ah]
0x18000dfad  xor     r9d, r9d
0x18000dfb0  mov     rcx, [rcx+10h]
0x18000dfb4  lea     r8, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids
0x18000dfbb  call    WPP_SF_d
0x18000dfc0  jmp     loc_18000E092
0x18000dfc5  mov     r8d, 1
0x18000dfcb  lea     rdx, [rbp+57h+var_70]
0x18000dfcf  mov     rcx, rbx
0x18000dfd2  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18000dfd8  mov     ecx, eax
0x18000dfda  call    cs:__imp_FwHResultToWindowsError
0x18000dfe0  mov     ebx, eax
0x18000dfe2  test    eax, eax
0x18000dfe4  jz      short loc_18000E011
0x18000dfe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfed  lea     rax, WPP_GLOBAL_Control
0x18000dff4  cmp     rcx, rax
0x18000dff7  jz      loc_18000E092
0x18000dffd  test    byte ptr [rcx+1Ch], 1
0x18000e001  jz      loc_18000E092
0x18000e007  mov     edx, 1Bh
0x18000e00c  mov     r9d, ebx
0x18000e00f  jmp     short loc_18000DFB0
0x18000e011  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18000e018  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18000e01d  mov     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18000e021  lea     rax, [rbp+57h+arg_0]
0x18000e025  mov     [rbp+57h+var_60], rax
0x18000e029  lea     rcx, [rbp+57h+var_30]; struct _EVENT_DATA_DESCRIPTOR *
0x18000e02d  lea     rax, [rbp+57h+arg_8]
0x18000e031  mov     [rbp+57h+var_58], 4
0x18000e039  mov     [rbp+57h+var_50], rax
0x18000e03d  lea     rax, [rbp+57h+arg_10]
0x18000e041  mov     [rbp+57h+var_40], rax
0x18000e045  mov     [rbp+57h+var_48], 4
0x18000e04d  mov     [rbp+57h+var_38], 4
0x18000e055  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18000e05a  mov     rcx, cs:qword_180131410
0x18000e061  lea     rdx, NetIsoCapabilityDefinitionChangedEvent
0x18000e068  xor     ebx, ebx
0x18000e06a  call    cs:__imp_EtwEventEnabled
0x18000e070  test    al, al
0x18000e072  jz      short loc_18000E092
0x18000e074  mov     rcx, cs:qword_180131410
0x18000e07b  lea     r9, [rbp+57h+var_60]
0x18000e07f  lea     r8d, [rbx+4]
0x18000e083  lea     rdx, NetIsoCapabilityDefinitionChangedEvent
0x18000e08a  call    cs:__imp_EtwEventWrite
0x18000e090  mov     ebx, eax
0x18000e092  mov     rcx, [rbp+57h+var_70]
0x18000e096  call    cs:__imp_FwFree
0x18000e09c  mov     eax, ebx
0x18000e09e  mov     rcx, [rbp+57h+var_20]
0x18000e0a2  xor     rcx, rsp; StackCookie
0x18000e0a5  call    __security_check_cookie
0x18000e0aa  add     rsp, 88h
0x18000e0b1  pop     rbx
0x18000e0b2  pop     rbp
0x18000e0b3  retn
```

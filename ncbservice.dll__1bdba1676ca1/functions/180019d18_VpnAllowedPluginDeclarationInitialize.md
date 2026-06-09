# VpnAllowedPluginDeclarationInitialize

- ea: `0x180019d18`
- end: `0x180019f8c`
- name: `VpnAllowedPluginDeclarationInitialize`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025af0`

## callees

- `0x180018180`
- `0x180019d18`
- `0x18001c500`
- `0x18001c564`
- `0x18001d09c`
- `0x1800316fc`
- `0x180031aec`
- `0x180031b7c`

## import_xrefs

- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180019e00`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180019e2a`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180019e00`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180019e2a`

## string_xrefs

- `0x180019f6f`: `onecoreuap\net\netio\vpnplugin\protocolengine\vpn_proteng_common.c`
- `0x180019d9b`: `VpnAllowedPluginDeclarationInitialize`
- `0x180019f1a`: `VpnAllowedPluginDeclarationInitialize`
- `0x180019f62`: `VpnAllowedPluginDeclarationInitialize`

## pseudocode

```c
__int64 VpnAllowedPluginDeclarationInitialize()
{
  PVOID *v0; // rcx
  unsigned int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rbp
  __int64 v4; // r14
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, WPP_672b541566103487d192f0b957157036_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( g_bAllowedPluginDeclInit == 1 )
  {
    v1 = 0;
    if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 1) != 0 )
      WPP_SF_d(v0[2], 169, WPP_672b541566103487d192f0b957157036_Traceguids, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(0, v2, 1344, "VpnAllowedPluginDeclarationInitialize");
  }
  else
  {
    v3 = 0;
    while ( 1 )
    {
      v4 = 10 * v3;
      v5 = VpnExpandEnvironmentStrings(allowedPluginDecl[10 * v3 + 7]);
      v6 = VpnHResultToWindowsError(v5);
      v1 = v6;
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, WPP_672b541566103487d192f0b957157036_Traceguids, v6);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        {
          v12 = 1350;
          goto LABEL_31;
        }
        goto LABEL_32;
      }
      v7 = AppContainerDeriveSidFromMoniker(allowedPluginDecl[v4], &algn_18004D0B8[v4 * 8]);
      v8 = VpnHResultToWindowsError(v7);
      v1 = v8;
      if ( v8 )
        break;
      v9 = AppContainerDeriveSidFromMoniker(allowedPluginDecl[v4 + 4], &qword_18004D0C8[v4]);
      v10 = VpnHResultToWindowsError(v9);
      v1 = v10;
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_672b541566103487d192f0b957157036_Traceguids, v10);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        {
          v12 = 1358;
LABEL_31:
          TraceVpnWppErrorW32Impl(v1, v11, v12, "VpnAllowedPluginDeclarationInitialize");
          goto LABEL_32;
        }
        goto LABEL_32;
      }
      v3 = (unsigned int)(v3 + 1);
      if ( (unsigned int)v3 >= 4 )
      {
        g_bAllowedPluginDeclInit = 1;
        goto LABEL_32;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_672b541566103487d192f0b957157036_Traceguids, v8);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    {
      v12 = 1354;
      goto LABEL_31;
    }
LABEL_32:
    if ( (v1 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_672b541566103487d192f0b957157036_Traceguids, v1);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorHRImpl(
          v1,
          L"onecoreuap\\net\\netio\\vpnplugin\\protocolengine\\vpn_proteng_common.c",
          1365,
          "VpnAllowedPluginDeclarationInitialize");
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180019d18  push    rbx
0x180019d1a  push    rbp
0x180019d1b  push    r12
0x180019d1d  push    r13
0x180019d1f  push    r14
0x180019d21  sub     rsp, 20h
0x180019d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d2c  lea     r12, WPP_GLOBAL_Control
0x180019d33  lea     r13, WPP_672b541566103487d192f0b957157036_Traceguids
0x180019d3a  cmp     rcx, r12
0x180019d3d  jz      short loc_180019D5D
0x180019d3f  test    byte ptr [rcx+1Ch], 8
0x180019d43  jz      short loc_180019D5D
0x180019d45  mov     rcx, [rcx+10h]
0x180019d49  mov     edx, 0A8h
0x180019d4e  mov     r8, r13
0x180019d51  call    WPP_SF_
0x180019d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d5d  cmp     cs:g_bAllowedPluginDeclInit, 1
0x180019d64  jnz     short loc_180019DB4
0x180019d66  xor     ebx, ebx
0x180019d68  cmp     rcx, r12
0x180019d6b  jz      short loc_180019D87
0x180019d6d  test    byte ptr [rcx+1Ch], 1
0x180019d71  jz      short loc_180019D87
0x180019d73  mov     rcx, [rcx+10h]
0x180019d77  mov     edx, 0A9h
0x180019d7c  xor     r9d, r9d
0x180019d7f  mov     r8, r13
0x180019d82  call    WPP_SF_d
0x180019d87  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x180019d8e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x180019d93  test    al, al
0x180019d95  jz      loc_180019F7D
0x180019d9b  lea     r9, aVpnallowedplug_1; "VpnAllowedPluginDeclarationInitialize"
0x180019da2  xor     ecx, ecx
0x180019da4  mov     r8d, 540h
0x180019daa  call    TraceVpnWppErrorW32Impl
0x180019daf  jmp     loc_180019F7D
0x180019db4  xor     ebp, ebp
0x180019db6  lea     rcx, allowedPluginDecl
0x180019dbd  lea     rdx, [rcx+40h]
0x180019dc1  lea     r14, ds:0[rbp*4]
0x180019dc9  add     r14, rbp
0x180019dcc  shl     r14, 4
0x180019dd0  add     rdx, r14
0x180019dd3  mov     rcx, [r14+rcx+38h]; lpSrc
0x180019dd8  call    VpnExpandEnvironmentStrings
0x180019ddd  mov     ecx, eax
0x180019ddf  call    VpnHResultToWindowsError
0x180019de4  mov     ebx, eax
0x180019de6  test    eax, eax
0x180019de8  jnz     loc_180019EDE
0x180019dee  lea     rcx, allowedPluginDecl
0x180019df5  lea     rdx, [rcx+18h]
0x180019df9  mov     rcx, [r14+rcx]
0x180019dfd  add     rdx, r14
0x180019e00  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180019e06  mov     ecx, eax
0x180019e08  call    VpnHResultToWindowsError
0x180019e0d  mov     ebx, eax
0x180019e0f  test    eax, eax
0x180019e11  jnz     loc_180019EA0
0x180019e17  lea     rax, allowedPluginDecl
0x180019e1e  mov     rcx, [r14+rax+20h]
0x180019e23  lea     rdx, [rax+28h]
0x180019e27  add     rdx, r14
0x180019e2a  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180019e30  mov     ecx, eax
0x180019e32  call    VpnHResultToWindowsError
0x180019e37  mov     ebx, eax
0x180019e39  test    eax, eax
0x180019e3b  jnz     short loc_180019E5E
0x180019e3d  inc     ebp
0x180019e3f  lea     rcx, allowedPluginDecl
0x180019e46  cmp     ebp, 4
0x180019e49  jb      loc_180019DBD
0x180019e4f  mov     cs:g_bAllowedPluginDeclInit, 1
0x180019e59  jmp     loc_180019F28
0x180019e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e65  cmp     rcx, r12
0x180019e68  jz      short loc_180019E84
0x180019e6a  test    byte ptr [rcx+1Ch], 1
0x180019e6e  jz      short loc_180019E84
0x180019e70  mov     rcx, [rcx+10h]
0x180019e74  mov     edx, 0ACh
0x180019e79  mov     r9d, ebx
0x180019e7c  mov     r8, r13
0x180019e7f  call    WPP_SF_d
0x180019e84  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x180019e8b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x180019e90  test    al, al
0x180019e92  jz      loc_180019F28
0x180019e98  mov     r8d, 54Eh
0x180019e9e  jmp     short loc_180019F1A
0x180019ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ea7  cmp     rcx, r12
0x180019eaa  jz      short loc_180019EC6
0x180019eac  test    byte ptr [rcx+1Ch], 1
0x180019eb0  jz      short loc_180019EC6
0x180019eb2  mov     rcx, [rcx+10h]
0x180019eb6  mov     edx, 0ABh
0x180019ebb  mov     r9d, ebx
0x180019ebe  mov     r8, r13
0x180019ec1  call    WPP_SF_d
0x180019ec6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x180019ecd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x180019ed2  test    al, al
0x180019ed4  jz      short loc_180019F28
0x180019ed6  mov     r8d, 54Ah
0x180019edc  jmp     short loc_180019F1A
0x180019ede  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ee5  cmp     rcx, r12
0x180019ee8  jz      short loc_180019F04
0x180019eea  test    byte ptr [rcx+1Ch], 1
0x180019eee  jz      short loc_180019F04
0x180019ef0  mov     rcx, [rcx+10h]
0x180019ef4  mov     edx, 0AAh
0x180019ef9  mov     r9d, ebx
0x180019efc  mov     r8, r13
0x180019eff  call    WPP_SF_d
0x180019f04  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x180019f0b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x180019f10  test    al, al
0x180019f12  jz      short loc_180019F28
0x180019f14  mov     r8d, 546h
0x180019f1a  lea     r9, aVpnallowedplug_1; "VpnAllowedPluginDeclarationInitialize"
0x180019f21  mov     ecx, ebx
0x180019f23  call    TraceVpnWppErrorW32Impl
0x180019f28  test    ebx, ebx
0x180019f2a  jns     short loc_180019F7D
0x180019f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f33  cmp     rcx, r12
0x180019f36  jz      short loc_180019F52
0x180019f38  test    byte ptr [rcx+1Ch], 8
0x180019f3c  jz      short loc_180019F52
0x180019f3e  mov     rcx, [rcx+10h]
0x180019f42  mov     edx, 0ADh
0x180019f47  mov     r9d, ebx
0x180019f4a  mov     r8, r13
0x180019f4d  call    WPP_SF_d
0x180019f52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x180019f59  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x180019f5e  test    al, al
0x180019f60  jz      short loc_180019F7D
0x180019f62  lea     r9, aVpnallowedplug_1; "VpnAllowedPluginDeclarationInitialize"
0x180019f69  mov     r8d, 555h
0x180019f6f  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prot"...
0x180019f76  mov     ecx, ebx
0x180019f78  call    TraceVpnWppErrorHRImpl
0x180019f7d  mov     eax, ebx
0x180019f7f  add     rsp, 20h
0x180019f83  pop     r14
0x180019f85  pop     r13
0x180019f87  pop     r12
0x180019f89  pop     rbp
0x180019f8a  pop     rbx
0x180019f8b  retn
```

# FwEventCapabilityDefinitionChanged

- ea: `0x18000d860`
- end: `0x18000d9fd`
- name: `FwEventCapabilityDefinitionChanged`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bb00`

## callees

- `0x18000a710`
- `0x18000d860`
- `0x18002d340`
- `0x18006b940`
- `0x1800729c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000d9c6`
- `ntdll!EtwEventWrite` at `0x18000d9c6`
- `ntdll!EtwEventEnabled` at `0x18000d8a1`
- `ntdll!EtwEventEnabled` at `0x18000d9a0`
- `ntdll!EtwEventEnabled` at `0x18000d8a1`
- `ntdll!EtwEventEnabled` at `0x18000d9a0`
- `fwbase!FwHResultToWindowsError` at `0x18000d90a`
- `fwbase!FwHResultToWindowsError` at `0x18000d90a`
- `fwbase!FwFree` at `0x18000d9d8`
- `fwbase!FwFree` at `0x18000d9d8`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18000d8fc`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18000d8fc`

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
  if ( (unsigned __int8)EtwEventEnabled(qword_1801375D0, NetIsoCapabilityDefinitionChangedEvent) )
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
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
      v12[0] = &v14;
      v12[1] = 4;
      v12[2] = &v15;
      v12[4] = &v16;
      v12[3] = 4;
      v12[5] = 4;
      FwSerializeStringEventParam(&v13, v11);
      v5 = 0;
      if ( (unsigned __int8)EtwEventEnabled(qword_1801375D0, NetIsoCapabilityDefinitionChangedEvent) )
        v5 = EtwEventWrite(qword_1801375D0, NetIsoCapabilityDefinitionChangedEvent, 4, v12);
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
0x18000d860  mov     rax, rsp
0x18000d863  mov     [rax+18h], r8d
0x18000d867  mov     [rax+10h], edx
0x18000d86a  mov     [rax+8], ecx
0x18000d86d  push    rbp
0x18000d86e  push    rbx
0x18000d86f  lea     rbp, [rax-5Fh]
0x18000d873  sub     rsp, 88h
0x18000d87a  mov     rax, cs:__security_cookie
0x18000d881  xor     rax, rsp
0x18000d884  mov     [rbp+57h+var_20], rax
0x18000d888  mov     rcx, cs:qword_1801375D0
0x18000d88f  lea     rdx, NetIsoCapabilityDefinitionChangedEvent
0x18000d896  mov     rbx, r9
0x18000d899  mov     [rbp+57h+var_70], 0
0x18000d8a1  call    cs:__imp_EtwEventEnabled
0x18000d8a8  nop     dword ptr [rax+rax+00h]
0x18000d8ad  test    al, al
0x18000d8af  jnz     short loc_18000D8EF
0x18000d8b1  xor     ebx, ebx
0x18000d8b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8ba  lea     rax, WPP_GLOBAL_Control
0x18000d8c1  cmp     rcx, rax
0x18000d8c4  jz      loc_18000D9D4
0x18000d8ca  test    byte ptr [rcx+1Ch], 1
0x18000d8ce  jz      loc_18000D9D4
0x18000d8d4  lea     edx, [rbx+1Ah]
0x18000d8d7  xor     r9d, r9d
0x18000d8da  mov     rcx, [rcx+10h]
0x18000d8de  lea     r8, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids
0x18000d8e5  call    WPP_SF_d
0x18000d8ea  jmp     loc_18000D9D4
0x18000d8ef  mov     r8d, 1
0x18000d8f5  lea     rdx, [rbp+57h+var_70]
0x18000d8f9  mov     rcx, rbx
0x18000d8fc  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18000d903  nop     dword ptr [rax+rax+00h]
0x18000d908  mov     ecx, eax
0x18000d90a  call    cs:__imp_FwHResultToWindowsError
0x18000d911  nop     dword ptr [rax+rax+00h]
0x18000d916  mov     ebx, eax
0x18000d918  test    eax, eax
0x18000d91a  jz      short loc_18000D947
0x18000d91c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d923  lea     rax, WPP_GLOBAL_Control
0x18000d92a  cmp     rcx, rax
0x18000d92d  jz      loc_18000D9D4
0x18000d933  test    byte ptr [rcx+1Ch], 1
0x18000d937  jz      loc_18000D9D4
0x18000d93d  mov     edx, 1Bh
0x18000d942  mov     r9d, ebx
0x18000d945  jmp     short loc_18000D8DA
0x18000d947  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18000d94e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18000d953  mov     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18000d957  lea     rax, [rbp+57h+arg_0]
0x18000d95b  mov     [rbp+57h+var_60], rax
0x18000d95f  lea     rcx, [rbp+57h+var_30]; struct _EVENT_DATA_DESCRIPTOR *
0x18000d963  lea     rax, [rbp+57h+arg_8]
0x18000d967  mov     [rbp+57h+var_58], 4
0x18000d96f  mov     [rbp+57h+var_50], rax
0x18000d973  lea     rax, [rbp+57h+arg_10]
0x18000d977  mov     [rbp+57h+var_40], rax
0x18000d97b  mov     [rbp+57h+var_48], 4
0x18000d983  mov     [rbp+57h+var_38], 4
0x18000d98b  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18000d990  mov     rcx, cs:qword_1801375D0
0x18000d997  lea     rdx, NetIsoCapabilityDefinitionChangedEvent
0x18000d99e  xor     ebx, ebx
0x18000d9a0  call    cs:__imp_EtwEventEnabled
0x18000d9a7  nop     dword ptr [rax+rax+00h]
0x18000d9ac  test    al, al
0x18000d9ae  jz      short loc_18000D9D4
0x18000d9b0  mov     rcx, cs:qword_1801375D0
0x18000d9b7  lea     r9, [rbp+57h+var_60]
0x18000d9bb  lea     r8d, [rbx+4]
0x18000d9bf  lea     rdx, NetIsoCapabilityDefinitionChangedEvent
0x18000d9c6  call    cs:__imp_EtwEventWrite
0x18000d9cd  nop     dword ptr [rax+rax+00h]
0x18000d9d2  mov     ebx, eax
0x18000d9d4  mov     rcx, [rbp+57h+var_70]
0x18000d9d8  call    cs:__imp_FwFree
0x18000d9df  nop     dword ptr [rax+rax+00h]
0x18000d9e4  mov     eax, ebx
0x18000d9e6  mov     rcx, [rbp+57h+var_20]
0x18000d9ea  xor     rcx, rsp; StackCookie
0x18000d9ed  call    __security_check_cookie
0x18000d9f2  add     rsp, 88h
0x18000d9f9  pop     rbx
0x18000d9fa  pop     rbp
0x18000d9fb  retn
```

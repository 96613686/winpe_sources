# FwEventHttpProxyChanged

- ea: `0x18006b578`
- end: `0x18006b937`
- name: `FwEventHttpProxyChanged`
- size: `959`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180045e40`

## callees

- `0x18000a710`
- `0x18002d340`
- `0x180048250`
- `0x18004f864`
- `0x18006b578`
- `0x18006b940`
- `0x1800729c0`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18006b673`
- `fwbase!FwHResultToWindowsError` at `0x18006b6cc`
- `fwbase!FwHResultToWindowsError` at `0x18006b725`
- `fwbase!FwHResultToWindowsError` at `0x18006b77e`
- `fwbase!FwHResultToWindowsError` at `0x18006b7d6`
- `fwbase!FwHResultToWindowsError` at `0x18006b673`
- `fwbase!FwHResultToWindowsError` at `0x18006b6cc`
- `fwbase!FwHResultToWindowsError` at `0x18006b725`
- `fwbase!FwHResultToWindowsError` at `0x18006b77e`
- `fwbase!FwHResultToWindowsError` at `0x18006b7d6`
- `fwbase!FwFree` at `0x18006b8a2`
- `fwbase!FwFree` at `0x18006b8bc`
- `fwbase!FwFree` at `0x18006b8d6`
- `fwbase!FwFree` at `0x18006b8f0`
- `fwbase!FwFree` at `0x18006b909`
- `fwbase!FwFree` at `0x18006b8a2`
- `fwbase!FwFree` at `0x18006b8bc`
- `fwbase!FwFree` at `0x18006b8d6`
- `fwbase!FwFree` at `0x18006b8f0`
- `fwbase!FwFree` at `0x18006b909`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b665`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b6be`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b717`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b770`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b7c8`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b665`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b6be`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b717`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b770`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b7c8`

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
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
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
0x18006b578  mov     [rsp-8+arg_0], ecx
0x18006b57c  push    rbp
0x18006b57d  push    rbx
0x18006b57e  push    rsi
0x18006b57f  push    r12
0x18006b581  push    r13
0x18006b583  push    r14
0x18006b585  push    r15
0x18006b587  lea     rbp, [rsp-0Fh]
0x18006b58c  sub     rsp, 0D0h
0x18006b593  mov     rax, cs:__security_cookie
0x18006b59a  xor     rax, rsp
0x18006b59d  mov     [rbp+3Fh+var_40], rax
0x18006b5a1  mov     r12, [rbp+3Fh+arg_20]
0x18006b5a5  lea     rcx, NetIsoHttpProxyChangedEvent
0x18006b5ac  mov     r13, [rbp+3Fh+arg_28]
0x18006b5b0  xor     eax, eax
0x18006b5b2  mov     rsi, rdx
0x18006b5b5  mov     [rsp+100h+var_E0], eax
0x18006b5b9  lea     rdx, [rsp+100h+var_E0]
0x18006b5be  mov     [rsp+100h+var_D8], rax
0x18006b5c3  mov     [rsp+100h+var_D0], rax
0x18006b5c8  mov     r15, r9
0x18006b5cb  mov     [rsp+100h+var_C8], rax
0x18006b5d0  mov     r14, r8
0x18006b5d3  mov     [rsp+100h+var_C0], rax
0x18006b5d8  mov     [rbp+3Fh+var_B8], rax
0x18006b5dc  call    FwIsEventEnbled
0x18006b5e1  mov     ebx, eax
0x18006b5e3  test    eax, eax
0x18006b5e5  jz      short loc_18006B625
0x18006b5e7  mov     rax, cs:WPP_GLOBAL_Control
0x18006b5ee  lea     rcx, WPP_GLOBAL_Control
0x18006b5f5  cmp     rax, rcx
0x18006b5f8  jz      loc_18006B89D
0x18006b5fe  test    byte ptr [rax+1Ch], 1
0x18006b602  jz      loc_18006B89D
0x18006b608  mov     edx, 0Dh
0x18006b60d  mov     r9d, ebx
0x18006b610  mov     rcx, [rax+10h]
0x18006b614  lea     r8, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids
0x18006b61b  call    WPP_SF_d
0x18006b620  jmp     loc_18006B89D
0x18006b625  cmp     [rsp+100h+var_E0], 0
0x18006b62a  jnz     short loc_18006B657
0x18006b62c  xor     ebx, ebx
0x18006b62e  mov     rax, cs:WPP_GLOBAL_Control
0x18006b635  lea     rcx, WPP_GLOBAL_Control
0x18006b63c  cmp     rax, rcx
0x18006b63f  jz      loc_18006B89D
0x18006b645  test    byte ptr [rax+1Ch], 1
0x18006b649  jz      loc_18006B89D
0x18006b64f  lea     edx, [rbx+0Eh]
0x18006b652  xor     r9d, r9d
0x18006b655  jmp     short loc_18006B610
0x18006b657  mov     r8d, 1
0x18006b65d  lea     rdx, [rsp+100h+var_D8]
0x18006b662  mov     rcx, rsi
0x18006b665  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18006b66c  nop     dword ptr [rax+rax+00h]
0x18006b671  mov     ecx, eax
0x18006b673  call    cs:__imp_FwHResultToWindowsError
0x18006b67a  nop     dword ptr [rax+rax+00h]
0x18006b67f  mov     ebx, eax
0x18006b681  test    eax, eax
0x18006b683  jz      short loc_18006B6B0
0x18006b685  mov     rax, cs:WPP_GLOBAL_Control
0x18006b68c  lea     rcx, WPP_GLOBAL_Control
0x18006b693  cmp     rax, rcx
0x18006b696  jz      loc_18006B89D
0x18006b69c  test    byte ptr [rax+1Ch], 1
0x18006b6a0  jz      loc_18006B89D
0x18006b6a6  mov     edx, 0Fh
0x18006b6ab  jmp     loc_18006B60D
0x18006b6b0  mov     r8d, 1
0x18006b6b6  lea     rdx, [rsp+100h+var_D0]
0x18006b6bb  mov     rcx, r14
0x18006b6be  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18006b6c5  nop     dword ptr [rax+rax+00h]
0x18006b6ca  mov     ecx, eax
0x18006b6cc  call    cs:__imp_FwHResultToWindowsError
0x18006b6d3  nop     dword ptr [rax+rax+00h]
0x18006b6d8  mov     ebx, eax
0x18006b6da  test    eax, eax
0x18006b6dc  jz      short loc_18006B709
0x18006b6de  mov     rax, cs:WPP_GLOBAL_Control
0x18006b6e5  lea     rcx, WPP_GLOBAL_Control
0x18006b6ec  cmp     rax, rcx
0x18006b6ef  jz      loc_18006B89D
0x18006b6f5  test    byte ptr [rax+1Ch], 1
0x18006b6f9  jz      loc_18006B89D
0x18006b6ff  mov     edx, 10h
0x18006b704  jmp     loc_18006B60D
0x18006b709  mov     r8d, 1
0x18006b70f  lea     rdx, [rsp+100h+var_C8]
0x18006b714  mov     rcx, r15
0x18006b717  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18006b71e  nop     dword ptr [rax+rax+00h]
0x18006b723  mov     ecx, eax
0x18006b725  call    cs:__imp_FwHResultToWindowsError
0x18006b72c  nop     dword ptr [rax+rax+00h]
0x18006b731  mov     ebx, eax
0x18006b733  test    eax, eax
0x18006b735  jz      short loc_18006B762
0x18006b737  mov     rax, cs:WPP_GLOBAL_Control
0x18006b73e  lea     rcx, WPP_GLOBAL_Control
0x18006b745  cmp     rax, rcx
0x18006b748  jz      loc_18006B89D
0x18006b74e  test    byte ptr [rax+1Ch], 1
0x18006b752  jz      loc_18006B89D
0x18006b758  mov     edx, 11h
0x18006b75d  jmp     loc_18006B60D
0x18006b762  mov     r8d, 1
0x18006b768  lea     rdx, [rsp+100h+var_C0]
0x18006b76d  mov     rcx, r12
0x18006b770  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18006b777  nop     dword ptr [rax+rax+00h]
0x18006b77c  mov     ecx, eax
0x18006b77e  call    cs:__imp_FwHResultToWindowsError
0x18006b785  nop     dword ptr [rax+rax+00h]
0x18006b78a  mov     ebx, eax
0x18006b78c  test    eax, eax
0x18006b78e  jz      short loc_18006B7BB
0x18006b790  mov     rax, cs:WPP_GLOBAL_Control
0x18006b797  lea     rcx, WPP_GLOBAL_Control
0x18006b79e  cmp     rax, rcx
0x18006b7a1  jz      loc_18006B89D
0x18006b7a7  test    byte ptr [rax+1Ch], 1
0x18006b7ab  jz      loc_18006B89D
0x18006b7b1  mov     edx, 12h
0x18006b7b6  jmp     loc_18006B60D
0x18006b7bb  mov     r8d, 1
0x18006b7c1  lea     rdx, [rbp+3Fh+var_B8]
0x18006b7c5  mov     rcx, r13
0x18006b7c8  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18006b7cf  nop     dword ptr [rax+rax+00h]
0x18006b7d4  mov     ecx, eax
0x18006b7d6  call    cs:__imp_FwHResultToWindowsError
0x18006b7dd  nop     dword ptr [rax+rax+00h]
0x18006b7e2  mov     ebx, eax
0x18006b7e4  test    eax, eax
0x18006b7e6  jz      short loc_18006B813
0x18006b7e8  mov     rax, cs:WPP_GLOBAL_Control
0x18006b7ef  lea     rcx, WPP_GLOBAL_Control
0x18006b7f6  cmp     rax, rcx
0x18006b7f9  jz      loc_18006B89D
0x18006b7ff  test    byte ptr [rax+1Ch], 1
0x18006b803  jz      loc_18006B89D
0x18006b809  mov     edx, 13h
0x18006b80e  jmp     loc_18006B60D
0x18006b813  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18006b81a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18006b81f  mov     rdx, [rsp+100h+var_D8]; unsigned __int16 *
0x18006b824  lea     rcx, [rbp+3Fh+var_A0]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b828  test    al, al
0x18006b82a  mov     qword ptr [rbp+3Fh+var_B0.Size], 4
0x18006b832  lea     rax, [rbp+3Fh+arg_0]
0x18006b836  mov     [rbp+3Fh+var_B0.Ptr], rax
0x18006b83a  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b83f  mov     rdx, [rsp+100h+var_D0]; unsigned __int16 *
0x18006b844  lea     rcx, [rbp+3Fh+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b848  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b84d  mov     rdx, [rsp+100h+var_C8]; unsigned __int16 *
0x18006b852  lea     rcx, [rbp+3Fh+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b856  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b85b  mov     rdx, [rsp+100h+var_C0]; unsigned __int16 *
0x18006b860  lea     rcx, [rbp+3Fh+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b864  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b869  mov     rdx, [rbp+3Fh+var_B8]; unsigned __int16 *
0x18006b86d  lea     rcx, [rbp+3Fh+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b871  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b876  lea     rax, [rbp+3Fh+arg_30]
0x18006b87a  mov     [rbp+3Fh+var_48], 4
0x18006b882  lea     r8, [rbp+3Fh+var_B0]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b886  mov     [rbp+3Fh+var_50], rax
0x18006b88a  mov     edx, 7; unsigned int
0x18006b88f  lea     rcx, NetIsoHttpProxyChangedEvent; struct _EVENT_DESCRIPTOR *
0x18006b896  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18006b89b  mov     ebx, eax
0x18006b89d  mov     rcx, [rsp+100h+var_D8]
0x18006b8a2  call    cs:__imp_FwFree
0x18006b8a9  nop     dword ptr [rax+rax+00h]
0x18006b8ae  mov     rcx, [rsp+100h+var_D0]
0x18006b8b3  mov     [rsp+100h+var_D8], 0
0x18006b8bc  call    cs:__imp_FwFree
0x18006b8c3  nop     dword ptr [rax+rax+00h]
0x18006b8c8  mov     rcx, [rsp+100h+var_C8]
0x18006b8cd  mov     [rsp+100h+var_D0], 0
0x18006b8d6  call    cs:__imp_FwFree
0x18006b8dd  nop     dword ptr [rax+rax+00h]
0x18006b8e2  mov     rcx, [rsp+100h+var_C0]
0x18006b8e7  mov     [rsp+100h+var_C8], 0
0x18006b8f0  call    cs:__imp_FwFree
0x18006b8f7  nop     dword ptr [rax+rax+00h]
0x18006b8fc  mov     rcx, [rbp+3Fh+var_B8]
0x18006b900  mov     [rsp+100h+var_C0], 0
0x18006b909  call    cs:__imp_FwFree
0x18006b910  nop     dword ptr [rax+rax+00h]
0x18006b915  mov     eax, ebx
0x18006b917  mov     rcx, [rbp+3Fh+var_40]
0x18006b91b  xor     rcx, rsp; StackCookie
0x18006b91e  call    __security_check_cookie
0x18006b923  add     rsp, 0D0h
0x18006b92a  pop     r15
0x18006b92c  pop     r14
0x18006b92e  pop     r13
0x18006b930  pop     r12
0x18006b932  pop     rsi
0x18006b933  pop     rbx
0x18006b934  pop     rbp
0x18006b935  retn
```

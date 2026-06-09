# FwEventSubnetsChanged

- ea: `0x18006af3c`
- end: `0x18006b1d6`
- name: `FwEventSubnetsChanged`
- size: `666`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18005bfcc`
- `0x180085600`

## callees

- `0x18000a710`
- `0x18002d340`
- `0x180048250`
- `0x18004f864`
- `0x18006af3c`
- `0x18006b940`
- `0x1800729c0`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18006b028`
- `fwbase!FwHResultToWindowsError` at `0x18006b080`
- `fwbase!FwHResultToWindowsError` at `0x18006b0d8`
- `fwbase!FwHResultToWindowsError` at `0x18006b028`
- `fwbase!FwHResultToWindowsError` at `0x18006b080`
- `fwbase!FwHResultToWindowsError` at `0x18006b0d8`
- `fwbase!FwFree` at `0x18006b17d`
- `fwbase!FwFree` at `0x18006b195`
- `fwbase!FwFree` at `0x18006b1ad`
- `fwbase!FwFree` at `0x18006b17d`
- `fwbase!FwFree` at `0x18006b195`
- `fwbase!FwFree` at `0x18006b1ad`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b01a`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b072`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b0ca`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b01a`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b072`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006b0ca`

## pseudocode

```c
__int64 __fastcall FwEventSubnetsChanged(int a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  unsigned int IsEventEnbled; // ebx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int OpenPortorAuthAppAddrAsString; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  int v16; // [rsp+20h] [rbp-51h] BYREF
  unsigned __int16 *v17; // [rsp+28h] [rbp-49h] BYREF
  unsigned __int16 *v18; // [rsp+30h] [rbp-41h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+40h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+50h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+60h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+70h] [rbp-1h] BYREF
  char *v24; // [rsp+80h] [rbp+Fh]
  __int64 v25; // [rsp+88h] [rbp+17h]
  int v26; // [rsp+D0h] [rbp+5Fh] BYREF

  v26 = a1;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  IsEventEnbled = FwIsEventEnbled(&NetIsoSubnetsChangedEvent, &v16);
  if ( IsEventEnbled )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v10 = 20;
LABEL_5:
      v11 = IsEventEnbled;
LABEL_6:
      WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids, v11);
    }
  }
  else if ( v16 )
  {
    OpenPortorAuthAppAddrAsString = GetOpenPortorAuthAppAddrAsString(a2, &v17, 1);
    IsEventEnbled = FwHResultToWindowsError(OpenPortorAuthAppAddrAsString);
    if ( IsEventEnbled )
    {
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v10 = 22;
        goto LABEL_5;
      }
    }
    else
    {
      v13 = GetOpenPortorAuthAppAddrAsString(a3, &v18, 1);
      IsEventEnbled = FwHResultToWindowsError(v13);
      if ( IsEventEnbled )
      {
        v9 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v10 = 23;
          goto LABEL_5;
        }
      }
      else
      {
        v14 = GetOpenPortorAuthAppAddrAsString(a4, &v19, 1);
        IsEventEnbled = FwHResultToWindowsError(v14);
        if ( !IsEventEnbled )
        {
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
          *(_QWORD *)&v20.Size = 4;
          v20.Ptr = (ULONGLONG)&v26;
          FwSerializeStringEventParam(&v21, v17);
          FwSerializeStringEventParam(&v22, v18);
          FwSerializeStringEventParam(&v23, v19);
          v25 = 4;
          v24 = &a5;
          IsEventEnbled = FwLogEvent(&NetIsoSubnetsChangedEvent, 5u, &v20);
          goto LABEL_24;
        }
        v9 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v10 = 24;
          goto LABEL_5;
        }
      }
    }
  }
  else
  {
    IsEventEnbled = 0;
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v10 = 21;
      v11 = 0;
      goto LABEL_6;
    }
  }
LABEL_24:
  FwFree(v17);
  v17 = 0;
  FwFree(v18);
  v18 = 0;
  FwFree(v19);
  return IsEventEnbled;
}

```

## disassembly

```asm
0x18006af3c  mov     [rsp-8+arg_0], ecx
0x18006af40  push    rbp
0x18006af41  push    rbx
0x18006af42  push    rsi
0x18006af43  push    rdi
0x18006af44  push    r14
0x18006af46  lea     rbp, [rsp-2Fh]
0x18006af4b  sub     rsp, 0A0h
0x18006af52  mov     rax, cs:__security_cookie
0x18006af59  xor     rax, rsp
0x18006af5c  mov     [rbp+4Fh+var_30], rax
0x18006af60  mov     rdi, rdx
0x18006af63  mov     [rbp+4Fh+var_A0], 0
0x18006af6a  lea     rdx, [rbp+4Fh+var_A0]
0x18006af6e  mov     [rbp+4Fh+var_98], 0
0x18006af76  lea     rcx, NetIsoSubnetsChangedEvent
0x18006af7d  mov     [rbp+4Fh+var_90], 0
0x18006af85  mov     r14, r9
0x18006af88  mov     [rbp+4Fh+var_88], 0
0x18006af90  mov     rsi, r8
0x18006af93  call    FwIsEventEnbled
0x18006af98  mov     ebx, eax
0x18006af9a  test    eax, eax
0x18006af9c  jz      short loc_18006AFDC
0x18006af9e  mov     rax, cs:WPP_GLOBAL_Control
0x18006afa5  lea     rcx, WPP_GLOBAL_Control
0x18006afac  cmp     rax, rcx
0x18006afaf  jz      loc_18006B179
0x18006afb5  test    byte ptr [rax+1Ch], 1
0x18006afb9  jz      loc_18006B179
0x18006afbf  mov     edx, 14h
0x18006afc4  mov     r9d, ebx
0x18006afc7  mov     rcx, [rax+10h]
0x18006afcb  lea     r8, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids
0x18006afd2  call    WPP_SF_d
0x18006afd7  jmp     loc_18006B179
0x18006afdc  cmp     [rbp+4Fh+var_A0], 0
0x18006afe0  jnz     short loc_18006B00D
0x18006afe2  xor     ebx, ebx
0x18006afe4  mov     rax, cs:WPP_GLOBAL_Control
0x18006afeb  lea     rcx, WPP_GLOBAL_Control
0x18006aff2  cmp     rax, rcx
0x18006aff5  jz      loc_18006B179
0x18006affb  test    byte ptr [rax+1Ch], 1
0x18006afff  jz      loc_18006B179
0x18006b005  lea     edx, [rbx+15h]
0x18006b008  xor     r9d, r9d
0x18006b00b  jmp     short loc_18006AFC7
0x18006b00d  mov     r8d, 1
0x18006b013  lea     rdx, [rbp+4Fh+var_98]
0x18006b017  mov     rcx, rdi
0x18006b01a  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18006b021  nop     dword ptr [rax+rax+00h]
0x18006b026  mov     ecx, eax
0x18006b028  call    cs:__imp_FwHResultToWindowsError
0x18006b02f  nop     dword ptr [rax+rax+00h]
0x18006b034  mov     ebx, eax
0x18006b036  test    eax, eax
0x18006b038  jz      short loc_18006B065
0x18006b03a  mov     rax, cs:WPP_GLOBAL_Control
0x18006b041  lea     rcx, WPP_GLOBAL_Control
0x18006b048  cmp     rax, rcx
0x18006b04b  jz      loc_18006B179
0x18006b051  test    byte ptr [rax+1Ch], 1
0x18006b055  jz      loc_18006B179
0x18006b05b  mov     edx, 16h
0x18006b060  jmp     loc_18006AFC4
0x18006b065  mov     r8d, 1
0x18006b06b  lea     rdx, [rbp+4Fh+var_90]
0x18006b06f  mov     rcx, rsi
0x18006b072  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18006b079  nop     dword ptr [rax+rax+00h]
0x18006b07e  mov     ecx, eax
0x18006b080  call    cs:__imp_FwHResultToWindowsError
0x18006b087  nop     dword ptr [rax+rax+00h]
0x18006b08c  mov     ebx, eax
0x18006b08e  test    eax, eax
0x18006b090  jz      short loc_18006B0BD
0x18006b092  mov     rax, cs:WPP_GLOBAL_Control
0x18006b099  lea     rcx, WPP_GLOBAL_Control
0x18006b0a0  cmp     rax, rcx
0x18006b0a3  jz      loc_18006B179
0x18006b0a9  test    byte ptr [rax+1Ch], 1
0x18006b0ad  jz      loc_18006B179
0x18006b0b3  mov     edx, 17h
0x18006b0b8  jmp     loc_18006AFC4
0x18006b0bd  mov     r8d, 1
0x18006b0c3  lea     rdx, [rbp+4Fh+var_88]
0x18006b0c7  mov     rcx, r14
0x18006b0ca  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x18006b0d1  nop     dword ptr [rax+rax+00h]
0x18006b0d6  mov     ecx, eax
0x18006b0d8  call    cs:__imp_FwHResultToWindowsError
0x18006b0df  nop     dword ptr [rax+rax+00h]
0x18006b0e4  mov     ebx, eax
0x18006b0e6  test    eax, eax
0x18006b0e8  jz      short loc_18006B10D
0x18006b0ea  mov     rax, cs:WPP_GLOBAL_Control
0x18006b0f1  lea     rcx, WPP_GLOBAL_Control
0x18006b0f8  cmp     rax, rcx
0x18006b0fb  jz      short loc_18006B179
0x18006b0fd  test    byte ptr [rax+1Ch], 1
0x18006b101  jz      short loc_18006B179
0x18006b103  mov     edx, 18h
0x18006b108  jmp     loc_18006AFC4
0x18006b10d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18006b114  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18006b119  mov     rdx, [rbp+4Fh+var_98]; unsigned __int16 *
0x18006b11d  lea     rcx, [rbp+4Fh+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b121  test    al, al
0x18006b123  mov     qword ptr [rbp+4Fh+var_80.Size], 4
0x18006b12b  lea     rax, [rbp+4Fh+arg_0]
0x18006b12f  mov     [rbp+4Fh+var_80.Ptr], rax
0x18006b133  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b138  mov     rdx, [rbp+4Fh+var_90]; unsigned __int16 *
0x18006b13c  lea     rcx, [rbp+4Fh+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b140  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b145  mov     rdx, [rbp+4Fh+var_88]; unsigned __int16 *
0x18006b149  lea     rcx, [rbp+4Fh+var_50]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b14d  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b152  lea     rax, [rbp+4Fh+arg_20]
0x18006b156  mov     [rbp+4Fh+var_38], 4
0x18006b15e  lea     r8, [rbp+4Fh+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b162  mov     [rbp+4Fh+var_40], rax
0x18006b166  mov     edx, 5; unsigned int
0x18006b16b  lea     rcx, NetIsoSubnetsChangedEvent; struct _EVENT_DESCRIPTOR *
0x18006b172  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18006b177  mov     ebx, eax
0x18006b179  mov     rcx, [rbp+4Fh+var_98]
0x18006b17d  call    cs:__imp_FwFree
0x18006b184  nop     dword ptr [rax+rax+00h]
0x18006b189  mov     rcx, [rbp+4Fh+var_90]
0x18006b18d  mov     [rbp+4Fh+var_98], 0
0x18006b195  call    cs:__imp_FwFree
0x18006b19c  nop     dword ptr [rax+rax+00h]
0x18006b1a1  mov     rcx, [rbp+4Fh+var_88]
0x18006b1a5  mov     [rbp+4Fh+var_90], 0
0x18006b1ad  call    cs:__imp_FwFree
0x18006b1b4  nop     dword ptr [rax+rax+00h]
0x18006b1b9  mov     eax, ebx
0x18006b1bb  mov     rcx, [rbp+4Fh+var_30]
0x18006b1bf  xor     rcx, rsp; StackCookie
0x18006b1c2  call    __security_check_cookie
0x18006b1c7  add     rsp, 0A0h
0x18006b1ce  pop     r14
0x18006b1d0  pop     rdi
0x18006b1d1  pop     rsi
0x18006b1d2  pop     rbx
0x18006b1d3  pop     rbp
0x18006b1d4  retn
```

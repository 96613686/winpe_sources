# FwEventSubnetsChanged

- ea: `0x180067674`
- end: `0x1800678d7`
- name: `FwEventSubnetsChanged`
- size: `611`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180057034`
- `0x180081510`

## callees

- `0x18000af3c`
- `0x180029b48`
- `0x180049d98`
- `0x18004c870`
- `0x180067674`
- `0x180067fc8`
- `0x18006f520`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18006775a`
- `fwbase!FwHResultToWindowsError` at `0x1800677a6`
- `fwbase!FwHResultToWindowsError` at `0x1800677f2`
- `fwbase!FwHResultToWindowsError` at `0x18006775a`
- `fwbase!FwHResultToWindowsError` at `0x1800677a6`
- `fwbase!FwHResultToWindowsError` at `0x1800677f2`
- `fwbase!FwFree` at `0x180067891`
- `fwbase!FwFree` at `0x1800678a3`
- `fwbase!FwFree` at `0x1800678b5`
- `fwbase!FwFree` at `0x180067891`
- `fwbase!FwFree` at `0x1800678a3`
- `fwbase!FwFree` at `0x1800678b5`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067752`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006779e`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800677ea`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x180067752`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x18006779e`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800677ea`

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
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
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
0x180067674  mov     [rsp-8+arg_0], ecx
0x180067678  push    rbp
0x180067679  push    rbx
0x18006767a  push    rsi
0x18006767b  push    rdi
0x18006767c  push    r14
0x18006767e  lea     rbp, [rsp-2Fh]
0x180067683  sub     rsp, 0A0h
0x18006768a  mov     rax, cs:__security_cookie
0x180067691  xor     rax, rsp
0x180067694  mov     [rbp+4Fh+var_30], rax
0x180067698  mov     rdi, rdx
0x18006769b  mov     [rbp+4Fh+var_A0], 0
0x1800676a2  lea     rdx, [rbp+4Fh+var_A0]
0x1800676a6  mov     [rbp+4Fh+var_98], 0
0x1800676ae  lea     rcx, NetIsoSubnetsChangedEvent
0x1800676b5  mov     [rbp+4Fh+var_90], 0
0x1800676bd  mov     r14, r9
0x1800676c0  mov     [rbp+4Fh+var_88], 0
0x1800676c8  mov     rsi, r8
0x1800676cb  call    FwIsEventEnbled
0x1800676d0  mov     ebx, eax
0x1800676d2  test    eax, eax
0x1800676d4  jz      short loc_180067714
0x1800676d6  mov     rax, cs:WPP_GLOBAL_Control
0x1800676dd  lea     rcx, WPP_GLOBAL_Control
0x1800676e4  cmp     rax, rcx
0x1800676e7  jz      loc_18006788D
0x1800676ed  test    byte ptr [rax+1Ch], 1
0x1800676f1  jz      loc_18006788D
0x1800676f7  mov     edx, 14h
0x1800676fc  mov     r9d, ebx
0x1800676ff  mov     rcx, [rax+10h]
0x180067703  lea     r8, WPP_cd8e8a94727e3fe3d514260ab96ea5e9_Traceguids
0x18006770a  call    WPP_SF_d
0x18006770f  jmp     loc_18006788D
0x180067714  cmp     [rbp+4Fh+var_A0], 0
0x180067718  jnz     short loc_180067745
0x18006771a  xor     ebx, ebx
0x18006771c  mov     rax, cs:WPP_GLOBAL_Control
0x180067723  lea     rcx, WPP_GLOBAL_Control
0x18006772a  cmp     rax, rcx
0x18006772d  jz      loc_18006788D
0x180067733  test    byte ptr [rax+1Ch], 1
0x180067737  jz      loc_18006788D
0x18006773d  lea     edx, [rbx+15h]
0x180067740  xor     r9d, r9d
0x180067743  jmp     short loc_1800676FF
0x180067745  mov     r8d, 1
0x18006774b  lea     rdx, [rbp+4Fh+var_98]
0x18006774f  mov     rcx, rdi
0x180067752  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x180067758  mov     ecx, eax
0x18006775a  call    cs:__imp_FwHResultToWindowsError
0x180067760  mov     ebx, eax
0x180067762  test    eax, eax
0x180067764  jz      short loc_180067791
0x180067766  mov     rax, cs:WPP_GLOBAL_Control
0x18006776d  lea     rcx, WPP_GLOBAL_Control
0x180067774  cmp     rax, rcx
0x180067777  jz      loc_18006788D
0x18006777d  test    byte ptr [rax+1Ch], 1
0x180067781  jz      loc_18006788D
0x180067787  mov     edx, 16h
0x18006778c  jmp     loc_1800676FC
0x180067791  mov     r8d, 1
0x180067797  lea     rdx, [rbp+4Fh+var_90]
0x18006779b  mov     rcx, rsi
0x18006779e  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x1800677a4  mov     ecx, eax
0x1800677a6  call    cs:__imp_FwHResultToWindowsError
0x1800677ac  mov     ebx, eax
0x1800677ae  test    eax, eax
0x1800677b0  jz      short loc_1800677DD
0x1800677b2  mov     rax, cs:WPP_GLOBAL_Control
0x1800677b9  lea     rcx, WPP_GLOBAL_Control
0x1800677c0  cmp     rax, rcx
0x1800677c3  jz      loc_18006788D
0x1800677c9  test    byte ptr [rax+1Ch], 1
0x1800677cd  jz      loc_18006788D
0x1800677d3  mov     edx, 17h
0x1800677d8  jmp     loc_1800676FC
0x1800677dd  mov     r8d, 1
0x1800677e3  lea     rdx, [rbp+4Fh+var_88]
0x1800677e7  mov     rcx, r14
0x1800677ea  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x1800677f0  mov     ecx, eax
0x1800677f2  call    cs:__imp_FwHResultToWindowsError
0x1800677f8  mov     ebx, eax
0x1800677fa  test    eax, eax
0x1800677fc  jz      short loc_180067821
0x1800677fe  mov     rax, cs:WPP_GLOBAL_Control
0x180067805  lea     rcx, WPP_GLOBAL_Control
0x18006780c  cmp     rax, rcx
0x18006780f  jz      short loc_18006788D
0x180067811  test    byte ptr [rax+1Ch], 1
0x180067815  jz      short loc_18006788D
0x180067817  mov     edx, 18h
0x18006781c  jmp     loc_1800676FC
0x180067821  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180067828  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18006782d  mov     rdx, [rbp+4Fh+var_98]; unsigned __int16 *
0x180067831  lea     rcx, [rbp+4Fh+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x180067835  test    al, al
0x180067837  mov     qword ptr [rbp+4Fh+var_80.Size], 4
0x18006783f  lea     rax, [rbp+4Fh+arg_0]
0x180067843  mov     [rbp+4Fh+var_80.Ptr], rax
0x180067847  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006784c  mov     rdx, [rbp+4Fh+var_90]; unsigned __int16 *
0x180067850  lea     rcx, [rbp+4Fh+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x180067854  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180067859  mov     rdx, [rbp+4Fh+var_88]; unsigned __int16 *
0x18006785d  lea     rcx, [rbp+4Fh+var_50]; struct _EVENT_DATA_DESCRIPTOR *
0x180067861  call    ?FwSerializeStringEventParam@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; FwSerializeStringEventParam(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180067866  lea     rax, [rbp+4Fh+arg_20]
0x18006786a  mov     [rbp+4Fh+var_38], 4
0x180067872  lea     r8, [rbp+4Fh+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x180067876  mov     [rbp+4Fh+var_40], rax
0x18006787a  mov     edx, 5; unsigned int
0x18006787f  lea     rcx, NetIsoSubnetsChangedEvent; struct _EVENT_DESCRIPTOR *
0x180067886  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18006788b  mov     ebx, eax
0x18006788d  mov     rcx, [rbp+4Fh+var_98]
0x180067891  call    cs:__imp_FwFree
0x180067897  mov     rcx, [rbp+4Fh+var_90]
0x18006789b  mov     [rbp+4Fh+var_98], 0
0x1800678a3  call    cs:__imp_FwFree
0x1800678a9  mov     rcx, [rbp+4Fh+var_88]
0x1800678ad  mov     [rbp+4Fh+var_90], 0
0x1800678b5  call    cs:__imp_FwFree
0x1800678bb  mov     eax, ebx
0x1800678bd  mov     rcx, [rbp+4Fh+var_30]
0x1800678c1  xor     rcx, rsp; StackCookie
0x1800678c4  call    __security_check_cookie
0x1800678c9  add     rsp, 0A0h
0x1800678d0  pop     r14
0x1800678d2  pop     rdi
0x1800678d3  pop     rsi
0x1800678d4  pop     rbx
0x1800678d5  pop     rbp
0x1800678d6  retn
```

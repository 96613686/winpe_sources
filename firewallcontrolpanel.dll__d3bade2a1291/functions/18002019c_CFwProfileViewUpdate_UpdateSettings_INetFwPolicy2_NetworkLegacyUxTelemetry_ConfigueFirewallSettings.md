# CFwProfileViewUpdate::UpdateSettings(INetFwPolicy2 *,NetworkLegacyUxTelemetry::ConfigueFirewallSettings)

- ea: `0x18002019c`
- end: `0x1800203e1`
- name: `?UpdateSettings@CFwProfileViewUpdate@@QEAAJPEAUINetFwPolicy2@@VConfigueFirewallSettings@NetworkLegacyUxTelemetry@@@Z`
- size: `581`
- prototype: `int __high(struct INetFwPolicy2 *, struct NetworkLegacyUxTelemetry::ConfigueFirewallSettings)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800171c8`

## callees

- `0x180009924`
- `0x18000994c`
- `0x18000c358`
- `0x18000d5b0`
- `0x180016a04`
- `0x18001f6b8`
- `0x18001fa48`
- `0x18002019c`
- `0x180030ea0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800202e8`
- `ntdll!EtwEventWrite` at `0x180020334`
- `ntdll!EtwEventWrite` at `0x1800202e8`
- `ntdll!EtwEventWrite` at `0x180020334`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180020260`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180020289`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800202b3`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180020260`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180020289`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800202b3`
- `DUI70!StrToID` at `0x18002024b`
- `DUI70!StrToID` at `0x180020274`
- `DUI70!StrToID` at `0x18002029e`
- `DUI70!StrToID` at `0x18002024b`
- `DUI70!StrToID` at `0x180020274`
- `DUI70!StrToID` at `0x18002029e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020257`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020280`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800202aa`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020257`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020280`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800202aa`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x18002034c`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x18002034c`

## string_xrefs

- `0x18002026d`: `blockAllIncomingConnections`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFwProfileViewUpdate::UpdateSettings(__int64 a1, struct INetFwPolicy2 *a2, unsigned __int16 *a3)
{
  CFwCplLua *v6; // rcx
  BOOL Selected; // ebp
  BOOL v8; // r15d
  BOOL v9; // r12d
  unsigned int v10; // edi
  __int64 v11; // rbx
  DirectUI::Element *v12; // rbx
  unsigned __int16 v13; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v15; // rbx
  unsigned __int16 v16; // ax
  DirectUI::Element *v17; // rax
  DirectUI::Element *v18; // rbx
  unsigned __int16 v19; // ax
  DirectUI::Element *v20; // rax
  __int64 *v21; // rdx
  __int64 *v22; // rdx
  int ProfileIndexFromProfileType; // eax
  unsigned __int16 *v25[2]; // [rsp+30h] [rbp-58h] BYREF

  v25[1] = a3;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4a589502d135308541a166db9771a95e_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v12 = *(DirectUI::Element **)(a1 + 32);
    v13 = StrToID(L"turnOnFirewall");
    Descendent = DirectUI::Element::FindDescendent(v12, v13);
    Selected = DirectUI::Element::GetSelected(Descendent);
    v15 = *(DirectUI::Element **)(a1 + 32);
    v16 = StrToID(L"blockAllIncomingConnections");
    v17 = DirectUI::Element::FindDescendent(v15, v16);
    v9 = DirectUI::Element::GetSelected(v17);
    v18 = *(DirectUI::Element **)(a1 + 32);
    v19 = StrToID(L"notifyMeWhenProgramAllowed");
    v20 = DirectUI::Element::FindDescendent(v18, v19);
    v8 = DirectUI::Element::GetSelected(v20);
    if ( Selected )
    {
      if ( !g_Provider )
        goto LABEL_15;
      v21 = SetFirewallOn_Start;
    }
    else
    {
      if ( !g_Provider )
        goto LABEL_15;
      v21 = SetFirewallOff_Start;
    }
    EtwEventWrite(g_Provider, v21, 0, 0);
LABEL_15:
    v11 = a1 + 40;
    v10 = CFwProfile::Update(*(CFwProfile **)(a1 + 40), Selected, v8, v9, a2);
    if ( Selected )
    {
      if ( !g_Provider )
        goto LABEL_21;
      v22 = SetFirewallOn_End;
    }
    else
    {
      if ( !g_Provider )
        goto LABEL_21;
      v22 = SetFirewallOff_End;
    }
    EtwEventWrite(g_Provider, v22, 0, 0);
    goto LABEL_21;
  }
  LOBYTE(Selected) = 0;
  LOBYTE(v8) = 0;
  LOBYTE(v9) = 0;
  v10 = -2147024809;
  if ( v6 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v6 + 2), 16, WPP_4a589502d135308541a166db9771a95e_Traceguids, 2147942487LL);
  v11 = a1 + 40;
LABEL_21:
  v25[0] = (unsigned __int16 *)WTL::_atltmpPchNil;
  ProfileIndexFromProfileType = FwGetProfileIndexFromProfileType(*(unsigned int *)(*(_QWORD *)v11 + 16LL));
  WTL::CString::LoadStringW((WTL::CString *)v25, ProfileIndexFromProfileType + 160);
  NetworkLegacyUxTelemetry::ConfigueFirewallSettings::ChangeIndividualProfileSetting(
    (NetworkLegacyUxTelemetry::ConfigueFirewallSettings *)a3,
    v25[0],
    Selected,
    v9,
    v8,
    v10);
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4a589502d135308541a166db9771a95e_Traceguids, v10);
  WTL::CString::~CString((WTL::CString *)v25);
  NetworkLegacyUxTelemetry::ConfigueFirewallSettings::~ConfigueFirewallSettings((NetworkLegacyUxTelemetry::ConfigueFirewallSettings *)a3);
  return v10;
}

```

## disassembly

```asm
0x18002019c  push    rbx
0x18002019e  push    rbp
0x18002019f  push    rsi
0x1800201a0  push    rdi
0x1800201a1  push    r12
0x1800201a3  push    r14
0x1800201a5  push    r15
0x1800201a7  sub     rsp, 50h
0x1800201ab  mov     rax, cs:__security_cookie
0x1800201b2  xor     rax, rsp
0x1800201b5  mov     [rsp+88h+var_48], rax
0x1800201ba  mov     rsi, r8
0x1800201bd  mov     rdi, rdx
0x1800201c0  mov     r14, rcx
0x1800201c3  mov     [rsp+88h+var_50], r8
0x1800201c8  lea     rax, WPP_GLOBAL_Control
0x1800201cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201d6  cmp     rcx, rax
0x1800201d9  jz      short loc_180020204
0x1800201db  test    byte ptr [rcx+1Ch], 8
0x1800201df  jz      short loc_180020204
0x1800201e1  mov     edx, 0Fh
0x1800201e6  lea     r8, WPP_4a589502d135308541a166db9771a95e_Traceguids
0x1800201ed  mov     rcx, [rcx+10h]
0x1800201f1  call    WPP_SF_
0x1800201f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201fd  lea     rax, WPP_GLOBAL_Control
0x180020204  test    rdi, rdi
0x180020207  jnz     short loc_180020240
0x180020209  xor     ebp, ebp
0x18002020b  xor     r15d, r15d
0x18002020e  xor     r12d, r12d
0x180020211  mov     edi, 80070057h
0x180020216  cmp     rcx, rax
0x180020219  jz      short loc_180020237
0x18002021b  test    byte ptr [rcx+1Ch], 1
0x18002021f  jz      short loc_180020237
0x180020221  lea     edx, [rbp+10h]
0x180020224  mov     r9d, edi
0x180020227  lea     r8, WPP_4a589502d135308541a166db9771a95e_Traceguids
0x18002022e  mov     rcx, [rcx+10h]
0x180020232  call    WPP_SF_d
0x180020237  lea     rbx, [r14+28h]
0x18002023b  jmp     loc_18002033A
0x180020240  mov     rbx, [r14+20h]
0x180020244  lea     rcx, aTurnonfirewall; "turnOnFirewall"
0x18002024b  call    cs:__imp_StrToID
0x180020251  movzx   edx, ax
0x180020254  mov     rcx, rbx
0x180020257  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002025d  mov     rcx, rax
0x180020260  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180020266  movzx   ebp, al
0x180020269  mov     rbx, [r14+20h]
0x18002026d  lea     rcx, aBlockallincomi; "blockAllIncomingConnections"
0x180020274  call    cs:__imp_StrToID
0x18002027a  movzx   edx, ax
0x18002027d  mov     rcx, rbx
0x180020280  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180020286  mov     rcx, rax
0x180020289  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18002028f  movzx   r12d, al
0x180020293  mov     rbx, [r14+20h]
0x180020297  lea     rcx, aNotifymewhenpr; "notifyMeWhenProgramAllowed"
0x18002029e  call    cs:__imp_StrToID
0x1800202a4  movzx   edx, ax
0x1800202a7  mov     rcx, rbx
0x1800202aa  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800202b0  mov     rcx, rax
0x1800202b3  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800202b9  movzx   r15d, al
0x1800202bd  mov     rcx, cs:g_Provider
0x1800202c4  test    ebp, ebp
0x1800202c6  jz      short loc_1800202D6
0x1800202c8  test    rcx, rcx
0x1800202cb  jz      short loc_1800202EE
0x1800202cd  lea     rdx, SetFirewallOn_Start
0x1800202d4  jmp     short loc_1800202E2
0x1800202d6  test    rcx, rcx
0x1800202d9  jz      short loc_1800202EE
0x1800202db  lea     rdx, SetFirewallOff_Start
0x1800202e2  xor     r9d, r9d
0x1800202e5  xor     r8d, r8d
0x1800202e8  call    cs:__imp_EtwEventWrite
0x1800202ee  lea     rbx, [r14+28h]
0x1800202f2  mov     [rsp+88h+var_68], rdi; struct INetFwPolicy2 *
0x1800202f7  mov     r9d, r12d; int
0x1800202fa  mov     r8d, r15d; int
0x1800202fd  mov     edx, ebp; int
0x1800202ff  mov     rcx, [rbx]; this
0x180020302  call    ?Update@CFwProfile@@QEAAJHHHPEAUINetFwPolicy2@@@Z; CFwProfile::Update(int,int,int,INetFwPolicy2 *)
0x180020307  mov     edi, eax
0x180020309  mov     rcx, cs:g_Provider
0x180020310  test    ebp, ebp
0x180020312  jz      short loc_180020322
0x180020314  test    rcx, rcx
0x180020317  jz      short loc_18002033A
0x180020319  lea     rdx, SetFirewallOn_End
0x180020320  jmp     short loc_18002032E
0x180020322  test    rcx, rcx
0x180020325  jz      short loc_18002033A
0x180020327  lea     rdx, SetFirewallOff_End
0x18002032e  xor     r9d, r9d
0x180020331  xor     r8d, r8d
0x180020334  call    cs:__imp_EtwEventWrite
0x18002033a  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x180020341  mov     [rsp+88h+var_58], rax
0x180020346  mov     rcx, [rbx]
0x180020349  mov     ecx, [rcx+10h]
0x18002034c  call    cs:__imp_FwGetProfileIndexFromProfileType
0x180020352  lea     edx, [rax+0A0h]; uID
0x180020358  lea     rcx, [rsp+88h+var_58]; this
0x18002035d  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x180020362  mov     r9b, r12b; bool
0x180020365  mov     r8b, bpl; bool
0x180020368  mov     [rsp+88h+var_60], edi; int
0x18002036c  mov     byte ptr [rsp+88h+var_68], r15b; bool
0x180020371  mov     rdx, [rsp+88h+var_58]; unsigned __int16 *
0x180020376  mov     rcx, rsi; this
0x180020379  call    ?ChangeIndividualProfileSetting@ConfigueFirewallSettings@NetworkLegacyUxTelemetry@@QEAAXPEBG_N11J@Z; NetworkLegacyUxTelemetry::ConfigueFirewallSettings::ChangeIndividualProfileSetting(ushort const *,bool,bool,bool,long)
0x18002037e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020385  lea     rax, WPP_GLOBAL_Control
0x18002038c  cmp     rcx, rax
0x18002038f  jz      short loc_1800203B0
0x180020391  test    byte ptr [rcx+1Ch], 8
0x180020395  jz      short loc_1800203B0
0x180020397  mov     edx, 11h
0x18002039c  mov     r9d, edi
0x18002039f  lea     r8, WPP_4a589502d135308541a166db9771a95e_Traceguids
0x1800203a6  mov     rcx, [rcx+10h]
0x1800203aa  call    WPP_SF_d
0x1800203af  nop
0x1800203b0  lea     rcx, [rsp+88h+var_58]; this
0x1800203b5  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800203ba  nop
0x1800203bb  mov     rcx, rsi; this
0x1800203be  call    ??1ConfigueFirewallSettings@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::ConfigueFirewallSettings::~ConfigueFirewallSettings(void)
0x1800203c3  mov     eax, edi
0x1800203c5  mov     rcx, [rsp+88h+var_48]
0x1800203ca  xor     rcx, rsp; StackCookie
0x1800203cd  call    __security_check_cookie
0x1800203d2  add     rsp, 50h
0x1800203d6  pop     r15
0x1800203d8  pop     r14
0x1800203da  pop     r12
0x1800203dc  pop     rdi
0x1800203dd  pop     rsi
0x1800203de  pop     rbp
0x1800203df  pop     rbx
0x1800203e0  retn
```

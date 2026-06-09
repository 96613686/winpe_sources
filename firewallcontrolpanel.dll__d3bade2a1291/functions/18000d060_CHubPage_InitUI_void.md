# CHubPage::InitUI(void)

- ea: `0x18000d060`
- end: `0x18000d43a`
- name: `?InitUI@CHubPage@@AEAAJXZ`
- size: `986`
- prototype: `__int64 __fastcall(CHubPage *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d440`
- `0x18000ded0`

## callees

- `0x180009040`
- `0x180009924`
- `0x18000994c`
- `0x180009b30`
- `0x18000c258`
- `0x18000c924`
- `0x18000d060`
- `0x18000d7cc`
- `0x180011070`
- `0x1800110d0`
- `0x18001d1e8`
- `0x18001daa8`
- `0x18001f0bc`
- `0x18001f16c`
- `0x180020c30`

## import_xrefs

- `DUI70!StrToID` at `0x18000d132`
- `DUI70!StrToID` at `0x18000d132`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000d38c`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000d38c`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18000d0dd`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18000d0dd`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x18000d411`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x18000d411`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000d13e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000d13e`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18000d1b3`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18000d1b3`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18000d207`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18000d207`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CHubPage::InitUI(CHubPage *this)
{
  int v2; // r15d
  unsigned int v3; // edi
  CFwProfileMgr *v4; // rcx
  int v5; // ebx
  DirectUI::Element *v6; // rbx
  unsigned __int16 v7; // ax
  int ProfileList; // eax
  CFwCplLua *v9; // rcx
  DirectUI::DUIXmlParser **v10; // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // r12d
  __int64 v15; // rax
  struct CFwProfile *v16; // r13
  unsigned __int64 v17; // rdx
  _DWORD *v18; // rax
  int v19; // eax
  __int64 v20; // rax
  __int64 *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  _DWORD *v25; // [rsp+30h] [rbp-39h] BYREF
  DirectUI::Element *v26; // [rsp+38h] [rbp-31h]
  unsigned int v27; // [rsp+40h] [rbp-29h] BYREF
  __int128 v28; // [rsp+48h] [rbp-21h] BYREF
  __int64 v29; // [rsp+58h] [rbp-11h]
  __int128 v30; // [rsp+60h] [rbp-9h]
  int v31; // [rsp+70h] [rbp+7h]
  int v32; // [rsp+D0h] [rbp+67h]
  int IsFwCategoryEnabled; // [rsp+D8h] [rbp+6Fh]
  __int64 i; // [rsp+E0h] [rbp+77h] BYREF
  struct DirectUI::Element *Descendent; // [rsp+E8h] [rbp+7Fh]

  v2 = 0;
  v3 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 10;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_041ed7bb04083fded16b958364bb1572_Traceguids);
  v26 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v27 = 0;
  DirectUI::Element::StartDefer(v26, &v27);
  if ( *((_DWORD *)this + 8) )
    goto LABEL_44;
  v4 = (CFwProfileMgr *)*((_QWORD *)this + 5);
  v5 = *((_DWORD *)v4 + 37);
  IsFwCategoryEnabled = CFwProfileMgr::IsFwCategoryEnabled(v4);
  if ( v5 )
  {
    CPageBase::UpdateGroupPolicyBanner(this, 0);
    CPageBase::UpdateRecommendedSettingsBanner(this, 0);
    CHubPage::DisplayFwCategoriesBanner(this, 0);
LABEL_44:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_45;
  }
  v6 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v7 = StrToID(L"hubExpandoHolder");
  Descendent = DirectUI::Element::FindDescendent(v6, v7);
  ProfileList = CFwProfileMgr::GetProfileList(*((CFwProfileMgr **)this + 5), (struct CFwProfileList *)&v28);
  v3 = ProfileList;
  if ( ProfileList < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_041ed7bb04083fded16b958364bb1572_Traceguids,
        (unsigned int)ProfileList);
      v9 = WPP_GLOBAL_Control;
    }
    v10 = (DirectUI::DUIXmlParser **)((char *)this + 48);
    goto LABEL_39;
  }
  v10 = (DirectUI::DUIXmlParser **)((char *)this + 48);
  v11 = DirectUI::DUIXmlParser::Create(
          (struct DirectUI::DUIXmlParser **)this + 6,
          0,
          0,
          (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))ParserError,
          0);
  v3 = v11;
  if ( v11 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v12 = 18;
    goto LABEL_17;
  }
  v11 = DirectUI::DUIXmlParser::SetXMLFromResource(*v10, 0xCDu, g_hinst, (HINSTANCE)&_ImageBase);
  v3 = v11;
  if ( v11 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v12 = 19;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v9 + 2), v12, WPP_041ed7bb04083fded16b958364bb1572_Traceguids, (unsigned int)v11);
    v9 = WPP_GLOBAL_Control;
    goto LABEL_39;
  }
  v32 = 0;
  v14 = 1;
  v15 = v28;
  for ( i = v28; ; v15 = i )
  {
    if ( !v15 )
    {
      if ( !IsFwCategoryEnabled )
        v14 = 1;
      CPageBase::UpdateGroupPolicyBanner(this, IsFwCategoryEnabled != 0 ? v2 : 0);
      CPageBase::UpdateRecommendedSettingsBanner(this, v14);
      CHubPage::DisplayFwCategoriesBanner(this, IsFwCategoryEnabled == 0);
      *((_DWORD *)this + 8) = 1;
      goto LABEL_44;
    }
    v16 = *(struct CFwProfile **)ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::GetNext(
                                   v13,
                                   &i);
    v18 = DirectUI::HAllocAndZero((DirectUI *)0x40, v17);
    v25 = v18;
    if ( !v18 )
      break;
    *(_QWORD *)v18 = &CRefObject::`vftable';
    v18[2] = 1;
    *(_QWORD *)v18 = &CFwProfileViewRead::`vftable'{for `CRefObject'};
    *((_QWORD *)v18 + 2) = &CFwProfileViewRead::`vftable'{for `IEventHandler'};
    *((_QWORD *)v18 + 3) = 0;
    *((_QWORD *)v18 + 4) = 0;
    *((_QWORD *)v18 + 5) = 0;
    v18[12] = 0;
    v18[13] = 1;
    *((_QWORD *)v18 + 7) = 0;
    v25 = v18;
    v19 = CFwProfileViewRead::Initialize((CFwProfileViewRead *)v18, Descendent, *v10, v16);
    v3 = v19;
    if ( v19 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v22 = 21;
        v23 = (unsigned int)v19;
LABEL_38:
        WPP_SF_d(*((_QWORD *)v9 + 2), v22, WPP_041ed7bb04083fded16b958364bb1572_Traceguids, v23);
        v9 = WPP_GLOBAL_Control;
        goto LABEL_39;
      }
      goto LABEL_39;
    }
    v20 = ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::NewNode(
            (char *)this + 56,
            &v25,
            *((_QWORD *)this + 8));
    v21 = (__int64 *)*((_QWORD *)this + 8);
    if ( v21 )
      *v21 = v20;
    else
      *((_QWORD *)this + 7) = v20;
    *((_QWORD *)this + 8) = v20;
    v2 = v32;
    if ( (unsigned int)CFwProfile::IsGPEnforced(v16) )
      v2 = 1;
    v32 = v2;
    v13 = (unsigned int)-((unsigned int)CFwProfile::IsPolicySecure(v16) != 0);
    v14 &= v13;
  }
  v3 = -2147024882;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v22 = 20;
    v23 = 2147942414LL;
    goto LABEL_38;
  }
LABEL_39:
  if ( *v10 )
  {
    DirectUI::DUIXmlParser::Destroy(*v10);
    *v10 = 0;
    goto LABEL_44;
  }
LABEL_45:
  if ( v9 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v9 + 2), 22, WPP_041ed7bb04083fded16b958364bb1572_Traceguids, v3);
  if ( v27 )
  {
    DirectUI::Element::EndDefer(v26, v27);
    v27 = 0;
  }
  CRefObjectList<CFwProfile *>::~CRefObjectList<CFwProfile *>(&v28);
  return v3;
}

```

## disassembly

```asm
0x18000d060  push    rbp
0x18000d062  push    rbx
0x18000d063  push    rsi
0x18000d064  push    rdi
0x18000d065  push    r12
0x18000d067  push    r13
0x18000d069  push    r14
0x18000d06b  push    r15
0x18000d06d  lea     rbp, [rsp-1Fh]
0x18000d072  sub     rsp, 88h
0x18000d079  mov     r14, rcx
0x18000d07c  xor     r15d, r15d
0x18000d07f  mov     edi, r15d
0x18000d082  xorps   xmm0, xmm0
0x18000d085  movdqu  [rbp+57h+var_78], xmm0
0x18000d08a  mov     [rbp+57h+var_68], r15
0x18000d08e  xorps   xmm1, xmm1
0x18000d091  movdqu  [rbp+57h+var_60], xmm1
0x18000d096  mov     [rbp+57h+var_50], 0Ah
0x18000d09d  lea     r12, WPP_GLOBAL_Control
0x18000d0a4  lea     r13, WPP_041ed7bb04083fded16b958364bb1572_Traceguids
0x18000d0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0b2  cmp     rcx, r12
0x18000d0b5  jz      short loc_18000D0CD
0x18000d0b7  test    byte ptr [rcx+1Ch], 8
0x18000d0bb  jz      short loc_18000D0CD
0x18000d0bd  lea     edx, [r15+10h]
0x18000d0c1  mov     r8, r13
0x18000d0c4  mov     rcx, [rcx+10h]
0x18000d0c8  call    WPP_SF_
0x18000d0cd  mov     rcx, [r14+10h]
0x18000d0d1  mov     [rbp+57h+var_88], rcx
0x18000d0d5  mov     [rbp+57h+var_80], r15d
0x18000d0d9  lea     rdx, [rbp+57h+var_80]
0x18000d0dd  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x18000d0e3  nop
0x18000d0e4  cmp     [r14+20h], r15d
0x18000d0e8  jnz     loc_18000D3D4
0x18000d0ee  mov     rcx, [r14+28h]; this
0x18000d0f2  mov     ebx, [rcx+94h]
0x18000d0f8  call    ?IsFwCategoryEnabled@CFwProfileMgr@@QEAAHXZ; CFwProfileMgr::IsFwCategoryEnabled(void)
0x18000d0fd  mov     [rbp+57h+arg_8], eax
0x18000d100  test    ebx, ebx
0x18000d102  jz      short loc_18000D127
0x18000d104  xor     edx, edx; int
0x18000d106  mov     rcx, r14; this
0x18000d109  call    ?UpdateGroupPolicyBanner@CPageBase@@IEAAXH@Z; CPageBase::UpdateGroupPolicyBanner(int)
0x18000d10e  xor     edx, edx; int
0x18000d110  mov     rcx, r14; this
0x18000d113  call    ?UpdateRecommendedSettingsBanner@CPageBase@@IEAAXH@Z; CPageBase::UpdateRecommendedSettingsBanner(int)
0x18000d118  xor     edx, edx; bool
0x18000d11a  mov     rcx, r14; this
0x18000d11d  call    ?DisplayFwCategoriesBanner@CHubPage@@AEAAX_N@Z; CHubPage::DisplayFwCategoriesBanner(bool)
0x18000d122  jmp     loc_18000D3D4
0x18000d127  mov     rbx, [r14+10h]
0x18000d12b  lea     rcx, aHubexpandohold; "hubExpandoHolder"
0x18000d132  call    cs:__imp_StrToID
0x18000d138  movzx   edx, ax
0x18000d13b  mov     rcx, rbx
0x18000d13e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000d144  mov     [rbp+57h+arg_18], rax
0x18000d148  lea     rdx, [rbp+57h+var_78]; struct CFwProfileList *
0x18000d14c  mov     rcx, [r14+28h]; this
0x18000d150  call    ?GetProfileList@CFwProfileMgr@@QEAAJAEAVCFwProfileList@@@Z; CFwProfileMgr::GetProfileList(CFwProfileList &)
0x18000d155  mov     edi, eax
0x18000d157  test    eax, eax
0x18000d159  jns     short loc_18000D19B
0x18000d15b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d162  cmp     rcx, r12
0x18000d165  jz      short loc_18000D18B
0x18000d167  mov     esi, 1
0x18000d16c  test    [rcx+1Ch], sil
0x18000d170  jz      short loc_18000D18B
0x18000d172  lea     edx, [rsi+10h]
0x18000d175  mov     r9d, eax
0x18000d178  mov     r8, r13
0x18000d17b  mov     rcx, [rcx+10h]
0x18000d17f  call    WPP_SF_d
0x18000d184  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d18b  lea     rbx, [r14+30h]
0x18000d18f  lea     r14, WPP_GLOBAL_Control
0x18000d196  jmp     loc_18000D384
0x18000d19b  lea     rbx, [r14+30h]
0x18000d19f  mov     [rsp+0C0h+var_A0], r15
0x18000d1a4  lea     r9, ParserError
0x18000d1ab  xor     r8d, r8d
0x18000d1ae  xor     edx, edx
0x18000d1b0  mov     rcx, rbx
0x18000d1b3  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18000d1b9  mov     edi, eax
0x18000d1bb  test    eax, eax
0x18000d1bd  jns     short loc_18000D1F1
0x18000d1bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1c6  cmp     rcx, r12
0x18000d1c9  jz      short loc_18000D18F
0x18000d1cb  mov     esi, 1
0x18000d1d0  test    [rcx+1Ch], sil
0x18000d1d4  jz      short loc_18000D18F
0x18000d1d6  lea     edx, [rsi+11h]
0x18000d1d9  mov     r9d, eax
0x18000d1dc  mov     r8, r13
0x18000d1df  mov     rcx, [rcx+10h]
0x18000d1e3  call    WPP_SF_d
0x18000d1e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1ef  jmp     short loc_18000D18F
0x18000d1f1  lea     r9, __ImageBase
0x18000d1f8  mov     r8, cs:g_hinst
0x18000d1ff  mov     edx, 0CDh
0x18000d204  mov     rcx, [rbx]
0x18000d207  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18000d20d  mov     edi, eax
0x18000d20f  test    eax, eax
0x18000d211  jns     short loc_18000D237
0x18000d213  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d21a  cmp     rcx, r12
0x18000d21d  jz      loc_18000D18F
0x18000d223  mov     esi, 1
0x18000d228  test    [rcx+1Ch], sil
0x18000d22c  jz      loc_18000D18F
0x18000d232  lea     edx, [rsi+12h]
0x18000d235  jmp     short loc_18000D1D9
0x18000d237  mov     [rbp+57h+arg_0], r15d
0x18000d23b  mov     esi, 1
0x18000d240  mov     r12d, esi
0x18000d243  mov     rax, qword ptr [rbp+57h+var_78]
0x18000d247  mov     [rbp+57h+arg_10], rax
0x18000d24b  test    rax, rax
0x18000d24e  jz      loc_18000D397
0x18000d254  lea     rdx, [rbp+57h+arg_10]
0x18000d258  call    ?GetNext@?$CAtlList@PEAVCFwProfileViewUpdate@@V?$CElementTraits@PEAVCFwProfileViewUpdate@@@ATL@@@ATL@@QEAAAEAPEAVCFwProfileViewUpdate@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::GetNext(__POSITION * &)
0x18000d25d  mov     r13, [rax]
0x18000d260  mov     ecx, 40h ; '@'; this
0x18000d265  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000d26a  mov     [rbp+57h+var_90], rax
0x18000d26e  xor     r15d, r15d
0x18000d271  test    rax, rax
0x18000d274  jz      loc_18000D347
0x18000d27a  lea     rcx, ??_7CRefObject@@6B@; const CRefObject::`vftable'
0x18000d281  mov     [rax], rcx
0x18000d284  mov     [rax+8], esi
0x18000d287  lea     rcx, ??_7CFwProfileViewRead@@6BCRefObject@@@; const CFwProfileViewRead::`vftable'{for `CRefObject'}
0x18000d28e  mov     [rax], rcx
0x18000d291  lea     rcx, ??_7CFwProfileViewRead@@6BIEventHandler@@@; const CFwProfileViewRead::`vftable'{for `IEventHandler'}
0x18000d298  mov     [rax+10h], rcx
0x18000d29c  mov     [rax+18h], r15
0x18000d2a0  mov     [rax+20h], r15
0x18000d2a4  mov     [rax+28h], r15
0x18000d2a8  mov     [rax+30h], r15d
0x18000d2ac  mov     [rax+34h], esi
0x18000d2af  mov     [rax+38h], r15
0x18000d2b3  mov     [rbp+57h+var_90], rax
0x18000d2b7  mov     r9, r13; struct CFwProfile *
0x18000d2ba  mov     r8, [rbx]; struct DirectUI::DUIXmlParser *
0x18000d2bd  mov     rdx, [rbp+57h+arg_18]; struct DirectUI::Element *
0x18000d2c1  mov     rcx, rax; this
0x18000d2c4  call    ?Initialize@CFwProfileViewRead@@QEAAJPEAVElement@DirectUI@@PEAVDUIXmlParser@3@PEAVCFwProfile@@@Z; CFwProfileViewRead::Initialize(DirectUI::Element *,DirectUI::DUIXmlParser *,CFwProfile *)
0x18000d2c9  mov     edi, eax
0x18000d2cb  test    eax, eax
0x18000d2cd  js      short loc_18000D324
0x18000d2cf  mov     r8, [r14+40h]
0x18000d2d3  lea     rdx, [rbp+57h+var_90]
0x18000d2d7  lea     rcx, [r14+38h]
0x18000d2db  call    ?NewNode@?$CAtlList@PEAVCFwProfileViewUpdate@@V?$CElementTraits@PEAVCFwProfileViewUpdate@@@ATL@@@ATL@@AEAAPEAVCNode@12@AEBQEAVCFwProfileViewUpdate@@PEAV312@1@Z; ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::NewNode(CFwProfileViewUpdate * const &,ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::CNode *,ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::CNode *)
0x18000d2e0  mov     rcx, [r14+40h]
0x18000d2e4  test    rcx, rcx
0x18000d2e7  jz      short loc_18000D2EE
0x18000d2e9  mov     [rcx], rax
0x18000d2ec  jmp     short loc_18000D2F2
0x18000d2ee  mov     [r14+38h], rax
0x18000d2f2  mov     [r14+40h], rax
0x18000d2f6  mov     rcx, r13; this
0x18000d2f9  call    ?IsGPEnforced@CFwProfile@@QEAAHXZ; CFwProfile::IsGPEnforced(void)
0x18000d2fe  mov     r15d, [rbp+57h+arg_0]
0x18000d302  test    eax, eax
0x18000d304  cmovnz  r15d, esi
0x18000d308  mov     [rbp+57h+arg_0], r15d
0x18000d30c  mov     rcx, r13; this
0x18000d30f  call    ?IsPolicySecure@CFwProfile@@QEAAHXZ; CFwProfile::IsPolicySecure(void)
0x18000d314  neg     eax
0x18000d316  sbb     ecx, ecx
0x18000d318  and     r12d, ecx
0x18000d31b  mov     rax, [rbp+57h+arg_10]
0x18000d31f  jmp     loc_18000D24B
0x18000d324  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d32b  lea     r14, WPP_GLOBAL_Control
0x18000d332  cmp     rcx, r14
0x18000d335  jz      short loc_18000D384
0x18000d337  test    [rcx+1Ch], sil
0x18000d33b  jz      short loc_18000D384
0x18000d33d  mov     edx, 15h
0x18000d342  mov     r9d, eax
0x18000d345  jmp     short loc_18000D36D
0x18000d347  mov     edi, 8007000Eh
0x18000d34c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d353  lea     r14, WPP_GLOBAL_Control
0x18000d35a  cmp     rcx, r14
0x18000d35d  jz      short loc_18000D384
0x18000d35f  test    [rcx+1Ch], sil
0x18000d363  jz      short loc_18000D384
0x18000d365  mov     edx, 14h
0x18000d36a  mov     r9d, edi
0x18000d36d  lea     r8, WPP_041ed7bb04083fded16b958364bb1572_Traceguids
0x18000d374  mov     rcx, [rcx+10h]
0x18000d378  call    WPP_SF_d
0x18000d37d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d384  cmp     [rbx], r15
0x18000d387  jz      short loc_18000D3E2
0x18000d389  mov     rcx, [rbx]
0x18000d38c  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18000d392  mov     [rbx], r15
0x18000d395  jmp     short loc_18000D3DB
0x18000d397  mov     r13d, [rbp+57h+arg_8]
0x18000d39b  test    r13d, r13d
0x18000d39e  cmovz   r12d, esi
0x18000d3a2  mov     eax, r13d
0x18000d3a5  neg     eax
0x18000d3a7  sbb     edx, edx
0x18000d3a9  and     edx, r15d; int
0x18000d3ac  mov     rcx, r14; this
0x18000d3af  call    ?UpdateGroupPolicyBanner@CPageBase@@IEAAXH@Z; CPageBase::UpdateGroupPolicyBanner(int)
0x18000d3b4  mov     edx, r12d; int
0x18000d3b7  mov     rcx, r14; this
0x18000d3ba  call    ?UpdateRecommendedSettingsBanner@CPageBase@@IEAAXH@Z; CPageBase::UpdateRecommendedSettingsBanner(int)
0x18000d3bf  xor     r15d, r15d
0x18000d3c2  test    r13d, r13d
0x18000d3c5  setz    dl; bool
0x18000d3c8  mov     rcx, r14; this
0x18000d3cb  call    ?DisplayFwCategoriesBanner@CHubPage@@AEAAX_N@Z; CHubPage::DisplayFwCategoriesBanner(bool)
0x18000d3d0  mov     [r14+20h], esi
0x18000d3d4  lea     r14, WPP_GLOBAL_Control
0x18000d3db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3e2  cmp     rcx, r14
0x18000d3e5  jz      short loc_18000D406
0x18000d3e7  test    byte ptr [rcx+1Ch], 8
0x18000d3eb  jz      short loc_18000D406
0x18000d3ed  mov     edx, 16h
0x18000d3f2  mov     r9d, edi
0x18000d3f5  lea     r8, WPP_041ed7bb04083fded16b958364bb1572_Traceguids
0x18000d3fc  mov     rcx, [rcx+10h]
0x18000d400  call    WPP_SF_d
0x18000d405  nop
0x18000d406  mov     edx, [rbp+57h+var_80]
0x18000d409  test    edx, edx
0x18000d40b  jz      short loc_18000D41B
0x18000d40d  mov     rcx, [rbp+57h+var_88]
0x18000d411  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x18000d417  mov     [rbp+57h+var_80], r15d
0x18000d41b  lea     rcx, [rbp+57h+var_78]
0x18000d41f  call    ??1?$CRefObjectList@PEAVCFwProfile@@@@QEAA@XZ; CRefObjectList<CFwProfile *>::~CRefObjectList<CFwProfile *>(void)
0x18000d424  mov     eax, edi
0x18000d426  add     rsp, 88h
0x18000d42d  pop     r15
0x18000d42f  pop     r14
0x18000d431  pop     r13
0x18000d433  pop     r12
0x18000d435  pop     rdi
0x18000d436  pop     rsi
0x18000d437  pop     rbx
0x18000d438  pop     rbp
0x18000d439  retn
```

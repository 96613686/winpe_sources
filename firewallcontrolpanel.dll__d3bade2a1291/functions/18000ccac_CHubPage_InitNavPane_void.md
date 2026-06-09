# CHubPage::InitNavPane(void)

- ea: `0x18000ccac`
- end: `0x18000d05a`
- name: `?InitNavPane@CHubPage@@IEAAJXZ`
- size: `942`
- prototype: `__int64 __fastcall(CHubPage *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000d440`

## callees

- `0x180009924`
- `0x18000994c`
- `0x180009b30`
- `0x18000ccac`
- `0x18000e1a8`
- `0x18001daa8`
- `0x18002ee68`
- `0x18002ef3c`
- `0x18002f160`
- `0x180032010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18000cfd2`
- `SHCORE!IUnknown_QueryService` at `0x18000cfd2`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x18000cfec`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x18000cfec`

## string_xrefs

- `0x18000cd5d`: `PageConfigureApps`
- `0x18000cdac`: `PageConfigureSettings`
- `0x18000ce0d`: `PageConfigureSettings`
- `0x18000cfe2`: `ControlPanelNavLinks`

## pseudocode

```c
__int64 __fastcall CHubPage::InitNavPane(CFwProfileMgr **this, unsigned __int64 a2)
{
  CControlPanelNavLinks *v3; // rsi
  signed int v4; // edi
  int IsFwCategoryEnabled; // ebx
  CControlPanelNavLink *v6; // r8
  CHubPage *v7; // rcx
  struct CControlPanelNavLink *v8; // rdx
  bool v9; // r14
  CControlPanelNavLink *v10; // r8
  HINSTANCE v11; // rdx
  int v12; // r8d
  struct CControlPanelNavLink *v13; // rbx
  signed int v14; // eax
  CHubPage *v15; // rcx
  CControlPanelNavLink *v16; // r8
  HINSTANCE v17; // rdx
  int v18; // r8d
  struct CControlPanelNavLink *v19; // rbx
  signed int v20; // eax
  CHubPage *v21; // rcx
  CControlPanelNavLink *v22; // r8
  HINSTANCE v23; // rdx
  int v24; // r8d
  struct CControlPanelNavLink *v25; // rbx
  signed int v26; // eax
  CHubPage *v27; // rcx
  __int64 v28; // rdx
  CControlPanelNavLink *v29; // r8
  __int64 v30; // r9
  HINSTANCE v31; // rdx
  int v32; // r8d
  CHubPage *v33; // rcx
  CControlPanelNavLink *v34; // r8
  CHubPage *v35; // rcx
  CControlPanelNavLink *v36; // r8
  CControlPanelNavLink *v37; // r8
  IUnknown *v38; // rcx
  __int64 v40; // [rsp+20h] [rbp-20h]
  void *ppvOut; // [rsp+70h] [rbp+30h] BYREF
  CControlPanelNavLinks *v42; // [rsp+78h] [rbp+38h]

  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_041ed7bb04083fded16b958364bb1572_Traceguids);
  ppvOut = 0;
  v42 = (CControlPanelNavLinks *)DirectUI::HAllocAndZero((DirectUI *)0x18, a2);
  v3 = v42;
  if ( v42 )
  {
    *((_QWORD *)v42 + 1) = 0;
    *(_QWORD *)v3 = &CControlPanelNavLinks::`vftable';
    *((_DWORD *)v3 + 4) = 1;
  }
  else
  {
    v3 = 0;
  }
  v4 = v3 == 0 ? 0x8007000E : 0;
  IsFwCategoryEnabled = CFwProfileMgr::IsFwCategoryEnabled(this[5]);
  if ( v3 )
  {
    v4 = CControlPanelNavLinks::AddLinkControlPanel(
           v3,
           0,
           v6,
           0x19u,
           L"Microsoft.WindowsFirewall",
           L"PageConfigureApps",
           (CControlPanelNavLink **)&ppvOut);
    if ( v4 >= 0 )
    {
      v8 = (struct CControlPanelNavLink *)ppvOut;
      v9 = IsFwCategoryEnabled == 0;
      *((_BYTE *)ppvOut + 80) = IsFwCategoryEnabled == 0;
      CHubPage::RegisterNavLinkSQM(v7, v8, 0);
      v4 = CControlPanelNavLinks::AddLinkControlPanel(
             v3,
             0,
             v10,
             0x1Au,
             L"Microsoft.WindowsFirewall",
             L"PageConfigureSettings",
             (CControlPanelNavLink **)&ppvOut);
      if ( v4 >= 0 )
      {
        v13 = (struct CControlPanelNavLink *)ppvOut;
        v14 = CControlPanelNavLink::SetIcon((CControlPanelNavLink *)ppvOut, v11, v12);
        *((_BYTE *)v13 + 80) = v9;
        v4 = v14;
        CHubPage::RegisterNavLinkSQM(v15, v13, 1u);
        if ( v4 >= 0 )
        {
          v4 = CControlPanelNavLinks::AddLinkControlPanel(
                 v3,
                 0,
                 v16,
                 0x18u,
                 L"Microsoft.WindowsFirewall",
                 L"PageConfigureSettings",
                 (CControlPanelNavLink **)&ppvOut);
          if ( v4 >= 0 )
          {
            v19 = (struct CControlPanelNavLink *)ppvOut;
            v20 = CControlPanelNavLink::SetIcon((CControlPanelNavLink *)ppvOut, v17, v18);
            *((_BYTE *)v19 + 80) = v9;
            v4 = v20;
            CHubPage::RegisterNavLinkSQM(v21, v19, 2u);
            if ( v4 >= 0 )
            {
              v4 = CControlPanelNavLinks::AddLinkControlPanel(
                     v3,
                     0,
                     v22,
                     0x21u,
                     L"Microsoft.WindowsFirewall",
                     L"PageRestoreDefaults",
                     (CControlPanelNavLink **)&ppvOut);
              if ( v4 >= 0 )
              {
                v25 = (struct CControlPanelNavLink *)ppvOut;
                v26 = CControlPanelNavLink::SetIcon((CControlPanelNavLink *)ppvOut, v23, v24);
                *((_BYTE *)v25 + 80) = v9;
                v4 = v26;
                CHubPage::RegisterNavLinkSQM(v27, v25, 3u);
                if ( v4 >= 0 )
                {
                  v4 = CControlPanelNavLinks::AddLinkNotify(v3, v28, v29, v30, v40, (CControlPanelNavLink **)&ppvOut);
                  if ( v4 >= 0 )
                  {
                    v4 = CControlPanelNavLink::SetIcon((CControlPanelNavLink *)ppvOut, v31, v32);
                    CHubPage::RegisterNavLinkSQM(v33, (struct CControlPanelNavLink *)ppvOut, 5u);
                    if ( v4 >= 0 )
                    {
                      v4 = CControlPanelNavLinks::AddLinkControlPanel(
                             v3,
                             0,
                             v34,
                             0x4Eu,
                             L"Microsoft.Troubleshooting",
                             L"Network",
                             (CControlPanelNavLink **)&ppvOut);
                      if ( v4 >= 0 )
                      {
                        CHubPage::RegisterNavLinkSQM(v35, (struct CControlPanelNavLink *)ppvOut, 4u);
                        v4 = CControlPanelNavLinks::AddLinkControlPanel(
                               v3,
                               1u,
                               v36,
                               0x1Cu,
                               L"Microsoft.ActionCenter",
                               0,
                               0);
                        if ( v4 >= 0 )
                        {
                          v4 = CControlPanelNavLinks::AddLinkControlPanel(
                                 v3,
                                 1u,
                                 v37,
                                 0x1Bu,
                                 L"Microsoft.NetworkAndSharingCenter",
                                 0,
                                 0);
                          if ( v4 >= 0 )
                          {
                            v38 = (IUnknown *)this[3];
                            ppvOut = 0;
                            v4 = IUnknown_QueryService(
                                   v38,
                                   (const GUID *const)&SID_PerLayoutPropertyBag,
                                   &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                                   &ppvOut);
                            if ( v4 >= 0 )
                            {
                              v4 = PSPropertyBag_WriteUnknown(
                                     (IPropertyBag *)ppvOut,
                                     L"ControlPanelNavLinks",
                                     (IUnknown *)v3);
                              (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    (*(void (__fastcall **)(CControlPanelNavLinks *))(*(_QWORD *)v3 + 16LL))(v3);
  }
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_041ed7bb04083fded16b958364bb1572_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ccac  mov     [rsp-28h+arg_10], rbx
0x18000ccb1  push    rbp
0x18000ccb2  push    rsi
0x18000ccb3  push    rdi
0x18000ccb4  push    r14
0x18000ccb6  push    r15
0x18000ccb8  mov     rbp, rsp
0x18000ccbb  sub     rsp, 40h
0x18000ccbf  mov     r15, rcx
0x18000ccc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccc9  lea     r14, WPP_GLOBAL_Control
0x18000ccd0  cmp     rcx, r14
0x18000ccd3  jz      short loc_18000CCF0
0x18000ccd5  test    byte ptr [rcx+1Ch], 8
0x18000ccd9  jz      short loc_18000CCF0
0x18000ccdb  mov     rcx, [rcx+10h]
0x18000ccdf  lea     r8, WPP_041ed7bb04083fded16b958364bb1572_Traceguids
0x18000cce6  mov     edx, 0Ah
0x18000cceb  call    WPP_SF_
0x18000ccf0  mov     ecx, 18h; this
0x18000ccf5  mov     [rbp+ppvOut], 0
0x18000ccfd  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000cd02  mov     [rbp+arg_8], rax
0x18000cd06  mov     rsi, rax
0x18000cd09  test    rax, rax
0x18000cd0c  jz      short loc_18000CD29
0x18000cd0e  lea     rax, ??_7CControlPanelNavLinks@@6B@; const CControlPanelNavLinks::`vftable'
0x18000cd15  mov     qword ptr [rsi+8], 0
0x18000cd1d  mov     [rsi], rax
0x18000cd20  mov     dword ptr [rsi+10h], 1
0x18000cd27  jmp     short loc_18000CD2B
0x18000cd29  xor     esi, esi
0x18000cd2b  mov     rcx, [r15+28h]; this
0x18000cd2f  mov     rax, rsi
0x18000cd32  neg     rax
0x18000cd35  sbb     edi, edi
0x18000cd37  not     edi
0x18000cd39  and     edi, 8007000Eh
0x18000cd3f  call    ?IsFwCategoryEnabled@CFwProfileMgr@@QEAAHXZ; CFwProfileMgr::IsFwCategoryEnabled(void)
0x18000cd44  mov     ebx, eax
0x18000cd46  test    rsi, rsi
0x18000cd49  jz      loc_18000D01A
0x18000cd4f  lea     rax, [rbp+ppvOut]
0x18000cd53  xor     edx, edx
0x18000cd55  mov     [rsp+40h+var_10], rax
0x18000cd5a  mov     rcx, rsi
0x18000cd5d  lea     rax, aPageconfigurea; "PageConfigureApps"
0x18000cd64  mov     [rsp+40h+var_18], rax
0x18000cd69  lea     rax, aMicrosoftWindo; "Microsoft.WindowsFirewall"
0x18000cd70  lea     r9d, [rdx+19h]
0x18000cd74  mov     [rsp+40h+var_20], rax
0x18000cd79  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x18000cd7e  mov     edi, eax
0x18000cd80  test    eax, eax
0x18000cd82  js      loc_18000D00B
0x18000cd88  mov     rdx, [rbp+ppvOut]; struct CControlPanelNavLink *
0x18000cd8c  test    ebx, ebx
0x18000cd8e  setz    r14b
0x18000cd92  xor     r8d, r8d; unsigned int
0x18000cd95  mov     [rdx+50h], r14b
0x18000cd99  call    ?RegisterNavLinkSQM@CHubPage@@AEAAXPEAVCControlPanelNavLink@@K@Z; CHubPage::RegisterNavLinkSQM(CControlPanelNavLink *,ulong)
0x18000cd9e  lea     rax, [rbp+ppvOut]
0x18000cda2  xor     edx, edx
0x18000cda4  mov     [rsp+40h+var_10], rax
0x18000cda9  mov     rcx, rsi
0x18000cdac  lea     rax, aPageconfigures; "PageConfigureSettings"
0x18000cdb3  mov     [rsp+40h+var_18], rax
0x18000cdb8  lea     rax, aMicrosoftWindo; "Microsoft.WindowsFirewall"
0x18000cdbf  lea     r9d, [rdx+1Ah]
0x18000cdc3  mov     [rsp+40h+var_20], rax
0x18000cdc8  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x18000cdcd  mov     edi, eax
0x18000cdcf  test    eax, eax
0x18000cdd1  js      loc_18000D004
0x18000cdd7  mov     rbx, [rbp+ppvOut]
0x18000cddb  mov     rcx, rbx; this
0x18000cdde  call    ?SetIcon@CControlPanelNavLink@@QEAAJPEAUHINSTANCE__@@H@Z; CControlPanelNavLink::SetIcon(HINSTANCE__ *,int)
0x18000cde3  mov     r8d, 1; unsigned int
0x18000cde9  mov     [rbx+50h], r14b
0x18000cded  mov     rdx, rbx; struct CControlPanelNavLink *
0x18000cdf0  mov     edi, eax
0x18000cdf2  call    ?RegisterNavLinkSQM@CHubPage@@AEAAXPEAVCControlPanelNavLink@@K@Z; CHubPage::RegisterNavLinkSQM(CControlPanelNavLink *,ulong)
0x18000cdf7  test    edi, edi
0x18000cdf9  js      loc_18000D004
0x18000cdff  lea     rax, [rbp+ppvOut]
0x18000ce03  xor     edx, edx
0x18000ce05  mov     [rsp+40h+var_10], rax
0x18000ce0a  mov     rcx, rsi
0x18000ce0d  lea     rax, aPageconfigures; "PageConfigureSettings"
0x18000ce14  mov     [rsp+40h+var_18], rax
0x18000ce19  lea     rax, aMicrosoftWindo; "Microsoft.WindowsFirewall"
0x18000ce20  lea     r9d, [rdx+18h]
0x18000ce24  mov     [rsp+40h+var_20], rax
0x18000ce29  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x18000ce2e  mov     edi, eax
0x18000ce30  test    eax, eax
0x18000ce32  js      loc_18000D004
0x18000ce38  mov     rbx, [rbp+ppvOut]
0x18000ce3c  mov     rcx, rbx; this
0x18000ce3f  call    ?SetIcon@CControlPanelNavLink@@QEAAJPEAUHINSTANCE__@@H@Z; CControlPanelNavLink::SetIcon(HINSTANCE__ *,int)
0x18000ce44  mov     r8d, 2; unsigned int
0x18000ce4a  mov     [rbx+50h], r14b
0x18000ce4e  mov     rdx, rbx; struct CControlPanelNavLink *
0x18000ce51  mov     edi, eax
0x18000ce53  call    ?RegisterNavLinkSQM@CHubPage@@AEAAXPEAVCControlPanelNavLink@@K@Z; CHubPage::RegisterNavLinkSQM(CControlPanelNavLink *,ulong)
0x18000ce58  test    edi, edi
0x18000ce5a  js      loc_18000D004
0x18000ce60  lea     rax, [rbp+ppvOut]
0x18000ce64  xor     edx, edx
0x18000ce66  mov     [rsp+40h+var_10], rax
0x18000ce6b  mov     rcx, rsi
0x18000ce6e  lea     rax, aPagerestoredef; "PageRestoreDefaults"
0x18000ce75  mov     [rsp+40h+var_18], rax
0x18000ce7a  lea     rax, aMicrosoftWindo; "Microsoft.WindowsFirewall"
0x18000ce81  lea     r9d, [rdx+21h]
0x18000ce85  mov     [rsp+40h+var_20], rax
0x18000ce8a  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x18000ce8f  mov     edi, eax
0x18000ce91  test    eax, eax
0x18000ce93  js      loc_18000D004
0x18000ce99  mov     rbx, [rbp+ppvOut]
0x18000ce9d  mov     rcx, rbx; this
0x18000cea0  call    ?SetIcon@CControlPanelNavLink@@QEAAJPEAUHINSTANCE__@@H@Z; CControlPanelNavLink::SetIcon(HINSTANCE__ *,int)
0x18000cea5  mov     r8d, 3; unsigned int
0x18000ceab  mov     [rbx+50h], r14b
0x18000ceaf  mov     rdx, rbx; struct CControlPanelNavLink *
0x18000ceb2  mov     edi, eax
0x18000ceb4  call    ?RegisterNavLinkSQM@CHubPage@@AEAAXPEAVCControlPanelNavLink@@K@Z; CHubPage::RegisterNavLinkSQM(CControlPanelNavLink *,ulong)
0x18000ceb9  test    edi, edi
0x18000cebb  js      loc_18000D004
0x18000cec1  lea     rax, [rbp+ppvOut]
0x18000cec5  mov     rcx, rsi
0x18000cec8  mov     [rsp+40h+var_18], rax
0x18000cecd  call    ?AddLinkNotify@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IHPEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkNotify(CPNAV_LIST,HINSTANCE__ *,uint,int,CControlPanelNavLink * *)
0x18000ced2  mov     edi, eax
0x18000ced4  test    eax, eax
0x18000ced6  js      loc_18000D004
0x18000cedc  mov     rcx, [rbp+ppvOut]; this
0x18000cee0  call    ?SetIcon@CControlPanelNavLink@@QEAAJPEAUHINSTANCE__@@H@Z; CControlPanelNavLink::SetIcon(HINSTANCE__ *,int)
0x18000cee5  mov     rdx, [rbp+ppvOut]; struct CControlPanelNavLink *
0x18000cee9  mov     r8d, 5; unsigned int
0x18000ceef  mov     edi, eax
0x18000cef1  call    ?RegisterNavLinkSQM@CHubPage@@AEAAXPEAVCControlPanelNavLink@@K@Z; CHubPage::RegisterNavLinkSQM(CControlPanelNavLink *,ulong)
0x18000cef6  test    edi, edi
0x18000cef8  js      loc_18000D004
0x18000cefe  lea     rax, [rbp+ppvOut]
0x18000cf02  xor     edx, edx
0x18000cf04  mov     [rsp+40h+var_10], rax
0x18000cf09  mov     rcx, rsi
0x18000cf0c  lea     rax, aNetwork; "Network"
0x18000cf13  mov     [rsp+40h+var_18], rax
0x18000cf18  lea     rax, aMicrosoftTroub; "Microsoft.Troubleshooting"
0x18000cf1f  lea     r9d, [rdx+4Eh]
0x18000cf23  mov     [rsp+40h+var_20], rax
0x18000cf28  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x18000cf2d  mov     edi, eax
0x18000cf2f  test    eax, eax
0x18000cf31  js      loc_18000D004
0x18000cf37  mov     rdx, [rbp+ppvOut]; struct CControlPanelNavLink *
0x18000cf3b  mov     r8d, 4; unsigned int
0x18000cf41  call    ?RegisterNavLinkSQM@CHubPage@@AEAAXPEAVCControlPanelNavLink@@K@Z; CHubPage::RegisterNavLinkSQM(CControlPanelNavLink *,ulong)
0x18000cf46  mov     edx, 1
0x18000cf4b  mov     [rsp+40h+var_10], 0
0x18000cf54  lea     rax, aMicrosoftActio; "Microsoft.ActionCenter"
0x18000cf5b  mov     [rsp+40h+var_18], 0
0x18000cf64  mov     rcx, rsi
0x18000cf67  mov     [rsp+40h+var_20], rax
0x18000cf6c  lea     r9d, [rdx+1Bh]
0x18000cf70  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x18000cf75  mov     edi, eax
0x18000cf77  test    eax, eax
0x18000cf79  js      loc_18000D004
0x18000cf7f  mov     edx, 1
0x18000cf84  mov     [rsp+40h+var_10], 0
0x18000cf8d  lea     rax, aMicrosoftNetwo; "Microsoft.NetworkAndSharingCenter"
0x18000cf94  mov     [rsp+40h+var_18], 0
0x18000cf9d  mov     rcx, rsi
0x18000cfa0  mov     [rsp+40h+var_20], rax
0x18000cfa5  lea     r9d, [rdx+1Ah]
0x18000cfa9  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x18000cfae  mov     edi, eax
0x18000cfb0  test    eax, eax
0x18000cfb2  js      short loc_18000D004
0x18000cfb4  mov     rcx, [r15+18h]; punk
0x18000cfb8  lea     r9, [rbp+ppvOut]; ppvOut
0x18000cfbc  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18000cfc3  mov     [rbp+ppvOut], 0
0x18000cfcb  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x18000cfd2  call    cs:__imp_IUnknown_QueryService
0x18000cfd8  mov     edi, eax
0x18000cfda  test    eax, eax
0x18000cfdc  js      short loc_18000D004
0x18000cfde  mov     rcx, [rbp+ppvOut]; propBag
0x18000cfe2  lea     rdx, propName; "ControlPanelNavLinks"
0x18000cfe9  mov     r8, rsi; punk
0x18000cfec  call    cs:__imp_PSPropertyBag_WriteUnknown
0x18000cff2  mov     rcx, [rbp+ppvOut]
0x18000cff6  mov     edi, eax
0x18000cff8  mov     rax, [rcx]
0x18000cffb  mov     rax, [rax+10h]
0x18000cfff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d004  lea     r14, WPP_GLOBAL_Control
0x18000d00b  mov     rax, [rsi]
0x18000d00e  mov     rcx, rsi
0x18000d011  mov     rax, [rax+10h]
0x18000d015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d01a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d021  cmp     rcx, r14
0x18000d024  jz      short loc_18000D044
0x18000d026  test    byte ptr [rcx+1Ch], 8
0x18000d02a  jz      short loc_18000D044
0x18000d02c  mov     rcx, [rcx+10h]
0x18000d030  lea     r8, WPP_041ed7bb04083fded16b958364bb1572_Traceguids
0x18000d037  mov     edx, 0Bh
0x18000d03c  mov     r9d, edi
0x18000d03f  call    WPP_SF_d
0x18000d044  mov     rbx, [rsp+40h+arg_10]
0x18000d04c  mov     eax, edi
0x18000d04e  add     rsp, 40h
0x18000d052  pop     r15
0x18000d054  pop     r14
0x18000d056  pop     rdi
0x18000d057  pop     rsi
0x18000d058  pop     rbp
0x18000d059  retn
```

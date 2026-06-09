# COSKKeyboardManager::CreateKeyboard(ushort const *,ushort const *,IAccSoftKeyboardUI * *)

- ea: `0x14000fe10`
- end: `0x14000ffd6`
- name: `?CreateKeyboard@COSKKeyboardManager@@AEAAJPEBG0PEAPEAUIAccSoftKeyboardUI@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(COSKKeyboardManager *__hidden this, const unsigned __int16 *, OLECHAR *psz, struct IAccSoftKeyboardUI **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140010120`
- `0x14001025c`

## callees

- `0x14000f93c`
- `0x14000fe10`
- `0x140011d2c`
- `0x140012db0`
- `0x14001b7bc`
- `0x140027010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14000fe58`
- `ole32!CoCreateInstance` at `0x14000fe58`
- `OLEAUT32!__imp_SysAllocString` at `0x14000fe8c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000fe8c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ff42`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ff4b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ff42`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ff4b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14000ff68`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14000ff84`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14000ff68`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14000ff84`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x14000ffa2`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x14000ffa2`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x14000ff97`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x14000ff97`
- `DUI70!StrToID` at `0x14000ff5c`
- `DUI70!StrToID` at `0x14000ff78`
- `DUI70!StrToID` at `0x14000ff5c`
- `DUI70!StrToID` at `0x14000ff78`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COSKKeyboardManager::CreateKeyboard(
        DirectUI::Element **this,
        const unsigned __int16 *a2,
        OLECHAR *psz,
        struct IAccSoftKeyboardUI **a4)
{
  HRESULT Instance; // edi
  OLECHAR *v9; // rbx
  __int64 v10; // rdx
  bool ShouldRunSecureOnLockScreen; // al
  DirectUI::Element *v12; // rbx
  unsigned __int16 v13; // ax
  DirectUI::Element *Descendent; // rbx
  unsigned __int16 v15; // ax
  DirectUI::Element *v16; // rbx
  struct IAccSoftKeyboardUI *v17; // rax
  BSTR bstrString[2]; // [rsp+30h] [rbp-28h] BYREF
  GUID v20; // [rsp+40h] [rbp-18h] BYREF
  struct IAccSoftKeyboardUI *ppv; // [rsp+A8h] [rbp+50h] BYREF

  *a4 = 0;
  ppv = 0;
  Instance = CoCreateInstance(
               &GUID_bdcd51fb_55a0_4486_908c_5240f23698ac,
               0,
               1u,
               &GUID_615e499c_60ab_44b2_b14f_86fe516f9b71,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = COSKKeyboardManager::InitializeKeyboard((COSKKeyboardManager *)this, ppv, a2);
    if ( Instance >= 0 )
    {
      bstrString[0] = 0;
      v9 = SysAllocString(psz);
      if ( v9 )
      {
        Instance = (*(__int64 (__fastcall **)(DirectUI::Element *, OLECHAR *, DirectUI::Element *, BSTR *))(*(_QWORD *)this[10] + 40LL))(
                     this[10],
                     v9,
                     this[18],
                     bstrString);
        if ( Instance >= 0 )
        {
          v20 = GUID_NULL;
          Instance = (*(__int64 (__fastcall **)(struct IAccSoftKeyboardUI *, BSTR, DirectUI::Element *, GUID *, _DWORD))(*(_QWORD *)ppv + 32LL))(
                       ppv,
                       bstrString[0],
                       this[18],
                       &v20,
                       0);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(struct IAccSoftKeyboardUI *, __int64))(*(_QWORD *)ppv + 56LL))(ppv, 1);
            if ( Instance >= 0 )
            {
              LOBYTE(v10) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl'::`2'::impl,
                v10);
              ShouldRunSecureOnLockScreen = COSKUtils::ShouldRunSecureOnLockScreen();
              Instance = (*(__int64 (__fastcall **)(struct IAccSoftKeyboardUI *, bool))(*(_QWORD *)ppv + 40LL))(
                           ppv,
                           ShouldRunSecureOnLockScreen);
            }
          }
        }
        SysFreeString(bstrString[0]);
        SysFreeString(v9);
        if ( Instance >= 0 )
        {
          v12 = this[15];
          v13 = StrToID(a2);
          Descendent = DirectUI::Element::FindDescendent(v12, v13);
          v15 = StrToID(L"KBControl");
          v16 = DirectUI::Element::FindDescendent(Descendent, v15);
          DirectUI::Element::SetWidth(v16, 100);
          DirectUI::Element::SetHeight(v16, 100);
          v17 = ppv;
          ppv = 0;
          *a4 = v17;
        }
      }
      else
      {
        Instance = -2147024882;
      }
    }
  }
  ATL::CComPtrBase<ITPLangMod>::~CComPtrBase<ITPLangMod>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14000fe10  push    rbp
0x14000fe12  push    rbx
0x14000fe13  push    rsi
0x14000fe14  push    rdi
0x14000fe15  push    r14
0x14000fe17  push    r15
0x14000fe19  mov     rbp, rsp
0x14000fe1c  sub     rsp, 58h
0x14000fe20  mov     r15, r9
0x14000fe23  mov     rbx, r8
0x14000fe26  mov     r14, rdx
0x14000fe29  mov     rsi, rcx
0x14000fe2c  mov     qword ptr [r9], 0
0x14000fe33  mov     [rbp+arg_18], 0
0x14000fe3b  lea     rax, [rbp+arg_18]
0x14000fe3f  mov     [rsp+58h+ppv], rax; ppv
0x14000fe44  lea     r9, _GUID_615e499c_60ab_44b2_b14f_86fe516f9b71; riid
0x14000fe4b  xor     edx, edx; pUnkOuter
0x14000fe4d  lea     r8d, [rdx+1]; dwClsContext
0x14000fe51  lea     rcx, _GUID_bdcd51fb_55a0_4486_908c_5240f23698ac; rclsid
0x14000fe58  call    cs:__imp_CoCreateInstance
0x14000fe5e  mov     edi, eax
0x14000fe60  test    eax, eax
0x14000fe62  js      loc_14000FFBE
0x14000fe68  mov     r8, r14; unsigned __int16 *
0x14000fe6b  mov     rdx, [rbp+arg_18]; struct IAccSoftKeyboardUI *
0x14000fe6f  mov     rcx, rsi; this
0x14000fe72  call    ?InitializeKeyboard@COSKKeyboardManager@@AEAAJPEAUIAccSoftKeyboardUI@@PEBG@Z; COSKKeyboardManager::InitializeKeyboard(IAccSoftKeyboardUI *,ushort const *)
0x14000fe77  mov     edi, eax
0x14000fe79  test    eax, eax
0x14000fe7b  js      loc_14000FFBE
0x14000fe81  mov     [rbp+bstrString], 0
0x14000fe89  mov     rcx, rbx; psz
0x14000fe8c  call    cs:__imp_SysAllocString
0x14000fe92  mov     rbx, rax
0x14000fe95  test    rax, rax
0x14000fe98  jz      loc_14000FFB9
0x14000fe9e  mov     rcx, [rsi+50h]
0x14000fea2  mov     rdx, [rcx]
0x14000fea5  mov     rax, [rdx+28h]
0x14000fea9  lea     r9, [rbp+bstrString]
0x14000fead  mov     r8, [rsi+90h]
0x14000feb4  mov     rdx, rbx
0x14000feb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000febc  mov     edi, eax
0x14000febe  test    eax, eax
0x14000fec0  js      short loc_14000FF3E
0x14000fec2  mov     rcx, [rbp+arg_18]
0x14000fec6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000fecd  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x14000fed2  mov     rax, [rcx]
0x14000fed5  mov     dword ptr [rsp+58h+ppv], 0
0x14000fedd  lea     r9, [rbp+var_18]
0x14000fee1  mov     r8, [rsi+90h]
0x14000fee8  mov     rdx, [rbp+bstrString]
0x14000feec  mov     rax, [rax+20h]
0x14000fef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fef5  mov     edi, eax
0x14000fef7  test    eax, eax
0x14000fef9  js      short loc_14000FF3E
0x14000fefb  mov     rcx, [rbp+arg_18]
0x14000feff  mov     rax, [rcx]
0x14000ff02  mov     edx, 1
0x14000ff07  mov     rax, [rax+38h]
0x14000ff0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff10  mov     edi, eax
0x14000ff12  test    eax, eax
0x14000ff14  js      short loc_14000FF3E
0x14000ff16  mov     dl, 1
0x14000ff18  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen> `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl(void)'::`2'::impl
0x14000ff1f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000ff24  call    ?ShouldRunSecureOnLockScreen@COSKUtils@@SA_NXZ; COSKUtils::ShouldRunSecureOnLockScreen(void)
0x14000ff29  mov     rcx, [rbp+arg_18]
0x14000ff2d  mov     r8, [rcx]
0x14000ff30  movzx   edx, al
0x14000ff33  mov     rax, [r8+28h]
0x14000ff37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff3c  mov     edi, eax
0x14000ff3e  mov     rcx, [rbp+bstrString]; bstrString
0x14000ff42  call    cs:__imp_SysFreeString
0x14000ff48  mov     rcx, rbx; bstrString
0x14000ff4b  call    cs:__imp_SysFreeString
0x14000ff51  test    edi, edi
0x14000ff53  js      short loc_14000FFBE
0x14000ff55  mov     rbx, [rsi+78h]
0x14000ff59  mov     rcx, r14
0x14000ff5c  call    cs:__imp_StrToID
0x14000ff62  movzx   edx, ax
0x14000ff65  mov     rcx, rbx
0x14000ff68  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14000ff6e  mov     rbx, rax
0x14000ff71  lea     rcx, aKbcontrol; "KBControl"
0x14000ff78  call    cs:__imp_StrToID
0x14000ff7e  movzx   edx, ax
0x14000ff81  mov     rcx, rbx
0x14000ff84  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14000ff8a  mov     rbx, rax
0x14000ff8d  mov     esi, 64h ; 'd'
0x14000ff92  mov     edx, esi
0x14000ff94  mov     rcx, rax
0x14000ff97  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x14000ff9d  mov     edx, esi
0x14000ff9f  mov     rcx, rbx
0x14000ffa2  call    cs:__imp_?SetHeight@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetHeight(int)
0x14000ffa8  mov     rax, [rbp+arg_18]
0x14000ffac  mov     [rbp+arg_18], 0
0x14000ffb4  mov     [r15], rax
0x14000ffb7  jmp     short loc_14000FFBE
0x14000ffb9  mov     edi, 8007000Eh
0x14000ffbe  lea     rcx, [rbp+arg_18]
0x14000ffc2  call    ??1?$CComPtrBase@UITPLangMod@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITPLangMod>::~CComPtrBase<ITPLangMod>(void)
0x14000ffc7  mov     eax, edi
0x14000ffc9  add     rsp, 58h
0x14000ffcd  pop     r15
0x14000ffcf  pop     r14
0x14000ffd1  pop     rdi
0x14000ffd2  pop     rsi
0x14000ffd3  pop     rbx
0x14000ffd4  pop     rbp
0x14000ffd5  retn
```

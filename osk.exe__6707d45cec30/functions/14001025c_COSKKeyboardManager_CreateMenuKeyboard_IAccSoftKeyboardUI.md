# COSKKeyboardManager::CreateMenuKeyboard(IAccSoftKeyboardUI * *)

- ea: `0x14001025c`
- end: `0x140010337`
- name: `?CreateMenuKeyboard@COSKKeyboardManager@@AEAAJPEAPEAUIAccSoftKeyboardUI@@@Z`
- size: `219`
- prototype: `int(COSKKeyboardManager *__hidden this, struct IAccSoftKeyboardUI **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140010120`

## callees

- `0x140009f28`
- `0x14000fe10`
- `0x14001025c`
- `0x140012db0`
- `0x14001b7bc`
- `0x140025d70`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1400102c6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140010300`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1400102c6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140010300`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x140010317`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x140010317`
- `DUI70!StrToID` at `0x1400102ba`
- `DUI70!StrToID` at `0x1400102f4`
- `DUI70!StrToID` at `0x1400102ba`
- `DUI70!StrToID` at `0x1400102f4`

## pseudocode

```c
__int64 __fastcall COSKKeyboardManager::CreateMenuKeyboard(DirectUI::Element **this, struct IAccSoftKeyboardUI **a2)
{
  __int64 v3; // rdx
  int Keyboard; // edi
  DirectUI::Element *v5; // rbx
  unsigned __int16 v6; // ax
  DirectUI::Element *Descendent; // rbx
  unsigned __int16 v8; // ax
  struct DirectUI::Element *v9; // rax
  DirectUI::Element *v10; // rcx
  unsigned __int16 v12[16]; // [rsp+20h] [rbp-38h] BYREF

  Keyboard = COSKKeyboardManager::CreateKeyboard(this, L"SoftKeyboardMenu", (OLECHAR *)L"\\oskmenu", a2);
  if ( Keyboard >= 0 )
  {
    LOBYTE(v3) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl'::`2'::impl,
      v3);
    if ( COSKUtils::ShouldRunSecureOnLockScreen() )
    {
      v5 = this[15];
      v6 = StrToID(L"SoftKeyboardMenu");
      Descendent = DirectUI::Element::FindDescendent(v5, v6);
      if ( (int)StringCchPrintfW(v12, 0x10u, L"%x", 67073) >= 0 )
      {
        v8 = StrToID(v12);
        v9 = DirectUI::Element::FindDescendent(Descendent, v8);
        if ( v9 )
        {
          v10 = (DirectUI::Element *)*((_QWORD *)v9 + 10);
          if ( v10 )
            DirectUI::Element::Remove(v10, v9);
        }
      }
    }
  }
  return (unsigned int)Keyboard;
}

```

## disassembly

```asm
0x14001025c  mov     [rsp+arg_10], rbx
0x140010261  push    rdi
0x140010262  sub     rsp, 50h
0x140010266  mov     rax, cs:__security_cookie
0x14001026d  xor     rax, rsp
0x140010270  mov     [rsp+58h+var_18], rax
0x140010275  mov     r9, rdx; struct IAccSoftKeyboardUI **
0x140010278  lea     r8, aOskmenu; "\\oskmenu"
0x14001027f  lea     rdx, aSoftkeyboardme; "SoftKeyboardMenu"
0x140010286  mov     rbx, rcx
0x140010289  call    ?CreateKeyboard@COSKKeyboardManager@@AEAAJPEBG0PEAPEAUIAccSoftKeyboardUI@@@Z; COSKKeyboardManager::CreateKeyboard(ushort const *,ushort const *,IAccSoftKeyboardUI * *)
0x14001028e  mov     edi, eax
0x140010290  test    eax, eax
0x140010292  js      loc_14001031D
0x140010298  mov     dl, 1
0x14001029a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen> `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl(void)'::`2'::impl
0x1400102a1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400102a6  call    ?ShouldRunSecureOnLockScreen@COSKUtils@@SA_NXZ; COSKUtils::ShouldRunSecureOnLockScreen(void)
0x1400102ab  test    al, al
0x1400102ad  jz      short loc_14001031D
0x1400102af  mov     rbx, [rbx+78h]
0x1400102b3  lea     rcx, aSoftkeyboardme; "SoftKeyboardMenu"
0x1400102ba  call    cs:__imp_StrToID
0x1400102c0  movzx   edx, ax
0x1400102c3  mov     rcx, rbx
0x1400102c6  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1400102cc  mov     r9d, 10601h
0x1400102d2  lea     r8, asc_14002B6EC; "%x"
0x1400102d9  mov     edx, 10h; unsigned __int64
0x1400102de  lea     rcx, [rsp+58h+var_38]; unsigned __int16 *
0x1400102e3  mov     rbx, rax
0x1400102e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400102eb  test    eax, eax
0x1400102ed  js      short loc_14001031D
0x1400102ef  lea     rcx, [rsp+58h+var_38]
0x1400102f4  call    cs:__imp_StrToID
0x1400102fa  movzx   edx, ax
0x1400102fd  mov     rcx, rbx
0x140010300  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x140010306  test    rax, rax
0x140010309  jz      short loc_14001031D
0x14001030b  mov     rcx, [rax+50h]
0x14001030f  test    rcx, rcx
0x140010312  jz      short loc_14001031D
0x140010314  mov     rdx, rax
0x140010317  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x14001031d  mov     eax, edi
0x14001031f  mov     rcx, [rsp+58h+var_18]
0x140010324  xor     rcx, rsp; StackCookie
0x140010327  call    __security_check_cookie
0x14001032c  mov     rbx, [rsp+58h+arg_10]
0x140010331  add     rsp, 50h
0x140010335  pop     rdi
0x140010336  retn
```

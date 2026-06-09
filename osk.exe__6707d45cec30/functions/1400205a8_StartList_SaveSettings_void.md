# StartList::SaveSettings(void)

- ea: `0x1400205a8`
- end: `0x1400206b2`
- name: `?SaveSettings@StartList@@AEAAJXZ`
- size: `266`
- prototype: `__int64 __fastcall(StartList *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001d9b8`
- `0x14001fdc8`
- `0x140020ebc`

## callees

- `0x140004700`
- `0x140009524`
- `0x14001c748`
- `0x14001c768`
- `0x14001dc50`
- `0x1400205a8`
- `0x140021068`
- `0x1400255dc`
- `0x14002562c`

## string_xrefs

- `0x14002062f`: `SettingConfiguration`
- `0x140020671`: `Configuration`
- `0x14002060c`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x140020678`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x140020605`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::SaveSettings(StartList *this)
{
  bool IsDesktopOOBEUserSessionActive; // bp
  int IsInteractiveUser; // edi
  const WCHAR *v4; // rdx
  unsigned __int16 *v5; // rbx
  StartList *v6; // rdx
  unsigned __int16 *v7; // rbx
  unsigned int v8; // ebx
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 *v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  _Trace::_Trace((_Trace *)v10, L"StartList::SaveSettings", (int *)&v11);
  IsDesktopOOBEUserSessionActive = CATUtils::IsDesktopOOBEUserSessionActive();
  IsInteractiveUser = CATUtils::IsInteractiveUser();
  if ( IsDesktopOOBEUserSessionActive )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v12);
    StartList::BuildConfigString(&v12, (char *)this + 144);
    v4 = StartList::_accessibilityKeyString;
    if ( !IsInteractiveUser )
      v4 = StartList::_oobeAccessibilityKeyString;
    v5 = v12;
    anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
      (HKEY)(-(__int64)(IsInteractiveUser != 0) - 2147483646),
      v4,
      StartList::_settingConfiguration,
      v12);
    ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
  }
  if ( IsInteractiveUser )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v12);
    v6 = (StartList *)((char *)this + 48);
    if ( !IsDesktopOOBEUserSessionActive )
      v6 = this;
    StartList::BuildConfigString(&v12, v6);
    v7 = v12;
    anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
      HKEY_CURRENT_USER,
      StartList::_accessibilityKeyString,
      StartList::_configuration,
      v12);
    ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
  }
  v8 = v11;
  _Trace::~_Trace((_Trace *)v10);
  return v8;
}

```

## disassembly

```asm
0x1400205a8  mov     rax, rsp
0x1400205ab  mov     [rax+8], rbx
0x1400205af  push    rbp
0x1400205b0  push    rsi
0x1400205b1  push    rdi
0x1400205b2  sub     rsp, 30h
0x1400205b6  mov     rsi, rcx
0x1400205b9  mov     dword ptr [rax+10h], 0
0x1400205c0  lea     r8, [rax+10h]; int *
0x1400205c4  lea     rdx, aStartlistSaves_0; "StartList::SaveSettings"
0x1400205cb  lea     rcx, [rax-28h]; this
0x1400205cf  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x1400205d4  nop
0x1400205d5  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x1400205da  mov     bpl, al
0x1400205dd  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x1400205e2  mov     edi, eax
0x1400205e4  test    bpl, bpl
0x1400205e7  jz      short loc_140020645
0x1400205e9  lea     rcx, [rsp+48h+arg_10]
0x1400205ee  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1400205f3  nop
0x1400205f4  lea     rdx, [rsi+90h]
0x1400205fb  lea     rcx, [rsp+48h+arg_10]
0x140020600  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x140020605  lea     rax, ?_oobeAccessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14002060c  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140020613  test    edi, edi
0x140020615  cmovz   rdx, rax; lpSubKey
0x140020619  mov     eax, edi
0x14002061b  neg     eax
0x14002061d  sbb     rcx, rcx
0x140020620  add     rcx, 0FFFFFFFF80000002h; hKey
0x140020627  mov     rbx, [rsp+48h+arg_10]
0x14002062c  mov     r9, rbx; unsigned __int16 *
0x14002062f  lea     r8, ?_settingConfiguration@StartList@@0PAGA; "SettingConfiguration"
0x140020636  call    _anonymous_namespace___WriteAccessibilityConfigStringListToRegistry
0x14002063b  nop
0x14002063c  lea     rcx, [rbx-18h]; this
0x140020640  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140020645  test    edi, edi
0x140020647  jz      short loc_140020695
0x140020649  lea     rcx, [rsp+48h+arg_10]
0x14002064e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140020653  nop
0x140020654  lea     rdx, [rsi+30h]
0x140020658  test    bpl, bpl
0x14002065b  cmovz   rdx, rsi
0x14002065f  lea     rcx, [rsp+48h+arg_10]
0x140020664  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x140020669  mov     rbx, [rsp+48h+arg_10]
0x14002066e  mov     r9, rbx; unsigned __int16 *
0x140020671  lea     r8, ?_configuration@StartList@@0PAGA; "Configuration"
0x140020678  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14002067f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140020686  call    _anonymous_namespace___WriteAccessibilityConfigStringListToRegistry
0x14002068b  nop
0x14002068c  lea     rcx, [rbx-18h]; this
0x140020690  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140020695  mov     ebx, [rsp+48h+arg_8]
0x140020699  lea     rcx, [rsp+48h+var_28]; this
0x14002069e  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x1400206a3  mov     eax, ebx
0x1400206a5  mov     rbx, [rsp+48h+arg_0]
0x1400206aa  add     rsp, 30h
0x1400206ae  pop     rdi
0x1400206af  pop     rsi
0x1400206b0  pop     rbp
0x1400206b1  retn
```

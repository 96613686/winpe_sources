# Accommodation::Open(ushort const *)

- ea: `0x14002180c`
- end: `0x140021a1f`
- name: `?Open@Accommodation@@SAPEAV1@PEBG@Z`
- size: `531`
- prototype: `struct Accommodation *__fastcall(const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001d3ac`
- `0x14001f060`
- `0x140020938`
- `0x140020ebc`

## callees

- `0x1400020d8`
- `0x140004700`
- `0x140005c90`
- `0x140007e90`
- `0x140009524`
- `0x140009cd8`
- `0x14001c4e0`
- `0x14002140c`
- `0x1400217b0`
- `0x14002180c`
- `0x140021a28`
- `0x140021a60`
- `0x140025d42`

## string_xrefs

- `0x14002182f`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs\`
- `0x14002199f`: `SecureDesktopAccommodation`
- `0x14002198a`: `CopySettingsToLockedDesktop`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct Accommodation *__fastcall Accommodation::Open(const unsigned __int16 *a1)
{
  LPCWSTR v2; // rbx
  ATL::CStringData *v3; // rcx
  Accommodation *v4; // rax
  Accommodation *v5; // rdi
  _QWORD v7[3]; // [rsp+20h] [rbp-28h] BYREF
  ATL::CAtlException *v8; // [rsp+38h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp+10h] BYREF
  Accommodation *v10; // [rsp+60h] [rbp+18h]

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
  try
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(
      (char **)&lpSubKey,
      L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs\\",
      0x3Fu);
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, a1);
  }
  catch ( ATL::CAtlException *v8 )
  {
    v3 = (ATL::CStringData *)(lpSubKey - 12);
    goto LABEL_11;
  }
  memset(v7, 0, sizeof(v7));
  v2 = lpSubKey;
  if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v7, HKEY_LOCAL_MACHINE, lpSubKey, 0x20019u)
    || ((v4 = (Accommodation *)operator new(0x58u), (v10 = v4) == 0)
      ? (v5 = 0)
      : (v5 = Accommodation::Accommodation(v4, a1)),
        (v10 = v5) == 0) )
  {
    ATL::CRegKey::Close((ATL::CRegKey *)v7);
    v3 = (ATL::CStringData *)(v2 - 12);
LABEL_11:
    ATL::CStringData::Release(v3);
    return 0;
  }
  else
  {
    Accommodation::QueryStringValue((ATL::CRegKey *)v7, L"ApplicationName");
    Accommodation::QueryStringValue((ATL::CRegKey *)v7, L"Description");
    Accommodation::QueryStringValue((ATL::CRegKey *)v7, L"StartExe");
    Accommodation::QueryStringValue((ATL::CRegKey *)v7, L"StartParams");
    Accommodation::QueryStringValue((ATL::CRegKey *)v7, L"SimpleProfile");
    Accommodation::QueryStringValue((ATL::CRegKey *)v7, L"Profile");
    Accommodation::QueryStringValue((ATL::CRegKey *)v7, L"ATExe");
    Accommodation::QueryDWORDValue((struct ATL::CRegKey *)v7, L"TerminateOnDesktopSwitch", (unsigned int *)v5 + 16, 1u);
    Accommodation::QueryDWORDValue(
      (struct ATL::CRegKey *)v7,
      L"CopySettingsToLockedDesktop",
      (unsigned int *)v5 + 17,
      0);
    Accommodation::QueryStringValue((ATL::CRegKey *)v7, L"SecureDesktopAccommodation");
    Accommodation::QueryDWORDValue((struct ATL::CRegKey *)v7, L"PassiveAutoStartBehavior", (unsigned int *)v5 + 20, 0);
    if ( wcscmp_0(*((const wchar_t **)v5 + 5), L"SystemSetting") )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower((char *)v5 + 40);
    ATL::CRegKey::Close((ATL::CRegKey *)v7);
    ATL::CStringData::Release((ATL::CStringData *)(v2 - 12));
    return v5;
  }
}

```

## disassembly

```asm
0x14002180c  mov     [rsp+arg_0], rbx
0x140021811  mov     [rsp+arg_18], rsi
0x140021816  push    rdi
0x140021817  sub     rsp, 40h
0x14002181b  mov     rdi, rcx
0x14002181e  lea     rcx, [rsp+48h+lpSubKey]
0x140021823  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140021828  nop
0x140021829  mov     r8d, 3Fh ; '?'
0x14002182f  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows NT\\Curren"...
0x140021836  lea     rcx, [rsp+48h+lpSubKey]
0x14002183b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140021840  mov     rdx, rdi
0x140021843  lea     rcx, [rsp+48h+lpSubKey]
0x140021848  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14002184d  nop
0x14002184e  mov     [rsp+48h+var_28], 0
0x140021857  mov     [rsp+48h+var_20], 0
0x140021860  mov     [rsp+48h+var_18], 0
0x140021869  mov     r9d, 20019h; unsigned int
0x14002186f  mov     rbx, [rsp+48h+lpSubKey]
0x140021874  mov     r8, rbx; lpSubKey
0x140021877  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14002187e  lea     rcx, [rsp+48h+var_28]; this
0x140021883  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140021888  test    eax, eax
0x14002188a  jz      short loc_1400218A0
0x14002188c  lea     rcx, [rsp+48h+var_28]; this
0x140021891  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140021896  nop
0x140021897  lea     rcx, [rbx-18h]
0x14002189b  jmp     loc_140021A08
0x1400218a0  mov     ecx, 58h ; 'X'; Size
0x1400218a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400218aa  mov     [rsp+48h+arg_10], rax
0x1400218af  test    rax, rax
0x1400218b2  jz      short loc_1400218C4
0x1400218b4  mov     rdx, rdi; unsigned __int16 *
0x1400218b7  mov     rcx, rax; this
0x1400218ba  call    ??0Accommodation@@AEAA@PEBG@Z; Accommodation::Accommodation(ushort const *)
0x1400218bf  mov     rdi, rax
0x1400218c2  jmp     short loc_1400218C6
0x1400218c4  xor     edi, edi
0x1400218c6  mov     [rsp+48h+arg_10], rdi
0x1400218cb  test    rdi, rdi
0x1400218ce  jnz     short loc_1400218D2
0x1400218d0  jmp     short loc_14002188C
0x1400218d2  lea     r8, [rdi+8]
0x1400218d6  lea     rdx, aApplicationnam; "ApplicationName"
0x1400218dd  lea     rcx, [rsp+48h+var_28]; this
0x1400218e2  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400218e7  lea     r8, [rdi+10h]
0x1400218eb  lea     rdx, aDescription; "Description"
0x1400218f2  lea     rcx, [rsp+48h+var_28]; this
0x1400218f7  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400218fc  lea     r8, [rdi+18h]
0x140021900  lea     rdx, aStartexe; "StartExe"
0x140021907  lea     rcx, [rsp+48h+var_28]; this
0x14002190c  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140021911  lea     r8, [rdi+20h]
0x140021915  lea     rdx, aStartparams; "StartParams"
0x14002191c  lea     rcx, [rsp+48h+var_28]; this
0x140021921  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140021926  lea     rsi, [rdi+28h]
0x14002192a  mov     r8, rsi
0x14002192d  lea     rdx, aSimpleprofile; "SimpleProfile"
0x140021934  lea     rcx, [rsp+48h+var_28]; this
0x140021939  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14002193e  lea     r8, [rdi+30h]
0x140021942  lea     rdx, aProfile; "Profile"
0x140021949  lea     rcx, [rsp+48h+var_28]; this
0x14002194e  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140021953  lea     r8, [rdi+38h]
0x140021957  lea     rdx, aAtexe; "ATExe"
0x14002195e  lea     rcx, [rsp+48h+var_28]; this
0x140021963  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140021968  lea     r8, [rdi+40h]; unsigned int *
0x14002196c  mov     r9d, 1; unsigned int
0x140021972  lea     rdx, aTerminateondes; "TerminateOnDesktopSwitch"
0x140021979  lea     rcx, [rsp+48h+var_28]; struct ATL::CRegKey *
0x14002197e  call    ?QueryDWORDValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAKK@Z; Accommodation::QueryDWORDValue(ATL::CRegKey &,ushort *,ulong &,ulong)
0x140021983  lea     r8, [rdi+44h]; unsigned int *
0x140021987  xor     r9d, r9d; unsigned int
0x14002198a  lea     rdx, aCopysettingsto; "CopySettingsToLockedDesktop"
0x140021991  lea     rcx, [rsp+48h+var_28]; struct ATL::CRegKey *
0x140021996  call    ?QueryDWORDValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAKK@Z; Accommodation::QueryDWORDValue(ATL::CRegKey &,ushort *,ulong &,ulong)
0x14002199b  lea     r8, [rdi+48h]
0x14002199f  lea     rdx, aSecuredesktopa; "SecureDesktopAccommodation"
0x1400219a6  lea     rcx, [rsp+48h+var_28]; this
0x1400219ab  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400219b0  lea     r8, [rdi+50h]; unsigned int *
0x1400219b4  xor     r9d, r9d; unsigned int
0x1400219b7  lea     rdx, aPassiveautosta; "PassiveAutoStartBehavior"
0x1400219be  lea     rcx, [rsp+48h+var_28]; struct ATL::CRegKey *
0x1400219c3  call    ?QueryDWORDValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAKK@Z; Accommodation::QueryDWORDValue(ATL::CRegKey &,ushort *,ulong &,ulong)
0x1400219c8  nop
0x1400219c9  lea     rdx, aSystemsetting; "SystemSetting"
0x1400219d0  mov     rcx, [rsi]; String1
0x1400219d3  call    wcscmp_0
0x1400219d8  nop
0x1400219d9  test    eax, eax
0x1400219db  jz      short loc_1400219E6
0x1400219dd  mov     rcx, rsi
0x1400219e0  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x1400219e5  nop
0x1400219e6  lea     rcx, [rsp+48h+var_28]; this
0x1400219eb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400219f0  nop
0x1400219f1  lea     rcx, [rbx-18h]; this
0x1400219f5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400219fa  mov     rax, rdi
0x1400219fd  jmp     short loc_140021A0F
0x1400219ff  mov     rcx, [rsp+48h+lpSubKey]
0x140021a04  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140021a08  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140021a0d  xor     eax, eax
0x140021a0f  mov     rbx, [rsp+48h+arg_0]
0x140021a14  mov     rsi, [rsp+48h+arg_18]
0x140021a19  add     rsp, 40h
0x140021a1d  pop     rdi
0x140021a1e  retn
```

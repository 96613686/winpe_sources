# ConsentPage::OnSetActive(void)

- ea: `0x1400172e0`
- end: `0x140017663`
- name: `?OnSetActive@ConsentPage@@MEAA_JXZ`
- size: `899`
- prototype: `__int64 __fastcall(ConsentPage *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x14000e300`
- `0x14000e978`
- `0x14000f480`
- `0x1400104bc`
- `0x140010680`
- `0x140010a10`
- `0x1400172e0`
- `0x140020420`
- `0x140020d58`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001734d`
- `KERNEL32!HeapAlloc` at `0x14001734d`
- `KERNEL32!GetProcessHeap` at `0x140017336`
- `KERNEL32!GetProcessHeap` at `0x140017336`
- `msvcrt!_wcsnicmp` at `0x140017511`
- `msvcrt!_wcsnicmp` at `0x140017531`
- `msvcrt!_wcsnicmp` at `0x140017551`
- `msvcrt!_wcsnicmp` at `0x140017511`
- `msvcrt!_wcsnicmp` at `0x140017531`
- `msvcrt!_wcsnicmp` at `0x140017551`
- `OLEAUT32!__imp_SysFreeString` at `0x140017609`
- `OLEAUT32!__imp_SysFreeString` at `0x140017626`
- `OLEAUT32!__imp_SysFreeString` at `0x140017609`
- `OLEAUT32!__imp_SysFreeString` at `0x140017626`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140017645`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140017645`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140017329`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140017329`

## string_xrefs

- `0x1400175db`: `linkContainer`
- `0x140017593`: `linkInteraction`
- `0x1400175b9`: `linkInteraction`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConsentPage::OnSetActive(ConsentPage *this)
{
  __int64 v2; // r15
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v4; // r14
  int v5; // eax
  int v6; // eax
  int v7; // eax
  const wchar_t *v8; // rdi
  const unsigned __int16 *v9; // rsi
  const wchar_t **v10; // rax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  const unsigned __int16 *v21; // [rsp+20h] [rbp-28h]
  const unsigned __int16 *v22; // [rsp+20h] [rbp-28h]
  DirectUI::Element *v23; // [rsp+30h] [rbp-18h]
  unsigned int v24[4]; // [rsp+38h] [rbp-10h] BYREF
  int v25; // [rsp+80h] [rbp+38h] BYREF
  BSTR v26; // [rsp+88h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp+48h] BYREF
  __int64 v28; // [rsp+98h] [rbp+50h] BYREF

  v2 = -1;
  v25 = 0;
  bstrString = 0;
  v26 = 0;
  v28 = 0;
  v23 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v24[0] = 0;
  DirectUI::Element::StartDefer(v23, v24);
  ProcessHeap = GetProcessHeap();
  v4 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x400u);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 14) + 56LL))(
           *((_QWORD *)this + 14),
           &bstrString);
    if ( v5 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1785, v5);
      goto LABEL_37;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 14) + 64LL))(*((_QWORD *)this + 14), &v26);
    if ( v6 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1788, v6);
      goto LABEL_37;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 14) + 32LL))(*((_QWORD *)this + 14), &v28);
    if ( v7 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1791, v7);
      goto LABEL_37;
    }
    v8 = 0;
    v9 = 0;
    if ( v28 )
    {
      v10 = *(const wchar_t ***)(v28 + 24);
      if ( v10 )
      {
        v8 = *v10;
        v9 = v10[1];
      }
    }
    WizardPage::StartRetireBannerTipTest(this, 14);
    WizardPage::OnSetActive(this);
    v11 = DwzStrTruncate(v4, 0x80u, bstrString, &v25);
    if ( v11 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1806, v11);
      goto LABEL_37;
    }
    v12 = WizardPage::SetHeader(this, v4);
    if ( v12 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1809, v12);
      goto LABEL_37;
    }
    v13 = DwzStrTruncate(v4, 0x200u, v26, &v25);
    if ( v13 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1812, v13);
      goto LABEL_37;
    }
    v14 = WizardPage::EnableNamedTooltip(this, L"txtConsDescription", v25);
    if ( v14 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1815, v14);
      goto LABEL_37;
    }
    v15 = WizardPage::SetNamedValues(this, L"txtConsDescription", v4, v26, v21, v26);
    if ( v15 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1823, v15);
      goto LABEL_37;
    }
    if ( !v8
      || !v9
      || _wcsnicmp(v8, L"http://", 7u) && _wcsnicmp(v8, L"https://", 8u) && _wcsnicmp(v8, L"mshelp://", 9u) )
    {
      v19 = WizardPage::HideNamedElement(this, L"linkContainer");
      if ( v19 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1833, v19);
        goto LABEL_37;
      }
    }
    else
    {
      v16 = DwzStrTruncate(v4, 0x48u, v9, &v25);
      if ( v16 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1843, v16);
        goto LABEL_37;
      }
      v17 = WizardPage::SetNamedValues(this, L"linkInteraction", v4, 0, v22, v9);
      if ( v17 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1851, v17);
        goto LABEL_37;
      }
      v18 = WizardPage::EnableNamedTooltip(this, L"linkInteraction", v25);
      if ( v18 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1854, v18);
        goto LABEL_37;
      }
    }
    v2 = 0;
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentPage::OnSetActive", 1782, -2147024882);
  }
LABEL_37:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v26 )
  {
    SysFreeString(v26);
    v26 = 0;
  }
  if ( v24[0] )
    DirectUI::Element::EndDefer(v23, v24[0]);
  return v2;
}

```

## disassembly

```asm
0x1400172e0  push    rbp
0x1400172e2  push    rbx
0x1400172e3  push    rsi
0x1400172e4  push    rdi
0x1400172e5  push    r14
0x1400172e7  push    r15
0x1400172e9  mov     rbp, rsp
0x1400172ec  sub     rsp, 48h
0x1400172f0  mov     rbx, rcx
0x1400172f3  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400172f7  mov     [rbp+arg_0], 0
0x1400172fe  mov     [rbp+bstrString], 0
0x140017306  mov     [rbp+arg_8], 0
0x14001730e  mov     [rbp+arg_18], 0
0x140017316  mov     rcx, [rcx+40h]
0x14001731a  mov     [rbp+var_18], rcx
0x14001731e  mov     [rbp+var_10], 0
0x140017325  lea     rdx, [rbp+var_10]
0x140017329  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x140017330  nop     dword ptr [rax+rax+00h]
0x140017335  nop
0x140017336  call    cs:__imp_GetProcessHeap
0x14001733d  nop     dword ptr [rax+rax+00h]
0x140017342  mov     rcx, rax; hHeap
0x140017345  xor     edx, edx; dwFlags
0x140017347  mov     r8d, 400h; dwBytes
0x14001734d  call    cs:__imp_HeapAlloc
0x140017354  nop     dword ptr [rax+rax+00h]
0x140017359  mov     r14, rax
0x14001735c  test    rax, rax
0x14001735f  jnz     short loc_14001738C
0x140017361  mov     dword ptr [rsp+48h+var_28], 8007000Eh
0x140017369  mov     r9d, 6F6h
0x14001736f  lea     r8, aConsentpageOns; "ConsentPage::OnSetActive"
0x140017376  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001737d  mov     ecx, 1; Level
0x140017382  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140017387  jmp     loc_140017600
0x14001738c  mov     rcx, [rbx+70h]
0x140017390  mov     rax, [rcx]
0x140017393  lea     rdx, [rbp+bstrString]
0x140017397  mov     rax, [rax+38h]
0x14001739b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400173a0  test    eax, eax
0x1400173a2  jns     short loc_1400173B0
0x1400173a4  mov     dword ptr [rsp+48h+var_28], eax
0x1400173a8  mov     r9d, 6F9h
0x1400173ae  jmp     short loc_14001736F
0x1400173b0  mov     rcx, [rbx+70h]
0x1400173b4  mov     rax, [rcx]
0x1400173b7  lea     rdx, [rbp+arg_8]
0x1400173bb  mov     rax, [rax+40h]
0x1400173bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400173c4  test    eax, eax
0x1400173c6  jns     short loc_1400173D4
0x1400173c8  mov     dword ptr [rsp+48h+var_28], eax
0x1400173cc  mov     r9d, 6FCh
0x1400173d2  jmp     short loc_14001736F
0x1400173d4  mov     rcx, [rbx+70h]
0x1400173d8  mov     rax, [rcx]
0x1400173db  lea     rdx, [rbp+arg_18]
0x1400173df  mov     rax, [rax+20h]
0x1400173e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400173e8  test    eax, eax
0x1400173ea  jns     short loc_1400173FB
0x1400173ec  mov     dword ptr [rsp+48h+var_28], eax
0x1400173f0  mov     r9d, 6FFh
0x1400173f6  jmp     loc_14001736F
0x1400173fb  xor     edi, edi
0x1400173fd  xor     esi, esi
0x1400173ff  mov     rax, [rbp+arg_18]
0x140017403  test    rax, rax
0x140017406  jz      short loc_140017418
0x140017408  mov     rax, [rax+18h]
0x14001740c  test    rax, rax
0x14001740f  jz      short loc_140017418
0x140017411  mov     rdi, [rax]
0x140017414  mov     rsi, [rax+8]
0x140017418  mov     edx, 0Eh
0x14001741d  mov     rcx, rbx
0x140017420  call    ?StartRetireBannerTipTest@WizardPage@@IEAAXW4PageNames@@@Z; WizardPage::StartRetireBannerTipTest(PageNames)
0x140017425  mov     rcx, rbx; this
0x140017428  call    ?OnSetActive@WizardPage@@MEAA_JXZ; WizardPage::OnSetActive(void)
0x14001742d  lea     r9, [rbp+arg_0]; int *
0x140017431  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x140017435  mov     edx, 80h; unsigned __int64
0x14001743a  mov     rcx, r14; unsigned __int16 *
0x14001743d  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x140017442  test    eax, eax
0x140017444  jns     short loc_140017455
0x140017446  mov     dword ptr [rsp+48h+var_28], eax
0x14001744a  mov     r9d, 70Eh
0x140017450  jmp     loc_14001736F
0x140017455  mov     rdx, r14; unsigned __int16 *
0x140017458  mov     rcx, rbx; this
0x14001745b  call    ?SetHeader@WizardPage@@IEAAJPEBG@Z; WizardPage::SetHeader(ushort const *)
0x140017460  test    eax, eax
0x140017462  jns     short loc_140017473
0x140017464  mov     dword ptr [rsp+48h+var_28], eax
0x140017468  mov     r9d, 711h
0x14001746e  jmp     loc_14001736F
0x140017473  lea     r9, [rbp+arg_0]; int *
0x140017477  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x14001747b  mov     edx, 200h; unsigned __int64
0x140017480  mov     rcx, r14; unsigned __int16 *
0x140017483  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x140017488  test    eax, eax
0x14001748a  jns     short loc_14001749B
0x14001748c  mov     dword ptr [rsp+48h+var_28], eax
0x140017490  mov     r9d, 714h
0x140017496  jmp     loc_14001736F
0x14001749b  mov     r8d, [rbp+arg_0]; int
0x14001749f  lea     rdx, aTxtconsdescrip; "txtConsDescription"
0x1400174a6  mov     rcx, rbx; this
0x1400174a9  call    ?EnableNamedTooltip@WizardPage@@IEAAJPEBGH@Z; WizardPage::EnableNamedTooltip(ushort const *,int)
0x1400174ae  test    eax, eax
0x1400174b0  jns     short loc_1400174C1
0x1400174b2  mov     dword ptr [rsp+48h+var_28], eax
0x1400174b6  mov     r9d, 717h
0x1400174bc  jmp     loc_14001736F
0x1400174c1  mov     r9, [rbp+arg_8]; unsigned __int16 *
0x1400174c5  mov     [rsp+48h+var_20], r9; unsigned __int16 *
0x1400174ca  mov     r8, r14; unsigned __int16 *
0x1400174cd  lea     rdx, aTxtconsdescrip; "txtConsDescription"
0x1400174d4  mov     rcx, rbx; this
0x1400174d7  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1400174dc  test    eax, eax
0x1400174de  jns     short loc_1400174EF
0x1400174e0  mov     dword ptr [rsp+48h+var_28], eax
0x1400174e4  mov     r9d, 71Fh
0x1400174ea  jmp     loc_14001736F
0x1400174ef  test    rdi, rdi
0x1400174f2  jz      loc_1400175DB
0x1400174f8  test    rsi, rsi
0x1400174fb  jz      loc_1400175DB
0x140017501  mov     r8d, 7; MaxCount
0x140017507  lea     rdx, aHttp; "http://"
0x14001750e  mov     rcx, rdi; String1
0x140017511  call    cs:__imp__wcsnicmp
0x140017518  nop     dword ptr [rax+rax+00h]
0x14001751d  test    eax, eax
0x14001751f  jz      short loc_140017561
0x140017521  mov     r8d, 8; MaxCount
0x140017527  lea     rdx, aHttps; "https://"
0x14001752e  mov     rcx, rdi; String1
0x140017531  call    cs:__imp__wcsnicmp
0x140017538  nop     dword ptr [rax+rax+00h]
0x14001753d  test    eax, eax
0x14001753f  jz      short loc_140017561
0x140017541  mov     r8d, 9; MaxCount
0x140017547  lea     rdx, aMshelp; "mshelp://"
0x14001754e  mov     rcx, rdi; String1
0x140017551  call    cs:__imp__wcsnicmp
0x140017558  nop     dword ptr [rax+rax+00h]
0x14001755d  test    eax, eax
0x14001755f  jnz     short loc_1400175DB
0x140017561  lea     r9, [rbp+arg_0]; int *
0x140017565  mov     r8, rsi; unsigned __int16 *
0x140017568  mov     edx, 48h ; 'H'; unsigned __int64
0x14001756d  mov     rcx, r14; unsigned __int16 *
0x140017570  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x140017575  test    eax, eax
0x140017577  jns     short loc_140017588
0x140017579  mov     dword ptr [rsp+48h+var_28], eax
0x14001757d  mov     r9d, 733h
0x140017583  jmp     loc_14001736F
0x140017588  mov     [rsp+48h+var_20], rsi; unsigned __int16 *
0x14001758d  xor     r9d, r9d; unsigned __int16 *
0x140017590  mov     r8, r14; unsigned __int16 *
0x140017593  lea     rdx, aLinkinteractio; "linkInteraction"
0x14001759a  mov     rcx, rbx; this
0x14001759d  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1400175a2  test    eax, eax
0x1400175a4  jns     short loc_1400175B5
0x1400175a6  mov     dword ptr [rsp+48h+var_28], eax
0x1400175aa  mov     r9d, 73Bh
0x1400175b0  jmp     loc_14001736F
0x1400175b5  mov     r8d, [rbp+arg_0]; int
0x1400175b9  lea     rdx, aLinkinteractio; "linkInteraction"
0x1400175c0  mov     rcx, rbx; this
0x1400175c3  call    ?EnableNamedTooltip@WizardPage@@IEAAJPEBGH@Z; WizardPage::EnableNamedTooltip(ushort const *,int)
0x1400175c8  test    eax, eax
0x1400175ca  jns     short loc_1400175FD
0x1400175cc  mov     dword ptr [rsp+48h+var_28], eax
0x1400175d0  mov     r9d, 73Eh
0x1400175d6  jmp     loc_14001736F
0x1400175db  lea     rdx, aLinkcontainer; "linkContainer"
0x1400175e2  mov     rcx, rbx; this
0x1400175e5  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x1400175ea  test    eax, eax
0x1400175ec  jns     short loc_1400175FD
0x1400175ee  mov     dword ptr [rsp+48h+var_28], eax
0x1400175f2  mov     r9d, 729h
0x1400175f8  jmp     loc_14001736F
0x1400175fd  xor     r15d, r15d
0x140017600  mov     rcx, [rbp+bstrString]; bstrString
0x140017604  test    rcx, rcx
0x140017607  jz      short loc_14001761D
0x140017609  call    cs:__imp_SysFreeString
0x140017610  nop     dword ptr [rax+rax+00h]
0x140017615  mov     [rbp+bstrString], 0
0x14001761d  mov     rcx, [rbp+arg_8]; bstrString
0x140017621  test    rcx, rcx
0x140017624  jz      short loc_14001763A
0x140017626  call    cs:__imp_SysFreeString
0x14001762d  nop     dword ptr [rax+rax+00h]
0x140017632  mov     [rbp+arg_8], 0
0x14001763a  mov     edx, [rbp+var_10]
0x14001763d  test    edx, edx
0x14001763f  jz      short loc_140017652
0x140017641  mov     rcx, [rbp+var_18]
0x140017645  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14001764c  nop     dword ptr [rax+rax+00h]
0x140017651  nop
0x140017652  mov     rax, r15
0x140017655  add     rsp, 48h
0x140017659  pop     r15
0x14001765b  pop     r14
0x14001765d  pop     rdi
0x14001765e  pop     rsi
0x14001765f  pop     rbx
0x140017660  pop     rbp
0x140017661  retn
```

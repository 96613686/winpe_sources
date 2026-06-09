# FinalLinksPage::AddRootCauses(DirectUI::DUIXmlParser *)

- ea: `0x140019710`
- end: `0x140019e92`
- name: `?AddRootCauses@FinalLinksPage@@IEAAJPEAVDUIXmlParser@DirectUI@@@Z`
- size: `1922`
- prototype: `__int64 __fastcall(FinalLinksPage *__hidden this, struct DirectUI::DUIXmlParser *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config`

## callers

- `0x14001af10`

## callees

- `0x140001d54`
- `0x140001d94`
- `0x1400070b0`
- `0x14000e378`
- `0x14000e6bc`
- `0x14000e978`
- `0x140010308`
- `0x1400108b0`
- `0x140019710`
- `0x140020420`
- `0x140020d58`
- `0x140041c54`
- `0x14004d3f4`
- `0x14004d444`
- `0x14004d750`
- `0x14004e3d4`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140019770`
- `KERNEL32!HeapAlloc` at `0x140019770`
- `KERNEL32!HeapFree` at `0x140019d15`
- `KERNEL32!HeapFree` at `0x140019d15`
- `KERNEL32!GetProcessHeap` at `0x140019759`
- `KERNEL32!GetProcessHeap` at `0x140019d01`
- `KERNEL32!GetProcessHeap` at `0x140019759`
- `KERNEL32!GetProcessHeap` at `0x140019d01`
- `OLEAUT32!__imp_SysFreeString` at `0x1400198fe`
- `OLEAUT32!__imp_SysFreeString` at `0x140019917`
- `OLEAUT32!__imp_SysFreeString` at `0x140019ca1`
- `OLEAUT32!__imp_SysFreeString` at `0x140019cbe`
- `OLEAUT32!__imp_SysFreeString` at `0x1400198fe`
- `OLEAUT32!__imp_SysFreeString` at `0x140019917`
- `OLEAUT32!__imp_SysFreeString` at `0x140019ca1`
- `OLEAUT32!__imp_SysFreeString` at `0x140019cbe`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x140019a87`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x140019c2b`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x140019a87`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x140019c2b`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1400199ba`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x140019abc`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1400199ba`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x140019abc`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x1400197df`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x140019829`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x1400197df`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x140019829`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x140019a69`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x140019b85`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x140019a69`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x140019b85`
- `DUI70!StrToID` at `0x140019ad9`
- `DUI70!StrToID` at `0x140019ad9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140019aec`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140019aec`

## string_xrefs

- `0x140019e38`: `nofeedbackQuestionLinks`
- `0x140019799`: `FinalLinksPage::AddRootCauses`
- `0x140019c83`: `FinalLinksPage::AddRootCauses`
- `0x140019df7`: `FinalLinksPage::AddRootCauses`

## pseudocode

```c
__int64 __fastcall FinalLinksPage::AddRootCauses(FinalLinksPage *this, struct DirectUI::DUIXmlParser *a2)
{
  RootCauseIterator *v3; // r15
  struct IRootCause *v4; // r12
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // r13
  int v7; // r9d
  unsigned int v8; // ebx
  int NamedElement; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  RootCauseIterator *v13; // rax
  int v14; // ebx
  int v15; // r13d
  int NextRootCause; // eax
  __int64 v17; // rax
  const unsigned __int16 *v18; // r13
  int LocalString; // eax
  BOOL v20; // edx
  int v21; // eax
  unsigned __int16 v22; // ax
  struct DirectUI::Element *Descendent; // r13
  WizardPage *v24; // rcx
  WizardPage *v25; // rcx
  WizardPage *v26; // rcx
  WizardPage *v27; // rcx
  int v28; // r9d
  HANDLE v29; // rax
  WCHAR *lpBuffer; // [rsp+30h] [rbp-50h]
  BSTR bstrString; // [rsp+38h] [rbp-48h] BYREF
  BSTR v33; // [rsp+40h] [rbp-40h] BYREF
  int v34; // [rsp+48h] [rbp-38h] BYREF
  int v35; // [rsp+4Ch] [rbp-34h]
  struct DirectUI::Element *v36; // [rsp+50h] [rbp-30h] BYREF
  struct IRootCause *v37; // [rsp+58h] [rbp-28h] BYREF
  struct DirectUI::Element *v38; // [rsp+60h] [rbp-20h] BYREF
  struct DirectUI::Element *v39; // [rsp+68h] [rbp-18h] BYREF
  struct DirectUI::Element *v40; // [rsp+70h] [rbp-10h] BYREF
  int v42; // [rsp+D0h] [rbp+50h]
  int v43; // [rsp+D8h] [rbp+58h] BYREF

  v36 = 0;
  v3 = 0;
  v38 = 0;
  v4 = 0;
  v39 = 0;
  v40 = 0;
  v34 = 0;
  bstrString = 0;
  v33 = 0;
  v37 = 0;
  ProcessHeap = GetProcessHeap();
  lpBuffer = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x1800u);
  v6 = lpBuffer;
  if ( !lpBuffer )
  {
    v7 = 368;
LABEL_3:
    v8 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::AddRootCauses", v7, -2147024882);
    goto LABEL_59;
  }
  NamedElement = WizardPage::GetNamedElement(this, L"entrypoint", &v38);
  v8 = NamedElement;
  if ( NamedElement < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::AddRootCauses", 374, NamedElement);
    goto LABEL_59;
  }
  v10 = DirectUI::Element::RemoveAll(v38);
  v8 = v10;
  if ( v10 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::AddRootCauses", 377, v10);
    goto LABEL_59;
  }
  v11 = WizardPage::GetNamedElement(this, L"headerentrypoint", &v40);
  v8 = v11;
  if ( v11 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::AddRootCauses", 383, v11);
    goto LABEL_59;
  }
  v12 = DirectUI::Element::RemoveAll(v40);
  v8 = v12;
  if ( v12 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::AddRootCauses", 386, v12);
    goto LABEL_59;
  }
  v13 = (RootCauseIterator *)operator new(0x18u);
  v3 = v13;
  if ( !v13 )
  {
    v3 = 0;
    v7 = 389;
    goto LABEL_3;
  }
  *((_QWORD *)v13 + 1) = 0;
  *((_DWORD *)v13 + 4) = 5;
  v14 = 0;
  v42 = 0;
  if ( (*(unsigned int (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 176LL))(this) == 8
    || (v15 = 1, (*(unsigned int (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 176LL))(this) == 9) )
  {
    v15 = 0;
  }
  v35 = v15;
  while ( (unsigned int)RootCauseIterator::HasNext(v3) && v15 )
  {
    if ( v4 )
    {
      (*(void (__fastcall **)(struct IRootCause *))(*(_QWORD *)v4 + 16LL))(v4);
      v37 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v33 )
    {
      SysFreeString(v33);
      v33 = 0;
    }
    NextRootCause = RootCauseIterator::GetNextRootCause(v3, &v37);
    v8 = NextRootCause;
    if ( NextRootCause < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::AddRootCauses", 402, NextRootCause);
      v4 = v37;
      goto LABEL_58;
    }
    v4 = v37;
    v14 = v42;
    if ( RootCause_GetNumberResolutions(v37)
      && (*(unsigned int (__fastcall **)(FinalLinksPage *, struct IRootCause *))(*(_QWORD *)this + 248LL))(this, v4) )
    {
      v17 = *(_QWORD *)this;
      v36 = 0;
      v18 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(FinalLinksPage *))(v17 + 232))(this);
      if ( v42 )
        goto LABEL_40;
      LocalString = DirectUI::DUIXmlParser::CreateElement(a2, L"rcheader", 0, 0, 0, &v39);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 420;
        goto LABEL_57;
      }
      v43 = 0;
      if ( !v4 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RootCause_IsChecked", 455, -2147024809);
LABEL_33:
        v20 = 1;
        goto LABEL_37;
      }
      v21 = (*(__int64 (__fastcall **)(struct IRootCause *, int *))(*(_QWORD *)v4 + 72LL))(v4, &v43);
      if ( v21 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RootCause_IsChecked", 458, v21);
        goto LABEL_33;
      }
      v20 = v43 != 4;
LABEL_37:
      LocalString = DwzLoadLocalString(v20 + (*((_DWORD *)Config + 20) != 0 ? 10396 : 396), lpBuffer, 0x400u);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 428;
        goto LABEL_57;
      }
      LocalString = DirectUI::Element::SetContentString(v39, lpBuffer);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 431;
        goto LABEL_57;
      }
      LocalString = DirectUI::Element::Add(v40, v39);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 434;
        goto LABEL_57;
      }
LABEL_40:
      LocalString = DirectUI::DUIXmlParser::CreateElement(a2, v18, 0, 0, 0, &v36);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 443;
        goto LABEL_57;
      }
      v22 = StrToID(L"txtName");
      Descendent = DirectUI::Element::FindDescendent(v36, v22);
      if ( !Descendent )
      {
        v8 = -2147418113;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::AddRootCauses", 450, -2147418113);
        goto LABEL_58;
      }
      LocalString = (*(__int64 (__fastcall **)(struct IRootCause *, BSTR *))(*(_QWORD *)v4 + 56LL))(v4, &bstrString);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 453;
        goto LABEL_57;
      }
      LocalString = (*(__int64 (__fastcall **)(struct IRootCause *, BSTR *))(*(_QWORD *)v4 + 64LL))(v4, &v33);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 455;
        goto LABEL_57;
      }
      LocalString = WizardPage::SetAccValues(v24, Descendent, bstrString, 0, bstrString);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 458;
        goto LABEL_57;
      }
      LocalString = DwzStrTruncate(lpBuffer, 0x80u, bstrString, &v34);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 468;
        goto LABEL_57;
      }
      LocalString = DirectUI::Element::SetContentString(Descendent, lpBuffer);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 471;
        goto LABEL_57;
      }
      if ( v34 )
      {
        LocalString = StringCchPrintfW(lpBuffer, 0xC00u, L"%s\n\n%s", bstrString, v33);
        v8 = LocalString;
        if ( LocalString < 0 )
        {
          v28 = 483;
          goto LABEL_57;
        }
        LocalString = WizardPage::SetAccValues(v26, Descendent, bstrString, 0, lpBuffer);
        v8 = LocalString;
        if ( LocalString < 0 )
        {
          v28 = 486;
LABEL_57:
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::AddRootCauses", v28, LocalString);
          goto LABEL_58;
        }
      }
      else
      {
        LocalString = WizardPage::SetAccValues(v25, Descendent, 0, 0, v33);
        v8 = LocalString;
        if ( LocalString < 0 )
        {
          v28 = 489;
          goto LABEL_57;
        }
      }
      LocalString = WizardPage::EnableTooltip(v27, Descendent, 1);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 493;
        goto LABEL_57;
      }
      LocalString = DirectUI::Element::Add(v38, v36);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 496;
        goto LABEL_57;
      }
      LocalString = (*(__int64 (__fastcall **)(FinalLinksPage *, struct DirectUI::Element *, struct IRootCause *, struct DirectUI::DUIXmlParser *))(*(_QWORD *)this + 240LL))(
                      this,
                      v36,
                      v4,
                      a2);
      v8 = LocalString;
      if ( LocalString < 0 )
      {
        v28 = 499;
        goto LABEL_57;
      }
      v15 = v35;
      v14 = ++v42;
    }
  }
  if ( v14 )
  {
    LocalString = (*(__int64 (__fastcall **)(FinalLinksPage *, struct DirectUI::Element *))(*(_QWORD *)this + 256LL))(
                    this,
                    v38);
    v8 = LocalString;
    if ( LocalString < 0 )
    {
      v28 = 515;
      goto LABEL_57;
    }
  }
  else
  {
    LocalString = WizardPage::HideNamedElement(this, L"rcbox");
    v8 = LocalString;
    if ( LocalString < 0 )
    {
      v28 = 509;
      goto LABEL_57;
    }
    LocalString = WizardPage::ShowNamedElement(this, L"nofeedbackQuestionLinks", 1);
    v8 = LocalString;
    if ( LocalString < 0 )
    {
      v28 = 512;
      goto LABEL_57;
    }
  }
LABEL_58:
  v6 = lpBuffer;
LABEL_59:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v33 )
  {
    SysFreeString(v33);
    v33 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(struct IRootCause *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v3 )
  {
    RootCauseIterator::~RootCauseIterator(v3);
    operator delete(v3);
  }
  if ( v6 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v6);
  }
  return v8;
}

```

## disassembly

```asm
0x140019710  mov     [rsp-38h+arg_0], rbx
0x140019715  mov     [rsp-38h+arg_8], rdx
0x14001971a  push    rbp
0x14001971b  push    rsi
0x14001971c  push    rdi
0x14001971d  push    r12
0x14001971f  push    r13
0x140019721  push    r14
0x140019723  push    r15
0x140019725  mov     rbp, rsp
0x140019728  sub     rsp, 80h
0x14001972f  xor     esi, esi
0x140019731  mov     r14, rcx
0x140019734  mov     [rbp+var_30], rsi
0x140019738  mov     r15d, esi
0x14001973b  mov     [rbp+var_20], rsi
0x14001973f  mov     r12d, esi
0x140019742  mov     [rbp+var_18], rsi
0x140019746  mov     [rbp+var_10], rsi
0x14001974a  mov     [rbp+var_38], esi
0x14001974d  mov     [rbp+bstrString], rsi
0x140019751  mov     [rbp+var_40], rsi
0x140019755  mov     [rbp+var_28], rsi
0x140019759  call    cs:__imp_GetProcessHeap
0x140019760  nop     dword ptr [rax+rax+00h]
0x140019765  xor     edx, edx; dwFlags
0x140019767  mov     r8d, 1800h; dwBytes
0x14001976d  mov     rcx, rax; hHeap
0x140019770  call    cs:__imp_HeapAlloc
0x140019777  nop     dword ptr [rax+rax+00h]
0x14001977c  mov     [rbp+lpBuffer], rax
0x140019780  mov     r13, rax
0x140019783  test    rax, rax
0x140019786  jnz     short loc_1400197B6
0x140019788  mov     r9d, 170h
0x14001978e  mov     ecx, 8007000Eh
0x140019793  mov     dword ptr [rsp+80h+var_60], ecx
0x140019797  mov     ebx, ecx
0x140019799  lea     r8, aFinallinkspage_4; "FinalLinksPage::AddRootCauses"
0x1400197a0  mov     ecx, 1; Level
0x1400197a5  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400197ac  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400197b1  jmp     loc_140019C98
0x1400197b6  lea     r8, [rbp+var_20]; struct DirectUI::Element **
0x1400197ba  mov     rcx, r14; this
0x1400197bd  lea     rdx, aEntrypoint; "entrypoint"
0x1400197c4  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x1400197c9  mov     ebx, eax
0x1400197cb  test    eax, eax
0x1400197cd  jns     short loc_1400197DB
0x1400197cf  mov     dword ptr [rsp+80h+var_60], eax
0x1400197d3  mov     r9d, 176h
0x1400197d9  jmp     short loc_140019799
0x1400197db  mov     rcx, [rbp+var_20]
0x1400197df  call    cs:__imp_?RemoveAll@Element@DirectUI@@QEAAJXZ; DirectUI::Element::RemoveAll(void)
0x1400197e6  nop     dword ptr [rax+rax+00h]
0x1400197eb  mov     ebx, eax
0x1400197ed  test    eax, eax
0x1400197ef  jns     short loc_1400197FD
0x1400197f1  mov     dword ptr [rsp+80h+var_60], eax
0x1400197f5  mov     r9d, 179h
0x1400197fb  jmp     short loc_140019799
0x1400197fd  lea     r8, [rbp+var_10]; struct DirectUI::Element **
0x140019801  mov     rcx, r14; this
0x140019804  lea     rdx, aHeaderentrypoi; "headerentrypoint"
0x14001980b  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140019810  mov     ebx, eax
0x140019812  test    eax, eax
0x140019814  jns     short loc_140019825
0x140019816  mov     dword ptr [rsp+80h+var_60], eax
0x14001981a  mov     r9d, 17Fh
0x140019820  jmp     loc_140019799
0x140019825  mov     rcx, [rbp+var_10]
0x140019829  call    cs:__imp_?RemoveAll@Element@DirectUI@@QEAAJXZ; DirectUI::Element::RemoveAll(void)
0x140019830  nop     dword ptr [rax+rax+00h]
0x140019835  mov     ebx, eax
0x140019837  test    eax, eax
0x140019839  jns     short loc_14001984A
0x14001983b  mov     dword ptr [rsp+80h+var_60], eax
0x14001983f  mov     r9d, 182h
0x140019845  jmp     loc_140019799
0x14001984a  mov     ecx, 18h; Size
0x14001984f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140019854  mov     [rbp+arg_10], rax
0x140019858  mov     r15, rax
0x14001985b  test    rax, rax
0x14001985e  jz      loc_140019E84
0x140019864  mov     [rax+8], rsi
0x140019868  mov     dword ptr [rax+10h], 5
0x14001986f  test    rax, rax
0x140019872  jz      loc_140019E87
0x140019878  mov     rax, [r14]
0x14001987b  mov     ebx, esi
0x14001987d  mov     rcx, r14
0x140019880  mov     dword ptr [rbp+arg_10], ebx
0x140019883  mov     rax, [rax+0B0h]
0x14001988a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001988f  mov     edi, 1
0x140019894  cmp     eax, 8
0x140019897  jz      short loc_1400198B3
0x140019899  mov     rax, [r14]
0x14001989c  mov     rcx, r14
0x14001989f  mov     rax, [rax+0B0h]
0x1400198a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400198ab  mov     r13d, edi
0x1400198ae  cmp     eax, 9
0x1400198b1  jnz     short loc_1400198B6
0x1400198b3  mov     r13d, esi
0x1400198b6  mov     [rbp+var_34], r13d
0x1400198ba  lea     rsi, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400198c1  mov     rcx, r15; this
0x1400198c4  call    ?HasNext@RootCauseIterator@@QEAAHXZ; RootCauseIterator::HasNext(void)
0x1400198c9  test    eax, eax
0x1400198cb  jz      loc_140019E11
0x1400198d1  test    r13d, r13d
0x1400198d4  jz      loc_140019E11
0x1400198da  xor     ebx, ebx
0x1400198dc  test    r12, r12
0x1400198df  jz      short loc_1400198F5
0x1400198e1  mov     rax, [r12]
0x1400198e5  mov     rcx, r12
0x1400198e8  mov     rax, [rax+10h]
0x1400198ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400198f1  mov     [rbp+var_28], rbx
0x1400198f5  mov     rcx, [rbp+bstrString]; bstrString
0x1400198f9  test    rcx, rcx
0x1400198fc  jz      short loc_14001990E
0x1400198fe  call    cs:__imp_SysFreeString
0x140019905  nop     dword ptr [rax+rax+00h]
0x14001990a  mov     [rbp+bstrString], rbx
0x14001990e  mov     rcx, [rbp+var_40]; bstrString
0x140019912  test    rcx, rcx
0x140019915  jz      short loc_140019927
0x140019917  call    cs:__imp_SysFreeString
0x14001991e  nop     dword ptr [rax+rax+00h]
0x140019923  mov     [rbp+var_40], rbx
0x140019927  lea     rdx, [rbp+var_28]; struct IRootCause **
0x14001992b  mov     rcx, r15; this
0x14001992e  call    ?GetNextRootCause@RootCauseIterator@@QEAAJPEAPEAVIRootCause@@@Z; RootCauseIterator::GetNextRootCause(IRootCause * *)
0x140019933  mov     ebx, eax
0x140019935  test    eax, eax
0x140019937  js      loc_140019DED
0x14001993d  mov     r12, [rbp+var_28]
0x140019941  mov     rcx, r12; struct IRootCause *
0x140019944  call    ?RootCause_GetNumberResolutions@@YAIPEAVIRootCause@@@Z; RootCause_GetNumberResolutions(IRootCause *)
0x140019949  mov     ebx, dword ptr [rbp+arg_10]
0x14001994c  test    eax, eax
0x14001994e  jz      loc_1400198C1
0x140019954  mov     rax, [r14]
0x140019957  mov     rdx, r12
0x14001995a  mov     rcx, r14
0x14001995d  mov     rax, [rax+0F8h]
0x140019964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019969  test    eax, eax
0x14001996b  jz      loc_1400198C1
0x140019971  mov     rax, [r14]
0x140019974  mov     rcx, r14
0x140019977  mov     [rbp+var_30], 0
0x14001997f  mov     rax, [rax+0E8h]
0x140019986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001998b  mov     r13, rax
0x14001998e  cmp     ebx, 0
0x140019991  jnz     loc_140019A9D
0x140019997  mov     rcx, [rbp+arg_8]
0x14001999b  lea     rax, [rbp+var_18]
0x14001999f  mov     [rsp+80h+var_58], rax
0x1400199a4  lea     rdx, aRcheader; "rcheader"
0x1400199ab  xor     r9d, r9d
0x1400199ae  mov     [rsp+80h+var_60], 0
0x1400199b7  xor     r8d, r8d
0x1400199ba  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1400199c1  nop     dword ptr [rax+rax+00h]
0x1400199c6  mov     ebx, eax
0x1400199c8  test    eax, eax
0x1400199ca  js      loc_140019D55
0x1400199d0  mov     [rbp+arg_18], 0
0x1400199d7  test    r12, r12
0x1400199da  jnz     short loc_1400199FF
0x1400199dc  mov     dword ptr [rsp+80h+var_60], 80070057h
0x1400199e4  mov     r9d, 1C7h
0x1400199ea  lea     r8, aRootcauseIsche; "RootCause_IsChecked"
0x1400199f1  mov     rdx, rsi; char *
0x1400199f4  mov     ecx, edi; Level
0x1400199f6  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400199fb  mov     edx, edi
0x1400199fd  jmp     short loc_140019A2C
0x1400199ff  mov     rax, [r12]
0x140019a03  lea     rdx, [rbp+arg_18]
0x140019a07  mov     rcx, r12
0x140019a0a  mov     rax, [rax+48h]
0x140019a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019a13  test    eax, eax
0x140019a15  jns     short loc_140019A23
0x140019a17  mov     dword ptr [rsp+80h+var_60], eax
0x140019a1b  mov     r9d, 1CAh
0x140019a21  jmp     short loc_1400199EA
0x140019a23  xor     edx, edx
0x140019a25  cmp     [rbp+arg_18], 4
0x140019a29  setnz   dl
0x140019a2c  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140019a33  mov     r8d, 400h; cchBufferMax
0x140019a39  mov     ecx, [rax+50h]
0x140019a3c  neg     ecx
0x140019a3e  sbb     ecx, ecx
0x140019a40  and     ecx, 2710h
0x140019a46  add     ecx, 18Ch
0x140019a4c  add     ecx, edx; uID
0x140019a4e  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x140019a52  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x140019a57  mov     ebx, eax
0x140019a59  test    eax, eax
0x140019a5b  js      loc_140019D4A
0x140019a61  mov     rdx, [rbp+lpBuffer]
0x140019a65  mov     rcx, [rbp+var_18]
0x140019a69  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x140019a70  nop     dword ptr [rax+rax+00h]
0x140019a75  mov     ebx, eax
0x140019a77  test    eax, eax
0x140019a79  js      loc_140019D3F
0x140019a7f  mov     rdx, [rbp+var_18]
0x140019a83  mov     rcx, [rbp+var_10]
0x140019a87  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x140019a8e  nop     dword ptr [rax+rax+00h]
0x140019a93  mov     ebx, eax
0x140019a95  test    eax, eax
0x140019a97  js      loc_140019C79
0x140019a9d  mov     rcx, [rbp+arg_8]
0x140019aa1  lea     rax, [rbp+var_30]
0x140019aa5  mov     [rsp+80h+var_58], rax
0x140019aaa  xor     r9d, r9d
0x140019aad  xor     r8d, r8d
0x140019ab0  mov     [rsp+80h+var_60], 0
0x140019ab9  mov     rdx, r13
0x140019abc  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x140019ac3  nop     dword ptr [rax+rax+00h]
0x140019ac8  mov     ebx, eax
0x140019aca  test    eax, eax
0x140019acc  js      loc_140019DE2
0x140019ad2  lea     rcx, aTxtname; "txtName"
0x140019ad9  call    cs:__imp_StrToID
0x140019ae0  nop     dword ptr [rax+rax+00h]
0x140019ae5  mov     rcx, [rbp+var_30]
0x140019ae9  movzx   edx, ax
0x140019aec  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x140019af3  nop     dword ptr [rax+rax+00h]
0x140019af8  mov     r13, rax
0x140019afb  test    rax, rax
0x140019afe  jz      loc_140019DCE
0x140019b04  mov     rcx, [r12]
0x140019b08  lea     rdx, [rbp+bstrString]
0x140019b0c  mov     rax, [rcx+38h]
0x140019b10  mov     rcx, r12
0x140019b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019b18  mov     ebx, eax
0x140019b1a  test    eax, eax
0x140019b1c  js      loc_140019DC3
0x140019b22  mov     rax, [r12]
0x140019b26  lea     rdx, [rbp+var_40]
0x140019b2a  mov     rcx, r12
0x140019b2d  mov     rax, [rax+40h]
0x140019b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019b36  mov     ebx, eax
0x140019b38  test    eax, eax
0x140019b3a  js      loc_140019DB8
0x140019b40  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x140019b44  xor     r9d, r9d; unsigned __int16 *
0x140019b47  mov     rdx, r13; struct DirectUI::Element *
0x140019b4a  mov     [rsp+80h+var_60], r8; unsigned __int16 *
0x140019b4f  call    ?SetAccValues@WizardPage@@IEAAJPEAVElement@DirectUI@@PEBG11@Z; WizardPage::SetAccValues(DirectUI::Element *,ushort const *,ushort const *,ushort const *)
0x140019b54  mov     ebx, eax
0x140019b56  test    eax, eax
0x140019b58  js      loc_140019DAD
0x140019b5e  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x140019b62  lea     r9, [rbp+var_38]; int *
0x140019b66  mov     rcx, [rbp+lpBuffer]; unsigned __int16 *
0x140019b6a  mov     edx, 80h; unsigned __int64
0x140019b6f  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x140019b74  mov     ebx, eax
0x140019b76  test    eax, eax
0x140019b78  js      loc_140019DA2
0x140019b7e  mov     rdx, [rbp+lpBuffer]
0x140019b82  mov     rcx, r13
0x140019b85  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x140019b8c  nop     dword ptr [rax+rax+00h]
0x140019b91  mov     ebx, eax
0x140019b93  test    eax, eax
0x140019b95  js      loc_140019D97
0x140019b9b  cmp     [rbp+var_38], 0
0x140019b9f  mov     rax, [rbp+var_40]
0x140019ba3  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x140019ba8  jz      short loc_140019BF6
0x140019baa  mov     r9, [rbp+bstrString]
0x140019bae  lea     r8, aSS_3; "%s\n\n%s"
0x140019bb5  mov     rcx, [rbp+lpBuffer]; unsigned __int16 *
0x140019bb9  mov     edx, 0C00h; unsigned __int64
0x140019bbe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140019bc3  mov     ebx, eax
0x140019bc5  test    eax, eax
0x140019bc7  js      loc_140019D60
0x140019bcd  mov     rax, [rbp+lpBuffer]
  ... truncated ...
```

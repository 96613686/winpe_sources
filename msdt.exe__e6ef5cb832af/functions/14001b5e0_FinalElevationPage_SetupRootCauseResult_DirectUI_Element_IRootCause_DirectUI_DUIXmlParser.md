# FinalElevationPage::SetupRootCauseResult(DirectUI::Element *,IRootCause *,DirectUI::DUIXmlParser *)

- ea: `0x14001b5e0`
- end: `0x14001b8e3`
- name: `?SetupRootCauseResult@FinalElevationPage@@EEAAJPEAVElement@DirectUI@@PEAVIRootCause@@PEAVDUIXmlParser@3@@Z`
- size: `771`
- prototype: `__int64 __fastcall(FinalElevationPage *this, struct DirectUI::Element *, struct IRootCause *, struct DirectUI::DUIXmlParser *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x140010308`
- `0x14001b5e0`
- `0x140020420`
- `0x140041c54`
- `0x14004e3d4`
- `0x14004effc`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001b71b`
- `KERNEL32!HeapAlloc` at `0x14001b71b`
- `KERNEL32!HeapFree` at `0x14001b8c3`
- `KERNEL32!HeapFree` at `0x14001b8c3`
- `KERNEL32!GetProcessHeap` at `0x14001b704`
- `KERNEL32!GetProcessHeap` at `0x14001b8af`
- `KERNEL32!GetProcessHeap` at `0x14001b704`
- `KERNEL32!GetProcessHeap` at `0x14001b8af`
- `OLEAUT32!__imp_SysFreeString` at `0x14001b879`
- `OLEAUT32!__imp_SysFreeString` at `0x14001b879`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001b818`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001b818`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001b78b`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001b78b`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x14001b7f7`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x14001b7f7`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x14001b656`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x14001b83f`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x14001b656`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x14001b83f`
- `DUI70!StrToID` at `0x14001b617`
- `DUI70!StrToID` at `0x14001b677`
- `DUI70!StrToID` at `0x14001b617`
- `DUI70!StrToID` at `0x14001b677`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001b629`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001b689`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001b629`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001b689`

## pseudocode

```c
__int64 __fastcall FinalElevationPage::SetupRootCauseResult(
        FinalElevationPage *this,
        struct DirectUI::Element *a2,
        struct IRootCause *a3,
        struct DirectUI::DUIXmlParser *a4)
{
  unsigned __int16 *v4; // r15
  unsigned __int16 v8; // ax
  DirectUI::Element *Descendent; // rax
  int v10; // r9d
  int LocalString; // eax
  unsigned int v12; // ebx
  unsigned __int16 v13; // ax
  DirectUI::Element *v14; // r14
  unsigned int i; // esi
  HANDLE ProcessHeap; // rax
  WCHAR *v17; // rax
  WizardPage *v18; // rcx
  HANDLE v19; // rax
  struct IResolution *v21; // [rsp+30h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-20h] BYREF
  struct DirectUI::Element *v23; // [rsp+40h] [rbp-18h] BYREF

  v4 = 0;
  v23 = 0;
  bstrString = 0;
  v21 = 0;
  v8 = StrToID(L"txtResult");
  Descendent = DirectUI::Element::FindDescendent(a2, v8);
  if ( !Descendent )
  {
    v10 = 1093;
LABEL_3:
    LocalString = -2147418113;
    v12 = -2147418113;
    goto LABEL_32;
  }
  LocalString = DirectUI::Element::SetVisible(Descendent, 0);
  v12 = LocalString;
  if ( LocalString < 0 )
  {
    v10 = 1096;
    goto LABEL_32;
  }
  v13 = StrToID(L"rcpic");
  v14 = DirectUI::Element::FindDescendent(a2, v13);
  if ( !v14 )
  {
    v10 = 1099;
    goto LABEL_3;
  }
  for ( i = 0; i < RootCause_GetNumberResolutions(a3); ++i )
  {
    if ( v21 )
    {
      (*(void (__fastcall **)(struct IResolution *))(*(_QWORD *)v21 + 16LL))(v21);
      v21 = 0;
    }
    LocalString = (*(__int64 (__fastcall **)(struct IRootCause *, _QWORD, struct IResolution **))(*(_QWORD *)a3 + 88LL))(
                    a3,
                    i,
                    &v21);
    v12 = LocalString;
    if ( LocalString < 0 )
    {
      v10 = 1105;
      goto LABEL_32;
    }
    if ( (unsigned int)Resolution_GetElevation(v21) )
    {
      ProcessHeap = GetProcessHeap();
      v17 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
      v4 = v17;
      if ( !v17 )
      {
        v12 = -2147024882;
        SdpDebugPrint(
          1u,
          "Dwz ERROR: %s:%d - hr = 0x%08X\n",
          "FinalElevationPage::SetupRootCauseResult",
          1123,
          -2147024882);
        goto LABEL_33;
      }
      LocalString = DwzLoadLocalString(0x18Fu, v17, 0x400u);
      v12 = LocalString;
      if ( LocalString < 0 )
      {
        v10 = 1126;
        goto LABEL_32;
      }
      LocalString = DirectUI::DUIXmlParser::CreateElement(a4, L"shieldicon", 0, 0, 0, &v23);
      v12 = LocalString;
      if ( LocalString < 0 )
      {
        v10 = 1132;
        goto LABEL_32;
      }
      LocalString = (*(__int64 (__fastcall **)(struct IRootCause *, BSTR *))(*(_QWORD *)a3 + 56LL))(a3, &bstrString);
      v12 = LocalString;
      if ( LocalString < 0 )
      {
        v10 = 1135;
        goto LABEL_32;
      }
      LocalString = WizardPage::SetAccValues(v18, v23, bstrString, v4, 0);
      v12 = LocalString;
      if ( LocalString < 0 )
      {
        v10 = 1141;
        goto LABEL_32;
      }
      LocalString = DirectUI::Element::RemoveAll(v14);
      v12 = LocalString;
      if ( LocalString < 0 )
      {
        v10 = 1144;
        goto LABEL_32;
      }
      LocalString = DirectUI::Element::Add(v14, v23);
      v12 = LocalString;
      if ( LocalString < 0 )
      {
        v10 = 1147;
        goto LABEL_32;
      }
      goto LABEL_33;
    }
  }
  LocalString = DirectUI::Element::SetVisible(v14, 0);
  v12 = LocalString;
  if ( LocalString >= 0 )
    goto LABEL_33;
  v10 = 1118;
LABEL_32:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalElevationPage::SetupRootCauseResult", v10, LocalString);
LABEL_33:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(struct IResolution *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v4 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v4);
  }
  return v12;
}

```

## disassembly

```asm
0x14001b5e0  push    rbp
0x14001b5e2  push    rbx
0x14001b5e3  push    rsi
0x14001b5e4  push    rdi
0x14001b5e5  push    r12
0x14001b5e7  push    r13
0x14001b5e9  push    r14
0x14001b5eb  push    r15
0x14001b5ed  mov     rbp, rsp
0x14001b5f0  sub     rsp, 58h
0x14001b5f4  xor     r15d, r15d
0x14001b5f7  mov     [rbp+var_18], 0
0x14001b5ff  lea     rcx, aTxtresult; "txtResult"
0x14001b606  mov     [rbp+bstrString], r15
0x14001b60a  mov     [rbp+var_28], r15
0x14001b60e  mov     r13, r9
0x14001b611  mov     r12, r8
0x14001b614  mov     rdi, rdx
0x14001b617  call    cs:__imp_StrToID
0x14001b61e  nop     dword ptr [rax+rax+00h]
0x14001b623  movzx   edx, ax
0x14001b626  mov     rcx, rdi
0x14001b629  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14001b630  nop     dword ptr [rax+rax+00h]
0x14001b635  test    rax, rax
0x14001b638  jnz     short loc_14001B651
0x14001b63a  mov     r9d, 445h
0x14001b640  mov     eax, 8000FFFFh
0x14001b645  mov     ebx, eax
0x14001b647  mov     ecx, 1
0x14001b64c  jmp     loc_14001B859
0x14001b651  xor     edx, edx
0x14001b653  mov     rcx, rax
0x14001b656  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x14001b65d  nop     dword ptr [rax+rax+00h]
0x14001b662  mov     ebx, eax
0x14001b664  test    eax, eax
0x14001b666  jns     short loc_14001B670
0x14001b668  mov     r9d, 448h
0x14001b66e  jmp     short loc_14001B647
0x14001b670  lea     rcx, aRcpic; "rcpic"
0x14001b677  call    cs:__imp_StrToID
0x14001b67e  nop     dword ptr [rax+rax+00h]
0x14001b683  movzx   edx, ax
0x14001b686  mov     rcx, rdi
0x14001b689  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14001b690  nop     dword ptr [rax+rax+00h]
0x14001b695  mov     r14, rax
0x14001b698  test    rax, rax
0x14001b69b  jnz     short loc_14001B6A5
0x14001b69d  mov     r9d, 44Bh
0x14001b6a3  jmp     short loc_14001B640
0x14001b6a5  xor     esi, esi
0x14001b6a7  lea     edi, [rsi+1]
0x14001b6aa  mov     rcx, r12; struct IRootCause *
0x14001b6ad  call    ?RootCause_GetNumberResolutions@@YAIPEAVIRootCause@@@Z; RootCause_GetNumberResolutions(IRootCause *)
0x14001b6b2  cmp     esi, eax
0x14001b6b4  jnb     loc_14001B83A
0x14001b6ba  mov     rcx, [rbp+var_28]
0x14001b6be  test    rcx, rcx
0x14001b6c1  jz      short loc_14001B6D3
0x14001b6c3  mov     rax, [rcx]
0x14001b6c6  mov     rax, [rax+10h]
0x14001b6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b6cf  mov     [rbp+var_28], r15
0x14001b6d3  mov     rax, [r12]
0x14001b6d7  lea     r8, [rbp+var_28]
0x14001b6db  mov     edx, esi
0x14001b6dd  mov     rcx, r12
0x14001b6e0  mov     rax, [rax+58h]
0x14001b6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b6e9  mov     ebx, eax
0x14001b6eb  test    eax, eax
0x14001b6ed  js      loc_14001B832
0x14001b6f3  mov     rcx, [rbp+var_28]; struct IResolution *
0x14001b6f7  call    ?Resolution_GetElevation@@YAHPEAVIResolution@@@Z; Resolution_GetElevation(IResolution *)
0x14001b6fc  test    eax, eax
0x14001b6fe  jnz     short loc_14001B704
0x14001b700  add     esi, edi
0x14001b702  jmp     short loc_14001B6AA
0x14001b704  call    cs:__imp_GetProcessHeap
0x14001b70b  nop     dword ptr [rax+rax+00h]
0x14001b710  xor     edx, edx; dwFlags
0x14001b712  mov     r8d, 800h; dwBytes
0x14001b718  mov     rcx, rax; hHeap
0x14001b71b  call    cs:__imp_HeapAlloc
0x14001b722  nop     dword ptr [rax+rax+00h]
0x14001b727  mov     r15, rax
0x14001b72a  test    rax, rax
0x14001b72d  jnz     short loc_14001B745
0x14001b72f  mov     ebx, 8007000Eh
0x14001b734  mov     r9d, 463h
0x14001b73a  mov     dword ptr [rsp+58h+var_38], ebx
0x14001b73e  mov     ecx, edi
0x14001b740  jmp     loc_14001B85D
0x14001b745  mov     r8d, 400h; cchBufferMax
0x14001b74b  mov     rdx, r15; lpBuffer
0x14001b74e  mov     ecx, 18Fh; uID
0x14001b753  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14001b758  mov     ebx, eax
0x14001b75a  test    eax, eax
0x14001b75c  jns     short loc_14001B769
0x14001b75e  mov     r9d, 466h
0x14001b764  jmp     loc_14001B857
0x14001b769  lea     rax, [rbp+var_18]
0x14001b76d  xor     r9d, r9d
0x14001b770  mov     [rsp+58h+var_30], rax
0x14001b775  lea     rdx, aShieldicon; "shieldicon"
0x14001b77c  xor     r8d, r8d
0x14001b77f  mov     [rsp+58h+var_38], 0
0x14001b788  mov     rcx, r13
0x14001b78b  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x14001b792  nop     dword ptr [rax+rax+00h]
0x14001b797  mov     ebx, eax
0x14001b799  test    eax, eax
0x14001b79b  jns     short loc_14001B7A8
0x14001b79d  mov     r9d, 46Ch
0x14001b7a3  jmp     loc_14001B857
0x14001b7a8  mov     rax, [r12]
0x14001b7ac  lea     rdx, [rbp+bstrString]
0x14001b7b0  mov     rcx, r12
0x14001b7b3  mov     rax, [rax+38h]
0x14001b7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b7bc  mov     ebx, eax
0x14001b7be  test    eax, eax
0x14001b7c0  jns     short loc_14001B7CD
0x14001b7c2  mov     r9d, 46Fh
0x14001b7c8  jmp     loc_14001B857
0x14001b7cd  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x14001b7d1  mov     r9, r15; unsigned __int16 *
0x14001b7d4  mov     rdx, [rbp+var_18]; struct DirectUI::Element *
0x14001b7d8  mov     [rsp+58h+var_38], 0; unsigned __int16 *
0x14001b7e1  call    ?SetAccValues@WizardPage@@IEAAJPEAVElement@DirectUI@@PEBG11@Z; WizardPage::SetAccValues(DirectUI::Element *,ushort const *,ushort const *,ushort const *)
0x14001b7e6  mov     ebx, eax
0x14001b7e8  test    eax, eax
0x14001b7ea  jns     short loc_14001B7F4
0x14001b7ec  mov     r9d, 475h
0x14001b7f2  jmp     short loc_14001B857
0x14001b7f4  mov     rcx, r14
0x14001b7f7  call    cs:__imp_?RemoveAll@Element@DirectUI@@QEAAJXZ; DirectUI::Element::RemoveAll(void)
0x14001b7fe  nop     dword ptr [rax+rax+00h]
0x14001b803  mov     ebx, eax
0x14001b805  test    eax, eax
0x14001b807  jns     short loc_14001B811
0x14001b809  mov     r9d, 478h
0x14001b80f  jmp     short loc_14001B857
0x14001b811  mov     rdx, [rbp+var_18]
0x14001b815  mov     rcx, r14
0x14001b818  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x14001b81f  nop     dword ptr [rax+rax+00h]
0x14001b824  mov     ebx, eax
0x14001b826  test    eax, eax
0x14001b828  jns     short loc_14001B870
0x14001b82a  mov     r9d, 47Bh
0x14001b830  jmp     short loc_14001B857
0x14001b832  mov     r9d, 451h
0x14001b838  jmp     short loc_14001B857
0x14001b83a  xor     edx, edx
0x14001b83c  mov     rcx, r14
0x14001b83f  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x14001b846  nop     dword ptr [rax+rax+00h]
0x14001b84b  mov     ebx, eax
0x14001b84d  test    eax, eax
0x14001b84f  jns     short loc_14001B870
0x14001b851  mov     r9d, 45Eh
0x14001b857  mov     ecx, edi; Level
0x14001b859  mov     dword ptr [rsp+58h+var_38], eax
0x14001b85d  lea     r8, aFinalelevation_2; "FinalElevationPage::SetupRootCauseResul"...
0x14001b864  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001b86b  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001b870  mov     rcx, [rbp+bstrString]; bstrString
0x14001b874  test    rcx, rcx
0x14001b877  jz      short loc_14001B88D
0x14001b879  call    cs:__imp_SysFreeString
0x14001b880  nop     dword ptr [rax+rax+00h]
0x14001b885  mov     [rbp+bstrString], 0
0x14001b88d  mov     rcx, [rbp+var_28]
0x14001b891  test    rcx, rcx
0x14001b894  jz      short loc_14001B8AA
0x14001b896  mov     rax, [rcx]
0x14001b899  mov     rax, [rax+10h]
0x14001b89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b8a2  mov     [rbp+var_28], 0
0x14001b8aa  test    r15, r15
0x14001b8ad  jz      short loc_14001B8CF
0x14001b8af  call    cs:__imp_GetProcessHeap
0x14001b8b6  nop     dword ptr [rax+rax+00h]
0x14001b8bb  mov     r8, r15; lpMem
0x14001b8be  xor     edx, edx; dwFlags
0x14001b8c0  mov     rcx, rax; hHeap
0x14001b8c3  call    cs:__imp_HeapFree
0x14001b8ca  nop     dword ptr [rax+rax+00h]
0x14001b8cf  mov     eax, ebx
0x14001b8d1  add     rsp, 58h
0x14001b8d5  pop     r15
0x14001b8d7  pop     r14
0x14001b8d9  pop     r13
0x14001b8db  pop     r12
0x14001b8dd  pop     rdi
0x14001b8de  pop     rsi
0x14001b8df  pop     rbx
0x14001b8e0  pop     rbp
0x14001b8e1  retn
```

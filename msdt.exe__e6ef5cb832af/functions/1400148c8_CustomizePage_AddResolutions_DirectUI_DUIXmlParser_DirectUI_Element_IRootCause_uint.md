# CustomizePage::AddResolutions(DirectUI::DUIXmlParser *,DirectUI::Element *,IRootCause *,uint)

- ea: `0x1400148c8`
- end: `0x140014d0f`
- name: `?AddResolutions@CustomizePage@@IEAAJPEAVDUIXmlParser@DirectUI@@PEAVElement@3@PEAVIRootCause@@I@Z`
- size: `1095`
- prototype: `int(CustomizePage *__hidden this, struct DirectUI::DUIXmlParser *, struct DirectUI::Element *, struct IRootCause *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140014d18`

## callees

- `0x14000706c`
- `0x1400070b0`
- `0x14000e378`
- `0x140010308`
- `0x1400148c8`
- `0x140020420`
- `0x140020d58`
- `0x14004175c`
- `0x14004e3d4`
- `0x14004effc`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140014925`
- `KERNEL32!HeapAlloc` at `0x140014925`
- `KERNEL32!HeapFree` at `0x140014ce8`
- `KERNEL32!HeapFree` at `0x140014ce8`
- `KERNEL32!GetProcessHeap` at `0x14001490e`
- `KERNEL32!GetProcessHeap` at `0x140014cd4`
- `KERNEL32!GetProcessHeap` at `0x14001490e`
- `KERNEL32!GetProcessHeap` at `0x140014cd4`
- `OLEAUT32!__imp_SysFreeString` at `0x140014974`
- `OLEAUT32!__imp_SysFreeString` at `0x140014991`
- `OLEAUT32!__imp_SysFreeString` at `0x140014c8d`
- `OLEAUT32!__imp_SysFreeString` at `0x140014ca6`
- `OLEAUT32!__imp_SysFreeString` at `0x140014974`
- `OLEAUT32!__imp_SysFreeString` at `0x140014991`
- `OLEAUT32!__imp_SysFreeString` at `0x140014c8d`
- `OLEAUT32!__imp_SysFreeString` at `0x140014ca6`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x140014bc4`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x140014bc4`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x140014a27`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x140014a27`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x140014ae4`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x140014ae4`
- `DUI70!StrToID` at `0x140014a44`
- `DUI70!StrToID` at `0x140014b99`
- `DUI70!StrToID` at `0x140014a44`
- `DUI70!StrToID` at `0x140014b99`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140014a57`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140014bac`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140014a57`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140014bac`

## pseudocode

```c
__int64 __fastcall CustomizePage::AddResolutions(
        CustomizePage *this,
        struct DirectUI::DUIXmlParser *a2,
        struct DirectUI::Element *a3,
        struct IRootCause *a4,
        unsigned int a5)
{
  struct IRootCause *v5; // rsi
  DirectUI::DUIXmlParser *v6; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v9; // r15
  unsigned int v10; // ebx
  unsigned int v11; // r12d
  int v12; // eax
  BOOL v13; // esi
  const unsigned __int16 *v14; // rdx
  unsigned __int16 v15; // ax
  __int64 v16; // r14
  WizardPage *v17; // rcx
  int v18; // r9d
  WizardPage *v19; // rcx
  unsigned __int16 v20; // ax
  DirectUI::Element *Descendent; // rax
  HANDLE v22; // rax
  WINBOOL IsMember; // [rsp+30h] [rbp-30h] BYREF
  int v25; // [rsp+34h] [rbp-2Ch] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-28h] BYREF
  BSTR v27; // [rsp+40h] [rbp-20h] BYREF
  struct IResolution *v28; // [rsp+48h] [rbp-18h] BYREF
  struct DirectUI::Element *v29; // [rsp+50h] [rbp-10h] BYREF

  v5 = a4;
  IsMember = 0;
  v6 = a2;
  v25 = 0;
  v29 = 0;
  bstrString = 0;
  v27 = 0;
  v28 = 0;
  ProcessHeap = GetProcessHeap();
  v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x1800u);
  if ( v9 )
  {
    v10 = 0;
    v11 = 0;
    while ( 1 )
    {
      if ( v11 >= RootCause_GetNumberResolutions(v5) )
        goto LABEL_47;
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v27 )
      {
        SysFreeString(v27);
        v27 = 0;
      }
      v12 = (*(__int64 (__fastcall **)(struct IRootCause *, _QWORD, struct IResolution **))(*(_QWORD *)v5 + 88LL))(
              v5,
              v11,
              &v28);
      v10 = v12;
      if ( v12 < 0 )
      {
        v18 = 2601;
        goto LABEL_46;
      }
      v13 = 0;
      if ( (unsigned int)Resolution_GetElevation(v28) )
      {
        v12 = IsAdminToken(&IsMember);
        v10 = v12;
        if ( v12 < 0 )
        {
          v18 = 2607;
          goto LABEL_46;
        }
        if ( !IsMember )
          v13 = *(_DWORD *)Config == 0;
      }
      v14 = L"checklistshieldid";
      if ( !v13 )
        v14 = L"checklistitemid";
      v12 = DirectUI::DUIXmlParser::CreateElement(v6, v14, 0, 0, 0, &v29);
      v10 = v12;
      if ( v12 < 0 )
      {
        v18 = 2623;
        goto LABEL_46;
      }
      v15 = StrToID(L"txtSubName");
      v16 = a5;
      *(_QWORD *)(*((_QWORD *)this + 14) + 8LL * a5) = DirectUI::Element::FindDescendent(v29, v15);
      if ( !*(_QWORD *)(*((_QWORD *)this + 14) + 8LL * a5) )
      {
        v12 = -2147418113;
        v18 = 2627;
        v10 = -2147418113;
        goto LABEL_46;
      }
      v12 = (*(__int64 (__fastcall **)(struct IResolution *, BSTR *))(*(_QWORD *)v28 + 56LL))(v28, &bstrString);
      v10 = v12;
      if ( v12 < 0 )
      {
        v18 = 2630;
        goto LABEL_46;
      }
      v12 = (*(__int64 (__fastcall **)(struct IResolution *, BSTR *))(*(_QWORD *)v28 + 64LL))(v28, &v27);
      v10 = v12;
      if ( v12 < 0 )
      {
        v18 = 2632;
        goto LABEL_46;
      }
      v12 = DwzStrTruncate(v9, 0x80u, bstrString, &v25);
      v10 = v12;
      if ( v12 < 0 )
      {
        v18 = 2638;
        goto LABEL_46;
      }
      v12 = DirectUI::Element::SetContentString(*(DirectUI::Element **)(*((_QWORD *)this + 14) + 8LL * a5), v9);
      v10 = v12;
      if ( v12 < 0 )
      {
        v18 = 2641;
        goto LABEL_46;
      }
      if ( v25 )
      {
        v12 = StringCchPrintfW(v9, 0xC00u, L"%s\n\n%s", bstrString, v27);
        v10 = v12;
        if ( v12 < 0 )
        {
          v18 = 2650;
LABEL_46:
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CustomizePage::AddResolutions", v18, v12);
          goto LABEL_47;
        }
      }
      else
      {
        v12 = StringCchCopyW(v9, 0xC00u, v27);
        v10 = v12;
        if ( v12 < 0 )
        {
          v18 = 2653;
          goto LABEL_46;
        }
      }
      v12 = WizardPage::SetAccValues(
              v17,
              *(struct DirectUI::Element **)(*((_QWORD *)this + 14) + 8LL * a5),
              bstrString,
              0,
              v9);
      v10 = v12;
      if ( v12 < 0 )
      {
        v18 = 2657;
        goto LABEL_46;
      }
      v12 = WizardPage::EnableTooltip(v19, *(struct DirectUI::Element **)(*((_QWORD *)this + 14) + 8LL * a5), 1);
      v10 = v12;
      if ( v12 < 0 )
      {
        v18 = 2660;
        goto LABEL_46;
      }
      if ( v13 )
        *(_QWORD *)(*((_QWORD *)this + 14) + 8LL * a5) = 0;
      v20 = StrToID(L"entrypointlist");
      Descendent = DirectUI::Element::FindDescendent(a3, v20);
      if ( !Descendent )
      {
        v12 = -2147418113;
        v18 = 2672;
        v10 = -2147418113;
        goto LABEL_46;
      }
      v12 = DirectUI::Element::Add(Descendent, v29);
      v10 = v12;
      if ( v12 < 0 )
      {
        v18 = 2675;
        goto LABEL_46;
      }
      ++v11;
      ++a5;
      v5 = a4;
      *(_QWORD *)(*((_QWORD *)this + 15) + 8 * v16) = v29;
      v6 = a2;
    }
  }
  v10 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CustomizePage::AddResolutions", 2591, -2147024882);
LABEL_47:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v27 )
  {
    SysFreeString(v27);
    v27 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(struct IResolution *))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v9 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v9);
  }
  return v10;
}

```

## disassembly

```asm
0x1400148c8  mov     rax, rsp
0x1400148cb  mov     [rax+8], rbx
0x1400148cf  mov     [rax+20h], r9
0x1400148d3  mov     [rax+18h], r8
0x1400148d7  mov     [rax+10h], rdx
0x1400148db  push    rbp
0x1400148dc  push    rsi
0x1400148dd  push    rdi
0x1400148de  push    r12
0x1400148e0  push    r13
0x1400148e2  push    r14
0x1400148e4  push    r15
0x1400148e6  mov     rbp, rsp
0x1400148e9  sub     rsp, 60h
0x1400148ed  xor     edi, edi
0x1400148ef  mov     rsi, r9
0x1400148f2  mov     [rbp+IsMember], edi
0x1400148f5  mov     r14, rdx
0x1400148f8  mov     [rbp+var_2C], edi
0x1400148fb  mov     r13, rcx
0x1400148fe  mov     [rbp+var_10], rdi
0x140014902  mov     [rbp+bstrString], rdi
0x140014906  mov     [rbp+var_20], rdi
0x14001490a  mov     [rbp+var_18], rdi
0x14001490e  call    cs:__imp_GetProcessHeap
0x140014915  nop     dword ptr [rax+rax+00h]
0x14001491a  xor     edx, edx; dwFlags
0x14001491c  mov     r8d, 1800h; dwBytes
0x140014922  mov     rcx, rax; hHeap
0x140014925  call    cs:__imp_HeapAlloc
0x14001492c  nop     dword ptr [rax+rax+00h]
0x140014931  mov     r15, rax
0x140014934  test    rax, rax
0x140014937  jnz     short loc_140014950
0x140014939  mov     ebx, 8007000Eh
0x14001493e  lea     ecx, [rdi+1]
0x140014941  mov     dword ptr [rsp+60h+var_40], ebx
0x140014945  mov     r9d, 0A1Fh
0x14001494b  jmp     loc_140014C6F
0x140014950  mov     ebx, edi
0x140014952  mov     r12d, edi
0x140014955  mov     edi, 1
0x14001495a  mov     rcx, rsi; struct IRootCause *
0x14001495d  call    ?RootCause_GetNumberResolutions@@YAIPEAVIRootCause@@@Z; RootCause_GetNumberResolutions(IRootCause *)
0x140014962  cmp     r12d, eax
0x140014965  jnb     loc_140014C82
0x14001496b  mov     rcx, [rbp+bstrString]; bstrString
0x14001496f  test    rcx, rcx
0x140014972  jz      short loc_140014988
0x140014974  call    cs:__imp_SysFreeString
0x14001497b  nop     dword ptr [rax+rax+00h]
0x140014980  mov     [rbp+bstrString], 0
0x140014988  mov     rcx, [rbp+var_20]; bstrString
0x14001498c  test    rcx, rcx
0x14001498f  jz      short loc_1400149A5
0x140014991  call    cs:__imp_SysFreeString
0x140014998  nop     dword ptr [rax+rax+00h]
0x14001499d  mov     [rbp+var_20], 0
0x1400149a5  mov     rax, [rsi]
0x1400149a8  lea     r8, [rbp+var_18]
0x1400149ac  mov     edx, r12d
0x1400149af  mov     rcx, rsi
0x1400149b2  mov     rax, [rax+58h]
0x1400149b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400149bb  mov     ebx, eax
0x1400149bd  test    eax, eax
0x1400149bf  js      loc_140014C63
0x1400149c5  mov     rcx, [rbp+var_18]; struct IResolution *
0x1400149c9  xor     esi, esi
0x1400149cb  call    ?Resolution_GetElevation@@YAHPEAVIResolution@@@Z; Resolution_GetElevation(IResolution *)
0x1400149d0  test    eax, eax
0x1400149d2  jz      short loc_1400149F8
0x1400149d4  lea     rcx, [rbp+IsMember]; IsMember
0x1400149d8  call    ?IsAdminToken@@YAJPEAH@Z; IsAdminToken(int *)
0x1400149dd  mov     ebx, eax
0x1400149df  test    eax, eax
0x1400149e1  js      loc_140014BF5
0x1400149e7  cmp     [rbp+IsMember], esi
0x1400149ea  jnz     short loc_1400149F8
0x1400149ec  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400149f3  cmp     [rax], esi
0x1400149f5  cmovz   esi, edi
0x1400149f8  lea     rax, aChecklistitemi; "checklistitemid"
0x1400149ff  test    esi, esi
0x140014a01  lea     rdx, aChecklistshiel; "checklistshieldid"
0x140014a08  mov     rcx, r14
0x140014a0b  cmovz   rdx, rax
0x140014a0f  lea     rax, [rbp+var_10]
0x140014a13  mov     [rsp+60h+var_38], rax
0x140014a18  xor     r9d, r9d
0x140014a1b  xor     r8d, r8d
0x140014a1e  mov     [rsp+60h+var_40], 0
0x140014a27  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x140014a2e  nop     dword ptr [rax+rax+00h]
0x140014a33  mov     ebx, eax
0x140014a35  test    eax, eax
0x140014a37  js      loc_140014C5B
0x140014a3d  lea     rcx, aTxtsubname; "txtSubName"
0x140014a44  call    cs:__imp_StrToID
0x140014a4b  nop     dword ptr [rax+rax+00h]
0x140014a50  mov     rcx, [rbp+var_10]
0x140014a54  movzx   edx, ax
0x140014a57  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x140014a5e  nop     dword ptr [rax+rax+00h]
0x140014a63  mov     r14d, [rbp+arg_20]
0x140014a67  mov     rcx, [r13+70h]
0x140014a6b  mov     [rcx+r14*8], rax
0x140014a6f  mov     rax, [r13+70h]
0x140014a73  cmp     qword ptr [rax+r14*8], 0
0x140014a78  jz      loc_140014C4C
0x140014a7e  mov     rcx, [rbp+var_18]
0x140014a82  lea     rdx, [rbp+bstrString]
0x140014a86  mov     rax, [rcx]
0x140014a89  mov     rax, [rax+38h]
0x140014a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a92  mov     ebx, eax
0x140014a94  test    eax, eax
0x140014a96  js      loc_140014C44
0x140014a9c  mov     rcx, [rbp+var_18]
0x140014aa0  lea     rdx, [rbp+var_20]
0x140014aa4  mov     rax, [rcx]
0x140014aa7  mov     rax, [rax+40h]
0x140014aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ab0  mov     ebx, eax
0x140014ab2  test    eax, eax
0x140014ab4  js      loc_140014C3C
0x140014aba  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x140014abe  lea     r9, [rbp+var_2C]; int *
0x140014ac2  mov     edx, 80h; unsigned __int64
0x140014ac7  mov     rcx, r15; unsigned __int16 *
0x140014aca  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x140014acf  mov     ebx, eax
0x140014ad1  test    eax, eax
0x140014ad3  js      loc_140014C34
0x140014ad9  mov     rcx, [r13+70h]
0x140014add  mov     rdx, r15
0x140014ae0  mov     rcx, [rcx+r14*8]
0x140014ae4  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x140014aeb  nop     dword ptr [rax+rax+00h]
0x140014af0  mov     ebx, eax
0x140014af2  test    eax, eax
0x140014af4  js      loc_140014C2C
0x140014afa  cmp     [rbp+var_2C], 0
0x140014afe  mov     edx, 0C00h; unsigned __int64
0x140014b03  mov     rcx, r15; unsigned __int16 *
0x140014b06  jz      short loc_140014B32
0x140014b08  mov     rax, [rbp+var_20]
0x140014b0c  lea     r8, aSS_3; "%s\n\n%s"
0x140014b13  mov     r9, [rbp+bstrString]
0x140014b17  mov     [rsp+60h+var_40], rax
0x140014b1c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014b21  mov     ebx, eax
0x140014b23  test    eax, eax
0x140014b25  jns     short loc_140014B45
0x140014b27  mov     r9d, 0A5Ah
0x140014b2d  jmp     loc_140014C69
0x140014b32  mov     r8, [rbp+var_20]; unsigned __int16 *
0x140014b36  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140014b3b  mov     ebx, eax
0x140014b3d  test    eax, eax
0x140014b3f  js      loc_140014C24
0x140014b45  mov     rdx, [r13+70h]
0x140014b49  xor     r9d, r9d; unsigned __int16 *
0x140014b4c  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x140014b50  mov     [rsp+60h+var_40], r15; unsigned __int16 *
0x140014b55  mov     rdx, [rdx+r14*8]; struct DirectUI::Element *
0x140014b59  call    ?SetAccValues@WizardPage@@IEAAJPEAVElement@DirectUI@@PEBG11@Z; WizardPage::SetAccValues(DirectUI::Element *,ushort const *,ushort const *,ushort const *)
0x140014b5e  mov     ebx, eax
0x140014b60  test    eax, eax
0x140014b62  js      loc_140014C1C
0x140014b68  mov     rdx, [r13+70h]
0x140014b6c  mov     r8d, edi; int
0x140014b6f  mov     rdx, [rdx+r14*8]; struct DirectUI::Element *
0x140014b73  call    ?EnableTooltip@WizardPage@@IEAAJPEAVElement@DirectUI@@H@Z; WizardPage::EnableTooltip(DirectUI::Element *,int)
0x140014b78  mov     ebx, eax
0x140014b7a  test    eax, eax
0x140014b7c  js      loc_140014C14
0x140014b82  test    esi, esi
0x140014b84  jz      short loc_140014B92
0x140014b86  mov     rax, [r13+70h]
0x140014b8a  mov     qword ptr [rax+r14*8], 0
0x140014b92  lea     rcx, aEntrypointlist; "entrypointlist"
0x140014b99  call    cs:__imp_StrToID
0x140014ba0  nop     dword ptr [rax+rax+00h]
0x140014ba5  mov     rcx, [rbp+arg_10]
0x140014ba9  movzx   edx, ax
0x140014bac  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x140014bb3  nop     dword ptr [rax+rax+00h]
0x140014bb8  test    rax, rax
0x140014bbb  jz      short loc_140014C05
0x140014bbd  mov     rdx, [rbp+var_10]
0x140014bc1  mov     rcx, rax
0x140014bc4  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x140014bcb  nop     dword ptr [rax+rax+00h]
0x140014bd0  mov     ebx, eax
0x140014bd2  test    eax, eax
0x140014bd4  js      short loc_140014BFD
0x140014bd6  mov     rcx, [r13+78h]
0x140014bda  add     r12d, edi
0x140014bdd  mov     rax, [rbp+var_10]
0x140014be1  add     [rbp+arg_20], edi
0x140014be4  mov     rsi, [rbp+arg_18]
0x140014be8  mov     [rcx+r14*8], rax
0x140014bec  mov     r14, [rbp+arg_8]
0x140014bf0  jmp     loc_14001495A
0x140014bf5  mov     r9d, 0A2Fh
0x140014bfb  jmp     short loc_140014C69
0x140014bfd  mov     r9d, 0A73h
0x140014c03  jmp     short loc_140014C69
0x140014c05  mov     eax, 8000FFFFh
0x140014c0a  mov     r9d, 0A70h
0x140014c10  mov     ebx, eax
0x140014c12  jmp     short loc_140014C69
0x140014c14  mov     r9d, 0A64h
0x140014c1a  jmp     short loc_140014C69
0x140014c1c  mov     r9d, 0A61h
0x140014c22  jmp     short loc_140014C69
0x140014c24  mov     r9d, 0A5Dh
0x140014c2a  jmp     short loc_140014C69
0x140014c2c  mov     r9d, 0A51h
0x140014c32  jmp     short loc_140014C69
0x140014c34  mov     r9d, 0A4Eh
0x140014c3a  jmp     short loc_140014C69
0x140014c3c  mov     r9d, 0A48h
0x140014c42  jmp     short loc_140014C69
0x140014c44  mov     r9d, 0A46h
0x140014c4a  jmp     short loc_140014C69
0x140014c4c  mov     eax, 8000FFFFh
0x140014c51  mov     r9d, 0A43h
0x140014c57  mov     ebx, eax
0x140014c59  jmp     short loc_140014C69
0x140014c5b  mov     r9d, 0A3Fh
0x140014c61  jmp     short loc_140014C69
0x140014c63  mov     r9d, 0A29h
0x140014c69  mov     ecx, edi; Level
0x140014c6b  mov     dword ptr [rsp+60h+var_40], eax
0x140014c6f  lea     r8, aCustomizepageA_0; "CustomizePage::AddResolutions"
0x140014c76  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140014c7d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140014c82  mov     rcx, [rbp+bstrString]; bstrString
0x140014c86  xor     edi, edi
0x140014c88  test    rcx, rcx
0x140014c8b  jz      short loc_140014C9D
0x140014c8d  call    cs:__imp_SysFreeString
0x140014c94  nop     dword ptr [rax+rax+00h]
0x140014c99  mov     [rbp+bstrString], rdi
0x140014c9d  mov     rcx, [rbp+var_20]; bstrString
0x140014ca1  test    rcx, rcx
0x140014ca4  jz      short loc_140014CB6
0x140014ca6  call    cs:__imp_SysFreeString
0x140014cad  nop     dword ptr [rax+rax+00h]
0x140014cb2  mov     [rbp+var_20], rdi
0x140014cb6  mov     rcx, [rbp+var_18]
0x140014cba  test    rcx, rcx
0x140014cbd  jz      short loc_140014CCF
0x140014cbf  mov     rax, [rcx]
0x140014cc2  mov     rax, [rax+10h]
0x140014cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ccb  mov     [rbp+var_18], rdi
0x140014ccf  test    r15, r15
0x140014cd2  jz      short loc_140014CF4
0x140014cd4  call    cs:__imp_GetProcessHeap
0x140014cdb  nop     dword ptr [rax+rax+00h]
0x140014ce0  mov     r8, r15; lpMem
0x140014ce3  xor     edx, edx; dwFlags
0x140014ce5  mov     rcx, rax; hHeap
0x140014ce8  call    cs:__imp_HeapFree
0x140014cef  nop     dword ptr [rax+rax+00h]
0x140014cf4  mov     eax, ebx
0x140014cf6  mov     rbx, [rsp+60h+arg_0]
0x140014cfe  add     rsp, 60h
0x140014d02  pop     r15
0x140014d04  pop     r14
0x140014d06  pop     r13
0x140014d08  pop     r12
0x140014d0a  pop     rdi
0x140014d0b  pop     rsi
0x140014d0c  pop     rbp
0x140014d0d  retn
```

# CMarkup::ProcessURLAction2(ulong,int *,ulong,ulong *,IUri *,uchar *,ulong,PUA_Flags)

- ea: `0x1803e51b0`
- end: `0x1803e5cd6`
- name: `?ProcessURLAction2@CMarkup@@UEAAJKPEAHKPEAKPEAUIUri@@PEAEKW4PUA_Flags@@@Z`
- size: `2854`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x180011a98`
- `0x18005d080`
- `0x18005e684`
- `0x1800ea428`
- `0x18011a7c4`
- `0x180133b3c`
- `0x180139080`
- `0x1801dc4a4`
- `0x180265374`
- `0x180303f98`
- `0x1803cc580`
- `0x1803ddae0`
- `0x1803e434c`
- `0x1803e51b0`
- `0x1803e706c`
- `0x180402d68`
- `0x18040ac58`
- `0x1804b4674`
- `0x180681508`
- `0x18077b900`
- `0x18083bed4`
- `0x18084ed20`
- `0x180898b90`
- `0x181104010`

## import_xrefs

- `iertutil!CreateUri` at `0x1803e5ac5`
- `iertutil!CreateUri` at `0x1803e5ac5`
- `iertutil!__imp_?IECompatLogLMZL2@@YAXPEAUIUri@@K@Z` at `0x1803e5b0a`
- `iertutil!__imp_?IECompatLogLMZL2@@YAXPEAUIUri@@K@Z` at `0x1803e5b75`
- `iertutil!__imp_?IECompatLogLMZL2@@YAXPEAUIUri@@K@Z` at `0x1803e5b0a`
- `iertutil!__imp_?IECompatLogLMZL2@@YAXPEAUIUri@@K@Z` at `0x1803e5b75`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1803e5363`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1803e53ba`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1803e5660`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1803e5732`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1803e5905`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1803e5363`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1803e53ba`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1803e5660`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1803e5732`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1803e5905`
- `urlmon!__imp_GetZoneFromUriPrivate` at `0x1803e539e`
- `urlmon!__imp_GetZoneFromUriPrivate` at `0x1803e539e`

## string_xrefs

- `0x1803e5a59`: `about:security_`

## pseudocode

```c
__int64 __fastcall CMarkup::ProcessURLAction2(
        __int64 a1,
        unsigned int a2,
        _DWORD *a3,
        int a4,
        _DWORD *a5,
        IUri *a6,
        __int64 a7,
        int a8,
        char a9)
{
  int v9; // ebx
  __int64 v13; // rax
  HRESULT Uri; // esi
  int v15; // r12d
  __int64 v16; // rdx
  struct CDwnDoc *DwnDoc; // rax
  int v18; // ecx
  struct CElement *FrameSite; // rbx
  __int64 v20; // rax
  __int64 v21; // rcx
  CMarkup *v22; // rdx
  CMarkup *v23; // rax
  int v24; // r12d
  HRESULT v25; // eax
  __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // r12d
  int v29; // ebx
  HRESULT v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  int v34; // ecx
  _DWORD *v35; // r14
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // ecx
  CDoc *v39; // rbx
  CMarkup *v40; // rcx
  bool v41; // al
  unsigned int v42; // edx
  void *v43; // r8
  CMarkup *v45; // rcx
  struct COmWindowProxy *v46; // rax
  CWindow *v47; // r8
  struct IFrameContentData *FrameContentData; // rax
  unsigned int v49; // r14d
  HRESULT v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rcx
  int v55; // r12d
  HRESULT v56; // eax
  __int64 v57; // rcx
  __int64 v58; // rax
  HRESULT v59; // eax
  __int64 v60; // rcx
  __int64 v61; // rax
  _DWORD *v62; // rax
  unsigned int v63; // r8d
  unsigned __int64 v64; // r9
  __int64 v65; // rax
  unsigned __int64 v66; // rbx
  __int64 v67; // rax
  unsigned __int64 v68; // kr00_8
  int v69; // eax
  CDoc *v70; // rbx
  CMarkup *v71; // rcx
  bool IsPendingRoot; // al
  CMarkup *v73; // rcx
  struct CDoc *v74; // rax
  CMarkup *v75; // rcx
  struct GWND *Gwnd; // rax
  unsigned __int64 v77; // r10
  CMarkup *v78; // rcx
  CMarkup *v79; // rcx
  CMarkup *v80; // rcx
  CMarkup *v81; // rcx
  CMarkup *v82; // rcx
  IUri *ppURI; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v84; // [rsp+68h] [rbp-41h] BYREF
  struct IUnknown *v85; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int64 v86; // [rsp+78h] [rbp-31h] BYREF
  int v87; // [rsp+80h] [rbp-29h] BYREF
  int v88; // [rsp+84h] [rbp-25h] BYREF
  int v89; // [rsp+88h] [rbp-21h] BYREF
  int v90; // [rsp+8Ch] [rbp-1Dh] BYREF
  int v91; // [rsp+90h] [rbp-19h] BYREF
  LPCWSTR pwzURI; // [rsp+98h] [rbp-11h]
  unsigned __int16 *v93; // [rsp+A0h] [rbp-9h] BYREF
  int v94; // [rsp+F8h] [rbp+4Fh] BYREF
  _DWORD *v95; // [rsp+100h] [rbp+57h]

  v95 = a3;
  v9 = 0;
  v94 = 0;
  v85 = 0;
  pwzURI = 0;
  ppURI = 0;
  *a3 = 0;
  if ( a2 == 5120 && (*(_BYTE *)(a1 + 756) & 8) != 0 )
  {
    v62 = a5;
    Uri = 0;
    *a3 = 1;
    if ( v62 )
      *v62 = 0;
    goto LABEL_71;
  }
  v13 = *(_QWORD *)(a1 + 320);
  if ( !v13 || !*(_QWORD *)(v13 + 16) )
  {
    Uri = -2147467259;
    goto LABEL_70;
  }
  if ( *(__int64 (__fastcall **)())(*(_QWORD *)a1 + 984LL) != _vtguard )
    _report_securityfailure(1);
  Uri = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)a1 + 1016LL))(a1, &v85);
  if ( Uri < 0 )
    goto LABEL_70;
  v15 = a9 & 1;
  v16 = 128;
  switch ( a2 )
  {
    case 0x1400u:
      if ( (a9 & 1) == 0 && (unsigned int)CMarkup::DontRunScripts((CMarkup *)a1) )
        goto LABEL_71;
      v9 = v16;
      if ( (*(_DWORD *)(a1 + 756) & 0x100) != 0 && !CMarkup::SandboxAllowScript((CMarkup *)a1) )
        goto LABEL_71;
      break;
    case 0x1200u:
      v9 = 512;
      break;
    case 0x1605u:
    case 0x1C00u:
      v9 = 256;
      break;
  }
  if ( (a9 & 2) == 0
    && v9
    && ((DwnDoc = CMarkup::GetDwnDoc((CMarkup *)a1)) == 0
      ? (v18 = *((_DWORD *)CMarkup::Doc((CMarkup *)a1) + 1112))
      : (v18 = *((_DWORD *)DwnDoc + 41)),
        (v18 & v9) != 0) )
  {
    if ( !v15 )
      goto LABEL_70;
    if ( v9 != 128 )
      goto LABEL_70;
    FrameSite = 0;
    if ( !(unsigned int)CMarkup::DontRunScripts((CMarkup *)a1) )
      goto LABEL_70;
  }
  else
  {
    FrameSite = 0;
  }
  if ( a6 )
  {
    ppURI = a6;
    ((void (__fastcall *)(IUri *, __int64))a6->lpVtbl->AddRef)(a6, v16);
  }
  else
  {
    Uri = CMarkup::GetUri((const struct CMarkup *const)a1, &ppURI);
    if ( Uri < 0 || !ppURI )
      goto LABEL_71;
  }
  if ( g_IEHardened
    && !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_HARDENING_SHOW_SECURITY_URL_ON_ABOUT_BLANK)
    && IsEqualUri(ppURI, L"about:blank", v63, v64) )
  {
    v65 = -1;
    do
      ++v65;
    while ( g_tszModuleFileName[v65] );
    v66 = v65 + 16;
    v68 = v65 + 16;
    v67 = 2 * (v65 + 16);
    if ( !is_mul_ok(v68, 2u) )
      v67 = -1;
    pwzURI = (LPCWSTR)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v67);
    if ( !pwzURI )
    {
      Uri = -2147024882;
      goto LABEL_70;
    }
    v93 = 0;
    v86 = v66;
    v69 = StringCchCopyNExW((STRSAFE_LPWSTR)pwzURI, v66, L"about:security_", 0xFu, &v93, &v86, 0x900u);
    FrameSite = 0;
    Uri = v69;
    if ( v69 >= 0 )
      Uri = StringCchCopyW(v93, v86, g_tszModuleFileName);
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    if ( Uri < 0 || (Uri = CreateUri(pwzURI, 0x3002B80u, 0, &ppURI), Uri < 0) )
    {
      ppURI = 0;
      goto LABEL_70;
    }
  }
  v20 = *(_QWORD *)(a1 + 320);
  v21 = 0;
  if ( v20 )
    v21 = *(_QWORD *)(v20 + 16);
  v22 = *(CMarkup **)(a1 + 144);
  v23 = (CMarkup *)a1;
  v24 = *(_DWORD *)(v21 + 5560);
  LODWORD(v86) = v24;
  if ( v22 )
    v23 = v22;
  if ( (*((_DWORD *)v23 + 187) & 0x4000000) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 748) & 0x8000000) == 0 )
    {
      v45 = (CMarkup *)a1;
      if ( v22 )
        v45 = v22;
      v46 = CMarkup::Window(v45);
      goto LABEL_78;
    }
  }
  else if ( (*(_DWORD *)(a1 + 748) & 0x8000000) == 0 )
  {
    goto LABEL_26;
  }
  v46 = *(struct COmWindowProxy **)(a1 + 352);
LABEL_78:
  if ( v46 )
  {
    if ( (*(_BYTE *)(*((_QWORD *)v46 + 15) + 224LL) & 0x40) != 0 )
    {
      a4 |= 0x100u;
    }
    else if ( (*((_BYTE *)v46 + 168) & 2) != 0 )
    {
      a4 |= 0x40u;
    }
    if ( (*((_BYTE *)CMarkup::Doc((CMarkup *)a1) + 4860) & 1) != 0 )
    {
      FrameSite = CWindow::GetFrameSite(v47);
      FrameContentData = GetFrameContentData(FrameSite);
      if ( !FrameSite
        || (FrameSite = 0,
            (*(unsigned __int8 (__fastcall **)(struct IFrameContentData *))(*(_QWORD *)FrameContentData + 16LL))(FrameContentData)) )
      {
        a4 |= 0x40u;
      }
    }
  }
LABEL_26:
  if ( v85 == (struct IUnknown *)FrameSite )
    goto LABEL_70;
  v87 = (int)FrameSite;
  v84 = -1;
  v89 = -1;
  v25 = CoInternetIsFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 2u) == 1
      ? GetZoneFromUriPrivate(v85, ppURI, &v84, 0, FrameSite, FrameSite, 0x40000000, FrameSite)
      : ((__int64 (__fastcall *)(struct IUnknown *, IUri *, unsigned int *, _QWORD, struct CElement *, struct CElement *))v85->lpVtbl[4].QueryInterface)(
          v85,
          ppURI,
          &v84,
          0,
          FrameSite,
          FrameSite);
  Uri = v25;
  if ( v25 )
    goto LABEL_70;
  if ( CoInternetIsFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 2u) != 1 && !v84 )
    LODWORD(FrameSite) = 1;
  v26 = *(_QWORD *)(a1 + 320);
  Uri = 0;
  v27 = 0;
  if ( v26 )
    v27 = *(_QWORD *)(v26 + 16);
  if ( (*(_BYTE *)(v27 + 4872) & 2) != 0 )
  {
    a4 |= 0x10000u;
  }
  else if ( !v84 && CoInternetIsFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 2u) != 1 )
  {
    v49 = a4 & 0xFFFFFFFB;
    if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
      IECompatLogLMZL2(ppURI, a2);
    v50 = ((__int64 (__fastcall *)(struct IUnknown *, IUri *, _QWORD, int *, int, __int64, int, unsigned int, _QWORD, int *))v85->lpVtbl[4].AddRef)(
            v85,
            ppURI,
            a2,
            &v89,
            4,
            a7,
            a8,
            v49 | 0x10001,
            0,
            &v87);
    v51 = *(_QWORD *)(a1 + 320);
    if ( v50 != 1 )
      Uri = v50;
    v52 = 0;
    if ( v51 )
      v52 = *(_QWORD *)(v51 + 16);
    if ( *(_DWORD *)(v52 + 5560) != v24 )
      goto LABEL_134;
    if ( Uri )
      goto LABEL_70;
    a4 = v49 | 0x20001;
    Uri = 0;
  }
  v28 = 0;
  v88 = -1;
  v91 = -1;
  if ( (_DWORD)FrameSite || CoInternetIsFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 2u) == 1 )
    goto LABEL_36;
  if ( v84 > 4 )
    goto LABEL_158;
  v53 = *(_QWORD *)(a1 + 320);
  v54 = 0;
  if ( v53 )
    v54 = *(_QWORD *)(v53 + 16);
  if ( *(_DWORD *)(v54 + 4LL * v84 + 4952) == 1 )
  {
LABEL_158:
    a4 |= 0x40000u;
LABEL_36:
    v29 = v86;
    goto LABEL_37;
  }
  v55 = a8;
  v56 = ((__int64 (__fastcall *)(struct IUnknown *, IUri *, __int64, int *, int, __int64, int, unsigned int, _QWORD, int *))v85->lpVtbl[4].AddRef)(
          v85,
          ppURI,
          8960,
          &v88,
          4,
          a7,
          a8,
          a4 & 0xFFFBFFFA | 0x40001,
          0,
          &v87);
  v57 = *(_QWORD *)(a1 + 320);
  if ( v56 != 1 )
    Uri = v56;
  v58 = 0;
  if ( v57 )
    v58 = *(_QWORD *)(v57 + 16);
  if ( *(_DWORD *)(v58 + 5560) != (_DWORD)v86 )
    goto LABEL_134;
  if ( Uri )
    goto LABEL_70;
  v59 = ((__int64 (__fastcall *)(struct IUnknown *, IUri *, _QWORD, int *, int, __int64, int, unsigned int, _QWORD, int *))v85->lpVtbl[4].AddRef)(
          v85,
          ppURI,
          a2,
          &v91,
          4,
          a7,
          v55,
          a4 & 0xFFFBFFFA | 0x40001,
          0,
          &v87);
  v60 = *(_QWORD *)(a1 + 320);
  Uri = 0;
  if ( v59 != 1 )
    Uri = v59;
  v61 = 0;
  if ( v60 )
    v61 = *(_QWORD *)(v60 + 16);
  v29 = v86;
  if ( *(_DWORD *)(v61 + 5560) != (_DWORD)v86 )
  {
LABEL_134:
    Uri = -2147467260;
    goto LABEL_70;
  }
  if ( Uri )
    goto LABEL_70;
  a4 |= 0x80000u;
  Uri = 0;
  v28 = 1;
  if ( v88 )
    a4 |= 0x100000u;
LABEL_37:
  v90 = 0;
  v30 = ((__int64 (__fastcall *)(struct IUnknown *, IUri *, _QWORD, int *, int, __int64, int, int, _QWORD, int *))v85->lpVtbl[4].AddRef)(
          v85,
          ppURI,
          a2,
          &v94,
          4,
          a7,
          a8,
          a4,
          0,
          &v90);
  v31 = *(_QWORD *)(a1 + 320);
  if ( v30 != 1 )
    Uri = v30;
  v32 = 0;
  if ( v31 )
    v32 = *(_QWORD *)(v31 + 16);
  if ( *(_DWORD *)(v32 + 5560) != v29 )
    goto LABEL_134;
  if ( Uri )
  {
LABEL_70:
    *v95 = 0;
    goto LABEL_71;
  }
  v33 = v94;
  if ( a5 )
    *a5 = v94;
  v34 = 0;
  if ( a2 == 7168 )
    LOBYTE(v34) = v33 != 0;
  else
    LOBYTE(v34) = (v33 & 0xF) == 0;
  v35 = v95;
  v36 = 0;
  *v95 = v34;
  v37 = *(_QWORD *)(a1 + 320);
  if ( v37 )
    v36 = *(_QWORD *)(v37 + 16);
  if ( (*(_BYTE *)(v36 + 4872) & 2) != 0 || v84 )
    goto LABEL_50;
  if ( CoInternetIsFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 2u) == 1 )
  {
LABEL_126:
    v33 = v94;
    goto LABEL_50;
  }
  v33 = v94;
  if ( !v94 && !v89 || v94 == 3 && v89 == 3 )
    goto LABEL_50;
  if ( v94 )
  {
LABEL_167:
    if ( g_cmptlgs != 1 )
    {
      if ( (unsigned int)IECompatLoggingEnabled() )
        IECompatLogLMZL2(ppURI, a2);
      v33 = v94;
    }
    if ( (a9 & 4) != 0 )
      goto LABEL_50;
    v70 = CMarkup::Doc((CMarkup *)a1);
    IsPendingRoot = CMarkup::IsPendingRoot(v71);
    if ( (unsigned int)CDoc::OnPageActionBlocked(v70, 0x80u, IsPendingRoot, 0) == -2147221244
      && (unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
      && (*((_BYTE *)CMarkup::Doc((CMarkup *)a1) + 4872) & 4) == 0 )
    {
      v74 = CMarkup::Doc(v73);
      *((_DWORD *)v74 + 1218) |= 4u;
      CMarkup::Doc(v75);
      Gwnd = GetGwnd();
      _GWPostMethodCallEx(Gwnd, v77, (__int64)CDoc::ShowLMZLUnlockDialog, 0, 1, 0);
    }
    goto LABEL_126;
  }
  if ( a2 != 7168 || v89 )
  {
    *v35 = 0;
    goto LABEL_167;
  }
LABEL_50:
  if ( !v28 || (v90 & 1) == 0 || !v33 && !v91 || v33 == 3 && v91 == 3 || a2 == 7168 && !v33 && !v91 )
    goto LABEL_71;
  v38 = v88;
  if ( !v33 && v88 )
    *v35 = 0;
  if ( v38 == 1 )
  {
    if ( v84 )
    {
      switch ( v84 )
      {
        case 1u:
          v39 = CMarkup::Doc((CMarkup *)a1);
          v41 = CMarkup::IsPendingRoot(v80);
          v42 = 4096;
          break;
        case 2u:
          v39 = CMarkup::Doc((CMarkup *)a1);
          v41 = CMarkup::IsPendingRoot(v79);
          v42 = 2048;
          break;
        case 3u:
          v39 = CMarkup::Doc((CMarkup *)a1);
          v41 = CMarkup::IsPendingRoot(v78);
          v42 = 0x2000;
          break;
        case 4u:
          v39 = CMarkup::Doc((CMarkup *)a1);
          v41 = CMarkup::IsPendingRoot(v40);
          v42 = 0x4000;
          break;
        default:
          goto LABEL_71;
      }
    }
    else
    {
      v39 = CMarkup::Doc((CMarkup *)a1);
      v41 = CMarkup::IsPendingRoot(v81);
      v42 = 1024;
    }
    goto LABEL_181;
  }
  if ( v38 == 3 )
  {
    v39 = CMarkup::Doc((CMarkup *)a1);
    v41 = CMarkup::IsPendingRoot(v82);
    v42 = 0x8000;
LABEL_181:
    CDoc::OnPageActionBlocked(v39, v42, v41, 0);
  }
LABEL_71:
  ReleaseInterface(v85);
  ReleaseInterface((struct IUnknown *)ppURI);
  if ( pwzURI )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)pwzURI, v43);
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x1803e51b0  mov     [rsp-8+arg_0], rbx
0x1803e51b5  mov     [rsp-8+arg_10], r8
0x1803e51ba  push    rbp
0x1803e51bb  push    rsi
0x1803e51bc  push    rdi
0x1803e51bd  push    r12
0x1803e51bf  push    r13
0x1803e51c1  push    r14
0x1803e51c3  push    r15
0x1803e51c5  lea     rbp, [rsp-7]
0x1803e51ca  sub     rsp, 0B0h
0x1803e51d1  xor     ebx, ebx
0x1803e51d3  mov     r14d, r9d
0x1803e51d6  mov     [rbp+37h+arg_8], ebx
0x1803e51d9  mov     r13d, edx
0x1803e51dc  mov     [rbp+37h+var_70], rbx
0x1803e51e0  mov     rdi, rcx
0x1803e51e3  mov     [rbp+37h+pwzURI], rbx
0x1803e51e7  mov     [rbp+37h+ppURI], rbx
0x1803e51eb  mov     [r8], ebx
0x1803e51ee  cmp     edx, 1400h
0x1803e51f4  jnz     short loc_1803E5203
0x1803e51f6  test    byte ptr [rcx+2F4h], 8
0x1803e51fd  jnz     loc_1803E594F
0x1803e5203  mov     rax, [rcx+140h]
0x1803e520a  test    rax, rax
0x1803e520d  jz      loc_1803E556A
0x1803e5213  cmp     [rax+10h], rbx
0x1803e5217  jz      loc_1803E556A
0x1803e521d  mov     rax, [rcx]
0x1803e5220  lea     rcx, __vtguard
0x1803e5227  cmp     [rax+3D8h], rcx
0x1803e522e  jnz     loc_1803E5CB7
0x1803e5234  mov     rax, [rax+3F8h]
0x1803e523b  lea     rdx, [rbp+37h+var_70]
0x1803e523f  mov     rcx, rdi
0x1803e5242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e5247  mov     esi, eax
0x1803e5249  test    eax, eax
0x1803e524b  js      loc_1803E556F
0x1803e5251  mov     r12d, [rbp+37h+arg_40]
0x1803e5258  mov     r15d, 1
0x1803e525e  mov     eax, 100h
0x1803e5263  and     r12d, r15d
0x1803e5266  lea     edx, [rax-80h]
0x1803e5269  cmp     r13d, 1400h
0x1803e5270  jz      loc_1803E5891
0x1803e5276  cmp     r13d, 1200h
0x1803e527d  jz      loc_1803E599A
0x1803e5283  cmp     r13d, 1605h
0x1803e528a  jz      loc_1803E5993
0x1803e5290  cmp     r13d, 1C00h
0x1803e5297  jz      loc_1803E5993
0x1803e529d  test    byte ptr [rbp+37h+arg_40], 2
0x1803e52a4  jnz     short loc_1803E52C9
0x1803e52a6  test    ebx, ebx
0x1803e52a8  jz      short loc_1803E52C9
0x1803e52aa  mov     rcx, rdi; this
0x1803e52ad  call    ?GetDwnDoc@CMarkup@@QEAAPEAVCDwnDoc@@XZ; CMarkup::GetDwnDoc(void)
0x1803e52b2  test    rax, rax
0x1803e52b5  jz      loc_1803E593C
0x1803e52bb  mov     ecx, [rax+0A4h]
0x1803e52c1  test    ebx, ecx
0x1803e52c3  jnz     loc_1803E59A4
0x1803e52c9  xor     ebx, ebx
0x1803e52cb  mov     rcx, [rbp+37h+arg_28]
0x1803e52cf  test    rcx, rcx
0x1803e52d2  jz      loc_1803E58CF
0x1803e52d8  mov     [rbp+37h+ppURI], rcx
0x1803e52dc  mov     rax, [rcx]
0x1803e52df  mov     rax, [rax+8]
0x1803e52e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e52e8  cmp     cs:?g_IEHardened@@3HA, ebx; int g_IEHardened
0x1803e52ee  jnz     loc_1803E59D0
0x1803e52f4  mov     rax, [rdi+140h]
0x1803e52fb  mov     rcx, rbx
0x1803e52fe  test    rax, rax
0x1803e5301  jz      short loc_1803E5307
0x1803e5303  mov     rcx, [rax+10h]
0x1803e5307  mov     rdx, [rdi+90h]
0x1803e530e  mov     rax, rdi
0x1803e5311  mov     r12d, [rcx+15B8h]
0x1803e5318  test    rdx, rdx
0x1803e531b  mov     dword ptr [rbp+37h+var_68], r12d
0x1803e531f  cmovnz  rax, rdx
0x1803e5323  mov     eax, [rax+2ECh]
0x1803e5329  shr     eax, 1Ah
0x1803e532c  test    r15b, al
0x1803e532f  jnz     loc_1803E55B7
0x1803e5335  test    dword ptr [rdi+2ECh], 8000000h
0x1803e533f  jnz     loc_1803E5980
0x1803e5345  cmp     [rbp+37h+var_70], rbx
0x1803e5349  jz      loc_1803E556F
0x1803e534f  or      eax, 0FFFFFFFFh
0x1803e5352  mov     [rbp+37h+var_60], ebx
0x1803e5355  mov     edx, 2; dwFlags
0x1803e535a  mov     [rbp+37h+var_78], eax
0x1803e535d  mov     [rbp+37h+var_58], eax
0x1803e5360  lea     ecx, [rdx+0Ch]; FeatureEntry
0x1803e5363  call    cs:__imp_CoInternetIsFeatureEnabled
0x1803e536a  nop     dword ptr [rax+rax+00h]
0x1803e536f  mov     rcx, [rbp+37h+var_70]
0x1803e5373  lea     r8, [rbp+37h+var_78]
0x1803e5377  mov     rdx, [rbp+37h+ppURI]
0x1803e537b  xor     r9d, r9d
0x1803e537e  cmp     eax, r15d
0x1803e5381  jnz     loc_1803E570F
0x1803e5387  mov     [rsp+0E0h+var_A8], rbx
0x1803e538c  mov     [rsp+0E0h+var_B0], 40000000h
0x1803e5394  mov     [rsp+0E0h+var_B8], rbx
0x1803e5399  mov     [rsp+0E0h+var_C0], rbx
0x1803e539e  call    cs:__imp_GetZoneFromUriPrivate
0x1803e53a5  nop     dword ptr [rax+rax+00h]
0x1803e53aa  mov     esi, eax
0x1803e53ac  test    eax, eax
0x1803e53ae  jnz     loc_1803E556F
0x1803e53b4  lea     edx, [rax+2]; dwFlags
0x1803e53b7  lea     ecx, [rax+8]; FeatureEntry
0x1803e53ba  call    cs:__imp_CoInternetIsFeatureEnabled
0x1803e53c1  nop     dword ptr [rax+rax+00h]
0x1803e53c6  mov     edx, [rbp+37h+var_78]
0x1803e53c9  cmp     eax, r15d
0x1803e53cc  jnz     loc_1803E5922
0x1803e53d2  mov     rax, [rdi+140h]
0x1803e53d9  xor     esi, esi
0x1803e53db  mov     ecx, esi
0x1803e53dd  test    rax, rax
0x1803e53e0  jz      short loc_1803E53E6
0x1803e53e2  mov     rcx, [rax+10h]
0x1803e53e6  test    byte ptr [rcx+1308h], 2
0x1803e53ed  jz      loc_1803E5650
0x1803e53f3  bts     r14d, 10h
0x1803e53f8  or      eax, 0FFFFFFFFh
0x1803e53fb  mov     r12d, esi
0x1803e53fe  mov     [rbp+37h+var_5C], eax
0x1803e5401  mov     [rbp+37h+var_50], eax
0x1803e5404  test    ebx, ebx
0x1803e5406  jz      loc_1803E572A
0x1803e540c  mov     ebx, dword ptr [rbp+37h+var_68]
0x1803e540f  mov     rcx, [rbp+37h+var_70]
0x1803e5413  lea     rdx, [rbp+37h+var_54]
0x1803e5417  mov     [rsp+0E0h+var_98], rdx
0x1803e541c  lea     r9, [rbp+37h+arg_8]
0x1803e5420  mov     edx, [rbp+37h+arg_38]
0x1803e5423  mov     r8d, r13d
0x1803e5426  mov     [rsp+0E0h+var_A0], rsi
0x1803e542b  mov     dword ptr [rsp+0E0h+var_A8], r14d
0x1803e5430  mov     [rsp+0E0h+var_B0], edx
0x1803e5434  mov     rdx, [rbp+37h+arg_30]
0x1803e5438  mov     [rsp+0E0h+var_B8], rdx
0x1803e543d  mov     rdx, [rbp+37h+ppURI]
0x1803e5441  mov     [rbp+37h+var_54], esi
0x1803e5444  mov     rax, [rcx]
0x1803e5447  mov     dword ptr [rsp+0E0h+var_C0], 4
0x1803e544f  mov     rax, [rax+68h]
0x1803e5453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e5458  mov     rcx, [rdi+140h]
0x1803e545f  cmp     eax, r15d
0x1803e5462  cmovnz  esi, eax
0x1803e5465  xor     eax, eax
0x1803e5467  test    rcx, rcx
0x1803e546a  jz      short loc_1803E5470
0x1803e546c  mov     rax, [rcx+10h]
0x1803e5470  cmp     [rax+15B8h], ebx
0x1803e5476  jnz     loc_1803E5976
0x1803e547c  xor     ebx, ebx
0x1803e547e  test    esi, esi
0x1803e5480  jnz     loc_1803E556F
0x1803e5486  mov     rcx, [rbp+37h+arg_20]
0x1803e548a  mov     eax, [rbp+37h+arg_8]
0x1803e548d  test    rcx, rcx
0x1803e5490  jnz     loc_1803E598C
0x1803e5496  mov     ecx, ebx
0x1803e5498  cmp     r13d, 1C00h
0x1803e549f  jz      loc_1803E5932
0x1803e54a5  test    al, 0Fh
0x1803e54a7  setz    cl
0x1803e54aa  mov     r14, [rbp+37h+arg_10]
0x1803e54ae  mov     r8, rbx
0x1803e54b1  mov     [r14], ecx
0x1803e54b4  mov     r9, [rdi+140h]
0x1803e54bb  test    r9, r9
0x1803e54be  jz      short loc_1803E54C4
0x1803e54c0  mov     r8, [r9+10h]
0x1803e54c4  test    byte ptr [r8+1308h], 2
0x1803e54cc  jz      loc_1803E58F4
0x1803e54d2  test    r12d, r12d
0x1803e54d5  jz      loc_1803E557A
0x1803e54db  test    byte ptr [rbp+37h+var_54], r15b
0x1803e54df  jz      loc_1803E557A
0x1803e54e5  mov     ecx, [rbp+37h+var_50]
0x1803e54e8  test    eax, eax
0x1803e54ea  jnz     short loc_1803E54F4
0x1803e54ec  test    ecx, ecx
0x1803e54ee  jz      loc_1803E557A
0x1803e54f4  cmp     eax, 3
0x1803e54f7  jnz     short loc_1803E54FD
0x1803e54f9  cmp     ecx, eax
0x1803e54fb  jz      short loc_1803E557A
0x1803e54fd  cmp     r13d, 1C00h
0x1803e5504  jnz     short loc_1803E550E
0x1803e5506  test    eax, eax
0x1803e5508  jnz     short loc_1803E550E
0x1803e550a  test    ecx, ecx
0x1803e550c  jz      short loc_1803E557A
0x1803e550e  mov     ecx, [rbp+37h+var_5C]
0x1803e5511  test    eax, eax
0x1803e5513  jnz     short loc_1803E551C
0x1803e5515  test    ecx, ecx
0x1803e5517  jz      short loc_1803E551C
0x1803e5519  mov     [r14], ebx
0x1803e551c  cmp     ecx, r15d
0x1803e551f  jnz     loc_1803E5CAC
0x1803e5525  mov     eax, [rbp+37h+var_78]
0x1803e5528  test    eax, eax
0x1803e552a  jz      loc_1803E5C6C
0x1803e5530  sub     eax, r15d
0x1803e5533  jz      loc_1803E5C55
0x1803e5539  sub     eax, r15d
0x1803e553c  jz      loc_1803E5C3E
0x1803e5542  sub     eax, r15d
0x1803e5545  jz      loc_1803E5C27
0x1803e554b  cmp     eax, r15d
0x1803e554e  jnz     short loc_1803E557A
0x1803e5550  mov     rcx, rdi; this
0x1803e5553  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x1803e5558  mov     rbx, rax
0x1803e555b  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x1803e5560  mov     edx, 4000h
0x1803e5565  jmp     loc_1803E5C98
0x1803e556a  mov     esi, 80004005h
0x1803e556f  mov     r14, [rbp+37h+arg_10]
0x1803e5573  mov     dword ptr [r14], 0
0x1803e557a  mov     rcx, [rbp+37h+var_70]; struct IUnknown *
0x1803e557e  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e5583  mov     rcx, [rbp+37h+ppURI]; struct IUnknown *
0x1803e5587  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e558c  mov     rax, [rbp+37h+pwzURI]
0x1803e5590  test    rax, rax
0x1803e5593  jnz     loc_1803E5CC2
0x1803e5599  mov     rbx, [rsp+0E0h+arg_0]
0x1803e55a1  mov     eax, esi
0x1803e55a3  add     rsp, 0B0h
0x1803e55aa  pop     r15
0x1803e55ac  pop     r14
0x1803e55ae  pop     r13
0x1803e55b0  pop     r12
0x1803e55b2  pop     rdi
0x1803e55b3  pop     rsi
0x1803e55b4  pop     rbp
0x1803e55b5  retn
0x1803e55b7  test    dword ptr [rdi+2ECh], 8000000h
0x1803e55c1  jnz     loc_1803E5980
0x1803e55c7  test    rdx, rdx
0x1803e55ca  mov     rcx, rdi
0x1803e55cd  cmovnz  rcx, rdx; this
0x1803e55d1  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x1803e55d6  test    rax, rax
0x1803e55d9  jz      loc_1803E5345
0x1803e55df  mov     r8, [rax+78h]
0x1803e55e3  test    byte ptr [r8+0E0h], 40h
0x1803e55eb  jnz     loc_1803E596C
0x1803e55f1  test    byte ptr [rax+0A8h], 2
0x1803e55f8  jnz     loc_1803E5AE4
0x1803e55fe  mov     rcx, rdi; this
0x1803e5601  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x1803e5606  test    [rax+12FCh], r15b
0x1803e560d  jz      loc_1803E5345
0x1803e5613  mov     rcx, r8; this
0x1803e5616  call    ?GetFrameSite@CWindow@@QEAAPEAVCFrameSite@@XZ; CWindow::GetFrameSite(void)
0x1803e561b  mov     rcx, rax; struct CElement *
0x1803e561e  mov     rbx, rax
0x1803e5621  call    ?GetFrameContentData@@YAPEAUIFrameContentData@@PEAVCElement@@@Z; GetFrameContentData(CElement *)
0x1803e5626  mov     rdx, rax
0x1803e5629  test    rbx, rbx
0x1803e562c  jz      loc_1803E5AED
0x1803e5632  mov     rcx, [rax]
0x1803e5635  mov     rax, [rcx+10h]
0x1803e5639  mov     rcx, rdx
0x1803e563c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e5641  xor     ebx, ebx
0x1803e5643  test    al, al
0x1803e5645  jz      loc_1803E5345
0x1803e564b  jmp     loc_1803E5AED
0x1803e5650  test    edx, edx
0x1803e5652  jnz     loc_1803E53F8
0x1803e5658  mov     edx, 2; dwFlags
0x1803e565d  lea     ecx, [rdx+6]; FeatureEntry
0x1803e5660  call    cs:__imp_CoInternetIsFeatureEnabled
0x1803e5667  nop     dword ptr [rax+rax+00h]
0x1803e566c  cmp     eax, r15d
0x1803e566f  jz      loc_1803E53F8
0x1803e5675  and     r14d, 0FFFFFFFBh
0x1803e5679  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r15d; CMPTLGS g_cmptlgs
0x1803e5680  jnz     loc_1803E5AF6
0x1803e5686  mov     rcx, [rbp+37h+var_70]
0x1803e568a  lea     r8, [rbp+37h+var_60]
0x1803e568e  mov     [rsp+0E0h+var_98], r8
0x1803e5693  lea     r9, [rbp+37h+var_58]
0x1803e5697  mov     [rsp+0E0h+var_A0], rsi
  ... truncated ...
```

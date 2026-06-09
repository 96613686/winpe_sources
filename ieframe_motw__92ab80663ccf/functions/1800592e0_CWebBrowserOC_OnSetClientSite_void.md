# CWebBrowserOC::_OnSetClientSite(void)

- ea: `0x1800592e0`
- end: `0x18005991c`
- name: `?_OnSetClientSite@CWebBrowserOC@@MEAAXXZ`
- size: `1596`
- prototype: `void __fastcall(CWebBrowserOC *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180007010`
- `0x18001546c`
- `0x180015b60`
- `0x1800178b0`
- `0x1800188f4`
- `0x180027cbc`
- `0x1800592e0`
- `0x18007e39c`
- `0x18009a1b4`
- `0x18017c7c4`
- `0x18017c9b4`
- `0x180180a30`
- `0x1801817a0`
- `0x180181880`
- `0x180181d00`
- `0x180425cdc`
- `0x180594010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180059683`
- `msvcrt!memcpy_s` at `0x1800597ba`
- `msvcrt!memcpy_s` at `0x180059683`
- `msvcrt!memcpy_s` at `0x1800597ba`
- `USER32!DestroyWindow` at `0x180059581`
- `USER32!DestroyWindow` at `0x180059581`
- `USER32!GetParent` at `0x180059814`
- `USER32!GetParent` at `0x180059814`
- `USER32!GetWindowThreadProcessId` at `0x18005982e`
- `USER32!GetWindowThreadProcessId` at `0x180059841`
- `USER32!GetWindowThreadProcessId` at `0x18005982e`
- `USER32!GetWindowThreadProcessId` at `0x180059841`
- `OLEAUT32!__imp_VariantClear` at `0x180059693`
- `OLEAUT32!__imp_VariantClear` at `0x1800596a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800597ca`
- `OLEAUT32!__imp_VariantClear` at `0x1800597da`
- `OLEAUT32!__imp_VariantClear` at `0x180059693`
- `OLEAUT32!__imp_VariantClear` at `0x1800596a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800597ca`
- `OLEAUT32!__imp_VariantClear` at `0x1800597da`
- `OLEAUT32!__imp_VariantChangeType` at `0x180059663`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005979a`
- `OLEAUT32!__imp_VariantChangeType` at `0x180059663`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005979a`
- `SHELL32!__imp_ILFree` at `0x1800598ec`
- `SHELL32!__imp_ILFree` at `0x1800598ec`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRegisterMessageFilter` at `0x18005942f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRegisterMessageFilter` at `0x180059883`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRegisterMessageFilter` at `0x18005942f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRegisterMessageFilter` at `0x180059883`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18005932e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18005932e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHDeleteValueW` at `0x180059502`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHDeleteValueW` at `0x18005951f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHDeleteValueW` at `0x180059502`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHDeleteValueW` at `0x18005951f`
- `WININET!InternetSetOptionW` at `0x1800594c6`
- `WININET!InternetSetOptionW` at `0x1800594de`
- `WININET!InternetSetOptionW` at `0x1800594c6`
- `WININET!InternetSetOptionW` at `0x1800594de`

## string_xrefs

- `0x1800594fb`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180059518`: `Software\Microsoft\Internet Explorer\LowRegistry`

## pseudocode

```c
void __fastcall CWebBrowserOC::_OnSetClientSite(CWebBrowserOC *this)
{
  IUnknown *v2; // rcx
  _DWORD *v3; // rbx
  CWebBrowserSB *v4; // rax
  CWebBrowserSB *v5; // rax
  __int64 v6; // rcx
  LPMESSAGEFILTER *v7; // rsi
  int v8; // ebx
  volatile signed __int32 *GlobalCounterMemoryAddress; // rax
  signed __int32 v10; // ecx
  int (__fastcall ***v11)(_QWORD, GUID *, void **); // rcx
  HWND v12; // rcx
  void (__fastcall ***v13)(_QWORD, GUID *, char *); // rcx
  __int64 v14; // rax
  __int64 *v15; // rbx
  __int64 v16; // rcx
  HRESULT v17; // esi
  void (__fastcall ***v18)(_QWORD, GUID *, char *); // rcx
  __int64 v19; // rcx
  HRESULT v20; // ebx
  HWND v21; // rcx
  HWND Parent; // rsi
  DWORD WindowThreadProcessId; // ebx
  CMsgFilter **v24; // rbx
  CMsgFilter *v25; // rax
  CMsgFilter *v26; // rax
  __int64 v27; // rcx
  int v28; // [rsp+20h] [rbp-49h]
  VARIANTARG pvargDest; // [rsp+50h] [rbp-19h] BYREF
  VARIANTARG pvarSrc; // [rsp+68h] [rbp-1h] BYREF
  __int128 v31; // [rsp+80h] [rbp+17h] BYREF
  __int64 v32; // [rsp+90h] [rbp+27h]
  void *ppvOut; // [rsp+D0h] [rbp+67h] BYREF
  LPITEMIDLIST pidl; // [rsp+D8h] [rbp+6Fh] BYREF

  v2 = (IUnknown *)*((_QWORD *)this + 13);
  ppvOut = 0;
  if ( v2 )
  {
    v3 = (_DWORD *)((char *)this + 648);
    if ( IUnknown_QueryService(
           v2,
           (const GUID *const)&SID_STopLevelBrowser,
           &GUID_02ba3b52_0547_11d1_b833_00c04fc9b31f,
           &ppvOut) < 0 )
      *v3 |= 0x20u;
    else
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    if ( !*((_QWORD *)this + 87) )
    {
      v4 = (CWebBrowserSB *)operator new(0x1898u);
      if ( !v4 )
      {
        *((_QWORD *)this + 87) = 0;
        return;
      }
      v5 = CWebBrowserSB::CWebBrowserSB(v4, (struct IUnknown *)this + 8, this);
      *((_QWORD *)this + 87) = v5;
      if ( !v5 )
        return;
      v6 = *(_QWORD *)((char *)this + 684);
      *((_BYTE *)this + 812) = 0;
      *((_QWORD *)v5 + 235) = v6;
      if ( (*(_BYTE *)v3 & 0x20) != 0 )
        CWebBrowserSB::v_SetTopBrowser(*((CWebBrowserSB **)this + 87));
      CBaseBrowser2::_UIActivateView(*((CBaseBrowser2 **)this + 87), 0);
    }
  }
  else
  {
    if ( (***((int (__fastcall ****)(_QWORD, GUID *, void **))this + 78))(
           *((_QWORD *)this + 78),
           &GUID_401062ac_2f9c_426e_91a2_4af5bead509f,
           &ppvOut) >= 0 )
    {
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 24LL))(ppvOut, 0);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
    v7 = (LPMESSAGEFILTER *)*((_QWORD *)this + 100);
    if ( v7 )
    {
      *((_QWORD *)this + 100) = 0;
      CoRegisterMessageFilter(v7[2], 0);
      ATL::CComPtr<IPrivacIEDatabase>::Release(v7 + 2);
      ((void (__fastcall *)(LPMESSAGEFILTER *))(*v7)[2].lpVtbl)(v7);
    }
    if ( (*((_DWORD *)this + 162) & 0x4000) != 0 )
    {
      v8 = 0;
      GlobalCounterMemoryAddress = (volatile signed __int32 *)GetGlobalCounterMemoryAddress(4);
      if ( GlobalCounterMemoryAddress )
        v10 = _InterlockedDecrement(GlobalCounterMemoryAddress);
      else
        v10 = _InterlockedIncrement(&g_cUniqueCounterValue);
      if ( !v10 )
      {
        v8 = 1;
        Dialmon_SendMessage(0x467u);
      }
      if ( (unsigned int)GetBrowserProcess() == 1 && !(unsigned int)IEGlobalCounterDecrement(5) || v8 )
      {
        InternetSetOptionW(0, 0x2Au, 0, 0);
        InternetSetOptionW(0, 0x3Cu, 0, 0);
        SHDeleteValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
          L"AddToFavoritesInitialSelection");
        SHDeleteValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
          L"AddToFeedsInitialSelection");
      }
      *((_DWORD *)this + 162) &= ~0x4000u;
    }
  }
  v11 = (int (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 13);
  if ( v11 )
  {
    ppvOut = 0;
    if ( (**v11)(v11, &GUID_00000119_0000_0000_c000_000000000046, &ppvOut) >= 0 )
    {
      CShellEmbedding::_CreateWindowOrSetParent(this, (struct IOleWindow *)ppvOut);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
  }
  else
  {
    v12 = (HWND)*((_QWORD *)this + 12);
    if ( v12 )
    {
      DestroyWindow(v12);
      *((_QWORD *)this + 12) = 0;
    }
  }
  v13 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 13);
  if ( v13 )
  {
    v14 = *((_QWORD *)this + 20);
    LOWORD(ppvOut) = 0;
    v15 = (__int64 *)((char *)this + 400);
    if ( *(GUID **)(v14 + 8) != &CLSID_WebBrowser_V1 )
    {
      if ( !*v15 )
        (**v13)(v13, &GUID_00020400_0000_0000_c000_000000000046, (char *)this + 400);
      v16 = *v15;
      if ( *v15 )
      {
        v32 = 0;
        v31 = 0;
        memset(&pvarSrc, 0, sizeof(pvarSrc));
        if ( (*(int (__fastcall **)(__int64, __int64, GUID *, _QWORD, __int16, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v16 + 48LL))(
               v16,
               4294961795LL,
               &GUID_NULL,
               0,
               2,
               &v31,
               &pvarSrc,
               0,
               0) >= 0 )
        {
          memset(&pvargDest, 0, sizeof(pvargDest));
          v17 = VariantChangeType(&pvargDest, &pvarSrc, 0, 0xBu);
          if ( v17 >= 0 )
          {
            memcpy_s(&ppvOut, 2u, &pvargDest.decVal.8, 2u);
            VariantClear(&pvargDest);
          }
          VariantClear(&pvarSrc);
          if ( v17 >= 0 )
            CWebBrowserOC::put_Offline((CWebBrowserOC *)((char *)this + 544), (__int16)ppvOut);
        }
      }
    }
    if ( (*((_BYTE *)this + 648) & 0x20) != 0 && !(_WORD)ppvOut )
    {
      SetQueryNetSessionCount(3);
      *((_DWORD *)this + 162) |= 0x4000u;
    }
    if ( *(GUID **)(*((_QWORD *)this + 20) + 8LL) != &CLSID_WebBrowser_V1 )
    {
      if ( !*v15 )
      {
        v18 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 13);
        if ( v18 )
          (**v18)(v18, &GUID_00020400_0000_0000_c000_000000000046, (char *)this + 400);
      }
      v19 = *v15;
      if ( *v15 )
      {
        v32 = 0;
        v31 = 0;
        LOWORD(v28) = 2;
        memset(&pvargDest, 0, sizeof(pvargDest));
        if ( (*(int (__fastcall **)(__int64, __int64, GUID *, _QWORD, int, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v19 + 48LL))(
               v19,
               4294961794LL,
               &GUID_NULL,
               0,
               v28,
               &v31,
               &pvargDest,
               0,
               0) >= 0 )
        {
          memset(&pvarSrc, 0, sizeof(pvarSrc));
          v20 = VariantChangeType(&pvarSrc, &pvargDest, 0, 0xBu);
          if ( v20 >= 0 )
          {
            memcpy_s(&ppvOut, 2u, &pvarSrc.decVal.8, 2u);
            VariantClear(&pvarSrc);
          }
          VariantClear(&pvargDest);
          if ( v20 >= 0 )
            CWebBrowserOC::put_Silent((CWebBrowserOC *)((char *)this + 544), (__int16)ppvOut);
        }
      }
    }
    if ( (*((_BYTE *)this + 648) & 0x20) != 0 )
    {
      v21 = (HWND)*((_QWORD *)this + 12);
      if ( v21 )
      {
        Parent = GetParent(v21);
        if ( Parent )
        {
          WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)this + 12), 0);
          if ( WindowThreadProcessId != GetWindowThreadProcessId(Parent, 0) )
          {
            v24 = (CMsgFilter **)((char *)this + 800);
            if ( !*((_QWORD *)this + 100) )
            {
              v25 = (CMsgFilter *)operator new(0x18u);
              if ( v25 )
              {
                v26 = CMsgFilter::CMsgFilter(v25);
                *v24 = v26;
                if ( v26 && CoRegisterMessageFilter((LPMESSAGEFILTER)v26, (LPMESSAGEFILTER *)v26 + 2) == 1 )
                  ATL::CComPtr<IPrivacIEDatabase>::Release((char *)this + 800);
              }
              else
              {
                *v24 = 0;
              }
            }
          }
        }
      }
    }
    if ( (*((_BYTE *)this + 648) & 4) != 0 )
    {
      v27 = *((_QWORD *)this + 89);
      if ( v27 )
      {
        if ( *((_QWORD *)this + 87) )
        {
          pidl = 0;
          if ( (*(int (__fastcall **)(__int64, LPITEMIDLIST *))(*(_QWORD *)v27 + 32LL))(v27, &pidl) >= 0 )
          {
            if ( pidl )
            {
              CWebBrowserOC::_BrowseObject(this, (const struct _ITEMIDLIST_ABSOLUTE *)pidl);
              ILFree(pidl);
            }
          }
          *((_DWORD *)this + 162) &= ~4u;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800592e0  mov     [rsp-8+arg_10], rbx
0x1800592e5  mov     [rsp-8+arg_18], rsi
0x1800592ea  push    rbp
0x1800592eb  push    rdi
0x1800592ec  push    r13
0x1800592ee  push    r14
0x1800592f0  push    r15
0x1800592f2  lea     rbp, [rsp-37h]
0x1800592f7  sub     rsp, 0A0h
0x1800592fe  xor     r14d, r14d
0x180059301  mov     rdi, rcx
0x180059304  mov     rcx, [rcx+68h]; punk
0x180059308  mov     [rbp+57h+ppvOut], r14
0x18005930c  test    rcx, rcx
0x18005930f  jz      loc_1800593D3
0x180059315  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x180059319  lea     r8, _GUID_02ba3b52_0547_11d1_b833_00c04fc9b31f; riid
0x180059320  lea     rdx, SID_STopLevelBrowser; guidService
0x180059327  lea     rbx, [rdi+288h]
0x18005932e  call    cs:__imp_IUnknown_QueryService
0x180059335  nop     dword ptr [rax+rax+00h]
0x18005933a  test    eax, eax
0x18005933c  js      short loc_180059350
0x18005933e  mov     rcx, [rbp+57h+ppvOut]
0x180059342  mov     rax, [rcx]
0x180059345  mov     rax, [rax+10h]
0x180059349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005934e  jmp     short loc_180059353
0x180059350  or      dword ptr [rbx], 20h
0x180059353  cmp     [rdi+2B8h], r14
0x18005935a  jnz     loc_180059533
0x180059360  mov     ecx, 1898h; dwBytes
0x180059365  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005936a  test    rax, rax
0x18005936d  jz      short loc_1800593C7
0x18005936f  lea     rdx, [rdi+40h]; struct IUnknown *
0x180059373  mov     r8, rdi; struct CWebBrowserOC *
0x180059376  mov     rcx, rax; this
0x180059379  call    ??0CWebBrowserSB@@QEAA@PEAUIUnknown@@PEAVCWebBrowserOC@@@Z; CWebBrowserSB::CWebBrowserSB(IUnknown *,CWebBrowserOC *)
0x18005937e  mov     [rdi+2B8h], rax
0x180059385  test    rax, rax
0x180059388  jz      loc_1800598FF
0x18005938e  mov     rcx, [rdi+2ACh]
0x180059395  mov     [rdi+32Ch], r14b
0x18005939c  mov     [rax+758h], rcx
0x1800593a3  test    byte ptr [rbx], 20h
0x1800593a6  jz      short loc_1800593B4
0x1800593a8  mov     rcx, [rdi+2B8h]; this
0x1800593af  call    ?v_SetTopBrowser@CWebBrowserSB@@MEAAJXZ; CWebBrowserSB::v_SetTopBrowser(void)
0x1800593b4  mov     rcx, [rdi+2B8h]; this
0x1800593bb  xor     edx, edx; unsigned int
0x1800593bd  call    ?_UIActivateView@CBaseBrowser2@@IEAAJI@Z; CBaseBrowser2::_UIActivateView(uint)
0x1800593c2  jmp     loc_180059533
0x1800593c7  mov     [rdi+2B8h], r14
0x1800593ce  jmp     loc_1800598FF
0x1800593d3  mov     rcx, [rdi+270h]
0x1800593da  lea     r8, [rbp+57h+ppvOut]
0x1800593de  lea     rdx, _GUID_401062ac_2f9c_426e_91a2_4af5bead509f
0x1800593e5  mov     rax, [rcx]
0x1800593e8  mov     rax, [rax]
0x1800593eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800593f0  test    eax, eax
0x1800593f2  js      short loc_180059416
0x1800593f4  mov     rcx, [rbp+57h+ppvOut]
0x1800593f8  xor     edx, edx
0x1800593fa  mov     rax, [rcx]
0x1800593fd  mov     rax, [rax+18h]
0x180059401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059406  mov     rcx, [rbp+57h+ppvOut]
0x18005940a  mov     rax, [rcx]
0x18005940d  mov     rax, [rax+10h]
0x180059411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059416  mov     rsi, [rdi+320h]
0x18005941d  test    rsi, rsi
0x180059420  jz      short loc_180059453
0x180059422  mov     [rdi+320h], r14
0x180059429  xor     edx, edx; lplpMessageFilter
0x18005942b  mov     rcx, [rsi+10h]; lpMessageFilter
0x18005942f  call    cs:__imp_CoRegisterMessageFilter
0x180059436  nop     dword ptr [rax+rax+00h]
0x18005943b  lea     rcx, [rsi+10h]
0x18005943f  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x180059444  mov     rax, [rsi]
0x180059447  mov     rcx, rsi
0x18005944a  mov     rax, [rax+10h]
0x18005944e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059453  test    dword ptr [rdi+288h], 4000h
0x18005945d  jz      loc_180059533
0x180059463  mov     ecx, 4
0x180059468  mov     ebx, r14d
0x18005946b  call    ?GetGlobalCounterMemoryAddress@@YAPEAJW4IEGLOBALCOUNTER@@@Z; GetGlobalCounterMemoryAddress(IEGLOBALCOUNTER)
0x180059470  test    rax, rax
0x180059473  jz      short loc_180059480
0x180059475  or      ecx, 0FFFFFFFFh
0x180059478  lock xadd [rax], ecx
0x18005947c  dec     ecx
0x18005947e  jmp     short loc_18005948F
0x180059480  mov     ecx, 1
0x180059485  lock xadd cs:?g_cUniqueCounterValue@@3JA, ecx; long g_cUniqueCounterValue
0x18005948d  inc     ecx
0x18005948f  test    ecx, ecx
0x180059491  jnz     short loc_1800594A0
0x180059493  lea     ebx, [rcx+1]
0x180059496  mov     ecx, 467h; Msg
0x18005949b  call    ?Dialmon_SendMessage@@YAXI@Z; Dialmon_SendMessage(uint)
0x1800594a0  call    GetBrowserProcess
0x1800594a5  cmp     eax, 1
0x1800594a8  jnz     short loc_1800594B6
0x1800594aa  lea     ecx, [rax+4]
0x1800594ad  call    IEGlobalCounterDecrement
0x1800594b2  test    eax, eax
0x1800594b4  jz      short loc_1800594BA
0x1800594b6  test    ebx, ebx
0x1800594b8  jz      short loc_18005952B
0x1800594ba  xor     r9d, r9d; dwBufferLength
0x1800594bd  xor     r8d, r8d; lpBuffer
0x1800594c0  xor     ecx, ecx; hInternet
0x1800594c2  lea     edx, [r9+2Ah]; dwOption
0x1800594c6  call    cs:__imp_InternetSetOptionW
0x1800594cd  nop     dword ptr [rax+rax+00h]
0x1800594d2  xor     r9d, r9d; dwBufferLength
0x1800594d5  xor     r8d, r8d; lpBuffer
0x1800594d8  xor     ecx, ecx; hInternet
0x1800594da  lea     edx, [r9+3Ch]; dwOption
0x1800594de  call    cs:__imp_InternetSetOptionW
0x1800594e5  nop     dword ptr [rax+rax+00h]
0x1800594ea  mov     rbx, 0FFFFFFFF80000001h
0x1800594f1  lea     r8, pszValue; "AddToFavoritesInitialSelection"
0x1800594f8  mov     rcx, rbx; hkey
0x1800594fb  lea     rdx, pszSubKey; "Software\\Microsoft\\Internet Explorer"...
0x180059502  call    cs:__imp_SHDeleteValueW
0x180059509  nop     dword ptr [rax+rax+00h]
0x18005950e  lea     r8, aAddtofeedsinit; "AddToFeedsInitialSelection"
0x180059515  mov     rcx, rbx; hkey
0x180059518  lea     rdx, pszSubKey; "Software\\Microsoft\\Internet Explorer"...
0x18005951f  call    cs:__imp_SHDeleteValueW
0x180059526  nop     dword ptr [rax+rax+00h]
0x18005952b  btr     dword ptr [rdi+288h], 0Eh
0x180059533  mov     rcx, [rdi+68h]
0x180059537  test    rcx, rcx
0x18005953a  jz      short loc_180059578
0x18005953c  mov     [rbp+57h+ppvOut], r14
0x180059540  lea     r8, [rbp+57h+ppvOut]
0x180059544  mov     rax, [rcx]
0x180059547  lea     rdx, _GUID_00000119_0000_0000_c000_000000000046
0x18005954e  mov     rax, [rax]
0x180059551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059556  test    eax, eax
0x180059558  js      short loc_180059591
0x18005955a  mov     rdx, [rbp+57h+ppvOut]; struct IOleWindow *
0x18005955e  mov     rcx, rdi; this
0x180059561  call    ?_CreateWindowOrSetParent@CShellEmbedding@@IEAAJPEAUIOleWindow@@@Z; CShellEmbedding::_CreateWindowOrSetParent(IOleWindow *)
0x180059566  mov     rcx, [rbp+57h+ppvOut]
0x18005956a  mov     rax, [rcx]
0x18005956d  mov     rax, [rax+10h]
0x180059571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059576  jmp     short loc_180059591
0x180059578  mov     rcx, [rdi+60h]; hWnd
0x18005957c  test    rcx, rcx
0x18005957f  jz      short loc_180059591
0x180059581  call    cs:__imp_DestroyWindow
0x180059588  nop     dword ptr [rax+rax+00h]
0x18005958d  mov     [rdi+60h], r14
0x180059591  mov     rcx, [rdi+68h]
0x180059595  test    rcx, rcx
0x180059598  jz      loc_1800598FF
0x18005959e  mov     rax, [rdi+0A0h]
0x1800595a5  lea     r13, CLSID_WebBrowser_V1
0x1800595ac  mov     word ptr [rbp+57h+ppvOut], r14w
0x1800595b1  lea     rbx, [rdi+190h]
0x1800595b8  mov     r15d, 2
0x1800595be  cmp     [rax+8], r13
0x1800595c2  jz      loc_1800596C3
0x1800595c8  cmp     [rbx], r14
0x1800595cb  jnz     short loc_1800595E2
0x1800595cd  mov     rax, [rcx]
0x1800595d0  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x1800595d7  mov     r8, rbx
0x1800595da  mov     rax, [rax]
0x1800595dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595e2  mov     rcx, [rbx]
0x1800595e5  test    rcx, rcx
0x1800595e8  jz      loc_1800596C3
0x1800595ee  xor     eax, eax
0x1800595f0  mov     [rsp+0C0h+var_80], r14
0x1800595f5  mov     [rbp+57h+var_30], rax
0x1800595f9  lea     rdx, [rbp+57h+pvarSrc]
0x1800595fd  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x180059601  lea     r8, GUID_NULL
0x180059608  mov     [rsp+0C0h+var_88], r14
0x18005960d  xorps   xmm0, xmm0
0x180059610  mov     [rsp+0C0h+var_90], rdx
0x180059615  xorps   xmm1, xmm1
0x180059618  lea     rdx, [rbp+57h+var_40]
0x18005961c  xor     r9d, r9d
0x18005961f  mov     [rsp+0C0h+var_98], rdx
0x180059624  mov     edx, 0FFFFEA83h
0x180059629  movups  [rbp+57h+var_40], xmm0
0x18005962d  mov     [rsp+0C0h+var_A0], r15w
0x180059633  movups  xmmword ptr [rbp+57h+pvarSrc], xmm1
0x180059637  mov     rax, [rcx]
0x18005963a  mov     rax, [rax+30h]
0x18005963e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059643  test    eax, eax
0x180059645  js      short loc_1800596C3
0x180059647  xor     eax, eax
0x180059649  lea     rdx, [rbp+57h+pvarSrc]; pvarSrc
0x18005964d  xorps   xmm0, xmm0
0x180059650  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x180059654  xor     r8d, r8d; wFlags
0x180059657  lea     rcx, [rbp+57h+pvargDest]; pvargDest
0x18005965b  movups  xmmword ptr [rbp+57h+pvargDest], xmm0
0x18005965f  lea     r9d, [rax+0Bh]; vt
0x180059663  call    cs:__imp_VariantChangeType
0x18005966a  nop     dword ptr [rax+rax+00h]
0x18005966f  mov     esi, eax
0x180059671  test    eax, eax
0x180059673  js      short loc_18005969F
0x180059675  mov     r9, r15; SourceSize
0x180059678  lea     r8, [rbp+57h+pvargDest+8]; Source
0x18005967c  mov     rdx, r15; DestinationSize
0x18005967f  lea     rcx, [rbp+57h+ppvOut]; Destination
0x180059683  call    cs:__imp_memcpy_s
0x18005968a  nop     dword ptr [rax+rax+00h]
0x18005968f  lea     rcx, [rbp+57h+pvargDest]; pvarg
0x180059693  call    cs:__imp_VariantClear
0x18005969a  nop     dword ptr [rax+rax+00h]
0x18005969f  lea     rcx, [rbp+57h+pvarSrc]; pvarg
0x1800596a3  call    cs:__imp_VariantClear
0x1800596aa  nop     dword ptr [rax+rax+00h]
0x1800596af  test    esi, esi
0x1800596b1  js      short loc_1800596C3
0x1800596b3  movzx   edx, word ptr [rbp+57h+ppvOut]; __int16
0x1800596b7  lea     rcx, [rdi+220h]; this
0x1800596be  call    ?put_Offline@CWebBrowserOC@@UEAAJF@Z; CWebBrowserOC::put_Offline(short)
0x1800596c3  test    byte ptr [rdi+288h], 20h
0x1800596ca  jz      short loc_1800596E5
0x1800596cc  cmp     word ptr [rbp+57h+ppvOut], r14w
0x1800596d1  jnz     short loc_1800596E5
0x1800596d3  mov     ecx, 3
0x1800596d8  call    ?SetQueryNetSessionCount@@YAJW4SessionOp@@@Z; SetQueryNetSessionCount(SessionOp)
0x1800596dd  bts     dword ptr [rdi+288h], 0Eh
0x1800596e5  mov     rax, [rdi+0A0h]
0x1800596ec  cmp     [rax+8], r13
0x1800596f0  jz      loc_1800597FA
0x1800596f6  cmp     [rbx], r14
0x1800596f9  jnz     short loc_180059719
0x1800596fb  mov     rcx, [rdi+68h]
0x1800596ff  test    rcx, rcx
0x180059702  jz      short loc_180059719
0x180059704  mov     rax, [rcx]
0x180059707  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x18005970e  mov     r8, rbx
0x180059711  mov     rax, [rax]
0x180059714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059719  mov     rcx, [rbx]
0x18005971c  test    rcx, rcx
0x18005971f  jz      loc_1800597FA
0x180059725  xor     eax, eax
0x180059727  mov     [rsp+0C0h+var_80], r14
0x18005972c  mov     [rbp+57h+var_30], rax
0x180059730  lea     rdx, [rbp+57h+pvargDest]
0x180059734  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x180059738  lea     r8, GUID_NULL
0x18005973f  mov     [rsp+0C0h+var_88], r14
0x180059744  xorps   xmm0, xmm0
0x180059747  mov     [rsp+0C0h+var_90], rdx
0x18005974c  xorps   xmm1, xmm1
0x18005974f  lea     rdx, [rbp+57h+var_40]
0x180059753  xor     r9d, r9d
0x180059756  mov     [rsp+0C0h+var_98], rdx
0x18005975b  mov     edx, 0FFFFEA82h
0x180059760  movups  [rbp+57h+var_40], xmm0
0x180059764  mov     [rsp+0C0h+var_A0], r15w
0x18005976a  movups  xmmword ptr [rbp+57h+pvargDest], xmm1
0x18005976e  mov     rax, [rcx]
0x180059771  mov     rax, [rax+30h]
0x180059775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005977a  test    eax, eax
0x18005977c  js      short loc_1800597FA
0x18005977e  xor     eax, eax
0x180059780  lea     rdx, [rbp+57h+pvargDest]; pvarSrc
0x180059784  xorps   xmm0, xmm0
0x180059787  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x18005978b  xor     r8d, r8d; wFlags
0x18005978e  lea     rcx, [rbp+57h+pvarSrc]; pvargDest
0x180059792  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x180059796  lea     r9d, [rax+0Bh]; vt
0x18005979a  call    cs:__imp_VariantChangeType
0x1800597a1  nop     dword ptr [rax+rax+00h]
0x1800597a6  mov     ebx, eax
0x1800597a8  test    eax, eax
0x1800597aa  js      short loc_1800597D6
0x1800597ac  mov     r9, r15; SourceSize
0x1800597af  lea     r8, [rbp+57h+pvarSrc+8]; Source
0x1800597b3  mov     rdx, r15; DestinationSize
0x1800597b6  lea     rcx, [rbp+57h+ppvOut]; Destination
0x1800597ba  call    cs:__imp_memcpy_s
0x1800597c1  nop     dword ptr [rax+rax+00h]
0x1800597c6  lea     rcx, [rbp+57h+pvarSrc]; pvarg
  ... truncated ...
```

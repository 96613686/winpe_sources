# CWebBrowserOC::_OnSetClientSite(void)

- ea: `0x180055940`
- end: `0x180055efb`
- name: `?_OnSetClientSite@CWebBrowserOC@@MEAAXXZ`
- size: `1467`
- prototype: `void __fastcall(CWebBrowserOC *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180012140`
- `0x180012a90`
- `0x180014660`
- `0x1800154e4`
- `0x180025c0c`
- `0x18002acc0`
- `0x180055940`
- `0x180078670`
- `0x180092ff4`
- `0x18016b094`
- `0x18016b284`
- `0x18016f230`
- `0x18016ff80`
- `0x180170060`
- `0x1801704e0`
- `0x1803f003c`
- `0x180550010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180055cb3`
- `msvcrt!memcpy_s` at `0x180055dd2`
- `msvcrt!memcpy_s` at `0x180055cb3`
- `msvcrt!memcpy_s` at `0x180055dd2`
- `USER32!DestroyWindow` at `0x180055bbd`
- `USER32!DestroyWindow` at `0x180055bbd`
- `USER32!GetParent` at `0x180055e12`
- `USER32!GetParent` at `0x180055e12`
- `USER32!GetWindowThreadProcessId` at `0x180055e26`
- `USER32!GetWindowThreadProcessId` at `0x180055e33`
- `USER32!GetWindowThreadProcessId` at `0x180055e26`
- `USER32!GetWindowThreadProcessId` at `0x180055e33`
- `OLEAUT32!__imp_VariantClear` at `0x180055cbd`
- `OLEAUT32!__imp_VariantClear` at `0x180055cc7`
- `OLEAUT32!__imp_VariantClear` at `0x180055ddc`
- `OLEAUT32!__imp_VariantClear` at `0x180055de6`
- `OLEAUT32!__imp_VariantClear` at `0x180055cbd`
- `OLEAUT32!__imp_VariantClear` at `0x180055cc7`
- `OLEAUT32!__imp_VariantClear` at `0x180055ddc`
- `OLEAUT32!__imp_VariantClear` at `0x180055de6`
- `OLEAUT32!__imp_VariantChangeType` at `0x180055c99`
- `OLEAUT32!__imp_VariantChangeType` at `0x180055db8`
- `OLEAUT32!__imp_VariantChangeType` at `0x180055c99`
- `OLEAUT32!__imp_VariantChangeType` at `0x180055db8`
- `SHELL32!__imp_ILFree` at `0x180055ed2`
- `SHELL32!__imp_ILFree` at `0x180055ed2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRegisterMessageFilter` at `0x180055a89`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRegisterMessageFilter` at `0x180055e6f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRegisterMessageFilter` at `0x180055a89`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRegisterMessageFilter` at `0x180055e6f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18005598e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18005598e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHDeleteValueW` at `0x180055b4a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHDeleteValueW` at `0x180055b61`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHDeleteValueW` at `0x180055b4a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHDeleteValueW` at `0x180055b61`
- `WININET!InternetSetOptionW` at `0x180055b1a`
- `WININET!InternetSetOptionW` at `0x180055b2c`
- `WININET!InternetSetOptionW` at `0x180055b1a`
- `WININET!InternetSetOptionW` at `0x180055b2c`

## string_xrefs

- `0x180055b43`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180055b5a`: `Software\Microsoft\Internet Explorer\LowRegistry`

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
0x180055940  mov     [rsp-8+arg_10], rbx
0x180055945  mov     [rsp-8+arg_18], rsi
0x18005594a  push    rbp
0x18005594b  push    rdi
0x18005594c  push    r13
0x18005594e  push    r14
0x180055950  push    r15
0x180055952  lea     rbp, [rsp-37h]
0x180055957  sub     rsp, 0A0h
0x18005595e  xor     r14d, r14d
0x180055961  mov     rdi, rcx
0x180055964  mov     rcx, [rcx+68h]; punk
0x180055968  mov     [rbp+57h+ppvOut], r14
0x18005596c  test    rcx, rcx
0x18005596f  jz      loc_180055A2D
0x180055975  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x180055979  lea     r8, _GUID_02ba3b52_0547_11d1_b833_00c04fc9b31f; riid
0x180055980  lea     rdx, SID_STopLevelBrowser; guidService
0x180055987  lea     rbx, [rdi+288h]
0x18005598e  call    cs:__imp_IUnknown_QueryService
0x180055994  test    eax, eax
0x180055996  js      short loc_1800559AA
0x180055998  mov     rcx, [rbp+57h+ppvOut]
0x18005599c  mov     rax, [rcx]
0x18005599f  mov     rax, [rax+10h]
0x1800559a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800559a8  jmp     short loc_1800559AD
0x1800559aa  or      dword ptr [rbx], 20h
0x1800559ad  cmp     [rdi+2B8h], r14
0x1800559b4  jnz     loc_180055B6F
0x1800559ba  mov     ecx, 1898h; dwBytes
0x1800559bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800559c4  test    rax, rax
0x1800559c7  jz      short loc_180055A21
0x1800559c9  lea     rdx, [rdi+40h]; struct IUnknown *
0x1800559cd  mov     r8, rdi; struct CWebBrowserOC *
0x1800559d0  mov     rcx, rax; this
0x1800559d3  call    ??0CWebBrowserSB@@QEAA@PEAUIUnknown@@PEAVCWebBrowserOC@@@Z; CWebBrowserSB::CWebBrowserSB(IUnknown *,CWebBrowserOC *)
0x1800559d8  mov     [rdi+2B8h], rax
0x1800559df  test    rax, rax
0x1800559e2  jz      loc_180055EDF
0x1800559e8  mov     rcx, [rdi+2ACh]
0x1800559ef  mov     [rdi+32Ch], r14b
0x1800559f6  mov     [rax+758h], rcx
0x1800559fd  test    byte ptr [rbx], 20h
0x180055a00  jz      short loc_180055A0E
0x180055a02  mov     rcx, [rdi+2B8h]; this
0x180055a09  call    ?v_SetTopBrowser@CWebBrowserSB@@MEAAJXZ; CWebBrowserSB::v_SetTopBrowser(void)
0x180055a0e  mov     rcx, [rdi+2B8h]; this
0x180055a15  xor     edx, edx; unsigned int
0x180055a17  call    ?_UIActivateView@CBaseBrowser2@@IEAAJI@Z; CBaseBrowser2::_UIActivateView(uint)
0x180055a1c  jmp     loc_180055B6F
0x180055a21  mov     [rdi+2B8h], r14
0x180055a28  jmp     loc_180055EDF
0x180055a2d  mov     rcx, [rdi+270h]
0x180055a34  lea     r8, [rbp+57h+ppvOut]
0x180055a38  lea     rdx, _GUID_401062ac_2f9c_426e_91a2_4af5bead509f
0x180055a3f  mov     rax, [rcx]
0x180055a42  mov     rax, [rax]
0x180055a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a4a  test    eax, eax
0x180055a4c  js      short loc_180055A70
0x180055a4e  mov     rcx, [rbp+57h+ppvOut]
0x180055a52  xor     edx, edx
0x180055a54  mov     rax, [rcx]
0x180055a57  mov     rax, [rax+18h]
0x180055a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a60  mov     rcx, [rbp+57h+ppvOut]
0x180055a64  mov     rax, [rcx]
0x180055a67  mov     rax, [rax+10h]
0x180055a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a70  mov     rsi, [rdi+320h]
0x180055a77  test    rsi, rsi
0x180055a7a  jz      short loc_180055AA7
0x180055a7c  mov     [rdi+320h], r14
0x180055a83  xor     edx, edx; lplpMessageFilter
0x180055a85  mov     rcx, [rsi+10h]; lpMessageFilter
0x180055a89  call    cs:__imp_CoRegisterMessageFilter
0x180055a8f  lea     rcx, [rsi+10h]
0x180055a93  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x180055a98  mov     rax, [rsi]
0x180055a9b  mov     rcx, rsi
0x180055a9e  mov     rax, [rax+10h]
0x180055aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055aa7  test    dword ptr [rdi+288h], 4000h
0x180055ab1  jz      loc_180055B6F
0x180055ab7  mov     ecx, 4
0x180055abc  mov     ebx, r14d
0x180055abf  call    ?GetGlobalCounterMemoryAddress@@YAPEAJW4IEGLOBALCOUNTER@@@Z; GetGlobalCounterMemoryAddress(IEGLOBALCOUNTER)
0x180055ac4  test    rax, rax
0x180055ac7  jz      short loc_180055AD4
0x180055ac9  or      ecx, 0FFFFFFFFh
0x180055acc  lock xadd [rax], ecx
0x180055ad0  dec     ecx
0x180055ad2  jmp     short loc_180055AE3
0x180055ad4  mov     ecx, 1
0x180055ad9  lock xadd cs:?g_cUniqueCounterValue@@3JA, ecx; long g_cUniqueCounterValue
0x180055ae1  inc     ecx
0x180055ae3  test    ecx, ecx
0x180055ae5  jnz     short loc_180055AF4
0x180055ae7  lea     ebx, [rcx+1]
0x180055aea  mov     ecx, 467h; Msg
0x180055aef  call    ?Dialmon_SendMessage@@YAXI@Z; Dialmon_SendMessage(uint)
0x180055af4  call    GetBrowserProcess
0x180055af9  cmp     eax, 1
0x180055afc  jnz     short loc_180055B0A
0x180055afe  lea     ecx, [rax+4]
0x180055b01  call    IEGlobalCounterDecrement
0x180055b06  test    eax, eax
0x180055b08  jz      short loc_180055B0E
0x180055b0a  test    ebx, ebx
0x180055b0c  jz      short loc_180055B67
0x180055b0e  xor     r9d, r9d; dwBufferLength
0x180055b11  xor     r8d, r8d; lpBuffer
0x180055b14  xor     ecx, ecx; hInternet
0x180055b16  lea     edx, [r9+2Ah]; dwOption
0x180055b1a  call    cs:__imp_InternetSetOptionW
0x180055b20  xor     r9d, r9d; dwBufferLength
0x180055b23  xor     r8d, r8d; lpBuffer
0x180055b26  xor     ecx, ecx; hInternet
0x180055b28  lea     edx, [r9+3Ch]; dwOption
0x180055b2c  call    cs:__imp_InternetSetOptionW
0x180055b32  mov     rbx, 0FFFFFFFF80000001h
0x180055b39  lea     r8, pszValue; "AddToFavoritesInitialSelection"
0x180055b40  mov     rcx, rbx; hkey
0x180055b43  lea     rdx, pszSubKey; "Software\\Microsoft\\Internet Explorer"...
0x180055b4a  call    cs:__imp_SHDeleteValueW
0x180055b50  lea     r8, aAddtofeedsinit; "AddToFeedsInitialSelection"
0x180055b57  mov     rcx, rbx; hkey
0x180055b5a  lea     rdx, pszSubKey; "Software\\Microsoft\\Internet Explorer"...
0x180055b61  call    cs:__imp_SHDeleteValueW
0x180055b67  btr     dword ptr [rdi+288h], 0Eh
0x180055b6f  mov     rcx, [rdi+68h]
0x180055b73  test    rcx, rcx
0x180055b76  jz      short loc_180055BB4
0x180055b78  mov     [rbp+57h+ppvOut], r14
0x180055b7c  lea     r8, [rbp+57h+ppvOut]
0x180055b80  mov     rax, [rcx]
0x180055b83  lea     rdx, _GUID_00000119_0000_0000_c000_000000000046
0x180055b8a  mov     rax, [rax]
0x180055b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b92  test    eax, eax
0x180055b94  js      short loc_180055BC7
0x180055b96  mov     rdx, [rbp+57h+ppvOut]; struct IOleWindow *
0x180055b9a  mov     rcx, rdi; this
0x180055b9d  call    ?_CreateWindowOrSetParent@CShellEmbedding@@IEAAJPEAUIOleWindow@@@Z; CShellEmbedding::_CreateWindowOrSetParent(IOleWindow *)
0x180055ba2  mov     rcx, [rbp+57h+ppvOut]
0x180055ba6  mov     rax, [rcx]
0x180055ba9  mov     rax, [rax+10h]
0x180055bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055bb2  jmp     short loc_180055BC7
0x180055bb4  mov     rcx, [rdi+60h]; hWnd
0x180055bb8  test    rcx, rcx
0x180055bbb  jz      short loc_180055BC7
0x180055bbd  call    cs:__imp_DestroyWindow
0x180055bc3  mov     [rdi+60h], r14
0x180055bc7  mov     rcx, [rdi+68h]
0x180055bcb  test    rcx, rcx
0x180055bce  jz      loc_180055EDF
0x180055bd4  mov     rax, [rdi+0A0h]
0x180055bdb  lea     r13, CLSID_WebBrowser_V1
0x180055be2  mov     word ptr [rbp+57h+ppvOut], r14w
0x180055be7  lea     rbx, [rdi+190h]
0x180055bee  mov     r15d, 2
0x180055bf4  cmp     [rax+8], r13
0x180055bf8  jz      loc_180055CE1
0x180055bfe  cmp     [rbx], r14
0x180055c01  jnz     short loc_180055C18
0x180055c03  mov     rax, [rcx]
0x180055c06  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x180055c0d  mov     r8, rbx
0x180055c10  mov     rax, [rax]
0x180055c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c18  mov     rcx, [rbx]
0x180055c1b  test    rcx, rcx
0x180055c1e  jz      loc_180055CE1
0x180055c24  xor     eax, eax
0x180055c26  mov     [rsp+0C0h+var_80], r14
0x180055c2b  mov     [rbp+57h+var_30], rax
0x180055c2f  lea     rdx, [rbp+57h+pvarSrc]
0x180055c33  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x180055c37  lea     r8, GUID_NULL
0x180055c3e  mov     [rsp+0C0h+var_88], r14
0x180055c43  xorps   xmm0, xmm0
0x180055c46  mov     [rsp+0C0h+var_90], rdx
0x180055c4b  xorps   xmm1, xmm1
0x180055c4e  lea     rdx, [rbp+57h+var_40]
0x180055c52  xor     r9d, r9d
0x180055c55  mov     [rsp+0C0h+var_98], rdx
0x180055c5a  mov     edx, 0FFFFEA83h
0x180055c5f  movups  [rbp+57h+var_40], xmm0
0x180055c63  mov     [rsp+0C0h+var_A0], r15w
0x180055c69  movups  xmmword ptr [rbp+57h+pvarSrc], xmm1
0x180055c6d  mov     rax, [rcx]
0x180055c70  mov     rax, [rax+30h]
0x180055c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c79  test    eax, eax
0x180055c7b  js      short loc_180055CE1
0x180055c7d  xor     eax, eax
0x180055c7f  lea     rdx, [rbp+57h+pvarSrc]; pvarSrc
0x180055c83  xorps   xmm0, xmm0
0x180055c86  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x180055c8a  xor     r8d, r8d; wFlags
0x180055c8d  lea     rcx, [rbp+57h+pvargDest]; pvargDest
0x180055c91  movups  xmmword ptr [rbp+57h+pvargDest], xmm0
0x180055c95  lea     r9d, [rax+0Bh]; vt
0x180055c99  call    cs:__imp_VariantChangeType
0x180055c9f  mov     esi, eax
0x180055ca1  test    eax, eax
0x180055ca3  js      short loc_180055CC3
0x180055ca5  mov     r9, r15; SourceSize
0x180055ca8  lea     r8, [rbp+57h+pvargDest+8]; Source
0x180055cac  mov     rdx, r15; DestinationSize
0x180055caf  lea     rcx, [rbp+57h+ppvOut]; Destination
0x180055cb3  call    cs:__imp_memcpy_s
0x180055cb9  lea     rcx, [rbp+57h+pvargDest]; pvarg
0x180055cbd  call    cs:__imp_VariantClear
0x180055cc3  lea     rcx, [rbp+57h+pvarSrc]; pvarg
0x180055cc7  call    cs:__imp_VariantClear
0x180055ccd  test    esi, esi
0x180055ccf  js      short loc_180055CE1
0x180055cd1  movzx   edx, word ptr [rbp+57h+ppvOut]; __int16
0x180055cd5  lea     rcx, [rdi+220h]; this
0x180055cdc  call    ?put_Offline@CWebBrowserOC@@UEAAJF@Z; CWebBrowserOC::put_Offline(short)
0x180055ce1  test    byte ptr [rdi+288h], 20h
0x180055ce8  jz      short loc_180055D03
0x180055cea  cmp     word ptr [rbp+57h+ppvOut], r14w
0x180055cef  jnz     short loc_180055D03
0x180055cf1  mov     ecx, 3
0x180055cf6  call    ?SetQueryNetSessionCount@@YAJW4SessionOp@@@Z; SetQueryNetSessionCount(SessionOp)
0x180055cfb  bts     dword ptr [rdi+288h], 0Eh
0x180055d03  mov     rax, [rdi+0A0h]
0x180055d0a  cmp     [rax+8], r13
0x180055d0e  jz      loc_180055E00
0x180055d14  cmp     [rbx], r14
0x180055d17  jnz     short loc_180055D37
0x180055d19  mov     rcx, [rdi+68h]
0x180055d1d  test    rcx, rcx
0x180055d20  jz      short loc_180055D37
0x180055d22  mov     rax, [rcx]
0x180055d25  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x180055d2c  mov     r8, rbx
0x180055d2f  mov     rax, [rax]
0x180055d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d37  mov     rcx, [rbx]
0x180055d3a  test    rcx, rcx
0x180055d3d  jz      loc_180055E00
0x180055d43  xor     eax, eax
0x180055d45  mov     [rsp+0C0h+var_80], r14
0x180055d4a  mov     [rbp+57h+var_30], rax
0x180055d4e  lea     rdx, [rbp+57h+pvargDest]
0x180055d52  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x180055d56  lea     r8, GUID_NULL
0x180055d5d  mov     [rsp+0C0h+var_88], r14
0x180055d62  xorps   xmm0, xmm0
0x180055d65  mov     [rsp+0C0h+var_90], rdx
0x180055d6a  xorps   xmm1, xmm1
0x180055d6d  lea     rdx, [rbp+57h+var_40]
0x180055d71  xor     r9d, r9d
0x180055d74  mov     [rsp+0C0h+var_98], rdx
0x180055d79  mov     edx, 0FFFFEA82h
0x180055d7e  movups  [rbp+57h+var_40], xmm0
0x180055d82  mov     [rsp+0C0h+var_A0], r15w
0x180055d88  movups  xmmword ptr [rbp+57h+pvargDest], xmm1
0x180055d8c  mov     rax, [rcx]
0x180055d8f  mov     rax, [rax+30h]
0x180055d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d98  test    eax, eax
0x180055d9a  js      short loc_180055E00
0x180055d9c  xor     eax, eax
0x180055d9e  lea     rdx, [rbp+57h+pvargDest]; pvarSrc
0x180055da2  xorps   xmm0, xmm0
0x180055da5  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x180055da9  xor     r8d, r8d; wFlags
0x180055dac  lea     rcx, [rbp+57h+pvarSrc]; pvargDest
0x180055db0  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x180055db4  lea     r9d, [rax+0Bh]; vt
0x180055db8  call    cs:__imp_VariantChangeType
0x180055dbe  mov     ebx, eax
0x180055dc0  test    eax, eax
0x180055dc2  js      short loc_180055DE2
0x180055dc4  mov     r9, r15; SourceSize
0x180055dc7  lea     r8, [rbp+57h+pvarSrc+8]; Source
0x180055dcb  mov     rdx, r15; DestinationSize
0x180055dce  lea     rcx, [rbp+57h+ppvOut]; Destination
0x180055dd2  call    cs:__imp_memcpy_s
0x180055dd8  lea     rcx, [rbp+57h+pvarSrc]; pvarg
0x180055ddc  call    cs:__imp_VariantClear
0x180055de2  lea     rcx, [rbp+57h+pvargDest]; pvarg
0x180055de6  call    cs:__imp_VariantClear
0x180055dec  test    ebx, ebx
0x180055dee  js      short loc_180055E00
0x180055df0  movzx   edx, word ptr [rbp+57h+ppvOut]; __int16
0x180055df4  lea     rcx, [rdi+220h]; this
0x180055dfb  call    ?put_Silent@CWebBrowserOC@@UEAAJF@Z; CWebBrowserOC::put_Silent(short)
0x180055e00  test    byte ptr [rdi+288h], 20h
0x180055e07  jz      short loc_180055E87
0x180055e09  mov     rcx, [rdi+60h]; hWnd
0x180055e0d  test    rcx, rcx
0x180055e10  jz      short loc_180055E87
  ... truncated ...
```

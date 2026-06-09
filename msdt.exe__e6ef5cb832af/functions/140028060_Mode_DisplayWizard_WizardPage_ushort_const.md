# Mode::DisplayWizard(WizardPage *,ushort const *)

- ea: `0x140028060`
- end: `0x140028406`
- name: `?DisplayWizard@Mode@@MEAAJPEAVWizardPage@@PEBG@Z`
- size: `934`
- prototype: `__int64 __fastcall(Mode *this, struct WizardPage *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400039b1`
- `0x140008540`
- `0x140009230`
- `0x140009370`
- `0x1400094d0`
- `0x14000a724`
- `0x14001c380`
- `0x140020420`
- `0x140020d58`
- `0x140028060`
- `0x140041a90`
- `0x14004a1d0`
- `0x140061c90`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400280cd`
- `KERNEL32!HeapAlloc` at `0x1400280cd`
- `KERNEL32!HeapFree` at `0x1400283d4`
- `KERNEL32!HeapFree` at `0x1400283d4`
- `KERNEL32!GetProcessHeap` at `0x1400280b6`
- `KERNEL32!GetProcessHeap` at `0x1400283c0`
- `KERNEL32!GetProcessHeap` at `0x1400280b6`
- `KERNEL32!GetProcessHeap` at `0x1400283c0`
- `KERNEL32!LoadLibraryW` at `0x1400281a9`
- `KERNEL32!LoadLibraryW` at `0x1400281a9`
- `USER32!IsWindow` at `0x1400282b2`
- `USER32!IsWindow` at `0x1400282b2`
- `COMCTL32!PropertySheetW` at `0x14002838e`
- `COMCTL32!PropertySheetW` at `0x14002838e`
- `ole32!OleInitialize` at `0x1400281d6`
- `ole32!OleInitialize` at `0x1400281d6`
- `DUI70!??BTaskPage@DirectUI@@QEAAPEAU_PSP@@XZ` at `0x140028294`
- `DUI70!??BTaskPage@DirectUI@@QEAAPEAU_PSP@@XZ` at `0x140028294`
- `DUI70!?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z` at `0x140028270`
- `DUI70!?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z` at `0x140028270`
- `DUI70!InitProcessPriv` at `0x140028153`
- `DUI70!InitProcessPriv` at `0x140028153`
- `DUI70!InitThread` at `0x14002817d`
- `DUI70!InitThread` at `0x14002817d`

## string_xrefs

- `0x14002819e`: `MSFTEDIT.DLL`

## pseudocode

```c
__int64 __fastcall Mode::DisplayWizard(Mode *this, struct WizardPage *a2, const unsigned __int16 *a3)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // r15
  int v9; // ebx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  int inited; // eax
  int v14; // r9d
  int v15; // eax
  HRESULT v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  BOOL v22; // eax
  Configuration *v23; // rcx
  const unsigned __int16 *v24; // rax
  __int64 v25; // r8
  HANDLE v26; // rax
  int v28; // [rsp+20h] [rbp-79h]
  HICON v29; // [rsp+30h] [rbp-69h] BYREF
  __int64 v30; // [rsp+38h] [rbp-61h] BYREF
  int v31[4]; // [rsp+40h] [rbp-59h] BYREF
  PROPSHEETHEADERW_V2 v32; // [rsp+50h] [rbp-49h] BYREF
  struct PageManager *v33[2]; // [rsp+B0h] [rbp+17h] BYREF

  memset_0(&v32, 0, sizeof(v32));
  v30 = 0;
  v33[0] = 0;
  v29 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x98u);
  v8 = v7;
  if ( v7 )
  {
    v10 = DwzStrTruncate(v7, 0x4Cu, a3, v31);
    v9 = v10;
    if ( v10 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Mode::DisplayWizard", 313, v10);
LABEL_37:
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v8);
      return (unsigned int)v9;
    }
    LOBYTE(v12) = 1;
    LOBYTE(v11) = 1;
    inited = InitProcessPriv(14, 0x140000000uLL, v11, v12, 1);
    v9 = inited;
    if ( inited >= 0 )
    {
      *((_DWORD *)this + 3) = 1;
      v15 = InitThread(2);
      v9 = v15;
      if ( v15 >= 0 )
      {
        *((_DWORD *)this + 2) = 1;
        CCRichEdit::hRichEdit = LoadLibraryW(L"MSFTEDIT.DLL");
        if ( CCRichEdit::hRichEdit )
        {
          v9 = DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>::Register();
          if ( v9 >= 0 )
          {
            v16 = OleInitialize(0);
            v9 = v16;
            if ( v16 >= 0 )
            {
              v17 = DirectUI::ClassInfo<WebBrowser,DirectUI::HWNDHost,DirectUI::StandardCreator<WebBrowser>>::Register();
              v9 = v17;
              if ( v17 >= 0 )
              {
                v18 = DirectUI::ClassInfo<MsdtListView,DirectUI::HWNDElement,DirectUI::StandardCreator<MsdtListView>>::Register();
                v9 = v18;
                if ( v18 >= 0 )
                {
                  v19 = DirectUI::ClassInfo<MsdtEdit,DirectUI::Edit,DirectUI::StandardCreator<MsdtEdit>>::Register();
                  v9 = v19;
                  if ( v19 >= 0 )
                  {
                    v20 = PageManager::Create(a2, v33);
                    v9 = v20;
                    if ( v20 >= 0 )
                    {
                      v21 = DirectUI::TaskPage::DUICreatePropertySheetPage(a2, g_hInstance);
                      v9 = v21;
                      if ( v21 >= 0 )
                      {
                        v30 = DirectUI::TaskPage::operator _PSP *(a2);
                        v22 = IsWindow(*((HWND *)Config + 34));
                        v23 = Config;
                        if ( !v22 )
                          *((_QWORD *)Config + 34) = 0;
                        v32.hInstance = g_hInstance;
                        v32.dwSize = 96;
                        v32.hwndParent = (HWND)*((_QWORD *)v23 + 34);
                        v32.dwFlags = 16640;
                        if ( Packages_Icon() )
                        {
                          v24 = Packages_Icon();
                          v9 = DwzLoadIcon(v24, &v29);
                          if ( v9 >= 0 )
                          {
                            v32.dwFlags |= 2u;
                            v32.hIcon = v29;
                          }
                        }
                        if ( !Packages_Icon() || v9 < 0 )
                        {
                          v9 = 0;
                          v32.hIcon = (HICON)107;
                          v32.dwFlags |= 4u;
                        }
                        v32.ppsp = (LPCPROPSHEETPAGEW)&v30;
                        v32.pfnCallback = (PFNPROPSHEETCALLBACK)PropSheetProc;
                        v32.nStartPage = 0;
                        v32.nPages = 1;
                        v32.pszCaption = v8;
                        if ( (Microsoft_Windows_Diagnosis_MSDEEnableBits & 1) != 0 )
                          McGenEventWrite_EventWriteTransfer(
                            &MSDT_PROVIDER_GUID_Context,
                            MSDT_APP_INIT_STOP,
                            v25,
                            1,
                            v33);
                        PropertySheetW(&v32);
                        goto LABEL_37;
                      }
                      v28 = v21;
                      v14 = 354;
                    }
                    else
                    {
                      v28 = v20;
                      v14 = 351;
                    }
                  }
                  else
                  {
                    v28 = v19;
                    v14 = 345;
                  }
                }
                else
                {
                  v28 = v18;
                  v14 = 342;
                }
              }
              else
              {
                v28 = v17;
                v14 = 339;
              }
            }
            else
            {
              v28 = v16;
              v14 = 336;
            }
            goto LABEL_36;
          }
        }
        else
        {
          v9 = -2147467259;
        }
        v28 = v9;
        v14 = 330;
      }
      else
      {
        v28 = v15;
        v14 = 323;
      }
    }
    else
    {
      v28 = inited;
      v14 = 319;
    }
LABEL_36:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Mode::DisplayWizard", v14, v28);
    goto LABEL_37;
  }
  v9 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Mode::DisplayWizard", 307, -2147024882);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140028060  mov     [rsp-8+arg_18], rbx
0x140028065  push    rbp
0x140028066  push    rsi
0x140028067  push    rdi
0x140028068  push    r14
0x14002806a  push    r15
0x14002806c  lea     rbp, [rsp-37h]
0x140028071  sub     rsp, 0D0h
0x140028078  mov     rax, cs:__security_cookie
0x14002807f  xor     rax, rsp
0x140028082  mov     [rbp+57h+var_30], rax
0x140028086  mov     rsi, rdx
0x140028089  mov     rbx, r8
0x14002808c  xor     edx, edx; Val
0x14002808e  mov     r14, rcx
0x140028091  lea     rcx, [rbp+57h+var_A0]; void *
0x140028095  lea     r8d, [rdx+60h]; Size
0x140028099  call    memset_0
0x14002809e  mov     [rbp+57h+var_B8], 0
0x1400280a6  mov     [rbp+57h+var_40], 0
0x1400280ae  mov     [rbp+57h+var_C0], 0
0x1400280b6  call    cs:__imp_GetProcessHeap
0x1400280bd  nop     dword ptr [rax+rax+00h]
0x1400280c2  xor     edx, edx; dwFlags
0x1400280c4  mov     r8d, 98h; dwBytes
0x1400280ca  mov     rcx, rax; hHeap
0x1400280cd  call    cs:__imp_HeapAlloc
0x1400280d4  nop     dword ptr [rax+rax+00h]
0x1400280d9  mov     r15, rax
0x1400280dc  test    rax, rax
0x1400280df  jnz     short loc_14002810B
0x1400280e1  mov     ebx, 8007000Eh
0x1400280e6  lea     r8, aModeDisplaywiz; "Mode::DisplayWizard"
0x1400280ed  mov     r9d, 133h
0x1400280f3  mov     [rsp+0F0h+var_D0], ebx
0x1400280f7  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400280fe  lea     ecx, [rax+1]; Level
0x140028101  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140028106  jmp     loc_1400283E0
0x14002810b  lea     r9, [rbp+57h+var_B0]; int *
0x14002810f  mov     r8, rbx; unsigned __int16 *
0x140028112  mov     edx, 4Ch ; 'L'; unsigned __int64
0x140028117  mov     rcx, r15; unsigned __int16 *
0x14002811a  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x14002811f  mov     ebx, eax
0x140028121  test    eax, eax
0x140028123  jns     short loc_140028139
0x140028125  mov     [rsp+0F0h+var_D0], eax
0x140028129  mov     r9d, 139h
0x14002812f  mov     ecx, 1
0x140028134  jmp     loc_1400283AD
0x140028139  mov     edi, 1
0x14002813e  lea     rdx, cs:140000000h
0x140028145  mov     r9b, dil
0x140028148  mov     byte ptr [rsp+0F0h+var_D0], dil
0x14002814d  mov     r8b, dil
0x140028150  lea     ecx, [rdi+0Dh]
0x140028153  call    cs:__imp_InitProcessPriv
0x14002815a  nop     dword ptr [rax+rax+00h]
0x14002815f  mov     ebx, eax
0x140028161  test    eax, eax
0x140028163  jns     short loc_140028174
0x140028165  mov     [rsp+0F0h+var_D0], eax
0x140028169  mov     r9d, 13Fh
0x14002816f  jmp     loc_1400283AB
0x140028174  mov     ecx, 2
0x140028179  mov     [r14+0Ch], edi
0x14002817d  call    cs:__imp_InitThread
0x140028184  nop     dword ptr [rax+rax+00h]
0x140028189  mov     ebx, eax
0x14002818b  test    eax, eax
0x14002818d  jns     short loc_14002819E
0x14002818f  mov     [rsp+0F0h+var_D0], eax
0x140028193  mov     r9d, 143h
0x140028199  jmp     loc_1400283AB
0x14002819e  lea     rcx, LibFileName; "MSFTEDIT.DLL"
0x1400281a5  mov     [r14+8], edi
0x1400281a9  call    cs:__imp_LoadLibraryW
0x1400281b0  nop     dword ptr [rax+rax+00h]
0x1400281b5  mov     cs:?hRichEdit@CCRichEdit@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CCRichEdit::hRichEdit
0x1400281bc  test    rax, rax
0x1400281bf  jz      loc_14002839C
0x1400281c5  call    ?Register@?$ClassInfo@VCCRichEdit@@VCCBase@DirectUI@@V?$StandardCreator@VCCRichEdit@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x1400281ca  mov     ebx, eax
0x1400281cc  test    eax, eax
0x1400281ce  js      loc_1400283A1
0x1400281d4  xor     ecx, ecx; pvReserved
0x1400281d6  call    cs:__imp_OleInitialize
0x1400281dd  nop     dword ptr [rax+rax+00h]
0x1400281e2  mov     ebx, eax
0x1400281e4  test    eax, eax
0x1400281e6  jns     short loc_1400281F7
0x1400281e8  mov     [rsp+0F0h+var_D0], eax
0x1400281ec  mov     r9d, 150h
0x1400281f2  jmp     loc_1400283AB
0x1400281f7  call    ?Register@?$ClassInfo@VWebBrowser@@VHWNDHost@DirectUI@@V?$StandardCreator@VWebBrowser@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<WebBrowser,DirectUI::HWNDHost,DirectUI::StandardCreator<WebBrowser>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x1400281fc  mov     ebx, eax
0x1400281fe  test    eax, eax
0x140028200  jns     short loc_140028211
0x140028202  mov     [rsp+0F0h+var_D0], eax
0x140028206  mov     r9d, 153h
0x14002820c  jmp     loc_1400283AB
0x140028211  call    ?Register@?$ClassInfo@VMsdtListView@@VHWNDElement@DirectUI@@V?$StandardCreator@VMsdtListView@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<MsdtListView,DirectUI::HWNDElement,DirectUI::StandardCreator<MsdtListView>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x140028216  mov     ebx, eax
0x140028218  test    eax, eax
0x14002821a  jns     short loc_14002822B
0x14002821c  mov     [rsp+0F0h+var_D0], eax
0x140028220  mov     r9d, 156h
0x140028226  jmp     loc_1400283AB
0x14002822b  call    ?Register@?$ClassInfo@VMsdtEdit@@VEdit@DirectUI@@V?$StandardCreator@VMsdtEdit@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<MsdtEdit,DirectUI::Edit,DirectUI::StandardCreator<MsdtEdit>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x140028230  mov     ebx, eax
0x140028232  test    eax, eax
0x140028234  jns     short loc_140028245
0x140028236  mov     [rsp+0F0h+var_D0], eax
0x14002823a  mov     r9d, 159h
0x140028240  jmp     loc_1400283AB
0x140028245  lea     rdx, [rbp+57h+var_40]; struct PageManager **
0x140028249  mov     rcx, rsi; struct WizardPage *
0x14002824c  call    ?Create@PageManager@@SAJPEAVWizardPage@@PEAPEAV1@@Z; PageManager::Create(WizardPage *,PageManager * *)
0x140028251  mov     ebx, eax
0x140028253  test    eax, eax
0x140028255  jns     short loc_140028266
0x140028257  mov     [rsp+0F0h+var_D0], eax
0x14002825b  mov     r9d, 15Fh
0x140028261  jmp     loc_1400283AB
0x140028266  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x14002826d  mov     rcx, rsi
0x140028270  call    cs:__imp_?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z; DirectUI::TaskPage::DUICreatePropertySheetPage(HINSTANCE__ *)
0x140028277  nop     dword ptr [rax+rax+00h]
0x14002827c  mov     ebx, eax
0x14002827e  test    eax, eax
0x140028280  jns     short loc_140028291
0x140028282  mov     [rsp+0F0h+var_D0], eax
0x140028286  mov     r9d, 162h
0x14002828c  jmp     loc_1400283AB
0x140028291  mov     rcx, rsi
0x140028294  call    cs:__imp_??BTaskPage@DirectUI@@QEAAPEAU_PSP@@XZ; DirectUI::TaskPage::operator _PSP *(void)
0x14002829b  nop     dword ptr [rax+rax+00h]
0x1400282a0  mov     rcx, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400282a7  mov     [rbp+57h+var_B8], rax
0x1400282ab  mov     rcx, [rcx+110h]; hWnd
0x1400282b2  call    cs:__imp_IsWindow
0x1400282b9  nop     dword ptr [rax+rax+00h]
0x1400282be  mov     rcx, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400282c5  test    eax, eax
0x1400282c7  jnz     short loc_1400282D4
0x1400282c9  mov     qword ptr [rcx+110h], 0
0x1400282d4  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1400282db  mov     [rbp+57h+var_A0.hInstance], rax
0x1400282df  mov     [rbp+57h+var_A0.dwSize], 60h ; '`'
0x1400282e6  mov     rax, [rcx+110h]
0x1400282ed  mov     [rbp+57h+var_A0.hwndParent], rax
0x1400282f1  mov     [rbp+57h+var_A0.dwFlags], 4100h
0x1400282f8  call    ?Packages_Icon@@YAPEBGXZ; Packages_Icon(void)
0x1400282fd  test    rax, rax
0x140028300  jz      short loc_140028325
0x140028302  call    ?Packages_Icon@@YAPEBGXZ; Packages_Icon(void)
0x140028307  mov     rcx, rax; unsigned __int16 *
0x14002830a  lea     rdx, [rbp+57h+var_C0]; HICON *
0x14002830e  call    ?DwzLoadIcon@@YAJPEBGPEAPEAUHICON__@@@Z; DwzLoadIcon(ushort const *,HICON__ * *)
0x140028313  mov     ebx, eax
0x140028315  test    eax, eax
0x140028317  js      short loc_140028325
0x140028319  mov     rax, [rbp+57h+var_C0]
0x14002831d  or      [rbp+57h+var_A0.dwFlags], 2
0x140028321  mov     qword ptr [rbp+57h+var_A0.18h], rax
0x140028325  call    ?Packages_Icon@@YAPEBGXZ; Packages_Icon(void)
0x14002832a  test    rax, rax
0x14002832d  jz      short loc_140028333
0x14002832f  test    ebx, ebx
0x140028331  jns     short loc_140028341
0x140028333  xor     ebx, ebx
0x140028335  mov     qword ptr [rbp+57h+var_A0.18h], 6Bh ; 'k'
0x14002833d  or      [rbp+57h+var_A0.dwFlags], 4
0x140028341  test    cs:Microsoft_Windows_Diagnosis_MSDEEnableBits, dil
0x140028348  lea     rax, [rbp+57h+var_B8]
0x14002834c  mov     qword ptr [rbp+57h+var_A0.38h], rax
0x140028350  lea     rax, ?PropSheetProc@@YAHPEAUHWND__@@I_J@Z; PropSheetProc(HWND__ *,uint,__int64)
0x140028357  mov     [rbp+57h+var_A0.pfnCallback], rax
0x14002835b  mov     dword ptr [rbp+57h+var_A0.30h], 0
0x140028362  mov     [rbp+57h+var_A0.nPages], edi
0x140028365  mov     [rbp+57h+var_A0.pszCaption], r15
0x140028369  jz      short loc_14002838A
0x14002836b  lea     rax, [rbp+57h+var_40]
0x14002836f  mov     r9d, edi
0x140028372  lea     rdx, MSDT_APP_INIT_STOP
0x140028379  mov     qword ptr [rsp+0F0h+var_D0], rax
0x14002837e  lea     rcx, MSDT_PROVIDER_GUID_Context
0x140028385  call    McGenEventWrite_EventWriteTransfer
0x14002838a  lea     rcx, [rbp+57h+var_A0]; LPCPROPSHEETHEADERW
0x14002838e  call    cs:__imp_PropertySheetW
0x140028395  nop     dword ptr [rax+rax+00h]
0x14002839a  jmp     short loc_1400283C0
0x14002839c  mov     ebx, 80004005h
0x1400283a1  mov     [rsp+0F0h+var_D0], ebx
0x1400283a5  mov     r9d, 14Ah
0x1400283ab  mov     ecx, edi; Level
0x1400283ad  lea     r8, aModeDisplaywiz; "Mode::DisplayWizard"
0x1400283b4  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400283bb  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400283c0  call    cs:__imp_GetProcessHeap
0x1400283c7  nop     dword ptr [rax+rax+00h]
0x1400283cc  mov     r8, r15; lpMem
0x1400283cf  xor     edx, edx; dwFlags
0x1400283d1  mov     rcx, rax; hHeap
0x1400283d4  call    cs:__imp_HeapFree
0x1400283db  nop     dword ptr [rax+rax+00h]
0x1400283e0  mov     eax, ebx
0x1400283e2  mov     rcx, [rbp+57h+var_30]
0x1400283e6  xor     rcx, rsp; StackCookie
0x1400283e9  call    __security_check_cookie
0x1400283ee  mov     rbx, [rsp+0F0h+arg_18]
0x1400283f6  add     rsp, 0D0h
0x1400283fd  pop     r15
0x1400283ff  pop     r14
0x140028401  pop     rdi
0x140028402  pop     rsi
0x140028403  pop     rbp
0x140028404  retn
```

# PageManager::TypeToPage(_PAGETYPE,WizardPage * *)

- ea: `0x14001d480`
- end: `0x14001df9d`
- name: `?TypeToPage@PageManager@@QEAAJW4_PAGETYPE@@PEAPEAVWizardPage@@@Z`
- size: `2845`
- prototype: `__int64 __fastcall(__int64, int, ProgressPage **)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000f1a0`
- `0x14001c4f4`
- `0x14001d070`
- `0x14002a7d4`

## callees

- `0x140001d54`
- `0x1400039b1`
- `0x14000d524`
- `0x14001475c`
- `0x14001be80`
- `0x14001bf04`
- `0x14001bf38`
- `0x14001bf6c`
- `0x14001bfa0`
- `0x14001bfe0`
- `0x14001c014`
- `0x14001d480`
- `0x140020420`
- `0x140029ef8`
- `0x14002a024`
- `0x140063010`

## import_xrefs

- `USER32!SendMessageW` at `0x14001df25`
- `USER32!SendMessageW` at `0x14001df25`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14001df07`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14001df07`
- `DUI70!??BTaskPage@DirectUI@@QEAAPEAU_PSP@@XZ` at `0x14001deeb`
- `DUI70!??BTaskPage@DirectUI@@QEAAPEAU_PSP@@XZ` at `0x14001deeb`
- `DUI70!?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z` at `0x14001dece`
- `DUI70!?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z` at `0x14001dece`

## pseudocode

```c
__int64 __fastcall PageManager::TypeToPage(__int64 a1, int a2, ProgressPage **a3)
{
  __int64 v4; // rbx
  __int64 v6; // r14
  ProgressPage *v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  ProgressPage *v10; // rax
  ProgressPage *v11; // rbx
  ProgressPage *v12; // rax
  ProgressPage *v13; // rax
  ProgressPage *v14; // rax
  FinalElevationPage *v15; // rax
  FinalElevationPage *v16; // rbx
  ProgressPage *v17; // rax
  FinalLinksPage *v18; // rax
  FinalLinksPage *v19; // rbx
  IntroPage *v20; // rax
  IntroPage *v21; // rbx
  ProgressPage *v22; // rax
  ProgressPage *v23; // rax
  ProgressPage *v24; // rax
  WizardPage *v25; // rax
  ProgressPage *v26; // rax
  ProgressPage *v27; // rax
  DetailsPage *v28; // rax
  DetailsPage *v29; // rbx
  WizardPage *v30; // rax
  ProgressPage *v31; // rax
  ProgressPage *v32; // rax
  ProgressPage *v33; // rax
  WizardPage *v34; // rax
  InteractivityTextPage *v35; // rax
  ProgressPage *v36; // rax
  ProgressPage *v37; // rax
  SupportKeyPage *v38; // rax
  SupportKeyPage *v39; // rbx
  ProgressPage *v40; // rax
  InteractivityPage *v41; // rax
  InteractivityTextPage *v42; // rax
  ProgressPage *v43; // rax
  ProgressPage *v44; // rax
  ProgressPage *v45; // rax
  EditPage *v46; // rax
  int v47; // eax
  int v48; // r9d
  LPARAM v49; // rdi
  HWND ParentHWND; // rax

  v4 = a2;
  v6 = a2;
  v7 = *(ProgressPage **)(*(_QWORD *)(a1 + 16) + 8LL * a2);
  if ( v7 )
  {
    *a3 = v7;
    v8 = (*(__int64 (__fastcall **)(ProgressPage *))(*(_QWORD *)v7 + 192LL))(v7);
    v9 = v8;
    if ( v8 >= 0 )
    {
      if ( (_DWORD)v4 == 41 )
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v4) + 136LL) = *(_QWORD *)(a1 + 32);
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "PageManager::TypeToPage", 1141, v8);
    }
    return v9;
  }
  if ( a2 > 28 )
  {
    if ( a2 > 47 )
    {
      switch ( a2 )
      {
        case '0':
          v46 = (EditPage *)operator new(0xF0u);
          if ( v46 )
            v11 = EditPage::EditPage(v46);
          else
            v11 = 0;
          goto LABEL_136;
        case '1':
          v45 = (ProgressPage *)operator new(0xF0u);
          v11 = v45;
          if ( v45 )
          {
            memset_0(v45, 0, 0xF0u);
            EditPage::EditPage(v11);
            *(_QWORD *)v11 = &SmallEditPage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
        case '2':
          v44 = (ProgressPage *)operator new(0xC0u);
          v11 = v44;
          if ( v44 )
          {
            memset_0(v44, 0, 0xC0u);
            InteractivityPage::InteractivityPage(v11);
            *(_QWORD *)v11 = &ListViewPage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
        case '3':
          v43 = (ProgressPage *)operator new(0xB8u);
          v11 = v43;
          if ( v43 )
          {
            memset_0(v43, 0, 0xB8u);
            InteractivityPage::InteractivityPage(v11);
            *(_QWORD *)v11 = &EulaPage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
        case '4':
          v42 = (InteractivityTextPage *)operator new(0xC0u);
          if ( v42 )
            v11 = InteractivityTextPage::InteractivityTextPage(v42);
          else
            v11 = 0;
          goto LABEL_136;
        case '5':
          v41 = (InteractivityPage *)operator new(0xD8u);
          v11 = v41;
          if ( v41 )
          {
            InteractivityPage::InteractivityPage(v41);
            *(_QWORD *)v11 = &InteractivityUIPage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
            *((_QWORD *)v11 + 23) = 0;
            *((_QWORD *)v11 + 24) = 0;
            *((_QWORD *)v11 + 25) = 0;
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
      }
    }
    else
    {
      switch ( a2 )
      {
        case 47:
          v40 = (ProgressPage *)operator new(0xB8u);
          v11 = v40;
          if ( v40 )
          {
            memset_0(v40, 0, 0xB8u);
            InteractivityPage::InteractivityPage(v11);
            *(_QWORD *)v11 = &CheckBoxPage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
        case 29:
          v38 = (SupportKeyPage *)operator new(0x70u);
          v39 = v38;
          if ( v38 )
          {
            memset_0(v38, 0, 0x70u);
            v11 = SupportKeyPage::SupportKeyPage(v39);
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
        case 30:
          v37 = (ProgressPage *)operator new(0x70u);
          v11 = v37;
          if ( v37 )
          {
            memset_0(v37, 0, 0x70u);
            WizardPage::WizardPage(v11);
            *(_QWORD *)v11 = &RetryDownloadPage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
        case 41:
          v36 = (ProgressPage *)operator new(0xA8u);
          if ( v36 )
            v11 = ProgressPage::ProgressPage(v36, *(void **)(a1 + 32), 0, 0);
          else
            v11 = 0;
          goto LABEL_136;
        case 42:
          v35 = (InteractivityTextPage *)operator new(0xC8u);
          v11 = v35;
          if ( v35 )
          {
            InteractivityTextPage::InteractivityTextPage(v35);
            *(_QWORD *)v11 = &PausePage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
            *((_QWORD *)v11 + 24) = 0;
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
        case 44:
          v34 = (WizardPage *)operator new(0x78u);
          v11 = v34;
          if ( v34 )
          {
            WizardPage::WizardPage(v34);
            *(_QWORD *)v11 = &ConsentPage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
            *((_QWORD *)v11 + 14) = 0;
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
        case 45:
          v33 = (ProgressPage *)operator new(0xC0u);
          v11 = v33;
          if ( v33 )
          {
            memset_0(v33, 0, 0xC0u);
            InteractivityPage::InteractivityPage(v11);
            *(_QWORD *)v11 = &RadioButtonPage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
        case 46:
          v32 = (ProgressPage *)operator new(0xC0u);
          v11 = v32;
          if ( v32 )
          {
            memset_0(v32, 0, 0xC0u);
            InteractivityPage::InteractivityPage(v11);
            *(_QWORD *)v11 = &CommandLinkPage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
          }
          else
          {
            v11 = 0;
          }
          goto LABEL_136;
      }
    }
    goto LABEL_117;
  }
  if ( a2 == 28 )
  {
    v31 = (ProgressPage *)operator new(0x70u);
    v11 = v31;
    if ( v31 )
    {
      memset_0(v31, 0, 0x70u);
      WizardPage::WizardPage(v11);
      *(_QWORD *)v11 = &SaveResultsPage::`vftable'{for `DirectUI::IElementListener'};
      *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
    }
    else
    {
      v11 = 0;
    }
    goto LABEL_136;
  }
  if ( a2 > 10 )
  {
    switch ( a2 )
    {
      case 20:
        v30 = (WizardPage *)operator new(0x98u);
        v11 = v30;
        if ( v30 )
        {
          WizardPage::WizardPage(v30);
          *(_QWORD *)v11 = &CustomizePage::`vftable'{for `DirectUI::IElementListener'};
          *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
          *((_QWORD *)v11 + 14) = 0;
          *((_QWORD *)v11 + 15) = 0;
          *((_QWORD *)v11 + 16) = 0;
          *((_QWORD *)v11 + 17) = 0;
          *((_DWORD *)v11 + 36) = 0;
          *((_DWORD *)v11 + 20) = 55;
        }
        else
        {
          v11 = 0;
        }
        goto LABEL_136;
      case 22:
        v28 = (DetailsPage *)operator new(0x70u);
        v29 = v28;
        if ( v28 )
        {
          memset_0(v28, 0, 0x70u);
          v11 = DetailsPage::DetailsPage(v29);
        }
        else
        {
          v11 = 0;
        }
        goto LABEL_136;
      case 23:
        v27 = (ProgressPage *)operator new(0x70u);
        v11 = v27;
        if ( v27 )
        {
          memset_0(v27, 0, 0x70u);
          IntroPage::IntroPage(v11);
          *(_QWORD *)v11 = &PackageContentsPage::`vftable'{for `DirectUI::IElementListener'};
          *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
        }
        else
        {
          v11 = 0;
        }
        goto LABEL_136;
      case 24:
        v26 = (ProgressPage *)operator new(0x70u);
        v11 = v26;
        if ( v26 )
        {
          memset_0(v26, 0, 0x70u);
          WizardPage::WizardPage(v11);
          *(_QWORD *)v11 = &UploadCompletePage::`vftable'{for `DirectUI::IElementListener'};
          *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
        }
        else
        {
          v11 = 0;
        }
        goto LABEL_136;
      case 25:
        v25 = (WizardPage *)operator new(0x78u);
        v11 = v25;
        if ( v25 )
        {
          WizardPage::WizardPage(v25);
          *(_QWORD *)v11 = &UploadFilePage::`vftable'{for `DirectUI::IElementListener'};
          *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
          *((_DWORD *)v11 + 28) = 0;
        }
        else
        {
          v11 = 0;
        }
        goto LABEL_136;
      case 26:
        v24 = (ProgressPage *)operator new(0x70u);
        v11 = v24;
        if ( v24 )
        {
          memset_0(v24, 0, 0x70u);
          WizardPage::WizardPage(v11);
          *(_QWORD *)v11 = &UploadConsentPage::`vftable'{for `DirectUI::IElementListener'};
          *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
        }
        else
        {
          v11 = 0;
        }
        goto LABEL_136;
      case 27:
        v23 = (ProgressPage *)operator new(0x70u);
        v11 = v23;
        if ( v23 )
        {
          memset_0(v23, 0, 0x70u);
          WizardPage::WizardPage(v11);
          *(_QWORD *)v11 = &UploadFailurePage::`vftable'{for `DirectUI::IElementListener'};
          *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
        }
        else
        {
          v11 = 0;
        }
        goto LABEL_136;
    }
    goto LABEL_117;
  }
  switch ( a2 )
  {
    case 10:
      v22 = (ProgressPage *)operator new(0x70u);
      v11 = v22;
      if ( v22 )
      {
        memset_0(v22, 0, 0x70u);
        FinalLinksPage::FinalLinksPage(v11);
        *(_QWORD *)v11 = &FinalMaintenancePage::`vftable'{for `DirectUI::IElementListener'};
        *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
      }
      else
      {
        v11 = 0;
      }
      goto LABEL_136;
    case 0:
      v20 = (IntroPage *)operator new(0x70u);
      v21 = v20;
      if ( v20 )
      {
        memset_0(v20, 0, 0x70u);
        v11 = IntroPage::IntroPage(v21);
      }
      else
      {
        v11 = 0;
      }
      *((_QWORD *)v11 + 11) = qword_14007FFC8;
      goto LABEL_136;
    case 3:
      v18 = (FinalLinksPage *)operator new(0x70u);
      v19 = v18;
      if ( v18 )
      {
        memset_0(v18, 0, 0x70u);
        v11 = FinalLinksPage::FinalLinksPage(v19);
      }
      else
      {
        v11 = 0;
      }
      goto LABEL_136;
    case 4:
      v17 = (ProgressPage *)operator new(0x70u);
      v11 = v17;
      if ( v17 )
      {
        memset_0(v17, 0, 0x70u);
        FinalWERReportPage::FinalWERReportPage(v11);
        *(_QWORD *)v11 = &FinalFailurePage::`vftable'{for `DirectUI::IElementListener'};
        *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
      }
      else
      {
        v11 = 0;
      }
      goto LABEL_136;
    case 6:
      v15 = (FinalElevationPage *)operator new(0x70u);
      v16 = v15;
      if ( v15 )
      {
        memset_0(v15, 0, 0x70u);
        v11 = FinalElevationPage::FinalElevationPage(v16);
      }
      else
      {
        v11 = 0;
      }
      goto LABEL_136;
    case 7:
      v14 = (ProgressPage *)operator new(0x70u);
      v11 = v14;
      if ( v14 )
      {
        memset_0(v14, 0, 0x70u);
        FinalElevationPage::FinalElevationPage(v11);
        *(_QWORD *)v11 = &FinalElevationContinuePage::`vftable'{for `DirectUI::IElementListener'};
        *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
      }
      else
      {
        v11 = 0;
      }
      goto LABEL_136;
    case 8:
      if ( *((_DWORD *)Config + 20) )
      {
        v12 = (ProgressPage *)operator new(0x70u);
        v11 = v12;
        if ( v12 )
        {
          memset_0(v12, 0, 0x70u);
          FinalLinksPage::FinalLinksPage(v11);
          *(_QWORD *)v11 = &NoRootCausesMaintenancePage::`vftable'{for `DirectUI::IElementListener'};
          *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
        }
        else
        {
          v11 = 0;
        }
      }
      else
      {
        v13 = (ProgressPage *)operator new(0x70u);
        v11 = v13;
        if ( v13 )
        {
          memset_0(v13, 0, 0x70u);
          FinalWERReportPage::FinalWERReportPage(v11);
          *(_QWORD *)v11 = &NoRootCausesPage::`vftable'{for `DirectUI::IElementListener'};
          *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
        }
        else
        {
          v11 = 0;
        }
      }
      goto LABEL_136;
  }
  if ( a2 != 9 )
  {
LABEL_117:
    v9 = -2147024809;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "PageManager::TypeToPage", 1256, -2147024809);
    return v9;
  }
  v10 = (ProgressPage *)operator new(0x70u);
  v11 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, 0x70u);
    FinalLinksPage::FinalLinksPage(v11);
    *(_QWORD *)v11 = &NoRootCausesElevatePage::`vftable'{for `DirectUI::IElementListener'};
    *((_QWORD *)v11 + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
  }
  else
  {
    v11 = 0;
  }
LABEL_136:
  if ( v11 )
  {
    v47 = DirectUI::TaskPage::DUICreatePropertySheetPage(v11, g_hInstance);
    v9 = v47;
    if ( v47 >= 0 )
    {
      v49 = DirectUI::TaskPage::operator _PSP *(v11);
      ParentHWND = *(HWND *)(a1 + 24);
      if ( !ParentHWND )
      {
        ParentHWND = DirectUI::TaskPage::GetParentHWND(*(DirectUI::TaskPage **)(a1 + 8));
        *(_QWORD *)(a1 + 24) = ParentHWND;
      }
      if ( SendMessageW(ParentHWND, 0x467u, 0, v49) )
      {
        v9 = 0;
        *a3 = v11;
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v6) = v11;
        return v9;
      }
      v9 = -2147467259;
      v48 = 1276;
      v47 = -2147467259;
    }
    else
    {
      v48 = 1264;
    }
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "PageManager::TypeToPage", v48, v47);
    (*(void (__fastcall **)(ProgressPage *, __int64))(*(_QWORD *)v11 + 48LL))(v11, 1);
    return v9;
  }
  v9 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "PageManager::TypeToPage", 1258, -2147024882);
  return v9;
}

```

## disassembly

```asm
0x14001d480  mov     [rsp-28h+arg_8], rbx
0x14001d485  mov     [rsp-28h+arg_10], rsi
0x14001d48a  push    rbp
0x14001d48b  push    rdi
0x14001d48c  push    r12
0x14001d48e  push    r14
0x14001d490  push    r15
0x14001d492  mov     rbp, rsp
0x14001d495  sub     rsp, 30h
0x14001d499  mov     r15, r8
0x14001d49c  movsxd  rbx, edx
0x14001d49f  mov     rsi, rcx
0x14001d4a2  mov     r14, rbx
0x14001d4a5  mov     rax, [rcx+10h]
0x14001d4a9  mov     rcx, [rax+rbx*8]
0x14001d4ad  xor     r12d, r12d
0x14001d4b0  test    rcx, rcx
0x14001d4b3  jz      short loc_14001D515
0x14001d4b5  mov     [r8], rcx
0x14001d4b8  mov     rax, [rcx]
0x14001d4bb  mov     rax, [rax+0C0h]
0x14001d4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d4c7  mov     edi, eax
0x14001d4c9  test    eax, eax
0x14001d4cb  jns     short loc_14001D4F4
0x14001d4cd  mov     [rsp+30h+var_10], eax
0x14001d4d1  mov     r9d, 475h
0x14001d4d7  lea     r8, aPagemanagerTyp; "PageManager::TypeToPage"
0x14001d4de  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001d4e5  mov     ecx, 1; Level
0x14001d4ea  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001d4ef  jmp     loc_14001DF83
0x14001d4f4  cmp     ebx, 29h ; ')'
0x14001d4f7  jnz     loc_14001DF83
0x14001d4fd  mov     rax, [rsi+10h]
0x14001d501  mov     rcx, [rax+rbx*8]
0x14001d505  mov     rax, [rsi+20h]
0x14001d509  mov     [rcx+88h], rax
0x14001d510  jmp     loc_14001DF83
0x14001d515  cmp     ebx, 1Ch
0x14001d518  jg      loc_14001DA83
0x14001d51e  jz      loc_14001DA37
0x14001d524  cmp     ebx, 0Ah
0x14001d527  jg      loc_14001D7F2
0x14001d52d  jz      loc_14001D7A6
0x14001d533  test    edx, edx
0x14001d535  jz      loc_14001D761
0x14001d53b  sub     ebx, 3
0x14001d53e  jz      loc_14001D727
0x14001d544  sub     ebx, 1
0x14001d547  jz      loc_14001D6DB
0x14001d54d  sub     ebx, 2
0x14001d550  jz      loc_14001D6A1
0x14001d556  sub     ebx, 1
0x14001d559  jz      loc_14001D655
0x14001d55f  sub     ebx, 1
0x14001d562  jz      short loc_14001D5B7
0x14001d564  cmp     ebx, 1
0x14001d567  jnz     loc_14001DD1C
0x14001d56d  lea     edi, [rbx+6Fh]
0x14001d570  mov     ecx, edi; Size
0x14001d572  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d577  mov     rbx, rax
0x14001d57a  mov     [rbp+arg_0], rax
0x14001d57e  test    rax, rax
0x14001d581  jz      short loc_14001D5AF
0x14001d583  mov     r8d, edi; Size
0x14001d586  xor     edx, edx; Val
0x14001d588  mov     rcx, rax; void *
0x14001d58b  call    memset_0
0x14001d590  mov     rcx, rbx; this
0x14001d593  call    ??0FinalLinksPage@@QEAA@XZ; FinalLinksPage::FinalLinksPage(void)
0x14001d598  lea     rax, ??_7NoRootCausesElevatePage@@6BIElementListener@DirectUI@@@; const NoRootCausesElevatePage::`vftable'{for `DirectUI::IElementListener'}
0x14001d59f  mov     [rbx], rax
0x14001d5a2  lea     rax, ??_7WizardPage@@6BIXProviderCP@DirectUI@@@; const WizardPage::`vftable'{for `DirectUI::IXProviderCP'}
0x14001d5a9  mov     [rbx+8], rax
0x14001d5ad  jmp     short loc_14001D5B2
0x14001d5af  mov     rbx, r12
0x14001d5b2  jmp     loc_14001DEAB
0x14001d5b7  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14001d5be  mov     edi, 70h ; 'p'
0x14001d5c3  mov     ecx, edi; Size
0x14001d5c5  cmp     [rax+50h], r12d
0x14001d5c9  jz      short loc_14001D610
0x14001d5cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d5d0  mov     rbx, rax
0x14001d5d3  mov     [rbp+arg_0], rax
0x14001d5d7  test    rax, rax
0x14001d5da  jz      short loc_14001D608
0x14001d5dc  mov     r8d, edi; Size
0x14001d5df  xor     edx, edx; Val
0x14001d5e1  mov     rcx, rax; void *
0x14001d5e4  call    memset_0
0x14001d5e9  mov     rcx, rbx; this
0x14001d5ec  call    ??0FinalLinksPage@@QEAA@XZ; FinalLinksPage::FinalLinksPage(void)
0x14001d5f1  lea     rax, ??_7NoRootCausesMaintenancePage@@6BIElementListener@DirectUI@@@; const NoRootCausesMaintenancePage::`vftable'{for `DirectUI::IElementListener'}
0x14001d5f8  mov     [rbx], rax
0x14001d5fb  lea     rax, ??_7WizardPage@@6BIXProviderCP@DirectUI@@@; const WizardPage::`vftable'{for `DirectUI::IXProviderCP'}
0x14001d602  mov     [rbx+8], rax
0x14001d606  jmp     short loc_14001D60B
0x14001d608  mov     rbx, r12
0x14001d60b  jmp     loc_14001DEAB
0x14001d610  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d615  mov     rbx, rax
0x14001d618  mov     [rbp+arg_0], rax
0x14001d61c  test    rax, rax
0x14001d61f  jz      short loc_14001D64D
0x14001d621  mov     r8, rdi; Size
0x14001d624  xor     edx, edx; Val
0x14001d626  mov     rcx, rax; void *
0x14001d629  call    memset_0
0x14001d62e  mov     rcx, rbx; this
0x14001d631  call    ??0FinalWERReportPage@@QEAA@XZ; FinalWERReportPage::FinalWERReportPage(void)
0x14001d636  lea     rax, ??_7NoRootCausesPage@@6BIElementListener@DirectUI@@@; const NoRootCausesPage::`vftable'{for `DirectUI::IElementListener'}
0x14001d63d  mov     [rbx], rax
0x14001d640  lea     rax, ??_7WizardPage@@6BIXProviderCP@DirectUI@@@; const WizardPage::`vftable'{for `DirectUI::IXProviderCP'}
0x14001d647  mov     [rbx+8], rax
0x14001d64b  jmp     short loc_14001D650
0x14001d64d  mov     rbx, r12
0x14001d650  jmp     loc_14001DEAB
0x14001d655  mov     edi, 70h ; 'p'
0x14001d65a  mov     ecx, edi; Size
0x14001d65c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d661  mov     rbx, rax
0x14001d664  mov     [rbp+arg_0], rax
0x14001d668  test    rax, rax
0x14001d66b  jz      short loc_14001D699
0x14001d66d  mov     r8d, edi; Size
0x14001d670  xor     edx, edx; Val
0x14001d672  mov     rcx, rax; void *
0x14001d675  call    memset_0
0x14001d67a  mov     rcx, rbx; this
0x14001d67d  call    ??0FinalElevationPage@@QEAA@XZ; FinalElevationPage::FinalElevationPage(void)
0x14001d682  lea     rax, ??_7FinalElevationContinuePage@@6BIElementListener@DirectUI@@@; const FinalElevationContinuePage::`vftable'{for `DirectUI::IElementListener'}
0x14001d689  mov     [rbx], rax
0x14001d68c  lea     rax, ??_7WizardPage@@6BIXProviderCP@DirectUI@@@; const WizardPage::`vftable'{for `DirectUI::IXProviderCP'}
0x14001d693  mov     [rbx+8], rax
0x14001d697  jmp     short loc_14001D69C
0x14001d699  mov     rbx, r12
0x14001d69c  jmp     loc_14001DEAB
0x14001d6a1  mov     edi, 70h ; 'p'
0x14001d6a6  mov     ecx, edi; Size
0x14001d6a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d6ad  mov     rbx, rax
0x14001d6b0  mov     [rbp+arg_0], rax
0x14001d6b4  test    rax, rax
0x14001d6b7  jz      short loc_14001D6D3
0x14001d6b9  mov     r8d, edi; Size
0x14001d6bc  xor     edx, edx; Val
0x14001d6be  mov     rcx, rax; void *
0x14001d6c1  call    memset_0
0x14001d6c6  mov     rcx, rbx; this
0x14001d6c9  call    ??0FinalElevationPage@@QEAA@XZ; FinalElevationPage::FinalElevationPage(void)
0x14001d6ce  mov     rbx, rax
0x14001d6d1  jmp     short loc_14001D6D6
0x14001d6d3  mov     rbx, r12
0x14001d6d6  jmp     loc_14001DEAB
0x14001d6db  mov     edi, 70h ; 'p'
0x14001d6e0  mov     ecx, edi; Size
0x14001d6e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d6e7  mov     rbx, rax
0x14001d6ea  mov     [rbp+arg_0], rax
0x14001d6ee  test    rax, rax
0x14001d6f1  jz      short loc_14001D71F
0x14001d6f3  mov     r8d, edi; Size
0x14001d6f6  xor     edx, edx; Val
0x14001d6f8  mov     rcx, rax; void *
0x14001d6fb  call    memset_0
0x14001d700  mov     rcx, rbx; this
0x14001d703  call    ??0FinalWERReportPage@@QEAA@XZ; FinalWERReportPage::FinalWERReportPage(void)
0x14001d708  lea     rax, ??_7FinalFailurePage@@6BIElementListener@DirectUI@@@; const FinalFailurePage::`vftable'{for `DirectUI::IElementListener'}
0x14001d70f  mov     [rbx], rax
0x14001d712  lea     rax, ??_7WizardPage@@6BIXProviderCP@DirectUI@@@; const WizardPage::`vftable'{for `DirectUI::IXProviderCP'}
0x14001d719  mov     [rbx+8], rax
0x14001d71d  jmp     short loc_14001D722
0x14001d71f  mov     rbx, r12
0x14001d722  jmp     loc_14001DEAB
0x14001d727  mov     edi, 70h ; 'p'
0x14001d72c  mov     ecx, edi; Size
0x14001d72e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d733  mov     rbx, rax
0x14001d736  mov     [rbp+arg_0], rax
0x14001d73a  test    rax, rax
0x14001d73d  jz      short loc_14001D759
0x14001d73f  mov     r8d, edi; Size
0x14001d742  xor     edx, edx; Val
0x14001d744  mov     rcx, rax; void *
0x14001d747  call    memset_0
0x14001d74c  mov     rcx, rbx; this
0x14001d74f  call    ??0FinalLinksPage@@QEAA@XZ; FinalLinksPage::FinalLinksPage(void)
0x14001d754  mov     rbx, rax
0x14001d757  jmp     short loc_14001D75C
0x14001d759  mov     rbx, r12
0x14001d75c  jmp     loc_14001DEAB
0x14001d761  mov     edi, 70h ; 'p'
0x14001d766  mov     ecx, edi; Size
0x14001d768  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d76d  mov     rbx, rax
0x14001d770  mov     [rbp+arg_0], rax
0x14001d774  test    rax, rax
0x14001d777  jz      short loc_14001D793
0x14001d779  mov     r8d, edi; Size
0x14001d77c  xor     edx, edx; Val
0x14001d77e  mov     rcx, rax; void *
0x14001d781  call    memset_0
0x14001d786  mov     rcx, rbx; this
0x14001d789  call    ??0IntroPage@@QEAA@XZ; IntroPage::IntroPage(void)
0x14001d78e  mov     rbx, rax
0x14001d791  jmp     short loc_14001D796
0x14001d793  mov     rbx, r12
0x14001d796  mov     rax, cs:qword_14007FFC8
0x14001d79d  mov     [rbx+58h], rax
0x14001d7a1  jmp     loc_14001DEAB
0x14001d7a6  mov     edi, 70h ; 'p'
0x14001d7ab  mov     ecx, edi; Size
0x14001d7ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d7b2  mov     rbx, rax
0x14001d7b5  mov     [rbp+arg_0], rax
0x14001d7b9  test    rax, rax
0x14001d7bc  jz      short loc_14001D7EA
0x14001d7be  mov     r8d, edi; Size
0x14001d7c1  xor     edx, edx; Val
0x14001d7c3  mov     rcx, rax; void *
0x14001d7c6  call    memset_0
0x14001d7cb  mov     rcx, rbx; this
0x14001d7ce  call    ??0FinalLinksPage@@QEAA@XZ; FinalLinksPage::FinalLinksPage(void)
0x14001d7d3  lea     rax, ??_7FinalMaintenancePage@@6BIElementListener@DirectUI@@@; const FinalMaintenancePage::`vftable'{for `DirectUI::IElementListener'}
0x14001d7da  mov     [rbx], rax
0x14001d7dd  lea     rax, ??_7WizardPage@@6BIXProviderCP@DirectUI@@@; const WizardPage::`vftable'{for `DirectUI::IXProviderCP'}
0x14001d7e4  mov     [rbx+8], rax
0x14001d7e8  jmp     short loc_14001D7ED
0x14001d7ea  mov     rbx, r12
0x14001d7ed  jmp     loc_14001DEAB
0x14001d7f2  sub     ebx, 14h
0x14001d7f5  jz      loc_14001D9D6
0x14001d7fb  sub     ebx, 2
0x14001d7fe  jz      loc_14001D99C
0x14001d804  sub     ebx, 1
0x14001d807  jz      loc_14001D950
0x14001d80d  sub     ebx, 1
0x14001d810  jz      loc_14001D904
0x14001d816  sub     ebx, 1
0x14001d819  jz      loc_14001D8C3
0x14001d81f  sub     ebx, 1
0x14001d822  jz      short loc_14001D877
0x14001d824  cmp     ebx, 1
0x14001d827  jnz     loc_14001DD1C
0x14001d82d  lea     edi, [rbx+6Fh]
0x14001d830  mov     ecx, edi; Size
0x14001d832  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d837  mov     rbx, rax
0x14001d83a  mov     [rbp+arg_0], rax
0x14001d83e  test    rax, rax
0x14001d841  jz      short loc_14001D86F
0x14001d843  mov     r8d, edi; Size
0x14001d846  xor     edx, edx; Val
0x14001d848  mov     rcx, rax; void *
0x14001d84b  call    memset_0
0x14001d850  mov     rcx, rbx; this
0x14001d853  call    ??0WizardPage@@QEAA@XZ; WizardPage::WizardPage(void)
0x14001d858  lea     rax, ??_7UploadFailurePage@@6BIElementListener@DirectUI@@@; const UploadFailurePage::`vftable'{for `DirectUI::IElementListener'}
0x14001d85f  mov     [rbx], rax
0x14001d862  lea     rax, ??_7WizardPage@@6BIXProviderCP@DirectUI@@@; const WizardPage::`vftable'{for `DirectUI::IXProviderCP'}
0x14001d869  mov     [rbx+8], rax
0x14001d86d  jmp     short loc_14001D872
0x14001d86f  mov     rbx, r12
0x14001d872  jmp     loc_14001DEAB
0x14001d877  mov     edi, 70h ; 'p'
0x14001d87c  mov     ecx, edi; Size
0x14001d87e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d883  mov     rbx, rax
0x14001d886  mov     [rbp+arg_0], rax
0x14001d88a  test    rax, rax
0x14001d88d  jz      short loc_14001D8BB
0x14001d88f  mov     r8d, edi; Size
0x14001d892  xor     edx, edx; Val
0x14001d894  mov     rcx, rax; void *
0x14001d897  call    memset_0
0x14001d89c  mov     rcx, rbx; this
0x14001d89f  call    ??0WizardPage@@QEAA@XZ; WizardPage::WizardPage(void)
0x14001d8a4  lea     rax, ??_7UploadConsentPage@@6BIElementListener@DirectUI@@@; const UploadConsentPage::`vftable'{for `DirectUI::IElementListener'}
0x14001d8ab  mov     [rbx], rax
0x14001d8ae  lea     rax, ??_7WizardPage@@6BIXProviderCP@DirectUI@@@; const WizardPage::`vftable'{for `DirectUI::IXProviderCP'}
0x14001d8b5  mov     [rbx+8], rax
0x14001d8b9  jmp     short loc_14001D8BE
0x14001d8bb  mov     rbx, r12
0x14001d8be  jmp     loc_14001DEAB
0x14001d8c3  mov     ecx, 78h ; 'x'; Size
0x14001d8c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d8cd  mov     rbx, rax
0x14001d8d0  mov     [rbp+arg_0], rax
0x14001d8d4  test    rax, rax
0x14001d8d7  jz      short loc_14001D8FC
0x14001d8d9  mov     rcx, rax; this
0x14001d8dc  call    ??0WizardPage@@QEAA@XZ; WizardPage::WizardPage(void)
0x14001d8e1  lea     rax, ??_7UploadFilePage@@6BIElementListener@DirectUI@@@; const UploadFilePage::`vftable'{for `DirectUI::IElementListener'}
0x14001d8e8  mov     [rbx], rax
0x14001d8eb  lea     rax, ??_7WizardPage@@6BIXProviderCP@DirectUI@@@; const WizardPage::`vftable'{for `DirectUI::IXProviderCP'}
0x14001d8f2  mov     [rbx+8], rax
0x14001d8f6  mov     [rbx+70h], r12d
  ... truncated ...
```

# CAdvancedPage::InitializePage(void *)

- ea: `0x1800076f0`
- end: `0x180007976`
- name: `?InitializePage@CAdvancedPage@@MEAAJPEAX@Z`
- size: `646`
- prototype: `__int64 __fastcall(CAdvancedPage *__hidden this, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006dfc`
- `0x180007204`
- `0x1800076f0`
- `0x180008ddc`
- `0x180008fd0`
- `0x180009b64`
- `0x18000a578`
- `0x18000b18c`
- `0x18000b1e4`
- `0x180015ed4`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x180007871`
- `SHLWAPI!__imp_SHCreateThread` at `0x180007871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000787b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000787b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078d1`
- `ntdll!WinSqmIncrementDWORD` at `0x180007944`
- `ntdll!WinSqmIncrementDWORD` at `0x180007944`
- `USER32!SendMessageW` at `0x180007842`
- `USER32!SendMessageW` at `0x180007842`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000780f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800078ee`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000780f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800078ee`
- `DUI70!StrToID` at `0x180007803`
- `DUI70!StrToID` at `0x1800078e2`
- `DUI70!StrToID` at `0x180007803`
- `DUI70!StrToID` at `0x1800078e2`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000784d`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000784d`

## pseudocode

```c
__int64 __fastcall CAdvancedPage::InitializePage(CAdvancedPage *this, void *a2, __int64 a3)
{
  char v3; // bp
  int (*v6)(unsigned int, unsigned __int64, __int64, __int64 *, void *); // r9
  __int64 v7; // rax
  signed int v8; // edi
  int (*v9)(unsigned int, unsigned __int64, __int64, __int64 *, void *); // r9
  int (*v10)(unsigned int, unsigned __int64, __int64, __int64 *, void *); // r9
  int (*v11)(unsigned int, unsigned __int64, __int64, __int64 *, void *); // r9
  DirectUI::Element *v12; // rbx
  unsigned __int16 v13; // ax
  struct DirectUI::Element *Descendent; // rax
  DirectUI::Element *v15; // rbx
  HWND v16; // rax
  signed int LastError; // eax
  const wchar_t **v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  const wchar_t *v22; // r9
  DirectUI::Element *v23; // rbx
  unsigned __int16 v24; // ax
  struct DirectUI::Element *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  _QWORD v29[42]; // [rsp+30h] [rbp-1A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR hMem; // [rsp+180h] [rbp-58h] BYREF

  v3 = 0;
  LODWORD(hMem.Ptr) = 0;
  if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)this,
      (const EVENT_DESCRIPTOR *)Perf_Initialization_AdvancedPage_Start,
      a3,
      1u,
      &hMem);
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v29,
    "PageInitialization");
  v29[0] = &AdvancedSettingsTelemetry::PageInitialization::`vftable';
  AdvancedSettingsTelemetry::PageInitialization::StartActivity((AdvancedSettingsTelemetry::PageInitialization *)v29);
  v7 = 0;
  v8 = -2147467259;
  do
  {
    *((_DWORD *)this + 2 * v7 + 9) = -1;
    *((_DWORD *)this + 2 * v7++ + 8) = -1;
  }
  while ( v7 != 12 );
  if ( !*((_QWORD *)this + 2) || !a2 )
    goto LABEL_16;
  *((_QWORD *)this + 3) = a2;
  CAdvancedPage::_SetNotifyHandler(this, L"NetworkDiscoverySetting", L"Caption", v6);
  CAdvancedPage::_SetNotifyHandler(this, L"PublicFolderSetting", L"Caption", v9);
  CAdvancedPage::_SetNotifyHandler(this, L"NetworkDiscoverySetting", L"Button0OptionHelp", v10);
  CAdvancedPage::_SetNotifyHandler(this, L"NetworkDiscoverySetting", L"Button1OptionHelp", v11);
  v12 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v13 = StrToID(L"ButtonSaveChanges");
  Descendent = DirectUI::Element::FindDescendent(v12, v13);
  v15 = Descendent;
  if ( Descendent )
  {
    v16 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 360LL))(Descendent);
    if ( v16 )
      SendMessageW(v16, 0x160Cu, 0, 1);
    DirectUI::Element::SetEnabled(v15, 0);
  }
  CAdvancedPage::_EnsureProfileArea(this);
  v8 = 0;
  if ( !SHCreateThread(CAdvancedPage::_s_GetAdvancedSettingsThreadProc, (void *)**((unsigned int **)this + 3), 0xAu, 0) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
LABEL_16:
    if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 1) != 0 )
    {
      v18 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v8);
      v22 = L"???";
      if ( *v18 )
        v22 = *v18;
      McTemplateU0zz_EventWriteTransfer(v20, v19, v21, v22);
      v3 = 1;
    }
    if ( (v3 & 1) != 0 )
      LocalFree((HLOCAL)hMem.Ptr);
  }
  v23 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v24 = StrToID(L"ButtonCancel");
  v25 = DirectUI::Element::FindDescendent(v23, v24);
  (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v25 + 168LL))(v25);
  if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v26,
      (const EVENT_DESCRIPTOR *)Perf_Initialization_AdvancedPage_Stop,
      v27,
      1u,
      &hMem);
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v29, v8);
  WinSqmIncrementDWORD(0, 3367, 1);
  AdvancedSettingsTelemetry::PageInitialization::~PageInitialization((AdvancedSettingsTelemetry::PageInitialization *)v29);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800076f0  mov     r11, rsp
0x1800076f3  push    rbx
0x1800076f4  push    rbp
0x1800076f5  push    rsi
0x1800076f6  push    rdi
0x1800076f7  push    r14
0x1800076f9  push    r15
0x1800076fb  sub     rsp, 1A8h
0x180007702  mov     rax, cs:__security_cookie
0x180007709  xor     rax, rsp
0x18000770c  mov     [rsp+1D8h+var_48], rax
0x180007714  xor     ebp, ebp
0x180007716  mov     rbx, rdx
0x180007719  mov     dword ptr [rsp+1D8h+hMem], ebp
0x180007720  mov     rsi, rcx
0x180007723  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 4
0x18000772a  lea     r14d, [rbp+1]
0x18000772e  jz      short loc_180007748
0x180007730  lea     rax, [r11-58h]
0x180007734  mov     r9d, r14d
0x180007737  lea     rdx, Perf_Initialization_AdvancedPage_Start
0x18000773e  mov     [rsp+1D8h+var_1B8], rax
0x180007743  call    McGenEventWrite_EventWriteTransfer
0x180007748  lea     rdx, aPageinitializa; "PageInitialization"
0x18000774f  lea     rcx, [rsp+1D8h+var_1A8]
0x180007754  call    ??0?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180007759  lea     rax, ??_7PageInitialization@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::PageInitialization::`vftable'
0x180007760  lea     rcx, [rsp+1D8h+var_1A8]; this
0x180007765  mov     [rsp+1D8h+var_1A8], rax
0x18000776a  call    ?StartActivity@PageInitialization@AdvancedSettingsTelemetry@@QEAAXXZ; AdvancedSettingsTelemetry::PageInitialization::StartActivity(void)
0x18000776f  mov     r15d, 80004005h
0x180007775  xor     eax, eax
0x180007777  mov     edi, r15d
0x18000777a  or      ecx, 0FFFFFFFFh
0x18000777d  mov     [rsi+rax*8+24h], ecx
0x180007781  mov     [rsi+rax*8+20h], ecx
0x180007785  add     rax, r14
0x180007788  cmp     rax, 0Ch
0x18000778c  jnz     short loc_18000777D
0x18000778e  cmp     [rsi+10h], rbp
0x180007792  jz      loc_180007896
0x180007798  test    rbx, rbx
0x18000779b  jz      loc_180007896
0x1800077a1  mov     [rsi+18h], rbx
0x1800077a5  lea     r8, aCaption; "Caption"
0x1800077ac  lea     rbx, String2; "NetworkDiscoverySetting"
0x1800077b3  mov     rcx, rsi; this
0x1800077b6  mov     rdx, rbx; unsigned __int16 *
0x1800077b9  call    ?_SetNotifyHandler@CAdvancedPage@@AEAAXPEBG0P6AHI_K_JPEA_JPEAX@Z@Z; CAdvancedPage::_SetNotifyHandler(ushort const *,ushort const *,int (*)(uint,unsigned __int64,__int64,__int64 *,void *))
0x1800077be  lea     r8, aCaption; "Caption"
0x1800077c5  mov     rcx, rsi; this
0x1800077c8  lea     rdx, aPublicfolderse; "PublicFolderSetting"
0x1800077cf  call    ?_SetNotifyHandler@CAdvancedPage@@AEAAXPEBG0P6AHI_K_JPEA_JPEAX@Z@Z; CAdvancedPage::_SetNotifyHandler(ushort const *,ushort const *,int (*)(uint,unsigned __int64,__int64,__int64 *,void *))
0x1800077d4  lea     r8, aButton0optionh; "Button0OptionHelp"
0x1800077db  mov     rdx, rbx; unsigned __int16 *
0x1800077de  mov     rcx, rsi; this
0x1800077e1  call    ?_SetNotifyHandler@CAdvancedPage@@AEAAXPEBG0P6AHI_K_JPEA_JPEAX@Z@Z; CAdvancedPage::_SetNotifyHandler(ushort const *,ushort const *,int (*)(uint,unsigned __int64,__int64,__int64 *,void *))
0x1800077e6  lea     r8, aButton1optionh; "Button1OptionHelp"
0x1800077ed  mov     rdx, rbx; unsigned __int16 *
0x1800077f0  mov     rcx, rsi; this
0x1800077f3  call    ?_SetNotifyHandler@CAdvancedPage@@AEAAXPEBG0P6AHI_K_JPEA_JPEAX@Z@Z; CAdvancedPage::_SetNotifyHandler(ushort const *,ushort const *,int (*)(uint,unsigned __int64,__int64,__int64 *,void *))
0x1800077f8  mov     rbx, [rsi+10h]
0x1800077fc  lea     rcx, aButtonsavechan; "ButtonSaveChanges"
0x180007803  call    cs:__imp_StrToID
0x180007809  movzx   edx, ax
0x18000780c  mov     rcx, rbx
0x18000780f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180007815  mov     rbx, rax
0x180007818  test    rax, rax
0x18000781b  jz      short loc_180007853
0x18000781d  mov     rcx, [rax]
0x180007820  mov     rax, [rcx+168h]
0x180007827  mov     rcx, rbx
0x18000782a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782f  test    rax, rax
0x180007832  jz      short loc_180007848
0x180007834  mov     r9, r14; lParam
0x180007837  xor     r8d, r8d; wParam
0x18000783a  mov     edx, 160Ch; Msg
0x18000783f  mov     rcx, rax; hWnd
0x180007842  call    cs:__imp_SendMessageW
0x180007848  xor     edx, edx
0x18000784a  mov     rcx, rbx
0x18000784d  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180007853  mov     rcx, rsi; this
0x180007856  call    ?_EnsureProfileArea@CAdvancedPage@@AEAAXXZ; CAdvancedPage::_EnsureProfileArea(void)
0x18000785b  mov     rax, [rsi+18h]
0x18000785f  lea     rcx, ?_s_GetAdvancedSettingsThreadProc@CAdvancedPage@@CAKPEAX@Z; pfnThreadProc
0x180007866  xor     edi, edi
0x180007868  xor     r9d, r9d; pfnCallback
0x18000786b  mov     edx, [rax]; pData
0x18000786d  lea     r8d, [rdi+0Ah]; flags
0x180007871  call    cs:__imp_SHCreateThread
0x180007877  test    eax, eax
0x180007879  jnz     short loc_1800078D7
0x18000787b  call    cs:__imp_GetLastError
0x180007881  mov     edi, eax
0x180007883  test    eax, eax
0x180007885  jle     short loc_180007890
0x180007887  movzx   edi, ax
0x18000788a  or      edi, 80070000h
0x180007890  test    edi, edi
0x180007892  cmovns  edi, r15d
0x180007896  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, r14b
0x18000789d  jz      short loc_1800078C4
0x18000789f  mov     edx, edi; dwMessageId
0x1800078a1  lea     rcx, [rsp+1D8h+hMem]; lpBuffer
0x1800078a9  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x1800078ae  lea     r9, asc_18001ECC8; "???"
0x1800078b5  cmp     [rax], rbp
0x1800078b8  cmovnz  r9, [rax]
0x1800078bc  call    McTemplateU0zz_EventWriteTransfer
0x1800078c1  mov     ebp, r14d
0x1800078c4  test    r14b, bpl
0x1800078c7  jz      short loc_1800078D7
0x1800078c9  mov     rcx, qword ptr [rsp+1D8h+hMem]; hMem
0x1800078d1  call    cs:__imp_LocalFree
0x1800078d7  mov     rbx, [rsi+10h]
0x1800078db  lea     rcx, aButtoncancel; "ButtonCancel"
0x1800078e2  call    cs:__imp_StrToID
0x1800078e8  movzx   edx, ax
0x1800078eb  mov     rcx, rbx
0x1800078ee  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800078f4  mov     rdx, rax
0x1800078f7  mov     rcx, [rax]
0x1800078fa  mov     rax, [rcx+0A8h]
0x180007901  mov     rcx, rdx
0x180007904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007909  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 4
0x180007910  jz      short loc_18000792E
0x180007912  lea     rax, [rsp+1D8h+hMem]
0x18000791a  mov     r9d, r14d
0x18000791d  lea     rdx, Perf_Initialization_AdvancedPage_Stop
0x180007924  mov     [rsp+1D8h+var_1B8], rax
0x180007929  call    McGenEventWrite_EventWriteTransfer
0x18000792e  mov     edx, edi
0x180007930  lea     rcx, [rsp+1D8h+var_1A8]
0x180007935  call    ?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000793a  mov     r8d, r14d
0x18000793d  mov     edx, 0D27h
0x180007942  xor     ecx, ecx
0x180007944  call    cs:__imp_WinSqmIncrementDWORD
0x18000794a  lea     rcx, [rsp+1D8h+var_1A8]; this
0x18000794f  call    ??1PageInitialization@AdvancedSettingsTelemetry@@QEAA@XZ; AdvancedSettingsTelemetry::PageInitialization::~PageInitialization(void)
0x180007954  mov     eax, edi
0x180007956  mov     rcx, [rsp+1D8h+var_48]
0x18000795e  xor     rcx, rsp; StackCookie
0x180007961  call    __security_check_cookie
0x180007966  add     rsp, 1A8h
0x18000796d  pop     r15
0x18000796f  pop     r14
0x180007971  pop     rdi
0x180007972  pop     rsi
0x180007973  pop     rbp
0x180007974  pop     rbx
0x180007975  retn
```

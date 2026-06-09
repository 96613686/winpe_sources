# InitSystemMetricValues(THREADSTATEUI *)

- ea: `0x1804765a0`
- end: `0x1804769db`
- name: `?InitSystemMetricValues@@YAJPEAUTHREADSTATEUI@@@Z`
- size: `1083`
- prototype: `__int64 __fastcall(struct THREADSTATEUI *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f2674`
- `0x180474d64`
- `0x1806d4ea8`

## callees

- `0x1804765a0`
- `0x1804769e4`
- `0x180476a8c`
- `0x180476d2c`
- `0x180476dc4`
- `0x180476e00`
- `0x180476e8c`
- `0x1804774c0`
- `0x18083c0b4`
- `0x18083c124`
- `0x180b60484`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!GetUserDefaultLCID` at `0x18047678b`
- `KERNEL32!GetUserDefaultLCID` at `0x18047678b`
- `KERNEL32!GetACP` at `0x18047679d`
- `KERNEL32!GetACP` at `0x18047679d`
- `KERNEL32!GetCurrentProcess` at `0x180476979`
- `KERNEL32!GetCurrentProcess` at `0x180476979`
- `GDI32!DeleteObject` at `0x18047676d`
- `GDI32!DeleteObject` at `0x18047676d`
- `GDI32!SelectObject` at `0x180476752`
- `GDI32!SelectObject` at `0x1804768a8`
- `GDI32!SelectObject` at `0x180476752`
- `GDI32!SelectObject` at `0x1804768a8`
- `GDI32!CreateCompatibleDC` at `0x18047693a`
- `GDI32!CreateCompatibleDC` at `0x18047693a`
- `GDI32!GetTextMetricsW` at `0x180476876`
- `GDI32!GetTextMetricsW` at `0x180476876`
- `USER32!GetSystemMetrics` at `0x180476620`
- `USER32!GetSystemMetrics` at `0x180476630`
- `USER32!GetSystemMetrics` at `0x18047664d`
- `USER32!GetSystemMetrics` at `0x180476664`
- `USER32!GetSystemMetrics` at `0x180476620`
- `USER32!GetSystemMetrics` at `0x180476630`
- `USER32!GetSystemMetrics` at `0x18047664d`
- `USER32!GetSystemMetrics` at `0x180476664`
- `USER32!SystemParametersInfoW` at `0x1804767c3`
- `USER32!SystemParametersInfoW` at `0x1804767fa`
- `USER32!SystemParametersInfoW` at `0x180476817`
- `USER32!SystemParametersInfoW` at `0x1804767c3`
- `USER32!SystemParametersInfoW` at `0x1804767fa`
- `USER32!SystemParametersInfoW` at `0x180476817`
- `iertutil!__imp_?IEIsImmersiveProcess@@YAHPEAX@Z` at `0x180476988`
- `iertutil!__imp_?IEIsImmersiveProcess@@YAHPEAX@Z` at `0x180476988`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1804768f2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1804768f2`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180476779`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180476779`
- `UXTHEME!IsAppThemed` at `0x1804767d4`
- `UXTHEME!IsAppThemed` at `0x1804767d4`

## pseudocode

```c
__int64 __fastcall InitSystemMetricValues(struct THREADSTATEUI *a1)
{
  HDC CompatibleDC; // rax
  int SystemDpiWrapper; // esi
  int SystemMetrics; // ebx
  int v5; // eax
  struct CSize *v6; // rcx
  HFONT SystemFont; // rax
  HFONT v8; // rsi
  HGDIOBJ v9; // rbx
  unsigned int *v10; // rdx
  enum NUMSHAPE *v11; // rcx
  enum HighContrastMode::Enum *v12; // rcx
  float v14; // xmm1_4
  HANDLE CurrentProcess; // rax
  int EffectiveDpiWrapper; // eax
  tagTEXTMETRICW tm; // [rsp+20h] [rbp-68h] BYREF

  memset(&tm, 0, sizeof(tm));
  _InterlockedIncrement(&g_cMetricChange);
  CompatibleDC = (HDC)*((_QWORD *)a1 + 30);
  if ( !CompatibleDC )
  {
    CompatibleDC = CreateCompatibleDC(0);
    *((_QWORD *)a1 + 30) = CompatibleDC;
    if ( !CompatibleDC )
      return 2147942414LL;
  }
  SystemDpiWrapper = GetSystemDpiWrapper(CompatibleDC);
  if ( !(_BYTE)word_1815BFDD1 )
  {
    if ( dword_1815C7148 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 12LL) )
    {
      Init_thread_header(&dword_1815C7148);
      if ( dword_1815C7148 == -1 )
      {
        CurrentProcess = GetCurrentProcess();
        dword_1815C714C = IEIsImmersiveProcess(CurrentProcess);
        Init_thread_footer(&dword_1815C7148);
      }
    }
    if ( !dword_1815C714C || (unsigned __int8)IEConfiguration_GetBool(268435481) )
    {
      if ( (byte_1815BFC78 & 2) != 0 )
        EffectiveDpiWrapper = GetEffectiveDpiWrapper(*(HWND *)(*((_QWORD *)a1 + 29) + 96LL));
      else
        EffectiveDpiWrapper = SystemDpiWrapper;
      v14 = (float)EffectiveDpiWrapper / 96.0;
    }
    else
    {
      v14 = FLOAT_1_0;
    }
    CUnitInfo::SetResolutionAtNormalZoom(96, v14, 0);
  }
  SystemMetrics = GetSystemMetrics(1);
  v5 = GetSystemMetrics(0);
  HIDWORD(g_sizePrimaryDisplay) = SystemMetrics;
  LODWORD(g_sizePrimaryDisplay) = v5;
  g_sizeDragMin.cx = GetSystemMetrics(68);
  g_sizeDragMin.cy = GetSystemMetrics(69);
  g_lWidthComboButton = 16;
  if ( g_fOverrideScrollbarSizes )
  {
    g_sizeScrollbar = 16;
    *(&g_sizeScrollbar + 1) = 16;
    g_sizeRootScrollbar = 0x1000000010LL;
  }
  else
  {
    GetSystemScrollbarSizeWrapper(v6);
    CSize::SetSize(
      (CSize *)&g_sizeScrollbar,
      (float)g_sizeScrollbar * (float)(96.0 / (float)SystemDpiWrapper),
      (float)*(&g_sizeScrollbar + 1) * (float)(96.0 / (float)SystemDpiWrapper),
      0);
    g_sizeRootScrollbar = g_sizeScrollbar;
  }
  g_sizeOverlayScrollbarDisplay = 0x1100000011LL;
  g_sizeRootOverlayScrollbarDisplay = 0x1100000011LL;
  g_lScrollGutterRatio = 8;
  dword_1815B8D9C = 10;
  dword_1815C4DD4 = (int)(((8LL * dword_1815BFD50) >> ((unsigned __int8)dword_1815BFD54 - 1)) + 1) >> 1;
  LODWORD(g_alHimetricFrom8Pixels) = dword_1815C4DD4;
  g_sizeSystemChar.cx = 10;
  SystemFont = GetSystemFont();
  v8 = SystemFont;
  if ( SystemFont )
  {
    v9 = SelectObject(*((HDC *)a1 + 30), SystemFont);
    if ( v9 )
    {
      if ( GetTextMetricsW(*((HDC *)a1 + 30), &tm) )
      {
        g_sizeSystemChar.cx = tm.tmAveCharWidth;
        dword_1815B8D9C = tm.tmHeight;
      }
      else
      {
        g_sizeSystemChar.cx = 10;
        dword_1815B8D9C = 10;
      }
      SelectObject(*((HDC *)a1 + 30), v9);
    }
  }
  DeleteObject(v8);
  g_lcidUserDefault = GetSystemDefaultLCID();
  g_lcidLocalUserDefault = GetUserDefaultLCID();
  g_cpDefault = GetACP();
  GetSystemNumberSettings(v11, v10);
  SystemParametersInfoW(0x46u, 0, &g_fScreenReader, 0);
  GetHighContrastMode(v12);
  g_fIsAppThemed = IsAppThemed();
  SystemParametersInfoW(0x1042u, 0, &g_fAnimationsEnabled, 0);
  SystemParametersInfoW(0x103Eu, 0, &g_fUIEffectsEnabled, 0);
  return 0;
}

```

## disassembly

```asm
0x1804765a0  mov     r11, rsp
0x1804765a3  mov     [r11+10h], rbx
0x1804765a7  mov     [r11+18h], rsi
0x1804765ab  mov     [r11+8], rcx
0x1804765af  push    rdi
0x1804765b0  sub     rsp, 80h
0x1804765b7  movaps  [rsp+88h+var_18], xmm6
0x1804765bc  mov     rax, cs:__security_cookie
0x1804765c3  xor     rax, rsp
0x1804765c6  mov     [rsp+88h+var_28], rax
0x1804765cb  xorps   xmm0, xmm0
0x1804765ce  mov     rdi, rcx
0x1804765d1  movups  xmmword ptr [rsp+88h+tm.tmOverhang], xmm0
0x1804765d6  movups  xmmword ptr [rsp+88h+tm.tmFirstChar], xmm0
0x1804765db  movups  xmmword ptr [rsp+88h+tm.tmHeight], xmm0
0x1804765e0  movups  xmmword ptr [rsp+88h+tm.tmExternalLeading], xmm0
0x1804765e5  lock inc cs:?g_cMetricChange@@3JA; long g_cMetricChange
0x1804765ec  mov     rax, [rcx+0F0h]
0x1804765f3  test    rax, rax
0x1804765f6  jz      loc_180476938
0x1804765fc  mov     rcx, rax; HDC
0x1804765ff  call    ?GetSystemDpiWrapper@@YAIPEAUHDC__@@@Z; GetSystemDpiWrapper(HDC__ *)
0x180476604  cmp     byte ptr cs:word_1815BFDD1, 0
0x18047660b  movss   xmm6, cs:__real@42c00000
0x180476613  mov     esi, eax
0x180476615  jz      loc_1804768B9
0x18047661b  mov     ecx, 1; nIndex
0x180476620  call    cs:__imp_GetSystemMetrics
0x180476627  nop     dword ptr [rax+rax+00h]
0x18047662c  xor     ecx, ecx; nIndex
0x18047662e  mov     ebx, eax
0x180476630  call    cs:__imp_GetSystemMetrics
0x180476637  nop     dword ptr [rax+rax+00h]
0x18047663c  mov     ecx, 44h ; 'D'; nIndex
0x180476641  mov     dword ptr cs:?g_sizePrimaryDisplay@@3VCSize@@A+4, ebx; CSize g_sizePrimaryDisplay
0x180476647  mov     dword ptr cs:?g_sizePrimaryDisplay@@3VCSize@@A, eax; CSize g_sizePrimaryDisplay
0x18047664d  call    cs:__imp_GetSystemMetrics
0x180476654  nop     dword ptr [rax+rax+00h]
0x180476659  mov     ecx, 45h ; 'E'; nIndex
0x18047665e  mov     dword ptr cs:?g_sizeDragMin@@3UtagSIZE@@A, eax; tagSIZE g_sizeDragMin
0x180476664  call    cs:__imp_GetSystemMetrics
0x18047666b  nop     dword ptr [rax+rax+00h]
0x180476670  cmp     cs:?g_fOverrideScrollbarSizes@@3HA, 0; int g_fOverrideScrollbarSizes
0x180476677  mov     dword ptr cs:?g_sizeDragMin@@3UtagSIZE@@A+4, eax; tagSIZE g_sizeDragMin
0x18047667d  mov     eax, 10h
0x180476682  mov     cs:?g_lWidthComboButton@@3JA, eax; long g_lWidthComboButton
0x180476688  jnz     loc_18047684D
0x18047668e  call    ?GetSystemScrollbarSizeWrapper@@YAXAEAVCSize@@@Z; GetSystemScrollbarSizeWrapper(CSize &)
0x180476693  movd    xmm2, dword ptr cs:?g_sizeScrollbar@@3VCSize@@A+4; CSize g_sizeScrollbar
0x18047669b  lea     rcx, ?g_sizeScrollbar@@3VCSize@@A; this
0x1804766a2  movd    xmm1, dword ptr cs:?g_sizeScrollbar@@3VCSize@@A; CSize g_sizeScrollbar
0x1804766aa  xorps   xmm0, xmm0
0x1804766ad  cvtsi2ss xmm0, rsi
0x1804766b2  xor     r9d, r9d; bool
0x1804766b5  cvtdq2ps xmm2, xmm2
0x1804766b8  divss   xmm6, xmm0
0x1804766bc  cvtdq2ps xmm1, xmm1
0x1804766bf  mulss   xmm2, xmm6; float
0x1804766c3  mulss   xmm1, xmm6; float
0x1804766c7  call    ?SetSize@CSize@@QEAAXMM_N@Z; CSize::SetSize(float,float,bool)
0x1804766cc  mov     rax, cs:?g_sizeScrollbar@@3VCSize@@A; CSize g_sizeScrollbar
0x1804766d3  mov     cs:?g_sizeRootScrollbar@@3VCSize@@A, rax; CSize g_sizeRootScrollbar
0x1804766da  mov     ecx, cs:dword_1815BFD54
0x1804766e0  mov     eax, 11h
0x1804766e5  mov     dword ptr cs:?g_sizeOverlayScrollbarDisplay@@3VCSize@@A, eax; CSize g_sizeOverlayScrollbarDisplay
0x1804766eb  mov     dword ptr cs:?g_sizeOverlayScrollbarDisplay@@3VCSize@@A+4, eax; CSize g_sizeOverlayScrollbarDisplay
0x1804766f1  mov     dword ptr cs:?g_sizeRootOverlayScrollbarDisplay@@3VCSize@@A, eax; CSize g_sizeRootOverlayScrollbarDisplay
0x1804766f7  mov     dword ptr cs:?g_sizeRootOverlayScrollbarDisplay@@3VCSize@@A+4, eax; CSize g_sizeRootOverlayScrollbarDisplay
0x1804766fd  movsxd  rax, cs:dword_1815BFD50
0x180476704  shl     rax, 3
0x180476708  dec     ecx
0x18047670a  mov     cs:?g_lScrollGutterRatio@@3JA, 8; long g_lScrollGutterRatio
0x180476714  sar     rax, cl
0x180476717  inc     eax
0x180476719  mov     cs:dword_1815B8D9C, 0Ah
0x180476723  sar     eax, 1
0x180476725  mov     cs:dword_1815C4DD4, eax
0x18047672b  mov     cs:?g_alHimetricFrom8Pixels@@3PAJA, eax; long near * g_alHimetricFrom8Pixels
0x180476731  mov     cs:?g_sizeSystemChar@@3UtagSIZE@@A, 0Ah; tagSIZE g_sizeSystemChar
0x18047673b  call    ?GetSystemFont@@YAPEAUHFONT__@@XZ; GetSystemFont(void)
0x180476740  mov     rsi, rax
0x180476743  test    rax, rax
0x180476746  jz      short loc_18047676A
0x180476748  mov     rcx, [rdi+0F0h]; hdc
0x18047674f  mov     rdx, rax; h
0x180476752  call    cs:__imp_SelectObject
0x180476759  nop     dword ptr [rax+rax+00h]
0x18047675e  mov     rbx, rax
0x180476761  test    rax, rax
0x180476764  jnz     loc_18047686A
0x18047676a  mov     rcx, rsi; ho
0x18047676d  call    cs:__imp_DeleteObject
0x180476774  nop     dword ptr [rax+rax+00h]
0x180476779  call    cs:__imp_GetSystemDefaultLCID
0x180476780  nop     dword ptr [rax+rax+00h]
0x180476785  mov     cs:?g_lcidUserDefault@@3KA, eax; ulong g_lcidUserDefault
0x18047678b  call    cs:__imp_GetUserDefaultLCID
0x180476792  nop     dword ptr [rax+rax+00h]
0x180476797  mov     cs:?g_lcidLocalUserDefault@@3KA, eax; ulong g_lcidLocalUserDefault
0x18047679d  call    cs:__imp_GetACP
0x1804767a4  nop     dword ptr [rax+rax+00h]
0x1804767a9  mov     cs:?g_cpDefault@@3IA, eax; uint g_cpDefault
0x1804767af  call    ?GetSystemNumberSettings@@YAXPEAW4NUMSHAPE@@PEAK@Z; GetSystemNumberSettings(NUMSHAPE *,ulong *)
0x1804767b4  xor     edx, edx; uiParam
0x1804767b6  lea     r8, ?g_fScreenReader@@3HA; pvParam
0x1804767bd  xor     r9d, r9d; fWinIni
0x1804767c0  lea     ecx, [rdx+46h]; uiAction
0x1804767c3  call    cs:__imp_SystemParametersInfoW
0x1804767ca  nop     dword ptr [rax+rax+00h]
0x1804767cf  call    ?GetHighContrastMode@@YAXPEAW4Enum@HighContrastMode@@@Z; GetHighContrastMode(HighContrastMode::Enum *)
0x1804767d4  call    cs:__imp_IsAppThemed
0x1804767db  nop     dword ptr [rax+rax+00h]
0x1804767e0  lea     r8, ?g_fAnimationsEnabled@@3HA; pvParam
0x1804767e7  mov     ecx, 1042h; uiAction
0x1804767ec  test    eax, eax
0x1804767ee  setnz   cs:?g_fIsAppThemed@@3_NA; bool g_fIsAppThemed
0x1804767f5  xor     r9d, r9d; fWinIni
0x1804767f8  xor     edx, edx; uiParam
0x1804767fa  call    cs:__imp_SystemParametersInfoW
0x180476801  nop     dword ptr [rax+rax+00h]
0x180476806  xor     r9d, r9d; fWinIni
0x180476809  lea     r8, ?g_fUIEffectsEnabled@@3HA; pvParam
0x180476810  xor     edx, edx; uiParam
0x180476812  mov     ecx, 103Eh; uiAction
0x180476817  call    cs:__imp_SystemParametersInfoW
0x18047681e  nop     dword ptr [rax+rax+00h]
0x180476823  xor     eax, eax
0x180476825  mov     rcx, [rsp+88h+var_28]
0x18047682a  xor     rcx, rsp; StackCookie
0x18047682d  call    __security_check_cookie
0x180476832  lea     r11, [rsp+88h+var_8]
0x18047683a  mov     rbx, [r11+18h]
0x18047683e  mov     rsi, [r11+20h]
0x180476842  movaps  xmm6, [rsp+88h+var_18]
0x180476847  mov     rsp, r11
0x18047684a  pop     rdi
0x18047684b  retn
0x18047684d  mov     dword ptr cs:?g_sizeScrollbar@@3VCSize@@A, eax; CSize g_sizeScrollbar
0x180476853  mov     dword ptr cs:?g_sizeScrollbar@@3VCSize@@A+4, eax; CSize g_sizeScrollbar
0x180476859  mov     dword ptr cs:?g_sizeRootScrollbar@@3VCSize@@A, eax; CSize g_sizeRootScrollbar
0x18047685f  mov     dword ptr cs:?g_sizeRootScrollbar@@3VCSize@@A+4, eax; CSize g_sizeRootScrollbar
0x180476865  jmp     loc_1804766DA
0x18047686a  mov     rcx, [rdi+0F0h]; hdc
0x180476871  lea     rdx, [rsp+88h+tm]; lptm
0x180476876  call    cs:__imp_GetTextMetricsW
0x18047687d  nop     dword ptr [rax+rax+00h]
0x180476882  test    eax, eax
0x180476884  jz      loc_18047691F
0x18047688a  mov     eax, [rsp+88h+tm.tmAveCharWidth]
0x18047688e  mov     cs:?g_sizeSystemChar@@3UtagSIZE@@A, eax; tagSIZE g_sizeSystemChar
0x180476894  mov     eax, [rsp+88h+tm.tmHeight]
0x180476898  mov     cs:dword_1815B8D9C, eax
0x18047689e  mov     rcx, [rdi+0F0h]; hdc
0x1804768a5  mov     rdx, rbx; h
0x1804768a8  call    cs:__imp_SelectObject
0x1804768af  nop     dword ptr [rax+rax+00h]
0x1804768b4  jmp     loc_18047676A
0x1804768b9  mov     edx, cs:_tls_index
0x1804768bf  mov     rcx, gs:58h
0x1804768c8  mov     eax, 0Ch
0x1804768cd  mov     rcx, [rcx+rdx*8]
0x1804768d1  mov     edx, [rax+rcx]
0x1804768d4  cmp     cs:dword_1815C7148, edx
0x1804768da  jg      loc_180476960
0x1804768e0  cmp     cs:dword_1815C714C, 0
0x1804768e7  jz      loc_1804769AB
0x1804768ed  mov     ecx, 10000019h
0x1804768f2  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1804768f9  nop     dword ptr [rax+rax+00h]
0x1804768fe  test    al, al
0x180476900  jnz     loc_1804769AB
0x180476906  movss   xmm1, cs:__real@3f800000; float
0x18047690e  xor     r8d, r8d; bool
0x180476911  lea     ecx, [r8+60h]; unsigned int
0x180476915  call    ?SetResolutionAtNormalZoom@CUnitInfo@@CAXHM_N@Z; CUnitInfo::SetResolutionAtNormalZoom(int,float,bool)
0x18047691a  jmp     loc_18047661B
0x18047691f  mov     cs:?g_sizeSystemChar@@3UtagSIZE@@A, 0Ah; tagSIZE g_sizeSystemChar
0x180476929  mov     cs:dword_1815B8D9C, 0Ah
0x180476933  jmp     loc_18047689E
0x180476938  xor     ecx, ecx; hdc
0x18047693a  call    cs:__imp_CreateCompatibleDC
0x180476941  nop     dword ptr [rax+rax+00h]
0x180476946  mov     [rdi+0F0h], rax
0x18047694d  test    rax, rax
0x180476950  jnz     loc_1804765FC
0x180476956  mov     eax, 8007000Eh
0x18047695b  jmp     loc_180476825
0x180476960  lea     rcx, dword_1815C7148
0x180476967  call    _Init_thread_header
0x18047696c  cmp     cs:dword_1815C7148, 0FFFFFFFFh
0x180476973  jnz     loc_1804768E0
0x180476979  call    cs:__imp_GetCurrentProcess
0x180476980  nop     dword ptr [rax+rax+00h]
0x180476985  mov     rcx, rax
0x180476988  call    cs:__imp_?IEIsImmersiveProcess@@YAHPEAX@Z; IEIsImmersiveProcess(void *)
0x18047698f  nop     dword ptr [rax+rax+00h]
0x180476994  lea     rcx, dword_1815C7148
0x18047699b  mov     cs:dword_1815C714C, eax
0x1804769a1  call    _Init_thread_footer
0x1804769a6  jmp     loc_1804768E0
0x1804769ab  test    cs:byte_1815BFC78, 2
0x1804769b2  jz      short loc_1804769C6
0x1804769b4  mov     rcx, [rdi+0E8h]
0x1804769bb  mov     rcx, [rcx+60h]; HWND
0x1804769bf  call    ?GetEffectiveDpiWrapper@@YAIPEAUHWND__@@@Z; GetEffectiveDpiWrapper(HWND__ *)
0x1804769c4  jmp     short loc_1804769C8
0x1804769c6  mov     eax, esi
0x1804769c8  xorps   xmm1, xmm1
0x1804769cb  mov     eax, eax
0x1804769cd  cvtsi2ss xmm1, rax
0x1804769d2  divss   xmm1, xmm6
0x1804769d6  jmp     loc_18047690E
```

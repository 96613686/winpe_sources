# InitSystemMetricValues(THREADSTATEUI *)

- ea: `0x180320590`
- end: `0x180320954`
- name: `?InitSystemMetricValues@@YAJPEAUTHREADSTATEUI@@@Z`
- size: `964`
- prototype: `__int64 __fastcall(struct THREADSTATEUI *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d2228`
- `0x1805e2fac`
- `0x1806d3d68`

## callees

- `0x1802267a4`
- `0x180320590`
- `0x18032095c`
- `0x1803209f0`
- `0x180320c7c`
- `0x180320d00`
- `0x180320d34`
- `0x180320db4`
- `0x1808395a4`
- `0x180839614`
- `0x180b47a2c`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!GetUserDefaultLCID` at `0x180320751`
- `KERNEL32!GetUserDefaultLCID` at `0x180320751`
- `KERNEL32!GetACP` at `0x18032075d`
- `KERNEL32!GetACP` at `0x18032075d`
- `KERNEL32!GetCurrentProcess` at `0x1803208fe`
- `KERNEL32!GetCurrentProcess` at `0x1803208fe`
- `GDI32!DeleteObject` at `0x18032073f`
- `GDI32!DeleteObject` at `0x18032073f`
- `GDI32!SelectObject` at `0x18032072a`
- `GDI32!SelectObject` at `0x180320843`
- `GDI32!SelectObject` at `0x18032072a`
- `GDI32!SelectObject` at `0x180320843`
- `GDI32!CreateCompatibleDC` at `0x1803208c5`
- `GDI32!CreateCompatibleDC` at `0x1803208c5`
- `GDI32!GetTextMetricsW` at `0x180320817`
- `GDI32!GetTextMetricsW` at `0x180320817`
- `USER32!GetSystemMetrics` at `0x180320610`
- `USER32!GetSystemMetrics` at `0x18032061a`
- `USER32!GetSystemMetrics` at `0x180320631`
- `USER32!GetSystemMetrics` at `0x180320642`
- `USER32!GetSystemMetrics` at `0x180320610`
- `USER32!GetSystemMetrics` at `0x18032061a`
- `USER32!GetSystemMetrics` at `0x180320631`
- `USER32!GetSystemMetrics` at `0x180320642`
- `USER32!SystemParametersInfoW` at `0x18032077d`
- `USER32!SystemParametersInfoW` at `0x1803207a8`
- `USER32!SystemParametersInfoW` at `0x1803207bf`
- `USER32!SystemParametersInfoW` at `0x18032077d`
- `USER32!SystemParametersInfoW` at `0x1803207a8`
- `USER32!SystemParametersInfoW` at `0x1803207bf`
- `iertutil!__imp_?IEIsImmersiveProcess@@YAHPEAX@Z` at `0x180320907`
- `iertutil!__imp_?IEIsImmersiveProcess@@YAHPEAX@Z` at `0x180320907`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180320883`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180320883`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180320745`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180320745`
- `UXTHEME!IsAppThemed` at `0x180320788`
- `UXTHEME!IsAppThemed` at `0x180320788`

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
  __int64 v16; // rdx
  __int64 v17; // r8
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
  if ( !(_BYTE)word_18158CCD1 )
  {
    if ( dword_181594158 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 12LL) )
    {
      Init_thread_header(&dword_181594158);
      if ( dword_181594158 == -1 )
      {
        CurrentProcess = GetCurrentProcess();
        dword_18159415C = IEIsImmersiveProcess(CurrentProcess);
        Init_thread_footer(&dword_181594158, v16, v17);
      }
    }
    if ( !dword_18159415C || (unsigned __int8)IEConfiguration_GetBool(268435481) )
    {
      if ( (byte_18158CB78 & 2) != 0 )
        EffectiveDpiWrapper = GetEffectiveDpiWrapper(*(HWND *)(*((_QWORD *)a1 + 29) + 96LL));
      else
        EffectiveDpiWrapper = SystemDpiWrapper;
      v14 = (float)EffectiveDpiWrapper / 96.0;
    }
    else
    {
      v14 = FLOAT_1_0;
    }
    CUnitInfo::SetResolutionAtNormalZoom(0x60u, v14, 0);
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
  dword_181585C9C = 10;
  dword_181591CD4 = (int)(((8LL * dword_18158CC50) >> ((unsigned __int8)dword_18158CC54 - 1)) + 1) >> 1;
  LODWORD(g_alHimetricFrom8Pixels) = dword_181591CD4;
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
        dword_181585C9C = tm.tmHeight;
      }
      else
      {
        g_sizeSystemChar.cx = 10;
        dword_181585C9C = 10;
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
0x180320590  mov     r11, rsp
0x180320593  mov     [r11+10h], rbx
0x180320597  mov     [r11+18h], rsi
0x18032059b  mov     [r11+8], rcx
0x18032059f  push    rdi
0x1803205a0  sub     rsp, 80h
0x1803205a7  movaps  [rsp+88h+var_18], xmm6
0x1803205ac  mov     rax, cs:__security_cookie
0x1803205b3  xor     rax, rsp
0x1803205b6  mov     [rsp+88h+var_28], rax
0x1803205bb  xorps   xmm0, xmm0
0x1803205be  mov     rdi, rcx
0x1803205c1  movups  xmmword ptr [rsp+88h+tm.tmOverhang], xmm0
0x1803205c6  movups  xmmword ptr [rsp+88h+tm.tmFirstChar], xmm0
0x1803205cb  movups  xmmword ptr [rsp+88h+tm.tmHeight], xmm0
0x1803205d0  movups  xmmword ptr [rsp+88h+tm.tmExternalLeading], xmm0
0x1803205d5  lock inc cs:?g_cMetricChange@@3JA; long g_cMetricChange
0x1803205dc  mov     rax, [rcx+0F0h]
0x1803205e3  test    rax, rax
0x1803205e6  jz      loc_1803208C3
0x1803205ec  mov     rcx, rax; HDC
0x1803205ef  call    ?GetSystemDpiWrapper@@YAIPEAUHDC__@@@Z; GetSystemDpiWrapper(HDC__ *)
0x1803205f4  cmp     byte ptr cs:word_18158CCD1, 0
0x1803205fb  movss   xmm6, cs:__real@42c00000
0x180320603  mov     esi, eax
0x180320605  jz      loc_18032084E
0x18032060b  mov     ecx, 1; nIndex
0x180320610  call    cs:__imp_GetSystemMetrics
0x180320616  xor     ecx, ecx; nIndex
0x180320618  mov     ebx, eax
0x18032061a  call    cs:__imp_GetSystemMetrics
0x180320620  mov     ecx, 44h ; 'D'; nIndex
0x180320625  mov     dword ptr cs:?g_sizePrimaryDisplay@@3VCSize@@A+4, ebx; CSize g_sizePrimaryDisplay
0x18032062b  mov     dword ptr cs:?g_sizePrimaryDisplay@@3VCSize@@A, eax; CSize g_sizePrimaryDisplay
0x180320631  call    cs:__imp_GetSystemMetrics
0x180320637  mov     ecx, 45h ; 'E'; nIndex
0x18032063c  mov     dword ptr cs:?g_sizeDragMin@@3UtagSIZE@@A, eax; tagSIZE g_sizeDragMin
0x180320642  call    cs:__imp_GetSystemMetrics
0x180320648  cmp     cs:?g_fOverrideScrollbarSizes@@3HA, 0; int g_fOverrideScrollbarSizes
0x18032064f  mov     dword ptr cs:?g_sizeDragMin@@3UtagSIZE@@A+4, eax; tagSIZE g_sizeDragMin
0x180320655  mov     eax, 10h
0x18032065a  mov     cs:?g_lWidthComboButton@@3JA, eax; long g_lWidthComboButton
0x180320660  jnz     loc_1803207EE
0x180320666  call    ?GetSystemScrollbarSizeWrapper@@YAXAEAVCSize@@@Z; GetSystemScrollbarSizeWrapper(CSize &)
0x18032066b  movd    xmm2, dword ptr cs:?g_sizeScrollbar@@3VCSize@@A+4; CSize g_sizeScrollbar
0x180320673  lea     rcx, ?g_sizeScrollbar@@3VCSize@@A; this
0x18032067a  movd    xmm1, dword ptr cs:?g_sizeScrollbar@@3VCSize@@A; CSize g_sizeScrollbar
0x180320682  xorps   xmm0, xmm0
0x180320685  cvtsi2ss xmm0, rsi
0x18032068a  xor     r9d, r9d; bool
0x18032068d  cvtdq2ps xmm2, xmm2
0x180320690  divss   xmm6, xmm0
0x180320694  cvtdq2ps xmm1, xmm1
0x180320697  mulss   xmm2, xmm6; float
0x18032069b  mulss   xmm1, xmm6; float
0x18032069f  call    ?SetSize@CSize@@QEAAXMM_N@Z; CSize::SetSize(float,float,bool)
0x1803206a4  mov     rax, cs:?g_sizeScrollbar@@3VCSize@@A; CSize g_sizeScrollbar
0x1803206ab  mov     cs:?g_sizeRootScrollbar@@3VCSize@@A, rax; CSize g_sizeRootScrollbar
0x1803206b2  mov     ecx, cs:dword_18158CC54
0x1803206b8  mov     eax, 11h
0x1803206bd  mov     dword ptr cs:?g_sizeOverlayScrollbarDisplay@@3VCSize@@A, eax; CSize g_sizeOverlayScrollbarDisplay
0x1803206c3  mov     dword ptr cs:?g_sizeOverlayScrollbarDisplay@@3VCSize@@A+4, eax; CSize g_sizeOverlayScrollbarDisplay
0x1803206c9  mov     dword ptr cs:?g_sizeRootOverlayScrollbarDisplay@@3VCSize@@A, eax; CSize g_sizeRootOverlayScrollbarDisplay
0x1803206cf  mov     dword ptr cs:?g_sizeRootOverlayScrollbarDisplay@@3VCSize@@A+4, eax; CSize g_sizeRootOverlayScrollbarDisplay
0x1803206d5  movsxd  rax, cs:dword_18158CC50
0x1803206dc  shl     rax, 3
0x1803206e0  dec     ecx
0x1803206e2  mov     cs:?g_lScrollGutterRatio@@3JA, 8; long g_lScrollGutterRatio
0x1803206ec  sar     rax, cl
0x1803206ef  inc     eax
0x1803206f1  mov     cs:dword_181585C9C, 0Ah
0x1803206fb  sar     eax, 1
0x1803206fd  mov     cs:dword_181591CD4, eax
0x180320703  mov     cs:?g_alHimetricFrom8Pixels@@3PAJA, eax; long near * g_alHimetricFrom8Pixels
0x180320709  mov     cs:?g_sizeSystemChar@@3UtagSIZE@@A, 0Ah; tagSIZE g_sizeSystemChar
0x180320713  call    ?GetSystemFont@@YAPEAUHFONT__@@XZ; GetSystemFont(void)
0x180320718  mov     rsi, rax
0x18032071b  test    rax, rax
0x18032071e  jz      short loc_18032073C
0x180320720  mov     rcx, [rdi+0F0h]; hdc
0x180320727  mov     rdx, rax; h
0x18032072a  call    cs:__imp_SelectObject
0x180320730  mov     rbx, rax
0x180320733  test    rax, rax
0x180320736  jnz     loc_18032080B
0x18032073c  mov     rcx, rsi; ho
0x18032073f  call    cs:__imp_DeleteObject
0x180320745  call    cs:__imp_GetSystemDefaultLCID
0x18032074b  mov     cs:?g_lcidUserDefault@@3KA, eax; ulong g_lcidUserDefault
0x180320751  call    cs:__imp_GetUserDefaultLCID
0x180320757  mov     cs:?g_lcidLocalUserDefault@@3KA, eax; ulong g_lcidLocalUserDefault
0x18032075d  call    cs:__imp_GetACP
0x180320763  mov     cs:?g_cpDefault@@3IA, eax; uint g_cpDefault
0x180320769  call    ?GetSystemNumberSettings@@YAXPEAW4NUMSHAPE@@PEAK@Z; GetSystemNumberSettings(NUMSHAPE *,ulong *)
0x18032076e  xor     edx, edx; uiParam
0x180320770  lea     r8, ?g_fScreenReader@@3HA; pvParam
0x180320777  xor     r9d, r9d; fWinIni
0x18032077a  lea     ecx, [rdx+46h]; uiAction
0x18032077d  call    cs:__imp_SystemParametersInfoW
0x180320783  call    ?GetHighContrastMode@@YAXPEAW4Enum@HighContrastMode@@@Z; GetHighContrastMode(HighContrastMode::Enum *)
0x180320788  call    cs:__imp_IsAppThemed
0x18032078e  lea     r8, ?g_fAnimationsEnabled@@3HA; pvParam
0x180320795  mov     ecx, 1042h; uiAction
0x18032079a  test    eax, eax
0x18032079c  setnz   cs:?g_fIsAppThemed@@3_NA; bool g_fIsAppThemed
0x1803207a3  xor     r9d, r9d; fWinIni
0x1803207a6  xor     edx, edx; uiParam
0x1803207a8  call    cs:__imp_SystemParametersInfoW
0x1803207ae  xor     r9d, r9d; fWinIni
0x1803207b1  lea     r8, ?g_fUIEffectsEnabled@@3HA; pvParam
0x1803207b8  xor     edx, edx; uiParam
0x1803207ba  mov     ecx, 103Eh; uiAction
0x1803207bf  call    cs:__imp_SystemParametersInfoW
0x1803207c5  xor     eax, eax
0x1803207c7  mov     rcx, [rsp+88h+var_28]
0x1803207cc  xor     rcx, rsp; StackCookie
0x1803207cf  call    __security_check_cookie
0x1803207d4  lea     r11, [rsp+88h+var_8]
0x1803207dc  mov     rbx, [r11+18h]
0x1803207e0  mov     rsi, [r11+20h]
0x1803207e4  movaps  xmm6, [rsp+88h+var_18]
0x1803207e9  mov     rsp, r11
0x1803207ec  pop     rdi
0x1803207ed  retn
0x1803207ee  mov     dword ptr cs:?g_sizeScrollbar@@3VCSize@@A, eax; CSize g_sizeScrollbar
0x1803207f4  mov     dword ptr cs:?g_sizeScrollbar@@3VCSize@@A+4, eax; CSize g_sizeScrollbar
0x1803207fa  mov     dword ptr cs:?g_sizeRootScrollbar@@3VCSize@@A, eax; CSize g_sizeRootScrollbar
0x180320800  mov     dword ptr cs:?g_sizeRootScrollbar@@3VCSize@@A+4, eax; CSize g_sizeRootScrollbar
0x180320806  jmp     loc_1803206B2
0x18032080b  mov     rcx, [rdi+0F0h]; hdc
0x180320812  lea     rdx, [rsp+88h+tm]; lptm
0x180320817  call    cs:__imp_GetTextMetricsW
0x18032081d  test    eax, eax
0x18032081f  jz      loc_1803208AA
0x180320825  mov     eax, [rsp+88h+tm.tmAveCharWidth]
0x180320829  mov     cs:?g_sizeSystemChar@@3UtagSIZE@@A, eax; tagSIZE g_sizeSystemChar
0x18032082f  mov     eax, [rsp+88h+tm.tmHeight]
0x180320833  mov     cs:dword_181585C9C, eax
0x180320839  mov     rcx, [rdi+0F0h]; hdc
0x180320840  mov     rdx, rbx; h
0x180320843  call    cs:__imp_SelectObject
0x180320849  jmp     loc_18032073C
0x18032084e  mov     edx, cs:_tls_index
0x180320854  mov     rcx, gs:58h
0x18032085d  mov     eax, 0Ch
0x180320862  mov     rcx, [rcx+rdx*8]
0x180320866  mov     edx, [rax+rcx]
0x180320869  cmp     cs:dword_181594158, edx
0x18032086f  jg      short loc_1803208E5
0x180320871  cmp     cs:dword_18159415C, 0
0x180320878  jz      loc_180320924
0x18032087e  mov     ecx, 10000019h
0x180320883  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180320889  test    al, al
0x18032088b  jnz     loc_180320924
0x180320891  movss   xmm1, cs:__real@3f800000; float
0x180320899  xor     r8d, r8d; bool
0x18032089c  lea     ecx, [r8+60h]; unsigned int
0x1803208a0  call    ?SetResolutionAtNormalZoom@CUnitInfo@@CAXHM_N@Z; CUnitInfo::SetResolutionAtNormalZoom(int,float,bool)
0x1803208a5  jmp     loc_18032060B
0x1803208aa  mov     cs:?g_sizeSystemChar@@3UtagSIZE@@A, 0Ah; tagSIZE g_sizeSystemChar
0x1803208b4  mov     cs:dword_181585C9C, 0Ah
0x1803208be  jmp     loc_180320839
0x1803208c3  xor     ecx, ecx; hdc
0x1803208c5  call    cs:__imp_CreateCompatibleDC
0x1803208cb  mov     [rdi+0F0h], rax
0x1803208d2  test    rax, rax
0x1803208d5  jnz     loc_1803205EC
0x1803208db  mov     eax, 8007000Eh
0x1803208e0  jmp     loc_1803207C7
0x1803208e5  lea     rcx, dword_181594158
0x1803208ec  call    _Init_thread_header
0x1803208f1  cmp     cs:dword_181594158, 0FFFFFFFFh
0x1803208f8  jnz     loc_180320871
0x1803208fe  call    cs:__imp_GetCurrentProcess
0x180320904  mov     rcx, rax
0x180320907  call    cs:__imp_?IEIsImmersiveProcess@@YAHPEAX@Z; IEIsImmersiveProcess(void *)
0x18032090d  lea     rcx, dword_181594158
0x180320914  mov     cs:dword_18159415C, eax
0x18032091a  call    _Init_thread_footer
0x18032091f  jmp     loc_180320871
0x180320924  test    cs:byte_18158CB78, 2
0x18032092b  jz      short loc_18032093F
0x18032092d  mov     rcx, [rdi+0E8h]
0x180320934  mov     rcx, [rcx+60h]; HWND
0x180320938  call    ?GetEffectiveDpiWrapper@@YAIPEAUHWND__@@@Z; GetEffectiveDpiWrapper(HWND__ *)
0x18032093d  jmp     short loc_180320941
0x18032093f  mov     eax, esi
0x180320941  xorps   xmm1, xmm1
0x180320944  mov     eax, eax
0x180320946  cvtsi2ss xmm1, rax
0x18032094b  divss   xmm1, xmm6
0x18032094f  jmp     loc_180320899
```

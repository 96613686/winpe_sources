# GetTDColorAndSetFont(HWND__ *,ulong *,HFONT__ * *)

- ea: `0x140029518`
- end: `0x140029816`
- name: `?GetTDColorAndSetFont@@YAJPEAUHWND__@@PEAKPEAPEAUHFONT__@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(HWND hWnd, COLORREF *pColor, HFONT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140021e00`

## callees

- `0x140002463`
- `0x140029518`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!MulDiv` at `0x14002972d`
- `KERNEL32!MulDiv` at `0x14002972d`
- `KERNEL32!GetLastError` at `0x14002966a`
- `KERNEL32!GetLastError` at `0x14002967a`
- `KERNEL32!GetLastError` at `0x14002975e`
- `KERNEL32!GetLastError` at `0x140029772`
- `KERNEL32!GetLastError` at `0x14002966a`
- `KERNEL32!GetLastError` at `0x14002967a`
- `KERNEL32!GetLastError` at `0x14002975e`
- `KERNEL32!GetLastError` at `0x140029772`
- `GDI32!CreateFontIndirectW` at `0x140029744`
- `GDI32!CreateFontIndirectW` at `0x140029744`
- `GDI32!GetObjectW` at `0x1400296af`
- `GDI32!GetObjectW` at `0x1400296af`
- `GDI32!GetDeviceCaps` at `0x140029716`
- `GDI32!GetDeviceCaps` at `0x140029716`
- `USER32!SendMessageW` at `0x14002964e`
- `USER32!SendMessageW` at `0x1400297a1`
- `USER32!SendMessageW` at `0x14002964e`
- `USER32!SendMessageW` at `0x1400297a1`
- `USER32!ReleaseDC` at `0x1400297b8`
- `USER32!ReleaseDC` at `0x1400297b8`
- `USER32!GetDC` at `0x14002955b`
- `USER32!GetDC` at `0x14002955b`
- `USER32!GetSysColor` at `0x140029596`
- `USER32!GetSysColor` at `0x140029596`
- `UxTheme!IsAppThemed` at `0x140029583`
- `UxTheme!IsAppThemed` at `0x140029583`
- `UxTheme!GetThemeFont` at `0x1400295d4`
- `UxTheme!GetThemeFont` at `0x1400295d4`
- `UxTheme!OpenThemeData` at `0x140029574`
- `UxTheme!OpenThemeData` at `0x140029574`
- `UxTheme!GetThemeColor` at `0x140029601`
- `UxTheme!GetThemeColor` at `0x140029601`
- `UxTheme!CloseThemeData` at `0x1400297cc`
- `UxTheme!CloseThemeData` at `0x1400297cc`

## string_xrefs

- `0x140029567`: `TaskDialog`
- `0x140029624`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x1400296d5`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall GetTDColorAndSetFont(HWND hWnd, COLORREF *pColor, HFONT *a3)
{
  int ThemeFont; // ebx
  HDC DC; // r15
  HTHEME v8; // rdi
  HRESULT ThemeColor; // eax
  void *v10; // rsi
  signed int LastError; // eax
  int DeviceCaps; // eax
  HFONT v13; // rax
  signed int v14; // eax
  LOGFONTW pv; // [rsp+30h] [rbp-98h] BYREF

  ThemeFont = 0;
  memset_0(&pv, 0, sizeof(pv));
  DC = GetDC(hWnd);
  v8 = OpenThemeData(hWnd, L"TaskDialog");
  if ( IsAppThemed() )
  {
    if ( v8 )
    {
      ThemeColor = GetThemeColor(v8, 2, 0, 3803, pColor);
      ThemeFont = ThemeColor;
      if ( ThemeColor < 0 )
      {
        CEventLogger::LogError(
          (CEventLogger *)L"GetTDColorAndSetFont",
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0xEFDu,
          L"GetTDColorAndSetFont",
          ThemeColor);
        goto LABEL_27;
      }
    }
  }
  else
  {
    *pColor = GetSysColor(18);
  }
  if ( !a3 )
    goto LABEL_27;
  if ( !v8 )
  {
    v10 = (void *)SendMessageW(hWnd, 0x31u, 0, 0);
    if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_16;
    if ( GetLastError() )
    {
      LastError = GetLastError();
      ThemeFont = LastError;
      if ( LastError > 0 )
        ThemeFont = (unsigned __int16)LastError | 0x80070000;
      if ( ThemeFont >= 0 )
      {
        if ( !v10 )
          goto LABEL_21;
LABEL_16:
        if ( !GetObjectW(v10, 92, &pv) )
        {
          CEventLogger::LogError(
            (CEventLogger *)L"GetTDColorAndSetFont",
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
            0xF2Au,
            L"GetTDColorAndSetFont",
            0);
          ThemeFont = -2147467259;
          goto LABEL_27;
        }
        pv.lfWeight = 400;
        DeviceCaps = GetDeviceCaps(DC, 90);
        pv.lfHeight = -MulDiv(12, DeviceCaps, 72);
        goto LABEL_21;
      }
    }
    else
    {
      ThemeFont = -2147467259;
    }
    CEventLogger::LogError(
      (CEventLogger *)L"GetTDColorAndSetFont",
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0xF23u,
      L"GetTDColorAndSetFont",
      ThemeFont);
    goto LABEL_27;
  }
  ThemeFont = GetThemeFont(v8, 0, 2, 0, 210, &pv);
LABEL_21:
  v13 = CreateFontIndirectW(&pv);
  *a3 = v13;
  if ( (((unsigned __int64)v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
LABEL_26:
    SendMessageW(hWnd, 0x30u, (WPARAM)*a3, 1);
    goto LABEL_27;
  }
  if ( GetLastError() )
  {
    v14 = GetLastError();
    ThemeFont = v14;
    if ( v14 > 0 )
      ThemeFont = (unsigned __int16)v14 | 0x80070000;
    if ( ThemeFont >= 0 )
      goto LABEL_26;
  }
  else
  {
    ThemeFont = -2147467259;
  }
  CEventLogger::LogError(
    (CEventLogger *)L"GetTDColorAndSetFont",
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
    0xF3Bu,
    L"GetTDColorAndSetFont",
    ThemeFont);
LABEL_27:
  if ( DC )
    ReleaseDC(hWnd, DC);
  if ( v8 )
    CloseThemeData(v8);
  return (unsigned int)ThemeFont;
}

```

## disassembly

```asm
0x140029518  mov     [rsp+arg_18], rbx
0x14002951d  push    rbp
0x14002951e  push    rsi
0x14002951f  push    rdi
0x140029520  push    r14
0x140029522  push    r15
0x140029524  sub     rsp, 0A0h
0x14002952b  mov     rax, cs:__security_cookie
0x140029532  xor     rax, rsp
0x140029535  mov     [rsp+0C8h+var_38], rax
0x14002953d  mov     r14, r8
0x140029540  mov     rsi, rdx
0x140029543  mov     rbp, rcx
0x140029546  xor     ebx, ebx
0x140029548  xor     edx, edx; Val
0x14002954a  lea     rcx, [rsp+0C8h+pv]; void *
0x14002954f  lea     r8d, [rbx+5Ch]; Size
0x140029553  call    memset_0
0x140029558  mov     rcx, rbp; hWnd
0x14002955b  call    cs:__imp_GetDC
0x140029562  nop     dword ptr [rax+rax+00h]
0x140029567  lea     rdx, pszClassList; "TaskDialog"
0x14002956e  mov     rcx, rbp; hwnd
0x140029571  mov     r15, rax
0x140029574  call    cs:__imp_OpenThemeData
0x14002957b  nop     dword ptr [rax+rax+00h]
0x140029580  mov     rdi, rax
0x140029583  call    cs:__imp_IsAppThemed
0x14002958a  nop     dword ptr [rax+rax+00h]
0x14002958f  test    eax, eax
0x140029591  jnz     short loc_1400295E7
0x140029593  lea     ecx, [rbx+12h]; nIndex
0x140029596  call    cs:__imp_GetSysColor
0x14002959d  nop     dword ptr [rax+rax+00h]
0x1400295a2  mov     [rsi], eax
0x1400295a4  test    r14, r14
0x1400295a7  jz      loc_1400297AD
0x1400295ad  test    rdi, rdi
0x1400295b0  jz      loc_140029641
0x1400295b6  xor     r9d, r9d; iStateId
0x1400295b9  lea     rax, [rsp+0C8h+pv]
0x1400295be  mov     [rsp+0C8h+pFont], rax; pFont
0x1400295c3  xor     edx, edx; hdc
0x1400295c5  mov     rcx, rdi; hTheme
0x1400295c8  mov     [rsp+0C8h+iPropId], 0D2h; iPropId
0x1400295d0  lea     r8d, [r9+2]; iPartId
0x1400295d4  call    cs:__imp_GetThemeFont
0x1400295db  nop     dword ptr [rax+rax+00h]
0x1400295e0  mov     ebx, eax
0x1400295e2  jmp     loc_14002973F
0x1400295e7  test    rdi, rdi
0x1400295ea  jz      short loc_1400295A4
0x1400295ec  xor     r8d, r8d; iStateId
0x1400295ef  mov     qword ptr [rsp+0C8h+iPropId], rsi; pColor
0x1400295f4  mov     r9d, 0EDBh; iPropId
0x1400295fa  mov     rcx, rdi; hTheme
0x1400295fd  lea     edx, [r8+2]; iPartId
0x140029601  call    cs:__imp_GetThemeColor
0x140029608  nop     dword ptr [rax+rax+00h]
0x14002960d  mov     ebx, eax
0x14002960f  test    eax, eax
0x140029611  jns     short loc_1400295A4
0x140029613  mov     dword ptr [rsp+0C8h+pFont], eax; unsigned int
0x140029617  mov     r9d, 0EFDh; unsigned int
0x14002961d  lea     rcx, aGettdcolorands; "GetTDColorAndSetFont"
0x140029624  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002962b  mov     qword ptr [rsp+0C8h+iPropId], rcx; unsigned __int16 *
0x140029630  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140029637  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002963c  jmp     loc_1400297AD
0x140029641  xor     r9d, r9d; lParam
0x140029644  xor     r8d, r8d; wParam
0x140029647  mov     rcx, rbp; hWnd
0x14002964a  lea     edx, [r9+31h]; Msg
0x14002964e  call    cs:__imp_SendMessageW
0x140029655  nop     dword ptr [rax+rax+00h]
0x14002965a  mov     rsi, rax
0x14002965d  lea     rcx, [rax+1]
0x140029661  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140029668  jnz     short loc_1400296A2
0x14002966a  call    cs:__imp_GetLastError
0x140029671  nop     dword ptr [rax+rax+00h]
0x140029676  test    eax, eax
0x140029678  jz      short loc_1400296F2
0x14002967a  call    cs:__imp_GetLastError
0x140029681  nop     dword ptr [rax+rax+00h]
0x140029686  mov     ebx, eax
0x140029688  test    eax, eax
0x14002968a  jle     short loc_140029695
0x14002968c  movzx   ebx, ax
0x14002968f  or      ebx, 80070000h
0x140029695  test    ebx, ebx
0x140029697  js      short loc_1400296F7
0x140029699  test    rsi, rsi
0x14002969c  jz      loc_14002973F
0x1400296a2  lea     r8, [rsp+0C8h+pv]; pv
0x1400296a7  mov     edx, 5Ch ; '\'; c
0x1400296ac  mov     rcx, rsi; h
0x1400296af  call    cs:__imp_GetObjectW
0x1400296b6  nop     dword ptr [rax+rax+00h]
0x1400296bb  test    eax, eax
0x1400296bd  jnz     short loc_140029706
0x1400296bf  lea     rcx, aGettdcolorands; "GetTDColorAndSetFont"
0x1400296c6  mov     dword ptr [rsp+0C8h+pFont], eax; unsigned int
0x1400296ca  mov     r9d, 0F2Ah; unsigned int
0x1400296d0  mov     qword ptr [rsp+0C8h+iPropId], rcx; unsigned __int16 *
0x1400296d5  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x1400296dc  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400296e3  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400296e8  mov     ebx, 80004005h
0x1400296ed  jmp     loc_1400297AD
0x1400296f2  mov     ebx, 80004005h
0x1400296f7  mov     dword ptr [rsp+0C8h+pFont], ebx
0x1400296fb  mov     r9d, 0F23h
0x140029701  jmp     loc_14002961D
0x140029706  mov     edx, 5Ah ; 'Z'; index
0x14002970b  mov     [rsp+0C8h+pv.lfWeight], 190h
0x140029713  mov     rcx, r15; hdc
0x140029716  call    cs:__imp_GetDeviceCaps
0x14002971d  nop     dword ptr [rax+rax+00h]
0x140029722  mov     ecx, 0Ch; nNumber
0x140029727  mov     edx, eax; nNumerator
0x140029729  lea     r8d, [rcx+3Ch]; nDenominator
0x14002972d  call    cs:__imp_MulDiv
0x140029734  nop     dword ptr [rax+rax+00h]
0x140029739  neg     eax
0x14002973b  mov     [rsp+0C8h+pv.lfHeight], eax
0x14002973f  lea     rcx, [rsp+0C8h+pv]; lplf
0x140029744  call    cs:__imp_CreateFontIndirectW
0x14002974b  nop     dword ptr [rax+rax+00h]
0x140029750  mov     [r14], rax
0x140029753  inc     rax
0x140029756  test    rax, 0FFFFFFFFFFFFFFFEh
0x14002975c  jnz     short loc_140029791
0x14002975e  call    cs:__imp_GetLastError
0x140029765  nop     dword ptr [rax+rax+00h]
0x14002976a  test    eax, eax
0x14002976c  jz      loc_140029802
0x140029772  call    cs:__imp_GetLastError
0x140029779  nop     dword ptr [rax+rax+00h]
0x14002977e  mov     ebx, eax
0x140029780  test    eax, eax
0x140029782  jle     short loc_14002978D
0x140029784  movzx   ebx, ax
0x140029787  or      ebx, 80070000h
0x14002978d  test    ebx, ebx
0x14002978f  js      short loc_140029807
0x140029791  mov     r8, [r14]; wParam
0x140029794  mov     r9d, 1; lParam
0x14002979a  mov     rcx, rbp; hWnd
0x14002979d  lea     edx, [r9+2Fh]; Msg
0x1400297a1  call    cs:__imp_SendMessageW
0x1400297a8  nop     dword ptr [rax+rax+00h]
0x1400297ad  test    r15, r15
0x1400297b0  jz      short loc_1400297C4
0x1400297b2  mov     rdx, r15; hDC
0x1400297b5  mov     rcx, rbp; hWnd
0x1400297b8  call    cs:__imp_ReleaseDC
0x1400297bf  nop     dword ptr [rax+rax+00h]
0x1400297c4  test    rdi, rdi
0x1400297c7  jz      short loc_1400297D8
0x1400297c9  mov     rcx, rdi; hTheme
0x1400297cc  call    cs:__imp_CloseThemeData
0x1400297d3  nop     dword ptr [rax+rax+00h]
0x1400297d8  mov     eax, ebx
0x1400297da  mov     rcx, [rsp+0C8h+var_38]
0x1400297e2  xor     rcx, rsp; StackCookie
0x1400297e5  call    __security_check_cookie
0x1400297ea  mov     rbx, [rsp+0C8h+arg_18]
0x1400297f2  add     rsp, 0A0h
0x1400297f9  pop     r15
0x1400297fb  pop     r14
0x1400297fd  pop     rdi
0x1400297fe  pop     rsi
0x1400297ff  pop     rbp
0x140029800  retn
0x140029802  mov     ebx, 80004005h
0x140029807  mov     dword ptr [rsp+0C8h+pFont], ebx
0x14002980b  mov     r9d, 0F3Bh
0x140029811  jmp     loc_14002961D
```

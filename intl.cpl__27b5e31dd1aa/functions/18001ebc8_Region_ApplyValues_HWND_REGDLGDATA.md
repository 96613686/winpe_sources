# Region_ApplyValues(HWND__ *,REGDLGDATA *)

- ea: `0x18001ebc8`
- end: `0x18001ee8a`
- name: `?Region_ApplyValues@@YAHPEAUHWND__@@PEAUREGDLGDATA@@@Z`
- size: `706`
- prototype: `__int64 __fastcall(HWND, struct REGDLGDATA *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x18001e340`

## callees

- `0x18001319c`
- `0x1800157dc`
- `0x180016e00`
- `0x18001e2e8`
- `0x18001e314`
- `0x18001e8c0`
- `0x18001ebc8`
- `0x18001ee90`
- `0x18001f834`
- `0x180020304`
- `0x1800203c4`
- `0x1800254f0`
- `0x1800256cc`
- `0x18002673c`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ecb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ecb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ecda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ecf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ecda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ecf9`
- `Bcp47Langs!GetAppropriateUserLocaleForUserLanguages` at `0x18001ecc5`
- `Bcp47Langs!GetAppropriateUserLocaleForUserLanguages` at `0x18001ecc5`
- `USER32!GetDlgItem` at `0x18001ec30`
- `USER32!GetDlgItem` at `0x18001ec30`
- `USER32!SetCursor` at `0x18001ec16`
- `USER32!SetCursor` at `0x18001edb7`
- `USER32!SetCursor` at `0x18001ee58`
- `USER32!SetCursor` at `0x18001ec16`
- `USER32!SetCursor` at `0x18001edb7`
- `USER32!SetCursor` at `0x18001ee58`
- `USER32!LoadCursorW` at `0x18001ec0d`
- `USER32!LoadCursorW` at `0x18001ec0d`
- `USER32!SendMessageW` at `0x18001ec47`
- `USER32!SendMessageW` at `0x18001ec8f`
- `USER32!SendMessageW` at `0x18001ec47`
- `USER32!SendMessageW` at `0x18001ec8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Region_ApplyValues(HWND a1, struct REGDLGDATA *a2)
{
  HCURSOR CursorW; // rax
  HCURSOR v5; // rsi
  HWND DlgItem; // rbx
  int v7; // edi
  unsigned int v8; // eax
  unsigned int UserLocaleNameIndex; // edi
  const WCHAR *StringRawBuffer; // rax
  const char *v11; // rax
  bool v13; // cl
  BOOL v14; // eax
  HSTRING string[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  if ( *(__int64 *)a2 > 1 )
  {
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v5 = SetCursor(CursorW);
    if ( (*(_BYTE *)a2 & 4) != 0 )
    {
      DlgItem = GetDlgItem(a1, 1021);
      v7 = SendMessageW(DlgItem, 0x147u, 0, 0);
      if ( v7 != -1 )
      {
        wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
          v16,
          "RegionApplyValues_ChangeUserLocale");
        v16[0] = &IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::`vftable';
        IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::StartActivity((IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale *)v16);
        v8 = SendMessageW(DlgItem, 0x150u, v7, 0);
        UserLocaleNameIndex = v8;
        if ( v8 )
        {
          v13 = 1;
          g_fSetUserLocaleBasedOnLanguageListOptOut = 1;
          UserLocaleNameIndex = v8 - 1;
        }
        else
        {
          g_fSetUserLocaleBasedOnLanguageListOptOut = 0;
          WindowsDeleteString(0);
          string[0] = 0;
          if ( (int)GetAppropriateUserLocaleForUserLanguages(string) >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
            UserLocaleNameIndex = Intl_FindUserLocaleNameIndex(StringRawBuffer);
            if ( UserLocaleNameIndex == g_dwLocaleCount )
            {
              v11 = (const char *)WindowsGetStringRawBuffer(string[0], 0);
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x1A6,
                (unsigned int)"shell\\osshell\\cpls\\intl\\regdlg.cpp",
                (const char *)0x80070490LL,
                (int)"%ws",
                v11);
              wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
                v16,
                2147943568LL);
              Windows::Internal::String::~String((Windows::Internal::String *)string);
LABEL_8:
              IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::~RegionApplyValues_ChangeUserLocale((IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale *)v16);
              return 0;
            }
          }
          Windows::Internal::String::~String((Windows::Internal::String *)string);
          v13 = g_fSetUserLocaleBasedOnLanguageListOptOut;
        }
        Intl_SetFormatLabelText(v13, a1, UserLocaleNameIndex);
        if ( g_fSetUserLocaleBasedOnLanguageListOptOut == Intl_GetUserLocalFromLanguageProfileOptOut()
          && UserLocaleNameIndex == UserLocaleIndex
          && UserLocaleNameIndex == RegUserLocaleIndex
          && UserLocaleNameIndex == g_savedLocaleIndex )
        {
          wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
            v16,
            0);
          SetCursor(v5);
          goto LABEL_8;
        }
        IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::Stop(
          (IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale *)v16,
          *(const unsigned __int16 **)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
          *(const unsigned __int16 **)(*((_QWORD *)g_localeInfo + UserLocaleNameIndex) + 8LL),
          !g_fSetUserLocaleBasedOnLanguageListOptOut);
        UserLocaleIndex = UserLocaleNameIndex;
        bShowRtL = IsRtLLocale(*(const unsigned __int16 **)(*((_QWORD *)g_localeInfo + UserLocaleNameIndex) + 8LL));
        v14 = bShowRtL && (*(_WORD *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 16LL) & 0x3FF) != 0xD;
        bShowArabic = v14;
        Region_RevertTempDigitSubst();
        Region_ChangeDigitSubstitution(UserLocaleNameIndex);
        IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::~RegionApplyValues_ChangeUserLocale((IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale *)v16);
      }
    }
    SetCursor(v5);
  }
  return 1;
}

```

## disassembly

```asm
0x18001ebc8  mov     [rsp-8+arg_8], rbx
0x18001ebcd  mov     [rsp-8+arg_10], rsi
0x18001ebd2  push    rbp
0x18001ebd3  push    rdi
0x18001ebd4  push    r14
0x18001ebd6  lea     rbp, [rsp-0A0h]
0x18001ebde  sub     rsp, 1A0h
0x18001ebe5  mov     rax, cs:__security_cookie
0x18001ebec  xor     rax, rsp
0x18001ebef  mov     [rbp+0B0h+var_20], rax
0x18001ebf6  mov     rbx, rdx
0x18001ebf9  mov     r14, rcx
0x18001ebfc  cmp     qword ptr [rdx], 1
0x18001ec00  jle     loc_18001EE5E
0x18001ec06  mov     edx, 7F02h; lpCursorName
0x18001ec0b  xor     ecx, ecx; hInstance
0x18001ec0d  call    cs:__imp_LoadCursorW
0x18001ec13  mov     rcx, rax; hCursor
0x18001ec16  call    cs:__imp_SetCursor
0x18001ec1c  mov     rsi, rax
0x18001ec1f  test    byte ptr [rbx], 4
0x18001ec22  jz      loc_18001EE55
0x18001ec28  mov     edx, 3FDh; nIDDlgItem
0x18001ec2d  mov     rcx, r14; hDlg
0x18001ec30  call    cs:__imp_GetDlgItem
0x18001ec36  mov     rbx, rax
0x18001ec39  xor     r9d, r9d; lParam
0x18001ec3c  xor     r8d, r8d; wParam
0x18001ec3f  mov     edx, 147h; Msg
0x18001ec44  mov     rcx, rax; hWnd
0x18001ec47  call    cs:__imp_SendMessageW
0x18001ec4d  mov     rdi, rax
0x18001ec50  cmp     eax, 0FFFFFFFFh
0x18001ec53  jz      loc_18001EE55
0x18001ec59  lea     rdx, aRegionapplyval; "RegionApplyValues_ChangeUserLocale"
0x18001ec60  lea     rcx, [rsp+1B0h+var_170]
0x18001ec65  call    ??0?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001ec6a  lea     rax, ??_7RegionApplyValues_ChangeUserLocale@IntlCplTraceLoggingTelemetry@@6B@; const IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::`vftable'
0x18001ec71  mov     [rsp+1B0h+var_170], rax
0x18001ec76  lea     rcx, [rsp+1B0h+var_170]; this
0x18001ec7b  call    ?StartActivity@RegionApplyValues_ChangeUserLocale@IntlCplTraceLoggingTelemetry@@QEAAXXZ; IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::StartActivity(void)
0x18001ec80  nop
0x18001ec81  movsxd  r8, edi; wParam
0x18001ec84  xor     r9d, r9d; lParam
0x18001ec87  mov     edx, 150h; Msg
0x18001ec8c  mov     rcx, rbx; hWnd
0x18001ec8f  call    cs:__imp_SendMessageW
0x18001ec95  mov     rdi, rax
0x18001ec98  test    eax, eax
0x18001ec9a  jnz     loc_18001ED6A
0x18001eca0  mov     cs:?g_fSetUserLocaleBasedOnLanguageListOptOut@@3_NA, al; bool g_fSetUserLocaleBasedOnLanguageListOptOut
0x18001eca6  mov     [rsp+1B0h+string], 0
0x18001ecaf  xor     ecx, ecx; string
0x18001ecb1  call    cs:__imp_WindowsDeleteString
0x18001ecb7  mov     [rsp+1B0h+string], 0
0x18001ecc0  lea     rcx, [rsp+1B0h+string]
0x18001ecc5  call    cs:__imp_GetAppropriateUserLocaleForUserLanguages
0x18001eccb  test    eax, eax
0x18001eccd  js      loc_18001ED58
0x18001ecd3  xor     edx, edx; length
0x18001ecd5  mov     rcx, [rsp+1B0h+string]; string
0x18001ecda  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ece0  mov     rcx, rax; lpString2
0x18001ece3  call    ?Intl_FindUserLocaleNameIndex@@YAKPEBG@Z; Intl_FindUserLocaleNameIndex(ushort const *)
0x18001ece8  mov     edi, eax
0x18001ecea  cmp     eax, cs:?g_dwLocaleCount@@3KA; ulong g_dwLocaleCount
0x18001ecf0  jnz     short loc_18001ED58
0x18001ecf2  xor     edx, edx; length
0x18001ecf4  mov     rcx, [rsp+1B0h+string]; string
0x18001ecf9  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ecff  mov     rcx, [rbp+0B8h]; this
0x18001ed06  mov     [rsp+1B0h+var_188], rax; char *
0x18001ed0b  lea     rax, aWs; "%ws"
0x18001ed12  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x18001ed17  mov     ebx, 80070490h
0x18001ed1c  mov     r9d, ebx; char *
0x18001ed1f  lea     r8, aShellOsshellCp_2; "shell\\osshell\\cpls\\intl\\regdlg.cpp"
0x18001ed26  mov     edx, 1A6h; void *
0x18001ed2b  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001ed30  mov     edx, ebx
0x18001ed32  lea     rcx, [rsp+1B0h+var_170]
0x18001ed37  call    ?Stop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001ed3c  lea     rcx, [rsp+1B0h+string]; this
0x18001ed41  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001ed46  nop
0x18001ed47  lea     rcx, [rsp+1B0h+var_170]; this
0x18001ed4c  call    ??1RegionApplyValues_ChangeUserLocale@IntlCplTraceLoggingTelemetry@@QEAA@XZ; IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::~RegionApplyValues_ChangeUserLocale(void)
0x18001ed51  xor     eax, eax
0x18001ed53  jmp     loc_18001EE63
0x18001ed58  lea     rcx, [rsp+1B0h+string]; this
0x18001ed5d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001ed62  mov     cl, cs:?g_fSetUserLocaleBasedOnLanguageListOptOut@@3_NA; bool g_fSetUserLocaleBasedOnLanguageListOptOut
0x18001ed68  jmp     short loc_18001ED74
0x18001ed6a  mov     cl, 1; bool
0x18001ed6c  mov     cs:?g_fSetUserLocaleBasedOnLanguageListOptOut@@3_NA, cl; bool g_fSetUserLocaleBasedOnLanguageListOptOut
0x18001ed72  dec     edi
0x18001ed74  mov     r8d, edi; unsigned int
0x18001ed77  mov     rdx, r14; HWND
0x18001ed7a  call    ?Intl_SetFormatLabelText@@YAX_NPEAUHWND__@@K@Z; Intl_SetFormatLabelText(bool,HWND__ *,ulong)
0x18001ed7f  call    ?Intl_GetUserLocalFromLanguageProfileOptOut@@YA_NXZ; Intl_GetUserLocalFromLanguageProfileOptOut(void)
0x18001ed84  mov     edx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001ed8a  mov     cl, cs:?g_fSetUserLocaleBasedOnLanguageListOptOut@@3_NA; bool g_fSetUserLocaleBasedOnLanguageListOptOut
0x18001ed90  cmp     cl, al
0x18001ed92  jnz     short loc_18001EDBF
0x18001ed94  cmp     edi, edx
0x18001ed96  jnz     short loc_18001EDBF
0x18001ed98  cmp     edi, cs:?RegUserLocaleIndex@@3KA; ulong RegUserLocaleIndex
0x18001ed9e  jnz     short loc_18001EDBF
0x18001eda0  cmp     edi, cs:?g_savedLocaleIndex@@3KA; ulong g_savedLocaleIndex
0x18001eda6  jnz     short loc_18001EDBF
0x18001eda8  xor     edx, edx
0x18001edaa  lea     rcx, [rsp+1B0h+var_170]
0x18001edaf  call    ?Stop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001edb4  mov     rcx, rsi; hCursor
0x18001edb7  call    cs:__imp_SetCursor
0x18001edbd  jmp     short loc_18001ED47
0x18001edbf  test    cl, cl
0x18001edc1  setz    r9b; bool
0x18001edc5  mov     ebx, edi
0x18001edc7  mov     rcx, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001edce  mov     r8, [rcx+rbx*8]
0x18001edd2  mov     rdx, [rcx+rdx*8]
0x18001edd6  mov     r8, [r8+8]; unsigned __int16 *
0x18001edda  mov     rdx, [rdx+8]; unsigned __int16 *
0x18001edde  lea     rcx, [rsp+1B0h+var_170]; this
0x18001ede3  call    ?Stop@RegionApplyValues_ChangeUserLocale@IntlCplTraceLoggingTelemetry@@QEAAXPEBG0_N@Z; IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::Stop(ushort const *,ushort const *,bool)
0x18001ede8  mov     cs:?UserLocaleIndex@@3KA, edi; ulong UserLocaleIndex
0x18001edee  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001edf5  mov     rcx, [rax+rbx*8]
0x18001edf9  mov     rcx, [rcx+8]; unsigned __int16 *
0x18001edfd  call    ?IsRtLLocale@@YAHPEBG@Z; IsRtLLocale(ushort const *)
0x18001ee02  mov     cs:?bShowRtL@@3HA, eax; int bShowRtL
0x18001ee08  test    eax, eax
0x18001ee0a  jz      short loc_18001EE36
0x18001ee0c  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001ee12  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001ee19  mov     rcx, [rax+rcx*8]
0x18001ee1d  movzx   eax, word ptr [rcx+10h]
0x18001ee21  mov     ecx, 3FFh
0x18001ee26  and     ax, cx
0x18001ee29  cmp     ax, 0Dh
0x18001ee2d  jz      short loc_18001EE36
0x18001ee2f  mov     eax, 1
0x18001ee34  jmp     short loc_18001EE38
0x18001ee36  xor     eax, eax
0x18001ee38  mov     cs:?bShowArabic@@3HA, eax; int bShowArabic
0x18001ee3e  call    ?Region_RevertTempDigitSubst@@YAXXZ; Region_RevertTempDigitSubst(void)
0x18001ee43  mov     ecx, edi; unsigned int
0x18001ee45  call    ?Region_ChangeDigitSubstitution@@YAXK@Z; Region_ChangeDigitSubstitution(ulong)
0x18001ee4a  nop
0x18001ee4b  lea     rcx, [rsp+1B0h+var_170]; this
0x18001ee50  call    ??1RegionApplyValues_ChangeUserLocale@IntlCplTraceLoggingTelemetry@@QEAA@XZ; IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::~RegionApplyValues_ChangeUserLocale(void)
0x18001ee55  mov     rcx, rsi; hCursor
0x18001ee58  call    cs:__imp_SetCursor
0x18001ee5e  mov     eax, 1
0x18001ee63  mov     rcx, [rbp+0B0h+var_20]
0x18001ee6a  xor     rcx, rsp; StackCookie
0x18001ee6d  call    __security_check_cookie
0x18001ee72  lea     r11, [rsp+1B0h+var_10]
0x18001ee7a  mov     rbx, [r11+28h]
0x18001ee7e  mov     rsi, [r11+30h]
0x18001ee82  mov     rsp, r11
0x18001ee85  pop     r14
0x18001ee87  pop     rdi
0x18001ee88  pop     rbp
0x18001ee89  retn
```

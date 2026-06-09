# CConsolePropPage::OnChangeIcon(void)

- ea: `0x1400c9c10`
- end: `0x1400c9ebe`
- name: `?OnChangeIcon@CConsolePropPage@@IEAAXXZ`
- size: `686`
- prototype: `void __fastcall(CConsolePropPage *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callees

- `0x14000125c`
- `0x140001aec`
- `0x14000d720`
- `0x14001de00`
- `0x140042dc0`
- `0x140045208`
- `0x14007a864`
- `0x140097eb0`
- `0x1400c9c10`
- `0x1400e9e10`

## import_xrefs

- `USER32!SendMessageW` at `0x1400c9e83`
- `USER32!SendMessageW` at `0x1400c9e83`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@PEBG@Z` at `0x1400c9e59`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@PEBG@Z` at `0x1400c9e59`
- `MFC42u!__imp_?SetModified@CPropertyPage@@QEAAXH@Z` at `0x1400c9e91`
- `MFC42u!__imp_?SetModified@CPropertyPage@@QEAAXH@Z` at `0x1400c9e91`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400c9e9d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400c9e9d`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x1400c9c41`
- `mmcbase!MMC_PickIconDlg` at `0x1400c9de3`
- `mmcbase!MMC_PickIconDlg` at `0x1400c9de3`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400c9c60`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400c9c60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400c9d32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400c9d32`
- `KERNEL32!lstrcmpiW` at `0x1400c9e07`
- `KERNEL32!lstrcmpiW` at `0x1400c9e07`
- `SHELL32!ExtractIconW` at `0x1400c9e2c`
- `SHELL32!ExtractIconW` at `0x1400c9e2c`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=3
void __fastcall CConsolePropPage::OnChangeIcon(CConsolePropPage *this)
{
  __int64 v2; // rdx
  const OLECHAR *v3; // rax
  const OLECHAR *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // r10d
  UINT v11; // r8d
  _QWORD **v12; // rsi
  HICON IconW; // rax
  _QWORD *v14; // r8
  UINT nIconIndex; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+54h] [rbp-ACh] BYREF
  DWORD CurrentProcessId; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+68h] [rbp-98h]
  __int64 v20; // [rsp+78h] [rbp-88h]
  const OLECHAR *v21; // [rsp+80h] [rbp-80h] BYREF
  const OLECHAR *v22; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v23[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v24; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v25; // [rsp+A8h] [rbp-58h]
  _QWORD v26[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v28; // [rsp+C8h] [rbp-38h]
  WCHAR String1[264]; // [rsp+D0h] [rbp-30h] BYREF

  v19 = 0;
  ++mmcerror::SC::s_CallDepth;
  v18 = 3;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)&v18, L"CConsolePropPage::OnChangeIcon");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatsecond>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatsecond>::GetImpl'::`2'::impl) )
  {
    v27 = 0;
    v28 = 7;
    std::wstring::_Eos(v26, 0);
    v24 = 0;
    v25 = 7;
    std::wstring::_Eos(v23, 0);
    v16 = 0;
    GetMMCTelemetryContext(v26, v23, &v16);
    if ( (unsigned int)dword_140157418 > 4 && (unsigned __int8)tlgKeywordOn() )
    {
      v20 = 0x2000000;
      v3 = &WindowName;
      if ( v24 )
      {
        v4 = (const OLECHAR *)v23;
        if ( v25 >= 8 )
          v4 = (const OLECHAR *)v23[0];
      }
      else
      {
        v4 = &WindowName;
      }
      v21 = v4;
      if ( v27 )
      {
        v3 = (const OLECHAR *)v26;
        if ( v28 >= 8 )
          v3 = (const OLECHAR *)v26[0];
      }
      v22 = v3;
      CurrentProcessId = GetCurrentProcessId();
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v5,
        (__int64)&dword_1401356D4,
        v6,
        v7,
        (__int64)&CurrentProcessId,
        &v22,
        &v21);
    }
    LOBYTE(v2) = 1;
    std::wstring::_Tidy(v23, v2, 0);
    LOBYTE(v8) = 1;
    std::wstring::_Tidy(v26, v8, 0);
  }
  nIconIndex = *((_DWORD *)this + 242);
  v9 = StringCchCopyW(String1, 0x104u, *((const unsigned __int16 **)this + 120));
  LODWORD(v18) = 3;
  HIDWORD(v18) = v9;
  if ( v9 >= 0 && MMC_PickIconDlg(*((HWND *)this + 8), String1, v10, (int *)&nIconIndex) )
  {
    v11 = nIconIndex;
    if ( nIconIndex == *((_DWORD *)this + 242) )
    {
      if ( !lstrcmpiW(String1, *((LPCWSTR *)this + 120)) )
        goto LABEL_23;
      v11 = nIconIndex;
    }
    v12 = (_QWORD **)((char *)this + 952);
    IconW = ExtractIconW(*((HINSTANCE *)this + 118), String1, v11);
    CSmartIcon::Attach((CConsolePropPage *)((char *)this + 952), IconW);
    if ( *((_QWORD *)this + 119) && **((_QWORD **)this + 119) )
    {
      *((_BYTE *)this + 973) = 1;
      CString::operator=((char *)this + 960, String1);
      *((_DWORD *)this + 242) = nIconIndex;
      v14 = *v12;
      if ( *v12 )
        v14 = (_QWORD *)*v14;
      SendMessageW(*((HWND *)this + 107), 0x170u, (WPARAM)v14, 0);
      CPropertyPage::SetModified(this, 1);
    }
  }
LABEL_23:
  mmcerror::SC::~SC((mmcerror::SC *)&v18);
}

```

## disassembly

```asm
0x1400c9c10  push    rbp
0x1400c9c12  push    rbx
0x1400c9c13  push    rsi
0x1400c9c14  push    rdi
0x1400c9c15  lea     rbp, [rsp-1F8h]
0x1400c9c1d  sub     rsp, 2F8h
0x1400c9c24  mov     rax, cs:__security_cookie
0x1400c9c2b  xor     rax, rsp
0x1400c9c2e  mov     [rbp+210h+var_30], rax
0x1400c9c35  mov     rbx, rcx
0x1400c9c38  xorps   xmm0, xmm0
0x1400c9c3b  movdqu  [rsp+310h+var_2A8], xmm0
0x1400c9c41  mov     rax, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x1400c9c48  inc     dword ptr [rax]
0x1400c9c4a  mov     esi, 3
0x1400c9c4f  mov     [rsp+310h+var_2B0], rsi
0x1400c9c54  lea     rdx, aCconsoleproppa_0; "CConsolePropPage::OnChangeIcon"
0x1400c9c5b  lea     rcx, [rsp+310h+var_2B0]
0x1400c9c60  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400c9c66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatsecond@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatsecond@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatsecond> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatsecond>::GetImpl(void)'::`2'::impl
0x1400c9c6d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatsecond@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatsecond>::__private_IsEnabled(void)
0x1400c9c72  test    al, al
0x1400c9c74  jz      loc_1400C9D96
0x1400c9c7a  mov     [rbp+210h+var_250], 0
0x1400c9c82  lea     edi, [rsi+4]
0x1400c9c85  mov     [rbp+210h+var_248], rdi
0x1400c9c89  xor     edx, edx
0x1400c9c8b  lea     rcx, [rbp+210h+var_260]
0x1400c9c8f  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1400c9c94  nop
0x1400c9c95  mov     [rbp+210h+var_270], 0
0x1400c9c9d  mov     [rbp+210h+var_268], rdi
0x1400c9ca1  xor     edx, edx
0x1400c9ca3  lea     rcx, [rbp+210h+var_280]
0x1400c9ca7  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1400c9cac  nop
0x1400c9cad  mov     [rsp+310h+var_2BC], 0
0x1400c9cb5  lea     r8, [rsp+310h+var_2BC]
0x1400c9cba  lea     rdx, [rbp+210h+var_280]
0x1400c9cbe  lea     rcx, [rbp+210h+var_260]
0x1400c9cc2  call    ?GetMMCTelemetryContext@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAJ@Z; GetMMCTelemetryContext(std::wstring &,std::wstring &,long &)
0x1400c9cc7  mov     eax, cs:dword_140157418
0x1400c9ccd  cmp     eax, 4
0x1400c9cd0  jbe     loc_1400C9D79
0x1400c9cd6  call    _tlgKeywordOn
0x1400c9cdb  test    al, al
0x1400c9cdd  jz      loc_1400C9D79
0x1400c9ce3  mov     [rsp+310h+var_298], 2000000h
0x1400c9cec  mov     eax, [rsp+310h+var_2BC]
0x1400c9cf0  mov     [rsp+310h+var_2BC], eax
0x1400c9cf4  lea     rax, WindowName
0x1400c9cfb  cmp     [rbp+210h+var_270], 0
0x1400c9d00  jnz     short loc_1400C9D07
0x1400c9d02  mov     rcx, rax
0x1400c9d05  jmp     short loc_1400C9D15
0x1400c9d07  lea     rcx, [rbp+210h+var_280]
0x1400c9d0b  cmp     [rbp+210h+var_268], 8
0x1400c9d10  cmovnb  rcx, [rbp+210h+var_280]
0x1400c9d15  mov     [rbp+210h+var_290], rcx
0x1400c9d19  cmp     [rbp+210h+var_250], 0
0x1400c9d1e  jz      short loc_1400C9D2E
0x1400c9d20  lea     rax, [rbp+210h+var_260]
0x1400c9d24  cmp     [rbp+210h+var_248], 8
0x1400c9d29  cmovnb  rax, [rbp+210h+var_260]
0x1400c9d2e  mov     [rbp+210h+var_288], rax
0x1400c9d32  call    cs:__imp_GetCurrentProcessId
0x1400c9d38  mov     [rsp+310h+var_2B8], eax
0x1400c9d3c  lea     rax, [rsp+310h+var_298]
0x1400c9d41  mov     [rsp+310h+var_2D0], rax
0x1400c9d46  lea     rax, [rsp+310h+var_2BC]
0x1400c9d4b  mov     [rsp+310h+var_2D8], rax
0x1400c9d50  lea     rax, [rbp+210h+var_290]
0x1400c9d54  mov     [rsp+310h+var_2E0], rax
0x1400c9d59  lea     rax, [rbp+210h+var_288]
0x1400c9d5d  mov     [rsp+310h+var_2E8], rax
0x1400c9d62  lea     rax, [rsp+310h+var_2B8]
0x1400c9d67  mov     [rsp+310h+var_2F0], rax
0x1400c9d6c  lea     rdx, dword_1401356D4
0x1400c9d73  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400c9d78  nop
0x1400c9d79  xor     r8d, r8d
0x1400c9d7c  mov     dl, 1
0x1400c9d7e  lea     rcx, [rbp+210h+var_280]
0x1400c9d82  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400c9d87  nop
0x1400c9d88  xor     r8d, r8d
0x1400c9d8b  mov     dl, 1
0x1400c9d8d  lea     rcx, [rbp+210h+var_260]
0x1400c9d91  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400c9d96  mov     eax, [rbx+3C8h]
0x1400c9d9c  mov     [rsp+310h+nIconIndex], eax
0x1400c9da0  lea     rdi, [rbx+3C0h]
0x1400c9da7  mov     r8, [rdi]; unsigned __int16 *
0x1400c9daa  mov     r10d, 104h
0x1400c9db0  mov     edx, r10d; unsigned __int64
0x1400c9db3  lea     rcx, [rbp+210h+String1]; unsigned __int16 *
0x1400c9db7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400c9dbc  mov     dword ptr [rsp+310h+var_2B0], esi
0x1400c9dc0  mov     dword ptr [rsp+310h+var_2B0+4], eax
0x1400c9dc4  test    eax, eax
0x1400c9dc6  jz      short loc_1400C9DD3
0x1400c9dc8  shr     eax, 1Fh
0x1400c9dcb  test    al, al
0x1400c9dcd  jnz     loc_1400C9E98
0x1400c9dd3  lea     r9, [rsp+310h+nIconIndex]
0x1400c9dd8  mov     r8d, r10d
0x1400c9ddb  lea     rdx, [rbp+210h+String1]
0x1400c9ddf  mov     rcx, [rbx+40h]
0x1400c9de3  call    cs:__imp_?MMC_PickIconDlg@@YA_JPEAUHWND__@@PEAGIPEAH@Z; MMC_PickIconDlg(HWND__ *,ushort *,uint,int *)
0x1400c9de9  test    rax, rax
0x1400c9dec  jz      loc_1400C9E98
0x1400c9df2  mov     r8d, [rsp+310h+nIconIndex]
0x1400c9df7  cmp     r8d, [rbx+3C8h]
0x1400c9dfe  jnz     short loc_1400C9E1A
0x1400c9e00  mov     rdx, [rdi]; lpString2
0x1400c9e03  lea     rcx, [rbp+210h+String1]; lpString1
0x1400c9e07  call    cs:__imp_lstrcmpiW
0x1400c9e0d  test    eax, eax
0x1400c9e0f  jz      loc_1400C9E98
0x1400c9e15  mov     r8d, [rsp+310h+nIconIndex]; nIconIndex
0x1400c9e1a  lea     rsi, [rbx+3B8h]
0x1400c9e21  lea     rdx, [rbp+210h+String1]; pszExeFileName
0x1400c9e25  mov     rcx, [rbx+3B0h]; hInst
0x1400c9e2c  call    cs:__imp_ExtractIconW
0x1400c9e32  mov     rdx, rax; HICON
0x1400c9e35  mov     rcx, rsi; this
0x1400c9e38  call    ?Attach@CSmartIcon@@QEAAXPEAUHICON__@@@Z; CSmartIcon::Attach(HICON__ *)
0x1400c9e3d  mov     rax, [rsi]
0x1400c9e40  test    rax, rax
0x1400c9e43  jz      short loc_1400C9E98
0x1400c9e45  cmp     qword ptr [rax], 0
0x1400c9e49  jz      short loc_1400C9E98
0x1400c9e4b  mov     byte ptr [rbx+3CDh], 1
0x1400c9e52  lea     rdx, [rbp+210h+String1]
0x1400c9e56  mov     rcx, rdi
0x1400c9e59  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1400c9e5f  mov     eax, [rsp+310h+nIconIndex]
0x1400c9e63  mov     [rbx+3C8h], eax
0x1400c9e69  mov     r8, [rsi]
0x1400c9e6c  test    r8, r8
0x1400c9e6f  jz      short loc_1400C9E74
0x1400c9e71  mov     r8, [r8]; wParam
0x1400c9e74  xor     r9d, r9d; lParam
0x1400c9e77  mov     edx, 170h; Msg
0x1400c9e7c  mov     rcx, [rbx+358h]; hWnd
0x1400c9e83  call    cs:__imp_SendMessageW
0x1400c9e89  mov     edx, 1
0x1400c9e8e  mov     rcx, rbx
0x1400c9e91  call    cs:__imp_?SetModified@CPropertyPage@@QEAAXH@Z; CPropertyPage::SetModified(int)
0x1400c9e97  nop
0x1400c9e98  lea     rcx, [rsp+310h+var_2B0]
0x1400c9e9d  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400c9ea3  mov     rcx, [rbp+210h+var_30]
0x1400c9eaa  xor     rcx, rsp; StackCookie
0x1400c9ead  call    __security_check_cookie
0x1400c9eb2  add     rsp, 2F8h
0x1400c9eb9  pop     rdi
0x1400c9eba  pop     rsi
0x1400c9ebb  pop     rbx
0x1400c9ebc  pop     rbp
0x1400c9ebd  retn
```

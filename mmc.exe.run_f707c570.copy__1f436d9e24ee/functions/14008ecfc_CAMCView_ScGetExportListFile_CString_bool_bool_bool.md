# CAMCView::ScGetExportListFile(CString &,bool &,bool &,bool &)

- ea: `0x14008ecfc`
- end: `0x14008f12f`
- name: `?ScGetExportListFile@CAMCView@@AEAA?AVSC@mmcerror@@AEAVCString@@AEA_N11@Z`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14008e910`

## callees

- `0x14000125c`
- `0x1400019b8`
- `0x14000c1d0`
- `0x14000d720`
- `0x140027c80`
- `0x140033828`
- `0x140042dc0`
- `0x140067e90`
- `0x14006875c`
- `0x14007a864`
- `0x14008ecfc`
- `0x140097e74`
- `0x1400b5c10`
- `0x1400d1440`
- `0x1400d1670`
- `0x1400e9e10`

## import_xrefs

- `USER32!SendMessageW` at `0x14008ee6f`
- `USER32!SendMessageW` at `0x14008ee6f`
- `USER32!RedrawWindow` at `0x14008eee4`
- `USER32!RedrawWindow` at `0x14008eee4`
- `MFC42u!__imp_??0CString@@QEAA@PEBD@Z` at `0x14008edd5`
- `MFC42u!__imp_??0CString@@QEAA@PEBD@Z` at `0x14008edd5`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14008ed7c`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14008ed97`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14008ed7c`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14008ed97`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14008edc3`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14008edf2`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14008ef0c`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14008f0f7`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14008edc3`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14008edf2`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14008ef0c`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14008f0f7`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x14008ef00`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x14008ef00`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@AEBV0@@Z` at `0x14008edb7`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@AEBV0@@Z` at `0x14008ede6`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@AEBV0@@Z` at `0x14008edb7`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@AEBV0@@Z` at `0x14008ede6`
- `MFC42u!__imp_?GetPathName@CFileDialog@@QEBA?AVCString@@XZ` at `0x14008eef3`
- `MFC42u!__imp_?GetPathName@CFileDialog@@QEBA?AVCString@@XZ` at `0x14008eef3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14008ee22`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14008f103`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14008ee22`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14008f103`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x14008ed53`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x14008eeaa`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14008ee43`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14008f0d6`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14008ee43`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14008f0d6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14008ee17`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14008ee17`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14008ed71`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14008ed71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008f062`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008f062`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=9
__int64 __fastcall CAMCView::ScGetExportListFile(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4, _BYTE *a5, _BYTE *a6)
{
  __int64 v10; // rax
  int v11; // eax
  int v12; // edx
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r9
  struct CWnd *MainWnd; // rax
  __int64 PathName; // rax
  const OLECHAR *v17; // rdi
  const wchar_t *v18; // rsi
  __int64 v19; // rdx
  const OLECHAR *v20; // rax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rdx
  unsigned int v26; // [rsp+20h] [rbp-E0h]
  struct CWnd *v27; // [rsp+38h] [rbp-C8h]
  _BYTE v28[8]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD CurrentProcessId; // [rsp+58h] [rbp-A8h] BYREF
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v31; // [rsp+68h] [rbp-98h] BYREF
  signed __int64 v32; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+78h] [rbp-88h]
  const OLECHAR *v34; // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v36; // [rsp+A0h] [rbp-60h] BYREF
  const OLECHAR *v37; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v38[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v40; // [rsp+C8h] [rbp-38h]
  _QWORD v41[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v42; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v43; // [rsp+E8h] [rbp-18h]
  _BYTE v44[236]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v45; // [rsp+1DCh] [rbp+DCh]
  char v46; // [rsp+9C0h] [rbp+8C0h]

  v34 = (const OLECHAR *)a2;
  v33 = 0;
  ++mmcerror::SC::s_CallDepth;
  v32 = 3;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)&v32, L"CAMCView::ScGetExportListFile");
  CString::CString(&v31);
  LoadStringW((struct CString *)&v31, 0x3423u);
  CString::CString(&CurrentProcessId);
  LoadStringW((struct CString *)&CurrentProcessId, 0x3424u);
  CString::operator+=(&v31, &CurrentProcessId);
  CString::~CString(&CurrentProcessId);
  CString::CString((CString *)&CurrentProcessId, "|");
  CString::operator+=(&v31, &CurrentProcessId);
  CString::~CString(&CurrentProcessId);
  v10 = ScCheckPointers(v38, *(_QWORD *)(a1 + 704), 2147549183LL);
  mmcerror::SC::operator=(&v32, v10);
  mmcerror::SC::~SC((mmcerror::SC *)v38);
  if ( !HIDWORD(v32) || (_DWORD)v32 == 3 && v32 >= 0 )
  {
    v11 = SendMessageW(*(HWND *)(*(_QWORD *)(*(_QWORD *)(a1 + 704) + 128LL) + 64LL), 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
    CSaveFileDialog::CSaveFileDialog((CSaveFileDialog *)v44, v12, v13, v14, v26, v31, v11 != -1, v27);
    if ( CFileDialogEx::DoModal((CFileDialogEx *)v44) == 2 )
    {
      *(_QWORD *)(a2 + 8) = 0;
      *(_QWORD *)(a2 + 16) = 0;
      ++mmcerror::SC::s_CallDepth;
      *(_DWORD *)a2 = 3;
      *(_DWORD *)(a2 + 4) = 1;
    }
    else
    {
      CWaitCursor::CWaitCursor((CWaitCursor *)v28);
      MainWnd = AfxGetMainWnd();
      RedrawWindow(*((HWND *)MainWnd + 8), 0, 0, 0x180u);
      PathName = CFileDialog::GetPathName(v44, &CurrentProcessId);
      CString::operator=(a3, PathName);
      CString::~CString(&CurrentProcessId);
      *a6 = v46 & 1;
      v17 = &WindowName;
      switch ( (_DWORD)v45 )
      {
        case 1:
          *a5 = 1;
          *a4 = 0;
          v18 = L"ANSI_TEXT";
          break;
        case 2:
          *a5 = 0;
          *a4 = 0;
          v18 = L"ANSI_CSV";
          break;
        case 3:
          *a5 = 1;
          *a4 = 1;
          v18 = L"UNICODE_TEXT";
          break;
        case 4:
          *a5 = 0;
          *a4 = 1;
          v18 = L"UNICODE_CSV";
          break;
        default:
          v18 = &WindowName;
          v32 = 0x8000FFFF00000003uLL;
          break;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatfirst>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatfirst>::GetImpl'::`2'::impl)
        && (((_DWORD)v45 - 1) & 0xFFFFFFFD) == 0 )
      {
        v42 = 0;
        v43 = 7;
        std::wstring::_Eos(v41, 0);
        v39 = 0;
        v40 = 7;
        std::wstring::_Eos(v38, 0);
        v30 = 0;
        GetMMCTelemetryContext(v41, v38, &v30);
        if ( (unsigned int)dword_140157418 > 4 && (unsigned __int8)tlgKeywordOn() )
        {
          v35 = 0x2000000;
          v36 = v18;
          if ( v39 )
          {
            v20 = (const OLECHAR *)v38;
            if ( v40 >= 8 )
              v20 = (const OLECHAR *)v38[0];
          }
          else
          {
            v20 = &WindowName;
          }
          v37 = v20;
          if ( v42 )
          {
            v17 = (const OLECHAR *)v41;
            if ( v43 >= 8 )
              v17 = (const OLECHAR *)v41[0];
          }
          v34 = v17;
          CurrentProcessId = GetCurrentProcessId();
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            v21,
            (unsigned int)byte_140134DD9,
            v22,
            v23,
            (__int64)&CurrentProcessId,
            (__int64)&v34,
            (__int64)&v37,
            (__int64)&v30,
            (__int64)&v36,
            (__int64)&v35);
        }
        LOBYTE(v19) = 1;
        std::wstring::_Tidy(v38, v19, 0);
        LOBYTE(v24) = 1;
        std::wstring::_Tidy(v41, v24, 0);
      }
      mmcerror::SC::SC((mmcerror::SC *)a2, (const struct mmcerror::SC *)&v32);
      CWaitCursor::~CWaitCursor((CWaitCursor *)v28);
    }
    CSaveFileDialog::~CSaveFileDialog((CSaveFileDialog *)v44);
  }
  else
  {
    mmcerror::SC::SC((mmcerror::SC *)a2, (const struct mmcerror::SC *)&v32);
  }
  CString::~CString(&v31);
  mmcerror::SC::~SC((mmcerror::SC *)&v32);
  return a2;
}

```

## disassembly

```asm
0x14008ecfc  push    rbp
0x14008ecfe  push    rbx
0x14008ecff  push    rsi
0x14008ed00  push    rdi
0x14008ed01  push    r12
0x14008ed03  push    r13
0x14008ed05  push    r14
0x14008ed07  push    r15
0x14008ed09  lea     rbp, [rsp-8E8h]
0x14008ed11  sub     rsp, 9E8h
0x14008ed18  mov     rax, cs:__security_cookie
0x14008ed1f  xor     rax, rsp
0x14008ed22  mov     [rbp+920h+var_50], rax
0x14008ed29  mov     rsi, r9
0x14008ed2c  mov     r15, r8
0x14008ed2f  mov     rbx, rdx
0x14008ed32  mov     rdi, rcx
0x14008ed35  mov     [rbp+920h+var_998], rdx
0x14008ed39  mov     r14, [rbp+920h+arg_20]
0x14008ed40  mov     r12, [rbp+920h+arg_28]
0x14008ed47  xor     r13d, r13d
0x14008ed4a  xorps   xmm0, xmm0
0x14008ed4d  movdqu  [rsp+0A20h+var_9A8], xmm0
0x14008ed53  mov     rax, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x14008ed5a  inc     dword ptr [rax]
0x14008ed5c  mov     [rsp+0A20h+var_9B0], 3
0x14008ed65  lea     rdx, aCamcviewScgete; "CAMCView::ScGetExportListFile"
0x14008ed6c  lea     rcx, [rsp+0A20h+var_9B0]
0x14008ed71  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14008ed77  lea     rcx, [rsp+0A20h+var_9B8]
0x14008ed7c  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x14008ed82  nop
0x14008ed83  mov     edx, 3423h; unsigned int
0x14008ed88  lea     rcx, [rsp+0A20h+var_9B8]; struct CString *
0x14008ed8d  call    ?LoadStringW@@YAHAEAVCString@@I@Z; LoadStringW(CString &,uint)
0x14008ed92  lea     rcx, [rsp+0A20h+var_9C8]
0x14008ed97  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x14008ed9d  nop
0x14008ed9e  mov     edx, 3424h; unsigned int
0x14008eda3  lea     rcx, [rsp+0A20h+var_9C8]; struct CString *
0x14008eda8  call    ?LoadStringW@@YAHAEAVCString@@I@Z; LoadStringW(CString &,uint)
0x14008edad  lea     rdx, [rsp+0A20h+var_9C8]
0x14008edb2  lea     rcx, [rsp+0A20h+var_9B8]
0x14008edb7  call    cs:__imp_??YCString@@QEAAAEBV0@AEBV0@@Z; CString::operator+=(CString const &)
0x14008edbd  nop
0x14008edbe  lea     rcx, [rsp+0A20h+var_9C8]
0x14008edc3  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14008edc9  lea     rdx, asc_140114184; "|"
0x14008edd0  lea     rcx, [rsp+0A20h+var_9C8]
0x14008edd5  call    cs:__imp_??0CString@@QEAA@PEBD@Z; CString::CString(char const *)
0x14008eddb  nop
0x14008eddc  lea     rdx, [rsp+0A20h+var_9C8]
0x14008ede1  lea     rcx, [rsp+0A20h+var_9B8]
0x14008ede6  call    cs:__imp_??YCString@@QEAAAEBV0@AEBV0@@Z; CString::operator+=(CString const &)
0x14008edec  nop
0x14008eded  lea     rcx, [rsp+0A20h+var_9C8]
0x14008edf2  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14008edf8  mov     r8d, 8000FFFFh
0x14008edfe  mov     rdx, [rdi+2C0h]
0x14008ee05  lea     rcx, [rbp+920h+var_970]
0x14008ee09  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x14008ee0e  nop
0x14008ee0f  mov     rdx, rax
0x14008ee12  lea     rcx, [rsp+0A20h+var_9B0]
0x14008ee17  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14008ee1d  nop
0x14008ee1e  lea     rcx, [rbp+920h+var_970]
0x14008ee22  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14008ee28  mov     eax, dword ptr [rsp+0A20h+var_9B0+4]
0x14008ee2c  test    eax, eax
0x14008ee2e  jz      short loc_14008EE4E
0x14008ee30  cmp     dword ptr [rsp+0A20h+var_9B0], 3
0x14008ee35  jnz     short loc_14008EE3B
0x14008ee37  test    eax, eax
0x14008ee39  jns     short loc_14008EE4E
0x14008ee3b  lea     rdx, [rsp+0A20h+var_9B0]
0x14008ee40  mov     rcx, rbx
0x14008ee43  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14008ee49  jmp     loc_14008F0F2
0x14008ee4e  mov     rax, [rdi+2C0h]
0x14008ee55  mov     rcx, [rax+80h]
0x14008ee5c  mov     r9d, 2; lParam
0x14008ee62  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x14008ee66  mov     edx, 100Ch; Msg
0x14008ee6b  mov     rcx, [rcx+40h]; hWnd
0x14008ee6f  call    cs:__imp_SendMessageW
0x14008ee75  cmp     eax, 0FFFFFFFFh
0x14008ee78  setnz   al
0x14008ee7b  mov     [rsp+0A20h+var_9F0], al; bool
0x14008ee7f  mov     rax, [rsp+0A20h+var_9B8]
0x14008ee84  mov     [rsp+0A20h+var_9F8], rax; unsigned __int16 *
0x14008ee89  lea     rcx, [rbp+920h+var_930]; this
0x14008ee8d  call    ??0CSaveFileDialog@@QEAA@HPEBG0K0_NPEAVCWnd@@@Z; CSaveFileDialog::CSaveFileDialog(int,ushort const *,ushort const *,ulong,ushort const *,bool,CWnd *)
0x14008ee92  nop
0x14008ee93  lea     rcx, [rbp+920h+var_930]; this
0x14008ee97  call    ?DoModal@CFileDialogEx@@UEAA_JXZ; CFileDialogEx::DoModal(void)
0x14008ee9c  cmp     rax, 2
0x14008eea0  jnz     short loc_14008EEC5
0x14008eea2  mov     [rbx+8], r13
0x14008eea6  mov     [rbx+10h], r13
0x14008eeaa  mov     rax, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x14008eeb1  inc     dword ptr [rax]
0x14008eeb3  mov     dword ptr [rbx], 3
0x14008eeb9  mov     dword ptr [rbx+4], 1
0x14008eec0  jmp     loc_14008F0E8
0x14008eec5  lea     rcx, [rsp+0A20h+var_9D0]; this
0x14008eeca  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x14008eecf  nop
0x14008eed0  call    ?AfxGetMainWnd@@YAPEAVCWnd@@XZ; AfxGetMainWnd(void)
0x14008eed5  mov     r9d, 180h; flags
0x14008eedb  xor     r8d, r8d; hrgnUpdate
0x14008eede  xor     edx, edx; lprcUpdate
0x14008eee0  mov     rcx, [rax+40h]; hWnd
0x14008eee4  call    cs:__imp_RedrawWindow
0x14008eeea  lea     rdx, [rsp+0A20h+var_9C8]
0x14008eeef  lea     rcx, [rbp+920h+var_930]
0x14008eef3  call    cs:__imp_?GetPathName@CFileDialog@@QEBA?AVCString@@XZ; CFileDialog::GetPathName(void)
0x14008eef9  nop
0x14008eefa  mov     rdx, rax
0x14008eefd  mov     rcx, r15
0x14008ef00  call    cs:__imp_??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x14008ef06  nop
0x14008ef07  lea     rcx, [rsp+0A20h+var_9C8]
0x14008ef0c  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14008ef12  mov     al, [rbp+920h+var_60]
0x14008ef18  and     al, 1
0x14008ef1a  mov     [r12], al
0x14008ef1e  mov     rcx, [rbp+920h+var_844]
0x14008ef25  lea     rdi, WindowName
0x14008ef2c  sub     ecx, 1
0x14008ef2f  jz      short loc_14008EF83
0x14008ef31  sub     ecx, 1
0x14008ef34  jz      short loc_14008EF74
0x14008ef36  sub     ecx, 1
0x14008ef39  jz      short loc_14008EF64
0x14008ef3b  cmp     ecx, 1
0x14008ef3e  jz      short loc_14008EF55
0x14008ef40  mov     rsi, rdi
0x14008ef43  mov     dword ptr [rsp+0A20h+var_9B0], 3
0x14008ef4b  mov     dword ptr [rsp+0A20h+var_9B0+4], 8000FFFFh
0x14008ef53  jmp     short loc_14008EF91
0x14008ef55  mov     [r14], r13b
0x14008ef58  mov     byte ptr [rsi], 1
0x14008ef5b  lea     rsi, aUnicodeCsv; "UNICODE_CSV"
0x14008ef62  jmp     short loc_14008EF91
0x14008ef64  mov     byte ptr [r14], 1
0x14008ef68  mov     byte ptr [rsi], 1
0x14008ef6b  lea     rsi, aUnicodeText; "UNICODE_TEXT"
0x14008ef72  jmp     short loc_14008EF91
0x14008ef74  mov     [r14], r13b
0x14008ef77  mov     [rsi], r13b
0x14008ef7a  lea     rsi, aAnsiCsv; "ANSI_CSV"
0x14008ef81  jmp     short loc_14008EF91
0x14008ef83  mov     byte ptr [r14], 1
0x14008ef87  mov     [rsi], r13b
0x14008ef8a  lea     rsi, aAnsiText; "ANSI_TEXT"
0x14008ef91  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatfirst@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatfirst@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatfirst> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatfirst>::GetImpl(void)'::`2'::impl
0x14008ef98  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatfirst@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatfirst>::__private_IsEnabled(void)
0x14008ef9d  test    al, al
0x14008ef9f  jz      loc_14008F0CE
0x14008efa5  mov     eax, dword ptr [rbp+920h+var_844]
0x14008efab  dec     eax
0x14008efad  test    eax, 0FFFFFFFDh
0x14008efb2  jnz     loc_14008F0CE
0x14008efb8  mov     [rbp+920h+var_940], r13
0x14008efbc  mov     r14d, 7
0x14008efc2  mov     [rbp+920h+var_938], r14
0x14008efc6  xor     edx, edx
0x14008efc8  lea     rcx, [rbp+920h+var_950]
0x14008efcc  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x14008efd1  nop
0x14008efd2  mov     [rbp+920h+var_960], r13
0x14008efd6  mov     [rbp+920h+var_958], r14
0x14008efda  xor     edx, edx
0x14008efdc  lea     rcx, [rbp+920h+var_970]
0x14008efe0  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x14008efe5  nop
0x14008efe6  mov     [rsp+0A20h+var_9C0], r13d
0x14008efeb  lea     r8, [rsp+0A20h+var_9C0]
0x14008eff0  lea     rdx, [rbp+920h+var_970]
0x14008eff4  lea     rcx, [rbp+920h+var_950]
0x14008eff8  call    ?GetMMCTelemetryContext@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAJ@Z; GetMMCTelemetryContext(std::wstring &,std::wstring &,long &)
0x14008effd  mov     eax, cs:dword_140157418
0x14008f003  cmp     eax, 4
0x14008f006  jbe     loc_14008F0B1
0x14008f00c  call    _tlgKeywordOn
0x14008f011  test    al, al
0x14008f013  jz      loc_14008F0B1
0x14008f019  mov     [rbp+920h+var_988], 2000000h
0x14008f021  mov     [rbp+920h+var_980], rsi
0x14008f025  mov     eax, [rsp+0A20h+var_9C0]
0x14008f029  mov     [rsp+0A20h+var_9C0], eax
0x14008f02d  cmp     [rbp+920h+var_960], r13
0x14008f031  jnz     short loc_14008F038
0x14008f033  mov     rax, rdi
0x14008f036  jmp     short loc_14008F046
0x14008f038  lea     rax, [rbp+920h+var_970]
0x14008f03c  cmp     [rbp+920h+var_958], 8
0x14008f041  cmovnb  rax, [rbp+920h+var_970]
0x14008f046  mov     [rbp+920h+var_978], rax
0x14008f04a  cmp     [rbp+920h+var_940], r13
0x14008f04e  jz      short loc_14008F05E
0x14008f050  lea     rdi, [rbp+920h+var_950]
0x14008f054  cmp     [rbp+920h+var_938], 8
0x14008f059  cmovnb  rdi, [rbp+920h+var_950]
0x14008f05e  mov     [rbp+920h+var_998], rdi
0x14008f062  call    cs:__imp_GetCurrentProcessId
0x14008f068  mov     [rsp+0A20h+var_9C8], eax
0x14008f06c  lea     rax, [rbp+920h+var_988]
0x14008f070  mov     [rsp+0A20h+var_9D8], rax
0x14008f075  lea     rax, [rbp+920h+var_980]
0x14008f079  mov     [rsp+0A20h+var_9E0], rax
0x14008f07e  lea     rax, [rsp+0A20h+var_9C0]
0x14008f083  mov     [rsp+0A20h+var_9E8], rax
0x14008f088  lea     rax, [rbp+920h+var_978]
0x14008f08c  mov     qword ptr [rsp+0A20h+var_9F0], rax
0x14008f091  lea     rax, [rbp+920h+var_998]
0x14008f095  mov     [rsp+0A20h+var_9F8], rax
0x14008f09a  lea     rax, [rsp+0A20h+var_9C8]
0x14008f09f  mov     [rsp+0A20h+var_A00], rax
0x14008f0a4  lea     rdx, byte_140134DD9
0x14008f0ab  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@434AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14008f0b0  nop
0x14008f0b1  xor     r8d, r8d
0x14008f0b4  mov     dl, 1
0x14008f0b6  lea     rcx, [rbp+920h+var_970]
0x14008f0ba  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14008f0bf  nop
0x14008f0c0  xor     r8d, r8d
0x14008f0c3  mov     dl, 1
0x14008f0c5  lea     rcx, [rbp+920h+var_950]
0x14008f0c9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14008f0ce  lea     rdx, [rsp+0A20h+var_9B0]
0x14008f0d3  mov     rcx, rbx
0x14008f0d6  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14008f0dc  nop
0x14008f0dd  lea     rcx, [rsp+0A20h+var_9D0]; this
0x14008f0e2  call    ??1CWaitCursor@@QEAA@XZ; CWaitCursor::~CWaitCursor(void)
0x14008f0e7  nop
0x14008f0e8  lea     rcx, [rbp+920h+var_930]; this
0x14008f0ec  call    ??1CSaveFileDialog@@UEAA@XZ; CSaveFileDialog::~CSaveFileDialog(void)
0x14008f0f1  nop
0x14008f0f2  lea     rcx, [rsp+0A20h+var_9B8]
0x14008f0f7  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14008f0fd  nop
0x14008f0fe  lea     rcx, [rsp+0A20h+var_9B0]
0x14008f103  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14008f109  mov     rax, rbx
0x14008f10c  mov     rcx, [rbp+920h+var_50]
0x14008f113  xor     rcx, rsp; StackCookie
0x14008f116  call    __security_check_cookie
0x14008f11b  add     rsp, 9E8h
0x14008f122  pop     r15
0x14008f124  pop     r14
0x14008f126  pop     r13
0x14008f128  pop     r12
0x14008f12a  pop     rdi
0x14008f12b  pop     rsi
0x14008f12c  pop     rbx
0x14008f12d  pop     rbp
0x14008f12e  retn
```

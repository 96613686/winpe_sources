# CDocument::OnFileSendMail(void)

- ea: `0x18022c770`
- end: `0x18022cc65`
- name: `?OnFileSendMail@CDocument@@IEAAXXZ`
- size: `1269`
- prototype: `void __fastcall(CDocument *this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting`

## callers

- `0x18022cd90`

## callees

- `0x18000df50`
- `0x180078e7c`
- `0x1800dafb8`
- `0x180139860`
- `0x180153990`
- `0x1801d6b60`
- `0x1801d7170`
- `0x1801d7400`
- `0x1801d74b0`
- `0x1801e77f0`
- `0x180224d98`
- `0x18022c770`
- `0x180231d10`
- `0x180231d70`
- `0x1802373b0`
- `0x180296d00`
- `0x1802b6790`
- `0x1802b67c0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18022cc47`
- `KERNEL32!GetLastError` at `0x18022cc47`
- `KERNEL32!GetProcAddress` at `0x18022c80a`
- `KERNEL32!GetProcAddress` at `0x18022c80a`
- `KERNEL32!DeleteFileW` at `0x18022cc2c`
- `KERNEL32!DeleteFileW` at `0x18022cc2c`
- `KERNEL32!GetTempPathW` at `0x18022c8d4`
- `KERNEL32!GetTempPathW` at `0x18022c8d4`
- `KERNEL32!WideCharToMultiByte` at `0x18022c973`
- `KERNEL32!WideCharToMultiByte` at `0x18022caf4`
- `KERNEL32!WideCharToMultiByte` at `0x18022c973`
- `KERNEL32!WideCharToMultiByte` at `0x18022caf4`
- `VCRUNTIME140!memset` at `0x18022cb05`
- `VCRUNTIME140!memset` at `0x18022cb32`
- `VCRUNTIME140!memset` at `0x18022cb05`
- `VCRUNTIME140!memset` at `0x18022cb32`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18022ca5b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18022ca6b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18022ca5b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18022ca6b`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x18022ca88`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x18022ca88`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18022c89f`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18022c9a8`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18022c89f`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18022c9a8`
- `USER32!SetFocus` at `0x18022cb80`
- `USER32!SetFocus` at `0x18022cb80`
- `USER32!SetActiveWindow` at `0x18022cbc4`
- `USER32!SetActiveWindow` at `0x18022cbce`
- `USER32!SetActiveWindow` at `0x18022cbc4`
- `USER32!SetActiveWindow` at `0x18022cbce`
- `USER32!EnableWindow` at `0x18022cbf0`
- `USER32!EnableWindow` at `0x18022cbf0`
- `USER32!SetCapture` at `0x18022cb70`
- `USER32!SetCapture` at `0x18022cb70`
- `USER32!ReleaseCapture` at `0x18022cbab`
- `USER32!ReleaseCapture` at `0x18022cbab`
- `SHLWAPI!PathFindExtensionW` at `0x18022c9c8`
- `SHLWAPI!PathFindExtensionW` at `0x18022c9c8`

## string_xrefs

- `0x18022c7e4`: `MAPI32.DLL`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=3
void __fastcall CDocument::OnFileSendMail(CDocument *this)
{
  AFX_MODULE_STATE *ModuleState; // rax
  CNoTrackObject *Data; // rax
  CNoTrackObject *v4; // rbx
  HMODULE SystemLibraryUsingFullPath; // rax
  unsigned int v6; // ecx
  FARPROC ProcAddress; // r12
  int v8; // r15d
  errno_t v9; // eax
  int v10; // edi
  int v11; // ebx
  wchar_t *m_pszData; // rcx
  errno_t v13; // eax
  const wchar_t *ExtensionW; // rax
  _QWORD *v15; // rax
  int v16; // ebx
  wchar_t *v17; // rdx
  wchar_t *v18; // rax
  CDocTemplate *m_pDocTemplate; // rcx
  size_t v20; // rbx
  errno_t v21; // eax
  HWND__ *SafeOwner; // rax
  CWnd *v23; // rbx
  HWND v24; // rax
  int v25; // edi
  HWND v26; // rax
  DWORD LastError; // eax
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > wait; // [rsp+48h] [rbp-C0h] OVERLAPPED BYREF
  MapiFileDesc fileDesc; // [rsp+50h] [rbp-B8h] BYREF
  MapiMessage message; // [rsp+80h] [rbp-88h] BYREF
  wchar_t szTempName[260]; // [rsp+E0h] [rbp-28h] BYREF
  wchar_t szTitle[264]; // [rsp+2F0h] [rbp+1E8h] BYREF
  CHAR szTempNameA[272]; // [rsp+500h] [rbp+3F8h] BYREF
  CHAR szTitleA[272]; // [rsp+610h] [rbp+508h] BYREF
  wchar_t szPath[268]; // [rsp+720h] [rbp+618h] BYREF

  ModuleState = AfxGetModuleState();
  CCmdTarget::BeginWaitCursor(ModuleState->m_pCurrentWinApp);
  Data = CProcessLocalObject::GetData(&_afxMailState, CProcessLocal<_AFX_MAIL_STATE>::CreateObject);
  v4 = Data;
  if ( !Data )
    goto LABEL_43;
  SystemLibraryUsingFullPath = (HMODULE)Data[1].__vftable;
  if ( !SystemLibraryUsingFullPath )
  {
    SystemLibraryUsingFullPath = ATL::AtlLoadSystemLibraryUsingFullPath(L"MAPI32.DLL");
    v4[1].__vftable = (CNoTrackObject_vtbl *)SystemLibraryUsingFullPath;
    if ( !SystemLibraryUsingFullPath )
    {
      v6 = 61840;
LABEL_7:
      AfxMessageBox(v6, 0, 0xFFFFFFFF);
      goto LABEL_8;
    }
  }
  ProcAddress = GetProcAddress(SystemLibraryUsingFullPath, "MAPISendMail");
  if ( !ProcAddress )
  {
    v6 = 61841;
    goto LABEL_7;
  }
  v8 = 0;
  if ( !*((_DWORD *)this->m_strPathName.m_pszData - 4) || this->IsModified(this) )
  {
    GetTempPathW(0x104u, &szPath[4]);
    AfxGetTempFileName(&szPath[4], L"afx", &szTempName[4], 0x104u);
    v10 = this->IsModified(this);
    v11 = this->DoSave(this, &szTempName[4], 0);
    this->SetModifiedFlag(this, v10);
    if ( !v11 )
      goto LABEL_8;
    v8 = 1;
  }
  else
  {
    v9 = wcsncpy_s(&szTempName[4], 0x104u, this->m_strPathName.m_pszData, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v9 )
    {
      if ( v9 == 12 )
        goto LABEL_46;
      if ( v9 != 80 )
        goto LABEL_43;
    }
  }
  WideCharToMultiByte(3u, 0, &szTempName[4], -1, &szTempNameA[8], 260, 0, 0);
  m_pszData = this->m_strPathName.m_pszData;
  if ( *((_DWORD *)m_pszData - 4) )
  {
    AfxGetFileName(m_pszData, &szTitle[4], 0x104u);
    goto LABEL_34;
  }
  v13 = wcsncpy_s(&szTitle[4], 0x104u, this->m_strTitle.m_pszData, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v13 )
  {
    if ( v13 != 12 )
    {
      if ( v13 == 80 )
        goto LABEL_22;
LABEL_43:
      AfxThrowInvalidArgException();
    }
LABEL_46:
    AfxThrowMemoryException();
  }
LABEL_22:
  ExtensionW = PathFindExtensionW(this->m_strTitle.m_pszData);
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &wait,
    ExtensionW);
  v16 = *(_DWORD *)(*v15 - 16LL);
  v17 = wait.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)wait.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 8LL))(*(_QWORD *)v17);
  if ( !v16 )
  {
    v18 = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
    wait.m_pszData = v18;
    m_pDocTemplate = this->m_pDocTemplate;
    if ( m_pDocTemplate )
    {
      if ( m_pDocTemplate->GetDocString(m_pDocTemplate, &wait, filterExt) )
      {
        v20 = wcslen(wait.m_pszData);
        if ( v20 + wcslen(&szTitle[4]) < 0x104 )
        {
          v21 = wcscat_s(&szTitle[4], 0x104u, wait.m_pszData);
          if ( v21 )
          {
            if ( v21 == 12 )
              AfxThrowMemoryException();
            if ( v21 != 80 )
LABEL_45:
              AfxThrowInvalidArgException();
          }
        }
      }
      v18 = wait.m_pszData;
    }
    if ( _InterlockedDecrement((volatile signed __int32 *)v18 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v18 - 3) + 8LL))(*((_QWORD *)v18 - 3));
  }
LABEL_34:
  WideCharToMultiByte(3u, 0, &szTitle[4], -1, &szTitleA[8], 260, 0, 0);
  memset(&fileDesc.nPosition, 0, sizeof(MapiFileDesc));
  LODWORD(fileDesc.lpszPathName) = -1;
  fileDesc.lpszFileName = &szTempNameA[8];
  fileDesc.lpFileType = &szTitleA[8];
  memset(&message.lpszSubject, 0, sizeof(MapiMessage));
  LODWORD(message.lpFiles) = 1;
  *(_QWORD *)szTempName = &fileDesc.nPosition;
  AfxGetModuleState();
  CWinApp::DoEnableModeless(0);
  SafeOwner = CWnd::GetSafeOwner_(0, (HWND__ **)&wait);
  v23 = CWnd::FromHandle(SafeOwner);
  v24 = SetCapture(v23->m_hWnd);
  CWnd::FromHandle(v24);
  SetFocus(0);
  v23->m_nFlags |= 4u;
  v25 = ((__int64 (__fastcall *)(_QWORD, HWND__ *, char **, __int64, _DWORD))ProcAddress)(
          0,
          v23->m_hWnd,
          &message.lpszSubject,
          9,
          0);
  ReleaseCapture();
  v23->m_nFlags &= ~4u;
  CWnd::EnableWindow(v23, 1);
  SetActiveWindow(0);
  v26 = SetActiveWindow(v23->m_hWnd);
  CWnd::FromHandle(v26);
  CWnd::SetFocus(v23);
  if ( wait.m_pszData )
    EnableWindow((HWND)wait.m_pszData, 1);
  AfxGetModuleState();
  CWinApp::DoEnableModeless(1);
  if ( (v25 & 0xFFFFFFFC) != 0 || v25 == 2 )
    AfxMessageBox(0xF192u, 0, 0xFFFFFFFF);
  if ( v8 && !DeleteFileW(&szTempName[4]) )
  {
    LastError = GetLastError();
    CFileException::ThrowOsError(LastError, &szTempName[4]);
    goto LABEL_45;
  }
LABEL_8:
  CWaitCursor::~CWaitCursor((CWaitCursor *)&fileDesc);
}

```

## disassembly

```asm
0x18022c770  mov     rax, rsp
0x18022c773  mov     [rax+10h], rbx
0x18022c777  mov     [rax+18h], rsi
0x18022c77b  mov     [rax+20h], rdi
0x18022c77f  push    rbp
0x18022c780  push    r12
0x18022c782  push    r13
0x18022c784  push    r14
0x18022c786  push    r15
0x18022c788  lea     rbp, [rax-868h]
0x18022c78f  sub     rsp, 940h
0x18022c796  mov     rax, cs:__security_cookie
0x18022c79d  xor     rax, rsp
0x18022c7a0  mov     [rbp+860h+var_30], rax
0x18022c7a7  mov     rsi, this
0x18022c7aa  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18022c7af  mov     this, [rax+8]; this
0x18022c7b3  call    ?BeginWaitCursor@CCmdTarget@@QEAAXXZ; CCmdTarget::BeginWaitCursor(void)
0x18022c7b8  nop
0x18022c7b9  lea     rdx, ?CreateObject@?$CProcessLocal@V_AFX_MAIL_STATE@@@@SAPEAVCNoTrackObject@@XZ; pfnCreateObject
0x18022c7c0  lea     this, ?_afxMailState@@3V?$CProcessLocal@V_AFX_MAIL_STATE@@@@A; this
0x18022c7c7  call    ?GetData@CProcessLocalObject@@QEAAPEAVCNoTrackObject@@P6APEAV2@XZ@Z; CProcessLocalObject::GetData(CNoTrackObject * (*)(void))
0x18022c7cc  mov     rbx, rax
0x18022c7cf  xor     r13d, r13d
0x18022c7d2  test    rax, rax
0x18022c7d5  jz      loc_18022CC41
0x18022c7db  mov     rax, [rax+8]
0x18022c7df  test    rax, rax
0x18022c7e2  jnz     short loc_18022C800
0x18022c7e4  lea     this, aMapi32Dll; "MAPI32.DLL"
0x18022c7eb  call    ?AtlLoadSystemLibraryUsingFullPath@ATL@@YAPEAUHINSTANCE__@@PEB_W@Z; ATL::AtlLoadSystemLibraryUsingFullPath(wchar_t const *)
0x18022c7f0  mov     [rbx+8], rax
0x18022c7f4  test    rax, rax
0x18022c7f7  jnz     short loc_18022C800
0x18022c7f9  mov     ecx, 0F190h
0x18022c7fe  jmp     short loc_18022C81D
0x18022c800  lea     rdx, aMapisendmail; "MAPISendMail"
0x18022c807  mov     this, rax; hModule
0x18022c80a  call    cs:__imp_GetProcAddress
0x18022c810  mov     r12, rax
0x18022c813  test    rax, rax
0x18022c816  jnz     short loc_18022C863
0x18022c818  mov     ecx, 0F191h; nIDPrompt
0x18022c81d  or      r8d, 0FFFFFFFFh; nIDHelp
0x18022c821  xor     edx, edx; nType
0x18022c823  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x18022c828  nop
0x18022c829  lea     this, [rsp+960h+fileDesc]; this
0x18022c82e  call    ??1CWaitCursor@@QEAA@XZ; CWaitCursor::~CWaitCursor(void)
0x18022c833  mov     this, [rbp+860h+var_30]
0x18022c83a  xor     this, rsp; StackCookie
0x18022c83d  call    __security_check_cookie
0x18022c842  lea     r11, [rsp+960h+var_20]
0x18022c84a  mov     rbx, [r11+38h]
0x18022c84e  mov     rsi, [r11+40h]
0x18022c852  mov     rdi, [r11+48h]
0x18022c856  mov     rsp, r11
0x18022c859  pop     r15
0x18022c85b  pop     r14
0x18022c85d  pop     r13
0x18022c85f  pop     r12
0x18022c861  pop     rbp
0x18022c862  retn
0x18022c863  mov     r15d, r13d
0x18022c866  mov     rax, [rsi+48h]
0x18022c86a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18022c86e  cmp     [rax-10h], r13d
0x18022c872  jz      short loc_18022C8C4
0x18022c874  mov     rax, [rsi]
0x18022c877  mov     this, rsi
0x18022c87a  mov     rax, [rax+0D0h]
0x18022c881  call    cs:__guard_dispatch_icall_fptr
0x18022c887  test    eax, eax
0x18022c889  jnz     short loc_18022C8C4
0x18022c88b  mov     r9, rdi; MaxCount
0x18022c88e  mov     r8, [rsi+48h]; Source
0x18022c892  mov     r14d, 104h
0x18022c898  mov     edx, r14d; SizeInWords
0x18022c89b  lea     this, [rbp+860h+szTempName+8]; Destination
0x18022c89f  call    cs:__imp_wcsncpy_s
0x18022c8a5  test    eax, eax
0x18022c8a7  jz      loc_18022C94C
0x18022c8ad  cmp     eax, 0Ch
0x18022c8b0  jz      loc_18022CC5F
0x18022c8b6  cmp     eax, 50h ; 'P'
0x18022c8b9  jnz     loc_18022CC41
0x18022c8bf  jmp     loc_18022C94C
0x18022c8c4  lea     rdx, [rbp+860h+szPath+8]; lpBuffer
0x18022c8cb  mov     r14d, 104h
0x18022c8d1  mov     ecx, r14d; nBufferLength
0x18022c8d4  call    cs:__imp_GetTempPathW
0x18022c8da  mov     r9d, r14d; sizeOfTempName
0x18022c8dd  lea     r8, [rbp+860h+szTempName+8]; lpszTempName
0x18022c8e1  lea     rdx, aAfx; "afx"
0x18022c8e8  lea     this, [rbp+860h+szPath+8]; lpszPath
0x18022c8ef  call    ?AfxGetTempFileName@@YAXPEB_W0PEA_W_K@Z; AfxGetTempFileName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x18022c8f4  mov     rax, [rsi]
0x18022c8f7  mov     this, rsi
0x18022c8fa  mov     rax, [rax+0D0h]
0x18022c901  call    cs:__guard_dispatch_icall_fptr
0x18022c907  mov     edi, eax
0x18022c909  mov     this, [rsi]
0x18022c90c  mov     rax, [this+1D0h]
0x18022c913  xor     r8d, r8d
0x18022c916  lea     rdx, [rbp+860h+szTempName+8]
0x18022c91a  mov     this, rsi
0x18022c91d  call    cs:__guard_dispatch_icall_fptr
0x18022c923  mov     ebx, eax
0x18022c925  mov     this, [rsi]
0x18022c928  mov     rax, [this+0D8h]
0x18022c92f  mov     edx, edi
0x18022c931  mov     this, rsi
0x18022c934  call    cs:__guard_dispatch_icall_fptr
0x18022c93a  test    ebx, ebx
0x18022c93c  jz      loc_18022C829
0x18022c942  mov     r15d, 1
0x18022c948  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18022c94c  mov     [rsp+960h+strExt.m_pszData], r13; lpUsedDefaultChar
0x18022c951  mov     [rsp+960h+lpDefaultChar], r13; lpDefaultChar
0x18022c956  mov     [rsp+960h+cbMultiByte], r14d; cbMultiByte
0x18022c95b  lea     rax, [rbp+860h+szTempNameA+8]
0x18022c962  mov     [rsp+960h+lpMultiByteStr], rax; lpMultiByteStr
0x18022c967  mov     r9d, edi; cchWideChar
0x18022c96a  lea     r8, [rbp+860h+szTempName+8]; lpWideCharStr
0x18022c96e  xor     edx, edx; dwFlags
0x18022c970  lea     ecx, [rdx+3]; CodePage
0x18022c973  call    cs:__imp_WideCharToMultiByte
0x18022c979  mov     this, [rsi+48h]; lpszPathName
0x18022c97d  cmp     [this-10h], r13d
0x18022c981  jz      short loc_18022C997
0x18022c983  mov     r8d, r14d; nMax
0x18022c986  lea     rdx, [rbp+860h+szTitle+8]; lpszTitle
0x18022c98d  call    ?AfxGetFileName@@YAIPEB_WPEA_WI@Z; AfxGetFileName(wchar_t const *,wchar_t *,uint)
0x18022c992  jmp     loc_18022CACA
0x18022c997  mov     r9, rdi; MaxCount
0x18022c99a  mov     r8, [rsi+40h]; Source
0x18022c99e  mov     rdx, r14; SizeInWords
0x18022c9a1  lea     this, [rbp+860h+szTitle+8]; Destination
0x18022c9a8  call    cs:__imp_wcsncpy_s
0x18022c9ae  test    eax, eax
0x18022c9b0  jz      short loc_18022C9C4
0x18022c9b2  cmp     eax, 0Ch
0x18022c9b5  jz      loc_18022CC5F
0x18022c9bb  cmp     eax, 50h ; 'P'
0x18022c9be  jnz     loc_18022CC41
0x18022c9c4  mov     this, [rsi+40h]; pszPath
0x18022c9c8  call    cs:__imp_PathFindExtensionW
0x18022c9ce  mov     rdx, rax; pszSrc
0x18022c9d1  lea     this, [rsp+960h+wait]; this
0x18022c9d6  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18022c9db  mov     this, [rax]
0x18022c9de  mov     ebx, [this-10h]
0x18022c9e1  mov     rdx, qword ptr [rsp+960h+wait]
0x18022c9e6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18022c9ea  mov     eax, edi
0x18022c9ec  lock xadd [rdx+10h], eax
0x18022c9f1  add     eax, edi
0x18022c9f3  test    eax, eax
0x18022c9f5  jg      short loc_18022CA07
0x18022c9f7  mov     this, [rdx]
0x18022c9fa  mov     rax, [this]
0x18022c9fd  mov     rax, [rax+8]
0x18022ca01  call    cs:__guard_dispatch_icall_fptr
0x18022ca07  test    ebx, ebx
0x18022ca09  jnz     loc_18022CACA
0x18022ca0f  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18022ca16  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x18022ca1d  mov     rax, [rax+18h]
0x18022ca21  call    cs:__guard_dispatch_icall_fptr
0x18022ca27  add     rax, 18h
0x18022ca2b  mov     qword ptr [rsp+960h+wait], rax
0x18022ca30  mov     this, [rsi+50h]
0x18022ca34  test    this, this
0x18022ca37  jz      short loc_18022CAA9
0x18022ca39  mov     rax, [this]
0x18022ca3c  lea     r8d, [rbx+4]
0x18022ca40  lea     rdx, [rsp+960h+wait]
0x18022ca45  mov     rax, [rax+0D8h]
0x18022ca4c  call    cs:__guard_dispatch_icall_fptr
0x18022ca52  test    eax, eax
0x18022ca54  jz      short loc_18022CAA4
0x18022ca56  mov     this, qword ptr [rsp+960h+wait]; String
0x18022ca5b  call    cs:__imp_wcslen
0x18022ca61  mov     rbx, rax
0x18022ca64  lea     this, [rbp+860h+szTitle+8]; String
0x18022ca6b  call    cs:__imp_wcslen
0x18022ca71  add     rax, rbx
0x18022ca74  cmp     rax, r14
0x18022ca77  jnb     short loc_18022CAA4
0x18022ca79  mov     r8, qword ptr [rsp+960h+wait]; Source
0x18022ca7e  mov     rdx, r14; SizeInWords
0x18022ca81  lea     this, [rbp+860h+szTitle+8]; Destination
0x18022ca88  call    cs:__imp_wcscat_s
0x18022ca8e  test    eax, eax
0x18022ca90  jz      short loc_18022CAA4
0x18022ca92  cmp     eax, 0Ch
0x18022ca95  jz      loc_18022CC3B
0x18022ca9b  cmp     eax, 50h ; 'P'
0x18022ca9e  jnz     loc_18022CC59
0x18022caa4  mov     rax, qword ptr [rsp+960h+wait]
0x18022caa9  lea     rdx, [rax-18h]
0x18022caad  mov     eax, edi
0x18022caaf  lock xadd [rdx+10h], eax
0x18022cab4  add     eax, edi
0x18022cab6  test    eax, eax
0x18022cab8  jg      short loc_18022CACA
0x18022caba  mov     this, [rdx]
0x18022cabd  mov     rax, [this]
0x18022cac0  mov     rax, [rax+8]
0x18022cac4  call    cs:__guard_dispatch_icall_fptr
0x18022caca  mov     [rsp+960h+strExt.m_pszData], r13; lpUsedDefaultChar
0x18022cacf  mov     [rsp+960h+lpDefaultChar], r13; lpDefaultChar
0x18022cad4  mov     [rsp+960h+cbMultiByte], r14d; cbMultiByte
0x18022cad9  lea     rax, [rbp+860h+szTitleA+8]
0x18022cae0  mov     [rsp+960h+lpMultiByteStr], rax; lpMultiByteStr
0x18022cae5  mov     r9d, edi; cchWideChar
0x18022cae8  lea     r8, [rbp+860h+szTitle+8]; lpWideCharStr
0x18022caef  xor     edx, edx; dwFlags
0x18022caf1  lea     ecx, [rdx+3]; CodePage
0x18022caf4  call    cs:__imp_WideCharToMultiByte
0x18022cafa  xor     edx, edx; Val
0x18022cafc  lea     r8d, [rdx+28h]; Size
0x18022cb00  lea     this, [rsp+960h+fileDesc.nPosition]; void *
0x18022cb05  call    cs:__imp_memset
0x18022cb0b  or      dword ptr [rsp+960h+fileDesc.lpszPathName], 0FFFFFFFFh
0x18022cb10  lea     rax, [rbp+860h+szTempNameA+8]
0x18022cb17  mov     [rsp+960h+fileDesc.lpszFileName], rax
0x18022cb1c  lea     rax, [rbp+860h+szTitleA+8]
0x18022cb23  mov     [rsp+960h+fileDesc.lpFileType], rax
0x18022cb28  xor     edx, edx; Val
0x18022cb2a  lea     r8d, [rdx+60h]; Size
0x18022cb2e  lea     this, [rbp+860h+message.lpszSubject]; void *
0x18022cb32  call    cs:__imp_memset
0x18022cb38  mov     esi, 1
0x18022cb3d  mov     dword ptr [rbp+860h+message.lpFiles], esi
0x18022cb40  lea     rax, [rsp+960h+fileDesc.nPosition]
0x18022cb45  mov     qword ptr [rbp+860h+szTempName], rax
0x18022cb49  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18022cb4e  xor     ecx, ecx; bEnable
0x18022cb50  call    ?DoEnableModeless@CWinApp@@SAXH@Z; CWinApp::DoEnableModeless(int)
0x18022cb55  lea     rdx, [rsp+960h+wait]; pWndTop
0x18022cb5a  xor     ecx, ecx; hParent
0x18022cb5c  call    ?GetSafeOwner_@CWnd@@SAPEAUHWND__@@PEAU2@PEAPEAU2@@Z; CWnd::GetSafeOwner_(HWND__ *,HWND__ * *)
0x18022cb61  mov     this, rax; hWnd
0x18022cb64  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18022cb69  mov     rbx, rax
0x18022cb6c  mov     this, [rax+40h]; hWnd
0x18022cb70  call    cs:__imp_SetCapture
0x18022cb76  mov     this, rax; hWnd
0x18022cb79  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18022cb7e  xor     ecx, ecx; hWnd
0x18022cb80  call    cs:__imp_SetFocus
0x18022cb86  or      dword ptr [rbx+0A8h], 4
0x18022cb8d  mov     dword ptr [rsp+960h+lpMultiByteStr], r13d
0x18022cb92  lea     r9d, [rsi+8]
0x18022cb96  lea     r8, [rbp+860h+message.lpszSubject]
0x18022cb9a  mov     rdx, [rbx+40h]
0x18022cb9e  xor     ecx, ecx
0x18022cba0  mov     rax, r12
0x18022cba3  call    cs:__guard_dispatch_icall_fptr
0x18022cba9  mov     edi, eax
0x18022cbab  call    cs:__imp_ReleaseCapture
0x18022cbb1  and     dword ptr [rbx+0A8h], 0FFFFFFFBh
0x18022cbb8  mov     edx, esi; bEnable
0x18022cbba  mov     this, rbx; this
0x18022cbbd  call    ?EnableWindow@CWnd@@QEAAHH@Z; CWnd::EnableWindow(int)
0x18022cbc2  xor     ecx, ecx; hWnd
0x18022cbc4  call    cs:__imp_SetActiveWindow
0x18022cbca  mov     this, [rbx+40h]; hWnd
0x18022cbce  call    cs:__imp_SetActiveWindow
0x18022cbd4  mov     this, rax; hWnd
0x18022cbd7  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18022cbdc  mov     this, rbx; this
0x18022cbdf  call    ?SetFocus@CWnd@@QEAAPEAV1@XZ; CWnd::SetFocus(void)
0x18022cbe4  mov     this, qword ptr [rsp+960h+wait]; hWnd
0x18022cbe9  test    this, this
0x18022cbec  jz      short loc_18022CBF6
0x18022cbee  mov     edx, esi; bEnable
0x18022cbf0  call    cs:__imp_EnableWindow
0x18022cbf6  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18022cbfb  mov     ecx, esi; bEnable
0x18022cbfd  call    ?DoEnableModeless@CWinApp@@SAXH@Z; CWinApp::DoEnableModeless(int)
0x18022cc02  test    edi, 0FFFFFFFCh
0x18022cc08  jnz     short loc_18022CC0F
0x18022cc0a  cmp     edi, 2
0x18022cc0d  jnz     short loc_18022CC1F
0x18022cc0f  or      r8d, 0FFFFFFFFh; nIDHelp
0x18022cc13  xor     edx, edx; nType
0x18022cc15  mov     ecx, 0F192h; nIDPrompt
0x18022cc1a  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x18022cc1f  test    r15d, r15d
0x18022cc22  jz      loc_18022C829
0x18022cc28  lea     this, [rbp+860h+szTempName+8]; lpFileName
0x18022cc2c  call    cs:__imp_DeleteFileW
0x18022cc32  test    eax, eax
0x18022cc34  jz      short loc_18022CC47
0x18022cc36  jmp     loc_18022C829
0x18022cc3b  call    ?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
0x18022cc41  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x18022cc47  call    cs:__imp_GetLastError
  ... truncated ...
```

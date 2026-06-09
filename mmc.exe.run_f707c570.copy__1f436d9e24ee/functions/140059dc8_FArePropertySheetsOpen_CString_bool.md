# FArePropertySheetsOpen(CString *,bool)

- ea: `0x140059dc8`
- end: `0x14005a2ac`
- name: `?FArePropertySheetsOpen@@YA_NPEAVCString@@_N@Z`
- size: `1252`
- prototype: `bool __fastcall(struct CString *, bool)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x140039960`
- `0x1400483e0`
- `0x14007c1e0`
- `0x14007d798`
- `0x1400bb87c`

## callees

- `0x140027c80`
- `0x140033828`
- `0x1400598b4`
- `0x140059d58`
- `0x140059dc8`
- `0x1400b5b00`

## import_xrefs

- `USER32!SetForegroundWindow` at `0x14005a0f7`
- `USER32!SetForegroundWindow` at `0x14005a0f7`
- `USER32!SetActiveWindow` at `0x14005a0ee`
- `USER32!SetActiveWindow` at `0x14005a0ee`
- `USER32!EnumThreadWindows` at `0x140059ea0`
- `USER32!EnumThreadWindows` at `0x14005a01e`
- `USER32!EnumThreadWindows` at `0x140059ea0`
- `USER32!EnumThreadWindows` at `0x14005a01e`
- `USER32!IsWindowEnabled` at `0x14005a100`
- `USER32!IsWindowEnabled` at `0x14005a100`
- `USER32!IsWindow` at `0x140059e6b`
- `USER32!IsWindow` at `0x140059eaa`
- `USER32!IsWindow` at `0x14005a028`
- `USER32!IsWindow` at `0x140059e6b`
- `USER32!IsWindow` at `0x140059eaa`
- `USER32!IsWindow` at `0x14005a028`
- `USER32!GetWindowLongPtrW` at `0x140059e54`
- `USER32!GetWindowLongPtrW` at `0x140059e54`
- `USER32!MessageBoxW` at `0x14005a244`
- `USER32!MessageBoxW` at `0x14005a244`
- `USER32!FindWindowExW` at `0x140059e15`
- `USER32!FindWindowExW` at `0x140059f97`
- `USER32!FindWindowExW` at `0x140059e15`
- `USER32!FindWindowExW` at `0x140059f97`
- `USER32!GetWindowThreadProcessId` at `0x140059e3a`
- `USER32!GetWindowThreadProcessId` at `0x140059e8d`
- `USER32!GetWindowThreadProcessId` at `0x140059e3a`
- `USER32!GetWindowThreadProcessId` at `0x140059e8d`
- `USER32!EnableWindow` at `0x14005a10f`
- `USER32!EnableWindow` at `0x14005a266`
- `USER32!EnableWindow` at `0x14005a10f`
- `USER32!EnableWindow` at `0x14005a266`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005a19b`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005a19b`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005a24f`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005a24f`
- `MFC42u!__imp_?EnableWindow@CWnd@@QEAAHH@Z` at `0x14005a1d8`
- `MFC42u!__imp_?EnableWindow@CWnd@@QEAAHH@Z` at `0x14005a1d8`
- `MFC42u!__imp_?IsWindowEnabled@CWnd@@QEBAHXZ` at `0x14005a1c9`
- `MFC42u!__imp_?IsWindowEnabled@CWnd@@QEBAHXZ` at `0x14005a1c9`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x14005a280`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x14005a28f`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x14005a280`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x14005a28f`
- `mmcbase!?FindAllSnapinUIThreads@BookKeeping@@SAJPEAPEAKPEAK@Z` at `0x140059fbd`
- `mmcbase!?FindAllSnapinUIThreads@BookKeeping@@SAJPEAPEAKPEAK@Z` at `0x140059fbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140059e40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140059e40`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall FArePropertySheetsOpen(LPCWSTR *a1, char a2)
{
  char v2; // r12
  LPARAM *v3; // rdi
  HWND Window; // r15
  LPARAM *v5; // rbx
  LPARAM *v6; // rsi
  LONG_PTR WindowLongPtrW; // r14
  HWND v8; // r12
  DWORD WindowThreadProcessId; // eax
  LPARAM v10; // rax
  __int64 v11; // r14
  __int64 v12; // r14
  int AllSnapinUIThreads; // eax
  unsigned int i; // r15d
  __int64 v15; // r14
  LPARAM v16; // rax
  bool v17; // r13
  HWND v18; // r12
  HWND *v19; // rdi
  HWND *v20; // r14
  HWND *v21; // r13
  __int64 v22; // r15
  int StringW; // eax
  const WCHAR *v24; // r15
  CWnd *MainWnd; // rax
  CWnd *v26; // rbx
  char *v27; // rbx
  __int64 v28; // rbx
  HWND v29; // rax
  __int128 v31; // [rsp+20h] [rbp-49h] BYREF
  LPARAM *v32; // [rsp+30h] [rbp-39h]
  LPARAM lParam; // [rsp+38h] [rbp-31h] BYREF
  __int128 v34; // [rsp+40h] [rbp-29h] BYREF
  HWND *v35; // [rsp+50h] [rbp-19h]
  LPARAM v36; // [rsp+58h] [rbp-11h] BYREF
  unsigned int *v37; // [rsp+60h] [rbp-9h] BYREF
  HWND v38; // [rsp+68h] [rbp-1h] BYREF
  _QWORD v39[10]; // [rsp+70h] [rbp+7h] BYREF
  bool v42; // [rsp+D8h] [rbp+6Fh]
  unsigned int v43; // [rsp+E0h] [rbp+77h] BYREF
  __int64 dwProcessId; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = a2;
  v31 = 0;
  v3 = 0;
  v32 = 0;
  v34 = 0;
  v35 = 0;
  Window = FindWindowExW(0, 0, L"MMCDataWindow", 0);
  v5 = 0;
  v6 = 0;
  if ( Window )
  {
    do
    {
      LODWORD(dwProcessId) = 0;
      GetWindowThreadProcessId(Window, (LPDWORD)&dwProcessId);
      if ( (_DWORD)dwProcessId == GetCurrentProcessId() )
      {
        WindowLongPtrW = GetWindowLongPtrW(Window, 0);
        v8 = *(HWND *)(WindowLongPtrW + 184);
        v38 = v8;
        if ( IsWindow(v8) )
        {
          lParam = *(_QWORD *)(WindowLongPtrW + 184);
          WindowThreadProcessId = GetWindowThreadProcessId(*(HWND *)(WindowLongPtrW + 184), 0);
          EnumThreadWindows(WindowThreadProcessId, MyEnumThreadWindProc, (LPARAM)&lParam);
          if ( IsWindow((HWND)lParam) )
          {
            v10 = lParam;
            if ( (HWND)lParam != v8 )
            {
              if ( &lParam >= v5 || v6 > &lParam )
              {
                if ( v5 == v3 )
                {
                  std::vector<CMMCToolBarCtrlEx *>::_Reserve(&v31);
                  v3 = v32;
                  v5 = (LPARAM *)*((_QWORD *)&v31 + 1);
                  v6 = (LPARAM *)v31;
                  v10 = lParam;
                }
              }
              else
              {
                v11 = &lParam - v6;
                if ( v5 == v3 )
                {
                  std::vector<CMMCToolBarCtrlEx *>::_Reserve(&v31);
                  v3 = v32;
                  v5 = (LPARAM *)*((_QWORD *)&v31 + 1);
                  v6 = (LPARAM *)v31;
                }
                v10 = v6[v11];
              }
              *v5++ = v10;
              *((_QWORD *)&v31 + 1) = v5;
            }
          }
          if ( &v38 >= (HWND *)v5 || v6 > (LPARAM *)&v38 )
          {
            if ( v5 == v3 )
            {
              std::vector<CMMCToolBarCtrlEx *>::_Reserve(&v31);
              v3 = v32;
              v5 = (LPARAM *)*((_QWORD *)&v31 + 1);
              v6 = (LPARAM *)v31;
            }
            *v5 = (LPARAM)v8;
          }
          else
          {
            v12 = ((char *)&v38 - (char *)v6) >> 3;
            if ( v5 == v3 )
            {
              std::vector<CMMCToolBarCtrlEx *>::_Reserve(&v31);
              v3 = v32;
              v5 = (LPARAM *)*((_QWORD *)&v31 + 1);
              v6 = (LPARAM *)v31;
            }
            *v5 = v6[v12];
          }
          *((_QWORD *)&v31 + 1) = ++v5;
        }
      }
      Window = FindWindowExW(0, Window, L"MMCDataWindow", 0);
    }
    while ( Window );
    v2 = a2;
  }
  v37 = 0;
  v43 = 0;
  AllSnapinUIThreads = BookKeeping::FindAllSnapinUIThreads(&v37, &v43);
  if ( AllSnapinUIThreads < 0
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      12,
      WPP_0483bcc4bca33cc27265609366f64d76_Traceguids,
      (unsigned int)AllSnapinUIThreads);
  }
  for ( i = 0; i < v43; ++i )
  {
    v36 = 0;
    EnumThreadWindows(v37[i], MyEnumThreadWindProc, (LPARAM)&v36);
    if ( IsWindow((HWND)v36) )
    {
      if ( &v36 >= v5 || v6 > &v36 )
      {
        if ( v5 == v3 )
        {
          std::vector<CMMCToolBarCtrlEx *>::_Reserve(&v31);
          v3 = v32;
          v5 = (LPARAM *)*((_QWORD *)&v31 + 1);
          v6 = (LPARAM *)v31;
        }
        v16 = v36;
      }
      else
      {
        v15 = &v36 - v6;
        if ( v5 == v3 )
        {
          std::vector<CMMCToolBarCtrlEx *>::_Reserve(&v31);
          v3 = v32;
          v5 = (LPARAM *)*((_QWORD *)&v31 + 1);
          v6 = (LPARAM *)v31;
        }
        v16 = v6[v15];
      }
      *v5++ = v16;
      *((_QWORD *)&v31 + 1) = v5;
    }
  }
  v17 = v6 != v5;
  v42 = v6 != v5;
  if ( v2 )
  {
    v18 = 0;
    v19 = (HWND *)*((_QWORD *)&v34 + 1);
    v20 = (HWND *)v34;
    v21 = v35;
    while ( v6 != v5 )
    {
      v18 = (HWND)*--v5;
      v39[0] = v18;
      *((_QWORD *)&v31 + 1) = v5;
      SetActiveWindow(v18);
      SetForegroundWindow(v18);
      if ( IsWindowEnabled(v18) )
      {
        EnableWindow(v18, 0);
        if ( v39 >= v19 || v20 > v39 )
        {
          if ( v19 == v21 )
          {
            std::vector<CMMCToolBarCtrlEx *>::_Reserve(&v34);
            v19 = (HWND *)*((_QWORD *)&v34 + 1);
            v20 = (HWND *)v34;
            v21 = v35;
          }
          *v19 = v18;
        }
        else
        {
          v22 = (HWND *)v39 - v20;
          if ( v19 == v21 )
          {
            std::vector<CMMCToolBarCtrlEx *>::_Reserve(&v34);
            v19 = (HWND *)*((_QWORD *)&v34 + 1);
            v20 = (HWND *)v34;
            v21 = v35;
          }
          *v19 = v20[v22];
        }
        *((_QWORD *)&v34 + 1) = ++v19;
      }
    }
    v17 = v42;
    if ( v42 && a1 )
    {
      CString::CString(&dwProcessId);
      StringW = LoadStringW((struct CString *)&dwProcessId, 0x80u);
      v24 = (const WCHAR *)(dwProcessId & -(__int64)(StringW != 0));
      MainWnd = AfxGetMainWnd();
      v26 = MainWnd;
      if ( MainWnd && CWnd::IsWindowEnabled(MainWnd) )
      {
        CWnd::EnableWindow(v26, 0);
        v27 = (char *)v26 + 64;
        if ( v27 >= (char *)v19 || v20 > (HWND *)v27 )
        {
          if ( v19 == v35 )
          {
            std::vector<CMMCToolBarCtrlEx *>::_Reserve(&v34);
            v19 = (HWND *)*((_QWORD *)&v34 + 1);
            v20 = (HWND *)v34;
          }
          v29 = *(HWND *)v27;
        }
        else
        {
          v28 = (v27 - (char *)v20) >> 3;
          if ( v19 == v35 )
          {
            std::vector<CMMCToolBarCtrlEx *>::_Reserve(&v34);
            v19 = (HWND *)*((_QWORD *)&v34 + 1);
            v20 = (HWND *)v34;
          }
          v29 = v20[v28];
        }
        *v19++ = v29;
      }
      MessageBoxW(v18, *a1, v24, 0x10u);
      CString::~CString(&dwProcessId);
    }
    while ( v20 != v19 )
      EnableWindow(*--v19, 1);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v37);
    if ( v20 )
      operator delete(v20);
  }
  else
  {
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v37);
  }
  if ( v6 )
    operator delete(v6);
  return v17;
}

```

## disassembly

```asm
0x140059dc8  mov     [rsp-8+arg_8], dl
0x140059dcc  mov     [rsp-8+arg_0], rcx
0x140059dd1  push    rbp
0x140059dd2  push    rbx
0x140059dd3  push    rsi
0x140059dd4  push    rdi
0x140059dd5  push    r12
0x140059dd7  push    r13
0x140059dd9  push    r14
0x140059ddb  push    r15
0x140059ddd  lea     rbp, [rsp-1Fh]
0x140059de2  sub     rsp, 88h
0x140059de9  mov     r12b, dl
0x140059dec  xorps   xmm0, xmm0
0x140059def  movdqu  [rbp+57h+var_A0], xmm0
0x140059df4  xor     r13d, r13d
0x140059df7  mov     edi, r13d
0x140059dfa  mov     [rbp+57h+var_90], r13
0x140059dfe  movdqu  [rbp+57h+var_80], xmm0
0x140059e03  mov     [rbp+57h+var_70], r13
0x140059e07  xor     r9d, r9d; lpszWindow
0x140059e0a  lea     r8, szClass; "MMCDataWindow"
0x140059e11  xor     edx, edx; hWndChildAfter
0x140059e13  xor     ecx, ecx; hWndParent
0x140059e15  call    cs:__imp_FindWindowExW
0x140059e1b  mov     r15, rax
0x140059e1e  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x140059e22  mov     rsi, qword ptr [rbp+57h+var_A0]
0x140059e26  test    rax, rax
0x140059e29  jz      loc_140059FAD
0x140059e2f  mov     dword ptr [rbp+57h+dwProcessId], r13d
0x140059e33  lea     rdx, [rbp+57h+dwProcessId]; lpdwProcessId
0x140059e37  mov     rcx, r15; hWnd
0x140059e3a  call    cs:__imp_GetWindowThreadProcessId
0x140059e40  call    cs:__imp_GetCurrentProcessId
0x140059e46  cmp     dword ptr [rbp+57h+dwProcessId], eax
0x140059e49  jnz     loc_140059F88
0x140059e4f  xor     edx, edx; nIndex
0x140059e51  mov     rcx, r15; hWnd
0x140059e54  call    cs:__imp_GetWindowLongPtrW
0x140059e5a  mov     r14, rax
0x140059e5d  mov     r12, [rax+0B8h]
0x140059e64  mov     [rbp+57h+var_58], r12
0x140059e68  mov     rcx, r12; hWnd
0x140059e6b  call    cs:__imp_IsWindow
0x140059e71  test    eax, eax
0x140059e73  jz      loc_140059F88
0x140059e79  mov     rcx, [r14+0B8h]
0x140059e80  mov     [rbp+57h+lParam], rcx
0x140059e84  xor     edx, edx; lpdwProcessId
0x140059e86  mov     rcx, [r14+0B8h]; hWnd
0x140059e8d  call    cs:__imp_GetWindowThreadProcessId
0x140059e93  mov     ecx, eax; dwThreadId
0x140059e95  lea     r8, [rbp+57h+lParam]; lParam
0x140059e99  lea     rdx, ?MyEnumThreadWindProc@@YAHPEAUHWND__@@_J@Z; lpfn
0x140059ea0  call    cs:__imp_EnumThreadWindows
0x140059ea6  mov     rcx, [rbp+57h+lParam]; hWnd
0x140059eaa  call    cs:__imp_IsWindow
0x140059eb0  test    eax, eax
0x140059eb2  jz      short loc_140059F23
0x140059eb4  mov     rax, [rbp+57h+lParam]
0x140059eb8  cmp     rax, r12
0x140059ebb  jz      short loc_140059F23
0x140059ebd  lea     rcx, [rbp+57h+lParam]
0x140059ec1  cmp     rcx, rbx
0x140059ec4  jnb     short loc_140059EFA
0x140059ec6  lea     rcx, [rbp+57h+lParam]
0x140059eca  cmp     rsi, rcx
0x140059ecd  ja      short loc_140059EFA
0x140059ecf  lea     r14, [rbp+57h+lParam]
0x140059ed3  sub     r14, rsi
0x140059ed6  sar     r14, 3
0x140059eda  cmp     rbx, rdi
0x140059edd  jnz     short loc_140059EF4
0x140059edf  lea     rcx, [rbp+57h+var_A0]
0x140059ee3  call    ?_Reserve@?$vector@PEAVCMMCToolBarCtrlEx@@V?$allocator@PEAVCMMCToolBarCtrlEx@@@std@@@std@@IEAAX_K@Z; std::vector<CMMCToolBarCtrlEx *>::_Reserve(unsigned __int64)
0x140059ee8  mov     rdi, [rbp+57h+var_90]
0x140059eec  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x140059ef0  mov     rsi, qword ptr [rbp+57h+var_A0]
0x140059ef4  mov     rax, [rsi+r14*8]
0x140059ef8  jmp     short loc_140059F18
0x140059efa  cmp     rbx, rdi
0x140059efd  jnz     short loc_140059F18
0x140059eff  lea     rcx, [rbp+57h+var_A0]
0x140059f03  call    ?_Reserve@?$vector@PEAVCMMCToolBarCtrlEx@@V?$allocator@PEAVCMMCToolBarCtrlEx@@@std@@@std@@IEAAX_K@Z; std::vector<CMMCToolBarCtrlEx *>::_Reserve(unsigned __int64)
0x140059f08  mov     rdi, [rbp+57h+var_90]
0x140059f0c  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x140059f10  mov     rsi, qword ptr [rbp+57h+var_A0]
0x140059f14  mov     rax, [rbp+57h+lParam]
0x140059f18  mov     [rbx], rax
0x140059f1b  add     rbx, 8
0x140059f1f  mov     qword ptr [rbp+57h+var_A0+8], rbx
0x140059f23  lea     rax, [rbp+57h+var_58]
0x140059f27  cmp     rax, rbx
0x140059f2a  jnb     short loc_140059F63
0x140059f2c  lea     rax, [rbp+57h+var_58]
0x140059f30  cmp     rsi, rax
0x140059f33  ja      short loc_140059F63
0x140059f35  lea     r14, [rbp+57h+var_58]
0x140059f39  sub     r14, rsi
0x140059f3c  sar     r14, 3
0x140059f40  cmp     rbx, rdi
0x140059f43  jnz     short loc_140059F5A
0x140059f45  lea     rcx, [rbp+57h+var_A0]
0x140059f49  call    ?_Reserve@?$vector@PEAVCMMCToolBarCtrlEx@@V?$allocator@PEAVCMMCToolBarCtrlEx@@@std@@@std@@IEAAX_K@Z; std::vector<CMMCToolBarCtrlEx *>::_Reserve(unsigned __int64)
0x140059f4e  mov     rdi, [rbp+57h+var_90]
0x140059f52  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x140059f56  mov     rsi, qword ptr [rbp+57h+var_A0]
0x140059f5a  mov     rax, [rsi+r14*8]
0x140059f5e  mov     [rbx], rax
0x140059f61  jmp     short loc_140059F80
0x140059f63  cmp     rbx, rdi
0x140059f66  jnz     short loc_140059F7D
0x140059f68  lea     rcx, [rbp+57h+var_A0]
0x140059f6c  call    ?_Reserve@?$vector@PEAVCMMCToolBarCtrlEx@@V?$allocator@PEAVCMMCToolBarCtrlEx@@@std@@@std@@IEAAX_K@Z; std::vector<CMMCToolBarCtrlEx *>::_Reserve(unsigned __int64)
0x140059f71  mov     rdi, [rbp+57h+var_90]
0x140059f75  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x140059f79  mov     rsi, qword ptr [rbp+57h+var_A0]
0x140059f7d  mov     [rbx], r12
0x140059f80  add     rbx, 8
0x140059f84  mov     qword ptr [rbp+57h+var_A0+8], rbx
0x140059f88  xor     r9d, r9d; lpszWindow
0x140059f8b  lea     r8, szClass; "MMCDataWindow"
0x140059f92  mov     rdx, r15; hWndChildAfter
0x140059f95  xor     ecx, ecx; hWndParent
0x140059f97  call    cs:__imp_FindWindowExW
0x140059f9d  mov     r15, rax
0x140059fa0  test    rax, rax
0x140059fa3  jnz     loc_140059E2F
0x140059fa9  mov     r12b, [rbp+57h+arg_8]
0x140059fad  mov     [rbp+57h+var_60], r13
0x140059fb1  mov     [rbp+57h+arg_10], r13d
0x140059fb5  lea     rdx, [rbp+57h+arg_10]
0x140059fb9  lea     rcx, [rbp+57h+var_60]
0x140059fbd  call    cs:__imp_?FindAllSnapinUIThreads@BookKeeping@@SAJPEAPEAKPEAK@Z; BookKeeping::FindAllSnapinUIThreads(ulong * *,ulong *)
0x140059fc3  test    eax, eax
0x140059fc5  jns     short loc_140059FF8
0x140059fc7  lea     rdx, WPP_GLOBAL_Control
0x140059fce  mov     rcx, cs:WPP_GLOBAL_Control
0x140059fd5  cmp     rcx, rdx
0x140059fd8  jz      short loc_140059FF8
0x140059fda  cmp     byte ptr [rcx+19h], 3
0x140059fde  jb      short loc_140059FF8
0x140059fe0  mov     edx, 0Ch
0x140059fe5  mov     r9d, eax
0x140059fe8  lea     r8, WPP_0483bcc4bca33cc27265609366f64d76_Traceguids
0x140059fef  mov     rcx, [rcx+10h]
0x140059ff3  call    WPP_SF_d
0x140059ff8  mov     r15d, r13d
0x140059ffb  cmp     [rbp+57h+arg_10], r13d
0x140059fff  jbe     loc_14005A0A5
0x14005a005  mov     [rbp+57h+var_68], r13
0x14005a009  mov     eax, r15d
0x14005a00c  lea     r8, [rbp+57h+var_68]; lParam
0x14005a010  lea     rdx, ?MyEnumThreadWindProc@@YAHPEAUHWND__@@_J@Z; lpfn
0x14005a017  mov     rcx, [rbp+57h+var_60]
0x14005a01b  mov     ecx, [rcx+rax*4]; dwThreadId
0x14005a01e  call    cs:__imp_EnumThreadWindows
0x14005a024  mov     rcx, [rbp+57h+var_68]; hWnd
0x14005a028  call    cs:__imp_IsWindow
0x14005a02e  test    eax, eax
0x14005a030  jz      short loc_14005A098
0x14005a032  lea     rax, [rbp+57h+var_68]
0x14005a036  cmp     rax, rbx
0x14005a039  jnb     short loc_14005A06F
0x14005a03b  lea     rax, [rbp+57h+var_68]
0x14005a03f  cmp     rsi, rax
0x14005a042  ja      short loc_14005A06F
0x14005a044  lea     r14, [rbp+57h+var_68]
0x14005a048  sub     r14, rsi
0x14005a04b  sar     r14, 3
0x14005a04f  cmp     rbx, rdi
0x14005a052  jnz     short loc_14005A069
0x14005a054  lea     rcx, [rbp+57h+var_A0]
0x14005a058  call    ?_Reserve@?$vector@PEAVCMMCToolBarCtrlEx@@V?$allocator@PEAVCMMCToolBarCtrlEx@@@std@@@std@@IEAAX_K@Z; std::vector<CMMCToolBarCtrlEx *>::_Reserve(unsigned __int64)
0x14005a05d  mov     rdi, [rbp+57h+var_90]
0x14005a061  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x14005a065  mov     rsi, qword ptr [rbp+57h+var_A0]
0x14005a069  mov     rax, [rsi+r14*8]
0x14005a06d  jmp     short loc_14005A08D
0x14005a06f  cmp     rbx, rdi
0x14005a072  jnz     short loc_14005A089
0x14005a074  lea     rcx, [rbp+57h+var_A0]
0x14005a078  call    ?_Reserve@?$vector@PEAVCMMCToolBarCtrlEx@@V?$allocator@PEAVCMMCToolBarCtrlEx@@@std@@@std@@IEAAX_K@Z; std::vector<CMMCToolBarCtrlEx *>::_Reserve(unsigned __int64)
0x14005a07d  mov     rdi, [rbp+57h+var_90]
0x14005a081  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x14005a085  mov     rsi, qword ptr [rbp+57h+var_A0]
0x14005a089  mov     rax, [rbp+57h+var_68]
0x14005a08d  mov     [rbx], rax
0x14005a090  add     rbx, 8
0x14005a094  mov     qword ptr [rbp+57h+var_A0+8], rbx
0x14005a098  inc     r15d
0x14005a09b  cmp     r15d, [rbp+57h+arg_10]
0x14005a09f  jb      loc_14005A005
0x14005a0a5  cmp     rsi, rbx
0x14005a0a8  setnz   r13b
0x14005a0ac  mov     [rbp+57h+arg_8], r13b
0x14005a0b0  test    r12b, r12b
0x14005a0b3  jnz     short loc_14005A0C4
0x14005a0b5  lea     rcx, [rbp+57h+var_60]
0x14005a0b9  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x14005a0be  nop
0x14005a0bf  jmp     loc_14005A287
0x14005a0c4  xor     r12d, r12d
0x14005a0c7  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x14005a0cb  mov     r14, qword ptr [rbp+57h+var_80]
0x14005a0cf  mov     r13, [rbp+57h+var_70]
0x14005a0d3  cmp     rsi, rbx
0x14005a0d6  jz      loc_14005A17F
0x14005a0dc  add     rbx, 0FFFFFFFFFFFFFFF8h
0x14005a0e0  mov     r12, [rbx]
0x14005a0e3  mov     [rbp+57h+var_50], r12
0x14005a0e7  mov     qword ptr [rbp+57h+var_A0+8], rbx
0x14005a0eb  mov     rcx, r12; hWnd
0x14005a0ee  call    cs:__imp_SetActiveWindow
0x14005a0f4  mov     rcx, r12; hWnd
0x14005a0f7  call    cs:__imp_SetForegroundWindow
0x14005a0fd  mov     rcx, r12; hWnd
0x14005a100  call    cs:__imp_IsWindowEnabled
0x14005a106  test    eax, eax
0x14005a108  jz      short loc_14005A0D3
0x14005a10a  xor     edx, edx; bEnable
0x14005a10c  mov     rcx, r12; hWnd
0x14005a10f  call    cs:__imp_EnableWindow
0x14005a115  lea     rax, [rbp+57h+var_50]
0x14005a119  cmp     rax, rdi
0x14005a11c  jnb     short loc_14005A155
0x14005a11e  lea     rax, [rbp+57h+var_50]
0x14005a122  cmp     r14, rax
0x14005a125  ja      short loc_14005A155
0x14005a127  lea     r15, [rbp+57h+var_50]
0x14005a12b  sub     r15, r14
0x14005a12e  sar     r15, 3
0x14005a132  cmp     rdi, r13
0x14005a135  jnz     short loc_14005A14C
0x14005a137  lea     rcx, [rbp+57h+var_80]
0x14005a13b  call    ?_Reserve@?$vector@PEAVCMMCToolBarCtrlEx@@V?$allocator@PEAVCMMCToolBarCtrlEx@@@std@@@std@@IEAAX_K@Z; std::vector<CMMCToolBarCtrlEx *>::_Reserve(unsigned __int64)
0x14005a140  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x14005a144  mov     r14, qword ptr [rbp+57h+var_80]
0x14005a148  mov     r13, [rbp+57h+var_70]
0x14005a14c  mov     rax, [r14+r15*8]
0x14005a150  mov     [rdi], rax
0x14005a153  jmp     short loc_14005A172
0x14005a155  cmp     rdi, r13
0x14005a158  jnz     short loc_14005A16F
0x14005a15a  lea     rcx, [rbp+57h+var_80]
0x14005a15e  call    ?_Reserve@?$vector@PEAVCMMCToolBarCtrlEx@@V?$allocator@PEAVCMMCToolBarCtrlEx@@@std@@@std@@IEAAX_K@Z; std::vector<CMMCToolBarCtrlEx *>::_Reserve(unsigned __int64)
0x14005a163  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x14005a167  mov     r14, qword ptr [rbp+57h+var_80]
0x14005a16b  mov     r13, [rbp+57h+var_70]
0x14005a16f  mov     [rdi], r12
0x14005a172  add     rdi, 8
0x14005a176  mov     qword ptr [rbp+57h+var_80+8], rdi
0x14005a17a  jmp     loc_14005A0D3
0x14005a17f  mov     r13b, [rbp+57h+arg_8]
0x14005a183  test    r13b, r13b
0x14005a186  jz      loc_14005A255
0x14005a18c  cmp     [rbp+57h+arg_0], 0
0x14005a191  jz      loc_14005A255
0x14005a197  lea     rcx, [rbp+57h+dwProcessId]
0x14005a19b  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x14005a1a1  nop
0x14005a1a2  mov     edx, 80h; unsigned int
0x14005a1a7  lea     rcx, [rbp+57h+dwProcessId]; struct CString *
0x14005a1ab  call    ?LoadStringW@@YAHAEAVCString@@I@Z; LoadStringW(CString &,uint)
0x14005a1b0  neg     eax
0x14005a1b2  sbb     r15, r15
0x14005a1b5  and     r15, [rbp+57h+dwProcessId]
0x14005a1b9  call    ?AfxGetMainWnd@@YAPEAVCWnd@@XZ; AfxGetMainWnd(void)
0x14005a1be  mov     rbx, rax
0x14005a1c1  test    rax, rax
0x14005a1c4  jz      short loc_14005A231
0x14005a1c6  mov     rcx, rax
0x14005a1c9  call    cs:__imp_?IsWindowEnabled@CWnd@@QEBAHXZ; CWnd::IsWindowEnabled(void)
0x14005a1cf  test    eax, eax
0x14005a1d1  jz      short loc_14005A231
0x14005a1d3  xor     edx, edx
0x14005a1d5  mov     rcx, rbx
0x14005a1d8  call    cs:__imp_?EnableWindow@CWnd@@QEAAHH@Z; CWnd::EnableWindow(int)
0x14005a1de  add     rbx, 40h ; '@'
0x14005a1e2  cmp     rbx, rdi
0x14005a1e5  jnb     short loc_14005A210
0x14005a1e7  cmp     r14, rbx
0x14005a1ea  ja      short loc_14005A210
0x14005a1ec  sub     rbx, r14
0x14005a1ef  sar     rbx, 3
0x14005a1f3  cmp     rdi, [rbp+57h+var_70]
0x14005a1f7  jnz     short loc_14005A20A
0x14005a1f9  lea     rcx, [rbp+57h+var_80]
0x14005a1fd  call    ?_Reserve@?$vector@PEAVCMMCToolBarCtrlEx@@V?$allocator@PEAVCMMCToolBarCtrlEx@@@std@@@std@@IEAAX_K@Z; std::vector<CMMCToolBarCtrlEx *>::_Reserve(unsigned __int64)
0x14005a202  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x14005a206  mov     r14, qword ptr [rbp+57h+var_80]
0x14005a20a  mov     rax, [r14+rbx*8]
0x14005a20e  jmp     short loc_14005A22A
0x14005a210  cmp     rdi, [rbp+57h+var_70]
0x14005a214  jnz     short loc_14005A227
0x14005a216  lea     rcx, [rbp+57h+var_80]
0x14005a21a  call    ?_Reserve@?$vector@PEAVCMMCToolBarCtrlEx@@V?$allocator@PEAVCMMCToolBarCtrlEx@@@std@@@std@@IEAAX_K@Z; std::vector<CMMCToolBarCtrlEx *>::_Reserve(unsigned __int64)
0x14005a21f  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x14005a223  mov     r14, qword ptr [rbp+57h+var_80]
  ... truncated ...
```

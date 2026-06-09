# CChildFrame::OnNcPaint(void)

- ea: `0x140028d80`
- end: `0x14002905f`
- name: `?OnNcPaint@CChildFrame@@IEAAXXZ`
- size: `735`
- prototype: `void __fastcall(CChildFrame *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x14000d478`
- `0x14000d5c0`
- `0x14000d750`
- `0x14000e9cc`
- `0x1400253a4`
- `0x140028d80`
- `0x14002e2d8`
- `0x14003ec30`
- `0x140046d90`
- `0x14005a420`
- `0x140062455`
- `0x14009d700`
- `0x14009d79c`
- `0x1400b6264`
- `0x1400e9e10`

## import_xrefs

- `USER32!GetSysColor` at `0x140028f46`
- `USER32!GetSysColor` at `0x140028f51`
- `USER32!GetSysColor` at `0x140028f70`
- `USER32!GetSysColor` at `0x140028f93`
- `USER32!GetSysColor` at `0x140028f46`
- `USER32!GetSysColor` at `0x140028f51`
- `USER32!GetSysColor` at `0x140028f70`
- `USER32!GetSysColor` at `0x140028f93`
- `USER32!SystemParametersInfoW` at `0x140028e60`
- `USER32!SystemParametersInfoW` at `0x140028e60`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x140028ea4`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x140028ea4`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x140028e2c`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x140028e2c`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x140029012`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x140029012`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x14002902e`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x14002902e`
- `MFC42u!__imp_?Default@CWnd@@IEAA_JXZ` at `0x140028db5`
- `MFC42u!__imp_?Default@CWnd@@IEAA_JXZ` at `0x140028db5`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x140028f82`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x140028f82`
- `MFC42u!__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z` at `0x140028eb3`
- `MFC42u!__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z` at `0x140028eb3`
- `MFC42u!__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z` at `0x140028f2a`
- `MFC42u!__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z` at `0x140028f2a`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x140028e96`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x140028ff2`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x140028e96`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x140028ff2`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x140028fb2`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x140028fe4`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x140028fb2`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x140028fe4`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x140028fa0`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x140028fd7`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x140028fa0`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x140028fd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140028dee`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140028dee`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CChildFrame::OnNcPaint(CChildFrame *this)
{
  char v2; // r14
  char v3; // al
  struct CFont *v4; // r15
  __int64 v5; // rax
  __int64 v6; // rdi
  DWORD SysColor; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  unsigned int v11; // edi
  int v12; // ebx
  __int64 v13; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v14[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v15[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h]
  _BYTE v17[40]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v18[64]; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT v19; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v20[4]; // [rsp+E0h] [rbp-20h] BYREF
  HDC v21[10]; // [rsp+F0h] [rbp-10h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+140h] [rbp+40h] BYREF
  int pvParam; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v24[20]; // [rsp+264h] [rbp+164h] BYREF
  struct tagLOGFONTW v25; // [rsp+278h] [rbp+178h] BYREF

  CWnd::Default(this);
  v2 = *((_BYTE *)this + 1026);
  if ( byte_1401606C1 )
  {
    byte_1401606C1 = 0;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
    VersionInformation.dwOSVersionInfoSize = 276;
    GetVersionExW(&VersionInformation);
    v3 = VersionInformation.dwPlatformId == 2
      && (VersionInformation.dwMajorVersion > 5
       || VersionInformation.dwMajorVersion == 5 && VersionInformation.dwMinorVersion);
    byte_1401624E8 = v3;
  }
  else
  {
    v3 = byte_1401624E8;
  }
  if ( !v3 )
  {
    CWindowDC::CWindowDC((CWindowDC *)v15, this);
    memset_0(v24, 0, 0x1F4u);
    pvParam = 504;
    SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0);
    v14[1] = 0;
    v14[0] = &CFont::`vftable';
    CFont::CreateFontIndirectW((CFont *)v14, &v25);
    v4 = CDC::SelectObject((CDC *)v15, (struct CFont *)v14);
    CString::CString(&v13);
    CWnd::GetWindowTextW(this, (struct CString *)&v13);
    v5 = std::wstring::wstring(v17, v13);
    CRichText::CRichText(v21, v16, v5);
    CFontLinker::CFontLinker((CFontLinker *)v18);
    if ( CFontLinker::ComposeRichText((CFontLinker *)v18, (struct CRichText *)v21)
      && !CRichText::IsDefaultFontSufficient((CRichText *)v21) )
    {
      ComputeCaptionRects(this, v20, &v19, &pvParam);
      CDC::IntersectClipRect((CDC *)v15, &v19);
      v6 = v16;
      SysColor = GetSysColor(28 - (v2 != 0));
      v8 = GetSysColor(3 - (v2 != 0));
      if ( !GradientFillRect(v6, v20, v8, SysColor) )
      {
        v9 = GetSysColor(3 - (v2 != 0));
        CDC::FillSolidRect((CDC *)v15, &v19, v9);
      }
      v10 = GetSysColor(v2 != 0 ? 9 : 19);
      v11 = CDC::SetTextColor((CDC *)v15, v10);
      v12 = CDC::SetBkMode((CDC *)v15, 1);
      CRichText::Draw(v21, &v19, 0x8824u, 0);
      CDC::SetTextColor((CDC *)v15, v11);
      CDC::SetBkMode((CDC *)v15, v12);
    }
    CDC::SelectObject((CDC *)v15, v4);
    CFontLinker::~CFontLinker((CFontLinker *)v18);
    CRichText::~CRichText((CRichText *)v21);
    CString::~CString(&v13);
    v14[0] = &CFont::`vftable';
    CGdiObject::~CGdiObject((CGdiObject *)v14);
    CWindowDC::~CWindowDC((CWindowDC *)v15);
  }
}

```

## disassembly

```asm
0x140028d80  mov     [rsp-8+arg_8], rbx
0x140028d85  mov     [rsp-8+arg_10], rsi
0x140028d8a  push    rbp
0x140028d8b  push    rdi
0x140028d8c  push    r13
0x140028d8e  push    r14
0x140028d90  push    r15
0x140028d92  lea     rbp, [rsp-370h]
0x140028d9a  sub     rsp, 470h
0x140028da1  mov     rax, cs:__security_cookie
0x140028da8  xor     rax, rsp
0x140028dab  mov     [rbp+390h+var_30], rax
0x140028db2  mov     rbx, rcx
0x140028db5  call    cs:__imp_?Default@CWnd@@IEAA_JXZ; CWnd::Default(void)
0x140028dbb  mov     r14b, [rbx+402h]
0x140028dc2  cmp     cs:byte_1401606C1, 0
0x140028dc9  jz      short loc_140028E16
0x140028dcb  mov     cs:byte_1401606C1, 0
0x140028dd2  xor     edx, edx; Val
0x140028dd4  mov     r8d, 110h; Size
0x140028dda  lea     rcx, [rbp+390h+VersionInformation.dwMajorVersion]; void *
0x140028dde  call    memset_0
0x140028de3  mov     [rbp+390h+VersionInformation.dwOSVersionInfoSize], 114h
0x140028dea  lea     rcx, [rbp+390h+VersionInformation]; lpVersionInformation
0x140028dee  call    cs:__imp_GetVersionExW
0x140028df4  cmp     [rbp+390h+VersionInformation.dwPlatformId], 2
0x140028df8  jnz     short loc_140028E0C
0x140028dfa  cmp     [rbp+390h+VersionInformation.dwMajorVersion], 5
0x140028dfe  ja      short loc_140028E08
0x140028e00  jnz     short loc_140028E0C
0x140028e02  cmp     [rbp+390h+VersionInformation.dwMinorVersion], 1
0x140028e06  jb      short loc_140028E0C
0x140028e08  mov     al, 1
0x140028e0a  jmp     short loc_140028E0E
0x140028e0c  xor     al, al
0x140028e0e  mov     cs:byte_1401624E8, al
0x140028e14  jmp     short loc_140028E1C
0x140028e16  mov     al, cs:byte_1401624E8
0x140028e1c  test    al, al
0x140028e1e  jnz     loc_140029034
0x140028e24  mov     rdx, rbx
0x140028e27  lea     rcx, [rsp+490h+var_458]
0x140028e2c  call    cs:__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x140028e32  nop
0x140028e33  xor     edx, edx; Val
0x140028e35  mov     r8d, 1F4h; Size
0x140028e3b  lea     rcx, [rbp+390h+var_22C]; void *
0x140028e42  call    memset_0
0x140028e47  mov     edx, 1F8h; uiParam
0x140028e4c  mov     [rbp+390h+pvParam], edx
0x140028e52  xor     r9d, r9d; fWinIni
0x140028e55  lea     r8, [rbp+390h+pvParam]; pvParam
0x140028e5c  lea     ecx, [r9+29h]; uiAction
0x140028e60  call    cs:__imp_SystemParametersInfoW
0x140028e66  mov     [rsp+490h+var_460], 0
0x140028e6f  lea     r13, ??_7CFont@@6B@; const CFont::`vftable'
0x140028e76  mov     [rsp+490h+var_468], r13
0x140028e7b  lea     rdx, [rbp+390h+var_218]; struct tagLOGFONTW *
0x140028e82  lea     rcx, [rsp+490h+var_468]; this
0x140028e87  call    ?CreateFontIndirectW@CFont@@QEAAHPEBUtagLOGFONTW@@@Z; CFont::CreateFontIndirectW(tagLOGFONTW const *)
0x140028e8c  lea     rdx, [rsp+490h+var_468]
0x140028e91  lea     rcx, [rsp+490h+var_458]
0x140028e96  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x140028e9c  mov     r15, rax
0x140028e9f  lea     rcx, [rsp+490h+var_470]
0x140028ea4  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x140028eaa  nop
0x140028eab  lea     rdx, [rsp+490h+var_470]
0x140028eb0  mov     rcx, rbx
0x140028eb3  call    cs:__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z; CWnd::GetWindowTextW(CString &)
0x140028eb9  mov     rdx, [rsp+490h+var_470]
0x140028ebe  lea     rcx, [rsp+490h+var_428]
0x140028ec3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140028ec8  mov     r8, rax
0x140028ecb  mov     rdx, [rsp+490h+var_450]
0x140028ed0  lea     rcx, [rbp+390h+var_3A0]
0x140028ed4  call    ??0CRichText@@QEAA@PEAUHDC__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CRichText::CRichText(HDC__ *,std::wstring)
0x140028ed9  nop
0x140028eda  lea     rcx, [rbp+390h+var_400]; this
0x140028ede  call    ??0CFontLinker@@QEAA@XZ; CFontLinker::CFontLinker(void)
0x140028ee3  nop
0x140028ee4  lea     rdx, [rbp+390h+var_3A0]; struct CRichText *
0x140028ee8  lea     rcx, [rbp+390h+var_400]; this
0x140028eec  call    ?ComposeRichText@CFontLinker@@QEAA_NAEAVCRichText@@@Z; CFontLinker::ComposeRichText(CRichText &)
0x140028ef1  test    al, al
0x140028ef3  jz      loc_140028FEA
0x140028ef9  lea     rcx, [rbp+390h+var_3A0]; this
0x140028efd  call    ?IsDefaultFontSufficient@CRichText@@QEBA_NXZ; CRichText::IsDefaultFontSufficient(void)
0x140028f02  test    al, al
0x140028f04  jnz     loc_140028FEA
0x140028f0a  lea     r9, [rbp+390h+pvParam]
0x140028f11  lea     r8, [rbp+390h+var_3C0]
0x140028f15  lea     rdx, [rbp+390h+var_3B0]
0x140028f19  mov     rcx, rbx
0x140028f1c  call    ComputeCaptionRects
0x140028f21  lea     rdx, [rbp+390h+var_3C0]
0x140028f25  lea     rcx, [rsp+490h+var_458]
0x140028f2a  call    cs:__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z; CDC::IntersectClipRect(tagRECT const *)
0x140028f30  mov     rdi, [rsp+490h+var_450]
0x140028f35  mov     al, r14b
0x140028f38  neg     al
0x140028f3a  sbb     esi, esi
0x140028f3c  mov     al, r14b
0x140028f3f  neg     al
0x140028f41  sbb     ecx, ecx
0x140028f43  add     ecx, 1Ch; nIndex
0x140028f46  call    cs:__imp_GetSysColor
0x140028f4c  mov     ebx, eax
0x140028f4e  lea     ecx, [rsi+3]; nIndex
0x140028f51  call    cs:__imp_GetSysColor
0x140028f57  mov     r9d, ebx
0x140028f5a  mov     r8d, eax
0x140028f5d  lea     rdx, [rbp+390h+var_3B0]
0x140028f61  mov     rcx, rdi
0x140028f64  call    GradientFillRect
0x140028f69  test    al, al
0x140028f6b  jnz     short loc_140028F88
0x140028f6d  lea     ecx, [rsi+3]; nIndex
0x140028f70  call    cs:__imp_GetSysColor
0x140028f76  mov     r8d, eax
0x140028f79  lea     rdx, [rbp+390h+var_3C0]
0x140028f7d  lea     rcx, [rsp+490h+var_458]
0x140028f82  call    cs:__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z; CDC::FillSolidRect(tagRECT const *,ulong)
0x140028f88  neg     r14b
0x140028f8b  sbb     ecx, ecx
0x140028f8d  and     ecx, 0FFFFFFF6h
0x140028f90  add     ecx, 13h; nIndex
0x140028f93  call    cs:__imp_GetSysColor
0x140028f99  mov     edx, eax
0x140028f9b  lea     rcx, [rsp+490h+var_458]
0x140028fa0  call    cs:__imp_?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x140028fa6  mov     edi, eax
0x140028fa8  mov     edx, 1
0x140028fad  lea     rcx, [rsp+490h+var_458]
0x140028fb2  call    cs:__imp_?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x140028fb8  mov     ebx, eax
0x140028fba  xor     r9d, r9d; struct tagRECT *
0x140028fbd  mov     r8d, 8824h; unsigned int
0x140028fc3  lea     rdx, [rbp+390h+var_3C0]; struct tagRECT *
0x140028fc7  lea     rcx, [rbp+390h+var_3A0]; this
0x140028fcb  call    ?Draw@CRichText@@QEBA_NPEBUtagRECT@@IPEAU2@@Z; CRichText::Draw(tagRECT const *,uint,tagRECT *)
0x140028fd0  mov     edx, edi
0x140028fd2  lea     rcx, [rsp+490h+var_458]
0x140028fd7  call    cs:__imp_?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x140028fdd  mov     edx, ebx
0x140028fdf  lea     rcx, [rsp+490h+var_458]
0x140028fe4  call    cs:__imp_?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x140028fea  mov     rdx, r15
0x140028fed  lea     rcx, [rsp+490h+var_458]
0x140028ff2  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x140028ff8  nop
0x140028ff9  lea     rcx, [rbp+390h+var_400]; this
0x140028ffd  call    ??1CFontLinker@@UEAA@XZ; CFontLinker::~CFontLinker(void)
0x140029002  nop
0x140029003  lea     rcx, [rbp+390h+var_3A0]; this
0x140029007  call    ??1CRichText@@QEAA@XZ; CRichText::~CRichText(void)
0x14002900c  nop
0x14002900d  lea     rcx, [rsp+490h+var_470]
0x140029012  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x140029018  nop
0x140029019  mov     [rsp+490h+var_468], r13
0x14002901e  lea     rcx, [rsp+490h+var_468]; this
0x140029023  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140029028  nop
0x140029029  lea     rcx, [rsp+490h+var_458]
0x14002902e  call    cs:__imp_??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x140029034  mov     rcx, [rbp+390h+var_30]
0x14002903b  xor     rcx, rsp; StackCookie
0x14002903e  call    __security_check_cookie
0x140029043  lea     r11, [rsp+490h+var_20]
0x14002904b  mov     rbx, [r11+38h]
0x14002904f  mov     rsi, [r11+40h]
0x140029053  mov     rsp, r11
0x140029056  pop     r15
0x140029058  pop     r14
0x14002905a  pop     r13
0x14002905c  pop     rdi
0x14002905d  pop     rbp
0x14002905e  retn
```

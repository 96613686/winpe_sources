# CMainFrame::OnNcActivate(int)

- ea: `0x140027e90`
- end: `0x14002810e`
- name: `?OnNcActivate@CMainFrame@@IEAAHH@Z`
- size: `638`
- prototype: `__int64 __fastcall(CMainFrame *__hidden this, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14000d478`
- `0x14000d5c0`
- `0x14000d750`
- `0x14000e9cc`
- `0x1400253a4`
- `0x140027e90`
- `0x1400283ac`
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

- `USER32!GetSysColor` at `0x140027ff3`
- `USER32!GetSysColor` at `0x140027ffe`
- `USER32!GetSysColor` at `0x14002801d`
- `USER32!GetSysColor` at `0x140028040`
- `USER32!GetSysColor` at `0x140027ff3`
- `USER32!GetSysColor` at `0x140027ffe`
- `USER32!GetSysColor` at `0x14002801d`
- `USER32!GetSysColor` at `0x140028040`
- `USER32!SystemParametersInfoW` at `0x140027f13`
- `USER32!SystemParametersInfoW` at `0x140027f13`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x140027f54`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x140027f54`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x140027ee8`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x140027ee8`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400280bf`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400280bf`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x1400280db`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x1400280db`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x14002802f`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x14002802f`
- `MFC42u!__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z` at `0x140027f63`
- `MFC42u!__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z` at `0x140027f63`
- `MFC42u!__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z` at `0x140027fd7`
- `MFC42u!__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z` at `0x140027fd7`
- `MFC42u!__imp_?OnNcActivate@CFrameWnd@@IEAAHH@Z` at `0x140027ec3`
- `MFC42u!__imp_?OnNcActivate@CFrameWnd@@IEAAHH@Z` at `0x140027ec3`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x140027f46`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x14002809f`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x140027f46`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x14002809f`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x14002805f`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x140028091`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x14002805f`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x140028091`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x14002804d`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x140028084`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x14002804d`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x140028084`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMainFrame::OnNcActivate(CMainFrame *this, int a2)
{
  unsigned int v3; // r15d
  char v4; // r14
  struct CFont *v5; // r12
  __int64 v6; // rax
  __int64 v7; // rdi
  DWORD SysColor; // ebx
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  unsigned int v12; // edi
  int v13; // ebx
  __int64 v15; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v16[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h]
  _BYTE v19[40]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v20[64]; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT v21; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v22[4]; // [rsp+E0h] [rbp-20h] BYREF
  HDC v23[10]; // [rsp+F0h] [rbp-10h] BYREF
  int pvParam; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v25[20]; // [rsp+144h] [rbp+44h] BYREF
  struct tagLOGFONTW v26; // [rsp+158h] [rbp+58h] BYREF

  v3 = CFrameWnd::OnNcActivate(this, a2);
  v4 = *((_BYTE *)this + 642);
  if ( !IsWhistler() )
  {
    CWindowDC::CWindowDC((CWindowDC *)v17, this);
    memset_0(v25, 0, 0x1F4u);
    pvParam = 504;
    SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0);
    v16[1] = 0;
    v16[0] = &CFont::`vftable';
    CFont::CreateFontIndirectW((CFont *)v16, &v26);
    v5 = CDC::SelectObject((CDC *)v17, (struct CFont *)v16);
    CString::CString(&v15);
    CWnd::GetWindowTextW(this, (struct CString *)&v15);
    v6 = std::wstring::wstring(v19, v15);
    CRichText::CRichText(v23, v18, v6);
    CFontLinker::CFontLinker((CFontLinker *)v20);
    if ( CFontLinker::ComposeRichText((CFontLinker *)v20, (struct CRichText *)v23)
      && !CRichText::IsDefaultFontSufficient((CRichText *)v23) )
    {
      ComputeCaptionRects(this, v22, &v21, &pvParam);
      CDC::IntersectClipRect((CDC *)v17, &v21);
      v7 = v18;
      SysColor = GetSysColor(28 - (v4 != 0));
      v9 = GetSysColor(3 - (v4 != 0));
      if ( !GradientFillRect(v7, v22, v9, SysColor) )
      {
        v10 = GetSysColor(3 - (v4 != 0));
        CDC::FillSolidRect((CDC *)v17, &v21, v10);
      }
      v11 = GetSysColor(v4 != 0 ? 9 : 19);
      v12 = CDC::SetTextColor((CDC *)v17, v11);
      v13 = CDC::SetBkMode((CDC *)v17, 1);
      CRichText::Draw(v23, &v21, 0x8824u, 0);
      CDC::SetTextColor((CDC *)v17, v12);
      CDC::SetBkMode((CDC *)v17, v13);
    }
    CDC::SelectObject((CDC *)v17, v5);
    CFontLinker::~CFontLinker((CFontLinker *)v20);
    CRichText::~CRichText((CRichText *)v23);
    CString::~CString(&v15);
    v16[0] = &CFont::`vftable';
    CGdiObject::~CGdiObject((CGdiObject *)v16);
    CWindowDC::~CWindowDC((CWindowDC *)v17);
  }
  return v3;
}

```

## disassembly

```asm
0x140027e90  mov     [rsp-8+arg_10], rbx
0x140027e95  push    rbp
0x140027e96  push    rsi
0x140027e97  push    rdi
0x140027e98  push    r12
0x140027e9a  push    r13
0x140027e9c  push    r14
0x140027e9e  push    r15
0x140027ea0  lea     rbp, [rsp-250h]
0x140027ea8  sub     rsp, 350h
0x140027eaf  mov     rax, cs:__security_cookie
0x140027eb6  xor     rax, rsp
0x140027eb9  mov     [rbp+280h+var_40], rax
0x140027ec0  mov     rbx, rcx
0x140027ec3  call    cs:__imp_?OnNcActivate@CFrameWnd@@IEAAHH@Z; CFrameWnd::OnNcActivate(int)
0x140027ec9  mov     r15d, eax
0x140027ecc  mov     r14b, [rbx+282h]
0x140027ed3  call    ?IsWhistler@@YA_NXZ; IsWhistler(void)
0x140027ed8  test    al, al
0x140027eda  jnz     loc_1400280E1
0x140027ee0  mov     rdx, rbx
0x140027ee3  lea     rcx, [rsp+380h+var_348]
0x140027ee8  call    cs:__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x140027eee  nop
0x140027eef  xor     edx, edx; Val
0x140027ef1  mov     r8d, 1F4h; Size
0x140027ef7  lea     rcx, [rbp+280h+var_23C]; void *
0x140027efb  call    memset_0
0x140027f00  mov     edx, 1F8h; uiParam
0x140027f05  mov     [rbp+280h+pvParam], edx
0x140027f08  xor     r9d, r9d; fWinIni
0x140027f0b  lea     r8, [rbp+280h+pvParam]; pvParam
0x140027f0f  lea     ecx, [r9+29h]; uiAction
0x140027f13  call    cs:__imp_SystemParametersInfoW
0x140027f19  mov     [rsp+380h+var_350], 0
0x140027f22  lea     r13, ??_7CFont@@6B@; const CFont::`vftable'
0x140027f29  mov     [rsp+380h+var_358], r13
0x140027f2e  lea     rdx, [rbp+280h+var_228]; struct tagLOGFONTW *
0x140027f32  lea     rcx, [rsp+380h+var_358]; this
0x140027f37  call    ?CreateFontIndirectW@CFont@@QEAAHPEBUtagLOGFONTW@@@Z; CFont::CreateFontIndirectW(tagLOGFONTW const *)
0x140027f3c  lea     rdx, [rsp+380h+var_358]
0x140027f41  lea     rcx, [rsp+380h+var_348]
0x140027f46  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x140027f4c  mov     r12, rax
0x140027f4f  lea     rcx, [rsp+380h+var_360]
0x140027f54  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x140027f5a  nop
0x140027f5b  lea     rdx, [rsp+380h+var_360]
0x140027f60  mov     rcx, rbx
0x140027f63  call    cs:__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z; CWnd::GetWindowTextW(CString &)
0x140027f69  mov     rdx, [rsp+380h+var_360]
0x140027f6e  lea     rcx, [rsp+380h+var_318]
0x140027f73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140027f78  mov     r8, rax
0x140027f7b  mov     rdx, [rsp+380h+var_340]
0x140027f80  lea     rcx, [rbp+280h+var_290]
0x140027f84  call    ??0CRichText@@QEAA@PEAUHDC__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CRichText::CRichText(HDC__ *,std::wstring)
0x140027f89  nop
0x140027f8a  lea     rcx, [rbp+280h+var_2F0]; this
0x140027f8e  call    ??0CFontLinker@@QEAA@XZ; CFontLinker::CFontLinker(void)
0x140027f93  nop
0x140027f94  lea     rdx, [rbp+280h+var_290]; struct CRichText *
0x140027f98  lea     rcx, [rbp+280h+var_2F0]; this
0x140027f9c  call    ?ComposeRichText@CFontLinker@@QEAA_NAEAVCRichText@@@Z; CFontLinker::ComposeRichText(CRichText &)
0x140027fa1  test    al, al
0x140027fa3  jz      loc_140028097
0x140027fa9  lea     rcx, [rbp+280h+var_290]; this
0x140027fad  call    ?IsDefaultFontSufficient@CRichText@@QEBA_NXZ; CRichText::IsDefaultFontSufficient(void)
0x140027fb2  test    al, al
0x140027fb4  jnz     loc_140028097
0x140027fba  lea     r9, [rbp+280h+pvParam]
0x140027fbe  lea     r8, [rbp+280h+var_2B0]
0x140027fc2  lea     rdx, [rbp+280h+var_2A0]
0x140027fc6  mov     rcx, rbx
0x140027fc9  call    ComputeCaptionRects
0x140027fce  lea     rdx, [rbp+280h+var_2B0]
0x140027fd2  lea     rcx, [rsp+380h+var_348]
0x140027fd7  call    cs:__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z; CDC::IntersectClipRect(tagRECT const *)
0x140027fdd  mov     rdi, [rsp+380h+var_340]
0x140027fe2  mov     al, r14b
0x140027fe5  neg     al
0x140027fe7  sbb     esi, esi
0x140027fe9  mov     al, r14b
0x140027fec  neg     al
0x140027fee  sbb     ecx, ecx
0x140027ff0  add     ecx, 1Ch; nIndex
0x140027ff3  call    cs:__imp_GetSysColor
0x140027ff9  mov     ebx, eax
0x140027ffb  lea     ecx, [rsi+3]; nIndex
0x140027ffe  call    cs:__imp_GetSysColor
0x140028004  mov     r9d, ebx
0x140028007  mov     r8d, eax
0x14002800a  lea     rdx, [rbp+280h+var_2A0]
0x14002800e  mov     rcx, rdi
0x140028011  call    GradientFillRect
0x140028016  test    al, al
0x140028018  jnz     short loc_140028035
0x14002801a  lea     ecx, [rsi+3]; nIndex
0x14002801d  call    cs:__imp_GetSysColor
0x140028023  mov     r8d, eax
0x140028026  lea     rdx, [rbp+280h+var_2B0]
0x14002802a  lea     rcx, [rsp+380h+var_348]
0x14002802f  call    cs:__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z; CDC::FillSolidRect(tagRECT const *,ulong)
0x140028035  neg     r14b
0x140028038  sbb     ecx, ecx
0x14002803a  and     ecx, 0FFFFFFF6h
0x14002803d  add     ecx, 13h; nIndex
0x140028040  call    cs:__imp_GetSysColor
0x140028046  mov     edx, eax
0x140028048  lea     rcx, [rsp+380h+var_348]
0x14002804d  call    cs:__imp_?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x140028053  mov     edi, eax
0x140028055  mov     edx, 1
0x14002805a  lea     rcx, [rsp+380h+var_348]
0x14002805f  call    cs:__imp_?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x140028065  mov     ebx, eax
0x140028067  xor     r9d, r9d; struct tagRECT *
0x14002806a  mov     r8d, 8824h; unsigned int
0x140028070  lea     rdx, [rbp+280h+var_2B0]; struct tagRECT *
0x140028074  lea     rcx, [rbp+280h+var_290]; this
0x140028078  call    ?Draw@CRichText@@QEBA_NPEBUtagRECT@@IPEAU2@@Z; CRichText::Draw(tagRECT const *,uint,tagRECT *)
0x14002807d  mov     edx, edi
0x14002807f  lea     rcx, [rsp+380h+var_348]
0x140028084  call    cs:__imp_?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x14002808a  mov     edx, ebx
0x14002808c  lea     rcx, [rsp+380h+var_348]
0x140028091  call    cs:__imp_?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x140028097  mov     rdx, r12
0x14002809a  lea     rcx, [rsp+380h+var_348]
0x14002809f  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x1400280a5  nop
0x1400280a6  lea     rcx, [rbp+280h+var_2F0]; this
0x1400280aa  call    ??1CFontLinker@@UEAA@XZ; CFontLinker::~CFontLinker(void)
0x1400280af  nop
0x1400280b0  lea     rcx, [rbp+280h+var_290]; this
0x1400280b4  call    ??1CRichText@@QEAA@XZ; CRichText::~CRichText(void)
0x1400280b9  nop
0x1400280ba  lea     rcx, [rsp+380h+var_360]
0x1400280bf  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1400280c5  nop
0x1400280c6  mov     [rsp+380h+var_358], r13
0x1400280cb  lea     rcx, [rsp+380h+var_358]; this
0x1400280d0  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1400280d5  nop
0x1400280d6  lea     rcx, [rsp+380h+var_348]
0x1400280db  call    cs:__imp_??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x1400280e1  mov     eax, r15d
0x1400280e4  mov     rcx, [rbp+280h+var_40]
0x1400280eb  xor     rcx, rsp; StackCookie
0x1400280ee  call    __security_check_cookie
0x1400280f3  mov     rbx, [rsp+380h+arg_10]
0x1400280fb  add     rsp, 350h
0x140028102  pop     r15
0x140028104  pop     r14
0x140028106  pop     r13
0x140028108  pop     r12
0x14002810a  pop     rdi
0x14002810b  pop     rsi
0x14002810c  pop     rbp
0x14002810d  retn
```

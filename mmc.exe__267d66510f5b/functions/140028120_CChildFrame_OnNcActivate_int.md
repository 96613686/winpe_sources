# CChildFrame::OnNcActivate(int)

- ea: `0x140028120`
- end: `0x1400283a4`
- name: `?OnNcActivate@CChildFrame@@IEAAHH@Z`
- size: `644`
- prototype: `__int64 __fastcall(CChildFrame *__hidden this, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14000d478`
- `0x14000d5c0`
- `0x14000d750`
- `0x14000e9cc`
- `0x1400253a4`
- `0x140028120`
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

- `USER32!GetSysColor` at `0x140028288`
- `USER32!GetSysColor` at `0x140028294`
- `USER32!GetSysColor` at `0x1400282b4`
- `USER32!GetSysColor` at `0x1400282d6`
- `USER32!GetSysColor` at `0x140028288`
- `USER32!GetSysColor` at `0x140028294`
- `USER32!GetSysColor` at `0x1400282b4`
- `USER32!GetSysColor` at `0x1400282d6`
- `USER32!SystemParametersInfoW` at `0x1400281a9`
- `USER32!SystemParametersInfoW` at `0x1400281a9`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1400281ea`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1400281ea`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x14002817e`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x14002817e`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x140028355`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x140028355`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x140028371`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x140028371`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x1400282c6`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x1400282c6`
- `MFC42u!__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z` at `0x1400281f9`
- `MFC42u!__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z` at `0x1400281f9`
- `MFC42u!__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z` at `0x14002826d`
- `MFC42u!__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z` at `0x14002826d`
- `MFC42u!__imp_?OnNcActivate@CMDIChildWnd@@IEAAHH@Z` at `0x140028155`
- `MFC42u!__imp_?OnNcActivate@CMDIChildWnd@@IEAAHH@Z` at `0x140028155`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x1400281dc`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x140028335`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x1400281dc`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x140028335`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x1400282f5`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x140028327`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x1400282f5`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x140028327`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x1400282e3`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x14002831a`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x1400282e3`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x14002831a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CChildFrame::OnNcActivate(CChildFrame *this, int a2)
{
  unsigned int v4; // r15d
  struct CFont *v5; // r12
  char *v6; // rax
  __int64 v7; // rdi
  DWORD SysColor; // ebx
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  unsigned int v12; // edi
  int v13; // ebx
  char *v15; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v16[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h]
  char v19[40]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v20[64]; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT v21; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v22[4]; // [rsp+E0h] [rbp-20h] BYREF
  HDC v23[10]; // [rsp+F0h] [rbp-10h] BYREF
  int pvParam; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v25[20]; // [rsp+144h] [rbp+44h] BYREF
  struct tagLOGFONTW v26; // [rsp+158h] [rbp+58h] BYREF

  v4 = CMDIChildWnd::OnNcActivate(this, a2);
  *((_BYTE *)this + 1026) = a2 != 0;
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
      SysColor = GetSysColor(28 - (a2 != 0));
      v9 = GetSysColor(3 - (a2 != 0));
      if ( !GradientFillRect(v7, v22, v9, SysColor) )
      {
        v10 = GetSysColor(3 - (a2 != 0));
        CDC::FillSolidRect((CDC *)v17, &v21, v10);
      }
      v11 = GetSysColor(a2 != 0 ? 9 : 19);
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
  return v4;
}

```

## disassembly

```asm
0x140028120  mov     [rsp-8+arg_10], rbx
0x140028125  push    rbp
0x140028126  push    rsi
0x140028127  push    rdi
0x140028128  push    r12
0x14002812a  push    r13
0x14002812c  push    r14
0x14002812e  push    r15
0x140028130  lea     rbp, [rsp-250h]
0x140028138  sub     rsp, 350h
0x14002813f  mov     rax, cs:__security_cookie
0x140028146  xor     rax, rsp
0x140028149  mov     [rbp+280h+var_40], rax
0x140028150  mov     esi, edx
0x140028152  mov     rbx, rcx
0x140028155  call    cs:__imp_?OnNcActivate@CMDIChildWnd@@IEAAHH@Z; CMDIChildWnd::OnNcActivate(int)
0x14002815b  mov     r15d, eax
0x14002815e  test    esi, esi
0x140028160  setnz   cl
0x140028163  mov     [rbx+402h], cl
0x140028169  call    ?IsWhistler@@YA_NXZ; IsWhistler(void)
0x14002816e  test    al, al
0x140028170  jnz     loc_140028377
0x140028176  mov     rdx, rbx
0x140028179  lea     rcx, [rsp+380h+var_348]
0x14002817e  call    cs:__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x140028184  nop
0x140028185  xor     edx, edx; Val
0x140028187  mov     r8d, 1F4h; Size
0x14002818d  lea     rcx, [rbp+280h+var_23C]; void *
0x140028191  call    memset_0
0x140028196  mov     edx, 1F8h; uiParam
0x14002819b  mov     [rbp+280h+pvParam], edx
0x14002819e  xor     r9d, r9d; fWinIni
0x1400281a1  lea     r8, [rbp+280h+pvParam]; pvParam
0x1400281a5  lea     ecx, [r9+29h]; uiAction
0x1400281a9  call    cs:__imp_SystemParametersInfoW
0x1400281af  mov     [rsp+380h+var_350], 0
0x1400281b8  lea     r13, ??_7CFont@@6B@; const CFont::`vftable'
0x1400281bf  mov     [rsp+380h+var_358], r13
0x1400281c4  lea     rdx, [rbp+280h+var_228]; struct tagLOGFONTW *
0x1400281c8  lea     rcx, [rsp+380h+var_358]; this
0x1400281cd  call    ?CreateFontIndirectW@CFont@@QEAAHPEBUtagLOGFONTW@@@Z; CFont::CreateFontIndirectW(tagLOGFONTW const *)
0x1400281d2  lea     rdx, [rsp+380h+var_358]
0x1400281d7  lea     rcx, [rsp+380h+var_348]
0x1400281dc  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x1400281e2  mov     r12, rax
0x1400281e5  lea     rcx, [rsp+380h+var_360]
0x1400281ea  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x1400281f0  nop
0x1400281f1  lea     rdx, [rsp+380h+var_360]
0x1400281f6  mov     rcx, rbx
0x1400281f9  call    cs:__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z; CWnd::GetWindowTextW(CString &)
0x1400281ff  mov     rdx, [rsp+380h+var_360]
0x140028204  lea     rcx, [rsp+380h+var_318]
0x140028209  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14002820e  mov     r8, rax
0x140028211  mov     rdx, [rsp+380h+var_340]
0x140028216  lea     rcx, [rbp+280h+var_290]
0x14002821a  call    ??0CRichText@@QEAA@PEAUHDC__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CRichText::CRichText(HDC__ *,std::wstring)
0x14002821f  nop
0x140028220  lea     rcx, [rbp+280h+var_2F0]; this
0x140028224  call    ??0CFontLinker@@QEAA@XZ; CFontLinker::CFontLinker(void)
0x140028229  nop
0x14002822a  lea     rdx, [rbp+280h+var_290]; struct CRichText *
0x14002822e  lea     rcx, [rbp+280h+var_2F0]; this
0x140028232  call    ?ComposeRichText@CFontLinker@@QEAA_NAEAVCRichText@@@Z; CFontLinker::ComposeRichText(CRichText &)
0x140028237  test    al, al
0x140028239  jz      loc_14002832D
0x14002823f  lea     rcx, [rbp+280h+var_290]; this
0x140028243  call    ?IsDefaultFontSufficient@CRichText@@QEBA_NXZ; CRichText::IsDefaultFontSufficient(void)
0x140028248  test    al, al
0x14002824a  jnz     loc_14002832D
0x140028250  lea     r9, [rbp+280h+pvParam]
0x140028254  lea     r8, [rbp+280h+var_2B0]
0x140028258  lea     rdx, [rbp+280h+var_2A0]
0x14002825c  mov     rcx, rbx
0x14002825f  call    ComputeCaptionRects
0x140028264  lea     rdx, [rbp+280h+var_2B0]
0x140028268  lea     rcx, [rsp+380h+var_348]
0x14002826d  call    cs:__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z; CDC::IntersectClipRect(tagRECT const *)
0x140028273  mov     rdi, [rsp+380h+var_340]
0x140028278  mov     eax, esi
0x14002827a  neg     eax
0x14002827c  sbb     r14d, r14d
0x14002827f  mov     eax, esi
0x140028281  neg     eax
0x140028283  sbb     ecx, ecx
0x140028285  add     ecx, 1Ch; nIndex
0x140028288  call    cs:__imp_GetSysColor
0x14002828e  mov     ebx, eax
0x140028290  lea     ecx, [r14+3]; nIndex
0x140028294  call    cs:__imp_GetSysColor
0x14002829a  mov     r9d, ebx
0x14002829d  mov     r8d, eax
0x1400282a0  lea     rdx, [rbp+280h+var_2A0]
0x1400282a4  mov     rcx, rdi
0x1400282a7  call    GradientFillRect
0x1400282ac  test    al, al
0x1400282ae  jnz     short loc_1400282CC
0x1400282b0  lea     ecx, [r14+3]; nIndex
0x1400282b4  call    cs:__imp_GetSysColor
0x1400282ba  mov     r8d, eax
0x1400282bd  lea     rdx, [rbp+280h+var_2B0]
0x1400282c1  lea     rcx, [rsp+380h+var_348]
0x1400282c6  call    cs:__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z; CDC::FillSolidRect(tagRECT const *,ulong)
0x1400282cc  neg     esi
0x1400282ce  sbb     ecx, ecx
0x1400282d0  and     ecx, 0FFFFFFF6h
0x1400282d3  add     ecx, 13h; nIndex
0x1400282d6  call    cs:__imp_GetSysColor
0x1400282dc  mov     edx, eax
0x1400282de  lea     rcx, [rsp+380h+var_348]
0x1400282e3  call    cs:__imp_?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x1400282e9  mov     edi, eax
0x1400282eb  mov     edx, 1
0x1400282f0  lea     rcx, [rsp+380h+var_348]
0x1400282f5  call    cs:__imp_?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x1400282fb  mov     ebx, eax
0x1400282fd  xor     r9d, r9d; struct tagRECT *
0x140028300  mov     r8d, 8824h; unsigned int
0x140028306  lea     rdx, [rbp+280h+var_2B0]; struct tagRECT *
0x14002830a  lea     rcx, [rbp+280h+var_290]; this
0x14002830e  call    ?Draw@CRichText@@QEBA_NPEBUtagRECT@@IPEAU2@@Z; CRichText::Draw(tagRECT const *,uint,tagRECT *)
0x140028313  mov     edx, edi
0x140028315  lea     rcx, [rsp+380h+var_348]
0x14002831a  call    cs:__imp_?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x140028320  mov     edx, ebx
0x140028322  lea     rcx, [rsp+380h+var_348]
0x140028327  call    cs:__imp_?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x14002832d  mov     rdx, r12
0x140028330  lea     rcx, [rsp+380h+var_348]
0x140028335  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x14002833b  nop
0x14002833c  lea     rcx, [rbp+280h+var_2F0]; this
0x140028340  call    ??1CFontLinker@@UEAA@XZ; CFontLinker::~CFontLinker(void)
0x140028345  nop
0x140028346  lea     rcx, [rbp+280h+var_290]; this
0x14002834a  call    ??1CRichText@@QEAA@XZ; CRichText::~CRichText(void)
0x14002834f  nop
0x140028350  lea     rcx, [rsp+380h+var_360]
0x140028355  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14002835b  nop
0x14002835c  mov     [rsp+380h+var_358], r13
0x140028361  lea     rcx, [rsp+380h+var_358]; this
0x140028366  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x14002836b  nop
0x14002836c  lea     rcx, [rsp+380h+var_348]
0x140028371  call    cs:__imp_??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x140028377  mov     eax, r15d
0x14002837a  mov     rcx, [rbp+280h+var_40]
0x140028381  xor     rcx, rsp; StackCookie
0x140028384  call    __security_check_cookie
0x140028389  mov     rbx, [rsp+380h+arg_10]
0x140028391  add     rsp, 350h
0x140028398  pop     r15
0x14002839a  pop     r14
0x14002839c  pop     r13
0x14002839e  pop     r12
0x1400283a0  pop     rdi
0x1400283a1  pop     rsi
0x1400283a2  pop     rbp
0x1400283a3  retn
```

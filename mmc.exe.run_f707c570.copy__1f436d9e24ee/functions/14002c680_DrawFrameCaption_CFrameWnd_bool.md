# DrawFrameCaption(CFrameWnd *,bool)

- ea: `0x14002c680`
- end: `0x14002c9a0`
- name: `?DrawFrameCaption@@YA_NPEAVCFrameWnd@@_N@Z`
- size: `800`
- prototype: `bool __fastcall(struct CFrameWnd *, bool)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1400ac480`
- `0x1400bc920`

## callees

- `0x14000d478`
- `0x14000d5c0`
- `0x14000d750`
- `0x14000e9cc`
- `0x1400253a4`
- `0x14002c680`
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

- `USER32!GetSysColor` at `0x14002c837`
- `USER32!GetSysColor` at `0x14002c842`
- `USER32!GetSysColor` at `0x14002c861`
- `USER32!GetSysColor` at `0x14002c884`
- `USER32!GetSysColor` at `0x14002c837`
- `USER32!GetSysColor` at `0x14002c842`
- `USER32!GetSysColor` at `0x14002c861`
- `USER32!GetSysColor` at `0x14002c884`
- `USER32!SystemParametersInfoW` at `0x14002c756`
- `USER32!SystemParametersInfoW` at `0x14002c756`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14002c79a`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14002c79a`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x14002c722`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x14002c722`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14002c903`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14002c951`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14002c903`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14002c951`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x14002c91f`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x14002c96d`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x14002c91f`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x14002c96d`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x14002c873`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x14002c873`
- `MFC42u!__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z` at `0x14002c7a9`
- `MFC42u!__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z` at `0x14002c7a9`
- `MFC42u!__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z` at `0x14002c820`
- `MFC42u!__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z` at `0x14002c820`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x14002c78c`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x14002c8e3`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x14002c931`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x14002c78c`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x14002c8e3`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x14002c931`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x14002c8a3`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x14002c8d5`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x14002c8a3`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x14002c8d5`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x14002c891`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x14002c8c8`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x14002c891`
- `MFC42u!__imp_?SetTextColor@CDC@@UEAAKK@Z` at `0x14002c8c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x14002c6e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x14002c6e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall DrawFrameCaption(struct CFrameWnd *a1, unsigned __int8 a2)
{
  int v2; // esi
  char v4; // al
  struct CFont *v5; // r15
  __int64 v6; // rax
  __int64 v7; // rdi
  int v8; // r14d
  DWORD SysColor; // ebx
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  unsigned int v13; // edi
  int v14; // ebx
  __int64 v16; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v17[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h]
  _BYTE v20[40]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v21[64]; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT v22; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v23[4]; // [rsp+E0h] [rbp-20h] BYREF
  HDC v24[10]; // [rsp+F0h] [rbp-10h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+140h] [rbp+40h] BYREF
  int pvParam; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v27[20]; // [rsp+264h] [rbp+164h] BYREF
  struct tagLOGFONTW v28; // [rsp+278h] [rbp+178h] BYREF

  v2 = a2;
  if ( byte_1401606C1 )
  {
    byte_1401606C1 = 0;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
    VersionInformation.dwOSVersionInfoSize = 276;
    GetVersionExW(&VersionInformation);
    v4 = VersionInformation.dwPlatformId == 2
      && (VersionInformation.dwMajorVersion > 5
       || VersionInformation.dwMajorVersion == 5 && VersionInformation.dwMinorVersion);
    byte_1401624E8 = v4;
  }
  else
  {
    v4 = byte_1401624E8;
  }
  if ( v4 )
    return 0;
  CWindowDC::CWindowDC((CWindowDC *)v18, a1);
  memset_0(v27, 0, 0x1F4u);
  pvParam = 504;
  SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0);
  v17[1] = 0;
  v17[0] = &CFont::`vftable';
  CFont::CreateFontIndirectW((CFont *)v17, &v28);
  v5 = CDC::SelectObject((CDC *)v18, (struct CFont *)v17);
  CString::CString(&v16);
  CWnd::GetWindowTextW(a1, (struct CString *)&v16);
  v6 = std::wstring::wstring(v20, v16);
  CRichText::CRichText(v24, v19, v6);
  CFontLinker::CFontLinker((CFontLinker *)v21);
  if ( !CFontLinker::ComposeRichText((CFontLinker *)v21, (struct CRichText *)v24)
    || CRichText::IsDefaultFontSufficient((CRichText *)v24) )
  {
    CDC::SelectObject((CDC *)v18, v5);
    CFontLinker::~CFontLinker((CFontLinker *)v21);
    CRichText::~CRichText((CRichText *)v24);
    CString::~CString(&v16);
    v17[0] = &CFont::`vftable';
    CGdiObject::~CGdiObject((CGdiObject *)v17);
    CWindowDC::~CWindowDC((CWindowDC *)v18);
    return 0;
  }
  ComputeCaptionRects(a1, v23, &v22, &pvParam);
  CDC::IntersectClipRect((CDC *)v18, &v22);
  v7 = v19;
  v8 = (v2 ^ 1) + 2;
  SysColor = GetSysColor((v2 ^ 1) + 27);
  v10 = GetSysColor(v8);
  if ( !GradientFillRect(v7, v23, v10, SysColor) )
  {
    v11 = GetSysColor(v8);
    CDC::FillSolidRect((CDC *)v18, &v22, v11);
  }
  v12 = GetSysColor((_BYTE)v2 != 0 ? 9 : 19);
  v13 = CDC::SetTextColor((CDC *)v18, v12);
  v14 = CDC::SetBkMode((CDC *)v18, 1);
  CRichText::Draw(v24, &v22, 0x8824u, 0);
  CDC::SetTextColor((CDC *)v18, v13);
  CDC::SetBkMode((CDC *)v18, v14);
  CDC::SelectObject((CDC *)v18, v5);
  CFontLinker::~CFontLinker((CFontLinker *)v21);
  CRichText::~CRichText((CRichText *)v24);
  CString::~CString(&v16);
  v17[0] = &CFont::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)v17);
  CWindowDC::~CWindowDC((CWindowDC *)v18);
  return 1;
}

```

## disassembly

```asm
0x14002c680  mov     [rsp-8+arg_8], rbx
0x14002c685  mov     [rsp-8+arg_10], rsi
0x14002c68a  push    rbp
0x14002c68b  push    rdi
0x14002c68c  push    r13
0x14002c68e  push    r14
0x14002c690  push    r15
0x14002c692  lea     rbp, [rsp-370h]
0x14002c69a  sub     rsp, 470h
0x14002c6a1  mov     rax, cs:__security_cookie
0x14002c6a8  xor     rax, rsp
0x14002c6ab  mov     [rbp+390h+var_30], rax
0x14002c6b2  movzx   esi, dl
0x14002c6b5  mov     rbx, rcx
0x14002c6b8  cmp     cs:byte_1401606C1, 0
0x14002c6bf  jz      short loc_14002C70C
0x14002c6c1  mov     cs:byte_1401606C1, 0
0x14002c6c8  xor     edx, edx; Val
0x14002c6ca  mov     r8d, 110h; Size
0x14002c6d0  lea     rcx, [rbp+390h+VersionInformation.dwMajorVersion]; void *
0x14002c6d4  call    memset_0
0x14002c6d9  mov     [rbp+390h+VersionInformation.dwOSVersionInfoSize], 114h
0x14002c6e0  lea     rcx, [rbp+390h+VersionInformation]; lpVersionInformation
0x14002c6e4  call    cs:__imp_GetVersionExW
0x14002c6ea  cmp     [rbp+390h+VersionInformation.dwPlatformId], 2
0x14002c6ee  jnz     short loc_14002C702
0x14002c6f0  cmp     [rbp+390h+VersionInformation.dwMajorVersion], 5
0x14002c6f4  ja      short loc_14002C6FE
0x14002c6f6  jnz     short loc_14002C702
0x14002c6f8  cmp     [rbp+390h+VersionInformation.dwMinorVersion], 1
0x14002c6fc  jb      short loc_14002C702
0x14002c6fe  mov     al, 1
0x14002c700  jmp     short loc_14002C704
0x14002c702  xor     al, al
0x14002c704  mov     cs:byte_1401624E8, al
0x14002c70a  jmp     short loc_14002C712
0x14002c70c  mov     al, cs:byte_1401624E8
0x14002c712  test    al, al
0x14002c714  jnz     loc_14002C973
0x14002c71a  mov     rdx, rbx
0x14002c71d  lea     rcx, [rsp+490h+var_458]
0x14002c722  call    cs:__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x14002c728  nop
0x14002c729  xor     edx, edx; Val
0x14002c72b  mov     r8d, 1F4h; Size
0x14002c731  lea     rcx, [rbp+390h+var_22C]; void *
0x14002c738  call    memset_0
0x14002c73d  mov     edx, 1F8h; uiParam
0x14002c742  mov     [rbp+390h+pvParam], edx
0x14002c748  xor     r9d, r9d; fWinIni
0x14002c74b  lea     r8, [rbp+390h+pvParam]; pvParam
0x14002c752  lea     ecx, [r9+29h]; uiAction
0x14002c756  call    cs:__imp_SystemParametersInfoW
0x14002c75c  mov     [rsp+490h+var_460], 0
0x14002c765  lea     r13, ??_7CFont@@6B@; const CFont::`vftable'
0x14002c76c  mov     [rsp+490h+var_468], r13
0x14002c771  lea     rdx, [rbp+390h+var_218]; struct tagLOGFONTW *
0x14002c778  lea     rcx, [rsp+490h+var_468]; this
0x14002c77d  call    ?CreateFontIndirectW@CFont@@QEAAHPEBUtagLOGFONTW@@@Z; CFont::CreateFontIndirectW(tagLOGFONTW const *)
0x14002c782  lea     rdx, [rsp+490h+var_468]
0x14002c787  lea     rcx, [rsp+490h+var_458]
0x14002c78c  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x14002c792  mov     r15, rax
0x14002c795  lea     rcx, [rsp+490h+var_470]
0x14002c79a  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x14002c7a0  nop
0x14002c7a1  lea     rdx, [rsp+490h+var_470]
0x14002c7a6  mov     rcx, rbx
0x14002c7a9  call    cs:__imp_?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z; CWnd::GetWindowTextW(CString &)
0x14002c7af  mov     rdx, [rsp+490h+var_470]
0x14002c7b4  lea     rcx, [rsp+490h+var_428]
0x14002c7b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14002c7be  mov     r8, rax
0x14002c7c1  mov     rdx, [rsp+490h+var_450]
0x14002c7c6  lea     rcx, [rbp+390h+var_3A0]
0x14002c7ca  call    ??0CRichText@@QEAA@PEAUHDC__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CRichText::CRichText(HDC__ *,std::wstring)
0x14002c7cf  nop
0x14002c7d0  lea     rcx, [rbp+390h+var_400]; this
0x14002c7d4  call    ??0CFontLinker@@QEAA@XZ; CFontLinker::CFontLinker(void)
0x14002c7d9  nop
0x14002c7da  lea     rdx, [rbp+390h+var_3A0]; struct CRichText *
0x14002c7de  lea     rcx, [rbp+390h+var_400]; this
0x14002c7e2  call    ?ComposeRichText@CFontLinker@@QEAA_NAEAVCRichText@@@Z; CFontLinker::ComposeRichText(CRichText &)
0x14002c7e7  test    al, al
0x14002c7e9  jz      loc_14002C929
0x14002c7ef  lea     rcx, [rbp+390h+var_3A0]; this
0x14002c7f3  call    ?IsDefaultFontSufficient@CRichText@@QEBA_NXZ; CRichText::IsDefaultFontSufficient(void)
0x14002c7f8  test    al, al
0x14002c7fa  jnz     loc_14002C929
0x14002c800  lea     r9, [rbp+390h+pvParam]
0x14002c807  lea     r8, [rbp+390h+var_3C0]
0x14002c80b  lea     rdx, [rbp+390h+var_3B0]
0x14002c80f  mov     rcx, rbx
0x14002c812  call    ComputeCaptionRects
0x14002c817  lea     rdx, [rbp+390h+var_3C0]
0x14002c81b  lea     rcx, [rsp+490h+var_458]
0x14002c820  call    cs:__imp_?IntersectClipRect@CDC@@QEAAHPEBUtagRECT@@@Z; CDC::IntersectClipRect(tagRECT const *)
0x14002c826  mov     rdi, [rsp+490h+var_450]
0x14002c82b  mov     ecx, esi
0x14002c82d  xor     ecx, 1
0x14002c830  lea     r14d, [rcx+2]
0x14002c834  add     ecx, 1Bh; nIndex
0x14002c837  call    cs:__imp_GetSysColor
0x14002c83d  mov     ebx, eax
0x14002c83f  mov     ecx, r14d; nIndex
0x14002c842  call    cs:__imp_GetSysColor
0x14002c848  mov     r9d, ebx
0x14002c84b  mov     r8d, eax
0x14002c84e  lea     rdx, [rbp+390h+var_3B0]
0x14002c852  mov     rcx, rdi
0x14002c855  call    GradientFillRect
0x14002c85a  test    al, al
0x14002c85c  jnz     short loc_14002C879
0x14002c85e  mov     ecx, r14d; nIndex
0x14002c861  call    cs:__imp_GetSysColor
0x14002c867  mov     r8d, eax
0x14002c86a  lea     rdx, [rbp+390h+var_3C0]
0x14002c86e  lea     rcx, [rsp+490h+var_458]
0x14002c873  call    cs:__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z; CDC::FillSolidRect(tagRECT const *,ulong)
0x14002c879  neg     sil
0x14002c87c  sbb     ecx, ecx
0x14002c87e  and     ecx, 0FFFFFFF6h
0x14002c881  add     ecx, 13h; nIndex
0x14002c884  call    cs:__imp_GetSysColor
0x14002c88a  mov     edx, eax
0x14002c88c  lea     rcx, [rsp+490h+var_458]
0x14002c891  call    cs:__imp_?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x14002c897  mov     edi, eax
0x14002c899  mov     edx, 1
0x14002c89e  lea     rcx, [rsp+490h+var_458]
0x14002c8a3  call    cs:__imp_?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x14002c8a9  mov     ebx, eax
0x14002c8ab  xor     r9d, r9d; struct tagRECT *
0x14002c8ae  mov     r8d, 8824h; unsigned int
0x14002c8b4  lea     rdx, [rbp+390h+var_3C0]; struct tagRECT *
0x14002c8b8  lea     rcx, [rbp+390h+var_3A0]; this
0x14002c8bc  call    ?Draw@CRichText@@QEBA_NPEBUtagRECT@@IPEAU2@@Z; CRichText::Draw(tagRECT const *,uint,tagRECT *)
0x14002c8c1  mov     edx, edi
0x14002c8c3  lea     rcx, [rsp+490h+var_458]
0x14002c8c8  call    cs:__imp_?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x14002c8ce  mov     edx, ebx
0x14002c8d0  lea     rcx, [rsp+490h+var_458]
0x14002c8d5  call    cs:__imp_?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x14002c8db  mov     rdx, r15
0x14002c8de  lea     rcx, [rsp+490h+var_458]
0x14002c8e3  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x14002c8e9  nop
0x14002c8ea  lea     rcx, [rbp+390h+var_400]; this
0x14002c8ee  call    ??1CFontLinker@@UEAA@XZ; CFontLinker::~CFontLinker(void)
0x14002c8f3  nop
0x14002c8f4  lea     rcx, [rbp+390h+var_3A0]; this
0x14002c8f8  call    ??1CRichText@@QEAA@XZ; CRichText::~CRichText(void)
0x14002c8fd  nop
0x14002c8fe  lea     rcx, [rsp+490h+var_470]
0x14002c903  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14002c909  nop
0x14002c90a  mov     [rsp+490h+var_468], r13
0x14002c90f  lea     rcx, [rsp+490h+var_468]; this
0x14002c914  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x14002c919  nop
0x14002c91a  lea     rcx, [rsp+490h+var_458]
0x14002c91f  call    cs:__imp_??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x14002c925  mov     al, 1
0x14002c927  jmp     short loc_14002C975
0x14002c929  mov     rdx, r15
0x14002c92c  lea     rcx, [rsp+490h+var_458]
0x14002c931  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x14002c937  nop
0x14002c938  lea     rcx, [rbp+390h+var_400]; this
0x14002c93c  call    ??1CFontLinker@@UEAA@XZ; CFontLinker::~CFontLinker(void)
0x14002c941  nop
0x14002c942  lea     rcx, [rbp+390h+var_3A0]; this
0x14002c946  call    ??1CRichText@@QEAA@XZ; CRichText::~CRichText(void)
0x14002c94b  nop
0x14002c94c  lea     rcx, [rsp+490h+var_470]
0x14002c951  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14002c957  nop
0x14002c958  mov     [rsp+490h+var_468], r13
0x14002c95d  lea     rcx, [rsp+490h+var_468]; this
0x14002c962  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x14002c967  nop
0x14002c968  lea     rcx, [rsp+490h+var_458]
0x14002c96d  call    cs:__imp_??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x14002c973  xor     al, al
0x14002c975  mov     rcx, [rbp+390h+var_30]
0x14002c97c  xor     rcx, rsp; StackCookie
0x14002c97f  call    __security_check_cookie
0x14002c984  lea     r11, [rsp+490h+var_20]
0x14002c98c  mov     rbx, [r11+38h]
0x14002c990  mov     rsi, [r11+40h]
0x14002c994  mov     rsp, r11
0x14002c997  pop     r15
0x14002c999  pop     r14
0x14002c99b  pop     r13
0x14002c99d  pop     rdi
0x14002c99e  pop     rbp
0x14002c99f  retn
```

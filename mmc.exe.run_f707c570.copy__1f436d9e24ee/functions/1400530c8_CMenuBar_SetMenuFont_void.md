# CMenuBar::SetMenuFont(void)

- ea: `0x1400530c8`
- end: `0x140053230`
- name: `?SetMenuFont@CMenuBar@@IEAAXXZ`
- size: `360`
- prototype: `void __fastcall(CMenuBar *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140038180`
- `0x14004cf60`

## callees

- `0x1400530c8`
- `0x140062455`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `GDI32!GetTextMetricsW` at `0x1400531a6`
- `GDI32!GetTextMetricsW` at `0x1400531a6`
- `GDI32!CreateFontIndirectW` at `0x140053134`
- `GDI32!CreateFontIndirectW` at `0x140053134`
- `USER32!SendMessageW` at `0x14005315f`
- `USER32!SendMessageW` at `0x14005315f`
- `USER32!SystemParametersInfoW` at `0x14005312a`
- `USER32!SystemParametersInfoW` at `0x14005312a`
- `USER32!GetSystemMetrics` at `0x1400531c9`
- `USER32!GetSystemMetrics` at `0x1400531dc`
- `USER32!GetSystemMetrics` at `0x1400531c9`
- `USER32!GetSystemMetrics` at `0x1400531dc`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x140053184`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x140053184`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x140053206`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x140053206`
- `MFC42u!__imp_?Attach@CGdiObject@@QEAAHPEAX@Z` at `0x140053140`
- `MFC42u!__imp_?Attach@CGdiObject@@QEAAHPEAX@Z` at `0x140053140`
- `MFC42u!__imp_?DeleteObject@CGdiObject@@QEAAHXZ` at `0x140053100`
- `MFC42u!__imp_?DeleteObject@CGdiObject@@QEAAHXZ` at `0x140053100`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x140053193`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x1400531b4`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x140053193`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x1400531b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMenuBar::SetMenuFont(HWND *this)
{
  CGdiObject *v2; // rbx
  HFONT v3; // rax
  WPARAM v4; // r8
  struct CFont *v5; // rbx
  void (__fastcall *v6)(HWND *, __int64); // rbx
  LONG SystemMetrics; // eax
  LONG tmHeight; // ecx
  __int64 v9; // [rsp+20h] [rbp-E0h]
  _BYTE v10[16]; // [rsp+28h] [rbp-D8h] BYREF
  HDC hdc; // [rsp+38h] [rbp-C8h]
  tagTEXTMETRICW tm; // [rsp+50h] [rbp-B0h] BYREF
  int pvParam; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v14[220]; // [rsp+94h] [rbp-6Ch] BYREF
  LOGFONTW lf; // [rsp+170h] [rbp+70h] BYREF

  v2 = (CGdiObject *)(this + 40);
  CGdiObject::DeleteObject((CGdiObject *)(this + 40));
  memset_0(v14, 0, 0x1F4u);
  pvParam = 504;
  SystemParametersInfoW(0x29u, 0, &pvParam, 0);
  v3 = CreateFontIndirectW(&lf);
  CGdiObject::Attach(v2, v3);
  if ( v2 )
    v4 = *((_QWORD *)v2 + 1);
  else
    v4 = 0;
  SendMessageW(this[8], 0x30u, v4, 0);
  memset(&tm, 0, sizeof(tm));
  CWindowDC::CWindowDC((CWindowDC *)v10, (struct CWnd *)this);
  v5 = CDC::SelectObject((CDC *)v10, v2);
  GetTextMetricsW(hdc, &tm);
  CDC::SelectObject((CDC *)v10, v5);
  v6 = (void (__fastcall *)(HWND *, __int64))*((_QWORD *)*this + 49);
  SystemMetrics = GetSystemMetrics(49);
  tmHeight = tm.tmHeight;
  if ( tm.tmHeight <= SystemMetrics )
    tmHeight = GetSystemMetrics(49);
  LODWORD(v9) = 0;
  HIDWORD(v9) = tmHeight;
  v6(this, v9);
  CWindowDC::~CWindowDC((CWindowDC *)v10);
}

```

## disassembly

```asm
0x1400530c8  mov     [rsp-8+arg_8], rbx
0x1400530cd  mov     [rsp-8+arg_10], rdi
0x1400530d2  push    rbp
0x1400530d3  lea     rbp, [rsp-1A0h]
0x1400530db  sub     rsp, 2A0h
0x1400530e2  mov     rax, cs:__security_cookie
0x1400530e9  xor     rax, rsp
0x1400530ec  mov     [rbp+1A0h+var_10], rax
0x1400530f3  mov     rdi, rcx
0x1400530f6  lea     rbx, [rcx+140h]
0x1400530fd  mov     rcx, rbx
0x140053100  call    cs:__imp_?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x140053106  xor     edx, edx; Val
0x140053108  mov     r8d, 1F4h; Size
0x14005310e  lea     rcx, [rbp+1A0h+var_20C]; void *
0x140053112  call    memset_0
0x140053117  mov     [rbp+1A0h+pvParam], 1F8h
0x14005311e  xor     r9d, r9d; fWinIni
0x140053121  lea     r8, [rbp+1A0h+pvParam]; pvParam
0x140053125  xor     edx, edx; uiParam
0x140053127  lea     ecx, [rdx+29h]; uiAction
0x14005312a  call    cs:__imp_SystemParametersInfoW
0x140053130  lea     rcx, [rbp+1A0h+lf]; lplf
0x140053134  call    cs:__imp_CreateFontIndirectW
0x14005313a  mov     rdx, rax
0x14005313d  mov     rcx, rbx
0x140053140  call    cs:__imp_?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x140053146  test    rbx, rbx
0x140053149  jnz     short loc_140053150
0x14005314b  xor     r8d, r8d
0x14005314e  jmp     short loc_140053154
0x140053150  mov     r8, [rbx+8]; wParam
0x140053154  xor     r9d, r9d; lParam
0x140053157  lea     edx, [r9+30h]; Msg
0x14005315b  mov     rcx, [rdi+40h]; hWnd
0x14005315f  call    cs:__imp_SendMessageW
0x140053165  xorps   xmm0, xmm0
0x140053168  movups  xmmword ptr [rsp+2A0h+tm.tmHeight], xmm0
0x14005316d  movups  xmmword ptr [rsp+2A0h+tm.tmExternalLeading], xmm0
0x140053172  movups  xmmword ptr [rsp+2A0h+tm.tmOverhang], xmm0
0x140053177  movups  xmmword ptr [rsp+2A0h+tm.tmFirstChar], xmm0
0x14005317c  mov     rdx, rdi
0x14005317f  lea     rcx, [rsp+2A0h+var_278]
0x140053184  call    cs:__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x14005318a  nop
0x14005318b  mov     rdx, rbx
0x14005318e  lea     rcx, [rsp+2A0h+var_278]
0x140053193  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x140053199  mov     rbx, rax
0x14005319c  lea     rdx, [rsp+2A0h+tm]; lptm
0x1400531a1  mov     rcx, [rsp+2A0h+hdc]; hdc
0x1400531a6  call    cs:__imp_GetTextMetricsW
0x1400531ac  mov     rdx, rbx
0x1400531af  lea     rcx, [rsp+2A0h+var_278]
0x1400531b4  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x1400531ba  mov     rax, [rdi]
0x1400531bd  mov     rbx, [rax+188h]
0x1400531c4  mov     ecx, 31h ; '1'; nIndex
0x1400531c9  call    cs:__imp_GetSystemMetrics
0x1400531cf  mov     ecx, [rsp+2A0h+tm.tmHeight]
0x1400531d3  cmp     ecx, eax
0x1400531d5  jg      short loc_1400531E4
0x1400531d7  mov     ecx, 31h ; '1'; nIndex
0x1400531dc  call    cs:__imp_GetSystemMetrics
0x1400531e2  mov     ecx, eax
0x1400531e4  mov     dword ptr [rsp+2A0h+var_280], 0
0x1400531ec  mov     dword ptr [rsp+2A0h+var_280+4], ecx
0x1400531f0  mov     rdx, [rsp+2A0h+var_280]
0x1400531f5  mov     rcx, rdi
0x1400531f8  mov     rax, rbx
0x1400531fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053200  nop
0x140053201  lea     rcx, [rsp+2A0h+var_278]
0x140053206  call    cs:__imp_??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x14005320c  mov     rcx, [rbp+1A0h+var_10]
0x140053213  xor     rcx, rsp; StackCookie
0x140053216  call    __security_check_cookie
0x14005321b  lea     r11, [rsp+2A0h+var_s0]
0x140053223  mov     rbx, [r11+18h]
0x140053227  mov     rdi, [r11+20h]
0x14005322b  mov     rsp, r11
0x14005322e  pop     rbp
0x14005322f  retn
```

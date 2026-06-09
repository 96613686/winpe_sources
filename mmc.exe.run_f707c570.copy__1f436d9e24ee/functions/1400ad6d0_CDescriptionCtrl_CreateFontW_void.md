# CDescriptionCtrl::CreateFontW(void)

- ea: `0x1400ad6d0`
- end: `0x1400ad858`
- name: `?CreateFontW@CDescriptionCtrl@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(CDescriptionCtrl *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140036610`
- `0x1400ae350`

## callees

- `0x14005a420`
- `0x140062455`
- `0x1400a1e24`
- `0x1400ad6d0`
- `0x1400e9e10`

## import_xrefs

- `USER32!AdjustWindowRectEx` at `0x1400ad80e`
- `USER32!AdjustWindowRectEx` at `0x1400ad80e`
- `USER32!SystemParametersInfoW` at `0x1400ad71d`
- `USER32!SystemParametersInfoW` at `0x1400ad73e`
- `USER32!SystemParametersInfoW` at `0x1400ad71d`
- `USER32!SystemParametersInfoW` at `0x1400ad73e`
- `USER32!GetSystemMetrics` at `0x1400ad7d3`
- `USER32!GetSystemMetrics` at `0x1400ad7d3`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x1400ad76d`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x1400ad76d`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x1400ad83a`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x1400ad83a`
- `MFC42u!__imp_?GetExStyle@CWnd@@QEBAKXZ` at `0x1400ad7f1`
- `MFC42u!__imp_?GetExStyle@CWnd@@QEBAKXZ` at `0x1400ad7f1`
- `MFC42u!__imp_?GetStyle@CWnd@@QEBAKXZ` at `0x1400ad7fc`
- `MFC42u!__imp_?GetStyle@CWnd@@QEBAKXZ` at `0x1400ad7fc`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x1400ad77b`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x1400ad82f`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x1400ad77b`
- `MFC42u!__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z` at `0x1400ad82f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDescriptionCtrl::CreateFontW(CDescriptionCtrl *this)
{
  struct CFont *v2; // rsi
  int SystemMetrics; // eax
  DWORD v4; // ebx
  DWORD Style; // eax
  _WORD v6[2]; // [rsp+20h] [rbp-89h] BYREF
  _BYTE v7[12]; // [rsp+24h] [rbp-85h] BYREF
  _BYTE v8[40]; // [rsp+30h] [rbp-79h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-51h] BYREF
  struct tagLOGFONTW pvParam; // [rsp+70h] [rbp-39h] BYREF

  *((_DWORD *)this + 52) = 24;
  memset_0(&pvParam, 0, sizeof(pvParam));
  SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0);
  CFont::CreateFontIndirectW((CDescriptionCtrl *)((char *)this + 184), &pvParam);
  SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0);
  pvParam.lfWeight = 700;
  CFont::CreateFontIndirectW((CDescriptionCtrl *)((char *)this + 168), &pvParam);
  v6[0] = 48;
  CWindowDC::CWindowDC((CWindowDC *)v8, this);
  v2 = CDC::SelectObject((CDC *)v8, (CDescriptionCtrl *)((char *)this + 168));
  *((_DWORD *)this + 51) = *(_DWORD *)(((__int64 (__fastcall *)(_BYTE *, _BYTE *, _WORD *, __int64))CDC::GetTextExtent)(
                                         v8,
                                         v7,
                                         v6,
                                         1)
                                     + 4);
  v6[0] = 32;
  *((_DWORD *)this + 50) = 2
                         * *(_DWORD *)((__int64 (__fastcall *)(_BYTE *, _BYTE *, _WORD *, __int64))CDC::GetTextExtent)(
                                        v8,
                                        v7,
                                        v6,
                                        1);
  SystemMetrics = GetSystemMetrics(46);
  *(_QWORD *)&Rect.left = 0;
  Rect.right = 0;
  Rect.bottom = *((_DWORD *)this + 51) + 2 * SystemMetrics;
  v4 = CWnd::GetExStyle(this);
  Style = CWnd::GetStyle(this);
  AdjustWindowRectEx(&Rect, Style, 0, v4);
  if ( Rect.bottom - Rect.top > *((_DWORD *)this + 52) )
    *((_DWORD *)this + 52) = Rect.bottom - Rect.top;
  CDC::SelectObject((CDC *)v8, v2);
  CWindowDC::~CWindowDC((CWindowDC *)v8);
}

```

## disassembly

```asm
0x1400ad6d0  push    rbp
0x1400ad6d2  push    rbx
0x1400ad6d3  push    rsi
0x1400ad6d4  push    rdi
0x1400ad6d5  lea     rbp, [rsp-3Fh]
0x1400ad6da  sub     rsp, 0E8h
0x1400ad6e1  mov     rax, cs:__security_cookie
0x1400ad6e8  xor     rax, rsp
0x1400ad6eb  mov     [rbp+57h+var_30], rax
0x1400ad6ef  mov     rdi, rcx
0x1400ad6f2  mov     dword ptr [rcx+0D0h], 18h
0x1400ad6fc  mov     esi, 5Ch ; '\'
0x1400ad701  mov     r8d, esi; Size
0x1400ad704  xor     edx, edx; Val
0x1400ad706  lea     rcx, [rbp+57h+pvParam]; void *
0x1400ad70a  call    memset_0
0x1400ad70f  xor     r9d, r9d; fWinIni
0x1400ad712  lea     r8, [rbp+57h+pvParam]; pvParam
0x1400ad716  mov     edx, esi; uiParam
0x1400ad718  lea     ebx, [rsi-3Dh]
0x1400ad71b  mov     ecx, ebx; uiAction
0x1400ad71d  call    cs:__imp_SystemParametersInfoW
0x1400ad723  lea     rcx, [rdi+0B8h]; this
0x1400ad72a  lea     rdx, [rbp+57h+pvParam]; struct tagLOGFONTW *
0x1400ad72e  call    ?CreateFontIndirectW@CFont@@QEAAHPEBUtagLOGFONTW@@@Z; CFont::CreateFontIndirectW(tagLOGFONTW const *)
0x1400ad733  xor     r9d, r9d; fWinIni
0x1400ad736  lea     r8, [rbp+57h+pvParam]; pvParam
0x1400ad73a  mov     edx, esi; uiParam
0x1400ad73c  mov     ecx, ebx; uiAction
0x1400ad73e  call    cs:__imp_SystemParametersInfoW
0x1400ad744  mov     [rbp+57h+var_80], 2BCh
0x1400ad74b  lea     rbx, [rdi+0A8h]
0x1400ad752  lea     rdx, [rbp+57h+pvParam]; struct tagLOGFONTW *
0x1400ad756  mov     rcx, rbx; this
0x1400ad759  call    ?CreateFontIndirectW@CFont@@QEAAHPEBUtagLOGFONTW@@@Z; CFont::CreateFontIndirectW(tagLOGFONTW const *)
0x1400ad75e  lea     eax, [rsi-2Ch]
0x1400ad761  mov     [rsp+100h+var_E0], ax
0x1400ad766  mov     rdx, rdi
0x1400ad769  lea     rcx, [rbp+57h+var_D0]
0x1400ad76d  call    cs:__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x1400ad773  nop
0x1400ad774  mov     rdx, rbx
0x1400ad777  lea     rcx, [rbp+57h+var_D0]
0x1400ad77b  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x1400ad781  mov     rsi, rax
0x1400ad784  mov     ebx, 1
0x1400ad789  mov     r9d, ebx
0x1400ad78c  lea     r8, [rsp+100h+var_E0]
0x1400ad791  lea     rdx, [rsp+100h+var_DC]
0x1400ad796  lea     rcx, [rbp+57h+var_D0]
0x1400ad79a  call    ?GetTextExtent@CDC@@QEBA?AVCSize@@PEBGH@Z; CDC::GetTextExtent(ushort const *,int)
0x1400ad79f  mov     ecx, [rax+4]
0x1400ad7a2  mov     [rdi+0CCh], ecx
0x1400ad7a8  lea     eax, [rbx+1Fh]
0x1400ad7ab  mov     [rsp+100h+var_E0], ax
0x1400ad7b0  mov     r9d, ebx
0x1400ad7b3  lea     r8, [rsp+100h+var_E0]
0x1400ad7b8  lea     rdx, [rsp+100h+var_DC]
0x1400ad7bd  lea     rcx, [rbp+57h+var_D0]
0x1400ad7c1  call    ?GetTextExtent@CDC@@QEBA?AVCSize@@PEBGH@Z; CDC::GetTextExtent(ushort const *,int)
0x1400ad7c6  mov     ecx, [rax]
0x1400ad7c8  add     ecx, ecx
0x1400ad7ca  mov     [rdi+0C8h], ecx
0x1400ad7d0  lea     ecx, [rbx+2Dh]; nIndex
0x1400ad7d3  call    cs:__imp_GetSystemMetrics
0x1400ad7d9  lea     ecx, [rax+rax]
0x1400ad7dc  xor     eax, eax
0x1400ad7de  mov     qword ptr [rbp+57h+Rect.left], rax
0x1400ad7e2  mov     [rbp+57h+Rect.right], eax
0x1400ad7e5  add     ecx, [rdi+0CCh]
0x1400ad7eb  mov     [rbp+57h+Rect.bottom], ecx
0x1400ad7ee  mov     rcx, rdi
0x1400ad7f1  call    cs:__imp_?GetExStyle@CWnd@@QEBAKXZ; CWnd::GetExStyle(void)
0x1400ad7f7  mov     ebx, eax
0x1400ad7f9  mov     rcx, rdi
0x1400ad7fc  call    cs:__imp_?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1400ad802  mov     r9d, ebx; dwExStyle
0x1400ad805  xor     r8d, r8d; bMenu
0x1400ad808  mov     edx, eax; dwStyle
0x1400ad80a  lea     rcx, [rbp+57h+Rect]; lpRect
0x1400ad80e  call    cs:__imp_AdjustWindowRectEx
0x1400ad814  mov     eax, [rbp+57h+Rect.bottom]
0x1400ad817  sub     eax, [rbp+57h+Rect.top]
0x1400ad81a  cmp     eax, [rdi+0D0h]
0x1400ad820  jle     short loc_1400AD828
0x1400ad822  mov     [rdi+0D0h], eax
0x1400ad828  mov     rdx, rsi
0x1400ad82b  lea     rcx, [rbp+57h+var_D0]
0x1400ad82f  call    cs:__imp_?SelectObject@CDC@@UEAAPEAVCFont@@PEAV2@@Z; CDC::SelectObject(CFont *)
0x1400ad835  nop
0x1400ad836  lea     rcx, [rbp+57h+var_D0]
0x1400ad83a  call    cs:__imp_??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x1400ad840  mov     rcx, [rbp+57h+var_30]
0x1400ad844  xor     rcx, rsp; StackCookie
0x1400ad847  call    __security_check_cookie
0x1400ad84c  add     rsp, 0E8h
0x1400ad853  pop     rdi
0x1400ad854  pop     rsi
0x1400ad855  pop     rbx
0x1400ad856  pop     rbp
0x1400ad857  retn
```

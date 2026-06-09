# CAMCHeaderCtrl::OnCustomDraw(tagNMHDR *,__int64 *)

- ea: `0x1400a3080`
- end: `0x1400a345b`
- name: `?OnCustomDraw@CAMCHeaderCtrl@@IEAA_JPEAUtagNMHDR@@PEA_J@Z`
- size: `987`
- prototype: `__int64 __fastcall(CAMCHeaderCtrl *__hidden this, struct tagNMHDR *, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1400575d8`
- `0x140062455`
- `0x1400a0e54`
- `0x1400a3080`
- `0x1400aa518`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `USER32!DrawEdge` at `0x1400a31e2`
- `USER32!DrawEdge` at `0x1400a31e2`
- `USER32!GetSysColor` at `0x1400a3179`
- `USER32!GetSysColor` at `0x1400a319b`
- `USER32!GetSysColor` at `0x1400a31bd`
- `USER32!GetSysColor` at `0x1400a32fc`
- `USER32!GetSysColor` at `0x1400a331e`
- `USER32!GetSysColor` at `0x1400a3179`
- `USER32!GetSysColor` at `0x1400a319b`
- `USER32!GetSysColor` at `0x1400a31bd`
- `USER32!GetSysColor` at `0x1400a32fc`
- `USER32!GetSysColor` at `0x1400a331e`
- `USER32!SendMessageW` at `0x1400a3120`
- `USER32!SendMessageW` at `0x1400a3148`
- `USER32!SendMessageW` at `0x1400a3245`
- `USER32!SendMessageW` at `0x1400a329f`
- `USER32!SendMessageW` at `0x1400a32c7`
- `USER32!SendMessageW` at `0x1400a338e`
- `USER32!SendMessageW` at `0x1400a3120`
- `USER32!SendMessageW` at `0x1400a3148`
- `USER32!SendMessageW` at `0x1400a3245`
- `USER32!SendMessageW` at `0x1400a329f`
- `USER32!SendMessageW` at `0x1400a32c7`
- `USER32!SendMessageW` at `0x1400a338e`
- `USER32!SystemParametersInfoW` at `0x1400a30ec`
- `USER32!SystemParametersInfoW` at `0x1400a30ec`
- `MFC42u!__imp_??0CString@@QEAA@PEBG@Z` at `0x1400a327b`
- `MFC42u!__imp_??0CString@@QEAA@PEBG@Z` at `0x1400a33c0`
- `MFC42u!__imp_??0CString@@QEAA@PEBG@Z` at `0x1400a327b`
- `MFC42u!__imp_??0CString@@QEAA@PEBG@Z` at `0x1400a33c0`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400a33e4`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400a33e4`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x1400a3189`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x1400a31ab`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x1400a330c`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x1400a3189`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x1400a31ab`
- `MFC42u!__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z` at `0x1400a330c`
- `MFC42u!__imp_?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z` at `0x1400a315a`
- `MFC42u!__imp_?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z` at `0x1400a32d9`
- `MFC42u!__imp_?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z` at `0x1400a315a`
- `MFC42u!__imp_?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z` at `0x1400a32d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAMCHeaderCtrl::OnCustomDraw(CAMCHeaderCtrl *this, struct tagNMHDR *a2, __int64 *a3)
{
  WPARAM idFrom_low; // rbx
  HWND v7; // rcx
  WPARAM v8; // r15
  HDC *v9; // rdi
  DWORD SysColor; // eax
  int v11; // ecx
  DWORD v12; // eax
  void (__fastcall *v13)(HDC *, _QWORD); // rbx
  DWORD v14; // eax
  WPARAM v15; // r15
  DWORD v16; // eax
  void (__fastcall *v17)(HDC *, _QWORD); // rbx
  DWORD v18; // eax
  CAMCHeaderCtrl *v19; // rcx
  _BYTE v21[8]; // [rsp+20h] [rbp-E0h] BYREF
  int pvParam; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+2Ch] [rbp-D4h]
  int v24; // [rsp+34h] [rbp-CCh]
  struct _HD_ITEMW v25; // [rsp+40h] [rbp-C0h] BYREF
  struct tagRECT v26; // [rsp+90h] [rbp-70h] BYREF
  LPARAM lParam[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v28[256]; // [rsp+B0h] [rbp-50h] BYREF

  if ( LODWORD(a2[1].hwndFrom) == 1 )
  {
    *a3 = 32;
    return 1;
  }
  if ( LODWORD(a2[1].hwndFrom) != 65537 )
    goto LABEL_23;
  pvParam = 16;
  v23 = 0;
  v24 = 0;
  if ( !SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) )
    goto LABEL_23;
  idFrom_low = SLODWORD(a2[2].idFrom);
  if ( (idFrom_low & 0x80000000) != 0LL )
    goto LABEL_23;
  v7 = (HWND)*((_QWORD *)this + 8);
  if ( (v23 & 1) != 0 )
  {
    if ( (int)idFrom_low < (int)SendMessageW(v7, 0x1200u, 0, 0) )
    {
      *(_OWORD *)lParam = 0;
      v8 = idFrom_low;
      if ( (unsigned int)SendMessageW(*((HWND *)this + 8), 0x1207u, idFrom_low, (LPARAM)lParam) )
      {
        v9 = (HDC *)CDC::FromHandle((HDC)a2[1].idFrom);
        if ( v9 )
        {
          if ( (_DWORD)idFrom_low == *((_DWORD *)this + 32) )
          {
            SysColor = GetSysColor(13);
            CDC::FillSolidRect((CDC *)v9, (const struct tagRECT *)lParam, SysColor);
            v11 = 14;
          }
          else
          {
            v12 = GetSysColor(15);
            CDC::FillSolidRect((CDC *)v9, (const struct tagRECT *)lParam, v12);
            v11 = 8;
          }
          v13 = (void (__fastcall *)(HDC *, _QWORD))*((_QWORD *)*v9 + 14);
          v14 = GetSysColor(v11);
          v13(v9, v14);
          DrawEdge(v9[1], (LPRECT)lParam, 6u, 0xFu);
          memset_0(v28, 0, sizeof(v28));
          memset_0(&v25, 0, sizeof(v25));
          v25.mask = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::GetImpl'::`2'::impl) != 0
                   ? 6
                   : 2;
          v25.pszText = v28;
          v25.cchTextMax = 256;
          if ( !(unsigned int)SendMessageW(*((HWND *)this + 8), 0x120Bu, v8, (LPARAM)&v25) )
            goto LABEL_22;
          goto LABEL_19;
        }
      }
    }
LABEL_23:
    *a3 = 0;
    return 0;
  }
  if ( (int)idFrom_low >= (int)SendMessageW(v7, 0x1200u, 0, 0) )
    goto LABEL_23;
  *(_OWORD *)lParam = 0;
  v15 = idFrom_low;
  if ( !(unsigned int)SendMessageW(*((HWND *)this + 8), 0x1207u, idFrom_low, (LPARAM)lParam) )
    goto LABEL_23;
  v9 = (HDC *)CDC::FromHandle((HDC)a2[1].idFrom);
  if ( !v9 || (_DWORD)idFrom_low != *((_DWORD *)this + 32) )
    goto LABEL_23;
  v16 = GetSysColor(13);
  CDC::FillSolidRect((CDC *)v9, (const struct tagRECT *)lParam, v16);
  v17 = (void (__fastcall *)(HDC *, _QWORD))*((_QWORD *)*v9 + 14);
  v18 = GetSysColor(14);
  v17(v9, v18);
  memset_0(v28, 0, sizeof(v28));
  memset_0(&v25, 0, sizeof(v25));
  v25.mask = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::GetImpl'::`2'::impl) != 0
           ? 6
           : 2;
  v25.pszText = v28;
  v25.cchTextMax = 256;
  if ( (unsigned int)SendMessageW(*((HWND *)this + 8), 0x120Bu, v15, (LPARAM)&v25) )
  {
LABEL_19:
    v26.left = _mm_cvtsi128_si32(*(__m128i *)lParam) + 4;
    v26.right = LODWORD(lParam[1]) - 4;
    v26.bottom = HIDWORD(lParam[1]) - 2;
    v26.top = HIDWORD(lParam[0]) + 2;
    CString::CString((CString *)v21, v28);
    CDC::DrawTextW((CDC *)v9, (const struct CString *)v21, &v26, 0x8024u);
    CString::~CString(v21);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::GetImpl'::`2'::impl) )
    {
      if ( (v25.fmt & 0x600) != 0 )
        CAMCHeaderCtrl::DrawSortArrow(v19, v9, (const struct tagRECT *)lParam, &v25);
    }
  }
LABEL_22:
  *a3 = 4;
  return 1;
}

```

## disassembly

```asm
0x1400a3080  mov     [rsp-8+arg_18], rbx
0x1400a3085  push    rbp
0x1400a3086  push    rsi
0x1400a3087  push    rdi
0x1400a3088  push    r14
0x1400a308a  push    r15
0x1400a308c  lea     rbp, [rsp-1C0h]
0x1400a3094  sub     rsp, 2C0h
0x1400a309b  mov     rax, cs:__security_cookie
0x1400a30a2  xor     rax, rsp
0x1400a30a5  mov     [rbp+1E0h+var_30], rax
0x1400a30ac  mov     r14, r8
0x1400a30af  mov     rdi, rdx
0x1400a30b2  mov     rsi, rcx
0x1400a30b5  mov     ecx, [rdx+18h]
0x1400a30b8  sub     ecx, 1
0x1400a30bb  jz      loc_1400A3429
0x1400a30c1  cmp     ecx, 10000h
0x1400a30c7  jnz     loc_1400A341E
0x1400a30cd  mov     edx, 10h; uiParam
0x1400a30d2  mov     [rsp+2E0h+pvParam], edx
0x1400a30d6  xor     eax, eax
0x1400a30d8  mov     [rsp+2E0h+var_2B4], rax
0x1400a30dd  mov     [rsp+2E0h+var_2AC], eax
0x1400a30e1  xor     r9d, r9d; fWinIni
0x1400a30e4  lea     r8, [rsp+2E0h+pvParam]; pvParam
0x1400a30e9  lea     ecx, [rdx+32h]; uiAction
0x1400a30ec  call    cs:__imp_SystemParametersInfoW
0x1400a30f2  test    eax, eax
0x1400a30f4  jz      loc_1400A341E
0x1400a30fa  movsxd  rbx, dword ptr [rdi+38h]
0x1400a30fe  test    ebx, ebx
0x1400a3100  js      loc_1400A341E
0x1400a3106  xor     r9d, r9d; lParam
0x1400a3109  xor     r8d, r8d; wParam
0x1400a310c  mov     edx, 1200h; Msg
0x1400a3111  mov     rcx, [rsi+40h]; hWnd
0x1400a3115  test    byte ptr [rsp+2E0h+var_2B4], 1
0x1400a311a  jz      loc_1400A329F
0x1400a3120  call    cs:__imp_SendMessageW
0x1400a3126  cmp     ebx, eax
0x1400a3128  jge     loc_1400A341E
0x1400a312e  xorps   xmm0, xmm0
0x1400a3131  movups  xmmword ptr [rbp+1E0h+lParam], xmm0
0x1400a3135  mov     r15, rbx
0x1400a3138  lea     r9, [rbp+1E0h+lParam]; lParam
0x1400a313c  mov     r8, rbx; wParam
0x1400a313f  mov     edx, 1207h; Msg
0x1400a3144  mov     rcx, [rsi+40h]; hWnd
0x1400a3148  call    cs:__imp_SendMessageW
0x1400a314e  test    eax, eax
0x1400a3150  jz      loc_1400A341E
0x1400a3156  mov     rcx, [rdi+20h]
0x1400a315a  call    cs:__imp_?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x1400a3160  mov     rdi, rax
0x1400a3163  test    rax, rax
0x1400a3166  jz      loc_1400A341E
0x1400a316c  cmp     ebx, [rsi+80h]
0x1400a3172  jnz     short loc_1400A3196
0x1400a3174  mov     ecx, 0Dh; nIndex
0x1400a3179  call    cs:__imp_GetSysColor
0x1400a317f  mov     r8d, eax
0x1400a3182  lea     rdx, [rbp+1E0h+lParam]
0x1400a3186  mov     rcx, rdi
0x1400a3189  call    cs:__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z; CDC::FillSolidRect(tagRECT const *,ulong)
0x1400a318f  mov     ecx, 0Eh
0x1400a3194  jmp     short loc_1400A31B6
0x1400a3196  mov     ecx, 0Fh; nIndex
0x1400a319b  call    cs:__imp_GetSysColor
0x1400a31a1  mov     r8d, eax
0x1400a31a4  lea     rdx, [rbp+1E0h+lParam]
0x1400a31a8  mov     rcx, rdi
0x1400a31ab  call    cs:__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z; CDC::FillSolidRect(tagRECT const *,ulong)
0x1400a31b1  mov     ecx, 8; nIndex
0x1400a31b6  mov     rax, [rdi]
0x1400a31b9  mov     rbx, [rax+70h]
0x1400a31bd  call    cs:__imp_GetSysColor
0x1400a31c3  mov     edx, eax
0x1400a31c5  mov     rcx, rdi
0x1400a31c8  mov     rax, rbx
0x1400a31cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a31d0  mov     r9d, 0Fh; grfFlags
0x1400a31d6  lea     r8d, [r9-9]; edge
0x1400a31da  lea     rdx, [rbp+1E0h+lParam]; qrc
0x1400a31de  mov     rcx, [rdi+8]; hdc
0x1400a31e2  call    cs:__imp_DrawEdge
0x1400a31e8  xor     edx, edx; Val
0x1400a31ea  mov     r8d, 200h; Size
0x1400a31f0  lea     rcx, [rbp+1E0h+var_230]; void *
0x1400a31f4  call    memset_0
0x1400a31f9  xor     edx, edx; Val
0x1400a31fb  lea     r8d, [rdx+48h]; Size
0x1400a31ff  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x1400a3204  call    memset_0
0x1400a3209  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon> `wil::Feature<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::GetImpl(void)'::`2'::impl
0x1400a3210  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::__private_IsEnabled(void)
0x1400a3215  neg     al
0x1400a3217  sbb     ecx, ecx
0x1400a3219  and     ecx, 4
0x1400a321c  add     ecx, 2
0x1400a321f  mov     dword ptr [rsp+2E0h+var_2A0], ecx
0x1400a3223  lea     rax, [rbp+1E0h+var_230]
0x1400a3227  mov     [rsp+2E0h+var_298], rax
0x1400a322c  mov     [rsp+2E0h+var_288], 100h
0x1400a3234  lea     r9, [rsp+2E0h+var_2A0]; lParam
0x1400a3239  mov     r8, r15; wParam
0x1400a323c  mov     edx, 120Bh; Msg
0x1400a3241  mov     rcx, [rsi+40h]; hWnd
0x1400a3245  call    cs:__imp_SendMessageW
0x1400a324b  test    eax, eax
0x1400a324d  jz      loc_1400A3415
0x1400a3253  movaps  xmm0, xmmword ptr [rbp+1E0h+lParam]
0x1400a3257  movdqa  xmmword ptr [rbp+1E0h+var_250.left], xmm0
0x1400a325c  movd    eax, xmm0
0x1400a3260  add     eax, 4
0x1400a3263  mov     [rbp+1E0h+var_250.left], eax
0x1400a3266  sub     [rbp+1E0h+var_250.right], 4
0x1400a326a  sub     [rbp+1E0h+var_250.bottom], 2
0x1400a326e  add     [rbp+1E0h+var_250.top], 2
0x1400a3272  lea     rdx, [rbp+1E0h+var_230]
0x1400a3276  lea     rcx, [rsp+2E0h+var_2C0]
0x1400a327b  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x1400a3281  nop
0x1400a3282  mov     r9d, 8024h; unsigned int
0x1400a3288  lea     r8, [rbp+1E0h+var_250]; struct tagRECT *
0x1400a328c  lea     rdx, [rsp+2E0h+var_2C0]; struct CString *
0x1400a3291  mov     rcx, rdi; this
0x1400a3294  call    ?DrawTextW@CDC@@QEAAHAEBVCString@@PEAUtagRECT@@I@Z; CDC::DrawTextW(CString const &,tagRECT *,uint)
0x1400a3299  nop
0x1400a329a  jmp     loc_1400A33DF
0x1400a329f  call    cs:__imp_SendMessageW
0x1400a32a5  cmp     ebx, eax
0x1400a32a7  jge     loc_1400A341E
0x1400a32ad  xorps   xmm0, xmm0
0x1400a32b0  movups  xmmword ptr [rbp+1E0h+lParam], xmm0
0x1400a32b4  mov     r15, rbx
0x1400a32b7  lea     r9, [rbp+1E0h+lParam]; lParam
0x1400a32bb  mov     r8, rbx; wParam
0x1400a32be  mov     edx, 1207h; Msg
0x1400a32c3  mov     rcx, [rsi+40h]; hWnd
0x1400a32c7  call    cs:__imp_SendMessageW
0x1400a32cd  test    eax, eax
0x1400a32cf  jz      loc_1400A341E
0x1400a32d5  mov     rcx, [rdi+20h]
0x1400a32d9  call    cs:__imp_?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x1400a32df  mov     rdi, rax
0x1400a32e2  test    rax, rax
0x1400a32e5  jz      loc_1400A341E
0x1400a32eb  cmp     ebx, [rsi+80h]
0x1400a32f1  jnz     loc_1400A341E
0x1400a32f7  mov     ecx, 0Dh; nIndex
0x1400a32fc  call    cs:__imp_GetSysColor
0x1400a3302  mov     r8d, eax
0x1400a3305  lea     rdx, [rbp+1E0h+lParam]
0x1400a3309  mov     rcx, rdi
0x1400a330c  call    cs:__imp_?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z; CDC::FillSolidRect(tagRECT const *,ulong)
0x1400a3312  mov     rax, [rdi]
0x1400a3315  mov     rbx, [rax+70h]
0x1400a3319  mov     ecx, 0Eh; nIndex
0x1400a331e  call    cs:__imp_GetSysColor
0x1400a3324  mov     edx, eax
0x1400a3326  mov     rcx, rdi
0x1400a3329  mov     rax, rbx
0x1400a332c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a3331  xor     edx, edx; Val
0x1400a3333  mov     r8d, 200h; Size
0x1400a3339  lea     rcx, [rbp+1E0h+var_230]; void *
0x1400a333d  call    memset_0
0x1400a3342  xor     edx, edx; Val
0x1400a3344  lea     r8d, [rdx+48h]; Size
0x1400a3348  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x1400a334d  call    memset_0
0x1400a3352  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon> `wil::Feature<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::GetImpl(void)'::`2'::impl
0x1400a3359  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::__private_IsEnabled(void)
0x1400a335e  neg     al
0x1400a3360  sbb     ecx, ecx
0x1400a3362  and     ecx, 4
0x1400a3365  add     ecx, 2
0x1400a3368  mov     dword ptr [rsp+2E0h+var_2A0], ecx
0x1400a336c  lea     rax, [rbp+1E0h+var_230]
0x1400a3370  mov     [rsp+2E0h+var_298], rax
0x1400a3375  mov     [rsp+2E0h+var_288], 100h
0x1400a337d  lea     r9, [rsp+2E0h+var_2A0]; lParam
0x1400a3382  mov     r8, r15; wParam
0x1400a3385  mov     edx, 120Bh; Msg
0x1400a338a  mov     rcx, [rsi+40h]; hWnd
0x1400a338e  call    cs:__imp_SendMessageW
0x1400a3394  test    eax, eax
0x1400a3396  jz      short loc_1400A3415
0x1400a3398  movaps  xmm0, xmmword ptr [rbp+1E0h+lParam]
0x1400a339c  movdqa  xmmword ptr [rbp+1E0h+var_250.left], xmm0
0x1400a33a1  movd    eax, xmm0
0x1400a33a5  add     eax, 4
0x1400a33a8  mov     [rbp+1E0h+var_250.left], eax
0x1400a33ab  sub     [rbp+1E0h+var_250.right], 4
0x1400a33af  sub     [rbp+1E0h+var_250.bottom], 2
0x1400a33b3  add     [rbp+1E0h+var_250.top], 2
0x1400a33b7  lea     rdx, [rbp+1E0h+var_230]
0x1400a33bb  lea     rcx, [rsp+2E0h+var_2C0]
0x1400a33c0  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x1400a33c6  nop
0x1400a33c7  mov     r9d, 8024h; unsigned int
0x1400a33cd  lea     r8, [rbp+1E0h+var_250]; struct tagRECT *
0x1400a33d1  lea     rdx, [rsp+2E0h+var_2C0]; struct CString *
0x1400a33d6  mov     rcx, rdi; this
0x1400a33d9  call    ?DrawTextW@CDC@@QEAAHAEBVCString@@PEAUtagRECT@@I@Z; CDC::DrawTextW(CString const &,tagRECT *,uint)
0x1400a33de  nop
0x1400a33df  lea     rcx, [rsp+2E0h+var_2C0]
0x1400a33e4  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1400a33ea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon> `wil::Feature<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::GetImpl(void)'::`2'::impl
0x1400a33f1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KeyboardFocusSortIcon>::__private_IsEnabled(void)
0x1400a33f6  test    al, al
0x1400a33f8  jz      short loc_1400A3415
0x1400a33fa  test    [rsp+2E0h+var_284], 600h
0x1400a3402  jz      short loc_1400A3415
0x1400a3404  lea     r9, [rsp+2E0h+var_2A0]; struct _HD_ITEMW *
0x1400a3409  lea     r8, [rbp+1E0h+lParam]; struct tagRECT *
0x1400a340d  mov     rdx, rdi; struct CDC *
0x1400a3410  call    ?DrawSortArrow@CAMCHeaderCtrl@@AEAAXPEAVCDC@@AEBUtagRECT@@AEBU_HD_ITEMW@@@Z; CAMCHeaderCtrl::DrawSortArrow(CDC *,tagRECT const &,_HD_ITEMW const &)
0x1400a3415  mov     qword ptr [r14], 4
0x1400a341c  jmp     short loc_1400A3430
0x1400a341e  mov     qword ptr [r14], 0
0x1400a3425  xor     eax, eax
0x1400a3427  jmp     short loc_1400A3435
0x1400a3429  mov     qword ptr [r8], 20h ; ' '
0x1400a3430  mov     eax, 1
0x1400a3435  mov     rcx, [rbp+1E0h+var_30]
0x1400a343c  xor     rcx, rsp; StackCookie
0x1400a343f  call    __security_check_cookie
0x1400a3444  mov     rbx, [rsp+2E0h+arg_18]
0x1400a344c  add     rsp, 2C0h
0x1400a3453  pop     r15
0x1400a3455  pop     r14
0x1400a3457  pop     rdi
0x1400a3458  pop     rsi
0x1400a3459  pop     rbp
0x1400a345a  retn
```

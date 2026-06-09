# CMfObject::Draw(void *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,int (*)(unsigned __int64),unsigned __int64)

- ea: `0x18009f4c0`
- end: `0x18009f880`
- name: `?Draw@CMfObject@@UEAAJPEAXPEAUHDC__@@1PEBU_RECTL@@2P6AH_K@Z3@Z`
- size: `960`
- prototype: `HRESULT __fastcall(CMfObject *this, void *__formal, HDC__ *__formal, HDC__ *hdcDraw, const _RECTL *lprcBounds, const _RECTL *lprcWBounds, int (__fastcall *pfnContinue)(unsigned __int64), unsigned __int64 dwContinue)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180046460`
- `0x18009f4c0`
- `0x18009fd34`
- `0x1800a0248`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f7c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f7e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f7c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f7e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f6cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f6cc`
- `GDI32!DeleteObject` at `0x18009f83a`
- `GDI32!DeleteObject` at `0x18009f83a`
- `GDI32!DeleteEnhMetaFile` at `0x18009f632`
- `GDI32!DeleteEnhMetaFile` at `0x18009f632`
- `GDI32!SetMapMode` at `0x18009f65e`
- `GDI32!SetMapMode` at `0x18009f65e`
- `GDI32!SaveDC` at `0x18009f526`
- `GDI32!SaveDC` at `0x18009f526`
- `GDI32!IntersectClipRect` at `0x18009f572`
- `GDI32!IntersectClipRect` at `0x18009f572`
- `GDI32!GetGraphicsMode` at `0x18009f59a`
- `GDI32!GetGraphicsMode` at `0x18009f59a`
- `GDI32!CreateEnhMetaFileW` at `0x18009f5dc`
- `GDI32!CreateEnhMetaFileW` at `0x18009f5dc`
- `GDI32!PlayMetaFile` at `0x18009f5f2`
- `GDI32!PlayMetaFile` at `0x18009f5f2`
- `GDI32!CloseEnhMetaFile` at `0x18009f601`
- `GDI32!CloseEnhMetaFile` at `0x18009f601`
- `GDI32!PlayEnhMetaFile` at `0x18009f623`
- `GDI32!PlayEnhMetaFile` at `0x18009f623`
- `GDI32!LPtoDP` at `0x18009f64a`
- `GDI32!LPtoDP` at `0x18009f64a`
- `GDI32!SetViewportOrgEx` at `0x18009f677`
- `GDI32!SetViewportOrgEx` at `0x18009f677`
- `GDI32!SetViewportExtEx` at `0x18009f697`
- `GDI32!SetViewportExtEx` at `0x18009f697`
- `GDI32!EnumMetaFile` at `0x18009f79a`
- `GDI32!EnumMetaFile` at `0x18009f79a`
- `GDI32!GetStockObject` at `0x18009f807`
- `GDI32!GetStockObject` at `0x18009f807`
- `GDI32!SelectPalette` at `0x18009f82a`
- `GDI32!SelectPalette` at `0x18009f82a`
- `GDI32!RestoreDC` at `0x18009f850`
- `GDI32!RestoreDC` at `0x18009f850`
- `USER32!GetDC` at `0x18009f5b7`
- `USER32!GetDC` at `0x18009f5b7`

## pseudocode

```c
__int64 __fastcall CMfObject::Draw(
        CMfObject *this,
        void *__formal,
        HDC__ *a3,
        HDC hdcDraw,
        tagRECT *lprcBounds,
        const _RECTL *lprcWBounds,
        int (__fastcall *pfnContinue)(unsigned __int64),
        unsigned __int64 dwContinue)
{
  int v11; // r14d
  int IsDcMeta; // eax
  int v13; // eax
  HDC DC; // rax
  HDC v15; // rbx
  HENHMETAFILE v16; // rax
  HENHMETAFILE v17; // rbx
  _METAINFO *v18; // rax
  HMETAFILE__ *m_hPres; // rdx
  _METAINFO *m_pMetaInfo; // r8
  _METADC *pNext; // rcx
  HPALETTE StockObject; // rax
  tagRECT rect; // [rsp+30h] [rbp-30h] BYREF
  RECT rc; // [rsp+40h] [rbp-20h] BYREF

  this->m_error = 0;
  if ( !this->m_hPres && !CMfObject::LoadHPRES(this) )
    return 2147745799LL;
  rect = *lprcBounds;
  v11 = SaveDC(hdcDraw);
  if ( !v11 )
    return 2147942414LL;
  this->m_nRecord = 16;
  IsDcMeta = OleIsDcMeta(hdcDraw);
  this->m_fMetaDC = IsDcMeta;
  if ( IsDcMeta )
  {
    v11 = -1;
    if ( !lprcWBounds )
      return 2147746112LL;
    v18 = (_METAINFO *)HeapAlloc(g_hHeap, 0, 0x38u);
    this->m_pMetaInfo = v18;
    if ( !v18 )
    {
      this->m_error = -2147024882;
      goto $errRtn_135;
    }
    this->m_pCurMdc = &v18->headDc;
    v18->xwo = lprcWBounds->left;
    this->m_pMetaInfo->ywo = lprcWBounds->top;
    this->m_pMetaInfo->xwe = lprcWBounds->right;
    this->m_pMetaInfo->ywe = lprcWBounds->bottom;
    this->m_pMetaInfo->xro = rect.left - lprcWBounds->left;
    this->m_pMetaInfo->yro = rect.top - lprcWBounds->top;
    this->m_pCurMdc->xre = rect.right - rect.left;
    this->m_pCurMdc->yre = rect.bottom - rect.top;
    this->m_pCurMdc->xMwo = 0;
    this->m_pCurMdc->yMwo = 0;
    this->m_pCurMdc->xMwe = 0;
    this->m_pCurMdc->yMwe = 0;
    this->m_pCurMdc->pNext = 0;
    goto LABEL_19;
  }
  v13 = IntersectClipRect(hdcDraw, rect.left, rect.top, rect.right, rect.bottom);
  if ( v13 != 1 )
  {
    if ( !v13 )
    {
      this->m_error = -2147467259;
      goto $errRtn_135;
    }
    if ( GetGraphicsMode(hdcDraw) == 2 )
    {
      DC = GetDC(0);
      rc = (RECT)_mm_load_si128((const __m128i *)&_xmm);
      v15 = CreateEnhMetaFileW(DC, 0, &rc, 0);
      PlayMetaFile(v15, this->m_hPres);
      v16 = CloseEnhMetaFile(v15);
      v17 = v16;
      if ( v16 )
      {
        PlayEnhMetaFile(hdcDraw, v16, &rect);
        DeleteEnhMetaFile(v17);
      }
      goto $errRtn_135;
    }
    LPtoDP(hdcDraw, (LPPOINT)&rect, 2);
    SetMapMode(hdcDraw, 8);
    SetViewportOrgEx(hdcDraw, rect.left, rect.top, 0);
    SetViewportExtEx(hdcDraw, rect.right - rect.left, rect.bottom - rect.top, 0);
LABEL_19:
    m_hPres = this->m_hPres;
    this->m_pfnContinue = pfnContinue;
    this->m_dwContinue = dwContinue;
    this->m_hPalDCOriginal = 0;
    this->m_hPalLast = 0;
    EnumMetaFile(hdcDraw, m_hPres, MfCallbackFuncForDraw, (LPARAM)this);
    if ( this->m_fMetaDC )
    {
      while ( 1 )
      {
        m_pMetaInfo = this->m_pMetaInfo;
        pNext = m_pMetaInfo->headDc.pNext;
        if ( !pNext )
          break;
        m_pMetaInfo->headDc.pNext = pNext->pNext;
        HeapFree(g_hHeap, 0, pNext);
      }
      HeapFree(g_hHeap, 0, m_pMetaInfo);
      this->m_pCurMdc = 0;
      this->m_pMetaInfo = 0;
    }
    if ( this->m_hPalLast )
    {
      if ( this->m_fMetaDC )
        StockObject = (HPALETTE)GetStockObject(15);
      else
        StockObject = this->m_hPalDCOriginal;
      if ( StockObject )
        SelectPalette(hdcDraw, StockObject, 1);
      DeleteObject(this->m_hPalLast);
    }
    this->m_fMetaDC = 0;
  }
$errRtn_135:
  RestoreDC(hdcDraw, v11);
  return (unsigned int)this->m_error;
}

```

## disassembly

```asm
0x18009f4c0  mov     [rsp-28h+arg_8], rbx
0x18009f4c5  push    rbp
0x18009f4c6  push    rsi
0x18009f4c7  push    rdi
0x18009f4c8  push    r14
0x18009f4ca  push    r15
0x18009f4cc  mov     rbp, rsp
0x18009f4cf  sub     rsp, 60h
0x18009f4d3  mov     rax, cs:__security_cookie
0x18009f4da  xor     rax, rsp
0x18009f4dd  mov     [rbp+var_10], rax
0x18009f4e1  xor     r15d, r15d
0x18009f4e4  mov     rsi, hdcDraw
0x18009f4e7  mov     rdi, this
0x18009f4ea  mov     [this+30h], r15d
0x18009f4ee  cmp     [this+10h], r15
0x18009f4f2  jnz     short loc_18009F508
0x18009f4f4  call    ?LoadHPRES@CMfObject@@AEAAPEAXXZ; CMfObject::LoadHPRES(void)
0x18009f4f9  test    rax, rax
0x18009f4fc  jnz     short loc_18009F508
0x18009f4fe  mov     eax, 80040007h
0x18009f503  jmp     loc_18009F85F
0x18009f508  mov     this, [rbp+arg_20]
0x18009f50c  mov     eax, [this]
0x18009f50e  mov     [rbp+rect.left], eax
0x18009f511  mov     eax, [this+8]
0x18009f514  mov     [rbp+rect.right], eax
0x18009f517  mov     eax, [this+4]
0x18009f51a  mov     [rbp+rect.top], eax
0x18009f51d  mov     eax, [this+0Ch]
0x18009f520  mov     this, rsi; hdc
0x18009f523  mov     [rbp+rect.bottom], eax
0x18009f526  call    cs:__imp_SaveDC
0x18009f52d  nop     dword ptr [rax+rax+00h]
0x18009f532  mov     r14d, eax
0x18009f535  test    eax, eax
0x18009f537  jnz     short loc_18009F543
0x18009f539  mov     eax, 8007000Eh
0x18009f53e  jmp     loc_18009F85F
0x18009f543  mov     this, rsi; hdc
0x18009f546  mov     dword ptr [rdi+2Ch], 10h
0x18009f54d  call    OleIsDcMeta
0x18009f552  mov     [rdi+28h], eax
0x18009f555  test    eax, eax
0x18009f557  jnz     loc_18009F6A8
0x18009f55d  mov     eax, [rbp+rect.bottom]
0x18009f560  mov     this, rsi; hdc
0x18009f563  mov     r9d, [rbp+rect.right]; right
0x18009f567  mov     r8d, [rbp+rect.top]; top
0x18009f56b  mov     edx, [rbp+rect.left]; left
0x18009f56e  mov     [rsp+60h+bottom], eax; bottom
0x18009f572  call    cs:__imp_IntersectClipRect
0x18009f579  nop     dword ptr [rax+rax+00h]
0x18009f57e  cmp     eax, 1
0x18009f581  jz      $errRtn_135
0x18009f587  test    eax, eax
0x18009f589  jnz     short loc_18009F597
0x18009f58b  mov     dword ptr [rdi+30h], 80004005h
0x18009f592  jmp     $errRtn_135
0x18009f597  mov     this, rsi; hdc
0x18009f59a  call    cs:__imp_GetGraphicsMode
0x18009f5a1  nop     dword ptr [rax+rax+00h]
0x18009f5a6  mov     r8d, 2; c
0x18009f5ac  cmp     eax, r8d
0x18009f5af  jnz     loc_18009F643
0x18009f5b5  xor     ecx, ecx; hWnd
0x18009f5b7  call    cs:__imp_GetDC
0x18009f5be  nop     dword ptr [rax+rax+00h]
0x18009f5c3  movdqa  xmm0, cs:__xmm@000003e8000003e80000000000000000
0x18009f5cb  lea     r8, [rbp+rc]; lprc
0x18009f5cf  mov     this, rax; hdc
0x18009f5d2  xor     r9d, r9d; lpDesc
0x18009f5d5  xor     edx, edx; lpFilename
0x18009f5d7  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x18009f5dc  call    cs:__imp_CreateEnhMetaFileW
0x18009f5e3  nop     dword ptr [rax+rax+00h]
0x18009f5e8  mov     __formal, [rdi+10h]; hmf
0x18009f5ec  mov     this, rax; hdc
0x18009f5ef  mov     rbx, rax
0x18009f5f2  call    cs:__imp_PlayMetaFile
0x18009f5f9  nop     dword ptr [rax+rax+00h]
0x18009f5fe  mov     this, rbx; hdc
0x18009f601  call    cs:__imp_CloseEnhMetaFile
0x18009f608  nop     dword ptr [rax+rax+00h]
0x18009f60d  mov     rbx, rax
0x18009f610  test    rax, rax
0x18009f613  jz      $errRtn_135
0x18009f619  lea     r8, [rbp+rect]; lprect
0x18009f61d  mov     __formal, rax; hmf
0x18009f620  mov     this, rsi; hdc
0x18009f623  call    cs:__imp_PlayEnhMetaFile
0x18009f62a  nop     dword ptr [rax+rax+00h]
0x18009f62f  mov     this, rbx; hmf
0x18009f632  call    cs:__imp_DeleteEnhMetaFile
0x18009f639  nop     dword ptr [rax+rax+00h]
0x18009f63e  jmp     $errRtn_135
0x18009f643  lea     __formal, [rbp+rect]; lppt
0x18009f647  mov     this, rsi; hdc
0x18009f64a  call    cs:__imp_LPtoDP
0x18009f651  nop     dword ptr [rax+rax+00h]
0x18009f656  mov     edx, 8; iMode
0x18009f65b  mov     this, rsi; hdc
0x18009f65e  call    cs:__imp_SetMapMode
0x18009f665  nop     dword ptr [rax+rax+00h]
0x18009f66a  mov     r8d, [rbp+rect.top]; y
0x18009f66e  xor     r9d, r9d; lppt
0x18009f671  mov     edx, [rbp+rect.left]; x
0x18009f674  mov     this, rsi; hdc
0x18009f677  call    cs:__imp_SetViewportOrgEx
0x18009f67e  nop     dword ptr [rax+rax+00h]
0x18009f683  mov     r8d, [rbp+rect.bottom]
0x18009f687  xor     r9d, r9d; lpsz
0x18009f68a  mov     edx, [rbp+rect.right]
0x18009f68d  mov     this, rsi; hdc
0x18009f690  sub     r8d, [rbp+rect.top]; y
0x18009f694  sub     edx, [rbp+rect.left]; x
0x18009f697  call    cs:__imp_SetViewportExtEx
0x18009f69e  nop     dword ptr [rax+rax+00h]
0x18009f6a3  jmp     loc_18009F771
0x18009f6a8  mov     rbx, [rbp+arg_28]
0x18009f6ac  or      r14d, 0FFFFFFFFh
0x18009f6b0  test    rbx, rbx
0x18009f6b3  jnz     short loc_18009F6BF
0x18009f6b5  mov     eax, 80040140h
0x18009f6ba  jmp     loc_18009F85F
0x18009f6bf  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009f6c6  xor     edx, edx; dwFlags
0x18009f6c8  lea     r8d, [__formal+38h]; dwBytes
0x18009f6cc  call    cs:__imp_HeapAlloc
0x18009f6d3  nop     dword ptr [rax+rax+00h]
0x18009f6d8  mov     [rdi+18h], rax
0x18009f6dc  mov     this, rax
0x18009f6df  test    rax, rax
0x18009f6e2  jnz     short loc_18009F6F0
0x18009f6e4  mov     dword ptr [rdi+30h], 8007000Eh
0x18009f6eb  jmp     $errRtn_135
0x18009f6f0  mov     [rdi+20h], this
0x18009f6f4  mov     eax, [rbx]
0x18009f6f6  mov     [this+20h], eax
0x18009f6f9  mov     eax, [rbx+4]
0x18009f6fc  mov     this, [rdi+18h]
0x18009f700  mov     [this+24h], eax
0x18009f703  mov     eax, [rbx+8]
0x18009f706  mov     this, [rdi+18h]
0x18009f70a  mov     [this+28h], eax
0x18009f70d  mov     this, [rdi+18h]
0x18009f711  mov     eax, [rbx+0Ch]
0x18009f714  mov     [this+2Ch], eax
0x18009f717  mov     rax, [rdi+18h]
0x18009f71b  mov     ecx, [rbp+rect.left]
0x18009f71e  sub     ecx, [rbx]
0x18009f720  mov     [rax+30h], ecx
0x18009f723  mov     rax, [rdi+18h]
0x18009f727  mov     ecx, [rbp+rect.top]
0x18009f72a  sub     ecx, [rbx+4]
0x18009f72d  mov     [rax+34h], ecx
0x18009f730  mov     rax, [rdi+20h]
0x18009f734  mov     ecx, [rbp+rect.right]
0x18009f737  sub     ecx, [rbp+rect.left]
0x18009f73a  mov     [rax+10h], ecx
0x18009f73d  mov     rax, [rdi+20h]
0x18009f741  mov     ecx, [rbp+rect.bottom]
0x18009f744  sub     ecx, [rbp+rect.top]
0x18009f747  mov     [rax+14h], ecx
0x18009f74a  mov     rax, [rdi+20h]
0x18009f74e  mov     [rax], r15d
0x18009f751  mov     rax, [rdi+20h]
0x18009f755  mov     [rax+4], r15d
0x18009f759  mov     rax, [rdi+20h]
0x18009f75d  mov     [rax+8], r15d
0x18009f761  mov     rax, [rdi+20h]
0x18009f765  mov     [rax+0Ch], r15d
0x18009f769  mov     rax, [rdi+20h]
0x18009f76d  mov     [rax+18h], r15
0x18009f771  mov     rax, [rbp+arg_30]
0x18009f775  lea     r8, ?MfCallbackFuncForDraw@@YAHPEAUHDC__@@PEAUtagHANDLETABLE@@PEAUtagMETARECORD@@H_J@Z; proc
0x18009f77c  mov     __formal, [rdi+10h]; hmf
0x18009f780  mov     hdcDraw, rdi; param
0x18009f783  mov     [rdi+48h], rax
0x18009f787  mov     this, rsi; hdc
0x18009f78a  mov     rax, [rbp+arg_38]
0x18009f78e  mov     [rdi+50h], rax
0x18009f792  mov     [rdi+70h], r15
0x18009f796  mov     [rdi+78h], r15
0x18009f79a  call    cs:__imp_EnumMetaFile
0x18009f7a1  nop     dword ptr [rax+rax+00h]
0x18009f7a6  cmp     [rdi+28h], r15d
0x18009f7aa  jz      short loc_18009F7F6
0x18009f7ac  jmp     short loc_18009F7CC
0x18009f7ae  mov     rax, [this+18h]
0x18009f7b2  mov     [r8+18h], rax
0x18009f7b6  mov     r8, this; lpMem
0x18009f7b9  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009f7c0  call    cs:__imp_HeapFree
0x18009f7c7  nop     dword ptr [rax+rax+00h]
0x18009f7cc  mov     r8, [rdi+18h]; lpMem
0x18009f7d0  xor     edx, edx; dwFlags
0x18009f7d2  mov     this, [r8+18h]
0x18009f7d6  test    this, this
0x18009f7d9  jnz     short loc_18009F7AE
0x18009f7db  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009f7e2  call    cs:__imp_HeapFree
0x18009f7e9  nop     dword ptr [rax+rax+00h]
0x18009f7ee  mov     [rdi+20h], r15
0x18009f7f2  mov     [rdi+18h], r15
0x18009f7f6  cmp     [rdi+78h], r15
0x18009f7fa  jz      short loc_18009F846
0x18009f7fc  cmp     [rdi+28h], r15d
0x18009f800  jz      short loc_18009F815
0x18009f802  mov     ecx, 0Fh; i
0x18009f807  call    cs:__imp_GetStockObject
0x18009f80e  nop     dword ptr [rax+rax+00h]
0x18009f813  jmp     short loc_18009F819
0x18009f815  mov     rax, [rdi+70h]
0x18009f819  test    rax, rax
0x18009f81c  jz      short loc_18009F836
0x18009f81e  mov     r8d, 1; bForceBkgd
0x18009f824  mov     __formal, rax; hPal
0x18009f827  mov     this, rsi; hdc
0x18009f82a  call    cs:__imp_SelectPalette
0x18009f831  nop     dword ptr [rax+rax+00h]
0x18009f836  mov     this, [rdi+78h]; ho
0x18009f83a  call    cs:__imp_DeleteObject
0x18009f841  nop     dword ptr [rax+rax+00h]
0x18009f846  mov     [rdi+28h], r15d
0x18009f84a  mov     edx, r14d; nSavedDC
0x18009f84d  mov     this, rsi; hdc
0x18009f850  call    cs:__imp_RestoreDC
0x18009f857  nop     dword ptr [rax+rax+00h]
0x18009f85c  mov     eax, [rdi+30h]
0x18009f85f  mov     this, [rbp+var_10]
0x18009f863  xor     this, rsp; StackCookie
0x18009f866  call    __security_check_cookie
0x18009f86b  mov     rbx, [rsp+60h+arg_8]
0x18009f873  add     rsp, 60h
0x18009f877  pop     r15
0x18009f879  pop     r14
0x18009f87b  pop     rdi
0x18009f87c  pop     rsi
0x18009f87d  pop     rbp
0x18009f87e  retn
```

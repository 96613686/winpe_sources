# CChevronOwnerDrawMenu::DrawItem(tagDRAWITEMSTRUCT *)

- ea: `0x1802b5000`
- end: `0x1802b5684`
- name: `?DrawItem@CChevronOwnerDrawMenu@@UEAAXPEAUtagDRAWITEMSTRUCT@@@Z`
- size: `1668`
- prototype: `void __fastcall(CChevronOwnerDrawMenu *this, tagDRAWITEMSTRUCT *pdis)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003230`
- `0x1800033dc`
- `0x18000df50`
- `0x18001d090`
- `0x18023f820`
- `0x1802aee30`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802aef40`
- `0x1802af260`
- `0x1802b09a0`
- `0x1802b0e30`
- `0x1802b1590`
- `0x1802b2580`
- `0x1802b26d0`
- `0x1802b5000`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `VCRUNTIME140!memset` at `0x1802b5075`
- `VCRUNTIME140!memset` at `0x1802b5075`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1802b510a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1802b510a`
- `USER32!GetSystemMetrics` at `0x1802b5188`
- `USER32!GetSystemMetrics` at `0x1802b5196`
- `USER32!GetSystemMetrics` at `0x1802b5188`
- `USER32!GetSystemMetrics` at `0x1802b5196`
- `USER32!GetSysColor` at `0x1802b51db`
- `USER32!GetSysColor` at `0x1802b5269`
- `USER32!GetSysColor` at `0x1802b528f`
- `USER32!GetSysColor` at `0x1802b529c`
- `USER32!GetSysColor` at `0x1802b52e8`
- `USER32!GetSysColor` at `0x1802b5351`
- `USER32!GetSysColor` at `0x1802b53da`
- `USER32!GetSysColor` at `0x1802b542d`
- `USER32!GetSysColor` at `0x1802b543a`
- `USER32!GetSysColor` at `0x1802b5496`
- `USER32!GetSysColor` at `0x1802b51db`
- `USER32!GetSysColor` at `0x1802b5269`
- `USER32!GetSysColor` at `0x1802b528f`
- `USER32!GetSysColor` at `0x1802b529c`
- `USER32!GetSysColor` at `0x1802b52e8`
- `USER32!GetSysColor` at `0x1802b5351`
- `USER32!GetSysColor` at `0x1802b53da`
- `USER32!GetSysColor` at `0x1802b542d`
- `USER32!GetSysColor` at `0x1802b543a`
- `USER32!GetSysColor` at `0x1802b5496`
- `USER32!GetMenuItemInfoW` at `0x1802b509a`
- `USER32!GetMenuItemInfoW` at `0x1802b50f9`
- `USER32!GetMenuItemInfoW` at `0x1802b509a`
- `USER32!GetMenuItemInfoW` at `0x1802b50f9`
- `USER32!CopyRect` at `0x1802b5145`
- `USER32!CopyRect` at `0x1802b5255`
- `USER32!CopyRect` at `0x1802b5145`
- `USER32!CopyRect` at `0x1802b5255`
- `USER32!InflateRect` at `0x1802b55a4`
- `USER32!InflateRect` at `0x1802b55a4`
- `GDI32!ExtTextOutW` at `0x1802b53c8`
- `GDI32!ExtTextOutW` at `0x1802b54f5`
- `GDI32!ExtTextOutW` at `0x1802b53c8`
- `GDI32!ExtTextOutW` at `0x1802b54f5`
- `GDI32!DeleteDC` at `0x1802b55f6`
- `GDI32!DeleteDC` at `0x1802b55f6`
- `GDI32!BitBlt` at `0x1802b55d9`
- `GDI32!BitBlt` at `0x1802b55d9`
- `GDI32!SelectObject` at `0x1802b558d`
- `GDI32!SelectObject` at `0x1802b558d`
- `GDI32!CreateCompatibleDC` at `0x1802b51ff`
- `GDI32!CreateCompatibleDC` at `0x1802b556b`
- `GDI32!CreateCompatibleDC` at `0x1802b51ff`
- `GDI32!CreateCompatibleDC` at `0x1802b556b`
- `GDI32!GetObjectW` at `0x1802b5170`
- `GDI32!GetObjectW` at `0x1802b5170`
- `GDI32!GetTextExtentPoint32W` at `0x1802b523d`
- `GDI32!GetTextExtentPoint32W` at `0x1802b523d`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=5
void __fastcall CChevronOwnerDrawMenu::DrawItem(CChevronOwnerDrawMenu *this, tagDRAWITEMSTRUCT *pdis)
{
  CDC *v4; // rsi
  BOOL MenuItemInfoW; // edi
  int v6; // r13d
  unsigned int cch; // edx
  wchar_t *m_pszData; // rax
  int v9; // eax
  CBitmap *itemData; // r14
  int SystemMetrics; // r12d
  int v12; // r9d
  DWORD SysColor; // r12d
  HDC CompatibleDC; // rax
  tagRECT *p_rcItem; // rdx
  DWORD v16; // eax
  DWORD clrBottomRight; // ebx
  DWORD clrTopLeft; // eax
  unsigned int (__fastcall *SetBkColor)(CDC *, unsigned int); // rbx
  DWORD v20; // eax
  unsigned int (__fastcall *SetTextColor)(CDC *, unsigned int); // rbx
  DWORD v22; // eax
  int v23; // ecx
  unsigned int (__fastcall *v24)(CDC *, unsigned int); // rbx
  DWORD v25; // eax
  int v26; // edi
  unsigned int (__fastcall *v27)(CDC *, unsigned int); // rbx
  DWORD v28; // eax
  DWORD v29; // ebx
  DWORD v30; // eax
  HDC v31; // rax
  void *m_hObject; // rdx
  HGDIOBJ v33; // rax
  HDC v34; // rax
  wchar_t *v35; // rdx
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strText; // [rsp+50h] [rbp-B0h] BYREF
  CBitmap bmp; // [rsp+58h] [rbp-A8h] BYREF
  int v38; // [rsp+68h] [rbp-98h]
  CDC dcMem; // [rsp+70h] [rbp-90h] BYREF
  tagMENUITEMINFOW info; // [rsp+90h] [rbp-70h] BYREF
  CRect rc; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE rcFill[24]; // [rsp+F0h] [rbp-10h] OVERLAPPED BYREF
  int v43; // [rsp+108h] [rbp+8h]
  CRect rcItem; // [rsp+110h] [rbp+10h] BYREF

  bmp.__vftable = (CBitmap_vtbl *)this;
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &strText,
    &CmdLine);
  v4 = CDC::FromHandle(pdis->hDC);
  v38 = v4->SaveDC(v4);
  memset(&info, 0, sizeof(info));
  info.cbSize = 80;
  info.fMask = 64;
  MenuItemInfoW = 0;
  v6 = 1;
  if ( GetMenuItemInfoW(this->m_hMenu, pdis->itemID, 0, &info) )
  {
    cch = info.cch;
    if ( (info.cch & 0x80000000) != 0 )
      goto LABEL_44;
    m_pszData = strText.m_pszData;
    if ( (((1 - *((_DWORD *)strText.m_pszData - 2)) | (*((_DWORD *)strText.m_pszData - 3) - info.cch)) & 0x80000000) != 0 )
    {
      ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&strText, info.cch);
      m_pszData = strText.m_pszData;
      cch = info.cch;
    }
    info.dwTypeData = m_pszData;
    info.cch = cch + 1;
    MenuItemInfoW = GetMenuItemInfoW(this->m_hMenu, pdis->itemID, 0, &info);
    v9 = wcsnlen(strText.m_pszData, *((int *)strText.m_pszData - 3));
    if ( v9 < 0 || v9 > *((_DWORD *)strText.m_pszData - 3) )
LABEL_44:
      ATL::AtlThrowImpl(-2147024809);
    *((_DWORD *)strText.m_pszData - 4) = v9;
    strText.m_pszData[v9] = 0;
  }
  itemData = (CBitmap *)pdis->itemData;
  CopyRect(&rcItem, &pdis->rcItem);
  if ( itemData && CObject::IsKindOf(itemData, &CBitmap::classCBitmap) )
  {
    GetObjectW(itemData->m_hObject, 32, rcFill);
    SystemMetrics = *(_DWORD *)&rcFill[8];
    v12 = *(_DWORD *)&rcFill[4];
  }
  else
  {
    v6 = 0;
    SystemMetrics = GetSystemMetrics(50);
    v12 = GetSystemMetrics(49);
  }
  rc.top = (rcItem.bottom - rcItem.top) / 2 - SystemMetrics / 2 + rcItem.top - 1;
  rc.left = 0;
  rc.bottom = SystemMetrics + (rcItem.bottom - rcItem.top) / 2 - SystemMetrics / 2 + rcItem.top;
  rc.right = v12 + 1;
  SysColor = GetSysColor(4);
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcMem.m_hDC, 0, 20);
  CompatibleDC = CreateCompatibleDC(0);
  CDC::Attach(&dcMem, CompatibleDC);
  v4->SelectObject(v4, (CFont *)&bmp.Serialize);
  GetTextExtentPoint32W(v4->m_hAttribDC, strText.m_pszData, *((_DWORD *)strText.m_pszData - 4), (LPSIZE)&bmp);
  p_rcItem = &pdis->rcItem;
  if ( (pdis->itemState & 1) != 0 )
  {
    CopyRect((LPRECT)rcFill, p_rcItem);
    *(_DWORD *)rcFill = rc.right + 2;
    v16 = GetSysColor(13);
    CDC::FillSolidRect(v4, (const tagRECT *)rcFill, v16);
    if ( v6 && (pdis->itemState & 0xA) == 0 )
    {
      clrBottomRight = GetSysColor(16);
      clrTopLeft = GetSysColor(20);
      CDC::Draw3dRect(v4, rc.left, rc.top, rc.right - rc.left + 1, rc.bottom - rc.top + 1, clrTopLeft, clrBottomRight);
    }
    if ( MenuItemInfoW )
    {
      SetBkColor = v4->SetBkColor;
      v20 = GetSysColor(13);
      SetBkColor(v4, v20);
      SetTextColor = v4->SetTextColor;
      if ( (pdis->itemState & 2) != 0 )
      {
        v22 = SysColor;
LABEL_29:
        SetTextColor(v4, v22);
        ExtTextOutW(
          v4->m_hDC,
          rc.right + 3,
          rc.top + (rc.bottom - rc.top) / 2 - SHIDWORD(bmp.__vftable) / 2,
          2u,
          0,
          strText.m_pszData,
          *((_DWORD *)strText.m_pszData - 4),
          0);
        goto LABEL_30;
      }
      v23 = 14;
LABEL_28:
      v22 = GetSysColor(v23);
      goto LABEL_29;
    }
  }
  else
  {
    CDC::FillSolidRect(v4, p_rcItem, SysColor);
    v4->SetBkColor(v4, SysColor);
    if ( (pdis->itemState & 2) != 0 )
    {
      v24 = v4->SetTextColor;
      v25 = GetSysColor(20);
      v24(v4, v25);
      CDC::SetBkMode(v4, 1);
      if ( MenuItemInfoW )
      {
        v26 = SHIDWORD(bmp.__vftable) / 2;
        ExtTextOutW(
          v4->m_hDC,
          rc.right + 4,
          (rc.bottom - rc.top) / 2 - SHIDWORD(bmp.__vftable) / 2 + rc.top + 1,
          2u,
          0,
          strText.m_pszData,
          *((_DWORD *)strText.m_pszData - 4),
          0);
        v27 = v4->SetTextColor;
        v28 = GetSysColor(17);
        v27(v4, v28);
        ExtTextOutW(
          v4->m_hDC,
          rc.right + 3,
          rc.top + (rc.bottom - rc.top) / 2 - v26,
          0,
          0,
          strText.m_pszData,
          *((_DWORD *)strText.m_pszData - 4),
          0);
      }
    }
    else
    {
      if ( v6 && (pdis->itemState & 8) != 0 )
      {
        v29 = GetSysColor(20);
        v30 = GetSysColor(16);
        CDC::Draw3dRect(v4, rc.left, rc.top, rc.right - rc.left + 1, rc.bottom - rc.top + 1, v30, v29);
      }
      if ( MenuItemInfoW )
      {
        v4->SetBkColor(v4, SysColor);
        SetTextColor = v4->SetTextColor;
        v23 = 7;
        goto LABEL_28;
      }
    }
  }
LABEL_30:
  if ( !v6 )
    goto LABEL_41;
  bmp.m_hObject = 0;
  bmp.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  if ( (pdis->itemState & 2) != 0 )
  {
    AfxGetGrayBitmap(itemData, &bmp, SysColor);
LABEL_35:
    itemData = &bmp;
    goto LABEL_36;
  }
  if ( (pdis->itemState & 8) != 0 )
  {
    AfxGetDitheredBitmap(itemData, &bmp, SysColor, 0xFFFFFFu);
    goto LABEL_35;
  }
LABEL_36:
  *(_QWORD *)rcFill = CDC::`vftable';
  *(_OWORD *)&rcFill[8] = 0;
  v43 = 0;
  v31 = CreateCompatibleDC(0);
  CDC::Attach((CDC *)rcFill, v31);
  m_hObject = 0;
  if ( itemData )
    m_hObject = itemData->m_hObject;
  v33 = SelectObject(*(HDC *)&rcFill[8], m_hObject);
  CGdiObject::FromHandle(v33);
  InflateRect(&rc, -1, -1);
  BitBlt(v4->m_hDC, rc.left, rc.top, rc.right, rc.bottom, *(HDC *)&rcFill[8], 0, 0, 0xCC0020u);
  *(_QWORD *)rcFill = CDC::`vftable';
  if ( *(_QWORD *)&rcFill[8] )
  {
    v34 = CDC::Detach((CDC *)rcFill);
    DeleteDC(v34);
  }
  bmp.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&bmp);
LABEL_41:
  v4->RestoreDC(v4, v38);
  CDC::~CDC(&dcMem);
  v35 = strText.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)strText.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 8LL))(*(_QWORD *)v35);
}

```

## disassembly

```asm
0x1802b5000  mov     [rsp-8+arg_10], rbx
0x1802b5005  push    rbp
0x1802b5006  push    rsi
0x1802b5007  push    rdi
0x1802b5008  push    r12
0x1802b500a  push    r13
0x1802b500c  push    r14
0x1802b500e  push    r15
0x1802b5010  lea     rbp, [rsp-30h]
0x1802b5015  sub     rsp, 130h
0x1802b501c  mov     rax, cs:__security_cookie
0x1802b5023  xor     rax, rsp
0x1802b5026  mov     [rbp+60h+var_40], rax
0x1802b502a  mov     r15, pdis
0x1802b502d  mov     rbx, this
0x1802b5030  mov     [rsp+160h+bmp.__vftable], this
0x1802b5035  lea     pdis, CmdLine; pszSrc
0x1802b503c  lea     this, [rsp+160h+strText]; this
0x1802b5041  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x1802b5046  nop
0x1802b5047  mov     this, [r15+20h]; hDC
0x1802b504b  call    ?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x1802b5050  mov     rsi, rax
0x1802b5053  mov     this, [rax]
0x1802b5056  mov     rax, [this+48h]
0x1802b505a  mov     this, rsi
0x1802b505d  call    cs:__guard_dispatch_icall_fptr
0x1802b5063  mov     [rsp+160h+var_F8], eax
0x1802b5067  mov     edi, 50h ; 'P'
0x1802b506c  mov     r8d, edi; Size
0x1802b506f  xor     edx, edx; Val
0x1802b5071  lea     this, [rbp+60h+info]; void *
0x1802b5075  call    cs:__imp_memset
0x1802b507b  mov     [rbp+60h+info.cbSize], edi
0x1802b507e  mov     [rbp+60h+info.fMask], 40h ; '@'
0x1802b5085  xor     r12d, r12d
0x1802b5088  mov     edi, r12d
0x1802b508b  lea     r9, [rbp+60h+info]; lpmii
0x1802b508f  xor     r8d, r8d; fByPosition
0x1802b5092  mov     edx, [r15+8]; item
0x1802b5096  mov     this, [rbx+8]; hmenu
0x1802b509a  call    cs:__imp_GetMenuItemInfoW
0x1802b50a0  lea     r13d, [r12+1]
0x1802b50a5  test    eax, eax
0x1802b50a7  jz      loc_1802B5136
0x1802b50ad  mov     edx, [rbp+60h+info.cch]; nLength
0x1802b50b0  test    edx, edx
0x1802b50b2  js      loc_1802B5679
0x1802b50b8  mov     rax, [rsp+160h+strText.m_pszData]
0x1802b50bd  mov     r8d, r13d
0x1802b50c0  sub     r8d, [rax-8]
0x1802b50c4  mov     ecx, [rax-0Ch]
0x1802b50c7  sub     ecx, edx
0x1802b50c9  or      ecx, r8d
0x1802b50cc  jge     short loc_1802B50E0
0x1802b50ce  lea     this, [rsp+160h+strText]; this
0x1802b50d3  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x1802b50d8  mov     rax, [rsp+160h+strText.m_pszData]
0x1802b50dd  mov     edx, [rbp+60h+info.cch]
0x1802b50e0  mov     [rbp+60h+info.dwTypeData], rax
0x1802b50e4  add     edx, r13d
0x1802b50e7  mov     [rbp+60h+info.cch], edx
0x1802b50ea  lea     r9, [rbp+60h+info]; lpmii
0x1802b50ee  xor     r8d, r8d; fByPosition
0x1802b50f1  mov     edx, [r15+8]; item
0x1802b50f5  mov     this, [rbx+8]; hmenu
0x1802b50f9  call    cs:__imp_GetMenuItemInfoW
0x1802b50ff  mov     edi, eax
0x1802b5101  mov     this, [rsp+160h+strText.m_pszData]; Source
0x1802b5106  movsxd  pdis, dword ptr [this-0Ch]; MaxCount
0x1802b510a  call    cs:__imp_wcsnlen
0x1802b5110  test    eax, eax
0x1802b5112  js      loc_1802B5679
0x1802b5118  mov     this, [rsp+160h+strText.m_pszData]
0x1802b511d  cmp     eax, [this-0Ch]
0x1802b5120  jg      loc_1802B5679
0x1802b5126  mov     [this-10h], eax
0x1802b5129  movsxd  this, eax
0x1802b512c  mov     rax, [rsp+160h+strText.m_pszData]
0x1802b5131  mov     [rax+this*2], r12w
0x1802b5136  mov     r14, [r15+38h]
0x1802b513a  lea     rbx, [r15+28h]
0x1802b513e  mov     pdis, rbx; lprcSrc
0x1802b5141  lea     this, [rbp+60h+rcItem]; lprcDst
0x1802b5145  call    cs:__imp_CopyRect
0x1802b514b  test    r14, r14
0x1802b514e  jz      short loc_1802B5180
0x1802b5150  lea     pdis, ?classCBitmap@CBitmap@@2UCRuntimeClass@@B; pClass
0x1802b5157  mov     this, r14; this
0x1802b515a  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1802b515f  test    eax, eax
0x1802b5161  jz      short loc_1802B5180
0x1802b5163  lea     r8, [rbp+60h+rcFill]; pv
0x1802b5167  mov     edx, 20h ; ' '; c
0x1802b516c  mov     this, [r14+8]; h
0x1802b5170  call    cs:__imp_GetObjectW
0x1802b5176  mov     r12d, [rbp+60h+rcFill.right]
0x1802b517a  mov     r9d, [rbp+60h+rcFill.top]
0x1802b517e  jmp     short loc_1802B519F
0x1802b5180  mov     r13d, r12d
0x1802b5183  mov     ecx, 32h ; '2'; nIndex
0x1802b5188  call    cs:__imp_GetSystemMetrics
0x1802b518e  mov     r12d, eax
0x1802b5191  mov     ecx, 31h ; '1'; nIndex
0x1802b5196  call    cs:__imp_GetSystemMetrics
0x1802b519c  mov     r9d, eax
0x1802b519f  mov     eax, [rbp+60h+rcItem.bottom]
0x1802b51a2  mov     r8d, [rbp+60h+rcItem.top]
0x1802b51a6  sub     eax, r8d
0x1802b51a9  cdq
0x1802b51aa  sub     eax, edx
0x1802b51ac  sar     eax, 1
0x1802b51ae  mov     ecx, eax
0x1802b51b0  mov     eax, r12d
0x1802b51b3  cdq
0x1802b51b4  sub     eax, edx
0x1802b51b6  sar     eax, 1
0x1802b51b8  sub     ecx, eax
0x1802b51ba  lea     eax, [r8-1]
0x1802b51be  add     eax, ecx
0x1802b51c0  mov     [rbp+60h+rc.top], eax
0x1802b51c3  and     [rbp+60h+rc.left], 0
0x1802b51c7  inc     eax
0x1802b51c9  add     eax, r12d
0x1802b51cc  mov     [rbp+60h+rc.bottom], eax
0x1802b51cf  lea     eax, [r9+1]
0x1802b51d3  mov     [rbp+60h+rc.right], eax
0x1802b51d6  mov     ecx, 4; nIndex
0x1802b51db  call    cs:__imp_GetSysColor
0x1802b51e1  mov     r12d, eax
0x1802b51e4  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1802b51eb  mov     [rsp+160h+dcMem.__vftable], rax
0x1802b51f0  xorps   xmm0, xmm0
0x1802b51f3  movdqu  xmmword ptr [rsp+160h+dcMem.m_hDC], xmm0
0x1802b51f9  and     [rbp+60h+dcMem.m_bPrinting], 0
0x1802b51fd  xor     ecx, ecx; hdc
0x1802b51ff  call    cs:__imp_CreateCompatibleDC
0x1802b5205  mov     pdis, rax; hDC
0x1802b5208  lea     this, [rsp+160h+dcMem]; this
0x1802b520d  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802b5212  mov     this, [rsi]
0x1802b5215  mov     rax, [this+60h]
0x1802b5219  mov     pdis, [rsp+160h+bmp.__vftable]
0x1802b521e  add     pdis, 10h
0x1802b5222  mov     this, rsi
0x1802b5225  call    cs:__guard_dispatch_icall_fptr
0x1802b522b  mov     pdis, [rsp+160h+strText.m_pszData]; lpString
0x1802b5230  lea     r9, [rsp+160h+bmp]; psizl
0x1802b5235  mov     r8d, [pdis-10h]; c
0x1802b5239  mov     this, [rsi+10h]; hdc
0x1802b523d  call    cs:__imp_GetTextExtentPoint32W
0x1802b5243  mov     pdis, rbx; lpRect
0x1802b5246  test    byte ptr [r15+10h], 1
0x1802b524b  jz      loc_1802B531C
0x1802b5251  lea     this, [rbp+60h+rcFill]; lprcDst
0x1802b5255  call    cs:__imp_CopyRect
0x1802b525b  mov     eax, [rbp+60h+rc.right]
0x1802b525e  add     eax, 2
0x1802b5261  mov     [rbp+60h+rcFill.left], eax
0x1802b5264  mov     ecx, 0Dh; nIndex
0x1802b5269  call    cs:__imp_GetSysColor
0x1802b526f  mov     r8d, eax; clr
0x1802b5272  lea     pdis, [rbp+60h+rcFill]; lpRect
0x1802b5276  mov     this, rsi; this
0x1802b5279  call    ?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z; CDC::FillSolidRect(tagRECT const *,ulong)
0x1802b527e  xor     ebx, ebx
0x1802b5280  test    r13d, r13d
0x1802b5283  jz      short loc_1802B52D4
0x1802b5285  test    byte ptr [r15+10h], 0Ah
0x1802b528a  jnz     short loc_1802B52D4
0x1802b528c  lea     ecx, [rbx+10h]; nIndex
0x1802b528f  call    cs:__imp_GetSysColor
0x1802b5295  mov     ebx, eax
0x1802b5297  mov     ecx, 14h; nIndex
0x1802b529c  call    cs:__imp_GetSysColor
0x1802b52a2  mov     r10d, [rbp+60h+rc.bottom]
0x1802b52a6  mov     r8d, [rbp+60h+rc.top]; y
0x1802b52aa  sub     r10d, r8d
0x1802b52ad  inc     r10d
0x1802b52b0  mov     r9d, [rbp+60h+rc.right]
0x1802b52b4  mov     edx, [rbp+60h+rc.left]; x
0x1802b52b7  sub     r9d, edx
0x1802b52ba  inc     r9d; cx
0x1802b52bd  mov     [rsp+160h+clrBottomRight], ebx; clrBottomRight
0x1802b52c1  mov     [rsp+160h+clrTopLeft], eax; clrTopLeft
0x1802b52c5  mov     [rsp+160h+cy], r10d; cy
0x1802b52ca  mov     this, rsi; this
0x1802b52cd  call    ?Draw3dRect@CDC@@QEAAXHHHHKK@Z; CDC::Draw3dRect(int,int,int,int,ulong,ulong)
0x1802b52d2  xor     ebx, ebx
0x1802b52d4  test    edi, edi
0x1802b52d6  jz      loc_1802B54FB
0x1802b52dc  mov     rax, [rsi]
0x1802b52df  mov     rbx, [rax+68h]
0x1802b52e3  mov     ecx, 0Dh; nIndex
0x1802b52e8  call    cs:__imp_GetSysColor
0x1802b52ee  mov     edx, eax
0x1802b52f0  mov     this, rsi
0x1802b52f3  mov     rax, rbx
0x1802b52f6  call    cs:__guard_dispatch_icall_fptr
0x1802b52fc  mov     rax, [rsi]
0x1802b52ff  mov     rbx, [rax+70h]
0x1802b5303  test    byte ptr [r15+10h], 2
0x1802b5308  jz      short loc_1802B5312
0x1802b530a  mov     eax, r12d
0x1802b530d  jmp     loc_1802B549C
0x1802b5312  mov     ecx, 0Eh
0x1802b5317  jmp     loc_1802B5496
0x1802b531c  mov     r8d, r12d; clr
0x1802b531f  mov     this, rsi; this
0x1802b5322  call    ?FillSolidRect@CDC@@QEAAXPEBUtagRECT@@K@Z; CDC::FillSolidRect(tagRECT const *,ulong)
0x1802b5327  mov     rax, [rsi]
0x1802b532a  mov     edx, r12d
0x1802b532d  mov     this, rsi
0x1802b5330  mov     rax, [rax+68h]
0x1802b5334  call    cs:__guard_dispatch_icall_fptr
0x1802b533a  test    byte ptr [r15+10h], 2
0x1802b533f  jz      loc_1802B541C
0x1802b5345  mov     rax, [rsi]
0x1802b5348  mov     rbx, [rax+70h]
0x1802b534c  mov     ecx, 14h; nIndex
0x1802b5351  call    cs:__imp_GetSysColor
0x1802b5357  mov     edx, eax
0x1802b5359  mov     this, rsi
0x1802b535c  mov     rax, rbx
0x1802b535f  call    cs:__guard_dispatch_icall_fptr
0x1802b5365  mov     edx, 1; nBkMode
0x1802b536a  mov     this, rsi; this
0x1802b536d  call    ?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x1802b5372  xor     ebx, ebx
0x1802b5374  test    edi, edi
0x1802b5376  jz      loc_1802B54FB
0x1802b537c  mov     eax, dword ptr [rsp+160h+bmp.__vftable+4]
0x1802b5380  cdq
0x1802b5381  sub     eax, edx
0x1802b5383  sar     eax, 1
0x1802b5385  mov     edi, eax
0x1802b5387  mov     eax, [rbp+60h+rc.bottom]
0x1802b538a  mov     ecx, [rbp+60h+rc.top]
0x1802b538d  sub     eax, ecx
0x1802b538f  cdq
0x1802b5390  sub     eax, edx
0x1802b5392  sar     eax, 1
0x1802b5394  sub     eax, edi
0x1802b5396  lea     r8d, [this+1]
0x1802b539a  add     r8d, eax; y
0x1802b539d  mov     edx, [rbp+60h+rc.right]
0x1802b53a0  add     edx, 4; x
0x1802b53a3  mov     r9, [rsp+160h+strText.m_pszData]
0x1802b53a8  mov     r10d, [r9-10h]
0x1802b53ac  mov     [rsp+160h+lpDx], rbx; lpDx
0x1802b53b1  mov     [rsp+160h+clrBottomRight], r10d; c
0x1802b53b6  mov     qword ptr [rsp+160h+clrTopLeft], r9; lpString
0x1802b53bb  mov     qword ptr [rsp+160h+cy], rbx; lprect
0x1802b53c0  lea     r9d, [rbx+2]; options
0x1802b53c4  mov     this, [rsi+8]; hdc
0x1802b53c8  call    cs:__imp_ExtTextOutW
0x1802b53ce  mov     rax, [rsi]
0x1802b53d1  mov     rbx, [rax+70h]
0x1802b53d5  mov     ecx, 11h; nIndex
0x1802b53da  call    cs:__imp_GetSysColor
0x1802b53e0  mov     edx, eax
0x1802b53e2  mov     this, rsi
0x1802b53e5  mov     rax, rbx
0x1802b53e8  call    cs:__guard_dispatch_icall_fptr
0x1802b53ee  mov     eax, [rbp+60h+rc.bottom]
0x1802b53f1  sub     eax, [rbp+60h+rc.top]
0x1802b53f4  cdq
0x1802b53f5  sub     eax, edx
0x1802b53f7  sar     eax, 1
0x1802b53f9  mov     r8d, eax
0x1802b53fc  sub     r8d, edi
0x1802b53ff  mov     rax, [rsp+160h+strText.m_pszData]
0x1802b5404  mov     r9d, [rax-10h]
0x1802b5408  xor     ebx, ebx
0x1802b540a  mov     [rsp+160h+lpDx], rbx
0x1802b540f  mov     [rsp+160h+clrBottomRight], r9d
0x1802b5414  xor     r9d, r9d
0x1802b5417  jmp     loc_1802B54DD
0x1802b541c  xor     ebx, ebx
0x1802b541e  test    r13d, r13d
0x1802b5421  jz      short loc_1802B546F
0x1802b5423  test    byte ptr [r15+10h], 8
0x1802b5428  jz      short loc_1802B546F
0x1802b542a  lea     ecx, [rbx+14h]; nIndex
0x1802b542d  call    cs:__imp_GetSysColor
0x1802b5433  mov     ebx, eax
0x1802b5435  mov     ecx, 10h; nIndex
0x1802b543a  call    cs:__imp_GetSysColor
0x1802b5440  mov     ecx, [rbp+60h+rc.bottom]
0x1802b5443  mov     r8d, [rbp+60h+rc.top]; y
0x1802b5447  sub     ecx, r8d
0x1802b544a  inc     ecx
0x1802b544c  mov     r9d, [rbp+60h+rc.right]
0x1802b5450  mov     edx, [rbp+60h+rc.left]; x
0x1802b5453  sub     r9d, edx
0x1802b5456  inc     r9d; cx
0x1802b5459  mov     [rsp+160h+clrBottomRight], ebx; clrBottomRight
0x1802b545d  mov     [rsp+160h+clrTopLeft], eax; clrTopLeft
0x1802b5461  mov     [rsp+160h+cy], ecx; cy
0x1802b5465  mov     this, rsi; this
  ... truncated ...
```

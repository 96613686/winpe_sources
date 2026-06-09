# CCheckListBox::PreDrawItemNonThemed(CDC *,tagDRAWITEMSTRUCT &,int,int)

- ea: `0x1802a4580`
- end: `0x1802a483e`
- name: `?PreDrawItemNonThemed@CCheckListBox@@IEAAXPEAVCDC@@AEAUtagDRAWITEMSTRUCT@@HH@Z`
- size: `702`
- prototype: `void __fastcall(CCheckListBox *this, CDC *pDC, tagDRAWITEMSTRUCT *drawItem, int nCheck, int cyItem)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1802a4840`

## callees

- `0x18001d090`
- `0x180153990`
- `0x180231d70`
- `0x1802a3d40`
- `0x1802a40e0`
- `0x1802a4580`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b0b50`
- `0x1802b6760`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetSysColor` at `0x1802a46f0`
- `USER32!GetSysColor` at `0x1802a472c`
- `USER32!GetSysColor` at `0x1802a46f0`
- `USER32!GetSysColor` at `0x1802a472c`
- `USER32!FillRect` at `0x1802a474d`
- `USER32!FillRect` at `0x1802a474d`
- `USER32!CopyRect` at `0x1802a4661`
- `USER32!CopyRect` at `0x1802a46a9`
- `USER32!CopyRect` at `0x1802a4661`
- `USER32!CopyRect` at `0x1802a46a9`
- `GDI32!DeleteDC` at `0x1802a4811`
- `GDI32!DeleteDC` at `0x1802a4811`
- `GDI32!BitBlt` at `0x1802a47a4`
- `GDI32!BitBlt` at `0x1802a47a4`
- `GDI32!SelectObject` at `0x1802a4639`
- `GDI32!SelectObject` at `0x1802a47ce`
- `GDI32!SelectObject` at `0x1802a4639`
- `GDI32!SelectObject` at `0x1802a47ce`
- `GDI32!CreateCompatibleDC` at `0x1802a45f9`
- `GDI32!CreateCompatibleDC` at `0x1802a45f9`
- `GDI32!GetLayout` at `0x1802a4619`
- `GDI32!GetLayout` at `0x1802a4757`
- `GDI32!GetLayout` at `0x1802a4619`
- `GDI32!GetLayout` at `0x1802a4757`
- `GDI32!SetLayout` at `0x1802a462a`
- `GDI32!SetLayout` at `0x1802a4768`
- `GDI32!SetLayout` at `0x1802a47b0`
- `GDI32!SetLayout` at `0x1802a47bf`
- `GDI32!SetLayout` at `0x1802a462a`
- `GDI32!SetLayout` at `0x1802a4768`
- `GDI32!SetLayout` at `0x1802a47b0`
- `GDI32!SetLayout` at `0x1802a47bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CCheckListBox::PreDrawItemNonThemed(
        CCheckListBox *this,
        CDC *pDC,
        tagDRAWITEMSTRUCT *drawItem,
        int nCheck,
        int cyItem)
{
  _AFX_CHECKLIST_STATE *Data; // rbx
  HDC__ *m_hDC; // rcx
  HDC CompatibleDC; // rax
  CSize v12; // rbx
  tagRECT *p_rcItem; // r13
  int v14; // r8d
  int v15; // ecx
  CCheckListBox_vtbl *v16; // rax
  DWORD SysColor; // r12d
  BOOL v18; // ecx
  DWORD Layout; // edi
  HDC v20; // rax
  DWORD l; // [rsp+50h] [rbp-B0h]
  CDC bitmapDC; // [rsp+58h] [rbp-A8h] BYREF
  CSize sizeCheck; // [rsp+78h] [rbp-88h]
  HGDIOBJ h; // [rsp+80h] [rbp-80h]
  CBrush brush; // [rsp+88h] [rbp-78h] BYREF
  CRect v26; // [rsp+A0h] [rbp-60h] BYREF
  CRect v27; // [rsp+B0h] [rbp-50h] BYREF
  CRect rectCheck; // [rsp+C0h] [rbp-40h] BYREF
  CRect rectItem; // [rsp+D0h] [rbp-30h] BYREF
  CRect rectCheckBox; // [rsp+E0h] [rbp-20h] BYREF

  Data = (_AFX_CHECKLIST_STATE *)CProcessLocalObject::GetData(
                                   &_afxChecklistState,
                                   CProcessLocal<_AFX_CHECKLIST_STATE>::CreateObject);
  if ( !Data )
    AfxThrowInvalidArgException();
  bitmapDC.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&bitmapDC.m_hDC, 0, 20);
  if ( pDC )
    m_hDC = pDC->m_hDC;
  else
    m_hDC = 0;
  CompatibleDC = CreateCompatibleDC(m_hDC);
  if ( CDC::Attach(&bitmapDC, CompatibleDC) )
  {
    l = GetLayout(bitmapDC.m_hDC);
    SetLayout(bitmapDC.m_hDC, 0);
    h = SelectObject(bitmapDC.m_hDC, Data->m_hbitmapCheck);
    v12 = *_AFX_CHECKLIST_STATE::GetCheckBoxSize(Data, this);
    sizeCheck = v12;
    p_rcItem = &drawItem->rcItem;
    CopyRect(&rectCheck, &drawItem->rcItem);
    v14 = ++rectCheck.left;
    v15 = 0;
    if ( (cyItem - sizeCheck.cy) / 2 >= 0 )
      v15 = (cyItem - sizeCheck.cy) / 2;
    rectCheck.top += v15 + 1;
    rectCheck.right = v14 + v12.cx;
    rectCheck.bottom = rectCheck.top + sizeCheck.cy;
    CopyRect(&rectItem, &drawItem->rcItem);
    rectItem.right = v12.cx + rectItem.left + 2;
    v16 = this->__vftable;
    v26 = rectCheck;
    v27 = rectItem;
    ((void (__fastcall *)(CCheckListBox *, CRect *, CRect *, CRect *))v16->OnGetCheckPosition)(
      this,
      &rectCheckBox,
      &v27,
      &v26);
    SysColor = GetSysColor(5);
    v18 = !CWnd::IsWindowEnabled(this) || !CCheckListBox::IsEnabled(this, drawItem->itemID);
    if ( (drawItem->itemState & 1) != 0 && !v18 )
      SysColor = GetSysColor(13);
    CBrush::CBrush(&brush, SysColor);
    FillRect(pDC->m_hDC, &rectItem, (HBRUSH)brush.m_hObject);
    Layout = GetLayout(pDC->m_hDC);
    SetLayout(pDC->m_hDC, Layout | 8);
    BitBlt(
      pDC->m_hDC,
      rectCheckBox.left,
      rectCheckBox.top,
      v12.cx,
      sizeCheck.cy,
      bitmapDC.m_hDC,
      v12.cx * nCheck,
      0,
      0xCC0020u);
    SetLayout(pDC->m_hDC, Layout);
    SetLayout(bitmapDC.m_hDC, l);
    SelectObject(bitmapDC.m_hDC, h);
    p_rcItem->left += v12.cx + 3;
    brush.__vftable = (CBrush_vtbl *)CBrush::`vftable';
    CGdiObject::~CGdiObject(&brush);
  }
  bitmapDC.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( bitmapDC.m_hDC )
  {
    v20 = CDC::Detach(&bitmapDC);
    DeleteDC(v20);
  }
}

```

## disassembly

```asm
0x1802a4580  push    rbp
0x1802a4582  push    rbx
0x1802a4583  push    rsi
0x1802a4584  push    rdi
0x1802a4585  push    r12
0x1802a4587  push    r13
0x1802a4589  push    r14
0x1802a458b  push    r15
0x1802a458d  lea     rbp, [rsp-8]
0x1802a4592  sub     rsp, 108h
0x1802a4599  mov     rax, cs:__security_cookie
0x1802a45a0  xor     rax, rsp
0x1802a45a3  mov     [rbp+40h+var_50], rax
0x1802a45a7  mov     r15d, nCheck
0x1802a45aa  mov     rdi, drawItem
0x1802a45ad  mov     rsi, pDC
0x1802a45b0  mov     r14, this
0x1802a45b3  lea     pDC, ?CreateObject@?$CProcessLocal@V_AFX_CHECKLIST_STATE@@@@SAPEAVCNoTrackObject@@XZ; pfnCreateObject
0x1802a45ba  lea     this, ?_afxChecklistState@@3V?$CProcessLocal@V_AFX_CHECKLIST_STATE@@@@A; this
0x1802a45c1  call    ?GetData@CProcessLocalObject@@QEAAPEAVCNoTrackObject@@P6APEAV2@XZ@Z; CProcessLocalObject::GetData(CNoTrackObject * (*)(void))
0x1802a45c6  mov     rbx, rax
0x1802a45c9  test    rax, rax
0x1802a45cc  jz      loc_1802A4838
0x1802a45d2  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1802a45d9  mov     [rsp+140h+bitmapDC.__vftable], rax
0x1802a45de  xorps   xmm0, xmm0
0x1802a45e1  movdqu  xmmword ptr [rsp+140h+bitmapDC.m_hDC], xmm0
0x1802a45e7  and     [rsp+140h+bitmapDC.m_bPrinting], 0
0x1802a45ec  test    rsi, rsi
0x1802a45ef  jnz     short loc_1802A45F5
0x1802a45f1  xor     ecx, ecx
0x1802a45f3  jmp     short loc_1802A45F9
0x1802a45f5  mov     this, [rsi+8]; hdc
0x1802a45f9  call    cs:__imp_CreateCompatibleDC
0x1802a45ff  mov     pDC, rax; hDC
0x1802a4602  lea     this, [rsp+140h+bitmapDC]; this
0x1802a4607  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802a460c  test    eax, eax
0x1802a460e  jz      loc_1802A47F0
0x1802a4614  mov     this, [rsp+140h+bitmapDC.m_hDC]; hdc
0x1802a4619  call    cs:__imp_GetLayout
0x1802a461f  mov     [rsp+140h+l], eax
0x1802a4623  xor     edx, edx; l
0x1802a4625  mov     this, [rsp+140h+bitmapDC.m_hDC]; hdc
0x1802a462a  call    cs:__imp_SetLayout
0x1802a4630  mov     pDC, [rbx+8]; h
0x1802a4634  mov     this, [rsp+140h+bitmapDC.m_hDC]; hdc
0x1802a4639  call    cs:__imp_SelectObject
0x1802a463f  mov     [rbp+40h+h], rax
0x1802a4643  mov     pDC, r14; pWndCheckList
0x1802a4646  mov     this, rbx; this
0x1802a4649  call    ?GetCheckBoxSize@_AFX_CHECKLIST_STATE@@QEAAAEBVCSize@@PEAVCWnd@@@Z; _AFX_CHECKLIST_STATE::GetCheckBoxSize(CWnd *)
0x1802a464e  mov     rbx, [rax]
0x1802a4651  mov     qword ptr [rsp+140h+sizeCheck.cx], rbx
0x1802a4656  lea     r13, [rdi+28h]
0x1802a465a  mov     pDC, r13; lprcSrc
0x1802a465d  lea     this, [rbp+40h+rectCheck]; lprcDst
0x1802a4661  call    cs:__imp_CopyRect
0x1802a4667  mov     r8d, [rbp+40h+rectCheck.left]
0x1802a466b  inc     r8d
0x1802a466e  mov     [rbp+40h+rectCheck.left], r8d
0x1802a4672  mov     eax, [rbp+40h+arg_20]
0x1802a4675  mov     nCheck, [rsp+140h+sizeCheck.cy]
0x1802a467a  sub     eax, nCheck
0x1802a467d  cdq
0x1802a467e  sub     eax, edx
0x1802a4680  sar     eax, 1
0x1802a4682  mov     ecx, 0
0x1802a4687  cmovns  ecx, eax
0x1802a468a  mov     edx, [rbp+40h+rectCheck.top]
0x1802a468d  inc     edx
0x1802a468f  add     edx, ecx
0x1802a4691  mov     [rbp+40h+rectCheck.top], edx
0x1802a4694  lea     eax, [drawItem+rbx]
0x1802a4698  mov     [rbp+40h+rectCheck.right], eax
0x1802a469b  lea     eax, [pDC+r9]
0x1802a469f  mov     [rbp+40h+rectCheck.bottom], eax
0x1802a46a2  mov     pDC, r13; lprcSrc
0x1802a46a5  lea     this, [rbp+40h+rectItem]; lprcDst
0x1802a46a9  call    cs:__imp_CopyRect
0x1802a46af  mov     ecx, [rbp+40h+rectItem.left]
0x1802a46b2  add     ecx, 2
0x1802a46b5  add     ecx, ebx
0x1802a46b7  mov     [rbp+40h+rectItem.right], ecx
0x1802a46ba  mov     rax, [r14]
0x1802a46bd  movaps  xmm0, xmmword ptr [rbp+40h+rectCheck.left]
0x1802a46c1  movdqa  [rbp+40h+var_A0], xmm0
0x1802a46c6  movaps  xmm1, xmmword ptr [rbp+40h+rectItem.left]
0x1802a46ca  movdqa  [rbp+40h+var_90], xmm1
0x1802a46cf  lea     r9, [rbp+40h+var_A0]
0x1802a46d3  lea     drawItem, [rbp+40h+var_90]
0x1802a46d7  lea     pDC, [rbp+40h+rectCheckBox]
0x1802a46db  mov     this, r14
0x1802a46de  mov     rax, [rax+310h]
0x1802a46e5  call    cs:__guard_dispatch_icall_fptr
0x1802a46eb  mov     ecx, 5; nIndex
0x1802a46f0  call    cs:__imp_GetSysColor
0x1802a46f6  mov     r12d, eax
0x1802a46f9  mov     this, r14; this
0x1802a46fc  call    ?IsWindowEnabled@CWnd@@QEBAHXZ; CWnd::IsWindowEnabled(void)
0x1802a4701  test    eax, eax
0x1802a4703  jz      short loc_1802A4718
0x1802a4705  mov     edx, [rdi+8]; nIndex
0x1802a4708  mov     this, r14; this
0x1802a470b  call    ?IsEnabled@CCheckListBox@@QEAAHH@Z; CCheckListBox::IsEnabled(int)
0x1802a4710  test    eax, eax
0x1802a4712  jz      short loc_1802A4718
0x1802a4714  xor     ecx, ecx
0x1802a4716  jmp     short loc_1802A471D
0x1802a4718  mov     ecx, 1
0x1802a471d  test    byte ptr [rdi+10h], 1
0x1802a4721  jz      short loc_1802A4735
0x1802a4723  test    ecx, ecx
0x1802a4725  jnz     short loc_1802A4735
0x1802a4727  mov     ecx, 0Dh; nIndex
0x1802a472c  call    cs:__imp_GetSysColor
0x1802a4732  mov     r12d, eax
0x1802a4735  mov     edx, r12d; crColor
0x1802a4738  lea     this, [rbp+40h+brush]; this
0x1802a473c  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x1802a4741  mov     drawItem, [rbp+40h+brush.m_hObject]; hbr
0x1802a4745  lea     pDC, [rbp+40h+rectItem]; lprc
0x1802a4749  mov     this, [rsi+8]; hDC
0x1802a474d  call    cs:__imp_FillRect
0x1802a4753  mov     this, [rsi+8]; hdc
0x1802a4757  call    cs:__imp_GetLayout
0x1802a475d  mov     edi, eax
0x1802a475f  mov     edx, eax
0x1802a4761  or      edx, 8; l
0x1802a4764  mov     this, [rsi+8]; hdc
0x1802a4768  call    cs:__imp_SetLayout
0x1802a476e  imul    r15d, ebx
0x1802a4772  mov     [rsp+140h+rop], 0CC0020h; rop
0x1802a477a  and     [rsp+140h+var_108], 0
0x1802a477f  mov     [rsp+140h+x1], r15d; x1
0x1802a4784  mov     pDC, [rsp+140h+bitmapDC.m_hDC]
0x1802a4789  mov     [rsp+140h+hdcSrc], pDC; hdcSrc
0x1802a478e  mov     eax, [rsp+140h+sizeCheck.cy]
0x1802a4792  mov     [rsp+140h+cy], eax; cy
0x1802a4796  mov     nCheck, ebx; cx
0x1802a4799  mov     r8d, [rbp+40h+rectCheckBox.top]; y
0x1802a479d  mov     edx, [rbp+40h+rectCheckBox.left]; x
0x1802a47a0  mov     this, [rsi+8]; hdc
0x1802a47a4  call    cs:__imp_BitBlt
0x1802a47aa  mov     edx, edi; l
0x1802a47ac  mov     this, [rsi+8]; hdc
0x1802a47b0  call    cs:__imp_SetLayout
0x1802a47b6  mov     edx, [rsp+140h+l]; l
0x1802a47ba  mov     this, [rsp+140h+bitmapDC.m_hDC]; hdc
0x1802a47bf  call    cs:__imp_SetLayout
0x1802a47c5  mov     pDC, [rbp+40h+h]; h
0x1802a47c9  mov     this, [rsp+140h+bitmapDC.m_hDC]; hdc
0x1802a47ce  call    cs:__imp_SelectObject
0x1802a47d4  add     ebx, 3
0x1802a47d7  add     [r13+0], ebx
0x1802a47db  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x1802a47e2  mov     [rbp+40h+brush.__vftable], rax
0x1802a47e6  lea     this, [rbp+40h+brush]; this
0x1802a47ea  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802a47ef  nop
0x1802a47f0  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1802a47f7  mov     [rsp+140h+bitmapDC.__vftable], rax
0x1802a47fc  cmp     [rsp+140h+bitmapDC.m_hDC], 0
0x1802a4802  jz      short loc_1802A4818
0x1802a4804  lea     this, [rsp+140h+bitmapDC]; this
0x1802a4809  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1802a480e  mov     this, rax; hdc
0x1802a4811  call    cs:__imp_DeleteDC
0x1802a4817  nop
0x1802a4818  mov     this, [rbp+40h+var_50]
0x1802a481c  xor     this, rsp; StackCookie
0x1802a481f  call    __security_check_cookie
0x1802a4824  add     rsp, 108h
0x1802a482b  pop     r15
0x1802a482d  pop     r14
0x1802a482f  pop     r13
0x1802a4831  pop     r12
0x1802a4833  pop     rdi
0x1802a4834  pop     rsi
0x1802a4835  pop     rbx
0x1802a4836  pop     rbp
0x1802a4837  retn
0x1802a4838  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```

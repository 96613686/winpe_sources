# CDC::DrawDragRect(tagRECT const *,tagSIZE,tagRECT const *,tagSIZE,CBrush *,CBrush *)

- ea: `0x1802b2210`
- end: `0x1802b2580`
- name: `?DrawDragRect@CDC@@QEAAXPEBUtagRECT@@UtagSIZE@@01PEAVCBrush@@2@Z`
- size: `880`
- prototype: `void __fastcall(CDC *this, const tagRECT *lpRect, tagSIZE size, const tagRECT *lpRectLast, tagSIZE sizeLast, CBrush *pBrush, CBrush *pBrushLast)`
- caller_count: `8`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180042560`
- `0x180057b20`
- `0x180083130`
- `0x18009c0d0`
- `0x180143020`
- `0x1801576b0`
- `0x180229bb0`
- `0x180282230`

## callees

- `0x18001d090`
- `0x180231d70`
- `0x1802af110`
- `0x1802af8a0`
- `0x1802b09d0`
- `0x1802b2130`
- `0x1802b2210`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!IntersectRect` at `0x1802b22b1`
- `USER32!IntersectRect` at `0x1802b23ad`
- `USER32!IntersectRect` at `0x1802b22b1`
- `USER32!IntersectRect` at `0x1802b23ad`
- `USER32!CopyRect` at `0x1802b228b`
- `USER32!CopyRect` at `0x1802b2386`
- `USER32!CopyRect` at `0x1802b228b`
- `USER32!CopyRect` at `0x1802b2386`
- `USER32!InflateRect` at `0x1802b22a0`
- `USER32!InflateRect` at `0x1802b239c`
- `USER32!InflateRect` at `0x1802b22a0`
- `USER32!InflateRect` at `0x1802b239c`
- `GDI32!SetRectRgn` at `0x1802b2379`
- `GDI32!SetRectRgn` at `0x1802b23c9`
- `GDI32!SetRectRgn` at `0x1802b2379`
- `GDI32!SetRectRgn` at `0x1802b23c9`
- `GDI32!CombineRgn` at `0x1802b22fd`
- `GDI32!CombineRgn` at `0x1802b23de`
- `GDI32!CombineRgn` at `0x1802b2419`
- `GDI32!CombineRgn` at `0x1802b22fd`
- `GDI32!CombineRgn` at `0x1802b23de`
- `GDI32!CombineRgn` at `0x1802b2419`
- `GDI32!CreateRectRgn` at `0x1802b22d7`
- `GDI32!CreateRectRgn` at `0x1802b234c`
- `GDI32!CreateRectRgn` at `0x1802b23f8`
- `GDI32!CreateRectRgn` at `0x1802b22d7`
- `GDI32!CreateRectRgn` at `0x1802b234c`
- `GDI32!CreateRectRgn` at `0x1802b23f8`
- `GDI32!PatBlt` at `0x1802b2483`
- `GDI32!PatBlt` at `0x1802b24f6`
- `GDI32!PatBlt` at `0x1802b2483`
- `GDI32!PatBlt` at `0x1802b24f6`
- `GDI32!CreateRectRgnIndirect` at `0x1802b2272`
- `GDI32!CreateRectRgnIndirect` at `0x1802b22bb`
- `GDI32!CreateRectRgnIndirect` at `0x1802b2272`
- `GDI32!CreateRectRgnIndirect` at `0x1802b22bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CDC::DrawDragRect(
        CDC *this,
        const tagRECT *lpRect,
        tagSIZE size,
        const tagRECT *lpRectLast,
        tagSIZE sizeLast,
        CFont *pBrush,
        CFont *pBrushLast)
{
  int cx; // ebx
  CBrush *HalftoneBrush; // r14
  CFont *v12; // r15
  HRGN RectRgnIndirect; // rax
  HRGN v14; // rax
  HRGN RectRgn; // rax
  HRGN v16; // rax
  HRGN v17; // rax
  CFont *v18; // rbx
  CRgn *p_rgnUpdate; // rdx
  CFont *v20; // rbx
  CRgn rgnUpdate; // [rsp+30h] [rbp-61h] BYREF
  CRgn rgnLast; // [rsp+40h] [rbp-51h] BYREF
  CRgn rgnInside; // [rsp+50h] [rbp-41h] BYREF
  CRgn rgnOutside; // [rsp+60h] [rbp-31h] BYREF
  CRgn rgnNew; // [rsp+70h] [rbp-21h] BYREF
  tagSIZE v26; // [rsp+80h] [rbp-11h]
  CRect rect; // [rsp+88h] [rbp-9h] BYREF

  cx = size.cx;
  v26 = size;
  HalftoneBrush = (CBrush *)pBrush;
  v12 = pBrushLast;
  rgnNew.m_hObject = 0;
  rgnNew.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  rgnOutside.m_hObject = 0;
  rgnOutside.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  rgnInside.m_hObject = 0;
  rgnInside.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  RectRgnIndirect = CreateRectRgnIndirect(lpRect);
  CGdiObject::Attach(&rgnOutside, RectRgnIndirect);
  CopyRect(&rect, lpRect);
  InflateRect(&rect, -cx, -v26.cy);
  IntersectRect(&rect, &rect, lpRect);
  v14 = CreateRectRgnIndirect(&rect);
  CGdiObject::Attach(&rgnInside, v14);
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  CGdiObject::Attach(&rgnNew, RectRgn);
  CombineRgn((HRGN)rgnNew.m_hObject, (HRGN)rgnOutside.m_hObject, (HRGN)rgnInside.m_hObject, 3);
  if ( !pBrush )
  {
    HalftoneBrush = CDC::GetHalftoneBrush();
    if ( !HalftoneBrush )
      AfxThrowInvalidArgException();
  }
  if ( !pBrushLast )
    v12 = (CFont *)HalftoneBrush;
  rgnLast.m_hObject = 0;
  rgnLast.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  rgnUpdate.m_hObject = 0;
  rgnUpdate.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  if ( lpRectLast )
  {
    v16 = CreateRectRgn(0, 0, 0, 0);
    CGdiObject::Attach(&rgnLast, v16);
    SetRectRgn((HRGN)rgnOutside.m_hObject, lpRectLast->left, lpRectLast->top, lpRectLast->right, lpRectLast->bottom);
    CopyRect(&rect, lpRectLast);
    InflateRect(&rect, -sizeLast.cx, -sizeLast.cy);
    IntersectRect(&rect, &rect, lpRectLast);
    SetRectRgn((HRGN)rgnInside.m_hObject, rect.left, rect.top, rect.right, rect.bottom);
    CombineRgn((HRGN)rgnLast.m_hObject, (HRGN)rgnOutside.m_hObject, (HRGN)rgnInside.m_hObject, 3);
    if ( HalftoneBrush->m_hObject == v12->m_hObject )
    {
      v17 = CreateRectRgn(0, 0, 0, 0);
      CGdiObject::Attach(&rgnUpdate, v17);
      CombineRgn((HRGN)rgnUpdate.m_hObject, (HRGN)rgnLast.m_hObject, (HRGN)rgnNew.m_hObject, 3);
    }
  }
  if ( HalftoneBrush->m_hObject != v12->m_hObject && lpRectLast )
  {
    CDC::SelectClipRgn(this, &rgnLast);
    this->GetClipBox(this, &rect);
    v18 = CDC::SelectObject(this, v12);
    PatBlt(this->m_hDC, rect.left, rect.top, rect.right - rect.left, rect.bottom - rect.top, 0x5A0049u);
    CDC::SelectObject(this, v18);
  }
  p_rgnUpdate = &rgnUpdate;
  if ( !rgnUpdate.m_hObject )
    p_rgnUpdate = &rgnNew;
  CDC::SelectClipRgn(this, p_rgnUpdate);
  this->GetClipBox(this, &rect);
  v20 = CDC::SelectObject(this, (CFont *)HalftoneBrush);
  PatBlt(this->m_hDC, rect.left, rect.top, rect.right - rect.left, rect.bottom - rect.top, 0x5A0049u);
  if ( v20 )
    CDC::SelectObject(this, v20);
  CDC::SelectClipRgn(this, 0);
  rgnUpdate.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  CGdiObject::~CGdiObject(&rgnUpdate);
  rgnLast.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  CGdiObject::~CGdiObject(&rgnLast);
  rgnInside.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  CGdiObject::~CGdiObject(&rgnInside);
  rgnOutside.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  CGdiObject::~CGdiObject(&rgnOutside);
  rgnNew.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  CGdiObject::~CGdiObject(&rgnNew);
}

```

## disassembly

```asm
0x1802b2210  push    rbp
0x1802b2212  push    rbx
0x1802b2213  push    rsi
0x1802b2214  push    rdi
0x1802b2215  push    r12
0x1802b2217  push    r14
0x1802b2219  push    r15
0x1802b221b  lea     rbp, [rsp-0Fh]
0x1802b2220  sub     rsp, 0A0h
0x1802b2227  mov     rax, cs:__security_cookie
0x1802b222e  xor     rax, rsp
0x1802b2231  mov     [rbp+3Fh+var_38], rax
0x1802b2235  mov     r12, lpRectLast
0x1802b2238  mov     rbx, size
0x1802b223b  mov     rdi, lpRect
0x1802b223e  mov     rsi, this
0x1802b2241  mov     [rbp+3Fh+var_50], rbx
0x1802b2245  mov     r14, [rbp+3Fh+pFont]
0x1802b2249  mov     r15, [rbp+3Fh+arg_30]
0x1802b224d  and     [rbp+3Fh+rgnNew.m_hObject], 0
0x1802b2252  lea     rax, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1802b2259  mov     [rbp+3Fh+rgnNew.__vftable], rax
0x1802b225d  and     [rbp+3Fh+rgnOutside.m_hObject], 0
0x1802b2262  mov     [rbp+3Fh+rgnOutside.__vftable], rax
0x1802b2266  and     [rbp+3Fh+rgnInside.m_hObject], 0
0x1802b226b  mov     [rbp+3Fh+rgnInside.__vftable], rax
0x1802b226f  mov     this, lpRect; lprect
0x1802b2272  call    cs:__imp_CreateRectRgnIndirect
0x1802b2278  mov     lpRect, rax; hObject
0x1802b227b  lea     this, [rbp+3Fh+rgnOutside]; this
0x1802b227f  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b2284  mov     lpRect, rdi; lprcSrc
0x1802b2287  lea     this, [rbp+3Fh+rect]; lprcDst
0x1802b228b  call    cs:__imp_CopyRect
0x1802b2291  mov     r8d, dword ptr [rbp+3Fh+var_50+4]
0x1802b2295  neg     r8d; dy
0x1802b2298  neg     ebx
0x1802b229a  mov     edx, ebx; dx
0x1802b229c  lea     this, [rbp+3Fh+rect]; lprc
0x1802b22a0  call    cs:__imp_InflateRect
0x1802b22a6  mov     size, rdi; lprcSrc2
0x1802b22a9  lea     lpRect, [rbp+3Fh+rect]; lprcSrc1
0x1802b22ad  lea     this, [rbp+3Fh+rect]; lprcDst
0x1802b22b1  call    cs:__imp_IntersectRect
0x1802b22b7  lea     this, [rbp+3Fh+rect]; lprect
0x1802b22bb  call    cs:__imp_CreateRectRgnIndirect
0x1802b22c1  mov     lpRect, rax; hObject
0x1802b22c4  lea     this, [rbp+3Fh+rgnInside]; this
0x1802b22c8  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b22cd  xor     r9d, r9d; y2
0x1802b22d0  xor     r8d, r8d; x2
0x1802b22d3  xor     edx, edx; y1
0x1802b22d5  xor     ecx, ecx; x1
0x1802b22d7  call    cs:__imp_CreateRectRgn
0x1802b22dd  mov     lpRect, rax; hObject
0x1802b22e0  lea     this, [rbp+3Fh+rgnNew]; this
0x1802b22e4  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b22e9  mov     ebx, 3
0x1802b22ee  mov     r9d, ebx; iMode
0x1802b22f1  mov     size, [rbp+3Fh+rgnInside.m_hObject]; hrgnSrc2
0x1802b22f5  mov     lpRect, [rbp+3Fh+rgnOutside.m_hObject]; hrgnSrc1
0x1802b22f9  mov     this, [rbp+3Fh+rgnNew.m_hObject]; hrgnDst
0x1802b22fd  call    cs:__imp_CombineRgn
0x1802b2303  test    r14, r14
0x1802b2306  jnz     short loc_1802B2319
0x1802b2308  call    ?GetHalftoneBrush@CDC@@SAPEAVCBrush@@XZ; CDC::GetHalftoneBrush(void)
0x1802b230d  mov     r14, rax
0x1802b2310  test    rax, rax
0x1802b2313  jz      loc_1802B257A
0x1802b2319  test    r15, r15
0x1802b231c  cmovz   r15, r14
0x1802b2320  and     [rbp+3Fh+rgnLast.m_hObject], 0
0x1802b2325  lea     rdi, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1802b232c  mov     [rbp+3Fh+rgnLast.__vftable], rdi
0x1802b2330  and     [rbp+3Fh+rgnUpdate.m_hObject], 0
0x1802b2335  mov     [rbp+3Fh+rgnUpdate.__vftable], rdi
0x1802b2339  test    r12, r12
0x1802b233c  jz      loc_1802B241F
0x1802b2342  xor     r9d, r9d; y2
0x1802b2345  xor     r8d, r8d; x2
0x1802b2348  xor     edx, edx; y1
0x1802b234a  xor     ecx, ecx; x1
0x1802b234c  call    cs:__imp_CreateRectRgn
0x1802b2352  mov     lpRect, rax; hObject
0x1802b2355  lea     this, [rbp+3Fh+rgnLast]; this
0x1802b2359  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b235e  mov     eax, [r12+0Ch]
0x1802b2363  mov     [rsp+0D0h+bottom], eax; bottom
0x1802b2367  mov     r9d, [r12+8]; right
0x1802b236c  mov     r8d, [r12+4]; top
0x1802b2371  mov     edx, [r12]; left
0x1802b2375  mov     this, [rbp+3Fh+rgnOutside.m_hObject]; hrgn
0x1802b2379  call    cs:__imp_SetRectRgn
0x1802b237f  mov     lpRect, r12; lprcSrc
0x1802b2382  lea     this, [rbp+3Fh+rect]; lprcDst
0x1802b2386  call    cs:__imp_CopyRect
0x1802b238c  mov     r8d, [rbp+3Fh+arg_24]
0x1802b2390  neg     r8d; dy
0x1802b2393  mov     edx, [rbp+3Fh+arg_20]
0x1802b2396  neg     edx; dx
0x1802b2398  lea     this, [rbp+3Fh+rect]; lprc
0x1802b239c  call    cs:__imp_InflateRect
0x1802b23a2  mov     size, r12; lprcSrc2
0x1802b23a5  lea     lpRect, [rbp+3Fh+rect]; lprcSrc1
0x1802b23a9  lea     this, [rbp+3Fh+rect]; lprcDst
0x1802b23ad  call    cs:__imp_IntersectRect
0x1802b23b3  mov     eax, [rbp+3Fh+rect.bottom]
0x1802b23b6  mov     [rsp+0D0h+bottom], eax; bottom
0x1802b23ba  mov     r9d, [rbp+3Fh+rect.right]; right
0x1802b23be  mov     r8d, [rbp+3Fh+rect.top]; top
0x1802b23c2  mov     edx, [rbp+3Fh+rect.left]; left
0x1802b23c5  mov     this, [rbp+3Fh+rgnInside.m_hObject]; hrgn
0x1802b23c9  call    cs:__imp_SetRectRgn
0x1802b23cf  mov     r9d, ebx; iMode
0x1802b23d2  mov     size, [rbp+3Fh+rgnInside.m_hObject]; hrgnSrc2
0x1802b23d6  mov     lpRect, [rbp+3Fh+rgnOutside.m_hObject]; hrgnSrc1
0x1802b23da  mov     this, [rbp+3Fh+rgnLast.m_hObject]; hrgnDst
0x1802b23de  call    cs:__imp_CombineRgn
0x1802b23e4  mov     rax, [r15+8]
0x1802b23e8  cmp     [r14+8], rax
0x1802b23ec  jnz     short loc_1802B241F
0x1802b23ee  xor     r9d, r9d; y2
0x1802b23f1  xor     r8d, r8d; x2
0x1802b23f4  xor     edx, edx; y1
0x1802b23f6  xor     ecx, ecx; x1
0x1802b23f8  call    cs:__imp_CreateRectRgn
0x1802b23fe  mov     lpRect, rax; hObject
0x1802b2401  lea     this, [rbp+3Fh+rgnUpdate]; this
0x1802b2405  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b240a  mov     r9d, ebx; iMode
0x1802b240d  mov     size, [rbp+3Fh+rgnNew.m_hObject]; hrgnSrc2
0x1802b2411  mov     lpRect, [rbp+3Fh+rgnLast.m_hObject]; hrgnSrc1
0x1802b2415  mov     this, [rbp+3Fh+rgnUpdate.m_hObject]; hrgnDst
0x1802b2419  call    cs:__imp_CombineRgn
0x1802b241f  mov     rax, [r15+8]
0x1802b2423  cmp     [r14+8], rax
0x1802b2427  jz      short loc_1802B2494
0x1802b2429  test    r12, r12
0x1802b242c  jz      short loc_1802B2494
0x1802b242e  lea     lpRect, [rbp+3Fh+rgnLast]; pRgn
0x1802b2432  mov     this, rsi; this
0x1802b2435  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1802b243a  mov     rax, [rsi]
0x1802b243d  lea     lpRect, [rbp+3Fh+rect]
0x1802b2441  mov     this, rsi
0x1802b2444  mov     rax, [rax+0B0h]
0x1802b244b  call    cs:__guard_dispatch_icall_fptr
0x1802b2451  mov     lpRect, r15; pFont
0x1802b2454  mov     this, rsi; this
0x1802b2457  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1802b245c  mov     rbx, rax
0x1802b245f  mov     ecx, [rbp+3Fh+rect.bottom]
0x1802b2462  mov     r8d, [rbp+3Fh+rect.top]; y
0x1802b2466  sub     ecx, r8d
0x1802b2469  mov     r9d, [rbp+3Fh+rect.right]
0x1802b246d  mov     edx, [rbp+3Fh+rect.left]; x
0x1802b2470  sub     r9d, edx; w
0x1802b2473  mov     [rsp+0D0h+rop], 5A0049h; rop
0x1802b247b  mov     [rsp+0D0h+bottom], ecx; h
0x1802b247f  mov     this, [rsi+8]; hdc
0x1802b2483  call    cs:__imp_PatBlt
0x1802b2489  mov     lpRect, rbx; pFont
0x1802b248c  mov     this, rsi; this
0x1802b248f  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1802b2494  lea     lpRect, [rbp+3Fh+rgnUpdate]
0x1802b2498  lea     rax, [rbp+3Fh+rgnNew]
0x1802b249c  cmp     [rbp+3Fh+rgnUpdate.m_hObject], 0
0x1802b24a1  cmovz   lpRect, rax; pRgn
0x1802b24a5  mov     this, rsi; this
0x1802b24a8  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1802b24ad  mov     rax, [rsi]
0x1802b24b0  lea     lpRect, [rbp+3Fh+rect]
0x1802b24b4  mov     this, rsi
0x1802b24b7  mov     rax, [rax+0B0h]
0x1802b24be  call    cs:__guard_dispatch_icall_fptr
0x1802b24c4  mov     lpRect, r14; pFont
0x1802b24c7  mov     this, rsi; this
0x1802b24ca  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1802b24cf  mov     rbx, rax
0x1802b24d2  mov     ecx, [rbp+3Fh+rect.bottom]
0x1802b24d5  mov     r8d, [rbp+3Fh+rect.top]; y
0x1802b24d9  sub     ecx, r8d
0x1802b24dc  mov     r9d, [rbp+3Fh+rect.right]
0x1802b24e0  mov     edx, [rbp+3Fh+rect.left]; x
0x1802b24e3  sub     r9d, edx; w
0x1802b24e6  mov     [rsp+0D0h+rop], 5A0049h; rop
0x1802b24ee  mov     [rsp+0D0h+bottom], ecx; h
0x1802b24f2  mov     this, [rsi+8]; hdc
0x1802b24f6  call    cs:__imp_PatBlt
0x1802b24fc  test    rbx, rbx
0x1802b24ff  jz      short loc_1802B250C
0x1802b2501  mov     lpRect, rbx; pFont
0x1802b2504  mov     this, rsi; this
0x1802b2507  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1802b250c  xor     edx, edx; pRgn
0x1802b250e  mov     this, rsi; this
0x1802b2511  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1802b2516  nop
0x1802b2517  mov     [rbp+3Fh+rgnUpdate.__vftable], rdi
0x1802b251b  lea     this, [rbp+3Fh+rgnUpdate]; this
0x1802b251f  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b2524  nop
0x1802b2525  mov     [rbp+3Fh+rgnLast.__vftable], rdi
0x1802b2529  lea     this, [rbp+3Fh+rgnLast]; this
0x1802b252d  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b2532  nop
0x1802b2533  mov     [rbp+3Fh+rgnInside.__vftable], rdi
0x1802b2537  lea     this, [rbp+3Fh+rgnInside]; this
0x1802b253b  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b2540  nop
0x1802b2541  mov     [rbp+3Fh+rgnOutside.__vftable], rdi
0x1802b2545  lea     this, [rbp+3Fh+rgnOutside]; this
0x1802b2549  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b254e  nop
0x1802b254f  mov     [rbp+3Fh+rgnNew.__vftable], rdi
0x1802b2553  lea     this, [rbp+3Fh+rgnNew]; this
0x1802b2557  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b255c  mov     this, [rbp+3Fh+var_38]
0x1802b2560  xor     this, rsp; StackCookie
0x1802b2563  call    __security_check_cookie
0x1802b2568  add     rsp, 0A0h
0x1802b256f  pop     r15
0x1802b2571  pop     r14
0x1802b2573  pop     r12
0x1802b2575  pop     rdi
0x1802b2576  pop     rsi
0x1802b2577  pop     rbx
0x1802b2578  pop     rbp
0x1802b2579  retn
0x1802b257a  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```

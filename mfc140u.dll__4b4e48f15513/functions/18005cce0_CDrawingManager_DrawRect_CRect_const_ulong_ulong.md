# CDrawingManager::DrawRect(CRect const &,ulong,ulong)

- ea: `0x18005cce0`
- end: `0x18005d0df`
- name: `?DrawRect@CDrawingManager@@QEAAXAEBVCRect@@KK@Z`
- size: `1023`
- prototype: `void __fastcall(CDrawingManager *this, const CRect *rect, unsigned int clrFill, unsigned int clrLine)`
- caller_count: `23`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800f8920`
- `0x180138510`
- `0x18018f260`
- `0x180191a10`
- `0x180191ce0`
- `0x180194a80`
- `0x180194dc0`
- `0x180194f40`
- `0x180195c70`
- `0x180195d50`
- `0x180195f10`
- `0x1801960c0`
- `0x18019b3e0`
- `0x1801ad3c0`
- `0x1801ad710`
- `0x1801ad810`
- `0x1801b31c0`
- `0x1801b9440`
- `0x1801bab00`
- `0x1801bae50`
- `0x1801bb630`
- `0x1801bbc00`
- `0x1801cb120`

## callees

- `0x18001d090`
- `0x180058150`
- `0x18005cce0`
- `0x18005dd50`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802aef40`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18005cefc`
- `VCRUNTIME140!memcpy` at `0x18005cfb1`
- `VCRUNTIME140!memcpy` at `0x18005cefc`
- `VCRUNTIME140!memcpy` at `0x18005cfb1`
- `GDI32!DeleteDC` at `0x18005d0ab`
- `GDI32!DeleteDC` at `0x18005d0ab`
- `GDI32!BitBlt` at `0x18005d004`
- `GDI32!BitBlt` at `0x18005d004`
- `GDI32!CreateCompatibleBitmap` at `0x18005cde1`
- `GDI32!CreateCompatibleBitmap` at `0x18005cde1`
- `GDI32!DeleteObject` at `0x18005d059`
- `GDI32!DeleteObject` at `0x18005d059`
- `GDI32!SelectObject` at `0x18005ce19`
- `GDI32!SelectObject` at `0x18005ce62`
- `GDI32!SelectObject` at `0x18005d047`
- `GDI32!SelectObject` at `0x18005ce19`
- `GDI32!SelectObject` at `0x18005ce62`
- `GDI32!SelectObject` at `0x18005d047`
- `GDI32!CreateCompatibleDC` at `0x18005cdaa`
- `GDI32!CreateCompatibleDC` at `0x18005cdaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CDrawingManager::DrawRect(
        CDrawingManager *this,
        const CRect *rect,
        unsigned int clrFill,
        unsigned int clrLine)
{
  int v5; // r13d
  int right; // ebx
  int v7; // eax
  int top; // r15d
  int bottom; // edi
  int v10; // eax
  int v11; // edi
  int v12; // ebx
  CDC *m_dc; // rax
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v17; // rax
  HBITMAP__ *v18; // rax
  unsigned int *v19; // rbx
  int v20; // edx
  int cx; // esi
  __int64 v22; // r12
  int v23; // r8d
  int cy; // r14d
  unsigned int v25; // r9d
  unsigned int v26; // esi
  unsigned __int64 v27; // rcx
  unsigned int *v28; // rdi
  unsigned int v29; // r10d
  unsigned int v30; // edi
  __int64 v31; // r12
  unsigned __int64 v32; // rcx
  unsigned int v33; // eax
  unsigned int *v34; // rdi
  __int64 v35; // rdi
  __int64 v36; // r14
  CDrawingManager *v37; // rdi
  CDC *v38; // rcx
  HGDIOBJ v39; // rax
  HDC v40; // rax
  CSize size; // [rsp+50h] [rbp-59h] BYREF
  unsigned int v42; // [rsp+58h] [rbp-51h]
  unsigned int v43; // [rsp+5Ch] [rbp-4Dh]
  CBitmap bmpMem; // [rsp+60h] [rbp-49h] BYREF
  CDC dcMem; // [rsp+70h] [rbp-39h] BYREF
  unsigned int *pBits; // [rsp+90h] [rbp-19h] BYREF
  CRect rt; // [rsp+98h] [rbp-11h] BYREF
  CGdiObject *v48; // [rsp+A8h] [rbp-1h]
  HGDIOBJ ho; // [rsp+B0h] [rbp+7h]
  CRect rectSrc; // [rsp+B8h] [rbp+Fh] BYREF

  v42 = clrLine;
  v43 = clrFill;
  *(_QWORD *)&rectSrc.left = this;
  if ( clrFill != -1 || clrLine != -1 )
  {
    rt = *rect;
    v5 = _mm_cvtsi128_si32((__m128i)rt);
    right = rect->right;
    if ( v5 > right )
    {
      v7 = v5;
      v5 = rect->right;
      rt.left = v5;
      right = v7;
      rt.right = v7;
    }
    top = rt.top;
    bottom = rt.bottom;
    if ( rt.top > rt.bottom )
    {
      v10 = rt.top;
      top = rt.bottom;
      rt.top = rt.bottom;
      bottom = v10;
      rt.bottom = v10;
    }
    v11 = bottom - top;
    v12 = right - v5;
    size.cx = v12;
    size.cy = v11;
    if ( v12 )
    {
      if ( v11 )
      {
        dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
        memset(&dcMem.m_hDC, 0, 20);
        m_dc = this->m_dc;
        m_hDC = 0;
        if ( m_dc )
          m_hDC = m_dc->m_hDC;
        CompatibleDC = CreateCompatibleDC(m_hDC);
        if ( !CDC::Attach(&dcMem, CompatibleDC) )
          goto LABEL_48;
        bmpMem.m_hObject = 0;
        bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
        CompatibleBitmap = CreateCompatibleBitmap(this->m_dc->m_hDC, v12, v11);
        if ( !CGdiObject::Attach(&bmpMem, CompatibleBitmap) )
        {
          bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
          CGdiObject::~CGdiObject(&bmpMem);
          goto LABEL_48;
        }
        v17 = SelectObject(dcMem.m_hDC, bmpMem.m_hObject);
        v48 = CGdiObject::FromHandle(v17);
        if ( !v48 )
          AfxThrowInvalidArgException();
        v18 = CDrawingManager::CreateBitmap_32(&size, (void **)&pBits);
        ho = v18;
        if ( !v18 || (v19 = pBits) == 0 )
        {
          bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
          CGdiObject::~CGdiObject(&bmpMem);
LABEL_48:
          dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
          if ( dcMem.m_hDC )
          {
            v40 = CDC::Detach(&dcMem);
            DeleteDC(v40);
          }
          return;
        }
        SelectObject(dcMem.m_hDC, v18);
        v20 = 0;
        cx = size.cx;
        v22 = size.cx;
        v23 = 1;
        cy = size.cy;
        v25 = v42;
        if ( v42 != -1 )
        {
          v26 = BYTE2(v42) | ((v42 | 0xFFFFFF00) << 16) | v42 & 0xFF00;
          if ( size.cx > 0 )
          {
            v27 = (4 * (unsigned __int64)(unsigned int)size.cx) >> 2;
            v28 = v19;
            while ( v27 )
            {
              *v28++ = v26;
              --v27;
            }
            v19 += (unsigned int)v22;
          }
          v23 = 2;
          LODWORD(pBits) = 2;
          if ( cy > 1 )
          {
            memcpy(&v19[(int)v22 * (cy - 2)], &v19[-v22], 4 * v22);
            v23 = (int)pBits;
            if ( cy > (int)pBits )
            {
              *v19 = v26;
              if ( (int)v22 >= v23 )
                v19[v22 - 1] = v26;
              ++v19;
            }
            v25 = v42;
          }
          v20 = 1;
          cx = size.cx;
          LODWORD(v22) = size.cx - 1;
          cy = size.cy - 1;
        }
        v29 = v43;
        v30 = BYTE2(v43) | ((v43 | 0xFFFFFF00) << 16) | v43 & 0xFF00;
        if ( v43 == -1 )
          v30 = 0;
        if ( v23 <= cy )
        {
          if ( v20 < (int)v22 )
          {
            v31 = (unsigned int)(v22 - v20);
            v32 = (unsigned __int64)(4 * v31) >> 2;
            v33 = v30;
            v34 = v19;
            while ( v32 )
            {
              *v34++ = v33;
              --v32;
            }
            v19 += v31;
            if ( v25 != -1 )
              ++v19;
          }
          if ( v23 < cy )
          {
            v35 = 4LL * cx;
            v36 = (unsigned int)(cy - v23);
            do
            {
              memcpy(v19, &v19[v35 / 0xFFFFFFFFFFFFFFFCuLL], 4LL * cx);
              v19 = (unsigned int *)((char *)v19 + v35);
              --v36;
            }
            while ( v36 );
            v29 = v43;
          }
        }
        v37 = *(CDrawingManager **)&rectSrc.left;
        v38 = *(CDC **)(*(_QWORD *)&rectSrc.left + 8LL);
        if ( v29 == -1 )
        {
          *(_QWORD *)&rectSrc.left = 0;
          rectSrc.right = cx;
          rectSrc.bottom = size.cy;
          CDrawingManager::DrawAlpha(v37, v38, &rt, &dcMem, &rectSrc);
        }
        else
        {
          BitBlt(v38->m_hDC, v5, top, cx, size.cy, dcMem.m_hDC, 0, 0, 0xCC0020u);
        }
        v39 = SelectObject(dcMem.m_hDC, v48->m_hObject);
        CGdiObject::FromHandle(v39);
        DeleteObject(ho);
        bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
        CGdiObject::~CGdiObject(&bmpMem);
        CDC::~CDC(&dcMem);
      }
    }
  }
}

```

## disassembly

```asm
0x18005cce0  mov     [rsp-8+arg_10], rbx
0x18005cce5  push    rbp
0x18005cce6  push    rsi
0x18005cce7  push    rdi
0x18005cce8  push    r12
0x18005ccea  push    r13
0x18005ccec  push    r14
0x18005ccee  push    r15
0x18005ccf0  lea     rbp, [rsp-27h]
0x18005ccf5  sub     rsp, 0D0h
0x18005ccfc  mov     rax, cs:__security_cookie
0x18005cd03  xor     rax, rsp
0x18005cd06  mov     [rbp+57h+var_38], rax
0x18005cd0a  mov     [rbp+57h+var_A8], clrLine
0x18005cd0e  mov     [rbp+57h+var_A4], clrFill
0x18005cd12  mov     rsi, this
0x18005cd15  mov     qword ptr [rbp+57h+rectSrc.left], this
0x18005cd19  or      eax, 0FFFFFFFFh
0x18005cd1c  cmp     clrFill, eax
0x18005cd1f  jnz     short loc_18005CD2A
0x18005cd21  cmp     clrLine, eax
0x18005cd24  jz      loc_18005D0B2
0x18005cd2a  movups  xmm0, xmmword ptr [rect]
0x18005cd2d  movups  xmmword ptr [rbp+57h+rt.left], xmm0
0x18005cd31  movd    r13d, xmm0
0x18005cd36  mov     ebx, [rect+8]
0x18005cd39  cmp     r13d, ebx
0x18005cd3c  jle     short loc_18005CD4C
0x18005cd3e  mov     eax, r13d
0x18005cd41  mov     r13d, ebx
0x18005cd44  mov     [rbp+57h+rt.left], ebx
0x18005cd47  mov     ebx, eax
0x18005cd49  mov     [rbp+57h+rt.right], eax
0x18005cd4c  mov     r15d, [rbp+57h+rt.top]
0x18005cd50  mov     edi, [rbp+57h+rt.bottom]
0x18005cd53  cmp     r15d, edi
0x18005cd56  jle     short loc_18005CD66
0x18005cd58  mov     eax, r15d
0x18005cd5b  mov     r15d, edi
0x18005cd5e  mov     [rbp+57h+rt.top], edi
0x18005cd61  mov     edi, eax
0x18005cd63  mov     [rbp+57h+rt.bottom], eax
0x18005cd66  sub     edi, r15d
0x18005cd69  sub     ebx, r13d
0x18005cd6c  mov     [rbp+57h+size.cx], ebx
0x18005cd6f  mov     [rbp+57h+size.cy], edi
0x18005cd72  jz      loc_18005D0B2
0x18005cd78  xor     r14d, r14d
0x18005cd7b  test    edi, edi
0x18005cd7d  jz      loc_18005D0B2
0x18005cd83  lea     r12, ??_7CDC@@6B@; const CDC::`vftable'
0x18005cd8a  mov     [rbp+57h+dcMem.__vftable], r12
0x18005cd8e  xorps   xmm0, xmm0
0x18005cd91  movdqu  xmmword ptr [rbp+57h+dcMem.m_hDC], xmm0
0x18005cd96  mov     [rbp+57h+dcMem.m_bPrinting], r14d
0x18005cd9a  mov     rax, [this+8]
0x18005cd9e  test    rax, rax
0x18005cda1  mov     ecx, r14d
0x18005cda4  jz      short loc_18005CDAA
0x18005cda6  mov     this, [rax+8]; hdc
0x18005cdaa  call    cs:__imp_CreateCompatibleDC
0x18005cdb0  mov     rect, rax; hDC
0x18005cdb3  lea     this, [rbp+57h+dcMem]; this
0x18005cdb7  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18005cdbc  test    eax, eax
0x18005cdbe  jnz     short loc_18005CDC5
0x18005cdc0  jmp     loc_18005D095
0x18005cdc5  mov     [rbp+57h+bmpMem.m_hObject], r14
0x18005cdc9  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005cdd0  mov     [rbp+57h+bmpMem.__vftable], rax
0x18005cdd4  mov     this, [rsi+8]
0x18005cdd8  mov     clrFill, edi; cy
0x18005cddb  mov     edx, ebx; cx
0x18005cddd  mov     this, [this+8]; hdc
0x18005cde1  call    cs:__imp_CreateCompatibleBitmap
0x18005cde7  mov     rect, rax; hObject
0x18005cdea  lea     this, [rbp+57h+bmpMem]; this
0x18005cdee  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18005cdf3  test    eax, eax
0x18005cdf5  jnz     short loc_18005CE11
0x18005cdf7  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005cdfe  mov     [rbp+57h+bmpMem.__vftable], rax
0x18005ce02  lea     this, [rbp+57h+bmpMem]; this
0x18005ce06  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005ce0b  nop
0x18005ce0c  jmp     loc_18005D095
0x18005ce11  mov     rect, [rbp+57h+bmpMem.m_hObject]; h
0x18005ce15  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18005ce19  call    cs:__imp_SelectObject
0x18005ce1f  mov     this, rax; h
0x18005ce22  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18005ce27  mov     [rbp+57h+var_58], rax
0x18005ce2b  test    rax, rax
0x18005ce2e  jz      loc_18005D0D9
0x18005ce34  lea     rect, [rbp+57h+pBits]; pBits
0x18005ce38  lea     this, [rbp+57h+size]; size
0x18005ce3c  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@AEBVCSize@@PEAPEAX@Z; CDrawingManager::CreateBitmap_32(CSize const &,void * *)
0x18005ce41  mov     [rbp+57h+ho], rax
0x18005ce45  test    rax, rax
0x18005ce48  jz      loc_18005D080
0x18005ce4e  mov     rbx, [rbp+57h+pBits]
0x18005ce52  test    rbx, rbx
0x18005ce55  jz      loc_18005D080
0x18005ce5b  mov     rect, rax; h
0x18005ce5e  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18005ce62  call    cs:__imp_SelectObject
0x18005ce68  mov     edx, r14d
0x18005ce6b  movsxd  rsi, [rbp+57h+size.cx]
0x18005ce6f  mov     r12, rsi
0x18005ce72  mov     clrFill, 1
0x18005ce78  mov     r14d, [rbp+57h+size.cy]
0x18005ce7c  mov     clrLine, [rbp+57h+var_A8]
0x18005ce80  cmp     clrLine, 0FFFFFFFFh
0x18005ce84  jz      loc_18005CF31
0x18005ce8a  movzx   esi, r9w
0x18005ce8e  and     esi, 0FFFFFF00h
0x18005ce94  movzx   eax, r9b
0x18005ce98  or      eax, 0FFFFFF00h
0x18005ce9d  shl     eax, 10h
0x18005cea0  or      esi, eax
0x18005cea2  mov     eax, clrLine
0x18005cea5  shr     eax, 10h
0x18005cea8  movzx   ecx, al
0x18005ceab  or      esi, ecx
0x18005cead  test    r12d, r12d
0x18005ceb0  jle     short loc_18005CECE
0x18005ceb2  mov     eax, r12d
0x18005ceb5  lea     rect, ds:0[rax*4]
0x18005cebd  mov     this, rect
0x18005cec0  shr     this, 2
0x18005cec4  mov     eax, esi
0x18005cec6  mov     rdi, rbx
0x18005cec9  rep stosd
0x18005cecb  add     rbx, rect
0x18005cece  mov     clrFill, 2
0x18005ced4  mov     dword ptr [rbp+57h+pBits], clrFill
0x18005ced8  cmp     r14d, 1
0x18005cedc  jle     short loc_18005CF1E
0x18005cede  mov     rdi, r12
0x18005cee1  shl     rdi, 2
0x18005cee5  mov     rect, rbx
0x18005cee8  sub     rect, rdi; Src
0x18005ceeb  lea     eax, [r14-2]
0x18005ceef  imul    eax, r12d
0x18005cef3  cdqe
0x18005cef5  lea     this, [rbx+rax*4]; void *
0x18005cef9  mov     r8, rdi; Size
0x18005cefc  call    cs:__imp_memcpy
0x18005cf02  mov     clrFill, dword ptr [rbp+57h+pBits]
0x18005cf06  cmp     r14d, clrFill
0x18005cf09  jle     short loc_18005CF1A
0x18005cf0b  mov     [rbx], esi
0x18005cf0d  cmp     r12d, clrFill
0x18005cf10  jl      short loc_18005CF16
0x18005cf12  mov     [rdi+rbx-4], esi
0x18005cf16  add     rbx, 4
0x18005cf1a  mov     clrLine, [rbp+57h+var_A8]
0x18005cf1e  mov     edx, 1
0x18005cf23  mov     esi, [rbp+57h+size.cx]
0x18005cf26  lea     r12d, [rsi-1]
0x18005cf2a  mov     r14d, [rbp+57h+size.cy]
0x18005cf2e  dec     r14d
0x18005cf31  mov     r10d, [rbp+57h+var_A4]
0x18005cf35  movzx   edi, r10w
0x18005cf39  and     edi, 0FFFFFF00h
0x18005cf3f  movzx   eax, r10b
0x18005cf43  or      eax, 0FFFFFF00h
0x18005cf48  shl     eax, 10h
0x18005cf4b  or      edi, eax
0x18005cf4d  mov     eax, r10d
0x18005cf50  shr     eax, 10h
0x18005cf53  movzx   ecx, al
0x18005cf56  or      edi, ecx
0x18005cf58  cmp     r10d, 0FFFFFFFFh
0x18005cf5c  mov     r11d, 0
0x18005cf62  cmovz   edi, r11d
0x18005cf66  cmp     clrFill, r14d
0x18005cf69  jg      short loc_18005CFC7
0x18005cf6b  cmp     edx, r12d
0x18005cf6e  jge     short loc_18005CF96
0x18005cf70  sub     r12d, edx
0x18005cf73  lea     rect, ds:0[r12*4]
0x18005cf7b  mov     this, rect
0x18005cf7e  shr     this, 2
0x18005cf82  mov     eax, edi
0x18005cf84  mov     rdi, rbx
0x18005cf87  rep stosd
0x18005cf89  add     rbx, rect
0x18005cf8c  cmp     clrLine, 0FFFFFFFFh
0x18005cf90  jz      short loc_18005CF96
0x18005cf92  add     rbx, 4
0x18005cf96  cmp     clrFill, r14d
0x18005cf99  jge     short loc_18005CFC7
0x18005cf9b  movsxd  rdi, esi
0x18005cf9e  shl     rdi, 2
0x18005cfa2  sub     r14d, clrFill
0x18005cfa5  mov     rect, rbx
0x18005cfa8  sub     rect, rdi; Src
0x18005cfab  mov     r8, rdi; Size
0x18005cfae  mov     this, rbx; void *
0x18005cfb1  call    cs:__imp_memcpy
0x18005cfb7  add     rbx, rdi
0x18005cfba  sub     r14, 1
0x18005cfbe  jnz     short loc_18005CFA5
0x18005cfc0  mov     r10d, [rbp+57h+var_A4]
0x18005cfc4  xor     r11d, r11d
0x18005cfc7  mov     rdi, qword ptr [rbp+57h+rectSrc.left]
0x18005cfcb  mov     this, [rdi+8]
0x18005cfcf  cmp     r10d, 0FFFFFFFFh
0x18005cfd3  jz      short loc_18005D00C
0x18005cfd5  mov     [rsp+100h+rop], 0CC0020h; rop
0x18005cfdd  mov     [rsp+100h+y1], r11d; y1
0x18005cfe2  mov     [rsp+100h+x1], r11d; x1
0x18005cfe7  mov     rax, [rbp+57h+dcMem.m_hDC]
0x18005cfeb  mov     [rsp+100h+hdcSrc], rax; hdcSrc
0x18005cff0  mov     eax, [rbp+57h+size.cy]
0x18005cff3  mov     [rsp+100h+cy], eax; cy
0x18005cff7  mov     clrLine, esi; cx
0x18005cffa  mov     clrFill, r15d; y
0x18005cffd  mov     edx, r13d; x
0x18005d000  mov     this, [this+8]; hdc
0x18005d004  call    cs:__imp_BitBlt
0x18005d00a  jmp     short loc_18005D03B
0x18005d00c  and     qword ptr [rbp+57h+rectSrc.left], 0
0x18005d011  mov     [rbp+57h+rectSrc.right], esi
0x18005d014  mov     rax, qword ptr [rbp+57h+size.cx]
0x18005d018  shr     rax, 20h
0x18005d01c  mov     [rbp+57h+rectSrc.bottom], eax
0x18005d01f  lea     rax, [rbp+57h+rectSrc]
0x18005d023  mov     qword ptr [rsp+100h+cy], rax; rectSrc
0x18005d028  lea     r9, [rbp+57h+dcMem]; pSrcDC
0x18005d02c  lea     r8, [rbp+57h+rt]; rectDst
0x18005d030  mov     rect, this; pDstDC
0x18005d033  mov     this, rdi; this
0x18005d036  call    ?DrawAlpha@CDrawingManager@@QEAAXPEAVCDC@@AEBVCRect@@01@Z; CDrawingManager::DrawAlpha(CDC *,CRect const &,CDC *,CRect const &)
0x18005d03b  mov     rect, [rbp+57h+var_58]
0x18005d03f  mov     rect, [rect+8]; h
0x18005d043  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18005d047  call    cs:__imp_SelectObject
0x18005d04d  mov     this, rax; h
0x18005d050  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18005d055  mov     this, [rbp+57h+ho]; ho
0x18005d059  call    cs:__imp_DeleteObject
0x18005d05f  nop
0x18005d060  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005d067  mov     [rbp+57h+bmpMem.__vftable], rax
0x18005d06b  lea     this, [rbp+57h+bmpMem]; this
0x18005d06f  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005d074  nop
0x18005d075  lea     this, [rbp+57h+dcMem]; this
0x18005d079  call    ??1CDC@@UEAA@XZ; CDC::~CDC(void)
0x18005d07e  jmp     short loc_18005D0B2
0x18005d080  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005d087  mov     [rbp+57h+bmpMem.__vftable], rax
0x18005d08b  lea     this, [rbp+57h+bmpMem]; this
0x18005d08f  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005d094  nop
0x18005d095  mov     [rbp+57h+dcMem.__vftable], r12
0x18005d099  cmp     [rbp+57h+dcMem.m_hDC], r14
0x18005d09d  jz      short loc_18005D0B2
0x18005d09f  lea     this, [rbp+57h+dcMem]; this
0x18005d0a3  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18005d0a8  mov     this, rax; hdc
0x18005d0ab  call    cs:__imp_DeleteDC
0x18005d0b1  nop
0x18005d0b2  mov     this, [rbp+57h+var_38]
0x18005d0b6  xor     this, rsp; StackCookie
0x18005d0b9  call    __security_check_cookie
0x18005d0be  mov     rbx, [rsp+100h+arg_10]
0x18005d0c6  add     rsp, 0D0h
0x18005d0cd  pop     r15
0x18005d0cf  pop     r14
0x18005d0d1  pop     r13
0x18005d0d3  pop     r12
0x18005d0d5  pop     rdi
0x18005d0d6  pop     rsi
0x18005d0d7  pop     rbp
0x18005d0d8  retn
0x18005d0d9  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```

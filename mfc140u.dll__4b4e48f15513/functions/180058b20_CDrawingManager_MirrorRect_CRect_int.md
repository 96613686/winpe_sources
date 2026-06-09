# CDrawingManager::MirrorRect(CRect,int)

- ea: `0x180058b20`
- end: `0x180058f19`
- name: `?MirrorRect@CDrawingManager@@QEAAXVCRect@@H@Z`
- size: `1017`
- prototype: `void __fastcall(CDrawingManager *this, CRect rect, int bHorz)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800bbf90`
- `0x1801bf980`
- `0x1801bfdf0`
- `0x1801c3ad0`
- `0x1801c3d90`

## callees

- `0x18001d090`
- `0x180058150`
- `0x180058b20`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!UnionRect` at `0x180058bab`
- `USER32!UnionRect` at `0x180058bab`
- `USER32!EqualRect` at `0x180058bb9`
- `USER32!EqualRect` at `0x180058bb9`
- `GDI32!DeleteDC` at `0x180058ee5`
- `GDI32!DeleteDC` at `0x180058ee5`
- `GDI32!BitBlt` at `0x180058d07`
- `GDI32!BitBlt` at `0x180058e6c`
- `GDI32!BitBlt` at `0x180058d07`
- `GDI32!BitBlt` at `0x180058e6c`
- `GDI32!CreateCompatibleBitmap` at `0x180058c3c`
- `GDI32!CreateCompatibleBitmap` at `0x180058c3c`
- `GDI32!DeleteObject` at `0x180058e90`
- `GDI32!DeleteObject` at `0x180058e90`
- `GDI32!SelectObject` at `0x180058c74`
- `GDI32!SelectObject` at `0x180058cc3`
- `GDI32!SelectObject` at `0x180058e7e`
- `GDI32!SelectObject` at `0x180058c74`
- `GDI32!SelectObject` at `0x180058cc3`
- `GDI32!SelectObject` at `0x180058e7e`
- `GDI32!CreateCompatibleDC` at `0x180058c04`
- `GDI32!CreateCompatibleDC` at `0x180058c04`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CDrawingManager::MirrorRect(CDrawingManager *this, CRect *rect, int bHorz)
{
  CRect *v3; // rbx
  HDC__ *v5; // r15
  int right; // r13d
  int left; // r14d
  int v8; // esi
  int cy; // edi
  CDC *m_dc; // rcx
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v14; // rax
  HBITMAP__ *v15; // rax
  CDC *v16; // rcx
  HDC hdcSrc; // rax
  __int64 v18; // rdx
  int v19; // r13d
  int v20; // r11d
  __int64 v21; // r12
  unsigned int *v22; // rax
  int v23; // ecx
  CSize v24; // r8
  int v25; // r9d
  __int64 v26; // r10
  __int64 v27; // r14
  int v28; // edx
  __int64 v29; // r10
  __int64 v30; // r9
  __int64 v31; // r13
  __int64 v32; // rcx
  HDC__ *v33; // r11
  __int64 v34; // r15
  HDC__ *v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r14
  int v38; // ecx
  HGDIOBJ v39; // rax
  bool v40; // zf
  HDC v41; // rax
  CSize size; // [rsp+58h] [rbp-71h] BYREF
  CDC dcMem; // [rsp+60h] [rbp-69h] BYREF
  unsigned int *pBits; // [rsp+80h] [rbp-49h] BYREF
  CBitmap bmpMem; // [rsp+88h] [rbp-41h] BYREF
  __int64 v47; // [rsp+98h] [rbp-31h]
  CRect *v48; // [rsp+A0h] [rbp-29h]
  CDrawingManager *v49; // [rsp+A8h] [rbp-21h]
  CGdiObject *v50; // [rsp+B0h] [rbp-19h]
  HGDIOBJ ho; // [rsp+B8h] [rbp-11h]
  CRect rectClip; // [rsp+C0h] [rbp-9h] BYREF
  CRect rectUnion; // [rsp+D0h] [rbp+7h] BYREF

  v3 = rect;
  v48 = rect;
  v49 = this;
  v5 = 0;
  if ( rect->bottom - rect->top > 0 && rect->right - rect->left > 0 )
  {
    rectClip = 0;
    this->m_dc->GetClipBox(this->m_dc, &rectClip);
    rectUnion = 0;
    UnionRect(&rectUnion, &rectClip, v3);
    if ( EqualRect(&rectUnion, &rectClip) )
    {
      right = v3->right;
      left = v3->left;
      v8 = right - v3->left;
      cy = v3->bottom - v3->top;
      dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
      memset(&dcMem.m_hDC, 0, 20);
      m_dc = this->m_dc;
      if ( m_dc )
        m_hDC = m_dc->m_hDC;
      else
        m_hDC = 0;
      CompatibleDC = CreateCompatibleDC(m_hDC);
      if ( CDC::Attach(&dcMem, CompatibleDC) )
      {
        bmpMem.m_hObject = 0;
        bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
        CompatibleBitmap = CreateCompatibleBitmap(this->m_dc->m_hDC, v8, cy);
        if ( CGdiObject::Attach(&bmpMem, CompatibleBitmap) )
        {
          v14 = SelectObject(dcMem.m_hDC, bmpMem.m_hObject);
          v50 = CGdiObject::FromHandle(v14);
          if ( !v50 )
            AfxThrowInvalidArgException();
          size.cx = v8;
          size.cy = cy;
          v15 = CDrawingManager::CreateBitmap_32(&size, (void **)&pBits);
          ho = v15;
          if ( v15 )
          {
            v5 = (HDC__ *)pBits;
            if ( pBits )
            {
              SelectObject(dcMem.m_hDC, v15);
              v16 = this->m_dc;
              if ( v16 )
                hdcSrc = v16->m_hDC;
              else
                hdcSrc = 0;
              BitBlt(dcMem.m_hDC, 0, 0, v8, cy, hdcSrc, v3->left, v3->top, 0xCC0020u);
              if ( bHorz )
              {
                if ( cy >= 0 )
                {
                  v18 = v8 / 2;
                  v47 = v18;
                  v19 = v8 * cy;
                  v20 = v8 * cy;
                  v21 = v8 * cy;
                  size = (CSize)-v8;
                  v22 = (unsigned int *)(unsigned int)(cy + 1);
                  pBits = v22;
                  v23 = -v8;
                  v24 = size;
                  do
                  {
                    v25 = 0;
                    v26 = 0;
                    if ( v18 >= 0 )
                    {
                      v27 = v8;
                      do
                      {
                        if ( v20 + v25 < v19 && v8 + v20 - v25 - 1 < v19 )
                        {
                          v28 = *((_DWORD *)v5 + v26 + v21);
                          *((_DWORD *)v5 + v26 + v21) = *((_DWORD *)v5 + v21 + v27 - 1);
                          *((_DWORD *)v5 + v21 + v27 - 1) = v28;
                          v18 = v47;
                        }
                        ++v25;
                        ++v26;
                        --v27;
                      }
                      while ( v26 <= v18 );
                      v22 = pBits;
                      v23 = -v8;
                      v24 = size;
                    }
                    v20 += v23;
                    v21 += *(_QWORD *)&v24;
                    v22 = (unsigned int *)((char *)v22 - 1);
                    pBits = v22;
                  }
                  while ( v22 );
                  v3 = v48;
                }
              }
              else if ( cy / 2 >= 0 )
              {
                v29 = 0;
                v30 = v8 * (cy - 1);
                v31 = left - right;
                v32 = 4 * v31;
                v33 = v5 + v30;
                v34 = (unsigned int)(cy / 2 + 1);
                do
                {
                  if ( v8 > 0 )
                  {
                    v35 = v33;
                    v36 = v29 - v30;
                    v37 = v8;
                    do
                    {
                      v38 = *((_DWORD *)v35 + v36);
                      *((_DWORD *)v35 + v36) = *(_DWORD *)v35;
                      *(_DWORD *)v35++ = v38;
                      --v37;
                    }
                    while ( v37 );
                    v32 = 4 * v31;
                  }
                  v30 += v31;
                  v33 = (HDC__ *)((char *)v33 + v32);
                  v29 += v8;
                  --v34;
                }
                while ( v34 );
              }
              BitBlt(v49->m_dc->m_hDC, v3->left, v3->top, v8, cy, dcMem.m_hDC, 0, 0, 0xCC0020u);
              v39 = SelectObject(dcMem.m_hDC, v50->m_hObject);
              CGdiObject::FromHandle(v39);
              DeleteObject(ho);
              bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
              CGdiObject::~CGdiObject(&bmpMem);
              v40 = dcMem.m_hDC == 0;
              goto LABEL_38;
            }
          }
          bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
          CGdiObject::~CGdiObject(&bmpMem);
        }
        else
        {
          bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
          CGdiObject::~CGdiObject(&bmpMem);
        }
      }
      v40 = dcMem.m_hDC == v5;
LABEL_38:
      dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
      if ( !v40 )
      {
        v41 = CDC::Detach(&dcMem);
        DeleteDC(v41);
      }
    }
  }
}

```

## disassembly

```asm
0x180058b20  mov     [rsp-8+arg_10], rbx
0x180058b25  push    rbp
0x180058b26  push    rsi
0x180058b27  push    rdi
0x180058b28  push    r12
0x180058b2a  push    r13
0x180058b2c  push    r14
0x180058b2e  push    r15
0x180058b30  lea     rbp, [rsp-27h]
0x180058b35  sub     rsp, 0F0h
0x180058b3c  mov     rax, cs:__security_cookie
0x180058b43  xor     rax, rsp
0x180058b46  mov     [rbp+57h+var_40], rax
0x180058b4a  mov     [rbp+57h+var_D0], bHorz
0x180058b4e  mov     rbx, rect
0x180058b51  mov     [rbp+57h+var_80], rect
0x180058b55  mov     r12, this
0x180058b58  mov     [rbp+57h+var_78], this
0x180058b5c  mov     eax, [rect+0Ch]
0x180058b5f  sub     eax, [rect+4]
0x180058b62  xor     r15d, r15d
0x180058b65  test    eax, eax
0x180058b67  jle     loc_180058EEC
0x180058b6d  mov     eax, [rect+8]
0x180058b70  sub     eax, [rect]
0x180058b72  test    eax, eax
0x180058b74  jle     loc_180058EEC
0x180058b7a  xorps   xmm0, xmm0
0x180058b7d  movups  xmmword ptr [rbp+57h+rectClip.left], xmm0
0x180058b81  mov     this, [this+8]
0x180058b85  mov     rax, [this]
0x180058b88  lea     rect, [rbp+57h+rectClip]
0x180058b8c  mov     rax, [rax+0B0h]
0x180058b93  call    cs:__guard_dispatch_icall_fptr
0x180058b99  xorps   xmm0, xmm0
0x180058b9c  movups  xmmword ptr [rbp+57h+rectUnion.left], xmm0
0x180058ba0  mov     r8, rbx; lprcSrc2
0x180058ba3  lea     rect, [rbp+57h+rectClip]; lprcSrc1
0x180058ba7  lea     this, [rbp+57h+rectUnion]; lprcDst
0x180058bab  call    cs:__imp_UnionRect
0x180058bb1  lea     rect, [rbp+57h+rectClip]; lprc2
0x180058bb5  lea     this, [rbp+57h+rectUnion]; lprc1
0x180058bb9  call    cs:__imp_EqualRect
0x180058bbf  test    eax, eax
0x180058bc1  jz      loc_180058EEC
0x180058bc7  mov     r13d, [rbx+8]
0x180058bcb  mov     r14d, [rbx]
0x180058bce  mov     esi, r13d
0x180058bd1  sub     esi, r14d
0x180058bd4  mov     edi, [rbx+0Ch]
0x180058bd7  sub     edi, [rbx+4]
0x180058bda  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180058be1  mov     [rbp+57h+dcMem.__vftable], rax
0x180058be5  xorps   xmm0, xmm0
0x180058be8  movdqu  xmmword ptr [rbp+57h+dcMem.m_hDC], xmm0
0x180058bed  mov     [rbp+57h+dcMem.m_bPrinting], r15d
0x180058bf1  mov     this, [r12+8]
0x180058bf6  test    this, this
0x180058bf9  jnz     short loc_180058C00
0x180058bfb  mov     ecx, r15d
0x180058bfe  jmp     short loc_180058C04
0x180058c00  mov     this, [this+8]; hdc
0x180058c04  call    cs:__imp_CreateCompatibleDC
0x180058c0a  mov     rect, rax; hDC
0x180058c0d  lea     this, [rbp+57h+dcMem]; this
0x180058c11  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180058c16  test    eax, eax
0x180058c18  jnz     short loc_180058C1F
0x180058c1a  jmp     loc_180058EC8
0x180058c1f  mov     [rbp+57h+bmpMem.m_hObject], r15
0x180058c23  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180058c2a  mov     [rbp+57h+bmpMem.__vftable], rax
0x180058c2e  mov     this, [r12+8]
0x180058c33  mov     bHorz, edi; cy
0x180058c36  mov     edx, esi; cx
0x180058c38  mov     this, [this+8]; hdc
0x180058c3c  call    cs:__imp_CreateCompatibleBitmap
0x180058c42  mov     rect, rax; hObject
0x180058c45  lea     this, [rbp+57h+bmpMem]; this
0x180058c49  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180058c4e  test    eax, eax
0x180058c50  jnz     short loc_180058C6C
0x180058c52  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180058c59  mov     [rbp+57h+bmpMem.__vftable], rax
0x180058c5d  lea     this, [rbp+57h+bmpMem]; this
0x180058c61  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180058c66  nop
0x180058c67  jmp     loc_180058EC8
0x180058c6c  mov     rect, [rbp+57h+bmpMem.m_hObject]; h
0x180058c70  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x180058c74  call    cs:__imp_SelectObject
0x180058c7a  mov     this, rax; h
0x180058c7d  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180058c82  mov     [rbp+57h+var_70], rax
0x180058c86  test    rax, rax
0x180058c89  jz      loc_180058F13
0x180058c8f  mov     [rbp+57h+size.cx], esi
0x180058c92  mov     [rbp+57h+size.cy], edi
0x180058c95  lea     rect, [rbp+57h+pBits]; pBits
0x180058c99  lea     this, [rbp+57h+size]; size
0x180058c9d  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@AEBVCSize@@PEAPEAX@Z; CDrawingManager::CreateBitmap_32(CSize const &,void * *)
0x180058ca2  mov     [rbp+57h+ho], rax
0x180058ca6  test    rax, rax
0x180058ca9  jz      loc_180058EB3
0x180058caf  mov     r15, [rbp+57h+pBits]
0x180058cb3  test    r15, r15
0x180058cb6  jz      loc_180058EB3
0x180058cbc  mov     rect, rax; h
0x180058cbf  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x180058cc3  call    cs:__imp_SelectObject
0x180058cc9  mov     edx, [rbx+4]
0x180058ccc  mov     bHorz, [rbx]
0x180058ccf  mov     this, [r12+8]
0x180058cd4  test    this, this
0x180058cd7  jnz     short loc_180058CDD
0x180058cd9  xor     eax, eax
0x180058cdb  jmp     short loc_180058CE1
0x180058cdd  mov     rax, [this+8]
0x180058ce1  mov     [rsp+120h+rop], 0CC0020h; rop
0x180058ce9  mov     [rsp+120h+y1], edx; y1
0x180058ced  mov     [rsp+120h+x1], bHorz; x1
0x180058cf2  mov     [rsp+120h+hdcSrc], rax; hdcSrc
0x180058cf7  mov     [rsp+120h+cy], edi; cy
0x180058cfb  mov     r9d, esi; cx
0x180058cfe  xor     bHorz, bHorz; y
0x180058d01  xor     edx, edx; x
0x180058d03  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x180058d07  call    cs:__imp_BitBlt
0x180058d0d  movsxd  r12, esi
0x180058d10  cmp     [rbp+57h+var_D0], 0
0x180058d14  jz      loc_180058DCE
0x180058d1a  test    edi, edi
0x180058d1c  js      loc_180058E38
0x180058d22  mov     eax, esi
0x180058d24  cdq
0x180058d25  sub     eax, edx
0x180058d27  sar     eax, 1
0x180058d29  movsxd  rect, eax
0x180058d2c  mov     [rbp+57h+var_88], rect
0x180058d30  mov     eax, esi
0x180058d32  neg     eax
0x180058d34  mov     [rbp+57h+var_D0], eax
0x180058d37  mov     r13d, edi
0x180058d3a  imul    r13d, esi
0x180058d3e  mov     r11d, r13d
0x180058d41  movsxd  r12, r13d
0x180058d44  cdqe
0x180058d46  mov     qword ptr [rbp+57h+size.cx], rax
0x180058d4a  lea     eax, [rdi+1]
0x180058d4d  mov     [rbp+57h+pBits], rax
0x180058d51  movsxd  rbx, esi
0x180058d54  mov     ecx, [rbp+57h+var_D0]
0x180058d57  mov     r8, qword ptr [rbp+57h+size.cx]
0x180058d5b  xor     r9d, r9d
0x180058d5e  xor     r10d, r10d
0x180058d61  test    rect, rect
0x180058d64  js      short loc_180058DB8
0x180058d66  mov     r14, rbx
0x180058d69  lea     eax, [r11+r9]
0x180058d6d  cmp     eax, r13d
0x180058d70  jge     short loc_180058D9F
0x180058d72  mov     eax, r11d
0x180058d75  sub     eax, r9d
0x180058d78  dec     eax
0x180058d7a  add     eax, esi
0x180058d7c  cmp     eax, r13d
0x180058d7f  jge     short loc_180058D9F
0x180058d81  lea     r8, [r10+r12]
0x180058d85  mov     edx, [r15+r8*4]
0x180058d89  lea     this, [r12+r14]
0x180058d8d  mov     eax, [r15+this*4-4]
0x180058d92  mov     [r15+r8*4], eax
0x180058d96  mov     [r15+this*4-4], edx
0x180058d9b  mov     rect, [rbp+57h+var_88]
0x180058d9f  inc     r9d
0x180058da2  inc     r10
0x180058da5  dec     r14
0x180058da8  cmp     r10, rect
0x180058dab  jle     short loc_180058D69
0x180058dad  mov     rax, [rbp+57h+pBits]
0x180058db1  mov     ecx, [rbp+57h+var_D0]
0x180058db4  mov     r8, qword ptr [rbp+57h+size.cx]
0x180058db8  add     r11d, ecx
0x180058dbb  add     r12, r8
0x180058dbe  sub     rax, 1
0x180058dc2  mov     [rbp+57h+pBits], rax
0x180058dc6  jnz     short loc_180058D5B
0x180058dc8  mov     rbx, [rbp+57h+var_80]
0x180058dcc  jmp     short loc_180058E38
0x180058dce  mov     eax, edi
0x180058dd0  cdq
0x180058dd1  sub     eax, edx
0x180058dd3  sar     eax, 1
0x180058dd5  js      short loc_180058E38
0x180058dd7  xor     r10d, r10d
0x180058dda  lea     ecx, [rdi-1]
0x180058ddd  imul    ecx, esi
0x180058de0  movsxd  r9, ecx
0x180058de3  sub     r14d, r13d
0x180058de6  movsxd  r13, r14d
0x180058de9  lea     this, ds:0[r13*4]
0x180058df1  lea     r11, [r15+r9*4]
0x180058df5  lea     r15d, [rax+1]
0x180058df9  test    esi, esi
0x180058dfb  jle     short loc_180058E29
0x180058dfd  mov     r8, r11
0x180058e00  mov     rect, r10
0x180058e03  sub     rect, r9
0x180058e06  mov     r14, r12
0x180058e09  mov     ecx, [r8+rect*4]
0x180058e0d  mov     eax, [r8]
0x180058e10  mov     [r8+rect*4], eax
0x180058e14  mov     [r8], ecx
0x180058e17  lea     r8, [r8+4]
0x180058e1b  sub     r14, 1
0x180058e1f  jnz     short loc_180058E09
0x180058e21  lea     this, ds:0[r13*4]
0x180058e29  add     r9, r13
0x180058e2c  add     r11, this
0x180058e2f  add     r10, r12
0x180058e32  sub     r15, 1
0x180058e36  jnz     short loc_180058DF9
0x180058e38  mov     rax, [rbp+57h+var_78]
0x180058e3c  mov     rax, [rax+8]
0x180058e40  mov     this, [rax+8]; hdc
0x180058e44  mov     [rsp+120h+rop], 0CC0020h; rop
0x180058e4c  and     [rsp+120h+y1], 0
0x180058e51  and     [rsp+120h+x1], 0
0x180058e56  mov     rax, [rbp+57h+dcMem.m_hDC]
0x180058e5a  mov     [rsp+120h+hdcSrc], rax; hdcSrc
0x180058e5f  mov     [rsp+120h+cy], edi; cy
0x180058e63  mov     r9d, esi; cx
0x180058e66  mov     bHorz, [rbx+4]; y
0x180058e6a  mov     edx, [rbx]; x
0x180058e6c  call    cs:__imp_BitBlt
0x180058e72  mov     rect, [rbp+57h+var_70]
0x180058e76  mov     rect, [rect+8]; h
0x180058e7a  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x180058e7e  call    cs:__imp_SelectObject
0x180058e84  mov     this, rax; h
0x180058e87  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180058e8c  mov     this, [rbp+57h+ho]; ho
0x180058e90  call    cs:__imp_DeleteObject
0x180058e96  nop
0x180058e97  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180058e9e  mov     [rbp+57h+bmpMem.__vftable], rax
0x180058ea2  lea     this, [rbp+57h+bmpMem]; this
0x180058ea6  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180058eab  nop
0x180058eac  cmp     [rbp+57h+dcMem.m_hDC], 0
0x180058eb1  jmp     short loc_180058ECC
0x180058eb3  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180058eba  mov     [rbp+57h+bmpMem.__vftable], rax
0x180058ebe  lea     this, [rbp+57h+bmpMem]; this
0x180058ec2  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180058ec7  nop
0x180058ec8  cmp     [rbp+57h+dcMem.m_hDC], r15
0x180058ecc  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180058ed3  mov     [rbp+57h+dcMem.__vftable], rax
0x180058ed7  jz      short loc_180058EEC
0x180058ed9  lea     this, [rbp+57h+dcMem]; this
0x180058edd  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180058ee2  mov     this, rax; hdc
0x180058ee5  call    cs:__imp_DeleteDC
0x180058eeb  nop
0x180058eec  mov     this, [rbp+57h+var_40]
0x180058ef0  xor     this, rsp; StackCookie
0x180058ef3  call    __security_check_cookie
0x180058ef8  mov     rbx, [rsp+120h+arg_10]
0x180058f00  add     rsp, 0F0h
0x180058f07  pop     r15
0x180058f09  pop     r14
0x180058f0b  pop     r13
0x180058f0d  pop     r12
0x180058f0f  pop     rdi
0x180058f10  pop     rsi
0x180058f11  pop     rbp
0x180058f12  retn
0x180058f13  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```

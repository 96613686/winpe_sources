# CDrawingManager::DrawLine(int,int,int,int,ulong)

- ea: `0x18005b130`
- end: `0x18005b4f6`
- name: `?DrawLine@CDrawingManager@@QEAAXHHHHK@Z`
- size: `966`
- prototype: `void __fastcall(CDrawingManager *this, int x1, int y1, int x2, int y2, unsigned int clrLine)`
- caller_count: `9`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180194f40`
- `0x180195aa0`
- `0x18019b3e0`
- `0x18019feb0`
- `0x1801a0580`
- `0x1801ab920`
- `0x1801b9440`
- `0x1801bbc00`
- `0x1801bc4a0`

## callees

- `0x18001d090`
- `0x180058150`
- `0x18005b130`
- `0x18005dd50`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!abs` at `0x18005b174`
- `api-ms-win-crt-utility-l1-1-0!abs` at `0x18005b18d`
- `api-ms-win-crt-utility-l1-1-0!abs` at `0x18005b174`
- `api-ms-win-crt-utility-l1-1-0!abs` at `0x18005b18d`
- `GDI32!DeleteDC` at `0x18005b4c9`
- `GDI32!DeleteDC` at `0x18005b4c9`
- `GDI32!CreateCompatibleBitmap` at `0x18005b292`
- `GDI32!CreateCompatibleBitmap` at `0x18005b292`
- `GDI32!DeleteObject` at `0x18005b475`
- `GDI32!DeleteObject` at `0x18005b475`
- `GDI32!SelectObject` at `0x18005b2ca`
- `GDI32!SelectObject` at `0x18005b314`
- `GDI32!SelectObject` at `0x18005b463`
- `GDI32!SelectObject` at `0x18005b2ca`
- `GDI32!SelectObject` at `0x18005b314`
- `GDI32!SelectObject` at `0x18005b463`
- `GDI32!CreateCompatibleDC` at `0x18005b258`
- `GDI32!CreateCompatibleDC` at `0x18005b258`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CDrawingManager::DrawLine(CDrawingManager *this, int x1, int y1, int x2, int y2, unsigned int clrLine)
{
  int v8; // esi
  int v9; // edi
  int v10; // ebx
  int v11; // eax
  int v12; // ecx
  int v13; // edx
  int v14; // eax
  int v15; // r12d
  int v16; // edi
  int v17; // ebx
  int v18; // ebx
  int v19; // edi
  CDrawingManager *v20; // r15
  CDC *m_dc; // rax
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v25; // rax
  HBITMAP__ *v26; // rax
  unsigned int *v27; // rdi
  int v28; // r10d
  int v29; // eax
  int v30; // r11d
  unsigned int v31; // r8d
  int left; // r9d
  int v33; // ebx
  int v34; // r13d
  int cx; // r15d
  int v36; // ecx
  int v37; // eax
  int v38; // ecx
  HGDIOBJ v39; // rax
  bool v40; // zf
  HDC v41; // rax
  int v42; // [rsp+30h] [rbp-99h]
  int v43; // [rsp+34h] [rbp-95h]
  CSize size; // [rsp+38h] [rbp-91h] BYREF
  int v45; // [rsp+40h] [rbp-89h]
  int v46; // [rsp+44h] [rbp-85h]
  int v47; // [rsp+48h] [rbp-81h]
  CBitmap bmpMem; // [rsp+50h] [rbp-79h] BYREF
  CDC dcMem; // [rsp+60h] [rbp-69h] BYREF
  CRect rect; // [rsp+80h] [rbp-49h] BYREF
  int v51; // [rsp+90h] [rbp-39h]
  CDrawingManager *v52; // [rsp+98h] [rbp-31h]
  CGdiObject *v53; // [rsp+A0h] [rbp-29h]
  HGDIOBJ ho; // [rsp+A8h] [rbp-21h]
  unsigned int *pBits; // [rsp+B0h] [rbp-19h] BYREF
  int v56; // [rsp+B8h] [rbp-11h]
  int cy; // [rsp+BCh] [rbp-Dh]

  v8 = x1;
  v52 = this;
  if ( clrLine != -1 )
  {
    v9 = x2 - x1;
    v43 = abs(x2 - x1);
    v10 = y2 - y1;
    v11 = abs(y2 - y1);
    v42 = v11;
    v12 = -1;
    if ( v9 )
    {
      v13 = -1;
      if ( v9 > 0 )
        v13 = 1;
      v46 = v13;
    }
    else
    {
      v46 = 0;
    }
    if ( v10 )
    {
      if ( v10 > 0 )
        v12 = 1;
      v45 = v12;
    }
    else
    {
      v45 = 0;
    }
    if ( v43 || v11 )
    {
      v14 = v8;
      rect.left = v8;
      v15 = y1;
      rect.top = y1;
      v16 = x2;
      v17 = y2;
      if ( v8 > x2 )
      {
        v16 = v8;
        v14 = x2;
        rect.left = x2;
      }
      if ( y1 > y2 )
      {
        v17 = y1;
        v15 = y2;
        rect.top = y2;
      }
      rect.right = v16 + 1;
      rect.bottom = v17 + 1;
      v18 = v17 + 1 - v15;
      v19 = v16 + 1 - v14;
      size.cx = v19;
      size.cy = v18;
      if ( v19 )
      {
        if ( v18 )
        {
          dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
          memset(&dcMem.m_hDC, 0, 20);
          v20 = v52;
          m_dc = v52->m_dc;
          m_hDC = 0;
          if ( m_dc )
            m_hDC = m_dc->m_hDC;
          CompatibleDC = CreateCompatibleDC(m_hDC);
          if ( CDC::Attach(&dcMem, CompatibleDC) )
          {
            bmpMem.m_hObject = 0;
            bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
            CompatibleBitmap = CreateCompatibleBitmap(v20->m_dc->m_hDC, v19, v18);
            if ( CGdiObject::Attach(&bmpMem, CompatibleBitmap) )
            {
              v25 = SelectObject(dcMem.m_hDC, bmpMem.m_hObject);
              v53 = CGdiObject::FromHandle(v25);
              if ( !v53 )
                AfxThrowInvalidArgException();
              v26 = CDrawingManager::CreateBitmap_32(&size, (void **)&pBits);
              ho = v26;
              if ( v26 )
              {
                v27 = pBits;
                if ( pBits )
                {
                  SelectObject(dcMem.m_hDC, v26);
                  v28 = v43;
                  v29 = v42;
                  if ( v42 > v43 )
                  {
                    v28 = v42;
                    v29 = v43;
                  }
                  v51 = 2 * v29;
                  v30 = 2 * v29 - v28;
                  v47 = 1;
                  v31 = BYTE2(clrLine) | ((clrLine | 0xFFFFFF00) << 16) | clrLine & 0xFF00;
                  left = rect.left;
                  v33 = v45;
                  v34 = v46;
                  cx = size.cx;
                  do
                  {
                    v27[v8 - left + (__int64)(cx * (v15 - y1 + size.cy - 1))] = v31;
                    if ( v30 >= 0 )
                    {
                      do
                      {
                        v36 = v8;
                        if ( v42 <= v43 )
                          y1 += v33;
                        v8 += v34;
                        if ( v42 <= v43 )
                          v8 = v36;
                        v30 -= 2 * v28;
                      }
                      while ( v30 >= 0 );
                      left = rect.left;
                      v27 = pBits;
                    }
                    v37 = y1;
                    y1 += v33;
                    if ( v42 <= v43 )
                    {
                      y1 = v37;
                      v8 += v34;
                    }
                    v30 += v51;
                    ++v47;
                  }
                  while ( v47 <= v28 );
                  v38 = size.cx;
                  v27[v8 - left + (__int64)(size.cx * (v15 - y1 + size.cy - 1))] = v31;
                  pBits = 0;
                  v56 = v38;
                  cy = size.cy;
                  CDrawingManager::DrawAlpha(v52, v52->m_dc, &rect, &dcMem, (const CRect *)&pBits);
                  v39 = SelectObject(dcMem.m_hDC, v53->m_hObject);
                  CGdiObject::FromHandle(v39);
                  DeleteObject(ho);
                  bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
                  CGdiObject::~CGdiObject(&bmpMem);
                  v40 = dcMem.m_hDC == 0;
                  goto LABEL_44;
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
          v40 = dcMem.m_hDC == 0;
LABEL_44:
          dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
          if ( !v40 )
          {
            v41 = CDC::Detach(&dcMem);
            DeleteDC(v41);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18005b130  push    rbp
0x18005b132  push    rbx
0x18005b133  push    rsi
0x18005b134  push    rdi
0x18005b135  push    r12
0x18005b137  push    r13
0x18005b139  push    r14
0x18005b13b  push    r15
0x18005b13d  lea     rbp, [rsp-0Fh]
0x18005b142  sub     rsp, 0D8h
0x18005b149  mov     rax, cs:__security_cookie
0x18005b150  xor     rax, rsp
0x18005b153  mov     [rbp+47h+var_50], rax
0x18005b157  mov     r15d, x2
0x18005b15a  mov     r14d, y1
0x18005b15d  mov     esi, x1
0x18005b15f  mov     [rbp+47h+var_78], this
0x18005b163  cmp     [rbp+47h+arg_28], 0FFFFFFFFh
0x18005b167  jz      loc_18005B4D0
0x18005b16d  mov     edi, x2
0x18005b170  sub     edi, x1
0x18005b172  mov     ecx, edi; Number
0x18005b174  call    cs:__imp_abs
0x18005b17a  mov     [rsp+110h+var_DC], eax
0x18005b17e  mov     r12d, eax
0x18005b181  mov     r13d, [rbp+47h+arg_20]
0x18005b185  mov     ebx, r13d
0x18005b188  sub     ebx, r14d
0x18005b18b  mov     ecx, ebx; Number
0x18005b18d  call    cs:__imp_abs
0x18005b193  mov     [rsp+110h+var_E0], eax
0x18005b197  or      ecx, 0FFFFFFFFh
0x18005b19a  lea     x2, [this+2]
0x18005b19e  xor     y1, y1
0x18005b1a1  test    edi, edi
0x18005b1a3  jnz     short loc_18005B1AC
0x18005b1a5  mov     [rsp+110h+var_CC], y1
0x18005b1aa  jmp     short loc_18005B1B8
0x18005b1ac  mov     x1, ecx
0x18005b1ae  test    edi, edi
0x18005b1b0  cmovg   x1, x2
0x18005b1b4  mov     [rsp+110h+var_CC], x1
0x18005b1b8  test    ebx, ebx
0x18005b1ba  jnz     short loc_18005B1C3
0x18005b1bc  mov     [rsp+110h+var_D0], y1
0x18005b1c1  jmp     short loc_18005B1CB
0x18005b1c3  cmovg   ecx, x2
0x18005b1c7  mov     [rsp+110h+var_D0], ecx
0x18005b1cb  test    r12d, r12d
0x18005b1ce  jnz     short loc_18005B1D8
0x18005b1d0  test    eax, eax
0x18005b1d2  jz      loc_18005B4D0
0x18005b1d8  mov     eax, esi
0x18005b1da  mov     [rbp+47h+rect.left], eax
0x18005b1dd  mov     r12d, r14d
0x18005b1e0  mov     [rbp+47h+rect.top], r14d
0x18005b1e4  mov     edi, r15d
0x18005b1e7  mov     ebx, r13d
0x18005b1ea  cmp     esi, r15d
0x18005b1ed  jle     short loc_18005B1F7
0x18005b1ef  mov     edi, esi
0x18005b1f1  mov     eax, r15d
0x18005b1f4  mov     [rbp+47h+rect.left], eax
0x18005b1f7  cmp     r14d, r13d
0x18005b1fa  jle     short loc_18005B206
0x18005b1fc  mov     ebx, r14d
0x18005b1ff  mov     r12d, r13d
0x18005b202  mov     [rbp+47h+rect.top], r13d
0x18005b206  add     edi, x2
0x18005b209  mov     [rbp+47h+rect.right], edi
0x18005b20c  add     ebx, x2
0x18005b20f  mov     [rbp+47h+rect.bottom], ebx
0x18005b212  sub     ebx, r12d
0x18005b215  sub     edi, eax
0x18005b217  mov     [rsp+110h+size.cx], edi
0x18005b21b  mov     [rsp+110h+size.cy], ebx
0x18005b21f  jz      loc_18005B4D0
0x18005b225  test    ebx, ebx
0x18005b227  jz      loc_18005B4D0
0x18005b22d  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18005b234  mov     [rbp+47h+dcMem.__vftable], rax
0x18005b238  xorps   xmm0, xmm0
0x18005b23b  movdqu  xmmword ptr [rbp+47h+dcMem.m_hDC], xmm0
0x18005b240  mov     [rbp+47h+dcMem.m_bPrinting], y1
0x18005b244  mov     r15, [rbp+47h+var_78]
0x18005b248  mov     rax, [r15+8]
0x18005b24c  test    rax, rax
0x18005b24f  mov     this, r8
0x18005b252  jz      short loc_18005B258
0x18005b254  mov     this, [rax+8]; hdc
0x18005b258  call    cs:__imp_CreateCompatibleDC
0x18005b25e  mov     rdx, rax; hDC
0x18005b261  lea     this, [rbp+47h+dcMem]; this
0x18005b265  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18005b26a  xor     r13d, r13d
0x18005b26d  test    eax, eax
0x18005b26f  jnz     short loc_18005B276
0x18005b271  jmp     loc_18005B4AC
0x18005b276  mov     [rbp+47h+bmpMem.m_hObject], r13
0x18005b27a  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005b281  mov     [rbp+47h+bmpMem.__vftable], rax
0x18005b285  mov     this, [r15+8]
0x18005b289  mov     y1, ebx; cy
0x18005b28c  mov     x1, edi; cx
0x18005b28e  mov     this, [this+8]; hdc
0x18005b292  call    cs:__imp_CreateCompatibleBitmap
0x18005b298  mov     rdx, rax; hObject
0x18005b29b  lea     this, [rbp+47h+bmpMem]; this
0x18005b29f  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18005b2a4  test    eax, eax
0x18005b2a6  jnz     short loc_18005B2C2
0x18005b2a8  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005b2af  mov     [rbp+47h+bmpMem.__vftable], rax
0x18005b2b3  lea     this, [rbp+47h+bmpMem]; this
0x18005b2b7  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005b2bc  nop
0x18005b2bd  jmp     loc_18005B4AC
0x18005b2c2  mov     rdx, [rbp+47h+bmpMem.m_hObject]; h
0x18005b2c6  mov     this, [rbp+47h+dcMem.m_hDC]; hdc
0x18005b2ca  call    cs:__imp_SelectObject
0x18005b2d0  mov     this, rax; h
0x18005b2d3  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18005b2d8  mov     [rbp+47h+var_70], rax
0x18005b2dc  test    rax, rax
0x18005b2df  jz      loc_18005B4F0
0x18005b2e5  lea     rdx, [rbp+47h+pBits]; pBits
0x18005b2e9  lea     this, [rsp+110h+size]; size
0x18005b2ee  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@AEBVCSize@@PEAPEAX@Z; CDrawingManager::CreateBitmap_32(CSize const &,void * *)
0x18005b2f3  mov     [rbp+47h+ho], rax
0x18005b2f7  test    rax, rax
0x18005b2fa  jz      loc_18005B497
0x18005b300  mov     rdi, [rbp+47h+pBits]
0x18005b304  test    rdi, rdi
0x18005b307  jz      loc_18005B497
0x18005b30d  mov     rdx, rax; h
0x18005b310  mov     this, [rbp+47h+dcMem.m_hDC]; hdc
0x18005b314  call    cs:__imp_SelectObject
0x18005b31a  mov     x1, [rsp+110h+var_DC]
0x18005b31e  mov     r10d, x1
0x18005b321  mov     eax, [rsp+110h+var_E0]
0x18005b325  cmp     eax, x1
0x18005b327  jle     short loc_18005B32E
0x18005b329  mov     r10d, eax
0x18005b32c  mov     eax, x1
0x18005b32e  add     eax, eax
0x18005b330  mov     [rbp+47h+var_80], eax
0x18005b333  mov     r11d, eax
0x18005b336  sub     r11d, r10d
0x18005b339  mov     [rsp+110h+var_C8], 1
0x18005b341  mov     ecx, [rbp+47h+arg_28]
0x18005b344  movzx   y1, cx
0x18005b348  and     y1, 0FFFFFF00h
0x18005b34f  movzx   eax, cl
0x18005b352  or      eax, 0FFFFFF00h
0x18005b357  shl     eax, 10h
0x18005b35a  or      y1, eax
0x18005b35d  shr     ecx, 10h
0x18005b360  movzx   eax, cl
0x18005b363  or      y1, eax
0x18005b366  mov     x2, [rbp+47h+rect.left]
0x18005b36a  mov     ebx, [rsp+110h+var_D0]
0x18005b36e  mov     r13d, [rsp+110h+var_CC]
0x18005b373  mov     r15d, [rsp+110h+size.cx]
0x18005b378  mov     eax, r12d
0x18005b37b  sub     eax, r14d
0x18005b37e  mov     ecx, [rsp+110h+size.cy]
0x18005b382  dec     ecx
0x18005b384  add     ecx, eax
0x18005b386  imul    ecx, r15d
0x18005b38a  movsxd  rdx, ecx
0x18005b38d  mov     eax, esi
0x18005b38f  sub     eax, x2
0x18005b392  cdqe
0x18005b394  add     rdx, rax
0x18005b397  mov     [rdi+rdx*4], y1
0x18005b39b  test    r11d, r11d
0x18005b39e  js      short loc_18005B3CE
0x18005b3a0  lea     x1, [r10+r10]
0x18005b3a4  mov     x2, [rsp+110h+var_E0]
0x18005b3a9  mov     edi, [rsp+110h+var_DC]
0x18005b3ad  mov     ecx, esi
0x18005b3af  lea     eax, [r14+rbx]
0x18005b3b3  cmp     x2, edi
0x18005b3b6  cmovle  r14d, eax
0x18005b3ba  lea     esi, [rsi+r13]
0x18005b3be  cmovle  esi, ecx
0x18005b3c1  sub     r11d, x1
0x18005b3c4  jns     short loc_18005B3AD
0x18005b3c6  mov     x2, [rbp+47h+rect.left]
0x18005b3ca  mov     rdi, [rbp+47h+pBits]
0x18005b3ce  mov     eax, r14d
0x18005b3d1  add     r14d, ebx
0x18005b3d4  mov     ecx, [rsp+110h+var_E0]
0x18005b3d8  cmp     ecx, [rsp+110h+var_DC]
0x18005b3dc  cmovle  r14d, eax
0x18005b3e0  lea     eax, [rsi+r13]
0x18005b3e4  cmovle  esi, eax
0x18005b3e7  add     r11d, [rbp+47h+var_80]
0x18005b3eb  mov     eax, [rsp+110h+var_C8]
0x18005b3ef  inc     eax
0x18005b3f1  mov     [rsp+110h+var_C8], eax
0x18005b3f5  cmp     eax, r10d
0x18005b3f8  jle     loc_18005B378
0x18005b3fe  sub     r12d, r14d
0x18005b401  mov     eax, [rsp+110h+size.cy]
0x18005b405  dec     eax
0x18005b407  add     eax, r12d
0x18005b40a  mov     ecx, [rsp+110h+size.cx]
0x18005b40e  imul    eax, ecx
0x18005b411  movsxd  rdx, eax
0x18005b414  sub     esi, x2
0x18005b417  movsxd  rax, esi
0x18005b41a  add     rdx, rax
0x18005b41d  mov     [rdi+rdx*4], y1
0x18005b421  xor     ebx, ebx
0x18005b423  mov     [rbp+47h+pBits], rbx
0x18005b427  mov     [rbp+47h+var_58], ecx
0x18005b42a  mov     rax, qword ptr [rsp+110h+size.cx]
0x18005b42f  shr     rax, 20h
0x18005b433  mov     [rbp+47h+var_54], eax
0x18005b436  lea     rax, [rbp+47h+pBits]
0x18005b43a  mov     [rsp+110h+rectSrc], rax; rectSrc
0x18005b43f  lea     r9, [rbp+47h+dcMem]; pSrcDC
0x18005b443  lea     r8, [rbp+47h+rect]; rectDst
0x18005b447  mov     rax, [rbp+47h+var_78]
0x18005b44b  mov     rdx, [rax+8]; pDstDC
0x18005b44f  mov     this, rax; this
0x18005b452  call    ?DrawAlpha@CDrawingManager@@QEAAXPEAVCDC@@AEBVCRect@@01@Z; CDrawingManager::DrawAlpha(CDC *,CRect const &,CDC *,CRect const &)
0x18005b457  mov     rdx, [rbp+47h+var_70]
0x18005b45b  mov     rdx, [rdx+8]; h
0x18005b45f  mov     this, [rbp+47h+dcMem.m_hDC]; hdc
0x18005b463  call    cs:__imp_SelectObject
0x18005b469  mov     this, rax; h
0x18005b46c  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18005b471  mov     this, [rbp+47h+ho]; ho
0x18005b475  call    cs:__imp_DeleteObject
0x18005b47b  nop
0x18005b47c  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005b483  mov     [rbp+47h+bmpMem.__vftable], rax
0x18005b487  lea     this, [rbp+47h+bmpMem]; this
0x18005b48b  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005b490  nop
0x18005b491  cmp     [rbp+47h+dcMem.m_hDC], rbx
0x18005b495  jmp     short loc_18005B4B0
0x18005b497  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005b49e  mov     [rbp+47h+bmpMem.__vftable], rax
0x18005b4a2  lea     this, [rbp+47h+bmpMem]; this
0x18005b4a6  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005b4ab  nop
0x18005b4ac  cmp     [rbp+47h+dcMem.m_hDC], r13
0x18005b4b0  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18005b4b7  mov     [rbp+47h+dcMem.__vftable], rax
0x18005b4bb  jz      short loc_18005B4D0
0x18005b4bd  lea     this, [rbp+47h+dcMem]; this
0x18005b4c1  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18005b4c6  mov     this, rax; hdc
0x18005b4c9  call    cs:__imp_DeleteDC
0x18005b4cf  nop
0x18005b4d0  mov     this, [rbp+47h+var_50]
0x18005b4d4  xor     this, rsp; StackCookie
0x18005b4d7  call    __security_check_cookie
0x18005b4dc  add     rsp, 0D8h
0x18005b4e3  pop     r15
0x18005b4e5  pop     r14
0x18005b4e7  pop     r13
0x18005b4e9  pop     r12
0x18005b4eb  pop     rdi
0x18005b4ec  pop     rsi
0x18005b4ed  pop     rbx
0x18005b4ee  pop     rbp
0x18005b4ef  retn
0x18005b4f0  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```

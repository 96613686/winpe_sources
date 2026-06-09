# CImageList::_GenerateAlphaForImageUsingMask(int,int)

- ea: `0x1800a88c8`
- end: `0x1800a8cbb`
- name: `?_GenerateAlphaForImageUsingMask@CImageList@@IEAAXHH@Z`
- size: `1011`
- prototype: `void __fastcall(CImageList *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010c30`
- `0x180078410`
- `0x18007a9d4`

## callees

- `0x180010040`
- `0x18008e190`
- `0x1800a88c8`
- `0x1800ad31c`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800a8ba2`
- `GDI32!DeleteObject` at `0x1800a8ba2`
- `GDI32!SetBkColor` at `0x1800a8a69`
- `GDI32!SetBkColor` at `0x1800a8a69`
- `GDI32!SetTextColor` at `0x1800a8a5e`
- `GDI32!SetTextColor` at `0x1800a8a5e`
- `GDI32!SelectObject` at `0x1800a8a4c`
- `GDI32!SelectObject` at `0x1800a8b99`
- `GDI32!SelectObject` at `0x1800a8a4c`
- `GDI32!SelectObject` at `0x1800a8b99`
- `GDI32!DeleteDC` at `0x1800a8bab`
- `GDI32!DeleteDC` at `0x1800a8bab`
- `GDI32!CreateCompatibleDC` at `0x1800a8a06`
- `GDI32!CreateCompatibleDC` at `0x1800a8a06`
- `GDI32!BitBlt` at `0x1800a8aaa`
- `GDI32!BitBlt` at `0x1800a8aaa`
- `GDI32!CreateDIBSection` at `0x1800a8a34`
- `GDI32!CreateDIBSection` at `0x1800a8a34`
- `USER32!SetRect` at `0x1800a893b`
- `USER32!SetRect` at `0x1800a8985`
- `USER32!SetRect` at `0x1800a893b`
- `USER32!SetRect` at `0x1800a8985`

## pseudocode

```c
void __fastcall CImageList::_GenerateAlphaForImageUsingMask(CImageList *this, int a2, int a3)
{
  LONG v3; // r15d
  int v4; // r13d
  int v7; // ecx
  int v8; // r8d
  signed int v9; // ecx
  LONG v10; // ecx
  LONG v11; // eax
  HDC CompatibleDC; // rax
  HDC v13; // rsi
  HBITMAP v14; // rax
  HBITMAP v15; // r14
  int v16; // r9d
  int v17; // ecx
  int v18; // r10d
  int v19; // r15d
  int v20; // r11d
  __int64 v21; // rdx
  __int64 v22; // r13
  int v23; // ecx
  unsigned int v24; // edx
  unsigned int v25; // edx
  int v26; // esi
  int v27; // r14d
  __int64 v28; // r10
  int v29; // eax
  __int64 v30; // r11
  int v31; // eax
  unsigned int v32; // r9d
  HGDIOBJ h; // [rsp+60h] [rbp-39h]
  struct tagRECT v35; // [rsp+68h] [rbp-31h] BYREF
  void *ppvBits; // [rsp+78h] [rbp-21h] BYREF
  struct tagRECT rc; // [rsp+80h] [rbp-19h] BYREF
  BITMAPINFO pbmi; // [rsp+90h] [rbp-9h] BYREF

  v3 = 0;
  v4 = a3;
  rc = 0;
  v35 = 0;
  if ( a2 >= 0 && a2 < *((_DWORD *)this + 29) )
    SetRect(
      &rc,
      0,
      a2 * *((_DWORD *)this + 33),
      *((_DWORD *)this + 32),
      a2 * *((_DWORD *)this + 33) + *((_DWORD *)this + 33));
  if ( v4 )
  {
    v9 = (unsigned int)CImageList::_GetSpareImageRectInverted(this, &v35) == 0 ? 0x80004005 : 0;
  }
  else if ( a2 < 0 || a2 >= *((_DWORD *)this + 29) )
  {
    v9 = -2147467259;
  }
  else
  {
    v7 = *((_DWORD *)this + 33);
    v8 = v7 * (~a2 + *((_DWORD *)this + 30));
    SetRect(&v35, 0, v8, *((_DWORD *)this + 32), v8 + v7);
    v9 = 0;
  }
  if ( v9 >= 0 )
  {
    v10 = *((_DWORD *)this + 32);
    v11 = *((_DWORD *)this + 33);
    pbmi.bmiHeader.biHeight = v11;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biSize = 40;
    pbmi.bmiHeader.biWidth = v10;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    if ( *((_QWORD *)this + 21) )
    {
      CompatibleDC = CreateCompatibleDC(*((HDC *)this + 25));
      v13 = CompatibleDC;
      if ( CompatibleDC )
      {
        ppvBits = 0;
        v14 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
        v15 = v14;
        if ( v14 )
        {
          h = SelectObject(v13, v14);
          SetTextColor(v13, 0xFFFFFFu);
          SetBkColor(v13, 0);
          BitBlt(
            v13,
            0,
            0,
            *((_DWORD *)this + 32),
            *((_DWORD *)this + 33),
            *((HDC *)this + 25),
            rc.left,
            rc.top,
            0xCC0020u);
          v16 = 0;
          if ( *((int *)this + 33) > 0 )
          {
            do
            {
              v17 = *((_DWORD *)this + 32);
              v18 = 0;
              v19 = v16 * v17;
              v20 = v17 * (v16 + v35.top);
              if ( v17 > 0 )
              {
                do
                {
                  v21 = *((_QWORD *)this + 23);
                  v22 = v20 + v18 + v35.left;
                  if ( *((_BYTE *)ppvBits + 4 * v18 + 4 * v19) )
                  {
                    v23 = *(_DWORD *)(v21 + 4 * v22) >> 8;
                    v24 = 255 * (*(_DWORD *)(v21 + 4 * v22) & 0xFF00FF) + 8388736;
                    v25 = ((v24 + ((v24 >> 8) & 0xFF00FF)) >> 8)
                        ^ ((unsigned __int16)((v24 + ((v24 >> 8) & 0xFF00FF)) >> 8)
                         ^ (unsigned __int16)(255 * (unsigned __int8)v23
                                            + 128
                                            + (unsigned __int8)((unsigned __int16)(255 * (unsigned __int8)v23 + 128) >> 8)))
                        & 0xFF00
                        | 0xFF000000;
                  }
                  else
                  {
                    v25 = 0;
                  }
                  ++v18;
                  *(_DWORD *)(*((_QWORD *)this + 23) + 4 * v22) = v25;
                }
                while ( v18 < *((_DWORD *)this + 32) );
              }
              ++v16;
            }
            while ( v16 < *((_DWORD *)this + 33) );
            v4 = a3;
          }
          SelectObject(v13, h);
          DeleteObject(v15);
        }
        DeleteDC(v13);
      }
    }
    else if ( v11 > 0 )
    {
      v26 = 0;
      while ( 1 )
      {
        v27 = v10 * (v26 + v35.top);
        if ( v10 > 0 )
        {
          do
          {
            v28 = *((_QWORD *)this + 23);
            v29 = v35.left + v3 + v27;
            ++v3;
            v30 = v29;
            v31 = *(_DWORD *)(v28 + 4LL * v29);
            v32 = ((255 * (v31 & 0xFF00FFu) + 8388736) >> 8) & 0xFF00FF;
            *(_DWORD *)(v28 + 4 * v30) = ((255 * (v31 & 0xFF00FF) + 8388736 + v32) >> 8)
                                       ^ ((unsigned __int16)((255 * (v31 & 0xFF00FF) + 8388736 + v32) >> 8)
                                        ^ (unsigned __int16)(255 * BYTE1(v31)
                                                           + 128
                                                           + (unsigned __int8)((unsigned __int16)(255 * BYTE1(v31) + 128) >> 8)))
                                       & 0xFF00
                                       | 0xFF000000;
            v10 = *((_DWORD *)this + 32);
          }
          while ( v3 < v10 );
        }
        if ( ++v26 >= *((_DWORD *)this + 33) )
          break;
        v3 = 0;
      }
      v4 = a3;
    }
    if ( !v4 )
    {
      CImageList::_SetItemMaskedFlags(this, a2, 1u, 1u);
      CImageList::_PreProcessImage(this, a2);
    }
  }
}

```

## disassembly

```asm
0x1800a88c8  mov     [rsp-8+arg_10], rbx
0x1800a88cd  mov     [rsp-8+arg_18], rsi
0x1800a88d2  push    rbp
0x1800a88d3  push    rdi
0x1800a88d4  push    r13
0x1800a88d6  push    r14
0x1800a88d8  push    r15
0x1800a88da  lea     rbp, [rsp-37h]
0x1800a88df  sub     rsp, 0D0h
0x1800a88e6  mov     rax, cs:__security_cookie
0x1800a88ed  xor     rax, rsp
0x1800a88f0  mov     [rbp+57h+var_30], rax
0x1800a88f4  xor     r15d, r15d
0x1800a88f7  mov     [rbp+57h+var_A0], r8d
0x1800a88fb  xorps   xmm0, xmm0
0x1800a88fe  xorps   xmm1, xmm1
0x1800a8901  mov     r13d, r8d
0x1800a8904  mov     edi, edx
0x1800a8906  mov     rbx, rcx
0x1800a8909  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800a890d  movups  xmmword ptr [rbp+57h+var_88.left], xmm1
0x1800a8911  test    edx, edx
0x1800a8913  js      short loc_1800A8941
0x1800a8915  cmp     edx, [rcx+74h]
0x1800a8918  jge     short loc_1800A8941
0x1800a891a  mov     eax, [rcx+84h]
0x1800a8920  xor     edx, edx; xLeft
0x1800a8922  mov     r9d, [rcx+80h]; xRight
0x1800a8929  mov     r8d, eax
0x1800a892c  imul    r8d, edi; yTop
0x1800a8930  lea     rcx, [rbp+57h+rc]; lprc
0x1800a8934  add     eax, r8d
0x1800a8937  mov     [rsp+0F0h+yBottom], eax; yBottom
0x1800a893b  call    cs:__imp_SetRect
0x1800a8941  test    r13d, r13d
0x1800a8944  jnz     loc_1800A8BE0
0x1800a894a  test    edi, edi
0x1800a894c  js      loc_1800A8BFD
0x1800a8952  cmp     edi, [rbx+74h]
0x1800a8955  jge     loc_1800A8BFD
0x1800a895b  mov     ecx, [rbx+84h]
0x1800a8961  mov     eax, edi
0x1800a8963  mov     r8d, [rbx+78h]
0x1800a8967  not     eax
0x1800a8969  mov     r9d, [rbx+80h]; xRight
0x1800a8970  add     r8d, eax
0x1800a8973  imul    r8d, ecx; yTop
0x1800a8977  xor     edx, edx; xLeft
0x1800a8979  lea     eax, [r8+rcx]
0x1800a897d  lea     rcx, [rbp+57h+var_88]; lprc
0x1800a8981  mov     [rsp+0F0h+yBottom], eax; yBottom
0x1800a8985  call    cs:__imp_SetRect
0x1800a898b  mov     ecx, r15d
0x1800a898e  test    ecx, ecx
0x1800a8990  jns     short loc_1800A89BA
0x1800a8992  mov     rcx, [rbp+57h+var_30]
0x1800a8996  xor     rcx, rsp; StackCookie
0x1800a8999  call    __security_check_cookie
0x1800a899e  lea     r11, [rsp+0F0h+var_20]
0x1800a89a6  mov     rbx, [r11+40h]
0x1800a89aa  mov     rsi, [r11+48h]
0x1800a89ae  mov     rsp, r11
0x1800a89b1  pop     r15
0x1800a89b3  pop     r14
0x1800a89b5  pop     r13
0x1800a89b7  pop     rdi
0x1800a89b8  pop     rbp
0x1800a89b9  retn
0x1800a89ba  mov     ecx, [rbx+80h]
0x1800a89c0  xor     eax, eax
0x1800a89c2  xorps   xmm0, xmm0
0x1800a89c5  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x1800a89c9  mov     r8d, 1
0x1800a89cf  mov     eax, [rbx+84h]
0x1800a89d5  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x1800a89d9  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1800a89dc  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x1800a89e0  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800a89e7  mov     [rbp+57h+pbmi.bmiHeader.biWidth], ecx
0x1800a89ea  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1800a89f2  cmp     [rbx+0A8h], r15
0x1800a89f9  jz      loc_1800A8C07
0x1800a89ff  mov     rcx, [rbx+0C8h]; hdc
0x1800a8a06  call    cs:__imp_CreateCompatibleDC
0x1800a8a0c  mov     rsi, rax
0x1800a8a0f  test    rax, rax
0x1800a8a12  jz      loc_1800A8BB1
0x1800a8a18  mov     [rsp+0F0h+offset], r15d; offset
0x1800a8a1d  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x1800a8a21  xor     r8d, r8d; usage
0x1800a8a24  mov     qword ptr [rsp+0F0h+yBottom], r15; hSection
0x1800a8a29  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1800a8a2d  mov     [rbp+57h+ppvBits], r15
0x1800a8a31  mov     rcx, rax; hdc
0x1800a8a34  call    cs:__imp_CreateDIBSection
0x1800a8a3a  mov     r14, rax
0x1800a8a3d  test    rax, rax
0x1800a8a40  jz      loc_1800A8BA8
0x1800a8a46  mov     rdx, rax; h
0x1800a8a49  mov     rcx, rsi; hdc
0x1800a8a4c  call    cs:__imp_SelectObject
0x1800a8a52  mov     edx, 0FFFFFFh; color
0x1800a8a57  mov     rcx, rsi; hdc
0x1800a8a5a  mov     [rbp+57h+h], rax
0x1800a8a5e  call    cs:__imp_SetTextColor
0x1800a8a64  xor     edx, edx; color
0x1800a8a66  mov     rcx, rsi; hdc
0x1800a8a69  call    cs:__imp_SetBkColor
0x1800a8a6f  mov     ecx, [rbp+57h+rc.top]
0x1800a8a72  xor     r8d, r8d; y
0x1800a8a75  mov     r9d, [rbx+80h]; cx
0x1800a8a7c  xor     edx, edx; x
0x1800a8a7e  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x1800a8a86  mov     [rsp+0F0h+y1], ecx; y1
0x1800a8a8a  mov     ecx, [rbp+57h+rc.left]
0x1800a8a8d  mov     [rsp+0F0h+x1], ecx; x1
0x1800a8a91  mov     rcx, [rbx+0C8h]
0x1800a8a98  mov     qword ptr [rsp+0F0h+offset], rcx; hdcSrc
0x1800a8a9d  mov     ecx, [rbx+84h]
0x1800a8aa3  mov     [rsp+0F0h+yBottom], ecx; cy
0x1800a8aa7  mov     rcx, rsi; hdc
0x1800a8aaa  call    cs:__imp_BitBlt
0x1800a8ab0  mov     r9d, r15d
0x1800a8ab3  cmp     [rbx+84h], r15d
0x1800a8aba  jle     loc_1800A8B92
0x1800a8ac0  mov     ecx, [rbx+80h]
0x1800a8ac6  xor     r10d, r10d
0x1800a8ac9  mov     r11d, [rbp+57h+var_88.top]
0x1800a8acd  mov     r15d, ecx
0x1800a8ad0  add     r11d, r9d
0x1800a8ad3  imul    r15d, r9d
0x1800a8ad7  imul    r11d, ecx
0x1800a8adb  test    ecx, ecx
0x1800a8add  jle     loc_1800A8B7E
0x1800a8ae3  mov     ecx, [rbp+57h+var_88.left]
0x1800a8ae6  lea     eax, [r10+r15]
0x1800a8aea  mov     rdx, [rbx+0B8h]
0x1800a8af1  add     ecx, r10d
0x1800a8af4  add     ecx, r11d
0x1800a8af7  mov     [rbp+57h+var_98], rdx
0x1800a8afb  movsxd  r13, ecx
0x1800a8afe  movsxd  rcx, eax
0x1800a8b01  mov     rax, [rbp+57h+ppvBits]
0x1800a8b05  cmp     byte ptr [rax+rcx*4], 0
0x1800a8b09  jz      loc_1800A8BDC
0x1800a8b0f  mov     ecx, [rdx+r13*4]
0x1800a8b13  mov     eax, ecx
0x1800a8b15  and     eax, 0FF00FFh
0x1800a8b1a  shr     ecx, 8
0x1800a8b1d  imul    edx, eax, 0FFh
0x1800a8b23  movzx   eax, cl
0x1800a8b26  imul    ecx, eax, 0FFh
0x1800a8b2c  add     edx, 800080h
0x1800a8b32  mov     r8d, edx
0x1800a8b35  shr     r8d, 8
0x1800a8b39  sub     ecx, 0FFFFFF80h
0x1800a8b3c  and     r8d, 0FF00FFh
0x1800a8b43  mov     eax, ecx
0x1800a8b45  add     r8d, edx
0x1800a8b48  shr     eax, 8
0x1800a8b4b  shr     r8d, 8
0x1800a8b4f  movzx   edx, al
0x1800a8b52  add     edx, ecx
0x1800a8b54  xor     edx, r8d
0x1800a8b57  and     edx, 0FF00h
0x1800a8b5d  xor     edx, r8d
0x1800a8b60  or      edx, 0FF000000h
0x1800a8b66  mov     rax, [rbp+57h+var_98]
0x1800a8b6a  inc     r10d
0x1800a8b6d  mov     [rax+r13*4], edx
0x1800a8b71  cmp     r10d, [rbx+80h]
0x1800a8b78  jl      loc_1800A8AE3
0x1800a8b7e  inc     r9d
0x1800a8b81  cmp     r9d, [rbx+84h]
0x1800a8b88  jl      loc_1800A8AC0
0x1800a8b8e  mov     r13d, [rbp+57h+var_A0]
0x1800a8b92  mov     rdx, [rbp+57h+h]; h
0x1800a8b96  mov     rcx, rsi; hdc
0x1800a8b99  call    cs:__imp_SelectObject
0x1800a8b9f  mov     rcx, r14; ho
0x1800a8ba2  call    cs:__imp_DeleteObject
0x1800a8ba8  mov     rcx, rsi; hdc
0x1800a8bab  call    cs:__imp_DeleteDC
0x1800a8bb1  mov     r8d, 1; unsigned int
0x1800a8bb7  test    r13d, r13d
0x1800a8bba  jnz     loc_1800A8992
0x1800a8bc0  mov     r9d, r8d; unsigned int
0x1800a8bc3  mov     edx, edi; int
0x1800a8bc5  mov     rcx, rbx; this
0x1800a8bc8  call    ?_SetItemMaskedFlags@CImageList@@IEAAXHKK@Z; CImageList::_SetItemMaskedFlags(int,ulong,ulong)
0x1800a8bcd  mov     edx, edi; int
0x1800a8bcf  mov     rcx, rbx; this
0x1800a8bd2  call    ?_PreProcessImage@CImageList@@IEAAHH@Z; CImageList::_PreProcessImage(int)
0x1800a8bd7  jmp     loc_1800A8992
0x1800a8bdc  xor     edx, edx
0x1800a8bde  jmp     short loc_1800A8B66
0x1800a8be0  lea     rdx, [rbp+57h+var_88]; struct tagRECT *
0x1800a8be4  mov     rcx, rbx; this
0x1800a8be7  call    ?_GetSpareImageRectInverted@CImageList@@IEAAHPEAUtagRECT@@@Z; CImageList::_GetSpareImageRectInverted(tagRECT *)
0x1800a8bec  neg     eax
0x1800a8bee  sbb     ecx, ecx
0x1800a8bf0  not     ecx
0x1800a8bf2  and     ecx, 80004005h
0x1800a8bf8  jmp     loc_1800A898E
0x1800a8bfd  mov     ecx, 80004005h
0x1800a8c02  jmp     loc_1800A898E
0x1800a8c07  test    eax, eax
0x1800a8c09  jle     short loc_1800A8BB7
0x1800a8c0b  mov     esi, r15d
0x1800a8c0e  mov     r13d, r8d
0x1800a8c11  jmp     short loc_1800A8C16
0x1800a8c13  xor     r15d, r15d
0x1800a8c16  mov     r14d, [rbp+57h+var_88.top]
0x1800a8c1a  add     r14d, esi
0x1800a8c1d  imul    r14d, ecx
0x1800a8c21  test    ecx, ecx
0x1800a8c23  jle     short loc_1800A8CA3
0x1800a8c25  mov     r10, [rbx+0B8h]
0x1800a8c2c  lea     eax, [r15+r14]
0x1800a8c30  add     eax, [rbp+57h+var_88.left]
0x1800a8c33  add     r15d, r13d
0x1800a8c36  movsxd  r11, eax
0x1800a8c39  mov     ecx, [r10+r11*4]
0x1800a8c3d  mov     eax, ecx
0x1800a8c3f  shr     ecx, 8
0x1800a8c42  and     eax, 0FF00FFh
0x1800a8c47  imul    edx, eax, 0FFh
0x1800a8c4d  movzx   eax, cl
0x1800a8c50  imul    r8d, eax, 0FFh
0x1800a8c57  add     edx, 800080h
0x1800a8c5d  mov     r9d, edx
0x1800a8c60  shr     r9d, 8
0x1800a8c64  sub     r8d, 0FFFFFF80h
0x1800a8c68  and     r9d, 0FF00FFh
0x1800a8c6f  mov     eax, r8d
0x1800a8c72  shr     eax, 8
0x1800a8c75  add     r9d, edx
0x1800a8c78  shr     r9d, 8
0x1800a8c7c  movzx   ecx, al
0x1800a8c7f  add     ecx, r8d
0x1800a8c82  xor     ecx, r9d
0x1800a8c85  and     ecx, 0FF00h
0x1800a8c8b  xor     ecx, r9d
0x1800a8c8e  or      ecx, 0FF000000h
0x1800a8c94  mov     [r10+r11*4], ecx
0x1800a8c98  mov     ecx, [rbx+80h]
0x1800a8c9e  cmp     r15d, ecx
0x1800a8ca1  jl      short loc_1800A8C25
0x1800a8ca3  add     esi, r13d
0x1800a8ca6  cmp     esi, [rbx+84h]
0x1800a8cac  jl      loc_1800A8C13
0x1800a8cb2  mov     r13d, [rbp+57h+var_A0]
0x1800a8cb6  jmp     loc_1800A8BB1
```

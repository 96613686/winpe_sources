# ImageList_GetIconWithAlpha(_IMAGELIST *,int,uint,HICON__ * *)

- ea: `0x1804348f0`
- end: `0x180434c97`
- name: `?ImageList_GetIconWithAlpha@@YAJPEAU_IMAGELIST@@HIPEAPEAUHICON__@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(HIMAGELIST himl, int, unsigned int, HICON *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1802b24a4`
- `0x180434f6c`
- `0x18043dbbc`

## callees

- `0x1804348f0`
- `0x180435004`
- `0x18047cd48`
- `0x18047d034`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `GDI32!PatBlt` at `0x180434afc`
- `GDI32!PatBlt` at `0x180434b4c`
- `GDI32!PatBlt` at `0x180434afc`
- `GDI32!PatBlt` at `0x180434b4c`
- `GDI32!CreateDIBSection` at `0x180434a5b`
- `GDI32!CreateDIBSection` at `0x180434a5b`
- `GDI32!CreateBitmap` at `0x180434a9a`
- `GDI32!CreateBitmap` at `0x180434a9a`
- `GDI32!DeleteObject` at `0x180434c1c`
- `GDI32!DeleteObject` at `0x180434c47`
- `GDI32!DeleteObject` at `0x180434c1c`
- `GDI32!DeleteObject` at `0x180434c47`
- `GDI32!SelectObject` at `0x180434ad2`
- `GDI32!SelectObject` at `0x180434b25`
- `GDI32!SelectObject` at `0x180434b72`
- `GDI32!SelectObject` at `0x180434ad2`
- `GDI32!SelectObject` at `0x180434b25`
- `GDI32!SelectObject` at `0x180434b72`
- `GDI32!DeleteDC` at `0x180434c2e`
- `GDI32!DeleteDC` at `0x180434c2e`
- `GDI32!CreateCompatibleDC` at `0x180434ab4`
- `GDI32!CreateCompatibleDC` at `0x180434ab4`
- `USER32!CreateIconIndirect` at `0x180434c05`
- `USER32!CreateIconIndirect` at `0x180434c05`
- `USER32!ReleaseDC` at `0x180434a6f`
- `USER32!ReleaseDC` at `0x180434a6f`
- `USER32!GetDC` at `0x180434a2b`
- `USER32!GetDC` at `0x180434a2b`

## pseudocode

```c
__int64 __fastcall ImageList_GetIconWithAlpha(HIMAGELIST himl, unsigned int a2, __int64 a3, HICON *a4)
{
  int v8; // ebx
  HICON v9; // r12
  int v10; // ebx
  void (__fastcall *v11)(void *, int *, int *); // rax
  unsigned int v12; // esi
  WORD v13; // ax
  HDC DC; // rax
  HDC v15; // rbx
  HBITMAP v16; // r15
  HBITMAP Bitmap; // r14
  HDC CompatibleDC; // rax
  HDC v19; // rsi
  HGDIOBJ v20; // rbx
  int v21; // r9d
  int v22; // r9d
  unsigned int v23; // r8d
  int v24; // r9d
  _BYTE *i; // r11
  unsigned int v26; // eax
  void *v27; // rcx
  int hSection; // [rsp+20h] [rbp-69h]
  int hSectiona; // [rsp+20h] [rbp-69h]
  int nHeight; // [rsp+30h] [rbp-59h] BYREF
  int nWidth; // [rsp+34h] [rbp-55h] BYREF
  void *ppv; // [rsp+38h] [rbp-51h] BYREF
  int v33; // [rsp+40h] [rbp-49h] BYREF
  int v34; // [rsp+44h] [rbp-45h]
  int v35; // [rsp+48h] [rbp-41h]
  void *ppvBits; // [rsp+50h] [rbp-39h] BYREF
  ICONINFO piconinfo; // [rsp+58h] [rbp-31h] BYREF
  BITMAPINFO pbmi; // [rsp+78h] [rbp-11h] BYREF

  ppv = 0;
  nWidth = 0;
  nHeight = 0;
  ppvBits = 0;
  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( !himl || !a4 )
    return 2147500035LL;
  *a4 = 0;
  HIMAGELIST_QueryInterface(himl, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppv);
  if ( ppv )
  {
    v33 = 0;
    v8 = (*(__int64 (__fastcall **)(void *, _QWORD, int *))(*(_QWORD *)ppv + 240LL))(ppv, a2, &v33);
    if ( v8 >= 0 )
    {
      v9 = 0;
      v10 = v33 & 1;
      v11 = *(void (__fastcall **)(void *, int *, int *))(*(_QWORD *)ppv + 128LL);
      v35 = v10;
      v11(ppv, &nWidth, &nHeight);
      pbmi.bmiHeader.biSize = 40;
      v12 = -2147024882;
      v34 = -2147024882;
      pbmi.bmiHeader.biWidth = nWidth;
      pbmi.bmiHeader.biHeight = nHeight;
      v13 = 32;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 1;
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      if ( !v10 )
        v13 = 24;
      pbmi.bmiHeader.biBitCount = v13;
      pbmi.bmiHeader.biCompression = 0;
      DC = GetDC(0);
      v15 = DC;
      if ( DC )
      {
        v16 = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
        ReleaseDC(0, v15);
        if ( v16 )
        {
          Bitmap = CreateBitmap(nWidth, nHeight, 1u, 1u, 0);
          if ( Bitmap )
          {
            CompatibleDC = CreateCompatibleDC(0);
            v19 = CompatibleDC;
            if ( CompatibleDC )
            {
              v20 = SelectObject(CompatibleDC, Bitmap);
              PatBlt(v19, 0, 0, nWidth, nHeight, 0xFF0062u);
              WimpyDraw((struct IImageList *)ppv, a2, v19, v21, hSection, 0x10u);
              SelectObject(v19, v16);
              PatBlt(v19, 0, 0, nWidth, nHeight, 0x42u);
              WimpyDraw((struct IImageList *)ppv, a2, v19, v22, hSectiona, 0);
              SelectObject(v19, v20);
              if ( v35 )
              {
                v23 = 0;
                v24 = nWidth * nHeight;
                for ( i = ppvBits; (int)v23 < v24; ++v23 )
                {
                  v26 = (unsigned __int8)i[4 * v23 + 3];
                  if ( (_BYTE)v26 )
                  {
                    i[4 * v23 + 2] = 255 * (unsigned int)(unsigned __int8)i[4 * v23 + 2] / v26;
                    i[4 * v23 + 1] = 255 * (unsigned int)(unsigned __int8)i[4 * v23 + 1] / v26;
                    i[4 * v23] = 255 * (unsigned int)(unsigned __int8)i[4 * v23] / v26;
                  }
                }
              }
              *(_QWORD *)&piconinfo.fIcon = 1;
              piconinfo.yHotspot = 0;
              piconinfo.hbmColor = v16;
              piconinfo.hbmMask = Bitmap;
              v9 = CreateIconIndirect(&piconinfo);
              if ( v9 )
              {
                DeleteObject(Bitmap);
                v34 = 0;
              }
              DeleteDC(v19);
              v12 = v34;
            }
            else
            {
              v12 = -2147024882;
            }
          }
          DeleteObject(v16);
        }
      }
      v27 = ppv;
      *a4 = v9;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
      return v12;
    }
    else
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v8;
    }
  }
  else
  {
    *a4 = ImageList_GetIcon(himl, a2, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x1804348f0  mov     [rsp-8+arg_10], rbx
0x1804348f5  push    rbp
0x1804348f6  push    rsi
0x1804348f7  push    rdi
0x1804348f8  push    r12
0x1804348fa  push    r13
0x1804348fc  push    r14
0x1804348fe  push    r15
0x180434900  lea     rbp, [rsp-27h]
0x180434905  sub     rsp, 0B0h
0x18043490c  mov     rax, cs:__security_cookie
0x180434913  xor     rax, rsp
0x180434916  mov     [rbp+57h+var_38], rax
0x18043491a  xor     r14d, r14d
0x18043491d  xorps   xmm0, xmm0
0x180434920  mov     [rbp+57h+ppv], r14
0x180434924  mov     rdi, r9
0x180434927  mov     [rbp+57h+nWidth], r14d
0x18043492b  mov     r13d, edx
0x18043492e  mov     [rbp+57h+nHeight], r14d
0x180434932  mov     rbx, rcx
0x180434935  mov     [rbp+57h+ppvBits], r14
0x180434939  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x18043493d  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x180434941  test    rcx, rcx
0x180434944  jz      loc_180434C6A
0x18043494a  test    r9, r9
0x18043494d  jz      loc_180434C6A
0x180434953  lea     r8, [rbp+57h+ppv]; ppv
0x180434957  mov     [r9], r14
0x18043495a  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x180434961  call    HIMAGELIST_QueryInterface
0x180434966  mov     rcx, [rbp+57h+ppv]
0x18043496a  mov     edx, r13d; i
0x18043496d  test    rcx, rcx
0x180434970  jnz     short loc_180434987
0x180434972  xor     r8d, r8d; flags
0x180434975  mov     rcx, rbx; himl
0x180434978  call    ImageList_GetIcon
0x18043497d  mov     [rdi], rax
0x180434980  xor     eax, eax
0x180434982  jmp     loc_180434C6F
0x180434987  mov     [rbp+57h+var_A0], r14d
0x18043498b  lea     r8, [rbp+57h+var_A0]
0x18043498f  mov     rax, [rcx]
0x180434992  mov     rax, [rax+0F0h]
0x180434999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043499e  mov     rcx, [rbp+57h+ppv]
0x1804349a2  mov     ebx, eax
0x1804349a4  test    eax, eax
0x1804349a6  jns     short loc_1804349BB
0x1804349a8  mov     rdx, [rcx]
0x1804349ab  mov     rax, [rdx+10h]
0x1804349af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804349b4  mov     eax, ebx
0x1804349b6  jmp     loc_180434C6F
0x1804349bb  mov     rax, [rcx]
0x1804349be  lea     r8, [rbp+57h+nHeight]
0x1804349c2  mov     ebx, [rbp+57h+var_A0]
0x1804349c5  lea     rdx, [rbp+57h+nWidth]
0x1804349c9  mov     r15d, 1
0x1804349cf  mov     r12, r14
0x1804349d2  and     ebx, r15d
0x1804349d5  mov     rax, [rax+80h]
0x1804349dc  mov     [rbp+57h+var_98], ebx
0x1804349df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804349e4  xor     eax, eax
0x1804349e6  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1804349ed  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x1804349f1  xorps   xmm0, xmm0
0x1804349f4  mov     eax, [rbp+57h+nWidth]
0x1804349f7  mov     esi, 8007000Eh
0x1804349fc  mov     [rbp+57h+var_9C], esi
0x1804349ff  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x180434a03  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x180434a06  mov     eax, [rbp+57h+nHeight]
0x180434a09  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x180434a0c  lea     eax, [r15+1Fh]
0x180434a10  mov     [rbp+57h+pbmi.bmiHeader.biPlanes], r15w
0x180434a15  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x180434a19  test    ebx, ebx
0x180434a1b  jnz     short loc_180434A21
0x180434a1d  lea     eax, [r15+17h]
0x180434a21  xor     ecx, ecx; hWnd
0x180434a23  mov     [rbp+57h+pbmi.bmiHeader.biBitCount], ax
0x180434a27  mov     [rbp+57h+pbmi.bmiHeader.biCompression], r14d
0x180434a2b  call    cs:__imp_GetDC
0x180434a32  nop     dword ptr [rax+rax+00h]
0x180434a37  mov     rbx, rax
0x180434a3a  test    rax, rax
0x180434a3d  jz      loc_180434C53
0x180434a43  mov     [rsp+0E0h+offset], r14d; offset
0x180434a48  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180434a4c  xor     r8d, r8d; usage
0x180434a4f  mov     [rsp+0E0h+hSection], r14; hSection
0x180434a54  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180434a58  mov     rcx, rax; hdc
0x180434a5b  call    cs:__imp_CreateDIBSection
0x180434a62  nop     dword ptr [rax+rax+00h]
0x180434a67  mov     rdx, rbx; hDC
0x180434a6a  xor     ecx, ecx; hWnd
0x180434a6c  mov     r15, rax
0x180434a6f  call    cs:__imp_ReleaseDC
0x180434a76  nop     dword ptr [rax+rax+00h]
0x180434a7b  test    r15, r15
0x180434a7e  jz      loc_180434C53
0x180434a84  mov     edx, [rbp+57h+nHeight]; nHeight
0x180434a87  mov     eax, 1
0x180434a8c  mov     ecx, [rbp+57h+nWidth]; nWidth
0x180434a8f  mov     r9d, eax; nBitCount
0x180434a92  mov     r8d, eax; nPlanes
0x180434a95  mov     [rsp+0E0h+hSection], r14; lpBits
0x180434a9a  call    cs:__imp_CreateBitmap
0x180434aa1  nop     dword ptr [rax+rax+00h]
0x180434aa6  mov     r14, rax
0x180434aa9  test    rax, rax
0x180434aac  jz      loc_180434C44
0x180434ab2  xor     ecx, ecx; hdc
0x180434ab4  call    cs:__imp_CreateCompatibleDC
0x180434abb  nop     dword ptr [rax+rax+00h]
0x180434ac0  mov     rsi, rax
0x180434ac3  test    rax, rax
0x180434ac6  jz      loc_180434C3F
0x180434acc  mov     rdx, r14; h
0x180434acf  mov     rcx, rax; hdc
0x180434ad2  call    cs:__imp_SelectObject
0x180434ad9  nop     dword ptr [rax+rax+00h]
0x180434ade  mov     ecx, [rbp+57h+nHeight]
0x180434ae1  xor     r8d, r8d; y
0x180434ae4  mov     r9d, [rbp+57h+nWidth]; w
0x180434ae8  xor     edx, edx; x
0x180434aea  mov     [rsp+0E0h+offset], 0FF0062h; rop
0x180434af2  mov     rbx, rax
0x180434af5  mov     dword ptr [rsp+0E0h+hSection], ecx; int
0x180434af9  mov     rcx, rsi; hdc
0x180434afc  call    cs:__imp_PatBlt
0x180434b03  nop     dword ptr [rax+rax+00h]
0x180434b08  mov     rcx, [rbp+57h+ppv]; struct IImageList *
0x180434b0c  mov     r8, rsi; HDC
0x180434b0f  mov     edx, r13d; int
0x180434b12  mov     [rsp+0E0h+offset], 10h; unsigned int
0x180434b1a  call    ?WimpyDraw@@YAJPEAUIImageList@@HPEAUHDC__@@HHI@Z; WimpyDraw(IImageList *,int,HDC__ *,int,int,uint)
0x180434b1f  mov     rdx, r15; h
0x180434b22  mov     rcx, rsi; hdc
0x180434b25  call    cs:__imp_SelectObject
0x180434b2c  nop     dword ptr [rax+rax+00h]
0x180434b31  mov     eax, [rbp+57h+nHeight]
0x180434b34  xor     r8d, r8d; y
0x180434b37  mov     r9d, [rbp+57h+nWidth]; w
0x180434b3b  xor     edx, edx; x
0x180434b3d  mov     rcx, rsi; hdc
0x180434b40  mov     [rsp+0E0h+offset], 42h ; 'B'; rop
0x180434b48  mov     dword ptr [rsp+0E0h+hSection], eax; int
0x180434b4c  call    cs:__imp_PatBlt
0x180434b53  nop     dword ptr [rax+rax+00h]
0x180434b58  mov     rcx, [rbp+57h+ppv]; struct IImageList *
0x180434b5c  mov     r8, rsi; HDC
0x180434b5f  mov     edx, r13d; int
0x180434b62  mov     [rsp+0E0h+offset], r12d; unsigned int
0x180434b67  call    ?WimpyDraw@@YAJPEAUIImageList@@HPEAUHDC__@@HHI@Z; WimpyDraw(IImageList *,int,HDC__ *,int,int,uint)
0x180434b6c  mov     rdx, rbx; h
0x180434b6f  mov     rcx, rsi; hdc
0x180434b72  call    cs:__imp_SelectObject
0x180434b79  nop     dword ptr [rax+rax+00h]
0x180434b7e  xor     ebx, ebx
0x180434b80  cmp     [rbp+57h+var_98], ebx
0x180434b83  jz      short loc_180434BEE
0x180434b85  mov     r9d, [rbp+57h+nHeight]
0x180434b89  mov     r8d, ebx
0x180434b8c  imul    r9d, [rbp+57h+nWidth]
0x180434b91  mov     r11, [rbp+57h+ppvBits]
0x180434b95  test    r9d, r9d
0x180434b98  jle     short loc_180434BEE
0x180434b9a  mov     r10d, r8d
0x180434b9d  movzx   eax, byte ptr [r11+r10*4+3]
0x180434ba3  test    al, al
0x180434ba5  jz      short loc_180434BE6
0x180434ba7  mov     ecx, eax
0x180434ba9  xor     edx, edx
0x180434bab  movzx   eax, byte ptr [r11+r10*4+2]
0x180434bb1  imul    eax, 0FFh
0x180434bb7  div     ecx
0x180434bb9  xor     edx, edx
0x180434bbb  mov     [r11+r10*4+2], al
0x180434bc0  movzx   eax, byte ptr [r11+r10*4+1]
0x180434bc6  imul    eax, 0FFh
0x180434bcc  div     ecx
0x180434bce  xor     edx, edx
0x180434bd0  mov     [r11+r10*4+1], al
0x180434bd5  movzx   eax, byte ptr [r11+r10*4]
0x180434bda  imul    eax, 0FFh
0x180434be0  div     ecx
0x180434be2  mov     [r11+r10*4], al
0x180434be6  inc     r8d
0x180434be9  cmp     r8d, r9d
0x180434bec  jl      short loc_180434B9A
0x180434bee  lea     rcx, [rbp+57h+piconinfo]; piconinfo
0x180434bf2  mov     qword ptr [rbp+57h+piconinfo.fIcon], 1
0x180434bfa  mov     [rbp+57h+piconinfo.yHotspot], ebx
0x180434bfd  mov     [rbp+57h+piconinfo.hbmColor], r15
0x180434c01  mov     [rbp+57h+piconinfo.hbmMask], r14
0x180434c05  call    cs:__imp_CreateIconIndirect
0x180434c0c  nop     dword ptr [rax+rax+00h]
0x180434c11  mov     r12, rax
0x180434c14  test    rax, rax
0x180434c17  jz      short loc_180434C2B
0x180434c19  mov     rcx, r14; ho
0x180434c1c  call    cs:__imp_DeleteObject
0x180434c23  nop     dword ptr [rax+rax+00h]
0x180434c28  mov     [rbp+57h+var_9C], ebx
0x180434c2b  mov     rcx, rsi; hdc
0x180434c2e  call    cs:__imp_DeleteDC
0x180434c35  nop     dword ptr [rax+rax+00h]
0x180434c3a  mov     esi, [rbp+57h+var_9C]
0x180434c3d  jmp     short loc_180434C44
0x180434c3f  mov     esi, 8007000Eh
0x180434c44  mov     rcx, r15; ho
0x180434c47  call    cs:__imp_DeleteObject
0x180434c4e  nop     dword ptr [rax+rax+00h]
0x180434c53  mov     rcx, [rbp+57h+ppv]
0x180434c57  mov     [rdi], r12
0x180434c5a  mov     rdx, [rcx]
0x180434c5d  mov     rax, [rdx+10h]
0x180434c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180434c66  mov     eax, esi
0x180434c68  jmp     short loc_180434C6F
0x180434c6a  mov     eax, 80004003h
0x180434c6f  mov     rcx, [rbp+57h+var_38]
0x180434c73  xor     rcx, rsp; StackCookie
0x180434c76  call    __security_check_cookie
0x180434c7b  mov     rbx, [rsp+0E0h+arg_10]
0x180434c83  add     rsp, 0B0h
0x180434c8a  pop     r15
0x180434c8c  pop     r14
0x180434c8e  pop     r13
0x180434c90  pop     r12
0x180434c92  pop     rdi
0x180434c93  pop     rsi
0x180434c94  pop     rbp
0x180434c95  retn
```

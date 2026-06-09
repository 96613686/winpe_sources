# DrawBlobD2D(COleObject *,HDC__ *,tagRECT *)

- ea: `0x180150e38`
- end: `0x180151188`
- name: `?DrawBlobD2D@@YAJPEAVCOleObject@@PEAUHDC__@@PEAUtagRECT@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(struct COleObject *, HDC hdcDest, struct tagRECT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180151664`

## callees

- `0x18000aebc`
- `0x18000f430`
- `0x18008a518`
- `0x1800983a0`
- `0x18009abd0`
- `0x1800cffe8`
- `0x18013ce80`
- `0x180150e38`
- `0x1801a9ad0`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180150f0e`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180150f0e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180150f44`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180151133`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180150f44`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180151133`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x180150f2e`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x180150f2e`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x180151120`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x180151120`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x180150e9f`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x180150eb5`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x180150e9f`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x180150eb5`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180151143`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180151152`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180151143`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180151152`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180150e88`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180150e88`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180150f59`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180150f59`

## pseudocode

```c
__int64 __fastcall DrawBlobD2D(struct COleObject *a1, HDC hdcDest, struct tagRECT *a3)
{
  CTxtEdit *v3; // r12
  HDC DC; // rdi
  int DeviceCaps; // ebx
  LONG v10; // eax
  LONG top; // ecx
  int v12; // r11d
  LONG v13; // eax
  LONG right; // ecx
  LONG v15; // eax
  LONG bottom; // ecx
  int v17; // r11d
  HDC hdcSrc; // r14
  struct ID2D1Factory *D2DFactory; // rax
  int v20; // eax
  struct ID2D1RenderTarget *v21; // rdx
  int v22; // ebx
  struct ITextRenderTarget *D2DTextRenderTarget; // rdi
  unsigned int BackColor; // eax
  CTextMarkContainer *v25; // rcx
  RichEdit *v26; // [rsp+60h] [rbp-49h] BYREF
  __int64 v27; // [rsp+68h] [rbp-41h] BYREF
  HGDIOBJ h; // [rsp+70h] [rbp-39h]
  HGDIOBJ ho; // [rsp+78h] [rbp-31h]
  struct tagRECT v30; // [rsp+80h] [rbp-29h] BYREF
  float v31[4]; // [rsp+90h] [rbp-19h] BYREF
  int v32; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v33; // [rsp+A4h] [rbp-5h]
  __int64 v34; // [rsp+ACh] [rbp+3h]
  __int64 v35; // [rsp+B4h] [rbp+Bh]

  v3 = (CTxtEdit *)*((_QWORD *)a1 + 6);
  if ( !CTxtEdit::GetTextMarkContainer(v3) )
    return 2147500037LL;
  DC = GetDC(0);
  DeviceCaps = GetDeviceCaps(DC, 88);
  GetDeviceCaps(DC, 90);
  v10 = CW32System::MulDivFunc(a3->left, DeviceCaps, 2540);
  top = a3->top;
  v30.left = v10;
  v13 = CW32System::MulDivFunc(top, v12, 2540);
  right = a3->right;
  v30.top = v13;
  v15 = CW32System::MulDivFunc(right, DeviceCaps, 2540);
  bottom = a3->bottom;
  v30.right = v15;
  v30.bottom = CW32System::MulDivFunc(bottom, v17, 2540);
  hdcSrc = CreateCompatibleDC(DC);
  ho = CreateCompatibleBitmap(DC, v30.right - v30.left, v30.bottom - v30.top);
  h = SelectObject(hdcSrc, ho);
  ReleaseDC(0, DC);
  v27 = 0x300000057LL;
  v33 = 0x300000057LL;
  v32 = 0;
  v34 = 0;
  v35 = 0;
  D2DFactory = GetD2DFactory();
  v26 = 0;
  v20 = (*(__int64 (__fastcall **)(struct ID2D1Factory *, int *, RichEdit **))(*(_QWORD *)D2DFactory + 128LL))(
          D2DFactory,
          &v32,
          &v26);
  v27 = 0;
  v22 = v20;
  if ( v20 >= 0 )
  {
    D2DTextRenderTarget = RichEdit::CreateD2DTextRenderTarget(v26, v21);
    Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v27);
    v27 = (__int64)D2DTextRenderTarget;
    v22 = (*(__int64 (__fastcall **)(RichEdit *, HDC, struct tagRECT *))(*(_QWORD *)v26 + 456LL))(v26, hdcSrc, &v30);
    if ( v22 >= 0 )
    {
      (*(void (__fastcall **)(RichEdit *))(*(_QWORD *)v26 + 384LL))(v26);
      BackColor = CTxtEdit::TxGetBackColor(v3);
      v31[3] = 1.0;
      v31[0] = (float)BYTE2(BackColor) / 255.0;
      v31[1] = (float)BYTE1(BackColor) / 255.0;
      v31[2] = (float)(unsigned __int8)BackColor / 255.0;
      (*(void (__fastcall **)(RichEdit *, float *))(*(_QWORD *)v26 + 376LL))(v26, v31);
      v22 = CTextMarkContainer::DrawBlob(v25, a1, 0, &v30, D2DTextRenderTarget);
      if ( v22 >= 0 )
        v22 = (*(__int64 (__fastcall **)(RichEdit *, _QWORD, _QWORD))(*(_QWORD *)v26 + 392LL))(v26, 0, 0);
    }
  }
  if ( v26 )
    (*(void (__fastcall **)(RichEdit *))(*(_QWORD *)v26 + 16LL))(v26);
  Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v27);
  StretchBlt(
    hdcDest,
    0,
    0,
    a3->right - a3->left,
    a3->bottom - a3->top,
    hdcSrc,
    0,
    0,
    v30.right - v30.left,
    v30.bottom - v30.top,
    0xCC0020u);
  SelectObject(hdcSrc, h);
  DeleteObject(ho);
  DeleteObject(hdcSrc);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180150e38  mov     [rsp-8+arg_18], rbx
0x180150e3d  push    rbp
0x180150e3e  push    rsi
0x180150e3f  push    rdi
0x180150e40  push    r12
0x180150e42  push    r13
0x180150e44  push    r14
0x180150e46  push    r15
0x180150e48  lea     rbp, [rsp-27h]
0x180150e4d  sub     rsp, 0D0h
0x180150e54  mov     rax, cs:__security_cookie
0x180150e5b  xor     rax, rsp
0x180150e5e  mov     [rbp+57h+var_40], rax
0x180150e62  mov     r12, [rcx+30h]
0x180150e66  mov     r15, rcx
0x180150e69  mov     rcx, r12; this
0x180150e6c  mov     rsi, r8
0x180150e6f  mov     r13, rdx
0x180150e72  call    ?GetTextMarkContainer@CTxtEdit@@QEAAPEAVCTextMarkContainer@@XZ; CTxtEdit::GetTextMarkContainer(void)
0x180150e77  test    rax, rax
0x180150e7a  jnz     short loc_180150E86
0x180150e7c  mov     eax, 80004005h
0x180150e81  jmp     loc_180151160
0x180150e86  xor     ecx, ecx; hWnd
0x180150e88  call    cs:__imp_GetDC
0x180150e8f  nop     dword ptr [rax+rax+00h]
0x180150e94  mov     rcx, rax; hdc
0x180150e97  mov     edx, 58h ; 'X'; index
0x180150e9c  mov     rdi, rax
0x180150e9f  call    cs:__imp_GetDeviceCaps
0x180150ea6  nop     dword ptr [rax+rax+00h]
0x180150eab  mov     edx, 5Ah ; 'Z'; index
0x180150eb0  mov     rcx, rdi; hdc
0x180150eb3  mov     ebx, eax
0x180150eb5  call    cs:__imp_GetDeviceCaps
0x180150ebc  nop     dword ptr [rax+rax+00h]
0x180150ec1  mov     ecx, [rsi]; int
0x180150ec3  mov     r14d, 9ECh
0x180150ec9  mov     r8d, r14d; int
0x180150ecc  mov     edx, ebx; int
0x180150ece  mov     r11d, eax
0x180150ed1  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180150ed6  mov     ecx, [rsi+4]; int
0x180150ed9  mov     r8d, r14d; int
0x180150edc  mov     edx, r11d; int
0x180150edf  mov     [rbp+57h+var_80.left], eax
0x180150ee2  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180150ee7  mov     ecx, [rsi+8]; int
0x180150eea  mov     r8d, r14d; int
0x180150eed  mov     edx, ebx; int
0x180150eef  mov     [rbp+57h+var_80.top], eax
0x180150ef2  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180150ef7  mov     ecx, [rsi+0Ch]; int
0x180150efa  mov     r8d, r14d; int
0x180150efd  mov     edx, r11d; int
0x180150f00  mov     [rbp+57h+var_80.right], eax
0x180150f03  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180150f08  mov     rcx, rdi; hdc
0x180150f0b  mov     [rbp+57h+var_80.bottom], eax
0x180150f0e  call    cs:__imp_CreateCompatibleDC
0x180150f15  nop     dword ptr [rax+rax+00h]
0x180150f1a  mov     r8d, [rbp+57h+var_80.bottom]
0x180150f1e  mov     rcx, rdi; hdc
0x180150f21  mov     edx, [rbp+57h+var_80.right]
0x180150f24  mov     r14, rax
0x180150f27  sub     r8d, [rbp+57h+var_80.top]; cy
0x180150f2b  sub     edx, [rbp+57h+var_80.left]; cx
0x180150f2e  call    cs:__imp_CreateCompatibleBitmap
0x180150f35  nop     dword ptr [rax+rax+00h]
0x180150f3a  mov     rdx, rax; h
0x180150f3d  mov     [rbp+57h+ho], rax
0x180150f41  mov     rcx, r14; hdc
0x180150f44  call    cs:__imp_SelectObject
0x180150f4b  nop     dword ptr [rax+rax+00h]
0x180150f50  mov     rdx, rdi; hDC
0x180150f53  xor     ecx, ecx; hWnd
0x180150f55  mov     [rbp+57h+h], rax
0x180150f59  call    cs:__imp_ReleaseDC
0x180150f60  nop     dword ptr [rax+rax+00h]
0x180150f65  xor     edi, edi
0x180150f67  mov     dword ptr [rbp+57h+var_98], 57h ; 'W'
0x180150f6e  mov     dword ptr [rbp+57h+var_98+4], 3
0x180150f75  mov     rcx, [rbp+57h+var_98]
0x180150f79  mov     [rbp+57h+var_5C], rcx
0x180150f7d  mov     [rbp+57h+var_60], edi
0x180150f80  mov     [rbp+57h+var_54], rdi
0x180150f84  mov     [rbp+57h+var_4C], rdi
0x180150f88  call    ?GetD2DFactory@@YAPEAUID2D1Factory@@XZ; GetD2DFactory(void)
0x180150f8d  mov     r9, rax
0x180150f90  mov     [rbp+57h+var_A0], rdi
0x180150f94  lea     r8, [rbp+57h+var_A0]
0x180150f98  lea     rdx, [rbp+57h+var_60]
0x180150f9c  mov     rcx, [rax]
0x180150f9f  mov     rax, [rcx+80h]
0x180150fa6  mov     rcx, r9
0x180150fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150fae  mov     [rbp+57h+var_98], rdi
0x180150fb2  mov     ebx, eax
0x180150fb4  test    eax, eax
0x180150fb6  js      loc_1801510BD
0x180150fbc  mov     rcx, [rbp+57h+var_A0]; this
0x180150fc0  call    ?CreateD2DTextRenderTarget@RichEdit@@YAPEAUITextRenderTarget@@PEAUID2D1RenderTarget@@@Z; RichEdit::CreateD2DTextRenderTarget(ID2D1RenderTarget *)
0x180150fc5  lea     rcx, [rbp+57h+var_98]; void *
0x180150fc9  mov     rdi, rax
0x180150fcc  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x180150fd1  mov     r9, [rbp+57h+var_A0]
0x180150fd5  lea     r8, [rbp+57h+var_80]
0x180150fd9  mov     rdx, r14
0x180150fdc  mov     [rbp+57h+var_98], rdi
0x180150fe0  mov     rcx, [r9]
0x180150fe3  mov     rax, [rcx+1C8h]
0x180150fea  mov     rcx, r9
0x180150fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150ff2  mov     ebx, eax
0x180150ff4  test    eax, eax
0x180150ff6  js      loc_1801510BB
0x180150ffc  mov     rcx, [rbp+57h+var_A0]
0x180151000  mov     rax, [rcx]
0x180151003  mov     rax, [rax+180h]
0x18015100a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015100f  mov     rcx, r12; this
0x180151012  call    ?TxGetBackColor@CTxtEdit@@QEBAKXZ; CTxtEdit::TxGetBackColor(void)
0x180151017  movss   xmm1, cs:__real@437f0000
0x18015101f  lea     rdx, [rbp+57h+var_70]
0x180151023  xorps   xmm0, xmm0
0x180151026  mov     [rbp+57h+var_64], 3F800000h
0x18015102d  mov     ecx, eax
0x18015102f  shr     ecx, 10h
0x180151032  movzx   ecx, cl
0x180151035  cvtsi2ss xmm0, rcx
0x18015103a  mov     ecx, eax
0x18015103c  movzx   eax, al
0x18015103f  shr     ecx, 8
0x180151042  movzx   ecx, cl
0x180151045  divss   xmm0, xmm1
0x180151049  movss   [rbp+57h+var_70], xmm0
0x18015104e  xorps   xmm0, xmm0
0x180151051  cvtsi2ss xmm0, rcx
0x180151056  mov     rcx, [rbp+57h+var_A0]
0x18015105a  divss   xmm0, xmm1
0x18015105e  movss   [rbp+57h+var_6C], xmm0
0x180151063  xorps   xmm0, xmm0
0x180151066  cvtsi2ss xmm0, rax
0x18015106b  divss   xmm0, xmm1
0x18015106f  movss   [rbp+57h+var_68], xmm0
0x180151074  mov     rax, [rcx]
0x180151077  mov     rax, [rax+178h]
0x18015107e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151083  lea     r9, [rbp+57h+var_80]; struct tagRECT *
0x180151087  mov     qword ptr [rsp+100h+hDest], rdi; struct ITextRenderTarget *
0x18015108c  xor     r8d, r8d; HDC
0x18015108f  mov     rdx, r15; struct COleObject *
0x180151092  call    ?DrawBlob@CTextMarkContainer@@QEAAJAEBVCOleObject@@PEAUHDC__@@PEBUtagRECT@@PEAUITextRenderTarget@@@Z; CTextMarkContainer::DrawBlob(COleObject const &,HDC__ *,tagRECT const *,ITextRenderTarget *)
0x180151097  xor     edi, edi
0x180151099  mov     ebx, eax
0x18015109b  test    eax, eax
0x18015109d  js      short loc_1801510BD
0x18015109f  mov     rcx, [rbp+57h+var_A0]
0x1801510a3  xor     r8d, r8d
0x1801510a6  xor     edx, edx
0x1801510a8  mov     rax, [rcx]
0x1801510ab  mov     rax, [rax+188h]
0x1801510b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801510b7  mov     ebx, eax
0x1801510b9  jmp     short loc_1801510BD
0x1801510bb  xor     edi, edi
0x1801510bd  mov     rcx, [rbp+57h+var_A0]
0x1801510c1  test    rcx, rcx
0x1801510c4  jz      short loc_1801510D2
0x1801510c6  mov     rax, [rcx]
0x1801510c9  mov     rax, [rax+10h]
0x1801510cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801510d2  lea     rcx, [rbp+57h+var_98]; void *
0x1801510d6  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801510db  mov     edx, [rbp+57h+var_80.bottom]
0x1801510de  mov     rcx, r13; hdcDest
0x1801510e1  sub     edx, [rbp+57h+var_80.top]
0x1801510e4  mov     eax, [rbp+57h+var_80.right]
0x1801510e7  sub     eax, [rbp+57h+var_80.left]
0x1801510ea  mov     r8d, [rsi+0Ch]
0x1801510ee  sub     r8d, [rsi+4]
0x1801510f2  mov     r9d, [rsi+8]
0x1801510f6  sub     r9d, [rsi]; wDest
0x1801510f9  mov     [rsp+100h+rop], 0CC0020h; rop
0x180151101  mov     [rsp+100h+hSrc], edx; hSrc
0x180151105  xor     edx, edx; xDest
0x180151107  mov     [rsp+100h+wSrc], eax; wSrc
0x18015110b  mov     [rsp+100h+ySrc], edi; ySrc
0x18015110f  mov     [rsp+100h+xSrc], edi; xSrc
0x180151113  mov     [rsp+100h+hdcSrc], r14; hdcSrc
0x180151118  mov     [rsp+100h+hDest], r8d; hDest
0x18015111d  xor     r8d, r8d; yDest
0x180151120  call    cs:__imp_StretchBlt
0x180151127  nop     dword ptr [rax+rax+00h]
0x18015112c  mov     rdx, [rbp+57h+h]; h
0x180151130  mov     rcx, r14; hdc
0x180151133  call    cs:__imp_SelectObject
0x18015113a  nop     dword ptr [rax+rax+00h]
0x18015113f  mov     rcx, [rbp+57h+ho]; ho
0x180151143  call    cs:__imp_DeleteObject
0x18015114a  nop     dword ptr [rax+rax+00h]
0x18015114f  mov     rcx, r14; ho
0x180151152  call    cs:__imp_DeleteObject
0x180151159  nop     dword ptr [rax+rax+00h]
0x18015115e  mov     eax, ebx
0x180151160  mov     rcx, [rbp+57h+var_40]
0x180151164  xor     rcx, rsp; StackCookie
0x180151167  call    __security_check_cookie
0x18015116c  mov     rbx, [rsp+100h+arg_18]
0x180151174  add     rsp, 0D0h
0x18015117b  pop     r15
0x18015117d  pop     r14
0x18015117f  pop     r13
0x180151181  pop     r12
0x180151183  pop     rdi
0x180151184  pop     rsi
0x180151185  pop     rbp
0x180151186  retn
```

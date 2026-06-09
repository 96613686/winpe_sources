# CUIFSchemeOfc10::DrawMenuBitmap(HDC__ *,tagRECT const *,HBITMAP__ *,HBITMAP__ *,ulong)

- ea: `0x1800dcc50`
- end: `0x1800dd058`
- name: `?DrawMenuBitmap@CUIFSchemeOfc10@@UEAAXPEAUHDC__@@PEBUtagRECT@@PEAUHBITMAP__@@2K@Z`
- size: `1032`
- prototype: `void(CUIFSchemeOfc10 *__hidden this, HDC, const struct tagRECT *, HBITMAP, HBITMAP, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18006c598`
- `0x1800d9a6c`
- `0x1800d9a94`
- `0x1800d9e38`
- `0x1800da328`
- `0x1800da514`
- `0x1800dab08`
- `0x1800dadac`
- `0x1800dcc50`
- `0x1800de4d4`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dcd73`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dcf52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dcd73`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dcf52`
- `GDI32!DeleteObject` at `0x1800dd023`
- `GDI32!DeleteObject` at `0x1800dd033`
- `GDI32!DeleteObject` at `0x1800dd03e`
- `GDI32!DeleteObject` at `0x1800dd023`
- `GDI32!DeleteObject` at `0x1800dd033`
- `GDI32!DeleteObject` at `0x1800dd03e`
- `GDI32!GetStockObject` at `0x1800dccb7`
- `GDI32!GetStockObject` at `0x1800dccb7`

## pseudocode

```c
void __fastcall CUIFSchemeOfc10::DrawMenuBitmap(
        CUIFSchemeOfc10 *this,
        HDC a2,
        const struct tagRECT *a3,
        HBITMAP a4,
        HBITMAP a5,
        struct _BLENDFUNCTION a6)
{
  unsigned int v8; // ebx
  HBITMAP v11; // rsi
  HBRUSH v12; // rax
  HBRUSH StockObject; // rax
  __int64 v14; // rax
  LONG top; // esi
  int v16; // ebp
  LONG left; // ebx
  int v18; // edi
  HBRUSH v19; // rax
  int (*v20)(HDC, __int64, unsigned __int64, int, int); // r8
  CBitmapDC *v21; // rax
  int v22; // edx
  CBitmapDC *v23; // rax
  HBITMAP v24; // rdi
  HDC *v25; // rbx
  unsigned int v26; // edx
  HBITMAP v27; // rcx
  LONG v28; // esi
  int v29; // ebp
  LONG v30; // ebx
  int v31; // edi
  HBRUSH v32; // rax
  int (*v33)(HDC, __int64, unsigned __int64, int, int); // r8
  unsigned int v34; // edi
  __int64 (__fastcall *v35)(CUIFSchemeOfc10 *, __int64); // rax
  HBRUSH v36; // rbx
  HBRUSH v37; // rax
  HBITMAP v38; // rax
  HBITMAP MaskBmp; // rbx
  CBitmapDC *v40; // rax
  int v41; // edx
  HBRUSH v42; // rax
  HBRUSH v43; // [rsp+20h] [rbp-A8h]
  HBRUSH v44; // [rsp+20h] [rbp-A8h]
  HBRUSH v45; // [rsp+20h] [rbp-A8h]
  HBRUSH v46; // [rsp+20h] [rbp-A8h]
  int v47; // [rsp+30h] [rbp-98h]
  int v48; // [rsp+38h] [rbp-90h]
  HBITMAP ho; // [rsp+60h] [rbp-68h]
  struct tagRECT v50; // [rsp+68h] [rbp-60h] BYREF
  HBITMAP v51; // [rsp+D0h] [rbp+8h]

  v8 = a6.BlendOp & 0x10;
  if ( (*((_BYTE *)this + 8) & 1) != 0 )
  {
    v12 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(*(_QWORD *)this + 16LL))(this, v8 != 0 ? 3 : 9);
    a4 = CUIMirrorBitmap(a4, v12);
    StockObject = (HBRUSH)GetStockObject(4);
    v11 = CUIMirrorBitmap(a5, StockObject);
  }
  else
  {
    v11 = a5;
  }
  ho = v11;
  if ( (a6.BlendOp & 1) == 0 || (a6.BlendOp & 0x10) != 0 )
  {
    v24 = ProcessAlphaBitmap(a2, a4, *((_DWORD *)this + 2) & 1);
    if ( v24 )
    {
      v40 = (CBitmapDC *)LocalAlloc(0x40u, 0x20u);
      if ( v40 )
      {
        v23 = CBitmapDC::CBitmapDC(v40, v41);
LABEL_9:
        v25 = (HDC *)v23;
        if ( v23 )
        {
          CBitmapDC::SetBitmap(v23, v24);
          CUIAlphaBlend(
            a2,
            a3->left,
            a3->top,
            a3->right - a3->left,
            a3->bottom - a3->top,
            v25[3],
            v47,
            v48,
            a3->right - a3->left,
            a3->bottom - a3->top,
            (struct _BLENDFUNCTION)33488896);
          CBitmapDC::`scalar deleting destructor'((CBitmapDC *)v25, v26);
        }
      }
LABEL_12:
      v27 = v24;
LABEL_25:
      DeleteObject(v27);
      goto LABEL_26;
    }
    if ( v11 )
    {
      v42 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(*(_QWORD *)this + 16LL))(
                      this,
                      v8 != 0 ? 3 : 9);
      MaskBmp = CreateMaskBmp(a3, a4, v11, v42, 0, 0);
      CUIDrawState(
        a2,
        0,
        (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)a3->top,
        (__int64)MaskBmp,
        (unsigned __int64)v46,
        a3->left,
        a3->top,
        a3->right - a3->left,
        a3->bottom - a3->top,
        4u);
      goto LABEL_24;
    }
    CUIDrawState(
      a2,
      0,
      (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)a3->left,
      (__int64)a4,
      (unsigned __int64)v43,
      a3->left,
      a3->top,
      a3->right - a3->left,
      a3->bottom - a3->top,
      4u);
  }
  else
  {
    v51 = ProcessAlphaBitmap(a2, a4, *((_DWORD *)this + 2) & 1);
    v14 = *(_QWORD *)this;
    if ( v51 )
    {
      top = a3->top;
      v16 = a3->bottom - top;
      left = a3->left;
      v18 = a3->right - a3->left;
      v19 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, __int64))(v14 + 16))(this, 12);
      CUIDrawState(a2, v19, v20, (__int64)a4, (unsigned __int64)v43, left + 1, top + 1, v18, v16, 0x84u);
      v21 = (CBitmapDC *)LocalAlloc(0x40u, 0x20u);
      if ( v21 )
      {
        v23 = CBitmapDC::CBitmapDC(v21, v22);
        v24 = v51;
        goto LABEL_9;
      }
      v24 = v51;
      goto LABEL_12;
    }
    if ( !v11 )
    {
      v28 = a3->top;
      v29 = a3->bottom - v28;
      v30 = a3->left;
      v31 = a3->right - a3->left;
      v32 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, __int64))(v14 + 16))(this, 12);
      CUIDrawState(a2, v32, v33, (__int64)a4, (unsigned __int64)v43, v30 + 1, v28 + 1, v31, v29, 0x84u);
      CUIDrawState(
        a2,
        0,
        (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)(a3->bottom - a3->top),
        (__int64)a4,
        (unsigned __int64)v44,
        a3->left - 1,
        a3->top - 1,
        a3->right - a3->left,
        a3->bottom - a3->top,
        4u);
      goto LABEL_26;
    }
    v34 = (*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(v14 + 216))(this, *(unsigned int *)&a6);
    v35 = *(__int64 (__fastcall **)(CUIFSchemeOfc10 *, __int64))(*(_QWORD *)this + 16LL);
    v50 = *a3;
    v36 = (HBRUSH)v35(this, 12);
    v37 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(*(_QWORD *)this + 16LL))(this, v34);
    v38 = CreateShadowMaskBmp(&v50, a4, v11, v37, v36);
    MaskBmp = v38;
    if ( v38 )
    {
      CUIDrawState(
        a2,
        0,
        (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)(v50.bottom - v50.top),
        (__int64)v38,
        (unsigned __int64)v45,
        v50.left,
        v50.top,
        v50.right - v50.left,
        v50.bottom - v50.top,
        4u);
LABEL_24:
      v27 = MaskBmp;
      goto LABEL_25;
    }
  }
LABEL_26:
  if ( (*((_BYTE *)this + 8) & 1) != 0 )
  {
    DeleteObject(a4);
    DeleteObject(ho);
  }
}

```

## disassembly

```asm
0x1800dcc50  push    rbx
0x1800dcc52  push    rbp
0x1800dcc53  push    rsi
0x1800dcc54  push    rdi
0x1800dcc55  push    r12
0x1800dcc57  push    r13
0x1800dcc59  push    r14
0x1800dcc5b  push    r15
0x1800dcc5d  sub     rsp, 88h
0x1800dcc64  mov     edi, dword ptr [rsp+0C8h+arg_28.BlendOp]
0x1800dcc6b  mov     r13, r9
0x1800dcc6e  mov     ebx, edi
0x1800dcc70  mov     r14, r8
0x1800dcc73  and     ebx, 10h
0x1800dcc76  mov     r12, rdx
0x1800dcc79  test    byte ptr [rcx+8], 1
0x1800dcc7d  mov     r15, rcx
0x1800dcc80  jnz     short loc_1800DCC8C
0x1800dcc82  mov     rsi, [rsp+0C8h+arg_20]
0x1800dcc8a  jmp     short loc_1800DCCD0
0x1800dcc8c  mov     r8, [rcx]
0x1800dcc8f  mov     eax, ebx
0x1800dcc91  neg     eax
0x1800dcc93  sbb     edx, edx
0x1800dcc95  mov     rax, [r8+10h]
0x1800dcc99  and     edx, 0FFFFFFFAh
0x1800dcc9c  add     edx, 9
0x1800dcc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcca4  mov     rdx, rax; hbr
0x1800dcca7  mov     rcx, r13; HBITMAP
0x1800dccaa  call    ?CUIMirrorBitmap@@YAPEAUHBITMAP__@@PEAU1@PEAUHBRUSH__@@@Z; CUIMirrorBitmap(HBITMAP__ *,HBRUSH__ *)
0x1800dccaf  mov     ecx, 4; i
0x1800dccb4  mov     r13, rax
0x1800dccb7  call    cs:__imp_GetStockObject
0x1800dccbd  mov     rcx, [rsp+0C8h+arg_20]; HBITMAP
0x1800dccc5  mov     rdx, rax; hbr
0x1800dccc8  call    ?CUIMirrorBitmap@@YAPEAUHBITMAP__@@PEAU1@PEAUHBRUSH__@@@Z; CUIMirrorBitmap(HBITMAP__ *,HBRUSH__ *)
0x1800dcccd  mov     rsi, rax
0x1800dccd0  xor     ebp, ebp
0x1800dccd2  mov     [rsp+0C8h+ho], rsi
0x1800dccd7  test    dil, 1
0x1800dccdb  jz      loc_1800DCF24
0x1800dcce1  test    ebx, ebx
0x1800dcce3  jnz     loc_1800DCF24
0x1800dcce9  mov     r8d, [r15+8]
0x1800dcced  mov     rdx, r13; hbm
0x1800dccf0  and     r8d, 1; int
0x1800dccf4  mov     rcx, r12; hdc
0x1800dccf7  call    ?ProcessAlphaBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@PEAU1@H@Z; ProcessAlphaBitmap(HDC__ *,HBITMAP__ *,int)
0x1800dccfc  mov     [rsp+0C8h+arg_0], rax
0x1800dcd04  test    rax, rax
0x1800dcd07  mov     rax, [r15]
0x1800dcd0a  mov     rcx, r15
0x1800dcd0d  jz      loc_1800DCDF9
0x1800dcd13  mov     ebp, [r14+0Ch]
0x1800dcd17  mov     edx, 0Ch
0x1800dcd1c  mov     edi, [r14+8]
0x1800dcd20  mov     esi, [r14+4]
0x1800dcd24  sub     ebp, esi
0x1800dcd26  mov     ebx, [r14]
0x1800dcd29  sub     edi, ebx
0x1800dcd2b  mov     rax, [rax+10h]
0x1800dcd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcd34  mov     [rsp+0C8h+var_80], 84h; unsigned int
0x1800dcd3c  lea     ecx, [rsi+1]
0x1800dcd3f  mov     [rsp+0C8h+var_88], ebp; int
0x1800dcd43  lea     edx, [rbx+1]
0x1800dcd46  mov     [rsp+0C8h+var_90], edi; int
0x1800dcd4a  mov     r9, r13; __int64
0x1800dcd4d  mov     [rsp+0C8h+var_98], ecx; int
0x1800dcd51  mov     rcx, r12; hdc
0x1800dcd54  mov     dword ptr [rsp+0C8h+var_A0], edx; int
0x1800dcd58  mov     rdx, rax; hbrFore
0x1800dcd5b  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dcd60  mov     edx, 20h ; ' '; uBytes
0x1800dcd65  mov     dword ptr [rsp+0C8h+arg_28.BlendOp], 1FF0000h
0x1800dcd70  lea     ecx, [rdx+20h]; uFlags
0x1800dcd73  call    cs:__imp_LocalAlloc
0x1800dcd79  test    rax, rax
0x1800dcd7c  jz      short loc_1800DCDE9
0x1800dcd7e  mov     rcx, rax; this
0x1800dcd81  call    ??0CBitmapDC@@QEAA@H@Z; CBitmapDC::CBitmapDC(int)
0x1800dcd86  mov     rdi, [rsp+0C8h+arg_0]
0x1800dcd8e  mov     rbx, rax
0x1800dcd91  test    rax, rax
0x1800dcd94  jz      short loc_1800DCDF1
0x1800dcd96  mov     rdx, rdi; HBITMAP
0x1800dcd99  mov     rcx, rax; this
0x1800dcd9c  call    ?SetBitmap@CBitmapDC@@QEAAHPEAUHBITMAP__@@@Z; CBitmapDC::SetBitmap(HBITMAP__ *)
0x1800dcda1  mov     ecx, [r14+0Ch]
0x1800dcda5  mov     r8d, [r14+4]; int
0x1800dcda9  sub     ecx, r8d
0x1800dcdac  mov     r9d, [r14+8]
0x1800dcdb0  mov     eax, dword ptr [rsp+0C8h+arg_28.BlendOp]
0x1800dcdb7  sub     r9d, [r14]; int
0x1800dcdba  mov     edx, [r14]; int
0x1800dcdbd  mov     dword ptr [rsp+0C8h+var_78.BlendOp], eax; struct _BLENDFUNCTION
0x1800dcdc1  mov     rax, [rbx+18h]
0x1800dcdc5  mov     [rsp+0C8h+var_80], ecx; int
0x1800dcdc9  mov     [rsp+0C8h+var_88], r9d; int
0x1800dcdce  mov     [rsp+0C8h+var_A0], rax; HDC
0x1800dcdd3  mov     dword ptr [rsp+0C8h+var_A8], ecx; int
0x1800dcdd7  mov     rcx, r12; HDC
0x1800dcdda  call    ?CUIAlphaBlend@@YAHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@Z; CUIAlphaBlend(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int,_BLENDFUNCTION)
0x1800dcddf  mov     rcx, rbx; this
0x1800dcde2  call    ??_GCBitmapDC@@QEAAPEAXI@Z; CBitmapDC::`scalar deleting destructor'(uint)
0x1800dcde7  jmp     short loc_1800DCDF1
0x1800dcde9  mov     rdi, [rsp+0C8h+arg_0]
0x1800dcdf1  mov     rcx, rdi
0x1800dcdf4  jmp     loc_1800DD023
0x1800dcdf9  test    rsi, rsi
0x1800dcdfc  jnz     loc_1800DCE85
0x1800dce02  mov     ebp, [r14+0Ch]
0x1800dce06  mov     edx, 0Ch
0x1800dce0b  mov     edi, [r14+8]
0x1800dce0f  mov     esi, [r14+4]
0x1800dce13  sub     ebp, esi
0x1800dce15  mov     ebx, [r14]
0x1800dce18  sub     edi, ebx
0x1800dce1a  mov     rax, [rax+10h]
0x1800dce1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dce23  mov     [rsp+0C8h+var_80], 84h; unsigned int
0x1800dce2b  lea     ecx, [rsi+1]
0x1800dce2e  mov     [rsp+0C8h+var_88], ebp; int
0x1800dce32  lea     edx, [rbx+1]
0x1800dce35  mov     [rsp+0C8h+var_90], edi; int
0x1800dce39  mov     r9, r13; __int64
0x1800dce3c  mov     [rsp+0C8h+var_98], ecx; int
0x1800dce40  mov     rcx, r12; hdc
0x1800dce43  mov     dword ptr [rsp+0C8h+var_A0], edx; int
0x1800dce47  mov     rdx, rax; hbrFore
0x1800dce4a  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dce4f  mov     eax, [r14+4]
0x1800dce53  mov     ecx, [r14]
0x1800dce56  mov     r8d, [r14+0Ch]
0x1800dce5a  mov     edx, [r14+8]
0x1800dce5e  sub     r8d, eax
0x1800dce61  mov     [rsp+0C8h+var_80], 4
0x1800dce69  sub     edx, ecx
0x1800dce6b  mov     [rsp+0C8h+var_88], r8d
0x1800dce70  dec     eax
0x1800dce72  mov     [rsp+0C8h+var_90], edx
0x1800dce76  dec     ecx
0x1800dce78  mov     [rsp+0C8h+var_98], eax
0x1800dce7c  mov     dword ptr [rsp+0C8h+var_A0], ecx
0x1800dce80  jmp     loc_1800DCFA0
0x1800dce85  mov     rax, [rax+0D8h]
0x1800dce8c  mov     edx, edi
0x1800dce8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dce93  mov     rcx, [r15]
0x1800dce96  mov     edi, eax
0x1800dce98  movups  xmm0, xmmword ptr [r14]
0x1800dce9c  mov     edx, 0Ch
0x1800dcea1  mov     rax, [rcx+10h]
0x1800dcea5  mov     rcx, r15
0x1800dcea8  movdqu  xmmword ptr [rsp+0C8h+var_60.left], xmm0
0x1800dceae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dceb3  mov     rcx, [r15]
0x1800dceb6  mov     rbx, rax
0x1800dceb9  mov     edx, edi
0x1800dcebb  mov     rax, [rcx+10h]
0x1800dcebf  mov     rcx, r15
0x1800dcec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcec7  mov     r9, rax; HBRUSH
0x1800dceca  mov     [rsp+0C8h+var_A8], rbx; HBRUSH
0x1800dcecf  mov     r8, rsi; HBITMAP
0x1800dced2  lea     rcx, [rsp+0C8h+var_60]; struct tagRECT *
0x1800dced7  mov     rdx, r13; HBITMAP
0x1800dceda  call    ?CreateShadowMaskBmp@@YAPEAUHBITMAP__@@PEAUtagRECT@@PEAU1@1PEAUHBRUSH__@@2@Z; CreateShadowMaskBmp(tagRECT *,HBITMAP__ *,HBITMAP__ *,HBRUSH__ *,HBRUSH__ *)
0x1800dcedf  mov     rbx, rax
0x1800dcee2  test    rax, rax
0x1800dcee5  jz      loc_1800DD029
0x1800dceeb  mov     r9d, [rsp+0C8h+var_60.top]
0x1800dcef0  mov     edx, [rsp+0C8h+var_60.left]
0x1800dcef4  mov     r8d, [rsp+0C8h+var_60.bottom]
0x1800dcef9  mov     ecx, [rsp+0C8h+var_60.right]
0x1800dcefd  sub     r8d, r9d
0x1800dcf00  mov     [rsp+0C8h+var_80], 4
0x1800dcf08  sub     ecx, edx
0x1800dcf0a  mov     [rsp+0C8h+var_88], r8d
0x1800dcf0f  mov     [rsp+0C8h+var_90], ecx
0x1800dcf13  mov     [rsp+0C8h+var_98], r9d
0x1800dcf18  mov     r9, rax
0x1800dcf1b  mov     dword ptr [rsp+0C8h+var_A0], edx
0x1800dcf1f  jmp     loc_1800DD016
0x1800dcf24  mov     r8d, [r15+8]
0x1800dcf28  mov     rdx, r13; hbm
0x1800dcf2b  and     r8d, 1; int
0x1800dcf2f  mov     rcx, r12; hdc
0x1800dcf32  call    ?ProcessAlphaBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@PEAU1@H@Z; ProcessAlphaBitmap(HDC__ *,HBITMAP__ *,int)
0x1800dcf37  mov     rdi, rax
0x1800dcf3a  test    rax, rax
0x1800dcf3d  jz      short loc_1800DCF6E
0x1800dcf3f  mov     edx, 20h ; ' '; uBytes
0x1800dcf44  mov     dword ptr [rsp+0C8h+arg_28.BlendOp], 1FF0000h
0x1800dcf4f  lea     ecx, [rdx+20h]; uFlags
0x1800dcf52  call    cs:__imp_LocalAlloc
0x1800dcf58  test    rax, rax
0x1800dcf5b  jz      loc_1800DCDF1
0x1800dcf61  mov     rcx, rax; this
0x1800dcf64  call    ??0CBitmapDC@@QEAA@H@Z; CBitmapDC::CBitmapDC(int)
0x1800dcf69  jmp     loc_1800DCD8E
0x1800dcf6e  test    rsi, rsi
0x1800dcf71  jnz     short loc_1800DCFAF
0x1800dcf73  mov     edx, [r14+4]
0x1800dcf77  mov     r8d, [r14]; int (*)(HDC, __int64, unsigned __int64, int, int)
0x1800dcf7a  mov     ecx, [r14+0Ch]
0x1800dcf7e  mov     eax, [r14+8]
0x1800dcf82  sub     ecx, edx
0x1800dcf84  mov     [rsp+0C8h+var_80], 4; unsigned int
0x1800dcf8c  sub     eax, r8d
0x1800dcf8f  mov     [rsp+0C8h+var_88], ecx; int
0x1800dcf93  mov     [rsp+0C8h+var_90], eax; int
0x1800dcf97  mov     [rsp+0C8h+var_98], edx; int
0x1800dcf9b  mov     dword ptr [rsp+0C8h+var_A0], r8d; int
0x1800dcfa0  mov     r9, r13; __int64
0x1800dcfa3  xor     edx, edx; hbrFore
0x1800dcfa5  mov     rcx, r12; hdc
0x1800dcfa8  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dcfad  jmp     short loc_1800DD029
0x1800dcfaf  mov     rax, [r15]
0x1800dcfb2  neg     ebx
0x1800dcfb4  mov     rcx, r15
0x1800dcfb7  sbb     edx, edx
0x1800dcfb9  and     edx, 0FFFFFFFAh
0x1800dcfbc  mov     rax, [rax+10h]
0x1800dcfc0  add     edx, 9
0x1800dcfc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcfc8  mov     r9, rax; HBRUSH
0x1800dcfcb  mov     dword ptr [rsp+0C8h+var_A0], ebp; unsigned int
0x1800dcfcf  mov     r8, rsi; HBITMAP
0x1800dcfd2  mov     dword ptr [rsp+0C8h+var_A8], ebp; unsigned __int64
0x1800dcfd6  mov     rdx, r13; HBITMAP
0x1800dcfd9  mov     rcx, r14; struct tagRECT *
0x1800dcfdc  call    ?CreateMaskBmp@@YAPEAUHBITMAP__@@PEBUtagRECT@@PEAU1@1PEAUHBRUSH__@@KK@Z; CreateMaskBmp(tagRECT const *,HBITMAP__ *,HBITMAP__ *,HBRUSH__ *,ulong,ulong)
0x1800dcfe1  mov     r9d, [r14]
0x1800dcfe4  mov     rbx, rax
0x1800dcfe7  mov     r8d, [r14+4]; int (*)(HDC, __int64, unsigned __int64, int, int)
0x1800dcfeb  mov     edx, [r14+0Ch]
0x1800dcfef  mov     ecx, [r14+8]
0x1800dcff3  sub     edx, r8d
0x1800dcff6  mov     [rsp+0C8h+var_80], 4; unsigned int
0x1800dcffe  sub     ecx, r9d
0x1800dd001  mov     [rsp+0C8h+var_88], edx; int
0x1800dd005  mov     [rsp+0C8h+var_90], ecx; int
0x1800dd009  mov     [rsp+0C8h+var_98], r8d; int
0x1800dd00e  mov     dword ptr [rsp+0C8h+var_A0], r9d; int
0x1800dd013  mov     r9, rax; __int64
0x1800dd016  xor     edx, edx; hbrFore
0x1800dd018  mov     rcx, r12; hdc
0x1800dd01b  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dd020  mov     rcx, rbx; ho
0x1800dd023  call    cs:__imp_DeleteObject
0x1800dd029  test    byte ptr [r15+8], 1
0x1800dd02e  jz      short loc_1800DD044
0x1800dd030  mov     rcx, r13; ho
0x1800dd033  call    cs:__imp_DeleteObject
0x1800dd039  mov     rcx, [rsp+0C8h+ho]; ho
0x1800dd03e  call    cs:__imp_DeleteObject
0x1800dd044  add     rsp, 88h
0x1800dd04b  pop     r15
0x1800dd04d  pop     r14
0x1800dd04f  pop     r13
0x1800dd051  pop     r12
0x1800dd053  pop     rdi
0x1800dd054  pop     rsi
0x1800dd055  pop     rbp
0x1800dd056  pop     rbx
0x1800dd057  retn
```

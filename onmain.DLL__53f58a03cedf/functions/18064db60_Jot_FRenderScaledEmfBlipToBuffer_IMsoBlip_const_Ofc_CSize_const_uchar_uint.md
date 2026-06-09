# Jot::FRenderScaledEmfBlipToBuffer(IMsoBlip const *,Ofc::CSize const &,uchar *,uint)

- ea: `0x18064db60`
- end: `0x18064de7e`
- name: `?FRenderScaledEmfBlipToBuffer@Jot@@YA_NPEBUIMsoBlip@@AEBVCSize@Ofc@@PEAEI@Z`
- size: `798`
- prototype: `bool __fastcall(Jot *__hidden this, const struct IMsoBlip *, const struct Ofc::CSize *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18064d724`

## callees

- `0x1802e2251`
- `0x1802e5170`
- `0x1802e5190`
- `0x18064db60`
- `0x18064de80`
- `0x18064e030`

## import_xrefs

- `GDI32!DeleteEnhMetaFile` at `0x18064de6a`
- `GDI32!DeleteEnhMetaFile` at `0x18064de75`
- `GDI32!DeleteEnhMetaFile` at `0x18064de6a`
- `GDI32!DeleteEnhMetaFile` at `0x18064de75`
- `GDI32!GetStockObject` at `0x18064dc2e`
- `GDI32!GetStockObject` at `0x18064dcbe`
- `GDI32!GetStockObject` at `0x18064dc2e`
- `GDI32!GetStockObject` at `0x18064dcbe`
- `gdiplus!GdipDisposeImage` at `0x18064ddf2`
- `gdiplus!GdipDisposeImage` at `0x18064de58`
- `gdiplus!GdipDisposeImage` at `0x18064ddf2`
- `gdiplus!GdipDisposeImage` at `0x18064de58`
- `gdiplus!GdipDrawImageRect` at `0x18064dcae`
- `gdiplus!GdipDrawImageRect` at `0x18064dd34`
- `gdiplus!GdipDrawImageRect` at `0x18064dcae`
- `gdiplus!GdipDrawImageRect` at `0x18064dd34`
- `gdiplus!GdipDeleteGraphics` at `0x18064ddcd`
- `gdiplus!GdipDeleteGraphics` at `0x18064ddd6`
- `gdiplus!GdipDeleteGraphics` at `0x18064de33`
- `gdiplus!GdipDeleteGraphics` at `0x18064de3c`
- `gdiplus!GdipDeleteGraphics` at `0x18064ddcd`
- `gdiplus!GdipDeleteGraphics` at `0x18064ddd6`
- `gdiplus!GdipDeleteGraphics` at `0x18064de33`
- `gdiplus!GdipDeleteGraphics` at `0x18064de3c`
- `gdiplus!GdipCreateFromHDC` at `0x18064dc77`
- `gdiplus!GdipCreateFromHDC` at `0x18064dd11`
- `gdiplus!GdipCreateFromHDC` at `0x18064dc77`
- `gdiplus!GdipCreateFromHDC` at `0x18064dd11`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x18064dbca`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x18064dbca`
- `USER32!FillRect` at `0x18064dc53`
- `USER32!FillRect` at `0x18064dce6`
- `USER32!FillRect` at `0x18064dc53`
- `USER32!FillRect` at `0x18064dce6`

## pseudocode

```c
char __fastcall Jot::FRenderScaledEmfBlipToBuffer(
        Jot *this,
        LONG *a2,
        const struct Ofc::CSize *a3,
        unsigned __int8 *a4)
{
  unsigned int v4; // r13d
  __int64 v7; // rax
  HENHMETAFILE v8; // rbx
  LONG v9; // r12d
  HBRUSH StockObject; // rdi
  HDC DC; // rax
  HDC v12; // rax
  __int64 v13; // r15
  __int64 v14; // rsi
  HBRUSH v15; // rdi
  HDC v16; // rax
  HDC v17; // rax
  __int64 v18; // rdi
  int *v19; // r10
  __int64 v20; // r11
  unsigned int v21; // r12d
  char *v22; // r14
  int v23; // r9d
  int v24; // r8d
  __int16 v25; // cx
  unsigned int v26; // edx
  LONG v28; // [rsp+30h] [rbp-D0h]
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  RECT rc; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h]
  int v34; // [rsp+78h] [rbp-88h]
  _BYTE v35[72]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-38h]
  __int128 v37; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v38; // [rsp+E0h] [rbp-20h]
  int v39; // [rsp+E8h] [rbp-18h]
  _BYTE v40[72]; // [rsp+F0h] [rbp-10h] BYREF
  int *v41; // [rsp+138h] [rbp+38h]

  v4 = (unsigned int)a4;
  v7 = (*(__int64 (__fastcall **)(Jot *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 200LL))(this, 0, 0, 0);
  v29 = 0;
  v8 = (HENHMETAFILE)v7;
  GdipCreateMetafileFromEmf(v7, 0, &v29);
  v9 = *a2;
  v28 = a2[1];
  memset_0(v40, 0, 0x50u);
  v38 = 0;
  v37 = 0;
  v39 = 0;
  memset_0(v35, 0, 0x50u);
  v33 = 0;
  v32 = 0;
  v34 = 0;
  *(_QWORD *)&rc.left = 0;
  rc.right = v9;
  rc.bottom = v28;
  StockObject = (HBRUSH)GetStockObject(4);
  DC = Jot::CScreenDevice::GetDC((Jot::CScreenDevice *)&v37, 0, v9, v28);
  FillRect(DC, &rc, StockObject);
  v12 = Jot::CScreenDevice::GetDC((Jot::CScreenDevice *)&v37, 0, v9, v28);
  v30 = 0;
  GdipCreateFromHDC(v12, &v30);
  v13 = v30;
  v14 = v29;
  if ( !(unsigned int)GdipDrawImageRect(v30, v29) )
  {
    v15 = (HBRUSH)GetStockObject(0);
    v16 = Jot::CScreenDevice::GetDC((Jot::CScreenDevice *)&v32, 0, v9, v28);
    FillRect(v16, &rc, v15);
    v17 = Jot::CScreenDevice::GetDC((Jot::CScreenDevice *)&v32, 0, v9, v28);
    v29 = 0;
    GdipCreateFromHDC(v17, &v29);
    v18 = v29;
    if ( !(unsigned int)GdipDrawImageRect(v29, v14) )
    {
      if ( v36 )
      {
        v19 = v41;
        if ( v41 )
        {
          if ( v4 >= 4 )
          {
            v20 = v36 - (_QWORD)v41;
            v21 = 4;
            v22 = (char *)(a3 - (const struct Ofc::CSize *)v41);
            do
            {
              v23 = *(int *)((char *)v19 + v20);
              v21 += 4;
              v24 = *v19;
              v25 = BYTE1(*v19);
              v26 = HIWORD(*v19);
              v22[(_QWORD)v19 + 2] = v26;
              v22[(_QWORD)v19 + 1] = v25;
              v22[(_QWORD)v19++] = v24;
              v22[(_QWORD)v19 - 1] = ~(unsigned __int8)(((unsigned __int8)(v23 - v24)
                                                       + (unsigned __int8)(BYTE2(v23) - v26)
                                                       + 2 * (unsigned int)(unsigned __int8)(BYTE1(v23) - v25)) >> 2);
            }
            while ( v21 <= v4 );
          }
          GdipDeleteGraphics(v18);
          GdipDeleteGraphics(v13);
          Jot::CScreenDevice::FreeUnused((Jot::CScreenDevice *)&v32);
          Jot::CScreenDevice::FreeUnused((Jot::CScreenDevice *)&v37);
          GdipDisposeImage(v14);
          if ( v8 )
            DeleteEnhMetaFile(v8);
          return 1;
        }
      }
    }
    GdipDeleteGraphics(v18);
  }
  GdipDeleteGraphics(v13);
  Jot::CScreenDevice::FreeUnused((Jot::CScreenDevice *)&v32);
  Jot::CScreenDevice::FreeUnused((Jot::CScreenDevice *)&v37);
  GdipDisposeImage(v14);
  if ( v8 )
    DeleteEnhMetaFile(v8);
  return 0;
}

```

## disassembly

```asm
0x18064db60  mov     rax, rsp
0x18064db63  mov     [rax+20h], rbx
0x18064db67  push    rbp
0x18064db68  push    rsi
0x18064db69  push    rdi
0x18064db6a  push    r12
0x18064db6c  push    r13
0x18064db6e  push    r14
0x18064db70  push    r15
0x18064db72  lea     rbp, [rsp-70h]
0x18064db77  sub     rsp, 170h
0x18064db7e  movaps  xmmword ptr [rax-48h], xmm6
0x18064db82  movaps  xmmword ptr [rax-58h], xmm7
0x18064db86  mov     rax, cs:__security_cookie
0x18064db8d  xor     rax, rsp
0x18064db90  mov     [rbp+0A0h+var_60], rax
0x18064db94  mov     rax, [rcx]
0x18064db97  mov     r13d, r9d
0x18064db9a  mov     r14, r8
0x18064db9d  mov     rdi, rdx
0x18064dba0  xor     r9d, r9d
0x18064dba3  xor     r8d, r8d
0x18064dba6  xor     edx, edx
0x18064dba8  mov     rax, [rax+0C8h]
0x18064dbaf  call    cs:__guard_dispatch_icall_fptr
0x18064dbb5  xor     r15d, r15d
0x18064dbb8  lea     r8, [rsp+1A0h+var_168]
0x18064dbbd  mov     rcx, rax
0x18064dbc0  mov     [rsp+1A0h+var_168], r15
0x18064dbc5  xor     edx, edx
0x18064dbc7  mov     rbx, rax
0x18064dbca  call    cs:__imp_GdipCreateMetafileFromEmf
0x18064dbd0  mov     esi, [rdi+4]
0x18064dbd3  lea     rcx, [rbp+0A0h+var_B0]; void *
0x18064dbd7  mov     r12d, [rdi]
0x18064dbda  xor     edx, edx; Val
0x18064dbdc  lea     edi, [r15+50h]
0x18064dbe0  mov     [rsp+1A0h+var_170], esi
0x18064dbe4  mov     r8d, edi; Size
0x18064dbe7  call    memset_0
0x18064dbec  xorps   xmm0, xmm0
0x18064dbef  mov     [rbp+0A0h+var_C0], r15
0x18064dbf3  mov     r8d, edi; Size
0x18064dbf6  movdqa  [rbp+0A0h+var_D0], xmm0
0x18064dbfb  xor     edx, edx; Val
0x18064dbfd  mov     [rbp+0A0h+var_B8], r15d
0x18064dc01  lea     rcx, [rbp+0A0h+var_120]; void *
0x18064dc05  call    memset_0
0x18064dc0a  xorps   xmm0, xmm0
0x18064dc0d  mov     [rsp+1A0h+var_130], r15
0x18064dc12  lea     ecx, [rdi-4Ch]; i
0x18064dc15  movdqa  [rsp+1A0h+var_140], xmm0
0x18064dc1b  mov     [rsp+1A0h+var_128], r15d
0x18064dc20  mov     qword ptr [rsp+1A0h+rc.left], r15
0x18064dc25  mov     [rsp+1A0h+rc.right], r12d
0x18064dc2a  mov     [rsp+1A0h+rc.bottom], esi
0x18064dc2e  call    cs:__imp_GetStockObject
0x18064dc34  mov     r9d, esi; int
0x18064dc37  lea     rcx, [rbp+0A0h+var_D0]; this
0x18064dc3b  mov     r8d, r12d; int
0x18064dc3e  xor     edx, edx; hdc
0x18064dc40  mov     rdi, rax
0x18064dc43  call    ?GetDC@CScreenDevice@Jot@@QEAAPEAUHDC__@@PEAU3@HH@Z; Jot::CScreenDevice::GetDC(HDC__ *,int,int)
0x18064dc48  mov     r8, rdi; hbr
0x18064dc4b  lea     rdx, [rsp+1A0h+rc]; lprc
0x18064dc50  mov     rcx, rax; hDC
0x18064dc53  call    cs:__imp_FillRect
0x18064dc59  mov     r9d, esi; int
0x18064dc5c  lea     rcx, [rbp+0A0h+var_D0]; this
0x18064dc60  mov     r8d, r12d; int
0x18064dc63  xor     edx, edx; hdc
0x18064dc65  call    ?GetDC@CScreenDevice@Jot@@QEAAPEAUHDC__@@PEAU3@HH@Z; Jot::CScreenDevice::GetDC(HDC__ *,int,int)
0x18064dc6a  lea     rdx, [rsp+1A0h+var_160]
0x18064dc6f  mov     [rsp+1A0h+var_160], r15
0x18064dc74  mov     rcx, rax
0x18064dc77  call    cs:__imp_GdipCreateFromHDC
0x18064dc7d  mov     r15, [rsp+1A0h+var_160]
0x18064dc82  xorps   xmm3, xmm3
0x18064dc85  movd    xmm7, esi
0x18064dc89  xorps   xmm2, xmm2
0x18064dc8c  mov     rsi, [rsp+1A0h+var_168]
0x18064dc91  mov     rcx, r15
0x18064dc94  cvtdq2ps xmm7, xmm7
0x18064dc97  mov     rdx, rsi
0x18064dc9a  movd    xmm6, r12d
0x18064dc9f  cvtdq2ps xmm6, xmm6
0x18064dca2  movss   [rsp+1A0h+var_178], xmm7
0x18064dca8  movss   [rsp+1A0h+var_180], xmm6
0x18064dcae  call    cs:__imp_GdipDrawImageRect
0x18064dcb4  test    eax, eax
0x18064dcb6  jnz     loc_18064DE39
0x18064dcbc  xor     ecx, ecx; i
0x18064dcbe  call    cs:__imp_GetStockObject
0x18064dcc4  mov     r9d, [rsp+1A0h+var_170]; int
0x18064dcc9  lea     rcx, [rsp+1A0h+var_140]; this
0x18064dcce  mov     r8d, r12d; int
0x18064dcd1  xor     edx, edx; hdc
0x18064dcd3  mov     rdi, rax
0x18064dcd6  call    ?GetDC@CScreenDevice@Jot@@QEAAPEAUHDC__@@PEAU3@HH@Z; Jot::CScreenDevice::GetDC(HDC__ *,int,int)
0x18064dcdb  mov     r8, rdi; hbr
0x18064dcde  lea     rdx, [rsp+1A0h+rc]; lprc
0x18064dce3  mov     rcx, rax; hDC
0x18064dce6  call    cs:__imp_FillRect
0x18064dcec  mov     r9d, [rsp+1A0h+var_170]; int
0x18064dcf1  lea     rcx, [rsp+1A0h+var_140]; this
0x18064dcf6  mov     r8d, r12d; int
0x18064dcf9  xor     edx, edx; hdc
0x18064dcfb  call    ?GetDC@CScreenDevice@Jot@@QEAAPEAUHDC__@@PEAU3@HH@Z; Jot::CScreenDevice::GetDC(HDC__ *,int,int)
0x18064dd00  lea     rdx, [rsp+1A0h+var_168]
0x18064dd05  mov     [rsp+1A0h+var_168], 0
0x18064dd0e  mov     rcx, rax
0x18064dd11  call    cs:__imp_GdipCreateFromHDC
0x18064dd17  mov     rdi, [rsp+1A0h+var_168]
0x18064dd1c  xorps   xmm3, xmm3
0x18064dd1f  movss   [rsp+1A0h+var_178], xmm7
0x18064dd25  mov     rcx, rdi
0x18064dd28  xorps   xmm2, xmm2
0x18064dd2b  movss   [rsp+1A0h+var_180], xmm6
0x18064dd31  mov     rdx, rsi
0x18064dd34  call    cs:__imp_GdipDrawImageRect
0x18064dd3a  test    eax, eax
0x18064dd3c  jnz     loc_18064DE30
0x18064dd42  mov     r11, [rbp+0A0h+var_D8]
0x18064dd46  test    r11, r11
0x18064dd49  jz      loc_18064DE30
0x18064dd4f  mov     r10, [rbp+0A0h+var_68]
0x18064dd53  test    r10, r10
0x18064dd56  jz      loc_18064DE30
0x18064dd5c  cmp     r13d, 4
0x18064dd60  jb      short loc_18064DDCA
0x18064dd62  sub     r11, r10
0x18064dd65  lea     r12d, [rax+4]
0x18064dd69  sub     r14, r10
0x18064dd6c  mov     r9d, [r10+r11]
0x18064dd70  add     r12d, 4
0x18064dd74  mov     r8d, [r10]
0x18064dd77  movzx   eax, r9w
0x18064dd7b  shr     ax, 8
0x18064dd7f  movzx   ecx, r8w
0x18064dd83  shr     cx, 8
0x18064dd87  mov     edx, r8d
0x18064dd8a  sub     al, cl
0x18064dd8c  shr     edx, 10h
0x18064dd8f  mov     [r10+r14+2], dl
0x18064dd94  mov     [r10+r14+1], cl
0x18064dd99  movzx   ecx, al
0x18064dd9c  mov     eax, r9d
0x18064dd9f  shr     eax, 10h
0x18064dda2  sub     r9b, r8b
0x18064dda5  sub     al, dl
0x18064dda7  mov     [r10+r14], r8b
0x18064ddab  movzx   eax, al
0x18064ddae  lea     r10, [r10+4]
0x18064ddb2  lea     edx, [rax+rcx*2]
0x18064ddb5  movzx   eax, r9b
0x18064ddb9  add     edx, eax
0x18064ddbb  shr     edx, 2
0x18064ddbe  not     dl
0x18064ddc0  mov     [r10+r14-1], dl
0x18064ddc5  cmp     r12d, r13d
0x18064ddc8  jbe     short loc_18064DD6C
0x18064ddca  mov     rcx, rdi
0x18064ddcd  call    cs:__imp_GdipDeleteGraphics
0x18064ddd3  mov     rcx, r15
0x18064ddd6  call    cs:__imp_GdipDeleteGraphics
0x18064dddc  lea     rcx, [rsp+1A0h+var_140]; this
0x18064dde1  call    ?FreeUnused@CScreenDevice@Jot@@QEAAXXZ; Jot::CScreenDevice::FreeUnused(void)
0x18064dde6  lea     rcx, [rbp+0A0h+var_D0]; this
0x18064ddea  call    ?FreeUnused@CScreenDevice@Jot@@QEAAXXZ; Jot::CScreenDevice::FreeUnused(void)
0x18064ddef  mov     rcx, rsi
0x18064ddf2  call    cs:__imp_GdipDisposeImage
0x18064ddf8  test    rbx, rbx
0x18064ddfb  jnz     short loc_18064DE67
0x18064ddfd  mov     al, 1
0x18064ddff  mov     rcx, [rbp+0A0h+var_60]
0x18064de03  xor     rcx, rsp; StackCookie
0x18064de06  call    __security_check_cookie
0x18064de0b  lea     r11, [rsp+1A0h+var_30]
0x18064de13  mov     rbx, [r11+58h]
0x18064de17  movaps  xmm6, xmmword ptr [r11-10h]
0x18064de1c  movaps  xmm7, xmmword ptr [r11-20h]
0x18064de21  mov     rsp, r11
0x18064de24  pop     r15
0x18064de26  pop     r14
0x18064de28  pop     r13
0x18064de2a  pop     r12
0x18064de2c  pop     rdi
0x18064de2d  pop     rsi
0x18064de2e  pop     rbp
0x18064de2f  retn
0x18064de30  mov     rcx, rdi
0x18064de33  call    cs:__imp_GdipDeleteGraphics
0x18064de39  mov     rcx, r15
0x18064de3c  call    cs:__imp_GdipDeleteGraphics
0x18064de42  lea     rcx, [rsp+1A0h+var_140]; this
0x18064de47  call    ?FreeUnused@CScreenDevice@Jot@@QEAAXXZ; Jot::CScreenDevice::FreeUnused(void)
0x18064de4c  lea     rcx, [rbp+0A0h+var_D0]; this
0x18064de50  call    ?FreeUnused@CScreenDevice@Jot@@QEAAXXZ; Jot::CScreenDevice::FreeUnused(void)
0x18064de55  mov     rcx, rsi
0x18064de58  call    cs:__imp_GdipDisposeImage
0x18064de5e  test    rbx, rbx
0x18064de61  jnz     short loc_18064DE72
0x18064de63  xor     al, al
0x18064de65  jmp     short loc_18064DDFF
0x18064de67  mov     rcx, rbx; hmf
0x18064de6a  call    cs:__imp_DeleteEnhMetaFile
0x18064de70  jmp     short loc_18064DDFD
0x18064de72  mov     rcx, rbx; hmf
0x18064de75  call    cs:__imp_DeleteEnhMetaFile
0x18064de7b  jmp     short loc_18064DE63
```

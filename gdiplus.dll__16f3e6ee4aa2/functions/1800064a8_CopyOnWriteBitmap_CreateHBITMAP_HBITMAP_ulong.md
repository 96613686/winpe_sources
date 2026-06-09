# CopyOnWriteBitmap::CreateHBITMAP(HBITMAP__ * *,ulong)

- ea: `0x1800064a8`
- end: `0x1800067b6`
- name: `?CreateHBITMAP@CopyOnWriteBitmap@@AEAA?AW4Status@@PEAPEAUHBITMAP__@@K@Z`
- size: `782`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800061c8`
- `0x180006220`

## callees

- `0x1800064a8`
- `0x1800067dc`
- `0x180007264`
- `0x18000781c`
- `0x18002739c`
- `0x18005e5c0`
- `0x1800fe680`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x18000664b`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x180006771`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x18000664b`
- `api-ms-win-crt-runtime-l1-1-0!fesetround` at `0x180006771`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x18000663a`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800066ce`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x18000663a`
- `api-ms-win-crt-runtime-l1-1-0!fegetround` at `0x1800066ce`
- `GDI32!PatBlt` at `0x1800065f5`
- `GDI32!PatBlt` at `0x1800065f5`
- `GDI32!CreateBrushIndirect` at `0x1800065aa`
- `GDI32!CreateBrushIndirect` at `0x1800065aa`
- `GDI32!CreateDIBSection` at `0x18000654e`
- `GDI32!CreateDIBSection` at `0x18000654e`
- `GDI32!DeleteDC` at `0x180006706`
- `GDI32!DeleteDC` at `0x180006706`
- `GDI32!SelectObject` at `0x180006566`
- `GDI32!SelectObject` at `0x1800065c2`
- `GDI32!SelectObject` at `0x1800066ec`
- `GDI32!SelectObject` at `0x1800066fd`
- `GDI32!SelectObject` at `0x180006566`
- `GDI32!SelectObject` at `0x1800065c2`
- `GDI32!SelectObject` at `0x1800066ec`
- `GDI32!SelectObject` at `0x1800066fd`
- `GDI32!CreateCompatibleDC` at `0x1800064e5`
- `GDI32!CreateCompatibleDC` at `0x1800064e5`
- `GDI32!DeleteObject` at `0x18000671d`
- `GDI32!DeleteObject` at `0x1800067ab`
- `GDI32!DeleteObject` at `0x18000671d`
- `GDI32!DeleteObject` at `0x1800067ab`

## pseudocode

```c
void __fastcall __noreturn CopyOnWriteBitmap::CreateHBITMAP(LONG *a1, HBITMAP *a2, int a3)
{
  HGDIOBJ v5; // r13
  HDC CompatibleDC; // r15
  HBRUSH v7; // r12
  GpGraphics *v8; // r14
  HBITMAP v9; // rax
  HBITMAP v10; // rsi
  HBRUSH v11; // rax
  struct GpGraphics *v12; // rax
  signed __int32 v13; // eax
  int v14; // ebx
  int v15; // eax
  float v16; // xmm1_4
  unsigned int v17; // edx
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  float v19; // [rsp+38h] [rbp-C8h]
  float v20; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v21; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v22; // [rsp+48h] [rbp-B8h]
  void *ppvBits; // [rsp+50h] [rbp-B0h] BYREF
  HBITMAP *v24; // [rsp+58h] [rbp-A8h]
  HGDIOBJ h; // [rsp+60h] [rbp-A0h]
  LOGBRUSH plbrush; // [rsp+68h] [rbp-98h] BYREF
  BITMAPINFO pbmi; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v28[1504]; // [rsp+B0h] [rbp-50h] BYREF

  v24 = a2;
  v5 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    pbmi.bmiHeader.biWidth = a1[41];
    pbmi.bmiHeader.biHeight = a1[42];
    v7 = 0;
    ppvBits = 0;
    v8 = 0;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    v9 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
    v10 = v9;
    if ( v9 )
    {
      h = SelectObject(CompatibleDC, v9);
      if ( h )
      {
        HIDWORD(plbrush.lbHatch) = 0;
        plbrush.lbStyle = 0;
        *(_QWORD *)&plbrush.lbColor = ((unsigned __int8)a3 << 16) | BYTE2(a3) | (BYTE1(a3) << 8);
        v11 = CreateBrushIndirect(&plbrush);
        v7 = v11;
        if ( v11 )
        {
          v5 = SelectObject(CompatibleDC, v11);
          if ( v5 )
          {
            PatBlt(CompatibleDC, 0, 0, a1[41], a1[42], 0xF00021u);
            v12 = GpGraphics::GetFromHdc(CompatibleDC, 0);
            v8 = v12;
            if ( v12 )
            {
              if ( v12 == (struct GpGraphics *)-16LL )
              {
                v13 = 0;
                v22 = &v21;
              }
              else
              {
                v22 = (volatile signed __int32 *)((char *)v12 + 16);
                v13 = _InterlockedIncrement((volatile signed __int32 *)v12 + 4);
              }
              v21 = v13;
              if ( !v13 )
              {
                v14 = fegetround();
                if ( v14 != 256 )
                  fesetround(256);
                v15 = a1[41];
                v18 = 0;
                v16 = (float)a1[42];
                v19 = (float)v15;
                v20 = v16;
                GpBitmap::GpBitmap((GpBitmap *)v28, (const struct CopyOnWriteBitmap *)a1);
                if ( !(unsigned int)GpGraphics::DrawImage(v8, v28, &v18, &v18, 2, 0) )
                {
                  *v24 = v10;
                  v10 = 0;
                }
                GpBitmap::~GpBitmap((GpBitmap *)v28);
                if ( v14 != fegetround() )
                  fesetround(v14);
              }
              _InterlockedDecrement(v22);
            }
          }
        }
        SelectObject(CompatibleDC, h);
        if ( v5 )
          SelectObject(CompatibleDC, v5);
      }
    }
    DeleteDC(CompatibleDC);
    if ( v10 )
      DeleteObject(v10);
    if ( v7 )
      DeleteObject(v7);
    if ( v8 )
      GpGraphics::`scalar deleting destructor'(v8, v17);
  }
}

```

## disassembly

```asm
0x1800064a8  mov     [rsp-8+arg_18], rbx
0x1800064ad  push    rbp
0x1800064ae  push    rsi
0x1800064af  push    rdi
0x1800064b0  push    r12
0x1800064b2  push    r13
0x1800064b4  push    r14
0x1800064b6  push    r15
0x1800064b8  lea     rbp, [rsp-5A0h]
0x1800064c0  sub     rsp, 6A0h
0x1800064c7  mov     rax, cs:__security_cookie
0x1800064ce  xor     rax, rsp
0x1800064d1  mov     [rbp+5D0h+var_40], rax
0x1800064d8  mov     rdi, rcx
0x1800064db  mov     [rsp+6D0h+var_678], rdx
0x1800064e0  xor     ecx, ecx; hdc
0x1800064e2  mov     ebx, r8d
0x1800064e5  call    cs:__imp_CreateCompatibleDC
0x1800064eb  xor     r13d, r13d
0x1800064ee  mov     r15, rax
0x1800064f1  test    rax, rax
0x1800064f4  jz      loc_1800067A1
0x1800064fa  mov     eax, [rdi+0A4h]
0x180006500  lea     r9, [rsp+6D0h+ppvBits]; ppvBits
0x180006505  mov     [rsp+6D0h+pbmi.bmiHeader.biWidth], eax
0x180006509  lea     rdx, [rsp+6D0h+pbmi]; pbmi
0x18000650e  mov     eax, [rdi+0A8h]
0x180006514  xorps   xmm0, xmm0
0x180006517  mov     [rsp+6D0h+offset], r13d; offset
0x18000651c  xor     r8d, r8d; usage
0x18000651f  mov     rcx, r15; hdc
0x180006522  mov     [rbp+5D0h+pbmi.bmiHeader.biHeight], eax
0x180006525  mov     r12d, r13d
0x180006528  mov     [rsp+6D0h+ppvBits], r13
0x18000652d  mov     r14d, r13d
0x180006530  mov     qword ptr [rbp+5D0h+pbmi.bmiHeader.biClrImportant], r13
0x180006534  movdqu  xmmword ptr [rbp+5D0h+pbmi.bmiHeader.biSizeImage], xmm0
0x180006539  mov     [rsp+6D0h+pbmi.bmiHeader.biSize], 28h ; '('
0x180006541  mov     qword ptr [rbp+5D0h+pbmi.bmiHeader.biPlanes], 200001h
0x180006549  mov     [rsp+6D0h+hSection], r13; hSection
0x18000654e  call    cs:__imp_CreateDIBSection
0x180006554  mov     rsi, rax
0x180006557  test    rax, rax
0x18000655a  jz      loc_180006754
0x180006560  mov     rdx, rax; h
0x180006563  mov     rcx, r15; hdc
0x180006566  call    cs:__imp_SelectObject
0x18000656c  mov     [rsp+6D0h+h], rax
0x180006571  test    rax, rax
0x180006574  jz      loc_180006754
0x18000657a  mov     eax, ebx
0x18000657c  mov     [rsp+6D0h+plbrush.lbHatch], r13
0x180006581  shr     eax, 8
0x180006584  movzx   edx, al
0x180006587  mov     eax, ebx
0x180006589  shr     eax, 10h
0x18000658c  movzx   ecx, al
0x18000658f  shl     edx, 8
0x180006592  or      edx, ecx
0x180006594  movzx   eax, bl
0x180006597  shl     eax, 10h
0x18000659a  lea     rcx, [rsp+6D0h+plbrush]; plbrush
0x18000659f  or      edx, eax
0x1800065a1  mov     [rsp+6D0h+plbrush.lbStyle], r13d
0x1800065a6  mov     [rsp+6D0h+plbrush.lbColor], edx
0x1800065aa  call    cs:__imp_CreateBrushIndirect
0x1800065b0  mov     r12, rax
0x1800065b3  test    rax, rax
0x1800065b6  jz      loc_18000677C
0x1800065bc  mov     rdx, rax; h
0x1800065bf  mov     rcx, r15; hdc
0x1800065c2  call    cs:__imp_SelectObject
0x1800065c8  mov     r13, rax
0x1800065cb  test    rax, rax
0x1800065ce  jz      loc_18000677C
0x1800065d4  mov     eax, [rdi+0A8h]
0x1800065da  xor     r8d, r8d; y
0x1800065dd  mov     r9d, [rdi+0A4h]; w
0x1800065e4  xor     edx, edx; x
0x1800065e6  mov     [rsp+6D0h+offset], 0F00021h; rop
0x1800065ee  mov     rcx, r15; hdc
0x1800065f1  mov     dword ptr [rsp+6D0h+hSection], eax; h
0x1800065f5  call    cs:__imp_PatBlt
0x1800065fb  xor     edx, edx; void *
0x1800065fd  mov     rcx, r15; hdc
0x180006600  call    ?GetFromHdc@GpGraphics@@SAPEAV1@PEAUHDC__@@PEAX@Z
0x180006605  mov     r14, rax
0x180006608  test    rax, rax
0x18000660b  jz      loc_180006797
0x180006611  lea     rcx, [rax+10h]
0x180006615  test    rcx, rcx
0x180006618  jz      loc_180006786
0x18000661e  mov     [rsp+6D0h+var_688], rcx
0x180006623  mov     eax, 1
0x180006628  lock xadd [rcx], eax
0x18000662c  inc     eax
0x18000662e  mov     [rsp+6D0h+var_690], eax
0x180006632  test    eax, eax
0x180006634  jnz     loc_180006765
0x18000663a  call    cs:__imp_fegetround
0x180006640  mov     ecx, 100h; Round
0x180006645  mov     ebx, eax
0x180006647  cmp     eax, ecx
0x180006649  jz      short loc_180006651
0x18000664b  call    cs:__imp_fesetround
0x180006651  mov     eax, [rdi+0A4h]
0x180006657  lea     rcx, [rbp+5D0h+var_620]; this
0x18000665b  xorps   xmm0, xmm0
0x18000665e  mov     [rsp+6D0h+var_6A0], 0
0x180006667  xorps   xmm1, xmm1
0x18000666a  mov     rdx, rdi; struct CopyOnWriteBitmap *
0x18000666d  cvtsi2ss xmm0, rax
0x180006672  mov     eax, [rdi+0A8h]
0x180006678  cvtsi2ss xmm1, rax
0x18000667d  movss   [rsp+6D0h+var_698], xmm0
0x180006683  movss   [rsp+6D0h+var_694], xmm1
0x180006689  call    ??0GpBitmap@@AEAA@PEBVCopyOnWriteBitmap@@@Z
0x18000668e  lea     r9, [rsp+6D0h+var_6A0]
0x180006693  mov     qword ptr [rsp+6D0h+offset], 0
0x18000669c  lea     r8, [rsp+6D0h+var_6A0]
0x1800066a1  mov     dword ptr [rsp+6D0h+hSection], 2
0x1800066a9  lea     rdx, [rbp+5D0h+var_620]
0x1800066ad  mov     rcx, r14
0x1800066b0  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@AEBVRectF@@1W4Unit@@PEBVGpImageAttributes@@@Z
0x1800066b5  mov     edi, eax
0x1800066b7  test    eax, eax
0x1800066b9  jnz     short loc_1800066C5
0x1800066bb  mov     rax, [rsp+6D0h+var_678]
0x1800066c0  mov     [rax], rsi
0x1800066c3  xor     esi, esi
0x1800066c5  lea     rcx, [rbp+5D0h+var_620]; this
0x1800066c9  call    ??1GpBitmap@@EEAA@XZ
0x1800066ce  call    cs:__imp_fegetround
0x1800066d4  cmp     ebx, eax
0x1800066d6  jnz     loc_18000676F
0x1800066dc  mov     rax, [rsp+6D0h+var_688]
0x1800066e1  lock dec dword ptr [rax]
0x1800066e4  mov     rdx, [rsp+6D0h+h]; h
0x1800066e9  mov     rcx, r15; hdc
0x1800066ec  call    cs:__imp_SelectObject
0x1800066f2  test    r13, r13
0x1800066f5  jz      short loc_180006703
0x1800066f7  mov     rdx, r13; h
0x1800066fa  mov     rcx, r15; hdc
0x1800066fd  call    cs:__imp_SelectObject
0x180006703  mov     rcx, r15; hdc
0x180006706  call    cs:__imp_DeleteDC
0x18000670c  test    rsi, rsi
0x18000670f  jnz     loc_1800067A8
0x180006715  test    r12, r12
0x180006718  jz      short loc_180006723
0x18000671a  mov     rcx, r12; ho
0x18000671d  call    cs:__imp_DeleteObject
0x180006723  test    r14, r14
0x180006726  jnz     short loc_18000675B
0x180006728  mov     eax, edi
0x18000672a  mov     rcx, [rbp+5D0h+var_40]
0x180006731  xor     rcx, rsp; StackCookie
0x180006734  call    __security_check_cookie
0x180006739  mov     rbx, [rsp+6D0h+arg_18]
0x180006741  add     rsp, 6A0h
0x180006748  pop     r15
0x18000674a  pop     r14
0x18000674c  pop     r13
0x18000674e  pop     r12
0x180006750  pop     rdi
0x180006751  pop     rsi
0x180006752  pop     rbp
0x180006753  retn
0x180006754  mov     edi, 7
0x180006759  jmp     short loc_180006703
0x18000675b  mov     rcx, r14; this
0x18000675e  call    ??_GGpGraphics@@QEAAPEAXI@Z
0x180006763  jmp     short loc_180006728
0x180006765  mov     edi, 4
0x18000676a  jmp     loc_1800066DC
0x18000676f  mov     ecx, ebx; Round
0x180006771  call    cs:__imp_fesetround
0x180006777  jmp     loc_1800066DC
0x18000677c  mov     edi, 7
0x180006781  jmp     loc_1800066E4
0x180006786  lea     rcx, [rsp+6D0h+var_690]
0x18000678b  xor     eax, eax
0x18000678d  mov     [rsp+6D0h+var_688], rcx
0x180006792  jmp     loc_18000662E
0x180006797  mov     edi, 3
0x18000679c  jmp     loc_1800066E4
0x1800067a1  mov     edi, 7
0x1800067a6  jmp     short loc_180006728
0x1800067a8  mov     rcx, rsi; ho
0x1800067ab  call    cs:__imp_DeleteObject
0x1800067b1  jmp     loc_180006715
```

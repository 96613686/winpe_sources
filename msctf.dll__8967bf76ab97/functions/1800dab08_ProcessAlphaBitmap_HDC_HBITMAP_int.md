# ProcessAlphaBitmap(HDC__ *,HBITMAP__ *,int)

- ea: `0x1800dab08`
- end: `0x1800dada6`
- name: `?ProcessAlphaBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@PEAU1@H@Z`
- size: `670`
- prototype: `HBITMAP __fastcall(HDC hdc, HBITMAP hbm, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800db930`
- `0x1800dcc50`

## callees

- `0x1800dab08`
- `0x180106a60`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800dad76`
- `GDI32!DeleteObject` at `0x1800dad76`
- `GDI32!GetObjectW` at `0x1800dab74`
- `GDI32!GetObjectW` at `0x1800dab74`
- `GDI32!GetDIBits` at `0x1800dac4f`
- `GDI32!GetDIBits` at `0x1800dac4f`
- `GDI32!CreateDIBSection` at `0x1800dabe6`
- `GDI32!CreateDIBSection` at `0x1800dabe6`

## pseudocode

```c
HBITMAP __fastcall ProcessAlphaBitmap(HDC hdc, HBITMAP hbm, int a3)
{
  HBITMAP v6; // rdi
  LONG biHeight; // r8d
  LONG biWidth; // r10d
  unsigned int v9; // r11d
  __int64 i; // rdx
  unsigned int v11; // ebx
  __int64 v12; // r10
  unsigned int v13; // ecx
  LONG j; // r11d
  int v15; // ebx
  int v16; // esi
  __int64 v17; // r9
  int v18; // ecx
  __int64 v19; // rdx
  int v20; // eax
  void *ppvBits; // [rsp+40h] [rbp-29h] BYREF
  __int128 pv; // [rsp+48h] [rbp-21h] BYREF
  __int128 v24; // [rsp+58h] [rbp-11h]
  BITMAPINFO pbmi; // [rsp+68h] [rbp-1h] BYREF

  ppvBits = 0;
  pv = 0;
  v24 = 0;
  memset(&pbmi, 0, sizeof(pbmi));
  if ( hbm && GetObjectW(hbm, 32, &pv) && (_DWORD)v24 == 2097153 )
  {
    *(_QWORD *)&pbmi.bmiHeader.biWidth = *(_QWORD *)((char *)&pv + 4);
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    v6 = CreateDIBSection(hdc, &pbmi, 0, &ppvBits, 0, 0);
    if ( !v6 )
      return v6;
    *(_QWORD *)&pbmi.bmiHeader.biWidth = *(_QWORD *)((char *)&pv + 4);
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    if ( GetDIBits(hdc, hbm, 0, DWORD2(pv), ppvBits, &pbmi, 0) )
    {
      biHeight = pbmi.bmiHeader.biHeight;
      biWidth = pbmi.bmiHeader.biWidth;
      v9 = pbmi.bmiHeader.biWidth * pbmi.bmiHeader.biHeight;
      for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
      {
        if ( *((_BYTE *)ppvBits + 4 * i + 3) )
        {
          v11 = 0;
          if ( v9 )
          {
            v12 = 0;
            do
            {
              ++v11;
              v13 = *((_DWORD *)ppvBits + v12);
              *((_BYTE *)ppvBits + 4 * v12 + 2) = HIBYTE(v13) * BYTE2(v13) / 0xFFu;
              *((_BYTE *)ppvBits + 4 * v12 + 1) = HIBYTE(v13) * BYTE1(v13) / 0xFFu;
              *((_BYTE *)ppvBits + 4 * v12++) = HIBYTE(v13) * (unsigned __int8)v13 / 0xFFu;
            }
            while ( v11 < v9 );
            biHeight = pbmi.bmiHeader.biHeight;
            biWidth = pbmi.bmiHeader.biWidth;
          }
          if ( a3 )
          {
            for ( j = 0; j < biHeight; ++j )
            {
              v15 = biWidth * j;
              v16 = 0;
              if ( biWidth / 2 > 0 )
              {
                do
                {
                  v17 = v16 + v15;
                  v18 = v15 - v16++;
                  v19 = biWidth + v18;
                  v20 = *((_DWORD *)ppvBits + v17);
                  *((_DWORD *)ppvBits + v17) = *((_DWORD *)ppvBits + v19 - 1);
                  *((_DWORD *)ppvBits + v19 - 1) = v20;
                  biWidth = pbmi.bmiHeader.biWidth;
                }
                while ( v16 < pbmi.bmiHeader.biWidth / 2 );
                biHeight = pbmi.bmiHeader.biHeight;
              }
            }
          }
          return v6;
        }
      }
    }
    DeleteObject(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800dab08  mov     [rsp-8+arg_10], rbx
0x1800dab0d  mov     [rsp-8+arg_18], rsi
0x1800dab12  push    rbp
0x1800dab13  push    rdi
0x1800dab14  push    r12
0x1800dab16  push    r13
0x1800dab18  push    r14
0x1800dab1a  lea     rbp, [rsp-37h]
0x1800dab1f  sub     rsp, 0A0h
0x1800dab26  mov     rax, cs:__security_cookie
0x1800dab2d  xor     rax, rsp
0x1800dab30  mov     [rbp+57h+var_28], rax
0x1800dab34  xorps   xmm1, xmm1
0x1800dab37  xor     eax, eax
0x1800dab39  mov     [rbp+57h+ppvBits], rax
0x1800dab3d  xorps   xmm0, xmm0
0x1800dab40  mov     r14d, r8d
0x1800dab43  mov     rbx, rdx
0x1800dab46  mov     rsi, rcx
0x1800dab49  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biCompression], xmm1
0x1800dab4d  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], xmm1
0x1800dab51  movups  [rbp+57h+pv], xmm0
0x1800dab55  movups  [rbp+57h+var_68], xmm0
0x1800dab59  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSize], xmm1
0x1800dab5d  test    rdx, rdx
0x1800dab60  jz      loc_1800DAD7C
0x1800dab66  lea     r13d, [rax+20h]
0x1800dab6a  mov     rcx, rbx; h
0x1800dab6d  mov     edx, r13d; c
0x1800dab70  lea     r8, [rbp+57h+pv]; pv
0x1800dab74  call    cs:__imp_GetObjectW
0x1800dab7a  test    eax, eax
0x1800dab7c  jz      loc_1800DAD7C
0x1800dab82  lea     r12d, [r13-1Fh]
0x1800dab86  cmp     word ptr [rbp+57h+var_68], r12w
0x1800dab8b  jnz     loc_1800DAD7C
0x1800dab91  cmp     word ptr [rbp+57h+var_68+2], r13w
0x1800dab96  jnz     loc_1800DAD7C
0x1800dab9c  mov     eax, dword ptr [rbp+57h+pv+4]
0x1800dab9f  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x1800daba3  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x1800daba6  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1800dabaa  mov     eax, dword ptr [rbp+57h+pv+8]
0x1800dabad  xorps   xmm0, xmm0
0x1800dabb0  mov     [rsp+0C0h+offset], 0; offset
0x1800dabb8  xor     r8d, r8d; usage
0x1800dabbb  mov     rcx, rsi; hdc
0x1800dabbe  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1800dabc1  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x1800dabc6  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], 0
0x1800dabce  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800dabd5  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1800dabdd  mov     [rsp+0C0h+hSection], 0; hSection
0x1800dabe6  call    cs:__imp_CreateDIBSection
0x1800dabec  mov     rdi, rax
0x1800dabef  test    rax, rax
0x1800dabf2  jz      loc_1800DAD6E
0x1800dabf8  mov     ecx, dword ptr [rbp+57h+pv+4]
0x1800dabfb  lea     rax, [rbp+57h+pbmi]
0x1800dabff  mov     r9d, dword ptr [rbp+57h+pv+8]; cLines
0x1800dac03  xorps   xmm0, xmm0
0x1800dac06  mov     [rsp+0C0h+usage], 0; usage
0x1800dac0e  xor     r8d, r8d; start
0x1800dac11  mov     qword ptr [rsp+0C0h+offset], rax; lpbmi
0x1800dac16  mov     rdx, rbx; hbm
0x1800dac19  mov     rax, [rbp+57h+ppvBits]
0x1800dac1d  mov     [rbp+57h+pbmi.bmiHeader.biWidth], ecx
0x1800dac20  mov     rcx, rsi; hdc
0x1800dac23  mov     [rbp+57h+pbmi.bmiHeader.biHeight], 0
0x1800dac2a  mov     [rsp+0C0h+hSection], rax; lpvBits
0x1800dac2f  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x1800dac34  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], 0
0x1800dac3c  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800dac43  mov     [rbp+57h+pbmi.bmiHeader.biHeight], r9d
0x1800dac47  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1800dac4f  call    cs:__imp_GetDIBits
0x1800dac55  test    eax, eax
0x1800dac57  jz      loc_1800DAD73
0x1800dac5d  mov     r8d, [rbp+57h+pbmi.bmiHeader.biHeight]
0x1800dac61  mov     r11d, r8d
0x1800dac64  mov     r10d, [rbp+57h+pbmi.bmiHeader.biWidth]
0x1800dac68  imul    r11d, r10d
0x1800dac6c  xor     edx, edx
0x1800dac6e  cmp     edx, r11d
0x1800dac71  jnb     loc_1800DAD73
0x1800dac77  mov     rax, [rbp+57h+ppvBits]
0x1800dac7b  cmp     byte ptr [rax+rdx*4+3], 0
0x1800dac80  jnz     short loc_1800DAC87
0x1800dac82  add     edx, r12d
0x1800dac85  jmp     short loc_1800DAC6E
0x1800dac87  xor     ebx, ebx
0x1800dac89  test    r11d, r11d
0x1800dac8c  jz      short loc_1800DAD02
0x1800dac8e  xor     r10d, r10d
0x1800dac91  mov     esi, 80808081h
0x1800dac96  mov     r8, [rbp+57h+ppvBits]
0x1800dac9a  add     ebx, r12d
0x1800dac9d  mov     ecx, [r8+r10*4]
0x1800daca1  mov     eax, ecx
0x1800daca3  shr     eax, 10h
0x1800daca6  mov     r9d, ecx
0x1800daca9  movzx   edx, al
0x1800dacac  mov     eax, esi
0x1800dacae  shr     r9d, 18h
0x1800dacb2  imul    edx, r9d
0x1800dacb6  mul     edx
0x1800dacb8  mov     eax, ecx
0x1800dacba  shr     edx, 7
0x1800dacbd  mov     [r8+r10*4+2], dl
0x1800dacc2  shr     eax, 8
0x1800dacc5  movzx   edx, al
0x1800dacc8  mov     eax, esi
0x1800dacca  imul    edx, r9d
0x1800dacce  mul     edx
0x1800dacd0  mov     rax, [rbp+57h+ppvBits]
0x1800dacd4  shr     edx, 7
0x1800dacd7  mov     [rax+r10*4+1], dl
0x1800dacdc  mov     eax, esi
0x1800dacde  movzx   edx, cl
0x1800dace1  imul    edx, r9d
0x1800dace5  mul     edx
0x1800dace7  mov     rax, [rbp+57h+ppvBits]
0x1800daceb  shr     edx, 7
0x1800dacee  mov     [rax+r10*4], dl
0x1800dacf2  add     r10, r12
0x1800dacf5  cmp     ebx, r11d
0x1800dacf8  jb      short loc_1800DAC96
0x1800dacfa  mov     r8d, [rbp+57h+pbmi.bmiHeader.biHeight]
0x1800dacfe  mov     r10d, [rbp+57h+pbmi.bmiHeader.biWidth]
0x1800dad02  test    r14d, r14d
0x1800dad05  jz      short loc_1800DAD6E
0x1800dad07  xor     r11d, r11d
0x1800dad0a  test    r8d, r8d
0x1800dad0d  jle     short loc_1800DAD6E
0x1800dad0f  lea     r14d, [r11+2]
0x1800dad13  mov     eax, r10d
0x1800dad16  mov     ebx, r11d
0x1800dad19  cdq
0x1800dad1a  imul    ebx, r10d
0x1800dad1e  idiv    r14d
0x1800dad21  xor     esi, esi
0x1800dad23  test    eax, eax
0x1800dad25  jle     short loc_1800DAD66
0x1800dad27  mov     r8, [rbp+57h+ppvBits]
0x1800dad2b  lea     eax, [rsi+rbx]
0x1800dad2e  movsxd  r9, eax
0x1800dad31  mov     ecx, ebx
0x1800dad33  sub     ecx, esi
0x1800dad35  add     esi, r12d
0x1800dad38  add     ecx, r10d
0x1800dad3b  movsxd  rdx, ecx
0x1800dad3e  mov     eax, [r8+r9*4]
0x1800dad42  mov     ecx, [r8+rdx*4-4]
0x1800dad47  mov     [r8+r9*4], ecx
0x1800dad4b  mov     rcx, [rbp+57h+ppvBits]
0x1800dad4f  mov     [rcx+rdx*4-4], eax
0x1800dad53  mov     r10d, [rbp+57h+pbmi.bmiHeader.biWidth]
0x1800dad57  mov     eax, r10d
0x1800dad5a  cdq
0x1800dad5b  idiv    r14d
0x1800dad5e  cmp     esi, eax
0x1800dad60  jl      short loc_1800DAD27
0x1800dad62  mov     r8d, [rbp+57h+pbmi.bmiHeader.biHeight]
0x1800dad66  add     r11d, r12d
0x1800dad69  cmp     r11d, r8d
0x1800dad6c  jl      short loc_1800DAD13
0x1800dad6e  mov     rax, rdi
0x1800dad71  jmp     short loc_1800DAD7E
0x1800dad73  mov     rcx, rdi; ho
0x1800dad76  call    cs:__imp_DeleteObject
0x1800dad7c  xor     eax, eax
0x1800dad7e  mov     rcx, [rbp+57h+var_28]
0x1800dad82  xor     rcx, rsp; StackCookie
0x1800dad85  call    __security_check_cookie
0x1800dad8a  lea     r11, [rsp+0C0h+var_20]
0x1800dad92  mov     rbx, [r11+40h]
0x1800dad96  mov     rsi, [r11+48h]
0x1800dad9a  mov     rsp, r11
0x1800dad9d  pop     r14
0x1800dad9f  pop     r13
0x1800dada1  pop     r12
0x1800dada3  pop     rdi
0x1800dada4  pop     rbp
0x1800dada5  retn
```

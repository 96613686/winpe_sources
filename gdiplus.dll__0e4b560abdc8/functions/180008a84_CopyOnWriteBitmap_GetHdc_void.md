# CopyOnWriteBitmap::GetHdc(void)

- ea: `0x180008a84`
- end: `0x180008c64`
- name: `?GetHdc@CopyOnWriteBitmap@@AEAAPEAUHDC__@@XZ`
- size: `480`
- prototype: `__int64 __fastcall(__m128i *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008a38`

## callees

- `0x180008a84`
- `0x1800e9380`
- `0x1800ea0ec`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x180008ba1`
- `GDI32!CreateDIBSection` at `0x180008ba1`
- `GDI32!DeleteDC` at `0x180008c2c`
- `GDI32!DeleteDC` at `0x180008c2c`
- `GDI32!SelectObject` at `0x180008bec`
- `GDI32!SelectObject` at `0x180008bec`
- `GDI32!CreateCompatibleDC` at `0x180008b17`
- `GDI32!CreateCompatibleDC` at `0x180008b17`
- `GDI32!GetObjectA` at `0x180008bd0`
- `GDI32!GetObjectA` at `0x180008bd0`
- `GDI32!DeleteObject` at `0x180008c47`
- `GDI32!DeleteObject` at `0x180008c47`

## pseudocode

```c
__int64 __fastcall CopyOnWriteBitmap::GetHdc(__m128i *this)
{
  __int64 *v2; // r14
  __int64 v3; // rcx
  HDC CompatibleDC; // rax
  HDC v6; // rsi
  int v7; // r12d
  LONG v8; // r15d
  HBITMAP v9; // rdi
  _DWORD *v10; // rdi
  __m128i v11; // [rsp+30h] [rbp-D0h]
  BITMAPINFO pbmi; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pv[12]; // [rsp+B0h] [rbp-50h] BYREF
  int v14; // [rsp+BCh] [rbp-44h]
  int v15; // [rsp+D0h] [rbp-30h]

  if ( !this[13].m128i_i64[1] )
  {
    v11 = this[10];
    CompatibleDC = CreateCompatibleDC(0);
    v6 = CompatibleDC;
    if ( CompatibleDC )
    {
      v2 = &this[14].m128i_i64[1];
      memset(&pbmi.bmiHeader.biCompression, 0, 28);
      v7 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 8));
      v8 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 4));
      pbmi.bmiHeader.biSize = 40;
      *(_DWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      pbmi.bmiHeader.biHeight = -v7;
      pbmi.bmiHeader.biWidth = v8;
      v9 = CreateDIBSection(CompatibleDC, &pbmi, 0, (void **)&this[14].m128i_i64[1], 0, 0);
      memset_0(pv, 0, 0x68u);
      if ( v9 && GetObjectA(v9, 104, pv) && v15 && SelectObject(v6, v9) )
      {
        this[15].m128i_i64[0] = v14;
        this[13].m128i_i64[1] = (__int64)v6;
        this[14].m128i_i64[0] = (__int64)v9;
        this[15].m128i_i32[2] = v8;
        this[15].m128i_i32[3] = v7;
        goto LABEL_3;
      }
      DeleteDC(v6);
      if ( v9 )
        DeleteObject(v9);
    }
    return 0;
  }
  v2 = &this[14].m128i_i64[1];
LABEL_3:
  v3 = (unsigned int)(this[15].m128i_i32[3] * this[15].m128i_i32[2]);
  if ( (_DWORD)v3 )
  {
    v10 = (_DWORD *)*v2;
    while ( v3 )
    {
      *v10++ = 854796;
      --v3;
    }
  }
  return this[13].m128i_i64[1];
}

```

## disassembly

```asm
0x180008a84  mov     [rsp-8+arg_8], rbx
0x180008a89  mov     [rsp-8+arg_10], rsi
0x180008a8e  push    rbp
0x180008a8f  push    rdi
0x180008a90  push    r12
0x180008a92  push    r14
0x180008a94  push    r15
0x180008a96  lea     rbp, [rsp-30h]
0x180008a9b  sub     rsp, 130h
0x180008aa2  mov     rax, cs:__security_cookie
0x180008aa9  xor     rax, rsp
0x180008aac  mov     [rbp+50h+var_30], rax
0x180008ab0  cmp     qword ptr [rcx+0D8h], 0
0x180008ab8  mov     rbx, rcx
0x180008abb  jz      short loc_180008B09
0x180008abd  lea     r14, [rcx+0E8h]
0x180008ac4  mov     ecx, [rbx+0F8h]
0x180008aca  imul    ecx, [rbx+0FCh]
0x180008ad1  test    ecx, ecx
0x180008ad3  jnz     loc_180008C55
0x180008ad9  mov     rax, [rbx+0D8h]
0x180008ae0  mov     rcx, [rbp+50h+var_30]
0x180008ae4  xor     rcx, rsp; StackCookie
0x180008ae7  call    __security_check_cookie
0x180008aec  lea     r11, [rsp+150h+var_20]
0x180008af4  mov     rbx, [r11+38h]
0x180008af8  mov     rsi, [r11+40h]
0x180008afc  mov     rsp, r11
0x180008aff  pop     r15
0x180008b01  pop     r14
0x180008b03  pop     r12
0x180008b05  pop     rdi
0x180008b06  pop     rbp
0x180008b07  retn
0x180008b09  movups  xmm1, xmmword ptr [rcx+0A0h]
0x180008b10  xor     ecx, ecx; hdc
0x180008b12  movups  [rsp+150h+var_120], xmm1
0x180008b17  call    cs:__imp_CreateCompatibleDC
0x180008b1e  nop     dword ptr [rax+rax+00h]
0x180008b23  mov     rsi, rax
0x180008b26  test    rax, rax
0x180008b29  jz      loc_180008C3D
0x180008b2f  movups  xmm1, [rsp+150h+var_120]
0x180008b34  and     [rsp+150h+var_128], 0
0x180008b39  lea     r14, [rbx+0E8h]
0x180008b40  and     dword ptr [rbp+50h+pbmi.bmiColors.rgbBlue], 0
0x180008b44  lea     rdx, [rbp+50h+pbmi]; pbmi
0x180008b48  and     [rbp+50h+pbmi.bmiHeader.biCompression], 0
0x180008b4c  movdqa  xmm0, xmm1
0x180008b50  and     [rbp+50h+pbmi.bmiHeader.biSizeImage], 0
0x180008b54  mov     r9, r14; ppvBits
0x180008b57  and     [rbp+50h+pbmi.bmiHeader.biXPelsPerMeter], 0
0x180008b5b  xor     r8d, r8d; usage
0x180008b5e  and     [rbp+50h+pbmi.bmiHeader.biYPelsPerMeter], 0
0x180008b62  mov     rcx, rsi; hdc
0x180008b65  and     [rbp+50h+pbmi.bmiHeader.biClrUsed], 0
0x180008b69  and     [rbp+50h+pbmi.bmiHeader.biClrImportant], 0
0x180008b6d  and     [rsp+150h+var_130], 0
0x180008b73  psrldq  xmm1, 8
0x180008b78  movd    r12d, xmm1
0x180008b7d  psrldq  xmm0, 4
0x180008b82  movd    r15d, xmm0
0x180008b87  mov     eax, r12d
0x180008b8a  mov     [rbp+50h+pbmi.bmiHeader.biSize], 28h ; '('
0x180008b91  neg     eax
0x180008b93  mov     dword ptr [rbp+50h+pbmi.bmiHeader.biPlanes], 200001h
0x180008b9a  mov     [rbp+50h+pbmi.bmiHeader.biHeight], eax
0x180008b9d  mov     [rbp+50h+pbmi.bmiHeader.biWidth], r15d
0x180008ba1  call    cs:__imp_CreateDIBSection
0x180008ba8  nop     dword ptr [rax+rax+00h]
0x180008bad  xor     edx, edx; Val
0x180008baf  lea     rcx, [rbp+50h+pv]; void *
0x180008bb3  mov     rdi, rax
0x180008bb6  lea     r8d, [rdx+68h]; Size
0x180008bba  call    memset_0
0x180008bbf  test    rdi, rdi
0x180008bc2  jz      short loc_180008C29
0x180008bc4  lea     r8, [rbp+50h+pv]; pv
0x180008bc8  mov     edx, 68h ; 'h'; c
0x180008bcd  mov     rcx, rdi; h
0x180008bd0  call    cs:__imp_GetObjectA
0x180008bd7  nop     dword ptr [rax+rax+00h]
0x180008bdc  test    eax, eax
0x180008bde  jz      short loc_180008C29
0x180008be0  cmp     [rbp+50h+var_80], 0
0x180008be4  jz      short loc_180008C29
0x180008be6  mov     rdx, rdi; h
0x180008be9  mov     rcx, rsi; hdc
0x180008bec  call    cs:__imp_SelectObject
0x180008bf3  nop     dword ptr [rax+rax+00h]
0x180008bf8  test    rax, rax
0x180008bfb  jz      short loc_180008C29
0x180008bfd  movsxd  rax, [rbp+50h+var_94]
0x180008c01  mov     [rbx+0F0h], rax
0x180008c08  mov     [rbx+0D8h], rsi
0x180008c0f  mov     [rbx+0E0h], rdi
0x180008c16  mov     [rbx+0F8h], r15d
0x180008c1d  mov     [rbx+0FCh], r12d
0x180008c24  jmp     loc_180008AC4
0x180008c29  mov     rcx, rsi; hdc
0x180008c2c  call    cs:__imp_DeleteDC
0x180008c33  nop     dword ptr [rax+rax+00h]
0x180008c38  test    rdi, rdi
0x180008c3b  jnz     short loc_180008C44
0x180008c3d  xor     eax, eax
0x180008c3f  jmp     loc_180008AE0
0x180008c44  mov     rcx, rdi; ho
0x180008c47  call    cs:__imp_DeleteObject
0x180008c4e  nop     dword ptr [rax+rax+00h]
0x180008c53  jmp     short loc_180008C3D
0x180008c55  mov     rdi, [r14]
0x180008c58  mov     eax, 0D0B0Ch
0x180008c5d  rep stosd
0x180008c5f  jmp     loc_180008AD9
```

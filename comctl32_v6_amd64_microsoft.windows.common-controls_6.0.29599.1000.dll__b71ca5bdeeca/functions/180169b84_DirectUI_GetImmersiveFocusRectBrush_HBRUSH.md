# DirectUI::GetImmersiveFocusRectBrush(HBRUSH__ * *)

- ea: `0x180169b84`
- end: `0x180169d14`
- name: `?GetImmersiveFocusRectBrush@DirectUI@@YAJPEAPEAUHBRUSH__@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(DirectUI *__hidden this, HBRUSH *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18016a46c`

## callees

- `0x180107480`
- `0x180114520`
- `0x180169b84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180169bb4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180169bb4`
- `GDI32!DeleteObject` at `0x180169cdf`
- `GDI32!DeleteObject` at `0x180169cdf`
- `GDI32!SelectObject` at `0x180169c4a`
- `GDI32!SelectObject` at `0x180169ccd`
- `GDI32!SelectObject` at `0x180169c4a`
- `GDI32!SelectObject` at `0x180169ccd`
- `GDI32!DeleteDC` at `0x180169cd6`
- `GDI32!DeleteDC` at `0x180169cd6`
- `GDI32!CreateCompatibleDC` at `0x180169c2c`
- `GDI32!CreateCompatibleDC` at `0x180169c2c`
- `GDI32!CreatePatternBrush` at `0x180169cad`
- `GDI32!CreatePatternBrush` at `0x180169cad`
- `GDI32!CreateDIBSection` at `0x180169c12`
- `GDI32!CreateDIBSection` at `0x180169c12`
- `GDI32!SetPixel` at `0x180169c6a`
- `GDI32!SetPixel` at `0x180169c81`
- `GDI32!SetPixel` at `0x180169c92`
- `GDI32!SetPixel` at `0x180169ca4`
- `GDI32!SetPixel` at `0x180169c6a`
- `GDI32!SetPixel` at `0x180169c81`
- `GDI32!SetPixel` at `0x180169c92`
- `GDI32!SetPixel` at `0x180169ca4`

## pseudocode

```c
__int64 __fastcall DirectUI::GetImmersiveFocusRectBrush(DirectUI *this, HBRUSH *a2)
{
  unsigned int Error; // ebx
  _QWORD *Value; // rbp
  HBITMAP v5; // rsi
  HDC CompatibleDC; // rax
  HDC v7; // rdi
  HGDIOBJ v8; // r14
  HBRUSH PatternBrush; // rax
  void *ppvBits; // [rsp+30h] [rbp-68h] BYREF
  BITMAPINFO pbmi; // [rsp+38h] [rbp-60h] BYREF

  Error = 0;
  Value = TlsGetValue(DirectUI::g_dwElSlot);
  if ( !Value[9] )
  {
    pbmi.bmiHeader.biWidth = 2;
    pbmi.bmiHeader.biHeight = 2;
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 1572865;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    ppvBits = 0;
    v5 = CreateDIBSection(0, &pbmi, 0, &ppvBits, 0, 0);
    if ( v5 )
    {
      CompatibleDC = CreateCompatibleDC(0);
      v7 = CompatibleDC;
      if ( CompatibleDC )
      {
        v8 = SelectObject(CompatibleDC, v5);
        if ( v8 )
        {
          SetPixel(v7, 0, 0, 0);
          SetPixel(v7, 1, 0, 0xFFFFFFu);
          SetPixel(v7, 0, 1, 0xFFFFFFu);
          SetPixel(v7, 1, 1, 0);
          PatternBrush = CreatePatternBrush(v5);
          Value[9] = PatternBrush;
          if ( PatternBrush )
            Error = 0;
          else
            Error = ResultFromKnownLastError();
          SelectObject(v7, v8);
        }
        else
        {
          Error = -2147467259;
        }
        DeleteDC(v7);
      }
      else
      {
        Error = -2147024882;
      }
      DeleteObject(v5);
    }
    else
    {
      Error = -2147024882;
    }
  }
  *(_QWORD *)this = Value[9];
  return Error;
}

```

## disassembly

```asm
0x180169b84  mov     [rsp+arg_8], rbx
0x180169b89  mov     [rsp+arg_10], rbp
0x180169b8e  push    rsi
0x180169b8f  push    rdi
0x180169b90  push    r13
0x180169b92  push    r14
0x180169b94  push    r15
0x180169b96  sub     rsp, 70h
0x180169b9a  mov     rax, cs:__security_cookie
0x180169ba1  xor     rax, rsp
0x180169ba4  mov     [rsp+98h+var_30], rax
0x180169ba9  mov     r15, rcx
0x180169bac  xor     ebx, ebx
0x180169bae  mov     ecx, cs:?g_dwElSlot@DirectUI@@3KA; dwTlsIndex
0x180169bb4  call    cs:__imp_TlsGetValue
0x180169bba  mov     rbp, rax
0x180169bbd  cmp     [rax+48h], rbx
0x180169bc1  jnz     loc_180169CE5
0x180169bc7  lea     eax, [rbx+2]
0x180169bca  mov     [rsp+98h+offset], ebx; offset
0x180169bce  xorps   xmm0, xmm0
0x180169bd1  mov     [rsp+98h+pbmi.bmiHeader.biWidth], eax
0x180169bd5  lea     r9, [rsp+98h+ppvBits]; ppvBits
0x180169bda  mov     [rsp+98h+pbmi.bmiHeader.biHeight], eax
0x180169bde  xor     r8d, r8d; usage
0x180169be1  mov     qword ptr [rsp+98h+pbmi.bmiHeader.biClrImportant], rbx
0x180169be6  lea     rdx, [rsp+98h+pbmi]; pbmi
0x180169beb  mov     [rsp+98h+pbmi.bmiHeader.biSize], 28h ; '('
0x180169bf3  xor     ecx, ecx; hdc
0x180169bf5  mov     qword ptr [rsp+98h+pbmi.bmiHeader.biPlanes], 180001h
0x180169bfe  movdqu  xmmword ptr [rsp+98h+pbmi.bmiHeader.biSizeImage], xmm0
0x180169c04  lea     r13d, [rbx+1]
0x180169c08  mov     [rsp+98h+ppvBits], rbx
0x180169c0d  mov     [rsp+98h+hSection], rbx; hSection
0x180169c12  call    cs:__imp_CreateDIBSection
0x180169c18  mov     rsi, rax
0x180169c1b  test    rax, rax
0x180169c1e  jnz     short loc_180169C2A
0x180169c20  mov     ebx, 8007000Eh
0x180169c25  jmp     loc_180169CE5
0x180169c2a  xor     ecx, ecx; hdc
0x180169c2c  call    cs:__imp_CreateCompatibleDC
0x180169c32  mov     rdi, rax
0x180169c35  test    rax, rax
0x180169c38  jnz     short loc_180169C44
0x180169c3a  mov     ebx, 8007000Eh
0x180169c3f  jmp     loc_180169CDC
0x180169c44  mov     rdx, rsi; h
0x180169c47  mov     rcx, rdi; hdc
0x180169c4a  call    cs:__imp_SelectObject
0x180169c50  mov     r14, rax
0x180169c53  test    rax, rax
0x180169c56  jnz     short loc_180169C5F
0x180169c58  mov     ebx, 80004005h
0x180169c5d  jmp     short loc_180169CD3
0x180169c5f  xor     r9d, r9d; color
0x180169c62  xor     r8d, r8d; y
0x180169c65  xor     edx, edx; x
0x180169c67  mov     rcx, rdi; hdc
0x180169c6a  call    cs:__imp_SetPixel
0x180169c70  mov     ebx, 0FFFFFFh
0x180169c75  xor     r8d, r8d; y
0x180169c78  mov     r9d, ebx; color
0x180169c7b  mov     edx, r13d; x
0x180169c7e  mov     rcx, rdi; hdc
0x180169c81  call    cs:__imp_SetPixel
0x180169c87  mov     r9d, ebx; color
0x180169c8a  mov     r8d, r13d; y
0x180169c8d  xor     edx, edx; x
0x180169c8f  mov     rcx, rdi; hdc
0x180169c92  call    cs:__imp_SetPixel
0x180169c98  xor     r9d, r9d; color
0x180169c9b  mov     r8d, r13d; y
0x180169c9e  mov     edx, r13d; x
0x180169ca1  mov     rcx, rdi; hdc
0x180169ca4  call    cs:__imp_SetPixel
0x180169caa  mov     rcx, rsi; hbm
0x180169cad  call    cs:__imp_CreatePatternBrush
0x180169cb3  mov     [rbp+48h], rax
0x180169cb7  test    rax, rax
0x180169cba  jz      short loc_180169CC0
0x180169cbc  xor     ebx, ebx
0x180169cbe  jmp     short loc_180169CC7
0x180169cc0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180169cc5  mov     ebx, eax
0x180169cc7  mov     rdx, r14; h
0x180169cca  mov     rcx, rdi; hdc
0x180169ccd  call    cs:__imp_SelectObject
0x180169cd3  mov     rcx, rdi; hdc
0x180169cd6  call    cs:__imp_DeleteDC
0x180169cdc  mov     rcx, rsi; ho
0x180169cdf  call    cs:__imp_DeleteObject
0x180169ce5  mov     rax, [rbp+48h]
0x180169ce9  mov     [r15], rax
0x180169cec  mov     eax, ebx
0x180169cee  mov     rcx, [rsp+98h+var_30]
0x180169cf3  xor     rcx, rsp; StackCookie
0x180169cf6  call    __security_check_cookie
0x180169cfb  lea     r11, [rsp+98h+var_28]
0x180169d00  mov     rbx, [r11+38h]
0x180169d04  mov     rbp, [r11+40h]
0x180169d08  mov     rsp, r11
0x180169d0b  pop     r15
0x180169d0d  pop     r14
0x180169d0f  pop     r13
0x180169d11  pop     rdi
0x180169d12  pop     rsi
0x180169d13  retn
```

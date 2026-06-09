# DWriteCore::Binding::Windows::GdiBitmap::CreateBitmap(HDC__ *,uint,uint)

- ea: `0x180293b18`
- end: `0x180293c47`
- name: `?CreateBitmap@GdiBitmap@Windows@Binding@DWriteCore@@CA?AUBitmap@1234@PEAUHDC__@@II@Z`
- size: `303`
- prototype: `static struct DWriteCore::Binding::Windows::GdiBitmap::Bitmap __high(HDC, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1802939c0`
- `0x180293d10`

## callees

- `0x180212490`
- `0x180290fac`
- `0x180293b18`
- `0x1802bda68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180293bbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180293bbb`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180293be8`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180293be8`

## pseudocode

```c
HBITMAP *__fastcall DWriteCore::Binding::Windows::GdiBitmap::CreateBitmap(
        HBITMAP *a1,
        HDC a2,
        unsigned int a3,
        unsigned int a4)
{
  HBITMAP v8; // rax
  HBITMAP v9; // rcx
  void *ppvBits; // [rsp+30h] [rbp-50h] BYREF
  BITMAPINFO pbmi; // [rsp+40h] [rbp-40h] BYREF

  ppvBits = a1;
  if ( !a2 )
    goto LABEL_12;
  if ( !a3 || !a4 )
  {
    *(_OWORD *)(a1 + 1) = 0;
    *a1 = 0;
    return a1;
  }
  pbmi.bmiHeader.biSize = 40;
  memset(&pbmi.bmiHeader.biWidth, 0, 40);
  if ( a3 > 0x7FFFFFFF || (pbmi.bmiHeader.biWidth = a3, a4 > 0x7FFFFFFF) || a4 == 0x80000000 )
    DWriteCore::SafeIntExceptionHandler::SafeIntOnOverflow();
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  pbmi.bmiHeader.biHeight = -a4;
  SetLastError(0);
  ppvBits = 0;
  v8 = CreateDIBSection(a2, &pbmi, 0, &ppvBits, 0, 0);
  if ( !v8 )
LABEL_12:
    DWriteCore::Binding::Windows::ThrowLastError((DWriteCore::Binding::Windows *)a1);
  v9 = (HBITMAP)ppvBits;
  *a1 = v8;
  a1[2] = v9;
  *((_DWORD *)a1 + 2) = a3;
  *((_DWORD *)a1 + 3) = a4;
  return a1;
}

```

## disassembly

```asm
0x180293b18  mov     [rsp-18h+arg_10], rbx
0x180293b1d  mov     [rsp-18h+arg_18], rsi
0x180293b22  push    rbp
0x180293b23  push    rdi
0x180293b24  push    r14
0x180293b26  mov     rbp, rsp
0x180293b29  sub     rsp, 80h
0x180293b30  mov     rax, cs:__security_cookie
0x180293b37  xor     rax, rsp
0x180293b3a  mov     [rbp+var_10], rax
0x180293b3e  mov     [rbp+ppvBits], rcx
0x180293b42  mov     edi, r9d
0x180293b45  mov     esi, r8d
0x180293b48  mov     r14, rdx
0x180293b4b  mov     rbx, rcx
0x180293b4e  test    rdx, rdx
0x180293b51  jz      loc_180293C41
0x180293b57  test    r8d, r8d
0x180293b5a  jz      loc_180293C2B
0x180293b60  test    r9d, r9d
0x180293b63  jz      loc_180293C2B
0x180293b69  xor     eax, eax
0x180293b6b  mov     [rbp+pbmi.bmiHeader.biSize], 28h ; '('
0x180293b72  xorps   xmm0, xmm0
0x180293b75  mov     qword ptr [rbp+pbmi.bmiHeader.biClrImportant], rax
0x180293b79  mov     eax, 7FFFFFFFh
0x180293b7e  movups  xmmword ptr [rbp+pbmi.bmiHeader.biWidth], xmm0
0x180293b82  movups  xmmword ptr [rbp+pbmi.bmiHeader.biSizeImage], xmm0
0x180293b86  cmp     r8d, eax
0x180293b89  ja      loc_180293C3B
0x180293b8f  mov     [rbp+pbmi.bmiHeader.biWidth], r8d
0x180293b93  cmp     r9d, eax
0x180293b96  ja      loc_180293C3B
0x180293b9c  cmp     r9d, 80000000h
0x180293ba3  jz      loc_180293C3B
0x180293ba9  mov     eax, r9d
0x180293bac  mov     qword ptr [rbp+pbmi.bmiHeader.biPlanes], 200001h
0x180293bb4  neg     eax
0x180293bb6  xor     ecx, ecx; dwErrCode
0x180293bb8  mov     [rbp+pbmi.bmiHeader.biHeight], eax
0x180293bbb  call    cs:__imp_SetLastError
0x180293bc1  lea     r9, [rbp+ppvBits]; ppvBits
0x180293bc5  mov     [rsp+80h+offset], 0; offset
0x180293bcd  xor     r8d, r8d; usage
0x180293bd0  mov     [rbp+ppvBits], 0
0x180293bd8  lea     rdx, [rbp+pbmi]; pbmi
0x180293bdc  mov     [rsp+80h+hSection], 0; hSection
0x180293be5  mov     rcx, r14; hdc
0x180293be8  call    cs:__imp_CreateDIBSection
0x180293bee  test    rax, rax
0x180293bf1  jz      short loc_180293C41
0x180293bf3  mov     rcx, [rbp+ppvBits]
0x180293bf7  mov     [rbx], rax
0x180293bfa  mov     [rbx+10h], rcx
0x180293bfe  mov     [rbx+8], esi
0x180293c01  mov     [rbx+0Ch], edi
0x180293c04  mov     rax, rbx
0x180293c07  mov     rcx, [rbp+var_10]
0x180293c0b  xor     rcx, rsp; StackCookie
0x180293c0e  call    __security_check_cookie
0x180293c13  lea     r11, [rsp+80h+var_s0]
0x180293c1b  mov     rbx, [r11+30h]
0x180293c1f  mov     rsi, [r11+38h]
0x180293c23  mov     rsp, r11
0x180293c26  pop     r14
0x180293c28  pop     rdi
0x180293c29  pop     rbp
0x180293c2a  retn
0x180293c2b  xorps   xmm0, xmm0
0x180293c2e  movups  xmmword ptr [rcx+8], xmm0
0x180293c32  mov     qword ptr [rcx], 0
0x180293c39  jmp     short loc_180293C04
0x180293c3b  call    ?SafeIntOnOverflow@SafeIntExceptionHandler@DWriteCore@@SAXXZ; DWriteCore::SafeIntExceptionHandler::SafeIntOnOverflow(void)
0x180293c41  call    ?ThrowLastError@Windows@Binding@DWriteCore@@YAXXZ; DWriteCore::Binding::Windows::ThrowLastError(void)
```

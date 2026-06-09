# Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)

- ea: `0x18002ced8`
- end: `0x18002cf96`
- name: `?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(HDC, const struct tagSIZE *, void **, HBITMAP *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cf9c`

## callees

- `0x18002ced8`
- `0x180031070`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x18002cf5a`
- `GDI32!CreateDIBSection` at `0x18002cf5a`
- `USER32!ReleaseDC` at `0x18002cf68`
- `USER32!ReleaseDC` at `0x18002cf68`
- `USER32!GetDC` at `0x18002cf2d`
- `USER32!GetDC` at `0x18002cf2d`

## pseudocode

```c
__int64 __fastcall Create32BitHBITMAP(HDC a1, const struct tagSIZE *a2, void **a3, HBITMAP *a4)
{
  HDC DC; // rax
  HDC v6; // rdi
  __int64 result; // rax
  BITMAPINFO pbmi; // [rsp+30h] [rbp-48h] BYREF

  *a4 = 0;
  *(struct tagSIZE *)&pbmi.bmiHeader.biWidth = *a2;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  pbmi.bmiHeader.biSize = 40;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  DC = GetDC(0);
  v6 = DC;
  if ( DC )
  {
    *a4 = CreateDIBSection(DC, &pbmi, 0, 0, 0, 0);
    ReleaseDC(0, v6);
  }
  result = 2147942414LL;
  if ( *a4 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18002ced8  mov     [rsp+arg_0], rbx
0x18002cedd  push    rdi
0x18002cede  sub     rsp, 70h
0x18002cee2  mov     rax, cs:__security_cookie
0x18002cee9  xor     rax, rsp
0x18002ceec  mov     [rsp+78h+var_18], rax
0x18002cef1  mov     qword ptr [r9], 0
0x18002cef8  xorps   xmm0, xmm0
0x18002cefb  mov     eax, [rdx]
0x18002cefd  xor     ecx, ecx; hWnd
0x18002ceff  mov     [rsp+78h+pbmi.bmiHeader.biWidth], eax
0x18002cf03  mov     rbx, r9
0x18002cf06  mov     eax, [rdx+4]
0x18002cf09  mov     [rsp+78h+pbmi.bmiHeader.biHeight], eax
0x18002cf0d  movdqu  xmmword ptr [rsp+78h+pbmi.bmiHeader.biSizeImage], xmm0
0x18002cf13  mov     qword ptr [rsp+78h+pbmi.bmiHeader.biClrImportant], 0
0x18002cf1c  mov     [rsp+78h+pbmi.bmiHeader.biSize], 28h ; '('
0x18002cf24  mov     qword ptr [rsp+78h+pbmi.bmiHeader.biPlanes], 200001h
0x18002cf2d  call    cs:__imp_GetDC
0x18002cf33  mov     rdi, rax
0x18002cf36  test    rax, rax
0x18002cf39  jz      short loc_18002CF6E
0x18002cf3b  mov     [rsp+78h+offset], 0; offset
0x18002cf43  lea     rdx, [rsp+78h+pbmi]; pbmi
0x18002cf48  xor     r9d, r9d; ppvBits
0x18002cf4b  mov     [rsp+78h+hSection], 0; hSection
0x18002cf54  xor     r8d, r8d; usage
0x18002cf57  mov     rcx, rax; hdc
0x18002cf5a  call    cs:__imp_CreateDIBSection
0x18002cf60  mov     rdx, rdi; hDC
0x18002cf63  xor     ecx, ecx; hWnd
0x18002cf65  mov     [rbx], rax
0x18002cf68  call    cs:__imp_ReleaseDC
0x18002cf6e  xor     ecx, ecx
0x18002cf70  mov     eax, 8007000Eh
0x18002cf75  cmp     [rbx], rcx
0x18002cf78  cmovnz  eax, ecx
0x18002cf7b  mov     rcx, [rsp+78h+var_18]
0x18002cf80  xor     rcx, rsp; StackCookie
0x18002cf83  call    __security_check_cookie
0x18002cf88  mov     rbx, [rsp+78h+arg_0]
0x18002cf90  add     rsp, 70h
0x18002cf94  pop     rdi
0x18002cf95  retn
```

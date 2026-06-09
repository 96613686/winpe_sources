# Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)

- ea: `0x180049940`
- end: `0x180049a00`
- name: `?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(HDC, const struct tagSIZE *, void **, HBITMAP *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180049a08`

## callees

- `0x18001e1e0`
- `0x180049940`

## import_xrefs

- `USER32!GetDC` at `0x180049997`
- `USER32!GetDC` at `0x180049997`
- `USER32!ReleaseDC` at `0x1800499d2`
- `USER32!ReleaseDC` at `0x1800499d2`
- `GDI32!CreateDIBSection` at `0x1800499c4`
- `GDI32!CreateDIBSection` at `0x1800499c4`

## pseudocode

```c
__int64 __fastcall Create32BitHBITMAP(HDC a1, const struct tagSIZE *a2, void **a3, HBITMAP *a4)
{
  LONG cx; // eax
  HDC DC; // rax
  HDC v7; // rdi
  __int64 result; // rax
  BITMAPINFO pbmi; // [rsp+30h] [rbp-48h] BYREF

  *a4 = 0;
  cx = a2->cx;
  memset(&pbmi.bmiHeader.biWidth, 0, 40);
  pbmi.bmiHeader.biWidth = cx;
  pbmi.bmiHeader.biHeight = a2->cy;
  pbmi.bmiHeader.biSize = 40;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  DC = GetDC(0);
  v7 = DC;
  if ( DC )
  {
    *a4 = CreateDIBSection(DC, &pbmi, 0, 0, 0, 0);
    ReleaseDC(0, v7);
  }
  result = 2147942414LL;
  if ( *a4 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180049940  mov     [rsp+arg_0], rbx
0x180049945  push    rdi
0x180049946  sub     rsp, 70h
0x18004994a  mov     rax, cs:__security_cookie
0x180049951  xor     rax, rsp
0x180049954  mov     [rsp+78h+var_18], rax
0x180049959  xor     eax, eax
0x18004995b  mov     qword ptr [r9], 0
0x180049962  xorps   xmm0, xmm0
0x180049965  mov     qword ptr [rsp+78h+pbmi.bmiHeader.biClrImportant], rax
0x18004996a  mov     eax, [rdx]
0x18004996c  xor     ecx, ecx; hWnd
0x18004996e  movups  xmmword ptr [rsp+78h+pbmi.bmiHeader.biWidth], xmm0
0x180049973  mov     [rsp+78h+pbmi.bmiHeader.biWidth], eax
0x180049977  mov     rbx, r9
0x18004997a  mov     eax, [rdx+4]
0x18004997d  mov     [rsp+78h+pbmi.bmiHeader.biHeight], eax
0x180049981  movups  xmmword ptr [rsp+78h+pbmi.bmiHeader.biSizeImage], xmm0
0x180049986  mov     [rsp+78h+pbmi.bmiHeader.biSize], 28h ; '('
0x18004998e  mov     qword ptr [rsp+78h+pbmi.bmiHeader.biPlanes], 200001h
0x180049997  call    cs:__imp_GetDC
0x18004999d  mov     rdi, rax
0x1800499a0  test    rax, rax
0x1800499a3  jz      short loc_1800499D8
0x1800499a5  mov     [rsp+78h+offset], 0; offset
0x1800499ad  lea     rdx, [rsp+78h+pbmi]; pbmi
0x1800499b2  xor     r9d, r9d; ppvBits
0x1800499b5  mov     [rsp+78h+hSection], 0; hSection
0x1800499be  xor     r8d, r8d; usage
0x1800499c1  mov     rcx, rax; hdc
0x1800499c4  call    cs:__imp_CreateDIBSection
0x1800499ca  mov     rdx, rdi; hDC
0x1800499cd  xor     ecx, ecx; hWnd
0x1800499cf  mov     [rbx], rax
0x1800499d2  call    cs:__imp_ReleaseDC
0x1800499d8  xor     ecx, ecx
0x1800499da  mov     eax, 8007000Eh
0x1800499df  cmp     [rbx], rcx
0x1800499e2  cmovnz  eax, ecx
0x1800499e5  mov     rcx, [rsp+78h+var_18]
0x1800499ea  xor     rcx, rsp; StackCookie
0x1800499ed  call    __security_check_cookie
0x1800499f2  mov     rbx, [rsp+78h+arg_0]
0x1800499fa  add     rsp, 70h
0x1800499fe  pop     rdi
0x1800499ff  retn
```

# CGhostWindow::UpdateThumbnailRect(void)

- ea: `0x1800077ac`
- end: `0x1800078ad`
- name: `?UpdateThumbnailRect@CGhostWindow@@AEAAHXZ`
- size: `257`
- prototype: `__int64 __fastcall(CGhostWindow *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180006bb8`
- `0x180007530`

## callees

- `0x180001190`
- `0x1800077ac`

## import_xrefs

- `USER32!OffsetRect` at `0x18000785c`
- `USER32!OffsetRect` at `0x18000785c`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x1800077f4`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x1800077f4`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18000780e`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18000780e`
- `ext-ms-win-ntuser-window-l1-1-2!ClientToScreen` at `0x180007820`
- `ext-ms-win-ntuser-window-l1-1-2!ClientToScreen` at `0x180007820`
- `dwmapi!DwmUpdateThumbnailProperties` at `0x180007871`
- `dwmapi!DwmUpdateThumbnailProperties` at `0x180007871`

## pseudocode

```c
_BOOL8 __fastcall CGhostWindow::UpdateThumbnailRect(CGhostWindow *this)
{
  bool v1; // zf
  BOOL ClientRect; // eax
  LONG x; // ecx
  void *v5; // rcx
  tagPOINT Point; // [rsp+20h] [rbp-60h] BYREF
  struct tagRECT v8; // [rsp+28h] [rbp-58h] BYREF
  DWM_THUMBNAIL_PROPERTIES ptnProperties; // [rsp+38h] [rbp-48h] BYREF
  struct tagRECT Rect; // [rsp+68h] [rbp-18h] BYREF

  v1 = (*((_DWORD *)this + 28) & 0x400000) == 0;
  Point = 0;
  v8 = 0;
  Rect = 0;
  if ( !v1 )
  {
    ClientRect = GetClientRect(*((HWND *)this + 6), &Rect);
    x = Point.x;
    if ( ClientRect )
      x = Rect.right;
    Point.x = x;
  }
  if ( GetWindowRect(*((HWND *)this + 6), &v8) )
  {
    if ( ClientToScreen(*((HWND *)this + 6), &Point) )
    {
      memset(&ptnProperties, 0, sizeof(ptnProperties));
      ptnProperties.rcDestination.right = v8.right - v8.left;
      ptnProperties.rcDestination.bottom = v8.bottom - v8.top;
      OffsetRect(&ptnProperties.rcDestination, v8.left - Point.x, v8.top - Point.y);
      v5 = (void *)*((_QWORD *)this + 18);
      ptnProperties.dwFlags |= 1u;
      if ( DwmUpdateThumbnailProperties(v5, &ptnProperties) >= 0 )
        *((_DWORD *)this + 38) = 0;
    }
  }
  return *((_DWORD *)this + 38) == 0;
}

```

## disassembly

```asm
0x1800077ac  mov     [rsp-8+arg_8], rbx
0x1800077b1  push    rbp
0x1800077b2  mov     rbp, rsp
0x1800077b5  sub     rsp, 80h
0x1800077bc  mov     rax, cs:__security_cookie
0x1800077c3  xor     rax, rsp
0x1800077c6  mov     [rbp+var_8], rax
0x1800077ca  test    dword ptr [rcx+70h], 400000h
0x1800077d1  xorps   xmm0, xmm0
0x1800077d4  xorps   xmm1, xmm1
0x1800077d7  mov     qword ptr [rbp+Point.x], 0
0x1800077df  movups  xmmword ptr [rbp+var_58.left], xmm0
0x1800077e3  mov     rbx, rcx
0x1800077e6  movups  xmmword ptr [rbp+Rect.left], xmm1
0x1800077ea  jz      short loc_180007806
0x1800077ec  mov     rcx, [rcx+30h]; hWnd
0x1800077f0  lea     rdx, [rbp+Rect]; lpRect
0x1800077f4  call    cs:__imp_GetClientRect
0x1800077fa  mov     ecx, [rbp+Point.x]
0x1800077fd  test    eax, eax
0x1800077ff  cmovnz  ecx, [rbp+Rect.right]
0x180007803  mov     [rbp+Point.x], ecx
0x180007806  mov     rcx, [rbx+30h]; hWnd
0x18000780a  lea     rdx, [rbp+var_58]; lpRect
0x18000780e  call    cs:__imp_GetWindowRect
0x180007814  test    eax, eax
0x180007816  jz      short loc_180007885
0x180007818  mov     rcx, [rbx+30h]; hWnd
0x18000781c  lea     rdx, [rbp+Point]; lpPoint
0x180007820  call    cs:__imp_ClientToScreen
0x180007826  test    eax, eax
0x180007828  jz      short loc_180007885
0x18000782a  mov     edx, [rbp+var_58.left]
0x18000782d  lea     rcx, [rbp+ptnProperties.rcDestination]; lprc
0x180007831  mov     r8d, [rbp+var_58.top]
0x180007835  xorps   xmm0, xmm0
0x180007838  mov     eax, [rbp+var_58.right]
0x18000783b  sub     eax, edx
0x18000783d  sub     edx, [rbp+Point.x]; dx
0x180007840  movups  xmmword ptr [rbp+ptnProperties.rcDestination.bottom], xmm0
0x180007844  movups  xmmword ptr [rbp-48h], xmm0
0x180007848  mov     [rbp+ptnProperties.rcDestination.right], eax
0x18000784b  mov     eax, [rbp+var_58.bottom]
0x18000784e  sub     eax, r8d
0x180007851  sub     r8d, [rbp+Point.y]; dy
0x180007855  mov     [rbp+ptnProperties.rcDestination.bottom], eax
0x180007858  movups  xmmword ptr [rbp+ptnProperties.rcSource.right+1], xmm0
0x18000785c  call    cs:__imp_OffsetRect
0x180007862  mov     rcx, [rbx+90h]; hThumbnailId
0x180007869  lea     rdx, [rbp+ptnProperties]; ptnProperties
0x18000786d  or      [rbp+ptnProperties.dwFlags], 1
0x180007871  call    cs:__imp_DwmUpdateThumbnailProperties
0x180007877  test    eax, eax
0x180007879  js      short loc_180007885
0x18000787b  mov     dword ptr [rbx+98h], 0
0x180007885  xor     eax, eax
0x180007887  cmp     [rbx+98h], eax
0x18000788d  setz    al
0x180007890  mov     rcx, [rbp+var_8]
0x180007894  xor     rcx, rsp; StackCookie
0x180007897  call    __security_check_cookie
0x18000789c  mov     rbx, [rsp+80h+arg_8]
0x1800078a4  add     rsp, 80h
0x1800078ab  pop     rbp
0x1800078ac  retn
```

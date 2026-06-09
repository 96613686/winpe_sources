# CMapiPreviewer::ConvertIconToBitmap(HWND__ *,HICON__ *,HBITMAP__ * *)

- ea: `0x180022800`
- end: `0x1800229aa`
- name: `?ConvertIconToBitmap@CMapiPreviewer@@CAJPEAUHWND__@@PEAUHICON__@@PEAPEAUHBITMAP__@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(HWND hWnd, HICON hIcon, HBITMAP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800265dc`

## callees

- `0x18000557c`
- `0x180006270`
- `0x180022800`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180022853`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180022861`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180022853`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180022861`
- `USER32!ReleaseDC` at `0x18002296b`
- `USER32!ReleaseDC` at `0x18002296b`
- `USER32!DrawIconEx` at `0x18002293a`
- `USER32!DrawIconEx` at `0x18002293a`
- `USER32!GetDC` at `0x180022831`
- `USER32!GetDC` at `0x180022831`
- `USER32!FillRect` at `0x1800228f8`
- `USER32!FillRect` at `0x1800228f8`
- `GDI32!DeleteDC` at `0x180022953`
- `GDI32!DeleteDC` at `0x180022953`
- `GDI32!CreateCompatibleDC` at `0x18002287d`
- `GDI32!CreateCompatibleDC` at `0x18002287d`
- `GDI32!SelectObject` at `0x1800228c6`
- `GDI32!SelectObject` at `0x1800228c6`
- `GDI32!CreateCompatibleBitmap` at `0x1800228a3`
- `GDI32!CreateCompatibleBitmap` at `0x1800228a3`
- `GDI32!DeleteObject` at `0x18002297d`
- `GDI32!DeleteObject` at `0x18002297d`

## pseudocode

```c
__int64 __fastcall CMapiPreviewer::ConvertIconToBitmap(HWND hWnd, HICON hIcon, HBITMAP *a3)
{
  int Error; // ebx
  HDC DC; // rsi
  int cxWidth; // r14d
  int SystemMetrics; // eax
  int cyWidth; // ebp
  HDC CompatibleDC; // rdi
  HBITMAP CompatibleBitmap; // rax
  RECT rc; // [rsp+50h] [rbp-58h] BYREF

  Error = 0;
  *a3 = 0;
  DC = GetDC(hWnd);
  if ( !DC )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_26;
  }
  cxWidth = GetSystemMetrics(49);
  SystemMetrics = GetSystemMetrics(50);
  cyWidth = SystemMetrics;
  if ( cxWidth && SystemMetrics )
  {
    CompatibleDC = CreateCompatibleDC(DC);
    if ( CompatibleDC || (Error = ResultFromLastError(), Error >= 0) )
    {
      CompatibleBitmap = CreateCompatibleBitmap(DC, cxWidth, cyWidth);
      *a3 = CompatibleBitmap;
      if ( CompatibleBitmap || (Error = ResultFromLastError(), Error >= 0) )
      {
        if ( SelectObject(CompatibleDC, *a3) )
        {
          *(_QWORD *)&rc.left = 0;
          rc.right = cxWidth;
          rc.bottom = cyWidth;
          if ( FillRect(CompatibleDC, &rc, (HBRUSH)6) || (Error = ResultFromLastError(), Error >= 0) )
          {
            if ( !DrawIconEx(CompatibleDC, 0, 0, hIcon, cxWidth, cyWidth, 0, 0, 3u) )
              Error = ResultFromLastError();
          }
        }
        else
        {
          Error = -2147467259;
        }
      }
      if ( CompatibleDC )
        DeleteDC(CompatibleDC);
    }
  }
  else
  {
    Error = -2147467259;
  }
  if ( DC )
    ReleaseDC(hWnd, DC);
  if ( Error < 0 )
  {
LABEL_26:
    if ( *a3 )
      DeleteObject(*a3);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180022800  mov     [rsp+arg_18], rbx
0x180022805  push    rbp
0x180022806  push    rsi
0x180022807  push    rdi
0x180022808  push    r12
0x18002280a  push    r13
0x18002280c  push    r14
0x18002280e  push    r15
0x180022810  sub     rsp, 70h
0x180022814  mov     rax, cs:__security_cookie
0x18002281b  xor     rax, rsp
0x18002281e  mov     [rsp+0A8h+var_48], rax
0x180022823  xor     ebx, ebx
0x180022825  mov     r15, r8
0x180022828  mov     [r8], rbx
0x18002282b  mov     r13, rdx
0x18002282e  mov     r12, rcx
0x180022831  call    cs:__imp_GetDC
0x180022837  mov     rsi, rax
0x18002283a  test    rax, rax
0x18002283d  jnz     short loc_18002284E
0x18002283f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022844  mov     ebx, eax
0x180022846  test    eax, eax
0x180022848  js      loc_180022975
0x18002284e  mov     ecx, 31h ; '1'; nIndex
0x180022853  call    cs:__imp_GetSystemMetrics
0x180022859  mov     ecx, 32h ; '2'; nIndex
0x18002285e  mov     r14d, eax
0x180022861  call    cs:__imp_GetSystemMetrics
0x180022867  mov     ebp, eax
0x180022869  test    r14d, r14d
0x18002286c  jz      loc_18002295B
0x180022872  test    eax, eax
0x180022874  jz      loc_18002295B
0x18002287a  mov     rcx, rsi; hdc
0x18002287d  call    cs:__imp_CreateCompatibleDC
0x180022883  mov     rdi, rax
0x180022886  test    rax, rax
0x180022889  jnz     short loc_18002289A
0x18002288b  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022890  mov     ebx, eax
0x180022892  test    eax, eax
0x180022894  js      loc_180022960
0x18002289a  mov     r8d, ebp; cy
0x18002289d  mov     edx, r14d; cx
0x1800228a0  mov     rcx, rsi; hdc
0x1800228a3  call    cs:__imp_CreateCompatibleBitmap
0x1800228a9  mov     [r15], rax
0x1800228ac  test    rax, rax
0x1800228af  jnz     short loc_1800228C0
0x1800228b1  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800228b6  mov     ebx, eax
0x1800228b8  test    eax, eax
0x1800228ba  js      loc_18002294B
0x1800228c0  mov     rdx, [r15]; h
0x1800228c3  mov     rcx, rdi; hdc
0x1800228c6  call    cs:__imp_SelectObject
0x1800228cc  test    rax, rax
0x1800228cf  jnz     short loc_1800228D8
0x1800228d1  mov     ebx, 80004005h
0x1800228d6  jmp     short loc_18002294B
0x1800228d8  mov     r8d, 6; hbr
0x1800228de  mov     qword ptr [rsp+0A8h+rc.left], 0
0x1800228e7  lea     rdx, [rsp+0A8h+rc]; lprc
0x1800228ec  mov     [rsp+0A8h+rc.right], r14d
0x1800228f1  mov     rcx, rdi; hDC
0x1800228f4  mov     [rsp+0A8h+rc.bottom], ebp
0x1800228f8  call    cs:__imp_FillRect
0x1800228fe  test    eax, eax
0x180022900  jnz     short loc_18002290D
0x180022902  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022907  mov     ebx, eax
0x180022909  test    eax, eax
0x18002290b  js      short loc_18002294B
0x18002290d  mov     [rsp+0A8h+diFlags], 3; diFlags
0x180022915  mov     r9, r13; hIcon
0x180022918  mov     [rsp+0A8h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x180022921  xor     r8d, r8d; yTop
0x180022924  mov     [rsp+0A8h+istepIfAniCur], 0; istepIfAniCur
0x18002292c  xor     edx, edx; xLeft
0x18002292e  mov     [rsp+0A8h+cyWidth], ebp; cyWidth
0x180022932  mov     rcx, rdi; hdc
0x180022935  mov     [rsp+0A8h+cxWidth], r14d; cxWidth
0x18002293a  call    cs:__imp_DrawIconEx
0x180022940  test    eax, eax
0x180022942  jnz     short loc_18002294B
0x180022944  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022949  mov     ebx, eax
0x18002294b  test    rdi, rdi
0x18002294e  jz      short loc_180022960
0x180022950  mov     rcx, rdi; hdc
0x180022953  call    cs:__imp_DeleteDC
0x180022959  jmp     short loc_180022960
0x18002295b  mov     ebx, 80004005h
0x180022960  test    rsi, rsi
0x180022963  jz      short loc_180022971
0x180022965  mov     rdx, rsi; hDC
0x180022968  mov     rcx, r12; hWnd
0x18002296b  call    cs:__imp_ReleaseDC
0x180022971  test    ebx, ebx
0x180022973  jns     short loc_180022983
0x180022975  mov     rcx, [r15]; ho
0x180022978  test    rcx, rcx
0x18002297b  jz      short loc_180022983
0x18002297d  call    cs:__imp_DeleteObject
0x180022983  mov     eax, ebx
0x180022985  mov     rcx, [rsp+0A8h+var_48]
0x18002298a  xor     rcx, rsp; StackCookie
0x18002298d  call    __security_check_cookie
0x180022992  mov     rbx, [rsp+0A8h+arg_18]
0x18002299a  add     rsp, 70h
0x18002299e  pop     r15
0x1800229a0  pop     r14
0x1800229a2  pop     r13
0x1800229a4  pop     r12
0x1800229a6  pop     rdi
0x1800229a7  pop     rsi
0x1800229a8  pop     rbp
0x1800229a9  retn
```

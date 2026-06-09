# CreateUserFontW(ushort const *,ulong *,HDC__ *,int)

- ea: `0x1800665d0`
- end: `0x18006686c`
- name: `?CreateUserFontW@@YAPEAUHFONT__@@PEBGPEAKPEAUHDC__@@H@Z`
- size: `668`
- prototype: `HFONT __fastcall(const unsigned __int16 *, unsigned int *, HDC, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800197c8`
- `0x18005d400`

## callees

- `0x1800665d0`
- `0x180068194`
- `0x18006c3dc`
- `0x180075c90`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800666eb`
- `msvcrt!wcsstr` at `0x18006670e`
- `msvcrt!wcsstr` at `0x180066732`
- `msvcrt!wcsstr` at `0x180066751`
- `msvcrt!wcsstr` at `0x180066771`
- `msvcrt!wcsstr` at `0x180066786`
- `msvcrt!wcsstr` at `0x1800666eb`
- `msvcrt!wcsstr` at `0x18006670e`
- `msvcrt!wcsstr` at `0x180066732`
- `msvcrt!wcsstr` at `0x180066751`
- `msvcrt!wcsstr` at `0x180066771`
- `msvcrt!wcsstr` at `0x180066786`
- `msvcrt!wcschr` at `0x18006663f`
- `msvcrt!wcschr` at `0x18006668a`
- `msvcrt!wcschr` at `0x1800666c6`
- `msvcrt!wcschr` at `0x18006663f`
- `msvcrt!wcschr` at `0x18006668a`
- `msvcrt!wcschr` at `0x1800666c6`
- `msvcrt!_wcsdup` at `0x18006662e`
- `msvcrt!_wcsdup` at `0x18006662e`
- `msvcrt!_wtoi` at `0x180066679`
- `msvcrt!_wtoi` at `0x1800666b4`
- `msvcrt!_wtoi` at `0x180066679`
- `msvcrt!_wtoi` at `0x1800666b4`
- `msvcrt!free` at `0x180066833`
- `msvcrt!free` at `0x180066833`
- `KERNEL32!MulDiv` at `0x180066819`
- `KERNEL32!MulDiv` at `0x180066819`
- `GDI32!CreateFontIndirectW` at `0x18006683e`
- `GDI32!CreateFontIndirectW` at `0x18006683e`
- `GDI32!DeleteDC` at `0x180066824`
- `GDI32!DeleteDC` at `0x180066824`
- `GDI32!CreateICA` at `0x1800667f7`
- `GDI32!CreateICA` at `0x1800667f7`
- `GDI32!GetDeviceCaps` at `0x180066808`
- `GDI32!GetDeviceCaps` at `0x180066808`

## pseudocode

```c
HFONT __fastcall CreateUserFontW(const unsigned __int16 *a1, unsigned int *a2, HDC a3, int a4)
{
  wchar_t *v5; // rbp
  wchar_t *v6; // rax
  int v7; // r14d
  const wchar_t *NonSpaceW; // rax
  const wchar_t *v9; // rbx
  wchar_t *v10; // rax
  const wchar_t *v11; // rax
  const wchar_t *v12; // rbx
  wchar_t *v13; // rax
  const wchar_t *v14; // rdi
  wchar_t *v15; // rax
  LONG lfWeight; // ecx
  wchar_t *v17; // rax
  BYTE lfItalic; // cl
  wchar_t *v19; // rax
  BYTE lfUnderline; // cl
  __int64 v21; // rcx
  WCHAR *lfFaceName; // rax
  wchar_t *v23; // r8
  __int64 v24; // rdx
  WCHAR *v25; // rcx
  int v26; // r14d
  HDC ICA; // rdi
  int DeviceCaps; // eax
  int v29; // ebx
  LOGFONTW lf; // [rsp+20h] [rbp-88h] BYREF

  memset(&lf.lfWeight, 0, 76);
  lf.lfWeight = 400;
  lf.lfPitchAndFamily = 0;
  lf.lfCharSet = -1;
  *(_OWORD *)&lf.lfHeight = 0;
  v5 = _wcsdup(a1);
  v6 = wcschr(v5, 0x2Cu);
  v7 = 12;
  if ( v6 )
  {
    *v6 = 0;
    NonSpaceW = (const wchar_t *)FirstNonSpaceW(v6 + 1);
    v9 = NonSpaceW;
    if ( (unsigned __int16)(*NonSpaceW - 48) <= 0x4C09u )
      v7 = _wtoi(NonSpaceW);
    v10 = wcschr(v9, 0x2Cu);
    if ( v10 )
    {
      v11 = (const wchar_t *)FirstNonSpaceW(v10 + 1);
      v12 = v11;
      if ( (unsigned __int16)(*v11 - 48) <= 0x4C09u )
        lf.lfCharSet = _wtoi(v11);
      v13 = wcschr(v12, 0x2Cu);
      if ( v13 )
      {
        v14 = (const wchar_t *)FirstNonSpaceW(v13 + 1);
        v15 = wcsstr(v14, L"BOLD");
        lfWeight = lf.lfWeight;
        if ( v15 )
          lfWeight = 700;
        lf.lfWeight = lfWeight;
        v17 = wcsstr(v14, L"ITALIC");
        lfItalic = lf.lfItalic;
        if ( v17 )
          lfItalic = 1;
        lf.lfItalic = lfItalic;
        v19 = wcsstr(v14, L"UNDERLINE");
        lfUnderline = lf.lfUnderline;
        if ( v19 )
          lfUnderline = 1;
        lf.lfUnderline = lfUnderline;
        if ( wcsstr(v14, L"#") )
        {
          MEMORY[0] = IEColorToWin32Color(v14);
        }
        else if ( !wcsstr(v14, L"0x") )
        {
          wcsstr(v14, L"0X");
        }
      }
    }
  }
  v21 = 31;
  lfFaceName = lf.lfFaceName;
  v23 = v5;
  v24 = 32;
  do
  {
    if ( !v21 )
      break;
    if ( !*v23 )
      break;
    *lfFaceName++ = *v23++;
    --v21;
    --v24;
  }
  while ( v24 );
  v25 = lfFaceName - 1;
  if ( v24 )
    v25 = lfFaceName;
  v26 = 2 * v7;
  *v25 = 0;
  *(_WORD *)&lf.lfOutPrecision = 0;
  lf.lfQuality = 0;
  if ( a4 != -1 )
    lf.lfCharSet = a4;
  ICA = CreateICA("DISPLAY", 0, 0, 0);
  DeviceCaps = GetDeviceCaps(ICA, 90);
  v29 = MulDiv(DeviceCaps, v26, 144);
  DeleteDC(ICA);
  lf.lfHeight = -v29;
  free(v5);
  return CreateFontIndirectW(&lf);
}

```

## disassembly

```asm
0x1800665d0  mov     [rsp+arg_8], rbx
0x1800665d5  mov     [rsp+arg_10], rbp
0x1800665da  push    rsi
0x1800665db  push    rdi
0x1800665dc  push    r14
0x1800665de  sub     rsp, 90h
0x1800665e5  mov     rax, cs:__security_cookie
0x1800665ec  xor     rax, rsp
0x1800665ef  mov     [rsp+0A8h+var_28], rax
0x1800665f7  xorps   xmm0, xmm0
0x1800665fa  xor     eax, eax
0x1800665fc  movups  xmmword ptr [rsp+0A8h+lf.lfWeight], xmm0
0x180066601  mov     [rsp+0A8h+lf.lfWeight], 190h
0x180066609  mov     esi, r9d
0x18006660c  movups  xmmword ptr [rsp+0A8h+lf.lfFaceName+24h], xmm0
0x180066611  mov     [rsp+0A8h+lf.lfPitchAndFamily], al
0x180066615  movups  xmmword ptr [rsp+0A8h+lf.lfFaceName+30h], xmm0
0x18006661a  mov     [rsp+0A8h+lf.lfCharSet], 0FFh
0x18006661f  movups  xmmword ptr [rsp+0A8h+lf.lfHeight], xmm0
0x180066624  movups  xmmword ptr [rsp+0A8h+lf.lfFaceName+4], xmm0
0x180066629  movups  xmmword ptr [rsp+0A8h+lf.lfFaceName+14h], xmm0
0x18006662e  call    cs:__imp__wcsdup
0x180066634  mov     rcx, rax; Str
0x180066637  mov     edx, 2Ch ; ','; Ch
0x18006663c  mov     rbp, rax
0x18006663f  call    cs:__imp_wcschr
0x180066645  mov     r14d, 0Ch
0x18006664b  test    rax, rax
0x18006664e  jz      loc_18006678C
0x180066654  xor     ecx, ecx
0x180066656  mov     [rax], cx
0x180066659  lea     rcx, [rax+2]
0x18006665d  call    FirstNonSpaceW
0x180066662  mov     edi, 4C09h
0x180066667  mov     rbx, rax
0x18006666a  movzx   ecx, word ptr [rax]
0x18006666d  sub     cx, 30h ; '0'
0x180066671  cmp     cx, di
0x180066674  ja      short loc_180066682
0x180066676  mov     rcx, rax; String
0x180066679  call    cs:__imp__wtoi
0x18006667f  mov     r14d, eax
0x180066682  mov     edx, 2Ch ; ','; Ch
0x180066687  mov     rcx, rbx; Str
0x18006668a  call    cs:__imp_wcschr
0x180066690  test    rax, rax
0x180066693  jz      loc_18006678C
0x180066699  lea     rcx, [rax+2]
0x18006669d  call    FirstNonSpaceW
0x1800666a2  mov     rbx, rax
0x1800666a5  movzx   ecx, word ptr [rax]
0x1800666a8  sub     cx, 30h ; '0'
0x1800666ac  cmp     cx, di
0x1800666af  ja      short loc_1800666BE
0x1800666b1  mov     rcx, rax; String
0x1800666b4  call    cs:__imp__wtoi
0x1800666ba  mov     [rsp+0A8h+lf.lfCharSet], al
0x1800666be  mov     edx, 2Ch ; ','; Ch
0x1800666c3  mov     rcx, rbx; Str
0x1800666c6  call    cs:__imp_wcschr
0x1800666cc  test    rax, rax
0x1800666cf  jz      loc_18006678C
0x1800666d5  lea     rcx, [rax+2]
0x1800666d9  call    FirstNonSpaceW
0x1800666de  mov     rcx, rax; Str
0x1800666e1  lea     rdx, aBold_0; "BOLD"
0x1800666e8  mov     rdi, rax
0x1800666eb  call    cs:__imp_wcsstr
0x1800666f1  mov     ecx, [rsp+0A8h+lf.lfWeight]
0x1800666f5  mov     edx, 2BCh
0x1800666fa  test    rax, rax
0x1800666fd  cmovnz  ecx, edx
0x180066700  lea     rdx, aItalic; "ITALIC"
0x180066707  mov     [rsp+0A8h+lf.lfWeight], ecx
0x18006670b  mov     rcx, rdi; Str
0x18006670e  call    cs:__imp_wcsstr
0x180066714  movzx   ecx, [rsp+0A8h+lf.lfItalic]
0x180066719  lea     rdx, aUnderline; "UNDERLINE"
0x180066720  test    rax, rax
0x180066723  mov     ebx, 1
0x180066728  cmovnz  ecx, ebx
0x18006672b  mov     [rsp+0A8h+lf.lfItalic], cl
0x18006672f  mov     rcx, rdi; Str
0x180066732  call    cs:__imp_wcsstr
0x180066738  movzx   ecx, [rsp+0A8h+lf.lfUnderline]
0x18006673d  lea     rdx, asc_180080024; "#"
0x180066744  test    rax, rax
0x180066747  cmovnz  ecx, ebx
0x18006674a  mov     [rsp+0A8h+lf.lfUnderline], cl
0x18006674e  mov     rcx, rdi; Str
0x180066751  call    cs:__imp_wcsstr
0x180066757  mov     rcx, rdi; unsigned __int16 *
0x18006675a  test    rax, rax
0x18006675d  jz      short loc_18006676A
0x18006675f  xor     ebx, ebx
0x180066761  call    ?IEColorToWin32Color@@YAHPEBG@Z; IEColorToWin32Color(ushort const *)
0x180066766  mov     [rbx], eax
0x180066768  jmp     short loc_18006678C
0x18006676a  lea     rdx, a0x; "0x"
0x180066771  call    cs:__imp_wcsstr
0x180066777  test    rax, rax
0x18006677a  jnz     short loc_18006678C
0x18006677c  lea     rdx, a0x_0; "0X"
0x180066783  mov     rcx, rdi; Str
0x180066786  call    cs:__imp_wcsstr
0x18006678c  mov     ecx, 1Fh
0x180066791  lea     rax, [rsp+0A8h+lf.lfFaceName]
0x180066796  mov     r8, rbp
0x180066799  mov     edx, 20h ; ' '
0x18006679e  test    rcx, rcx
0x1800667a1  jz      short loc_1800667C2
0x1800667a3  movzx   r9d, word ptr [r8]
0x1800667a7  test    r9w, r9w
0x1800667ab  jz      short loc_1800667C2
0x1800667ad  mov     [rax], r9w
0x1800667b1  add     r8, 2
0x1800667b5  add     rax, 2
0x1800667b9  dec     rcx
0x1800667bc  sub     rdx, 1
0x1800667c0  jnz     short loc_18006679E
0x1800667c2  test    rdx, rdx
0x1800667c5  lea     rcx, [rax-2]
0x1800667c9  cmovnz  rcx, rax
0x1800667cd  xor     eax, eax
0x1800667cf  add     r14d, r14d
0x1800667d2  mov     [rcx], ax
0x1800667d5  mov     word ptr [rsp+0A8h+lf.lfOutPrecision], ax
0x1800667da  mov     [rsp+0A8h+lf.lfQuality], al
0x1800667de  cmp     esi, 0FFFFFFFFh
0x1800667e1  jz      short loc_1800667E8
0x1800667e3  mov     [rsp+0A8h+lf.lfCharSet], sil
0x1800667e8  xor     r9d, r9d; pdm
0x1800667eb  lea     rcx, pszDriver; "DISPLAY"
0x1800667f2  xor     r8d, r8d; pszPort
0x1800667f5  xor     edx, edx; pszDevice
0x1800667f7  call    cs:__imp_CreateICA
0x1800667fd  mov     rcx, rax; hdc
0x180066800  mov     edx, 5Ah ; 'Z'; index
0x180066805  mov     rdi, rax
0x180066808  call    cs:__imp_GetDeviceCaps
0x18006680e  mov     r8d, 90h; nDenominator
0x180066814  mov     edx, r14d; nNumerator
0x180066817  mov     ecx, eax; nNumber
0x180066819  call    cs:__imp_MulDiv
0x18006681f  mov     rcx, rdi; hdc
0x180066822  mov     ebx, eax
0x180066824  call    cs:__imp_DeleteDC
0x18006682a  neg     ebx
0x18006682c  mov     rcx, rbp; Block
0x18006682f  mov     [rsp+0A8h+lf.lfHeight], ebx
0x180066833  call    cs:__imp_free
0x180066839  lea     rcx, [rsp+0A8h+lf]; lplf
0x18006683e  call    cs:__imp_CreateFontIndirectW
0x180066844  mov     rcx, [rsp+0A8h+var_28]
0x18006684c  xor     rcx, rsp; StackCookie
0x18006684f  call    __security_check_cookie
0x180066854  lea     r11, [rsp+0A8h+var_18]
0x18006685c  mov     rbx, [r11+28h]
0x180066860  mov     rbp, [r11+30h]
0x180066864  mov     rsp, r11
0x180066867  pop     r14
0x180066869  pop     rdi
0x18006686a  pop     rsi
0x18006686b  retn
```

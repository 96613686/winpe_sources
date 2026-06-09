# HandleOpen

- ea: `0x180070738`
- end: `0x180070b4d`
- name: `HandleOpen`
- size: `1045`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180070360`

## callees

- `0x1800115f0`
- `0x180070738`
- `0x180070b54`
- `0x180070d30`
- `0x18008ac10`
- `0x18008ad00`
- `0x18008ae88`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18007091f`
- `GDI32!CreateCompatibleDC` at `0x18007091f`
- `GDI32!CreateCompatibleBitmap` at `0x180070933`
- `GDI32!CreateCompatibleBitmap` at `0x180070933`
- `GDI32!SelectObject` at `0x180070942`
- `GDI32!SelectObject` at `0x180070942`
- `GDI32!DeleteObject` at `0x180070970`
- `GDI32!DeleteObject` at `0x180070970`
- `GDI32!DeleteDC` at `0x180070967`
- `GDI32!DeleteDC` at `0x180070967`
- `GDI32!GetPixel` at `0x18007095b`
- `GDI32!GetPixel` at `0x18007095b`
- `GDI32!GetBkColor` at `0x18007098e`
- `GDI32!GetBkColor` at `0x18007098e`
- `KERNEL32!LocalFree` at `0x1800707c1`
- `KERNEL32!LocalFree` at `0x180070b17`
- `KERNEL32!LocalFree` at `0x1800707c1`
- `KERNEL32!LocalFree` at `0x180070b17`
- `KERNEL32!LocalAlloc` at `0x1800707fb`
- `KERNEL32!LocalAlloc` at `0x1800707fb`
- `KERNEL32!FindResourceW` at `0x180070829`
- `KERNEL32!FindResourceW` at `0x180070829`
- `KERNEL32!LoadResource` at `0x18007083a`
- `KERNEL32!LoadResource` at `0x18007083a`
- `KERNEL32!LockResource` at `0x18007084b`
- `KERNEL32!LockResource` at `0x18007084b`
- `USER32!GetClientRect` at `0x180070a36`
- `USER32!GetClientRect` at `0x180070a36`
- `USER32!GetWindowLongW` at `0x180070a7b`
- `USER32!GetWindowLongW` at `0x180070a8b`
- `USER32!GetWindowLongW` at `0x180070a7b`
- `USER32!GetWindowLongW` at `0x180070a8b`
- `USER32!SetWindowPos` at `0x180070acf`
- `USER32!SetWindowPos` at `0x180070acf`
- `USER32!GetDC` at `0x180070913`
- `USER32!GetDC` at `0x180070913`
- `USER32!ReleaseDC` at `0x18007099c`
- `USER32!ReleaseDC` at `0x18007099c`
- `USER32!SetRect` at `0x1800708f5`
- `USER32!SetRect` at `0x1800708f5`
- `USER32!SendMessageW` at `0x180070985`
- `USER32!SendMessageW` at `0x180070985`
- `USER32!InvalidateRect` at `0x180070afd`
- `USER32!InvalidateRect` at `0x180070afd`
- `USER32!GetWindowLongPtrW` at `0x18007079e`
- `USER32!GetWindowLongPtrW` at `0x18007079e`
- `USER32!PostMessageW` at `0x180070aef`
- `USER32!PostMessageW` at `0x180070aef`
- `USER32!GetWindowTextW` at `0x180070785`
- `USER32!GetWindowTextW` at `0x180070785`
- `USER32!OffsetRect` at `0x180070a5e`
- `USER32!OffsetRect` at `0x180070a5e`
- `USER32!AdjustWindowRectEx` at `0x180070a9e`
- `USER32!AdjustWindowRectEx` at `0x180070a9e`

## pseudocode

```c
__int64 __fastcall HandleOpen(__int64 a1, HMODULE WindowLongPtrW, WCHAR *a3, int a4)
{
  HLOCAL v7; // rax
  HLOCAL v8; // rsi
  HRSRC ResourceW; // rax
  HGLOBAL Resource; // rax
  HGLOBAL v11; // rdi
  LPVOID v12; // rax
  __int64 v13; // rdi
  __int64 v14; // r9
  __int64 v15; // rdx
  _DWORD *v16; // r9
  HDC DC; // rsi
  HDC CompatibleDC; // rdi
  HBITMAP CompatibleBitmap; // rbx
  COLORREF Pixel; // r12d
  COLORREF BkColor; // ebx
  __int64 v22; // r9
  int v23; // r10d
  int v24; // ecx
  int v25; // eax
  HWND v26; // rcx
  HWND v27; // rdi
  HWND v28; // rcx
  LONG WindowLongW; // ebx
  LONG v30; // eax
  HWND v31; // rcx
  unsigned int v33; // [rsp+40h] [rbp-C0h] BYREF
  void *v34; // [rsp+48h] [rbp-B8h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( a4 == 42 )
  {
    GetWindowTextW(*(HWND *)a1, String, 260);
    a3 = String;
  }
  if ( !WindowLongPtrW )
    WindowLongPtrW = (HMODULE)GetWindowLongPtrW(*(HWND *)a1, -6);
  HandleStop(a1);
  if ( *(_QWORD *)(a1 + 32) )
  {
    ((void (*)(void))RleFile_Close)();
    LocalFree(*(HLOCAL *)(a1 + 32));
    *(_QWORD *)(a1 + 32) = 0;
  }
  *(_DWORD *)(a1 + 104) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  if ( !a3 || (unsigned __int64)a3 >= 0x10000 && !*a3 )
    return 0;
  v7 = LocalAlloc(0x40u, 0x4B0u);
  *(_QWORD *)(a1 + 32) = v7;
  v8 = v7;
  if ( !v7 )
    return 0;
  if ( (unsigned __int64)a3 >= 0x10000 && !*a3
    || (ResourceW = FindResourceW(WindowLongPtrW, a3, L"AVI")) == 0
    || (Resource = LoadResource(WindowLongPtrW, ResourceW), (v11 = Resource) == 0)
    || (v12 = LockResource(Resource), !(unsigned int)RleFile_Init(v8, v12, v11, 0)) )
  {
    v33 = 0;
    *(_QWORD *)&Rect.left = 0;
    v34 = 0;
    if ( (unsigned __int64)a3 < 0x10000
      || (v13 = *(_QWORD *)(a1 + 32), !(unsigned int)LoadFile(a3, &v33, (void **)&Rect, &v34))
      || (v14 = v33,
          v15 = *(_QWORD *)&Rect.left,
          *(_QWORD *)(v13 + 1184) = v34,
          !(unsigned int)RleFile_Init(v13, v15, 0, v14)) )
    {
      RleFile_Close(*(_QWORD *)(a1 + 32));
      LocalFree(*(HLOCAL *)(a1 + 32));
      *(_QWORD *)(a1 + 32) = 0;
      return 0;
    }
  }
  v16 = *(_DWORD **)(a1 + 32);
  *(_DWORD *)(a1 + 96) = *v16;
  *(_DWORD *)(a1 + 100) = v16[3];
  SetRect((LPRECT)(a1 + 80), 0, 0, v16[1], v16[2]);
  if ( (*(_BYTE *)(a1 + 24) & 2) != 0 )
  {
    if ( *(_QWORD *)(a1 + 16) )
    {
      DC = GetDC(*(HWND *)a1);
      CompatibleDC = CreateCompatibleDC(DC);
      CompatibleBitmap = CreateCompatibleBitmap(DC, 1, 1);
      SelectObject(CompatibleDC, CompatibleBitmap);
      HandlePaint(a1, CompatibleDC);
      Pixel = GetPixel(CompatibleDC, 0, 0);
      DeleteDC(CompatibleDC);
      DeleteObject(CompatibleBitmap);
      SendMessageW(*(HWND *)(a1 + 16), 0x138u, (WPARAM)DC, *(_QWORD *)a1);
      BkColor = GetBkColor(DC);
      ReleaseDC(*(HWND *)a1, DC);
      v22 = *(_QWORD *)(a1 + 32);
      if ( v22 )
      {
        if ( *(_QWORD *)(v22 + 1160) )
        {
          v23 = 256;
          v24 = *(_DWORD *)(v22 + 104);
          v25 = 0;
          if ( (unsigned int)v24 > 0x100 || (v23 = *(_DWORD *)(v22 + 104), v24 > 0) )
          {
            do
            {
              if ( *(_DWORD *)(v22 + 4LL * v25 + 112) == (((unsigned __int8)Pixel << 16) | BYTE2(Pixel) | Pixel & 0xFF00) )
                *(_DWORD *)(v22 + 4LL * v25 + 112) = ((unsigned __int8)BkColor << 16)
                                                   | BYTE2(BkColor)
                                                   | BkColor & 0xFF00;
              ++v25;
            }
            while ( v25 < v23 );
          }
        }
      }
    }
  }
  if ( (*(_BYTE *)(a1 + 24) & 1) != 0 )
  {
    v26 = *(HWND *)a1;
    Rect = 0;
    GetClientRect(v26, &Rect);
    OffsetRect((LPRECT)(a1 + 80), (Rect.right - *(_DWORD *)(a1 + 88)) / 2, (Rect.bottom - *(_DWORD *)(a1 + 92)) / 2);
  }
  else
  {
    v27 = *(HWND *)a1;
    v28 = *(HWND *)a1;
    Rect = *(struct tagRECT *)(a1 + 80);
    WindowLongW = GetWindowLongW(v28, -20);
    v30 = GetWindowLongW(v27, -16);
    AdjustWindowRectEx(&Rect, v30, 0, WindowLongW);
    SetWindowPos(*(HWND *)a1, 0, 0, 0, Rect.right - Rect.left, Rect.bottom - Rect.top, 0x16u);
  }
  v31 = *(HWND *)a1;
  if ( (*(_BYTE *)(a1 + 24) & 4) != 0 )
    PostMessageW(v31, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, -65536);
  else
    InvalidateRect(v31, 0, 1);
  return 1;
}

```

## disassembly

```asm
0x180070738  mov     [rsp-8+arg_18], rbx
0x18007073d  push    rbp
0x18007073e  push    rsi
0x18007073f  push    rdi
0x180070740  push    r12
0x180070742  push    r13
0x180070744  push    r14
0x180070746  push    r15
0x180070748  lea     rbp, [rsp-180h]
0x180070750  sub     rsp, 280h
0x180070757  mov     rax, cs:__security_cookie
0x18007075e  xor     rax, rsp
0x180070761  mov     [rbp+1B0h+var_40], rax
0x180070768  mov     rbx, r8
0x18007076b  mov     rdi, rdx
0x18007076e  mov     r14, rcx
0x180070771  cmp     r9d, 2Ah ; '*'
0x180070775  jnz     short loc_180070790
0x180070777  mov     rcx, [rcx]; hWnd
0x18007077a  lea     rdx, [rsp+2B0h+String]; lpString
0x18007077f  mov     r8d, 104h; nMaxCount
0x180070785  call    cs:__imp_GetWindowTextW
0x18007078b  lea     rbx, [rsp+2B0h+String]
0x180070790  xor     r13d, r13d
0x180070793  test    rdi, rdi
0x180070796  jnz     short loc_1800707A7
0x180070798  mov     rcx, [r14]; hWnd
0x18007079b  lea     edx, [rdi-6]; nIndex
0x18007079e  call    cs:__imp_GetWindowLongPtrW
0x1800707a4  mov     rdi, rax
0x1800707a7  mov     rcx, r14
0x1800707aa  call    HandleStop
0x1800707af  mov     rcx, [r14+20h]
0x1800707b3  test    rcx, rcx
0x1800707b6  jz      short loc_1800707CB
0x1800707b8  call    RleFile_Close
0x1800707bd  mov     rcx, [r14+20h]; hMem
0x1800707c1  call    cs:__imp_LocalFree
0x1800707c7  mov     [r14+20h], r13
0x1800707cb  mov     [r14+68h], r13d
0x1800707cf  mov     [r14+60h], r13d
0x1800707d3  test    rbx, rbx
0x1800707d6  jz      loc_180070B21
0x1800707dc  mov     r15d, 10000h
0x1800707e2  cmp     rbx, r15
0x1800707e5  jb      short loc_1800707F1
0x1800707e7  cmp     [rbx], r13w
0x1800707eb  jz      loc_180070B21
0x1800707f1  mov     edx, 4B0h; uBytes
0x1800707f6  mov     ecx, 40h ; '@'; uFlags
0x1800707fb  call    cs:__imp_LocalAlloc
0x180070801  mov     [r14+20h], rax
0x180070805  mov     rsi, rax
0x180070808  test    rax, rax
0x18007080b  jz      loc_180070B21
0x180070811  cmp     rbx, r15
0x180070814  jb      short loc_18007081C
0x180070816  cmp     [rbx], r13w
0x18007081a  jz      short loc_180070866
0x18007081c  lea     r8, Type; "AVI"
0x180070823  mov     rdx, rbx; lpName
0x180070826  mov     rcx, rdi; hModule
0x180070829  call    cs:__imp_FindResourceW
0x18007082f  test    rax, rax
0x180070832  jz      short loc_180070866
0x180070834  mov     rdx, rax; hResInfo
0x180070837  mov     rcx, rdi; hModule
0x18007083a  call    cs:__imp_LoadResource
0x180070840  mov     rdi, rax
0x180070843  test    rax, rax
0x180070846  jz      short loc_180070866
0x180070848  mov     rcx, rax; hResData
0x18007084b  call    cs:__imp_LockResource
0x180070851  xor     r9d, r9d
0x180070854  mov     r8, rdi
0x180070857  mov     rdx, rax
0x18007085a  mov     rcx, rsi
0x18007085d  call    RleFile_Init
0x180070862  test    eax, eax
0x180070864  jnz     short loc_1800708CA
0x180070866  mov     [rsp+2B0h+var_270], r13d
0x18007086b  mov     qword ptr [rsp+2B0h+Rect.left], r13
0x180070870  mov     [rsp+2B0h+var_268], r13
0x180070875  cmp     rbx, r15
0x180070878  jb      loc_180070B0A
0x18007087e  mov     rdi, [r14+20h]
0x180070882  lea     r9, [rsp+2B0h+var_268]; void **
0x180070887  lea     r8, [rsp+2B0h+Rect]; void **
0x18007088c  mov     rcx, rbx; unsigned __int16 *
0x18007088f  lea     rdx, [rsp+2B0h+var_270]; unsigned int *
0x180070894  call    ?LoadFile@@YAHPEBGPEAKPEAPEAX2@Z; LoadFile(ushort const *,ulong *,void * *,void * *)
0x180070899  test    eax, eax
0x18007089b  jz      loc_180070B0A
0x1800708a1  mov     rax, [rsp+2B0h+var_268]
0x1800708a6  xor     r8d, r8d
0x1800708a9  mov     r9d, [rsp+2B0h+var_270]
0x1800708ae  mov     rcx, rdi
0x1800708b1  mov     rdx, qword ptr [rsp+2B0h+Rect.left]
0x1800708b6  mov     [rdi+4A0h], rax
0x1800708bd  call    RleFile_Init
0x1800708c2  test    eax, eax
0x1800708c4  jz      loc_180070B0A
0x1800708ca  mov     r9, [r14+20h]
0x1800708ce  lea     r15, [r14+50h]
0x1800708d2  xor     r8d, r8d; yTop
0x1800708d5  xor     edx, edx; xLeft
0x1800708d7  mov     rcx, r15; lprc
0x1800708da  mov     eax, [r9]
0x1800708dd  mov     [r14+60h], eax
0x1800708e1  mov     eax, [r9+0Ch]
0x1800708e5  mov     [r14+64h], eax
0x1800708e9  mov     eax, [r9+8]
0x1800708ed  mov     r9d, [r9+4]; xRight
0x1800708f1  mov     [rsp+2B0h+yBottom], eax; yBottom
0x1800708f5  call    cs:__imp_SetRect
0x1800708fb  test    byte ptr [r14+18h], 2
0x180070900  jz      loc_180070A1F
0x180070906  cmp     [r14+10h], r13
0x18007090a  jz      loc_180070A1F
0x180070910  mov     rcx, [r14]; hWnd
0x180070913  call    cs:__imp_GetDC
0x180070919  mov     rcx, rax; hdc
0x18007091c  mov     rsi, rax
0x18007091f  call    cs:__imp_CreateCompatibleDC
0x180070925  mov     edx, 1; cx
0x18007092a  mov     rcx, rsi; hdc
0x18007092d  mov     r8d, edx; cy
0x180070930  mov     rdi, rax
0x180070933  call    cs:__imp_CreateCompatibleBitmap
0x180070939  mov     rdx, rax; h
0x18007093c  mov     rcx, rdi; hdc
0x18007093f  mov     rbx, rax
0x180070942  call    cs:__imp_SelectObject
0x180070948  mov     rdx, rdi
0x18007094b  mov     rcx, r14
0x18007094e  call    HandlePaint
0x180070953  xor     r8d, r8d; y
0x180070956  xor     edx, edx; x
0x180070958  mov     rcx, rdi; hdc
0x18007095b  call    cs:__imp_GetPixel
0x180070961  mov     rcx, rdi; hdc
0x180070964  mov     r12d, eax
0x180070967  call    cs:__imp_DeleteDC
0x18007096d  mov     rcx, rbx; ho
0x180070970  call    cs:__imp_DeleteObject
0x180070976  mov     r9, [r14]; lParam
0x180070979  mov     r8, rsi; wParam
0x18007097c  mov     rcx, [r14+10h]; hWnd
0x180070980  mov     edx, 138h; Msg
0x180070985  call    cs:__imp_SendMessageW
0x18007098b  mov     rcx, rsi; hdc
0x18007098e  call    cs:__imp_GetBkColor
0x180070994  mov     rcx, [r14]; hWnd
0x180070997  mov     rdx, rsi; hDC
0x18007099a  mov     ebx, eax
0x18007099c  call    cs:__imp_ReleaseDC
0x1800709a2  mov     r9, [r14+20h]
0x1800709a6  test    r9, r9
0x1800709a9  jz      short loc_180070A1F
0x1800709ab  cmp     [r9+488h], r13
0x1800709b2  jz      short loc_180070A1F
0x1800709b4  mov     eax, r12d
0x1800709b7  movzx   r8d, r12w
0x1800709bb  shr     eax, 10h
0x1800709be  and     r8d, 0FFFFFF00h
0x1800709c5  movzx   ecx, al
0x1800709c8  mov     r10d, 100h
0x1800709ce  or      r8d, ecx
0x1800709d1  movzx   eax, r12b
0x1800709d5  shl     eax, 10h
0x1800709d8  or      r8d, eax
0x1800709db  movzx   edx, bx
0x1800709de  and     edx, 0FFFFFF00h
0x1800709e4  mov     eax, ebx
0x1800709e6  shr     eax, 10h
0x1800709e9  movzx   ecx, al
0x1800709ec  or      edx, ecx
0x1800709ee  movzx   eax, bl
0x1800709f1  mov     ecx, [r9+68h]
0x1800709f5  shl     eax, 10h
0x1800709f8  or      edx, eax
0x1800709fa  mov     eax, r13d
0x1800709fd  cmp     ecx, r10d
0x180070a00  ja      short loc_180070A09
0x180070a02  mov     r10d, ecx
0x180070a05  test    ecx, ecx
0x180070a07  jle     short loc_180070A1F
0x180070a09  movsxd  rcx, eax
0x180070a0c  cmp     [r9+rcx*4+70h], r8d
0x180070a11  jnz     short loc_180070A18
0x180070a13  mov     [r9+rcx*4+70h], edx
0x180070a18  inc     eax
0x180070a1a  cmp     eax, r10d
0x180070a1d  jl      short loc_180070A09
0x180070a1f  test    byte ptr [r14+18h], 1
0x180070a24  jz      short loc_180070A66
0x180070a26  mov     rcx, [r14]; hWnd
0x180070a29  lea     rdx, [rsp+2B0h+Rect]; lpRect
0x180070a2e  xorps   xmm0, xmm0
0x180070a31  movups  xmmword ptr [rsp+2B0h+Rect.left], xmm0
0x180070a36  call    cs:__imp_GetClientRect
0x180070a3c  mov     eax, [rsp+2B0h+Rect.bottom]
0x180070a40  mov     rcx, r15; lprc
0x180070a43  sub     eax, [r14+5Ch]
0x180070a47  cdq
0x180070a48  sub     eax, edx
0x180070a4a  sar     eax, 1
0x180070a4c  mov     r8d, eax; dy
0x180070a4f  mov     eax, [rsp+2B0h+Rect.right]
0x180070a53  sub     eax, [r14+58h]
0x180070a57  cdq
0x180070a58  sub     eax, edx
0x180070a5a  sar     eax, 1
0x180070a5c  mov     edx, eax; dx
0x180070a5e  call    cs:__imp_OffsetRect
0x180070a64  jmp     short loc_180070AD5
0x180070a66  movups  xmm0, xmmword ptr [r15]
0x180070a6a  mov     rdi, [r14]
0x180070a6d  mov     edx, 0FFFFFFECh; nIndex
0x180070a72  mov     rcx, rdi; hWnd
0x180070a75  movdqu  xmmword ptr [rsp+2B0h+Rect.left], xmm0
0x180070a7b  call    cs:__imp_GetWindowLongW
0x180070a81  mov     edx, 0FFFFFFF0h; nIndex
0x180070a86  mov     rcx, rdi; hWnd
0x180070a89  mov     ebx, eax
0x180070a8b  call    cs:__imp_GetWindowLongW
0x180070a91  mov     r9d, ebx; dwExStyle
0x180070a94  lea     rcx, [rsp+2B0h+Rect]; lpRect
0x180070a99  mov     edx, eax; dwStyle
0x180070a9b  xor     r8d, r8d; bMenu
0x180070a9e  call    cs:__imp_AdjustWindowRectEx
0x180070aa4  mov     ecx, [rsp+2B0h+Rect.bottom]
0x180070aa8  xor     r9d, r9d; Y
0x180070aab  sub     ecx, [rsp+2B0h+Rect.top]
0x180070aaf  xor     r8d, r8d; X
0x180070ab2  mov     eax, [rsp+2B0h+Rect.right]
0x180070ab6  xor     edx, edx; hWndInsertAfter
0x180070ab8  sub     eax, [rsp+2B0h+Rect.left]
0x180070abc  mov     [rsp+2B0h+uFlags], 16h; uFlags
0x180070ac4  mov     [rsp+2B0h+cy], ecx; cy
0x180070ac8  mov     rcx, [r14]; hWnd
0x180070acb  mov     [rsp+2B0h+yBottom], eax; cx
0x180070acf  call    cs:__imp_SetWindowPos
0x180070ad5  test    byte ptr [r14+18h], 4
0x180070ada  mov     rcx, [r14]; hWnd
0x180070add  jz      short loc_180070AF7
0x180070adf  mov     r9, 0FFFFFFFFFFFF0000h; lParam
0x180070ae6  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180070aea  mov     edx, 465h; Msg
0x180070aef  call    cs:__imp_PostMessageW
0x180070af5  jmp     short loc_180070B03
0x180070af7  xor     edx, edx; lpRect
0x180070af9  lea     r8d, [rdx+1]; bErase
0x180070afd  call    cs:__imp_InvalidateRect
0x180070b03  mov     eax, 1
0x180070b08  jmp     short loc_180070B23
0x180070b0a  mov     rcx, [r14+20h]
0x180070b0e  call    RleFile_Close
0x180070b13  mov     rcx, [r14+20h]; hMem
0x180070b17  call    cs:__imp_LocalFree
0x180070b1d  mov     [r14+20h], r13
0x180070b21  xor     eax, eax
0x180070b23  mov     rcx, [rbp+1B0h+var_40]
0x180070b2a  xor     rcx, rsp; StackCookie
0x180070b2d  call    __security_check_cookie
0x180070b32  mov     rbx, [rsp+2B0h+arg_18]
0x180070b3a  add     rsp, 280h
0x180070b41  pop     r15
0x180070b43  pop     r14
0x180070b45  pop     r13
0x180070b47  pop     r12
0x180070b49  pop     rdi
0x180070b4a  pop     rsi
0x180070b4b  pop     rbp
0x180070b4c  retn
```

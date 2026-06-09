# Animate::NextFrame(void)

- ea: `0x18000b410`
- end: `0x18000b9df`
- name: `?NextFrame@Animate@@QEAAXXZ`
- size: `1487`
- prototype: `void __fastcall(Animate *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b3f0`

## callees

- `0x180005a4c`
- `0x18000b410`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18000b434`
- `KERNEL32!GetTickCount` at `0x18000b434`
- `USER32!GetSysColor` at `0x18000b452`
- `USER32!GetSysColor` at `0x18000b464`
- `USER32!GetSysColor` at `0x18000b452`
- `USER32!GetSysColor` at `0x18000b464`
- `USER32!ReleaseDC` at `0x18000b96e`
- `USER32!ReleaseDC` at `0x18000b96e`
- `USER32!GetDC` at `0x18000b902`
- `USER32!GetDC` at `0x18000b902`
- `USER32!ShowWindow` at `0x18000b8f5`
- `USER32!ShowWindow` at `0x18000b8f5`
- `USER32!LoadBitmapA` at `0x18000b4a4`
- `USER32!LoadBitmapA` at `0x18000b4c6`
- `USER32!LoadBitmapA` at `0x18000b4a4`
- `USER32!LoadBitmapA` at `0x18000b4c6`
- `GDI32!DeleteObject` at `0x18000b8c4`
- `GDI32!DeleteObject` at `0x18000b8cd`
- `GDI32!DeleteObject` at `0x18000b8d6`
- `GDI32!DeleteObject` at `0x18000b9ad`
- `GDI32!DeleteObject` at `0x18000b9bb`
- `GDI32!DeleteObject` at `0x18000b9c9`
- `GDI32!DeleteObject` at `0x18000b8c4`
- `GDI32!DeleteObject` at `0x18000b8cd`
- `GDI32!DeleteObject` at `0x18000b8d6`
- `GDI32!DeleteObject` at `0x18000b9ad`
- `GDI32!DeleteObject` at `0x18000b9bb`
- `GDI32!DeleteObject` at `0x18000b9c9`
- `GDI32!DeleteDC` at `0x18000b8df`
- `GDI32!DeleteDC` at `0x18000b9d7`
- `GDI32!DeleteDC` at `0x18000b8df`
- `GDI32!DeleteDC` at `0x18000b9d7`
- `GDI32!CreateCompatibleDC` at `0x18000b4d6`
- `GDI32!CreateCompatibleDC` at `0x18000b4e1`
- `GDI32!CreateCompatibleDC` at `0x18000b4d6`
- `GDI32!CreateCompatibleDC` at `0x18000b4e1`
- `GDI32!SelectObject` at `0x18000b4fe`
- `GDI32!SelectObject` at `0x18000b575`
- `GDI32!SelectObject` at `0x18000b587`
- `GDI32!SelectObject` at `0x18000b5dd`
- `GDI32!SelectObject` at `0x18000b702`
- `GDI32!SelectObject` at `0x18000b75f`
- `GDI32!SelectObject` at `0x18000b803`
- `GDI32!SelectObject` at `0x18000b846`
- `GDI32!SelectObject` at `0x18000b8a2`
- `GDI32!SelectObject` at `0x18000b8bb`
- `GDI32!SelectObject` at `0x18000b913`
- `GDI32!SelectObject` at `0x18000b961`
- `GDI32!SelectObject` at `0x18000b9a4`
- `GDI32!SelectObject` at `0x18000b4fe`
- `GDI32!SelectObject` at `0x18000b575`
- `GDI32!SelectObject` at `0x18000b587`
- `GDI32!SelectObject` at `0x18000b5dd`
- `GDI32!SelectObject` at `0x18000b702`
- `GDI32!SelectObject` at `0x18000b75f`
- `GDI32!SelectObject` at `0x18000b803`
- `GDI32!SelectObject` at `0x18000b846`
- `GDI32!SelectObject` at `0x18000b8a2`
- `GDI32!SelectObject` at `0x18000b8bb`
- `GDI32!SelectObject` at `0x18000b913`
- `GDI32!SelectObject` at `0x18000b961`
- `GDI32!SelectObject` at `0x18000b9a4`
- `GDI32!CreateCompatibleBitmap` at `0x18000b516`
- `GDI32!CreateCompatibleBitmap` at `0x18000b564`
- `GDI32!CreateCompatibleBitmap` at `0x18000b516`
- `GDI32!CreateCompatibleBitmap` at `0x18000b564`
- `GDI32!PatBlt` at `0x18000b5d0`
- `GDI32!PatBlt` at `0x18000b7e6`
- `GDI32!PatBlt` at `0x18000b5d0`
- `GDI32!PatBlt` at `0x18000b7e6`
- `GDI32!BitBlt` at `0x18000b619`
- `GDI32!BitBlt` at `0x18000b751`
- `GDI32!BitBlt` at `0x18000b796`
- `GDI32!BitBlt` at `0x18000b838`
- `GDI32!BitBlt` at `0x18000b881`
- `GDI32!BitBlt` at `0x18000b954`
- `GDI32!BitBlt` at `0x18000b619`
- `GDI32!BitBlt` at `0x18000b751`
- `GDI32!BitBlt` at `0x18000b796`
- `GDI32!BitBlt` at `0x18000b838`
- `GDI32!BitBlt` at `0x18000b881`
- `GDI32!BitBlt` at `0x18000b954`
- `GDI32!SetPixel` at `0x18000b66e`
- `GDI32!SetPixel` at `0x18000b6e3`
- `GDI32!SetPixel` at `0x18000b66e`
- `GDI32!SetPixel` at `0x18000b6e3`

## pseudocode

```c
void __fastcall Animate::NextFrame(Animate *this)
{
  Animate *v1; // rsi
  DWORD TickCount; // eax
  DWORD v3; // ebx
  HINSTANCE ResourceInstance; // rax
  HBITMAP v5; // rbp
  HINSTANCE v6; // rax
  HDC CompatibleDC; // rbx
  HDC v8; // rax
  void *v9; // rdi
  HBITMAP CompatibleBitmap; // rax
  HDC v11; // rcx
  HBITMAP v12; // rax
  void *v13; // rdx
  COLORREF v14; // edi
  int v15; // r12d
  int v16; // r14d
  int i; // r13d
  COLORREF v18; // r9d
  signed int v19; // r14d
  COLORREF v20; // r9d
  int v21; // r13d
  int v22; // edx
  int x1; // eax
  int j; // r14d
  HWND v25; // rcx
  HDC DC; // rdi
  HGDIOBJ v27; // rbx
  HGDIOBJ ho; // [rsp+50h] [rbp-78h]
  HBITMAP v29; // [rsp+58h] [rbp-70h]
  Animate *v30; // [rsp+60h] [rbp-68h]
  HBITMAP BitmapA; // [rsp+68h] [rbp-60h]
  HGDIOBJ v32; // [rsp+70h] [rbp-58h]
  COLORREF color; // [rsp+D0h] [rbp+8h]
  signed int colora; // [rsp+D0h] [rbp+8h]
  DWORD SysColor; // [rsp+D8h] [rbp+10h]
  int y; // [rsp+E8h] [rbp+20h]

  v1 = qword_18008BED0;
  v30 = qword_18008BED0;
  TickCount = GetTickCount();
  v3 = TickCount;
  if ( TickCount - *((_DWORD *)v1 + 13) >= 0x64 )
  {
    *((_DWORD *)v1 + 13) = TickCount;
    color = GetSysColor(17);
    SysColor = GetSysColor(26);
    if ( *((_DWORD *)v1 + 15) )
    {
LABEL_34:
      DC = GetDC(*((HWND *)v1 + 1));
      v27 = SelectObject(*((HDC *)v1 + 3), *((HGDIOBJ *)v1 + 4));
      BitBlt(
        DC,
        *((_DWORD *)v1 + 11),
        *((_DWORD *)v1 + 12),
        40,
        40,
        *((HDC *)v1 + 3),
        40 * *((_DWORD *)v1 + 10),
        0,
        0xCC0020u);
      SelectObject(*((HDC *)v1 + 3), v27);
      ReleaseDC(*((HWND *)v1 + 1), DC);
      if ( (int)++*((_DWORD *)v1 + 10) > 45 )
        *((_DWORD *)v1 + 10) = 0;
      return;
    }
    if ( v3 - *((_DWORD *)v1 + 14) < 0x3E8 )
      return;
    ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    BitmapA = LoadBitmapA(ResourceInstance, (LPCSTR)0x1FE);
    v5 = BitmapA;
    v6 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    v29 = LoadBitmapA(v6, (LPCSTR)0x1FF);
    CompatibleDC = CreateCompatibleDC(0);
    v8 = CreateCompatibleDC(0);
    *((_QWORD *)v1 + 3) = v8;
    *((_QWORD *)v1 + 2) = 0;
    if ( v8 )
    {
      ho = SelectObject(v8, BitmapA);
      v9 = ho;
      CompatibleBitmap = CreateCompatibleBitmap(*((HDC *)v1 + 3), 40, 40);
      *((_QWORD *)v1 + 2) = CompatibleBitmap;
    }
    else
    {
      v9 = 0;
      ho = 0;
      CompatibleBitmap = 0;
    }
    if ( BitmapA )
    {
      if ( v29 )
      {
        if ( CompatibleBitmap )
        {
          v11 = (HDC)*((_QWORD *)v1 + 3);
          if ( v11 )
          {
            if ( CompatibleDC )
            {
              v12 = CreateCompatibleBitmap(v11, 1800, 40);
              v13 = (void *)*((_QWORD *)v1 + 2);
              *((_QWORD *)v1 + 4) = v12;
              v32 = SelectObject(CompatibleDC, v13);
              SelectObject(*((HDC *)v1 + 3), BitmapA);
              v14 = color;
              v15 = 0;
              *((_DWORD *)v1 + 10) = 0;
              do
              {
                colora = 0;
                do
                {
                  PatBlt(CompatibleDC, 0, 0, 40, 40, 0xFF0062u);
                  SelectObject(*((HDC *)v1 + 3), v5);
                  BitBlt(CompatibleDC, 0, 4, 36, 36, *((HDC *)v1 + 3), 144, 0, 0xCC0020u);
                  v16 = 0;
                  if ( v15 )
                  {
                    do
                    {
                      for ( i = 0; i < 10; ++i )
                      {
                        v18 = SysColor;
                        if ( (i & 1) != 0 )
                          v18 = v14;
                        SetPixel(CompatibleDC, i + 18, 2 * v16 + 21 + (5 - i) * (5 - i) / 10, v18);
                      }
                      ++v16;
                    }
                    while ( v16 < v15 );
                  }
                  v19 = 0;
                  do
                  {
                    v20 = SysColor;
                    v21 = v19 + 18;
                    v22 = (5 - v19) * (5 - v19) / 10;
                    if ( (v19 & 1) != 0 )
                      v20 = v14;
                    y = v22 + 2 * v15 + 2;
                    SetPixel(CompatibleDC, v21, v22 + 2 * v15 + 21, v20);
                    ++v19;
                  }
                  while ( v19 <= colora );
                  v1 = v30;
                  SelectObject(*((HDC *)v30 + 3), v29);
                  if ( (*((_DWORD *)v30 + 10) & 1) != 0 )
                    x1 = 15;
                  else
                    x1 = 15 * (*((_DWORD *)v30 + 10) & 2);
                  BitBlt(CompatibleDC, v21, y, 15, 20, *((HDC *)v30 + 3), x1, 0, 0x8800C6u);
                  SelectObject(*((HDC *)v30 + 3), *((HGDIOBJ *)v30 + 4));
                  BitBlt(*((HDC *)v30 + 3), 40 * *((_DWORD *)v30 + 10), 0, 40, 40, CompatibleDC, 0, 0, 0xCC0020u);
                  ++*((_DWORD *)v30 + 10);
                  v5 = BitmapA;
                  ++colora;
                }
                while ( colora < 10 );
                ++v15;
              }
              while ( v15 < 4 );
              PatBlt(CompatibleDC, 0, 0, 40, 40, 0xFF0062u);
              for ( j = 0; j != 180; j += 36 )
              {
                SelectObject(*((HDC *)v30 + 3), BitmapA);
                BitBlt(CompatibleDC, 0, 4, 36, 36, *((HDC *)v30 + 3), j, 0, 0xCC0020u);
                SelectObject(*((HDC *)v30 + 3), *((HGDIOBJ *)v30 + 4));
                BitBlt(*((HDC *)v30 + 3), 40 * *((_DWORD *)v30 + 10), 0, 40, 40, CompatibleDC, 0, 0, 0xCC0020u);
                ++*((_DWORD *)v30 + 10);
              }
              SelectObject(CompatibleDC, v32);
              *((_DWORD *)v30 + 10) = 0;
              if ( ho )
              {
                SelectObject(*((HDC *)v30 + 3), ho);
                DeleteObject(ho);
              }
              DeleteObject(BitmapA);
              DeleteObject(v29);
              DeleteDC(CompatibleDC);
              v25 = (HWND)*((_QWORD *)v30 + 1);
              *((_DWORD *)v30 + 15) = 1;
              ShowWindow(v25, 1);
              goto LABEL_34;
            }
          }
        }
      }
    }
    if ( v9 )
    {
      SelectObject(*((HDC *)v1 + 3), v9);
      DeleteObject(v9);
    }
    if ( BitmapA )
      DeleteObject(BitmapA);
    if ( v29 )
      DeleteObject(v29);
    if ( CompatibleDC )
      DeleteDC(CompatibleDC);
  }
}

```

## disassembly

```asm
0x18000b410  mov     qword ptr [rsp+color], rcx
0x18000b415  push    rbx
0x18000b416  push    rbp
0x18000b417  push    rsi
0x18000b418  push    rdi
0x18000b419  push    r12
0x18000b41b  push    r13
0x18000b41d  push    r14
0x18000b41f  push    r15
0x18000b421  sub     rsp, 88h
0x18000b428  mov     rsi, cs:qword_18008BED0
0x18000b42f  mov     [rsp+0C8h+var_68], rsi
0x18000b434  call    cs:__imp_GetTickCount
0x18000b43a  mov     ecx, eax
0x18000b43c  mov     ebx, eax
0x18000b43e  sub     ecx, [rsi+34h]
0x18000b441  cmp     ecx, 64h ; 'd'
0x18000b444  jb      loc_18000B984
0x18000b44a  mov     ecx, 11h; nIndex
0x18000b44f  mov     [rsi+34h], eax
0x18000b452  call    cs:__imp_GetSysColor
0x18000b458  mov     ecx, 1Ah; nIndex
0x18000b45d  mov     [rsp+0C8h+color], eax
0x18000b464  call    cs:__imp_GetSysColor
0x18000b46a  cmp     dword ptr [rsi+3Ch], 0
0x18000b46e  mov     r14d, 28h ; '('
0x18000b474  mov     [rsp+0C8h+arg_8], eax
0x18000b47b  jnz     loc_18000B8FE
0x18000b481  sub     ebx, [rsi+38h]
0x18000b484  cmp     ebx, 3E8h
0x18000b48a  jb      loc_18000B984
0x18000b490  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x18000b497  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18000b49c  mov     rcx, rax; hInstance
0x18000b49f  mov     edx, 1FEh; lpBitmapName
0x18000b4a4  call    cs:__imp_LoadBitmapA
0x18000b4aa  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x18000b4b1  mov     [rsp+0C8h+var_60], rax
0x18000b4b6  mov     rbp, rax
0x18000b4b9  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18000b4be  mov     rcx, rax; hInstance
0x18000b4c1  mov     edx, 1FFh; lpBitmapName
0x18000b4c6  call    cs:__imp_LoadBitmapA
0x18000b4cc  xor     ecx, ecx; hdc
0x18000b4ce  mov     [rsp+0C8h+var_70], rax
0x18000b4d3  mov     r15, rax
0x18000b4d6  call    cs:__imp_CreateCompatibleDC
0x18000b4dc  xor     ecx, ecx; hdc
0x18000b4de  mov     rbx, rax
0x18000b4e1  call    cs:__imp_CreateCompatibleDC
0x18000b4e7  mov     [rsi+18h], rax
0x18000b4eb  mov     qword ptr [rsi+10h], 0
0x18000b4f3  test    rax, rax
0x18000b4f6  jz      short loc_18000B522
0x18000b4f8  mov     rdx, rbp; h
0x18000b4fb  mov     rcx, rax; hdc
0x18000b4fe  call    cs:__imp_SelectObject
0x18000b504  mov     rcx, [rsi+18h]; hdc
0x18000b508  mov     r8d, r14d; cy
0x18000b50b  mov     edx, r14d; cx
0x18000b50e  mov     [rsp+0C8h+ho], rax
0x18000b513  mov     rdi, rax
0x18000b516  call    cs:__imp_CreateCompatibleBitmap
0x18000b51c  mov     [rsi+10h], rax
0x18000b520  jmp     short loc_18000B52B
0x18000b522  xor     edi, edi
0x18000b524  mov     [rsp+0C8h+ho], rdi
0x18000b529  xor     eax, eax
0x18000b52b  test    rbp, rbp
0x18000b52e  jz      loc_18000B998
0x18000b534  test    r15, r15
0x18000b537  jz      loc_18000B998
0x18000b53d  test    rax, rax
0x18000b540  jz      loc_18000B998
0x18000b546  mov     rcx, [rsi+18h]; hdc
0x18000b54a  test    rcx, rcx
0x18000b54d  jz      loc_18000B998
0x18000b553  test    rbx, rbx
0x18000b556  jz      loc_18000B998
0x18000b55c  mov     r8d, r14d; cy
0x18000b55f  mov     edx, 708h; cx
0x18000b564  call    cs:__imp_CreateCompatibleBitmap
0x18000b56a  mov     rdx, [rsi+10h]; h
0x18000b56e  mov     rcx, rbx; hdc
0x18000b571  mov     [rsi+20h], rax
0x18000b575  call    cs:__imp_SelectObject
0x18000b57b  mov     rcx, [rsi+18h]; hdc
0x18000b57f  mov     rdx, rbp; h
0x18000b582  mov     [rsp+0C8h+var_58], rax
0x18000b587  call    cs:__imp_SelectObject
0x18000b58d  mov     edi, [rsp+0C8h+color]
0x18000b594  xor     r12d, r12d
0x18000b597  mov     dword ptr [rsi+28h], 0
0x18000b59e  lea     eax, ds:15h[r12*2]
0x18000b5a6  mov     [rsp+0C8h+color], 0
0x18000b5b1  mov     [rsp+0C8h+arg_10], eax
0x18000b5b8  mov     [rsp+0C8h+rop], 0FF0062h; rop
0x18000b5c0  mov     r9d, r14d; w
0x18000b5c3  xor     r8d, r8d; y
0x18000b5c6  mov     [rsp+0C8h+h], r14d; h
0x18000b5cb  xor     edx, edx; x
0x18000b5cd  mov     rcx, rbx; hdc
0x18000b5d0  call    cs:__imp_PatBlt
0x18000b5d6  mov     rcx, [rsi+18h]; hdc
0x18000b5da  mov     rdx, rbp; h
0x18000b5dd  call    cs:__imp_SelectObject
0x18000b5e3  mov     rax, [rsi+18h]
0x18000b5e7  xor     edx, edx; x
0x18000b5e9  mov     [rsp+0C8h+var_88], 0CC0020h; rop
0x18000b5f1  mov     rcx, rbx; hdc
0x18000b5f4  mov     [rsp+0C8h+y1], 0; y1
0x18000b5fc  mov     [rsp+0C8h+x1], 90h; x1
0x18000b604  mov     qword ptr [rsp+0C8h+rop], rax; hdcSrc
0x18000b609  lea     r9d, [rdx+24h]; cx
0x18000b60d  lea     r8d, [rdx+4]; y
0x18000b611  mov     [rsp+0C8h+h], 24h ; '$'; cy
0x18000b619  call    cs:__imp_BitBlt
0x18000b61f  xor     r14d, r14d
0x18000b622  test    r12d, r12d
0x18000b625  jz      short loc_18000B685
0x18000b627  mov     r15d, [rsp+0C8h+arg_8]
0x18000b62f  xor     r13d, r13d
0x18000b632  lea     ebp, ds:15h[r14*2]
0x18000b63a  mov     ecx, 5
0x18000b63f  mov     eax, 66666667h
0x18000b644  sub     ecx, r13d
0x18000b647  mov     r9d, r15d
0x18000b64a  imul    ecx, ecx
0x18000b64d  imul    ecx
0x18000b64f  mov     rcx, rbx; hdc
0x18000b652  sar     edx, 2
0x18000b655  mov     r8d, edx
0x18000b658  shr     r8d, 1Fh
0x18000b65c  add     r8d, edx
0x18000b65f  lea     edx, [r13+12h]; x
0x18000b663  test    r13b, 1
0x18000b667  cmovnz  r9d, edi; color
0x18000b66b  add     r8d, ebp; y
0x18000b66e  call    cs:__imp_SetPixel
0x18000b674  inc     r13d
0x18000b677  cmp     r13d, 0Ah
0x18000b67b  jl      short loc_18000B63A
0x18000b67d  inc     r14d
0x18000b680  cmp     r14d, r12d
0x18000b683  jl      short loc_18000B62F
0x18000b685  mov     ebp, [rsp+0C8h+color]
0x18000b68c  lea     r15d, ds:2[r12*2]
0x18000b694  mov     esi, [rsp+0C8h+arg_10]
0x18000b69b  xor     r14d, r14d
0x18000b69e  mov     r9d, [rsp+0C8h+arg_8]
0x18000b6a6  lea     r13d, [r14+12h]
0x18000b6aa  mov     ecx, 5
0x18000b6af  mov     eax, 66666667h
0x18000b6b4  sub     ecx, r14d
0x18000b6b7  imul    ecx, ecx
0x18000b6ba  imul    ecx
0x18000b6bc  mov     rcx, rbx; hdc
0x18000b6bf  sar     edx, 2
0x18000b6c2  mov     eax, edx
0x18000b6c4  shr     eax, 1Fh
0x18000b6c7  add     edx, eax
0x18000b6c9  test    r14b, 1
0x18000b6cd  cmovnz  r9d, edi; color
0x18000b6d1  lea     eax, [rdx+r15]
0x18000b6d5  lea     r8d, [rdx+rsi]; y
0x18000b6d9  mov     [rsp+0C8h+y], eax
0x18000b6e0  mov     edx, r13d; x
0x18000b6e3  call    cs:__imp_SetPixel
0x18000b6e9  inc     r14d
0x18000b6ec  cmp     r14d, ebp
0x18000b6ef  jle     short loc_18000B69E
0x18000b6f1  mov     rsi, [rsp+0C8h+var_68]
0x18000b6f6  mov     r15, [rsp+0C8h+var_70]
0x18000b6fb  mov     rdx, r15; h
0x18000b6fe  mov     rcx, [rsi+18h]; hdc
0x18000b702  call    cs:__imp_SelectObject
0x18000b708  mov     eax, [rsi+28h]
0x18000b70b  test    al, 1
0x18000b70d  jz      short loc_18000B716
0x18000b70f  mov     eax, 0Fh
0x18000b714  jmp     short loc_18000B71C
0x18000b716  and     eax, 2
0x18000b719  imul    eax, 0Fh
0x18000b71c  mov     r8d, [rsp+0C8h+y]; y
0x18000b724  xor     ebp, ebp
0x18000b726  mov     [rsp+0C8h+var_88], 8800C6h; rop
0x18000b72e  mov     edx, r13d; x
0x18000b731  mov     [rsp+0C8h+y1], ebp; y1
0x18000b735  mov     rcx, rbx; hdc
0x18000b738  mov     [rsp+0C8h+x1], eax; x1
0x18000b73c  mov     rax, [rsi+18h]
0x18000b740  lea     r9d, [rbp+0Fh]; cx
0x18000b744  mov     qword ptr [rsp+0C8h+rop], rax; hdcSrc
0x18000b749  mov     [rsp+0C8h+h], 14h; cy
0x18000b751  call    cs:__imp_BitBlt
0x18000b757  mov     rdx, [rsi+20h]; h
0x18000b75b  mov     rcx, [rsi+18h]; hdc
0x18000b75f  call    cs:__imp_SelectObject
0x18000b765  mov     eax, [rsi+28h]
0x18000b768  lea     r14d, [rbp+28h]
0x18000b76c  mov     rcx, [rsi+18h]; hdc
0x18000b770  mov     r9d, r14d; cx
0x18000b773  mov     [rsp+0C8h+var_88], 0CC0020h; rop
0x18000b77b  xor     r8d, r8d; y
0x18000b77e  mov     [rsp+0C8h+y1], ebp; y1
0x18000b782  lea     edx, [rax+rax*4]
0x18000b785  mov     [rsp+0C8h+x1], ebp; x1
0x18000b789  shl     edx, 3; x
0x18000b78c  mov     qword ptr [rsp+0C8h+rop], rbx; hdcSrc
0x18000b791  mov     [rsp+0C8h+h], r14d; cy
0x18000b796  call    cs:__imp_BitBlt
0x18000b79c  mov     r13d, [rsp+0C8h+color]
0x18000b7a4  inc     dword ptr [rsi+28h]
0x18000b7a7  inc     r13d
0x18000b7aa  mov     rbp, [rsp+0C8h+var_60]
0x18000b7af  mov     [rsp+0C8h+color], r13d
0x18000b7b7  cmp     r13d, 0Ah
0x18000b7bb  jl      loc_18000B5B8
0x18000b7c1  inc     r12d
0x18000b7c4  cmp     r12d, 4
0x18000b7c8  jl      loc_18000B59E
0x18000b7ce  mov     [rsp+0C8h+rop], 0FF0062h; rop
0x18000b7d6  mov     r9d, r14d; w
0x18000b7d9  xor     r8d, r8d; y
0x18000b7dc  mov     [rsp+0C8h+h], r14d; h
0x18000b7e1  xor     edx, edx; x
0x18000b7e3  mov     rcx, rbx; hdc
0x18000b7e6  call    cs:__imp_PatBlt
0x18000b7ec  mov     rdi, [rsp+0C8h+ho]
0x18000b7f1  xor     r14d, r14d
0x18000b7f4  lea     r12d, [r14+28h]
0x18000b7f8  lea     r13d, [r14+24h]
0x18000b7fc  mov     rcx, [rsi+18h]; hdc
0x18000b800  mov     rdx, rbp; h
0x18000b803  call    cs:__imp_SelectObject
0x18000b809  mov     rax, [rsi+18h]
0x18000b80d  xor     edx, edx; x
0x18000b80f  mov     [rsp+0C8h+var_88], 0CC0020h; rop
0x18000b817  mov     r9d, r13d; cx
0x18000b81a  mov     [rsp+0C8h+y1], 0; y1
0x18000b822  mov     rcx, rbx; hdc
0x18000b825  mov     [rsp+0C8h+x1], r14d; x1
0x18000b82a  mov     qword ptr [rsp+0C8h+rop], rax; hdcSrc
0x18000b82f  lea     r8d, [rdx+4]; y
0x18000b833  mov     [rsp+0C8h+h], r13d; cy
0x18000b838  call    cs:__imp_BitBlt
0x18000b83e  mov     rdx, [rsi+20h]; h
0x18000b842  mov     rcx, [rsi+18h]; hdc
0x18000b846  call    cs:__imp_SelectObject
0x18000b84c  mov     eax, [rsi+28h]
0x18000b84f  mov     r9d, r12d; cx
0x18000b852  mov     rcx, [rsi+18h]; hdc
0x18000b856  xor     r8d, r8d; y
0x18000b859  mov     [rsp+0C8h+var_88], 0CC0020h; rop
0x18000b861  mov     [rsp+0C8h+y1], 0; y1
0x18000b869  lea     edx, [rax+rax*4]
0x18000b86c  mov     [rsp+0C8h+x1], 0; x1
0x18000b874  shl     edx, 3; x
0x18000b877  mov     qword ptr [rsp+0C8h+rop], rbx; hdcSrc
0x18000b87c  mov     [rsp+0C8h+h], r12d; cy
0x18000b881  call    cs:__imp_BitBlt
0x18000b887  inc     dword ptr [rsi+28h]
0x18000b88a  add     r14d, r13d
0x18000b88d  cmp     r14d, 0B4h
0x18000b894  jnz     loc_18000B7FC
0x18000b89a  mov     rdx, [rsp+0C8h+var_58]; h
0x18000b89f  mov     rcx, rbx; hdc
0x18000b8a2  call    cs:__imp_SelectObject
0x18000b8a8  mov     dword ptr [rsi+28h], 0
0x18000b8af  test    rdi, rdi
0x18000b8b2  jz      short loc_18000B8CA
0x18000b8b4  mov     rcx, [rsi+18h]; hdc
0x18000b8b8  mov     rdx, rdi; h
0x18000b8bb  call    cs:__imp_SelectObject
0x18000b8c1  mov     rcx, rdi; ho
0x18000b8c4  call    cs:__imp_DeleteObject
0x18000b8ca  mov     rcx, rbp; ho
0x18000b8cd  call    cs:__imp_DeleteObject
0x18000b8d3  mov     rcx, r15; ho
0x18000b8d6  call    cs:__imp_DeleteObject
0x18000b8dc  mov     rcx, rbx; hdc
0x18000b8df  call    cs:__imp_DeleteDC
0x18000b8e5  mov     rcx, [rsi+8]; hWnd
0x18000b8e9  mov     edx, 1; nCmdShow
0x18000b8ee  mov     dword ptr [rsi+3Ch], 1
0x18000b8f5  call    cs:__imp_ShowWindow
0x18000b8fb  mov     r14d, r12d
0x18000b8fe  mov     rcx, [rsi+8]; hWnd
0x18000b902  call    cs:__imp_GetDC
0x18000b908  mov     rdx, [rsi+20h]; h
0x18000b90c  mov     rdi, rax
0x18000b90f  mov     rcx, [rsi+18h]; hdc
0x18000b913  call    cs:__imp_SelectObject
0x18000b919  mov     ecx, [rsi+28h]
0x18000b91c  mov     r9d, r14d; cx
0x18000b91f  mov     r8d, [rsi+30h]; y
0x18000b923  mov     rbx, rax
0x18000b926  mov     [rsp+0C8h+var_88], 0CC0020h; rop
0x18000b92e  mov     [rsp+0C8h+y1], 0; y1
0x18000b936  lea     edx, [rcx+rcx*4]
  ... truncated ...
```

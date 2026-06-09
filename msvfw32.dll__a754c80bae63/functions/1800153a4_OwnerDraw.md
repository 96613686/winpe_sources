# OwnerDraw

- ea: `0x1800153a4`
- end: `0x1800158ff`
- name: `OwnerDraw`
- size: `1371`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010cc0`

## callees

- `0x1800014b0`
- `0x180003f98`
- `0x18000fcc8`
- `0x1800153a4`
- `0x180015908`

## import_xrefs

- `GDI32!GetClipBox` at `0x180015555`
- `GDI32!GetClipBox` at `0x180015555`
- `GDI32!SelectObject` at `0x1800157aa`
- `GDI32!SelectObject` at `0x1800157aa`
- `GDI32!ExtTextOutW` at `0x18001584c`
- `GDI32!ExtTextOutW` at `0x18001584c`
- `GDI32!SetBkColor` at `0x180015631`
- `GDI32!SetBkColor` at `0x1800156e9`
- `GDI32!SetBkColor` at `0x180015732`
- `GDI32!SetBkColor` at `0x18001579a`
- `GDI32!SetBkColor` at `0x1800158aa`
- `GDI32!SetBkColor` at `0x180015631`
- `GDI32!SetBkColor` at `0x1800156e9`
- `GDI32!SetBkColor` at `0x180015732`
- `GDI32!SetBkColor` at `0x18001579a`
- `GDI32!SetBkColor` at `0x1800158aa`
- `GDI32!ExcludeClipRect` at `0x180015866`
- `GDI32!ExcludeClipRect` at `0x180015894`
- `GDI32!ExcludeClipRect` at `0x180015866`
- `GDI32!ExcludeClipRect` at `0x180015894`
- `GDI32!CreateFontW` at `0x180015447`
- `GDI32!CreateFontW` at `0x180015447`
- `GDI32!GetTextExtentPointW` at `0x1800157f9`
- `GDI32!GetTextExtentPointW` at `0x1800157f9`
- `USER32!SendMessageW` at `0x180015548`
- `USER32!SendMessageW` at `0x180015548`
- `USER32!KillTimer` at `0x180015508`
- `USER32!KillTimer` at `0x180015508`
- `USER32!SetTimer` at `0x1800154b9`
- `USER32!SetTimer` at `0x1800154b9`
- `USER32!GetSysColor` at `0x180015626`
- `USER32!GetSysColor` at `0x1800156de`
- `USER32!GetSysColor` at `0x180015727`
- `USER32!GetSysColor` at `0x18001578f`
- `USER32!GetSysColor` at `0x18001589f`
- `USER32!GetSysColor` at `0x180015626`
- `USER32!GetSysColor` at `0x1800156de`
- `USER32!GetSysColor` at `0x180015727`
- `USER32!GetSysColor` at `0x18001578f`
- `USER32!GetSysColor` at `0x18001589f`
- `USER32!InflateRect` at `0x1800156c7`
- `USER32!InflateRect` at `0x180015786`
- `USER32!InflateRect` at `0x1800156c7`
- `USER32!InflateRect` at `0x180015786`

## pseudocode

```c
__int64 __fastcall OwnerDraw(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  int v6; // edx
  int v7; // r15d
  int v8; // ecx
  HWND v9; // rbx
  HDC v10; // r13
  bool v11; // cl
  bool v12; // zf
  int v13; // eax
  __int64 v14; // rax
  unsigned int v15; // edx
  int v16; // r8d
  int v17; // r9d
  struct tagRECT v18; // xmm0
  int v19; // eax
  struct tagRECT v20; // xmm1
  __int64 v21; // r12
  int v22; // edi
  unsigned __int64 v23; // xmm1_8
  LONG v24; // ebx
  LONG v25; // r12d
  DWORD SysColor; // eax
  int v27; // edi
  int v28; // ebx
  DWORD v29; // eax
  DWORD v30; // eax
  __int64 v31; // rbx
  DWORD v32; // eax
  __int64 v33; // r8
  DWORD v34; // eax
  LONG right; // [rsp+70h] [rbp-59h]
  int bottom; // [rsp+78h] [rbp-51h]
  int left; // [rsp+80h] [rbp-49h]
  int v39; // [rsp+90h] [rbp-39h]
  int v40; // [rsp+94h] [rbp-35h]
  int v41; // [rsp+98h] [rbp-31h]
  int v42; // [rsp+9Ch] [rbp-2Dh]
  tagSIZE sz; // [rsp+A0h] [rbp-29h] BYREF
  int top[4]; // [rsp+B0h] [rbp-19h]
  struct tagRECT rect; // [rsp+C0h] [rbp-9h] BYREF
  wchar_t pszDest[12]; // [rsp+D0h] [rbp+7h] BYREF

  rect = 0;
  sz = 0;
  v6 = a2 - 43;
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      v7 = 2;
      if ( !*(_QWORD *)(a1 + 184) )
        *(_QWORD *)(a1 + 184) = CreateFontW(8, 0, 0, 0, 400, 0, 0, 0, 0, 0, 0, 2u, 2u, szSmallFonts);
      v8 = *(_DWORD *)(a4 + 8);
      if ( (unsigned int)(v8 - 12201) <= 1 || (unsigned int)(v8 - 13201) <= 1 )
        v7 = 6;
      *(_DWORD *)(a4 + 16) = v7;
      *(_DWORD *)(a4 + 12) = 10;
    }
  }
  else
  {
    v9 = *(HWND *)a1;
    v10 = *(HDC *)(a4 + 32);
    v11 = (*(_BYTE *)(a4 + 12) & 2) != 0;
    v12 = (*(_BYTE *)(a4 + 16) & 1) == 0;
    rect = *(struct tagRECT *)(a4 + 40);
    if ( v11 && v12 )
      SetTimer(v9, 0x2Bu, 0x1F4u, 0);
    if ( (*(_BYTE *)(a4 + 16) & 9) != 0 )
    {
      if ( (*(_BYTE *)(a4 + 16) & 8) != 0 )
      {
        v13 = *(_DWORD *)(a4 + 8);
        *(_DWORD *)(a1 + 912) = v13;
        if ( (unsigned int)(v13 - 13000) > 0xC8 )
          v14 = *(_QWORD *)(a1 + 168);
        else
          v14 = *(_QWORD *)(a1 + 176);
        *(_QWORD *)(a1 + 920) = v14;
      }
      if ( (*(_BYTE *)(a4 + 16) & 1) != 0 )
        KillTimer(*(HWND *)a1, 0x2Bu);
      v15 = *(_DWORD *)(a4 + 8);
      if ( v15 - 12201 > 1 && v15 != 13201 && v15 != 13202 )
      {
        SendMessageW(v9, 0x111u, v15, 42);
        GetClipBox(v10, &rect);
        v16 = *(_DWORD *)(a4 + 48);
        v17 = *(_DWORD *)(a4 + 40);
        v18 = *(struct tagRECT *)(a4 + 40);
        v40 = rect.top + 1;
        v19 = (v16 - v17 - 14) / 2;
        v42 = v17;
        rect.top += 7;
        v39 = rect.bottom - 2;
        v41 = v16;
        rect.bottom -= 8;
        rect.left = v19 + v17;
        rect.right = v16 - v19;
        v20 = rect;
        v21 = HIDWORD(*(_QWORD *)&rect.left);
        *(struct tagRECT *)top = rect;
        rect = v18;
        v22 = v18.top + 2;
        if ( v18.top >= (int)v21 )
          LODWORD(v21) = rect.top;
        else
          v22 = v21 + 2;
        v23 = _mm_srli_si128((__m128i)v20, 8).m128i_u64[0];
        if ( (int)v21 > HIDWORD(v23) - 2 )
        {
          LODWORD(v21) = HIDWORD(v23) - 2;
          v22 = HIDWORD(v23);
        }
        left = rect.left + 2;
        v25 = v21 - 5;
        rect.left += 2;
        v24 = rect.left;
        rect.right -= 2;
        right = rect.right;
        bottom = v22 + 5;
        rect.bottom = v22 + 5;
        rect.top = v25;
        SysColor = GetSysColor(6);
        SetBkColor(v10, SysColor);
        PatRect((_DWORD)v10, rect.left + 1, rect.top, right - v24 - 2, 1);
        PatRect((_DWORD)v10, rect.left + 1, rect.bottom - 1, right - v24 - 2, 1);
        PatRect((_DWORD)v10, rect.left, rect.top + 1, 1, v22 + 5 - v25 - 2);
        PatRect((_DWORD)v10, rect.right - 1, rect.top + 1, 1, v22 + 5 - v25 - 2);
        InflateRect(&rect, -1, -1);
        v27 = rect.right - rect.left;
        v28 = rect.bottom - rect.top;
        v29 = GetSysColor(20);
        SetBkColor(v10, v29);
        PatRect((_DWORD)v10, rect.left, rect.top, 1, v28);
        PatRect((_DWORD)v10, rect.left, rect.top, v27, 1);
        v30 = GetSysColor(16);
        SetBkColor(v10, v30);
        PatRect((_DWORD)v10, rect.right - 1, rect.top + 1, 1, v28 - 1);
        PatRect((_DWORD)v10, rect.left + 1, rect.bottom - 1, v27 - 1, 1);
        v31 = -1;
        InflateRect(&rect, -1, -1);
        v32 = GetSysColor(15);
        SetBkColor(v10, v32);
        SelectObject(v10, *(HGDIOBJ *)(a1 + 184));
        StringCchPrintfW(pszDest, 0xAu, L"%d", *(_DWORD *)(a4 + 8) % 0x3E8u);
        v33 = -1;
        do
          ++v33;
        while ( pszDest[v33] );
        GetTextExtentPointW(v10, pszDest, v33, &sz);
        do
          ++v31;
        while ( pszDest[v31] );
        ExtTextOutW(
          v10,
          (rect.left + rect.right - sz.cx) / 2,
          (rect.top + rect.bottom - sz.cy) / 2,
          2u,
          &rect,
          pszDest,
          v31,
          0);
        ExcludeClipRect(v10, left, v25, right, bottom);
        DrawChannel(v10);
        ExcludeClipRect(v10, top[0], top[1], top[2], top[3]);
        v34 = GetSysColor(4);
        SetBkColor(v10, v34);
        PatRect((_DWORD)v10, v42, v40, v41 - v42, v39 - v40);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800153a4  mov     [rsp-8+arg_8], rbx
0x1800153a9  push    rbp
0x1800153aa  push    rsi
0x1800153ab  push    rdi
0x1800153ac  push    r12
0x1800153ae  push    r13
0x1800153b0  push    r14
0x1800153b2  push    r15
0x1800153b4  lea     rbp, [rsp-27h]
0x1800153b9  sub     rsp, 0F0h
0x1800153c0  mov     rax, cs:__security_cookie
0x1800153c7  xor     rax, rsp
0x1800153ca  mov     [rbp+57h+var_38], rax
0x1800153ce  mov     r14, rcx
0x1800153d1  xorps   xmm0, xmm0
0x1800153d4  xor     ecx, ecx
0x1800153d6  mov     rsi, r9
0x1800153d9  movups  xmmword ptr [rbp+57h+rect.left], xmm0
0x1800153dd  mov     qword ptr [rbp+57h+sz.cx], rcx
0x1800153e1  lea     r12d, [rcx+2Bh]
0x1800153e5  lea     edi, [rcx+1]
0x1800153e8  sub     edx, r12d
0x1800153eb  jz      loc_180015481
0x1800153f1  cmp     edx, edi
0x1800153f3  jnz     loc_1800158D5
0x1800153f9  lea     r15d, [rcx+2]
0x1800153fd  cmp     [r14+0B8h], rcx
0x180015404  jnz     short loc_180015454
0x180015406  lea     rax, szSmallFonts; "small fonts"
0x18001540d  xor     r9d, r9d; cOrientation
0x180015410  mov     [rsp+120h+pszFaceName], rax; pszFaceName
0x180015415  xor     r8d, r8d; cEscapement
0x180015418  mov     [rsp+120h+iPitchAndFamily], r15d; iPitchAndFamily
0x18001541d  xor     edx, edx; cWidth
0x18001541f  mov     [rsp+120h+iQuality], r15d; iQuality
0x180015424  mov     [rsp+120h+iClipPrecision], ecx; iClipPrecision
0x180015428  mov     [rsp+120h+iOutPrecision], ecx; iOutPrecision
0x18001542c  mov     [rsp+120h+iCharSet], ecx; iCharSet
0x180015430  mov     [rsp+120h+bStrikeOut], ecx; bStrikeOut
0x180015434  mov     [rsp+120h+bUnderline], ecx; bUnderline
0x180015438  mov     [rsp+120h+bItalic], ecx; bItalic
0x18001543c  lea     ecx, [rdi+7]; cHeight
0x18001543f  mov     [rsp+120h+cWeight], 190h; cWeight
0x180015447  call    cs:__imp_CreateFontW
0x18001544d  mov     [r14+0B8h], rax
0x180015454  mov     ecx, [rsi+8]
0x180015457  lea     eax, [rcx-2FA9h]
0x18001545d  cmp     eax, edi
0x18001545f  jbe     short loc_18001546B
0x180015461  lea     eax, [rcx-3391h]
0x180015467  cmp     eax, edi
0x180015469  ja      short loc_180015471
0x18001546b  mov     r15d, 6
0x180015471  mov     [rsi+10h], r15d
0x180015475  mov     dword ptr [rsi+0Ch], 0Ah
0x18001547c  jmp     loc_1800158D5
0x180015481  movups  xmm0, xmmword ptr [r9+28h]
0x180015486  mov     rbx, [r14]
0x180015489  mov     r15d, 2
0x18001548f  test    [r9+0Ch], r15b
0x180015493  mov     r13, [r9+20h]
0x180015497  setnz   cl
0x18001549a  test    [r9+10h], dil
0x18001549e  movdqu  xmmword ptr [rbp+57h+rect.left], xmm0
0x1800154a3  setz    al
0x1800154a6  test    al, cl
0x1800154a8  jz      short loc_1800154BF
0x1800154aa  xor     r9d, r9d; lpTimerFunc
0x1800154ad  mov     r8d, 1F4h; uElapse
0x1800154b3  mov     rdx, r12; nIDEvent
0x1800154b6  mov     rcx, rbx; hWnd
0x1800154b9  call    cs:__imp_SetTimer
0x1800154bf  test    byte ptr [rsi+10h], 9
0x1800154c3  jz      loc_1800158D5
0x1800154c9  test    byte ptr [rsi+10h], 8
0x1800154cd  jz      short loc_1800154FC
0x1800154cf  mov     eax, [rsi+8]
0x1800154d2  mov     [r14+390h], eax
0x1800154d9  add     eax, 0FFFFCD38h
0x1800154de  cmp     eax, 0C8h
0x1800154e3  ja      short loc_1800154EE
0x1800154e5  mov     rax, [r14+0B0h]
0x1800154ec  jmp     short loc_1800154F5
0x1800154ee  mov     rax, [r14+0A8h]
0x1800154f5  mov     [r14+398h], rax
0x1800154fc  test    [rsi+10h], dil
0x180015500  jz      short loc_18001550E
0x180015502  mov     rcx, [r14]; hWnd
0x180015505  mov     rdx, r12; uIDEvent
0x180015508  call    cs:__imp_KillTimer
0x18001550e  mov     edx, [rsi+8]
0x180015511  lea     eax, [rdx-2FA9h]
0x180015517  cmp     eax, edi
0x180015519  jbe     loc_1800158D5
0x18001551f  cmp     edx, 3391h
0x180015525  jz      loc_1800158D5
0x18001552b  cmp     edx, 3392h
0x180015531  jz      loc_1800158D5
0x180015537  mov     r8d, edx; wParam
0x18001553a  mov     r9d, 2Ah ; '*'; lParam
0x180015540  mov     edx, 111h; Msg
0x180015545  mov     rcx, rbx; hWnd
0x180015548  call    cs:__imp_SendMessageW
0x18001554e  lea     rdx, [rbp+57h+rect]; lprect
0x180015552  mov     rcx, r13; hdc
0x180015555  call    cs:__imp_GetClipBox
0x18001555b  mov     r8d, [rsi+30h]
0x18001555f  mov     eax, r8d
0x180015562  mov     r9d, [rsi+28h]
0x180015566  sub     eax, r9d
0x180015569  mov     ecx, [rbp+57h+rect.top]
0x18001556c  sub     eax, 0Eh
0x18001556f  mov     r10d, [rbp+57h+rect.bottom]
0x180015573  inc     ecx
0x180015575  movups  xmm0, xmmword ptr [rsi+28h]
0x180015579  mov     [rbp+57h+var_8C], ecx
0x18001557c  cdq
0x18001557d  idiv    r15d
0x180015580  add     ecx, 6
0x180015583  mov     [rbp+57h+var_84], r9d
0x180015587  mov     [rbp+57h+rect.top], ecx
0x18001558a  add     r10d, 0FFFFFFFEh
0x18001558e  mov     [rbp+57h+var_90], r10d
0x180015592  mov     [rbp+57h+var_88], r8d
0x180015596  lea     ecx, [r10-6]
0x18001559a  mov     [rbp+57h+rect.bottom], ecx
0x18001559d  lea     ecx, [rax+r9]
0x1800155a1  mov     [rbp+57h+rect.left], ecx
0x1800155a4  mov     ecx, r8d
0x1800155a7  sub     ecx, eax
0x1800155a9  movq    rax, xmm0
0x1800155ae  mov     [rbp+57h+rect.right], ecx
0x1800155b1  movaps  xmm1, xmmword ptr [rbp+57h+rect.left]
0x1800155b5  shr     rax, 20h
0x1800155b9  movq    r12, xmm1
0x1800155be  shr     r12, 20h
0x1800155c2  movaps  xmmword ptr [rbp+57h+top], xmm1
0x1800155c6  movaps  xmmword ptr [rbp+57h+rect.left], xmm0
0x1800155ca  lea     edi, [rax+2]
0x1800155cd  cmp     eax, r12d
0x1800155d0  jge     short loc_1800155D9
0x1800155d2  lea     edi, [r12+2]
0x1800155d7  jmp     short loc_1800155DD
0x1800155d9  mov     r12d, [rbp+57h+rect.top]
0x1800155dd  psrldq  xmm1, 8
0x1800155e2  movq    rax, xmm1
0x1800155e7  shr     rax, 20h
0x1800155eb  lea     ecx, [rax-2]
0x1800155ee  cmp     r12d, ecx
0x1800155f1  jle     short loc_1800155F8
0x1800155f3  mov     r12d, ecx
0x1800155f6  mov     edi, eax
0x1800155f8  mov     ebx, [rbp+57h+rect.left]
0x1800155fb  add     edi, 5
0x1800155fe  mov     eax, [rbp+57h+rect.right]
0x180015601  add     ebx, r15d
0x180015604  sub     eax, r15d
0x180015607  mov     [rbp+57h+left], ebx
0x18001560a  sub     r12d, 5
0x18001560e  mov     [rbp+57h+rect.left], ebx
0x180015611  mov     ecx, 6; nIndex
0x180015616  mov     [rbp+57h+right], eax
0x180015619  mov     [rbp+57h+rect.right], eax
0x18001561c  mov     [rbp+57h+bottom], edi
0x18001561f  mov     [rbp+57h+rect.bottom], edi
0x180015622  mov     [rbp+57h+rect.top], r12d
0x180015626  call    cs:__imp_GetSysColor
0x18001562c  mov     edx, eax; color
0x18001562e  mov     rcx, r13; hdc
0x180015631  call    cs:__imp_SetBkColor
0x180015637  mov     eax, [rbp+57h+right]
0x18001563a  mov     rcx, r13
0x18001563d  mov     edx, [rbp+57h+rect.left]
0x180015640  sub     eax, ebx
0x180015642  mov     r8d, [rbp+57h+rect.top]
0x180015646  inc     edx
0x180015648  mov     [rsp+120h+cWeight], 1
0x180015650  lea     ebx, [rax-2]
0x180015653  mov     r9d, ebx
0x180015656  call    PatRect
0x18001565b  mov     r8d, [rbp+57h+rect.bottom]
0x18001565f  mov     r9d, ebx
0x180015662  mov     edx, [rbp+57h+rect.left]
0x180015665  dec     r8d
0x180015668  inc     edx
0x18001566a  mov     [rsp+120h+cWeight], 1
0x180015672  mov     rcx, r13
0x180015675  call    PatRect
0x18001567a  mov     r8d, [rbp+57h+rect.top]
0x18001567e  mov     ebx, edi
0x180015680  mov     edx, [rbp+57h+rect.left]
0x180015683  sub     ebx, r12d
0x180015686  add     ebx, 0FFFFFFFEh
0x180015689  mov     r9d, 1
0x18001568f  inc     r8d
0x180015692  mov     [rsp+120h+cWeight], ebx
0x180015696  mov     rcx, r13
0x180015699  call    PatRect
0x18001569e  mov     r8d, [rbp+57h+rect.top]
0x1800156a2  mov     r9d, 1
0x1800156a8  mov     edx, [rbp+57h+rect.right]
0x1800156ab  inc     r8d
0x1800156ae  dec     edx
0x1800156b0  mov     [rsp+120h+cWeight], ebx
0x1800156b4  mov     rcx, r13
0x1800156b7  call    PatRect
0x1800156bc  or      rdx, 0FFFFFFFFFFFFFFFFh; dx
0x1800156c0  lea     rcx, [rbp+57h+rect]; lprc
0x1800156c4  mov     r8d, edx; dy
0x1800156c7  call    cs:__imp_InflateRect
0x1800156cd  mov     edi, [rbp+57h+rect.right]
0x1800156d0  mov     ecx, 14h; nIndex
0x1800156d5  mov     ebx, [rbp+57h+rect.bottom]
0x1800156d8  sub     edi, [rbp+57h+rect.left]
0x1800156db  sub     ebx, [rbp+57h+rect.top]
0x1800156de  call    cs:__imp_GetSysColor
0x1800156e4  mov     edx, eax; color
0x1800156e6  mov     rcx, r13; hdc
0x1800156e9  call    cs:__imp_SetBkColor
0x1800156ef  mov     r8d, [rbp+57h+rect.top]
0x1800156f3  mov     r9d, 1
0x1800156f9  mov     edx, [rbp+57h+rect.left]
0x1800156fc  mov     rcx, r13
0x1800156ff  mov     [rsp+120h+cWeight], ebx
0x180015703  call    PatRect
0x180015708  mov     r8d, [rbp+57h+rect.top]
0x18001570c  mov     r9d, edi
0x18001570f  mov     edx, [rbp+57h+rect.left]
0x180015712  mov     rcx, r13
0x180015715  mov     [rsp+120h+cWeight], 1
0x18001571d  call    PatRect
0x180015722  mov     ecx, 10h; nIndex
0x180015727  call    cs:__imp_GetSysColor
0x18001572d  mov     edx, eax; color
0x18001572f  mov     rcx, r13; hdc
0x180015732  call    cs:__imp_SetBkColor
0x180015738  mov     r8d, [rbp+57h+rect.top]
0x18001573c  lea     eax, [rbx-1]
0x18001573f  mov     edx, [rbp+57h+rect.right]
0x180015742  inc     r8d
0x180015745  dec     edx
0x180015747  mov     [rsp+120h+cWeight], eax
0x18001574b  mov     r9d, 1
0x180015751  mov     rcx, r13
0x180015754  call    PatRect
0x180015759  mov     r8d, [rbp+57h+rect.bottom]
0x18001575d  lea     r9d, [rdi-1]
0x180015761  mov     edx, [rbp+57h+rect.left]
0x180015764  dec     r8d
0x180015767  inc     edx
0x180015769  mov     [rsp+120h+cWeight], 1
0x180015771  mov     rcx, r13
0x180015774  call    PatRect
0x180015779  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001577d  lea     rcx, [rbp+57h+rect]; lprc
0x180015781  mov     r8d, ebx; dy
0x180015784  mov     edx, ebx; dx
0x180015786  call    cs:__imp_InflateRect
0x18001578c  lea     ecx, [rbx+10h]; nIndex
0x18001578f  call    cs:__imp_GetSysColor
0x180015795  mov     edx, eax; color
0x180015797  mov     rcx, r13; hdc
0x18001579a  call    cs:__imp_SetBkColor
0x1800157a0  mov     rdx, [r14+0B8h]; h
0x1800157a7  mov     rcx, r13; hdc
0x1800157aa  call    cs:__imp_SelectObject
0x1800157b0  mov     r9d, [rsi+8]
0x1800157b4  lea     r8, aD; "%d"
0x1800157bb  mov     eax, 10624DD3h
0x1800157c0  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800157c4  mul     r9d
0x1800157c7  shr     edx, 6
0x1800157ca  imul    eax, edx, 3E8h
0x1800157d0  lea     edx, [rbx+0Bh]; cchDest
0x1800157d3  sub     r9d, eax
0x1800157d6  call    StringCchPrintfW
0x1800157db  lea     rax, [rbp+57h+pszDest]
0x1800157df  mov     r8, rbx
0x1800157e2  xor     edi, edi
0x1800157e4  inc     r8; c
0x1800157e7  cmp     [rax+r8*2], di
0x1800157ec  jnz     short loc_1800157E4
0x1800157ee  lea     r9, [rbp+57h+sz]; lpsz
0x1800157f2  mov     rcx, r13; hdc
0x1800157f5  lea     rdx, [rbp+57h+pszDest]; lpString
0x1800157f9  call    cs:__imp_GetTextExtentPointW
0x1800157ff  lea     rax, [rbp+57h+pszDest]
0x180015803  inc     rbx
0x180015806  cmp     [rax+rbx*2], di
0x18001580a  jnz     short loc_180015803
0x18001580c  mov     eax, [rbp+57h+rect.bottom]
0x18001580f  mov     r9d, r15d; options
0x180015812  sub     eax, [rbp+57h+sz.cy]
0x180015815  mov     rcx, r13; hdc
0x180015818  add     eax, [rbp+57h+rect.top]
0x18001581b  cdq
0x18001581c  mov     qword ptr [rsp+120h+bStrikeOut], rdi; lpDx
0x180015821  idiv    r15d
0x180015824  mov     [rsp+120h+bUnderline], ebx; c
0x180015828  mov     r8d, eax; y
  ... truncated ...
```

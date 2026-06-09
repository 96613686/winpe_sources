# TV_CreateIndentBmps

- ea: `0x18007b364`
- end: `0x18007b888`
- name: `TV_CreateIndentBmps`
- size: `1316`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006a710`
- `0x18006a9c4`
- `0x18006b33c`
- `0x18006b754`
- `0x18006bbb0`
- `0x18007e9d4`

## callees

- `0x1800115f0`
- `0x18007b364`
- `0x18007b930`
- `0x18007c50c`
- `0x18007cbc0`
- `0x1800852a0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18007b3e8`
- `GDI32!CreateCompatibleDC` at `0x18007b3e8`
- `GDI32!SelectObject` at `0x18007b432`
- `GDI32!SelectObject` at `0x18007b443`
- `GDI32!SelectObject` at `0x18007b495`
- `GDI32!SelectObject` at `0x18007b83d`
- `GDI32!SelectObject` at `0x18007b432`
- `GDI32!SelectObject` at `0x18007b443`
- `GDI32!SelectObject` at `0x18007b495`
- `GDI32!SelectObject` at `0x18007b83d`
- `GDI32!DeleteObject` at `0x18007b43b`
- `GDI32!DeleteObject` at `0x18007b852`
- `GDI32!DeleteObject` at `0x18007b864`
- `GDI32!DeleteObject` at `0x18007b43b`
- `GDI32!DeleteObject` at `0x18007b852`
- `GDI32!DeleteObject` at `0x18007b864`
- `GDI32!CreateSolidBrush` at `0x18007b45e`
- `GDI32!CreateSolidBrush` at `0x18007b47b`
- `GDI32!CreateSolidBrush` at `0x18007b45e`
- `GDI32!CreateSolidBrush` at `0x18007b47b`
- `USER32!InvalidateRect` at `0x18007b39e`
- `USER32!InvalidateRect` at `0x18007b39e`
- `USER32!FillRect` at `0x18007b4cd`
- `USER32!FillRect` at `0x18007b4cd`

## pseudocode

```c
int __fastcall TV_CreateIndentBmps(__int64 a1)
{
  bool v1; // zf
  int result; // eax
  int v4; // ebx
  HDC CompatibleDC; // rbp
  void *v6; // rdi
  void *ColorBitmap; // rax
  COLORREF v8; // ecx
  HBRUSH SolidBrush; // r13
  COLORREF v10; // ecx
  HBRUSH v11; // rax
  HGDIOBJ v12; // rax
  HBRUSH v13; // r8
  LONG v14; // ecx
  int v15; // r14d
  int v16; // eax
  int v17; // r15d
  signed int v18; // eax
  signed int v19; // r12d
  unsigned int v20; // ebx
  int v21; // edi
  int v22; // edi
  int v23; // eax
  int v24; // r14d
  int v25; // ebx
  int v26; // ebx
  unsigned int v27; // [rsp+40h] [rbp-78h]
  int v28; // [rsp+44h] [rbp-74h]
  HBRUSH ho; // [rsp+48h] [rbp-70h]
  HGDIOBJ h; // [rsp+50h] [rbp-68h]
  RECT rc; // [rsp+58h] [rbp-60h] BYREF

  v1 = (*(_BYTE *)(a1 + 56) & 0x10) == 0;
  rc = 0;
  if ( !v1 )
    InvalidateRect(*(HWND *)a1, 0, 1);
  result = *(_DWORD *)(a1 + 16) & 1;
  if ( (*(_BYTE *)(a1 + 16) & 2) != 0 )
  {
    v4 = 4 * result + 3;
    if ( (*(_BYTE *)(a1 + 16) & 4) != 0 )
    {
      if ( result )
        v4 = 4 * result + 6;
      else
        v4 = 4;
    }
  }
  else
  {
    if ( !result )
      return result;
    v4 = 2;
  }
  CompatibleDC = *(HDC *)(a1 + 248);
  if ( !CompatibleDC )
  {
    CompatibleDC = CreateCompatibleDC(0);
    *(_QWORD *)(a1 + 248) = CompatibleDC;
  }
  TV_GetBackgroundBrush(a1, CompatibleDC);
  v6 = *(void **)(a1 + 240);
  ColorBitmap = (void *)CreateColorBitmap(v4 * *(__int16 *)(a1 + 308), *(__int16 *)(a1 + 302));
  *(_QWORD *)(a1 + 240) = ColorBitmap;
  if ( v6 )
  {
    SelectObject(CompatibleDC, ColorBitmap);
    DeleteObject(v6);
  }
  else
  {
    *(_QWORD *)(a1 + 232) = SelectObject(CompatibleDC, ColorBitmap);
  }
  v8 = *(_DWORD *)(a1 + 292);
  if ( v8 == -16777216 )
    SolidBrush = (HBRUSH)g_hbrGrayText;
  else
    SolidBrush = CreateSolidBrush(v8);
  v10 = *(_DWORD *)(a1 + 280);
  if ( v10 == -1 )
    v11 = (HBRUSH)g_hbrWindowText;
  else
    v11 = CreateSolidBrush(v10);
  ho = v11;
  v12 = SelectObject(CompatibleDC, SolidBrush);
  v13 = *(HBRUSH *)(a1 + 192);
  v14 = v4 * *(__int16 *)(a1 + 308);
  h = v12;
  *(_QWORD *)&rc.left = 0;
  rc.right = v14;
  rc.bottom = *(__int16 *)(a1 + 302);
  FillRect(CompatibleDC, &rc, v13);
  v15 = 0;
  if ( *(_QWORD *)(a1 + 152) )
    v16 = *(__int16 *)(a1 + 296) - 3;
  else
    v16 = *(__int16 *)(a1 + 308);
  v17 = v16 / 2;
  v18 = v17;
  v19 = (*(__int16 *)(a1 + 302) / 2 + 1) & 0xFFFFFFFE;
  if ( v17 >= v19 )
    v18 = (*(__int16 *)(a1 + 302) / 2 + 1) & 0xFFFFFFFE;
  v20 = v18 / 2;
  v27 = v18 / 2;
  if ( (*(_BYTE *)(a1 + 16) & 2) != 0 )
  {
    TV_DrawDottedLine(CompatibleDC, v17, 0, 1);
    v21 = *(__int16 *)(a1 + 308);
    TV_DrawDottedLine(CompatibleDC, v21 + v17, 0, 1);
    TV_DrawDottedLine(CompatibleDC, v21 + v17, v19, 0);
    v22 = *(__int16 *)(a1 + 308) + v21;
    TV_DrawDottedLine(CompatibleDC, v22 + v17, 0, 1);
    TV_DrawDottedLine(CompatibleDC, v22 + v17, v19, 0);
    v20 = v27;
    v15 = v22 + *(__int16 *)(a1 + 308);
  }
  if ( (*(_BYTE *)(a1 + 16) & 1) != 0 )
  {
    v23 = 1;
    v24 = v17 + v15;
    while ( 1 )
    {
      v28 = v23;
      TV_DrawPlusMinus(CompatibleDC, v24, v19, (HGDIOBJ)v20, ho, SolidBrush, *(_QWORD *)(a1 + 192));
      if ( (*(_BYTE *)(a1 + 16) & 2) != 0 )
      {
        TV_DrawDottedLine(CompatibleDC, v24, 0, 1);
        TV_DrawDottedLine(CompatibleDC, v27 + v24, v19, 0);
        TV_DrawDottedLine(CompatibleDC, v24, v19 + v27, 1);
        v24 += *(__int16 *)(a1 + 308);
        TV_DrawPlusMinus(CompatibleDC, v24, v19, (HGDIOBJ)v27, ho, SolidBrush, *(_QWORD *)(a1 + 192));
        TV_DrawDottedLine(CompatibleDC, v24, 0, 1);
        v20 = v27;
        TV_DrawDottedLine(CompatibleDC, v24 + v27, v19, 0);
      }
      v24 += *(__int16 *)(a1 + 308);
      if ( !v28 )
        break;
      v23 = 0;
    }
    v15 = v24 - v17;
  }
  if ( (*(_BYTE *)(a1 + 16) & 4) != 0 )
  {
    TV_DrawDottedLine(CompatibleDC, v15 + v17, v19, 0);
    if ( (*(_BYTE *)(a1 + 16) & 1) != 0 )
    {
      v25 = v17 + v15 + *(__int16 *)(a1 + 308);
      TV_DrawPlusMinus(CompatibleDC, v25, v19, (HGDIOBJ)v27, ho, SolidBrush, *(_QWORD *)(a1 + 192));
      TV_DrawDottedLine(CompatibleDC, v25 + v27, v19, 0);
      v26 = *(__int16 *)(a1 + 308) + v25;
      TV_DrawPlusMinus(CompatibleDC, v26, v19, (HGDIOBJ)v27, ho, SolidBrush, *(_QWORD *)(a1 + 192));
      TV_DrawDottedLine(CompatibleDC, v26 + v27, v19, 0);
    }
  }
  result = (int)h;
  if ( h )
    result = (unsigned int)SelectObject(*(HDC *)(a1 + 248), h);
  if ( *(_DWORD *)(a1 + 292) != -16777216 )
    result = DeleteObject(SolidBrush);
  if ( *(_DWORD *)(a1 + 280) != -1 )
    return DeleteObject(ho);
  return result;
}

```

## disassembly

```asm
0x18007b364  push    rbx
0x18007b366  push    rbp
0x18007b367  push    rsi
0x18007b368  push    rdi
0x18007b369  push    r12
0x18007b36b  push    r13
0x18007b36d  push    r14
0x18007b36f  push    r15
0x18007b371  sub     rsp, 78h
0x18007b375  mov     rax, cs:__security_cookie
0x18007b37c  xor     rax, rsp
0x18007b37f  mov     [rsp+0B8h+var_50], rax
0x18007b384  test    byte ptr [rcx+38h], 10h
0x18007b388  xorps   xmm0, xmm0
0x18007b38b  movups  xmmword ptr [rsp+0B8h+rc.left], xmm0
0x18007b390  mov     rsi, rcx
0x18007b393  jz      short loc_18007B3A4
0x18007b395  mov     rcx, [rcx]; hWnd
0x18007b398  xor     edx, edx; lpRect
0x18007b39a  lea     r8d, [rdx+1]; bErase
0x18007b39e  call    cs:__imp_InvalidateRect
0x18007b3a4  mov     eax, [rsi+10h]
0x18007b3a7  xor     r15d, r15d
0x18007b3aa  and     eax, 1
0x18007b3ad  test    byte ptr [rsi+10h], 2
0x18007b3b1  jz      short loc_18007B3CD
0x18007b3b3  test    byte ptr [rsi+10h], 4
0x18007b3b7  lea     ebx, ds:3[rax*4]
0x18007b3be  jz      short loc_18007B3DA
0x18007b3c0  test    eax, eax
0x18007b3c2  jz      short loc_18007B3C9
0x18007b3c4  add     ebx, 3
0x18007b3c7  jmp     short loc_18007B3DA
0x18007b3c9  inc     ebx
0x18007b3cb  jmp     short loc_18007B3DA
0x18007b3cd  test    eax, eax
0x18007b3cf  jz      loc_18007B86A
0x18007b3d5  mov     ebx, 2
0x18007b3da  mov     rbp, [rsi+0F8h]
0x18007b3e1  test    rbp, rbp
0x18007b3e4  jnz     short loc_18007B3F8
0x18007b3e6  xor     ecx, ecx; hdc
0x18007b3e8  call    cs:__imp_CreateCompatibleDC
0x18007b3ee  mov     rbp, rax
0x18007b3f1  mov     [rsi+0F8h], rax
0x18007b3f8  mov     rdx, rbp
0x18007b3fb  mov     rcx, rsi
0x18007b3fe  call    TV_GetBackgroundBrush
0x18007b403  movsx   ecx, word ptr [rsi+134h]
0x18007b40a  movsx   edx, word ptr [rsi+12Eh]; cy
0x18007b411  mov     rdi, [rsi+0F0h]
0x18007b418  imul    ecx, ebx; cx
0x18007b41b  call    CreateColorBitmap
0x18007b420  mov     [rsi+0F0h], rax
0x18007b427  mov     rdx, rax; h
0x18007b42a  mov     rcx, rbp; hdc
0x18007b42d  test    rdi, rdi
0x18007b430  jz      short loc_18007B443
0x18007b432  call    cs:__imp_SelectObject
0x18007b438  mov     rcx, rdi; ho
0x18007b43b  call    cs:__imp_DeleteObject
0x18007b441  jmp     short loc_18007B450
0x18007b443  call    cs:__imp_SelectObject
0x18007b449  mov     [rsi+0E8h], rax
0x18007b450  mov     ecx, [rsi+124h]; color
0x18007b456  cmp     ecx, 0FF000000h
0x18007b45c  jz      short loc_18007B469
0x18007b45e  call    cs:__imp_CreateSolidBrush
0x18007b464  mov     r13, rax
0x18007b467  jmp     short loc_18007B470
0x18007b469  mov     r13, cs:g_hbrGrayText
0x18007b470  mov     ecx, [rsi+118h]; color
0x18007b476  cmp     ecx, 0FFFFFFFFh
0x18007b479  jz      short loc_18007B483
0x18007b47b  call    cs:__imp_CreateSolidBrush
0x18007b481  jmp     short loc_18007B48A
0x18007b483  mov     rax, cs:g_hbrWindowText
0x18007b48a  mov     rdx, r13; h
0x18007b48d  mov     [rsp+0B8h+ho], rax
0x18007b492  mov     rcx, rbp; hdc
0x18007b495  call    cs:__imp_SelectObject
0x18007b49b  movsx   ecx, word ptr [rsi+134h]
0x18007b4a2  lea     rdx, [rsp+0B8h+rc]; lprc
0x18007b4a7  mov     r8, [rsi+0C0h]; hbr
0x18007b4ae  imul    ecx, ebx
0x18007b4b1  mov     [rsp+0B8h+h], rax
0x18007b4b6  mov     qword ptr [rsp+0B8h+rc.left], r15
0x18007b4bb  mov     [rsp+0B8h+rc.right], ecx
0x18007b4bf  movsx   ecx, word ptr [rsi+12Eh]
0x18007b4c6  mov     [rsp+0B8h+rc.bottom], ecx
0x18007b4ca  mov     rcx, rbp; hDC
0x18007b4cd  call    cs:__imp_FillRect
0x18007b4d3  mov     r14d, r15d
0x18007b4d6  cmp     [rsi+98h], r15
0x18007b4dd  jz      short loc_18007B4EB
0x18007b4df  movsx   eax, word ptr [rsi+128h]
0x18007b4e6  sub     eax, 3
0x18007b4e9  jmp     short loc_18007B4F2
0x18007b4eb  movsx   eax, word ptr [rsi+134h]
0x18007b4f2  movsx   r9d, word ptr [rsi+12Eh]
0x18007b4fa  cdq
0x18007b4fb  sub     eax, edx
0x18007b4fd  sar     eax, 1
0x18007b4ff  mov     r15d, eax
0x18007b502  mov     eax, r9d
0x18007b505  cdq
0x18007b506  sub     eax, edx
0x18007b508  sar     eax, 1
0x18007b50a  lea     r12d, [rax+1]
0x18007b50e  mov     eax, r15d
0x18007b511  and     r12d, 0FFFFFFFEh
0x18007b515  cmp     r15d, r12d
0x18007b518  cmovge  eax, r12d
0x18007b51c  cdq
0x18007b51d  sub     eax, edx
0x18007b51f  sar     eax, 1
0x18007b521  test    byte ptr [rsi+10h], 2
0x18007b525  mov     ebx, eax
0x18007b527  mov     dword ptr [rsp+0B8h+var_78], eax
0x18007b52b  jz      loc_18007B5E3
0x18007b531  xor     r8d, r8d; y
0x18007b534  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x18007b53c  mov     edx, r15d; x
0x18007b53f  mov     rcx, rbp; hdc
0x18007b542  call    TV_DrawDottedLine
0x18007b547  movsx   edi, word ptr [rsi+134h]
0x18007b54e  mov     r14d, 1
0x18007b554  movsx   r9d, word ptr [rsi+12Eh]
0x18007b55c  xor     r8d, r8d; y
0x18007b55f  mov     rcx, rbp; hdc
0x18007b562  mov     dword ptr [rsp+0B8h+var_98], r14d; int
0x18007b567  lea     ebx, [rdi+r15]
0x18007b56b  mov     edx, ebx; x
0x18007b56d  call    TV_DrawDottedLine
0x18007b572  movsx   r9d, word ptr [rsi+134h]
0x18007b57a  mov     r8d, r12d; y
0x18007b57d  sub     r9d, r15d
0x18007b580  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x18007b588  mov     edx, ebx; x
0x18007b58a  mov     rcx, rbp; hdc
0x18007b58d  call    TV_DrawDottedLine
0x18007b592  movsx   eax, word ptr [rsi+134h]
0x18007b599  mov     r9d, r12d
0x18007b59c  add     edi, eax
0x18007b59e  mov     dword ptr [rsp+0B8h+var_98], r14d; int
0x18007b5a3  xor     r8d, r8d; y
0x18007b5a6  mov     rcx, rbp; hdc
0x18007b5a9  lea     ebx, [rdi+r15]
0x18007b5ad  mov     edx, ebx; x
0x18007b5af  call    TV_DrawDottedLine
0x18007b5b4  movsx   r9d, word ptr [rsi+134h]
0x18007b5bc  mov     r8d, r12d; y
0x18007b5bf  sub     r9d, r15d
0x18007b5c2  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x18007b5ca  mov     edx, ebx; x
0x18007b5cc  mov     rcx, rbp; hdc
0x18007b5cf  call    TV_DrawDottedLine
0x18007b5d4  movsx   r14d, word ptr [rsi+134h]
0x18007b5dc  mov     ebx, dword ptr [rsp+0B8h+var_78]
0x18007b5e0  add     r14d, edi
0x18007b5e3  test    byte ptr [rsi+10h], 1
0x18007b5e7  mov     rdi, [rsp+0B8h+ho]
0x18007b5ec  jz      loc_18007B732
0x18007b5f2  mov     eax, 1
0x18007b5f7  add     r14d, r15d
0x18007b5fa  mov     dword ptr [rsp+0B8h+var_78+4], eax
0x18007b5fe  mov     [rsp+0B8h+var_80], eax
0x18007b602  mov     r9d, ebx; h
0x18007b605  mov     rax, [rsi+0C0h]
0x18007b60c  mov     r8d, r12d; y
0x18007b60f  mov     qword ptr [rsp+0B8h+var_88], rax; int
0x18007b614  mov     edx, r14d; x
0x18007b617  mov     [rsp+0B8h+var_90], r13; HGDIOBJ
0x18007b61c  mov     rcx, rbp; hdc
0x18007b61f  mov     [rsp+0B8h+var_98], rdi; HGDIOBJ
0x18007b624  call    TV_DrawPlusMinus
0x18007b629  test    byte ptr [rsi+10h], 2
0x18007b62d  jz      loc_18007B717
0x18007b633  mov     ebx, r12d
0x18007b636  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x18007b63e  sub     ebx, dword ptr [rsp+0B8h+var_78]
0x18007b642  xor     r8d, r8d; y
0x18007b645  mov     r9d, ebx
0x18007b648  mov     edx, r14d; x
0x18007b64b  mov     rcx, rbp; hdc
0x18007b64e  call    TV_DrawDottedLine
0x18007b653  mov     eax, dword ptr [rsp+0B8h+var_78]
0x18007b657  mov     r8d, r12d; y
0x18007b65a  movsx   r9d, word ptr [rsi+134h]
0x18007b662  mov     rcx, rbp; hdc
0x18007b665  sub     r9d, eax
0x18007b668  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x18007b670  sub     r9d, r15d
0x18007b673  lea     edx, [rax+r14]; x
0x18007b677  call    TV_DrawDottedLine
0x18007b67c  mov     r8d, dword ptr [rsp+0B8h+var_78]
0x18007b681  mov     r9d, ebx
0x18007b684  add     r8d, r12d; y
0x18007b687  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x18007b68f  mov     edx, r14d; x
0x18007b692  mov     rcx, rbp; hdc
0x18007b695  call    TV_DrawDottedLine
0x18007b69a  movsx   eax, word ptr [rsi+134h]
0x18007b6a1  mov     r8d, r12d; y
0x18007b6a4  mov     r9d, dword ptr [rsp+0B8h+var_78]; h
0x18007b6a9  add     r14d, eax
0x18007b6ac  mov     eax, dword ptr [rsp+0B8h+var_78+4]
0x18007b6b0  mov     edx, r14d; x
0x18007b6b3  mov     [rsp+0B8h+var_80], eax
0x18007b6b7  mov     rcx, rbp; hdc
0x18007b6ba  mov     rax, [rsi+0C0h]
0x18007b6c1  mov     qword ptr [rsp+0B8h+var_88], rax; int
0x18007b6c6  mov     [rsp+0B8h+var_90], r13; HGDIOBJ
0x18007b6cb  mov     [rsp+0B8h+var_98], rdi; HGDIOBJ
0x18007b6d0  call    TV_DrawPlusMinus
0x18007b6d5  mov     r9d, ebx
0x18007b6d8  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x18007b6e0  xor     r8d, r8d; y
0x18007b6e3  mov     edx, r14d; x
0x18007b6e6  mov     rcx, rbp; hdc
0x18007b6e9  call    TV_DrawDottedLine
0x18007b6ee  mov     ebx, dword ptr [rsp+0B8h+var_78]
0x18007b6f2  mov     r8d, r12d; y
0x18007b6f5  movsx   r9d, word ptr [rsi+134h]
0x18007b6fd  mov     rcx, rbp; hdc
0x18007b700  sub     r9d, ebx
0x18007b703  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x18007b70b  sub     r9d, r15d
0x18007b70e  lea     edx, [r14+rbx]; x
0x18007b712  call    TV_DrawDottedLine
0x18007b717  movsx   eax, word ptr [rsi+134h]
0x18007b71e  add     r14d, eax
0x18007b721  cmp     dword ptr [rsp+0B8h+var_78+4], 0
0x18007b726  jz      short loc_18007B72F
0x18007b728  xor     eax, eax
0x18007b72a  jmp     loc_18007B5FA
0x18007b72f  sub     r14d, r15d
0x18007b732  test    byte ptr [rsi+10h], 4
0x18007b736  jz      loc_18007B829
0x18007b73c  movsx   r9d, word ptr [rsi+134h]
0x18007b744  lea     edx, [r14+r15]; x
0x18007b748  sub     r9d, r15d
0x18007b74b  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x18007b753  mov     r8d, r12d; y
0x18007b756  mov     rcx, rbp; hdc
0x18007b759  call    TV_DrawDottedLine
0x18007b75e  test    byte ptr [rsi+10h], 1
0x18007b762  jz      loc_18007B829
0x18007b768  movsx   ebx, word ptr [rsi+134h]
0x18007b76f  mov     r8d, r12d; y
0x18007b772  mov     rax, [rsi+0C0h]
0x18007b779  add     ebx, r14d
0x18007b77c  mov     r14d, dword ptr [rsp+0B8h+var_78]
0x18007b781  add     ebx, r15d
0x18007b784  mov     [rsp+0B8h+var_80], 1
0x18007b78c  mov     edx, ebx; x
0x18007b78e  mov     qword ptr [rsp+0B8h+var_88], rax; int
0x18007b793  mov     r9d, r14d; h
0x18007b796  mov     [rsp+0B8h+var_90], r13; HGDIOBJ
0x18007b79b  mov     rcx, rbp; hdc
0x18007b79e  mov     [rsp+0B8h+var_98], rdi; HGDIOBJ
0x18007b7a3  call    TV_DrawPlusMinus
0x18007b7a8  movsx   r9d, word ptr [rsi+134h]
0x18007b7b0  lea     edx, [rbx+r14]; x
0x18007b7b4  sub     r9d, r14d
0x18007b7b7  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x18007b7bf  sub     r9d, r15d
0x18007b7c2  mov     r8d, r12d; y
0x18007b7c5  mov     rcx, rbp; hdc
0x18007b7c8  call    TV_DrawDottedLine
0x18007b7cd  movsx   eax, word ptr [rsi+134h]
0x18007b7d4  mov     r9d, r14d; h
0x18007b7d7  add     ebx, eax
0x18007b7d9  mov     [rsp+0B8h+var_80], 0
0x18007b7e1  mov     rax, [rsi+0C0h]
0x18007b7e8  mov     r8d, r12d; y
0x18007b7eb  mov     qword ptr [rsp+0B8h+var_88], rax; int
0x18007b7f0  mov     edx, ebx; x
0x18007b7f2  mov     [rsp+0B8h+var_90], r13; HGDIOBJ
0x18007b7f7  mov     rcx, rbp; hdc
0x18007b7fa  mov     [rsp+0B8h+var_98], rdi; HGDIOBJ
0x18007b7ff  call    TV_DrawPlusMinus
0x18007b804  movsx   r9d, word ptr [rsi+134h]
0x18007b80c  lea     edx, [rbx+r14]; x
0x18007b810  sub     r9d, r14d
0x18007b813  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x18007b81b  sub     r9d, r15d
0x18007b81e  mov     r8d, r12d; y
0x18007b821  mov     rcx, rbp; hdc
0x18007b824  call    TV_DrawDottedLine
0x18007b829  mov     rax, [rsp+0B8h+h]
0x18007b82e  test    rax, rax
0x18007b831  jz      short loc_18007B843
0x18007b833  mov     rcx, [rsi+0F8h]; hdc
0x18007b83a  mov     rdx, rax; h
0x18007b83d  call    cs:__imp_SelectObject
0x18007b843  cmp     dword ptr [rsi+124h], 0FF000000h
0x18007b84d  jz      short loc_18007B858
0x18007b84f  mov     rcx, r13; ho
0x18007b852  call    cs:__imp_DeleteObject
  ... truncated ...
```

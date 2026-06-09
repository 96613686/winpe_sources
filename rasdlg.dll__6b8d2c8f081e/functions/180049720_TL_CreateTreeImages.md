# TL_CreateTreeImages

- ea: `0x180049720`
- end: `0x180049c51`
- name: `TL_CreateTreeImages`
- size: `1329`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004b64c`
- `0x18004c060`

## callees

- `0x180049720`
- `0x180049d74`
- `0x180049de0`
- `0x18004d110`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18004976e`
- `GDI32!CreateCompatibleDC` at `0x18004976e`
- `GDI32!CreateCompatibleBitmap` at `0x1800497e1`
- `GDI32!CreateCompatibleBitmap` at `0x1800497e1`
- `GDI32!DeleteObject` at `0x18004981f`
- `GDI32!DeleteObject` at `0x180049c24`
- `GDI32!DeleteObject` at `0x180049c2d`
- `GDI32!DeleteObject` at `0x18004981f`
- `GDI32!DeleteObject` at `0x180049c24`
- `GDI32!DeleteObject` at `0x180049c2d`
- `GDI32!SelectObject` at `0x180049807`
- `GDI32!SelectObject` at `0x180049816`
- `GDI32!SelectObject` at `0x18004984b`
- `GDI32!SelectObject` at `0x180049940`
- `GDI32!SelectObject` at `0x1800499a5`
- `GDI32!SelectObject` at `0x180049a5e`
- `GDI32!SelectObject` at `0x180049ae6`
- `GDI32!SelectObject` at `0x180049b96`
- `GDI32!SelectObject` at `0x180049c1b`
- `GDI32!SelectObject` at `0x180049807`
- `GDI32!SelectObject` at `0x180049816`
- `GDI32!SelectObject` at `0x18004984b`
- `GDI32!SelectObject` at `0x180049940`
- `GDI32!SelectObject` at `0x1800499a5`
- `GDI32!SelectObject` at `0x180049a5e`
- `GDI32!SelectObject` at `0x180049ae6`
- `GDI32!SelectObject` at `0x180049b96`
- `GDI32!SelectObject` at `0x180049c1b`
- `USER32!GetDC` at `0x1800497ba`
- `USER32!GetDC` at `0x1800497ba`
- `USER32!InvalidateRect` at `0x18004975a`
- `USER32!InvalidateRect` at `0x18004975a`
- `USER32!ReleaseDC` at `0x1800497ef`
- `USER32!ReleaseDC` at `0x1800497ef`
- `USER32!SendMessageW` at `0x18004979d`
- `USER32!SendMessageW` at `0x18004979d`
- `USER32!GetSysColorBrush` at `0x18004982a`
- `USER32!GetSysColorBrush` at `0x18004983a`
- `USER32!GetSysColorBrush` at `0x18004982a`
- `USER32!GetSysColorBrush` at `0x18004983a`
- `USER32!FillRect` at `0x18004987d`
- `USER32!FillRect` at `0x18004987d`

## pseudocode

```c
int __fastcall TL_CreateTreeImages(__int64 a1)
{
  HWND v2; // rcx
  HDC v3; // r12
  HDC CompatibleDC; // rax
  int v5; // r13d
  LRESULT v6; // rax
  void *v7; // rbp
  int v8; // ebx
  HDC DC; // rax
  HDC v10; // rdi
  HBITMAP CompatibleBitmap; // rbx
  HGDIOBJ v12; // rax
  HBRUSH v13; // r8
  signed int v14; // eax
  int v15; // esi
  signed int v16; // r14d
  unsigned int v17; // ebp
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  HBRUSH h; // [rsp+40h] [rbp-78h]
  HBRUSH ho; // [rsp+48h] [rbp-70h]
  HGDIOBJ v25; // [rsp+50h] [rbp-68h]
  RECT rc; // [rsp+58h] [rbp-60h] BYREF

  v2 = *(HWND *)(a1 + 16);
  rc = 0;
  if ( v2 )
    InvalidateRect(v2, 0, 1);
  v3 = *(HDC *)(a1 + 232);
  if ( v3 || (CompatibleDC = CreateCompatibleDC(0), *(_QWORD *)(a1 + 232) = CompatibleDC, (v3 = CompatibleDC) != 0) )
  {
    v5 = *(_DWORD *)(a1 + 228);
    v6 = SendMessageW(*(HWND *)(a1 + 24), 0x133u, (WPARAM)v3, *(_QWORD *)a1);
    v7 = *(void **)(a1 + 240);
    v8 = *(_DWORD *)(a1 + 220);
    *(_QWORD *)(a1 + 272) = v6;
    DC = GetDC(0);
    v10 = DC;
    if ( DC )
    {
      CompatibleBitmap = CreateCompatibleBitmap(DC, 10 * v5, v8);
      ReleaseDC(0, v10);
    }
    else
    {
      CompatibleBitmap = 0;
    }
    *(_QWORD *)(a1 + 240) = CompatibleBitmap;
    if ( v7 )
    {
      SelectObject(v3, CompatibleBitmap);
      DeleteObject(v7);
    }
    else
    {
      *(_QWORD *)(a1 + 264) = SelectObject(v3, CompatibleBitmap);
    }
    ho = GetSysColorBrush(8);
    h = GetSysColorBrush(17);
    v12 = SelectObject(v3, h);
    v13 = *(HBRUSH *)(a1 + 272);
    rc.bottom = *(_DWORD *)(a1 + 220);
    v25 = v12;
    *(_QWORD *)&rc.left = 0;
    rc.right = 10 * v5;
    FillRect(v3, &rc, v13);
    v14 = v5 / 2;
    v15 = v5 / 2;
    v16 = ((*(_DWORD *)(a1 + 220) >> 1) + 1) & 0xFFFFFFFE;
    if ( v5 / 2 >= v16 )
      v14 = ((*(_DWORD *)(a1 + 220) >> 1) + 1) & 0xFFFFFFFE;
    v17 = v14 / 2;
    TL_DottedLine(v3, v15, 0, 1);
    TL_DottedLine(v3, v15 + v5, v16, 0);
    TL_DottedLine(v3, v15 + 2 * v5, v16, 0);
    TL_DrawButton(v3, v15 + 2 * v5, v16, (HGDIOBJ)v17, ho, h, *(_QWORD *)(a1 + 272));
    SelectObject(v3, h);
    TL_DottedLine(v3, v5 + v15 + 2 * v5, v16, 0);
    TL_DrawButton(v3, v5 + v15 + 2 * v5, v16, (HGDIOBJ)v17, ho, h, *(_QWORD *)(a1 + 272));
    SelectObject(v3, h);
    TL_DottedLine(v3, v15 + 4 * v5, 0, 1);
    TL_DottedLine(v3, v15 + 4 * v5, v16, 0);
    v18 = v5 + v15 + 4 * v5;
    TL_DottedLine(v3, v18, 0, 1);
    TL_DottedLine(v3, v18, v16, 0);
    TL_DrawButton(v3, v18, v16, (HGDIOBJ)v17, ho, h, *(_QWORD *)(a1 + 272));
    SelectObject(v3, h);
    v19 = v15 + 6 * v5;
    TL_DottedLine(v3, v19, 0, 1);
    TL_DottedLine(v3, v19, v16, 0);
    TL_DrawButton(v3, v19, v16, (HGDIOBJ)v17, ho, h, *(_QWORD *)(a1 + 272));
    SelectObject(v3, h);
    TL_DottedLine(v3, v15 + 7 * v5, 0, 1);
    TL_DottedLine(v3, v15 + 7 * v5, v16, 0);
    v20 = v15 + 8 * v5;
    TL_DottedLine(v3, v20, 0, 1);
    TL_DottedLine(v3, v20, v16, 0);
    TL_DrawButton(v3, v20, v16, (HGDIOBJ)v17, ho, h, *(_QWORD *)(a1 + 272));
    SelectObject(v3, h);
    v21 = v5 + v20;
    TL_DottedLine(v3, v5 + v15 + 8 * v5, 0, 1);
    TL_DottedLine(v3, v21, v16, 0);
    TL_DrawButton(v3, v21, v16, (HGDIOBJ)v17, ho, h, *(_QWORD *)(a1 + 272));
    if ( v25 )
      SelectObject(v3, v25);
    DeleteObject(h);
    LODWORD(CompatibleDC) = DeleteObject(ho);
  }
  return (int)CompatibleDC;
}

```

## disassembly

```asm
0x180049720  push    rbx
0x180049722  push    rbp
0x180049723  push    rsi
0x180049724  push    rdi
0x180049725  push    r12
0x180049727  push    r13
0x180049729  push    r14
0x18004972b  push    r15
0x18004972d  sub     rsp, 78h
0x180049731  mov     rax, cs:__security_cookie
0x180049738  xor     rax, rsp
0x18004973b  mov     [rsp+0B8h+var_50], rax
0x180049740  mov     r15, rcx
0x180049743  xorps   xmm0, xmm0
0x180049746  mov     rcx, [rcx+10h]; hWnd
0x18004974a  movups  xmmword ptr [rsp+0B8h+rc.left], xmm0
0x18004974f  test    rcx, rcx
0x180049752  jz      short loc_180049760
0x180049754  xor     edx, edx; lpRect
0x180049756  lea     r8d, [rdx+1]; bErase
0x18004975a  call    cs:__imp_InvalidateRect
0x180049760  mov     r12, [r15+0E8h]
0x180049767  test    r12, r12
0x18004976a  jnz     short loc_180049787
0x18004976c  xor     ecx, ecx; hdc
0x18004976e  call    cs:__imp_CreateCompatibleDC
0x180049774  mov     [r15+0E8h], rax
0x18004977b  mov     r12, rax
0x18004977e  test    rax, rax
0x180049781  jz      loc_180049C33
0x180049787  mov     r9, [r15]; lParam
0x18004978a  mov     r8, r12; wParam
0x18004978d  mov     rcx, [r15+18h]; hWnd
0x180049791  mov     edx, 133h; Msg
0x180049796  mov     r13d, [r15+0E4h]
0x18004979d  call    cs:__imp_SendMessageW
0x1800497a3  mov     rbp, [r15+0F0h]
0x1800497aa  xor     ecx, ecx; hWnd
0x1800497ac  mov     ebx, [r15+0DCh]
0x1800497b3  mov     [r15+110h], rax
0x1800497ba  call    cs:__imp_GetDC
0x1800497c0  lea     esi, ds:0[r13*4]
0x1800497c8  mov     rdi, rax
0x1800497cb  add     esi, r13d
0x1800497ce  add     esi, esi
0x1800497d0  test    rax, rax
0x1800497d3  jnz     short loc_1800497D9
0x1800497d5  xor     ebx, ebx
0x1800497d7  jmp     short loc_1800497F5
0x1800497d9  mov     r8d, ebx; cy
0x1800497dc  mov     edx, esi; cx
0x1800497de  mov     rcx, rdi; hdc
0x1800497e1  call    cs:__imp_CreateCompatibleBitmap
0x1800497e7  mov     rdx, rdi; hDC
0x1800497ea  xor     ecx, ecx; hWnd
0x1800497ec  mov     rbx, rax
0x1800497ef  call    cs:__imp_ReleaseDC
0x1800497f5  mov     [r15+0F0h], rbx
0x1800497fc  mov     rdx, rbx; h
0x1800497ff  mov     rcx, r12; hdc
0x180049802  test    rbp, rbp
0x180049805  jnz     short loc_180049816
0x180049807  call    cs:__imp_SelectObject
0x18004980d  mov     [r15+108h], rax
0x180049814  jmp     short loc_180049825
0x180049816  call    cs:__imp_SelectObject
0x18004981c  mov     rcx, rbp; ho
0x18004981f  call    cs:__imp_DeleteObject
0x180049825  mov     ecx, 8; nIndex
0x18004982a  call    cs:__imp_GetSysColorBrush
0x180049830  mov     ecx, 11h; nIndex
0x180049835  mov     [rsp+0B8h+ho], rax
0x18004983a  call    cs:__imp_GetSysColorBrush
0x180049840  mov     rdx, rax; h
0x180049843  mov     [rsp+0B8h+h], rax
0x180049848  mov     rcx, r12; hdc
0x18004984b  call    cs:__imp_SelectObject
0x180049851  mov     ecx, [r15+0DCh]
0x180049858  lea     rdx, [rsp+0B8h+rc]; lprc
0x18004985d  mov     r8, [r15+110h]; hbr
0x180049864  mov     [rsp+0B8h+rc.bottom], ecx
0x180049868  mov     rcx, r12; hDC
0x18004986b  mov     [rsp+0B8h+var_68], rax
0x180049870  mov     qword ptr [rsp+0B8h+rc.left], 0
0x180049879  mov     [rsp+0B8h+rc.right], esi
0x18004987d  call    cs:__imp_FillRect
0x180049883  mov     r9d, [r15+0DCh]
0x18004988a  mov     ecx, 2
0x18004988f  mov     eax, r13d
0x180049892  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x18004989a  cdq
0x18004989b  mov     r14d, r9d
0x18004989e  idiv    ecx
0x1800498a0  shr     r14d, 1
0x1800498a3  mov     esi, eax
0x1800498a5  inc     r14d
0x1800498a8  and     r14d, 0FFFFFFFEh
0x1800498ac  cmp     eax, r14d
0x1800498af  cmovge  eax, r14d
0x1800498b3  xor     r8d, r8d; y
0x1800498b6  cdq
0x1800498b7  idiv    ecx
0x1800498b9  mov     edx, esi; x
0x1800498bb  mov     rcx, r12; hdc
0x1800498be  mov     ebp, eax
0x1800498c0  call    TL_DottedLine
0x1800498c5  mov     edi, r13d
0x1800498c8  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x1800498d0  sub     edi, esi
0x1800498d2  lea     edx, [rsi+r13]; x
0x1800498d6  mov     r9d, edi
0x1800498d9  mov     r8d, r14d; y
0x1800498dc  mov     rcx, r12; hdc
0x1800498df  call    TL_DottedLine
0x1800498e4  lea     ebx, [rsi+r13*2]
0x1800498e8  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x1800498f0  mov     edx, ebx; x
0x1800498f2  mov     r9d, edi
0x1800498f5  mov     r8d, r14d; y
0x1800498f8  mov     rcx, r12; hdc
0x1800498fb  call    TL_DottedLine
0x180049900  mov     rax, [r15+110h]
0x180049907  mov     r9d, ebp; HGDIOBJ
0x18004990a  mov     [rsp+0B8h+var_80], 1
0x180049912  mov     r8d, r14d; y
0x180049915  mov     qword ptr [rsp+0B8h+var_88], rax; int
0x18004991a  mov     edx, ebx; x
0x18004991c  mov     rax, [rsp+0B8h+h]
0x180049921  mov     rcx, r12; hdc
0x180049924  mov     [rsp+0B8h+var_90], rax; h
0x180049929  mov     rax, [rsp+0B8h+ho]
0x18004992e  mov     [rsp+0B8h+var_98], rax; HGDIOBJ
0x180049933  call    TL_DrawButton
0x180049938  mov     rdx, [rsp+0B8h+h]; h
0x18004993d  mov     rcx, r12; hdc
0x180049940  call    cs:__imp_SelectObject
0x180049946  lea     ebx, [rsi+r13*2]
0x18004994a  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x180049952  add     ebx, r13d
0x180049955  mov     r9d, edi
0x180049958  mov     edx, ebx; x
0x18004995a  mov     r8d, r14d; y
0x18004995d  mov     rcx, r12; hdc
0x180049960  call    TL_DottedLine
0x180049965  mov     rax, [r15+110h]
0x18004996c  mov     [rsp+0B8h+var_80], 0
0x180049974  mov     qword ptr [rsp+0B8h+var_88], rax; int
0x180049979  mov     rax, [rsp+0B8h+h]
0x18004997e  mov     [rsp+0B8h+var_90], rax; h
0x180049983  mov     rax, [rsp+0B8h+ho]
0x180049988  mov     r9d, ebp; HGDIOBJ
0x18004998b  mov     r8d, r14d; y
0x18004998e  mov     [rsp+0B8h+var_98], rax; HGDIOBJ
0x180049993  mov     edx, ebx; x
0x180049995  mov     rcx, r12; hdc
0x180049998  call    TL_DrawButton
0x18004999d  mov     rdx, [rsp+0B8h+h]; h
0x1800499a2  mov     rcx, r12; hdc
0x1800499a5  call    cs:__imp_SelectObject
0x1800499ab  mov     r9d, [r15+0DCh]
0x1800499b2  lea     ebx, [rsi+r13*4]
0x1800499b6  mov     edx, ebx; x
0x1800499b8  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x1800499c0  xor     r8d, r8d; y
0x1800499c3  mov     rcx, r12; hdc
0x1800499c6  call    TL_DottedLine
0x1800499cb  mov     r9d, edi
0x1800499ce  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x1800499d6  mov     r8d, r14d; y
0x1800499d9  mov     edx, ebx; x
0x1800499db  mov     rcx, r12; hdc
0x1800499de  call    TL_DottedLine
0x1800499e3  mov     r9d, [r15+0DCh]
0x1800499ea  lea     ebx, [rsi+r13*4]
0x1800499ee  add     ebx, r13d
0x1800499f1  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x1800499f9  mov     edx, ebx; x
0x1800499fb  xor     r8d, r8d; y
0x1800499fe  mov     rcx, r12; hdc
0x180049a01  call    TL_DottedLine
0x180049a06  mov     r9d, edi
0x180049a09  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x180049a11  mov     r8d, r14d; y
0x180049a14  mov     edx, ebx; x
0x180049a16  mov     rcx, r12; hdc
0x180049a19  call    TL_DottedLine
0x180049a1e  mov     rax, [r15+110h]
0x180049a25  mov     r9d, ebp; HGDIOBJ
0x180049a28  mov     [rsp+0B8h+var_80], 1
0x180049a30  mov     r8d, r14d; y
0x180049a33  mov     qword ptr [rsp+0B8h+var_88], rax; int
0x180049a38  mov     edx, ebx; x
0x180049a3a  mov     rax, [rsp+0B8h+h]
0x180049a3f  mov     rcx, r12; hdc
0x180049a42  mov     [rsp+0B8h+var_90], rax; h
0x180049a47  mov     rax, [rsp+0B8h+ho]
0x180049a4c  mov     [rsp+0B8h+var_98], rax; HGDIOBJ
0x180049a51  call    TL_DrawButton
0x180049a56  mov     rdx, [rsp+0B8h+h]; h
0x180049a5b  mov     rcx, r12; hdc
0x180049a5e  call    cs:__imp_SelectObject
0x180049a64  mov     r9d, [r15+0DCh]
0x180049a6b  lea     eax, ds:0[r13*2]
0x180049a73  add     eax, r13d
0x180049a76  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x180049a7e  xor     r8d, r8d; y
0x180049a81  mov     rcx, r12; hdc
0x180049a84  lea     ebx, [rsi+rax*2]
0x180049a87  mov     edx, ebx; x
0x180049a89  call    TL_DottedLine
0x180049a8e  mov     r9d, edi
0x180049a91  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x180049a99  mov     r8d, r14d; y
0x180049a9c  mov     edx, ebx; x
0x180049a9e  mov     rcx, r12; hdc
0x180049aa1  call    TL_DottedLine
0x180049aa6  mov     rax, [r15+110h]
0x180049aad  mov     r9d, ebp; HGDIOBJ
0x180049ab0  mov     [rsp+0B8h+var_80], 0
0x180049ab8  mov     r8d, r14d; y
0x180049abb  mov     qword ptr [rsp+0B8h+var_88], rax; int
0x180049ac0  mov     edx, ebx; x
0x180049ac2  mov     rax, [rsp+0B8h+h]
0x180049ac7  mov     rcx, r12; hdc
0x180049aca  mov     [rsp+0B8h+var_90], rax; h
0x180049acf  mov     rax, [rsp+0B8h+ho]
0x180049ad4  mov     [rsp+0B8h+var_98], rax; HGDIOBJ
0x180049ad9  call    TL_DrawButton
0x180049ade  mov     rdx, [rsp+0B8h+h]; h
0x180049ae3  mov     rcx, r12; hdc
0x180049ae6  call    cs:__imp_SelectObject
0x180049aec  imul    ebx, r13d, 7
0x180049af0  mov     r9d, r14d
0x180049af3  xor     r8d, r8d; y
0x180049af6  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x180049afe  mov     rcx, r12; hdc
0x180049b01  add     ebx, esi
0x180049b03  mov     edx, ebx; x
0x180049b05  call    TL_DottedLine
0x180049b0a  mov     r9d, edi
0x180049b0d  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x180049b15  mov     r8d, r14d; y
0x180049b18  mov     edx, ebx; x
0x180049b1a  mov     rcx, r12; hdc
0x180049b1d  call    TL_DottedLine
0x180049b22  lea     ebx, [rsi+r13*8]
0x180049b26  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x180049b2e  mov     edx, ebx; x
0x180049b30  mov     r9d, r14d
0x180049b33  xor     r8d, r8d; y
0x180049b36  mov     rcx, r12; hdc
0x180049b39  call    TL_DottedLine
0x180049b3e  mov     r9d, edi
0x180049b41  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x180049b49  mov     r8d, r14d; y
0x180049b4c  mov     edx, ebx; x
0x180049b4e  mov     rcx, r12; hdc
0x180049b51  call    TL_DottedLine
0x180049b56  mov     rax, [r15+110h]
0x180049b5d  mov     r9d, ebp; HGDIOBJ
0x180049b60  mov     [rsp+0B8h+var_80], 1
0x180049b68  mov     r8d, r14d; y
0x180049b6b  mov     qword ptr [rsp+0B8h+var_88], rax; int
0x180049b70  mov     edx, ebx; x
0x180049b72  mov     rax, [rsp+0B8h+h]
0x180049b77  mov     rcx, r12; hdc
0x180049b7a  mov     [rsp+0B8h+var_90], rax; h
0x180049b7f  mov     rax, [rsp+0B8h+ho]
0x180049b84  mov     [rsp+0B8h+var_98], rax; HGDIOBJ
0x180049b89  call    TL_DrawButton
0x180049b8e  mov     rdx, [rsp+0B8h+h]; h
0x180049b93  mov     rcx, r12; hdc
0x180049b96  call    cs:__imp_SelectObject
0x180049b9c  lea     ebx, [rsi+r13*8]
0x180049ba0  mov     dword ptr [rsp+0B8h+var_98], 1; int
0x180049ba8  add     ebx, r13d
0x180049bab  mov     r9d, r14d
0x180049bae  mov     edx, ebx; x
0x180049bb0  xor     r8d, r8d; y
0x180049bb3  mov     rcx, r12; hdc
0x180049bb6  call    TL_DottedLine
0x180049bbb  mov     r9d, edi
0x180049bbe  mov     dword ptr [rsp+0B8h+var_98], 0; int
0x180049bc6  mov     r8d, r14d; y
0x180049bc9  mov     edx, ebx; x
0x180049bcb  mov     rcx, r12; hdc
0x180049bce  call    TL_DottedLine
0x180049bd3  mov     rax, [r15+110h]
0x180049bda  mov     r9d, ebp; HGDIOBJ
0x180049bdd  mov     rdi, [rsp+0B8h+h]
0x180049be2  mov     r8d, r14d; y
0x180049be5  mov     rsi, [rsp+0B8h+ho]
0x180049bea  mov     edx, ebx; x
0x180049bec  mov     [rsp+0B8h+var_80], 0
0x180049bf4  mov     rcx, r12; hdc
0x180049bf7  mov     qword ptr [rsp+0B8h+var_88], rax; int
0x180049bfc  mov     [rsp+0B8h+var_90], rdi; h
0x180049c01  mov     [rsp+0B8h+var_98], rsi; HGDIOBJ
0x180049c06  call    TL_DrawButton
0x180049c0b  mov     rax, [rsp+0B8h+var_68]
  ... truncated ...
```

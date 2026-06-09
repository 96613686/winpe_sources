# Tab_DrawItemFrame

- ea: `0x1800644d0`
- end: `0x180064739`
- name: `Tab_DrawItemFrame`
- size: `617`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, HDC hdc@<rdx>, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180065e84`

## callees

- `0x1800115f0`
- `0x1800636e8`
- `0x180064428`
- `0x1800644d0`

## import_xrefs

- `GDI32!SelectObject` at `0x180064583`
- `GDI32!SelectObject` at `0x1800645d8`
- `GDI32!SelectObject` at `0x18006460e`
- `GDI32!SelectObject` at `0x180064663`
- `GDI32!SelectObject` at `0x180064583`
- `GDI32!SelectObject` at `0x1800645d8`
- `GDI32!SelectObject` at `0x18006460e`
- `GDI32!SelectObject` at `0x180064663`
- `GDI32!DeleteObject` at `0x1800645e1`
- `GDI32!DeleteObject` at `0x18006466c`
- `GDI32!DeleteObject` at `0x1800645e1`
- `GDI32!DeleteObject` at `0x18006466c`
- `GDI32!CreatePen` at `0x180064574`
- `GDI32!CreatePen` at `0x1800645ff`
- `GDI32!CreatePen` at `0x180064574`
- `GDI32!CreatePen` at `0x1800645ff`
- `GDI32!MoveToEx` at `0x180064599`
- `GDI32!MoveToEx` at `0x1800645bc`
- `GDI32!MoveToEx` at `0x180064624`
- `GDI32!MoveToEx` at `0x180064647`
- `GDI32!MoveToEx` at `0x180064599`
- `GDI32!MoveToEx` at `0x1800645bc`
- `GDI32!MoveToEx` at `0x180064624`
- `GDI32!MoveToEx` at `0x180064647`
- `GDI32!LineTo` at `0x1800645a9`
- `GDI32!LineTo` at `0x1800645cc`
- `GDI32!LineTo` at `0x180064634`
- `GDI32!LineTo` at `0x180064657`
- `GDI32!LineTo` at `0x1800645a9`
- `GDI32!LineTo` at `0x1800645cc`
- `GDI32!LineTo` at `0x180064634`
- `GDI32!LineTo` at `0x180064657`
- `USER32!GetSysColor` at `0x180064567`
- `USER32!GetSysColor` at `0x1800645f2`
- `USER32!GetSysColor` at `0x180064567`
- `USER32!GetSysColor` at `0x1800645f2`
- `USER32!CopyRect` at `0x180064551`
- `USER32!CopyRect` at `0x1800646ee`
- `USER32!CopyRect` at `0x180064551`
- `USER32!CopyRect` at `0x1800646ee`
- `USER32!DrawEdge` at `0x180064716`
- `USER32!DrawEdge` at `0x180064716`

## pseudocode

```c
int __fastcall Tab_DrawItemFrame(__int64 a1, HDC hdc, int a3, const RECT *a4, int a5)
{
  int v5; // eax
  int v9; // ebx
  DWORD SysColor; // eax
  HPEN Pen; // rdi
  HGDIOBJ v12; // rbx
  DWORD v13; // eax
  HPEN v14; // rdi
  HGDIOBJ v15; // rbx
  int result; // eax
  struct tagRECT rcDst; // [rsp+30h] [rbp-28h] BYREF

  v5 = *(_DWORD *)(a1 + 16);
  if ( (v5 & 0x100) == 0 || (v5 & 8) == 0 || a3 == 10 || a3 == 4 || (v5 & 0x40) != 0 && a5 == *(_DWORD *)(a1 + 216) )
  {
    result = Tab_DrawEdge(hdc, a1);
  }
  else
  {
    rcDst = 0;
    CopyRect(&rcDst, a4);
    v9 = 2 * g_cyEdge;
    SysColor = GetSysColor(15);
    Pen = CreatePen(0, v9, SysColor);
    v12 = SelectObject(hdc, Pen);
    MoveToEx(hdc, rcDst.left, rcDst.top, 0);
    LineTo(hdc, rcDst.right, rcDst.top);
    MoveToEx(hdc, rcDst.left, rcDst.bottom, 0);
    LineTo(hdc, rcDst.right, rcDst.bottom);
    SelectObject(hdc, v12);
    DeleteObject(Pen);
    LODWORD(v12) = 2 * g_cxEdge;
    v13 = GetSysColor(15);
    v14 = CreatePen(0, (int)v12, v13);
    v15 = SelectObject(hdc, v14);
    MoveToEx(hdc, rcDst.left, rcDst.top, 0);
    LineTo(hdc, rcDst.left, rcDst.bottom);
    MoveToEx(hdc, rcDst.right, rcDst.top, 0);
    LineTo(hdc, rcDst.right, rcDst.bottom);
    SelectObject(hdc, v15);
    result = DeleteObject(v14);
  }
  if ( (*(_DWORD *)(a1 + 16) & 0x100) == 0 )
    return DoCorners(hdc);
  if ( (*(_BYTE *)(a1 + 16) & 8) != 0 && (*(_BYTE *)(a1 + 80) & 1) != 0 )
  {
    rcDst = 0;
    CopyRect(&rcDst, a4);
    rcDst.right += g_cxEdge + 2 * g_cxEdge;
    return DrawEdge(hdc, &rcDst, 6u, 4u);
  }
  return result;
}

```

## disassembly

```asm
0x1800644d0  push    rbp
0x1800644d2  push    rbx
0x1800644d3  push    rsi
0x1800644d4  push    rdi
0x1800644d5  push    r12
0x1800644d7  push    r13
0x1800644d9  push    r14
0x1800644db  push    r15
0x1800644dd  mov     rbp, rsp
0x1800644e0  sub     rsp, 58h
0x1800644e4  mov     rax, cs:__security_cookie
0x1800644eb  xor     rax, rsp
0x1800644ee  mov     [rbp+var_18], rax
0x1800644f2  mov     eax, [rcx+10h]
0x1800644f5  xor     r13d, r13d
0x1800644f8  mov     r15, r9
0x1800644fb  mov     r12, rdx
0x1800644fe  mov     r14, rcx
0x180064501  bt      eax, 8
0x180064505  jnb     loc_180064682
0x18006450b  test    al, 8
0x18006450d  jz      loc_18006467B
0x180064513  cmp     r8d, 0Ah
0x180064517  jz      loc_180064674
0x18006451d  cmp     r8d, 4
0x180064521  jz      loc_180064674
0x180064527  test    al, 40h
0x180064529  jz      short loc_180064543
0x18006452b  mov     eax, [rcx+0D8h]
0x180064531  cmp     [rbp+arg_20], eax
0x180064534  jnz     short loc_180064543
0x180064536  lea     esi, [r13+0Fh]
0x18006453a  lea     r8d, [r13+4]
0x18006453e  jmp     loc_1800646A2
0x180064543  xorps   xmm0, xmm0
0x180064546  lea     rcx, [rbp+rcDst]; lprcDst
0x18006454a  mov     rdx, r15; lprcSrc
0x18006454d  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x180064551  call    cs:__imp_CopyRect
0x180064557  mov     eax, cs:g_cyEdge
0x18006455d  mov     esi, 0Fh
0x180064562  mov     ecx, esi; nIndex
0x180064564  lea     ebx, [rax+rax]
0x180064567  call    cs:__imp_GetSysColor
0x18006456d  mov     edx, ebx; cWidth
0x18006456f  xor     ecx, ecx; iStyle
0x180064571  mov     r8d, eax; color
0x180064574  call    cs:__imp_CreatePen
0x18006457a  mov     rdx, rax; h
0x18006457d  mov     rcx, r12; hdc
0x180064580  mov     rdi, rax
0x180064583  call    cs:__imp_SelectObject
0x180064589  mov     r8d, [rbp+rcDst.top]; y
0x18006458d  xor     r9d, r9d; lppt
0x180064590  mov     edx, [rbp+rcDst.left]; x
0x180064593  mov     rcx, r12; hdc
0x180064596  mov     rbx, rax
0x180064599  call    cs:__imp_MoveToEx
0x18006459f  mov     r8d, [rbp+rcDst.top]; y
0x1800645a3  mov     rcx, r12; hdc
0x1800645a6  mov     edx, [rbp+rcDst.right]; x
0x1800645a9  call    cs:__imp_LineTo
0x1800645af  mov     r8d, [rbp+rcDst.bottom]; y
0x1800645b3  xor     r9d, r9d; lppt
0x1800645b6  mov     edx, [rbp+rcDst.left]; x
0x1800645b9  mov     rcx, r12; hdc
0x1800645bc  call    cs:__imp_MoveToEx
0x1800645c2  mov     r8d, [rbp+rcDst.bottom]; y
0x1800645c6  mov     rcx, r12; hdc
0x1800645c9  mov     edx, [rbp+rcDst.right]; x
0x1800645cc  call    cs:__imp_LineTo
0x1800645d2  mov     rdx, rbx; h
0x1800645d5  mov     rcx, r12; hdc
0x1800645d8  call    cs:__imp_SelectObject
0x1800645de  mov     rcx, rdi; ho
0x1800645e1  call    cs:__imp_DeleteObject
0x1800645e7  mov     eax, cs:g_cxEdge
0x1800645ed  mov     ecx, esi; nIndex
0x1800645ef  lea     ebx, [rax+rax]
0x1800645f2  call    cs:__imp_GetSysColor
0x1800645f8  mov     edx, ebx; cWidth
0x1800645fa  xor     ecx, ecx; iStyle
0x1800645fc  mov     r8d, eax; color
0x1800645ff  call    cs:__imp_CreatePen
0x180064605  mov     rdx, rax; h
0x180064608  mov     rcx, r12; hdc
0x18006460b  mov     rdi, rax
0x18006460e  call    cs:__imp_SelectObject
0x180064614  mov     r8d, [rbp+rcDst.top]; y
0x180064618  xor     r9d, r9d; lppt
0x18006461b  mov     edx, [rbp+rcDst.left]; x
0x18006461e  mov     rcx, r12; hdc
0x180064621  mov     rbx, rax
0x180064624  call    cs:__imp_MoveToEx
0x18006462a  mov     r8d, [rbp+rcDst.bottom]; y
0x18006462e  mov     rcx, r12; hdc
0x180064631  mov     edx, [rbp+rcDst.left]; x
0x180064634  call    cs:__imp_LineTo
0x18006463a  mov     r8d, [rbp+rcDst.top]; y
0x18006463e  xor     r9d, r9d; lppt
0x180064641  mov     edx, [rbp+rcDst.right]; x
0x180064644  mov     rcx, r12; hdc
0x180064647  call    cs:__imp_MoveToEx
0x18006464d  mov     r8d, [rbp+rcDst.bottom]; y
0x180064651  mov     rcx, r12; hdc
0x180064654  mov     edx, [rbp+rcDst.right]; x
0x180064657  call    cs:__imp_LineTo
0x18006465d  mov     rdx, rbx; h
0x180064660  mov     rcx, r12; hdc
0x180064663  call    cs:__imp_SelectObject
0x180064669  mov     rcx, rdi; ho
0x18006466c  call    cs:__imp_DeleteObject
0x180064672  jmp     short loc_1800646B5
0x180064674  mov     esi, 0Fh
0x180064679  jmp     short loc_1800646A2
0x18006467b  mov     esi, 100Fh
0x180064680  jmp     short loc_1800646A2
0x180064682  mov     esi, 1007h
0x180064687  test    al, 1
0x180064689  jz      short loc_1800646A2
0x18006468b  mov     eax, [rcx+98h]
0x180064691  cmp     [r9+28h], eax
0x180064695  jle     short loc_1800646A2
0x180064697  mov     esi, 100Dh
0x18006469c  mov     r13d, 1
0x1800646a2  mov     r9d, esi
0x1800646a5  mov     [rsp+58h+var_38], r14; __int64
0x1800646aa  mov     rdx, r15
0x1800646ad  mov     rcx, r12; hdc
0x1800646b0  call    Tab_DrawEdge
0x1800646b5  test    dword ptr [r14+10h], 100h
0x1800646bd  jnz     short loc_1800646D2
0x1800646bf  mov     r9d, r13d
0x1800646c2  mov     r8, r14
0x1800646c5  mov     rdx, r15
0x1800646c8  mov     rcx, r12; hdc
0x1800646cb  call    DoCorners
0x1800646d0  jmp     short loc_18006471C
0x1800646d2  test    byte ptr [r14+10h], 8
0x1800646d7  jz      short loc_18006471C
0x1800646d9  test    byte ptr [r14+50h], 1
0x1800646de  jz      short loc_18006471C
0x1800646e0  xorps   xmm0, xmm0
0x1800646e3  lea     rcx, [rbp+rcDst]; lprcDst
0x1800646e7  mov     rdx, r15; lprcSrc
0x1800646ea  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x1800646ee  call    cs:__imp_CopyRect
0x1800646f4  mov     ecx, cs:g_cxEdge
0x1800646fa  lea     rdx, [rbp+rcDst]; qrc
0x1800646fe  mov     eax, ecx
0x180064700  mov     r9d, 4; grfFlags
0x180064706  add     eax, [rbp+rcDst.right]
0x180064709  lea     r8d, [r9+2]; edge
0x18006470d  lea     eax, [rax+rcx*2]
0x180064710  mov     rcx, r12; hdc
0x180064713  mov     [rbp+rcDst.right], eax
0x180064716  call    cs:__imp_DrawEdge
0x18006471c  mov     rcx, [rbp+var_18]
0x180064720  xor     rcx, rsp; StackCookie
0x180064723  call    __security_check_cookie
0x180064728  add     rsp, 58h
0x18006472c  pop     r15
0x18006472e  pop     r14
0x180064730  pop     r13
0x180064732  pop     r12
0x180064734  pop     rdi
0x180064735  pop     rsi
0x180064736  pop     rbx
0x180064737  pop     rbp
0x180064738  retn
```

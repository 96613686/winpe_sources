# ListView_SetEditSize

- ea: `0x180076674`
- end: `0x1800767e5`
- name: `ListView_SetEditSize`
- size: `369`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180054bc0`
- `0x1800753a8`
- `0x180075888`

## callees

- `0x1800115f0`
- `0x180052cf8`
- `0x18005a314`
- `0x1800733e0`
- `0x180076674`
- `0x180076c68`

## import_xrefs

- `USER32!CopyRect` at `0x18007678e`
- `USER32!CopyRect` at `0x18007678e`
- `USER32!InvalidateRect` at `0x1800767b2`
- `USER32!InvalidateRect` at `0x1800767b2`
- `USER32!InflateRect` at `0x180076711`
- `USER32!InflateRect` at `0x180076711`
- `USER32!UpdateWindow` at `0x1800767bb`
- `USER32!UpdateWindow` at `0x1800767bb`
- `USER32!EqualRect` at `0x18007677c`
- `USER32!EqualRect` at `0x18007677c`

## pseudocode

```c
int __fastcall ListView_SetEditSize(__int64 a1)
{
  int v1; // edx
  int v3; // r8d
  int v4; // edx
  int result; // eax
  int *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  struct tagRECT *v9; // rdi
  struct tagRECT rc; // [rsp+30h] [rbp-28h] BYREF

  v1 = *(_DWORD *)(a1 + 336);
  rc = 0;
  if ( v1 < 0 || v1 >= *(_DWORD *)(a1 + 512) )
    return ListView_DismissEdit(a1);
  ListView_GetRects(a1, v1, 0, (int)&rc, 0, 0);
  v3 = -g_cyBorder;
  if ( (*(_BYTE *)(a1 + 16) & 3) != 0 )
  {
    v3 -= (rc.bottom - *(_DWORD *)(a1 + 128) - rc.top) / 2;
    v4 = g_cxLabelMargin + g_cxBorder;
  }
  else
  {
    v4 = g_cxLabelMargin;
  }
  InflateRect(&rc, -v4, v3);
  result = SetEditInPlaceSize(*(HWND *)(a1 + 328), &rc, *(HGDIOBJ *)(a1 + 88));
  if ( (*(_DWORD *)(a1 + 76) & 0x200) != 0 )
  {
    v6 = *(int **)(a1 + 64);
    if ( v6 && (v7 = *(int *)(a1 + 336), v7 >= 0) && v7 < *v6 )
      v8 = *(_QWORD *)(*((_QWORD *)v6 + 1) + 8 * v7);
    else
      v8 = 0;
    v9 = (struct tagRECT *)(v8 + 56);
    result = EqualRect((const RECT *)(v8 + 56), &rc);
    if ( !result )
    {
      CopyRect(v9, &rc);
      ListView_RecalcRegion(a1, 1);
      InvalidateRect(*(HWND *)(a1 + 328), 0, 1);
      return UpdateWindow(*(HWND *)a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180076674  mov     r11, rsp
0x180076677  mov     [r11+10h], rbx
0x18007667b  push    rdi
0x18007667c  sub     rsp, 50h
0x180076680  mov     rax, cs:__security_cookie
0x180076687  xor     rax, rsp
0x18007668a  mov     [rsp+58h+var_18], rax
0x18007668f  mov     edx, [rcx+150h]; int
0x180076695  xorps   xmm0, xmm0
0x180076698  mov     rbx, rcx
0x18007669b  movups  xmmword ptr [rsp+58h+rc.left], xmm0
0x1800766a0  test    edx, edx
0x1800766a2  js      loc_1800767C3
0x1800766a8  cmp     edx, [rcx+200h]
0x1800766ae  jge     loc_1800767C3
0x1800766b4  mov     qword ptr [r11-30h], 0
0x1800766bc  lea     r9, [r11-28h]; int
0x1800766c0  xor     r8d, r8d; int
0x1800766c3  mov     qword ptr [r11-38h], 0
0x1800766cb  call    ListView_GetRects
0x1800766d0  mov     r8d, cs:g_cyBorder
0x1800766d7  lea     rcx, [rsp+58h+rc]; lprc
0x1800766dc  neg     r8d
0x1800766df  test    byte ptr [rbx+10h], 3
0x1800766e3  jnz     short loc_1800766ED
0x1800766e5  mov     edx, cs:g_cxLabelMargin
0x1800766eb  jmp     short loc_18007670F
0x1800766ed  mov     eax, [rsp+58h+rc.bottom]
0x1800766f1  sub     eax, [rbx+80h]
0x1800766f7  sub     eax, [rsp+58h+rc.top]
0x1800766fb  cdq
0x1800766fc  sub     eax, edx
0x1800766fe  mov     edx, cs:g_cxBorder
0x180076704  sar     eax, 1
0x180076706  sub     r8d, eax; dy
0x180076709  add     edx, cs:g_cxLabelMargin
0x18007670f  neg     edx; dx
0x180076711  call    cs:__imp_InflateRect
0x180076717  test    byte ptr [rbx+10h], 83h
0x18007671b  lea     rdx, [rsp+58h+rc]; lprcDst
0x180076720  mov     r8, [rbx+58h]; h
0x180076724  mov     r9d, 0
0x18007672a  mov     rcx, [rbx+148h]; hWnd
0x180076731  setz    r9b
0x180076735  call    SetEditInPlaceSize
0x18007673a  test    dword ptr [rbx+4Ch], 200h
0x180076741  jz      loc_1800767CD
0x180076747  mov     rcx, [rbx+40h]
0x18007674b  test    rcx, rcx
0x18007674e  jz      short loc_18007676E
0x180076750  movsxd  rdx, dword ptr [rbx+150h]
0x180076757  test    rdx, rdx
0x18007675a  js      short loc_18007676E
0x18007675c  movsxd  rax, dword ptr [rcx]
0x18007675f  cmp     rdx, rax
0x180076762  jge     short loc_18007676E
0x180076764  mov     rax, [rcx+8]
0x180076768  mov     rcx, [rax+rdx*8]
0x18007676c  jmp     short loc_180076770
0x18007676e  xor     ecx, ecx
0x180076770  lea     rdi, [rcx+38h]
0x180076774  mov     rcx, rdi; lprc1
0x180076777  lea     rdx, [rsp+58h+rc]; lprc2
0x18007677c  call    cs:__imp_EqualRect
0x180076782  test    eax, eax
0x180076784  jnz     short loc_1800767CD
0x180076786  lea     rdx, [rsp+58h+rc]; lprcSrc
0x18007678b  mov     rcx, rdi; lprcDst
0x18007678e  call    cs:__imp_CopyRect
0x180076794  mov     edi, 1
0x180076799  mov     rcx, rbx; int
0x18007679c  mov     r8d, edi
0x18007679f  mov     edx, edi
0x1800767a1  call    ListView_RecalcRegion
0x1800767a6  mov     rcx, [rbx+148h]; hWnd
0x1800767ad  mov     r8d, edi; bErase
0x1800767b0  xor     edx, edx; lpRect
0x1800767b2  call    cs:__imp_InvalidateRect
0x1800767b8  mov     rcx, [rbx]; hWnd
0x1800767bb  call    cs:__imp_UpdateWindow
0x1800767c1  jmp     short loc_1800767CD
0x1800767c3  mov     edx, 1
0x1800767c8  call    ListView_DismissEdit
0x1800767cd  mov     rcx, [rsp+58h+var_18]
0x1800767d2  xor     rcx, rsp; StackCookie
0x1800767d5  call    __security_check_cookie
0x1800767da  mov     rbx, [rsp+58h+arg_8]
0x1800767df  add     rsp, 50h
0x1800767e3  pop     rdi
0x1800767e4  retn
```

# Tab_DrawItemFrame(TC *,HDC__ *,uint,TABITEM const *,int)

- ea: `0x1800f1c5c`
- end: `0x1800f1ee2`
- name: `?Tab_DrawItemFrame@@YAXPEAUTC@@PEAUHDC__@@IPEBUTABITEM@@H@Z`
- size: `646`
- prototype: `void __usercall(struct TC *@<rcx>, HDC hdc@<rdx>, unsigned int@<r8d>, const struct TABITEM *@<r9>, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180068690`

## callees

- `0x1800670f8`
- `0x180069708`
- `0x180069798`
- `0x1800f1c5c`
- `0x1800ff5dc`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800f1d7b`
- `GDI32!DeleteObject` at `0x1800f1e0a`
- `GDI32!DeleteObject` at `0x1800f1d7b`
- `GDI32!DeleteObject` at `0x1800f1e0a`
- `GDI32!SelectObject` at `0x1800f1d1d`
- `GDI32!SelectObject` at `0x1800f1d72`
- `GDI32!SelectObject` at `0x1800f1dac`
- `GDI32!SelectObject` at `0x1800f1e01`
- `GDI32!SelectObject` at `0x1800f1d1d`
- `GDI32!SelectObject` at `0x1800f1d72`
- `GDI32!SelectObject` at `0x1800f1dac`
- `GDI32!SelectObject` at `0x1800f1e01`
- `GDI32!MoveToEx` at `0x1800f1d33`
- `GDI32!MoveToEx` at `0x1800f1d56`
- `GDI32!MoveToEx` at `0x1800f1dc2`
- `GDI32!MoveToEx` at `0x1800f1de5`
- `GDI32!MoveToEx` at `0x1800f1d33`
- `GDI32!MoveToEx` at `0x1800f1d56`
- `GDI32!MoveToEx` at `0x1800f1dc2`
- `GDI32!MoveToEx` at `0x1800f1de5`
- `GDI32!CreatePen` at `0x1800f1d0e`
- `GDI32!CreatePen` at `0x1800f1d9d`
- `GDI32!CreatePen` at `0x1800f1d0e`
- `GDI32!CreatePen` at `0x1800f1d9d`
- `GDI32!LineTo` at `0x1800f1d43`
- `GDI32!LineTo` at `0x1800f1d66`
- `GDI32!LineTo` at `0x1800f1dd2`
- `GDI32!LineTo` at `0x1800f1df5`
- `GDI32!LineTo` at `0x1800f1d43`
- `GDI32!LineTo` at `0x1800f1d66`
- `GDI32!LineTo` at `0x1800f1dd2`
- `GDI32!LineTo` at `0x1800f1df5`
- `USER32!CopyRect` at `0x1800f1ce6`
- `USER32!CopyRect` at `0x1800f1e94`
- `USER32!CopyRect` at `0x1800f1ce6`
- `USER32!CopyRect` at `0x1800f1e94`
- `USER32!GetSysColor` at `0x1800f1cf5`
- `USER32!GetSysColor` at `0x1800f1d84`
- `USER32!GetSysColor` at `0x1800f1cf5`
- `USER32!GetSysColor` at `0x1800f1d84`
- `USER32!DrawEdge` at `0x1800f1ebf`
- `USER32!DrawEdge` at `0x1800f1ebf`

## pseudocode

```c
void __fastcall Tab_DrawItemFrame(struct TC *a1, HDC hdc, unsigned int a3, const struct tagRECT *a4, int a5)
{
  int v5; // eax
  int v6; // ebx
  unsigned int v10; // r15d
  COLORREF SysColor; // ebx
  int ScaledEdgeHeight; // eax
  HPEN Pen; // rdi
  HGDIOBJ v14; // rbx
  int ScaledEdgeWidth; // eax
  HPEN v16; // rdi
  HGDIOBJ v17; // rbx
  bool v18; // zf
  int v19; // eax
  struct tagRECT rcDst; // [rsp+38h] [rbp-20h] BYREF

  v5 = *((_DWORD *)a1 + 4);
  v6 = 0;
  if ( (v5 & 0x100) == 0 )
  {
    v10 = 4103;
    if ( (v5 & 1) != 0 && a4[2].right > *((_DWORD *)a1 + 40) )
    {
      v6 = 1;
      v10 = 4109;
    }
    goto LABEL_15;
  }
  if ( (v5 & 8) == 0 )
  {
    v10 = 4111;
    goto LABEL_15;
  }
  if ( a3 == 10 || a3 == 4 )
  {
LABEL_8:
    v10 = 15;
LABEL_15:
    Tab_DrawEdge(hdc, a4, a3, v10, a1);
    goto LABEL_16;
  }
  if ( (v5 & 0x40) != 0 && a5 == *((_DWORD *)a1 + 56) )
  {
    a3 = 4;
    goto LABEL_8;
  }
  rcDst = 0;
  if ( !*((_QWORD *)a1 + 29) )
  {
    CopyRect(&rcDst, a4);
    SysColor = GetSysColor(15);
    ScaledEdgeHeight = DPISCALEINFO::GetScaledEdgeHeight((struct TC *)((char *)a1 + 52));
    Pen = CreatePen(0, 2 * ScaledEdgeHeight, SysColor);
    v14 = SelectObject(hdc, Pen);
    MoveToEx(hdc, rcDst.left, rcDst.top, 0);
    LineTo(hdc, rcDst.right, rcDst.top);
    MoveToEx(hdc, rcDst.left, rcDst.bottom, 0);
    LineTo(hdc, rcDst.right, rcDst.bottom);
    SelectObject(hdc, v14);
    DeleteObject(Pen);
    LODWORD(v14) = GetSysColor(15);
    ScaledEdgeWidth = DPISCALEINFO::GetScaledEdgeWidth((struct TC *)((char *)a1 + 52));
    v16 = CreatePen(0, 2 * ScaledEdgeWidth, (COLORREF)v14);
    v17 = SelectObject(hdc, v16);
    MoveToEx(hdc, rcDst.left, rcDst.top, 0);
    LineTo(hdc, rcDst.left, rcDst.bottom);
    MoveToEx(hdc, rcDst.right, rcDst.top, 0);
    LineTo(hdc, rcDst.right, rcDst.bottom);
    SelectObject(hdc, v17);
    DeleteObject(v16);
    v6 = 0;
  }
LABEL_16:
  if ( (*((_DWORD *)a1 + 4) & 0x100) != 0 )
  {
    if ( (*((_BYTE *)a1 + 16) & 8) != 0 && (*((_BYTE *)a1 + 88) & 1) != 0 )
    {
      v18 = *((_QWORD *)a1 + 29) == 0;
      rcDst = 0;
      if ( v18 )
      {
        CopyRect(&rcDst, a4);
        v19 = DPISCALEINFO::GetScaledEdgeWidth((struct TC *)((char *)a1 + 52));
        rcDst.right += v19 + 2 * v19;
        DrawEdge(hdc, &rcDst, 6u, 4u);
      }
    }
  }
  else
  {
    Tab_DoCorners(hdc, a4, a1, v6);
  }
}

```

## disassembly

```asm
0x1800f1c5c  push    rbp
0x1800f1c5e  push    rbx
0x1800f1c5f  push    rsi
0x1800f1c60  push    rdi
0x1800f1c61  push    r12
0x1800f1c63  push    r13
0x1800f1c65  push    r14
0x1800f1c67  push    r15
0x1800f1c69  mov     rbp, rsp
0x1800f1c6c  sub     rsp, 58h
0x1800f1c70  mov     rax, cs:__security_cookie
0x1800f1c77  xor     rax, rsp
0x1800f1c7a  mov     [rbp+var_10], rax
0x1800f1c7e  mov     eax, [rcx+10h]
0x1800f1c81  xor     ebx, ebx
0x1800f1c83  mov     [rbp+var_28], ebx
0x1800f1c86  mov     r12, r9
0x1800f1c89  mov     r13, rdx
0x1800f1c8c  mov     r14, rcx
0x1800f1c8f  bt      eax, 8
0x1800f1c93  jnb     loc_1800F1E1D
0x1800f1c99  test    al, 8
0x1800f1c9b  jz      loc_1800F1E15
0x1800f1ca1  cmp     r8d, 0Ah
0x1800f1ca5  jz      short loc_1800F1CC0
0x1800f1ca7  cmp     r8d, 4
0x1800f1cab  jz      short loc_1800F1CC0
0x1800f1cad  test    al, 40h
0x1800f1caf  jz      short loc_1800F1CCB
0x1800f1cb1  mov     eax, [rcx+0E0h]
0x1800f1cb7  cmp     [rbp+arg_20], eax
0x1800f1cba  jnz     short loc_1800F1CCB
0x1800f1cbc  lea     r8d, [rbx+4]
0x1800f1cc0  mov     r15d, 0Fh
0x1800f1cc6  jmp     loc_1800F1E3E
0x1800f1ccb  xorps   xmm0, xmm0
0x1800f1cce  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x1800f1cd2  cmp     [rcx+0E8h], rbx
0x1800f1cd9  jnz     loc_1800F1E51
0x1800f1cdf  mov     rdx, r12; lprcSrc
0x1800f1ce2  lea     rcx, [rbp+rcDst]; lprcDst
0x1800f1ce6  call    cs:__imp_CopyRect
0x1800f1cec  mov     r15d, 0Fh
0x1800f1cf2  mov     ecx, r15d; nIndex
0x1800f1cf5  call    cs:__imp_GetSysColor
0x1800f1cfb  lea     rcx, [r14+34h]; this
0x1800f1cff  mov     ebx, eax
0x1800f1d01  call    ?GetScaledEdgeHeight@DPISCALEINFO@@QEBAHXZ; DPISCALEINFO::GetScaledEdgeHeight(void)
0x1800f1d06  mov     r8d, ebx; color
0x1800f1d09  xor     ecx, ecx; iStyle
0x1800f1d0b  lea     edx, [rax+rax]; cWidth
0x1800f1d0e  call    cs:__imp_CreatePen
0x1800f1d14  mov     rdx, rax; h
0x1800f1d17  mov     rcx, r13; hdc
0x1800f1d1a  mov     rdi, rax
0x1800f1d1d  call    cs:__imp_SelectObject
0x1800f1d23  mov     r8d, [rbp+rcDst.top]; y
0x1800f1d27  xor     r9d, r9d; lppt
0x1800f1d2a  mov     edx, [rbp+rcDst.left]; x
0x1800f1d2d  mov     rcx, r13; hdc
0x1800f1d30  mov     rbx, rax
0x1800f1d33  call    cs:__imp_MoveToEx
0x1800f1d39  mov     r8d, [rbp+rcDst.top]; y
0x1800f1d3d  mov     rcx, r13; hdc
0x1800f1d40  mov     edx, [rbp+rcDst.right]; x
0x1800f1d43  call    cs:__imp_LineTo
0x1800f1d49  mov     r8d, [rbp+rcDst.bottom]; y
0x1800f1d4d  xor     r9d, r9d; lppt
0x1800f1d50  mov     edx, [rbp+rcDst.left]; x
0x1800f1d53  mov     rcx, r13; hdc
0x1800f1d56  call    cs:__imp_MoveToEx
0x1800f1d5c  mov     r8d, [rbp+rcDst.bottom]; y
0x1800f1d60  mov     rcx, r13; hdc
0x1800f1d63  mov     edx, [rbp+rcDst.right]; x
0x1800f1d66  call    cs:__imp_LineTo
0x1800f1d6c  mov     rdx, rbx; h
0x1800f1d6f  mov     rcx, r13; hdc
0x1800f1d72  call    cs:__imp_SelectObject
0x1800f1d78  mov     rcx, rdi; ho
0x1800f1d7b  call    cs:__imp_DeleteObject
0x1800f1d81  mov     ecx, r15d; nIndex
0x1800f1d84  call    cs:__imp_GetSysColor
0x1800f1d8a  lea     rcx, [r14+34h]; this
0x1800f1d8e  mov     ebx, eax
0x1800f1d90  call    ?GetScaledEdgeWidth@DPISCALEINFO@@QEBAHXZ; DPISCALEINFO::GetScaledEdgeWidth(void)
0x1800f1d95  mov     r8d, ebx; color
0x1800f1d98  xor     ecx, ecx; iStyle
0x1800f1d9a  lea     edx, [rax+rax]; cWidth
0x1800f1d9d  call    cs:__imp_CreatePen
0x1800f1da3  mov     rdx, rax; h
0x1800f1da6  mov     rcx, r13; hdc
0x1800f1da9  mov     rdi, rax
0x1800f1dac  call    cs:__imp_SelectObject
0x1800f1db2  mov     r8d, [rbp+rcDst.top]; y
0x1800f1db6  xor     r9d, r9d; lppt
0x1800f1db9  mov     edx, [rbp+rcDst.left]; x
0x1800f1dbc  mov     rcx, r13; hdc
0x1800f1dbf  mov     rbx, rax
0x1800f1dc2  call    cs:__imp_MoveToEx
0x1800f1dc8  mov     r8d, [rbp+rcDst.bottom]; y
0x1800f1dcc  mov     rcx, r13; hdc
0x1800f1dcf  mov     edx, [rbp+rcDst.left]; x
0x1800f1dd2  call    cs:__imp_LineTo
0x1800f1dd8  mov     r8d, [rbp+rcDst.top]; y
0x1800f1ddc  xor     r9d, r9d; lppt
0x1800f1ddf  mov     edx, [rbp+rcDst.right]; x
0x1800f1de2  mov     rcx, r13; hdc
0x1800f1de5  call    cs:__imp_MoveToEx
0x1800f1deb  mov     r8d, [rbp+rcDst.bottom]; y
0x1800f1def  mov     rcx, r13; hdc
0x1800f1df2  mov     edx, [rbp+rcDst.right]; x
0x1800f1df5  call    cs:__imp_LineTo
0x1800f1dfb  mov     rdx, rbx; h
0x1800f1dfe  mov     rcx, r13; hdc
0x1800f1e01  call    cs:__imp_SelectObject
0x1800f1e07  mov     rcx, rdi; ho
0x1800f1e0a  call    cs:__imp_DeleteObject
0x1800f1e10  mov     ebx, [rbp+var_28]
0x1800f1e13  jmp     short loc_1800F1E51
0x1800f1e15  mov     r15d, 100Fh
0x1800f1e1b  jmp     short loc_1800F1E3E
0x1800f1e1d  mov     r15d, 1007h
0x1800f1e23  test    al, 1
0x1800f1e25  jz      short loc_1800F1E3E
0x1800f1e27  mov     eax, [rcx+0A0h]
0x1800f1e2d  cmp     [r9+28h], eax
0x1800f1e31  jle     short loc_1800F1E3E
0x1800f1e33  mov     ebx, 1
0x1800f1e38  mov     r15d, 100Dh
0x1800f1e3e  mov     r9d, r15d; unsigned int
0x1800f1e41  mov     [rsp+58h+var_38], r14; struct TC *
0x1800f1e46  mov     rdx, r12; struct tagRECT *
0x1800f1e49  mov     rcx, r13; hdc
0x1800f1e4c  call    ?Tab_DrawEdge@@YAXPEAUHDC__@@PEBUtagRECT@@IIPEAUTC@@@Z; Tab_DrawEdge(HDC__ *,tagRECT const *,uint,uint,TC *)
0x1800f1e51  test    dword ptr [r14+10h], 100h
0x1800f1e59  jnz     short loc_1800F1E6E
0x1800f1e5b  mov     r9d, ebx; int
0x1800f1e5e  mov     r8, r14; struct TC *
0x1800f1e61  mov     rdx, r12; struct tagRECT *
0x1800f1e64  mov     rcx, r13; hdc
0x1800f1e67  call    ?Tab_DoCorners@@YAXPEAUHDC__@@PEBUtagRECT@@PEAUTC@@H@Z; Tab_DoCorners(HDC__ *,tagRECT const *,TC *,int)
0x1800f1e6c  jmp     short loc_1800F1EC5
0x1800f1e6e  test    byte ptr [r14+10h], 8
0x1800f1e73  jz      short loc_1800F1EC5
0x1800f1e75  test    byte ptr [r14+58h], 1
0x1800f1e7a  jz      short loc_1800F1EC5
0x1800f1e7c  cmp     qword ptr [r14+0E8h], 0
0x1800f1e84  xorps   xmm0, xmm0
0x1800f1e87  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x1800f1e8b  jnz     short loc_1800F1EC5
0x1800f1e8d  mov     rdx, r12; lprcSrc
0x1800f1e90  lea     rcx, [rbp+rcDst]; lprcDst
0x1800f1e94  call    cs:__imp_CopyRect
0x1800f1e9a  lea     rcx, [r14+34h]; this
0x1800f1e9e  call    ?GetScaledEdgeWidth@DPISCALEINFO@@QEBAHXZ; DPISCALEINFO::GetScaledEdgeWidth(void)
0x1800f1ea3  mov     ecx, eax
0x1800f1ea5  lea     rdx, [rbp+rcDst]; qrc
0x1800f1ea9  add     ecx, [rbp+rcDst.right]
0x1800f1eac  mov     r9d, 4; grfFlags
0x1800f1eb2  lea     eax, [rcx+rax*2]
0x1800f1eb5  mov     rcx, r13; hdc
0x1800f1eb8  lea     r8d, [r9+2]; edge
0x1800f1ebc  mov     [rbp+rcDst.right], eax
0x1800f1ebf  call    cs:__imp_DrawEdge
0x1800f1ec5  mov     rcx, [rbp+var_10]
0x1800f1ec9  xor     rcx, rsp; StackCookie
0x1800f1ecc  call    __security_check_cookie
0x1800f1ed1  add     rsp, 58h
0x1800f1ed5  pop     r15
0x1800f1ed7  pop     r14
0x1800f1ed9  pop     r13
0x1800f1edb  pop     r12
0x1800f1edd  pop     rdi
0x1800f1ede  pop     rsi
0x1800f1edf  pop     rbx
0x1800f1ee0  pop     rbp
0x1800f1ee1  retn
```

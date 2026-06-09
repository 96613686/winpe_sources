# RBEraseBkgnd

- ea: `0x18003b7f0`
- end: `0x18003bb70`
- name: `RBEraseBkgnd`
- size: `896`
- prototype: `__int64 __fastcall(int, HDC hdc)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003eff0`

## callees

- `0x1800115f0`
- `0x180017cac`
- `0x180036e24`
- `0x18003b7f0`
- `0x18003d0dc`
- `0x18003eda4`
- `0x180042570`
- `0x18008ea60`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18003ba2c`
- `GDI32!CreateCompatibleDC` at `0x18003ba2c`
- `GDI32!SelectObject` at `0x18003ba57`
- `GDI32!SelectObject` at `0x18003ba57`
- `GDI32!DeleteDC` at `0x18003bb10`
- `GDI32!DeleteDC` at `0x18003bb10`
- `USER32!GetClientRect` at `0x18003b890`
- `USER32!GetClientRect` at `0x18003b890`
- `USER32!SetRect` at `0x18003b905`
- `USER32!SetRect` at `0x18003b905`

## pseudocode

```c
__int64 __fastcall RBEraseBkgnd(__int64 a1, HDC hdc)
{
  int v2; // r12d
  __int64 v5; // rdi
  int v6; // eax
  int v7; // r15d
  int v8; // r12d
  HDC CompatibleDC; // r14
  COLORREF v10; // r8d
  unsigned int v11; // r13d
  int v12; // r8d
  int v13; // edx
  int v14; // ecx
  int v15; // r9d
  int v16; // edx
  __int16 v17; // r9
  char v18; // r15
  COLORREF v19; // r8d
  COLORREF v20; // eax
  __int64 yBottom; // [rsp+20h] [rbp-79h]
  int v23; // [rsp+40h] [rbp-59h]
  _QWORD v24[10]; // [rsp+50h] [rbp-49h] BYREF
  struct tagRECT Rect; // [rsp+A0h] [rbp+7h] BYREF

  v2 = *(_DWORD *)(a1 + 16);
  memset(v24, 0, sizeof(v24));
  v5 = *(_QWORD *)(a1 + 152);
  v24[4] = hdc;
  LODWORD(v24[8]) = 0;
  v24[9] = 0;
  Rect = 0;
  v6 = CICustomDrawNotify(a1, 3, v24);
  *(_DWORD *)(a1 + 20) = v6;
  if ( (v6 & 4) == 0 )
  {
    v7 = *(_DWORD *)(a1 + 16) & 0x400;
    v23 = v7;
    v8 = v2 & 0x80;
    CompatibleDC = 0;
    GetClientRect(*(HWND *)a1, &Rect);
    v10 = *(_DWORD *)(a1 + 160);
    if ( v10 == -16777216 )
      v10 = g_clrBtnFace;
    if ( v10 != -1 )
      FillRectClr(hdc, &Rect, v10);
    v11 = 0;
    if ( *(_DWORD *)(a1 + 88) )
    {
      while ( (*(_BYTE *)v5 & 8) != 0 )
      {
LABEL_39:
        ++v11;
        v5 += 144;
        if ( v11 >= *(_DWORD *)(a1 + 88) )
        {
          if ( CompatibleDC )
            DeleteDC(CompatibleDC);
          goto LABEL_42;
        }
      }
      if ( v8 )
      {
        v12 = *(_DWORD *)(v5 + 64);
        v13 = *(_DWORD *)(v5 + 68);
        v14 = *(_DWORD *)(v5 + 72);
        v15 = *(_DWORD *)(v5 + 76);
      }
      else
      {
        v12 = *(_DWORD *)(v5 + 68);
        v13 = *(_DWORD *)(v5 + 64);
        v14 = *(_DWORD *)(v5 + 76);
        v15 = *(_DWORD *)(v5 + 72);
      }
      SetRect((LPRECT)&v24[5], v13, v12, v13 + v15, v12 + v14);
      if ( v7 )
      {
        yBottom = a1 + 176;
        if ( *(_DWORD *)(v5 + 64) )
        {
          if ( v8 )
          {
            LODWORD(v24[6]) += g_cxEdge / 2;
            HIDWORD(v24[5]) -= g_cyEdge;
            CCDrawEdge(hdc, (LPRECT)&v24[5], 6, 2, yBottom);
            LODWORD(v24[6]) += g_cxEdge / -2;
            HIDWORD(v24[5]) += g_cyEdge;
          }
          else
          {
            HIDWORD(v24[6]) += g_cyEdge / 2;
            LODWORD(v24[5]) -= g_cxEdge;
            CCDrawEdge(hdc, (LPRECT)&v24[5], 6, 1, yBottom);
            HIDWORD(v24[6]) += g_cyEdge / -2;
            LODWORD(v24[5]) += g_cxEdge;
          }
        }
        else
        {
          v16 = *(_DWORD *)(v5 + 76) + *(_DWORD *)(v5 + 68);
          if ( v8 )
          {
            v17 = 4;
            Rect.right = v16 + g_cxEdge;
          }
          else
          {
            v17 = 8;
            Rect.bottom = v16 + g_cyEdge;
          }
          CCDrawEdge(hdc, &Rect, 6, v17, yBottom);
        }
      }
      v24[7] = *(unsigned int *)(v5 + 92);
      LODWORD(v24[8]) = 0;
      v18 = CICustomDrawNotify(a1, 65539, v24);
      if ( (v18 & 4) == 0 )
      {
        if ( *(_QWORD *)(v5 + 56) )
        {
          if ( !CompatibleDC )
          {
            CompatibleDC = CreateCompatibleDC(hdc);
            if ( !CompatibleDC )
            {
LABEL_38:
              v7 = v23;
              goto LABEL_39;
            }
            RBRealize(a1, hdc, 1, 0);
          }
          SelectObject(CompatibleDC, *(HGDIOBJ *)(v5 + 56));
          RBTileBlt(
            a1,
            v5,
            v24[5],
            SHIDWORD(v24[5]),
            LODWORD(v24[6]) - LODWORD(v24[5]),
            HIDWORD(v24[6]) - HIDWORD(v24[5]),
            hdc,
            CompatibleDC);
        }
        else
        {
          v19 = *(_DWORD *)(v5 + 8);
          if ( v19 == -16777216 )
          {
            v19 = g_clrBtnFace;
          }
          else if ( v19 == -1 )
          {
            v19 = *(_DWORD *)(a1 + 160);
            if ( v19 == -16777216 )
              v19 = g_clrBtnFace;
          }
          v20 = *(_DWORD *)(a1 + 160);
          if ( v20 == -16777216 )
            v20 = g_clrBtnFace;
          if ( v19 != v20 )
            FillRectClr(hdc, (RECT *)&v24[5], v19);
        }
      }
      if ( (v18 & 0x40) != 0 )
        CICustomDrawNotify(a1, 65540, v24);
      goto LABEL_38;
    }
  }
LABEL_42:
  if ( (*(_BYTE *)(a1 + 20) & 0x40) != 0 )
  {
    LODWORD(v24[8]) = 0;
    v24[7] = 0;
    v24[9] = 0;
    CICustomDrawNotify(a1, 4, v24);
  }
  return 1;
}

```

## disassembly

```asm
0x18003b7f0  mov     [rsp-8+arg_10], rbx
0x18003b7f5  push    rbp
0x18003b7f6  push    rsi
0x18003b7f7  push    rdi
0x18003b7f8  push    r12
0x18003b7fa  push    r13
0x18003b7fc  push    r14
0x18003b7fe  push    r15
0x18003b800  lea     rbp, [rsp-27h]
0x18003b805  sub     rsp, 0C0h
0x18003b80c  mov     rax, cs:__security_cookie
0x18003b813  xor     rax, rsp
0x18003b816  mov     [rbp+57h+var_40], rax
0x18003b81a  mov     r12d, [rcx+10h]
0x18003b81e  mov     rsi, rdx
0x18003b821  xor     edx, edx; Val
0x18003b823  mov     rbx, rcx
0x18003b826  lea     rcx, [rbp+57h+var_A0]; void *
0x18003b82a  lea     r8d, [rdx+50h]; Size
0x18003b82e  call    memset
0x18003b833  mov     rdi, [rbx+98h]
0x18003b83a  lea     r8, [rbp+57h+var_A0]
0x18003b83e  xorps   xmm0, xmm0
0x18003b841  mov     [rbp+57h+var_80], rsi
0x18003b845  mov     edx, 3
0x18003b84a  mov     [rbp+57h+var_60], 0
0x18003b851  mov     rcx, rbx
0x18003b854  mov     [rbp+57h+var_58], 0
0x18003b85c  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18003b860  call    CICustomDrawNotify
0x18003b865  mov     [rbx+14h], eax
0x18003b868  test    al, 4
0x18003b86a  jnz     loc_18003BB16
0x18003b870  mov     r15d, [rbx+10h]
0x18003b874  lea     rdx, [rbp+57h+Rect]; lpRect
0x18003b878  mov     rcx, [rbx]; hWnd
0x18003b87b  and     r15d, 400h
0x18003b882  mov     [rbp+57h+var_B0], r15d
0x18003b886  and     r12d, 80h
0x18003b88d  xor     r14d, r14d
0x18003b890  call    cs:__imp_GetClientRect
0x18003b896  mov     r8d, [rbx+0A0h]
0x18003b89d  cmp     r8d, 0FF000000h
0x18003b8a4  cmovz   r8d, cs:g_clrBtnFace; color
0x18003b8ac  cmp     r8d, 0FFFFFFFFh
0x18003b8b0  jz      short loc_18003B8BE
0x18003b8b2  lea     rdx, [rbp+57h+Rect]; lprect
0x18003b8b6  mov     rcx, rsi; hdc
0x18003b8b9  call    FillRectClr
0x18003b8be  xor     r13d, r13d
0x18003b8c1  cmp     [rbx+58h], r13d
0x18003b8c5  jbe     loc_18003BB16
0x18003b8cb  test    byte ptr [rdi], 8
0x18003b8ce  jnz     loc_18003BAF4
0x18003b8d4  test    r12d, r12d
0x18003b8d7  jz      short loc_18003B8E9
0x18003b8d9  mov     r8d, [rdi+40h]
0x18003b8dd  mov     edx, [rdi+44h]
0x18003b8e0  mov     ecx, [rdi+48h]
0x18003b8e3  mov     r9d, [rdi+4Ch]
0x18003b8e7  jmp     short loc_18003B8F7
0x18003b8e9  mov     r8d, [rdi+44h]; yTop
0x18003b8ed  mov     edx, [rdi+40h]; xLeft
0x18003b8f0  mov     ecx, [rdi+4Ch]
0x18003b8f3  mov     r9d, [rdi+48h]
0x18003b8f7  add     ecx, r8d
0x18003b8fa  add     r9d, edx; xRight
0x18003b8fd  mov     [rsp+0F0h+yBottom], ecx; yBottom
0x18003b901  lea     rcx, [rbp+57h+rc]; lprc
0x18003b905  call    cs:__imp_SetRect
0x18003b90b  test    r15d, r15d
0x18003b90e  jz      loc_18003B9F3
0x18003b914  cmp     dword ptr [rdi+40h], 0
0x18003b918  lea     r8, [rbx+0B0h]
0x18003b91f  mov     qword ptr [rsp+0F0h+yBottom], r8; __int64
0x18003b924  mov     r8d, 6
0x18003b92a  jz      loc_18003B9B8
0x18003b930  mov     rcx, rsi; hdc
0x18003b933  test    r12d, r12d
0x18003b936  jz      short loc_18003B977
0x18003b938  mov     eax, cs:g_cxEdge
0x18003b93e  lea     r9d, [r8-4]
0x18003b942  cdq
0x18003b943  sub     eax, edx
0x18003b945  lea     rdx, [rbp+57h+rc]; lprcDst
0x18003b949  sar     eax, 1
0x18003b94b  add     [rbp+57h+rc.right], eax
0x18003b94e  mov     eax, cs:g_cyEdge
0x18003b954  sub     [rbp+57h+rc.top], eax
0x18003b957  call    CCDrawEdge
0x18003b95c  mov     eax, cs:g_cxEdge
0x18003b962  cdq
0x18003b963  sub     eax, edx
0x18003b965  sar     eax, 1
0x18003b967  neg     eax
0x18003b969  add     [rbp+57h+rc.right], eax
0x18003b96c  mov     eax, cs:g_cyEdge
0x18003b972  add     [rbp+57h+rc.top], eax
0x18003b975  jmp     short loc_18003B9F3
0x18003b977  mov     eax, cs:g_cyEdge
0x18003b97d  mov     r9d, 1
0x18003b983  cdq
0x18003b984  sub     eax, edx
0x18003b986  lea     rdx, [rbp+57h+rc]; lprcDst
0x18003b98a  sar     eax, 1
0x18003b98c  add     [rbp+57h+rc.bottom], eax
0x18003b98f  mov     eax, cs:g_cxEdge
0x18003b995  sub     [rbp+57h+rc.left], eax
0x18003b998  call    CCDrawEdge
0x18003b99d  mov     eax, cs:g_cyEdge
0x18003b9a3  cdq
0x18003b9a4  sub     eax, edx
0x18003b9a6  sar     eax, 1
0x18003b9a8  neg     eax
0x18003b9aa  add     [rbp+57h+rc.bottom], eax
0x18003b9ad  mov     eax, cs:g_cxEdge
0x18003b9b3  add     [rbp+57h+rc.left], eax
0x18003b9b6  jmp     short loc_18003B9F3
0x18003b9b8  mov     edx, [rdi+44h]
0x18003b9bb  add     edx, [rdi+4Ch]
0x18003b9be  test    r12d, r12d
0x18003b9c1  jz      short loc_18003B9D6
0x18003b9c3  mov     ecx, cs:g_cxEdge
0x18003b9c9  mov     r9d, 4
0x18003b9cf  add     ecx, edx
0x18003b9d1  mov     [rbp+57h+Rect.right], ecx
0x18003b9d4  jmp     short loc_18003B9E7
0x18003b9d6  mov     ecx, cs:g_cyEdge
0x18003b9dc  mov     r9d, 8
0x18003b9e2  add     ecx, edx
0x18003b9e4  mov     [rbp+57h+Rect.bottom], ecx
0x18003b9e7  lea     rdx, [rbp+57h+Rect]; lprcDst
0x18003b9eb  mov     rcx, rsi; hdc
0x18003b9ee  call    CCDrawEdge
0x18003b9f3  mov     eax, [rdi+5Ch]
0x18003b9f6  lea     r8, [rbp+57h+var_A0]
0x18003b9fa  mov     edx, 10003h
0x18003b9ff  mov     [rbp+57h+var_68], rax
0x18003ba03  mov     rcx, rbx
0x18003ba06  mov     [rbp+57h+var_60], 0
0x18003ba0d  call    CICustomDrawNotify
0x18003ba12  mov     r15d, eax
0x18003ba15  test    al, 4
0x18003ba17  jnz     loc_18003BAD9
0x18003ba1d  cmp     qword ptr [rdi+38h], 0
0x18003ba22  jz      short loc_18003BA90
0x18003ba24  test    r14, r14
0x18003ba27  jnz     short loc_18003BA50
0x18003ba29  mov     rcx, rsi; hdc
0x18003ba2c  call    cs:__imp_CreateCompatibleDC
0x18003ba32  mov     r14, rax
0x18003ba35  test    rax, rax
0x18003ba38  jz      loc_18003BAF0
0x18003ba3e  xor     r9d, r9d
0x18003ba41  mov     rdx, rsi
0x18003ba44  mov     rcx, rbx
0x18003ba47  lea     r8d, [r9+1]
0x18003ba4b  call    RBRealize
0x18003ba50  mov     rdx, [rdi+38h]; h
0x18003ba54  mov     rcx, r14; hdc
0x18003ba57  call    cs:__imp_SelectObject
0x18003ba5d  mov     ecx, [rbp+57h+rc.bottom]
0x18003ba60  mov     rdx, rdi; int
0x18003ba63  mov     r9d, [rbp+57h+rc.top]; int
0x18003ba67  sub     ecx, r9d
0x18003ba6a  mov     eax, [rbp+57h+rc.right]
0x18003ba6d  mov     r8d, [rbp+57h+rc.left]; int
0x18003ba71  sub     eax, r8d
0x18003ba74  mov     [rsp+0F0h+var_B8], r14; HDC
0x18003ba79  mov     [rsp+0F0h+hdc], rsi; hdc
0x18003ba7e  mov     [rsp+0F0h+var_C8], ecx; int
0x18003ba82  mov     rcx, rbx; int
0x18003ba85  mov     [rsp+0F0h+yBottom], eax; int
0x18003ba89  call    RBTileBlt
0x18003ba8e  jmp     short loc_18003BAD9
0x18003ba90  mov     r8d, [rdi+8]
0x18003ba94  mov     edx, 0FF000000h
0x18003ba99  mov     ecx, cs:g_clrBtnFace
0x18003ba9f  cmp     r8d, edx
0x18003baa2  jz      short loc_18003BABA
0x18003baa4  cmp     r8d, 0FFFFFFFFh
0x18003baa8  jnz     short loc_18003BABD
0x18003baaa  mov     r8d, [rbx+0A0h]
0x18003bab1  cmp     r8d, edx
0x18003bab4  cmovz   r8d, ecx
0x18003bab8  jmp     short loc_18003BABD
0x18003baba  mov     r8d, ecx; color
0x18003babd  mov     eax, [rbx+0A0h]
0x18003bac3  cmp     eax, edx
0x18003bac5  cmovz   eax, ecx
0x18003bac8  cmp     r8d, eax
0x18003bacb  jz      short loc_18003BAD9
0x18003bacd  lea     rdx, [rbp+57h+rc]; lprect
0x18003bad1  mov     rcx, rsi; hdc
0x18003bad4  call    FillRectClr
0x18003bad9  test    r15b, 40h
0x18003badd  jz      short loc_18003BAF0
0x18003badf  lea     r8, [rbp+57h+var_A0]
0x18003bae3  mov     edx, 10004h
0x18003bae8  mov     rcx, rbx
0x18003baeb  call    CICustomDrawNotify
0x18003baf0  mov     r15d, [rbp+57h+var_B0]
0x18003baf4  inc     r13d
0x18003baf7  add     rdi, 90h
0x18003bafe  cmp     r13d, [rbx+58h]
0x18003bb02  jb      loc_18003B8CB
0x18003bb08  test    r14, r14
0x18003bb0b  jz      short loc_18003BB16
0x18003bb0d  mov     rcx, r14; hdc
0x18003bb10  call    cs:__imp_DeleteDC
0x18003bb16  test    byte ptr [rbx+14h], 40h
0x18003bb1a  jz      short loc_18003BB44
0x18003bb1c  lea     r8, [rbp+57h+var_A0]
0x18003bb20  mov     [rbp+57h+var_60], 0
0x18003bb27  mov     edx, 4
0x18003bb2c  mov     [rbp+57h+var_68], 0
0x18003bb34  mov     rcx, rbx
0x18003bb37  mov     [rbp+57h+var_58], 0
0x18003bb3f  call    CICustomDrawNotify
0x18003bb44  mov     eax, 1
0x18003bb49  mov     rcx, [rbp+57h+var_40]
0x18003bb4d  xor     rcx, rsp; StackCookie
0x18003bb50  call    __security_check_cookie
0x18003bb55  mov     rbx, [rsp+0F0h+arg_10]
0x18003bb5d  add     rsp, 0C0h
0x18003bb64  pop     r15
0x18003bb66  pop     r14
0x18003bb68  pop     r13
0x18003bb6a  pop     r12
0x18003bb6c  pop     rdi
0x18003bb6d  pop     rsi
0x18003bb6e  pop     rbp
0x18003bb6f  retn
```

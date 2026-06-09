# DrawCompositionLine

- ea: `0x1800728fc`
- end: `0x180072be6`
- name: `DrawCompositionLine`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180075a18`

## callees

- `0x180017a0c`
- `0x1800728fc`

## import_xrefs

- `GDI32!GetTextExtentPointW` at `0x180072b11`
- `GDI32!GetTextExtentPointW` at `0x180072b11`
- `GDI32!SelectObject` at `0x180072a6a`
- `GDI32!SelectObject` at `0x180072adf`
- `GDI32!SelectObject` at `0x180072b75`
- `GDI32!SelectObject` at `0x180072b96`
- `GDI32!SelectObject` at `0x180072a6a`
- `GDI32!SelectObject` at `0x180072adf`
- `GDI32!SelectObject` at `0x180072b75`
- `GDI32!SelectObject` at `0x180072b96`
- `GDI32!DeleteObject` at `0x180072b80`
- `GDI32!DeleteObject` at `0x180072b80`
- `GDI32!SetBkMode` at `0x180072af2`
- `GDI32!SetBkMode` at `0x180072b5f`
- `GDI32!SetBkMode` at `0x180072af2`
- `GDI32!SetBkMode` at `0x180072b5f`
- `GDI32!SetBkColor` at `0x180072a55`
- `GDI32!SetBkColor` at `0x180072bb0`
- `GDI32!SetBkColor` at `0x180072a55`
- `GDI32!SetBkColor` at `0x180072bb0`
- `GDI32!SetTextColor` at `0x180072a44`
- `GDI32!SetTextColor` at `0x180072ba3`
- `GDI32!SetTextColor` at `0x180072a44`
- `GDI32!SetTextColor` at `0x180072ba3`
- `GDI32!CreatePen` at `0x180072ac5`
- `GDI32!CreatePen` at `0x180072ac5`
- `GDI32!TextOutW` at `0x180072ab4`
- `GDI32!TextOutW` at `0x180072ab4`
- `GDI32!MoveToEx` at `0x180072b32`
- `GDI32!MoveToEx` at `0x180072b32`
- `GDI32!LineTo` at `0x180072b54`
- `GDI32!LineTo` at `0x180072b54`
- `KERNEL32!LocalFree` at `0x180072bb9`
- `KERNEL32!LocalFree` at `0x180072bb9`
- `KERNEL32!LocalAlloc` at `0x1800729c2`
- `KERNEL32!LocalAlloc` at `0x1800729c2`
- `USER32!SendMessageW` at `0x180072a8b`
- `USER32!SendMessageW` at `0x180072a8b`

## pseudocode

```c
SIZE_T __fastcall DrawCompositionLine(
        HWND a1,
        HDC a2,
        void *a3,
        __int64 a4,
        __int64 a5,
        unsigned int wParam,
        unsigned int a7,
        int a8)
{
  SIZE_T result; // rax
  unsigned int v9; // esi
  COLORREF v10; // r12d
  int v11; // r13d
  unsigned int v13; // r14d
  __int64 v14; // rax
  __int64 v15; // rbx
  unsigned int v16; // edi
  char v17; // cl
  unsigned int c; // edi
  size_t v19; // rcx
  unsigned __int64 v20; // kr00_8
  WCHAR *v21; // r15
  COLORREF v22; // eax
  HGDIOBJ v23; // rbx
  int v24; // eax
  HPEN Pen; // rax
  int v26; // eax
  int v27; // ebx
  COLORREF color; // [rsp+30h] [rbp-78h]
  int x; // [rsp+34h] [rbp-74h]
  struct tagSIZE sz; // [rsp+38h] [rbp-70h] BYREF
  COLORREF v31; // [rsp+40h] [rbp-68h]
  size_t cchDest; // [rsp+48h] [rbp-60h]
  HGDIOBJ v33; // [rsp+50h] [rbp-58h]
  HGDIOBJ v34; // [rsp+58h] [rbp-50h]
  HGDIOBJ ho; // [rsp+60h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+A8h] [rbp+0h] BYREF
  char wParama; // [rsp+D8h] [rbp+30h]
  int wParamb; // [rsp+D8h] [rbp+30h]

  result = (SIZE_T)&retaddr;
  v9 = wParam;
  v10 = 0;
  v11 = 0;
  color = 0;
  if ( wParam < a7 )
  {
    v13 = a7 - a8;
    while ( 1 )
    {
      v14 = v9 - a8;
      v15 = (unsigned int)v14;
      v16 = v9 - a8;
      v17 = *(_BYTE *)(v14 + a5);
      wParama = v17;
      if ( (unsigned int)v14 < v13 )
      {
        while ( v17 == *(_BYTE *)(v16 + a5) )
        {
          result = ++v16;
          if ( v16 >= v13 )
          {
            if ( v16 < (unsigned int)v15 )
              return result;
            break;
          }
        }
      }
      c = v16 - v15;
      result = c + 1;
      if ( (unsigned int)result < c )
        return result;
      v19 = (unsigned int)result;
      v20 = (unsigned int)result;
      result = 2LL * (unsigned int)result;
      v33 = 0;
      cchDest = v19;
      if ( is_mul_ok(v20, 2u) )
      {
        result = (SIZE_T)LocalAlloc(0x40u, result);
        v21 = (WCHAR *)result;
        if ( result )
          break;
      }
LABEL_26:
      v9 += c;
      if ( v9 >= a7 )
        return result;
    }
    StringCchCopyW((STRSAFE_LPWSTR)result, cchDest, (STRSAFE_LPCWSTR)(a4 + 2 * v15));
    if ( wParama )
    {
      if ( wParama == 1 )
      {
LABEL_14:
        v10 = g_clrHighlightText;
        v11 = 2;
        v22 = g_clrHighlight;
LABEL_18:
        color = v22;
        goto LABEL_19;
      }
      if ( wParama != 2 )
      {
        if ( wParama != 3 )
        {
LABEL_19:
          v31 = SetTextColor(a2, v10);
          LODWORD(cchDest) = SetBkColor(a2, color);
          v23 = SelectObject(a2, a3);
          v33 = v23;
          v24 = SendMessageW(a1, 0xD6u, v9, 0);
          wParamb = SHIWORD(v24);
          x = (__int16)v24;
          TextOutW(a2, (__int16)v24, SHIWORD(v24), v21, c);
          Pen = CreatePen(v11, 1, v10);
          ho = Pen;
          if ( Pen )
          {
            v34 = SelectObject(a2, Pen);
            v26 = SetBkMode(a2, 1);
            sz = 0;
            v27 = v26;
            GetTextExtentPointW(a2, v21, c, &sz);
            MoveToEx(a2, x, wParamb - 1 + sz.cy, 0);
            LineTo(a2, sz.cx + x, wParamb - 1 + sz.cy);
            SetBkMode(a2, v27);
            if ( v34 )
              SelectObject(a2, v34);
            DeleteObject(ho);
            v23 = v33;
          }
          if ( v23 )
            SelectObject(a2, v23);
          SetTextColor(a2, v31);
          SetBkColor(a2, cchDest);
          result = (SIZE_T)LocalFree(v21);
          goto LABEL_26;
        }
        goto LABEL_14;
      }
      v11 = 0;
    }
    else
    {
      v11 = 2;
    }
    v22 = g_clrWindow;
    v10 = g_clrWindowText;
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x1800728fc  mov     rax, rsp
0x1800728ff  mov     [rax+10h], rbx
0x180072903  mov     [rax+20h], r9
0x180072907  mov     [rax+18h], r8
0x18007290b  mov     [rax+8], rcx
0x18007290f  push    rbp
0x180072910  push    rsi
0x180072911  push    rdi
0x180072912  push    r12
0x180072914  push    r13
0x180072916  push    r14
0x180072918  push    r15
0x18007291a  sub     rsp, 70h
0x18007291e  mov     esi, dword ptr [rsp+0A8h+wParam]
0x180072925  xor     r12d, r12d
0x180072928  xor     r13d, r13d
0x18007292b  mov     [rsp+0A8h+color], r12d
0x180072930  mov     rbp, rdx
0x180072933  cmp     esi, [rsp+0A8h+arg_30]
0x18007293a  jnb     loc_180072BCE
0x180072940  mov     r14d, [rsp+0A8h+arg_30]
0x180072948  sub     r14d, [rsp+0A8h+arg_38]
0x180072950  mov     rdx, [rsp+0A8h+arg_20]
0x180072958  mov     eax, esi
0x18007295a  sub     eax, [rsp+0A8h+arg_38]
0x180072961  mov     ebx, eax
0x180072963  mov     edi, eax
0x180072965  mov     cl, [rax+rdx]
0x180072968  mov     byte ptr [rsp+0A8h+wParam], cl
0x18007296f  cmp     eax, r14d
0x180072972  jnb     short loc_18007298C
0x180072974  mov     eax, edi
0x180072976  cmp     cl, [rax+rdx]
0x180072979  jnz     short loc_18007298C
0x18007297b  inc     edi
0x18007297d  mov     eax, edi
0x18007297f  cmp     edi, r14d
0x180072982  jb      short loc_180072974
0x180072984  cmp     eax, ebx
0x180072986  jb      loc_180072BCE
0x18007298c  sub     edi, ebx
0x18007298e  lea     eax, [rdi+1]
0x180072991  cmp     eax, edi
0x180072993  jb      loc_180072BCE
0x180072999  mov     ecx, eax
0x18007299b  mov     eax, 2
0x1800729a0  mul     rcx
0x1800729a3  mov     [rsp+0A8h+var_58], 0
0x1800729ac  mov     [rsp+0A8h+cchDest], rcx
0x1800729b1  test    rdx, rdx
0x1800729b4  jnz     loc_180072BBF
0x1800729ba  mov     rdx, rax; uBytes
0x1800729bd  mov     ecx, 40h ; '@'; uFlags
0x1800729c2  call    cs:__imp_LocalAlloc
0x1800729c8  mov     r15, rax
0x1800729cb  test    rax, rax
0x1800729ce  jz      loc_180072BBF
0x1800729d4  mov     rax, [rsp+0A8h+arg_18]
0x1800729dc  mov     rcx, r15; pszDest
0x1800729df  mov     rdx, [rsp+0A8h+cchDest]; cchDest
0x1800729e4  lea     r8, [rax+rbx*2]; pszSrc
0x1800729e8  call    StringCchCopyW
0x1800729ed  movzx   r11d, byte ptr [rsp+0A8h+wParam]
0x1800729f6  test    r11d, r11d
0x1800729f9  jz      short loc_180072A27
0x1800729fb  sub     r11d, 1
0x1800729ff  jz      short loc_180072A0D
0x180072a01  sub     r11d, 1
0x180072a05  jz      short loc_180072A22
0x180072a07  cmp     r11d, 1
0x180072a0b  jnz     short loc_180072A3E
0x180072a0d  mov     r12d, cs:g_clrHighlightText
0x180072a14  mov     r13d, 2
0x180072a1a  mov     eax, cs:g_clrHighlight
0x180072a20  jmp     short loc_180072A3A
0x180072a22  xor     r13d, r13d
0x180072a25  jmp     short loc_180072A2D
0x180072a27  mov     r13d, 2
0x180072a2d  mov     eax, cs:g_clrWindow
0x180072a33  mov     r12d, cs:g_clrWindowText
0x180072a3a  mov     [rsp+0A8h+color], eax
0x180072a3e  mov     edx, r12d; color
0x180072a41  mov     rcx, rbp; hdc
0x180072a44  call    cs:__imp_SetTextColor
0x180072a4a  mov     edx, [rsp+0A8h+color]; color
0x180072a4e  mov     rcx, rbp; hdc
0x180072a51  mov     [rsp+0A8h+var_68], eax
0x180072a55  call    cs:__imp_SetBkColor
0x180072a5b  mov     rdx, [rsp+0A8h+h]; h
0x180072a63  mov     rcx, rbp; hdc
0x180072a66  mov     dword ptr [rsp+0A8h+cchDest], eax
0x180072a6a  call    cs:__imp_SelectObject
0x180072a70  mov     rcx, [rsp+0A8h+hWnd]; hWnd
0x180072a78  xor     r9d, r9d; lParam
0x180072a7b  mov     r8d, esi; wParam
0x180072a7e  mov     edx, 0D6h; Msg
0x180072a83  mov     rbx, rax
0x180072a86  mov     [rsp+0A8h+var_58], rax
0x180072a8b  call    cs:__imp_SendMessageW
0x180072a91  mov     r9, r15; lpString
0x180072a94  mov     [rsp+0A8h+c], edi; c
0x180072a98  mov     ecx, eax
0x180072a9a  cwde
0x180072a9b  shr     ecx, 10h
0x180072a9e  mov     edx, eax; x
0x180072aa0  movsx   ecx, cx
0x180072aa3  mov     dword ptr [rsp+0A8h+wParam], ecx
0x180072aaa  mov     r8d, ecx; y
0x180072aad  mov     rcx, rbp; hdc
0x180072ab0  mov     [rsp+0A8h+x], eax
0x180072ab4  call    cs:__imp_TextOutW
0x180072aba  mov     r8d, r12d; color
0x180072abd  mov     edx, 1; cWidth
0x180072ac2  mov     ecx, r13d; iStyle
0x180072ac5  call    cs:__imp_CreatePen
0x180072acb  mov     [rsp+0A8h+ho], rax
0x180072ad0  test    rax, rax
0x180072ad3  jz      loc_180072B8B
0x180072ad9  mov     rdx, rax; h
0x180072adc  mov     rcx, rbp; hdc
0x180072adf  call    cs:__imp_SelectObject
0x180072ae5  mov     edx, 1; mode
0x180072aea  mov     rcx, rbp; hdc
0x180072aed  mov     [rsp+0A8h+var_50], rax
0x180072af2  call    cs:__imp_SetBkMode
0x180072af8  lea     r9, [rsp+0A8h+sz]; lpsz
0x180072afd  mov     qword ptr [rsp+0A8h+sz.cx], 0
0x180072b06  mov     r8d, edi; c
0x180072b09  mov     rdx, r15; lpString
0x180072b0c  mov     rcx, rbp; hdc
0x180072b0f  mov     ebx, eax
0x180072b11  call    cs:__imp_GetTextExtentPointW
0x180072b17  mov     eax, dword ptr [rsp+0A8h+wParam]
0x180072b1e  xor     r9d, r9d; lppt
0x180072b21  mov     r8d, [rsp+0A8h+sz.cy]
0x180072b26  dec     eax
0x180072b28  mov     edx, [rsp+0A8h+x]; x
0x180072b2c  add     r8d, eax; y
0x180072b2f  mov     rcx, rbp; hdc
0x180072b32  call    cs:__imp_MoveToEx
0x180072b38  mov     eax, dword ptr [rsp+0A8h+wParam]
0x180072b3f  mov     rcx, rbp; hdc
0x180072b42  mov     r8d, [rsp+0A8h+sz.cy]
0x180072b47  dec     eax
0x180072b49  mov     edx, [rsp+0A8h+x]
0x180072b4d  add     r8d, eax; y
0x180072b50  add     edx, [rsp+0A8h+sz.cx]; x
0x180072b54  call    cs:__imp_LineTo
0x180072b5a  mov     edx, ebx; mode
0x180072b5c  mov     rcx, rbp; hdc
0x180072b5f  call    cs:__imp_SetBkMode
0x180072b65  mov     rax, [rsp+0A8h+var_50]
0x180072b6a  test    rax, rax
0x180072b6d  jz      short loc_180072B7B
0x180072b6f  mov     rdx, rax; h
0x180072b72  mov     rcx, rbp; hdc
0x180072b75  call    cs:__imp_SelectObject
0x180072b7b  mov     rcx, [rsp+0A8h+ho]; ho
0x180072b80  call    cs:__imp_DeleteObject
0x180072b86  mov     rbx, [rsp+0A8h+var_58]
0x180072b8b  test    rbx, rbx
0x180072b8e  jz      short loc_180072B9C
0x180072b90  mov     rdx, rbx; h
0x180072b93  mov     rcx, rbp; hdc
0x180072b96  call    cs:__imp_SelectObject
0x180072b9c  mov     edx, [rsp+0A8h+var_68]; color
0x180072ba0  mov     rcx, rbp; hdc
0x180072ba3  call    cs:__imp_SetTextColor
0x180072ba9  mov     edx, dword ptr [rsp+0A8h+cchDest]; color
0x180072bad  mov     rcx, rbp; hdc
0x180072bb0  call    cs:__imp_SetBkColor
0x180072bb6  mov     rcx, r15; hMem
0x180072bb9  call    cs:__imp_LocalFree
0x180072bbf  add     esi, edi
0x180072bc1  cmp     esi, [rsp+0A8h+arg_30]
0x180072bc8  jb      loc_180072950
0x180072bce  mov     rbx, [rsp+0A8h+arg_8]
0x180072bd6  add     rsp, 70h
0x180072bda  pop     r15
0x180072bdc  pop     r14
0x180072bde  pop     r13
0x180072be0  pop     r12
0x180072be2  pop     rdi
0x180072be3  pop     rsi
0x180072be4  pop     rbp
0x180072be5  retn
```

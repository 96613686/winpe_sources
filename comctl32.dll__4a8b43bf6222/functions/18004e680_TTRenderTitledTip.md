# TTRenderTitledTip

- ea: `0x18004e680`
- end: `0x18004e90a`
- name: `TTRenderTitledTip`
- size: `650`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18004dde4`
- `0x18004e18c`

## callees

- `0x1800115f0`
- `0x18004e680`
- `0x180085a10`
- `0x18008ea60`

## import_xrefs

- `GDI32!SelectObject` at `0x18004e7b4`
- `GDI32!SelectObject` at `0x18004e84c`
- `GDI32!SelectObject` at `0x18004e7b4`
- `GDI32!SelectObject` at `0x18004e84c`
- `GDI32!DeleteObject` at `0x18004e856`
- `GDI32!DeleteObject` at `0x18004e856`
- `GDI32!GetObjectW` at `0x18004e793`
- `GDI32!GetObjectW` at `0x18004e793`
- `GDI32!CreateFontIndirectW` at `0x18004e7a4`
- `GDI32!CreateFontIndirectW` at `0x18004e7a4`
- `GDI32!SetBkMode` at `0x18004e74f`
- `GDI32!SetBkMode` at `0x18004e8d8`
- `GDI32!SetBkMode` at `0x18004e74f`
- `GDI32!SetBkMode` at `0x18004e8d8`
- `GDI32!SetTextColor` at `0x18004e73e`
- `GDI32!SetTextColor` at `0x18004e8cc`
- `GDI32!SetTextColor` at `0x18004e73e`
- `GDI32!SetTextColor` at `0x18004e8cc`
- `GDI32!GetCurrentObject` at `0x18004e781`
- `GDI32!GetCurrentObject` at `0x18004e781`
- `KERNEL32!lstrlenW` at `0x18004e7fe`
- `KERNEL32!lstrlenW` at `0x18004e87a`
- `KERNEL32!lstrlenW` at `0x18004e7fe`
- `KERNEL32!lstrlenW` at `0x18004e87a`
- `USER32!CopyRect` at `0x18004e6dc`
- `USER32!CopyRect` at `0x18004e863`
- `USER32!CopyRect` at `0x18004e6dc`
- `USER32!CopyRect` at `0x18004e863`
- `USER32!DrawTextW` at `0x18004e818`
- `USER32!DrawTextW` at `0x18004e894`
- `USER32!DrawTextW` at `0x18004e818`
- `USER32!DrawTextW` at `0x18004e894`

## pseudocode

```c
__int64 __fastcall TTRenderTitledTip(__int64 a1, HDC a2, int a3, const RECT *a4, UINT a5)
{
  int v5; // esi
  int v11; // edx
  int v12; // ebx
  int v13; // r12d
  struct _IMAGELIST *v14; // rcx
  HGDIOBJ CurrentObject; // rax
  const WCHAR *v16; // rbx
  int v17; // eax
  int v18; // eax
  const WCHAR *v19; // rbx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  COLORREF color; // [rsp+30h] [rbp-81h]
  int mode; // [rsp+34h] [rbp-7Dh]
  HGDIOBJ h; // [rsp+40h] [rbp-71h]
  HFONT ho; // [rsp+48h] [rbp-69h]
  struct tagRECT rcDst; // [rsp+50h] [rbp-61h] BYREF
  LOGFONTW pv; // [rsp+60h] [rbp-51h] BYREF

  v5 = 0;
  rcDst = 0;
  if ( !*(_DWORD *)(a1 + 160) )
    return 0;
  color = 0;
  mode = 0;
  CopyRect(&rcDst, a4);
  v11 = *(_DWORD *)(a1 + 164);
  v12 = 16;
  if ( v11 )
  {
    v13 = 24;
    v5 = 16;
    if ( !a3 )
    {
      v14 = *(struct _IMAGELIST **)(a1 + 176);
      if ( v14 )
        ImageList_Draw(v14, v11 - 1, a2, rcDst.left, rcDst.top, 1u);
    }
    rcDst.left += 24;
  }
  else
  {
    v13 = 0;
  }
  if ( !a3 )
  {
    color = SetTextColor(a2, *(_DWORD *)(a1 + 200));
    mode = SetBkMode(a2, 1);
  }
  if ( **(_WORD **)(a1 + 152) )
  {
    memset(&pv, 0, sizeof(pv));
    CurrentObject = GetCurrentObject(a2, 6u);
    GetObjectW(CurrentObject, 92, &pv);
    pv.lfWeight = 700;
    ho = CreateFontIndirectW(&pv);
    h = SelectObject(a2, ho);
    if ( *(int *)(a1 + 168) > 16 )
      v12 = *(_DWORD *)(a1 + 168);
    rcDst.bottom = v12 + rcDst.top;
    if ( a3 )
      rcDst.right = rcDst.left + 300;
    v16 = *(const WCHAR **)(a1 + 152);
    v17 = lstrlenW(v16);
    DrawTextW(a2, v16, v17, &rcDst, a5 | (a3 != 0 ? 32 : 40));
    v18 = *(_DWORD *)(a1 + 168);
    if ( !v18 )
    {
      v18 = rcDst.bottom - rcDst.top;
      *(_DWORD *)(a1 + 168) = rcDst.bottom - rcDst.top;
    }
    if ( v5 <= v18 )
      v5 = v18;
    v5 += 6;
    v13 += rcDst.right - rcDst.left;
    SelectObject(a2, h);
    DeleteObject(ho);
  }
  CopyRect(&rcDst, a4);
  v19 = *(const WCHAR **)(a1 + 136);
  rcDst.top += v5;
  v20 = lstrlenW(v19);
  DrawTextW(a2, v19, v20, &rcDst, a5 & 0xFFFFFFDF);
  v21 = rcDst.right - rcDst.left;
  if ( v13 > rcDst.right - rcDst.left )
    v21 = v13;
  if ( a3 )
  {
    v22 = rcDst.bottom + a4->top - rcDst.top;
    a4->right = a4->left + v21;
    a4->bottom = v5 + v22;
  }
  else
  {
    SetTextColor(a2, color);
    SetBkMode(a2, mode);
  }
  return 1;
}

```

## disassembly

```asm
0x18004e680  mov     [rsp-8+arg_10], rbx
0x18004e685  push    rbp
0x18004e686  push    rsi
0x18004e687  push    rdi
0x18004e688  push    r12
0x18004e68a  push    r13
0x18004e68c  push    r14
0x18004e68e  push    r15
0x18004e690  lea     rbp, [rsp-1Fh]
0x18004e695  sub     rsp, 0D0h
0x18004e69c  mov     rax, cs:__security_cookie
0x18004e6a3  xor     rax, rsp
0x18004e6a6  mov     [rbp+4Fh+var_40], rax
0x18004e6aa  xor     esi, esi
0x18004e6ac  xorps   xmm0, xmm0
0x18004e6af  mov     r15, r9
0x18004e6b2  mov     r13d, r8d
0x18004e6b5  mov     r14, rdx
0x18004e6b8  mov     rdi, rcx
0x18004e6bb  movups  xmmword ptr [rbp+4Fh+rcDst.left], xmm0
0x18004e6bf  cmp     [rcx+0A0h], esi
0x18004e6c5  jnz     short loc_18004E6CE
0x18004e6c7  xor     eax, eax
0x18004e6c9  jmp     loc_18004E8E3
0x18004e6ce  mov     rdx, r15; lprcSrc
0x18004e6d1  mov     [rsp+100h+color], esi
0x18004e6d5  lea     rcx, [rbp+4Fh+rcDst]; lprcDst
0x18004e6d9  mov     [rbp+4Fh+mode], esi
0x18004e6dc  call    cs:__imp_CopyRect
0x18004e6e2  mov     edx, [rdi+0A4h]
0x18004e6e8  mov     ebx, 10h
0x18004e6ed  test    edx, edx
0x18004e6ef  jz      short loc_18004E72B
0x18004e6f1  lea     r12d, [rbx+8]
0x18004e6f5  mov     esi, ebx
0x18004e6f7  test    r13d, r13d
0x18004e6fa  jnz     short loc_18004E725
0x18004e6fc  mov     rcx, [rdi+0B0h]; himl
0x18004e703  test    rcx, rcx
0x18004e706  jz      short loc_18004E725
0x18004e708  mov     eax, [rbp+4Fh+rcDst.top]
0x18004e70b  dec     edx; i
0x18004e70d  mov     r9d, [rbp+4Fh+rcDst.left]; x
0x18004e711  mov     r8, r14; hdcDst
0x18004e714  mov     [rsp+100h+fStyle], 1; fStyle
0x18004e71c  mov     [rsp+100h+y], eax; y
0x18004e720  call    ImageList_Draw
0x18004e725  add     [rbp+4Fh+rcDst.left], r12d
0x18004e729  jmp     short loc_18004E72E
0x18004e72b  mov     r12d, esi
0x18004e72e  xor     eax, eax
0x18004e730  test    r13d, r13d
0x18004e733  jnz     short loc_18004E75A
0x18004e735  mov     edx, [rdi+0C8h]; color
0x18004e73b  mov     rcx, r14; hdc
0x18004e73e  call    cs:__imp_SetTextColor
0x18004e744  lea     edx, [r13+1]; mode
0x18004e748  mov     rcx, r14; hdc
0x18004e74b  mov     [rsp+100h+color], eax
0x18004e74f  call    cs:__imp_SetBkMode
0x18004e755  mov     [rbp+4Fh+mode], eax
0x18004e758  xor     eax, eax
0x18004e75a  mov     rcx, [rdi+98h]
0x18004e761  cmp     [rcx], ax
0x18004e764  jz      loc_18004E85C
0x18004e76a  xor     edx, edx; Val
0x18004e76c  lea     rcx, [rbp+4Fh+pv]; void *
0x18004e770  lea     r8d, [rdx+5Ch]; Size
0x18004e774  call    memset
0x18004e779  mov     edx, 6; type
0x18004e77e  mov     rcx, r14; hdc
0x18004e781  call    cs:__imp_GetCurrentObject
0x18004e787  lea     r8, [rbp+4Fh+pv]; pv
0x18004e78b  mov     edx, 5Ch ; '\'; c
0x18004e790  mov     rcx, rax; h
0x18004e793  call    cs:__imp_GetObjectW
0x18004e799  lea     rcx, [rbp+4Fh+pv]; lplf
0x18004e79d  mov     [rbp+4Fh+var_90], 2BCh
0x18004e7a4  call    cs:__imp_CreateFontIndirectW
0x18004e7aa  mov     rdx, rax; h
0x18004e7ad  mov     [rbp+4Fh+ho], rax
0x18004e7b1  mov     rcx, r14; hdc
0x18004e7b4  call    cs:__imp_SelectObject
0x18004e7ba  mov     [rbp+4Fh+h], rax
0x18004e7be  mov     ecx, r13d
0x18004e7c1  neg     ecx
0x18004e7c3  mov     ecx, [rdi+0A8h]
0x18004e7c9  sbb     eax, eax
0x18004e7cb  and     eax, 0FFFFFFF8h
0x18004e7ce  add     eax, 28h ; '('
0x18004e7d1  or      eax, [rbp+4Fh+arg_20]
0x18004e7d4  cmp     ecx, ebx
0x18004e7d6  mov     [rbp+4Fh+format], eax
0x18004e7d9  cmovg   ebx, ecx
0x18004e7dc  mov     ecx, [rbp+4Fh+rcDst.top]
0x18004e7df  add     ecx, ebx
0x18004e7e1  mov     [rbp+4Fh+rcDst.bottom], ecx
0x18004e7e4  test    r13d, r13d
0x18004e7e7  jz      short loc_18004E7F4
0x18004e7e9  mov     eax, [rbp+4Fh+rcDst.left]
0x18004e7ec  add     eax, 12Ch
0x18004e7f1  mov     [rbp+4Fh+rcDst.right], eax
0x18004e7f4  mov     rbx, [rdi+98h]
0x18004e7fb  mov     rcx, rbx; lpString
0x18004e7fe  call    cs:__imp_lstrlenW
0x18004e804  lea     r9, [rbp+4Fh+rcDst]; lprc
0x18004e808  mov     rdx, rbx; lpchText
0x18004e80b  mov     r8d, eax; cchText
0x18004e80e  mov     rcx, r14; hdc
0x18004e811  mov     eax, [rbp+4Fh+format]
0x18004e814  mov     [rsp+100h+y], eax; format
0x18004e818  call    cs:__imp_DrawTextW
0x18004e81e  mov     eax, [rdi+0A8h]
0x18004e824  test    eax, eax
0x18004e826  jnz     short loc_18004E834
0x18004e828  mov     eax, [rbp+4Fh+rcDst.bottom]
0x18004e82b  sub     eax, [rbp+4Fh+rcDst.top]
0x18004e82e  mov     [rdi+0A8h], eax
0x18004e834  mov     rdx, [rbp+4Fh+h]; h
0x18004e838  cmp     esi, eax
0x18004e83a  mov     rcx, r14; hdc
0x18004e83d  cmovle  esi, eax
0x18004e840  mov     eax, [rbp+4Fh+rcDst.right]
0x18004e843  sub     eax, [rbp+4Fh+rcDst.left]
0x18004e846  add     esi, 6
0x18004e849  add     r12d, eax
0x18004e84c  call    cs:__imp_SelectObject
0x18004e852  mov     rcx, [rbp+4Fh+ho]; ho
0x18004e856  call    cs:__imp_DeleteObject
0x18004e85c  mov     rdx, r15; lprcSrc
0x18004e85f  lea     rcx, [rbp+4Fh+rcDst]; lprcDst
0x18004e863  call    cs:__imp_CopyRect
0x18004e869  mov     rbx, [rdi+88h]
0x18004e870  add     [rbp+4Fh+rcDst.top], esi
0x18004e873  mov     rcx, rbx; lpString
0x18004e876  and     [rbp+4Fh+arg_20], 0FFFFFFDFh
0x18004e87a  call    cs:__imp_lstrlenW
0x18004e880  mov     ecx, [rbp+4Fh+arg_20]
0x18004e883  lea     r9, [rbp+4Fh+rcDst]; lprc
0x18004e887  mov     [rsp+100h+y], ecx; format
0x18004e88b  mov     r8d, eax; cchText
0x18004e88e  mov     rcx, r14; hdc
0x18004e891  mov     rdx, rbx; lpchText
0x18004e894  call    cs:__imp_DrawTextW
0x18004e89a  mov     ecx, [rbp+4Fh+rcDst.right]
0x18004e89d  sub     ecx, [rbp+4Fh+rcDst.left]
0x18004e8a0  cmp     r12d, ecx
0x18004e8a3  cmovg   ecx, r12d
0x18004e8a7  test    r13d, r13d
0x18004e8aa  jz      short loc_18004E8C5
0x18004e8ac  add     ecx, [r15]
0x18004e8af  mov     eax, [r15+4]
0x18004e8b3  sub     eax, [rbp+4Fh+rcDst.top]
0x18004e8b6  add     eax, [rbp+4Fh+rcDst.bottom]
0x18004e8b9  add     eax, esi
0x18004e8bb  mov     [r15+8], ecx
0x18004e8bf  mov     [r15+0Ch], eax
0x18004e8c3  jmp     short loc_18004E8DE
0x18004e8c5  mov     edx, [rsp+100h+color]; color
0x18004e8c9  mov     rcx, r14; hdc
0x18004e8cc  call    cs:__imp_SetTextColor
0x18004e8d2  mov     edx, [rbp+4Fh+mode]; mode
0x18004e8d5  mov     rcx, r14; hdc
0x18004e8d8  call    cs:__imp_SetBkMode
0x18004e8de  mov     eax, 1
0x18004e8e3  mov     rcx, [rbp+4Fh+var_40]
0x18004e8e7  xor     rcx, rsp; StackCookie
0x18004e8ea  call    __security_check_cookie
0x18004e8ef  mov     rbx, [rsp+100h+arg_10]
0x18004e8f7  add     rsp, 0D0h
0x18004e8fe  pop     r15
0x18004e900  pop     r14
0x18004e902  pop     r13
0x18004e904  pop     r12
0x18004e906  pop     rdi
0x18004e907  pop     rsi
0x18004e908  pop     rbp
0x18004e909  retn
```

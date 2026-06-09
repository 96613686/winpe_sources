# CCDrawEdge

- ea: `0x1800d7820`
- end: `0x1800d7b5a`
- name: `CCDrawEdge`
- size: `826`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, LPRECT lprcDst@<rdx>, __int64)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1800134f0`
- `0x180017364`
- `0x1800190a0`
- `0x18004f5f0`
- `0x1800d9958`
- `0x1800f3bb4`
- `0x180102578`
- `0x180102814`
- `0x180131740`

## callees

- `0x180007fc4`
- `0x1800d7820`
- `0x180114520`

## import_xrefs

- `USER32!CopyRect` at `0x1800d7874`
- `USER32!CopyRect` at `0x1800d7b2b`
- `USER32!CopyRect` at `0x1800d7874`
- `USER32!CopyRect` at `0x1800d7b2b`
- `USER32!GetSystemMetrics` at `0x1800d79bd`
- `USER32!GetSystemMetrics` at `0x1800d79d3`
- `USER32!GetSystemMetrics` at `0x1800d7a05`
- `USER32!GetSystemMetrics` at `0x1800d7a27`
- `USER32!GetSystemMetrics` at `0x1800d7a57`
- `USER32!GetSystemMetrics` at `0x1800d7a65`
- `USER32!GetSystemMetrics` at `0x1800d7aa0`
- `USER32!GetSystemMetrics` at `0x1800d7aba`
- `USER32!GetSystemMetrics` at `0x1800d79bd`
- `USER32!GetSystemMetrics` at `0x1800d79d3`
- `USER32!GetSystemMetrics` at `0x1800d7a05`
- `USER32!GetSystemMetrics` at `0x1800d7a27`
- `USER32!GetSystemMetrics` at `0x1800d7a57`
- `USER32!GetSystemMetrics` at `0x1800d7a65`
- `USER32!GetSystemMetrics` at `0x1800d7aa0`
- `USER32!GetSystemMetrics` at `0x1800d7aba`
- `USER32!GetSysColor` at `0x1800d78b5`
- `USER32!GetSysColor` at `0x1800d78ec`
- `USER32!GetSysColor` at `0x1800d78f9`
- `USER32!GetSysColor` at `0x1800d793a`
- `USER32!GetSysColor` at `0x1800d7957`
- `USER32!GetSysColor` at `0x1800d7974`
- `USER32!GetSysColor` at `0x1800d7981`
- `USER32!GetSysColor` at `0x1800d7b09`
- `USER32!GetSysColor` at `0x1800d78b5`
- `USER32!GetSysColor` at `0x1800d78ec`
- `USER32!GetSysColor` at `0x1800d78f9`
- `USER32!GetSysColor` at `0x1800d793a`
- `USER32!GetSysColor` at `0x1800d7957`
- `USER32!GetSysColor` at `0x1800d7974`
- `USER32!GetSysColor` at `0x1800d7981`
- `USER32!GetSysColor` at `0x1800d7b09`

## pseudocode

```c
__int64 __fastcall CCDrawEdge(HDC hdc, LPRECT lprcDst, char a3, __int16 a4, __int64 a5)
{
  __int16 v5; // di
  int v9; // eax
  int v10; // eax
  int v11; // ecx
  COLORREF v12; // esi
  COLORREF v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // ecx
  DWORD SysColor; // eax
  int v19; // ecx
  COLORREF v20; // eax
  int v21; // ecx
  DWORD v22; // eax
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  COLORREF v26; // eax
  int SystemMetrics; // eax
  int v28; // eax
  int v30; // ecx
  COLORREF v31; // eax
  struct tagRECT rcDst; // [rsp+20h] [rbp-30h] BYREF
  RECT rect; // [rsp+30h] [rbp-20h] BYREF

  v5 = a4 | 0x4000;
  if ( (a4 & 0x8000) == 0 )
    v5 = a4;
  rcDst = 0;
  rect = 0;
  CopyRect(&rcDst, lprcDst);
  v9 = a3 & 3;
  if ( (a3 & 3) == 0 )
    goto LABEL_48;
  while ( 1 )
  {
    if ( (v5 & 0x4000) == 0 )
    {
      v14 = v9 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( !v15 )
        {
          v24 = 21;
          if ( (v5 & 0x1000) == 0 )
            v24 = 16;
          SysColor = GetSysColor(v24);
          v19 = 20;
LABEL_19:
          v13 = SysColor;
          v12 = GetSysColor(v19);
          if ( a5 )
          {
            v20 = *(_DWORD *)(a5 + 8);
            if ( v20 == -16777216 )
              v20 = v13;
            v13 = v20;
            if ( *(_DWORD *)(a5 + 4) != -16777216 )
              v12 = *(_DWORD *)(a5 + 4);
          }
          goto LABEL_38;
        }
        v16 = v15 - 2;
        if ( v16 )
        {
          if ( v16 != 4 )
            return 0;
          v17 = 16;
          if ( (v5 & 0x1000) == 0 )
            v17 = 21;
          SysColor = GetSysColor(v17);
          v19 = 22;
          goto LABEL_19;
        }
        v21 = 22;
        if ( (v5 & 0x1000) == 0 )
          v21 = 20;
        v22 = GetSysColor(v21);
        v23 = 16;
      }
      else
      {
        v25 = 20;
        if ( (v5 & 0x1000) == 0 )
          v25 = 22;
        v22 = GetSysColor(v25);
        v23 = 21;
      }
      v13 = v22;
      v12 = GetSysColor(v23);
      if ( a5 )
      {
        v26 = *(_DWORD *)(a5 + 4);
        if ( v26 == -16777216 )
          v26 = v13;
        v13 = v26;
        if ( *(_DWORD *)(a5 + 8) != -16777216 )
          v12 = *(_DWORD *)(a5 + 8);
      }
      goto LABEL_38;
    }
    v10 = v9 & 3;
    if ( v5 < 0 )
    {
      v11 = v10 ? 6 : 5;
    }
    else
    {
      v11 = 16;
      if ( !v10 )
        v11 = 15;
    }
    v12 = GetSysColor(v11);
    v13 = v12;
LABEL_38:
    if ( (v5 & 0xC) != 0 )
    {
      if ( (v5 & 4) != 0 )
      {
        rcDst.right -= GetSystemMetrics(5);
        rect.left = rcDst.right;
        rect.right = rcDst.right + GetSystemMetrics(5);
        rect.top = rcDst.top;
        rect.bottom = rcDst.bottom;
        FillRectClr(hdc, &rect, v12);
      }
      if ( (v5 & 8) != 0 )
      {
        rcDst.bottom -= GetSystemMetrics(6);
        rect.left = rcDst.left;
        rect.top = rcDst.bottom;
        rect.right = rcDst.right;
        rect.bottom = rcDst.bottom + GetSystemMetrics(6);
        FillRectClr(hdc, &rect, v12);
      }
    }
    if ( (v5 & 3) != 0 )
    {
      if ( (v5 & 1) != 0 )
      {
        rcDst.left += GetSystemMetrics(5);
        SystemMetrics = GetSystemMetrics(5);
        rect.right = rcDst.left;
        rect.left = rcDst.left - SystemMetrics;
        rect.top = rcDst.top;
        rect.bottom = rcDst.bottom;
        FillRectClr(hdc, &rect, v13);
      }
      if ( (v5 & 2) != 0 )
      {
        rcDst.top += GetSystemMetrics(6);
        rect.left = rcDst.left;
        rect.right = rcDst.right;
        v28 = GetSystemMetrics(6);
        rect.bottom = rcDst.top;
        rect.top = rcDst.top - v28;
        FillRectClr(hdc, &rect, v13);
      }
    }
LABEL_48:
    v9 = a3 & 0xC;
    if ( (a3 & 0xC) == 0 )
      break;
    a3 &= 0xF3u;
  }
  if ( (v5 & 0x800) != 0 )
  {
    v30 = 5;
    if ( (v5 & 0x8000) == 0 )
      v30 = 15;
    v31 = GetSysColor(v30);
    FillRectClr(hdc, &rcDst, v31);
  }
  if ( (v5 & 0x2000) != 0 )
    CopyRect(lprcDst, &rcDst);
  return 1;
}

```

## disassembly

```asm
0x1800d7820  mov     [rsp-38h+arg_10], rbx
0x1800d7825  push    rbp
0x1800d7826  push    rsi
0x1800d7827  push    rdi
0x1800d7828  push    r12
0x1800d782a  push    r13
0x1800d782c  push    r14
0x1800d782e  push    r15
0x1800d7830  mov     rbp, rsp
0x1800d7833  sub     rsp, 50h
0x1800d7837  mov     rax, cs:__security_cookie
0x1800d783e  xor     rax, rsp
0x1800d7841  mov     [rbp+var_10], rax
0x1800d7845  mov     r14, [rbp+arg_20]
0x1800d7849  mov     edi, r9d
0x1800d784c  bts     edi, 0Eh
0x1800d7850  mov     r15, rcx
0x1800d7853  bt      r9d, 0Fh
0x1800d7858  lea     rcx, [rbp+rcDst]; lprcDst
0x1800d785c  xorps   xmm0, xmm0
0x1800d785f  xorps   xmm1, xmm1
0x1800d7862  cmovnb  edi, r9d
0x1800d7866  mov     r12d, r8d
0x1800d7869  mov     r13, rdx
0x1800d786c  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x1800d7870  movups  xmmword ptr [rbp+rect.left], xmm1
0x1800d7874  call    cs:__imp_CopyRect
0x1800d787a  mov     eax, r12d
0x1800d787d  and     eax, 3
0x1800d7880  jz      loc_1800D7ADE
0x1800d7886  bt      edi, 0Eh
0x1800d788a  jnb     short loc_1800D78C4
0x1800d788c  and     eax, 3
0x1800d788f  bt      edi, 0Fh
0x1800d7893  jnb     short loc_1800D78A7
0x1800d7895  test    eax, eax
0x1800d7897  jz      short loc_1800D78A0
0x1800d7899  mov     ecx, 6
0x1800d789e  jmp     short loc_1800D78B5
0x1800d78a0  mov     ecx, 5
0x1800d78a5  jmp     short loc_1800D78B5
0x1800d78a7  mov     ecx, 10h
0x1800d78ac  test    eax, eax
0x1800d78ae  jnz     short loc_1800D78B5
0x1800d78b0  mov     ecx, 0Fh; nIndex
0x1800d78b5  call    cs:__imp_GetSysColor
0x1800d78bb  mov     esi, eax
0x1800d78bd  mov     ebx, eax
0x1800d78bf  jmp     loc_1800D79A8
0x1800d78c4  sub     eax, 1
0x1800d78c7  jz      loc_1800D7964
0x1800d78cd  sub     eax, 1
0x1800d78d0  jz      short loc_1800D7947
0x1800d78d2  sub     eax, 2
0x1800d78d5  jz      short loc_1800D792A
0x1800d78d7  cmp     eax, 4
0x1800d78da  jnz     loc_1800D7AEF
0x1800d78e0  lea     ecx, [rax+0Ch]
0x1800d78e3  bt      edi, 0Ch
0x1800d78e7  jb      short loc_1800D78EC
0x1800d78e9  lea     ecx, [rax+11h]; nIndex
0x1800d78ec  call    cs:__imp_GetSysColor
0x1800d78f2  mov     ecx, 16h; nIndex
0x1800d78f7  mov     ebx, eax
0x1800d78f9  call    cs:__imp_GetSysColor
0x1800d78ff  mov     esi, eax
0x1800d7901  test    r14, r14
0x1800d7904  jz      loc_1800D79A8
0x1800d790a  mov     eax, [r14+8]
0x1800d790e  mov     ecx, 0FF000000h
0x1800d7913  cmp     eax, ecx
0x1800d7915  cmovz   eax, ebx
0x1800d7918  mov     ebx, eax
0x1800d791a  cmp     [r14+4], ecx
0x1800d791e  jz      loc_1800D79A8
0x1800d7924  mov     esi, [r14+4]
0x1800d7928  jmp     short loc_1800D79A8
0x1800d792a  mov     ecx, 16h
0x1800d792f  bt      edi, 0Ch
0x1800d7933  jb      short loc_1800D793A
0x1800d7935  mov     ecx, 14h; nIndex
0x1800d793a  call    cs:__imp_GetSysColor
0x1800d7940  mov     ecx, 10h
0x1800d7945  jmp     short loc_1800D797F
0x1800d7947  mov     ecx, 15h
0x1800d794c  bt      edi, 0Ch
0x1800d7950  jb      short loc_1800D7957
0x1800d7952  mov     ecx, 10h; nIndex
0x1800d7957  call    cs:__imp_GetSysColor
0x1800d795d  mov     ecx, 14h
0x1800d7962  jmp     short loc_1800D78F7
0x1800d7964  mov     ecx, 14h
0x1800d7969  bt      edi, 0Ch
0x1800d796d  jb      short loc_1800D7974
0x1800d796f  mov     ecx, 16h; nIndex
0x1800d7974  call    cs:__imp_GetSysColor
0x1800d797a  mov     ecx, 15h; nIndex
0x1800d797f  mov     ebx, eax
0x1800d7981  call    cs:__imp_GetSysColor
0x1800d7987  mov     esi, eax
0x1800d7989  test    r14, r14
0x1800d798c  jz      short loc_1800D79A8
0x1800d798e  mov     eax, [r14+4]
0x1800d7992  mov     ecx, 0FF000000h
0x1800d7997  cmp     eax, ecx
0x1800d7999  cmovz   eax, ebx
0x1800d799c  mov     ebx, eax
0x1800d799e  cmp     [r14+8], ecx
0x1800d79a2  jz      short loc_1800D79A8
0x1800d79a4  mov     esi, [r14+8]
0x1800d79a8  test    dil, 0Ch
0x1800d79ac  jz      loc_1800D7A42
0x1800d79b2  test    dil, 4
0x1800d79b6  jz      short loc_1800D79FA
0x1800d79b8  mov     ecx, 5; nIndex
0x1800d79bd  call    cs:__imp_GetSystemMetrics
0x1800d79c3  mov     ecx, [rbp+rcDst.right]
0x1800d79c6  sub     ecx, eax
0x1800d79c8  mov     [rbp+rcDst.right], ecx
0x1800d79cb  mov     [rbp+rect.left], ecx
0x1800d79ce  mov     ecx, 5; nIndex
0x1800d79d3  call    cs:__imp_GetSystemMetrics
0x1800d79d9  add     eax, [rbp+rcDst.right]
0x1800d79dc  mov     r8d, esi; color
0x1800d79df  mov     [rbp+rect.right], eax
0x1800d79e2  lea     rdx, [rbp+rect]; lprect
0x1800d79e6  mov     eax, [rbp+rcDst.top]
0x1800d79e9  mov     rcx, r15; hdc
0x1800d79ec  mov     [rbp+rect.top], eax
0x1800d79ef  mov     eax, [rbp+rcDst.bottom]
0x1800d79f2  mov     [rbp+rect.bottom], eax
0x1800d79f5  call    FillRectClr
0x1800d79fa  test    dil, 8
0x1800d79fe  jz      short loc_1800D7A42
0x1800d7a00  mov     ecx, 6; nIndex
0x1800d7a05  call    cs:__imp_GetSystemMetrics
0x1800d7a0b  mov     ecx, [rbp+rcDst.bottom]
0x1800d7a0e  sub     ecx, eax
0x1800d7a10  mov     eax, [rbp+rcDst.left]
0x1800d7a13  mov     [rbp+rcDst.bottom], ecx
0x1800d7a16  mov     [rbp+rect.left], eax
0x1800d7a19  mov     eax, [rbp+rcDst.right]
0x1800d7a1c  mov     [rbp+rect.top], ecx
0x1800d7a1f  mov     ecx, 6; nIndex
0x1800d7a24  mov     [rbp+rect.right], eax
0x1800d7a27  call    cs:__imp_GetSystemMetrics
0x1800d7a2d  add     eax, [rbp+rcDst.bottom]
0x1800d7a30  mov     r8d, esi; color
0x1800d7a33  lea     rdx, [rbp+rect]; lprect
0x1800d7a37  mov     [rbp+rect.bottom], eax
0x1800d7a3a  mov     rcx, r15; hdc
0x1800d7a3d  call    FillRectClr
0x1800d7a42  test    dil, 3
0x1800d7a46  jz      loc_1800D7ADE
0x1800d7a4c  test    dil, 1
0x1800d7a50  jz      short loc_1800D7A95
0x1800d7a52  mov     ecx, 5; nIndex
0x1800d7a57  call    cs:__imp_GetSystemMetrics
0x1800d7a5d  add     [rbp+rcDst.left], eax
0x1800d7a60  mov     ecx, 5; nIndex
0x1800d7a65  call    cs:__imp_GetSystemMetrics
0x1800d7a6b  mov     edx, [rbp+rcDst.left]
0x1800d7a6e  mov     r8d, ebx; color
0x1800d7a71  mov     ecx, eax
0x1800d7a73  mov     [rbp+rect.right], edx
0x1800d7a76  mov     eax, edx
0x1800d7a78  lea     rdx, [rbp+rect]; lprect
0x1800d7a7c  sub     eax, ecx
0x1800d7a7e  mov     rcx, r15; hdc
0x1800d7a81  mov     [rbp+rect.left], eax
0x1800d7a84  mov     eax, [rbp+rcDst.top]
0x1800d7a87  mov     [rbp+rect.top], eax
0x1800d7a8a  mov     eax, [rbp+rcDst.bottom]
0x1800d7a8d  mov     [rbp+rect.bottom], eax
0x1800d7a90  call    FillRectClr
0x1800d7a95  test    dil, 2
0x1800d7a99  jz      short loc_1800D7ADE
0x1800d7a9b  mov     ecx, 6; nIndex
0x1800d7aa0  call    cs:__imp_GetSystemMetrics
0x1800d7aa6  add     [rbp+rcDst.top], eax
0x1800d7aa9  mov     ecx, 6; nIndex
0x1800d7aae  mov     eax, [rbp+rcDst.left]
0x1800d7ab1  mov     [rbp+rect.left], eax
0x1800d7ab4  mov     eax, [rbp+rcDst.right]
0x1800d7ab7  mov     [rbp+rect.right], eax
0x1800d7aba  call    cs:__imp_GetSystemMetrics
0x1800d7ac0  mov     edx, [rbp+rcDst.top]
0x1800d7ac3  mov     r8d, ebx; color
0x1800d7ac6  mov     ecx, eax
0x1800d7ac8  mov     [rbp+rect.bottom], edx
0x1800d7acb  mov     eax, edx
0x1800d7acd  lea     rdx, [rbp+rect]; lprect
0x1800d7ad1  sub     eax, ecx
0x1800d7ad3  mov     rcx, r15; hdc
0x1800d7ad6  mov     [rbp+rect.top], eax
0x1800d7ad9  call    FillRectClr
0x1800d7ade  mov     eax, r12d
0x1800d7ae1  and     eax, 0Ch
0x1800d7ae4  jz      short loc_1800D7AF3
0x1800d7ae6  and     r12d, 0FFFFFFF3h
0x1800d7aea  jmp     loc_1800D7886
0x1800d7aef  xor     eax, eax
0x1800d7af1  jmp     short loc_1800D7B36
0x1800d7af3  bt      edi, 0Bh
0x1800d7af7  jnb     short loc_1800D7B1E
0x1800d7af9  mov     ecx, 5
0x1800d7afe  bt      edi, 0Fh
0x1800d7b02  jb      short loc_1800D7B09
0x1800d7b04  mov     ecx, 0Fh; nIndex
0x1800d7b09  call    cs:__imp_GetSysColor
0x1800d7b0f  lea     rdx, [rbp+rcDst]; lprect
0x1800d7b13  mov     rcx, r15; hdc
0x1800d7b16  mov     r8d, eax; color
0x1800d7b19  call    FillRectClr
0x1800d7b1e  bt      edi, 0Dh
0x1800d7b22  jnb     short loc_1800D7B31
0x1800d7b24  lea     rdx, [rbp+rcDst]; lprcSrc
0x1800d7b28  mov     rcx, r13; lprcDst
0x1800d7b2b  call    cs:__imp_CopyRect
0x1800d7b31  mov     eax, 1
0x1800d7b36  mov     rcx, [rbp+var_10]
0x1800d7b3a  xor     rcx, rsp; StackCookie
0x1800d7b3d  call    __security_check_cookie
0x1800d7b42  mov     rbx, [rsp+50h+arg_10]
0x1800d7b4a  add     rsp, 50h
0x1800d7b4e  pop     r15
0x1800d7b50  pop     r14
0x1800d7b52  pop     r13
0x1800d7b54  pop     r12
0x1800d7b56  pop     rdi
0x1800d7b57  pop     rsi
0x1800d7b58  pop     rbp
0x1800d7b59  retn
```

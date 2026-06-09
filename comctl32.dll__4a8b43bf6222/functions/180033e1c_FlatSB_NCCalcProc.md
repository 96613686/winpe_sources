# FlatSB_NCCalcProc

- ea: `0x180033e1c`
- end: `0x180033f80`
- name: `FlatSB_NCCalcProc`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180034af0`

## callees

- `0x1800115f0`
- `0x18001a590`
- `0x180030230`
- `0x180033e1c`

## import_xrefs

- `USER32!CopyRect` at `0x180033e5b`
- `USER32!CopyRect` at `0x180033e7f`
- `USER32!CopyRect` at `0x180033ecc`
- `USER32!CopyRect` at `0x180033f2a`
- `USER32!CopyRect` at `0x180033e5b`
- `USER32!CopyRect` at `0x180033e7f`
- `USER32!CopyRect` at `0x180033ecc`
- `USER32!CopyRect` at `0x180033f2a`

## pseudocode

```c
LRESULT __fastcall FlatSB_NCCalcProc(_DWORD *a1, HWND a2, WPARAM a3, struct tagRECT *a4)
{
  LRESULT v8; // rdi
  int v9; // ecx
  _DWORD *v10; // r8
  LONG right; // edx
  __int64 v12; // r8
  LONG bottom; // edx
  RECT rcSrc; // [rsp+20h] [rbp-38h] BYREF
  struct tagRECT rcDst; // [rsp+30h] [rbp-28h] BYREF

  rcSrc = 0;
  rcDst = 0;
  CopyRect(&rcDst, a4);
  SetWindowBits(a2, -16);
  CopyRect(&rcSrc, a4);
  v8 = DefSubclassProc(a2, 0x83u, a3, (LPARAM)a4);
  SetWindowBits(a2, -16);
  DefSubclassProc(a2, 0x83u, 0, (LPARAM)&rcSrc);
  CopyRect(&rcSrc, a4);
  a1[2] &= 0xFFFFFFF9;
  v9 = a1[2];
  if ( (v9 & 0x200000) != 0 )
  {
    v10 = *(_DWORD **)a1;
    right = rcSrc.right;
    if ( rcSrc.right - rcSrc.left >= **(_DWORD **)a1 )
    {
      v9 |= 2u;
      a1[2] = v9;
      rcSrc.right = right - *v10;
    }
  }
  if ( (v9 & 0x100000) != 0 )
  {
    v12 = *(_QWORD *)a1;
    bottom = rcSrc.bottom;
    if ( rcSrc.bottom - rcSrc.top > *(_DWORD *)(*(_QWORD *)a1 + 16LL) )
    {
      a1[2] = v9 | 4;
      rcSrc.bottom = bottom - *(_DWORD *)(v12 + 16);
    }
  }
  CopyRect(a4, &rcSrc);
  a1[41] = rcSrc.top - rcDst.top;
  a1[43] = rcSrc.bottom - rcDst.top;
  a1[40] = rcSrc.left - rcDst.left;
  a1[42] = rcSrc.right - rcDst.left;
  return v8;
}

```

## disassembly

```asm
0x180033e1c  push    rbp
0x180033e1e  push    rbx
0x180033e1f  push    rsi
0x180033e20  push    rdi
0x180033e21  push    r14
0x180033e23  push    r15
0x180033e25  mov     rbp, rsp
0x180033e28  sub     rsp, 58h
0x180033e2c  mov     rax, cs:__security_cookie
0x180033e33  xor     rax, rsp
0x180033e36  mov     [rbp+var_18], rax
0x180033e3a  mov     rsi, rdx
0x180033e3d  mov     r14, rcx
0x180033e40  xorps   xmm0, xmm0
0x180033e43  lea     rcx, [rbp+rcDst]; lprcDst
0x180033e47  xorps   xmm1, xmm1
0x180033e4a  mov     rdx, r9; lprcSrc
0x180033e4d  movups  xmmword ptr [rbp+rcSrc.left], xmm0
0x180033e51  mov     r15, r9
0x180033e54  mov     rdi, r8
0x180033e57  movups  xmmword ptr [rbp+rcDst.left], xmm1
0x180033e5b  call    cs:__imp_CopyRect
0x180033e61  xor     r9d, r9d
0x180033e64  mov     r8d, 300000h
0x180033e6a  mov     rcx, rsi; hWnd
0x180033e6d  lea     edx, [r9-10h]; nIndex
0x180033e71  call    SetWindowBits
0x180033e76  mov     rdx, r15; lprcSrc
0x180033e79  lea     rcx, [rbp+rcSrc]; lprcDst
0x180033e7d  mov     ebx, eax
0x180033e7f  call    cs:__imp_CopyRect
0x180033e85  mov     r9, r15; lParam
0x180033e88  mov     r8, rdi; wParam
0x180033e8b  mov     edx, 83h; uMsg
0x180033e90  mov     rcx, rsi; hWnd
0x180033e93  call    DefSubclassProc
0x180033e98  mov     r9d, ebx
0x180033e9b  mov     edx, 0FFFFFFF0h; nIndex
0x180033ea0  mov     r8d, 300000h
0x180033ea6  mov     rcx, rsi; hWnd
0x180033ea9  mov     rdi, rax
0x180033eac  call    SetWindowBits
0x180033eb1  lea     r9, [rbp+rcSrc]; lParam
0x180033eb5  xor     r8d, r8d; wParam
0x180033eb8  mov     edx, 83h; uMsg
0x180033ebd  mov     rcx, rsi; hWnd
0x180033ec0  call    DefSubclassProc
0x180033ec5  mov     rdx, r15; lprcSrc
0x180033ec8  lea     rcx, [rbp+rcSrc]; lprcDst
0x180033ecc  call    cs:__imp_CopyRect
0x180033ed2  and     dword ptr [r14+8], 0FFFFFFF9h
0x180033ed7  mov     ecx, [r14+8]
0x180033edb  bt      ecx, 15h
0x180033edf  jnb     short loc_180033EFE
0x180033ee1  mov     r8, [r14]
0x180033ee4  mov     edx, [rbp+rcSrc.right]
0x180033ee7  mov     eax, edx
0x180033ee9  sub     eax, [rbp+rcSrc.left]
0x180033eec  cmp     eax, [r8]
0x180033eef  jl      short loc_180033EFE
0x180033ef1  or      ecx, 2
0x180033ef4  mov     [r14+8], ecx
0x180033ef8  sub     edx, [r8]
0x180033efb  mov     [rbp+rcSrc.right], edx
0x180033efe  bt      ecx, 14h
0x180033f02  jnb     short loc_180033F23
0x180033f04  mov     r8, [r14]
0x180033f07  mov     edx, [rbp+rcSrc.bottom]
0x180033f0a  mov     eax, edx
0x180033f0c  sub     eax, [rbp+rcSrc.top]
0x180033f0f  cmp     eax, [r8+10h]
0x180033f13  jle     short loc_180033F23
0x180033f15  or      ecx, 4
0x180033f18  mov     [r14+8], ecx
0x180033f1c  sub     edx, [r8+10h]
0x180033f20  mov     [rbp+rcSrc.bottom], edx
0x180033f23  lea     rdx, [rbp+rcSrc]; lprcSrc
0x180033f27  mov     rcx, r15; lprcDst
0x180033f2a  call    cs:__imp_CopyRect
0x180033f30  mov     eax, [rbp+rcSrc.top]
0x180033f33  sub     eax, [rbp+rcDst.top]
0x180033f36  mov     [r14+0A4h], eax
0x180033f3d  mov     eax, [rbp+rcSrc.bottom]
0x180033f40  sub     eax, [rbp+rcDst.top]
0x180033f43  mov     [r14+0ACh], eax
0x180033f4a  mov     eax, [rbp+rcSrc.left]
0x180033f4d  sub     eax, [rbp+rcDst.left]
0x180033f50  mov     [r14+0A0h], eax
0x180033f57  mov     eax, [rbp+rcSrc.right]
0x180033f5a  sub     eax, [rbp+rcDst.left]
0x180033f5d  mov     [r14+0A8h], eax
0x180033f64  mov     rax, rdi
0x180033f67  mov     rcx, [rbp+var_18]
0x180033f6b  xor     rcx, rsp; StackCookie
0x180033f6e  call    __security_check_cookie
0x180033f73  add     rsp, 58h
0x180033f77  pop     r15
0x180033f79  pop     r14
0x180033f7b  pop     rdi
0x180033f7c  pop     rsi
0x180033f7d  pop     rbx
0x180033f7e  pop     rbp
0x180033f7f  retn
```

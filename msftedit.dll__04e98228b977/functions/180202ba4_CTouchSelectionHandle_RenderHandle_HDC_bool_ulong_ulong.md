# CTouchSelectionHandle::RenderHandle(HDC__ *,bool,ulong,ulong)

- ea: `0x180202ba4`
- end: `0x180202d80`
- name: `?RenderHandle@CTouchSelectionHandle@@IEBAXPEAUHDC__@@_NKK@Z`
- size: `476`
- prototype: `void __usercall(CTouchSelectionHandle *__hidden this@<rcx>, HDC@<rdx>, bool@<r8b>, unsigned int@<r9d>, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1801ff800`
- `0x180203ddc`

## callees

- `0x18013ce80`
- `0x18013dce6`
- `0x1801fed3c`
- `0x1801ff544`
- `0x1801ff5f8`
- `0x180202ba4`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180202c02`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180202d3d`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180202c02`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180202d3d`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkMode` at `0x180202c70`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkMode` at `0x180202c70`
- `ext-ms-win-gdi-font-l1-1-1!SetTextAlign` at `0x180202c84`
- `ext-ms-win-gdi-font-l1-1-1!SetTextAlign` at `0x180202c84`
- `ext-ms-win-gdi-font-l1-1-1!GetOutlineTextMetricsW` at `0x180202c5c`
- `ext-ms-win-gdi-font-l1-1-1!GetOutlineTextMetricsW` at `0x180202c5c`
- `ext-ms-win-gdi-font-l1-1-1!GetCharABCWidthsW` at `0x180202c31`
- `ext-ms-win-gdi-font-l1-1-1!GetCharABCWidthsW` at `0x180202c31`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180202d4c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180202d4c`

## pseudocode

```c
void __fastcall CTouchSelectionHandle::RenderHandle(
        CTouchSelectionHandle *this,
        HDC a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v5; // rax
  int v9; // ebx
  int v10; // r15d
  HFONT GripperFont; // r14
  HGDIOBJ v12; // r12
  int v13[4]; // [rsp+50h] [rbp-B0h] BYREF
  _OUTLINETEXTMETRICW potm; // [rsp+60h] [rbp-A0h] BYREF
  __int128 ABC; // [rsp+150h] [rbp+50h] BYREF
  int v16[4]; // [rsp+160h] [rbp+60h]
  int v17; // [rsp+170h] [rbp+70h]

  v5 = *((_QWORD *)this + 16);
  v13[0] = 0;
  v9 = *(_DWORD *)(v5 + 24);
  v10 = *(_DWORD *)(v5 + 8);
  GripperFont = CTouchSelectionHandle::CreateGripperFont(this, v9, v13);
  v12 = SelectObject(a2, GripperFont);
  ABC = 0;
  v17 = 0;
  *(_OWORD *)v16 = 0;
  GetCharABCWidthsW(a2, 0xE2A0u, 0xE2A2u, (LPABC)&ABC);
  memset_0(&potm, 0, sizeof(potm));
  GetOutlineTextMetricsW(a2, 0xE8u, &potm);
  SetBkMode(a2, 1);
  SetTextAlign(a2, 0x18u);
  CTouchSelectionHandle::DrawGripperGlyph(this, a2, a5, &byte_1802C42B8, v10, v9, v9, SHIDWORD(ABC), v16[0]);
  CTouchSelectionHandle::DrawGripperGlyph(this, a2, a4, &dword_1802C42BC, v10, v9, v9, ABC, SDWORD1(ABC));
  if ( *((_BYTE *)this + 113) )
    CTouchSelectionHandle::DrawPost(
      this,
      a2,
      a4,
      v16[3],
      v10,
      (int)(float)((float)((float)(v16[0] - DWORD1(ABC)) * 0.5) + 0.5));
  SelectObject(a2, v12);
  DeleteObject(GripperFont);
}

```

## disassembly

```asm
0x180202ba4  mov     [rsp-8+arg_10], rbx
0x180202ba9  push    rbp
0x180202baa  push    rsi
0x180202bab  push    rdi
0x180202bac  push    r12
0x180202bae  push    r13
0x180202bb0  push    r14
0x180202bb2  push    r15
0x180202bb4  lea     rbp, [rsp-80h]
0x180202bb9  sub     rsp, 180h
0x180202bc0  mov     rax, cs:__security_cookie
0x180202bc7  xor     rax, rsp
0x180202bca  mov     [rbp+0B0h+var_38], rax
0x180202bce  mov     rax, [rcx+80h]
0x180202bd5  lea     r8, [rsp+1B0h+var_160]; int *
0x180202bda  mov     rdi, rdx
0x180202bdd  mov     [rsp+1B0h+var_160], 0
0x180202be5  mov     r13d, r9d
0x180202be8  mov     rsi, rcx
0x180202beb  mov     ebx, [rax+18h]
0x180202bee  mov     edx, ebx; int
0x180202bf0  mov     r15d, [rax+8]
0x180202bf4  call    ?CreateGripperFont@CTouchSelectionHandle@@IEBAPEAUHFONT__@@HPEAH@Z; CTouchSelectionHandle::CreateGripperFont(int,int *)
0x180202bf9  mov     rdx, rax; h
0x180202bfc  mov     rcx, rdi; hdc
0x180202bff  mov     r14, rax
0x180202c02  call    cs:__imp_SelectObject
0x180202c09  nop     dword ptr [rax+rax+00h]
0x180202c0e  xorps   xmm0, xmm0
0x180202c11  lea     r9, [rbp+0B0h+ABC]; lpABC
0x180202c15  mov     edx, 0E2A0h; wFirst
0x180202c1a  mov     r12, rax
0x180202c1d  xor     eax, eax
0x180202c1f  mov     rcx, rdi; hdc
0x180202c22  movups  [rbp+0B0h+ABC], xmm0
0x180202c26  mov     [rbp+0B0h+var_40], eax
0x180202c29  lea     r8d, [rdx+2]; wLast
0x180202c2d  movups  xmmword ptr [rbp+0B0h+var_50], xmm0
0x180202c31  call    cs:__imp_GetCharABCWidthsW
0x180202c38  nop     dword ptr [rax+rax+00h]
0x180202c3d  xor     edx, edx; Val
0x180202c3f  lea     rcx, [rsp+1B0h+potm]; void *
0x180202c44  mov     r8d, 0E8h; Size
0x180202c4a  call    memset_0
0x180202c4f  lea     r8, [rsp+1B0h+potm]; potm
0x180202c54  mov     edx, 0E8h; cjCopy
0x180202c59  mov     rcx, rdi; hdc
0x180202c5c  call    cs:__imp_GetOutlineTextMetricsW
0x180202c63  nop     dword ptr [rax+rax+00h]
0x180202c68  mov     edx, 1; mode
0x180202c6d  mov     rcx, rdi; hdc
0x180202c70  call    cs:__imp_SetBkMode
0x180202c77  nop     dword ptr [rax+rax+00h]
0x180202c7c  mov     edx, 18h; align
0x180202c81  mov     rcx, rdi; hdc
0x180202c84  call    cs:__imp_SetTextAlign
0x180202c8b  nop     dword ptr [rax+rax+00h]
0x180202c90  mov     eax, [rbp+0B0h+var_50]
0x180202c93  lea     r9, byte_1802C42B8; unsigned __int16 *
0x180202c9a  mov     r8d, [rbp+0B0h+arg_20]; unsigned int
0x180202ca1  mov     rdx, rdi; HDC
0x180202ca4  mov     [rsp+1B0h+var_170], eax; int
0x180202ca8  mov     rcx, rsi; this
0x180202cab  mov     eax, dword ptr [rbp+0B0h+ABC+0Ch]
0x180202cae  mov     [rsp+1B0h+var_178], eax; int
0x180202cb2  mov     [rsp+1B0h+var_180], ebx; int
0x180202cb6  mov     [rsp+1B0h+var_188], ebx; int
0x180202cba  mov     [rsp+1B0h+var_190], r15d; int
0x180202cbf  call    ?DrawGripperGlyph@CTouchSelectionHandle@@IEBAXPEAUHDC__@@KPEBGHHHHH@Z; CTouchSelectionHandle::DrawGripperGlyph(HDC__ *,ulong,ushort const *,int,int,int,int,int)
0x180202cc4  mov     eax, dword ptr [rbp+0B0h+ABC+4]
0x180202cc7  lea     r9, dword_1802C42BC; unsigned __int16 *
0x180202cce  mov     [rsp+1B0h+var_170], eax; int
0x180202cd2  mov     r8d, r13d; unsigned int
0x180202cd5  mov     eax, dword ptr [rbp+0B0h+ABC]
0x180202cd8  mov     rdx, rdi; HDC
0x180202cdb  mov     [rsp+1B0h+var_178], eax; int
0x180202cdf  mov     rcx, rsi; this
0x180202ce2  mov     [rsp+1B0h+var_180], ebx; int
0x180202ce6  mov     [rsp+1B0h+var_188], ebx; int
0x180202cea  mov     [rsp+1B0h+var_190], r15d; int
0x180202cef  call    ?DrawGripperGlyph@CTouchSelectionHandle@@IEBAXPEAUHDC__@@KPEBGHHHHH@Z; CTouchSelectionHandle::DrawGripperGlyph(HDC__ *,ulong,ushort const *,int,int,int,int,int)
0x180202cf4  cmp     byte ptr [rsi+71h], 0
0x180202cf8  jz      short loc_180202D37
0x180202cfa  mov     eax, [rbp+0B0h+var_50]
0x180202cfd  xorps   xmm1, xmm1
0x180202d00  sub     eax, dword ptr [rbp+0B0h+ABC+4]
0x180202d03  mov     r8d, r13d; unsigned int
0x180202d06  mov     r9d, [rbp+0B0h+var_50+0Ch]; int
0x180202d0a  mov     rdx, rdi; HDC
0x180202d0d  mov     rcx, rsi; this
0x180202d10  cvtsi2ss xmm1, rax
0x180202d15  mulss   xmm1, cs:__real@3f000000
0x180202d1d  addss   xmm1, cs:__real@3f000000
0x180202d25  cvttss2si eax, xmm1
0x180202d29  mov     [rsp+1B0h+var_188], eax; int
0x180202d2d  mov     [rsp+1B0h+var_190], r15d; int
0x180202d32  call    ?DrawPost@CTouchSelectionHandle@@IEBAXPEAUHDC__@@KHHH@Z; CTouchSelectionHandle::DrawPost(HDC__ *,ulong,int,int,int)
0x180202d37  mov     rdx, r12; h
0x180202d3a  mov     rcx, rdi; hdc
0x180202d3d  call    cs:__imp_SelectObject
0x180202d44  nop     dword ptr [rax+rax+00h]
0x180202d49  mov     rcx, r14; ho
0x180202d4c  call    cs:__imp_DeleteObject
0x180202d53  nop     dword ptr [rax+rax+00h]
0x180202d58  mov     rcx, [rbp+0B0h+var_38]
0x180202d5c  xor     rcx, rsp; StackCookie
0x180202d5f  call    __security_check_cookie
0x180202d64  mov     rbx, [rsp+1B0h+arg_10]
0x180202d6c  add     rsp, 180h
0x180202d73  pop     r15
0x180202d75  pop     r14
0x180202d77  pop     r13
0x180202d79  pop     r12
0x180202d7b  pop     rdi
0x180202d7c  pop     rsi
0x180202d7d  pop     rbp
0x180202d7e  retn
```

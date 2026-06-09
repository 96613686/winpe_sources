# DWriteCore::Binding::Windows::OutlineRenderer::Close(void)

- ea: `0x180294230`
- end: `0x1802943b8`
- name: `?Close@OutlineRenderer@Windows@Binding@DWriteCore@@UEAAJXZ`
- size: `392`
- prototype: `__int64 __fastcall(DWriteCore::Binding::Windows::OutlineRenderer *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180212490`
- `0x1802941ec`
- `0x180294230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180294276`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180294276`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1802942f8`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180294371`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1802942f8`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180294371`
- `ext-ms-win-gdi-dc-l1-2-0!SetDCBrushColor` at `0x1802942c9`
- `ext-ms-win-gdi-dc-l1-2-0!SetDCBrushColor` at `0x18029437e`
- `ext-ms-win-gdi-dc-l1-2-0!SetDCBrushColor` at `0x1802942c9`
- `ext-ms-win-gdi-dc-l1-2-0!SetDCBrushColor` at `0x18029437e`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x1802942db`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x1802942db`
- `ext-ms-win-gdi-draw-l1-1-0!SetWorldTransform` at `0x1802942b4`
- `ext-ms-win-gdi-draw-l1-1-0!SetWorldTransform` at `0x1802942b4`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180294362`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180294362`
- `ext-ms-win-gdi-path-l1-1-0!EndPath` at `0x180294281`
- `ext-ms-win-gdi-path-l1-1-0!EndPath` at `0x180294281`
- `ext-ms-win-gdi-path-l1-1-0!FillPath` at `0x18029430d`
- `ext-ms-win-gdi-path-l1-1-0!FillPath` at `0x18029430d`
- `ext-ms-win-gdi-path-l1-1-0!PathToRegion` at `0x18029431f`
- `ext-ms-win-gdi-path-l1-1-0!PathToRegion` at `0x18029431f`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!FillRgn` at `0x18029433c`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!FillRgn` at `0x18029433c`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!GetRgnBox` at `0x180294353`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!GetRgnBox` at `0x180294353`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DWriteCore::Binding::Windows::OutlineRenderer::Close(
        DWriteCore::Binding::Windows::OutlineRenderer *this)
{
  unsigned int *v2; // rsi
  __int64 result; // rax
  BOOL v4; // eax
  HDC v5; // r14
  COLORREF v6; // r13d
  HBRUSH StockObject; // r15
  HDC v8; // r12
  HDC v9; // rcx
  BOOL v10; // edx
  HRGN v11; // rax
  HRGN v12; // rbx
  BOOL v13; // edx
  DWriteCore *v14; // rcx
  HGDIOBJ h; // [rsp+38h] [rbp-70h]
  XFORM xf; // [rsp+60h] [rbp-48h] BYREF

  v2 = (unsigned int *)((char *)this + 80);
  result = *((unsigned int *)this + 20);
  if ( !(_DWORD)result )
  {
    SetLastError(0);
    v4 = EndPath(*((HDC *)this + 3));
    try
    {
      DWriteCore::Binding::Windows::OutlineRenderer::CheckBoolReturn(this, v4);
      *((_BYTE *)this + 60) = 0;
      *(__m128i *)&xf.eM11 = _mm_load_si128((const __m128i *)&_xmm);
      *(_QWORD *)&xf.eDx = 0;
      SetWorldTransform(*((HDC *)this + 3), &xf);
      v5 = (HDC)*((_QWORD *)this + 3);
      v6 = SetDCBrushColor(v5, *((_DWORD *)this + 8));
      StockObject = (HBRUSH)GetStockObject(18);
      v8 = (HDC)*((_QWORD *)this + 3);
      h = SelectObject(v8, StockObject);
      v9 = (HDC)*((_QWORD *)this + 3);
      if ( *((_BYTE *)this + 61) )
      {
        v11 = PathToRegion(v9);
        v12 = v11;
        if ( v11 )
        {
          v13 = FillRgn(*((HDC *)this + 3), v11, StockObject);
          DWriteCore::Binding::Windows::OutlineRenderer::CheckBoolReturn(this, v13);
          GetRgnBox(v12, (LPRECT)this + 4);
        }
        if ( v12 )
          DeleteObject(v12);
      }
      else
      {
        v10 = FillPath(v9);
        DWriteCore::Binding::Windows::OutlineRenderer::CheckBoolReturn(this, v10);
      }
      SelectObject(v8, h);
      SetDCBrushColor(v5, v6);
    }
    catch ( ... )
    {
      DWriteCore::MapExceptionToHresult(v14);
    }
    return *v2;
  }
  return result;
}

```

## disassembly

```asm
0x180294230  mov     [rsp+arg_8], rbx
0x180294235  mov     [rsp+arg_10], rsi
0x18029423a  push    rdi
0x18029423b  push    r12
0x18029423d  push    r13
0x18029423f  push    r14
0x180294241  push    r15
0x180294243  sub     rsp, 80h
0x18029424a  mov     rax, cs:__security_cookie
0x180294251  xor     rax, rsp
0x180294254  mov     [rsp+0A8h+var_30], rax
0x180294259  mov     rdi, rcx
0x18029425c  mov     [rsp+0A8h+var_88], rcx
0x180294261  lea     rsi, [rcx+50h]
0x180294265  mov     [rsp+0A8h+var_80], rsi
0x18029426a  mov     eax, [rsi]
0x18029426c  test    eax, eax
0x18029426e  jnz     loc_18029438E
0x180294274  xor     ecx, ecx; dwErrCode
0x180294276  call    cs:__imp_SetLastError
0x18029427c  nop
0x18029427d  mov     rcx, [rdi+18h]; hdc
0x180294281  call    cs:__imp_EndPath
0x180294287  mov     edx, eax; int
0x180294289  mov     rcx, rdi; this
0x18029428c  call    ?CheckBoolReturn@OutlineRenderer@Windows@Binding@DWriteCore@@AEAAXH@Z; DWriteCore::Binding::Windows::OutlineRenderer::CheckBoolReturn(int)
0x180294291  mov     byte ptr [rdi+3Ch], 0
0x180294295  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x18029429d  movups  xmmword ptr [rsp+0A8h+xf.eM11], xmm0
0x1802942a2  mov     qword ptr [rsp+0A8h+xf.eDx], 0
0x1802942ab  lea     rdx, [rsp+0A8h+xf]; lpxf
0x1802942b0  mov     rcx, [rdi+18h]; hdc
0x1802942b4  call    cs:__imp_SetWorldTransform
0x1802942ba  mov     r14, [rdi+18h]
0x1802942be  mov     [rsp+0A8h+var_60], r14
0x1802942c3  mov     edx, [rdi+20h]; color
0x1802942c6  mov     rcx, r14; hdc
0x1802942c9  call    cs:__imp_SetDCBrushColor
0x1802942cf  mov     r13d, eax
0x1802942d2  mov     [rsp+0A8h+var_58], eax
0x1802942d6  mov     ecx, 12h; i
0x1802942db  call    cs:__imp_GetStockObject
0x1802942e1  mov     r15, rax
0x1802942e4  mov     [rsp+0A8h+var_50], rax
0x1802942e9  mov     r12, [rdi+18h]
0x1802942ed  mov     [rsp+0A8h+var_78], r12
0x1802942f2  mov     rdx, rax; h
0x1802942f5  mov     rcx, r12; hdc
0x1802942f8  call    cs:__imp_SelectObject
0x1802942fe  mov     [rsp+0A8h+h], rax
0x180294303  mov     rcx, [rdi+18h]; hdc
0x180294307  cmp     byte ptr [rdi+3Dh], 0
0x18029430b  jnz     short loc_18029431F
0x18029430d  call    cs:__imp_FillPath
0x180294313  mov     edx, eax; int
0x180294315  mov     rcx, rdi; this
0x180294318  call    ?CheckBoolReturn@OutlineRenderer@Windows@Binding@DWriteCore@@AEAAXH@Z; DWriteCore::Binding::Windows::OutlineRenderer::CheckBoolReturn(int)
0x18029431d  jmp     short loc_180294369
0x18029431f  call    cs:__imp_PathToRegion
0x180294325  mov     rbx, rax
0x180294328  mov     [rsp+0A8h+var_68], rax
0x18029432d  test    rax, rax
0x180294330  jz      short loc_18029435A
0x180294332  mov     r8, r15; hbr
0x180294335  mov     rdx, rax; hrgn
0x180294338  mov     rcx, [rdi+18h]; hdc
0x18029433c  call    cs:__imp_FillRgn
0x180294342  mov     edx, eax; int
0x180294344  mov     rcx, rdi; this
0x180294347  call    ?CheckBoolReturn@OutlineRenderer@Windows@Binding@DWriteCore@@AEAAXH@Z; DWriteCore::Binding::Windows::OutlineRenderer::CheckBoolReturn(int)
0x18029434c  lea     rdx, [rdi+40h]; lprc
0x180294350  mov     rcx, rbx; hrgn
0x180294353  call    cs:__imp_GetRgnBox
0x180294359  nop
0x18029435a  test    rbx, rbx
0x18029435d  jz      short loc_180294369
0x18029435f  mov     rcx, rbx; ho
0x180294362  call    cs:__imp_DeleteObject
0x180294368  nop
0x180294369  mov     rdx, [rsp+0A8h+h]; h
0x18029436e  mov     rcx, r12; hdc
0x180294371  call    cs:__imp_SelectObject
0x180294377  nop
0x180294378  mov     edx, r13d; color
0x18029437b  mov     rcx, r14; hdc
0x18029437e  call    cs:__imp_SetDCBrushColor
0x180294384  nop
0x180294385  jmp     short loc_18029438C
0x180294387  mov     rsi, [rsp+0A8h+var_80]
0x18029438c  mov     eax, [rsi]
0x18029438e  mov     rcx, [rsp+0A8h+var_30]
0x180294393  xor     rcx, rsp; StackCookie
0x180294396  call    __security_check_cookie
0x18029439b  lea     r11, [rsp+0A8h+var_28]
0x1802943a3  mov     rbx, [r11+38h]
0x1802943a7  mov     rsi, [r11+40h]
0x1802943ab  mov     rsp, r11
0x1802943ae  pop     r15
0x1802943b0  pop     r14
0x1802943b2  pop     r13
0x1802943b4  pop     r12
0x1802943b6  pop     rdi
0x1802943b7  retn
```

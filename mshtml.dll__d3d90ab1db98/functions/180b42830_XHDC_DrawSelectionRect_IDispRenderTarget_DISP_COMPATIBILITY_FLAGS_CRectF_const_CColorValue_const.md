# XHDC::DrawSelectionRect(IDispRenderTarget::DISP_COMPATIBILITY_FLAGS,CRectF const &,CColorValue const &)

- ea: `0x180b42830`
- end: `0x180b42a6d`
- name: `?DrawSelectionRect@XHDC@@UEBAJW4DISP_COMPATIBILITY_FLAGS@IDispRenderTarget@@AEBVCRectF@@AEBUCColorValue@@@Z`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800c8650`
- `0x180238718`
- `0x1802be988`
- `0x180b42830`

## import_xrefs

- `GDI32!SetBrushOrgEx` at `0x180b42945`
- `GDI32!SetBrushOrgEx` at `0x180b42945`
- `GDI32!CreatePatternBrush` at `0x180b4292a`
- `GDI32!CreatePatternBrush` at `0x180b4292a`
- `GDI32!CreateBitmap` at `0x180b42918`
- `GDI32!CreateBitmap` at `0x180b42918`
- `GDI32!PatBlt` at `0x180b429ac`
- `GDI32!PatBlt` at `0x180b429f5`
- `GDI32!PatBlt` at `0x180b429ac`
- `GDI32!PatBlt` at `0x180b429f5`
- `GDI32!DeleteObject` at `0x180b42a17`
- `GDI32!DeleteObject` at `0x180b42a26`
- `GDI32!DeleteObject` at `0x180b42a17`
- `GDI32!DeleteObject` at `0x180b42a26`
- `GDI32!SelectObject` at `0x180b42958`
- `GDI32!SelectObject` at `0x180b42a08`
- `GDI32!SelectObject` at `0x180b42958`
- `GDI32!SelectObject` at `0x180b42a08`
- `GDI32!SetTextColor` at `0x180b4296d`
- `GDI32!SetTextColor` at `0x180b429c9`
- `GDI32!SetTextColor` at `0x180b42a39`
- `GDI32!SetTextColor` at `0x180b4296d`
- `GDI32!SetTextColor` at `0x180b429c9`
- `GDI32!SetTextColor` at `0x180b42a39`
- `GDI32!SetBkColor` at `0x180b428ed`
- `GDI32!SetBkColor` at `0x180b42a4d`
- `GDI32!SetBkColor` at `0x180b428ed`
- `GDI32!SetBkColor` at `0x180b42a4d`

## pseudocode

```c
__int64 __fastcall XHDC::DrawSelectionRect(__int64 a1, __int64 a2, float *a3, CColorValue *a4)
{
  CWorldTransform *v5; // rcx
  int v6; // ebx
  int v7; // esi
  int v8; // edi
  COLORREF ColorRef; // eax
  HBITMAP Bitmap; // r13
  HBRUSH PatternBrush; // r12
  HGDIOBJ v12; // r14
  COLORREF v13; // eax
  int v14; // ebp
  COLORREF v15; // r15d
  int v16; // edi
  int v17; // esi
  COLORREF y; // [rsp+30h] [rbp-68h]
  int x[24]; // [rsp+38h] [rbp-60h] BYREF

  v5 = *(CWorldTransform **)(a1 + 112);
  *(_OWORD *)x = 0;
  if ( v5 )
    CWorldTransform::GetBoundingRectAfterTransform(v5, (const struct CRectF *)a3, (struct CRect *)x, 0);
  else
    CRect::SetRect((CRect *)x, *a3, a3[1], a3[2], a3[3], 0);
  v6 = x[0];
  if ( x[0] )
    v7 = x[0] - x[0] % 8;
  else
    v7 = 0;
  v8 = x[1];
  if ( x[1] )
    v8 = x[1] - x[1] % 8;
  ColorRef = CColorValue::GetColorRef(a4);
  y = SetBkColor(*(HDC *)(a1 + 32), ColorRef);
  Bitmap = CreateBitmap(8, 8, 1u, 1u, qword_1815B5570);
  PatternBrush = CreatePatternBrush(Bitmap);
  SetBrushOrgEx(*(HDC *)(a1 + 32), v7, v8, 0);
  v12 = SelectObject(*(HDC *)(a1 + 32), PatternBrush);
  v13 = SetTextColor(*(HDC *)(a1 + 32), 0);
  v14 = x[1];
  v15 = v13;
  v16 = x[2] - v6;
  v17 = x[3] - x[1];
  PatBlt(*(HDC *)(a1 + 32), v6, x[1], x[2] - v6, x[3] - x[1], 0xFA0089u);
  SetTextColor(*(HDC *)(a1 + 32), 0xFFFFFFu);
  PatBlt(*(HDC *)(a1 + 32), v6, v14, v16, v17, 0xA000C9u);
  SelectObject(*(HDC *)(a1 + 32), v12);
  DeleteObject(PatternBrush);
  DeleteObject(Bitmap);
  SetTextColor(*(HDC *)(a1 + 32), v15);
  SetBkColor(*(HDC *)(a1 + 32), y);
  return 0;
}

```

## disassembly

```asm
0x180b42830  mov     rax, rsp
0x180b42833  mov     [rax+20h], r9
0x180b42837  mov     [rax+18h], r8
0x180b4283b  mov     [rax+10h], edx
0x180b4283e  mov     [rax+8], rcx
0x180b42842  push    rbx
0x180b42843  push    rbp
0x180b42844  push    rsi
0x180b42845  push    rdi
0x180b42846  push    r12
0x180b42848  push    r13
0x180b4284a  push    r14
0x180b4284c  push    r15
0x180b4284e  sub     rsp, 58h
0x180b42852  mov     rbp, rcx
0x180b42855  xorps   xmm0, xmm0
0x180b42858  mov     rcx, [rcx+70h]; this
0x180b4285c  movdqu  xmmword ptr [rax-60h], xmm0
0x180b42861  test    rcx, rcx
0x180b42864  jnz     short loc_180B42891
0x180b42866  mov     [rax-70h], ecx
0x180b42869  mov     rax, r8
0x180b4286c  lea     rcx, [rsp+98h+x]; this
0x180b42871  movss   xmm0, dword ptr [rax+0Ch]
0x180b42876  movss   xmm3, dword ptr [rax+8]; float
0x180b4287b  movss   xmm2, dword ptr [rax+4]; float
0x180b42880  movss   xmm1, dword ptr [rax]; float
0x180b42884  movss   dword ptr [rsp+98h+lpBits], xmm0; float
0x180b4288a  call    ?SetRect@CRect@@QEAAXMMMMH@Z; CRect::SetRect(float,float,float,float,int)
0x180b4288f  jmp     short loc_180B428A6
0x180b42891  mov     rdx, [rsp+98h+arg_10]; struct CRectF *
0x180b42899  lea     r8, [rsp+98h+x]; struct CRect *
0x180b4289e  xor     r9d, r9d; bool
0x180b428a1  call    ?GetBoundingRectAfterTransform@CWorldTransform@@QEBAXPEBVCRectF@@PEAVCRect@@_N@Z; CWorldTransform::GetBoundingRectAfterTransform(CRectF const *,CRect *,bool)
0x180b428a6  mov     rbx, qword ptr [rsp+98h+x]
0x180b428ab  mov     r14d, 8
0x180b428b1  mov     qword ptr [rsp+98h+y], rbx
0x180b428b6  test    ebx, ebx
0x180b428b8  jz      short loc_180B428C6
0x180b428ba  mov     eax, ebx
0x180b428bc  mov     esi, ebx
0x180b428be  cdq
0x180b428bf  idiv    r14d
0x180b428c2  sub     esi, edx
0x180b428c4  jmp     short loc_180B428CA
0x180b428c6  mov     esi, [rsp+98h+y]
0x180b428ca  mov     edi, [rsp+98h+y+4]
0x180b428ce  test    edi, edi
0x180b428d0  jz      short loc_180B428DA
0x180b428d2  mov     eax, edi
0x180b428d4  cdq
0x180b428d5  idiv    r14d
0x180b428d8  sub     edi, edx
0x180b428da  mov     rcx, [rsp+98h+arg_18]; this
0x180b428e2  call    ?GetColorRef@CColorValue@@QEBAKXZ; CColorValue::GetColorRef(void)
0x180b428e7  mov     rcx, [rbp+20h]; hdc
0x180b428eb  mov     edx, eax; color
0x180b428ed  call    cs:__imp_SetBkColor
0x180b428f4  nop     dword ptr [rax+rax+00h]
0x180b428f9  mov     [rsp+98h+y], eax
0x180b428fd  mov     r8d, 1; nPlanes
0x180b42903  lea     rax, qword_1815B5570
0x180b4290a  mov     edx, r14d; nHeight
0x180b4290d  mov     r9d, r8d; nBitCount
0x180b42910  mov     [rsp+98h+lpBits], rax; lpBits
0x180b42915  mov     ecx, r14d; nWidth
0x180b42918  call    cs:__imp_CreateBitmap
0x180b4291f  nop     dword ptr [rax+rax+00h]
0x180b42924  mov     rcx, rax; hbm
0x180b42927  mov     r13, rax
0x180b4292a  call    cs:__imp_CreatePatternBrush
0x180b42931  nop     dword ptr [rax+rax+00h]
0x180b42936  mov     rcx, [rbp+20h]; hdc
0x180b4293a  xor     r9d, r9d; lppt
0x180b4293d  mov     r8d, edi; y
0x180b42940  mov     edx, esi; x
0x180b42942  mov     r12, rax
0x180b42945  call    cs:__imp_SetBrushOrgEx
0x180b4294c  nop     dword ptr [rax+rax+00h]
0x180b42951  mov     rcx, [rbp+20h]; hdc
0x180b42955  mov     rdx, r12; h
0x180b42958  call    cs:__imp_SelectObject
0x180b4295f  nop     dword ptr [rax+rax+00h]
0x180b42964  mov     rcx, [rbp+20h]; hdc
0x180b42968  xor     edx, edx; color
0x180b4296a  mov     r14, rax
0x180b4296d  call    cs:__imp_SetTextColor
0x180b42974  nop     dword ptr [rax+rax+00h]
0x180b42979  mov     ebp, [rsp+98h+x+4]
0x180b4297d  mov     edx, ebx; x
0x180b4297f  mov     rcx, [rsp+98h+arg_0]
0x180b42987  mov     r8d, ebp; y
0x180b4298a  mov     edi, [rsp+98h+var_58]
0x180b4298e  mov     r15d, eax
0x180b42991  mov     esi, [rsp+98h+var_54]
0x180b42995  sub     edi, ebx
0x180b42997  sub     esi, ebp
0x180b42999  mov     [rsp+98h+rop], 0FA0089h; rop
0x180b429a1  mov     rcx, [rcx+20h]; hdc
0x180b429a5  mov     r9d, edi; w
0x180b429a8  mov     dword ptr [rsp+98h+lpBits], esi; h
0x180b429ac  call    cs:__imp_PatBlt
0x180b429b3  nop     dword ptr [rax+rax+00h]
0x180b429b8  mov     rax, [rsp+98h+arg_0]
0x180b429c0  mov     edx, 0FFFFFFh; color
0x180b429c5  mov     rcx, [rax+20h]; hdc
0x180b429c9  call    cs:__imp_SetTextColor
0x180b429d0  nop     dword ptr [rax+rax+00h]
0x180b429d5  mov     edx, ebx; x
0x180b429d7  mov     [rsp+98h+rop], 0A000C9h; rop
0x180b429df  mov     rbx, [rsp+98h+arg_0]
0x180b429e7  mov     r9d, edi; w
0x180b429ea  mov     r8d, ebp; y
0x180b429ed  mov     dword ptr [rsp+98h+lpBits], esi; h
0x180b429f1  mov     rcx, [rbx+20h]; hdc
0x180b429f5  call    cs:__imp_PatBlt
0x180b429fc  nop     dword ptr [rax+rax+00h]
0x180b42a01  mov     rcx, [rbx+20h]; hdc
0x180b42a05  mov     rdx, r14; h
0x180b42a08  call    cs:__imp_SelectObject
0x180b42a0f  nop     dword ptr [rax+rax+00h]
0x180b42a14  mov     rcx, r12; ho
0x180b42a17  call    cs:__imp_DeleteObject
0x180b42a1e  nop     dword ptr [rax+rax+00h]
0x180b42a23  mov     rcx, r13; ho
0x180b42a26  call    cs:__imp_DeleteObject
0x180b42a2d  nop     dword ptr [rax+rax+00h]
0x180b42a32  mov     rcx, [rbx+20h]; hdc
0x180b42a36  mov     edx, r15d; color
0x180b42a39  call    cs:__imp_SetTextColor
0x180b42a40  nop     dword ptr [rax+rax+00h]
0x180b42a45  mov     edx, [rsp+98h+y]; color
0x180b42a49  mov     rcx, [rbx+20h]; hdc
0x180b42a4d  call    cs:__imp_SetBkColor
0x180b42a54  nop     dword ptr [rax+rax+00h]
0x180b42a59  xor     eax, eax
0x180b42a5b  add     rsp, 58h
0x180b42a5f  pop     r15
0x180b42a61  pop     r14
0x180b42a63  pop     r13
0x180b42a65  pop     r12
0x180b42a67  pop     rdi
0x180b42a68  pop     rsi
0x180b42a69  pop     rbp
0x180b42a6a  pop     rbx
0x180b42a6b  retn
```

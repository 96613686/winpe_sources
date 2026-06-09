# XHDC::DrawSelectionRect(IDispRenderTarget::DISP_COMPATIBILITY_FLAGS,CRectF const &,CColorValue const &)

- ea: `0x180b2b350`
- end: `0x180b2b538`
- name: `?DrawSelectionRect@XHDC@@UEBAJW4DISP_COMPATIBILITY_FLAGS@IDispRenderTarget@@AEBVCRectF@@AEBUCColorValue@@@Z`
- size: `488`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18008681c`
- `0x18023cf50`
- `0x180408190`
- `0x180b2b350`

## import_xrefs

- `GDI32!SetBrushOrgEx` at `0x180b2b453`
- `GDI32!SetBrushOrgEx` at `0x180b2b453`
- `GDI32!CreatePatternBrush` at `0x180b2b43e`
- `GDI32!CreatePatternBrush` at `0x180b2b43e`
- `GDI32!CreateBitmap` at `0x180b2b432`
- `GDI32!CreateBitmap` at `0x180b2b432`
- `GDI32!PatBlt` at `0x180b2b4a8`
- `GDI32!PatBlt` at `0x180b2b4e5`
- `GDI32!PatBlt` at `0x180b2b4a8`
- `GDI32!PatBlt` at `0x180b2b4e5`
- `GDI32!DeleteObject` at `0x180b2b4fb`
- `GDI32!DeleteObject` at `0x180b2b504`
- `GDI32!DeleteObject` at `0x180b2b4fb`
- `GDI32!DeleteObject` at `0x180b2b504`
- `GDI32!SelectObject` at `0x180b2b460`
- `GDI32!SelectObject` at `0x180b2b4f2`
- `GDI32!SelectObject` at `0x180b2b460`
- `GDI32!SelectObject` at `0x180b2b4f2`
- `GDI32!SetTextColor` at `0x180b2b46f`
- `GDI32!SetTextColor` at `0x180b2b4bf`
- `GDI32!SetTextColor` at `0x180b2b511`
- `GDI32!SetTextColor` at `0x180b2b46f`
- `GDI32!SetTextColor` at `0x180b2b4bf`
- `GDI32!SetTextColor` at `0x180b2b511`
- `GDI32!SetBkColor` at `0x180b2b40d`
- `GDI32!SetBkColor` at `0x180b2b51f`
- `GDI32!SetBkColor` at `0x180b2b40d`
- `GDI32!SetBkColor` at `0x180b2b51f`

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
  Bitmap = CreateBitmap(8, 8, 1u, 1u, &unk_181582470);
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
0x180b2b350  mov     rax, rsp
0x180b2b353  mov     [rax+20h], r9
0x180b2b357  mov     [rax+18h], r8
0x180b2b35b  mov     [rax+10h], edx
0x180b2b35e  mov     [rax+8], rcx
0x180b2b362  push    rbx
0x180b2b363  push    rbp
0x180b2b364  push    rsi
0x180b2b365  push    rdi
0x180b2b366  push    r12
0x180b2b368  push    r13
0x180b2b36a  push    r14
0x180b2b36c  push    r15
0x180b2b36e  sub     rsp, 58h
0x180b2b372  mov     rbp, rcx
0x180b2b375  xorps   xmm0, xmm0
0x180b2b378  mov     rcx, [rcx+70h]; this
0x180b2b37c  movdqu  xmmword ptr [rax-60h], xmm0
0x180b2b381  test    rcx, rcx
0x180b2b384  jnz     short loc_180B2B3B1
0x180b2b386  mov     [rax-70h], ecx
0x180b2b389  mov     rax, r8
0x180b2b38c  lea     rcx, [rsp+98h+x]; this
0x180b2b391  movss   xmm0, dword ptr [rax+0Ch]
0x180b2b396  movss   xmm3, dword ptr [rax+8]; float
0x180b2b39b  movss   xmm2, dword ptr [rax+4]; float
0x180b2b3a0  movss   xmm1, dword ptr [rax]; float
0x180b2b3a4  movss   dword ptr [rsp+98h+lpBits], xmm0; float
0x180b2b3aa  call    ?SetRect@CRect@@QEAAXMMMMH@Z; CRect::SetRect(float,float,float,float,int)
0x180b2b3af  jmp     short loc_180B2B3C6
0x180b2b3b1  mov     rdx, [rsp+98h+arg_10]; struct CRectF *
0x180b2b3b9  lea     r8, [rsp+98h+x]; struct CRect *
0x180b2b3be  xor     r9d, r9d; bool
0x180b2b3c1  call    ?GetBoundingRectAfterTransform@CWorldTransform@@QEBAXPEBVCRectF@@PEAVCRect@@_N@Z; CWorldTransform::GetBoundingRectAfterTransform(CRectF const *,CRect *,bool)
0x180b2b3c6  mov     rbx, qword ptr [rsp+98h+x]
0x180b2b3cb  mov     r14d, 8
0x180b2b3d1  mov     qword ptr [rsp+98h+y], rbx
0x180b2b3d6  test    ebx, ebx
0x180b2b3d8  jz      short loc_180B2B3E6
0x180b2b3da  mov     eax, ebx
0x180b2b3dc  mov     esi, ebx
0x180b2b3de  cdq
0x180b2b3df  idiv    r14d
0x180b2b3e2  sub     esi, edx
0x180b2b3e4  jmp     short loc_180B2B3EA
0x180b2b3e6  mov     esi, [rsp+98h+y]
0x180b2b3ea  mov     edi, [rsp+98h+y+4]
0x180b2b3ee  test    edi, edi
0x180b2b3f0  jz      short loc_180B2B3FA
0x180b2b3f2  mov     eax, edi
0x180b2b3f4  cdq
0x180b2b3f5  idiv    r14d
0x180b2b3f8  sub     edi, edx
0x180b2b3fa  mov     rcx, [rsp+98h+arg_18]; this
0x180b2b402  call    ?GetColorRef@CColorValue@@QEBAKXZ; CColorValue::GetColorRef(void)
0x180b2b407  mov     rcx, [rbp+20h]; hdc
0x180b2b40b  mov     edx, eax; color
0x180b2b40d  call    cs:__imp_SetBkColor
0x180b2b413  mov     [rsp+98h+y], eax
0x180b2b417  mov     r8d, 1; nPlanes
0x180b2b41d  lea     rax, unk_181582470
0x180b2b424  mov     edx, r14d; nHeight
0x180b2b427  mov     r9d, r8d; nBitCount
0x180b2b42a  mov     [rsp+98h+lpBits], rax; lpBits
0x180b2b42f  mov     ecx, r14d; nWidth
0x180b2b432  call    cs:__imp_CreateBitmap
0x180b2b438  mov     rcx, rax; hbm
0x180b2b43b  mov     r13, rax
0x180b2b43e  call    cs:__imp_CreatePatternBrush
0x180b2b444  mov     rcx, [rbp+20h]; hdc
0x180b2b448  xor     r9d, r9d; lppt
0x180b2b44b  mov     r8d, edi; y
0x180b2b44e  mov     edx, esi; x
0x180b2b450  mov     r12, rax
0x180b2b453  call    cs:__imp_SetBrushOrgEx
0x180b2b459  mov     rcx, [rbp+20h]; hdc
0x180b2b45d  mov     rdx, r12; h
0x180b2b460  call    cs:__imp_SelectObject
0x180b2b466  mov     rcx, [rbp+20h]; hdc
0x180b2b46a  xor     edx, edx; color
0x180b2b46c  mov     r14, rax
0x180b2b46f  call    cs:__imp_SetTextColor
0x180b2b475  mov     ebp, [rsp+98h+x+4]
0x180b2b479  mov     edx, ebx; x
0x180b2b47b  mov     rcx, [rsp+98h+arg_0]
0x180b2b483  mov     r8d, ebp; y
0x180b2b486  mov     edi, [rsp+98h+var_58]
0x180b2b48a  mov     r15d, eax
0x180b2b48d  mov     esi, [rsp+98h+var_54]
0x180b2b491  sub     edi, ebx
0x180b2b493  sub     esi, ebp
0x180b2b495  mov     [rsp+98h+rop], 0FA0089h; rop
0x180b2b49d  mov     rcx, [rcx+20h]; hdc
0x180b2b4a1  mov     r9d, edi; w
0x180b2b4a4  mov     dword ptr [rsp+98h+lpBits], esi; h
0x180b2b4a8  call    cs:__imp_PatBlt
0x180b2b4ae  mov     rax, [rsp+98h+arg_0]
0x180b2b4b6  mov     edx, 0FFFFFFh; color
0x180b2b4bb  mov     rcx, [rax+20h]; hdc
0x180b2b4bf  call    cs:__imp_SetTextColor
0x180b2b4c5  mov     edx, ebx; x
0x180b2b4c7  mov     [rsp+98h+rop], 0A000C9h; rop
0x180b2b4cf  mov     rbx, [rsp+98h+arg_0]
0x180b2b4d7  mov     r9d, edi; w
0x180b2b4da  mov     r8d, ebp; y
0x180b2b4dd  mov     dword ptr [rsp+98h+lpBits], esi; h
0x180b2b4e1  mov     rcx, [rbx+20h]; hdc
0x180b2b4e5  call    cs:__imp_PatBlt
0x180b2b4eb  mov     rcx, [rbx+20h]; hdc
0x180b2b4ef  mov     rdx, r14; h
0x180b2b4f2  call    cs:__imp_SelectObject
0x180b2b4f8  mov     rcx, r12; ho
0x180b2b4fb  call    cs:__imp_DeleteObject
0x180b2b501  mov     rcx, r13; ho
0x180b2b504  call    cs:__imp_DeleteObject
0x180b2b50a  mov     rcx, [rbx+20h]; hdc
0x180b2b50e  mov     edx, r15d; color
0x180b2b511  call    cs:__imp_SetTextColor
0x180b2b517  mov     edx, [rsp+98h+y]; color
0x180b2b51b  mov     rcx, [rbx+20h]; hdc
0x180b2b51f  call    cs:__imp_SetBkColor
0x180b2b525  xor     eax, eax
0x180b2b527  add     rsp, 58h
0x180b2b52b  pop     r15
0x180b2b52d  pop     r14
0x180b2b52f  pop     r13
0x180b2b531  pop     r12
0x180b2b533  pop     rdi
0x180b2b534  pop     rsi
0x180b2b535  pop     rbp
0x180b2b536  pop     rbx
0x180b2b537  retn
```

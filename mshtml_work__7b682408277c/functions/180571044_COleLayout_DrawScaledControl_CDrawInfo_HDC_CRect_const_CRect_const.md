# COleLayout::DrawScaledControl(CDrawInfo *,HDC__ *,CRect const *,CRect const *)

- ea: `0x180571044`
- end: `0x1805712fe`
- name: `?DrawScaledControl@COleLayout@@AEAAXPEAVCDrawInfo@@PEAUHDC__@@PEBVCRect@@2@Z`
- size: `698`
- prototype: `void __fastcall(COleLayout *__hidden this, struct CDrawInfo *, HDC, const struct CRect *, const struct CRect *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180570400`

## callees

- `0x180571044`
- `0x180e636c0`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `GDI32!DeleteDC` at `0x1805712a6`
- `GDI32!DeleteDC` at `0x1805712a6`
- `GDI32!SetStretchBltMode` at `0x1805710a8`
- `GDI32!SetStretchBltMode` at `0x1805712b8`
- `GDI32!SetStretchBltMode` at `0x1805710a8`
- `GDI32!SetStretchBltMode` at `0x1805712b8`
- `GDI32!SetBrushOrgEx` at `0x1805710c3`
- `GDI32!SetBrushOrgEx` at `0x1805712d1`
- `GDI32!SetBrushOrgEx` at `0x1805710c3`
- `GDI32!SetBrushOrgEx` at `0x1805712d1`
- `GDI32!StretchBlt` at `0x18057118f`
- `GDI32!StretchBlt` at `0x180571275`
- `GDI32!StretchBlt` at `0x18057118f`
- `GDI32!StretchBlt` at `0x180571275`
- `GDI32!OffsetViewportOrgEx` at `0x1805710f5`
- `GDI32!OffsetViewportOrgEx` at `0x1805710f5`
- `GDI32!DeleteObject` at `0x180571297`
- `GDI32!DeleteObject` at `0x180571297`
- `GDI32!SelectObject` at `0x18057112f`
- `GDI32!SelectObject` at `0x180571288`
- `GDI32!SelectObject` at `0x18057112f`
- `GDI32!SelectObject` at `0x180571288`
- `GDI32!CreateCompatibleBitmap` at `0x180571111`
- `GDI32!CreateCompatibleBitmap` at `0x180571111`
- `GDI32!CreateCompatibleDC` at `0x1805710d2`
- `GDI32!CreateCompatibleDC` at `0x1805710d2`

## pseudocode

```c
void __fastcall COleLayout::DrawScaledControl(
        COleLayout *this,
        struct CDrawInfo *a2,
        HDC a3,
        const struct CRect *a4,
        const struct CRect *a5)
{
  int v8; // r13d
  HDC CompatibleDC; // rax
  HDC v10; // rsi
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v12; // r12
  HGDIOBJ v13; // rax
  int v14; // r9d
  COleSite *v15; // rcx
  int IsOleProxy; // eax
  __int64 v17; // r9
  int hDest; // [rsp+28h] [rbp-71h]
  int xSrc; // [rsp+38h] [rbp-61h]
  int ySrc; // [rsp+40h] [rbp-59h]
  int wSrc; // [rsp+48h] [rbp-51h]
  int hSrc; // [rsp+50h] [rbp-49h]
  struct tagPOINT pt; // [rsp+68h] [rbp-31h] BYREF
  COleSite *v24; // [rsp+70h] [rbp-29h]
  __int64 v25; // [rsp+78h] [rbp-21h]
  void (__fastcall *v26)(__int64, _QWORD, _QWORD, __int64, COleSite *, _QWORD, HDC, __int64 *, _QWORD, _QWORD, _QWORD); // [rsp+80h] [rbp-19h]
  HGDIOBJ h; // [rsp+88h] [rbp-11h]
  __int64 v28; // [rsp+90h] [rbp-9h] BYREF
  int v29; // [rsp+98h] [rbp-1h]
  int v30; // [rsp+9Ch] [rbp+3h]

  v24 = (COleSite *)*((_QWORD *)this + 2);
  pt = 0;
  v8 = SetStretchBltMode(a3, 4);
  SetBrushOrgEx(a3, 0, 0, &pt);
  CompatibleDC = CreateCompatibleDC(a3);
  v10 = CompatibleDC;
  if ( CompatibleDC )
  {
    OffsetViewportOrgEx(CompatibleDC, 0, 0, 0);
    CompatibleBitmap = CreateCompatibleBitmap(
                         a3,
                         *((_DWORD *)a4 + 2) - *(_DWORD *)a4,
                         *((_DWORD *)a4 + 3) - *((_DWORD *)a4 + 1));
    v12 = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      v13 = SelectObject(v10, CompatibleBitmap);
      v14 = *((_DWORD *)a4 + 2) - *(_DWORD *)a4;
      hSrc = *((_DWORD *)a5 + 3) - *((_DWORD *)a5 + 1);
      wSrc = *((_DWORD *)a5 + 2) - *(_DWORD *)a5;
      ySrc = *((_DWORD *)a5 + 1);
      xSrc = *(_DWORD *)a5;
      hDest = *((_DWORD *)a4 + 3) - *((_DWORD *)a4 + 1);
      h = v13;
      StretchBlt(v10, 0, 0, v14, hDest, a3, xSrc, ySrc, wSrc, hSrc, 0xCC0020u);
      v15 = v24;
      v29 = *((_DWORD *)a4 + 2) - *(_DWORD *)a4;
      v30 = *((_DWORD *)a4 + 3) - *((_DWORD *)a4 + 1);
      v25 = *((_QWORD *)v24 + 23);
      v28 = 0;
      v26 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64, COleSite *, _QWORD, HDC, __int64 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v25 + 24LL);
      v24 = (COleSite *)*((_QWORD *)a2 + 8);
      IsOleProxy = COleSite::IsOleProxy(v15);
      v17 = 0;
      if ( !IsOleProxy )
        v17 = *((_QWORD *)a2 + 7);
      v26(v25, *((unsigned int *)a2 + 11), *((unsigned int *)a2 + 13), v17, v24, 0, v10, &v28, 0, 0, 0);
      StretchBlt(
        a3,
        *(_DWORD *)a5,
        *((_DWORD *)a5 + 1),
        *((_DWORD *)a5 + 2) - *(_DWORD *)a5,
        *((_DWORD *)a5 + 3) - *((_DWORD *)a5 + 1),
        v10,
        0,
        0,
        *((_DWORD *)a4 + 2) - *(_DWORD *)a4,
        *((_DWORD *)a4 + 3) - *((_DWORD *)a4 + 1),
        0xCC0020u);
      SelectObject(v10, h);
      DeleteObject(v12);
    }
    DeleteDC(v10);
  }
  SetStretchBltMode(a3, v8);
  SetBrushOrgEx(a3, pt.x, pt.y, 0);
}

```

## disassembly

```asm
0x180571044  mov     rax, rsp
0x180571047  mov     [rax+20h], r9
0x18057104b  mov     [rax+18h], r8
0x18057104f  mov     [rax+10h], rdx
0x180571053  mov     [rax+8], rcx
0x180571057  push    rbp
0x180571058  push    rbx
0x180571059  push    rsi
0x18057105a  push    rdi
0x18057105b  push    r12
0x18057105d  push    r13
0x18057105f  push    r14
0x180571061  push    r15
0x180571063  lea     rbp, [rax-57h]
0x180571067  sub     rsp, 0A8h
0x18057106e  mov     rax, cs:__security_cookie
0x180571075  xor     rax, rsp
0x180571078  mov     [rbp+4Fh+var_48], rax
0x18057107c  mov     rax, [rbp+4Fh+arg_0]
0x180571080  mov     edx, 4; mode
0x180571085  mov     rbx, [rbp+4Fh+hdc]
0x180571089  mov     r14, [rbp+4Fh+arg_8]
0x18057108d  mov     rcx, rbx; hdc
0x180571090  mov     rdi, [rbp+4Fh+arg_18]
0x180571094  mov     rax, [rax+10h]
0x180571098  mov     r15, [rbp+4Fh+arg_20]
0x18057109c  mov     [rbp+4Fh+var_78], rax
0x1805710a0  mov     qword ptr [rbp+4Fh+pt.x], 0
0x1805710a8  call    cs:__imp_SetStretchBltMode
0x1805710af  nop     dword ptr [rax+rax+00h]
0x1805710b4  lea     r9, [rbp+4Fh+pt]; lppt
0x1805710b8  xor     r8d, r8d; y
0x1805710bb  xor     edx, edx; x
0x1805710bd  mov     rcx, rbx; hdc
0x1805710c0  mov     r13d, eax
0x1805710c3  call    cs:__imp_SetBrushOrgEx
0x1805710ca  nop     dword ptr [rax+rax+00h]
0x1805710cf  mov     rcx, rbx; hdc
0x1805710d2  call    cs:__imp_CreateCompatibleDC
0x1805710d9  nop     dword ptr [rax+rax+00h]
0x1805710de  mov     rsi, rax
0x1805710e1  test    rax, rax
0x1805710e4  jz      loc_1805712B2
0x1805710ea  xor     r9d, r9d; lppt
0x1805710ed  xor     r8d, r8d; y
0x1805710f0  xor     edx, edx; x
0x1805710f2  mov     rcx, rax; hdc
0x1805710f5  call    cs:__imp_OffsetViewportOrgEx
0x1805710fc  nop     dword ptr [rax+rax+00h]
0x180571101  mov     r8d, [rdi+0Ch]
0x180571105  mov     rcx, rbx; hdc
0x180571108  mov     edx, [rdi+8]
0x18057110b  sub     r8d, [rdi+4]; cy
0x18057110f  sub     edx, [rdi]; cx
0x180571111  call    cs:__imp_CreateCompatibleBitmap
0x180571118  nop     dword ptr [rax+rax+00h]
0x18057111d  mov     r12, rax
0x180571120  test    rax, rax
0x180571123  jz      loc_1805712A3
0x180571129  mov     rdx, rax; h
0x18057112c  mov     rcx, rsi; hdc
0x18057112f  call    cs:__imp_SelectObject
0x180571136  nop     dword ptr [rax+rax+00h]
0x18057113b  mov     r10d, [r15+4]
0x18057113f  mov     ecx, [r15+8]
0x180571143  mov     r11d, [r15]
0x180571146  sub     ecx, r11d
0x180571149  mov     edx, [r15+0Ch]
0x18057114d  mov     r8d, [rdi+0Ch]
0x180571151  sub     edx, r10d
0x180571154  sub     r8d, [rdi+4]
0x180571158  mov     r9d, [rdi+8]
0x18057115c  sub     r9d, [rdi]; wDest
0x18057115f  mov     [rsp+0E0h+hSrc+8], 0CC0020h; rop
0x180571167  mov     [rsp+0E0h+hSrc], edx; hSrc
0x18057116b  xor     edx, edx; xDest
0x18057116d  mov     [rsp+0E0h+wSrc], ecx; wSrc
0x180571171  mov     rcx, rsi; hdcDest
0x180571174  mov     [rsp+0E0h+ySrc], r10d; ySrc
0x180571179  mov     [rsp+0E0h+xSrc], r11d; xSrc
0x18057117e  mov     [rsp+0E0h+hdcSrc], rbx; hdcSrc
0x180571183  mov     [rsp+0E0h+hDest], r8d; hDest
0x180571188  xor     r8d, r8d; yDest
0x18057118b  mov     [rbp+4Fh+h], rax
0x18057118f  call    cs:__imp_StretchBlt
0x180571196  nop     dword ptr [rax+rax+00h]
0x18057119b  mov     eax, [rdi+8]
0x18057119e  sub     eax, [rdi]
0x1805711a0  mov     rcx, [rbp+4Fh+var_78]; this
0x1805711a4  mov     [rbp+4Fh+var_50], eax
0x1805711a7  mov     eax, [rdi+0Ch]
0x1805711aa  sub     eax, [rdi+4]
0x1805711ad  mov     [rbp+4Fh+var_4C], eax
0x1805711b0  mov     rax, [rcx+0B8h]
0x1805711b7  mov     [rbp+4Fh+var_70], rax
0x1805711bb  mov     [rbp+4Fh+var_58], 0
0x1805711c3  mov     rax, [rax]
0x1805711c6  mov     rax, [rax+18h]
0x1805711ca  mov     [rbp+4Fh+var_68], rax
0x1805711ce  mov     rax, [r14+40h]
0x1805711d2  mov     [rbp+4Fh+var_78], rax
0x1805711d6  call    ?IsOleProxy@COleSite@@QEAAHXZ; COleSite::IsOleProxy(void)
0x1805711db  xor     ecx, ecx
0x1805711dd  mov     r9d, ecx
0x1805711e0  test    eax, eax
0x1805711e2  jnz     short loc_1805711E8
0x1805711e4  mov     r9, [r14+38h]
0x1805711e8  mov     r8d, [r14+34h]
0x1805711ec  lea     rax, [rbp+4Fh+var_58]
0x1805711f0  mov     edx, [r14+2Ch]
0x1805711f4  mov     qword ptr [rsp+0E0h+hSrc+8], rcx
0x1805711f9  mov     qword ptr [rsp+0E0h+hSrc], rcx
0x1805711fe  mov     qword ptr [rsp+0E0h+wSrc], rcx
0x180571203  mov     qword ptr [rsp+0E0h+ySrc], rax
0x180571208  mov     rax, [rbp+4Fh+var_68]
0x18057120c  mov     qword ptr [rsp+0E0h+xSrc], rsi
0x180571211  mov     [rsp+0E0h+hdcSrc], rcx
0x180571216  mov     rcx, [rbp+4Fh+var_78]
0x18057121a  mov     qword ptr [rsp+0E0h+hDest], rcx
0x18057121f  mov     rcx, [rbp+4Fh+var_70]
0x180571223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180571228  mov     ecx, [rdi+0Ch]
0x18057122b  sub     ecx, [rdi+4]
0x18057122e  mov     eax, [rdi+8]
0x180571231  sub     eax, [rdi]
0x180571233  mov     r10d, [r15+0Ch]
0x180571237  mov     r8d, [r15+4]; yDest
0x18057123b  sub     r10d, r8d
0x18057123e  mov     r9d, [r15+8]
0x180571242  sub     r9d, [r15]; wDest
0x180571245  mov     edx, [r15]; xDest
0x180571248  mov     [rsp+0E0h+hSrc+8], 0CC0020h; rop
0x180571250  mov     [rsp+0E0h+hSrc], ecx; hSrc
0x180571254  mov     rcx, rbx; hdcDest
0x180571257  mov     [rsp+0E0h+wSrc], eax; wSrc
0x18057125b  mov     [rsp+0E0h+ySrc], 0; ySrc
0x180571263  mov     [rsp+0E0h+xSrc], 0; xSrc
0x18057126b  mov     [rsp+0E0h+hdcSrc], rsi; hdcSrc
0x180571270  mov     [rsp+0E0h+hDest], r10d; hDest
0x180571275  call    cs:__imp_StretchBlt
0x18057127c  nop     dword ptr [rax+rax+00h]
0x180571281  mov     rdx, [rbp+4Fh+h]; h
0x180571285  mov     rcx, rsi; hdc
0x180571288  call    cs:__imp_SelectObject
0x18057128f  nop     dword ptr [rax+rax+00h]
0x180571294  mov     rcx, r12; ho
0x180571297  call    cs:__imp_DeleteObject
0x18057129e  nop     dword ptr [rax+rax+00h]
0x1805712a3  mov     rcx, rsi; hdc
0x1805712a6  call    cs:__imp_DeleteDC
0x1805712ad  nop     dword ptr [rax+rax+00h]
0x1805712b2  mov     edx, r13d; mode
0x1805712b5  mov     rcx, rbx; hdc
0x1805712b8  call    cs:__imp_SetStretchBltMode
0x1805712bf  nop     dword ptr [rax+rax+00h]
0x1805712c4  mov     r8d, [rbp+4Fh+pt.y]; y
0x1805712c8  xor     r9d, r9d; lppt
0x1805712cb  mov     edx, [rbp+4Fh+pt.x]; x
0x1805712ce  mov     rcx, rbx; hdc
0x1805712d1  call    cs:__imp_SetBrushOrgEx
0x1805712d8  nop     dword ptr [rax+rax+00h]
0x1805712dd  mov     rcx, [rbp+4Fh+var_48]
0x1805712e1  xor     rcx, rsp; StackCookie
0x1805712e4  call    __security_check_cookie
0x1805712e9  add     rsp, 0A8h
0x1805712f0  pop     r15
0x1805712f2  pop     r14
0x1805712f4  pop     r13
0x1805712f6  pop     r12
0x1805712f8  pop     rdi
0x1805712f9  pop     rsi
0x1805712fa  pop     rbx
0x1805712fb  pop     rbp
0x1805712fc  retn
```

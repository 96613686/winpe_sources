# COleLayout::DrawScaledControl(CDrawInfo *,HDC__ *,CRect const *,CRect const *)

- ea: `0x1800069cc`
- end: `0x180006c37`
- name: `?DrawScaledControl@COleLayout@@AEAAXPEAVCDrawInfo@@PEAUHDC__@@PEBVCRect@@2@Z`
- size: `619`
- prototype: `void __fastcall(COleLayout *__hidden this, struct CDrawInfo *, HDC, const struct CRect *, const struct CRect *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005dc0`

## callees

- `0x1800069cc`
- `0x180e3e698`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `GDI32!DeleteDC` at `0x180006bf2`
- `GDI32!DeleteDC` at `0x180006bf2`
- `GDI32!SetStretchBltMode` at `0x180006a30`
- `GDI32!SetStretchBltMode` at `0x180006bfe`
- `GDI32!SetStretchBltMode` at `0x180006a30`
- `GDI32!SetStretchBltMode` at `0x180006bfe`
- `GDI32!SetBrushOrgEx` at `0x180006a45`
- `GDI32!SetBrushOrgEx` at `0x180006c11`
- `GDI32!SetBrushOrgEx` at `0x180006a45`
- `GDI32!SetBrushOrgEx` at `0x180006c11`
- `GDI32!StretchBlt` at `0x180006af3`
- `GDI32!StretchBlt` at `0x180006bd3`
- `GDI32!StretchBlt` at `0x180006af3`
- `GDI32!StretchBlt` at `0x180006bd3`
- `GDI32!OffsetViewportOrgEx` at `0x180006a6b`
- `GDI32!OffsetViewportOrgEx` at `0x180006a6b`
- `GDI32!DeleteObject` at `0x180006be9`
- `GDI32!DeleteObject` at `0x180006be9`
- `GDI32!SelectObject` at `0x180006a99`
- `GDI32!SelectObject` at `0x180006be0`
- `GDI32!SelectObject` at `0x180006a99`
- `GDI32!SelectObject` at `0x180006be0`
- `GDI32!CreateCompatibleBitmap` at `0x180006a81`
- `GDI32!CreateCompatibleBitmap` at `0x180006a81`
- `GDI32!CreateCompatibleDC` at `0x180006a4e`
- `GDI32!CreateCompatibleDC` at `0x180006a4e`

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
0x1800069cc  mov     rax, rsp
0x1800069cf  mov     [rax+20h], r9
0x1800069d3  mov     [rax+18h], r8
0x1800069d7  mov     [rax+10h], rdx
0x1800069db  mov     [rax+8], rcx
0x1800069df  push    rbp
0x1800069e0  push    rbx
0x1800069e1  push    rsi
0x1800069e2  push    rdi
0x1800069e3  push    r12
0x1800069e5  push    r13
0x1800069e7  push    r14
0x1800069e9  push    r15
0x1800069eb  lea     rbp, [rax-57h]
0x1800069ef  sub     rsp, 0A8h
0x1800069f6  mov     rax, cs:__security_cookie
0x1800069fd  xor     rax, rsp
0x180006a00  mov     [rbp+4Fh+var_48], rax
0x180006a04  mov     rax, [rbp+4Fh+arg_0]
0x180006a08  mov     edx, 4; mode
0x180006a0d  mov     rbx, [rbp+4Fh+hdc]
0x180006a11  mov     r14, [rbp+4Fh+arg_8]
0x180006a15  mov     rcx, rbx; hdc
0x180006a18  mov     rdi, [rbp+4Fh+arg_18]
0x180006a1c  mov     rax, [rax+10h]
0x180006a20  mov     r15, [rbp+4Fh+arg_20]
0x180006a24  mov     [rbp+4Fh+var_78], rax
0x180006a28  mov     qword ptr [rbp+4Fh+pt.x], 0
0x180006a30  call    cs:__imp_SetStretchBltMode
0x180006a36  lea     r9, [rbp+4Fh+pt]; lppt
0x180006a3a  xor     r8d, r8d; y
0x180006a3d  xor     edx, edx; x
0x180006a3f  mov     rcx, rbx; hdc
0x180006a42  mov     r13d, eax
0x180006a45  call    cs:__imp_SetBrushOrgEx
0x180006a4b  mov     rcx, rbx; hdc
0x180006a4e  call    cs:__imp_CreateCompatibleDC
0x180006a54  mov     rsi, rax
0x180006a57  test    rax, rax
0x180006a5a  jz      loc_180006BF8
0x180006a60  xor     r9d, r9d; lppt
0x180006a63  xor     r8d, r8d; y
0x180006a66  xor     edx, edx; x
0x180006a68  mov     rcx, rax; hdc
0x180006a6b  call    cs:__imp_OffsetViewportOrgEx
0x180006a71  mov     r8d, [rdi+0Ch]
0x180006a75  mov     rcx, rbx; hdc
0x180006a78  mov     edx, [rdi+8]
0x180006a7b  sub     r8d, [rdi+4]; cy
0x180006a7f  sub     edx, [rdi]; cx
0x180006a81  call    cs:__imp_CreateCompatibleBitmap
0x180006a87  mov     r12, rax
0x180006a8a  test    rax, rax
0x180006a8d  jz      loc_180006BEF
0x180006a93  mov     rdx, rax; h
0x180006a96  mov     rcx, rsi; hdc
0x180006a99  call    cs:__imp_SelectObject
0x180006a9f  mov     r10d, [r15+4]
0x180006aa3  mov     ecx, [r15+8]
0x180006aa7  mov     r11d, [r15]
0x180006aaa  sub     ecx, r11d
0x180006aad  mov     edx, [r15+0Ch]
0x180006ab1  mov     r8d, [rdi+0Ch]
0x180006ab5  sub     edx, r10d
0x180006ab8  sub     r8d, [rdi+4]
0x180006abc  mov     r9d, [rdi+8]
0x180006ac0  sub     r9d, [rdi]; wDest
0x180006ac3  mov     [rsp+0E0h+hSrc+8], 0CC0020h; rop
0x180006acb  mov     [rsp+0E0h+hSrc], edx; hSrc
0x180006acf  xor     edx, edx; xDest
0x180006ad1  mov     [rsp+0E0h+wSrc], ecx; wSrc
0x180006ad5  mov     rcx, rsi; hdcDest
0x180006ad8  mov     [rsp+0E0h+ySrc], r10d; ySrc
0x180006add  mov     [rsp+0E0h+xSrc], r11d; xSrc
0x180006ae2  mov     [rsp+0E0h+hdcSrc], rbx; hdcSrc
0x180006ae7  mov     [rsp+0E0h+hDest], r8d; hDest
0x180006aec  xor     r8d, r8d; yDest
0x180006aef  mov     [rbp+4Fh+h], rax
0x180006af3  call    cs:__imp_StretchBlt
0x180006af9  mov     eax, [rdi+8]
0x180006afc  sub     eax, [rdi]
0x180006afe  mov     rcx, [rbp+4Fh+var_78]; this
0x180006b02  mov     [rbp+4Fh+var_50], eax
0x180006b05  mov     eax, [rdi+0Ch]
0x180006b08  sub     eax, [rdi+4]
0x180006b0b  mov     [rbp+4Fh+var_4C], eax
0x180006b0e  mov     rax, [rcx+0B8h]
0x180006b15  mov     [rbp+4Fh+var_70], rax
0x180006b19  mov     [rbp+4Fh+var_58], 0
0x180006b21  mov     rax, [rax]
0x180006b24  mov     rax, [rax+18h]
0x180006b28  mov     [rbp+4Fh+var_68], rax
0x180006b2c  mov     rax, [r14+40h]
0x180006b30  mov     [rbp+4Fh+var_78], rax
0x180006b34  call    ?IsOleProxy@COleSite@@QEAAHXZ; COleSite::IsOleProxy(void)
0x180006b39  xor     ecx, ecx
0x180006b3b  mov     r9d, ecx
0x180006b3e  test    eax, eax
0x180006b40  jnz     short loc_180006B46
0x180006b42  mov     r9, [r14+38h]
0x180006b46  mov     r8d, [r14+34h]
0x180006b4a  lea     rax, [rbp+4Fh+var_58]
0x180006b4e  mov     edx, [r14+2Ch]
0x180006b52  mov     qword ptr [rsp+0E0h+hSrc+8], rcx
0x180006b57  mov     qword ptr [rsp+0E0h+hSrc], rcx
0x180006b5c  mov     qword ptr [rsp+0E0h+wSrc], rcx
0x180006b61  mov     qword ptr [rsp+0E0h+ySrc], rax
0x180006b66  mov     rax, [rbp+4Fh+var_68]
0x180006b6a  mov     qword ptr [rsp+0E0h+xSrc], rsi
0x180006b6f  mov     [rsp+0E0h+hdcSrc], rcx
0x180006b74  mov     rcx, [rbp+4Fh+var_78]
0x180006b78  mov     qword ptr [rsp+0E0h+hDest], rcx
0x180006b7d  mov     rcx, [rbp+4Fh+var_70]
0x180006b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b86  mov     ecx, [rdi+0Ch]
0x180006b89  sub     ecx, [rdi+4]
0x180006b8c  mov     eax, [rdi+8]
0x180006b8f  sub     eax, [rdi]
0x180006b91  mov     r10d, [r15+0Ch]
0x180006b95  mov     r8d, [r15+4]; yDest
0x180006b99  sub     r10d, r8d
0x180006b9c  mov     r9d, [r15+8]
0x180006ba0  sub     r9d, [r15]; wDest
0x180006ba3  mov     edx, [r15]; xDest
0x180006ba6  mov     [rsp+0E0h+hSrc+8], 0CC0020h; rop
0x180006bae  mov     [rsp+0E0h+hSrc], ecx; hSrc
0x180006bb2  mov     rcx, rbx; hdcDest
0x180006bb5  mov     [rsp+0E0h+wSrc], eax; wSrc
0x180006bb9  mov     [rsp+0E0h+ySrc], 0; ySrc
0x180006bc1  mov     [rsp+0E0h+xSrc], 0; xSrc
0x180006bc9  mov     [rsp+0E0h+hdcSrc], rsi; hdcSrc
0x180006bce  mov     [rsp+0E0h+hDest], r10d; hDest
0x180006bd3  call    cs:__imp_StretchBlt
0x180006bd9  mov     rdx, [rbp+4Fh+h]; h
0x180006bdd  mov     rcx, rsi; hdc
0x180006be0  call    cs:__imp_SelectObject
0x180006be6  mov     rcx, r12; ho
0x180006be9  call    cs:__imp_DeleteObject
0x180006bef  mov     rcx, rsi; hdc
0x180006bf2  call    cs:__imp_DeleteDC
0x180006bf8  mov     edx, r13d; mode
0x180006bfb  mov     rcx, rbx; hdc
0x180006bfe  call    cs:__imp_SetStretchBltMode
0x180006c04  mov     r8d, [rbp+4Fh+pt.y]; y
0x180006c08  xor     r9d, r9d; lppt
0x180006c0b  mov     edx, [rbp+4Fh+pt.x]; x
0x180006c0e  mov     rcx, rbx; hdc
0x180006c11  call    cs:__imp_SetBrushOrgEx
0x180006c17  mov     rcx, [rbp+4Fh+var_48]
0x180006c1b  xor     rcx, rsp; StackCookie
0x180006c1e  call    __security_check_cookie
0x180006c23  add     rsp, 0A8h
0x180006c2a  pop     r15
0x180006c2c  pop     r14
0x180006c2e  pop     r13
0x180006c30  pop     r12
0x180006c32  pop     rdi
0x180006c33  pop     rsi
0x180006c34  pop     rbx
0x180006c35  pop     rbp
0x180006c36  retn
```

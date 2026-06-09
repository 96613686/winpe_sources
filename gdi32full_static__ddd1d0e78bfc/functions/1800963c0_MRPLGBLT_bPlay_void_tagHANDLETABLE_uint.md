# MRPLGBLT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x1800963c0`
- end: `0x180096692`
- name: `?bPlay@MRPLGBLT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `722`
- prototype: `__int64 __fastcall(MRPLGBLT *__hidden this, void *, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016350`

## callees

- `0x18001e920`
- `0x18002b344`
- `0x18002e040`
- `0x180034210`
- `0x180034f78`
- `0x180035af0`
- `0x18007d0ac`
- `0x180094f20`
- `0x1800963c0`
- `0x180099250`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009649c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800964dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800964fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096670`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009649c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800964dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800964fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096670`
- `GDI32!DeleteDC` at `0x18009663e`
- `GDI32!DeleteDC` at `0x18009663e`
- `GDI32!SelectObject` at `0x1800965a0`
- `GDI32!SelectObject` at `0x180096620`
- `GDI32!SelectObject` at `0x1800965a0`
- `GDI32!SelectObject` at `0x180096620`
- `GDI32!SetWorldTransform` at `0x1800965bb`
- `GDI32!SetWorldTransform` at `0x1800965bb`
- `GDI32!DeleteObject` at `0x18009662f`
- `GDI32!DeleteObject` at `0x180096656`
- `GDI32!DeleteObject` at `0x18009662f`
- `GDI32!DeleteObject` at `0x180096656`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MRPLGBLT::bPlay(MRPLGBLT *this, HDC a2, struct tagHANDLETABLE *a3)
{
  unsigned int v5; // r13d
  BITMAPINFOHEADER *v6; // r14
  char v7; // r15
  MF *v8; // rdi
  HBITMAP hbmMask; // rsi
  HLOCAL v11; // rdi
  HDC CompatibleDCAdvanced; // rdi
  int v13; // eax
  HBITMAP DIBitmap; // rax
  HBITMAP v15; // r12
  HGDIOBJ v16; // r15
  HLOCAL hMem; // [rsp+50h] [rbp-28h] BYREF
  char v18; // [rsp+58h] [rbp-20h]
  BITMAPINFOHEADER *pbmih; // [rsp+60h] [rbp-18h] BYREF
  char v20; // [rsp+68h] [rbp-10h]

  v5 = 0;
  v6 = 0;
  pbmih = 0;
  v7 = 0;
  v20 = 0;
  v8 = (MF *)pvClientObjGet(a3->objectHandle[0], 4587520);
  if ( !v8 || !MRPLGBLT::bCheckRecord(this, a3) )
    return 0;
  if ( MF::bClipped(v8, (MRPLGBLT *)((char *)this + 8)) )
    return 1;
  hbmMask = 0;
  if ( *((_DWORD *)this + 32) )
  {
    hMem = 0;
    v18 = 0;
    if ( !(unsigned int)bCheckBitmap(
                          a3,
                          this,
                          *((_DWORD *)this + 33),
                          *((_DWORD *)this + 34),
                          *((_DWORD *)this + 30),
                          0,
                          (BitmapInfoPtr *)&hMem) )
    {
      if ( hMem )
      {
        if ( v18 )
          LocalFree(hMem);
      }
      return 0;
    }
    v11 = hMem;
    hbmMask = (HBITMAP)CreateMonoDib(
                         (BITMAPINFO *)hMem,
                         (char *)this + *((unsigned int *)this + 33),
                         *((_DWORD *)this + 30));
    if ( !hbmMask )
    {
      if ( v11 && v18 )
        LocalFree(v11);
      return 0;
    }
    if ( v11 && v18 )
      LocalFree(v11);
  }
  CompatibleDCAdvanced = (HDC)CreateCompatibleDCAdvanced(a2);
  if ( CompatibleDCAdvanced )
  {
    v13 = bCheckBitmap(
            a3,
            this,
            *((_DWORD *)this + 26),
            *((_DWORD *)this + 27),
            *((_DWORD *)this + 23),
            0,
            (BitmapInfoPtr *)&pbmih);
    v6 = pbmih;
    if ( v13 )
    {
      DIBitmap = CreateDIBitmap(
                   CompatibleDCAdvanced,
                   pbmih,
                   6u,
                   (char *)this + *((unsigned int *)this + 26),
                   (const BITMAPINFO *)((char *)this + *((unsigned int *)this + 24)),
                   *((_DWORD *)this + 23));
      v15 = DIBitmap;
      if ( DIBitmap )
      {
        v16 = SelectObject(CompatibleDCAdvanced, DIBitmap);
        if ( v16 )
        {
          if ( SetWorldTransform(CompatibleDCAdvanced, (const XFORM *)((char *)this + 64))
            && SetBkColor(CompatibleDCAdvanced, *((_DWORD *)this + 22)) != -1 )
          {
            v5 = PlgBlt(
                   a2,
                   (const POINT *)this + 3,
                   CompatibleDCAdvanced,
                   *((_DWORD *)this + 12),
                   *((_DWORD *)this + 13),
                   *((_DWORD *)this + 14),
                   *((_DWORD *)this + 15),
                   hbmMask,
                   *((_DWORD *)this + 28),
                   *((_DWORD *)this + 29));
          }
          SelectObject(CompatibleDCAdvanced, v16);
        }
        DeleteObject(v15);
      }
    }
    DeleteDC(CompatibleDCAdvanced);
    v7 = v20;
  }
  if ( hbmMask )
    DeleteObject(hbmMask);
  if ( v6 && v7 )
    LocalFree(v6);
  return v5;
}

```

## disassembly

```asm
0x1800963c0  mov     [rsp-40h+hdcDest], rdx
0x1800963c5  push    rbp
0x1800963c6  push    rbx
0x1800963c7  push    rsi
0x1800963c8  push    rdi
0x1800963c9  push    r12
0x1800963cb  push    r13
0x1800963cd  push    r14
0x1800963cf  push    r15
0x1800963d1  mov     rbp, rsp
0x1800963d4  sub     rsp, 78h
0x1800963d8  mov     r12, r8
0x1800963db  mov     rbx, rcx
0x1800963de  xor     r13d, r13d
0x1800963e1  mov     r14d, r13d
0x1800963e4  mov     [rbp+pbmih], r13
0x1800963e8  mov     r15b, r13b
0x1800963eb  mov     [rbp+var_10], r13b
0x1800963ef  mov     edx, 460000h
0x1800963f4  mov     rcx, [r8]
0x1800963f7  call    pvClientObjGet
0x1800963fc  mov     rdi, rax
0x1800963ff  test    rax, rax
0x180096402  jnz     short loc_18009640B
0x180096404  xor     eax, eax
0x180096406  jmp     loc_180096680
0x18009640b  mov     rdx, r12; struct tagHANDLETABLE *
0x18009640e  mov     rcx, rbx; this
0x180096411  call    ?bCheckRecord@MRPLGBLT@@QEAAHPEAUtagHANDLETABLE@@@Z; MRPLGBLT::bCheckRecord(tagHANDLETABLE *)
0x180096416  test    eax, eax
0x180096418  jnz     short loc_18009641C
0x18009641a  jmp     short loc_180096404
0x18009641c  lea     rdx, [rbx+8]; struct ERECTL *
0x180096420  mov     rcx, rdi; this
0x180096423  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x180096428  test    eax, eax
0x18009642a  jz      short loc_180096436
0x18009642c  mov     eax, 1
0x180096431  jmp     loc_180096680
0x180096436  mov     rsi, r13
0x180096439  mov     r9d, [rbx+80h]
0x180096440  test    r9d, r9d
0x180096443  jz      loc_18009650A
0x180096449  mov     [rbp+hMem], r13
0x18009644d  mov     [rbp+var_20], r13b
0x180096451  lea     rax, [rbp+hMem]
0x180096455  mov     qword ptr [rsp+78h+xMask], rax; BitmapInfoPtr *
0x18009645a  mov     dword ptr [rsp+78h+hbmMask], r13d; int
0x18009645f  mov     eax, [rbx+78h]
0x180096462  mov     [rsp+78h+height], eax; int
0x180096466  mov     eax, [rbx+88h]
0x18009646c  mov     [rsp+78h+iUsage], eax; int
0x180096470  mov     eax, [rbx+84h]
0x180096476  mov     dword ptr [rsp+78h+pbmi], eax; int
0x18009647a  mov     r8d, [rbx+7Ch]
0x18009647e  mov     rdx, rbx; this
0x180096481  mov     rcx, r12; struct tagHANDLETABLE *
0x180096484  call    bCheckBitmap
0x180096489  test    eax, eax
0x18009648b  jnz     short loc_1800964AE
0x18009648d  mov     rcx, [rbp+hMem]; hMem
0x180096491  test    rcx, rcx
0x180096494  jz      short loc_1800964A9
0x180096496  cmp     [rbp+var_20], r13b
0x18009649a  jz      short loc_1800964A9
0x18009649c  call    cs:__imp_LocalFree
0x1800964a3  nop     dword ptr [rax+rax+00h]
0x1800964a8  nop
0x1800964a9  jmp     loc_180096404
0x1800964ae  mov     edx, [rbx+84h]
0x1800964b4  add     rdx, rbx; lpBits
0x1800964b7  mov     r8d, [rbx+78h]; ColorUse
0x1800964bb  mov     rdi, [rbp+hMem]
0x1800964bf  mov     rcx, rdi; lpbmi
0x1800964c2  call    CreateMonoDib
0x1800964c7  mov     rsi, rax
0x1800964ca  test    rax, rax
0x1800964cd  jnz     short loc_1800964EF
0x1800964cf  test    rdi, rdi
0x1800964d2  jz      short loc_1800964EA
0x1800964d4  cmp     [rbp+var_20], r13b
0x1800964d8  jz      short loc_1800964EA
0x1800964da  mov     rcx, rdi; hMem
0x1800964dd  call    cs:__imp_LocalFree
0x1800964e4  nop     dword ptr [rax+rax+00h]
0x1800964e9  nop
0x1800964ea  jmp     loc_180096404
0x1800964ef  test    rdi, rdi
0x1800964f2  jz      short loc_18009650A
0x1800964f4  cmp     [rbp+var_20], r13b
0x1800964f8  jz      short loc_18009650A
0x1800964fa  mov     rcx, rdi; hMem
0x1800964fd  call    cs:__imp_LocalFree
0x180096504  nop     dword ptr [rax+rax+00h]
0x180096509  nop
0x18009650a  mov     rcx, [rbp+hdcDest]
0x18009650e  call    CreateCompatibleDCAdvanced
0x180096513  mov     rdi, rax
0x180096516  test    rax, rax
0x180096519  jz      loc_18009664E
0x18009651f  lea     rax, [rbp+pbmih]
0x180096523  mov     qword ptr [rsp+78h+xMask], rax; BitmapInfoPtr *
0x180096528  mov     dword ptr [rsp+78h+hbmMask], 0; int
0x180096530  mov     ecx, [rbx+5Ch]
0x180096533  mov     [rsp+78h+height], ecx; int
0x180096537  mov     ecx, [rbx+6Ch]
0x18009653a  mov     [rsp+78h+iUsage], ecx; int
0x18009653e  mov     ecx, [rbx+68h]
0x180096541  mov     dword ptr [rsp+78h+pbmi], ecx; int
0x180096545  mov     r9d, [rbx+64h]
0x180096549  mov     r8d, [rbx+60h]
0x18009654d  mov     rdx, rbx; this
0x180096550  mov     rcx, r12; struct tagHANDLETABLE *
0x180096553  call    bCheckBitmap
0x180096558  mov     r14, [rbp+pbmih]
0x18009655c  test    eax, eax
0x18009655e  jz      loc_18009663B
0x180096564  mov     ecx, [rbx+60h]
0x180096567  add     rcx, rbx
0x18009656a  mov     r9d, [rbx+68h]
0x18009656e  add     r9, rbx; pjBits
0x180096571  mov     eax, [rbx+5Ch]
0x180096574  mov     [rsp+78h+iUsage], eax; iUsage
0x180096578  mov     [rsp+78h+pbmi], rcx; pbmi
0x18009657d  mov     r8d, 6; flInit
0x180096583  mov     rdx, r14; pbmih
0x180096586  mov     rcx, rdi; hdc
0x180096589  call    CreateDIBitmap
0x18009658e  mov     r12, rax
0x180096591  test    rax, rax
0x180096594  jz      loc_18009663B
0x18009659a  mov     rdx, rax; h
0x18009659d  mov     rcx, rdi; hdc
0x1800965a0  call    cs:__imp_SelectObject
0x1800965a7  nop     dword ptr [rax+rax+00h]
0x1800965ac  mov     r15, rax
0x1800965af  test    rax, rax
0x1800965b2  jz      short loc_18009662C
0x1800965b4  lea     rdx, [rbx+40h]; lpxf
0x1800965b8  mov     rcx, rdi; hdc
0x1800965bb  call    cs:__imp_SetWorldTransform
0x1800965c2  nop     dword ptr [rax+rax+00h]
0x1800965c7  test    eax, eax
0x1800965c9  jz      short loc_18009661A
0x1800965cb  mov     edx, [rbx+58h]; color
0x1800965ce  mov     rcx, rdi; hdc
0x1800965d1  call    SetBkColor
0x1800965d6  cmp     eax, 0FFFFFFFFh
0x1800965d9  jz      short loc_18009661A
0x1800965db  lea     rdx, [rbx+18h]; lpPoint
0x1800965df  mov     eax, [rbx+74h]
0x1800965e2  mov     [rsp+78h+yMask], eax; yMask
0x1800965e6  mov     eax, [rbx+70h]
0x1800965e9  mov     [rsp+78h+xMask], eax; xMask
0x1800965ed  mov     [rsp+78h+hbmMask], rsi; hbmMask
0x1800965f2  mov     eax, [rbx+3Ch]
0x1800965f5  mov     [rsp+78h+height], eax; height
0x1800965f9  mov     eax, [rbx+38h]
0x1800965fc  mov     [rsp+78h+iUsage], eax; width
0x180096600  mov     eax, [rbx+34h]
0x180096603  mov     dword ptr [rsp+78h+pbmi], eax; ySrc
0x180096607  mov     r9d, [rbx+30h]; xSrc
0x18009660b  mov     r8, rdi; hdcSrc
0x18009660e  mov     rcx, [rbp+hdcDest]; hdcDest
0x180096612  call    PlgBlt
0x180096617  mov     r13d, eax
0x18009661a  mov     rdx, r15; h
0x18009661d  mov     rcx, rdi; hdc
0x180096620  call    cs:__imp_SelectObject
0x180096627  nop     dword ptr [rax+rax+00h]
0x18009662c  mov     rcx, r12; ho
0x18009662f  call    cs:__imp_DeleteObject
0x180096636  nop     dword ptr [rax+rax+00h]
0x18009663b  mov     rcx, rdi; hdc
0x18009663e  call    cs:__imp_DeleteDC
0x180096645  nop     dword ptr [rax+rax+00h]
0x18009664a  mov     r15b, [rbp+var_10]
0x18009664e  test    rsi, rsi
0x180096651  jz      short loc_180096663
0x180096653  mov     rcx, rsi; ho
0x180096656  call    cs:__imp_DeleteObject
0x18009665d  nop     dword ptr [rax+rax+00h]
0x180096662  nop
0x180096663  test    r14, r14
0x180096666  jz      short loc_18009667D
0x180096668  test    r15b, r15b
0x18009666b  jz      short loc_18009667D
0x18009666d  mov     rcx, r14; hMem
0x180096670  call    cs:__imp_LocalFree
0x180096677  nop     dword ptr [rax+rax+00h]
0x18009667c  nop
0x18009667d  mov     eax, r13d
0x180096680  add     rsp, 78h
0x180096684  pop     r15
0x180096686  pop     r14
0x180096688  pop     r13
0x18009668a  pop     r12
0x18009668c  pop     rdi
0x18009668d  pop     rsi
0x18009668e  pop     rbx
0x18009668f  pop     rbp
0x180096690  retn
```

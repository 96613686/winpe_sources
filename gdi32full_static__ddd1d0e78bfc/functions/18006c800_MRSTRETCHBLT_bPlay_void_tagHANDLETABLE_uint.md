# MRSTRETCHBLT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x18006c800`
- end: `0x18006ca41`
- name: `?bPlay@MRSTRETCHBLT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `577`
- prototype: `__int64 __fastcall(MRSTRETCHBLT *__hidden this, HDC hdcDest, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
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
- `0x18006c800`
- `0x18006ca50`
- `0x18006cab0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ca21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ca21`
- `GDI32!DeleteDC` at `0x18006ca03`
- `GDI32!DeleteDC` at `0x18006ca03`
- `GDI32!SelectObject` at `0x18006c95f`
- `GDI32!SelectObject` at `0x18006c9e5`
- `GDI32!SelectObject` at `0x18006c95f`
- `GDI32!SelectObject` at `0x18006c9e5`
- `GDI32!SetWorldTransform` at `0x18006c97a`
- `GDI32!SetWorldTransform` at `0x18006c97a`
- `GDI32!DeleteObject` at `0x18006c9f4`
- `GDI32!DeleteObject` at `0x18006c9f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall MRSTRETCHBLT::bPlay(MRSTRETCHBLT *this, HDC hdcDest, struct tagHANDLETABLE *a3)
{
  BITMAPINFOHEADER *v6; // rsi
  char v7; // bp
  MF *v8; // rdi
  DWORD rop; // ecx
  BOOL v11; // r15d
  HDC hdcSrc; // rdi
  int v13; // eax
  HBITMAP DIBitmap; // rax
  HBITMAP v15; // rbp
  HGDIOBJ v16; // r14
  BITMAPINFOHEADER *pbmih; // [rsp+60h] [rbp-48h] BYREF
  char v18; // [rsp+68h] [rbp-40h]

  v6 = 0;
  pbmih = 0;
  v7 = 0;
  v18 = 0;
  v8 = (MF *)pvClientObjGet(a3->objectHandle[0], 4587520);
  if ( !v8 || !MRSTRETCHBLT::bCheckRecord(this, a3) )
    return 0;
  if ( MF::bClipped(v8, (MRSTRETCHBLT *)((char *)this + 8)) )
    return 1;
  rop = *((_DWORD *)this + 10);
  if ( ((rop ^ (4 * rop)) & 0xCCCC0000) == 0 )
    return StretchBlt(
             hdcDest,
             *((_DWORD *)this + 6),
             *((_DWORD *)this + 7),
             *((_DWORD *)this + 8),
             *((_DWORD *)this + 9),
             0,
             *((_DWORD *)this + 11),
             *((_DWORD *)this + 12),
             *((_DWORD *)this + 25),
             *((_DWORD *)this + 26),
             rop);
  v11 = 0;
  hdcSrc = (HDC)CreateCompatibleDCAdvanced(hdcDest);
  if ( hdcSrc )
  {
    v13 = bCheckBitmap(
            a3,
            this,
            *((_DWORD *)this + 23),
            *((_DWORD *)this + 24),
            *((_DWORD *)this + 20),
            0,
            (BitmapInfoPtr *)&pbmih);
    v6 = pbmih;
    if ( v13 )
    {
      DIBitmap = CreateDIBitmap(
                   hdcSrc,
                   pbmih,
                   6u,
                   (char *)this + *((unsigned int *)this + 23),
                   (const BITMAPINFO *)((char *)this + *((unsigned int *)this + 21)),
                   *((_DWORD *)this + 20));
      v15 = DIBitmap;
      if ( DIBitmap )
      {
        v16 = SelectObject(hdcSrc, DIBitmap);
        if ( v16 )
        {
          if ( SetWorldTransform(hdcSrc, (const XFORM *)((char *)this + 52))
            && SetBkColor(hdcSrc, *((_DWORD *)this + 19)) != -1 )
          {
            v11 = StretchBlt(
                    hdcDest,
                    *((_DWORD *)this + 6),
                    *((_DWORD *)this + 7),
                    *((_DWORD *)this + 8),
                    *((_DWORD *)this + 9),
                    hdcSrc,
                    *((_DWORD *)this + 11),
                    *((_DWORD *)this + 12),
                    *((_DWORD *)this + 25),
                    *((_DWORD *)this + 26),
                    *((_DWORD *)this + 10));
          }
          SelectObject(hdcSrc, v16);
        }
        DeleteObject(v15);
      }
    }
    DeleteDC(hdcSrc);
    v7 = v18;
  }
  if ( v6 )
  {
    if ( v7 )
      LocalFree(v6);
  }
  return v11;
}

```

## disassembly

```asm
0x18006c800  push    rbx
0x18006c802  push    rbp
0x18006c803  push    rsi
0x18006c804  push    rdi
0x18006c805  push    r12
0x18006c807  push    r14
0x18006c809  push    r15
0x18006c80b  sub     rsp, 70h
0x18006c80f  mov     r14, r8
0x18006c812  mov     r12, rdx
0x18006c815  mov     rbx, rcx
0x18006c818  xor     esi, esi
0x18006c81a  mov     [rsp+0A8h+pbmih], rsi
0x18006c81f  xor     bpl, bpl
0x18006c822  mov     [rsp+0A8h+var_40], bpl
0x18006c827  mov     edx, 460000h
0x18006c82c  mov     rcx, [r8]
0x18006c82f  call    pvClientObjGet
0x18006c834  mov     rdi, rax
0x18006c837  test    rax, rax
0x18006c83a  jnz     short loc_18006C843
0x18006c83c  xor     eax, eax
0x18006c83e  jmp     loc_18006CA31
0x18006c843  mov     rdx, r14; struct tagHANDLETABLE *
0x18006c846  mov     rcx, rbx; this
0x18006c849  call    ?bCheckRecord@MRSTRETCHBLT@@QEAAHPEAUtagHANDLETABLE@@@Z; MRSTRETCHBLT::bCheckRecord(tagHANDLETABLE *)
0x18006c84e  test    eax, eax
0x18006c850  jnz     short loc_18006C854
0x18006c852  jmp     short loc_18006C83C
0x18006c854  lea     rdx, [rbx+8]; struct ERECTL *
0x18006c858  mov     rcx, rdi; this
0x18006c85b  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x18006c860  test    eax, eax
0x18006c862  jz      short loc_18006C86E
0x18006c864  mov     eax, 1
0x18006c869  jmp     loc_18006CA31
0x18006c86e  mov     ecx, [rbx+28h]
0x18006c871  lea     eax, ds:0[rcx*4]
0x18006c878  xor     eax, ecx
0x18006c87a  test    eax, 0CCCC0000h
0x18006c87f  jnz     short loc_18006C8CA
0x18006c881  mov     [rsp+0A8h+rop], ecx; rop
0x18006c885  mov     eax, [rbx+68h]
0x18006c888  mov     [rsp+0A8h+hSrc], eax; hSrc
0x18006c88c  mov     eax, [rbx+64h]
0x18006c88f  mov     [rsp+0A8h+wSrc], eax; wSrc
0x18006c893  mov     eax, [rbx+30h]
0x18006c896  mov     [rsp+0A8h+ySrc], eax; ySrc
0x18006c89a  mov     eax, [rbx+2Ch]
0x18006c89d  mov     [rsp+0A8h+xSrc], eax; xSrc
0x18006c8a1  mov     [rsp+0A8h+hdcSrc], 0; hdcSrc
0x18006c8aa  mov     eax, [rbx+24h]
0x18006c8ad  mov     [rsp+0A8h+hDest], eax; hDest
0x18006c8b1  mov     r9d, [rbx+20h]; wDest
0x18006c8b5  mov     r8d, [rbx+1Ch]; yDest
0x18006c8b9  mov     edx, [rbx+18h]; xDest
0x18006c8bc  mov     rcx, r12; hdcDest
0x18006c8bf  call    StretchBlt
0x18006c8c4  nop
0x18006c8c5  jmp     loc_18006CA31
0x18006c8ca  xor     r15d, r15d
0x18006c8cd  mov     rcx, r12
0x18006c8d0  call    CreateCompatibleDCAdvanced
0x18006c8d5  mov     rdi, rax
0x18006c8d8  test    rax, rax
0x18006c8db  jz      loc_18006CA14
0x18006c8e1  lea     rax, [rsp+0A8h+pbmih]
0x18006c8e6  mov     qword ptr [rsp+0A8h+wSrc], rax; BitmapInfoPtr *
0x18006c8eb  mov     [rsp+0A8h+ySrc], r15d; int
0x18006c8f0  mov     ecx, [rbx+50h]
0x18006c8f3  mov     [rsp+0A8h+xSrc], ecx; int
0x18006c8f7  mov     ecx, [rbx+60h]
0x18006c8fa  mov     dword ptr [rsp+0A8h+hdcSrc], ecx; int
0x18006c8fe  mov     ecx, [rbx+5Ch]
0x18006c901  mov     [rsp+0A8h+hDest], ecx; int
0x18006c905  mov     r9d, [rbx+58h]
0x18006c909  mov     r8d, [rbx+54h]
0x18006c90d  mov     rdx, rbx; this
0x18006c910  mov     rcx, r14; struct tagHANDLETABLE *
0x18006c913  call    bCheckBitmap
0x18006c918  mov     rsi, [rsp+0A8h+pbmih]
0x18006c91d  test    eax, eax
0x18006c91f  jz      loc_18006CA00
0x18006c925  mov     ecx, [rbx+54h]
0x18006c928  add     rcx, rbx
0x18006c92b  mov     r9d, [rbx+5Ch]
0x18006c92f  add     r9, rbx; pjBits
0x18006c932  mov     eax, [rbx+50h]
0x18006c935  mov     dword ptr [rsp+0A8h+hdcSrc], eax; iUsage
0x18006c939  mov     qword ptr [rsp+0A8h+hDest], rcx; pbmi
0x18006c93e  lea     r8d, [r15+6]; flInit
0x18006c942  mov     rdx, rsi; pbmih
0x18006c945  mov     rcx, rdi; hdc
0x18006c948  call    CreateDIBitmap
0x18006c94d  mov     rbp, rax
0x18006c950  test    rax, rax
0x18006c953  jz      loc_18006CA00
0x18006c959  mov     rdx, rax; h
0x18006c95c  mov     rcx, rdi; hdc
0x18006c95f  call    cs:__imp_SelectObject
0x18006c966  nop     dword ptr [rax+rax+00h]
0x18006c96b  mov     r14, rax
0x18006c96e  test    rax, rax
0x18006c971  jz      short loc_18006C9F1
0x18006c973  lea     rdx, [rbx+34h]; lpxf
0x18006c977  mov     rcx, rdi; hdc
0x18006c97a  call    cs:__imp_SetWorldTransform
0x18006c981  nop     dword ptr [rax+rax+00h]
0x18006c986  test    eax, eax
0x18006c988  jz      short loc_18006C9DF
0x18006c98a  mov     edx, [rbx+4Ch]; color
0x18006c98d  mov     rcx, rdi; hdc
0x18006c990  call    SetBkColor
0x18006c995  cmp     eax, 0FFFFFFFFh
0x18006c998  jz      short loc_18006C9DF
0x18006c99a  mov     eax, [rbx+28h]
0x18006c99d  mov     [rsp+0A8h+rop], eax; rop
0x18006c9a1  mov     eax, [rbx+68h]
0x18006c9a4  mov     [rsp+0A8h+hSrc], eax; hSrc
0x18006c9a8  mov     eax, [rbx+64h]
0x18006c9ab  mov     [rsp+0A8h+wSrc], eax; wSrc
0x18006c9af  mov     eax, [rbx+30h]
0x18006c9b2  mov     [rsp+0A8h+ySrc], eax; ySrc
0x18006c9b6  mov     eax, [rbx+2Ch]
0x18006c9b9  mov     [rsp+0A8h+xSrc], eax; xSrc
0x18006c9bd  mov     [rsp+0A8h+hdcSrc], rdi; hdcSrc
0x18006c9c2  mov     eax, [rbx+24h]
0x18006c9c5  mov     [rsp+0A8h+hDest], eax; hDest
0x18006c9c9  mov     r9d, [rbx+20h]; wDest
0x18006c9cd  mov     r8d, [rbx+1Ch]; yDest
0x18006c9d1  mov     edx, [rbx+18h]; xDest
0x18006c9d4  mov     rcx, r12; hdcDest
0x18006c9d7  call    StretchBlt
0x18006c9dc  mov     r15d, eax
0x18006c9df  mov     rdx, r14; h
0x18006c9e2  mov     rcx, rdi; hdc
0x18006c9e5  call    cs:__imp_SelectObject
0x18006c9ec  nop     dword ptr [rax+rax+00h]
0x18006c9f1  mov     rcx, rbp; ho
0x18006c9f4  call    cs:__imp_DeleteObject
0x18006c9fb  nop     dword ptr [rax+rax+00h]
0x18006ca00  mov     rcx, rdi; hdc
0x18006ca03  call    cs:__imp_DeleteDC
0x18006ca0a  nop     dword ptr [rax+rax+00h]
0x18006ca0f  mov     bpl, [rsp+0A8h+var_40]
0x18006ca14  test    rsi, rsi
0x18006ca17  jz      short loc_18006CA2E
0x18006ca19  test    bpl, bpl
0x18006ca1c  jz      short loc_18006CA2E
0x18006ca1e  mov     rcx, rsi; hMem
0x18006ca21  call    cs:__imp_LocalFree
0x18006ca28  nop     dword ptr [rax+rax+00h]
0x18006ca2d  nop
0x18006ca2e  mov     eax, r15d
0x18006ca31  add     rsp, 70h
0x18006ca35  pop     r15
0x18006ca37  pop     r14
0x18006ca39  pop     r12
0x18006ca3b  pop     rdi
0x18006ca3c  pop     rsi
0x18006ca3d  pop     rbp
0x18006ca3e  pop     rbx
0x18006ca3f  retn
```

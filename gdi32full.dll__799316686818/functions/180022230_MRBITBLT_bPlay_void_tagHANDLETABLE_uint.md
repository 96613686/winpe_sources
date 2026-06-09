# MRBITBLT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180022230`
- end: `0x180022425`
- name: `?bPlay@MRBITBLT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `501`
- prototype: `__int64 __fastcall(MRBITBLT *__hidden this, HDC hdc, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800305e0`

## callees

- `0x18001dc40`
- `0x18001e870`
- `0x18001eb5c`
- `0x18001ec70`
- `0x1800218b0`
- `0x180022230`
- `0x180022430`
- `0x180022504`
- `0x180024fb8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800223b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800223b3`
- `GDI32!DeleteDC` at `0x180022393`
- `GDI32!DeleteDC` at `0x180022393`
- `GDI32!SelectObject` at `0x180022379`
- `GDI32!SelectObject` at `0x180022419`
- `GDI32!SelectObject` at `0x180022379`
- `GDI32!SelectObject` at `0x180022419`
- `GDI32!SetWorldTransform` at `0x1800223c2`
- `GDI32!SetWorldTransform` at `0x1800223c2`
- `GDI32!DeleteObject` at `0x18002238a`
- `GDI32!DeleteObject` at `0x18002238a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall MRBITBLT::bPlay(MRBITBLT *this, HDC hdc, struct tagHANDLETABLE *a3)
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
  BITMAPINFOHEADER *pbmih; // [rsp+50h] [rbp-48h] BYREF
  char v18; // [rsp+58h] [rbp-40h]

  v6 = 0;
  pbmih = 0;
  v7 = 0;
  v18 = 0;
  v8 = (MF *)pvClientObjGet(a3->objectHandle[0], 4587520);
  if ( !v8 || !MRBB::bCheckRecord(this, a3) )
    return 0;
  if ( MF::bClipped(v8, (MRBITBLT *)((char *)this + 8)) )
    return 1;
  rop = *((_DWORD *)this + 10);
  if ( ((rop ^ (4 * rop)) & 0xCCCC0000) == 0 )
    return BitBlt(
             hdc,
             *((_DWORD *)this + 6),
             *((_DWORD *)this + 7),
             *((_DWORD *)this + 8),
             *((_DWORD *)this + 9),
             0,
             *((_DWORD *)this + 11),
             *((_DWORD *)this + 12),
             rop);
  v11 = 0;
  hdcSrc = (HDC)CreateCompatibleDCAdvanced(hdc);
  if ( hdcSrc )
  {
    v13 = bCheckBitmap(
            a3,
            this,
            *((_DWORD *)this + 21),
            *((_DWORD *)this + 22),
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
            v11 = BitBlt(
                    hdc,
                    *((_DWORD *)this + 6),
                    *((_DWORD *)this + 7),
                    *((_DWORD *)this + 8),
                    *((_DWORD *)this + 9),
                    hdcSrc,
                    *((_DWORD *)this + 11),
                    *((_DWORD *)this + 12),
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
0x180022230  push    rbx
0x180022232  push    rbp
0x180022233  push    rsi
0x180022234  push    rdi
0x180022235  push    r12
0x180022237  push    r14
0x180022239  push    r15
0x18002223b  sub     rsp, 60h
0x18002223f  mov     r14, r8
0x180022242  mov     r12, rdx
0x180022245  mov     rbx, rcx
0x180022248  xor     esi, esi
0x18002224a  mov     [rsp+98h+pbmih], rsi
0x18002224f  xor     bpl, bpl
0x180022252  mov     [rsp+98h+var_40], bpl
0x180022257  mov     edx, 460000h
0x18002225c  mov     rcx, [r8]
0x18002225f  call    pvClientObjGet
0x180022264  mov     rdi, rax
0x180022267  test    rax, rax
0x18002226a  jz      short loc_1800222EA
0x18002226c  mov     rdx, r14; struct tagHANDLETABLE *
0x18002226f  mov     rcx, rbx; this
0x180022272  call    ?bCheckRecord@MRBB@@QEAAHPEAUtagHANDLETABLE@@@Z; MRBB::bCheckRecord(tagHANDLETABLE *)
0x180022277  test    eax, eax
0x180022279  jz      short loc_1800222DF
0x18002227b  lea     rdx, [rbx+8]; struct ERECTL *
0x18002227f  mov     rcx, rdi; this
0x180022282  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x180022287  test    eax, eax
0x180022289  jnz     short loc_1800222E3
0x18002228b  mov     ecx, [rbx+28h]
0x18002228e  lea     eax, ds:0[rcx*4]
0x180022295  xor     eax, ecx
0x180022297  test    eax, 0CCCC0000h
0x18002229c  jnz     short loc_1800222EC
0x18002229e  mov     [rsp+98h+rop], ecx; rop
0x1800222a2  mov     eax, [rbx+30h]
0x1800222a5  mov     [rsp+98h+y1], eax; y1
0x1800222a9  mov     eax, [rbx+2Ch]
0x1800222ac  mov     [rsp+98h+x1], eax; x1
0x1800222b0  mov     [rsp+98h+hdcSrc], rsi; hdcSrc
0x1800222b5  mov     eax, [rbx+24h]
0x1800222b8  mov     [rsp+98h+cy], eax; cy
0x1800222bc  mov     r9d, [rbx+20h]; cx
0x1800222c0  mov     r8d, [rbx+1Ch]; y
0x1800222c4  mov     edx, [rbx+18h]; x
0x1800222c7  mov     rcx, r12; hdc
0x1800222ca  call    BitBlt
0x1800222cf  nop
0x1800222d0  add     rsp, 60h
0x1800222d4  pop     r15
0x1800222d6  pop     r14
0x1800222d8  pop     r12
0x1800222da  pop     rdi
0x1800222db  pop     rsi
0x1800222dc  pop     rbp
0x1800222dd  pop     rbx
0x1800222de  retn
0x1800222df  xor     eax, eax
0x1800222e1  jmp     short loc_1800222D0
0x1800222e3  mov     eax, 1
0x1800222e8  jmp     short loc_1800222D0
0x1800222ea  jmp     short loc_1800222DF
0x1800222ec  xor     r15d, r15d
0x1800222ef  mov     rcx, r12
0x1800222f2  call    CreateCompatibleDCAdvanced
0x1800222f7  mov     rdi, rax
0x1800222fa  test    rax, rax
0x1800222fd  jz      loc_18002239E
0x180022303  lea     rax, [rsp+98h+pbmih]
0x180022308  mov     qword ptr [rsp+98h+rop], rax; BitmapInfoPtr *
0x18002230d  mov     [rsp+98h+y1], r15d; int
0x180022312  mov     ecx, [rbx+50h]
0x180022315  mov     [rsp+98h+x1], ecx; int
0x180022319  mov     ecx, [rbx+60h]
0x18002231c  mov     dword ptr [rsp+98h+hdcSrc], ecx; int
0x180022320  mov     ecx, [rbx+5Ch]
0x180022323  mov     [rsp+98h+cy], ecx; int
0x180022327  mov     r9d, [rbx+58h]
0x18002232b  mov     r8d, [rbx+54h]
0x18002232f  mov     rdx, rbx; this
0x180022332  mov     rcx, r14; struct tagHANDLETABLE *
0x180022335  call    bCheckBitmap
0x18002233a  mov     rsi, [rsp+98h+pbmih]
0x18002233f  test    eax, eax
0x180022341  jz      short loc_180022390
0x180022343  mov     ecx, [rbx+54h]
0x180022346  add     rcx, rbx
0x180022349  mov     r9d, [rbx+5Ch]
0x18002234d  add     r9, rbx; pjBits
0x180022350  mov     eax, [rbx+50h]
0x180022353  mov     dword ptr [rsp+98h+hdcSrc], eax; iUsage
0x180022357  mov     qword ptr [rsp+98h+cy], rcx; pbmi
0x18002235c  lea     r8d, [r15+6]; flInit
0x180022360  mov     rdx, rsi; pbmih
0x180022363  mov     rcx, rdi; hdc
0x180022366  call    CreateDIBitmap
0x18002236b  mov     rbp, rax
0x18002236e  test    rax, rax
0x180022371  jz      short loc_180022390
0x180022373  mov     rdx, rax; h
0x180022376  mov     rcx, rdi; hdc
0x180022379  call    cs:__imp_SelectObject
0x18002237f  mov     r14, rax
0x180022382  test    rax, rax
0x180022385  jnz     short loc_1800223BB
0x180022387  mov     rcx, rbp; ho
0x18002238a  call    cs:__imp_DeleteObject
0x180022390  mov     rcx, rdi; hdc
0x180022393  call    cs:__imp_DeleteDC
0x180022399  mov     bpl, [rsp+98h+var_40]
0x18002239e  test    rsi, rsi
0x1800223a1  jnz     short loc_1800223AB
0x1800223a3  mov     eax, r15d
0x1800223a6  jmp     loc_1800222D0
0x1800223ab  test    bpl, bpl
0x1800223ae  jz      short loc_1800223A3
0x1800223b0  mov     rcx, rsi; hMem
0x1800223b3  call    cs:__imp_LocalFree
0x1800223b9  jmp     short loc_1800223A3
0x1800223bb  lea     rdx, [rbx+34h]; lpxf
0x1800223bf  mov     rcx, rdi; hdc
0x1800223c2  call    cs:__imp_SetWorldTransform
0x1800223c8  test    eax, eax
0x1800223ca  jz      short loc_180022413
0x1800223cc  mov     edx, [rbx+4Ch]; color
0x1800223cf  mov     rcx, rdi; hdc
0x1800223d2  call    SetBkColor
0x1800223d7  cmp     eax, 0FFFFFFFFh
0x1800223da  jz      short loc_180022413
0x1800223dc  mov     eax, [rbx+28h]
0x1800223df  mov     [rsp+98h+rop], eax; rop
0x1800223e3  mov     eax, [rbx+30h]
0x1800223e6  mov     [rsp+98h+y1], eax; y1
0x1800223ea  mov     eax, [rbx+2Ch]
0x1800223ed  mov     [rsp+98h+x1], eax; x1
0x1800223f1  mov     [rsp+98h+hdcSrc], rdi; hdcSrc
0x1800223f6  mov     eax, [rbx+24h]
0x1800223f9  mov     [rsp+98h+cy], eax; cy
0x1800223fd  mov     r9d, [rbx+20h]; cx
0x180022401  mov     r8d, [rbx+1Ch]; y
0x180022405  mov     edx, [rbx+18h]; x
0x180022408  mov     rcx, r12; hdc
0x18002240b  call    BitBlt
0x180022410  mov     r15d, eax
0x180022413  mov     rdx, r14; h
0x180022416  mov     rcx, rdi; hdc
0x180022419  call    cs:__imp_SelectObject
0x18002241f  jmp     loc_180022387
```

# MRSTRETCHBLT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x1800684d0`
- end: `0x1800686ec`
- name: `?bPlay@MRSTRETCHBLT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `540`
- prototype: `__int64 __fastcall(MRSTRETCHBLT *__hidden this, HDC hdcDest, struct tagHANDLETABLE *, unsigned int)`
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
- `0x180022504`
- `0x180024fb8`
- `0x1800684d0`
- `0x180068700`
- `0x180068760`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800686d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800686d3`
- `GDI32!DeleteDC` at `0x1800686bb`
- `GDI32!DeleteDC` at `0x1800686bb`
- `GDI32!SelectObject` at `0x18006862f`
- `GDI32!SelectObject` at `0x1800686a9`
- `GDI32!SelectObject` at `0x18006862f`
- `GDI32!SelectObject` at `0x1800686a9`
- `GDI32!SetWorldTransform` at `0x180068644`
- `GDI32!SetWorldTransform` at `0x180068644`
- `GDI32!DeleteObject` at `0x1800686b2`
- `GDI32!DeleteObject` at `0x1800686b2`

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
0x1800684d0  push    rbx
0x1800684d2  push    rbp
0x1800684d3  push    rsi
0x1800684d4  push    rdi
0x1800684d5  push    r12
0x1800684d7  push    r14
0x1800684d9  push    r15
0x1800684db  sub     rsp, 70h
0x1800684df  mov     r14, r8
0x1800684e2  mov     r12, rdx
0x1800684e5  mov     rbx, rcx
0x1800684e8  xor     esi, esi
0x1800684ea  mov     [rsp+0A8h+pbmih], rsi
0x1800684ef  xor     bpl, bpl
0x1800684f2  mov     [rsp+0A8h+var_40], bpl
0x1800684f7  mov     edx, 460000h
0x1800684fc  mov     rcx, [r8]
0x1800684ff  call    pvClientObjGet
0x180068504  mov     rdi, rax
0x180068507  test    rax, rax
0x18006850a  jnz     short loc_180068513
0x18006850c  xor     eax, eax
0x18006850e  jmp     loc_1800686DD
0x180068513  mov     rdx, r14; struct tagHANDLETABLE *
0x180068516  mov     rcx, rbx; this
0x180068519  call    ?bCheckRecord@MRSTRETCHBLT@@QEAAHPEAUtagHANDLETABLE@@@Z; MRSTRETCHBLT::bCheckRecord(tagHANDLETABLE *)
0x18006851e  test    eax, eax
0x180068520  jnz     short loc_180068524
0x180068522  jmp     short loc_18006850C
0x180068524  lea     rdx, [rbx+8]; struct ERECTL *
0x180068528  mov     rcx, rdi; this
0x18006852b  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x180068530  test    eax, eax
0x180068532  jz      short loc_18006853E
0x180068534  mov     eax, 1
0x180068539  jmp     loc_1800686DD
0x18006853e  mov     ecx, [rbx+28h]
0x180068541  lea     eax, ds:0[rcx*4]
0x180068548  xor     eax, ecx
0x18006854a  test    eax, 0CCCC0000h
0x18006854f  jnz     short loc_18006859A
0x180068551  mov     [rsp+0A8h+rop], ecx; rop
0x180068555  mov     eax, [rbx+68h]
0x180068558  mov     [rsp+0A8h+hSrc], eax; hSrc
0x18006855c  mov     eax, [rbx+64h]
0x18006855f  mov     [rsp+0A8h+wSrc], eax; wSrc
0x180068563  mov     eax, [rbx+30h]
0x180068566  mov     [rsp+0A8h+ySrc], eax; ySrc
0x18006856a  mov     eax, [rbx+2Ch]
0x18006856d  mov     [rsp+0A8h+xSrc], eax; xSrc
0x180068571  mov     [rsp+0A8h+hdcSrc], 0; hdcSrc
0x18006857a  mov     eax, [rbx+24h]
0x18006857d  mov     [rsp+0A8h+hDest], eax; hDest
0x180068581  mov     r9d, [rbx+20h]; wDest
0x180068585  mov     r8d, [rbx+1Ch]; yDest
0x180068589  mov     edx, [rbx+18h]; xDest
0x18006858c  mov     rcx, r12; hdcDest
0x18006858f  call    StretchBlt
0x180068594  nop
0x180068595  jmp     loc_1800686DD
0x18006859a  xor     r15d, r15d
0x18006859d  mov     rcx, r12
0x1800685a0  call    CreateCompatibleDCAdvanced
0x1800685a5  mov     rdi, rax
0x1800685a8  test    rax, rax
0x1800685ab  jz      loc_1800686C6
0x1800685b1  lea     rax, [rsp+0A8h+pbmih]
0x1800685b6  mov     qword ptr [rsp+0A8h+wSrc], rax; BitmapInfoPtr *
0x1800685bb  mov     [rsp+0A8h+ySrc], r15d; int
0x1800685c0  mov     ecx, [rbx+50h]
0x1800685c3  mov     [rsp+0A8h+xSrc], ecx; int
0x1800685c7  mov     ecx, [rbx+60h]
0x1800685ca  mov     dword ptr [rsp+0A8h+hdcSrc], ecx; int
0x1800685ce  mov     ecx, [rbx+5Ch]
0x1800685d1  mov     [rsp+0A8h+hDest], ecx; int
0x1800685d5  mov     r9d, [rbx+58h]
0x1800685d9  mov     r8d, [rbx+54h]
0x1800685dd  mov     rdx, rbx; this
0x1800685e0  mov     rcx, r14; struct tagHANDLETABLE *
0x1800685e3  call    bCheckBitmap
0x1800685e8  mov     rsi, [rsp+0A8h+pbmih]
0x1800685ed  test    eax, eax
0x1800685ef  jz      loc_1800686B8
0x1800685f5  mov     ecx, [rbx+54h]
0x1800685f8  add     rcx, rbx
0x1800685fb  mov     r9d, [rbx+5Ch]
0x1800685ff  add     r9, rbx; pjBits
0x180068602  mov     eax, [rbx+50h]
0x180068605  mov     dword ptr [rsp+0A8h+hdcSrc], eax; iUsage
0x180068609  mov     qword ptr [rsp+0A8h+hDest], rcx; pbmi
0x18006860e  lea     r8d, [r15+6]; flInit
0x180068612  mov     rdx, rsi; pbmih
0x180068615  mov     rcx, rdi; hdc
0x180068618  call    CreateDIBitmap
0x18006861d  mov     rbp, rax
0x180068620  test    rax, rax
0x180068623  jz      loc_1800686B8
0x180068629  mov     rdx, rax; h
0x18006862c  mov     rcx, rdi; hdc
0x18006862f  call    cs:__imp_SelectObject
0x180068635  mov     r14, rax
0x180068638  test    rax, rax
0x18006863b  jz      short loc_1800686AF
0x18006863d  lea     rdx, [rbx+34h]; lpxf
0x180068641  mov     rcx, rdi; hdc
0x180068644  call    cs:__imp_SetWorldTransform
0x18006864a  test    eax, eax
0x18006864c  jz      short loc_1800686A3
0x18006864e  mov     edx, [rbx+4Ch]; color
0x180068651  mov     rcx, rdi; hdc
0x180068654  call    SetBkColor
0x180068659  cmp     eax, 0FFFFFFFFh
0x18006865c  jz      short loc_1800686A3
0x18006865e  mov     eax, [rbx+28h]
0x180068661  mov     [rsp+0A8h+rop], eax; rop
0x180068665  mov     eax, [rbx+68h]
0x180068668  mov     [rsp+0A8h+hSrc], eax; hSrc
0x18006866c  mov     eax, [rbx+64h]
0x18006866f  mov     [rsp+0A8h+wSrc], eax; wSrc
0x180068673  mov     eax, [rbx+30h]
0x180068676  mov     [rsp+0A8h+ySrc], eax; ySrc
0x18006867a  mov     eax, [rbx+2Ch]
0x18006867d  mov     [rsp+0A8h+xSrc], eax; xSrc
0x180068681  mov     [rsp+0A8h+hdcSrc], rdi; hdcSrc
0x180068686  mov     eax, [rbx+24h]
0x180068689  mov     [rsp+0A8h+hDest], eax; hDest
0x18006868d  mov     r9d, [rbx+20h]; wDest
0x180068691  mov     r8d, [rbx+1Ch]; yDest
0x180068695  mov     edx, [rbx+18h]; xDest
0x180068698  mov     rcx, r12; hdcDest
0x18006869b  call    StretchBlt
0x1800686a0  mov     r15d, eax
0x1800686a3  mov     rdx, r14; h
0x1800686a6  mov     rcx, rdi; hdc
0x1800686a9  call    cs:__imp_SelectObject
0x1800686af  mov     rcx, rbp; ho
0x1800686b2  call    cs:__imp_DeleteObject
0x1800686b8  mov     rcx, rdi; hdc
0x1800686bb  call    cs:__imp_DeleteDC
0x1800686c1  mov     bpl, [rsp+0A8h+var_40]
0x1800686c6  test    rsi, rsi
0x1800686c9  jz      short loc_1800686DA
0x1800686cb  test    bpl, bpl
0x1800686ce  jz      short loc_1800686DA
0x1800686d0  mov     rcx, rsi; hMem
0x1800686d3  call    cs:__imp_LocalFree
0x1800686d9  nop
0x1800686da  mov     eax, r15d
0x1800686dd  add     rsp, 70h
0x1800686e1  pop     r15
0x1800686e3  pop     r14
0x1800686e5  pop     r12
0x1800686e7  pop     rdi
0x1800686e8  pop     rsi
0x1800686e9  pop     rbp
0x1800686ea  pop     rbx
0x1800686eb  retn
```

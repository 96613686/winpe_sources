# MRTRANSPARENTBLT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180097530`
- end: `0x180097715`
- name: `?bPlay@MRTRANSPARENTBLT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `485`
- prototype: `__int64 __fastcall(MRTRANSPARENTBLT *__hidden this, HDC hdcDest, struct tagHANDLETABLE *, unsigned int)`
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
- `0x18006ca50`
- `0x180073fe0`
- `0x180097530`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800976f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800976f5`
- `GDI32!DeleteDC` at `0x1800976d7`
- `GDI32!DeleteDC` at `0x1800976d7`
- `GDI32!SelectObject` at `0x180097633`
- `GDI32!SelectObject` at `0x1800976b9`
- `GDI32!SelectObject` at `0x180097633`
- `GDI32!SelectObject` at `0x1800976b9`
- `GDI32!SetWorldTransform` at `0x18009764e`
- `GDI32!SetWorldTransform` at `0x18009764e`
- `GDI32!DeleteObject` at `0x1800976c8`
- `GDI32!DeleteObject` at `0x1800976c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MRTRANSPARENTBLT::bPlay(MRTRANSPARENTBLT *this, HDC hdcDest, struct tagHANDLETABLE *a3)
{
  BITMAPINFOHEADER *v6; // rsi
  char v7; // bp
  MF *v8; // rdi
  unsigned int v10; // r15d
  HDC CompatibleDCAdvanced; // rdi
  int v12; // eax
  HBITMAP DIBitmap; // rax
  HBITMAP v14; // rbp
  HGDIOBJ v15; // r14
  BITMAPINFOHEADER *pbmih; // [rsp+60h] [rbp-48h] BYREF
  char v17; // [rsp+68h] [rbp-40h]

  v6 = 0;
  pbmih = 0;
  v7 = 0;
  v17 = 0;
  v8 = (MF *)pvClientObjGet(a3->objectHandle[0], 4587520);
  if ( !v8 || !MRSTRETCHBLT::bCheckRecord(this, a3) )
    return 0;
  if ( MF::bClipped(v8, (MRTRANSPARENTBLT *)((char *)this + 8)) )
    return 1;
  v10 = 0;
  CompatibleDCAdvanced = (HDC)CreateCompatibleDCAdvanced(hdcDest);
  if ( CompatibleDCAdvanced )
  {
    v12 = bCheckBitmap(
            a3,
            this,
            *((_DWORD *)this + 23),
            *((_DWORD *)this + 24),
            *((_DWORD *)this + 20),
            0,
            (BitmapInfoPtr *)&pbmih);
    v6 = pbmih;
    if ( v12 )
    {
      DIBitmap = CreateDIBitmap(
                   CompatibleDCAdvanced,
                   pbmih,
                   6u,
                   (char *)this + *((unsigned int *)this + 23),
                   (const BITMAPINFO *)((char *)this + *((unsigned int *)this + 21)),
                   *((_DWORD *)this + 20));
      v14 = DIBitmap;
      if ( DIBitmap )
      {
        v15 = SelectObject(CompatibleDCAdvanced, DIBitmap);
        if ( v15 )
        {
          if ( SetWorldTransform(CompatibleDCAdvanced, (const XFORM *)((char *)this + 52))
            && SetBkColor(CompatibleDCAdvanced, *((_DWORD *)this + 19)) != -1 )
          {
            v10 = GdiTransparentBlt(
                    hdcDest,
                    *((_DWORD *)this + 6),
                    *((_DWORD *)this + 7),
                    *((_DWORD *)this + 8),
                    *((_DWORD *)this + 9),
                    CompatibleDCAdvanced,
                    *((_DWORD *)this + 11),
                    *((_DWORD *)this + 12),
                    *((_DWORD *)this + 25),
                    *((_DWORD *)this + 26),
                    *((_DWORD *)this + 10));
          }
          SelectObject(CompatibleDCAdvanced, v15);
        }
        DeleteObject(v14);
      }
    }
    DeleteDC(CompatibleDCAdvanced);
    v7 = v17;
  }
  if ( v6 )
  {
    if ( v7 )
      LocalFree(v6);
  }
  return v10;
}

```

## disassembly

```asm
0x180097530  push    rbx
0x180097532  push    rbp
0x180097533  push    rsi
0x180097534  push    rdi
0x180097535  push    r12
0x180097537  push    r14
0x180097539  push    r15
0x18009753b  sub     rsp, 70h
0x18009753f  mov     r14, r8
0x180097542  mov     r12, rdx
0x180097545  mov     rbx, rcx
0x180097548  xor     esi, esi
0x18009754a  mov     [rsp+0A8h+pbmih], rsi
0x18009754f  xor     bpl, bpl
0x180097552  mov     [rsp+0A8h+var_40], bpl
0x180097557  mov     edx, 460000h
0x18009755c  mov     rcx, [r8]
0x18009755f  call    pvClientObjGet
0x180097564  mov     rdi, rax
0x180097567  test    rax, rax
0x18009756a  jnz     short loc_180097573
0x18009756c  xor     eax, eax
0x18009756e  jmp     loc_180097705
0x180097573  mov     rdx, r14; struct tagHANDLETABLE *
0x180097576  mov     rcx, rbx; this
0x180097579  call    ?bCheckRecord@MRSTRETCHBLT@@QEAAHPEAUtagHANDLETABLE@@@Z; MRSTRETCHBLT::bCheckRecord(tagHANDLETABLE *)
0x18009757e  test    eax, eax
0x180097580  jnz     short loc_180097584
0x180097582  jmp     short loc_18009756C
0x180097584  lea     rdx, [rbx+8]; struct ERECTL *
0x180097588  mov     rcx, rdi; this
0x18009758b  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x180097590  test    eax, eax
0x180097592  jz      short loc_18009759E
0x180097594  mov     eax, 1
0x180097599  jmp     loc_180097705
0x18009759e  xor     r15d, r15d
0x1800975a1  mov     rcx, r12
0x1800975a4  call    CreateCompatibleDCAdvanced
0x1800975a9  mov     rdi, rax
0x1800975ac  test    rax, rax
0x1800975af  jz      loc_1800976E8
0x1800975b5  lea     rax, [rsp+0A8h+pbmih]
0x1800975ba  mov     qword ptr [rsp+0A8h+wSrc], rax; BitmapInfoPtr *
0x1800975bf  mov     [rsp+0A8h+yoriginSrc], r15d; int
0x1800975c4  mov     ecx, [rbx+50h]
0x1800975c7  mov     [rsp+0A8h+xoriginSrc], ecx; int
0x1800975cb  mov     ecx, [rbx+60h]
0x1800975ce  mov     [rsp+0A8h+iUsage], ecx; int
0x1800975d2  mov     ecx, [rbx+5Ch]
0x1800975d5  mov     dword ptr [rsp+0A8h+pbmi], ecx; int
0x1800975d9  mov     r9d, [rbx+58h]
0x1800975dd  mov     r8d, [rbx+54h]
0x1800975e1  mov     rdx, rbx; this
0x1800975e4  mov     rcx, r14; struct tagHANDLETABLE *
0x1800975e7  call    bCheckBitmap
0x1800975ec  mov     rsi, [rsp+0A8h+pbmih]
0x1800975f1  test    eax, eax
0x1800975f3  jz      loc_1800976D4
0x1800975f9  mov     ecx, [rbx+54h]
0x1800975fc  add     rcx, rbx
0x1800975ff  mov     r9d, [rbx+5Ch]
0x180097603  add     r9, rbx; pjBits
0x180097606  mov     eax, [rbx+50h]
0x180097609  mov     [rsp+0A8h+iUsage], eax; iUsage
0x18009760d  mov     [rsp+0A8h+pbmi], rcx; pbmi
0x180097612  lea     r8d, [r15+6]; flInit
0x180097616  mov     rdx, rsi; pbmih
0x180097619  mov     rcx, rdi; hdc
0x18009761c  call    CreateDIBitmap
0x180097621  mov     rbp, rax
0x180097624  test    rax, rax
0x180097627  jz      loc_1800976D4
0x18009762d  mov     rdx, rax; h
0x180097630  mov     rcx, rdi; hdc
0x180097633  call    cs:__imp_SelectObject
0x18009763a  nop     dword ptr [rax+rax+00h]
0x18009763f  mov     r14, rax
0x180097642  test    rax, rax
0x180097645  jz      short loc_1800976C5
0x180097647  lea     rdx, [rbx+34h]; lpxf
0x18009764b  mov     rcx, rdi; hdc
0x18009764e  call    cs:__imp_SetWorldTransform
0x180097655  nop     dword ptr [rax+rax+00h]
0x18009765a  test    eax, eax
0x18009765c  jz      short loc_1800976B3
0x18009765e  mov     edx, [rbx+4Ch]; color
0x180097661  mov     rcx, rdi; hdc
0x180097664  call    SetBkColor
0x180097669  cmp     eax, 0FFFFFFFFh
0x18009766c  jz      short loc_1800976B3
0x18009766e  mov     eax, [rbx+28h]
0x180097671  mov     [rsp+0A8h+crTransparent], eax; crTransparent
0x180097675  mov     eax, [rbx+68h]
0x180097678  mov     [rsp+0A8h+hSrc], eax; hSrc
0x18009767c  mov     eax, [rbx+64h]
0x18009767f  mov     [rsp+0A8h+wSrc], eax; wSrc
0x180097683  mov     eax, [rbx+30h]
0x180097686  mov     [rsp+0A8h+yoriginSrc], eax; yoriginSrc
0x18009768a  mov     eax, [rbx+2Ch]
0x18009768d  mov     [rsp+0A8h+xoriginSrc], eax; xoriginSrc
0x180097691  mov     qword ptr [rsp+0A8h+iUsage], rdi; hdcSrc
0x180097696  mov     eax, [rbx+24h]
0x180097699  mov     dword ptr [rsp+0A8h+pbmi], eax; hDest
0x18009769d  mov     r9d, [rbx+20h]; wDest
0x1800976a1  mov     r8d, [rbx+1Ch]; yoriginDest
0x1800976a5  mov     edx, [rbx+18h]; xoriginDest
0x1800976a8  mov     rcx, r12; hdcDest
0x1800976ab  call    GdiTransparentBlt
0x1800976b0  mov     r15d, eax
0x1800976b3  mov     rdx, r14; h
0x1800976b6  mov     rcx, rdi; hdc
0x1800976b9  call    cs:__imp_SelectObject
0x1800976c0  nop     dword ptr [rax+rax+00h]
0x1800976c5  mov     rcx, rbp; ho
0x1800976c8  call    cs:__imp_DeleteObject
0x1800976cf  nop     dword ptr [rax+rax+00h]
0x1800976d4  mov     rcx, rdi; hdc
0x1800976d7  call    cs:__imp_DeleteDC
0x1800976de  nop     dword ptr [rax+rax+00h]
0x1800976e3  mov     bpl, [rsp+0A8h+var_40]
0x1800976e8  test    rsi, rsi
0x1800976eb  jz      short loc_180097702
0x1800976ed  test    bpl, bpl
0x1800976f0  jz      short loc_180097702
0x1800976f2  mov     rcx, rsi; hMem
0x1800976f5  call    cs:__imp_LocalFree
0x1800976fc  nop     dword ptr [rax+rax+00h]
0x180097701  nop
0x180097702  mov     eax, r15d
0x180097705  add     rsp, 70h
0x180097709  pop     r15
0x18009770b  pop     r14
0x18009770d  pop     r12
0x18009770f  pop     rdi
0x180097710  pop     rsi
0x180097711  pop     rbp
0x180097712  pop     rbx
0x180097713  retn
```

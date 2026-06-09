# MRTRANSPARENTBLT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180091990`
- end: `0x180091b50`
- name: `?bPlay@MRTRANSPARENTBLT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `448`
- prototype: `__int64 __fastcall(MRTRANSPARENTBLT *__hidden this, HDC hdcDest, struct tagHANDLETABLE *, unsigned int)`
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
- `0x180068700`
- `0x18006f310`
- `0x180091990`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091b37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091b37`
- `GDI32!DeleteDC` at `0x180091b1f`
- `GDI32!DeleteDC` at `0x180091b1f`
- `GDI32!SelectObject` at `0x180091a93`
- `GDI32!SelectObject` at `0x180091b0d`
- `GDI32!SelectObject` at `0x180091a93`
- `GDI32!SelectObject` at `0x180091b0d`
- `GDI32!SetWorldTransform` at `0x180091aa8`
- `GDI32!SetWorldTransform` at `0x180091aa8`
- `GDI32!DeleteObject` at `0x180091b16`
- `GDI32!DeleteObject` at `0x180091b16`

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
            *((_DWORD *)this + 21),
            *((_DWORD *)this + 22),
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
0x180091990  push    rbx
0x180091992  push    rbp
0x180091993  push    rsi
0x180091994  push    rdi
0x180091995  push    r12
0x180091997  push    r14
0x180091999  push    r15
0x18009199b  sub     rsp, 70h
0x18009199f  mov     r14, r8
0x1800919a2  mov     r12, rdx
0x1800919a5  mov     rbx, rcx
0x1800919a8  xor     esi, esi
0x1800919aa  mov     [rsp+0A8h+pbmih], rsi
0x1800919af  xor     bpl, bpl
0x1800919b2  mov     [rsp+0A8h+var_40], bpl
0x1800919b7  mov     edx, 460000h
0x1800919bc  mov     rcx, [r8]
0x1800919bf  call    pvClientObjGet
0x1800919c4  mov     rdi, rax
0x1800919c7  test    rax, rax
0x1800919ca  jnz     short loc_1800919D3
0x1800919cc  xor     eax, eax
0x1800919ce  jmp     loc_180091B41
0x1800919d3  mov     rdx, r14; struct tagHANDLETABLE *
0x1800919d6  mov     rcx, rbx; this
0x1800919d9  call    ?bCheckRecord@MRSTRETCHBLT@@QEAAHPEAUtagHANDLETABLE@@@Z; MRSTRETCHBLT::bCheckRecord(tagHANDLETABLE *)
0x1800919de  test    eax, eax
0x1800919e0  jnz     short loc_1800919E4
0x1800919e2  jmp     short loc_1800919CC
0x1800919e4  lea     rdx, [rbx+8]; struct ERECTL *
0x1800919e8  mov     rcx, rdi; this
0x1800919eb  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x1800919f0  test    eax, eax
0x1800919f2  jz      short loc_1800919FE
0x1800919f4  mov     eax, 1
0x1800919f9  jmp     loc_180091B41
0x1800919fe  xor     r15d, r15d
0x180091a01  mov     rcx, r12
0x180091a04  call    CreateCompatibleDCAdvanced
0x180091a09  mov     rdi, rax
0x180091a0c  test    rax, rax
0x180091a0f  jz      loc_180091B2A
0x180091a15  lea     rax, [rsp+0A8h+pbmih]
0x180091a1a  mov     qword ptr [rsp+0A8h+wSrc], rax; BitmapInfoPtr *
0x180091a1f  mov     [rsp+0A8h+yoriginSrc], r15d; int
0x180091a24  mov     ecx, [rbx+50h]
0x180091a27  mov     [rsp+0A8h+xoriginSrc], ecx; int
0x180091a2b  mov     ecx, [rbx+60h]
0x180091a2e  mov     [rsp+0A8h+iUsage], ecx; int
0x180091a32  mov     ecx, [rbx+5Ch]
0x180091a35  mov     dword ptr [rsp+0A8h+pbmi], ecx; int
0x180091a39  mov     r9d, [rbx+58h]
0x180091a3d  mov     r8d, [rbx+54h]
0x180091a41  mov     rdx, rbx; this
0x180091a44  mov     rcx, r14; struct tagHANDLETABLE *
0x180091a47  call    bCheckBitmap
0x180091a4c  mov     rsi, [rsp+0A8h+pbmih]
0x180091a51  test    eax, eax
0x180091a53  jz      loc_180091B1C
0x180091a59  mov     ecx, [rbx+54h]
0x180091a5c  add     rcx, rbx
0x180091a5f  mov     r9d, [rbx+5Ch]
0x180091a63  add     r9, rbx; pjBits
0x180091a66  mov     eax, [rbx+50h]
0x180091a69  mov     [rsp+0A8h+iUsage], eax; iUsage
0x180091a6d  mov     [rsp+0A8h+pbmi], rcx; pbmi
0x180091a72  lea     r8d, [r15+6]; flInit
0x180091a76  mov     rdx, rsi; pbmih
0x180091a79  mov     rcx, rdi; hdc
0x180091a7c  call    CreateDIBitmap
0x180091a81  mov     rbp, rax
0x180091a84  test    rax, rax
0x180091a87  jz      loc_180091B1C
0x180091a8d  mov     rdx, rax; h
0x180091a90  mov     rcx, rdi; hdc
0x180091a93  call    cs:__imp_SelectObject
0x180091a99  mov     r14, rax
0x180091a9c  test    rax, rax
0x180091a9f  jz      short loc_180091B13
0x180091aa1  lea     rdx, [rbx+34h]; lpxf
0x180091aa5  mov     rcx, rdi; hdc
0x180091aa8  call    cs:__imp_SetWorldTransform
0x180091aae  test    eax, eax
0x180091ab0  jz      short loc_180091B07
0x180091ab2  mov     edx, [rbx+4Ch]; color
0x180091ab5  mov     rcx, rdi; hdc
0x180091ab8  call    SetBkColor
0x180091abd  cmp     eax, 0FFFFFFFFh
0x180091ac0  jz      short loc_180091B07
0x180091ac2  mov     eax, [rbx+28h]
0x180091ac5  mov     [rsp+0A8h+crTransparent], eax; crTransparent
0x180091ac9  mov     eax, [rbx+68h]
0x180091acc  mov     [rsp+0A8h+hSrc], eax; hSrc
0x180091ad0  mov     eax, [rbx+64h]
0x180091ad3  mov     [rsp+0A8h+wSrc], eax; wSrc
0x180091ad7  mov     eax, [rbx+30h]
0x180091ada  mov     [rsp+0A8h+yoriginSrc], eax; yoriginSrc
0x180091ade  mov     eax, [rbx+2Ch]
0x180091ae1  mov     [rsp+0A8h+xoriginSrc], eax; xoriginSrc
0x180091ae5  mov     qword ptr [rsp+0A8h+iUsage], rdi; hdcSrc
0x180091aea  mov     eax, [rbx+24h]
0x180091aed  mov     dword ptr [rsp+0A8h+pbmi], eax; hDest
0x180091af1  mov     r9d, [rbx+20h]; wDest
0x180091af5  mov     r8d, [rbx+1Ch]; yoriginDest
0x180091af9  mov     edx, [rbx+18h]; xoriginDest
0x180091afc  mov     rcx, r12; hdcDest
0x180091aff  call    GdiTransparentBlt
0x180091b04  mov     r15d, eax
0x180091b07  mov     rdx, r14; h
0x180091b0a  mov     rcx, rdi; hdc
0x180091b0d  call    cs:__imp_SelectObject
0x180091b13  mov     rcx, rbp; ho
0x180091b16  call    cs:__imp_DeleteObject
0x180091b1c  mov     rcx, rdi; hdc
0x180091b1f  call    cs:__imp_DeleteDC
0x180091b25  mov     bpl, [rsp+0A8h+var_40]
0x180091b2a  test    rsi, rsi
0x180091b2d  jz      short loc_180091B3E
0x180091b2f  test    bpl, bpl
0x180091b32  jz      short loc_180091B3E
0x180091b34  mov     rcx, rsi; hMem
0x180091b37  call    cs:__imp_LocalFree
0x180091b3d  nop
0x180091b3e  mov     eax, r15d
0x180091b41  add     rsp, 70h
0x180091b45  pop     r15
0x180091b47  pop     r14
0x180091b49  pop     r12
0x180091b4b  pop     rdi
0x180091b4c  pop     rsi
0x180091b4d  pop     rbp
0x180091b4e  pop     rbx
0x180091b4f  retn
```

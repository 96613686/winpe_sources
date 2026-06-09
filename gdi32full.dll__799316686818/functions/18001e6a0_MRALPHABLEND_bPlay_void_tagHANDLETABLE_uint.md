# MRALPHABLEND::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x18001e6a0`
- end: `0x18001e868`
- name: `?bPlay@MRALPHABLEND@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `456`
- prototype: `__int64 __fastcall(MRALPHABLEND *__hidden this, HDC hdcDest, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800305e0`

## callees

- `0x18001d880`
- `0x18001dc40`
- `0x18001e6a0`
- `0x18001e870`
- `0x18001e8a0`
- `0x18001eb5c`
- `0x18001ec70`
- `0x180022504`
- `0x180024fb8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7b7`
- `GDI32!DeleteDC` at `0x18001e78d`
- `GDI32!DeleteDC` at `0x18001e78d`
- `GDI32!SelectObject` at `0x18001e7c5`
- `GDI32!SelectObject` at `0x18001e7fa`
- `GDI32!SelectObject` at `0x18001e7c5`
- `GDI32!SelectObject` at `0x18001e7fa`
- `GDI32!SetWorldTransform` at `0x18001e7da`
- `GDI32!SetWorldTransform` at `0x18001e7da`
- `GDI32!DeleteObject` at `0x18001e803`
- `GDI32!DeleteObject` at `0x18001e803`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MRALPHABLEND::bPlay(MRALPHABLEND *this, HDC hdcDest, struct tagHANDLETABLE *a3)
{
  BITMAPINFOHEADER *v6; // rsi
  char v7; // bp
  MF *v8; // rdi
  unsigned int v9; // r15d
  HDC CompatibleDCAdvanced; // rdi
  int v11; // eax
  HBITMAP DIBitmap; // rax
  HBITMAP v13; // rbp
  HGDIOBJ v15; // r14
  BITMAPINFOHEADER *pbmih; // [rsp+60h] [rbp-48h] BYREF
  char v17; // [rsp+68h] [rbp-40h]

  v6 = 0;
  pbmih = 0;
  v7 = 0;
  v17 = 0;
  v8 = (MF *)pvClientObjGet(a3->objectHandle[0], 4587520);
  if ( !v8 || !MRALPHABLEND::bCheckRecord(this, a3) )
    return 0;
  if ( MF::bClipped(v8, (MRALPHABLEND *)((char *)this + 8)) )
    return 1;
  v9 = 0;
  CompatibleDCAdvanced = (HDC)CreateCompatibleDCAdvanced(hdcDest);
  if ( CompatibleDCAdvanced )
  {
    v11 = bCheckBitmap(
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
    if ( v11 )
    {
      DIBitmap = CreateDIBitmap(
                   CompatibleDCAdvanced,
                   pbmih,
                   6u,
                   (char *)this + *((unsigned int *)this + 23),
                   (const BITMAPINFO *)((char *)this + *((unsigned int *)this + 21)),
                   *((_DWORD *)this + 20));
      v13 = DIBitmap;
      if ( DIBitmap )
      {
        v15 = SelectObject(CompatibleDCAdvanced, DIBitmap);
        if ( v15 )
        {
          if ( SetWorldTransform(CompatibleDCAdvanced, (const XFORM *)((char *)this + 52))
            && SetBkColor(CompatibleDCAdvanced, *((_DWORD *)this + 19)) != -1 )
          {
            v9 = GdiAlphaBlend(
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
                   *(BLENDFUNCTION *)((char *)this + 40));
          }
          SelectObject(CompatibleDCAdvanced, v15);
        }
        DeleteObject(v13);
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
  return v9;
}

```

## disassembly

```asm
0x18001e6a0  push    rbx
0x18001e6a2  push    rbp
0x18001e6a3  push    rsi
0x18001e6a4  push    rdi
0x18001e6a5  push    r12
0x18001e6a7  push    r14
0x18001e6a9  push    r15
0x18001e6ab  sub     rsp, 70h
0x18001e6af  mov     r14, r8
0x18001e6b2  mov     r12, rdx
0x18001e6b5  mov     rbx, rcx
0x18001e6b8  xor     esi, esi
0x18001e6ba  mov     [rsp+0A8h+pbmih], rsi
0x18001e6bf  xor     bpl, bpl
0x18001e6c2  mov     [rsp+0A8h+var_40], bpl
0x18001e6c7  mov     edx, 460000h
0x18001e6cc  mov     rcx, [r8]
0x18001e6cf  call    pvClientObjGet
0x18001e6d4  mov     rdi, rax
0x18001e6d7  test    rax, rax
0x18001e6da  jz      loc_18001E855
0x18001e6e0  mov     rdx, r14; struct tagHANDLETABLE *
0x18001e6e3  mov     rcx, rbx; this
0x18001e6e6  call    ?bCheckRecord@MRALPHABLEND@@QEAAHPEAUtagHANDLETABLE@@@Z; MRALPHABLEND::bCheckRecord(tagHANDLETABLE *)
0x18001e6eb  test    eax, eax
0x18001e6ed  jz      loc_18001E857
0x18001e6f3  lea     rdx, [rbx+8]; struct ERECTL *
0x18001e6f7  mov     rcx, rdi; this
0x18001e6fa  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x18001e6ff  test    eax, eax
0x18001e701  jnz     loc_18001E85E
0x18001e707  xor     r15d, r15d
0x18001e70a  mov     rcx, r12
0x18001e70d  call    CreateCompatibleDCAdvanced
0x18001e712  mov     rdi, rax
0x18001e715  test    rax, rax
0x18001e718  jz      short loc_18001E798
0x18001e71a  lea     rax, [rsp+0A8h+pbmih]
0x18001e71f  mov     qword ptr [rsp+0A8h+wSrc], rax; BitmapInfoPtr *
0x18001e724  mov     [rsp+0A8h+yoriginSrc], r15d; int
0x18001e729  mov     ecx, [rbx+50h]
0x18001e72c  mov     [rsp+0A8h+xoriginSrc], ecx; int
0x18001e730  mov     ecx, [rbx+60h]
0x18001e733  mov     [rsp+0A8h+iUsage], ecx; int
0x18001e737  mov     ecx, [rbx+5Ch]
0x18001e73a  mov     dword ptr [rsp+0A8h+pbmi], ecx; int
0x18001e73e  mov     r9d, [rbx+58h]
0x18001e742  mov     r8d, [rbx+54h]
0x18001e746  mov     rdx, rbx; this
0x18001e749  mov     rcx, r14; struct tagHANDLETABLE *
0x18001e74c  call    bCheckBitmap
0x18001e751  mov     rsi, [rsp+0A8h+pbmih]
0x18001e756  test    eax, eax
0x18001e758  jz      short loc_18001E78A
0x18001e75a  mov     ecx, [rbx+54h]
0x18001e75d  add     rcx, rbx
0x18001e760  mov     r9d, [rbx+5Ch]
0x18001e764  add     r9, rbx; pjBits
0x18001e767  mov     eax, [rbx+50h]
0x18001e76a  mov     [rsp+0A8h+iUsage], eax; iUsage
0x18001e76e  mov     [rsp+0A8h+pbmi], rcx; pbmi
0x18001e773  lea     r8d, [r15+6]; flInit
0x18001e777  mov     rdx, rsi; pbmih
0x18001e77a  mov     rcx, rdi; hdc
0x18001e77d  call    CreateDIBitmap
0x18001e782  mov     rbp, rax
0x18001e785  test    rax, rax
0x18001e788  jnz     short loc_18001E7BF
0x18001e78a  mov     rcx, rdi; hdc
0x18001e78d  call    cs:__imp_DeleteDC
0x18001e793  mov     bpl, [rsp+0A8h+var_40]
0x18001e798  test    rsi, rsi
0x18001e79b  jnz     short loc_18001E7AF
0x18001e79d  mov     eax, r15d
0x18001e7a0  add     rsp, 70h
0x18001e7a4  pop     r15
0x18001e7a6  pop     r14
0x18001e7a8  pop     r12
0x18001e7aa  pop     rdi
0x18001e7ab  pop     rsi
0x18001e7ac  pop     rbp
0x18001e7ad  pop     rbx
0x18001e7ae  retn
0x18001e7af  test    bpl, bpl
0x18001e7b2  jz      short loc_18001E79D
0x18001e7b4  mov     rcx, rsi; hMem
0x18001e7b7  call    cs:__imp_LocalFree
0x18001e7bd  jmp     short loc_18001E79D
0x18001e7bf  mov     rdx, rbp; h
0x18001e7c2  mov     rcx, rdi; hdc
0x18001e7c5  call    cs:__imp_SelectObject
0x18001e7cb  mov     r14, rax
0x18001e7ce  test    rax, rax
0x18001e7d1  jz      short loc_18001E800
0x18001e7d3  lea     rdx, [rbx+34h]; lpxf
0x18001e7d7  mov     rcx, rdi; hdc
0x18001e7da  call    cs:__imp_SetWorldTransform
0x18001e7e0  test    eax, eax
0x18001e7e2  jz      short loc_18001E7F4
0x18001e7e4  mov     edx, [rbx+4Ch]; color
0x18001e7e7  mov     rcx, rdi; hdc
0x18001e7ea  call    SetBkColor
0x18001e7ef  cmp     eax, 0FFFFFFFFh
0x18001e7f2  jnz     short loc_18001E80E
0x18001e7f4  mov     rdx, r14; h
0x18001e7f7  mov     rcx, rdi; hdc
0x18001e7fa  call    cs:__imp_SelectObject
0x18001e800  mov     rcx, rbp; ho
0x18001e803  call    cs:__imp_DeleteObject
0x18001e809  jmp     loc_18001E78A
0x18001e80e  mov     eax, [rbx+28h]
0x18001e811  mov     dword ptr [rsp+0A8h+ftn.BlendOp], eax; ftn
0x18001e815  mov     eax, [rbx+68h]
0x18001e818  mov     [rsp+0A8h+hSrc], eax; hSrc
0x18001e81c  mov     eax, [rbx+64h]
0x18001e81f  mov     [rsp+0A8h+wSrc], eax; wSrc
0x18001e823  mov     eax, [rbx+30h]
0x18001e826  mov     [rsp+0A8h+yoriginSrc], eax; yoriginSrc
0x18001e82a  mov     eax, [rbx+2Ch]
0x18001e82d  mov     [rsp+0A8h+xoriginSrc], eax; xoriginSrc
0x18001e831  mov     qword ptr [rsp+0A8h+iUsage], rdi; hdcSrc
0x18001e836  mov     eax, [rbx+24h]
0x18001e839  mov     dword ptr [rsp+0A8h+pbmi], eax; hDest
0x18001e83d  mov     r9d, [rbx+20h]; wDest
0x18001e841  mov     r8d, [rbx+1Ch]; yoriginDest
0x18001e845  mov     edx, [rbx+18h]; xoriginDest
0x18001e848  mov     rcx, r12; hdcDest
0x18001e84b  call    GdiAlphaBlend
0x18001e850  mov     r15d, eax
0x18001e853  jmp     short loc_18001E7F4
0x18001e855  jmp     short $+2
0x18001e857  xor     eax, eax
0x18001e859  jmp     loc_18001E7A0
0x18001e85e  mov     eax, 1
0x18001e863  jmp     loc_18001E7A0
```

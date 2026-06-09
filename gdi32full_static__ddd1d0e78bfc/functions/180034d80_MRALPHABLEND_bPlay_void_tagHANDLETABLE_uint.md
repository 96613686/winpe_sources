# MRALPHABLEND::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180034d80`
- end: `0x180034f71`
- name: `?bPlay@MRALPHABLEND@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `497`
- prototype: `__int64 __fastcall(MRALPHABLEND *__hidden this, HDC hdcDest, struct tagHANDLETABLE *, unsigned int)`
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
- `0x180034d80`
- `0x180034f78`
- `0x180034fb0`
- `0x180035af0`
- `0x180036560`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034ea2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034ea2`
- `GDI32!DeleteDC` at `0x180034e71`
- `GDI32!DeleteDC` at `0x180034e71`
- `GDI32!SelectObject` at `0x180034eb6`
- `GDI32!SelectObject` at `0x180034ef7`
- `GDI32!SelectObject` at `0x180034eb6`
- `GDI32!SelectObject` at `0x180034ef7`
- `GDI32!SetWorldTransform` at `0x180034ed1`
- `GDI32!SetWorldTransform` at `0x180034ed1`
- `GDI32!DeleteObject` at `0x180034f06`
- `GDI32!DeleteObject` at `0x180034f06`

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
0x180034d80  push    rbx
0x180034d82  push    rbp
0x180034d83  push    rsi
0x180034d84  push    rdi
0x180034d85  push    r12
0x180034d87  push    r14
0x180034d89  push    r15
0x180034d8b  sub     rsp, 70h
0x180034d8f  mov     r14, r8
0x180034d92  mov     r12, rdx
0x180034d95  mov     rbx, rcx
0x180034d98  xor     esi, esi
0x180034d9a  mov     [rsp+0A8h+pbmih], rsi
0x180034d9f  xor     bpl, bpl
0x180034da2  mov     [rsp+0A8h+var_40], bpl
0x180034da7  mov     edx, 460000h
0x180034dac  mov     rcx, [r8]
0x180034daf  call    pvClientObjGet
0x180034db4  mov     rdi, rax
0x180034db7  test    rax, rax
0x180034dba  jz      loc_180034F5E
0x180034dc0  mov     rdx, r14; struct tagHANDLETABLE *
0x180034dc3  mov     rcx, rbx; this
0x180034dc6  call    ?bCheckRecord@MRALPHABLEND@@QEAAHPEAUtagHANDLETABLE@@@Z; MRALPHABLEND::bCheckRecord(tagHANDLETABLE *)
0x180034dcb  test    eax, eax
0x180034dcd  jz      loc_180034F60
0x180034dd3  lea     rdx, [rbx+8]; struct ERECTL *
0x180034dd7  mov     rcx, rdi; this
0x180034dda  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x180034ddf  test    eax, eax
0x180034de1  jnz     loc_180034F67
0x180034de7  xor     r15d, r15d
0x180034dea  mov     rcx, r12
0x180034ded  call    CreateCompatibleDCAdvanced
0x180034df2  mov     rdi, rax
0x180034df5  test    rax, rax
0x180034df8  jz      loc_180034E82
0x180034dfe  lea     rax, [rsp+0A8h+pbmih]
0x180034e03  mov     qword ptr [rsp+0A8h+wSrc], rax; BitmapInfoPtr *
0x180034e08  mov     [rsp+0A8h+yoriginSrc], r15d; int
0x180034e0d  mov     ecx, [rbx+50h]
0x180034e10  mov     [rsp+0A8h+xoriginSrc], ecx; int
0x180034e14  mov     ecx, [rbx+60h]
0x180034e17  mov     [rsp+0A8h+iUsage], ecx; int
0x180034e1b  mov     ecx, [rbx+5Ch]
0x180034e1e  mov     dword ptr [rsp+0A8h+pbmi], ecx; int
0x180034e22  mov     r9d, [rbx+58h]
0x180034e26  mov     r8d, [rbx+54h]
0x180034e2a  mov     rdx, rbx; this
0x180034e2d  mov     rcx, r14; struct tagHANDLETABLE *
0x180034e30  call    bCheckBitmap
0x180034e35  mov     rsi, [rsp+0A8h+pbmih]
0x180034e3a  test    eax, eax
0x180034e3c  jz      short loc_180034E6E
0x180034e3e  mov     ecx, [rbx+54h]
0x180034e41  add     rcx, rbx
0x180034e44  mov     r9d, [rbx+5Ch]
0x180034e48  add     r9, rbx; pjBits
0x180034e4b  mov     eax, [rbx+50h]
0x180034e4e  mov     [rsp+0A8h+iUsage], eax; iUsage
0x180034e52  mov     [rsp+0A8h+pbmi], rcx; pbmi
0x180034e57  lea     r8d, [r15+6]; flInit
0x180034e5b  mov     rdx, rsi; pbmih
0x180034e5e  mov     rcx, rdi; hdc
0x180034e61  call    CreateDIBitmap
0x180034e66  mov     rbp, rax
0x180034e69  test    rax, rax
0x180034e6c  jnz     short loc_180034EB0
0x180034e6e  mov     rcx, rdi; hdc
0x180034e71  call    cs:__imp_DeleteDC
0x180034e78  nop     dword ptr [rax+rax+00h]
0x180034e7d  mov     bpl, [rsp+0A8h+var_40]
0x180034e82  test    rsi, rsi
0x180034e85  jnz     short loc_180034E9A
0x180034e87  mov     eax, r15d
0x180034e8a  add     rsp, 70h
0x180034e8e  pop     r15
0x180034e90  pop     r14
0x180034e92  pop     r12
0x180034e94  pop     rdi
0x180034e95  pop     rsi
0x180034e96  pop     rbp
0x180034e97  pop     rbx
0x180034e98  retn
0x180034e9a  test    bpl, bpl
0x180034e9d  jz      short loc_180034E87
0x180034e9f  mov     rcx, rsi; hMem
0x180034ea2  call    cs:__imp_LocalFree
0x180034ea9  nop     dword ptr [rax+rax+00h]
0x180034eae  jmp     short loc_180034E87
0x180034eb0  mov     rdx, rbp; h
0x180034eb3  mov     rcx, rdi; hdc
0x180034eb6  call    cs:__imp_SelectObject
0x180034ebd  nop     dword ptr [rax+rax+00h]
0x180034ec2  mov     r14, rax
0x180034ec5  test    rax, rax
0x180034ec8  jz      short loc_180034F03
0x180034eca  lea     rdx, [rbx+34h]; lpxf
0x180034ece  mov     rcx, rdi; hdc
0x180034ed1  call    cs:__imp_SetWorldTransform
0x180034ed8  nop     dword ptr [rax+rax+00h]
0x180034edd  test    eax, eax
0x180034edf  jz      short loc_180034EF1
0x180034ee1  mov     edx, [rbx+4Ch]; color
0x180034ee4  mov     rcx, rdi; hdc
0x180034ee7  call    SetBkColor
0x180034eec  cmp     eax, 0FFFFFFFFh
0x180034eef  jnz     short loc_180034F17
0x180034ef1  mov     rdx, r14; h
0x180034ef4  mov     rcx, rdi; hdc
0x180034ef7  call    cs:__imp_SelectObject
0x180034efe  nop     dword ptr [rax+rax+00h]
0x180034f03  mov     rcx, rbp; ho
0x180034f06  call    cs:__imp_DeleteObject
0x180034f0d  nop     dword ptr [rax+rax+00h]
0x180034f12  jmp     loc_180034E6E
0x180034f17  mov     eax, [rbx+28h]
0x180034f1a  mov     dword ptr [rsp+0A8h+ftn.BlendOp], eax; ftn
0x180034f1e  mov     eax, [rbx+68h]
0x180034f21  mov     [rsp+0A8h+hSrc], eax; hSrc
0x180034f25  mov     eax, [rbx+64h]
0x180034f28  mov     [rsp+0A8h+wSrc], eax; wSrc
0x180034f2c  mov     eax, [rbx+30h]
0x180034f2f  mov     [rsp+0A8h+yoriginSrc], eax; yoriginSrc
0x180034f33  mov     eax, [rbx+2Ch]
0x180034f36  mov     [rsp+0A8h+xoriginSrc], eax; xoriginSrc
0x180034f3a  mov     qword ptr [rsp+0A8h+iUsage], rdi; hdcSrc
0x180034f3f  mov     eax, [rbx+24h]
0x180034f42  mov     dword ptr [rsp+0A8h+pbmi], eax; hDest
0x180034f46  mov     r9d, [rbx+20h]; wDest
0x180034f4a  mov     r8d, [rbx+1Ch]; yoriginDest
0x180034f4e  mov     edx, [rbx+18h]; xoriginDest
0x180034f51  mov     rcx, r12; hdcDest
0x180034f54  call    GdiAlphaBlend
0x180034f59  mov     r15d, eax
0x180034f5c  jmp     short loc_180034EF1
0x180034f5e  jmp     short $+2
0x180034f60  xor     eax, eax
0x180034f62  jmp     loc_180034E8A
0x180034f67  mov     eax, 1
0x180034f6c  jmp     loc_180034E8A
```

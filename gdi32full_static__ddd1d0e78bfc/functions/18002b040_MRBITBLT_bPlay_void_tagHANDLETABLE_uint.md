# MRBITBLT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x18002b040`
- end: `0x18002b25a`
- name: `?bPlay@MRBITBLT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `538`
- prototype: `__int64 __fastcall(MRBITBLT *__hidden this, HDC hdc, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180016350`

## callees

- `0x18001e920`
- `0x18002a660`
- `0x18002b040`
- `0x18002b260`
- `0x18002b344`
- `0x18002e040`
- `0x180034210`
- `0x180034f78`
- `0x180035af0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b1d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b1d6`
- `GDI32!DeleteDC` at `0x18002b1b0`
- `GDI32!DeleteDC` at `0x18002b1b0`
- `GDI32!SelectObject` at `0x18002b18a`
- `GDI32!SelectObject` at `0x18002b248`
- `GDI32!SelectObject` at `0x18002b18a`
- `GDI32!SelectObject` at `0x18002b248`
- `GDI32!SetWorldTransform` at `0x18002b1eb`
- `GDI32!SetWorldTransform` at `0x18002b1eb`
- `GDI32!DeleteObject` at `0x18002b1a1`
- `GDI32!DeleteObject` at `0x18002b1a1`

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
0x18002b040  push    rbx
0x18002b042  push    rbp
0x18002b043  push    rsi
0x18002b044  push    rdi
0x18002b045  push    r12
0x18002b047  push    r14
0x18002b049  push    r15
0x18002b04b  sub     rsp, 60h
0x18002b04f  mov     r14, r8
0x18002b052  mov     r12, rdx
0x18002b055  mov     rbx, rcx
0x18002b058  xor     esi, esi
0x18002b05a  mov     [rsp+98h+pbmih], rsi
0x18002b05f  xor     bpl, bpl
0x18002b062  mov     [rsp+98h+var_40], bpl
0x18002b067  mov     edx, 460000h
0x18002b06c  mov     rcx, [r8]
0x18002b06f  call    pvClientObjGet
0x18002b074  mov     rdi, rax
0x18002b077  test    rax, rax
0x18002b07a  jz      short loc_18002B0FB
0x18002b07c  mov     rdx, r14; struct tagHANDLETABLE *
0x18002b07f  mov     rcx, rbx; this
0x18002b082  call    ?bCheckRecord@MRBB@@QEAAHPEAUtagHANDLETABLE@@@Z; MRBB::bCheckRecord(tagHANDLETABLE *)
0x18002b087  test    eax, eax
0x18002b089  jz      short loc_18002B0F0
0x18002b08b  lea     rdx, [rbx+8]; struct ERECTL *
0x18002b08f  mov     rcx, rdi; this
0x18002b092  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x18002b097  test    eax, eax
0x18002b099  jnz     short loc_18002B0F4
0x18002b09b  mov     ecx, [rbx+28h]
0x18002b09e  lea     eax, ds:0[rcx*4]
0x18002b0a5  xor     eax, ecx
0x18002b0a7  test    eax, 0CCCC0000h
0x18002b0ac  jnz     short loc_18002B0FD
0x18002b0ae  mov     [rsp+98h+rop], ecx; rop
0x18002b0b2  mov     eax, [rbx+30h]
0x18002b0b5  mov     [rsp+98h+y1], eax; y1
0x18002b0b9  mov     eax, [rbx+2Ch]
0x18002b0bc  mov     [rsp+98h+x1], eax; x1
0x18002b0c0  mov     [rsp+98h+hdcSrc], rsi; hdcSrc
0x18002b0c5  mov     eax, [rbx+24h]
0x18002b0c8  mov     [rsp+98h+cy], eax; cy
0x18002b0cc  mov     r9d, [rbx+20h]; cx
0x18002b0d0  mov     r8d, [rbx+1Ch]; y
0x18002b0d4  mov     edx, [rbx+18h]; x
0x18002b0d7  mov     rcx, r12; hdc
0x18002b0da  call    BitBlt
0x18002b0df  nop
0x18002b0e0  add     rsp, 60h
0x18002b0e4  pop     r15
0x18002b0e6  pop     r14
0x18002b0e8  pop     r12
0x18002b0ea  pop     rdi
0x18002b0eb  pop     rsi
0x18002b0ec  pop     rbp
0x18002b0ed  pop     rbx
0x18002b0ee  retn
0x18002b0f0  xor     eax, eax
0x18002b0f2  jmp     short loc_18002B0E0
0x18002b0f4  mov     eax, 1
0x18002b0f9  jmp     short loc_18002B0E0
0x18002b0fb  jmp     short loc_18002B0F0
0x18002b0fd  xor     r15d, r15d
0x18002b100  mov     rcx, r12
0x18002b103  call    CreateCompatibleDCAdvanced
0x18002b108  mov     rdi, rax
0x18002b10b  test    rax, rax
0x18002b10e  jz      loc_18002B1C1
0x18002b114  lea     rax, [rsp+98h+pbmih]
0x18002b119  mov     qword ptr [rsp+98h+rop], rax; BitmapInfoPtr *
0x18002b11e  mov     [rsp+98h+y1], r15d; int
0x18002b123  mov     ecx, [rbx+50h]
0x18002b126  mov     [rsp+98h+x1], ecx; int
0x18002b12a  mov     ecx, [rbx+60h]
0x18002b12d  mov     dword ptr [rsp+98h+hdcSrc], ecx; int
0x18002b131  mov     ecx, [rbx+5Ch]
0x18002b134  mov     [rsp+98h+cy], ecx; int
0x18002b138  mov     r9d, [rbx+58h]
0x18002b13c  mov     r8d, [rbx+54h]
0x18002b140  mov     rdx, rbx; this
0x18002b143  mov     rcx, r14; struct tagHANDLETABLE *
0x18002b146  call    bCheckBitmap
0x18002b14b  mov     rsi, [rsp+98h+pbmih]
0x18002b150  test    eax, eax
0x18002b152  jz      short loc_18002B1AD
0x18002b154  mov     ecx, [rbx+54h]
0x18002b157  add     rcx, rbx
0x18002b15a  mov     r9d, [rbx+5Ch]
0x18002b15e  add     r9, rbx; pjBits
0x18002b161  mov     eax, [rbx+50h]
0x18002b164  mov     dword ptr [rsp+98h+hdcSrc], eax; iUsage
0x18002b168  mov     qword ptr [rsp+98h+cy], rcx; pbmi
0x18002b16d  lea     r8d, [r15+6]; flInit
0x18002b171  mov     rdx, rsi; pbmih
0x18002b174  mov     rcx, rdi; hdc
0x18002b177  call    CreateDIBitmap
0x18002b17c  mov     rbp, rax
0x18002b17f  test    rax, rax
0x18002b182  jz      short loc_18002B1AD
0x18002b184  mov     rdx, rax; h
0x18002b187  mov     rcx, rdi; hdc
0x18002b18a  call    cs:__imp_SelectObject
0x18002b191  nop     dword ptr [rax+rax+00h]
0x18002b196  mov     r14, rax
0x18002b199  test    rax, rax
0x18002b19c  jnz     short loc_18002B1E4
0x18002b19e  mov     rcx, rbp; ho
0x18002b1a1  call    cs:__imp_DeleteObject
0x18002b1a8  nop     dword ptr [rax+rax+00h]
0x18002b1ad  mov     rcx, rdi; hdc
0x18002b1b0  call    cs:__imp_DeleteDC
0x18002b1b7  nop     dword ptr [rax+rax+00h]
0x18002b1bc  mov     bpl, [rsp+98h+var_40]
0x18002b1c1  test    rsi, rsi
0x18002b1c4  jnz     short loc_18002B1CE
0x18002b1c6  mov     eax, r15d
0x18002b1c9  jmp     loc_18002B0E0
0x18002b1ce  test    bpl, bpl
0x18002b1d1  jz      short loc_18002B1C6
0x18002b1d3  mov     rcx, rsi; hMem
0x18002b1d6  call    cs:__imp_LocalFree
0x18002b1dd  nop     dword ptr [rax+rax+00h]
0x18002b1e2  jmp     short loc_18002B1C6
0x18002b1e4  lea     rdx, [rbx+34h]; lpxf
0x18002b1e8  mov     rcx, rdi; hdc
0x18002b1eb  call    cs:__imp_SetWorldTransform
0x18002b1f2  nop     dword ptr [rax+rax+00h]
0x18002b1f7  test    eax, eax
0x18002b1f9  jz      short loc_18002B242
0x18002b1fb  mov     edx, [rbx+4Ch]; color
0x18002b1fe  mov     rcx, rdi; hdc
0x18002b201  call    SetBkColor
0x18002b206  cmp     eax, 0FFFFFFFFh
0x18002b209  jz      short loc_18002B242
0x18002b20b  mov     eax, [rbx+28h]
0x18002b20e  mov     [rsp+98h+rop], eax; rop
0x18002b212  mov     eax, [rbx+30h]
0x18002b215  mov     [rsp+98h+y1], eax; y1
0x18002b219  mov     eax, [rbx+2Ch]
0x18002b21c  mov     [rsp+98h+x1], eax; x1
0x18002b220  mov     [rsp+98h+hdcSrc], rdi; hdcSrc
0x18002b225  mov     eax, [rbx+24h]
0x18002b228  mov     [rsp+98h+cy], eax; cy
0x18002b22c  mov     r9d, [rbx+20h]; cx
0x18002b230  mov     r8d, [rbx+1Ch]; y
0x18002b234  mov     edx, [rbx+18h]; x
0x18002b237  mov     rcx, r12; hdc
0x18002b23a  call    BitBlt
0x18002b23f  mov     r15d, eax
0x18002b242  mov     rdx, r14; h
0x18002b245  mov     rcx, rdi; hdc
0x18002b248  call    cs:__imp_SelectObject
0x18002b24f  nop     dword ptr [rax+rax+00h]
0x18002b254  jmp     loc_18002B19E
```

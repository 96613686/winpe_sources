# MirrorBitmapInDC

- ea: `0x18011f01c`
- end: `0x18011f16e`
- name: `MirrorBitmapInDC`
- size: `338`
- prototype: `__int64 __fastcall(HDC hdc, HANDLE h)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800fd92c`
- `0x1801360cc`
- `0x1801cb410`

## callees

- `0x180114520`
- `0x18011f01c`

## import_xrefs

- `GDI32!DeleteObject` at `0x18011f146`
- `GDI32!DeleteObject` at `0x18011f146`
- `GDI32!GetObjectW` at `0x18011f05d`
- `GDI32!GetObjectW` at `0x18011f05d`
- `GDI32!SelectObject` at `0x18011f0ab`
- `GDI32!SelectObject` at `0x18011f0ab`
- `GDI32!DeleteDC` at `0x18011f09d`
- `GDI32!DeleteDC` at `0x18011f13d`
- `GDI32!DeleteDC` at `0x18011f09d`
- `GDI32!DeleteDC` at `0x18011f13d`
- `GDI32!CreateCompatibleDC` at `0x18011f06e`
- `GDI32!CreateCompatibleDC` at `0x18011f06e`
- `GDI32!SetLayout` at `0x18011f0b9`
- `GDI32!SetLayout` at `0x18011f0fc`
- `GDI32!SetLayout` at `0x18011f0b9`
- `GDI32!SetLayout` at `0x18011f0fc`
- `GDI32!CreateCompatibleBitmap` at `0x18011f08c`
- `GDI32!CreateCompatibleBitmap` at `0x18011f08c`
- `GDI32!BitBlt` at `0x18011f0f1`
- `GDI32!BitBlt` at `0x18011f134`
- `GDI32!BitBlt` at `0x18011f0f1`
- `GDI32!BitBlt` at `0x18011f134`

## pseudocode

```c
int __fastcall MirrorBitmapInDC(HDC hdc, HANDLE h)
{
  HDC CompatibleDC; // rax
  HDC v4; // rbx
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v6; // rsi
  _OWORD pv[2]; // [rsp+50h] [rbp-38h] BYREF

  memset(pv, 0, sizeof(pv));
  LODWORD(CompatibleDC) = GetObjectW(h, 32, pv);
  if ( (_DWORD)CompatibleDC )
  {
    CompatibleDC = CreateCompatibleDC(hdc);
    v4 = CompatibleDC;
    if ( CompatibleDC )
    {
      CompatibleBitmap = CreateCompatibleBitmap(hdc, SDWORD1(pv[0]), SDWORD2(pv[0]));
      v6 = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        SelectObject(v4, CompatibleBitmap);
        SetLayout(v4, 1u);
        BitBlt(v4, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), hdc, 0, 0, 0xCC0020u);
        SetLayout(v4, 0);
        BitBlt(hdc, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), v4, 0, 0, 0xCC0020u);
        DeleteDC(v4);
        LODWORD(CompatibleDC) = DeleteObject(v6);
      }
      else
      {
        LODWORD(CompatibleDC) = DeleteDC(v4);
      }
    }
  }
  return (int)CompatibleDC;
}

```

## disassembly

```asm
0x18011f01c  mov     [rsp+arg_10], rbx
0x18011f021  mov     [rsp+arg_18], rsi
0x18011f026  push    rdi
0x18011f027  sub     rsp, 80h
0x18011f02e  mov     rax, cs:__security_cookie
0x18011f035  xor     rax, rsp
0x18011f038  mov     [rsp+88h+var_18], rax
0x18011f03d  mov     rax, rdx
0x18011f040  lea     r8, [rsp+88h+pv]; pv
0x18011f045  xorps   xmm0, xmm0
0x18011f048  mov     rdi, rcx
0x18011f04b  mov     rcx, rax; h
0x18011f04e  mov     edx, 20h ; ' '; c
0x18011f053  movups  [rsp+88h+pv], xmm0
0x18011f058  movups  [rsp+88h+var_28], xmm0
0x18011f05d  call    cs:__imp_GetObjectW
0x18011f063  test    eax, eax
0x18011f065  jz      loc_18011F14C
0x18011f06b  mov     rcx, rdi; hdc
0x18011f06e  call    cs:__imp_CreateCompatibleDC
0x18011f074  mov     rbx, rax
0x18011f077  test    rax, rax
0x18011f07a  jz      loc_18011F14C
0x18011f080  mov     r8d, dword ptr [rsp+88h+pv+8]; cy
0x18011f085  mov     rcx, rdi; hdc
0x18011f088  mov     edx, dword ptr [rsp+88h+pv+4]; cx
0x18011f08c  call    cs:__imp_CreateCompatibleBitmap
0x18011f092  mov     rsi, rax
0x18011f095  mov     rcx, rbx; hdc
0x18011f098  test    rax, rax
0x18011f09b  jnz     short loc_18011F0A8
0x18011f09d  call    cs:__imp_DeleteDC
0x18011f0a3  jmp     loc_18011F14C
0x18011f0a8  mov     rdx, rsi; h
0x18011f0ab  call    cs:__imp_SelectObject
0x18011f0b1  mov     edx, 1; l
0x18011f0b6  mov     rcx, rbx; hdc
0x18011f0b9  call    cs:__imp_SetLayout
0x18011f0bf  mov     eax, dword ptr [rsp+88h+pv+8]
0x18011f0c3  xor     r8d, r8d; y
0x18011f0c6  mov     r9d, dword ptr [rsp+88h+pv+4]; cx
0x18011f0cb  xor     edx, edx; x
0x18011f0cd  mov     [rsp+88h+rop], 0CC0020h; rop
0x18011f0d5  mov     rcx, rbx; hdc
0x18011f0d8  mov     [rsp+88h+y1], 0; y1
0x18011f0e0  mov     [rsp+88h+x1], 0; x1
0x18011f0e8  mov     [rsp+88h+hdcSrc], rdi; hdcSrc
0x18011f0ed  mov     [rsp+88h+cy], eax; cy
0x18011f0f1  call    cs:__imp_BitBlt
0x18011f0f7  xor     edx, edx; l
0x18011f0f9  mov     rcx, rbx; hdc
0x18011f0fc  call    cs:__imp_SetLayout
0x18011f102  mov     eax, dword ptr [rsp+88h+pv+8]
0x18011f106  xor     r8d, r8d; y
0x18011f109  mov     r9d, dword ptr [rsp+88h+pv+4]; cx
0x18011f10e  xor     edx, edx; x
0x18011f110  mov     [rsp+88h+rop], 0CC0020h; rop
0x18011f118  mov     rcx, rdi; hdc
0x18011f11b  mov     [rsp+88h+y1], 0; y1
0x18011f123  mov     [rsp+88h+x1], 0; x1
0x18011f12b  mov     [rsp+88h+hdcSrc], rbx; hdcSrc
0x18011f130  mov     [rsp+88h+cy], eax; cy
0x18011f134  call    cs:__imp_BitBlt
0x18011f13a  mov     rcx, rbx; hdc
0x18011f13d  call    cs:__imp_DeleteDC
0x18011f143  mov     rcx, rsi; ho
0x18011f146  call    cs:__imp_DeleteObject
0x18011f14c  mov     rcx, [rsp+88h+var_18]
0x18011f151  xor     rcx, rsp; StackCookie
0x18011f154  call    __security_check_cookie
0x18011f159  lea     r11, [rsp+88h+var_8]
0x18011f161  mov     rbx, [r11+20h]
0x18011f165  mov     rsi, [r11+28h]
0x18011f169  mov     rsp, r11
0x18011f16c  pop     rdi
0x18011f16d  retn
```

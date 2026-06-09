# MirrorBitmapInDC

- ea: `0x18001968c`
- end: `0x1800197b5`
- name: `MirrorBitmapInDC`
- size: `297`
- prototype: `__int64 __fastcall(HDC hdc, HANDLE h)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18005506c`
- `0x18005ffa0`
- `0x18007b070`

## callees

- `0x18001968c`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800196cc`
- `GDI32!CreateCompatibleDC` at `0x1800196cc`
- `GDI32!CreateCompatibleBitmap` at `0x1800196ea`
- `GDI32!CreateCompatibleBitmap` at `0x1800196ea`
- `GDI32!SelectObject` at `0x180019702`
- `GDI32!SelectObject` at `0x180019702`
- `GDI32!BitBlt` at `0x180019748`
- `GDI32!BitBlt` at `0x18001978b`
- `GDI32!BitBlt` at `0x180019748`
- `GDI32!BitBlt` at `0x18001978b`
- `GDI32!DeleteObject` at `0x180019794`
- `GDI32!DeleteObject` at `0x180019794`
- `GDI32!GetObjectW` at `0x1800196bb`
- `GDI32!GetObjectW` at `0x1800196bb`
- `GDI32!SetLayout` at `0x180019710`
- `GDI32!SetLayout` at `0x180019753`
- `GDI32!SetLayout` at `0x180019710`
- `GDI32!SetLayout` at `0x180019753`
- `GDI32!DeleteDC` at `0x18001979d`
- `GDI32!DeleteDC` at `0x18001979d`

## pseudocode

```c
int __fastcall MirrorBitmapInDC(HDC hdc, HANDLE h)
{
  HDC CompatibleDC; // rax
  HDC v4; // rbx
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v6; // rsi
  _OWORD pv[2]; // [rsp+50h] [rbp-28h] BYREF

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
        DeleteObject(v6);
      }
      LODWORD(CompatibleDC) = DeleteDC(v4);
    }
  }
  return (int)CompatibleDC;
}

```

## disassembly

```asm
0x18001968c  mov     [rsp+arg_0], rbx
0x180019691  mov     [rsp+arg_8], rsi
0x180019696  push    rdi
0x180019697  sub     rsp, 70h
0x18001969b  mov     rax, rdx
0x18001969e  lea     r8, [rsp+78h+pv]; pv
0x1800196a3  xorps   xmm0, xmm0
0x1800196a6  mov     rdi, rcx
0x1800196a9  mov     rcx, rax; h
0x1800196ac  mov     edx, 20h ; ' '; c
0x1800196b1  movups  [rsp+78h+pv], xmm0
0x1800196b6  movups  [rsp+78h+var_18], xmm0
0x1800196bb  call    cs:__imp_GetObjectW
0x1800196c1  test    eax, eax
0x1800196c3  jz      loc_1800197A3
0x1800196c9  mov     rcx, rdi; hdc
0x1800196cc  call    cs:__imp_CreateCompatibleDC
0x1800196d2  mov     rbx, rax
0x1800196d5  test    rax, rax
0x1800196d8  jz      loc_1800197A3
0x1800196de  mov     r8d, dword ptr [rsp+78h+pv+8]; cy
0x1800196e3  mov     rcx, rdi; hdc
0x1800196e6  mov     edx, dword ptr [rsp+78h+pv+4]; cx
0x1800196ea  call    cs:__imp_CreateCompatibleBitmap
0x1800196f0  mov     rsi, rax
0x1800196f3  test    rax, rax
0x1800196f6  jz      loc_18001979A
0x1800196fc  mov     rdx, rax; h
0x1800196ff  mov     rcx, rbx; hdc
0x180019702  call    cs:__imp_SelectObject
0x180019708  mov     edx, 1; l
0x18001970d  mov     rcx, rbx; hdc
0x180019710  call    cs:__imp_SetLayout
0x180019716  mov     eax, dword ptr [rsp+78h+pv+8]
0x18001971a  xor     r8d, r8d; y
0x18001971d  mov     r9d, dword ptr [rsp+78h+pv+4]; cx
0x180019722  xor     edx, edx; x
0x180019724  mov     [rsp+78h+rop], 0CC0020h; rop
0x18001972c  mov     rcx, rbx; hdc
0x18001972f  mov     [rsp+78h+y1], 0; y1
0x180019737  mov     [rsp+78h+x1], 0; x1
0x18001973f  mov     [rsp+78h+hdcSrc], rdi; hdcSrc
0x180019744  mov     [rsp+78h+cy], eax; cy
0x180019748  call    cs:__imp_BitBlt
0x18001974e  xor     edx, edx; l
0x180019750  mov     rcx, rbx; hdc
0x180019753  call    cs:__imp_SetLayout
0x180019759  mov     eax, dword ptr [rsp+78h+pv+8]
0x18001975d  xor     r8d, r8d; y
0x180019760  mov     r9d, dword ptr [rsp+78h+pv+4]; cx
0x180019765  xor     edx, edx; x
0x180019767  mov     [rsp+78h+rop], 0CC0020h; rop
0x18001976f  mov     rcx, rdi; hdc
0x180019772  mov     [rsp+78h+y1], 0; y1
0x18001977a  mov     [rsp+78h+x1], 0; x1
0x180019782  mov     [rsp+78h+hdcSrc], rbx; hdcSrc
0x180019787  mov     [rsp+78h+cy], eax; cy
0x18001978b  call    cs:__imp_BitBlt
0x180019791  mov     rcx, rsi; ho
0x180019794  call    cs:__imp_DeleteObject
0x18001979a  mov     rcx, rbx; hdc
0x18001979d  call    cs:__imp_DeleteDC
0x1800197a3  lea     r11, [rsp+78h+var_8]
0x1800197a8  mov     rbx, [r11+10h]
0x1800197ac  mov     rsi, [r11+18h]
0x1800197b0  mov     rsp, r11
0x1800197b3  pop     rdi
0x1800197b4  retn
```

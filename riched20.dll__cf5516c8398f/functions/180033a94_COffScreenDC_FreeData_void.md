# COffScreenDC::FreeData(void)

- ea: `0x180033a94`
- end: `0x180033aea`
- name: `?FreeData@COffScreenDC@@AEAAXXZ`
- size: `86`
- prototype: `void __fastcall(COffScreenDC *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180033288`
- `0x180033328`
- `0x1800333d0`
- `0x1800337ac`
- `0x180056fb0`
- `0x1800596c0`

## callees

- `0x180033a94`

## import_xrefs

- `GDI32!DeleteObject` at `0x180033ad5`
- `GDI32!DeleteObject` at `0x180033ad5`
- `GDI32!DeleteDC` at `0x180033ade`
- `GDI32!DeleteDC` at `0x180033ade`
- `GDI32!SelectObject` at `0x180033ac6`
- `GDI32!SelectObject` at `0x180033ac6`
- `GDI32!SelectPalette` at `0x180033ab4`
- `GDI32!SelectPalette` at `0x180033ab4`

## pseudocode

```c
void __fastcall COffScreenDC::FreeData(COffScreenDC *this)
{
  HDC v2; // rcx
  HPALETTE v3; // rdx
  void *v4; // rdx
  void *v5; // rcx

  v2 = *(HDC *)this;
  if ( v2 )
  {
    v3 = (HPALETTE)*((_QWORD *)this + 3);
    if ( v3 )
      SelectPalette(v2, v3, 1);
    v4 = (void *)*((_QWORD *)this + 1);
    if ( v4 )
      SelectObject(*(HDC *)this, v4);
    v5 = (void *)*((_QWORD *)this + 2);
    if ( v5 )
      DeleteObject(v5);
    DeleteDC(*(HDC *)this);
  }
}

```

## disassembly

```asm
0x180033a94  push    rbx
0x180033a96  sub     rsp, 20h
0x180033a9a  mov     rbx, rcx
0x180033a9d  mov     rcx, [rcx]; hdc
0x180033aa0  test    rcx, rcx
0x180033aa3  jz      short loc_180033AE4
0x180033aa5  mov     rdx, [rbx+18h]; hPal
0x180033aa9  test    rdx, rdx
0x180033aac  jz      short loc_180033ABA
0x180033aae  mov     r8d, 1; bForceBkgd
0x180033ab4  call    cs:__imp_SelectPalette
0x180033aba  mov     rdx, [rbx+8]; h
0x180033abe  test    rdx, rdx
0x180033ac1  jz      short loc_180033ACC
0x180033ac3  mov     rcx, [rbx]; hdc
0x180033ac6  call    cs:__imp_SelectObject
0x180033acc  mov     rcx, [rbx+10h]; ho
0x180033ad0  test    rcx, rcx
0x180033ad3  jz      short loc_180033ADB
0x180033ad5  call    cs:__imp_DeleteObject
0x180033adb  mov     rcx, [rbx]; hdc
0x180033ade  call    cs:__imp_DeleteDC
0x180033ae4  add     rsp, 20h
0x180033ae8  pop     rbx
0x180033ae9  retn
```

# COffScreenDC::FreeData(void)

- ea: `0x18002e76c`
- end: `0x18002e7db`
- name: `?FreeData@COffScreenDC@@AEAAXXZ`
- size: `111`
- prototype: `void __fastcall(COffScreenDC *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18002df0c`
- `0x18002dfac`
- `0x18002e060`
- `0x18002e440`
- `0x180058554`
- `0x18005ac94`

## callees

- `0x18002e76c`

## import_xrefs

- `GDI32!DeleteObject` at `0x18002e7b9`
- `GDI32!DeleteObject` at `0x18002e7b9`
- `GDI32!DeleteDC` at `0x18002e7c8`
- `GDI32!DeleteDC` at `0x18002e7c8`
- `GDI32!SelectObject` at `0x18002e7a4`
- `GDI32!SelectObject` at `0x18002e7a4`
- `GDI32!SelectPalette` at `0x18002e78c`
- `GDI32!SelectPalette` at `0x18002e78c`

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
0x18002e76c  push    rbx
0x18002e76e  sub     rsp, 20h
0x18002e772  mov     rbx, rcx
0x18002e775  mov     rcx, [rcx]; hdc
0x18002e778  test    rcx, rcx
0x18002e77b  jz      short loc_18002E7D4
0x18002e77d  mov     rdx, [rbx+18h]; hPal
0x18002e781  test    rdx, rdx
0x18002e784  jz      short loc_18002E798
0x18002e786  mov     r8d, 1; bForceBkgd
0x18002e78c  call    cs:__imp_SelectPalette
0x18002e793  nop     dword ptr [rax+rax+00h]
0x18002e798  mov     rdx, [rbx+8]; h
0x18002e79c  test    rdx, rdx
0x18002e79f  jz      short loc_18002E7B0
0x18002e7a1  mov     rcx, [rbx]; hdc
0x18002e7a4  call    cs:__imp_SelectObject
0x18002e7ab  nop     dword ptr [rax+rax+00h]
0x18002e7b0  mov     rcx, [rbx+10h]; ho
0x18002e7b4  test    rcx, rcx
0x18002e7b7  jz      short loc_18002E7C5
0x18002e7b9  call    cs:__imp_DeleteObject
0x18002e7c0  nop     dword ptr [rax+rax+00h]
0x18002e7c5  mov     rcx, [rbx]; hdc
0x18002e7c8  call    cs:__imp_DeleteDC
0x18002e7cf  nop     dword ptr [rax+rax+00h]
0x18002e7d4  add     rsp, 20h
0x18002e7d8  pop     rbx
0x18002e7d9  retn
```

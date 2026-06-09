# CImmersiveWatermark::_DeleteButtonBrushes(void)

- ea: `0x1400b1a78`
- end: `0x1400b1b3a`
- name: `?_DeleteButtonBrushes@CImmersiveWatermark@@AEAAXXZ`
- size: `194`
- prototype: `void __fastcall(CImmersiveWatermark *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140031b54`
- `0x14013bfa4`

## callees

- `0x1400b1a78`

## import_xrefs

- `GDI32!DeleteObject` at `0x1400b1a8a`
- `GDI32!DeleteObject` at `0x1400b1aa7`
- `GDI32!DeleteObject` at `0x1400b1ac4`
- `GDI32!DeleteObject` at `0x1400b1ae1`
- `GDI32!DeleteObject` at `0x1400b1afe`
- `GDI32!DeleteObject` at `0x1400b1b1b`
- `GDI32!DeleteObject` at `0x1400b1a8a`
- `GDI32!DeleteObject` at `0x1400b1aa7`
- `GDI32!DeleteObject` at `0x1400b1ac4`
- `GDI32!DeleteObject` at `0x1400b1ae1`
- `GDI32!DeleteObject` at `0x1400b1afe`
- `GDI32!DeleteObject` at `0x1400b1b1b`

## pseudocode

```c
void __fastcall CImmersiveWatermark::_DeleteButtonBrushes(CImmersiveWatermark *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    DeleteObject(v2);
    *((_QWORD *)this + 8) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
  {
    DeleteObject(v3);
    *((_QWORD *)this + 9) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 10);
  if ( v4 )
  {
    DeleteObject(v4);
    *((_QWORD *)this + 10) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 12);
  if ( v5 )
  {
    DeleteObject(v5);
    *((_QWORD *)this + 12) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 )
  {
    DeleteObject(v6);
    *((_QWORD *)this + 11) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 13);
  if ( v7 )
  {
    DeleteObject(v7);
    *((_QWORD *)this + 13) = 0;
  }
  *((_BYTE *)this + 112) = 0;
}

```

## disassembly

```asm
0x1400b1a78  push    rbx
0x1400b1a7a  sub     rsp, 20h
0x1400b1a7e  mov     rbx, rcx
0x1400b1a81  mov     rcx, [rcx+40h]; ho
0x1400b1a85  test    rcx, rcx
0x1400b1a88  jz      short loc_1400B1A9E
0x1400b1a8a  call    cs:__imp_DeleteObject
0x1400b1a91  nop     dword ptr [rax+rax+00h]
0x1400b1a96  mov     qword ptr [rbx+40h], 0
0x1400b1a9e  mov     rcx, [rbx+48h]; ho
0x1400b1aa2  test    rcx, rcx
0x1400b1aa5  jz      short loc_1400B1ABB
0x1400b1aa7  call    cs:__imp_DeleteObject
0x1400b1aae  nop     dword ptr [rax+rax+00h]
0x1400b1ab3  mov     qword ptr [rbx+48h], 0
0x1400b1abb  mov     rcx, [rbx+50h]; ho
0x1400b1abf  test    rcx, rcx
0x1400b1ac2  jz      short loc_1400B1AD8
0x1400b1ac4  call    cs:__imp_DeleteObject
0x1400b1acb  nop     dword ptr [rax+rax+00h]
0x1400b1ad0  mov     qword ptr [rbx+50h], 0
0x1400b1ad8  mov     rcx, [rbx+60h]; ho
0x1400b1adc  test    rcx, rcx
0x1400b1adf  jz      short loc_1400B1AF5
0x1400b1ae1  call    cs:__imp_DeleteObject
0x1400b1ae8  nop     dword ptr [rax+rax+00h]
0x1400b1aed  mov     qword ptr [rbx+60h], 0
0x1400b1af5  mov     rcx, [rbx+58h]; ho
0x1400b1af9  test    rcx, rcx
0x1400b1afc  jz      short loc_1400B1B12
0x1400b1afe  call    cs:__imp_DeleteObject
0x1400b1b05  nop     dword ptr [rax+rax+00h]
0x1400b1b0a  mov     qword ptr [rbx+58h], 0
0x1400b1b12  mov     rcx, [rbx+68h]; ho
0x1400b1b16  test    rcx, rcx
0x1400b1b19  jz      short loc_1400B1B2F
0x1400b1b1b  call    cs:__imp_DeleteObject
0x1400b1b22  nop     dword ptr [rax+rax+00h]
0x1400b1b27  mov     qword ptr [rbx+68h], 0
0x1400b1b2f  mov     byte ptr [rbx+70h], 0
0x1400b1b33  add     rsp, 20h
0x1400b1b37  pop     rbx
0x1400b1b38  retn
```

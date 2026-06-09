# EndGlPrinting

- ea: `0x180080b98`
- end: `0x180080c2b`
- name: `EndGlPrinting`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800511f8`
- `0x180051bac`

## callees

- `0x180059f00`
- `0x180080b98`
- `0x1800a5010`

## import_xrefs

- `GDI32!DeleteDC` at `0x180080c10`
- `GDI32!DeleteDC` at `0x180080c10`
- `GDI32!SetStretchBltMode` at `0x180080bc9`
- `GDI32!SetStretchBltMode` at `0x180080bc9`
- `GDI32!DeleteObject` at `0x180080c1f`
- `GDI32!DeleteObject` at `0x180080c1f`

## pseudocode

```c
int __fastcall EndGlPrinting(__int64 a1)
{
  int v2; // edx
  __int64 v3; // rax
  HDC v4; // rcx
  void *v5; // rcx

  if ( *(int *)(a1 + 64) > 1 )
  {
    if ( *(_DWORD *)(a1 + 88) )
      SetBrushOrgEx(*(HDC *)a1, *(_DWORD *)(a1 + 80), *(_DWORD *)(a1 + 84), 0);
    v2 = *(_DWORD *)(a1 + 76);
    if ( v2 )
      SetStretchBltMode(*(HDC *)a1, v2);
  }
  v3 = (*((__int64 (**)(void))&xmmword_1800FA750 + 1))();
  if ( v3 )
    LODWORD(v3) = ((__int64 (__fastcall *)(_QWORD, _QWORD))xmmword_1800FA750)(*(_QWORD *)(a1 + 8), 0);
  if ( *(_QWORD *)(a1 + 24) )
    LODWORD(v3) = (*((__int64 (**)(void))&xmmword_1800FA740 + 1))();
  v4 = *(HDC *)(a1 + 8);
  if ( v4 )
    LODWORD(v3) = DeleteDC(v4);
  v5 = *(void **)(a1 + 16);
  if ( v5 )
    LODWORD(v3) = DeleteObject(v5);
  return v3;
}

```

## disassembly

```asm
0x180080b98  push    rbx
0x180080b9a  sub     rsp, 20h
0x180080b9e  cmp     dword ptr [rcx+40h], 1
0x180080ba2  mov     rbx, rcx
0x180080ba5  jle     short loc_180080BCF
0x180080ba7  cmp     dword ptr [rcx+58h], 0
0x180080bab  jz      short loc_180080BBF
0x180080bad  mov     r8d, [rcx+54h]; y
0x180080bb1  xor     r9d, r9d; lppt
0x180080bb4  mov     edx, [rcx+50h]; x
0x180080bb7  mov     rcx, [rcx]; hdc
0x180080bba  call    SetBrushOrgEx
0x180080bbf  mov     edx, [rbx+4Ch]; mode
0x180080bc2  test    edx, edx
0x180080bc4  jz      short loc_180080BCF
0x180080bc6  mov     rcx, [rbx]; hdc
0x180080bc9  call    cs:__imp_SetStretchBltMode
0x180080bcf  mov     rax, qword ptr cs:xmmword_1800FA750+8
0x180080bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080bdb  test    rax, rax
0x180080bde  jz      short loc_180080BF2
0x180080be0  mov     rcx, [rbx+8]
0x180080be4  xor     edx, edx
0x180080be6  mov     rax, qword ptr cs:xmmword_1800FA750
0x180080bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080bf2  mov     rcx, [rbx+18h]
0x180080bf6  test    rcx, rcx
0x180080bf9  jz      short loc_180080C07
0x180080bfb  mov     rax, qword ptr cs:xmmword_1800FA740+8
0x180080c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080c07  mov     rcx, [rbx+8]; hdc
0x180080c0b  test    rcx, rcx
0x180080c0e  jz      short loc_180080C16
0x180080c10  call    cs:__imp_DeleteDC
0x180080c16  mov     rcx, [rbx+10h]; ho
0x180080c1a  test    rcx, rcx
0x180080c1d  jz      short loc_180080C25
0x180080c1f  call    cs:__imp_DeleteObject
0x180080c25  add     rsp, 20h
0x180080c29  pop     rbx
0x180080c2a  retn
```

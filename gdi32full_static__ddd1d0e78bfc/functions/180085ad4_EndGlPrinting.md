# EndGlPrinting

- ea: `0x180085ad4`
- end: `0x180085b7a`
- name: `EndGlPrinting`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180056ca4`
- `0x180057710`

## callees

- `0x18005dfc0`
- `0x180085ad4`
- `0x1800a8010`

## import_xrefs

- `GDI32!DeleteDC` at `0x180085b52`
- `GDI32!DeleteDC` at `0x180085b52`
- `GDI32!SetStretchBltMode` at `0x180085b05`
- `GDI32!SetStretchBltMode` at `0x180085b05`
- `GDI32!DeleteObject` at `0x180085b67`
- `GDI32!DeleteObject` at `0x180085b67`

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
  v3 = (*((__int64 (**)(void))&xmmword_1800FD840 + 1))();
  if ( v3 )
    LODWORD(v3) = ((__int64 (__fastcall *)(_QWORD, _QWORD))xmmword_1800FD840)(*(_QWORD *)(a1 + 8), 0);
  if ( *(_QWORD *)(a1 + 24) )
    LODWORD(v3) = (*((__int64 (**)(void))&xmmword_1800FD830 + 1))();
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
0x180085ad4  push    rbx
0x180085ad6  sub     rsp, 20h
0x180085ada  cmp     dword ptr [rcx+40h], 1
0x180085ade  mov     rbx, rcx
0x180085ae1  jle     short loc_180085B11
0x180085ae3  cmp     dword ptr [rcx+58h], 0
0x180085ae7  jz      short loc_180085AFB
0x180085ae9  mov     r8d, [rcx+54h]; y
0x180085aed  xor     r9d, r9d; lppt
0x180085af0  mov     edx, [rcx+50h]; x
0x180085af3  mov     rcx, [rcx]; hdc
0x180085af6  call    SetBrushOrgEx
0x180085afb  mov     edx, [rbx+4Ch]; mode
0x180085afe  test    edx, edx
0x180085b00  jz      short loc_180085B11
0x180085b02  mov     rcx, [rbx]; hdc
0x180085b05  call    cs:__imp_SetStretchBltMode
0x180085b0c  nop     dword ptr [rax+rax+00h]
0x180085b11  mov     rax, qword ptr cs:xmmword_1800FD840+8
0x180085b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b1d  test    rax, rax
0x180085b20  jz      short loc_180085B34
0x180085b22  mov     rcx, [rbx+8]
0x180085b26  xor     edx, edx
0x180085b28  mov     rax, qword ptr cs:xmmword_1800FD840
0x180085b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b34  mov     rcx, [rbx+18h]
0x180085b38  test    rcx, rcx
0x180085b3b  jz      short loc_180085B49
0x180085b3d  mov     rax, qword ptr cs:xmmword_1800FD830+8
0x180085b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b49  mov     rcx, [rbx+8]; hdc
0x180085b4d  test    rcx, rcx
0x180085b50  jz      short loc_180085B5E
0x180085b52  call    cs:__imp_DeleteDC
0x180085b59  nop     dword ptr [rax+rax+00h]
0x180085b5e  mov     rcx, [rbx+10h]; ho
0x180085b62  test    rcx, rcx
0x180085b65  jz      short loc_180085B73
0x180085b67  call    cs:__imp_DeleteObject
0x180085b6e  nop     dword ptr [rax+rax+00h]
0x180085b73  add     rsp, 20h
0x180085b77  pop     rbx
0x180085b78  retn
```

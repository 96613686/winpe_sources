# ObHBuildBitmap(_rtfobject *,void * &)

- ea: `0x18007e570`
- end: `0x18007e5f1`
- name: `?ObHBuildBitmap@@YAPEAXPEAU_rtfobject@@AEAPEAX@Z`
- size: `129`
- prototype: `void *__fastcall(struct _rtfobject *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18004bac8`
- `0x18007e570`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x18007e58a`
- `KERNEL32!GlobalLock` at `0x18007e58a`
- `KERNEL32!GlobalUnlock` at `0x18007e5c2`
- `KERNEL32!GlobalUnlock` at `0x18007e5c2`
- `GDI32!CreateBitmap` at `0x18007e5b0`
- `GDI32!CreateBitmap` at `0x18007e5b0`

## pseudocode

```c
HBITMAP __fastcall ObHBuildBitmap(struct _rtfobject *a1, void **a2)
{
  HBITMAP Bitmap; // rsi
  const void *lpBits; // rax
  HBITMAP result; // rax

  Bitmap = 0;
  lpBits = GlobalLock(*a2);
  if ( lpBits )
    Bitmap = CreateBitmap(*((_DWORD *)a1 + 4), *((_DWORD *)a1 + 5), *((__int16 *)a1 + 3), *((__int16 *)a1 + 2), lpBits);
  GlobalUnlock(*a2);
  CW32System::GlobalFree(*a2);
  result = Bitmap;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x18007e570  mov     [rsp+arg_0], rbx
0x18007e575  mov     [rsp+arg_8], rsi
0x18007e57a  push    rdi
0x18007e57b  sub     rsp, 30h
0x18007e57f  mov     rdi, rcx
0x18007e582  mov     rbx, rdx
0x18007e585  mov     rcx, [rdx]; hMem
0x18007e588  xor     esi, esi
0x18007e58a  call    cs:__imp_GlobalLock
0x18007e591  nop     dword ptr [rax+rax+00h]
0x18007e596  test    rax, rax
0x18007e599  jz      short loc_18007E5BF
0x18007e59b  movsx   r9d, word ptr [rdi+4]; nBitCount
0x18007e5a0  movsx   r8d, word ptr [rdi+6]; nPlanes
0x18007e5a5  mov     edx, [rdi+14h]; nHeight
0x18007e5a8  mov     ecx, [rdi+10h]; nWidth
0x18007e5ab  mov     [rsp+38h+lpBits], rax; lpBits
0x18007e5b0  call    cs:__imp_CreateBitmap
0x18007e5b7  nop     dword ptr [rax+rax+00h]
0x18007e5bc  mov     rsi, rax
0x18007e5bf  mov     rcx, [rbx]; hMem
0x18007e5c2  call    cs:__imp_GlobalUnlock
0x18007e5c9  nop     dword ptr [rax+rax+00h]
0x18007e5ce  mov     rcx, [rbx]; void *
0x18007e5d1  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007e5d6  mov     rax, rsi
0x18007e5d9  mov     qword ptr [rbx], 0
0x18007e5e0  mov     rsi, [rsp+38h+arg_8]
0x18007e5e5  mov     rbx, [rsp+38h+arg_0]
0x18007e5ea  add     rsp, 30h
0x18007e5ee  pop     rdi
0x18007e5ef  retn
```

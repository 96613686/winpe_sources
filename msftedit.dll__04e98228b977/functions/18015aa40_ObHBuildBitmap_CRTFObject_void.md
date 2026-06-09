# ObHBuildBitmap(CRTFObject *,void * &)

- ea: `0x18015aa40`
- end: `0x18015aac1`
- name: `?ObHBuildBitmap@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z`
- size: `129`
- prototype: `void *__fastcall(struct CRTFObject *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18008a47c`
- `0x18015aa40`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015aa92`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015aa92`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18015aa5a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18015aa5a`
- `ext-ms-win-gdi-draw-l1-1-0!CreateBitmap` at `0x18015aa80`
- `ext-ms-win-gdi-draw-l1-1-0!CreateBitmap` at `0x18015aa80`

## pseudocode

```c
HBITMAP __fastcall ObHBuildBitmap(struct CRTFObject *a1, void **a2)
{
  HBITMAP Bitmap; // rsi
  const void *lpBits; // rax
  HBITMAP result; // rax

  Bitmap = 0;
  lpBits = GlobalLock(*a2);
  if ( lpBits )
    Bitmap = CreateBitmap(*((_DWORD *)a1 + 5), *((_DWORD *)a1 + 6), *((__int16 *)a1 + 3), *((__int16 *)a1 + 2), lpBits);
  GlobalUnlock(*a2);
  CW32System::GlobalFree(*a2);
  result = Bitmap;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x18015aa40  mov     [rsp+arg_0], rbx
0x18015aa45  mov     [rsp+arg_8], rsi
0x18015aa4a  push    rdi
0x18015aa4b  sub     rsp, 30h
0x18015aa4f  mov     rdi, rcx
0x18015aa52  mov     rbx, rdx
0x18015aa55  mov     rcx, [rdx]; hMem
0x18015aa58  xor     esi, esi
0x18015aa5a  call    cs:__imp_GlobalLock
0x18015aa61  nop     dword ptr [rax+rax+00h]
0x18015aa66  test    rax, rax
0x18015aa69  jz      short loc_18015AA8F
0x18015aa6b  movsx   r9d, word ptr [rdi+4]; nBitCount
0x18015aa70  movsx   r8d, word ptr [rdi+6]; nPlanes
0x18015aa75  mov     edx, [rdi+18h]; nHeight
0x18015aa78  mov     ecx, [rdi+14h]; nWidth
0x18015aa7b  mov     [rsp+38h+lpBits], rax; lpBits
0x18015aa80  call    cs:__imp_CreateBitmap
0x18015aa87  nop     dword ptr [rax+rax+00h]
0x18015aa8c  mov     rsi, rax
0x18015aa8f  mov     rcx, [rbx]; hMem
0x18015aa92  call    cs:__imp_GlobalUnlock
0x18015aa99  nop     dword ptr [rax+rax+00h]
0x18015aa9e  mov     rcx, [rbx]; void *
0x18015aaa1  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18015aaa6  mov     rax, rsi
0x18015aaa9  mov     qword ptr [rbx], 0
0x18015aab0  mov     rsi, [rsp+38h+arg_8]
0x18015aab5  mov     rbx, [rsp+38h+arg_0]
0x18015aaba  add     rsp, 30h
0x18015aabe  pop     rdi
0x18015aabf  retn
```

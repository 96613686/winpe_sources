# GetRandomRgnBounds

- ea: `0x180021ca8`
- end: `0x180021d27`
- name: `GetRandomRgnBounds`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800239e8`
- `0x180023a44`

## callees

- `0x180021ca8`

## import_xrefs

- `GDI32!CreateRectRgn` at `0x180021cc6`
- `GDI32!CreateRectRgn` at `0x180021cc6`
- `GDI32!GetRgnBox` at `0x180021d18`
- `GDI32!GetRgnBox` at `0x180021d18`
- `GDI32!DeleteObject` at `0x180021cfa`
- `GDI32!DeleteObject` at `0x180021cfa`
- `win32u!NtGdiGetRandomRgn` at `0x180021cdf`
- `win32u!NtGdiGetRandomRgn` at `0x180021cdf`

## pseudocode

```c
HRGN __fastcall GetRandomRgnBounds(__int64 a1, struct tagRECT *a2, unsigned int a3)
{
  HRGN result; // rax
  HRGN v7; // rdi
  unsigned int v8; // ebx
  int RandomRgn; // eax

  result = CreateRectRgn(0, 0, 0, 0);
  v7 = result;
  if ( result )
  {
    v8 = 0;
    RandomRgn = NtGdiGetRandomRgn(a1, result, a3);
    if ( RandomRgn )
    {
      if ( RandomRgn == 1 )
        LOBYTE(v8) = GetRgnBox(v7, a2) != 0;
    }
    else
    {
      v8 = 1;
      *(struct _RECTL *)a2 = rclInfinity;
    }
    DeleteObject(v7);
    return (HRGN)v8;
  }
  return result;
}

```

## disassembly

```asm
0x180021ca8  push    rbx
0x180021caa  push    rbp
0x180021cab  push    rsi
0x180021cac  push    rdi
0x180021cad  push    r14
0x180021caf  sub     rsp, 20h
0x180021cb3  mov     ebp, r8d
0x180021cb6  mov     rsi, rdx
0x180021cb9  mov     r14, rcx
0x180021cbc  xor     r8d, r8d; x2
0x180021cbf  xor     edx, edx; y1
0x180021cc1  xor     ecx, ecx; x1
0x180021cc3  xor     r9d, r9d; y2
0x180021cc6  call    cs:__imp_CreateRectRgn
0x180021ccc  mov     rdi, rax
0x180021ccf  test    rax, rax
0x180021cd2  jz      short loc_180021D25
0x180021cd4  mov     r8d, ebp
0x180021cd7  mov     rdx, rax
0x180021cda  mov     rcx, r14
0x180021cdd  xor     ebx, ebx
0x180021cdf  call    cs:__imp_NtGdiGetRandomRgn
0x180021ce5  test    eax, eax
0x180021ce7  jnz     short loc_180021D0D
0x180021ce9  movups  xmm0, cs:?rclInfinity@@3U_RECTL@@A; _RECTL rclInfinity
0x180021cf0  lea     ebx, [rax+1]
0x180021cf3  movdqu  xmmword ptr [rsi], xmm0
0x180021cf7  mov     rcx, rdi; ho
0x180021cfa  call    cs:__imp_DeleteObject
0x180021d00  mov     eax, ebx
0x180021d02  add     rsp, 20h
0x180021d06  pop     r14
0x180021d08  pop     rdi
0x180021d09  pop     rsi
0x180021d0a  pop     rbp
0x180021d0b  pop     rbx
0x180021d0c  retn
0x180021d0d  cmp     eax, 1
0x180021d10  jnz     short loc_180021CF7
0x180021d12  mov     rdx, rsi; lprc
0x180021d15  mov     rcx, rdi; hrgn
0x180021d18  call    cs:__imp_GetRgnBox
0x180021d1e  test    eax, eax
0x180021d20  setnz   bl
0x180021d23  jmp     short loc_180021CF7
0x180021d25  jmp     short loc_180021D02
```

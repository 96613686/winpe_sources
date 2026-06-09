# GetRandomRgnBounds

- ea: `0x18002aa80`
- end: `0x18002ab18`
- name: `GetRandomRgnBounds`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c958`
- `0x18002c9b4`

## callees

- `0x18002aa80`

## import_xrefs

- `GDI32!CreateRectRgn` at `0x18002aa9e`
- `GDI32!CreateRectRgn` at `0x18002aa9e`
- `GDI32!GetRgnBox` at `0x18002ab03`
- `GDI32!GetRgnBox` at `0x18002ab03`
- `GDI32!DeleteObject` at `0x18002aade`
- `GDI32!DeleteObject` at `0x18002aade`
- `win32u!NtGdiGetRandomRgn` at `0x18002aabd`
- `win32u!NtGdiGetRandomRgn` at `0x18002aabd`

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
0x18002aa80  push    rbx
0x18002aa82  push    rbp
0x18002aa83  push    rsi
0x18002aa84  push    rdi
0x18002aa85  push    r14
0x18002aa87  sub     rsp, 20h
0x18002aa8b  mov     ebp, r8d
0x18002aa8e  mov     rsi, rdx
0x18002aa91  mov     r14, rcx
0x18002aa94  xor     r8d, r8d; x2
0x18002aa97  xor     edx, edx; y1
0x18002aa99  xor     ecx, ecx; x1
0x18002aa9b  xor     r9d, r9d; y2
0x18002aa9e  call    cs:__imp_CreateRectRgn
0x18002aaa5  nop     dword ptr [rax+rax+00h]
0x18002aaaa  mov     rdi, rax
0x18002aaad  test    rax, rax
0x18002aab0  jz      short loc_18002AB16
0x18002aab2  mov     r8d, ebp
0x18002aab5  mov     rdx, rax
0x18002aab8  mov     rcx, r14
0x18002aabb  xor     ebx, ebx
0x18002aabd  call    cs:__imp_NtGdiGetRandomRgn
0x18002aac4  nop     dword ptr [rax+rax+00h]
0x18002aac9  test    eax, eax
0x18002aacb  jnz     short loc_18002AAF8
0x18002aacd  movups  xmm0, cs:?rclInfinity@@3U_RECTL@@A; _RECTL rclInfinity
0x18002aad4  lea     ebx, [rax+1]
0x18002aad7  movdqu  xmmword ptr [rsi], xmm0
0x18002aadb  mov     rcx, rdi; ho
0x18002aade  call    cs:__imp_DeleteObject
0x18002aae5  nop     dword ptr [rax+rax+00h]
0x18002aaea  mov     eax, ebx
0x18002aaec  add     rsp, 20h
0x18002aaf0  pop     r14
0x18002aaf2  pop     rdi
0x18002aaf3  pop     rsi
0x18002aaf4  pop     rbp
0x18002aaf5  pop     rbx
0x18002aaf6  retn
0x18002aaf8  cmp     eax, 1
0x18002aafb  jnz     short loc_18002AADB
0x18002aafd  mov     rdx, rsi; lprc
0x18002ab00  mov     rcx, rdi; hrgn
0x18002ab03  call    cs:__imp_GetRgnBox
0x18002ab0a  nop     dword ptr [rax+rax+00h]
0x18002ab0f  test    eax, eax
0x18002ab11  setnz   bl
0x18002ab14  jmp     short loc_18002AADB
0x18002ab16  jmp     short loc_18002AAEC
```

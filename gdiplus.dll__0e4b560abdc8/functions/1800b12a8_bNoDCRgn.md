# bNoDCRgn

- ea: `0x1800b12a8`
- end: `0x1800b132d`
- name: `bNoDCRgn`
- size: `133`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b0ff0`
- `0x180140de0`
- `0x1801443b8`
- `0x180144674`
- `0x180145bf8`

## callees

- `0x1800b12a8`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800b1309`
- `GDI32!DeleteObject` at `0x1800b1309`
- `GDI32!GetRandomRgn` at `0x1800b12f5`
- `GDI32!GetRandomRgn` at `0x1800b12f5`
- `GDI32!CreateRectRgn` at `0x1800b12cb`
- `GDI32!CreateRectRgn` at `0x1800b12cb`

## pseudocode

```c
HRGN __fastcall bNoDCRgn(__int64 a1, int a2)
{
  HRGN result; // rax
  unsigned int v5; // ebx
  HRGN v6; // rdi

  result = CreateRectRgn(0, 0, 0, 0);
  v5 = 0;
  v6 = result;
  if ( result )
  {
    LOBYTE(v5) = GetRandomRgn(*(HDC *)(a1 + 40), result, (a2 != 1) + 1) == 0;
    DeleteObject(v6);
    return (HRGN)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800b12a8  mov     [rsp+arg_0], rbx
0x1800b12ad  mov     [rsp+arg_8], rbp
0x1800b12b2  mov     [rsp+arg_10], rsi
0x1800b12b7  push    rdi
0x1800b12b8  sub     rsp, 20h
0x1800b12bc  mov     esi, edx
0x1800b12be  mov     rbp, rcx
0x1800b12c1  xor     edx, edx; y1
0x1800b12c3  xor     ecx, ecx; x1
0x1800b12c5  xor     r9d, r9d; y2
0x1800b12c8  xor     r8d, r8d; x2
0x1800b12cb  call    cs:__imp_CreateRectRgn
0x1800b12d2  nop     dword ptr [rax+rax+00h]
0x1800b12d7  xor     ebx, ebx
0x1800b12d9  mov     rdi, rax
0x1800b12dc  test    rax, rax
0x1800b12df  jz      short loc_1800B1317
0x1800b12e1  mov     rcx, [rbp+28h]; hdc
0x1800b12e5  mov     r8d, ebx
0x1800b12e8  cmp     esi, 1
0x1800b12eb  mov     rdx, rdi; hrgn
0x1800b12ee  setnz   r8b
0x1800b12f2  inc     r8d; i
0x1800b12f5  call    cs:__imp_GetRandomRgn
0x1800b12fc  nop     dword ptr [rax+rax+00h]
0x1800b1301  test    eax, eax
0x1800b1303  mov     rcx, rdi; ho
0x1800b1306  setz    bl
0x1800b1309  call    cs:__imp_DeleteObject
0x1800b1310  nop     dword ptr [rax+rax+00h]
0x1800b1315  mov     eax, ebx
0x1800b1317  mov     rbx, [rsp+28h+arg_0]
0x1800b131c  mov     rbp, [rsp+28h+arg_8]
0x1800b1321  mov     rsi, [rsp+28h+arg_10]
0x1800b1326  add     rsp, 20h
0x1800b132a  pop     rdi
0x1800b132b  retn
```

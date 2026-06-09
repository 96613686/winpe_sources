# hdcMakeCompatibleDC

- ea: `0x1801417e0`
- end: `0x180141838`
- name: `hdcMakeCompatibleDC`
- size: `88`
- prototype: `__int64 __fastcall(XFORM *lpxf)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800f7f28`
- `0x1800f89e8`
- `0x180140f2c`

## callees

- `0x1801417e0`

## import_xrefs

- `GDI32!SetWorldTransform` at `0x180141815`
- `GDI32!SetWorldTransform` at `0x180141815`
- `GDI32!SetGraphicsMode` at `0x180141809`
- `GDI32!SetGraphicsMode` at `0x180141809`
- `GDI32!DeleteDC` at `0x180141822`
- `GDI32!DeleteDC` at `0x180141822`
- `GDI32!CreateCompatibleDC` at `0x1801417ef`
- `GDI32!CreateCompatibleDC` at `0x1801417ef`

## pseudocode

```c
HDC __fastcall hdcMakeCompatibleDC(XFORM *lpxf)
{
  HDC CompatibleDC; // rax
  HDC v3; // rbx

  CompatibleDC = CreateCompatibleDC(0);
  v3 = CompatibleDC;
  if ( !CompatibleDC )
    return 0;
  SetGraphicsMode(CompatibleDC, 2);
  if ( !SetWorldTransform(v3, lpxf) )
  {
    DeleteDC(v3);
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1801417e0  mov     [rsp+arg_0], rbx
0x1801417e5  push    rdi
0x1801417e6  sub     rsp, 20h
0x1801417ea  mov     rdi, rcx
0x1801417ed  xor     ecx, ecx; hdc
0x1801417ef  call    cs:__imp_CreateCompatibleDC
0x1801417f5  mov     rbx, rax
0x1801417f8  test    rax, rax
0x1801417fb  jnz     short loc_180141801
0x1801417fd  xor     eax, eax
0x1801417ff  jmp     short loc_18014182D
0x180141801  mov     edx, 2; iMode
0x180141806  mov     rcx, rbx; hdc
0x180141809  call    cs:__imp_SetGraphicsMode
0x18014180f  mov     rdx, rdi; lpxf
0x180141812  mov     rcx, rbx; hdc
0x180141815  call    cs:__imp_SetWorldTransform
0x18014181b  test    eax, eax
0x18014181d  jnz     short loc_18014182A
0x18014181f  mov     rcx, rbx; hdc
0x180141822  call    cs:__imp_DeleteDC
0x180141828  jmp     short loc_1801417FD
0x18014182a  mov     rax, rbx
0x18014182d  mov     rbx, [rsp+28h+arg_0]
0x180141832  add     rsp, 20h
0x180141836  pop     rdi
0x180141837  retn
```

# hdcMakeCompatibleDC

- ea: `0x18014a120`
- end: `0x18014a191`
- name: `hdcMakeCompatibleDC`
- size: `113`
- prototype: `__int64 __fastcall(XFORM *lpxf)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800ff3c0`
- `0x1800fff20`
- `0x1801497ec`

## callees

- `0x18014a120`

## import_xrefs

- `GDI32!SetWorldTransform` at `0x18014a161`
- `GDI32!SetWorldTransform` at `0x18014a161`
- `GDI32!SetGraphicsMode` at `0x18014a14f`
- `GDI32!SetGraphicsMode` at `0x18014a14f`
- `GDI32!DeleteDC` at `0x18014a174`
- `GDI32!DeleteDC` at `0x18014a174`
- `GDI32!CreateCompatibleDC` at `0x18014a12f`
- `GDI32!CreateCompatibleDC` at `0x18014a12f`

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
0x18014a120  mov     [rsp+arg_0], rbx
0x18014a125  push    rdi
0x18014a126  sub     rsp, 20h
0x18014a12a  mov     rdi, rcx
0x18014a12d  xor     ecx, ecx; hdc
0x18014a12f  call    cs:__imp_CreateCompatibleDC
0x18014a136  nop     dword ptr [rax+rax+00h]
0x18014a13b  mov     rbx, rax
0x18014a13e  test    rax, rax
0x18014a141  jnz     short loc_18014A147
0x18014a143  xor     eax, eax
0x18014a145  jmp     short loc_18014A185
0x18014a147  mov     edx, 2; iMode
0x18014a14c  mov     rcx, rbx; hdc
0x18014a14f  call    cs:__imp_SetGraphicsMode
0x18014a156  nop     dword ptr [rax+rax+00h]
0x18014a15b  mov     rdx, rdi; lpxf
0x18014a15e  mov     rcx, rbx; hdc
0x18014a161  call    cs:__imp_SetWorldTransform
0x18014a168  nop     dword ptr [rax+rax+00h]
0x18014a16d  test    eax, eax
0x18014a16f  jnz     short loc_18014A182
0x18014a171  mov     rcx, rbx; hdc
0x18014a174  call    cs:__imp_DeleteDC
0x18014a17b  nop     dword ptr [rax+rax+00h]
0x18014a180  jmp     short loc_18014A143
0x18014a182  mov     rax, rbx
0x18014a185  mov     rbx, [rsp+28h+arg_0]
0x18014a18a  add     rsp, 20h
0x18014a18e  pop     rdi
0x18014a18f  retn
```

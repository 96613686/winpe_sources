# hdcMakeCompatibleDC

- ea: `0x1801440d0`
- end: `0x180144141`
- name: `hdcMakeCompatibleDC`
- size: `113`
- prototype: `__int64 __fastcall(XFORM *lpxf)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180141ed8`
- `0x1801427e0`
- `0x1801432b0`

## callees

- `0x1801440d0`

## import_xrefs

- `GDI32!SetWorldTransform` at `0x180144111`
- `GDI32!SetWorldTransform` at `0x180144111`
- `GDI32!SetGraphicsMode` at `0x1801440ff`
- `GDI32!SetGraphicsMode` at `0x1801440ff`
- `GDI32!DeleteDC` at `0x180144124`
- `GDI32!DeleteDC` at `0x180144124`
- `GDI32!CreateCompatibleDC` at `0x1801440df`
- `GDI32!CreateCompatibleDC` at `0x1801440df`

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
0x1801440d0  mov     [rsp+arg_0], rbx
0x1801440d5  push    rdi
0x1801440d6  sub     rsp, 20h
0x1801440da  mov     rdi, rcx
0x1801440dd  xor     ecx, ecx; hdc
0x1801440df  call    cs:__imp_CreateCompatibleDC
0x1801440e6  nop     dword ptr [rax+rax+00h]
0x1801440eb  mov     rbx, rax
0x1801440ee  test    rax, rax
0x1801440f1  jnz     short loc_1801440F7
0x1801440f3  xor     eax, eax
0x1801440f5  jmp     short loc_180144135
0x1801440f7  mov     edx, 2; iMode
0x1801440fc  mov     rcx, rbx; hdc
0x1801440ff  call    cs:__imp_SetGraphicsMode
0x180144106  nop     dword ptr [rax+rax+00h]
0x18014410b  mov     rdx, rdi; lpxf
0x18014410e  mov     rcx, rbx; hdc
0x180144111  call    cs:__imp_SetWorldTransform
0x180144118  nop     dword ptr [rax+rax+00h]
0x18014411d  test    eax, eax
0x18014411f  jnz     short loc_180144132
0x180144121  mov     rcx, rbx; hdc
0x180144124  call    cs:__imp_DeleteDC
0x18014412b  nop     dword ptr [rax+rax+00h]
0x180144130  jmp     short loc_1801440F3
0x180144132  mov     rax, rbx
0x180144135  mov     rbx, [rsp+28h+arg_0]
0x18014413a  add     rsp, 20h
0x18014413e  pop     rdi
0x18014413f  retn
```

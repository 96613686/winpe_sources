# LDIDestroyDecompression

- ea: `0x180008dc8`
- end: `0x180008e2f`
- name: `LDIDestroyDecompression`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800088c0`

## callees

- `0x180008dc8`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall LDIDestroyDecompression(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rcx
  void (__fastcall *v4)(__int64); // rax

  if ( *(_DWORD *)a1 != 1128875084 )
    return 2;
  v2 = *(_QWORD *)(a1 + 72);
  if ( *(_QWORD *)v2 )
  {
    (*(void (**)(void))(v2 + 12024))();
    *(_QWORD *)v2 = 0;
  }
  v3 = *(_QWORD *)(a1 + 72);
  v4 = *(void (__fastcall **)(__int64))(a1 + 16);
  *(_DWORD *)a1 = 0;
  v4(v3);
  (*(void (__fastcall **)(__int64))(a1 + 16))(a1);
  return 0;
}

```

## disassembly

```asm
0x180008dc8  mov     [rsp+arg_0], rbx
0x180008dcd  push    rdi
0x180008dce  sub     rsp, 20h
0x180008dd2  cmp     dword ptr [rcx], 4349444Ch
0x180008dd8  mov     rbx, rcx
0x180008ddb  jnz     short loc_180008E28
0x180008ddd  mov     rdi, [rcx+48h]
0x180008de1  mov     rcx, [rdi]
0x180008de4  test    rcx, rcx
0x180008de7  jz      short loc_180008DFC
0x180008de9  mov     rax, [rdi+2EF8h]
0x180008df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df5  mov     qword ptr [rdi], 0
0x180008dfc  mov     rcx, [rbx+48h]
0x180008e00  mov     rax, [rbx+10h]
0x180008e04  mov     dword ptr [rbx], 0
0x180008e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0f  mov     rax, [rbx+10h]
0x180008e13  mov     rcx, rbx
0x180008e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e1b  xor     eax, eax
0x180008e1d  mov     rbx, [rsp+28h+arg_0]
0x180008e22  add     rsp, 20h
0x180008e26  pop     rdi
0x180008e27  retn
0x180008e28  mov     eax, 2
0x180008e2d  jmp     short loc_180008E1D
```

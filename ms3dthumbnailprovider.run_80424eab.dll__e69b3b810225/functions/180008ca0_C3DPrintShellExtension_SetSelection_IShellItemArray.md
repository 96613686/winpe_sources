# C3DPrintShellExtension::SetSelection(IShellItemArray *)

- ea: `0x180008ca0`
- end: `0x180008cea`
- name: `?SetSelection@C3DPrintShellExtension@@UEAAJPEAUIShellItemArray@@@Z`
- size: `74`
- prototype: `__int64 __fastcall(C3DPrintShellExtension *__hidden this, struct IShellItemArray *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008ca0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall C3DPrintShellExtension::SetSelection(C3DPrintShellExtension *this, struct IShellItemArray *a2)
{
  __int64 v4; // rcx

  if ( a2 )
    ((void (__fastcall *)(struct IShellItemArray *))a2->lpVtbl->AddRef)(a2);
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)this + 2) = a2;
  return 0;
}

```

## disassembly

```asm
0x180008ca0  mov     [rsp+arg_0], rbx
0x180008ca5  push    rdi
0x180008ca6  sub     rsp, 20h
0x180008caa  mov     rbx, rdx
0x180008cad  mov     rdi, rcx
0x180008cb0  test    rdx, rdx
0x180008cb3  jz      short loc_180008CC4
0x180008cb5  mov     rax, [rdx]
0x180008cb8  mov     rcx, rdx
0x180008cbb  mov     rax, [rax+8]
0x180008cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc4  mov     rcx, [rdi+10h]
0x180008cc8  test    rcx, rcx
0x180008ccb  jz      short loc_180008CD9
0x180008ccd  mov     rax, [rcx]
0x180008cd0  mov     rax, [rax+10h]
0x180008cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cd9  mov     [rdi+10h], rbx
0x180008cdd  xor     eax, eax
0x180008cdf  mov     rbx, [rsp+28h+arg_0]
0x180008ce4  add     rsp, 20h
0x180008ce8  pop     rdi
0x180008ce9  retn
```

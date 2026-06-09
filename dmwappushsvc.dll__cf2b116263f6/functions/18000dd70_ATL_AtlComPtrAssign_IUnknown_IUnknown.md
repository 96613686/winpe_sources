# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x18000dd70`
- end: `0x18000ddc2`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000df4c`
- `0x18000f960`
- `0x18000faf0`
- `0x18000fe10`

## callees

- `0x18000dd70`
- `0x180012010`

## pseudocode

```c
struct IUnknown *__fastcall ATL::AtlComPtrAssign(struct IUnknown **a1, struct IUnknown *a2)
{
  if ( !a1 )
    return 0;
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  if ( *a1 )
    ((void (__fastcall *)(_QWORD))(*a1)->lpVtbl->Release)(*a1);
  *a1 = a2;
  return a2;
}

```

## disassembly

```asm
0x18000dd70  mov     [rsp+arg_0], rbx
0x18000dd75  push    rdi
0x18000dd76  sub     rsp, 20h
0x18000dd7a  mov     rbx, rdx
0x18000dd7d  mov     rdi, rcx
0x18000dd80  test    rcx, rcx
0x18000dd83  jnz     short loc_18000DD89
0x18000dd85  xor     eax, eax
0x18000dd87  jmp     short loc_18000DDB7
0x18000dd89  test    rbx, rbx
0x18000dd8c  jz      short loc_18000DD9D
0x18000dd8e  mov     rax, [rdx]
0x18000dd91  mov     rcx, rbx
0x18000dd94  mov     rax, [rax+8]
0x18000dd98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd9d  mov     rcx, [rdi]
0x18000dda0  test    rcx, rcx
0x18000dda3  jz      short loc_18000DDB1
0x18000dda5  mov     rax, [rcx]
0x18000dda8  mov     rax, [rax+10h]
0x18000ddac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddb1  mov     [rdi], rbx
0x18000ddb4  mov     rax, rbx
0x18000ddb7  mov     rbx, [rsp+28h+arg_0]
0x18000ddbc  add     rsp, 20h
0x18000ddc0  pop     rdi
0x18000ddc1  retn
```

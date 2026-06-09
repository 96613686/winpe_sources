# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x1800095d4`
- end: `0x180009626`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a1a8`
- `0x18000a900`
- `0x18000e560`
- `0x18000ec10`
- `0x18000f23c`
- `0x1800130f8`
- `0x18001a638`
- `0x18001c928`
- `0x18001f010`
- `0x180020154`
- `0x180021d68`
- `0x1800245e0`

## callees

- `0x1800095d4`
- `0x180029010`

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
0x1800095d4  mov     [rsp+arg_0], rbx
0x1800095d9  push    rdi
0x1800095da  sub     rsp, 20h
0x1800095de  mov     rbx, rdx
0x1800095e1  mov     rdi, rcx
0x1800095e4  test    rcx, rcx
0x1800095e7  jnz     short loc_1800095ED
0x1800095e9  xor     eax, eax
0x1800095eb  jmp     short loc_18000961B
0x1800095ed  test    rbx, rbx
0x1800095f0  jz      short loc_180009601
0x1800095f2  mov     rax, [rdx]
0x1800095f5  mov     rcx, rbx
0x1800095f8  mov     rax, [rax+8]
0x1800095fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009601  mov     rcx, [rdi]
0x180009604  test    rcx, rcx
0x180009607  jz      short loc_180009615
0x180009609  mov     rax, [rcx]
0x18000960c  mov     rax, [rax+10h]
0x180009610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009615  mov     [rdi], rbx
0x180009618  mov     rax, rbx
0x18000961b  mov     rbx, [rsp+28h+arg_0]
0x180009620  add     rsp, 20h
0x180009624  pop     rdi
0x180009625  retn
```

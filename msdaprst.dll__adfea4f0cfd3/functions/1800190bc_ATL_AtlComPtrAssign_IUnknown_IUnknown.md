# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x1800190bc`
- end: `0x180019106`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `74`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c400`
- `0x18001c688`
- `0x180022240`

## callees

- `0x1800190bc`
- `0x180031010`

## pseudocode

```c
struct IUnknown *__fastcall ATL::AtlComPtrAssign(struct IUnknown **a1, struct IUnknown *a2)
{
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
0x1800190bc  mov     [rsp+arg_0], rbx
0x1800190c1  push    rdi
0x1800190c2  sub     rsp, 20h
0x1800190c6  mov     rbx, rdx
0x1800190c9  mov     rdi, rcx
0x1800190cc  test    rdx, rdx
0x1800190cf  jz      short loc_1800190E0
0x1800190d1  mov     rax, [rdx]
0x1800190d4  mov     rcx, rdx
0x1800190d7  mov     rax, [rax+8]
0x1800190db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190e0  mov     rcx, [rdi]
0x1800190e3  test    rcx, rcx
0x1800190e6  jz      short loc_1800190F4
0x1800190e8  mov     rax, [rcx]
0x1800190eb  mov     rax, [rax+10h]
0x1800190ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190f4  mov     [rdi], rbx
0x1800190f7  mov     rax, rbx
0x1800190fa  mov     rbx, [rsp+28h+arg_0]
0x1800190ff  add     rsp, 20h
0x180019103  pop     rdi
0x180019104  retn
```

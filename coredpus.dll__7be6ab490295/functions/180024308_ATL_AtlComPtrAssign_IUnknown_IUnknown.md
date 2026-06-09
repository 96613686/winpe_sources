# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x180024308`
- end: `0x18002435b`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `83`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024570`
- `0x180024fd0`
- `0x180025130`
- `0x180025300`
- `0x180025340`
- `0x1800253a0`
- `0x1800254a0`
- `0x180025c40`
- `0x180026480`
- `0x180026c80`
- `0x180027230`
- `0x180029240`

## callees

- `0x180024308`
- `0x180030010`

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
0x180024308  mov     [rsp+arg_0], rbx
0x18002430d  push    rdi
0x18002430e  sub     rsp, 20h
0x180024312  mov     rbx, rdx
0x180024315  mov     rdi, rcx
0x180024318  test    rcx, rcx
0x18002431b  jnz     short loc_180024321
0x18002431d  xor     eax, eax
0x18002431f  jmp     short loc_18002434F
0x180024321  test    rbx, rbx
0x180024324  jz      short loc_180024335
0x180024326  mov     rax, [rdx]
0x180024329  mov     rcx, rbx
0x18002432c  mov     rax, [rax+8]
0x180024330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024335  mov     rcx, [rdi]
0x180024338  test    rcx, rcx
0x18002433b  jz      short loc_180024349
0x18002433d  mov     rax, [rcx]
0x180024340  mov     rax, [rax+10h]
0x180024344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024349  mov     [rdi], rbx
0x18002434c  mov     rax, rbx
0x18002434f  mov     rbx, [rsp+28h+arg_0]
0x180024354  add     rsp, 20h
0x180024358  pop     rdi
0x180024359  retn
```

# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x180003458`
- end: `0x1800034aa`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003650`
- `0x180003730`
- `0x180004940`
- `0x18000c4dc`
- `0x1800122d0`
- `0x180012a70`

## callees

- `0x180003458`
- `0x180015010`

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
0x180003458  mov     [rsp+arg_0], rbx
0x18000345d  push    rdi
0x18000345e  sub     rsp, 20h
0x180003462  mov     rbx, rdx
0x180003465  mov     rdi, rcx
0x180003468  test    rcx, rcx
0x18000346b  jnz     short loc_180003471
0x18000346d  xor     eax, eax
0x18000346f  jmp     short loc_18000349F
0x180003471  test    rbx, rbx
0x180003474  jz      short loc_180003485
0x180003476  mov     rax, [rdx]
0x180003479  mov     rcx, rbx
0x18000347c  mov     rax, [rax+8]
0x180003480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003485  mov     rcx, [rdi]
0x180003488  test    rcx, rcx
0x18000348b  jz      short loc_180003499
0x18000348d  mov     rax, [rcx]
0x180003490  mov     rax, [rax+10h]
0x180003494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003499  mov     [rdi], rbx
0x18000349c  mov     rax, rbx
0x18000349f  mov     rbx, [rsp+28h+arg_0]
0x1800034a4  add     rsp, 20h
0x1800034a8  pop     rdi
0x1800034a9  retn
```

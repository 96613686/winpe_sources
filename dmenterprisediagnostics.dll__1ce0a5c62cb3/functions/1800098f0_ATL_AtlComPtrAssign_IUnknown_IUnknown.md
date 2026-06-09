# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x1800098f0`
- end: `0x180009942`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a844`
- `0x18000b810`
- `0x18000ce30`
- `0x18000d024`

## callees

- `0x1800098f0`
- `0x180026010`

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
0x1800098f0  mov     [rsp+arg_0], rbx
0x1800098f5  push    rdi
0x1800098f6  sub     rsp, 20h
0x1800098fa  mov     rbx, rdx
0x1800098fd  mov     rdi, rcx
0x180009900  test    rcx, rcx
0x180009903  jnz     short loc_180009909
0x180009905  xor     eax, eax
0x180009907  jmp     short loc_180009937
0x180009909  test    rbx, rbx
0x18000990c  jz      short loc_18000991D
0x18000990e  mov     rax, [rdx]
0x180009911  mov     rcx, rbx
0x180009914  mov     rax, [rax+8]
0x180009918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000991d  mov     rcx, [rdi]
0x180009920  test    rcx, rcx
0x180009923  jz      short loc_180009931
0x180009925  mov     rax, [rcx]
0x180009928  mov     rax, [rax+10h]
0x18000992c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009931  mov     [rdi], rbx
0x180009934  mov     rax, rbx
0x180009937  mov     rbx, [rsp+28h+arg_0]
0x18000993c  add     rsp, 20h
0x180009940  pop     rdi
0x180009941  retn
```

# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x180009834`
- end: `0x180009886`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a0dc`
- `0x18000a184`
- `0x18000ac60`
- `0x18000dc88`
- `0x18000ddb4`
- `0x180017c68`

## callees

- `0x180009834`
- `0x180034010`

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
0x180009834  mov     [rsp+arg_0], rbx
0x180009839  push    rdi
0x18000983a  sub     rsp, 20h
0x18000983e  mov     rbx, rdx
0x180009841  mov     rdi, rcx
0x180009844  test    rcx, rcx
0x180009847  jnz     short loc_18000984D
0x180009849  xor     eax, eax
0x18000984b  jmp     short loc_18000987B
0x18000984d  test    rbx, rbx
0x180009850  jz      short loc_180009861
0x180009852  mov     rax, [rdx]
0x180009855  mov     rcx, rbx
0x180009858  mov     rax, [rax+8]
0x18000985c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009861  mov     rcx, [rdi]
0x180009864  test    rcx, rcx
0x180009867  jz      short loc_180009875
0x180009869  mov     rax, [rcx]
0x18000986c  mov     rax, [rax+10h]
0x180009870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009875  mov     [rdi], rbx
0x180009878  mov     rax, rbx
0x18000987b  mov     rbx, [rsp+28h+arg_0]
0x180009880  add     rsp, 20h
0x180009884  pop     rdi
0x180009885  retn
```

# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x180009dc8`
- end: `0x180009e1b`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `83`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000adcc`
- `0x18000bd80`
- `0x18000d480`
- `0x18000d67c`

## callees

- `0x180009dc8`
- `0x180027010`

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
0x180009dc8  mov     [rsp+arg_0], rbx
0x180009dcd  push    rdi
0x180009dce  sub     rsp, 20h
0x180009dd2  mov     rbx, rdx
0x180009dd5  mov     rdi, rcx
0x180009dd8  test    rcx, rcx
0x180009ddb  jnz     short loc_180009DE1
0x180009ddd  xor     eax, eax
0x180009ddf  jmp     short loc_180009E0F
0x180009de1  test    rbx, rbx
0x180009de4  jz      short loc_180009DF5
0x180009de6  mov     rax, [rdx]
0x180009de9  mov     rcx, rbx
0x180009dec  mov     rax, [rax+8]
0x180009df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df5  mov     rcx, [rdi]
0x180009df8  test    rcx, rcx
0x180009dfb  jz      short loc_180009E09
0x180009dfd  mov     rax, [rcx]
0x180009e00  mov     rax, [rax+10h]
0x180009e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e09  mov     [rdi], rbx
0x180009e0c  mov     rax, rbx
0x180009e0f  mov     rbx, [rsp+28h+arg_0]
0x180009e14  add     rsp, 20h
0x180009e18  pop     rdi
0x180009e19  retn
```

# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x18000fd58`
- end: `0x18000fdaa`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `82`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fc0c`
- `0x18000fc4c`
- `0x1800185a0`
- `0x18001dd30`
- `0x1800251a0`
- `0x180028310`
- `0x18002e020`
- `0x180032900`
- `0x180037b30`
- `0x18003c700`
- `0x18003fc84`
- `0x18003fdb4`
- `0x180040bb0`
- `0x180040d54`

## callees

- `0x18000fd58`
- `0x18004a010`

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
0x18000fd58  mov     [rsp+arg_0], rbx
0x18000fd5d  push    rdi
0x18000fd5e  sub     rsp, 20h
0x18000fd62  mov     rbx, rdx
0x18000fd65  mov     rdi, rcx
0x18000fd68  test    rcx, rcx
0x18000fd6b  jnz     short loc_18000FD71
0x18000fd6d  xor     eax, eax
0x18000fd6f  jmp     short loc_18000FD9F
0x18000fd71  test    rbx, rbx
0x18000fd74  jz      short loc_18000FD85
0x18000fd76  mov     rax, [rdx]
0x18000fd79  mov     rcx, rbx
0x18000fd7c  mov     rax, [rax+8]
0x18000fd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd85  mov     rcx, [rdi]
0x18000fd88  test    rcx, rcx
0x18000fd8b  jz      short loc_18000FD99
0x18000fd8d  mov     rax, [rcx]
0x18000fd90  mov     rax, [rax+10h]
0x18000fd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd99  mov     [rdi], rbx
0x18000fd9c  mov     rax, rbx
0x18000fd9f  mov     rbx, [rsp+28h+arg_0]
0x18000fda4  add     rsp, 20h
0x18000fda8  pop     rdi
0x18000fda9  retn
```

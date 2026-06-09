# Microsoft::WRL::Details::Make<GenericBStrNode,>(void)

- ea: `0x180010b00`
- end: `0x180010b5b`
- name: `??$Make@VGenericBStrNode@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VGenericBStrNode@@@12@XZ`
- size: `91`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010bb0`
- `0x180014f14`
- `0x180022e48`
- `0x180025e18`

## callees

- `0x1800030e8`
- `0x18000fffc`
- `0x180010b00`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
GenericBStrNode **__fastcall Microsoft::WRL::Details::Make<GenericBStrNode,>(GenericBStrNode **a1)
{
  GenericBStrNode *v2; // rax
  GenericBStrNode *v3; // rdi

  *a1 = 0;
  v2 = (GenericBStrNode *)operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
  if ( v2 )
  {
    v3 = GenericBStrNode::GenericBStrNode(v2);
    if ( *a1 )
      (*(void (__fastcall **)(GenericBStrNode *))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
  }
  return a1;
}

```

## disassembly

```asm
0x180010b00  mov     [rsp+arg_0], rbx
0x180010b05  push    rdi
0x180010b06  sub     rsp, 20h
0x180010b0a  mov     rbx, rcx
0x180010b0d  mov     qword ptr [rcx], 0
0x180010b14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010b1b  mov     ecx, 38h ; '8'; unsigned __int64
0x180010b20  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010b25  test    rax, rax
0x180010b28  jz      short loc_180010B4C
0x180010b2a  mov     rcx, rax; this
0x180010b2d  call    ??0GenericBStrNode@@QEAA@XZ; GenericBStrNode::GenericBStrNode(void)
0x180010b32  mov     rdi, rax
0x180010b35  mov     rcx, [rbx]
0x180010b38  test    rcx, rcx
0x180010b3b  jz      short loc_180010B49
0x180010b3d  mov     rdx, [rcx]
0x180010b40  mov     rax, [rdx+10h]
0x180010b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b49  mov     [rbx], rdi
0x180010b4c  mov     rax, rbx
0x180010b4f  mov     rbx, [rsp+28h+arg_0]
0x180010b54  add     rsp, 20h
0x180010b58  pop     rdi
0x180010b59  retn
```

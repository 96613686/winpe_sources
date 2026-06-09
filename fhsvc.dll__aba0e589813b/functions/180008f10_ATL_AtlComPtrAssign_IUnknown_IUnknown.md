# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x180008f10`
- end: `0x180008f43`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `51`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c210`
- `0x18000c5d4`
- `0x180010894`

## callees

- `0x180008f10`
- `0x180013010`

## pseudocode

```c
struct IUnknown *__fastcall ATL::AtlComPtrAssign(struct IUnknown **a1, struct IUnknown *a2)
{
  __int64 v3; // rcx

  if ( a1 )
  {
    v3 = (__int64)*a1;
    if ( v3 )
      (*(void (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v3 + 16LL))(v3, a2);
    *a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180008f10  push    rbx
0x180008f12  sub     rsp, 20h
0x180008f16  mov     rbx, rcx
0x180008f19  test    rcx, rcx
0x180008f1c  jz      short loc_180008F2D
0x180008f1e  mov     rcx, [rcx]
0x180008f21  test    rcx, rcx
0x180008f24  jnz     short loc_180008F35
0x180008f26  mov     qword ptr [rbx], 0
0x180008f2d  xor     eax, eax
0x180008f2f  add     rsp, 20h
0x180008f33  pop     rbx
0x180008f34  retn
0x180008f35  mov     rax, [rcx]
0x180008f38  mov     rax, [rax+10h]
0x180008f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f41  jmp     short loc_180008F26
```

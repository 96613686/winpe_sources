# ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)

- ea: `0x1800029b0`
- end: `0x1800029e1`
- name: `?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z`
- size: `49`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000290c`
- `0x18000aa98`

## callees

- `0x1800029b0`
- `0x180015010`

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
0x1800029b0  push    rbx
0x1800029b2  sub     rsp, 20h
0x1800029b6  mov     rbx, rcx
0x1800029b9  test    rcx, rcx
0x1800029bc  jz      short loc_1800029D9
0x1800029be  mov     rcx, [rcx]
0x1800029c1  test    rcx, rcx
0x1800029c4  jz      short loc_1800029D2
0x1800029c6  mov     rax, [rcx]
0x1800029c9  mov     rax, [rax+10h]
0x1800029cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d2  mov     qword ptr [rbx], 0
0x1800029d9  xor     eax, eax
0x1800029db  add     rsp, 20h
0x1800029df  pop     rbx
0x1800029e0  retn
```

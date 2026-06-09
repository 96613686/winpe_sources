# D3DDeviceLock::D3DDeviceLock(ID3D11Multithread *)

- ea: `0x18000e3a0`
- end: `0x18000e3e9`
- name: `??0D3DDeviceLock@@QEAA@PEAUID3D11Multithread@@@Z`
- size: `73`
- prototype: `D3DDeviceLock *__fastcall(D3DDeviceLock *__hidden this, struct ID3D11Multithread *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f254`
- `0x180010d20`
- `0x180010eb4`
- `0x180011128`
- `0x180011ee8`

## callees

- `0x18000e3a0`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
D3DDeviceLock *__fastcall D3DDeviceLock::D3DDeviceLock(D3DDeviceLock *this, struct ID3D11Multithread *a2)
{
  *(_QWORD *)this = 0;
  if ( a2 )
  {
    *(_QWORD *)this = a2;
    ((void (__fastcall *)(struct ID3D11Multithread *))a2->lpVtbl->AddRef)(a2);
    if ( *(_QWORD *)this )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 24LL))(*(_QWORD *)this);
  }
  return this;
}

```

## disassembly

```asm
0x18000e3a0  mov     [rsp+arg_0], rcx
0x18000e3a5  push    rbx
0x18000e3a6  sub     rsp, 20h
0x18000e3aa  mov     rbx, rcx
0x18000e3ad  mov     qword ptr [rcx], 0
0x18000e3b4  test    rdx, rdx
0x18000e3b7  jz      short loc_18000E3E0
0x18000e3b9  mov     [rcx], rdx
0x18000e3bc  mov     rax, [rdx]
0x18000e3bf  mov     rcx, rdx
0x18000e3c2  mov     rax, [rax+8]
0x18000e3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3cb  mov     rcx, [rbx]
0x18000e3ce  test    rcx, rcx
0x18000e3d1  jz      short loc_18000E3E0
0x18000e3d3  mov     rax, [rcx]
0x18000e3d6  mov     rax, [rax+18h]
0x18000e3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3df  nop
0x18000e3e0  mov     rax, rbx
0x18000e3e3  add     rsp, 20h
0x18000e3e7  pop     rbx
0x18000e3e8  retn
```

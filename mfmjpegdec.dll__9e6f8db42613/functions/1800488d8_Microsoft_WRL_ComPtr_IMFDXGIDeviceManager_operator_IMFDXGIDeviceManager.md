# Microsoft::WRL::ComPtr<IMFDXGIDeviceManager>::operator=(IMFDXGIDeviceManager *)

- ea: `0x1800488d8`
- end: `0x180048925`
- name: `??4?$ComPtr@UIMFDXGIDeviceManager@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFDXGIDeviceManager@@@Z`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180048674`
- `0x18004d134`

## callees

- `0x180020598`
- `0x1800488d8`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall Microsoft::WRL::ComPtr<IMFDXGIDeviceManager>::operator=(__int64 *a1, __int64 a2)
{
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v5 = *a1;
    *a1 = a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x1800488d8  mov     [rsp+arg_8], rbx
0x1800488dd  push    rdi
0x1800488de  sub     rsp, 20h
0x1800488e2  mov     rbx, rdx
0x1800488e5  mov     rdi, rcx
0x1800488e8  cmp     [rcx], rdx
0x1800488eb  jz      short loc_180048917
0x1800488ed  test    rdx, rdx
0x1800488f0  jz      short loc_180048902
0x1800488f2  mov     rax, [rdx]
0x1800488f5  mov     rcx, rdx
0x1800488f8  mov     rax, [rax+8]
0x1800488fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048901  nop
0x180048902  mov     rax, [rdi]
0x180048905  mov     [rsp+28h+arg_0], rax
0x18004890a  mov     [rdi], rbx
0x18004890d  lea     rcx, [rsp+28h+arg_0]
0x180048912  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048917  mov     rax, rdi
0x18004891a  mov     rbx, [rsp+28h+arg_8]
0x18004891f  add     rsp, 20h
0x180048923  pop     rdi
0x180048924  retn
```

# D3D12CoreCreateLayeredDevice

- ea: `0x180009210`
- end: `0x18000924a`
- name: `D3D12CoreCreateLayeredDevice`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall D3D12CoreCreateLayeredDevice(__int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                          + (unsigned int)tls_index)
                                                        + 8LL)
                                            + 112LL))(a1);
}

```

## disassembly

```asm
0x180009210  sub     rsp, 38h
0x180009214  mov     r10d, cs:_tls_index
0x18000921b  mov     rax, gs:58h
0x180009224  mov     r11d, 8
0x18000922a  mov     rax, [rax+r10*8]
0x18000922e  mov     r10, [rax+r11]
0x180009232  mov     rax, [r10+70h]
0x180009236  mov     r10, [rsp+38h+arg_20]
0x18000923b  mov     [rsp+38h+var_18], r10
0x180009240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009245  add     rsp, 38h
0x180009249  retn
```

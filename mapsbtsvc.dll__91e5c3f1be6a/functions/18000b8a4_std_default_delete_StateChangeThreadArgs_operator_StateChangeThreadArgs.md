# std::default_delete<StateChangeThreadArgs>::operator()(StateChangeThreadArgs *)

- ea: `0x18000b8a4`
- end: `0x18000b8cd`
- name: `??R?$default_delete@UStateChangeThreadArgs@@@std@@QEBAXPEAUStateChangeThreadArgs@@@Z`
- size: `41`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000b3c0`

## callees

- `0x180001e54`
- `0x180005b9c`
- `0x18000b8a4`

## pseudocode

```c
void __fastcall std::default_delete<StateChangeThreadArgs>::operator()(__int64 a1, _QWORD *a2)
{
  std::_Ref_count_base *v2; // rcx

  if ( a2 )
  {
    v2 = (std::_Ref_count_base *)a2[1];
    if ( v2 )
      std::_Ref_count_base::_Decwref(v2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x18000b8a4  test    rdx, rdx
0x18000b8a7  jz      short locret_18000B8CC
0x18000b8a9  push    rbx
0x18000b8aa  sub     rsp, 20h
0x18000b8ae  mov     rcx, [rdx+8]; this
0x18000b8b2  mov     rbx, rdx
0x18000b8b5  test    rcx, rcx
0x18000b8b8  jz      short loc_18000B8BF
0x18000b8ba  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000b8bf  mov     rcx, rbx; Block
0x18000b8c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b8c7  add     rsp, 20h
0x18000b8cb  pop     rbx
0x18000b8cc  retn
```

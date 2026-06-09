# _NOutermost::CDeviceChild::LUCCompleteLayerConstruction_::_1_::catch$2

- ea: `0x180013d30`
- end: `0x180013d58`
- name: `_NOutermost::CDeviceChild::LUCCompleteLayerConstruction_::_1_::catch$2`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall NOutermost::CDeviceChild::LUCCompleteLayerConstruction_::_1_::catch_2(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 104) = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x180013d30  mov     [rsp+arg_8], rdx
0x180013d35  push    rbp
0x180013d36  sub     rsp, 20h
0x180013d3a  mov     rbp, rdx
0x180013d3d  mov     rax, [rbp+20h]
0x180013d41  mov     ecx, [rax+8]
0x180013d44  mov     [rbp+68h], ecx
0x180013d47  mov     rax, 0
0x180013d51  add     rsp, 20h
0x180013d55  pop     rbp
0x180013d56  retn
```

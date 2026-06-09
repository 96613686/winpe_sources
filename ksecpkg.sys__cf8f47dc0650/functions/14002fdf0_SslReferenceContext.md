# SslReferenceContext

- ea: `0x14002fdf0`
- end: `0x14002fe31`
- name: `SslReferenceContext`
- size: `65`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140021bb0`
- `0x1400230a0`
- `0x140023430`
- `0x140028eb0`

## callees

- `0x140003e30`
- `0x140010240`

## pseudocode

```c
__int64 __fastcall SslReferenceContext(__int64 a1, unsigned __int8 a2)
{
  GetExternalSchannelAlgorithmsDeferred();
  return (*((__int64 (__fastcall **)(__int64, __int64, _QWORD))SslLsaKernelFunctions + 4))(a1 + 320, 1129075539, a2);
}

```

## disassembly

```asm
0x14002fdf0  mov     [rsp+arg_0], rbx
0x14002fdf5  push    rdi
0x14002fdf6  sub     rsp, 20h
0x14002fdfa  movzx   edi, dl
0x14002fdfd  mov     rbx, rcx
0x14002fe00  call    GetExternalSchannelAlgorithmsDeferred
0x14002fe05  mov     rax, cs:?SslLsaKernelFunctions@@3PEAU_SECPKG_KERNEL_FUNCTIONS@@EA; _SECPKG_KERNEL_FUNCTIONS * SslLsaKernelFunctions
0x14002fe0c  lea     rcx, [rbx+140h]
0x14002fe13  movzx   r8d, dil
0x14002fe17  mov     edx, 434C5353h
0x14002fe1c  mov     rax, [rax+20h]
0x14002fe20  call    _guard_dispatch_icall
0x14002fe25  mov     rbx, [rsp+28h+arg_0]
0x14002fe2a  add     rsp, 20h
0x14002fe2e  pop     rdi
0x14002fe2f  retn
```

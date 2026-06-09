# std::_Func_impl_no_alloc__lambda_96637bf5a23727b2d4024f5c4e2d8d53__void_MosHostGetDataAsyncResult_const_&_::_Copy

- ea: `0x1800070e0`
- end: `0x180007123`
- name: `std::_Func_impl_no_alloc__lambda_96637bf5a23727b2d4024f5c4e2d8d53__void_MosHostGetDataAsyncResult_const_&_::_Copy`
- size: `67`
- prototype: `char *__fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000210c`

## pseudocode

```c
char *__fastcall std::_Func_impl_no_alloc__lambda_96637bf5a23727b2d4024f5c4e2d8d53__void_MosHostGetDataAsyncResult_const___::_Copy(
        __int64 a1)
{
  char *result; // rax

  result = (char *)operator new(0x48u);
  *(_QWORD *)result = off_18000E0A8;
  *(_OWORD *)(result + 8) = *(_OWORD *)(a1 + 8);
  *(_OWORD *)(result + 24) = *(_OWORD *)(a1 + 24);
  *(_OWORD *)(result + 40) = *(_OWORD *)(a1 + 40);
  *(_OWORD *)(result + 56) = *(_OWORD *)(a1 + 56);
  return result;
}

```

## disassembly

```asm
0x1800070e0  push    rbx
0x1800070e2  sub     rsp, 20h
0x1800070e6  mov     rbx, rcx
0x1800070e9  mov     ecx, 48h ; 'H'; Size
0x1800070ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800070f3  lea     rcx, off_18000E0A8
0x1800070fa  mov     [rax], rcx
0x1800070fd  movups  xmm0, xmmword ptr [rbx+8]
0x180007101  movups  xmmword ptr [rax+8], xmm0
0x180007105  movups  xmm1, xmmword ptr [rbx+18h]
0x180007109  movups  xmmword ptr [rax+18h], xmm1
0x18000710d  movups  xmm0, xmmword ptr [rbx+28h]
0x180007111  movups  xmmword ptr [rax+28h], xmm0
0x180007115  movups  xmm1, xmmword ptr [rbx+38h]
0x180007119  movups  xmmword ptr [rax+38h], xmm1
0x18000711d  add     rsp, 20h
0x180007121  pop     rbx
0x180007122  retn
```

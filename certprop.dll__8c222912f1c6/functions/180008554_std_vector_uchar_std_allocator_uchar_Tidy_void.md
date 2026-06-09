# std::vector<uchar,std::allocator<uchar>>::_Tidy(void)

- ea: `0x180008554`
- end: `0x1800085bc`
- name: `?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ`
- size: `104`
- prototype: `void __fastcall(__int64)`
- caller_count: `23`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006f40`
- `0x1800075d0`
- `0x1800090c8`
- `0x18000971c`
- `0x18000e6b0`
- `0x180013ab0`
- `0x180013b14`
- `0x18001466c`
- `0x1800245c0`
- `0x1800245e0`
- `0x180024600`
- `0x180024660`
- `0x180024700`
- `0x1800248c0`
- `0x180024900`
- `0x180024a92`
- `0x180024bd5`
- `0x180024be7`
- `0x180024cca`
- `0x180024d24`
- `0x180024ef8`
- `0x180024f0a`
- `0x180024f2e`

## callees

- `0x180008554`
- `0x180010d5c`
- `0x180016114`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::_Tidy(__int64 a1)
{
  void *v2; // rcx
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // [rsp+30h] [rbp+8h] BYREF
  void *v5; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(void **)a1;
  if ( v2 )
  {
    v3 = *(_QWORD *)(a1 + 16) - (_QWORD)v2;
    v5 = v2;
    v4 = v3;
    if ( v3 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v5, &v4);
      v2 = v5;
    }
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180008554  push    rbx
0x180008556  sub     rsp, 20h
0x18000855a  mov     rbx, rcx
0x18000855d  mov     rcx, [rcx]; void *
0x180008560  test    rcx, rcx
0x180008563  jz      short loc_18000859B
0x180008565  mov     rdx, [rbx+10h]
0x180008569  sub     rdx, rcx; unsigned __int64
0x18000856c  mov     [rsp+28h+arg_8], rcx
0x180008571  mov     [rsp+28h+arg_0], rdx
0x180008576  cmp     rdx, 1000h
0x18000857d  jnb     short loc_1800085A1
0x18000857f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008584  mov     qword ptr [rbx], 0
0x18000858b  mov     qword ptr [rbx+8], 0
0x180008593  mov     qword ptr [rbx+10h], 0
0x18000859b  add     rsp, 20h
0x18000859f  pop     rbx
0x1800085a0  retn
0x1800085a1  lea     rdx, [rsp+28h+arg_0]; unsigned __int64 *
0x1800085a6  lea     rcx, [rsp+28h+arg_8]; void **
0x1800085ab  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800085b0  mov     rdx, [rsp+28h+arg_0]
0x1800085b5  mov     rcx, [rsp+28h+arg_8]
0x1800085ba  jmp     short loc_18000857F
```

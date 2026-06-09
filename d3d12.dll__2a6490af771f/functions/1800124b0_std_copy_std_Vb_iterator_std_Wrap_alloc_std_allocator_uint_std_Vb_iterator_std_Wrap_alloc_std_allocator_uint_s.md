# std::copy<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)

- ea: `0x1800124b0`
- end: `0x180012505`
- name: `??$copy@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800131b4`

## callees

- `0x180011ebc`

## pseudocode

```c
_OWORD *__fastcall std::copy<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>(
        _OWORD *a1,
        __int128 *a2,
        __int128 *a3,
        __int128 *a4)
{
  __int128 v5; // xmm1
  _OWORD *result; // rax
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  __int128 v8; // [rsp+30h] [rbp-38h] BYREF
  __int128 v9; // [rsp+40h] [rbp-28h] BYREF
  __int128 v10; // [rsp+50h] [rbp-18h] BYREF

  v5 = *a3;
  v7 = *a4;
  v9 = *a2;
  v8 = v5;
  std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>(
    (__int64)&v10,
    (__int64)&v9,
    (__int64)&v8,
    (__int64)&v7);
  result = a1;
  *a1 = v10;
  return result;
}

```

## disassembly

```asm
0x1800124b0  mov     rax, rsp
0x1800124b3  mov     [rax+8], rbx
0x1800124b7  push    rdi
0x1800124b8  sub     rsp, 60h
0x1800124bc  movaps  xmm0, xmmword ptr [r9]
0x1800124c0  mov     rbx, rcx
0x1800124c3  movaps  xmm1, xmmword ptr [r8]
0x1800124c7  lea     r9, [rax-48h]
0x1800124cb  movdqa  xmmword ptr [rax-48h], xmm0
0x1800124d0  lea     r8, [rax-38h]
0x1800124d4  movaps  xmm0, xmmword ptr [rdx]
0x1800124d7  lea     rcx, [rax-18h]
0x1800124db  lea     rdx, [rax-28h]
0x1800124df  movdqa  xmmword ptr [rax-28h], xmm0
0x1800124e4  movdqa  xmmword ptr [rax-38h], xmm1
0x1800124e9  call    ??$_Copy_vbool@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z; std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)
0x1800124ee  movups  xmm0, [rsp+68h+var_18]
0x1800124f3  mov     rax, rbx
0x1800124f6  movdqu  xmmword ptr [rbx], xmm0
0x1800124fa  mov     rbx, [rsp+68h+arg_0]
0x1800124ff  add     rsp, 60h
0x180012503  pop     rdi
0x180012504  retn
```

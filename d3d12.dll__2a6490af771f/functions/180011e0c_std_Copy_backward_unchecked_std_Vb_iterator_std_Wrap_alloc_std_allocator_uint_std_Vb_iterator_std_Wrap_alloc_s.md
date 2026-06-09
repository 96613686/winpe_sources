# std::_Copy_backward_unchecked<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)

- ea: `0x180011e0c`
- end: `0x180011eb5`
- name: `??$_Copy_backward_unchecked@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013004`

## callees

- `0x180011e0c`
- `0x180012544`

## pseudocode

```c
_OWORD *__fastcall std::_Copy_backward_unchecked<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>(
        _OWORD *a1,
        __int64 *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v4; // rdi
  _QWORD *v5; // r11
  __int64 v6; // rsi
  __int64 v7; // r10
  _DWORD *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r8
  bool v14; // zf
  _OWORD *result; // rax
  _QWORD v16[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = *a2;
  v5 = a4;
  v6 = a2[1];
  v7 = a3;
  while ( 1 )
  {
    v9 = *(_DWORD **)v7;
    if ( v4 == *(_QWORD *)v7 && v6 == *(_QWORD *)(v7 + 8) )
      break;
    v10 = *(_QWORD *)(v7 + 8);
    if ( v10 )
    {
      v11 = v10 - 1;
    }
    else
    {
      --v9;
      v11 = 31;
      *(_QWORD *)v7 = v9;
    }
    *(_QWORD *)(v7 + 8) = v11;
    v12 = v5[1];
    if ( v12 )
    {
      v13 = v12 - 1;
    }
    else
    {
      *v5 -= 4LL;
      v13 = 31;
    }
    v5[1] = v13;
    v16[0] = *v5;
    v14 = ((1 << v11) & *v9) == 0;
    v16[1] = v13;
    LOBYTE(v9) = !v14;
    std::_Vb_reference<std::_Wrap_alloc<std::allocator<unsigned int>>>::operator=(v16, v9);
  }
  result = a1;
  *a1 = *(_OWORD *)v5;
  return result;
}

```

## disassembly

```asm
0x180011e0c  mov     [rsp+arg_0], rbx
0x180011e11  mov     [rsp+arg_8], rsi
0x180011e16  push    rdi
0x180011e17  sub     rsp, 30h
0x180011e1b  mov     rdi, [rdx]
0x180011e1e  mov     r11, r9
0x180011e21  mov     rsi, [rdx+8]
0x180011e25  mov     r10, r8
0x180011e28  mov     rbx, rcx
0x180011e2b  mov     rdx, [r10]
0x180011e2e  cmp     rdi, rdx
0x180011e31  jnz     short loc_180011E39
0x180011e33  cmp     rsi, [r10+8]
0x180011e37  jz      short loc_180011E9A
0x180011e39  mov     rax, [r10+8]
0x180011e3d  test    rax, rax
0x180011e40  jz      short loc_180011E48
0x180011e42  lea     rcx, [rax-1]
0x180011e46  jmp     short loc_180011E54
0x180011e48  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180011e4c  mov     ecx, 1Fh
0x180011e51  mov     [r10], rdx
0x180011e54  mov     [r10+8], rcx
0x180011e58  mov     rax, [r11+8]
0x180011e5c  test    rax, rax
0x180011e5f  jz      short loc_180011E67
0x180011e61  lea     r8, [rax-1]
0x180011e65  jmp     short loc_180011E71
0x180011e67  add     qword ptr [r11], 0FFFFFFFFFFFFFFFCh
0x180011e6b  mov     r8d, 1Fh
0x180011e71  mov     [r11+8], r8
0x180011e75  mov     rax, [r11]
0x180011e78  mov     [rsp+38h+var_18], rax
0x180011e7d  mov     eax, 1
0x180011e82  shl     eax, cl
0x180011e84  lea     rcx, [rsp+38h+var_18]
0x180011e89  test    [rdx], eax
0x180011e8b  mov     [rsp+38h+var_10], r8
0x180011e90  setnz   dl
0x180011e93  call    ??4?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@QEAAAEAV01@_N@Z; std::_Vb_reference<std::_Wrap_alloc<std::allocator<uint>>>::operator=(bool)
0x180011e98  jmp     short loc_180011E2B
0x180011e9a  movaps  xmm0, xmmword ptr [r11]
0x180011e9e  mov     rax, rbx
0x180011ea1  mov     rsi, [rsp+38h+arg_8]
0x180011ea6  movdqu  xmmword ptr [rbx], xmm0
0x180011eaa  mov     rbx, [rsp+38h+arg_0]
0x180011eaf  add     rsp, 30h
0x180011eb3  pop     rdi
0x180011eb4  retn
```

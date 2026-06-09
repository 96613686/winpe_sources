# std::_Uninitialized_move<std::_Tgt_state_t<ushort const *> *,std::allocator<std::_Tgt_state_t<ushort const *>>>(std::_Tgt_state_t<ushort const *> * const,std::_Tgt_state_t<ushort const *> * const,std::_Tgt_state_t<ushort const *> *,std::allocator<std::_Tgt_state_t<ushort const *>> &)

- ea: `0x180015a74`
- end: `0x180015b31`
- name: `??$_Uninitialized_move@PEAV?$_Tgt_state_t@PEBG@std@@V?$allocator@V?$_Tgt_state_t@PEBG@std@@@2@@std@@YAPEAV?$_Tgt_state_t@PEBG@0@QEAV10@0PEAV10@AEAV?$allocator@V?$_Tgt_state_t@PEBG@std@@@0@@Z`
- size: `189`
- prototype: `_QWORD *__fastcall(__int64 *, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800141e4`

## callees

- `0x180015a74`

## pseudocode

```c
_QWORD *__fastcall std::_Uninitialized_move<std::_Tgt_state_t<unsigned short const *> *,std::allocator<std::_Tgt_state_t<unsigned short const *>>>(
        __int64 *a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 *v5; // r9
  __int64 *v6; // r11
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx

  v5 = a1;
  if ( a1 != a2 )
  {
    v6 = a1 + 1;
    v7 = a1 + 5;
    do
    {
      v8 = *v5;
      v5 += 8;
      *a3 = v8;
      v9 = v6[2];
      v10 = v6[1];
      v11 = *v6;
      v6[2] = 0;
      v6[1] = 0;
      *v6 = 0;
      v6 += 8;
      a3[1] = v11;
      a3[2] = v10;
      a3[3] = v9;
      v12 = *(v6 - 5);
      *(v6 - 5) = 0;
      a3[4] = v12;
      v13 = v7[2];
      v14 = v7[1];
      v15 = *v7;
      v7[2] = 0;
      v7[1] = 0;
      *v7 = 0;
      v7 += 8;
      a3[5] = v15;
      a3[6] = v14;
      a3[7] = v13;
      a3 += 8;
    }
    while ( v5 != a2 );
  }
  return a3;
}

```

## disassembly

```asm
0x180015a74  mov     [rsp+arg_0], rbx
0x180015a79  mov     [rsp+arg_8], rdi
0x180015a7e  mov     r10, r8
0x180015a81  mov     rdi, rdx
0x180015a84  mov     r9, rcx
0x180015a87  cmp     rcx, rdx
0x180015a8a  jz      loc_180015B23
0x180015a90  lea     r11, [rcx+8]
0x180015a94  lea     rbx, [rcx+28h]
0x180015a98  mov     rax, [r9]
0x180015a9b  add     r9, 40h ; '@'
0x180015a9f  mov     [r10], rax
0x180015aa2  mov     rdx, [r11+10h]
0x180015aa6  mov     rcx, [r11+8]
0x180015aaa  mov     rax, [r11]
0x180015aad  mov     qword ptr [r11+10h], 0
0x180015ab5  mov     qword ptr [r11+8], 0
0x180015abd  mov     qword ptr [r11], 0
0x180015ac4  lea     r11, [r11+40h]
0x180015ac8  mov     [r10+8], rax
0x180015acc  mov     [r10+10h], rcx
0x180015ad0  mov     [r10+18h], rdx
0x180015ad4  mov     rax, [r11-28h]
0x180015ad8  mov     qword ptr [r11-28h], 0
0x180015ae0  mov     [r10+20h], rax
0x180015ae4  mov     r8, [rbx+10h]
0x180015ae8  mov     rdx, [rbx+8]
0x180015aec  mov     rcx, [rbx]
0x180015aef  mov     qword ptr [rbx+10h], 0
0x180015af7  mov     qword ptr [rbx+8], 0
0x180015aff  mov     qword ptr [rbx], 0
0x180015b06  lea     rbx, [rbx+40h]
0x180015b0a  mov     [r10+28h], rcx
0x180015b0e  mov     [r10+30h], rdx
0x180015b12  mov     [r10+38h], r8
0x180015b16  add     r10, 40h ; '@'
0x180015b1a  cmp     r9, rdi
0x180015b1d  jnz     loc_180015A98
0x180015b23  mov     rbx, [rsp+arg_0]
0x180015b28  mov     rax, r10
0x180015b2b  mov     rdi, [rsp+arg_8]
0x180015b30  retn
```

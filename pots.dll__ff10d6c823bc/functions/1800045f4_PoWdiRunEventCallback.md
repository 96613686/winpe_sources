# PoWdiRunEventCallback

- ea: `0x1800045f4`
- end: `0x18000465e`
- name: `PoWdiRunEventCallback`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ac0`
- `0x180003d10`

## callees

- `0x1800045f4`
- `0x180005010`

## pseudocode

```c
_WORD *__fastcall PoWdiRunEventCallback(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v5; // r10
  _WORD *result; // rax
  _QWORD *v7; // rcx

  if ( a3 )
  {
    v5 = 0;
    while ( 1 )
    {
      result = *(_WORD **)(a1 + 24);
      v7 = *(_QWORD **)(a2 + 24 * v5);
      if ( result == (_WORD *)*v7 )
      {
        result = *(_WORD **)(a1 + 32);
        if ( result == (_WORD *)v7[1] )
        {
          result = *(_WORD **)(a2 + 24 * v5 + 8);
          if ( *(_WORD *)(a1 + 40) == *result )
            break;
        }
      }
      v5 = (unsigned int)(v5 + 1);
      if ( (unsigned int)v5 >= a3 )
        return result;
    }
    return (_WORD *)(*(__int64 (__fastcall **)(__int64, __int64))(a2 + 24 * v5 + 16))(a1, a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800045f4  test    r8d, r8d
0x1800045f7  jz      short locret_18000465D
0x1800045f9  mov     [rsp+arg_0], rbx
0x1800045fe  push    rdi
0x1800045ff  sub     rsp, 20h
0x180004603  mov     edi, r8d
0x180004606  mov     rbx, rdx
0x180004609  mov     r11, rcx
0x18000460c  xor     r10d, r10d
0x18000460f  mov     rax, [r11+18h]
0x180004613  lea     r8, [r10+r10*2]
0x180004617  mov     rcx, [rdx+r8*8]
0x18000461b  cmp     rax, [rcx]
0x18000461e  jnz     short loc_180004639
0x180004620  mov     rax, [r11+20h]
0x180004624  cmp     rax, [rcx+8]
0x180004628  jnz     short loc_180004639
0x18000462a  mov     rax, [rdx+r8*8+8]
0x18000462f  movzx   ecx, word ptr [rax]
0x180004632  cmp     [r11+28h], cx
0x180004637  jz      short loc_180004643
0x180004639  inc     r10d
0x18000463c  cmp     r10d, edi
0x18000463f  jb      short loc_18000460F
0x180004641  jmp     short loc_180004653
0x180004643  mov     rax, [rbx+r8*8+10h]
0x180004648  mov     rdx, r9
0x18000464b  mov     rcx, r11
0x18000464e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004653  mov     rbx, [rsp+28h+arg_0]
0x180004658  add     rsp, 20h
0x18000465c  pop     rdi
0x18000465d  retn
```
